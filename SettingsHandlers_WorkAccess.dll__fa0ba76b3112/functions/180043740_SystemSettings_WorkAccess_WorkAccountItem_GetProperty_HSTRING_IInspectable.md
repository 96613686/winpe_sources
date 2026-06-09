# SystemSettings::WorkAccess::WorkAccountItem::GetProperty(HSTRING__ *,IInspectable * *)

- ea: `0x180043740`
- end: `0x180043e92`
- name: `?GetProperty@WorkAccountItem@WorkAccess@SystemSettings@@UEAAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z`
- size: `1874`
- prototype: `int(SystemSettings::WorkAccess::WorkAccountItem *__hidden this, HSTRING, struct IInspectable **)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180002a60`
- `0x1800076ac`
- `0x1800096ec`
- `0x18000ccc4`
- `0x18000cf0c`
- `0x180011898`
- `0x1800119c0`
- `0x180011a14`
- `0x180015000`
- `0x18001ce98`
- `0x180020584`
- `0x180043740`
- `0x1800476b8`
- `0x18004862c`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180043809`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180043a66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180043809`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180043a66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800437b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043886`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800438d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043a18`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043b1d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043b58`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800437b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043886`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800438d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043a18`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043b1d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043b58`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateRandomAccessStreamOnFile` at `0x180043ac6`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateRandomAccessStreamOnFile` at `0x180043ac6`
- `ext-ms-win-mrmcorer-resmanager-l1-1-0!ResourceManagerQueueGetString` at `0x180043a8c`
- `ext-ms-win-mrmcorer-resmanager-l1-1-0!ResourceManagerQueueGetString` at `0x180043a8c`

## string_xrefs

