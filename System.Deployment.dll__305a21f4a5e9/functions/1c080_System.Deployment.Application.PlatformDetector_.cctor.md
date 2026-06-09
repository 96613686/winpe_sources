# System.Deployment.Application.PlatformDetector::.cctor

- ea: `0x1c080`
- end: `0x1c1aa`
- name: `System.Deployment.Application.PlatformDetector::.cctor`
- size: `298`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x2c190`
- `0x2c1b0`

## string_xrefs

- `0x1c0d7`: `communications`

## pseudocode

```c

```

## disassembly

```asm
0x1c080  ldc.i4.s 0xE
0x1c082  newarr   Suite
0x1c087  dup
0x1c088  ldc.i4.0
0x1c089  ldstr    aServer// "server"
0x1c08e  ldc.i4   0x80000000
0x1c093  newobj   instance void Suite::.ctor(string Name, unsigned int32 Mask)
0x1c098  stelem.ref
0x1c099  dup
0x1c09a  ldc.i4.1
0x1c09b  ldstr    aWorkstation// "workstation"
0x1c0a0  ldc.i4   0x40000000
0x1c0a5  newobj   instance void Suite::.ctor(string Name, unsigned int32 Mask)
0x1c0aa  stelem.ref
0x1c0ab  dup
0x1c0ac  ldc.i4.2
0x1c0ad  ldstr    aSmallbusiness// "smallbusiness"
0x1c0b2  ldc.i4.1
0x1c0b3  newobj   instance void Suite::.ctor(string Name, unsigned int32 Mask)
0x1c0b8  stelem.ref
0x1c0b9  dup
0x1c0ba  ldc.i4.3
0x1c0bb  ldstr    aEnterprise// "enterprise"
0x1c0c0  ldc.i4.2
0x1c0c1  newobj   instance void Suite::.ctor(string Name, unsigned int32 Mask)
0x1c0c6  stelem.ref
0x1c0c7  dup
0x1c0c8  ldc.i4.4
0x1c0c9  ldstr    aBackoffice// "backoffice"
0x1c0ce  ldc.i4.4
0x1c0cf  newobj   instance void Suite::.ctor(string Name, unsigned int32 Mask)
0x1c0d4  stelem.ref
0x1c0d5  dup
0x1c0d6  ldc.i4.5
0x1c0d7  ldstr    aCommunications// "communications"
0x1c0dc  ldc.i4.8
0x1c0dd  newobj   instance void Suite::.ctor(string Name, unsigned int32 Mask)
0x1c0e2  stelem.ref
0x1c0e3  dup
0x1c0e4  ldc.i4.6
0x1c0e5  ldstr    aTerminal// "terminal"
0x1c0ea  ldc.i4.s 0x10
0x1c0ec  newobj   instance void Suite::.ctor(string Name, unsigned int32 Mask)
0x1c0f1  stelem.ref
0x1c0f2  dup
0x1c0f3  ldc.i4.7
0x1c0f4  ldstr    aSmallbusinessr// "smallbusinessRestricted"
0x1c0f9  ldc.i4.s 0x20
0x1c0fb  newobj   instance void Suite::.ctor(string Name, unsigned int32 Mask)
0x1c100  stelem.ref
0x1c101  dup
0x1c102  ldc.i4.8
0x1c103  ldstr    aEmbeddednt// "embeddednt"
0x1c108  ldc.i4.s 0x40
0x1c10a  newobj   instance void Suite::.ctor(string Name, unsigned int32 Mask)
0x1c10f  stelem.ref
0x1c110  dup
0x1c111  ldc.i4.s 9
0x1c113  ldstr    aDatacenter// "datacenter"
0x1c118  ldc.i4   0x80
0x1c11d  newobj   instance void Suite::.ctor(string Name, unsigned int32 Mask)
0x1c122  stelem.ref
0x1c123  dup
0x1c124  ldc.i4.s 0xA
0x1c126  ldstr    aSingleuserts// "singleuserts"
0x1c12b  ldc.i4   0x100
0x1c130  newobj   instance void Suite::.ctor(string Name, unsigned int32 Mask)
0x1c135  stelem.ref
0x1c136  dup
0x1c137  ldc.i4.s 0xB
0x1c139  ldstr    aPersonal// "personal"
0x1c13e  ldc.i4   0x200
0x1c143  newobj   instance void Suite::.ctor(string Name, unsigned int32 Mask)
0x1c148  stelem.ref
0x1c149  dup
0x1c14a  ldc.i4.s 0xC
0x1c14c  ldstr    aBlade// "blade"
0x1c151  ldc.i4   0x400
0x1c156  newobj   instance void Suite::.ctor(string Name, unsigned int32 Mask)
0x1c15b  stelem.ref
0x1c15c  dup
0x1c15d  ldc.i4.s 0xD
0x1c15f  ldstr    aEmbeddedrestri// "embeddedrestricted"
0x1c164  ldc.i4   0x800
0x1c169  newobj   instance void Suite::.ctor(string Name, unsigned int32 Mask)
0x1c16e  stelem.ref
0x1c16f  stsfld   class Suite[] System.Deployment.Application.PlatformDetector::Suites
0x1c174  ldc.i4.3
0x1c175  newarr   Product
0x1c17a  dup
0x1c17b  ldc.i4.0
0x1c17c  ldstr    aWorkstation// "workstation"
0x1c181  ldc.i4.1
0x1c182  newobj   instance void Product::.ctor(string Name, unsigned int32 Mask)
0x1c187  stelem.ref
0x1c188  dup
0x1c189  ldc.i4.1
0x1c18a  ldstr    aDomaincontroll// "domainController"
0x1c18f  ldc.i4.2
0x1c190  newobj   instance void Product::.ctor(string Name, unsigned int32 Mask)
0x1c195  stelem.ref
0x1c196  dup
0x1c197  ldc.i4.2
0x1c198  ldstr    aServer// "server"
0x1c19d  ldc.i4.3
0x1c19e  newobj   instance void Product::.ctor(string Name, unsigned int32 Mask)
0x1c1a3  stelem.ref
0x1c1a4  stsfld   class Product[] System.Deployment.Application.PlatformDetector::Products
0x1c1a9  ret
```
