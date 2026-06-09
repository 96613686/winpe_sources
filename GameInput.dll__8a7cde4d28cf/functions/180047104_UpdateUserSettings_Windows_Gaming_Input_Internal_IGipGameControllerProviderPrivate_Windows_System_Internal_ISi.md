# UpdateUserSettings(Windows::Gaming::Input::Internal::IGipGameControllerProviderPrivate *,Windows::System::Internal::ISignInStateManager *,Windows::System::IUser *)

- ea: `0x180047104`
- end: `0x180047c85`
- name: `?UpdateUserSettings@@YAJPEAUIGipGameControllerProviderPrivate@Internal@Input@Gaming@Windows@@PEAUISignInStateManager@2System@5@PEAUIUser@75@@Z`
- size: `2945`
- prototype: `__int64 __fastcall(struct Windows::Gaming::Input::Internal::IGipGameControllerProviderPrivate *, struct Windows::System::Internal::ISignInStateManager *, struct Windows::System::IUser *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180046920`
- `0x180047c8c`

## callees

- `0x180001304`
- `0x18003fe64`
- `0x180045b18`
- `0x180046570`
- `0x180047104`
- `0x18004c8e0`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180047431`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180047431`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047476`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800477f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004791b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047a16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047b71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047b91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047bb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047bd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047bf1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047c0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047c2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047c4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047c68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047476`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800477f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004791b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047a16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047b71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047b91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047bb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047bd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047bf1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047c0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047c2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047c4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047c68`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800477e2`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180047907`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180047a02`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800477e2`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180047907`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180047a02`

## string_xrefs

- `0x180047198`: `onecore\xbox\gameinput\xboxgipservices\SettingsHelper.cpp`
- `0x180047254`: `onecore\xbox\gameinput\xboxgipservices\SettingsHelper.cpp`
- `0x1800472e8`: `onecore\xbox\gameinput\xboxgipservices\SettingsHelper.cpp`
- `0x1800474b2`: `onecore\xbox\gameinput\xboxgipservices\SettingsHelper.cpp`
- `0x180047584`: `onecore\xbox\gameinput\xboxgipservices\SettingsHelper.cpp`
- `0x180047659`: `onecore\xbox\gameinput\xboxgipservices\SettingsHelper.cpp`
- `0x18004772e`: `onecore\xbox\gameinput\xboxgipservices\SettingsHelper.cpp`
- `0x180047832`: `onecore\xbox\gameinput\xboxgipservices\SettingsHelper.cpp`
- `0x180047957`: `onecore\xbox\gameinput\xboxgipservices\SettingsHelper.cpp`
- `0x180047a52`: `onecore\xbox\gameinput\xboxgipservices\SettingsHelper.cpp`

## pseudocode

```c
__int64 __fastcall UpdateUserSettings(
        struct Windows::Gaming::Input::Internal::IGipGameControllerProviderPrivate *a1,
        struct Windows::System::Internal::ISignInStateManager *a2,
        struct Windows::System::IUser *a3)
{
  __int64 v4; // rax
  __int64 v5; // rdx
  signed int v6; // ebx
  __int64 v7; // r8
  int v8; // r9d
  _QWORD *v9; // rcx
  __int64 v11; // rax
  int v12; // r9d
  int v13; // r9d
  int v14; // ecx
  __int16 *v15; // rdx
  __int64 v16; // rcx
  char AccessibilitySettings; // r14
  __int64 v18; // r8
  __int128 *p_OutBuffer; // rsi
  __int128 *v20; // rcx
  HANDLE FileW; // rax
  HANDLE v22; // rcx
  void *v23; // rbx
  int v24; // r9d
  __int64 v25; // rax
  int v26; // r9d
  const char *v27; // rcx
  __int64 v28; // rax
  int v29; // r9d
  const char *v30; // rcx
  __int64 v31; // rax
  int v32; // r9d
  const char *v33; // rcx
  int v34; // r9d
  const char *v35; // rcx
  const char *v36; // rcx
  int v37; // r9d
  HANDLE v38; // rcx
  __int64 v39; // r8
  int v40; // r9d
  __int64 v41; // rcx
  _QWORD *v42; // rcx
  __int64 v43; // rcx
  _QWORD *v44; // rcx
  signed int v45; // eax
  int v46; // edx
  unsigned int v47; // r8d
  signed int v48; // eax
  int v49; // edx
  unsigned int v50; // r8d
  signed int v51; // eax
  int v52; // edx
  unsigned int v53; // r8d
  signed int v54; // eax
  int v55; // edx
  unsigned int v56; // r8d
  signed int v57; // eax
  int v58; // edx
  unsigned int v59; // r8d
  signed int v60; // eax
  int v61; // edx
  unsigned int v62; // r8d
  signed int LastError; // eax
  int v64; // edx
  unsigned int v65; // r8d
  signed int v66; // eax
  int v67; // edx
  unsigned int v68; // r8d
  signed int v69; // eax
  int v70; // edx
  unsigned int v71; // r8d
  _BYTE v72[4]; // [rsp+40h] [rbp-69h] BYREF
  int v73; // [rsp+44h] [rbp-65h] BYREF
  int v74; // [rsp+48h] [rbp-61h] BYREF
  _QWORD *v75; // [rsp+50h] [rbp-59h] BYREF
  char v76[8]; // [rsp+58h] [rbp-51h] BYREF
  const char *v77; // [rsp+60h] [rbp-49h] BYREF
  __int64 v78; // [rsp+68h] [rbp-41h] BYREF
  void **v79; // [rsp+70h] [rbp-39h] BYREF
  HANDLE hDevice; // [rsp+78h] [rbp-31h]
  GUID v81; // [rsp+80h] [rbp-29h] BYREF
  __int64 v82; // [rsp+90h] [rbp-19h] BYREF
  __int64 v83; // [rsp+98h] [rbp-11h] BYREF
  __int128 InBuffer; // [rsp+A0h] [rbp-9h] BYREF
  __int64 v85; // [rsp+B0h] [rbp+7h] BYREF
  __int128 OutBuffer; // [rsp+B8h] [rbp+Fh] BYREF