- `0x18004383a`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountitem.cpp`
- `0x1800438b8`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountitem.cpp`
- `0x180043998`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountitem.cpp`
- `0x1800439ef`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountitem.cpp`
- `0x180043a44`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountitem.cpp`
- `0x180043afa`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountitem.cpp`
- `0x180043d92`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountitem.cpp`
- `0x180043e05`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountitem.cpp`
- `0x180043e56`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountitem.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall SystemSettings::WorkAccess::WorkAccountItem::GetProperty(
        SystemSettings::WorkAccess::WorkAccountItem *this,
        SystemSettings::DataModel *a2,
        struct IInspectable **a3)
{
  const unsigned __int16 *v6; // r8
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, HSTRING *); // rbx
  int v9; // eax
  int Boolean; // ebx
  __int64 v11; // rdx
  int v12; // eax
  int v13; // eax
  __int64 v14; // rdx
  __int64 v16; // rdx
  const unsigned __int16 *v17; // r8
  const unsigned __int16 *v18; // r8
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, HSTRING *)); // rbx
  int v21; // eax
  __int64 (__fastcall ***v22)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v23)(_QWORD, GUID *, HSTRING *); // rdi
  int v24; // eax
  HSTRING v25; // rdi
  __int64 (__fastcall *v26)(HSTRING, HSTRING *); // rbx
  int v27; // eax
  __int64 v28; // rdx
  PCWSTR StringRawBuffer; // rax
  int v30; // eax
  __int64 v31; // rdx
  const unsigned __int16 *v32; // r8
  __int64 v33; // rcx
  const unsigned __int16 *v34; // r8
  const unsigned __int16 *v35; // r8
  const unsigned __int16 *v36; // r8
  const unsigned __int16 *v37; // r8
  const unsigned __int16 *v38; // r8
  int v39; // eax
  int v40; // eax
  __int64 v41; // rdx
  int v42; // [rsp+20h] [rbp-E0h]
  HSTRING string; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING v44; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v45; // [rsp+40h] [rbp-C0h] BYREF
  __int64 (__fastcall ***v46)(_QWORD, GUID *, HSTRING *); // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v47; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v48; // [rsp+58h] [rbp-A8h]
  __int64 v49; // [rsp+60h] [rbp-A0h]
  unsigned __int16 *v50[3]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v51[528]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  *a3 = 0;
  if ( !SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18005B328, (const unsigned __int16 *)a3) )
  {
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18005B348, v6) )
    {
      Boolean = SystemSettings::DataModel::PropValueHelper::CreateString(&sourceString, a3);
      if ( Boolean >= 0 )
        return 0;
      v16 = 84;
      goto LABEL_83;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18005B370, v17) )
    {
      if ( !*((_BYTE *)this + 304) )
        return 0;
      v46 = 0;
      v19 = *((_QWORD *)this + 27);
      v20 = *(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, HSTRING *)))(*(_QWORD *)v19 + 48LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46);
      v21 = v20(v19, &v46);
      Boolean = v21;
      if ( v21 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5B,
          (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountitem.cpp",
          (const char *)(unsigned int)v21,
          v42);
LABEL_42:
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46);
        return (unsigned int)Boolean;
      }
      string = 0;
      v22 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v46;
      v23 = **v46;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&string);
      v24 = v23(v22, &GUID_2b9c347e_56fb_4947_ab47_6982bb2cf28d, &string);
      Boolean = v24;
      if ( v24 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5E,
          (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountitem.cpp",
          (const char *)(unsigned int)v24,
          v42);
LABEL_41:
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&string);
        goto LABEL_42;
      }
      v44 = 0;
      v25 = string;
      v26 = *(__int64 (__fastcall **)(HSTRING, HSTRING *))(*(_QWORD *)string + 48LL);
      WindowsDeleteString(0);
      v44 = 0;
      v27 = v26(v25, &v44);
      Boolean = v27;
      if ( v27 >= 0 )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(v44, 0);
        v42 = 260;
        v27 = ResourceManagerQueueGetString(StringRawBuffer, 0, 0, v51);
        Boolean = v27;
        if ( v27 >= 0 )
        {
          v45 = 0;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
          v30 = CreateRandomAccessStreamOnFile(v51, 0, &GUID_905a0fe1_bc53_11df_8c49_001e4fc686da, &v45);
          Boolean = v30;
          if ( v30 >= 0 )
          {
            v30 = Microsoft::WRL::ComPtr<Windows::Storage::Streams::IRandomAccessStream>::CopyTo<IInspectable>(&v45, a3);
            Boolean = v30;
            if ( v30 >= 0 )
            {
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
              WindowsDeleteString(v44);
              v44 = 0;
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&string);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46);
              return 0;
            }
            v31 = 114;
          }
          else
          {
            v31 = 112;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v31,
            (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountitem.cpp",
            (const char *)(unsigned int)v30,
            260);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
          goto LABEL_40;
        }
        v28 = 106;
      }
      else
      {
        v28 = 97;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v28,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountitem.cpp",
        (const char *)(unsigned int)v27,
        v42);
