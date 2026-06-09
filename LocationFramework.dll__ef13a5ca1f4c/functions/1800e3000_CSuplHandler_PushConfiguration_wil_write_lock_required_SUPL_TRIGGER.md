# CSuplHandler::PushConfiguration(wil::write_lock_required,SUPL_TRIGGER)

- ea: `0x1800e3000`
- end: `0x1800e3750`
- name: `?PushConfiguration@CSuplHandler@@AEAAJUwrite_lock_required@wil@@W4SUPL_TRIGGER@@@Z`
- size: `1872`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, unsigned int)`
- caller_count: `6`
- callee_count: `23`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800e25d0`
- `0x1800e2b80`
- `0x1800e2bd8`
- `0x1800e2c30`
- `0x1800e2cf8`
- `0x1800e2f20`

## callees

- `0x180003100`
- `0x18000411c`
- `0x180012310`
- `0x180041414`
- `0x180048b98`
- `0x1800557e0`
- `0x1800594ac`
- `0x18005ab30`
- `0x18009077c`
- `0x18009c344`
- `0x1800a98c0`
- `0x1800df99c`
- `0x1800e2558`
- `0x1800e3000`
- `0x1800e3758`
- `0x1800e3790`
- `0x1800e3e34`
- `0x1800e429c`
- `0x1800e439c`
- `0x1800e4b9c`
- `0x1800e4c84`
- `0x1800e4dfc`
- `0x18015e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e34b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e3539`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e34b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e3539`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e3368`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e3376`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e348e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e3511`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e3368`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e3376`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e348e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e3511`

## string_xrefs

- `0x1800e35b1`: `ServerAccessInterval`
- `0x1800e3425`: `V2UPL_ServerAccessInterval`
- `0x1800e360e`: `DriverConfigFailed`
- `0x1800e3631`: `ConfigurationFailed`

## pseudocode

```c
__int64 __fastcall CSuplHandler::PushConfiguration(__int64 a1, const unsigned __int16 *a2, unsigned int a3)
{
  char v4; // di
  unsigned int v6; // r13d
  int v7; // ebx
  __int64 v8; // rsi
  __int64 (__fastcall *v9)(__int64, __int64 *); // rbx
  int v10; // eax
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  __int64 v14; // rbx
  __int64 (__fastcall *v15)(__int64, __int64 *); // rsi
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  __int64 v19; // rsi
  __int64 (__fastcall *v20)(__int64, __int64 *); // rbx
  __int64 v21; // rbx
  __int64 v22; // rsi
  __int64 (__fastcall *v23)(__int64, __int64 *); // rbx
  __int64 v24; // rsi
  __int64 (__fastcall *v25)(__int64, __int64 *); // rbx
  int v26; // eax
  __int64 v27; // rdx
  __int64 v28; // rdx
  __int64 v29; // rcx
  int v30; // r8d
  int v31; // r9d
  const wchar_t *v32; // rax
  __int16 *v33; // rdx
  int v35; // r15d
  __int64 v36; // rsi
  void (__fastcall *v37)(__int64, HSTRING *); // rbx
  int v38; // r8d
  int v39; // r9d
  __int64 v40; // rsi
  int (__fastcall *v41)(__int64, struct Windows::Networking::NetworkOperators::IMobileBroadbandUicc **); // rbx
  __int64 v42; // rdx
  int v43; // r8d
  int v44; // r9d
  __int64 v45; // rdx
  __int64 v46; // rcx
  const unsigned __int16 *v47; // rcx
  int v48; // eax
  unsigned int v49; // ebx
  __int64 v50; // rax
  __int64 v51; // rdx
  int v52; // [rsp+20h] [rbp-99h]
  int v53; // [rsp+20h] [rbp-99h]
  int v54; // [rsp+30h] [rbp-89h] BYREF
  PCWSTR StringRawBuffer; // [rsp+38h] [rbp-81h] BYREF
  unsigned int v56; // [rsp+40h] [rbp-79h] BYREF
  unsigned int v57; // [rsp+44h] [rbp-75h] BYREF
  unsigned int v58; // [rsp+48h] [rbp-71h] BYREF
  unsigned int v59; // [rsp+4Ch] [rbp-6Dh] BYREF
  const wchar_t *v60; // [rsp+50h] [rbp-69h] BYREF
  unsigned int v61; // [rsp+58h] [rbp-61h] BYREF
  unsigned int v62; // [rsp+5Ch] [rbp-5Dh] BYREF
  HSTRING string; // [rsp+60h] [rbp-59h] BYREF
  HSTRING v64; // [rsp+68h] [rbp-51h] BYREF
  __int64 v65; // [rsp+70h] [rbp-49h] BYREF
  __int64 v66; // [rsp+78h] [rbp-41h] BYREF
  __int64 v67; // [rsp+80h] [rbp-39h] BYREF
  int v68; // [rsp+88h] [rbp-31h] BYREF
  struct Windows::Networking::NetworkOperators::IMobileBroadbandUicc *v69; // [rsp+90h] [rbp-29h] BYREF
  __int64 v70; // [rsp+98h] [rbp-21h] BYREF
  __int64 v71; // [rsp+A0h] [rbp-19h] BYREF
  __int64 v72; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v73; // [rsp+B0h] [rbp-9h] BYREF
  HSTRING v74[2]; // [rsp+B8h] [rbp-1h] BYREF
  __int128 v75; // [rsp+C8h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v4 = (char)a2;
  v6 = 30;
  v56 = 30;
  v58 = 60;
  v57 = 1;
  v59 = 0;
  *(_OWORD *)v74 = 0;
  v75 = 0;
  Windows::Internal::StringReference::StringReference(v74, (const unsigned __int16 (*)[57])a2);
  v73 = 0;
  v71 = 0;
  v67 = 0;
  v65 = 0;
  v66 = 0;
  v70 = 0;
  v69 = 0;
  v72 = 0;
  v61 = 0;
  v68 = 0;
  v62 = 0;
  v64 = 0;
  string = 0;
  *(_DWORD *)(a1 + 960) = 0;
  if ( a3 != 4 )
    CSuplHandler::SuplConfigRetryBackOff((CSuplHandler *)a1, 0);
  v7 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Networking::NetworkOperators::IMobileBroadbandModemStatics>>(
         v74[0],
         &v73);
  if ( v7 < 0 )
    goto LABEL_35;
  v8 = v73;
  v9 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v73 + 64LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v67);
  v10 = v9(v8, &v67);
  if ( v10 < 0 )
    goto LABEL_34;
  if ( (unsigned int)dword_1801DDF30 > 4 )
  {
    LOBYTE(v54) = v67 != 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>>(
      v11,
      (unsigned int)word_1801AFD82,
      v12,
      v13,
      (__int64)&v54);
  }
  v14 = v67;
  if ( !v67 )
    goto LABEL_8;
  v15 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v67 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v65);
  v10 = v15(v14, &v65);
  if ( v10 < 0 )
    goto LABEL_34;
  if ( (unsigned int)dword_1801DDF30 > 4 )
  {
    LOBYTE(v54) = v65 != 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>>(
      v16,
      (unsigned int)&word_1801AFC96,
      v17,
      v18,
      (__int64)&v54);
  }
  if ( !v65 )
    goto LABEL_8;
  v19 = v67;
  v20 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v67 + 112LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v72);
  v10 = v20(v19, &v72);
  if ( v10 < 0 )
    goto LABEL_34;
  v21 = v72;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v71);
  v10 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Networking::NetworkOperators::MobileBroadbandModemConfiguration *>,Windows::Foundation::IAsyncOperation<Windows::Networking::NetworkOperators::MobileBroadbandModemConfiguration *>>(v21);
  if ( v10 < 0 )
    goto LABEL_34;
  v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v21 + 64LL))(v21, &v71);
  if ( v10 < 0 )
    goto LABEL_34;
  v22 = v65;
  v23 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v65 + 72LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v66);
  v10 = v23(v22, &v66);
  if ( v10 < 0 )
    goto LABEL_34;
  if ( !v66 )
  {
LABEL_8:
    v7 = 1;
    goto LABEL_35;
  }
  v24 = v65;
  v25 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v65 + 80LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v70);
  v10 = v25(v24, &v70);
  if ( v10 < 0 )
  {
LABEL_34:
    v7 = v10;
    goto LABEL_35;
  }
  if ( !v70 )
    goto LABEL_8;
  v26 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v66 + 56LL))(v66, &v61);
  v7 = v26;
  if ( v26 < 0 )
  {
    v27 = 173;
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v27,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\gnssadapter\\suplhandler.cpp",
      (const char *)(unsigned int)v26,
      v52);
    goto LABEL_35;
  }
  v26 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v66 + 96LL))(v66, &v62);
  v7 = v26;
  if ( v26 < 0 )
  {
    v27 = 174;
    goto LABEL_22;
  }
  if ( (byte_1801E39C1 & 0x40) != 0 )
    McTemplateU0qq_EventWriteTransfer(v29, SuplPushConfiguration, a3, v61);
  if ( (unsigned int)dword_1801DDF30 > 4 )
  {
    LODWORD(v60) = a3;
    LODWORD(StringRawBuffer) = v61;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (unsigned int)&dword_1801DDF30,
      (unsigned int)&dword_1801AFE14,
      v30,
      v31,
      (__int64)&StringRawBuffer,
      (__int64)&v60);
  }
  if ( v61 - 3 > 2 )
  {
    if ( (unsigned int)dword_1801DDF30 <= 4 )
    {
LABEL_33:
      v10 = CSuplHandler::ForcePositioningMethod(a1, v28, 3);
      goto LABEL_34;
    }
    v32 = L"NetworkRegisterationState";
    v33 = &word_1801AFC5E;
LABEL_32:
    StringRawBuffer = v32;
    v60 = L"Standalone";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      v29,
      v33);
    goto LABEL_33;
  }
  v35 = 0;
  if ( (int)CSuplHandler::PushV2SuplConfiguration(a1, v28, v62) >= 0 )
  {
    v35 = 1;
    CspRegistry::ReadDword(L"V2UPL_NiDefaultTimeout", &v56);
    CspRegistry::ReadDword(L"V2UPL_ServerAccessInterval", &v58);
    CspRegistry::ReadDword(L"V2UPL_LocMasterSwitchDependencyNII", &v57);
    CspRegistry::ReadDword(L"V2UPL_PositioningMethod_MR", &v59);
    v6 = v56;
  }
  v26 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v70 + 48LL))(v70, &v68);
  v7 = v26;
  if ( v26 < 0 )
  {
    v27 = 214;
    goto LABEL_22;
  }
  if ( v68 == 1 )
  {
    v36 = v71;
    v37 = *(void (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v71 + 56LL);
    WindowsDeleteString(v64);
    v64 = 0;
    v37(v36, &v64);
    if ( (unsigned int)dword_1801DDEF8 > 4 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(v64, 0);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (unsigned int)&dword_1801DDEF8,
        (unsigned int)byte_1801AFFB3,
        v38,
        v39,
        (__int64)&StringRawBuffer);
    }
  }
  v40 = v71;
  v41 = *(int (__fastcall **)(__int64, struct Windows::Networking::NetworkOperators::IMobileBroadbandUicc **))(*(_QWORD *)v71 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v69);
  if ( v41(v40, &v69) >= 0 )
  {
    if ( v69 )
    {
      WindowsDeleteString(string);
      string = 0;
      CSuplHandler::ReadHslpFromUiccApp(v69, &string);
      if ( (unsigned int)dword_1801DDF30 > 4 )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (unsigned int)&dword_1801DDF30,
          (unsigned int)&dword_1801AFDDC,
          v43,
          v44,
          (__int64)&StringRawBuffer);
      }
    }
  }
  v53 = (int)string;
  LOBYTE(v42) = v4;
  if ( (int)CSuplHandler::PushSuplConfiguration(a1, v42, v62, v64) >= 0 )
  {
    ++v35;
    v56 = 30;
    v58 = 60;
    v57 = 1;
    v59 = 0;
    CspRegistry::ReadDword(L"NiDefaultTimeout", &v56);
    CspRegistry::ReadDword(L"ServerAccessInterval", &v58);
    CspRegistry::ReadDword(L"LocMasterSwitchDependencyNII", &v57);
    CspRegistry::ReadDword(L"HighAccPositioningMethod", &v59);
    v6 = v56;
  }
  if ( *(_DWORD *)(a1 + 960) )
  {
    v10 = CSuplHandler::SuplConfigRetryBackOff((CSuplHandler *)a1, 1);
    if ( v10 < 0 )
      goto LABEL_34;
    if ( (unsigned int)dword_1801DDF30 <= 4 )
      goto LABEL_33;
    v32 = L"DriverConfigFailed";
    v33 = (__int16 *)byte_1801AFF23;
    goto LABEL_32;
  }
  if ( v35 )
  {
    *(_DWORD *)(a1 + 156) = v57;
    CSuplHandler::PushNiAllowSetting(a1);
    v48 = CspRegistry::WriteDword(v47, v6);
    if ( v48 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x12C,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\gnssadapter\\suplhandler.cpp",
        (const char *)(unsigned int)v48,
        v53);
    (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**(_QWORD **)(a1 + 120) + 40LL))(
      *(_QWORD *)(a1 + 120),
      15,
      v6 + 5);
    (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**(_QWORD **)(a1 + 120) + 40LL))(*(_QWORD *)(a1 + 120), 14, v58);
    v49 = v59;
    if ( v61 - 4 <= 1 )
      v49 = 3;
    v50 = CSuplHandler::ToString(v49);
    if ( (unsigned int)dword_1801DDF30 > 4 )
    {
      StringRawBuffer = L"BasedOnConditions";
      v60 = (const wchar_t *)v50;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        L"BasedOnConditions",
        &dword_1801AFDA4);
    }
    CSuplHandler::ForcePositioningMethod(a1, v51, v49);
    v7 = 0;
  }
  else
  {
    if ( (unsigned int)dword_1801DDF30 > 4 )
    {
      StringRawBuffer = L"ConfigurationFailed";
      v60 = L"Standalone";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        v46,
        byte_1801AFEEB);
    }
    CSuplHandler::ForcePositioningMethod(a1, v45, 3);
    v7 = -2147467259;
  }
