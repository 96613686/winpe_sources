# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)

- ea: `0x1400013f0`
- end: `0x1400014ec`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@_W@@U3@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@_W@@54@Z`
- size: `252`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140005f98`

## callees

- `0x1400013f0`
- `0x14000162c`
- `0x140003200`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int **a7,
        int **a8,
        __int64 a9)
{
  __int64 v10; // rcx
  int v11; // r8d
  int *v12; // rdx
  __int64 v13; // rax
  int v14; // eax
  int *v15; // rdx
  struct _EVENT_DATA_DESCRIPTOR v17; // [rsp+30h] [rbp-51h] BYREF
  __int64 v18; // [rsp+50h] [rbp-31h]
  __int64 v19; // [rsp+58h] [rbp-29h]
  __int64 v20; // [rsp+60h] [rbp-21h]
  __int64 v21; // [rsp+68h] [rbp-19h]
  int *v22; // [rsp+70h] [rbp-11h]
  int v23; // [rsp+78h] [rbp-9h]
  int v24; // [rsp+7Ch] [rbp-5h]
  int *v25; // [rsp+80h] [rbp-1h]
  int v26; // [rsp+88h] [rbp+7h]
  int v27; // [rsp+8Ch] [rbp+Bh]
  __int64 v28; // [rsp+90h] [rbp+Fh]
  __int64 v29; // [rsp+98h] [rbp+17h]

  v28 = a9;
  v10 = -1;
  v29 = 4;
  v11 = 2;
  v12 = *a8;
  if ( *a8 )
  {
    v13 = -1;
    do
      ++v13;
    while ( *((_WORD *)v12 + v13) );
    v14 = 2 * v13 + 2;
  }
  else
  {
    v12 = &dword_1400241F4;
    v14 = 2;
  }
  v26 = v14;
  v25 = v12;
  v27 = 0;
  v15 = *a7;
  if ( *a7 )
  {
    do
      ++v10;
    while ( *((_WORD *)v15 + v10) );
    v11 = 2 * v10 + 2;
  }
  else
  {
    v15 = &dword_1400241F4;
  }
  v20 = a6;
  v18 = a5;
  v22 = v15;
  v23 = v11;
  v24 = 0;
  v21 = 4;
  v19 = 8;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_14002C000, a2, 0, 0, 7u, &v17);
}

```

## disassembly

```asm
0x1400013f0  push    rbp
0x1400013f2  lea     rbp, [rsp-2Fh]
0x1400013f7  sub     rsp, 0B0h
0x1400013fe  mov     rax, cs:__security_cookie
0x140001405  xor     rax, rsp
0x140001408  mov     [rbp+2Fh+var_10], rax
0x14000140c  mov     rax, [rbp+2Fh+arg_40]
0x140001410  xor     r9d, r9d
0x140001413  mov     [rbp+2Fh+var_20], rax
0x140001417  mov     r10, rdx
0x14000141a  mov     rax, [rbp+2Fh+arg_38]
0x14000141e  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140001422  mov     [rbp+2Fh+var_18], 4
0x14000142a  lea     r8d, [r9+2]
0x14000142e  mov     rdx, [rax]
0x140001431  test    rdx, rdx
0x140001434  jz      short loc_14000144C
0x140001436  mov     rax, rcx
0x140001439  inc     rax
0x14000143c  cmp     [rdx+rax*2], r9w
0x140001441  jnz     short loc_140001439
0x140001443  lea     eax, ds:2[rax*2]
0x14000144a  jmp     short loc_140001456
0x14000144c  lea     rdx, dword_1400241F4
0x140001453  mov     eax, r8d
0x140001456  mov     [rbp+2Fh+var_28], eax
0x140001459  mov     rax, [rbp+2Fh+arg_30]
0x14000145d  mov     [rbp+2Fh+var_30], rdx
0x140001461  mov     [rbp+2Fh+var_24], r9d
0x140001465  mov     rdx, [rax]
0x140001468  test    rdx, rdx
0x14000146b  jz      short loc_140001481
0x14000146d  inc     rcx
0x140001470  cmp     [rdx+rcx*2], r9w
0x140001475  jnz     short loc_14000146D
0x140001477  lea     r8d, ds:2[rcx*2]
0x14000147f  jmp     short loc_140001488
0x140001481  lea     rdx, dword_1400241F4
0x140001488  mov     rax, [rbp+2Fh+arg_28]
0x14000148c  lea     rcx, dword_14002C000
0x140001493  mov     [rbp+2Fh+var_50], rax
0x140001497  mov     rax, [rbp+2Fh+arg_20]
0x14000149b  mov     [rbp+2Fh+var_60], rax
0x14000149f  lea     rax, [rbp+2Fh+var_80]
0x1400014a3  mov     [rbp+2Fh+var_40], rdx
0x1400014a7  mov     rdx, r10
0x1400014aa  mov     [rbp+2Fh+var_38], r8d
0x1400014ae  xor     r8d, r8d
0x1400014b1  mov     [rsp+0B0h+var_88], rax
0x1400014b6  mov     [rsp+0B0h+var_90], 7
0x1400014be  mov     [rbp+2Fh+var_34], r9d
0x1400014c2  mov     [rbp+2Fh+var_48], 4
0x1400014ca  mov     [rbp+2Fh+var_58], 8
0x1400014d2  call    _tlgWriteTransfer_EventWriteTransfer
0x1400014d7  mov     rcx, [rbp+2Fh+var_10]
0x1400014db  xor     rcx, rsp; StackCookie
0x1400014de  call    __security_check_cookie
0x1400014e3  add     rsp, 0B0h
0x1400014ea  pop     rbp
0x1400014eb  retn
```
