# ConstraintIndexTelemetry::ConstraintIndexManager_GetEntitiesJSONInMemory::StopActivity(void)

- ea: `0x180098be0`
- end: `0x180098e04`
- name: `?StopActivity@ConstraintIndexManager_GetEntitiesJSONInMemory@ConstraintIndexTelemetry@@MEAAXXZ`
- size: `548`
- prototype: `void __fastcall(ConstraintIndexTelemetry::ConstraintIndexManager_GetEntitiesJSONInMemory *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x180001010`
- `0x1800019ec`
- `0x18000243c`
- `0x18003bf74`
- `0x18003c9b8`
- `0x180040bb8`
- `0x180098be0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180098da5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180098da5`

## pseudocode

```c
void __fastcall ConstraintIndexTelemetry::ConstraintIndexManager_GetEntitiesJSONInMemory::StopActivity(
        ConstraintIndexTelemetry::ConstraintIndexManager_GetEntitiesJSONInMemory *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // r8
  int v7; // r9d
  __int64 v8; // rcx
  __int64 v9; // r8
  const struct _tlgProvider_t *v10; // rax
  __int64 v11; // r8
  __int64 v12; // r9
  int v13; // edi
  DWORD CurrentThreadId; // eax
  __int64 v15; // r8
  int v16; // r9d
  int v17; // [rsp+A0h] [rbp-19h] BYREF
  int v18; // [rsp+A4h] [rbp-15h] BYREF
  __int64 v19; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v20; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v21; // [rsp+B8h] [rbp-1h] BYREF
  __int64 v22; // [rsp+C0h] [rbp+7h] BYREF
  __int64 v23; // [rsp+C8h] [rbp+Fh] BYREF
  __int64 v24; // [rsp+D0h] [rbp+17h] BYREF
  __int64 v25; // [rsp+D8h] [rbp+1Fh] BYREF
  __int64 v26; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v27; // [rsp+E8h] [rbp+2Fh] BYREF
  _QWORD v28[4]; // [rsp+F0h] [rbp+37h] BYREF
  DWORD v29; // [rsp+120h] [rbp+67h] BYREF
  int v30; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v31; // [rsp+130h] [rbp+77h] BYREF
  int v32; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = CortanaSearchTelemetryLogging::Provider();
    if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x200000000000LL, v6, v5) )
    {
      v8 = *((_QWORD *)v4 + 15);
      v9 = *((_QWORD *)this + 34);
      v20 = *((_QWORD *)v4 + 14);
      v29 = v4[26];
      v21 = *((_QWORD *)v4 + 12);
      v22 = *((_QWORD *)v4 + 11);
      v30 = v4[20];
      v23 = *((_QWORD *)v4 + 9);
      LODWORD(v31) = v4[8];
      v24 = *((_QWORD *)v4 + 3);
      v32 = *v4;
      v25 = *((_QWORD *)v4 + 16);
      v17 = v4[16];
      v26 = *((_QWORD *)v4 + 7);
      v18 = v4[2];
      v19 = v8;
      v27 = 0x1000000;
      v28[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(
        v7,
        (unsigned int)byte_180112C63,
        v9 + 8,
        v7,
        (__int64)v28,
        (__int64)&v27,
        (__int64)&v18,
        (__int64)&v26,
        (__int64)&v17,
        (__int64)&v25,
        (__int64)&v32,
        (__int64)&v24,
        (__int64)&v31,
        (__int64)&v23,
        (__int64)&v30,
        (__int64)&v22,
        (__int64)&v21,
        (__int64)&v29,
        (__int64)&v20,
        (__int64)&v19);
    }
  }
  else
  {
    wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v10 = CortanaSearchTelemetryLogging::Provider();
    v13 = (int)v10;
    if ( *(_DWORD *)v10 > 5u && (unsigned __int8)tlgKeywordOn(v10, 0x200000000000LL, v11, v12) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v15 = *((_QWORD *)this + 34);
      v29 = CurrentThreadId;
      v30 = *(_DWORD *)(v15 + 72);
      v31 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v13,
        (unsigned int)byte_180112DA9,
        v15 + 8,
        v16,
        (__int64)&v31,
        (__int64)&v30,
        (__int64)&v29);
    }
  }
  wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(this);
}

```