LABEL_35:
  WindowsDeleteString(string);
  string = 0;
  WindowsDeleteString(v64);
  v64 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v72);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v69);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v70);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v66);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v65);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v67);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v71);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v73);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800e3000  mov     [rsp-8+arg_8], rbx
0x1800e3005  push    rbp
0x1800e3006  push    rsi
0x1800e3007  push    rdi
0x1800e3008  push    r12
0x1800e300a  push    r13
0x1800e300c  push    r14
0x1800e300e  push    r15
0x1800e3010  lea     rbp, [rsp-27h]
0x1800e3015  sub     rsp, 0E0h
0x1800e301c  mov     rax, cs:__security_cookie
0x1800e3023  xor     rax, rsp
0x1800e3026  mov     [rbp+57h+var_38], rax
0x1800e302a  mov     r15d, r8d
0x1800e302d  mov     dil, dl
0x1800e3030  mov     r14, rcx
0x1800e3033  mov     r13d, 1Eh
0x1800e3039  mov     [rbp+57h+var_D0], r13d
0x1800e303d  mov     [rbp+57h+var_C8], 3Ch ; '<'
0x1800e3044  mov     [rbp+57h+var_CC], 1
0x1800e304b  xor     r12d, r12d
0x1800e304e  mov     [rbp+57h+var_C4], r12d
0x1800e3052  xorps   xmm0, xmm0
0x1800e3055  movups  xmmword ptr [rbp+57h+var_58], xmm0
0x1800e3059  movups  [rbp+57h+var_48], xmm0
0x1800e305d  lea     rcx, [rbp+57h+var_58]; string
0x1800e3061  call    ??$?0$0DJ@@StringReference@Internal@Windows@@QEAA@AEAY0DJ@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[57])
0x1800e3066  mov     [rbp+57h+var_60], r12
0x1800e306a  mov     [rbp+57h+var_70], r12
0x1800e306e  mov     [rbp+57h+var_90], r12
0x1800e3072  mov     [rbp+57h+var_A0], r12
0x1800e3076  mov     [rbp+57h+var_98], r12
0x1800e307a  mov     [rbp+57h+var_78], r12
0x1800e307e  mov     [rbp+57h+var_80], r12
0x1800e3082  mov     [rbp+57h+var_68], r12
0x1800e3086  mov     [rbp+57h+var_B8], r12d
0x1800e308a  mov     [rbp+57h+var_88], r12d
0x1800e308e  mov     [rbp+57h+var_B4], r12d
0x1800e3092  mov     [rbp+57h+var_A8], r12
0x1800e3096  mov     [rbp+57h+string], r12
0x1800e309a  mov     [r14+3C0h], r12d
0x1800e30a1  cmp     r15d, 4
0x1800e30a5  jz      short loc_1800E30B1
0x1800e30a7  xor     edx, edx; int
0x1800e30a9  mov     rcx, r14; this
0x1800e30ac  call    ?SuplConfigRetryBackOff@CSuplHandler@@AEAAJH@Z; CSuplHandler::SuplConfigRetryBackOff(int)
0x1800e30b1  lea     rdx, [rbp+57h+var_60]
0x1800e30b5  mov     rcx, [rbp+57h+var_58]
0x1800e30b9  call    ??$GetActivationFactory@V?$ComPtr@UIMobileBroadbandModemStatics@NetworkOperators@Networking@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIMobileBroadbandModemStatics@NetworkOperators@Networking@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Networking::NetworkOperators::IMobileBroadbandModemStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Networking::NetworkOperators::IMobileBroadbandModemStatics>>)
0x1800e30be  mov     ebx, eax
0x1800e30c0  test    eax, eax
0x1800e30c2  js      loc_1800E3364
0x1800e30c8  mov     rsi, [rbp+57h+var_60]
0x1800e30cc  mov     rax, [rsi]
0x1800e30cf  mov     rbx, [rax+40h]
0x1800e30d3  lea     rcx, [rbp+57h+var_90]
0x1800e30d7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800e30dc  lea     rdx, [rbp+57h+var_90]
0x1800e30e0  mov     rcx, rsi
0x1800e30e3  mov     rax, rbx
0x1800e30e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e30eb  test    eax, eax
0x1800e30ed  js      loc_1800E3362
0x1800e30f3  mov     eax, cs:dword_1801DDF30
0x1800e30f9  cmp     eax, 4
0x1800e30fc  jbe     short loc_1800E311D
0x1800e30fe  cmp     [rbp+57h+var_90], r12
0x1800e3102  setnz   byte ptr [rsp+110h+var_E0]
0x1800e3107  lea     rax, [rsp+110h+var_E0]
0x1800e310c  mov     qword ptr [rsp+110h+var_F0], rax
0x1800e3111  lea     rdx, word_1801AFD82
0x1800e3118  call    ??$Write@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<1> const &)
0x1800e311d  mov     rbx, [rbp+57h+var_90]
0x1800e3121  test    rbx, rbx
0x1800e3124  jnz     short loc_1800E3130
0x1800e3126  mov     ebx, 1
0x1800e312b  jmp     loc_1800E3364
0x1800e3130  mov     rax, [rbx]
0x1800e3133  mov     rsi, [rax+30h]
0x1800e3137  lea     rcx, [rbp+57h+var_A0]
0x1800e313b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800e3140  lea     rdx, [rbp+57h+var_A0]
0x1800e3144  mov     rcx, rbx
0x1800e3147  mov     rax, rsi
0x1800e314a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e314f  test    eax, eax
0x1800e3151  js      loc_1800E3362
0x1800e3157  mov     eax, cs:dword_1801DDF30
0x1800e315d  cmp     eax, 4
0x1800e3160  jbe     short loc_1800E3181
0x1800e3162  cmp     [rbp+57h+var_A0], r12
0x1800e3166  setnz   byte ptr [rsp+110h+var_E0]
0x1800e316b  lea     rax, [rsp+110h+var_E0]
0x1800e3170  mov     qword ptr [rsp+110h+var_F0], rax; int
0x1800e3175  lea     rdx, word_1801AFC96
0x1800e317c  call    ??$Write@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<1> const &)
0x1800e3181  cmp     [rbp+57h+var_A0], r12
0x1800e3185  jz      short loc_1800E3126
0x1800e3187  mov     rsi, [rbp+57h+var_90]
0x1800e318b  mov     rax, [rsi]
0x1800e318e  mov     rbx, [rax+70h]
0x1800e3192  lea     rcx, [rbp+57h+var_68]
0x1800e3196  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800e319b  lea     rdx, [rbp+57h+var_68]
0x1800e319f  mov     rcx, rsi
0x1800e31a2  mov     rax, rbx
0x1800e31a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e31aa  test    eax, eax
0x1800e31ac  js      loc_1800E3362
0x1800e31b2  mov     rbx, [rbp+57h+var_68]
0x1800e31b6  lea     rcx, [rbp+57h+var_70]
0x1800e31ba  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800e31bf  mov     rcx, rbx
0x1800e31c2  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVMobileBroadbandModemConfiguration@NetworkOperators@Networking@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVMobileBroadbandModemConfiguration@NetworkOperators@Networking@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVMobileBroadbandModemConfiguration@NetworkOperators@Networking@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Networking::NetworkOperators::MobileBroadbandModemConfiguration *>,Windows::Foundation::IAsyncOperation<Windows::Networking::NetworkOperators::MobileBroadbandModemConfiguration *>>(Windows::Foundation::IAsyncOperation<Windows::Networking::NetworkOperators::MobileBroadbandModemConfiguration *> *,tagCOWAIT_FLAGS,void *)
0x1800e31c7  test    eax, eax
0x1800e31c9  js      loc_1800E3362
0x1800e31cf  mov     rax, [rbx]
0x1800e31d2  lea     rdx, [rbp+57h+var_70]
0x1800e31d6  mov     rcx, rbx
0x1800e31d9  mov     rax, [rax+40h]
0x1800e31dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e31e2  test    eax, eax
0x1800e31e4  js      loc_1800E3362
0x1800e31ea  mov     rsi, [rbp+57h+var_A0]
0x1800e31ee  mov     rax, [rsi]
0x1800e31f1  mov     rbx, [rax+48h]
0x1800e31f5  lea     rcx, [rbp+57h+var_98]
0x1800e31f9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800e31fe  lea     rdx, [rbp+57h+var_98]
0x1800e3202  mov     rcx, rsi
0x1800e3205  mov     rax, rbx
0x1800e3208  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e320d  test    eax, eax
0x1800e320f  js      loc_1800E3362
0x1800e3215  cmp     [rbp+57h+var_98], r12
0x1800e3219  jz      loc_1800E3126
0x1800e321f  mov     rsi, [rbp+57h+var_A0]
0x1800e3223  mov     rax, [rsi]
0x1800e3226  mov     rbx, [rax+50h]
0x1800e322a  lea     rcx, [rbp+57h+var_78]
0x1800e322e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800e3233  lea     rdx, [rbp+57h+var_78]
0x1800e3237  mov     rcx, rsi
0x1800e323a  mov     rax, rbx
0x1800e323d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3242  test    eax, eax
0x1800e3244  js      loc_1800E3362
0x1800e324a  cmp     [rbp+57h+var_78], r12
0x1800e324e  jz      loc_1800E3126
0x1800e3254  mov     rcx, [rbp+57h+var_98]
0x1800e3258  mov     rax, [rcx]
0x1800e325b  lea     rdx, [rbp+57h+var_B8]
0x1800e325f  mov     rax, [rax+38h]
0x1800e3263  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3268  mov     ebx, eax
0x1800e326a  test    eax, eax
0x1800e326c  jns     short loc_1800E328B
0x1800e326e  mov     edx, 0ADh; void *
0x1800e3273  mov     rcx, [rbp+5Fh]; this
0x1800e3277  mov     r9d, eax; char *
0x1800e327a  lea     r8, aOnecoreuapDriv_19; "onecoreuap\\drivers\\mobilepc\\location"...
0x1800e3281  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e3286  jmp     loc_1800E3364
0x1800e328b  mov     rcx, [rbp+57h+var_98]
0x1800e328f  mov     rax, [rcx]
0x1800e3292  lea     rdx, [rbp+57h+var_B4]
0x1800e3296  mov     rax, [rax+60h]
0x1800e329a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e329f  mov     ebx, eax
0x1800e32a1  test    eax, eax
0x1800e32a3  jns     short loc_1800E32AC
0x1800e32a5  mov     edx, 0AEh
0x1800e32aa  jmp     short loc_1800E3273
0x1800e32ac  test    cs:byte_1801E39C1, 40h
0x1800e32b3  jz      short loc_1800E32C8
0x1800e32b5  mov     r9d, [rbp+57h+var_B8]
0x1800e32b9  mov     r8d, r15d
0x1800e32bc  lea     rdx, SuplPushConfiguration
0x1800e32c3  call    McTemplateU0qq_EventWriteTransfer
0x1800e32c8  mov     eax, cs:dword_1801DDF30
0x1800e32ce  cmp     eax, 4
0x1800e32d1  jbe     short loc_1800E3304
0x1800e32d3  mov     dword ptr [rbp+57h+var_C0], r15d
0x1800e32d7  mov     eax, [rbp+57h+var_B8]
0x1800e32da  mov     dword ptr [rsp+110h+var_D8], eax
0x1800e32de  lea     rax, [rbp+57h+var_C0]
0x1800e32e2  mov     [rsp+110h+var_E8], rax
0x1800e32e7  lea     rax, [rsp+110h+var_D8]
0x1800e32ec  mov     qword ptr [rsp+110h+var_F0], rax
0x1800e32f1  lea     rdx, dword_1801AFE14
0x1800e32f8  lea     rcx, dword_1801DDF30
0x1800e32ff  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800e3304  mov     eax, [rbp+57h+var_B8]
0x1800e3307  add     eax, 0FFFFFFFDh
0x1800e330a  cmp     eax, 2
0x1800e330d  jbe     loc_1800E33F8
0x1800e3313  mov     eax, cs:dword_1801DDF30
0x1800e3319  cmp     eax, 4
0x1800e331c  jbe     short loc_1800E3354
0x1800e331e  lea     rax, aNetworkregiste; "NetworkRegisterationState"
0x1800e3325  lea     rdx, word_1801AFC5E
0x1800e332c  mov     [rsp+110h+var_D8], rax
0x1800e3331  lea     rax, aStandalone; "Standalone"
0x1800e3338  mov     [rbp+57h+var_C0], rax
0x1800e333c  lea     rax, [rsp+110h+var_D8]
0x1800e3341  mov     [rsp+110h+var_E8], rax
0x1800e3346  lea     rax, [rbp+57h+var_C0]
0x1800e334a  mov     qword ptr [rsp+110h+var_F0], rax
0x1800e334f  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1800e3354  mov     r8d, 3
0x1800e335a  mov     rcx, r14
0x1800e335d  call    ?ForcePositioningMethod@CSuplHandler@@AEAAJUwrite_lock_required@wil@@W4CspPositioningMethod@@@Z; CSuplHandler::ForcePositioningMethod(wil::write_lock_required,CspPositioningMethod)
0x1800e3362  mov     ebx, eax
0x1800e3364  mov     rcx, [rbp+57h+string]; string
0x1800e3368  call    cs:__imp_WindowsDeleteString
0x1800e336e  mov     [rbp+57h+string], r12
0x1800e3372  mov     rcx, [rbp+57h+var_A8]; string
0x1800e3376  call    cs:__imp_WindowsDeleteString
0x1800e337c  mov     [rbp+57h+var_A8], r12
0x1800e3380  lea     rcx, [rbp+57h+var_68]
0x1800e3384  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800e3389  nop
0x1800e338a  lea     rcx, [rbp+57h+var_80]
0x1800e338e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800e3393  nop
0x1800e3394  lea     rcx, [rbp+57h+var_78]
0x1800e3398  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800e339d  nop
0x1800e339e  lea     rcx, [rbp+57h+var_98]
0x1800e33a2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800e33a7  nop
0x1800e33a8  lea     rcx, [rbp+57h+var_A0]
0x1800e33ac  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800e33b1  nop
0x1800e33b2  lea     rcx, [rbp+57h+var_90]
0x1800e33b6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800e33bb  nop
0x1800e33bc  lea     rcx, [rbp+57h+var_70]
0x1800e33c0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800e33c5  nop
0x1800e33c6  lea     rcx, [rbp+57h+var_60]
0x1800e33ca  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800e33cf  mov     eax, ebx
0x1800e33d1  mov     rcx, [rbp+57h+var_38]
0x1800e33d5  xor     rcx, rsp; StackCookie
0x1800e33d8  call    __security_check_cookie
0x1800e33dd  mov     rbx, [rsp+110h+arg_8]
0x1800e33e5  add     rsp, 0E0h
0x1800e33ec  pop     r15
0x1800e33ee  pop     r14
0x1800e33f0  pop     r13
0x1800e33f2  pop     r12
0x1800e33f4  pop     rdi
0x1800e33f5  pop     rsi
0x1800e33f6  pop     rbp
0x1800e33f7  retn
0x1800e33f8  mov     r15d, r12d
0x1800e33fb  mov     r8d, [rbp+57h+var_B4]
0x1800e33ff  mov     rcx, r14
0x1800e3402  call    ?PushV2SuplConfiguration@CSuplHandler@@AEAAJUwrite_lock_required@wil@@W4DataClasses@NetworkOperators@Networking@Windows@@@Z; CSuplHandler::PushV2SuplConfiguration(wil::write_lock_required,Windows::Networking::NetworkOperators::DataClasses)
0x1800e3407  test    eax, eax
0x1800e3409  js      short loc_1800E3455
0x1800e340b  mov     r15d, 1
0x1800e3411  lea     rdx, [rbp+57h+var_D0]; unsigned int *
0x1800e3415  lea     rcx, aV2uplNidefault; "V2UPL_NiDefaultTimeout"
0x1800e341c  call    ?ReadDword@CspRegistry@@SAJPEBGPEAK@Z; CspRegistry::ReadDword(ushort const *,ulong *)
0x1800e3421  lea     rdx, [rbp+57h+var_C8]; unsigned int *
0x1800e3425  lea     rcx, aV2uplServeracc; "V2UPL_ServerAccessInterval"
0x1800e342c  call    ?ReadDword@CspRegistry@@SAJPEBGPEAK@Z; CspRegistry::ReadDword(ushort const *,ulong *)
0x1800e3431  lea     rdx, [rbp+57h+var_CC]; unsigned int *
0x1800e3435  lea     rcx, aV2uplLocmaster; "V2UPL_LocMasterSwitchDependencyNII"
0x1800e343c  call    ?ReadDword@CspRegistry@@SAJPEBGPEAK@Z; CspRegistry::ReadDword(ushort const *,ulong *)
0x1800e3441  lea     rdx, [rbp+57h+var_C4]; unsigned int *
0x1800e3445  lea     rcx, aV2uplPositioni; "V2UPL_PositioningMethod_MR"
0x1800e344c  call    ?ReadDword@CspRegistry@@SAJPEBGPEAK@Z; CspRegistry::ReadDword(ushort const *,ulong *)
0x1800e3451  mov     r13d, [rbp+57h+var_D0]
0x1800e3455  mov     rcx, [rbp+57h+var_78]
0x1800e3459  mov     rax, [rcx]
0x1800e345c  lea     rdx, [rbp+57h+var_88]
0x1800e3460  mov     rax, [rax+30h]
0x1800e3464  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3469  mov     ebx, eax
0x1800e346b  test    eax, eax
0x1800e346d  jns     short loc_1800E3479
0x1800e346f  mov     edx, 0D6h
0x1800e3474  jmp     loc_1800E3273
0x1800e3479  cmp     [rbp+57h+var_88], 1
0x1800e347d  jnz     short loc_1800E34E0
0x1800e347f  mov     rsi, [rbp+57h+var_70]
0x1800e3483  mov     rax, [rsi]
0x1800e3486  mov     rbx, [rax+38h]
0x1800e348a  mov     rcx, [rbp+57h+var_A8]; string
0x1800e348e  call    cs:__imp_WindowsDeleteString
0x1800e3494  mov     [rbp+57h+var_A8], r12
0x1800e3498  lea     rdx, [rbp+57h+var_A8]
0x1800e349c  mov     rcx, rsi
0x1800e349f  mov     rax, rbx
0x1800e34a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e34a7  mov     eax, cs:dword_1801DDEF8
0x1800e34ad  cmp     eax, 4
  ... truncated ...
```
