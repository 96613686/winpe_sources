# wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18000a150`
- end: `0x18000a222`
- name: `?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `210`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000a054`
- `0x18000a750`

## callees

- `0x1800020d0`
- `0x180002134`
- `0x18000a150`
- `0x18000ac4c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a1c3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a1f5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a1c3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a1f5`

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
0x18000a150  push    rbx
0x18000a152  push    rbp
0x18000a153  push    rsi
0x18000a154  push    rdi
0x18000a155  sub     rsp, 28h
0x18000a159  lea     rbx, [rcx+28h]
0x18000a15d  mov     qword ptr [rdx], 0
0x18000a164  mov     rcx, [rbx]
0x18000a167  xor     eax, eax
0x18000a169  mov     r10, [rbx+8]
0x18000a16d  mov     rsi, r9
0x18000a170  sub     r10, rcx
0x18000a173  mov     rbp, r8
0x18000a176  shr     r10, 4
0x18000a17a  mov     rdi, rdx
0x18000a17d  test    r10, r10
0x18000a180  jz      short loc_18000A198
0x18000a182  lea     rdx, [rax+1]
0x18000a186  add     rax, rax
0x18000a189  cmp     qword ptr [rcx+rax*8], 0
0x18000a18e  jz      short loc_18000A1D1
0x18000a190  mov     rax, rdx
0x18000a193  cmp     rdx, r10
0x18000a196  jb      short loc_18000A182
0x18000a198  mov     edx, 10h; unsigned __int64
0x18000a19d  mov     rcx, rbx; this
0x18000a1a0  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000a1a5  test    al, al
0x18000a1a7  jz      short loc_18000A219
0x18000a1a9  mov     rcx, [rbx+8]; void *
0x18000a1ad  mov     rax, [rbx+10h]
0x18000a1b1  sub     rax, rcx
0x18000a1b4  cmp     rcx, [rbx+10h]
0x18000a1b8  sbb     r8, r8
0x18000a1bb  and     r8, rax; Size
0x18000a1be  test    rcx, rcx
0x18000a1c1  jnz     short loc_18000A1DF
0x18000a1c3  call    cs:__imp__o__errno
0x18000a1c9  mov     dword ptr [rax], 16h
0x18000a1cf  jmp     short loc_18000A201
0x18000a1d1  mov     [rcx+rax*8], rbp
0x18000a1d5  mov     [rcx+rax*8+8], rsi
0x18000a1da  mov     [rdi], rdx
0x18000a1dd  jmp     short loc_18000A219
0x18000a1df  cmp     r8, 10h
0x18000a1e3  jb      short loc_18000A1EE
0x18000a1e5  mov     [rcx], rbp
0x18000a1e8  mov     [rcx+8], rsi
0x18000a1ec  jmp     short loc_18000A206
0x18000a1ee  xor     edx, edx; Val
0x18000a1f0  call    memset_0
0x18000a1f5  call    cs:__imp__o__errno
0x18000a1fb  mov     dword ptr [rax], 22h ; '"'
0x18000a201  call    _invalid_parameter_noinfo
0x18000a206  add     qword ptr [rbx+8], 10h
0x18000a20b  mov     rax, [rbx+8]
0x18000a20f  sub     rax, [rbx]
0x18000a212  shr     rax, 4
0x18000a216  mov     [rdi], rax
0x18000a219  add     rsp, 28h
0x18000a21d  pop     rdi
0x18000a21e  pop     rsi
0x18000a21f  pop     rbp
0x18000a220  pop     rbx
0x18000a221  retn
```
