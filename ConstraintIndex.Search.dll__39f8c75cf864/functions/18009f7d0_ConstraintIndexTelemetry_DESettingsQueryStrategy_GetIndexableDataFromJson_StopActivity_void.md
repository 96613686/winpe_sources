# ConstraintIndexTelemetry::DESettingsQueryStrategy_GetIndexableDataFromJson::StopActivity(void)

- ea: `0x18009f7d0`
- end: `0x18009f9fc`
- name: `?StopActivity@DESettingsQueryStrategy_GetIndexableDataFromJson@ConstraintIndexTelemetry@@MEAAXXZ`
- size: `556`
- prototype: `void __fastcall(ConstraintIndexTelemetry::DESettingsQueryStrategy_GetIndexableDataFromJson *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x180001314`
- `0x1800019ec`
- `0x18003bf74`
- `0x18003c9b8`
- `0x180040bb8`
- `0x18009f7d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009f99d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009f99d`

## pseudocode

```c
void __fastcall ConstraintIndexTelemetry::DESettingsQueryStrategy_GetIndexableDataFromJson::StopActivity(
        ConstraintIndexTelemetry::DESettingsQueryStrategy_GetIndexableDataFromJson *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // rcx
  __int64 v7; // r8
  const struct _tlgProvider_t *v8; // rax
  int v9; // edi
  DWORD CurrentThreadId; // eax
  __int64 v11; // r8
  int v12; // r9d
  int v13; // [rsp+C0h] [rbp-80h] BYREF
  int v14; // [rsp+C4h] [rbp-7Ch] BYREF
  int v15; // [rsp+C8h] [rbp-78h] BYREF
  int v16; // [rsp+CCh] [rbp-74h] BYREF
  __int64 v17; // [rsp+D0h] [rbp-70h] BYREF
  __int64 v18; // [rsp+D8h] [rbp-68h] BYREF
  __int64 v19; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v20; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v21; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v22; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v23; // [rsp+100h] [rbp-40h] BYREF
  __int64 v24; // [rsp+108h] [rbp-38h] BYREF
  __int64 v25; // [rsp+110h] [rbp-30h] BYREF
  __int64 v26; // [rsp+118h] [rbp-28h] BYREF
  __int64 v27[4]; // [rsp+120h] [rbp-20h] BYREF
  __int64 v28; // [rsp+150h] [rbp+10h] BYREF
  __int64 v29; // [rsp+158h] [rbp+18h] BYREF
  __int64 v30; // [rsp+160h] [rbp+20h] BYREF
  __int64 v31; // [rsp+168h] [rbp+28h] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = CortanaSearchTelemetryLogging::Provider();
    if ( *(_DWORD *)v5 > 5u )
    {
      v6 = *((_QWORD *)v4 + 6);
      v19 = *((_QWORD *)v4 + 14);
      v7 = *((_QWORD *)this + 34);
      LODWORD(v30) = v4[26];
      v20 = *((_QWORD *)v4 + 12);
      v21 = *((_QWORD *)v4 + 11);
      LODWORD(v31) = v4[20];
      v22 = *((_QWORD *)v4 + 9);
      v13 = v4[8];
      v23 = *((_QWORD *)v4 + 3);
      v14 = *v4;
      v24 = *((_QWORD *)v4 + 16);
      v15 = v4[16];
      v25 = *((_QWORD *)v4 + 7);
      v16 = v4[2];
      v17 = v6;
      LODWORD(v28) = v4[17];
      LODWORD(v29) = v4[4];
      v18 = *((_QWORD *)v4 + 15);
      v26 = 0x1000000;
      v27[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (int)v5,
        (int)&byte_1801135DB,
        v7 + 8,
        (__int64)v27,
        (__int64)&v26,
        (__int64)&v16,
        (__int64)&v25,
        (__int64)&v15,
        (__int64)&v24,
        (__int64)&v14,
        (__int64)&v23,
        (__int64)&v13,
        (__int64)&v22,
        (__int64)&v31,
        (__int64)&v21,
        (__int64)&v20,
        (__int64)&v30,
        (__int64)&v19,
        (__int64)&v18,
        (__int64)&v29,
        (__int64)&v28,
        (__int64)&v17);
    }
  }
  else
  {
    wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v8 = CortanaSearchTelemetryLogging::Provider();
    v9 = (int)v8;
    if ( *(_DWORD *)v8 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v11 = *((_QWORD *)this + 34);
      LODWORD(v28) = CurrentThreadId;
      LODWORD(v29) = *(_DWORD *)(v11 + 72);
      v30 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v9,
        (unsigned int)&word_180113746,
        v11 + 8,
        v12,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v28);
    }
  }
  wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(this);
}

```

