Rego is an old query language. It extends Datalog to support structured document models such as JSON. Rego queries are assertions on data stored in OPA. These queries can be used to define policies that enumerate instances of data that violate the expected state of the system.

i)   Use Rego for defining policy that is easy to read and write. 
ii)  Rego focuses on providing powerful support for referencing nested documents and ensuring that  queries are correct and unambiguous.
iii) Rego is declarative so policy authors can focus on what queries should return rather than how queries should be executed. These queries are simpler and more concise than the equivalent in an imperative language.
iv)  Like other applications which support declarative query languages, OPA is able to optimize queries to improve performance.



# Basics
The simplest rule is a single expression and is defined in terms of a Scalar Value:
pi := 3.14159



We can generalize the example above with a rule that defines a set document instead of a boolean document:

package play

sites = [{"name": "prod"}, {"name": "smoke1"}, {"name": "dev"}]

hello[name] {
    name := sites[_].name 
}

p { q["prod"] }
 
o/p --->
{
 "hello": [
        "dev",
        "prod",
        "smoke1"
    ]
}