  if ( a3 )
  {
    v4 = *(_QWORD *)a2;
    v75 = 0;
    v6 = (*(__int64 (__fastcall **)(struct Windows::System::Internal::ISignInStateManager *, struct Windows::System::IUser *, _QWORD **))(v4 + 168))(
           a2,
           a3,
           &v75);
    if ( v6 < 0 )
    {
      if ( (unsigned int)dword_180069000 > 2 )
      {
        v7 = qword_180069018;
        v5 = 2048;
        if ( (qword_180069010 & 0x800) != 0 && (qword_180069018 & 0x800) == qword_180069018 )
        {
          v73 = v6;
          v77 = "onecore\\xbox\\gameinput\\xboxgipservices\\SettingsHelper.cpp";
          v74 = 200;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            qword_180069010,
            (unsigned int)&dword_18006333C,
            qword_180069018,
            v8,
            (__int64)&v77,
            (__int64)&v74,
            (__int64)&v73);
        }
      }
LABEL_7:
      v9 = v75;
      if ( v75 )
      {
        v75 = 0;
        (*(void (__fastcall **)(_QWORD *, __int64, __int64))(*v9 + 16LL))(v9, v5, v7);
      }
      return (unsigned int)v6;
    }
    v72[0] = 0;
    v85 = 0;
    v11 = *(_QWORD *)a1;
    v83 = 0;
    InBuffer = 0;
    v82 = 0;
    v6 = (*(__int64 (__fastcall **)(struct Windows::Gaming::Input::Internal::IGipGameControllerProviderPrivate *, __int64 *))(v11 + 64))(
           a1,
           &v82);
    if ( v6 < 0 )
    {
      if ( (unsigned int)dword_180069000 > 2 )
      {
        v7 = qword_180069018;
        v5 = 2048;
        if ( (qword_180069010 & 0x800) != 0 && (qword_180069018 & 0x800) == qword_180069018 )
        {
          v74 = v6;
          v77 = "onecore\\xbox\\gameinput\\xboxgipservices\\SettingsHelper.cpp";
          v73 = 209;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            qword_180069010,
            (unsigned int)word_18006394A,
            qword_180069018,
            v12,
            (__int64)&v77,
            (__int64)&v73,
            (__int64)&v74);
        }
      }
      goto LABEL_7;
    }
    *(_QWORD *)&InBuffer = v82;
    v78 = 0;
    v6 = (*(__int64 (__fastcall **)(_QWORD *, __int64 *))(*v75 + 88LL))(v75, &v78);
    if ( v6 < 0 )
    {
      if ( (unsigned int)dword_180069000 > 2 )
      {
        v7 = qword_180069018;
        v5 = 2048;
        v14 = qword_180069010;
        if ( (qword_180069010 & 0x800) != 0 && (qword_180069018 & 0x800) == qword_180069018 )
        {
          v73 = 214;
          v15 = (__int16 *)byte_1800636E5;
LABEL_20:
          v77 = "onecore\\xbox\\gameinput\\xboxgipservices\\SettingsHelper.cpp";
          v74 = v6;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v14,
            (_DWORD)v15,
            v7,
            v13,
            (__int64)&v77,
            (__int64)&v73,
            (__int64)&v74);
          goto LABEL_21;
        }
      }
      goto LABEL_21;
    }
    AccessibilitySettings = anonymous_namespace_::GetAccessibilitySettings(
                              v82,
                              v78,
                              (unsigned int)&v83,
                              (unsigned int)&InBuffer + 8,
                              (__int64)&v85,
                              (__int64)v72);
    LOBYTE(v18) = v72[0];
    v6 = (*(__int64 (__fastcall **)(struct Windows::Gaming::Input::Internal::IGipGameControllerProviderPrivate *, __int64, __int64))(*(_QWORD *)a1 + 224LL))(
           a1,
           1,
           v18);
    if ( v6 < 0 )
    {
      if ( (unsigned int)dword_180069000 > 2 )
      {
        v7 = qword_180069018;
        v5 = 2048;
        v14 = qword_180069010;
        if ( (qword_180069010 & 0x800) != 0 && (qword_180069018 & 0x800) == qword_180069018 )
        {
          v73 = 226;
          v15 = &word_180063856;
          goto LABEL_20;
        }
      }
LABEL_21:
      v16 = v78;
      if ( v78 )
      {
        v78 = 0;
        (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v16 + 16LL))(v16, v5, v7);
      }
      goto LABEL_7;
    }
    hDevice = (HANDLE)-1LL;
    p_OutBuffer = (__int128 *)((char *)&OutBuffer + 8);
    if ( AccessibilitySettings )
      p_OutBuffer = &OutBuffer;
    OutBuffer = 0;
    v20 = &OutBuffer;
    if ( AccessibilitySettings )
      v20 = (__int128 *)((char *)&OutBuffer + 8);
    v79 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::`vftable';
    *(_QWORD *)v20 = v82;
    *(_QWORD *)p_OutBuffer = 0;
    FileW = CreateFileW(L"\\\\.\\XboxGIP", 0xC0000000, 3u, 0, 3u, 0xA0000000, 0);
    v22 = hDevice;
    v23 = FileW;
    if ( FileW != hDevice )
    {
      if ( hDevice != (HANDLE)-1LL && !((unsigned __int8 (__fastcall *)(void ***))*v79)(&v79) )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v64, v65);
        __debugbreak();
      }
      v22 = v23;
      hDevice = v23;
    }
    if ( v22 == (HANDLE)-1LL )
    {
      v6 = GetLastError();
      if ( (unsigned int)dword_180069000 > 2 )
      {
        v5 = 2048;
        if ( (qword_180069010 & 0x800) != 0 && (qword_180069018 & 0x800) == qword_180069018 )
        {
          v74 = v6;
          v77 = "onecore\\xbox\\gameinput\\xboxgipservices\\SettingsHelper.cpp";
          v73 = 251;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            qword_180069018,
            (unsigned int)byte_1800634BD,
            v7,
            v24,
            (__int64)&v77,
            (__int64)&v73,
            (__int64)&v74);
        }
      }
      if ( v6 )
      {
        if ( v6 > 0 )
          v6 = (unsigned __int16)v6 | 0x80070000;
      }
      else
      {
        v6 = -2147418113;
      }
      v79 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::`vftable';
      if ( hDevice == (HANDLE)-1LL )
        goto LABEL_21;
      if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::InternalClose(&v79) )
      {
        v66 = GetLastError();
        if ( v66 > 0 )
          v66 = (unsigned __int16)v66 | 0x80070000;
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v66, v67, v68);
        __debugbreak();
      }
      goto LABEL_47;
    }
    v25 = *(_QWORD *)a1;
    v72[0] = 0;
    v76[0] = 0;
    v77 = 0;
    v6 = (*(__int64 (__fastcall **)(struct Windows::Gaming::Input::Internal::IGipGameControllerProviderPrivate *, const char **))(v25 + 120))(
           a1,
           &v77);
    if ( v6 < 0 )
    {
      if ( (unsigned int)dword_180069000 > 2 )
      {
        v7 = qword_180069018;
        v5 = 2048;
        if ( (qword_180069010 & 0x800) != 0 && (qword_180069018 & 0x800) == qword_180069018 )
        {
          v74 = v6;
          *(_QWORD *)&v81.Data1 = "onecore\\xbox\\gameinput\\xboxgipservices\\SettingsHelper.cpp";
          v73 = 258;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            qword_180069010,
            (unsigned int)&unk_180063480,
            qword_180069018,
            v26,
            (__int64)&v81,
            (__int64)&v73,
            (__int64)&v74);
        }
      }
      v27 = v77;
      if ( v77 )
      {
        v77 = 0;
        (*(void (__fastcall **)(const char *, __int64, __int64))(*(_QWORD *)v27 + 16LL))(v27, v5, v7);
      }
      v79 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::`vftable';
      if ( hDevice == (HANDLE)-1LL )
        goto LABEL_21;
      if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::InternalClose(&v79) )
      {
        v48 = GetLastError();
        if ( v48 > 0 )
          v48 = (unsigned __int16)v48 | 0x80070000;
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v48, v49, v50);
        __debugbreak();
      }
      goto LABEL_47;
    }
    v28 = *(_QWORD *)v77;
    v81 = GUID_GIP_MICROSOFT_XBOX_INPUT_IELITEGAMEPAD;
    v6 = (*(__int64 (__fastcall **)(const char *, GUID *, _BYTE *))(v28 + 120))(v77, &v81, v72);
    if ( v6 < 0 )
    {
      if ( (unsigned int)dword_180069000 > 2 )
      {
        v7 = qword_180069018;
        v5 = 2048;
        if ( (qword_180069010 & 0x800) != 0 && (qword_180069018 & 0x800) == qword_180069018 )
        {
          v74 = v6;
          *(_QWORD *)&v81.Data1 = "onecore\\xbox\\gameinput\\xboxgipservices\\SettingsHelper.cpp";
          v73 = 261;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            qword_180069010,
            (unsigned int)&byte_1800632AF,
            qword_180069018,
            v29,
            (__int64)&v81,
            (__int64)&v73,
            (__int64)&v74);
        }
      }
      v30 = v77;
      if ( v77 )
      {
        v77 = 0;
        (*(void (__fastcall **)(const char *, __int64, __int64))(*(_QWORD *)v30 + 16LL))(v30, v5, v7);
      }
      v79 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::`vftable';
      if ( hDevice == (HANDLE)-1LL )
        goto LABEL_21;
      if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::InternalClose(&v79) )
      {
        v51 = GetLastError();
        if ( v51 > 0 )
          v51 = (unsigned __int16)v51 | 0x80070000;
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v51, v52, v53);
        __debugbreak();
      }
      goto LABEL_47;
    }
    v31 = *(_QWORD *)v77;
    v81 = GUID_GIP_MICROSOFT_XBOX_INPUT_IPROGRAMMABLEGAMEPAD;
    v6 = (*(__int64 (__fastcall **)(const char *, GUID *, char *))(v31 + 120))(v77, &v81, v76);
    if ( v6 < 0 )
    {
      if ( (unsigned int)dword_180069000 > 2 )
      {
        v7 = qword_180069018;
        v5 = 2048;
        if ( (qword_180069010 & 0x800) != 0 && (qword_180069018 & 0x800) == qword_180069018 )
        {
          v74 = v6;
          *(_QWORD *)&v81.Data1 = "onecore\\xbox\\gameinput\\xboxgipservices\\SettingsHelper.cpp";
          v73 = 262;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            qword_180069010,
            (unsigned int)&unk_1800636A8,
            qword_180069018,
            v32,
            (__int64)&v81,
            (__int64)&v73,
            (__int64)&v74);
        }
      }
      v33 = v77;
      if ( v77 )
      {
        v77 = 0;
        (*(void (__fastcall **)(const char *, __int64, __int64))(*(_QWORD *)v33 + 16LL))(v33, v5, v7);
      }
      v79 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::`vftable';
      if ( hDevice == (HANDLE)-1LL )
        goto LABEL_21;
      if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::InternalClose(&v79) )
      {
        v54 = GetLastError();
        if ( v54 > 0 )
          v54 = (unsigned __int16)v54 | 0x80070000;
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v54, v55, v56);
        __debugbreak();
      }
      goto LABEL_47;
    }
    if ( !v72[0] && !v76[0] && !DeviceIoControl(hDevice, 0x40001CE8u, &InBuffer, 0x18u, 0, 0, 0, 0) )
    {
      v6 = GetLastError();
      if ( (unsigned int)dword_180069000 > 2 )
      {
        v5 = 2048;
        if ( (qword_180069010 & 0x800) != 0 && (qword_180069018 & 0x800) == qword_180069018 )
        {
          v74 = v6;
          *(_QWORD *)&v81.Data1 = "onecore\\xbox\\gameinput\\xboxgipservices\\SettingsHelper.cpp";
          v73 = 275;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            qword_180069018,
            (unsigned int)&dword_18006379C,
            v7,
            v34,
            (__int64)&v81,
            (__int64)&v73,
            (__int64)&v74);
        }
      }
      if ( v6 )
      {
        if ( v6 > 0 )
          v6 = (unsigned __int16)v6 | 0x80070000;
      }
      else
      {
        v6 = -2147418113;
      }
      v35 = v77;
      if ( v77 )
      {
        v77 = 0;
        (*(void (__fastcall **)(const char *))(*(_QWORD *)v35 + 16LL))(v35);
      }
      v79 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::`vftable';
      if ( hDevice == (HANDLE)-1LL )
        goto LABEL_21;
      if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::InternalClose(&v79) )
      {
        v57 = GetLastError();
        if ( v57 > 0 )
          v57 = (unsigned __int16)v57 | 0x80070000;
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v57, v58, v59);
        __debugbreak();
      }
      goto LABEL_47;
    }
    v36 = v77;
    if ( v77 )
    {
      v77 = 0;
      (*(void (__fastcall **)(const char *))(*(_QWORD *)v36 + 16LL))(v36);
    }
    if ( !DeviceIoControl(hDevice, 0x40001D14u, &OutBuffer, 0x10u, &OutBuffer, 0x10u, 0, 0) )
    {
      v6 = GetLastError();
      if ( (unsigned int)dword_180069000 > 2 )
      {
        v5 = 2048;
        if ( (qword_180069010 & 0x800) != 0 && (qword_180069018 & 0x800) == qword_180069018 )
        {
          v74 = v6;
          *(_QWORD *)&v81.Data1 = "onecore\\xbox\\gameinput\\xboxgipservices\\SettingsHelper.cpp";
          v73 = 287;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            qword_180069018,
            (unsigned int)&unk_1800631B8,
            v7,
            v37,
            (__int64)&v81,
            (__int64)&v73,
            (__int64)&v74);
        }
      }
      if ( v6 )
      {
        if ( v6 > 0 )
          v6 = (unsigned __int16)v6 | 0x80070000;
      }
      else
      {
        v6 = -2147418113;
      }
      v79 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::`vftable';
      if ( hDevice == (HANDLE)-1LL )
        goto LABEL_21;
      if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::InternalClose(&v79) )
      {
        v60 = GetLastError();
        if ( v60 > 0 )
          v60 = (unsigned __int16)v60 | 0x80070000;
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v60, v61, v62);
        __debugbreak();
      }
LABEL_47:
      hDevice = (HANDLE)-1LL;
      goto LABEL_21;
    }
    if ( *(_QWORD *)p_OutBuffer != v83 )
    {
      v38 = hDevice;
      *(_QWORD *)p_OutBuffer = v83;
      if ( !DeviceIoControl(v38, 0x40001D10u, &OutBuffer, 0x10u, 0, 0, 0, 0) )
      {
        v6 = GetLastError();
        if ( (unsigned int)dword_180069000 > 2
          && (qword_180069010 & 0x800) != 0
          && (qword_180069018 & 0x800) == qword_180069018 )
        {
          v74 = v6;
          *(_QWORD *)&v81.Data1 = "onecore\\xbox\\gameinput\\xboxgipservices\\SettingsHelper.cpp";
          v73 = 300;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            qword_180069018,
            (unsigned int)byte_180062DE9,
            v39,
            v40,
            (__int64)&v81,
            (__int64)&v73,
            (__int64)&v74);
        }
        if ( v6 )
        {
          if ( v6 > 0 )
            v6 = (unsigned __int16)v6 | 0x80070000;
        }
        else
        {
          v6 = -2147418113;
        }
        v79 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::`vftable';
        if ( hDevice != (HANDLE)-1LL )
        {
          if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::InternalClose(&v79) )
          {
            v69 = GetLastError();
            if ( v69 > 0 )
              v69 = (unsigned __int16)v69 | 0x80070000;
            Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v69, v70, v71);
            JUMPOUT(0x180047C84LL);
          }
          hDevice = (HANDLE)-1LL;
        }
        v41 = v78;
        if ( v78 )
        {
          v78 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
        }
        v42 = v75;
        if ( v75 )
        {
          v75 = 0;
          (*(void (__fastcall **)(_QWORD *, _QWORD, __int64))(*v42 + 16LL))(v42, *v42, v39);
        }
        return (unsigned int)v6;
      }
    }
    v79 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::`vftable';
    if ( hDevice != (HANDLE)-1LL )
    {
      if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::InternalClose(&v79) )
      {
        v45 = GetLastError();
        if ( v45 > 0 )
          v45 = (unsigned __int16)v45 | 0x80070000;
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v45, v46, v47);
        __debugbreak();
      }
      hDevice = (HANDLE)-1LL;
    }
    v43 = v78;
    if ( v78 )
    {
      v78 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    }
    v44 = v75;
    if ( v75 )
    {
      v75 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v44 + 16LL))(v44);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180047104  mov     [rsp-8+arg_18], rbx
0x180047109  push    rbp
0x18004710a  push    rsi
0x18004710b  push    rdi
0x18004710c  push    r12
0x18004710e  push    r13
0x180047110  push    r14
0x180047112  push    r15
0x180047114  lea     rbp, [rsp-27h]
0x180047119  sub     rsp, 0D0h
0x180047120  mov     rax, cs:__security_cookie
0x180047127  xor     rax, rsp
0x18004712a  mov     [rbp+57h+var_38], rax
0x18004712e  xor     r15d, r15d
0x180047131  mov     r9, r8
0x180047134  mov     r10, rdx
0x180047137  mov     rdi, rcx
0x18004713a  test    r8, r8
0x18004713d  jz      loc_180047B47
0x180047143  mov     rax, [rdx]
0x180047146  lea     r8, [rbp+57h+var_B0]
0x18004714a  mov     rdx, r9
0x18004714d  mov     [rbp+57h+var_B0], r15
0x180047151  mov     rcx, r10
0x180047154  mov     rax, [rax+0A8h]
0x18004715b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047160  mov     ebx, eax
0x180047162  test    eax, eax
0x180047164  jns     loc_1800471F4
0x18004716a  mov     ecx, cs:dword_180069000
0x180047170  cmp     ecx, 2
0x180047173  jbe     short loc_1800471D4
0x180047175  mov     r8, cs:qword_180069018
0x18004717c  mov     edx, 800h
0x180047181  mov     rcx, cs:qword_180069010
0x180047188  test    rdx, rcx
0x18004718b  jz      short loc_1800471D4
0x18004718d  mov     rax, r8
0x180047190  and     rax, rdx
0x180047193  cmp     rax, r8
0x180047196  jnz     short loc_1800471D4
0x180047198  lea     rax, aOnecoreXboxGam_53; "onecore\\xbox\\gameinput\\xboxgipservic"...
0x18004719f  mov     [rbp+57h+var_BC], ebx
0x1800471a2  mov     [rbp+57h+var_A0], rax
0x1800471a6  lea     rdx, dword_18006333C
0x1800471ad  lea     rax, [rbp+57h+var_BC]
0x1800471b1  mov     [rbp+57h+var_B8], 0C8h
0x1800471b8  mov     [rsp+100h+hTemplateFile], rax
0x1800471bd  lea     rax, [rbp+57h+var_B8]
0x1800471c1  mov     qword ptr [rsp+100h+dwFlagsAndAttributes], rax
0x1800471c6  lea     rax, [rbp+57h+var_A0]
0x1800471ca  mov     qword ptr [rsp+100h+dwCreationDisposition], rax
0x1800471cf  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800471d4  mov     rcx, [rbp+57h+var_B0]
0x1800471d8  test    rcx, rcx
0x1800471db  jz      short loc_1800471ED
0x1800471dd  mov     [rbp+57h+var_B0], r15
0x1800471e1  mov     rax, [rcx]
0x1800471e4  mov     rax, [rax+10h]
0x1800471e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800471ed  mov     eax, ebx
0x1800471ef  jmp     loc_180047B49
0x1800471f4  xor     eax, eax
0x1800471f6  mov     [rbp+57h+var_C0], r15b
0x1800471fa  mov     [rbp+57h+var_50], rax
0x1800471fe  lea     rdx, [rbp+57h+var_70]
0x180047202  mov     rax, [rdi]
0x180047205  xorps   xmm0, xmm0
0x180047208  mov     rcx, rdi
0x18004720b  mov     [rbp+57h+var_68], r15
0x18004720f  movups  [rbp+57h+InBuffer], xmm0
0x180047213  mov     [rbp+57h+var_70], r15
0x180047217  mov     rax, [rax+40h]
0x18004721b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047220  mov     ebx, eax
0x180047222  test    eax, eax
0x180047224  jns     short loc_180047282
0x180047226  mov     ecx, cs:dword_180069000
0x18004722c  cmp     ecx, 2
0x18004722f  jbe     short loc_1800471D4
0x180047231  mov     r8, cs:qword_180069018
0x180047238  mov     edx, 800h
0x18004723d  mov     rcx, cs:qword_180069010
0x180047244  test    rdx, rcx
0x180047247  jz      short loc_1800471D4
0x180047249  mov     rax, r8
0x18004724c  and     rax, rdx
0x18004724f  cmp     rax, r8
0x180047252  jnz     short loc_1800471D4
0x180047254  lea     rax, aOnecoreXboxGam_53; "onecore\\xbox\\gameinput\\xboxgipservic"...
0x18004725b  mov     [rbp+57h+var_B8], ebx
0x18004725e  mov     [rbp+57h+var_A0], rax
0x180047262  lea     rdx, word_18006394A
0x180047269  lea     rax, [rbp+57h+var_B8]
0x18004726d  mov     [rbp+57h+var_BC], 0D1h
0x180047274  mov     [rsp+100h+hTemplateFile], rax
0x180047279  lea     rax, [rbp+57h+var_BC]
0x18004727d  jmp     loc_1800471C1
0x180047282  mov     rax, [rbp+57h+var_70]
0x180047286  lea     rdx, [rbp+57h+var_98]
0x18004728a  mov     rcx, [rbp+57h+var_B0]
0x18004728e  mov     qword ptr [rbp+57h+InBuffer], rax
0x180047292  mov     [rbp+57h+var_98], r15
0x180047296  mov     rax, [rcx]
0x180047299  mov     rax, [rax+58h]
0x18004729d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800472a2  mov     ebx, eax
0x1800472a4  test    eax, eax
0x1800472a6  jns     loc_180047338
0x1800472ac  mov     ecx, cs:dword_180069000
0x1800472b2  cmp     ecx, 2
0x1800472b5  jbe     short loc_180047316
0x1800472b7  mov     r8, cs:qword_180069018
0x1800472be  mov     edx, 800h
0x1800472c3  mov     rcx, cs:qword_180069010
0x1800472ca  test    rdx, rcx
0x1800472cd  jz      short loc_180047316
0x1800472cf  mov     rax, r8
0x1800472d2  and     rax, rdx
0x1800472d5  cmp     rax, r8
0x1800472d8  jnz     short loc_180047316
0x1800472da  mov     [rbp+57h+var_BC], 0D6h
0x1800472e1  lea     rdx, byte_1800636E5
0x1800472e8  lea     rax, aOnecoreXboxGam_53; "onecore\\xbox\\gameinput\\xboxgipservic"...
0x1800472ef  mov     [rbp+57h+var_A0], rax
0x1800472f3  lea     rax, [rbp+57h+var_B8]
0x1800472f7  mov     [rsp+100h+hTemplateFile], rax
0x1800472fc  lea     rax, [rbp+57h+var_BC]
0x180047300  mov     qword ptr [rsp+100h+dwFlagsAndAttributes], rax
0x180047305  lea     rax, [rbp+57h+var_A0]
0x180047309  mov     qword ptr [rsp+100h+dwCreationDisposition], rax
0x18004730e  mov     [rbp+57h+var_B8], ebx
0x180047311  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180047316  mov     rcx, [rbp+57h+var_98]
0x18004731a  test    rcx, rcx
0x18004731d  jz      loc_1800471D4
0x180047323  mov     [rbp+57h+var_98], r15
0x180047327  mov     rax, [rcx]
0x18004732a  mov     rax, [rax+10h]
0x18004732e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047333  jmp     loc_1800471D4
0x180047338  mov     rdx, [rbp+57h+var_98]
0x18004733c  lea     rax, [rbp+57h+var_C0]
0x180047340  mov     rcx, [rbp+57h+var_70]
0x180047344  lea     r9, [rbp+57h+InBuffer+8]
0x180047348  mov     qword ptr [rsp+100h+dwFlagsAndAttributes], rax
0x18004734d  lea     r8, [rbp+57h+var_68]
0x180047351  lea     rax, [rbp+57h+var_50]
0x180047355  mov     qword ptr [rsp+100h+dwCreationDisposition], rax
0x18004735a  call    _anonymous_namespace___GetAccessibilitySettings
0x18004735f  mov     rcx, [rdi]
0x180047362  mov     r14b, al
0x180047365  mov     r8b, [rbp+57h+var_C0]
0x180047369  mov     edx, 1
0x18004736e  mov     rax, [rcx+0E0h]
0x180047375  mov     rcx, rdi
0x180047378  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004737d  mov     ebx, eax
0x18004737f  test    eax, eax
0x180047381  jns     short loc_1800473CC
0x180047383  mov     ecx, cs:dword_180069000
0x180047389  cmp     ecx, 2
0x18004738c  jbe     short loc_180047316
0x18004738e  mov     r8, cs:qword_180069018
0x180047395  mov     edx, 800h
0x18004739a  mov     rcx, cs:qword_180069010
0x1800473a1  test    rdx, rcx
0x1800473a4  jz      loc_180047316
0x1800473aa  mov     rax, r8
0x1800473ad  and     rax, rdx
0x1800473b0  cmp     rax, r8
0x1800473b3  jnz     loc_180047316
0x1800473b9  mov     [rbp+57h+var_BC], 0E2h
0x1800473c0  lea     rdx, word_180063856
0x1800473c7  jmp     loc_1800472E8
0x1800473cc  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800473d0  mov     [rsp+100h+hTemplateFile], r15; hTemplateFile
0x1800473d5  test    r14b, r14b
0x1800473d8  mov     [rsp+100h+dwFlagsAndAttributes], 0A0000000h; dwFlagsAndAttributes
0x1800473e0  lea     rax, [rbp+57h+OutBuffer]
0x1800473e4  mov     [rbp+57h+hDevice], r12
0x1800473e8  xorps   xmm0, xmm0
0x1800473eb  lea     rsi, [rbp+57h+OutBuffer+8]
0x1800473ef  cmovnz  rsi, rax
0x1800473f3  lea     r8d, [r12+4]; dwShareMode
0x1800473f8  movups  [rbp+57h+OutBuffer], xmm0
0x1800473fc  lea     rax, [rbp+57h+OutBuffer+8]
0x180047400  mov     [rsp+100h+dwCreationDisposition], r8d; dwCreationDisposition
0x180047405  lea     rcx, [rbp+57h+OutBuffer]
0x180047409  mov     edx, 0C0000000h; dwDesiredAccess
0x18004740e  cmovnz  rcx, rax
0x180047412  lea     r13, ??_7?$HandleT@UFileHandleTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::`vftable'
0x180047419  mov     rax, [rbp+57h+var_70]
0x18004741d  xor     r9d, r9d; lpSecurityAttributes
0x180047420  mov     [rbp+57h+var_90], r13
0x180047424  mov     [rcx], rax
0x180047427  lea     rcx, FileName; "\\\\.\\XboxGIP"
0x18004742e  mov     [rsi], r15
0x180047431  call    cs:__imp_CreateFileW
0x180047438  nop     dword ptr [rax+rax+00h]
0x18004743d  mov     rcx, [rbp+57h+hDevice]
0x180047441  mov     rbx, rax
0x180047444  cmp     rax, rcx
0x180047447  jz      short loc_18004746D
0x180047449  cmp     rcx, r12
0x18004744c  jz      short loc_180047466
0x18004744e  mov     rcx, [rbp+57h+var_90]
0x180047452  mov     rax, [rcx]
0x180047455  lea     rcx, [rbp+57h+var_90]
0x180047459  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004745e  test    al, al
0x180047460  jz      loc_180047C2B
0x180047466  mov     rcx, rbx
0x180047469  mov     [rbp+57h+hDevice], rbx
0x18004746d  cmp     rcx, r12
0x180047470  jnz     loc_18004752D
0x180047476  call    cs:__imp_GetLastError
0x18004747d  nop     dword ptr [rax+rax+00h]
0x180047482  mov     ebx, eax
0x180047484  mov     eax, cs:dword_180069000
0x18004748a  cmp     eax, 2
0x18004748d  jbe     short loc_1800474EE
0x18004748f  mov     rcx, cs:qword_180069018
0x180047496  mov     edx, 800h
0x18004749b  mov     rax, cs:qword_180069010
0x1800474a2  test    rdx, rax
0x1800474a5  jz      short loc_1800474EE
0x1800474a7  mov     rax, rcx
0x1800474aa  and     rax, rdx
0x1800474ad  cmp     rax, rcx
0x1800474b0  jnz     short loc_1800474EE
0x1800474b2  lea     rax, aOnecoreXboxGam_53; "onecore\\xbox\\gameinput\\xboxgipservic"...
0x1800474b9  mov     [rbp+57h+var_B8], ebx
0x1800474bc  mov     [rbp+57h+var_A0], rax
0x1800474c0  lea     rdx, byte_1800634BD
0x1800474c7  lea     rax, [rbp+57h+var_B8]
0x1800474cb  mov     [rbp+57h+var_BC], 0FBh
0x1800474d2  mov     [rsp+100h+hTemplateFile], rax
0x1800474d7  lea     rax, [rbp+57h+var_BC]
0x1800474db  mov     qword ptr [rsp+100h+dwFlagsAndAttributes], rax
0x1800474e0  lea     rax, [rbp+57h+var_A0]
0x1800474e4  mov     qword ptr [rsp+100h+dwCreationDisposition], rax
0x1800474e9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800474ee  mov     edi, 80070000h
0x1800474f3  test    ebx, ebx
0x1800474f5  jnz     short loc_1800474FE
0x1800474f7  mov     ebx, 8000FFFFh
0x1800474fc  jmp     short loc_180047505
0x1800474fe  jle     short loc_180047505
0x180047500  movzx   ebx, bx
0x180047503  or      ebx, edi
0x180047505  mov     [rbp+57h+var_90], r13
0x180047509  cmp     [rbp+57h+hDevice], r12
0x18004750d  jz      loc_180047316
0x180047513  lea     rcx, [rbp+57h+var_90]
0x180047517  call    ?InternalClose@?$HandleT@UFileHandleTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::InternalClose(void)
0x18004751c  test    al, al
0x18004751e  jz      loc_180047C4B
0x180047524  mov     [rbp+57h+hDevice], r12
0x180047528  jmp     loc_180047316
0x18004752d  mov     rax, [rdi]
0x180047530  lea     rdx, [rbp+57h+var_A0]
0x180047534  mov     rcx, rdi
0x180047537  mov     [rbp+57h+var_C0], r15b
0x18004753b  mov     [rbp+57h+var_A8], r15b
0x18004753f  mov     [rbp+57h+var_A0], r15
0x180047543  mov     rax, [rax+78h]
0x180047547  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004754c  mov     ebx, eax
0x18004754e  test    eax, eax
0x180047550  jns     loc_1800475FD
0x180047556  mov     ecx, cs:dword_180069000
0x18004755c  cmp     ecx, 2
0x18004755f  jbe     short loc_1800475C0
0x180047561  mov     r8, cs:qword_180069018
0x180047568  mov     edx, 800h
0x18004756d  mov     rcx, cs:qword_180069010
0x180047574  test    rdx, rcx
0x180047577  jz      short loc_1800475C0
0x180047579  mov     rax, r8
0x18004757c  and     rax, rdx
0x18004757f  cmp     rax, r8
0x180047582  jnz     short loc_1800475C0
0x180047584  lea     rax, aOnecoreXboxGam_53; "onecore\\xbox\\gameinput\\xboxgipservic"...
0x18004758b  mov     [rbp+57h+var_B8], ebx
0x18004758e  mov     qword ptr [rbp+57h+var_80], rax
0x180047592  lea     rdx, unk_180063480
0x180047599  lea     rax, [rbp+57h+var_B8]
0x18004759d  mov     [rbp+57h+var_BC], 102h
0x1800475a4  mov     [rsp+100h+hTemplateFile], rax
0x1800475a9  lea     rax, [rbp+57h+var_BC]
0x1800475ad  mov     qword ptr [rsp+100h+dwFlagsAndAttributes], rax
0x1800475b2  lea     rax, [rbp+57h+var_80]
0x1800475b6  mov     qword ptr [rsp+100h+dwCreationDisposition], rax
0x1800475bb  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800475c0  mov     rcx, [rbp+57h+var_A0]
0x1800475c4  test    rcx, rcx
0x1800475c7  jz      short loc_1800475D9
0x1800475c9  mov     [rbp+57h+var_A0], r15
0x1800475cd  mov     rax, [rcx]
  ... truncated ...
```
