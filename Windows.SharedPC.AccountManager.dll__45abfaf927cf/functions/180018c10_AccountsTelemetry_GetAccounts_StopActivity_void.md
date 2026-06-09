# AccountsTelemetry::GetAccounts::StopActivity(void)

- ea: `0x180018c10`
- end: `0x180018e37`
- name: `?StopActivity@GetAccounts@AccountsTelemetry@@MEAAXXZ`
- size: `551`
- prototype: `void __fastcall(AccountsTelemetry::GetAccounts *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180001010`
- `0x180001384`
- `0x180001b0c`
- `0x18000db78`
- `0x18000e00c`
- `0x18000ed9c`
- `0x180018c10`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018dd5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018dd5`

## pseudocode

```c
void __fastcall AccountsTelemetry::GetAccounts::StopActivity(AccountsTelemetry::GetAccounts *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  const WCHAR *v9; // rcx
  __int64 v10; // r8
  const struct _tlgProvider_t *v11; // rax
  __int64 v12; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v14; // r8
  int v15; // [rsp+A0h] [rbp-19h] BYREF
  int v16; // [rsp+A4h] [rbp-15h] BYREF
  const WCHAR *v17; // [rsp+A8h] [rbp-11h] BYREF
  const unsigned __int16 *v18; // [rsp+B0h] [rbp-9h] BYREF
  const WCHAR *v19; // [rsp+B8h] [rbp-1h] BYREF
  const unsigned __int16 *v20; // [rsp+C0h] [rbp+7h] BYREF
  const unsigned __int16 *v21; // [rsp+C8h] [rbp+Fh] BYREF
  const WCHAR *v22; // [rsp+D0h] [rbp+17h] BYREF
  const unsigned __int16 *v23; // [rsp+D8h] [rbp+1Fh] BYREF
  const unsigned __int16 *v24; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v25; // [rsp+E8h] [rbp+2Fh] BYREF
  _QWORD v26[4]; // [rsp+F0h] [rbp+37h] BYREF
  DWORD v27; // [rsp+120h] [rbp+67h] BYREF
  int v28; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v29; // [rsp+130h] [rbp+77h] BYREF
  int v30; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = SharedPCAccountManagerLogging::Provider();
    v8 = (__int64)v5;
    if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x200000000000LL, v7, v5) )
    {
      v9 = (const WCHAR *)*((_QWORD *)v4 + 15);
      v10 = *((_QWORD *)this + 34);
      v18 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      v27 = v4[26];
      v19 = (const WCHAR *)*((_QWORD *)v4 + 12);
      v20 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v28 = v4[20];
      v21 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      LODWORD(v29) = v4[8];
      v22 = (const WCHAR *)*((_QWORD *)v4 + 3);
      v30 = *v4;
      v23 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v15 = v4[16];
      v24 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v16 = v4[2];
      v17 = v9;
      v25 = 0x1000000;
      v26[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v8,
        (__int64)word_18002D00A,
        v10 + 8,
        v8,
        (__int64)v26,
        (__int64)&v25,
        (__int64)&v16,
        &v24,
        (__int64)&v15,
        &v23,
        (__int64)&v30,
        &v22,
        (__int64)&v29,
        &v21,
        (__int64)&v28,
        &v20,
        &v19,
        (__int64)&v27,
        &v18,
        &v17);
    }
  }
  else
  {
    wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v11 = SharedPCAccountManagerLogging::Provider();
    v12 = (__int64)v11;
    if ( *(_DWORD *)v11 > 5u && (unsigned __int8)tlgKeywordOn(v11, 0x200000000000LL, v7, v8) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v14 = *((_QWORD *)this + 34);
      v27 = CurrentThreadId;
      v28 = *(_DWORD *)(v14 + 72);
      v29 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v12,
        (__int64)byte_18002D165,
        v14 + 8,
        0,
        (__int64)&v29,
        (__int64)&v28,
        (__int64)&v27);
    }
  }
  wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v6,
    v7,
    v8);
}

