# TagNavigationNode<ConfigPathTagNode,ConfigPathNode,ConfigPathNavigationTree>::~TagNavigationNode<ConfigPathTagNode,ConfigPathNode,ConfigPathNavigationTree>(void)

- ea: `0x1800043c4`
- end: `0x180004425`
- name: `??1?$TagNavigationNode@VConfigPathTagNode@@VConfigPathNode@@VConfigPathNavigationTree@@@@UEAA@XZ`
- size: `97`
- prototype: `__int64 __fastcall(ConfigPathNode *this)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000442c`
- `0x1800044a0`
- `0x180004600`

## callees

- `0x1800043c4`
- `0x18000446c`
- `0x18000573c`
- `0x180014010`

## pseudocode

```c
void __fastcall TagNavigationNode<ConfigPathTagNode,ConfigPathNode,ConfigPathNavigationTree>::~TagNavigationNode<ConfigPathTagNode,ConfigPathNode,ConfigPathNavigationTree>(
        ConfigPathNode *this)
{
  __int64 v1; // rbx
  void (__fastcall ***v3)(_QWORD, __int64); // rcx

  v1 = *((_QWORD *)this + 6);
  *(_QWORD *)this = &TagNavigationNode<ConfigPathTagNode,ConfigPathNode,ConfigPathNavigationTree>::`vftable';
  if ( v1 )
  {
    do
    {
      v3 = (void (__fastcall ***)(_QWORD, __int64))v1;
      v1 = *(_QWORD *)(v1 + 56) - 56LL;
      if ( v3 )
        (**v3)(v3, 1);
    }
    while ( v1 != *((_QWORD *)this + 6) );
  }
  ScopedPtr<PropertyNode>::Reset((char *)this + 88);
  ConfigPathNode::~ConfigPathNode(this);
}

```

## disassembly

```asm
0x1800043c4  mov     [rsp+arg_0], rbx
0x1800043c9  push    rdi
0x1800043ca  sub     rsp, 20h
0x1800043ce  mov     rbx, [rcx+30h]
0x1800043d2  lea     rax, ??_7?$TagNavigationNode@VConfigPathTagNode@@VConfigPathNode@@VConfigPathNavigationTree@@@@6B@; const TagNavigationNode<ConfigPathTagNode,ConfigPathNode,ConfigPathNavigationTree>::`vftable'
0x1800043d9  mov     [rcx], rax
0x1800043dc  mov     rdi, rcx
0x1800043df  test    rbx, rbx
0x1800043e2  jz      short loc_18000440A
0x1800043e4  mov     rcx, rbx
0x1800043e7  mov     rbx, [rbx+38h]
0x1800043eb  sub     rbx, 38h ; '8'
0x1800043ef  test    rcx, rcx
0x1800043f2  jz      short loc_180004404
0x1800043f4  mov     rax, [rcx]
0x1800043f7  mov     edx, 1
0x1800043fc  mov     rax, [rax]
0x1800043ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004404  cmp     rbx, [rdi+30h]
0x180004408  jnz     short loc_1800043E4
0x18000440a  lea     rcx, [rdi+58h]
0x18000440e  call    ?Reset@?$ScopedPtr@VPropertyNode@@@@QEAAXXZ; ScopedPtr<PropertyNode>::Reset(void)
0x180004413  mov     rcx, rdi; this
0x180004416  mov     rbx, [rsp+28h+arg_0]
0x18000441b  add     rsp, 20h
0x18000441f  pop     rdi
0x180004420  jmp     ??1ConfigPathNode@@UEAA@XZ; ConfigPathNode::~ConfigPathNode(void)
```
