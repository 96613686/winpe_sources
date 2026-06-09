# ConstraintIndexTelemetry::SettingsFilterCacheManager_FilterDeviceItems::Stop(uint)

- ea: `0x1800c4c18`
- end: `0x1800c4ee0`
- name: `?Stop@SettingsFilterCacheManager_FilterDeviceItems@ConstraintIndexTelemetry@@QEAAXI@Z`
- size: `712`
- prototype: `void __fastcall(ConstraintIndexTelemetry::SettingsFilterCacheManager_FilterDeviceItems *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1800c29e0`

## callees

- `0x18000243c`
- `0x18000325c`
- `0x1800035c8`
- `0x18000619e`
- `0x18003bf74`
- `0x18003c9b8`
- `0x180040bb8`
- `0x1800925ec`
- `0x1800c4c18`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800c4e6c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800c4e6c`

## pseudocode

```c
void __fastcall ConstraintIndexTelemetry::SettingsFilterCacheManager_FilterDeviceItems::Stop(
        ConstraintIndexTelemetry::SettingsFilterCacheManager_FilterDeviceItems *this,
        int a2)
{
  __int64 v2; // rdi
  int v5; // eax
  int *v6; // rdi
  const struct _tlgProvider_t *v7; // rax
  __int64 v8; // r8
  __int64 v9; // r9
  int v10; // esi
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // r8
  const struct _tlgProvider_t *v14; // rax
  __int64 v15; // r8
  __int64 v16; // r9
  int v17; // edi
  __int64 v18; // rcx
  __int64 v19; // rax
  DWORD CurrentThreadId; // eax
  __int64 v21; // r8
  int v22; // [rsp+D0h] [rbp-80h] BYREF
  int v23; // [rsp+D4h] [rbp-7Ch] BYREF
  int v24; // [rsp+D8h] [rbp-78h] BYREF
  int v25; // [rsp+DCh] [rbp-74h] BYREF
  int v26; // [rsp+E0h] [rbp-70h] BYREF
  int v27; // [rsp+E4h] [rbp-6Ch] BYREF
  __int64 v28; // [rsp+E8h] [rbp-68h] BYREF
  __int64 v29; // [rsp+F0h] [rbp-60h] BYREF
  __int64 StringRawBuffer_0; // [rsp+F8h] [rbp-58h] BYREF
  __int64 v31; // [rsp+100h] [rbp-50h] BYREF
  __int64 v32; // [rsp+108h] [rbp-48h] BYREF
  __int64 v33; // [rsp+110h] [rbp-40h] BYREF
  __int64 v34; // [rsp+118h] [rbp-38h] BYREF
  __int64 v35; // [rsp+120h] [rbp-30h] BYREF
  __int64 v36; // [rsp+128h] [rbp-28h] BYREF
  __int64 v37; // [rsp+130h] [rbp-20h] BYREF
  __int64 v38; // [rsp+138h] [rbp-18h] BYREF
  __int64 v39; // [rsp+140h] [rbp-10h] BYREF
  __int64 v40; // [rsp+180h] [rbp+30h] BYREF
  __int64 v41; // [rsp+190h] [rbp+40h] BYREF
  __int64 v42; // [rsp+198h] [rbp+48h] BYREF

  v2 = *((_QWORD *)this + 34);
  v5 = *(_DWORD *)(v2 + 72);
  if ( v5 < 0 && (v6 = (int *)(v2 + 80), v5 == v6[2]) && v6 )
  {
    wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v7 = CortanaSearchTelemetryLogging::Provider();
    v10 = (int)v7;
    if ( *(_DWORD *)v7 > 5u && (unsigned __int8)tlgKeywordOn(v7, 1, v8, v9) )
    {
      LODWORD(v40) = a2;
      v12 = wil::details::static_lazy<ConstraintIndexTelemetry>::get(
              v11,
              _lambda_3f32e471ee4016ff12f12bcbf8a58c4e_::_lambda_invoker_cdecl_);
      StringRawBuffer_0 = (__int64)WindowsGetStringRawBuffer_0(*(HSTRING *)(v12 + 24), 0);
      v31 = *((_QWORD *)v6 + 6);
      LODWORD(v41) = v6[17];
      LODWORD(v42) = v6[4];
      v32 = *((_QWORD *)v6 + 15);
      v13 = *((_QWORD *)this + 34);
      v33 = *((_QWORD *)v6 + 14);
      v22 = v6[26];
      v34 = *((_QWORD *)v6 + 12);
      v35 = *((_QWORD *)v6 + 11);
      v23 = v6[20];
      v36 = *((_QWORD *)v6 + 9);
      v24 = v6[8];
      v37 = *((_QWORD *)v6 + 3);
      v25 = *v6;
      v38 = *((_QWORD *)v6 + 16);
      v26 = v6[16];
      v39 = *((_QWORD *)v6 + 7);
      v27 = v6[2];
      v28 = 0x1000000;
      v29 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
        v10,
        (int)&unk_180114430,
        v13 + 8,
        (__int64)&v29,
        (__int64)&v28,
        (__int64)&v27,
        (__int64)&v39,
        (__int64)&v26,
        (__int64)&v38,
        (__int64)&v25,
        (__int64)&v37,
        (__int64)&v24,
        (__int64)&v36,
        (__int64)&v23,
        (__int64)&v35,
        (__int64)&v34,
        (__int64)&v22,
        (__int64)&v33,
        (__int64)&v32,
        (__int64)&v42,
        (__int64)&v41,
        (__int64)&v31,
        (__int64)&StringRawBuffer_0,
        (__int64)&v40);
    }
  }
  else
  {
    wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v14 = CortanaSearchTelemetryLogging::Provider();
    v17 = (int)v14;
    if ( *(_DWORD *)v14 > 5u && (unsigned __int8)tlgKeywordOn(v14, 1, v15, v16) )
    {
      LODWORD(v40) = a2;
      v19 = wil::details::static_lazy<ConstraintIndexTelemetry>::get(
              v18,
              _lambda_3f32e471ee4016ff12f12bcbf8a58c4e_::_lambda_invoker_cdecl_);
      v29 = (__int64)WindowsGetStringRawBuffer_0(*(HSTRING *)(v19 + 24), 0);
      CurrentThreadId = GetCurrentThreadId();
      v21 = *((_QWORD *)this + 34);
      LODWORD(v41) = CurrentThreadId;
      LODWORD(v42) = *(_DWORD *)(v21 + 72);
      v28 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
        v17,
        (__int64)&v28,
        (__int64)&v42,
        (__int64)&v41,
        (__int64)&v29,
        (__int64)&v40);
    }
  }
  wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(this);
}

