# wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180009478`
- end: `0x18000954a`
- name: `?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `210`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000937c`
- `0x1800097d0`

## callees

- `0x18000201a`
- `0x180002084`
- `0x180009478`
- `0x180009a7c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800094eb`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000951d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800094eb`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000951d`

## pseudocode

```c
void __fastcall wil::details_abi::SubscriptionList::SubscribeUnderLock(
        wil::details_abi::SubscriptionList *this,
        struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **a2,
        void (*a3)(void *),
        void *a4)
{
  wil::details_abi::heap_buffer *v4; // rbx
  __int64 v5; // rcx
  struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *v6; // rax
  unsigned __int64 v9; // r10
  struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *v11; // rdx
  __int64 v12; // rax
  __int64 v13; // rdx
  _QWORD *v14; // rcx
  size_t v15; // r8
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8

  v4 = (wil::details_abi::SubscriptionList *)((char *)this + 40);
  *a2 = 0;
  v5 = *((_QWORD *)this + 5);
  v6 = 0;
  v9 = (unsigned __int64)(*((_QWORD *)v4 + 1) - v5) >> 4;
  if ( !v9 )
  {
LABEL_4:
    if ( !wil::details_abi::heap_buffer::ensure(v4, 0x10u) )
      return;
    v14 = (_QWORD *)*((_QWORD *)v4 + 1);
    v15 = (*((_QWORD *)v4 + 2) - (_QWORD)v14) & -(__int64)((unsigned __int64)v14 < *((_QWORD *)v4 + 2));
    if ( v14 )
    {
      if ( v15 >= 0x10 )
      {
        *v14 = a3;
        v14[1] = a4;
LABEL_12:
        *((_QWORD *)v4 + 1) += 16LL;
        *a2 = (struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)((*((_QWORD *)v4 + 1) - *(_QWORD *)v4) >> 4);
        return;
      }
      memset_0(v14, 0, v15);
      *(_DWORD *)_o__errno(v17, v16, v18) = 34;
    }
    else
    {
      *(_DWORD *)_o__errno(0, v13, v15) = 22;
    }
    invalid_parameter_noinfo();
    goto LABEL_12;
  }
  while ( 1 )
  {
    v11 = (struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)((char *)v6 + 1);
    v12 = 2LL * (_QWORD)v6;
    if ( !*(_QWORD *)(v5 + 8 * v12) )
      break;
    v6 = v11;
    if ( (unsigned __int64)v11 >= v9 )
      goto LABEL_4;
  }
  *(_QWORD *)(v5 + 8 * v12) = a3;
  *(_QWORD *)(v5 + 8 * v12 + 8) = a4;
  *a2 = v11;
}

```

## disassembly

```asm
0x180009478  push    rbx
0x18000947a  push    rbp
0x18000947b  push    rsi
0x18000947c  push    rdi
0x18000947d  sub     rsp, 28h
0x180009481  lea     rbx, [rcx+28h]
0x180009485  mov     qword ptr [rdx], 0
0x18000948c  mov     rcx, [rbx]
0x18000948f  xor     eax, eax
0x180009491  mov     r10, [rbx+8]
0x180009495  mov     rsi, r9
0x180009498  sub     r10, rcx
0x18000949b  mov     rbp, r8
0x18000949e  shr     r10, 4
0x1800094a2  mov     rdi, rdx
0x1800094a5  test    r10, r10
0x1800094a8  jz      short loc_1800094C0
0x1800094aa  lea     rdx, [rax+1]
0x1800094ae  add     rax, rax
0x1800094b1  cmp     qword ptr [rcx+rax*8], 0
0x1800094b6  jz      short loc_1800094F9
0x1800094b8  mov     rax, rdx
0x1800094bb  cmp     rdx, r10
0x1800094be  jb      short loc_1800094AA
0x1800094c0  mov     edx, 10h; unsigned __int64
0x1800094c5  mov     rcx, rbx; this
0x1800094c8  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800094cd  test    al, al
0x1800094cf  jz      short loc_180009541
0x1800094d1  mov     rcx, [rbx+8]; void *
0x1800094d5  mov     rax, [rbx+10h]
0x1800094d9  sub     rax, rcx
0x1800094dc  cmp     rcx, [rbx+10h]
0x1800094e0  sbb     r8, r8
0x1800094e3  and     r8, rax; Size
0x1800094e6  test    rcx, rcx
0x1800094e9  jnz     short loc_180009507
0x1800094eb  call    cs:__imp__o__errno
0x1800094f1  mov     dword ptr [rax], 16h
0x1800094f7  jmp     short loc_180009529
0x1800094f9  mov     [rcx+rax*8], rbp
0x1800094fd  mov     [rcx+rax*8+8], rsi
0x180009502  mov     [rdi], rdx
0x180009505  jmp     short loc_180009541
0x180009507  cmp     r8, 10h
0x18000950b  jb      short loc_180009516
0x18000950d  mov     [rcx], rbp
0x180009510  mov     [rcx+8], rsi
0x180009514  jmp     short loc_18000952E
0x180009516  xor     edx, edx; Val
0x180009518  call    memset_0
0x18000951d  call    cs:__imp__o__errno
0x180009523  mov     dword ptr [rax], 22h ; '"'
0x180009529  call    _invalid_parameter_noinfo
0x18000952e  add     qword ptr [rbx+8], 10h
0x180009533  mov     rax, [rbx+8]
0x180009537  sub     rax, [rbx]
0x18000953a  shr     rax, 4
0x18000953e  mov     [rdi], rax
0x180009541  add     rsp, 28h
0x180009545  pop     rdi
0x180009546  pop     rsi
0x180009547  pop     rbp
0x180009548  pop     rbx
0x180009549  retn
```
