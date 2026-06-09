# wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180008458`
- end: `0x18000852a`
- name: `?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `210`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000835c`
- `0x180008aa0`

## callees

- `0x180001f32`
- `0x180001f88`
- `0x180008458`
- `0x180008f3c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800084cb`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800084fd`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800084cb`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800084fd`

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
0x180008458  push    rbx
0x18000845a  push    rbp
0x18000845b  push    rsi
0x18000845c  push    rdi
0x18000845d  sub     rsp, 28h
0x180008461  lea     rbx, [rcx+28h]
0x180008465  mov     qword ptr [rdx], 0
0x18000846c  mov     rcx, [rbx]
0x18000846f  xor     eax, eax
0x180008471  mov     r10, [rbx+8]
0x180008475  mov     rsi, r9
0x180008478  sub     r10, rcx
0x18000847b  mov     rbp, r8
0x18000847e  shr     r10, 4
0x180008482  mov     rdi, rdx
0x180008485  test    r10, r10
0x180008488  jz      short loc_1800084A0
0x18000848a  lea     rdx, [rax+1]
0x18000848e  add     rax, rax
0x180008491  cmp     qword ptr [rcx+rax*8], 0
0x180008496  jz      short loc_1800084D9
0x180008498  mov     rax, rdx
0x18000849b  cmp     rdx, r10
0x18000849e  jb      short loc_18000848A
0x1800084a0  mov     edx, 10h; unsigned __int64
0x1800084a5  mov     rcx, rbx; this
0x1800084a8  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800084ad  test    al, al
0x1800084af  jz      short loc_180008521
0x1800084b1  mov     rcx, [rbx+8]; void *
0x1800084b5  mov     rax, [rbx+10h]
0x1800084b9  sub     rax, rcx
0x1800084bc  cmp     rcx, [rbx+10h]
0x1800084c0  sbb     r8, r8
0x1800084c3  and     r8, rax; Size
0x1800084c6  test    rcx, rcx
0x1800084c9  jnz     short loc_1800084E7
0x1800084cb  call    cs:__imp__o__errno
0x1800084d1  mov     dword ptr [rax], 16h
0x1800084d7  jmp     short loc_180008509
0x1800084d9  mov     [rcx+rax*8], rbp
0x1800084dd  mov     [rcx+rax*8+8], rsi
0x1800084e2  mov     [rdi], rdx
0x1800084e5  jmp     short loc_180008521
0x1800084e7  cmp     r8, 10h
0x1800084eb  jb      short loc_1800084F6
0x1800084ed  mov     [rcx], rbp
0x1800084f0  mov     [rcx+8], rsi
0x1800084f4  jmp     short loc_18000850E
0x1800084f6  xor     edx, edx; Val
0x1800084f8  call    memset_0
0x1800084fd  call    cs:__imp__o__errno
0x180008503  mov     dword ptr [rax], 22h ; '"'
0x180008509  call    _invalid_parameter_noinfo
0x18000850e  add     qword ptr [rbx+8], 10h
0x180008513  mov     rax, [rbx+8]
0x180008517  sub     rax, [rbx]
0x18000851a  shr     rax, 4
0x18000851e  mov     [rdi], rax
0x180008521  add     rsp, 28h
0x180008525  pop     rdi
0x180008526  pop     rsi
0x180008527  pop     rbp
0x180008528  pop     rbx
0x180008529  retn
```