```

## disassembly

```asm
0x1800c4c18  push    rbp
0x1800c4c1a  push    rbx
0x1800c4c1b  push    rsi
0x1800c4c1c  push    rdi
0x1800c4c1d  push    r14
0x1800c4c1f  mov     rbp, rsp
0x1800c4c22  sub     rsp, 150h
0x1800c4c29  mov     rdi, [rcx+110h]
0x1800c4c30  mov     r14d, edx
0x1800c4c33  mov     rbx, rcx
0x1800c4c36  mov     eax, [rdi+48h]
0x1800c4c39  test    eax, eax
0x1800c4c3b  jns     loc_1800C4E24
0x1800c4c41  add     rdi, 50h ; 'P'
0x1800c4c45  cmp     eax, [rdi+8]
0x1800c4c48  jnz     loc_1800C4E24
0x1800c4c4e  test    rdi, rdi
0x1800c4c51  jz      loc_1800C4E24
0x1800c4c57  call    ?zInternalStop@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800c4c5c  call    ?Provider@CortanaSearchTelemetryLogging@@SAPEBU_tlgProvider_t@@XZ; CortanaSearchTelemetryLogging::Provider(void)
0x1800c4c61  mov     rsi, rax
0x1800c4c64  mov     ecx, [rax]
0x1800c4c66  cmp     ecx, 5
0x1800c4c69  jbe     loc_1800C4ECB
0x1800c4c6f  mov     edx, 1
0x1800c4c74  mov     rcx, rax
0x1800c4c77  call    _tlgKeywordOn
0x1800c4c7c  test    al, al
0x1800c4c7e  jz      loc_1800C4ECB
0x1800c4c84  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_3f32e471ee4016ff12f12bcbf8a58c4e_@@CA@XZ; _lambda_3f32e471ee4016ff12f12bcbf8a58c4e_::_lambda_invoker_cdecl_(void)
0x1800c4c8b  mov     dword ptr [rbp+arg_0], r14d
0x1800c4c8f  call    ?get@?$static_lazy@VConstraintIndexTelemetry@@@details@wil@@QEAAPEAVConstraintIndexTelemetry@@P6AXXZ@Z; wil::details::static_lazy<ConstraintIndexTelemetry>::get(void (*)(void))
0x1800c4c94  xor     edx, edx; length
0x1800c4c96  mov     rcx, [rax+18h]; string
0x1800c4c9a  call    WindowsGetStringRawBuffer_0
0x1800c4c9f  mov     [rbp+var_58], rax
0x1800c4ca3  mov     rax, [rdi+30h]
0x1800c4ca7  mov     [rbp+var_50], rax
0x1800c4cab  mov     eax, [rdi+44h]
0x1800c4cae  mov     dword ptr [rbp+arg_10], eax
0x1800c4cb1  mov     eax, [rdi+10h]
0x1800c4cb4  mov     dword ptr [rbp+arg_18], eax
0x1800c4cb7  mov     rax, [rdi+78h]
0x1800c4cbb  mov     [rbp+var_48], rax
0x1800c4cbf  mov     rax, [rdi+70h]
0x1800c4cc3  mov     r8, [rbx+110h]
0x1800c4cca  mov     [rbp+var_40], rax
0x1800c4cce  add     r8, 8; int
0x1800c4cd2  mov     eax, [rdi+68h]
0x1800c4cd5  mov     dword ptr [rbp+var_80], eax
0x1800c4cd8  mov     rax, [rdi+60h]
0x1800c4cdc  mov     [rbp+var_38], rax
0x1800c4ce0  mov     rax, [rdi+58h]
0x1800c4ce4  mov     [rbp+var_30], rax
0x1800c4ce8  mov     eax, [rdi+50h]
0x1800c4ceb  mov     dword ptr [rbp+var_80+4], eax
0x1800c4cee  mov     rax, [rdi+48h]
0x1800c4cf2  mov     [rbp+var_28], rax
0x1800c4cf6  mov     eax, [rdi+20h]
0x1800c4cf9  mov     dword ptr [rbp+var_78], eax
0x1800c4cfc  mov     rax, [rdi+18h]
0x1800c4d00  mov     [rbp+var_20], rax
0x1800c4d04  mov     eax, [rdi]
0x1800c4d06  mov     dword ptr [rbp+var_78+4], eax
0x1800c4d09  mov     rax, [rdi+80h]
0x1800c4d10  mov     [rbp+var_18], rax
0x1800c4d14  mov     eax, [rdi+40h]
0x1800c4d17  mov     [rbp+var_70], eax
0x1800c4d1a  mov     rax, [rdi+38h]
0x1800c4d1e  mov     [rbp+var_10], rax
0x1800c4d22  mov     eax, [rdi+8]
0x1800c4d25  mov     [rbp+var_6C], eax
0x1800c4d28  lea     rax, [rbp+arg_0]
0x1800c4d2c  mov     [rsp+150h+var_90], rax; __int64
0x1800c4d34  lea     rax, [rbp+var_58]
0x1800c4d38  mov     [rsp+150h+var_98], rax; __int64
0x1800c4d40  lea     rax, [rbp+var_50]
0x1800c4d44  mov     [rsp+150h+var_A0], rax; __int64
0x1800c4d4c  lea     rax, [rbp+arg_10]
0x1800c4d50  mov     [rsp+150h+var_A8], rax; __int64
0x1800c4d58  lea     rax, [rbp+arg_18]
0x1800c4d5c  mov     [rsp+150h+var_B0], rax; __int64
0x1800c4d64  lea     rax, [rbp+var_48]
0x1800c4d68  mov     [rsp+150h+var_B8], rax; __int64
0x1800c4d70  lea     rax, [rbp+var_40]
0x1800c4d74  mov     [rsp+150h+var_C0], rax; __int64
0x1800c4d7c  lea     rax, [rbp+var_80]
0x1800c4d80  mov     [rsp+150h+var_C8], rax; __int64
0x1800c4d88  lea     rax, [rbp+var_38]
0x1800c4d8c  mov     [rsp+150h+var_D0], rax; __int64
0x1800c4d94  lea     rax, [rbp+var_30]
0x1800c4d98  mov     [rsp+150h+var_D8], rax; __int64
0x1800c4d9d  lea     rax, [rbp+var_80+4]
0x1800c4da1  mov     [rsp+150h+var_E0], rax; __int64
0x1800c4da6  lea     rax, [rbp+var_28]
0x1800c4daa  mov     [rsp+150h+var_E8], rax; __int64
0x1800c4daf  lea     rax, [rbp+var_78]
0x1800c4db3  mov     [rsp+150h+var_F0], rax; __int64
0x1800c4db8  lea     rax, [rbp+var_20]
0x1800c4dbc  mov     [rsp+150h+var_F8], rax; __int64
0x1800c4dc1  lea     rax, [rbp+var_78+4]
0x1800c4dc5  mov     [rsp+150h+var_100], rax; __int64
0x1800c4dca  lea     rax, [rbp+var_18]
0x1800c4dce  mov     [rsp+150h+var_108], rax; __int64
0x1800c4dd3  lea     rax, [rbp+var_70]
0x1800c4dd7  mov     [rsp+150h+var_110], rax; __int64
0x1800c4ddc  lea     rax, [rbp+var_10]
0x1800c4de0  mov     [rsp+150h+var_118], rax; __int64
0x1800c4de5  mov     [rbp+var_68], 1000000h
0x1800c4ded  mov     [rbp+var_60], 0
0x1800c4df5  lea     rax, [rbp+var_6C]
0x1800c4df9  mov     rcx, rsi; int
0x1800c4dfc  mov     [rsp+150h+var_120], rax; __int64
0x1800c4e01  lea     rdx, unk_180114430; int
0x1800c4e08  lea     rax, [rbp+var_68]
0x1800c4e0c  mov     [rsp+150h+var_128], rax; __int64
0x1800c4e11  lea     rax, [rbp+var_60]
0x1800c4e15  mov     [rsp+150h+var_130], rax; __int64
0x1800c4e1a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@U4@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@4545645644564@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x1800c4e1f  jmp     loc_1800C4ECB
0x1800c4e24  call    ?zInternalStop@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800c4e29  call    ?Provider@CortanaSearchTelemetryLogging@@SAPEBU_tlgProvider_t@@XZ; CortanaSearchTelemetryLogging::Provider(void)
0x1800c4e2e  mov     rdi, rax
0x1800c4e31  mov     ecx, [rax]
0x1800c4e33  cmp     ecx, 5
0x1800c4e36  jbe     loc_1800C4ECB
0x1800c4e3c  mov     edx, 1
0x1800c4e41  mov     rcx, rax
0x1800c4e44  call    _tlgKeywordOn
0x1800c4e49  test    al, al
0x1800c4e4b  jz      short loc_1800C4ECB
0x1800c4e4d  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_3f32e471ee4016ff12f12bcbf8a58c4e_@@CA@XZ; _lambda_3f32e471ee4016ff12f12bcbf8a58c4e_::_lambda_invoker_cdecl_(void)
0x1800c4e54  mov     dword ptr [rbp+arg_0], r14d
0x1800c4e58  call    ?get@?$static_lazy@VConstraintIndexTelemetry@@@details@wil@@QEAAPEAVConstraintIndexTelemetry@@P6AXXZ@Z; wil::details::static_lazy<ConstraintIndexTelemetry>::get(void (*)(void))
0x1800c4e5d  xor     edx, edx; length
0x1800c4e5f  mov     rcx, [rax+18h]; string
0x1800c4e63  call    WindowsGetStringRawBuffer_0
0x1800c4e68  mov     [rbp+var_60], rax
0x1800c4e6c  call    cs:__imp_GetCurrentThreadId
0x1800c4e72  mov     r8, [rbx+110h]
0x1800c4e79  lea     rdx, word_1801143AA
0x1800c4e80  mov     dword ptr [rbp+arg_10], eax
0x1800c4e83  mov     rcx, rdi; int
0x1800c4e86  mov     eax, [r8+48h]
0x1800c4e8a  add     r8, 8
0x1800c4e8e  mov     dword ptr [rbp+arg_18], eax
0x1800c4e91  lea     rax, [rbp+arg_0]
0x1800c4e95  mov     [rsp+150h+var_110], rax; __int64
0x1800c4e9a  lea     rax, [rbp+var_60]
0x1800c4e9e  mov     [rsp+150h+var_118], rax; __int64
0x1800c4ea3  lea     rax, [rbp+arg_10]
0x1800c4ea7  mov     [rsp+150h+var_120], rax; __int64
0x1800c4eac  lea     rax, [rbp+arg_18]
0x1800c4eb0  mov     [rsp+150h+var_128], rax; __int64
0x1800c4eb5  lea     rax, [rbp+var_68]
0x1800c4eb9  mov     [rsp+150h+var_130], rax; __int64
0x1800c4ebe  mov     [rbp+var_68], 0
0x1800c4ec6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@_W@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@_W@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x1800c4ecb  mov     rcx, rbx
0x1800c4ece  add     rsp, 150h
0x1800c4ed5  pop     r14
0x1800c4ed7  pop     rdi
0x1800c4ed8  pop     rsi
0x1800c4ed9  pop     rbx
0x1800c4eda  pop     rbp
0x1800c4edb  jmp     ?IgnoreCurrentThread@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