```

## disassembly

```asm
0x180018c10  push    rbp
0x180018c12  push    rbx
0x180018c13  push    rdi
0x180018c14  lea     rbp, [rsp-47h]
0x180018c19  sub     rsp, 100h
0x180018c20  mov     rdi, [rcx+110h]
0x180018c27  mov     rbx, rcx
0x180018c2a  mov     eax, [rdi+48h]
0x180018c2d  test    eax, eax
0x180018c2f  jns     loc_180018DAB
0x180018c35  add     rdi, 50h ; 'P'
0x180018c39  cmp     eax, [rdi+8]
0x180018c3c  jnz     loc_180018DAB
0x180018c42  test    rdi, rdi
0x180018c45  jz      loc_180018DAB
0x180018c4b  call    ?zInternalStop@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180018c50  call    ?Provider@SharedPCAccountManagerLogging@@SAPEBU_tlgProvider_t@@XZ; SharedPCAccountManagerLogging::Provider(void)
0x180018c55  mov     r9, rax
0x180018c58  mov     ecx, [rax]
0x180018c5a  cmp     ecx, 5
0x180018c5d  jbe     loc_180018E25
0x180018c63  mov     rdx, 200000000000h
0x180018c6d  mov     rcx, rax
0x180018c70  call    _tlgKeywordOn
0x180018c75  test    al, al
0x180018c77  jz      loc_180018E25
0x180018c7d  mov     rax, [rdi+70h]
0x180018c81  lea     rdx, word_18002D00A
0x180018c88  mov     rcx, [rdi+78h]
0x180018c8c  mov     r8, [rbx+110h]
0x180018c93  mov     [rbp+57h+var_60], rax
0x180018c97  add     r8, 8
0x180018c9b  mov     eax, [rdi+68h]
0x180018c9e  mov     [rbp+57h+arg_0], eax
0x180018ca1  mov     rax, [rdi+60h]
0x180018ca5  mov     [rbp+57h+var_58], rax
0x180018ca9  mov     rax, [rdi+58h]
0x180018cad  mov     [rbp+57h+var_50], rax
0x180018cb1  mov     eax, [rdi+50h]
0x180018cb4  mov     [rbp+57h+arg_8], eax
0x180018cb7  mov     rax, [rdi+48h]
0x180018cbb  mov     [rbp+57h+var_48], rax
0x180018cbf  mov     eax, [rdi+20h]
0x180018cc2  mov     dword ptr [rbp+57h+arg_10], eax
0x180018cc5  mov     rax, [rdi+18h]
0x180018cc9  mov     [rbp+57h+var_40], rax
0x180018ccd  mov     eax, [rdi]
0x180018ccf  mov     [rbp+57h+arg_18], eax
0x180018cd2  mov     rax, [rdi+80h]
0x180018cd9  mov     [rbp+57h+var_38], rax
0x180018cdd  mov     eax, [rdi+40h]
0x180018ce0  mov     [rbp+57h+var_70], eax
0x180018ce3  mov     rax, [rdi+38h]
0x180018ce7  mov     [rbp+57h+var_30], rax
0x180018ceb  mov     eax, [rdi+8]
0x180018cee  mov     [rbp+57h+var_6C], eax
0x180018cf1  lea     rax, [rbp+57h+var_68]
0x180018cf5  mov     [rsp+110h+var_78], rax
0x180018cfd  lea     rax, [rbp+57h+var_60]
0x180018d01  mov     [rsp+110h+var_80], rax
0x180018d09  lea     rax, [rbp+57h+arg_0]
0x180018d0d  mov     [rsp+110h+var_88], rax
0x180018d15  lea     rax, [rbp+57h+var_58]
0x180018d19  mov     [rsp+110h+var_90], rax
0x180018d21  lea     rax, [rbp+57h+var_50]
0x180018d25  mov     [rsp+110h+var_98], rax
0x180018d2a  lea     rax, [rbp+57h+arg_8]
0x180018d2e  mov     [rsp+110h+var_A0], rax
0x180018d33  lea     rax, [rbp+57h+var_48]
0x180018d37  mov     [rsp+110h+var_A8], rax
0x180018d3c  lea     rax, [rbp+57h+arg_10]
0x180018d40  mov     [rsp+110h+var_B0], rax
0x180018d45  lea     rax, [rbp+57h+var_40]
0x180018d49  mov     [rsp+110h+var_B8], rax
0x180018d4e  lea     rax, [rbp+57h+arg_18]
0x180018d52  mov     [rsp+110h+var_C0], rax
0x180018d57  lea     rax, [rbp+57h+var_38]
0x180018d5b  mov     [rsp+110h+var_C8], rax
0x180018d60  lea     rax, [rbp+57h+var_70]
0x180018d64  mov     [rsp+110h+var_D0], rax
0x180018d69  lea     rax, [rbp+57h+var_30]
0x180018d6d  mov     [rsp+110h+var_D8], rax
0x180018d72  lea     rax, [rbp+57h+var_6C]
0x180018d76  mov     [rsp+110h+var_E0], rax
0x180018d7b  lea     rax, [rbp+57h+var_28]
0x180018d7f  mov     [rsp+110h+var_E8], rax
0x180018d84  lea     rax, [rbp+57h+var_20]
0x180018d88  mov     [rbp+57h+var_68], rcx
0x180018d8c  mov     rcx, r9
0x180018d8f  mov     [rsp+110h+var_F0], rax
0x180018d94  mov     [rbp+57h+var_28], 1000000h
0x180018d9c  mov     [rbp+57h+var_20], 0
0x180018da4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180018da9  jmp     short loc_180018E25
0x180018dab  call    ?zInternalStop@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180018db0  call    ?Provider@SharedPCAccountManagerLogging@@SAPEBU_tlgProvider_t@@XZ; SharedPCAccountManagerLogging::Provider(void)
0x180018db5  mov     rdi, rax
0x180018db8  mov     ecx, [rax]
0x180018dba  cmp     ecx, 5
0x180018dbd  jbe     short loc_180018E25
0x180018dbf  mov     rdx, 200000000000h
0x180018dc9  mov     rcx, rax
0x180018dcc  call    _tlgKeywordOn
0x180018dd1  test    al, al
0x180018dd3  jz      short loc_180018E25
0x180018dd5  call    cs:__imp_GetCurrentThreadId
0x180018ddb  mov     r8, [rbx+110h]
0x180018de2  lea     rdx, byte_18002D165
0x180018de9  mov     [rbp+57h+arg_0], eax
0x180018dec  xor     r9d, r9d
0x180018def  mov     rcx, rdi
0x180018df2  mov     eax, [r8+48h]
0x180018df6  add     r8, 8
0x180018dfa  mov     [rbp+57h+arg_8], eax
0x180018dfd  lea     rax, [rbp+57h+arg_0]
0x180018e01  mov     [rsp+110h+var_E0], rax
0x180018e06  lea     rax, [rbp+57h+arg_8]
0x180018e0a  mov     [rsp+110h+var_E8], rax
0x180018e0f  lea     rax, [rbp+57h+arg_10]
0x180018e13  mov     [rsp+110h+var_F0], rax
0x180018e18  mov     [rbp+57h+arg_10], 0
0x180018e20  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180018e25  mov     rcx, rbx
0x180018e28  add     rsp, 100h
0x180018e2f  pop     rdi
0x180018e30  pop     rbx
0x180018e31  pop     rbp
0x180018e32  jmp     ?IgnoreCurrentThread@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
