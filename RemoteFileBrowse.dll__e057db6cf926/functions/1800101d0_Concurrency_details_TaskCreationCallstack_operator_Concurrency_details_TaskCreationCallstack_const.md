# Concurrency::details::_TaskCreationCallstack::operator=(Concurrency::details::_TaskCreationCallstack const &)

- ea: `0x1800101d0`
- end: `0x180010283`
- name: `??4_TaskCreationCallstack@details@Concurrency@@QEAAAEAV012@AEBV012@@Z`
- size: `179`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000e664`
- `0x18000f0a8`

## callees

- `0x180002db8`
- `0x1800101d0`
- `0x18001187c`

## pseudocode

```c
_QWORD *__fastcall Concurrency::details::_TaskCreationCallstack::operator=(_QWORD *a1, _QWORD *a2)
{
  void **v2; // r14
  char *v4; // r12
  char *v5; // rdi
  unsigned __int64 v6; // rbx
  char *v7; // rdx
  size_t v8; // rbx
  unsigned __int64 v10; // rbp

  v2 = (void **)(a1 + 1);
  *a1 = *a2;
  if ( a1 + 1 != a2 + 1 )
  {
    v4 = (char *)a2[1];
    v5 = (char *)*v2;
    v6 = (__int64)(a2[2] - (_QWORD)v4) >> 3;
    if ( v6 <= (__int64)(a1[3] - a1[1]) >> 3 )
    {
      v10 = (__int64)(a1[2] - (_QWORD)v5) >> 3;
      if ( v6 > v10 )
      {
        memmove_0(*v2, v4, 8 * v10);
        v5 = (char *)v2[1];
        v7 = &v4[8 * v10];
        v6 -= v10;
        goto LABEL_5;
      }
    }
    else
    {
      std::vector<void *>::_Clear_and_reserve_geometric(a1 + 1, v6);
      v5 = (char *)*v2;
    }
    v7 = v4;
LABEL_5:
    v8 = 8 * v6;
    memmove_0(v5, v7, v8);
    v2[1] = &v5[v8];
  }
  return a1;
}

```

## disassembly

```asm
0x1800101d0  push    rbx
0x1800101d2  push    rbp
0x1800101d3  push    rsi
0x1800101d4  push    rdi
0x1800101d5  push    r12
0x1800101d7  push    r14
0x1800101d9  push    r15
0x1800101db  sub     rsp, 20h
0x1800101df  mov     rax, [rdx]
0x1800101e2  lea     rbx, [rdx+8]
0x1800101e6  lea     r14, [rcx+8]
0x1800101ea  mov     [rcx], rax
0x1800101ed  mov     r15, rcx
0x1800101f0  cmp     r14, rbx
0x1800101f3  jz      short loc_18001023E
0x1800101f5  mov     r12, [rbx]
0x1800101f8  mov     rbx, [rbx+8]
0x1800101fc  mov     rdi, [r14]
0x1800101ff  sub     rbx, r12
0x180010202  mov     rax, [r14+10h]
0x180010206  sub     rax, rdi
0x180010209  sar     rbx, 3
0x18001020d  sar     rax, 3
0x180010211  cmp     rbx, rax
0x180010214  jbe     short loc_180010250
0x180010216  mov     rdx, rbx
0x180010219  mov     rcx, r14
0x18001021c  call    ?_Clear_and_reserve_geometric@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAX_K@Z; std::vector<void *>::_Clear_and_reserve_geometric(unsigned __int64)
0x180010221  mov     rdi, [r14]
0x180010224  mov     rdx, r12; Src
0x180010227  shl     rbx, 3
0x18001022b  mov     rcx, rdi; void *
0x18001022e  mov     r8, rbx; Size
0x180010231  call    memmove_0
0x180010236  lea     rax, [rbx+rdi]
0x18001023a  mov     [r14+8], rax
0x18001023e  mov     rax, r15
0x180010241  add     rsp, 20h
0x180010245  pop     r15
0x180010247  pop     r14
0x180010249  pop     r12
0x18001024b  pop     rdi
0x18001024c  pop     rsi
0x18001024d  pop     rbp
0x18001024e  pop     rbx
0x18001024f  retn
0x180010250  mov     rbp, [r14+8]
0x180010254  sub     rbp, rdi
0x180010257  sar     rbp, 3
0x18001025b  cmp     rbx, rbp
0x18001025e  jbe     short loc_180010224
0x180010260  lea     rsi, ds:0[rbp*8]
0x180010268  mov     rdx, r12; Src
0x18001026b  mov     r8, rsi; Size
0x18001026e  mov     rcx, rdi; void *
0x180010271  call    memmove_0
0x180010276  mov     rdi, [r14+8]
0x18001027a  lea     rdx, [rsi+r12]
0x18001027e  sub     rbx, rbp
0x180010281  jmp     short loc_180010227
```
