# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180001008`
- end: `0x180001104`
- name: `??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@4@Z`
- size: `252`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000f7d0`

## callees

- `0x180001008`
- `0x180001298`
- `0x180001960`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        void **a5,
        __int64 a6,
        void **a7,
        __int64 a8,
        __int64 a9)
{
  __int64 v10; // rcx
  int v11; // r8d
  _WORD *v12; // rdx
  __int64 v13; // rax
  int v14; // eax
  _WORD *v15; // rdx
  struct _EVENT_DATA_DESCRIPTOR v17; // [rsp+30h] [rbp-51h] BYREF
  _WORD *v18; // [rsp+50h] [rbp-31h]
  int v19; // [rsp+58h] [rbp-29h]
  int v20; // [rsp+5Ch] [rbp-25h]
  __int64 v21; // [rsp+60h] [rbp-21h]
  __int64 v22; // [rsp+68h] [rbp-19h]
  _WORD *v23; // [rsp+70h] [rbp-11h]
  int v24; // [rsp+78h] [rbp-9h]
  int v25; // [rsp+7Ch] [rbp-5h]
  __int64 v26; // [rsp+80h] [rbp-1h]
  __int64 v27; // [rsp+88h] [rbp+7h]
  __int64 v28; // [rsp+90h] [rbp+Fh]
  __int64 v29; // [rsp+98h] [rbp+17h]

  v28 = a9;
  v10 = -1;
  v26 = a8;
  v11 = 2;
  v29 = 4;
  v27 = 8;
  v12 = *a7;
  if ( *a7 )
  {
    v13 = -1;
    do
      ++v13;
    while ( v12[v13] );
    v14 = 2 * v13 + 2;
  }
  else
  {
    v12 = &unk_180016038;
    v14 = 2;
  }
  v24 = v14;
  v21 = a6;
  v23 = v12;
  v25 = 0;
  v22 = 4;
  v15 = *a5;
  if ( *a5 )
  {
    do
      ++v10;
    while ( v15[v10] );
    v11 = 2 * v10 + 2;
  }
  else
  {
    v15 = &unk_180016038;
  }
  v18 = v15;
  v19 = v11;
  v20 = 0;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_18001A010, a2, 0, 0, 7u, &v17);
}

```

## disassembly

```asm
0x180001008  push    rbp
0x18000100a  lea     rbp, [rsp-2Fh]
0x18000100f  sub     rsp, 0B0h
0x180001016  mov     rax, cs:__security_cookie
0x18000101d  xor     rax, rsp
0x180001020  mov     [rbp+2Fh+var_10], rax
0x180001024  mov     rax, [rbp+2Fh+arg_40]
0x180001028  xor     r9d, r9d
0x18000102b  mov     [rbp+2Fh+var_20], rax
0x18000102f  mov     r10, rdx
0x180001032  mov     rax, [rbp+2Fh+arg_38]
0x180001036  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000103a  mov     [rbp+2Fh+var_30], rax
0x18000103e  mov     rax, [rbp+2Fh+arg_30]
0x180001042  lea     r8d, [r9+2]
0x180001046  mov     [rbp+2Fh+var_18], 4
0x18000104e  mov     [rbp+2Fh+var_28], 8
0x180001056  mov     rdx, [rax]
0x180001059  test    rdx, rdx
0x18000105c  jz      short loc_180001074
0x18000105e  mov     rax, rcx
0x180001061  inc     rax
0x180001064  cmp     [rdx+rax*2], r9w
0x180001069  jnz     short loc_180001061
0x18000106b  lea     eax, ds:2[rax*2]
0x180001072  jmp     short loc_18000107E
0x180001074  lea     rdx, unk_180016038
0x18000107b  mov     eax, r8d
0x18000107e  mov     [rbp+2Fh+var_38], eax
0x180001081  mov     rax, [rbp+2Fh+arg_28]
0x180001085  mov     [rbp+2Fh+var_50], rax
0x180001089  mov     rax, [rbp+2Fh+arg_20]
0x18000108d  mov     [rbp+2Fh+var_40], rdx
0x180001091  mov     [rbp+2Fh+var_34], r9d
0x180001095  mov     [rbp+2Fh+var_48], 4
0x18000109d  mov     rdx, [rax]
0x1800010a0  test    rdx, rdx
0x1800010a3  jz      short loc_1800010B9
0x1800010a5  inc     rcx
0x1800010a8  cmp     [rdx+rcx*2], r9w
0x1800010ad  jnz     short loc_1800010A5
0x1800010af  lea     r8d, ds:2[rcx*2]
0x1800010b7  jmp     short loc_1800010C0
0x1800010b9  lea     rdx, unk_180016038
0x1800010c0  lea     rax, [rbp+2Fh+var_80]
0x1800010c4  mov     [rbp+2Fh+var_60], rdx
0x1800010c8  mov     [rbp+2Fh+var_58], r8d
0x1800010cc  lea     rcx, dword_18001A010
0x1800010d3  mov     [rsp+0B0h+var_88], rax
0x1800010d8  xor     r8d, r8d
0x1800010db  mov     rdx, r10
0x1800010de  mov     [rsp+0B0h+var_90], 7
0x1800010e6  mov     [rbp+2Fh+var_54], r9d
0x1800010ea  call    _tlgWriteTransfer_EventWriteTransfer
0x1800010ef  mov     rcx, [rbp+2Fh+var_10]
0x1800010f3  xor     rcx, rsp; StackCookie
0x1800010f6  call    __security_check_cookie
0x1800010fb  add     rsp, 0B0h
0x180001102  pop     rbp
0x180001103  retn
```
