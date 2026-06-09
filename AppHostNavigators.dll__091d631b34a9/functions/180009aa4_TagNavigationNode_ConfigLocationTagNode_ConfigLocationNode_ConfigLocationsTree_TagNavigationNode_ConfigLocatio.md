# TagNavigationNode<ConfigLocationTagNode,ConfigLocationNode,ConfigLocationsTree>::~TagNavigationNode<ConfigLocationTagNode,ConfigLocationNode,ConfigLocationsTree>(void)

- ea: `0x180009aa4`
- end: `0x180009b08`
- name: `??1?$TagNavigationNode@VConfigLocationTagNode@@VConfigLocationNode@@VConfigLocationsTree@@@@UEAA@XZ`
- size: `100`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180009b1c`
- `0x180009c00`

## callees

- `0x18000573c`
- `0x180009aa4`
- `0x180014010`

## pseudocode

```c
void **__fastcall TagNavigationNode<ConfigLocationTagNode,ConfigLocationNode,ConfigLocationsTree>::~TagNavigationNode<ConfigLocationTagNode,ConfigLocationNode,ConfigLocationsTree>(
        _QWORD *a1)
{
  __int64 v1; // rbx
  void (__fastcall ***v3)(_QWORD, __int64); // rcx
  void **result; // rax

  v1 = a1[4];
  *a1 = &TagNavigationNode<ConfigLocationTagNode,ConfigLocationNode,ConfigLocationsTree>::`vftable';
  if ( v1 )
  {
    do
    {
      v3 = (void (__fastcall ***)(_QWORD, __int64))v1;
      v1 = *(_QWORD *)(v1 + 40) - 40LL;
      if ( v3 )
        (**v3)(v3, 1);
    }
    while ( v1 != a1[4] );
  }
  ScopedPtr<PropertyNode>::Reset(a1 + 9);
  result = &NavigationNodeBase::`vftable';
  *a1 = &NavigationNodeBase::`vftable';
  return result;
}

```

## disassembly

```asm
0x180009aa4  mov     [rsp+arg_0], rbx
0x180009aa9  push    rdi
0x180009aaa  sub     rsp, 20h
0x180009aae  mov     rbx, [rcx+20h]
0x180009ab2  lea     rax, ??_7?$TagNavigationNode@VConfigLocationTagNode@@VConfigLocationNode@@VConfigLocationsTree@@@@6B@; const TagNavigationNode<ConfigLocationTagNode,ConfigLocationNode,ConfigLocationsTree>::`vftable'
0x180009ab9  mov     [rcx], rax
0x180009abc  mov     rdi, rcx
0x180009abf  test    rbx, rbx
0x180009ac2  jz      short loc_180009AEA
0x180009ac4  mov     rcx, rbx
0x180009ac7  mov     rbx, [rbx+28h]
0x180009acb  sub     rbx, 28h ; '('
0x180009acf  test    rcx, rcx
0x180009ad2  jz      short loc_180009AE4
0x180009ad4  mov     rax, [rcx]
0x180009ad7  mov     edx, 1
0x180009adc  mov     rax, [rax]
0x180009adf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ae4  cmp     rbx, [rdi+20h]
0x180009ae8  jnz     short loc_180009AC4
0x180009aea  lea     rcx, [rdi+48h]
0x180009aee  call    ?Reset@?$ScopedPtr@VPropertyNode@@@@QEAAXXZ; ScopedPtr<PropertyNode>::Reset(void)
0x180009af3  mov     rbx, [rsp+28h+arg_0]
0x180009af8  lea     rax, ??_7NavigationNodeBase@@6B@; const NavigationNodeBase::`vftable'
0x180009aff  mov     [rdi], rax
0x180009b02  add     rsp, 20h
0x180009b06  pop     rdi
0x180009b07  retn
```
