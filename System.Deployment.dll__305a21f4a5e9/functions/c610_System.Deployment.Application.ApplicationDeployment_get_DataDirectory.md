# System.Deployment.Application.ApplicationDeployment::get_DataDirectory

- ea: `0xc610`
- end: `0xc62c`
- name: `System.Deployment.Application.ApplicationDeployment::get_DataDirectory`
- size: `28`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0xc610`

## string_xrefs

- `0xc615`: `DataDirectory`

## pseudocode

```c

```

## disassembly

```asm
0xc610  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0xc615  ldstr    aDatadirectory// "DataDirectory"
0xc61a  callvirt instance object [mscorlib]System.AppDomain::GetData(string)
0xc61f  stloc.0
0xc620  ldloc.0
0xc621  brtrue.s loc_C625
0xc623  ldnull
0xc624  ret
0xc625  ldloc.0
0xc626  callvirt instance string [mscorlib]System.Object::ToString()
0xc62b  ret
```