LABEL_40:
      WindowsDeleteString(v44);
      v44 = 0;
      goto LABEL_41;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18005B3B0, v18) )
    {
      v33 = *((_QWORD *)this + 28);
      if ( !v33 )
        return 0;
      Boolean = Microsoft::WRL::Details::RuntimeClassBaseT<1>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,SystemSettings::DataModel::ISettingItem,SystemSettings::DataModel::ISettingItemTelemetry,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>>(
                  v33,
                  &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
                  a3);
      if ( Boolean >= 0 )
        return 0;
      v16 = 121;
      goto LABEL_83;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18005B3D0, v32) )
    {
      if ( !*((_QWORD *)this + 28) )
        return 0;
      Boolean = Microsoft::WRL::Details::RuntimeClassBaseT<1>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,SystemSettings::DataModel::ISettingItem,SystemSettings::DataModel::ISettingItemTelemetry,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>>(
                  *((_QWORD *)this + 29),
                  &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
                  a3);
      if ( Boolean >= 0 )
        return 0;
      v16 = 128;
      goto LABEL_83;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18005B388, v34) )
    {
      if ( !*((_QWORD *)this + 28) )
        return 0;
      Boolean = Microsoft::WRL::Details::RuntimeClassBaseT<1>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,SystemSettings::DataModel::ISettingItem,SystemSettings::DataModel::ISettingItemTelemetry,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>>(
                  *((_QWORD *)this + 30),
                  &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
                  a3);
      if ( Boolean >= 0 )
        return 0;
      v16 = 135;
      goto LABEL_83;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18005B3E8, v35) )
    {
      Boolean = SystemSettings::DataModel::PropValueHelper::CreateBoolean(*((_BYTE *)this + 304) == 0, a3);
      if ( Boolean >= 0 )
        return 0;
      v16 = 140;
      goto LABEL_83;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18005B408, v36) )
    {
      Boolean = SystemSettings::DataModel::PropValueHelper::CreateBoolean(*((_BYTE *)this + 304), a3);
      if ( Boolean >= 0 )
        return 0;
      v16 = 144;
      goto LABEL_83;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18005B428, v37) )
    {
      Boolean = SystemSettings::DataModel::PropValueHelper::CreateBoolean(*((_BYTE *)this + 305), a3);
      if ( Boolean >= 0 )
        return 0;
      v16 = 148;
      goto LABEL_83;
    }
    if ( !SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18005E038, v38) )
    {
      Boolean = -2147024809;
      v16 = 178;
      goto LABEL_83;
    }
    Boolean = SystemSettings::WorkAccess::CEnrollmentHelper::PopulateIDs();
    if ( Boolean < 0 )
    {
      v16 = 152;
      goto LABEL_83;
    }
    Boolean = SystemSettings::WorkAccess::CEnrollmentHelper::GetOmadmValue(4u);
    if ( Boolean < 0 )
    {
      v16 = 153;
      goto LABEL_83;
    }
    memset(v50, 0, sizeof(v50));
    if ( SystemSettings::WorkAccess::CEnrollmentHelper::_value && *SystemSettings::WorkAccess::CEnrollmentHelper::_value )
    {
      v39 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeResMessage(
              v50,
              &_ImageBase,
              106);
      Boolean = v39;
      if ( v39 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xAB,
          (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountitem.cpp",
          (const char *)(unsigned int)v39,
          v42);
LABEL_81:
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v50);
        return (unsigned int)Boolean;
      }
LABEL_80:
      Boolean = SystemSettings::DataModel::PropValueHelper::CreateString(v50[0], a3);
      goto LABEL_81;
    }
    v47 = 0;
    v48 = 0;
    v49 = 0;
    v40 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeResMessage(
            &v47,
            &_ImageBase,
            109);
    Boolean = v40;
    if ( v40 >= 0 )
    {
      v40 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeResMessage(
              v50,
              &_ImageBase,
              106);
      Boolean = v40;
      if ( v40 >= 0 )
      {
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v47);
        goto LABEL_80;
      }
      v41 = 165;
    }
    else
    {
      v41 = 161;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v41,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountitem.cpp",
      (const char *)(unsigned int)v40,
      v42);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v47);
    goto LABEL_81;
  }
  if ( !*((_BYTE *)this + 304) )
  {
    Boolean = SystemSettings::DataModel::PropValueHelper::CreateString(*((const unsigned __int16 **)this + 35), a3);
    if ( Boolean >= 0 )
      return 0;
    v16 = 78;
LABEL_83:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountitem.cpp",
      (const char *)(unsigned int)Boolean,
      v42);
    return (unsigned int)Boolean;
  }
  string = 0;
  v7 = *((_QWORD *)this + 27);
  v8 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v7 + 56LL);
  WindowsDeleteString(0);
  string = 0;
  v9 = v8(v7, &string);
  Boolean = v9;
  if ( v9 < 0 )
  {
    v11 = 61;
LABEL_17:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountitem.cpp",
      (const char *)(unsigned int)v9,
      v42);
    goto LABEL_18;
  }
  v12 = *((_DWORD *)this + 62);
  if ( v12 != 1 )
  {
    if ( !v12 )
    {
      v9 = SystemSettings::DataModel::PropValueHelper::CreateString(string, a3);
      Boolean = v9;
      if ( v9 < 0 )
      {
        v11 = 72;
        goto LABEL_17;
      }
    }
LABEL_12:
    WindowsDeleteString(string);
    return 0;
  }
  v47 = 0;
  v48 = 0;
  v49 = 0;
  WindowsGetStringRawBuffer(string, 0);
  v13 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeResMessage(
          &v47,
          &_ImageBase,
          105);
  Boolean = v13;
  if ( v13 >= 0 )
  {
    v13 = SystemSettings::DataModel::PropValueHelper::CreateString(v47, a3);
    Boolean = v13;
    if ( v13 < 0 )
    {
      v14 = 68;
      goto LABEL_8;
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v47);
    goto LABEL_12;
  }
  v14 = 67;