## disassembly

```asm
0x18009f7d0  push    rbp
0x18009f7d2  push    rbx
0x18009f7d3  push    rdi
0x18009f7d4  lea     rbp, [rsp+10h]
0x18009f7d9  sub     rsp, 130h
0x18009f7e0  mov     rdi, [rcx+110h]
0x18009f7e7  mov     rbx, rcx
0x18009f7ea  mov     eax, [rdi+48h]
0x18009f7ed  test    eax, eax
0x18009f7ef  jns     loc_18009F989
0x18009f7f5  add     rdi, 50h ; 'P'
0x18009f7f9  cmp     eax, [rdi+8]
0x18009f7fc  jnz     loc_18009F989
0x18009f802  test    rdi, rdi
0x18009f805  jz      loc_18009F989
0x18009f80b  call    ?zInternalStop@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18009f810  call    ?Provider@CortanaSearchTelemetryLogging@@SAPEBU_tlgProvider_t@@XZ; CortanaSearchTelemetryLogging::Provider(void)
0x18009f815  mov     r9, rax
0x18009f818  mov     ecx, [rax]
0x18009f81a  cmp     ecx, 5
0x18009f81d  jbe     loc_18009F9EA
0x18009f823  mov     rax, [rdi+70h]
0x18009f827  lea     rdx, byte_1801135DB; int
0x18009f82e  mov     rcx, [rdi+30h]
0x18009f832  mov     [rbp+var_60], rax
0x18009f836  mov     eax, [rdi+68h]
0x18009f839  mov     r8, [rbx+110h]
0x18009f840  mov     dword ptr [rbp+arg_10], eax
0x18009f843  add     r8, 8; int
0x18009f847  mov     rax, [rdi+60h]
0x18009f84b  mov     [rbp+var_58], rax
0x18009f84f  mov     rax, [rdi+58h]
0x18009f853  mov     [rbp+var_50], rax
0x18009f857  mov     eax, [rdi+50h]
0x18009f85a  mov     dword ptr [rbp+arg_18], eax
0x18009f85d  mov     rax, [rdi+48h]
0x18009f861  mov     [rbp+var_48], rax
0x18009f865  mov     eax, [rdi+20h]
0x18009f868  mov     dword ptr [rbp+var_80], eax
0x18009f86b  mov     rax, [rdi+18h]
0x18009f86f  mov     [rbp+var_40], rax
0x18009f873  mov     eax, [rdi]
0x18009f875  mov     dword ptr [rbp+var_80+4], eax
0x18009f878  mov     rax, [rdi+80h]
0x18009f87f  mov     [rbp+var_38], rax
0x18009f883  mov     eax, [rdi+40h]
0x18009f886  mov     dword ptr [rbp+var_78], eax
0x18009f889  mov     rax, [rdi+38h]
0x18009f88d  mov     [rbp+var_30], rax
0x18009f891  mov     eax, [rdi+8]
0x18009f894  mov     dword ptr [rbp+var_78+4], eax
0x18009f897  lea     rax, [rbp+var_70]
0x18009f89b  mov     [rsp+140h+var_90], rax; __int64
0x18009f8a3  lea     rax, [rbp+arg_0]
0x18009f8a7  mov     [rsp+140h+var_98], rax; __int64
0x18009f8af  lea     rax, [rbp+arg_8]
0x18009f8b3  mov     [rsp+140h+var_A0], rax; __int64
0x18009f8bb  lea     rax, [rbp+var_68]
0x18009f8bf  mov     [rsp+140h+var_A8], rax; __int64
0x18009f8c7  lea     rax, [rbp+var_60]
0x18009f8cb  mov     [rsp+140h+var_B0], rax; __int64
0x18009f8d3  lea     rax, [rbp+arg_10]
0x18009f8d7  mov     [rsp+140h+var_B8], rax; __int64
0x18009f8df  lea     rax, [rbp+var_58]
0x18009f8e3  mov     [rsp+140h+var_C0], rax; __int64
0x18009f8eb  lea     rax, [rbp+var_50]
0x18009f8ef  mov     [rsp+140h+var_C8], rax; __int64
0x18009f8f4  lea     rax, [rbp+arg_18]
0x18009f8f8  mov     [rsp+140h+var_D0], rax; __int64
0x18009f8fd  lea     rax, [rbp+var_48]
0x18009f901  mov     [rsp+140h+var_D8], rax; __int64
0x18009f906  lea     rax, [rbp+var_80]
0x18009f90a  mov     [rsp+140h+var_E0], rax; __int64
0x18009f90f  lea     rax, [rbp+var_40]
0x18009f913  mov     [rsp+140h+var_E8], rax; __int64
0x18009f918  lea     rax, [rbp+var_80+4]
0x18009f91c  mov     [rsp+140h+var_F0], rax; __int64
0x18009f921  lea     rax, [rbp+var_38]
0x18009f925  mov     [rsp+140h+var_F8], rax; __int64
0x18009f92a  lea     rax, [rbp+var_78]
0x18009f92e  mov     [rsp+140h+var_100], rax; __int64
0x18009f933  lea     rax, [rbp+var_30]
0x18009f937  mov     [rsp+140h+var_108], rax; __int64
0x18009f93c  lea     rax, [rbp+var_78+4]
0x18009f940  mov     [rbp+var_70], rcx
0x18009f944  mov     ecx, [rdi+44h]
0x18009f947  mov     [rsp+140h+var_110], rax; __int64
0x18009f94c  lea     rax, [rbp+var_28]
0x18009f950  mov     dword ptr [rbp+arg_0], ecx
0x18009f953  mov     ecx, [rdi+10h]
0x18009f956  mov     dword ptr [rbp+arg_8], ecx
0x18009f959  mov     rcx, [rdi+78h]
0x18009f95d  mov     [rsp+140h+var_118], rax; __int64
0x18009f962  lea     rax, [rbp+var_20]
0x18009f966  mov     [rbp+var_68], rcx
0x18009f96a  mov     rcx, r9; int
0x18009f96d  mov     [rsp+140h+var_120], rax; __int64
0x18009f972  mov     [rbp+var_28], 1000000h
0x18009f97a  mov     [rbp+var_20], 0
0x18009f982  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18009f987  jmp     short loc_18009F9EA
0x18009f989  call    ?zInternalStop@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18009f98e  call    ?Provider@CortanaSearchTelemetryLogging@@SAPEBU_tlgProvider_t@@XZ; CortanaSearchTelemetryLogging::Provider(void)
0x18009f993  mov     rdi, rax
0x18009f996  mov     ecx, [rax]
0x18009f998  cmp     ecx, 5
0x18009f99b  jbe     short loc_18009F9EA
0x18009f99d  call    cs:__imp_GetCurrentThreadId
0x18009f9a3  mov     r8, [rbx+110h]
0x18009f9aa  lea     rdx, word_180113746
0x18009f9b1  mov     dword ptr [rbp+arg_0], eax
0x18009f9b4  lea     rax, [rbp+arg_0]
0x18009f9b8  mov     [rsp+140h+var_110], rax
0x18009f9bd  lea     rax, [rbp+arg_8]
0x18009f9c1  mov     [rsp+140h+var_118], rax
0x18009f9c6  lea     rax, [rbp+arg_10]
0x18009f9ca  mov     ecx, [r8+48h]
0x18009f9ce  add     r8, 8
0x18009f9d2  mov     dword ptr [rbp+arg_8], ecx
0x18009f9d5  mov     rcx, rdi
0x18009f9d8  mov     [rsp+140h+var_120], rax
0x18009f9dd  mov     [rbp+arg_10], 0
0x18009f9e5  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18009f9ea  mov     rcx, rbx
0x18009f9ed  add     rsp, 130h
0x18009f9f4  pop     rdi
0x18009f9f5  pop     rbx
0x18009f9f6  pop     rbp
0x18009f9f7  jmp     ?IgnoreCurrentThread@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
