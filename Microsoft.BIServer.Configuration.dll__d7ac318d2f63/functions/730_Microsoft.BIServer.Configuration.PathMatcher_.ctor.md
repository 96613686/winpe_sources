# Microsoft.BIServer.Configuration.PathMatcher::.ctor

- ea: `0x730`
- end: `0x762`
- name: `Microsoft.BIServer.Configuration.PathMatcher::.ctor`
- size: `50`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x130`

## callees

- `0x730`

## pseudocode

```c

```

## disassembly

```asm
0x730  ldarg.0
0x731  call     instance void [mscorlib]System.Object::.ctor()
0x736  ldarg.1
0x737  brtrue.s loc_744
0x739  ldstr    aPath// "path"
0x73e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x743  throw
0x744  ldstr    a0// "^({0})"
0x749  ldarg.1
0x74a  call     string [mscorlib]System.String::Format(string, object)
0x74f  stloc.0
0x750  ldarg.0
0x751  ldloc.0
0x752  ldc.i4   0x201
0x757  newobj   instance void [System]System.Text.RegularExpressions.Regex::.ctor(string, valuetype [System]System.Text.RegularExpressions.RegexOptions)
0x75c  stfld    class [System]System.Text.RegularExpressions.Regex Microsoft.BIServer.Configuration.PathMatcher::_urlRegex
0x761  ret
```