## disassembly

```asm
0x180098be0  push    rbp
0x180098be2  push    rbx
0x180098be3  push    rdi
0x180098be4  lea     rbp, [rsp-47h]
0x180098be9  sub     rsp, 100h
0x180098bf0  mov     rdi, [rcx+110h]
0x180098bf7  mov     rbx, rcx
0x180098bfa  mov     eax, [rdi+48h]
0x180098bfd  test    eax, eax
0x180098bff  jns     loc_180098D7B
0x180098c05  add     rdi, 50h ; 'P'
0x180098c09  cmp     eax, [rdi+8]
0x180098c0c  jnz     loc_180098D7B
0x180098c12  test    rdi, rdi
0x180098c15  jz      loc_180098D7B
0x180098c1b  call    ?zInternalStop@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180098c20  call    ?Provider@CortanaSearchTelemetryLogging@@SAPEBU_tlgProvider_t@@XZ; CortanaSearchTelemetryLogging::Provider(void)
0x180098c25  mov     r9, rax
0x180098c28  mov     ecx, [rax]
0x180098c2a  cmp     ecx, 5
0x180098c2d  jbe     loc_180098DF2
0x180098c33  mov     rdx, 200000000000h
0x180098c3d  mov     rcx, rax
0x180098c40  call    _tlgKeywordOn
0x180098c45  test    al, al
0x180098c47  jz      loc_180098DF2
0x180098c4d  mov     rax, [rdi+70h]
0x180098c51  lea     rdx, byte_180112C63
0x180098c58  mov     rcx, [rdi+78h]
0x180098c5c  mov     r8, [rbx+110h]
0x180098c63  mov     [rbp+57h+var_60], rax
0x180098c67  add     r8, 8
0x180098c6b  mov     eax, [rdi+68h]
0x180098c6e  mov     [rbp+57h+arg_0], eax
0x180098c71  mov     rax, [rdi+60h]
0x180098c75  mov     [rbp+57h+var_58], rax
0x180098c79  mov     rax, [rdi+58h]
0x180098c7d  mov     [rbp+57h+var_50], rax
0x180098c81  mov     eax, [rdi+50h]
0x180098c84  mov     [rbp+57h+arg_8], eax
0x180098c87  mov     rax, [rdi+48h]
0x180098c8b  mov     [rbp+57h+var_48], rax
0x180098c8f  mov     eax, [rdi+20h]
0x180098c92  mov     dword ptr [rbp+57h+arg_10], eax
0x180098c95  mov     rax, [rdi+18h]
0x180098c99  mov     [rbp+57h+var_40], rax
0x180098c9d  mov     eax, [rdi]
0x180098c9f  mov     [rbp+57h+arg_18], eax
0x180098ca2  mov     rax, [rdi+80h]
0x180098ca9  mov     [rbp+57h+var_38], rax
0x180098cad  mov     eax, [rdi+40h]
0x180098cb0  mov     [rbp+57h+var_70], eax
0x180098cb3  mov     rax, [rdi+38h]
0x180098cb7  mov     [rbp+57h+var_30], rax
0x180098cbb  mov     eax, [rdi+8]
0x180098cbe  mov     [rbp+57h+var_6C], eax
0x180098cc1  lea     rax, [rbp+57h+var_68]
0x180098cc5  mov     [rsp+110h+var_78], rax
0x180098ccd  lea     rax, [rbp+57h+var_60]
0x180098cd1  mov     [rsp+110h+var_80], rax
0x180098cd9  lea     rax, [rbp+57h+arg_0]
0x180098cdd  mov     [rsp+110h+var_88], rax
0x180098ce5  lea     rax, [rbp+57h+var_58]
0x180098ce9  mov     [rsp+110h+var_90], rax
0x180098cf1  lea     rax, [rbp+57h+var_50]
0x180098cf5  mov     [rsp+110h+var_98], rax
0x180098cfa  lea     rax, [rbp+57h+arg_8]
0x180098cfe  mov     [rsp+110h+var_A0], rax
0x180098d03  lea     rax, [rbp+57h+var_48]
0x180098d07  mov     [rsp+110h+var_A8], rax
0x180098d0c  lea     rax, [rbp+57h+arg_10]
0x180098d10  mov     [rsp+110h+var_B0], rax
0x180098d15  lea     rax, [rbp+57h+var_40]
0x180098d19  mov     [rsp+110h+var_B8], rax
0x180098d1e  lea     rax, [rbp+57h+arg_18]
0x180098d22  mov     [rsp+110h+var_C0], rax
0x180098d27  lea     rax, [rbp+57h+var_38]
0x180098d2b  mov     [rsp+110h+var_C8], rax
0x180098d30  lea     rax, [rbp+57h+var_70]
0x180098d34  mov     [rsp+110h+var_D0], rax
0x180098d39  lea     rax, [rbp+57h+var_30]
0x180098d3d  mov     [rsp+110h+var_D8], rax
0x180098d42  lea     rax, [rbp+57h+var_6C]
0x180098d46  mov     [rsp+110h+var_E0], rax
0x180098d4b  lea     rax, [rbp+57h+var_28]
0x180098d4f  mov     [rsp+110h+var_E8], rax
0x180098d54  lea     rax, [rbp+57h+var_20]
0x180098d58  mov     [rbp+57h+var_68], rcx
0x180098d5c  mov     rcx, r9
0x180098d5f  mov     [rsp+110h+var_F0], rax
0x180098d64  mov     [rbp+57h+var_28], 1000000h
0x180098d6c  mov     [rbp+57h+var_20], 0
0x180098d74  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &)
0x180098d79  jmp     short loc_180098DF2
0x180098d7b  call    ?zInternalStop@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180098d80  call    ?Provider@CortanaSearchTelemetryLogging@@SAPEBU_tlgProvider_t@@XZ; CortanaSearchTelemetryLogging::Provider(void)
0x180098d85  mov     rdi, rax
0x180098d88  mov     ecx, [rax]
0x180098d8a  cmp     ecx, 5
0x180098d8d  jbe     short loc_180098DF2
0x180098d8f  mov     rdx, 200000000000h
0x180098d99  mov     rcx, rax
0x180098d9c  call    _tlgKeywordOn
0x180098da1  test    al, al
0x180098da3  jz      short loc_180098DF2
0x180098da5  call    cs:__imp_GetCurrentThreadId
0x180098dab  mov     r8, [rbx+110h]
0x180098db2  lea     rdx, byte_180112DA9
0x180098db9  mov     [rbp+57h+arg_0], eax
0x180098dbc  mov     rcx, rdi
0x180098dbf  mov     eax, [r8+48h]
0x180098dc3  add     r8, 8
0x180098dc7  mov     [rbp+57h+arg_8], eax
0x180098dca  lea     rax, [rbp+57h+arg_0]
0x180098dce  mov     [rsp+110h+var_E0], rax
0x180098dd3  lea     rax, [rbp+57h+arg_8]
0x180098dd7  mov     [rsp+110h+var_E8], rax
0x180098ddc  lea     rax, [rbp+57h+arg_10]
0x180098de0  mov     [rsp+110h+var_F0], rax
0x180098de5  mov     [rbp+57h+arg_10], 0
0x180098ded  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180098df2  mov     rcx, rbx
0x180098df5  add     rsp, 100h
0x180098dfc  pop     rdi
0x180098dfd  pop     rbx
0x180098dfe  pop     rbp
0x180098dff  jmp     ?IgnoreCurrentThread@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