LABEL_8:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v14,
    (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountitem.cpp",
    (const char *)(unsigned int)v13,
    v42);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v47);
LABEL_18:
  WindowsDeleteString(string);
  return (unsigned int)Boolean;
}

```

## disassembly

```asm
0x180043740  mov     [rsp-8+arg_18], rbx
0x180043745  push    rbp
0x180043746  push    rsi
0x180043747  push    rdi
0x180043748  push    r14
0x18004374a  push    r15
0x18004374c  lea     rbp, [rsp-1A0h]
0x180043754  sub     rsp, 2A0h
0x18004375b  mov     rax, cs:__security_cookie
0x180043762  xor     rax, rsp
0x180043765  mov     [rbp+1C0h+var_30], rax
0x18004376c  mov     r14, r8
0x18004376f  mov     rbx, rdx
0x180043772  mov     rsi, rcx
0x180043775  xor     r15d, r15d
0x180043778  mov     [r8], r15
0x18004377b  lea     rdx, stru_18005B328; HSTRING
0x180043782  mov     rcx, rbx; this
0x180043785  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18004378a  test    al, al
0x18004378c  jz      loc_180043901
0x180043792  cmp     [rsi+130h], r15b
0x180043799  jz      loc_1800438E2
0x18004379f  mov     [rsp+2C0h+string], r15
0x1800437a4  mov     rdi, [rsi+0D8h]
0x1800437ab  mov     rax, [rdi]
0x1800437ae  mov     rbx, [rax+38h]
0x1800437b2  xor     ecx, ecx; string
0x1800437b4  call    cs:__imp_WindowsDeleteString
0x1800437bb  nop     dword ptr [rax+rax+00h]
0x1800437c0  mov     [rsp+2C0h+string], r15
0x1800437c5  lea     rdx, [rsp+2C0h+string]
0x1800437ca  mov     rcx, rdi
0x1800437cd  mov     rax, rbx
0x1800437d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800437d5  mov     ebx, eax
0x1800437d7  test    eax, eax
0x1800437d9  jns     short loc_1800437E4
0x1800437db  lea     edx, [r15+3Dh]
0x1800437df  jmp     loc_1800438B5
0x1800437e4  mov     eax, [rsi+0F8h]
0x1800437ea  cmp     eax, 1
0x1800437ed  jnz     loc_180043899
0x1800437f3  mov     [rsp+2C0h+var_270], r15
0x1800437f8  mov     [rsp+2C0h+var_268], r15
0x1800437fd  mov     [rsp+2C0h+var_260], r15
0x180043802  xor     edx, edx; length
0x180043804  mov     rcx, [rsp+2C0h+string]; string
0x180043809  call    cs:__imp_WindowsGetStringRawBuffer
0x180043810  nop     dword ptr [rax+rax+00h]
0x180043815  mov     r9, rax
0x180043818  mov     r8d, 69h ; 'i'
0x18004381e  lea     rdx, __ImageBase
0x180043825  lea     rcx, [rsp+2C0h+var_270]
0x18004382a  call    ?InitializeResMessage@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@HZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeResMessage(HINSTANCE__ *,int,...)
0x18004382f  mov     ebx, eax
0x180043831  test    eax, eax
0x180043833  jns     short loc_18004385C
0x180043835  mov     edx, 43h ; 'C'; void *
0x18004383a  lea     r8, aShellcommonShe_6; "shellcommon\\shell\\settingshandlers\\w"...
0x180043841  mov     r9d, eax; char *
0x180043844  mov     rcx, [rbp+1C8h]; this
0x18004384b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043850  lea     rcx, [rsp+2C0h+var_270]
0x180043855  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18004385a  jmp     short loc_1800438CC
0x18004385c  mov     rdx, r14; struct IInspectable **
0x18004385f  mov     rcx, [rsp+2C0h+var_270]; unsigned __int16 *
0x180043864  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x180043869  mov     ebx, eax
0x18004386b  test    eax, eax
0x18004386d  jns     short loc_180043876
0x18004386f  mov     edx, 44h ; 'D'
0x180043874  jmp     short loc_18004383A
0x180043876  lea     rcx, [rsp+2C0h+var_270]
0x18004387b  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180043880  nop
0x180043881  mov     rcx, [rsp+2C0h+string]; string
0x180043886  call    cs:__imp_WindowsDeleteString
0x18004388d  nop     dword ptr [rax+rax+00h]
0x180043892  xor     eax, eax
0x180043894  jmp     loc_180043E6B
0x180043899  test    eax, eax
0x18004389b  jnz     short loc_180043881
0x18004389d  mov     rdx, r14; struct IInspectable **
0x1800438a0  mov     rcx, [rsp+2C0h+string]; HSTRING
0x1800438a5  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(HSTRING__ *,IInspectable * *)
0x1800438aa  mov     ebx, eax
0x1800438ac  test    eax, eax
0x1800438ae  jns     short loc_180043881
0x1800438b0  mov     edx, 48h ; 'H'; void *
0x1800438b5  mov     r9d, eax; char *
0x1800438b8  lea     r8, aShellcommonShe_6; "shellcommon\\shell\\settingshandlers\\w"...
0x1800438bf  mov     rcx, [rbp+1C8h]; this
0x1800438c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800438cb  nop
0x1800438cc  mov     rcx, [rsp+2C0h+string]; string
0x1800438d1  call    cs:__imp_WindowsDeleteString
0x1800438d8  nop     dword ptr [rax+rax+00h]
0x1800438dd  jmp     loc_180043E69
0x1800438e2  mov     rdx, r14; struct IInspectable **
0x1800438e5  mov     rcx, [rsi+118h]; unsigned __int16 *
0x1800438ec  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x1800438f1  mov     ebx, eax
0x1800438f3  test    eax, eax
0x1800438f5  jns     short loc_180043892
0x1800438f7  mov     edx, 4Eh ; 'N'
0x1800438fc  jmp     loc_180043E53
0x180043901  lea     rdx, stru_18005B348; HSTRING
0x180043908  mov     rcx, rbx; this
0x18004390b  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180043910  test    al, al
0x180043912  jz      short loc_180043937
0x180043914  mov     rdx, r14; struct IInspectable **
0x180043917  lea     rcx, sourceString; unsigned __int16 *
0x18004391e  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x180043923  mov     ebx, eax
0x180043925  test    eax, eax
0x180043927  jns     loc_180043892
0x18004392d  mov     edx, 54h ; 'T'
0x180043932  jmp     loc_180043E53
0x180043937  lea     rdx, stru_18005B370; HSTRING
0x18004393e  mov     rcx, rbx; this
0x180043941  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180043946  test    al, al
0x180043948  jz      loc_180043B83
0x18004394e  cmp     [rsi+130h], r15b
0x180043955  jz      loc_180043892
0x18004395b  mov     [rsp+2C0h+var_278], r15
0x180043960  mov     rdi, [rsi+0D8h]
0x180043967  mov     rax, [rdi]
0x18004396a  mov     rbx, [rax+30h]
0x18004396e  lea     rcx, [rsp+2C0h+var_278]
0x180043973  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180043978  lea     rdx, [rsp+2C0h+var_278]
0x18004397d  mov     rcx, rdi
0x180043980  mov     rax, rbx
0x180043983  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043988  mov     ebx, eax
0x18004398a  test    eax, eax
0x18004398c  jns     short loc_1800439AE
0x18004398e  mov     rcx, [rbp+1C8h]; this
0x180043995  mov     r9d, eax; char *
0x180043998  lea     r8, aShellcommonShe_6; "shellcommon\\shell\\settingshandlers\\w"...
0x18004399f  mov     edx, 5Bh ; '['; void *
0x1800439a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800439a9  jmp     loc_180043B39
0x1800439ae  mov     [rsp+2C0h+string], r15
0x1800439b3  mov     rbx, [rsp+2C0h+var_278]
0x1800439b8  mov     rax, [rbx]
0x1800439bb  mov     rdi, [rax]
0x1800439be  lea     rcx, [rsp+2C0h+string]
0x1800439c3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800439c8  lea     r8, [rsp+2C0h+string]
0x1800439cd  lea     rdx, _GUID_2b9c347e_56fb_4947_ab47_6982bb2cf28d
0x1800439d4  mov     rcx, rbx
0x1800439d7  mov     rax, rdi
0x1800439da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800439df  mov     ebx, eax
0x1800439e1  test    eax, eax
0x1800439e3  jns     short loc_180043A05
0x1800439e5  mov     rcx, [rbp+1C8h]; this
0x1800439ec  mov     r9d, eax; char *
0x1800439ef  lea     r8, aShellcommonShe_6; "shellcommon\\shell\\settingshandlers\\w"...
0x1800439f6  mov     edx, 5Eh ; '^'; void *
0x1800439fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043a00  jmp     loc_180043B2E
0x180043a05  mov     [rsp+2C0h+var_288], r15
0x180043a0a  mov     rdi, [rsp+2C0h+string]
0x180043a0f  mov     rax, [rdi]
0x180043a12  mov     rbx, [rax+30h]
0x180043a16  xor     ecx, ecx; string
0x180043a18  call    cs:__imp_WindowsDeleteString
0x180043a1f  nop     dword ptr [rax+rax+00h]
0x180043a24  mov     [rsp+2C0h+var_288], r15
0x180043a29  lea     rdx, [rsp+2C0h+var_288]
0x180043a2e  mov     rcx, rdi
0x180043a31  mov     rax, rbx
0x180043a34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043a39  mov     ebx, eax
0x180043a3b  test    eax, eax
0x180043a3d  jns     short loc_180043A5F
0x180043a3f  mov     edx, 61h ; 'a'; void *
0x180043a44  lea     r8, aShellcommonShe_6; "shellcommon\\shell\\settingshandlers\\w"...
0x180043a4b  mov     r9d, eax; char *
0x180043a4e  mov     rcx, [rbp+1C8h]; this
0x180043a55  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043a5a  jmp     loc_180043B18
0x180043a5f  xor     edx, edx; length
0x180043a61  mov     rcx, [rsp+2C0h+var_288]; string
0x180043a66  call    cs:__imp_WindowsGetStringRawBuffer
0x180043a6d  nop     dword ptr [rax+rax+00h]
0x180043a72  mov     [rsp+2C0h+var_298], r15
0x180043a77  mov     qword ptr [rsp+2C0h+var_2A0], 104h; int
0x180043a80  lea     r9, [rbp+1C0h+var_240]
0x180043a84  xor     r8d, r8d
0x180043a87  xor     edx, edx
0x180043a89  mov     rcx, rax
0x180043a8c  call    cs:__imp_ResourceManagerQueueGetString
0x180043a93  nop     dword ptr [rax+rax+00h]
0x180043a98  mov     ebx, eax
0x180043a9a  test    eax, eax
0x180043a9c  jns     short loc_180043AA5
0x180043a9e  mov     edx, 6Ah ; 'j'
0x180043aa3  jmp     short loc_180043A44
0x180043aa5  mov     [rsp+2C0h+var_280], r15
0x180043aaa  lea     rcx, [rsp+2C0h+var_280]
0x180043aaf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180043ab4  lea     r9, [rsp+2C0h+var_280]
0x180043ab9  lea     r8, _GUID_905a0fe1_bc53_11df_8c49_001e4fc686da
0x180043ac0  xor     edx, edx
0x180043ac2  lea     rcx, [rbp+1C0h+var_240]
0x180043ac6  call    cs:__imp_CreateRandomAccessStreamOnFile
0x180043acd  nop     dword ptr [rax+rax+00h]
0x180043ad2  mov     ebx, eax
0x180043ad4  test    eax, eax
0x180043ad6  jns     short loc_180043ADF
0x180043ad8  mov     edx, 70h ; 'p'
0x180043add  jmp     short loc_180043AF7
0x180043adf  mov     rdx, r14
0x180043ae2  lea     rcx, [rsp+2C0h+var_280]
0x180043ae7  call    ??$CopyTo@UIInspectable@@@?$ComPtr@UIRandomAccessStream@Streams@Storage@Windows@@@WRL@Microsoft@@QEBAJPEAPEAUIInspectable@@@Z; Microsoft::WRL::ComPtr<Windows::Storage::Streams::IRandomAccessStream>::CopyTo<IInspectable>(IInspectable * *)
0x180043aec  mov     ebx, eax
0x180043aee  test    eax, eax
0x180043af0  jns     short loc_180043B48
0x180043af2  mov     edx, 72h ; 'r'; void *
0x180043af7  mov     r9d, eax; char *
0x180043afa  lea     r8, aShellcommonShe_6; "shellcommon\\shell\\settingshandlers\\w"...
0x180043b01  mov     rcx, [rbp+1C8h]; this
0x180043b08  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043b0d  lea     rcx, [rsp+2C0h+var_280]
0x180043b12  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180043b17  nop
0x180043b18  mov     rcx, [rsp+2C0h+var_288]; string
0x180043b1d  call    cs:__imp_WindowsDeleteString
0x180043b24  nop     dword ptr [rax+rax+00h]
0x180043b29  mov     [rsp+2C0h+var_288], r15
0x180043b2e  lea     rcx, [rsp+2C0h+string]
0x180043b33  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180043b38  nop
0x180043b39  lea     rcx, [rsp+2C0h+var_278]
0x180043b3e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180043b43  jmp     loc_180043E69
0x180043b48  lea     rcx, [rsp+2C0h+var_280]
0x180043b4d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180043b52  nop
0x180043b53  mov     rcx, [rsp+2C0h+var_288]; string
0x180043b58  call    cs:__imp_WindowsDeleteString
0x180043b5f  nop     dword ptr [rax+rax+00h]
0x180043b64  mov     [rsp+2C0h+var_288], r15
0x180043b69  lea     rcx, [rsp+2C0h+string]
0x180043b6e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180043b73  nop
0x180043b74  lea     rcx, [rsp+2C0h+var_278]
0x180043b79  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180043b7e  jmp     loc_180043892
0x180043b83  lea     rdx, stru_18005B3B0; HSTRING
0x180043b8a  mov     rcx, rbx; this
0x180043b8d  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180043b92  test    al, al
0x180043b94  jz      short loc_180043BC9
0x180043b96  mov     rcx, [rsi+0E0h]
0x180043b9d  test    rcx, rcx
0x180043ba0  jz      loc_180043892
0x180043ba6  mov     r8, r14
0x180043ba9  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x180043bb0  call    ??$AsIID@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UISettingItem@DataModel@SystemSettings@@UISettingItemTelemetry@56@UISettingsAppNotification@56@UISettingItem2@56@VFtmBase@23@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$00@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UISettingItem@DataModel@SystemSettings@@UISettingItemTelemetry@56@UISettingsAppNotification@56@UISettingItem2@56@VFtmBase@23@@123@AEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassBaseT<1>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,SystemSettings::DataModel::ISettingItem,SystemSettings::DataModel::ISettingItemTelemetry,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,SystemSettings::DataModel::ISettingItem,SystemSettings::DataModel::ISettingItemTelemetry,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase> *,_GUID const &,void * *)
0x180043bb5  mov     ebx, eax
0x180043bb7  test    eax, eax
0x180043bb9  jns     loc_180043892
0x180043bbf  mov     edx, 79h ; 'y'
0x180043bc4  jmp     loc_180043E53
0x180043bc9  lea     rdx, stru_18005B3D0; HSTRING
0x180043bd0  mov     rcx, rbx; this
0x180043bd3  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180043bd8  test    al, al
0x180043bda  jz      short loc_180043C13
0x180043bdc  cmp     [rsi+0E0h], r15
0x180043be3  jz      loc_180043892
0x180043be9  mov     r8, r14
0x180043bec  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x180043bf3  mov     rcx, [rsi+0E8h]
0x180043bfa  call    ??$AsIID@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UISettingItem@DataModel@SystemSettings@@UISettingItemTelemetry@56@UISettingsAppNotification@56@UISettingItem2@56@VFtmBase@23@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$00@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UISettingItem@DataModel@SystemSettings@@UISettingItemTelemetry@56@UISettingsAppNotification@56@UISettingItem2@56@VFtmBase@23@@123@AEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassBaseT<1>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,SystemSettings::DataModel::ISettingItem,SystemSettings::DataModel::ISettingItemTelemetry,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,SystemSettings::DataModel::ISettingItem,SystemSettings::DataModel::ISettingItemTelemetry,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase> *,_GUID const &,void * *)
0x180043bff  mov     ebx, eax
0x180043c01  test    eax, eax
0x180043c03  jns     loc_180043892
0x180043c09  mov     edx, 80h
0x180043c0e  jmp     loc_180043E53
0x180043c13  lea     rdx, stru_18005B388; HSTRING
0x180043c1a  mov     rcx, rbx; this
0x180043c1d  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180043c22  test    al, al
0x180043c24  jz      short loc_180043C5D
0x180043c26  cmp     [rsi+0E0h], r15
0x180043c2d  jz      loc_180043892
0x180043c33  mov     r8, r14
0x180043c36  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x180043c3d  mov     rcx, [rsi+0F0h]
0x180043c44  call    ??$AsIID@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UISettingItem@DataModel@SystemSettings@@UISettingItemTelemetry@56@UISettingsAppNotification@56@UISettingItem2@56@VFtmBase@23@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$00@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UISettingItem@DataModel@SystemSettings@@UISettingItemTelemetry@56@UISettingsAppNotification@56@UISettingItem2@56@VFtmBase@23@@123@AEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassBaseT<1>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,SystemSettings::DataModel::ISettingItem,SystemSettings::DataModel::ISettingItemTelemetry,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,SystemSettings::DataModel::ISettingItem,SystemSettings::DataModel::ISettingItemTelemetry,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase> *,_GUID const &,void * *)
0x180043c49  mov     ebx, eax
  ... truncated ...
```
