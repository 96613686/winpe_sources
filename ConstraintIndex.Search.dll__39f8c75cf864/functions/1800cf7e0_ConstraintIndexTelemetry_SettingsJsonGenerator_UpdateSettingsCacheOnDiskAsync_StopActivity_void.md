# ConstraintIndexTelemetry::SettingsJsonGenerator_UpdateSettingsCacheOnDiskAsync::StopActivity(void)

- ea: `0x1800cf7e0`
- end: `0x1800cfa04`
- name: `?StopActivity@SettingsJsonGenerator_UpdateSettingsCacheOnDiskAsync@ConstraintIndexTelemetry@@MEAAXXZ`
- size: `548`
- prototype: `void __fastcall(ConstraintIndexTelemetry::SettingsJsonGenerator_UpdateSettingsCacheOnDiskAsync *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callees

- `0x180001010`
- `0x1800019ec`
- `0x18000243c`
- `0x18003bf74`
- `0x18003c9b8`
- `0x180040bb8`
- `0x1800cf7e0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cf9a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cf9a5`

## pseudocode

```c
void __fastcall ConstraintIndexTelemetry::SettingsJsonGenerator_UpdateSettingsCacheOnDiskAsync::StopActivity(
        ConstraintIndexTelemetry::SettingsJsonGenerator_UpdateSettingsCacheOnDiskAsync *this)
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
    if ( *(_DWORD *)v5 > 4u && (unsigned __int8)tlgKeywordOn(v5, 0x400000000000LL, v6, v5) )
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
        (unsigned int)byte_180114CB5,
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
    if ( *(_DWORD *)v10 > 4u && (unsigned __int8)tlgKeywordOn(v10, 0x400000000000LL, v11, v12) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v15 = *((_QWORD *)this + 34);
      v29 = CurrentThreadId;
      v30 = *(_DWORD *)(v15 + 72);
      v31 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v13,
        (unsigned int)byte_180114E01,
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
0x1800cf7e0  push    rbp
0x1800cf7e2  push    rbx
0x1800cf7e3  push    rdi
0x1800cf7e4  lea     rbp, [rsp-47h]
0x1800cf7e9  sub     rsp, 100h
0x1800cf7f0  mov     rdi, [rcx+110h]
0x1800cf7f7  mov     rbx, rcx
0x1800cf7fa  mov     eax, [rdi+48h]
0x1800cf7fd  test    eax, eax
0x1800cf7ff  jns     loc_1800CF97B
0x1800cf805  add     rdi, 50h ; 'P'
0x1800cf809  cmp     eax, [rdi+8]
0x1800cf80c  jnz     loc_1800CF97B
0x1800cf812  test    rdi, rdi
0x1800cf815  jz      loc_1800CF97B
0x1800cf81b  call    ?zInternalStop@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800cf820  call    ?Provider@CortanaSearchTelemetryLogging@@SAPEBU_tlgProvider_t@@XZ; CortanaSearchTelemetryLogging::Provider(void)
0x1800cf825  mov     r9, rax
0x1800cf828  mov     ecx, [rax]
0x1800cf82a  cmp     ecx, 4
0x1800cf82d  jbe     loc_1800CF9F2
0x1800cf833  mov     rdx, 400000000000h
0x1800cf83d  mov     rcx, rax
0x1800cf840  call    _tlgKeywordOn
0x1800cf845  test    al, al
0x1800cf847  jz      loc_1800CF9F2
0x1800cf84d  mov     rax, [rdi+70h]
0x1800cf851  lea     rdx, byte_180114CB5
0x1800cf858  mov     rcx, [rdi+78h]
0x1800cf85c  mov     r8, [rbx+110h]
0x1800cf863  mov     [rbp+57h+var_60], rax
0x1800cf867  add     r8, 8
0x1800cf86b  mov     eax, [rdi+68h]
0x1800cf86e  mov     [rbp+57h+arg_0], eax
0x1800cf871  mov     rax, [rdi+60h]
0x1800cf875  mov     [rbp+57h+var_58], rax
0x1800cf879  mov     rax, [rdi+58h]
0x1800cf87d  mov     [rbp+57h+var_50], rax
0x1800cf881  mov     eax, [rdi+50h]
0x1800cf884  mov     [rbp+57h+arg_8], eax
0x1800cf887  mov     rax, [rdi+48h]
0x1800cf88b  mov     [rbp+57h+var_48], rax
0x1800cf88f  mov     eax, [rdi+20h]
0x1800cf892  mov     dword ptr [rbp+57h+arg_10], eax
0x1800cf895  mov     rax, [rdi+18h]
0x1800cf899  mov     [rbp+57h+var_40], rax
0x1800cf89d  mov     eax, [rdi]
0x1800cf89f  mov     [rbp+57h+arg_18], eax
0x1800cf8a2  mov     rax, [rdi+80h]
0x1800cf8a9  mov     [rbp+57h+var_38], rax
0x1800cf8ad  mov     eax, [rdi+40h]
0x1800cf8b0  mov     [rbp+57h+var_70], eax
0x1800cf8b3  mov     rax, [rdi+38h]
0x1800cf8b7  mov     [rbp+57h+var_30], rax
0x1800cf8bb  mov     eax, [rdi+8]
0x1800cf8be  mov     [rbp+57h+var_6C], eax
0x1800cf8c1  lea     rax, [rbp+57h+var_68]
0x1800cf8c5  mov     [rsp+110h+var_78], rax
0x1800cf8cd  lea     rax, [rbp+57h+var_60]
0x1800cf8d1  mov     [rsp+110h+var_80], rax
0x1800cf8d9  lea     rax, [rbp+57h+arg_0]
0x1800cf8dd  mov     [rsp+110h+var_88], rax
0x1800cf8e5  lea     rax, [rbp+57h+var_58]
0x1800cf8e9  mov     [rsp+110h+var_90], rax
0x1800cf8f1  lea     rax, [rbp+57h+var_50]
0x1800cf8f5  mov     [rsp+110h+var_98], rax
0x1800cf8fa  lea     rax, [rbp+57h+arg_8]
0x1800cf8fe  mov     [rsp+110h+var_A0], rax
0x1800cf903  lea     rax, [rbp+57h+var_48]
0x1800cf907  mov     [rsp+110h+var_A8], rax
0x1800cf90c  lea     rax, [rbp+57h+arg_10]
0x1800cf910  mov     [rsp+110h+var_B0], rax
0x1800cf915  lea     rax, [rbp+57h+var_40]
0x1800cf919  mov     [rsp+110h+var_B8], rax
0x1800cf91e  lea     rax, [rbp+57h+arg_18]
0x1800cf922  mov     [rsp+110h+var_C0], rax
0x1800cf927  lea     rax, [rbp+57h+var_38]
0x1800cf92b  mov     [rsp+110h+var_C8], rax
0x1800cf930  lea     rax, [rbp+57h+var_70]
0x1800cf934  mov     [rsp+110h+var_D0], rax
0x1800cf939  lea     rax, [rbp+57h+var_30]
0x1800cf93d  mov     [rsp+110h+var_D8], rax
0x1800cf942  lea     rax, [rbp+57h+var_6C]
0x1800cf946  mov     [rsp+110h+var_E0], rax
0x1800cf94b  lea     rax, [rbp+57h+var_28]
0x1800cf94f  mov     [rsp+110h+var_E8], rax
0x1800cf954  lea     rax, [rbp+57h+var_20]
0x1800cf958  mov     [rbp+57h+var_68], rcx
0x1800cf95c  mov     rcx, r9
0x1800cf95f  mov     [rsp+110h+var_F0], rax
0x1800cf964  mov     [rbp+57h+var_28], 1000000h
0x1800cf96c  mov     [rbp+57h+var_20], 0
0x1800cf974  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &)
0x1800cf979  jmp     short loc_1800CF9F2
0x1800cf97b  call    ?zInternalStop@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800cf980  call    ?Provider@CortanaSearchTelemetryLogging@@SAPEBU_tlgProvider_t@@XZ; CortanaSearchTelemetryLogging::Provider(void)
0x1800cf985  mov     rdi, rax
0x1800cf988  mov     ecx, [rax]
0x1800cf98a  cmp     ecx, 4
0x1800cf98d  jbe     short loc_1800CF9F2
0x1800cf98f  mov     rdx, 400000000000h
0x1800cf999  mov     rcx, rax
0x1800cf99c  call    _tlgKeywordOn
0x1800cf9a1  test    al, al
0x1800cf9a3  jz      short loc_1800CF9F2
0x1800cf9a5  call    cs:__imp_GetCurrentThreadId
0x1800cf9ab  mov     r8, [rbx+110h]
0x1800cf9b2  lea     rdx, byte_180114E01
0x1800cf9b9  mov     [rbp+57h+arg_0], eax
0x1800cf9bc  mov     rcx, rdi
0x1800cf9bf  mov     eax, [r8+48h]
0x1800cf9c3  add     r8, 8
0x1800cf9c7  mov     [rbp+57h+arg_8], eax
0x1800cf9ca  lea     rax, [rbp+57h+arg_0]
0x1800cf9ce  mov     [rsp+110h+var_E0], rax
0x1800cf9d3  lea     rax, [rbp+57h+arg_8]
0x1800cf9d7  mov     [rsp+110h+var_E8], rax
0x1800cf9dc  lea     rax, [rbp+57h+arg_10]
0x1800cf9e0  mov     [rsp+110h+var_F0], rax
0x1800cf9e5  mov     [rbp+57h+arg_10], 0
0x1800cf9ed  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800cf9f2  mov     rcx, rbx
0x1800cf9f5  add     rsp, 100h
0x1800cf9fc  pop     rdi
0x1800cf9fd  pop     rbx
0x1800cf9fe  pop     rbp
0x1800cf9ff  jmp     ?IgnoreCurrentThread@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
