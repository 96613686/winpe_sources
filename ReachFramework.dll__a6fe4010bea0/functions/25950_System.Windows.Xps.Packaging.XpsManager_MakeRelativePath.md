# System.Windows.Xps.Packaging.XpsManager::MakeRelativePath

- ea: `0x25950`
- end: `0x259a5`
- name: `System.Windows.Xps.Packaging.XpsManager::MakeRelativePath`
- size: `85`
- prototype: ``
- caller_count: `14`
- callee_count: `1`
- tags: ``

## callers

- `0x20d00`
- `0x21370`
- `0x213f0`
- `0x217a0`
- `0x22190`
- `0x22200`
- `0x22330`
- `0x22d40`
- `0x22dc0`
- `0x22e80`
- `0x22f00`
- `0x24ac0`
- `0x24b60`
- `0x26450`

## callees

- `0x25950`

## pseudocode

```c

```

## disassembly

```asm
0x25950  ldstr    aHttpDummy// "http://dummy"
0x25955  newobj   instance void [System]System.Uri::.ctor(string)
0x2595a  stloc.0
0x2595b  ldarg.0
0x2595c  callvirt instance bool [System]System.Uri::get_IsAbsoluteUri()
0x25961  brtrue.s loc_2596C
0x25963  ldloc.0
0x25964  ldarg.0
0x25965  newobj   instance void [System]System.Uri::.ctor(class [System]System.Uri, class [System]System.Uri)
0x2596a  starg.s  0
0x2596c  ldarg.1
0x2596d  callvirt instance bool [System]System.Uri::get_IsAbsoluteUri()
0x25972  brtrue.s loc_2597D
0x25974  ldloc.0
0x25975  ldarg.1
0x25976  newobj   instance void [System]System.Uri::.ctor(class [System]System.Uri, class [System]System.Uri)
0x2597b  starg.s  1
0x2597d  ldarg.0
0x2597e  ldarg.1
0x2597f  callvirt instance class [System]System.Uri [System]System.Uri::MakeRelativeUri(class [System]System.Uri)
0x25984  stloc.1
0x25985  ldloc.1
0x25986  ldc.i4   0x80000000
0x2598b  ldc.i4.3
0x2598c  callvirt instance string [System]System.Uri::GetComponents(valuetype [System]System.UriComponents, valuetype [System]System.UriFormat)
0x25991  ldc.i4.0
0x25992  newobj   instance void [System]System.Uri::.ctor(string, valuetype [System]System.UriKind)
0x25997  stloc.2
0x25998  ldloc.2
0x25999  ldc.i4   0x80000000
0x2599e  ldc.i4.1
0x2599f  callvirt instance string [System]System.Uri::GetComponents(valuetype [System]System.UriComponents, valuetype [System]System.UriFormat)
0x259a4  ret
```
