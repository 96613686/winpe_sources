# wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x140007cb0`
- end: `0x140007d82`
- name: `?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `210`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x140007bb4`
- `0x140008010`

## callees

- `0x140001eae`
- `0x140001f50`
- `0x140007cb0`
- `0x1400082dc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140007d23`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140007d55`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140007d23`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140007d55`

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
0x140007cb0  push    rbx
0x140007cb2  push    rbp
0x140007cb3  push    rsi
0x140007cb4  push    rdi
0x140007cb5  sub     rsp, 28h
0x140007cb9  lea     rbx, [rcx+28h]
0x140007cbd  mov     qword ptr [rdx], 0
0x140007cc4  mov     rcx, [rbx]
0x140007cc7  xor     eax, eax
0x140007cc9  mov     r10, [rbx+8]
0x140007ccd  mov     rsi, r9
0x140007cd0  sub     r10, rcx
0x140007cd3  mov     rbp, r8
0x140007cd6  shr     r10, 4
0x140007cda  mov     rdi, rdx
0x140007cdd  test    r10, r10
0x140007ce0  jz      short loc_140007CF8
0x140007ce2  lea     rdx, [rax+1]
0x140007ce6  add     rax, rax
0x140007ce9  cmp     qword ptr [rcx+rax*8], 0
0x140007cee  jz      short loc_140007D31
0x140007cf0  mov     rax, rdx
0x140007cf3  cmp     rdx, r10
0x140007cf6  jb      short loc_140007CE2
0x140007cf8  mov     edx, 10h; unsigned __int64
0x140007cfd  mov     rcx, rbx; this
0x140007d00  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x140007d05  test    al, al
0x140007d07  jz      short loc_140007D79
0x140007d09  mov     rcx, [rbx+8]; void *
0x140007d0d  mov     rax, [rbx+10h]
0x140007d11  sub     rax, rcx
0x140007d14  cmp     rcx, [rbx+10h]
0x140007d18  sbb     r8, r8
0x140007d1b  and     r8, rax; Size
0x140007d1e  test    rcx, rcx
0x140007d21  jnz     short loc_140007D3F
0x140007d23  call    cs:__imp__o__errno
0x140007d29  mov     dword ptr [rax], 16h
0x140007d2f  jmp     short loc_140007D61
0x140007d31  mov     [rcx+rax*8], rbp
0x140007d35  mov     [rcx+rax*8+8], rsi
0x140007d3a  mov     [rdi], rdx
0x140007d3d  jmp     short loc_140007D79
0x140007d3f  cmp     r8, 10h
0x140007d43  jb      short loc_140007D4E
0x140007d45  mov     [rcx], rbp
0x140007d48  mov     [rcx+8], rsi
0x140007d4c  jmp     short loc_140007D66
0x140007d4e  xor     edx, edx; Val
0x140007d50  call    memset_0
0x140007d55  call    cs:__imp__o__errno
0x140007d5b  mov     dword ptr [rax], 22h ; '"'
0x140007d61  call    _invalid_parameter_noinfo
0x140007d66  add     qword ptr [rbx+8], 10h
0x140007d6b  mov     rax, [rbx+8]
0x140007d6f  sub     rax, [rbx]
0x140007d72  shr     rax, 4
0x140007d76  mov     [rdi], rax
0x140007d79  add     rsp, 28h
0x140007d7d  pop     rdi
0x140007d7e  pop     rsi
0x140007d7f  pop     rbp
0x140007d80  pop     rbx
0x140007d81  retn
```
