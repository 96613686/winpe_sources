# TagNavigationNode<ConfigTagNode,ConfigNavigationNode,ConfigTreeBase>::~TagNavigationNode<ConfigTagNode,ConfigNavigationNode,ConfigTreeBase>(void)

- ea: `0x18000a858`
- end: `0x18000a8bc`
- name: `??1?$TagNavigationNode@VConfigTagNode@@VConfigNavigationNode@@VConfigTreeBase@@@@UEAA@XZ`
- size: `100`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000a8d4`
- `0x18000a960`
- `0x18000aa00`

## callees

- `0x18000573c`
- `0x18000a858`
- `0x180014010`

## pseudocode

```c
void **__fastcall TagNavigationNode<ConfigTagNode,ConfigNavigationNode,ConfigTreeBase>::~TagNavigationNode<ConfigTagNode,ConfigNavigationNode,ConfigTreeBase>(
        _QWORD *a1)
{
  __int64 v1; // rbx
  void (__fastcall ***v3)(_QWORD, __int64); // rcx
  void **result; // rax

  v1 = a1[4];
  *a1 = &TagNavigationNode<ConfigTagNode,ConfigNavigationNode,ConfigTreeBase>::`vftable';
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
0x18000a858  mov     [rsp+arg_0], rbx
0x18000a85d  push    rdi
0x18000a85e  sub     rsp, 20h
0x18000a862  mov     rbx, [rcx+20h]
0x18000a866  lea     rax, ??_7?$TagNavigationNode@VConfigTagNode@@VConfigNavigationNode@@VConfigTreeBase@@@@6B@; const TagNavigationNode<ConfigTagNode,ConfigNavigationNode,ConfigTreeBase>::`vftable'
0x18000a86d  mov     [rcx], rax
0x18000a870  mov     rdi, rcx
0x18000a873  test    rbx, rbx
0x18000a876  jz      short loc_18000A89E
0x18000a878  mov     rcx, rbx
0x18000a87b  mov     rbx, [rbx+28h]
0x18000a87f  sub     rbx, 28h ; '('
0x18000a883  test    rcx, rcx
0x18000a886  jz      short loc_18000A898
0x18000a888  mov     rax, [rcx]
0x18000a88b  mov     edx, 1
0x18000a890  mov     rax, [rax]
0x18000a893  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a898  cmp     rbx, [rdi+20h]
0x18000a89c  jnz     short loc_18000A878
0x18000a89e  lea     rcx, [rdi+48h]
0x18000a8a2  call    ?Reset@?$ScopedPtr@VPropertyNode@@@@QEAAXXZ; ScopedPtr<PropertyNode>::Reset(void)
0x18000a8a7  mov     rbx, [rsp+28h+arg_0]
0x18000a8ac  lea     rax, ??_7NavigationNodeBase@@6B@; const NavigationNodeBase::`vftable'
0x18000a8b3  mov     [rdi], rax
0x18000a8b6  add     rsp, 20h
0x18000a8ba  pop     rdi
0x18000a8bb  retn
```
