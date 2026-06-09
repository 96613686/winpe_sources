# System.Deployment.Application.Logger::Serialize_0

- ea: `0x17ee0`
- end: `0x17f0f`
- name: `System.Deployment.Application.Logger::Serialize_0`
- size: `47`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x203a0`

## callees

- `0x17ee0`

## string_xrefs

- `0x17ef0`: `ResponseUri=`

## pseudocode

```c

```

## disassembly

```asm
0x17ee0  ldarg.0
0x17ee1  brtrue.s loc_17EE9
0x17ee3  ldstr    asc_2F208// ""
0x17ee8  ret
0x17ee9  ldstr    asc_2F208// ""
0x17eee  stloc.0
0x17eef  ldloc.0
0x17ef0  ldstr    aResponseuri// "ResponseUri="
0x17ef5  ldarg.0
0x17ef6  callvirt instance class [System]System.Uri [System]System.Net.WebResponse::get_ResponseUri()
0x17efb  dup
0x17efc  brtrue.s loc_17F02
0x17efe  pop
0x17eff  ldnull
0x17f00  br.s     loc_17F07
0x17f02  callvirt instance string [mscorlib]System.Object::ToString()
0x17f07  call     string [mscorlib]System.String::Concat(string, string, string)
0x17f0c  stloc.0
0x17f0d  ldloc.0
0x17f0e  ret
```
