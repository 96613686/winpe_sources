# NavigationNodeBase::ComparePositionsAtSameDepth(NavigationNodeBase *,NavigationNodeBase *,long)

- ea: `0x1800110dc`
- end: `0x18001116a`
- name: `?ComparePositionsAtSameDepth@NavigationNodeBase@@CAJPEAV1@0J@Z`
- size: `142`
- prototype: `__int64 __fastcall(struct NavigationNodeBase *, struct NavigationNodeBase *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180011064`

## callees

- `0x1800110dc`
- `0x180011170`
- `0x180012f3c`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall NavigationNodeBase::ComparePositionsAtSameDepth(
        struct NavigationNodeBase *a1,
        struct NavigationNodeBase *a2,
        unsigned int a3)
{
  unsigned int v6; // eax
  struct NavigationNodeBase *v7; // rax
  int pExceptionObject; // [rsp+30h] [rbp+8h] BYREF

  while ( a1 != a2 )
  {
    v6 = NavigationNodeBase::CompareSiblings(a1, a2);
    if ( v6 )
      a3 = v6;
    a1 = (struct NavigationNodeBase *)(*(__int64 (__fastcall **)(struct NavigationNodeBase *))(*(_QWORD *)a1 + 16LL))(a1);
    v7 = (struct NavigationNodeBase *)(*(__int64 (__fastcall **)(struct NavigationNodeBase *))(*(_QWORD *)a2 + 16LL))(a2);
    a2 = v7;
    if ( !a1 )
    {
      if ( v7 )
      {
LABEL_8:
        pExceptionObject = -2147024809;
        throw (long *)&pExceptionObject;
      }
      return a3;
    }
    if ( !v7 )
      goto LABEL_8;
  }
  return a3;
}

```

## disassembly

```asm
0x1800110dc  mov     [rsp+arg_8], rbx
0x1800110e1  mov     [rsp+arg_10], rsi
0x1800110e6  push    rdi
0x1800110e7  sub     rsp, 20h
0x1800110eb  mov     edi, r8d
0x1800110ee  mov     rbx, rdx
0x1800110f1  mov     rsi, rcx
0x1800110f4  cmp     rsi, rbx
0x1800110f7  jz      short loc_180011158
0x1800110f9  mov     rdx, rbx; struct NavigationNodeBase *
0x1800110fc  mov     rcx, rsi; struct NavigationNodeBase *
0x1800110ff  call    ?CompareSiblings@NavigationNodeBase@@CAJPEAV1@0@Z; NavigationNodeBase::CompareSiblings(NavigationNodeBase *,NavigationNodeBase *)
0x180011104  test    eax, eax
0x180011106  mov     rcx, rsi
0x180011109  cmovnz  edi, eax
0x18001110c  mov     rax, [rsi]
0x18001110f  mov     rax, [rax+10h]
0x180011113  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011118  mov     rsi, rax
0x18001111b  mov     rcx, rbx
0x18001111e  mov     rax, [rbx]
0x180011121  mov     rax, [rax+10h]
0x180011125  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001112a  mov     rbx, rax
0x18001112d  test    rsi, rsi
0x180011130  jz      short loc_180011139
0x180011132  test    rax, rax
0x180011135  jnz     short loc_1800110F4
0x180011137  jmp     short loc_18001113E
0x180011139  test    rax, rax
0x18001113c  jz      short loc_180011158
0x18001113e  lea     rdx, _TI1J; pThrowInfo
0x180011145  mov     [rsp+28h+pExceptionObject], 80070057h
0x18001114d  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180011152  call    _CxxThrowException_0
0x180011158  mov     rbx, [rsp+28h+arg_8]
0x18001115d  mov     eax, edi
0x18001115f  mov     rsi, [rsp+28h+arg_10]
0x180011164  add     rsp, 20h
0x180011168  pop     rdi
0x180011169  retn
```
