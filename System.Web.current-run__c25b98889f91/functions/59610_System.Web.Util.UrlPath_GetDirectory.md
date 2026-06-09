# System.Web.Util.UrlPath::GetDirectory

- ea: `0x59610`
- end: `0x59695`
- name: `System.Web.Util.UrlPath::GetDirectory`
- size: `133`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x8e8b0`
- `0x16ccf0`

## callees

- `0x34f20`
- `0x34fa0`
- `0x59610`

## string_xrefs

- `0x59618`: `Empty_path_has_no_directory`
- `0x5963e`: `Path_must_be_rooted`
- `0x59670`: `Path_must_be_rooted`

## pseudocode

```c

```

## disassembly

```asm
0x59610  ldarg.0
0x59611  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x59616  brfalse.s loc_59628
0x59618  ldstr    aEmptyPathHasNo// "Empty_path_has_no_directory"
0x5961d  call     string System.Web.SR::GetString(string name)
0x59622  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x59627  throw
0x59628  ldarg.0
0x59629  ldc.i4.0
0x5962a  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x5962f  ldc.i4.s 0x2F
0x59631  beq.s    loc_59658
0x59633  ldarg.0
0x59634  ldc.i4.0
0x59635  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x5963a  ldc.i4.s 0x7E
0x5963c  beq.s    loc_59658
0x5963e  ldstr    aPathMustBeRoot// "Path_must_be_rooted"
0x59643  ldc.i4.1
0x59644  newarr   [mscorlib]System.Object
0x59649  dup
0x5964a  ldc.i4.0
0x5964b  ldarg.0
0x5964c  stelem.ref
0x5964d  call     string System.Web.SR::GetString(string name, object[] args)
0x59652  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x59657  throw
0x59658  ldarg.0
0x59659  callvirt instance int32 [mscorlib]System.String::get_Length()
0x5965e  ldc.i4.1
0x5965f  bne.un.s loc_59663
0x59661  ldarg.0
0x59662  ret
0x59663  ldarg.0
0x59664  ldc.i4.s 0x2F
0x59666  callvirt instance int32 [mscorlib]System.String::LastIndexOf(char)
0x5966b  stloc.0
0x5966c  ldloc.0
0x5966d  ldc.i4.0
0x5966e  bge.s    loc_5968A
0x59670  ldstr    aPathMustBeRoot// "Path_must_be_rooted"
0x59675  ldc.i4.1
0x59676  newarr   [mscorlib]System.Object
0x5967b  dup
0x5967c  ldc.i4.0
0x5967d  ldarg.0
0x5967e  stelem.ref
0x5967f  call     string System.Web.SR::GetString(string name, object[] args)
0x59684  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x59689  throw
0x5968a  ldarg.0
0x5968b  ldc.i4.0
0x5968c  ldloc.0
0x5968d  ldc.i4.1
0x5968e  add
0x5968f  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x59694  ret
```
