# SystemSettings::WorkAccess::ResourceAccountListItem::GetProperty(HSTRING__ *,IInspectable * *)

- ea: `0x180012ce0`
- end: `0x180013287`
- name: `?GetProperty@ResourceAccountListItem@WorkAccess@SystemSettings@@UEAAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z`
- size: `1447`
- prototype: `int(SystemSettings::WorkAccess::ResourceAccountListItem *__hidden this, HSTRING, struct IInspectable **)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800076ac`
- `0x1800096ec`
- `0x18000ccc4`
- `0x18000cf0c`
- `0x18000e010`
- `0x18000e214`
- `0x18000e2f4`
- `0x18000eb2c`
- `0x18000ec74`
- `0x180011898`
- `0x1800119c0`
- `0x180011a14`
- `0x180012ce0`
- `0x180014d20`
- `0x180015000`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012d2f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012d89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012d9e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012d2f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012d89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012d9e`

## string_xrefs

- `0x180012d74`: `shellcommon\shell\settingshandlers\workaccess\lib\resourceaccount.cpp`
- `0x180012e73`: `shellcommon\shell\settingshandlers\workaccess\lib\resourceaccount.cpp`
- `0x180012ec6`: `shellcommon\shell\settingshandlers\workaccess\lib\resourceaccount.cpp`
- `0x180012f1b`: `shellcommon\shell\settingshandlers\workaccess\lib\resourceaccount.cpp`
- `0x180012f82`: `shellcommon\shell\settingshandlers\workaccess\lib\resourceaccount.cpp`
- `0x180013061`: `shellcommon\shell\settingshandlers\workaccess\lib\resourceaccount.cpp`
- `0x180013104`: `shellcommon\shell\settingshandlers\workaccess\lib\resourceaccount.cpp`
- `0x18001319e`: `shellcommon\shell\settingshandlers\workaccess\lib\resourceaccount.cpp`
- `0x180013261`: `shellcommon\shell\settingshandlers\workaccess\lib\resourceaccount.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall SystemSettings::WorkAccess::ResourceAccountListItem::GetProperty(
        SystemSettings::WorkAccess::ResourceAccountListItem *this,
        SystemSettings::DataModel *a2,
        struct IInspectable **a3)
{
  const unsigned __int16 *v6; // r8
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, HSTRING *); // rbx
  int v9; // eax
  int Boolean; // ebx
  __int64 v11; // rdx
  const unsigned __int16 *v13; // r8
  __int64 v14; // rdx
  const unsigned __int16 *v15; // r8
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, __int64, __int64 *); // rbx
  int v18; // eax
  unsigned __int64 v19; // r9
  __int64 v20; // rdx
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(_QWORD, HSTRING *); // rbx
  int v23; // eax
  HSTRING v24; // rdi
  __int64 (__fastcall ***v25)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v26)(_QWORD, GUID *, __int64 *); // rbx
  int v27; // eax
  __int64 v28; // rdx
  const unsigned __int16 *v29; // r8
  int v30; // eax
  __int64 v31; // rdx
  const unsigned __int16 *v32; // r8
  const unsigned __int16 *v33; // r8
  int v34; // eax
  __int64 v35; // rdx
  const unsigned __int16 *v36; // r8
  const unsigned __int16 *v37; // r8
  __int64 v38; // [rsp+20h] [rbp-20h] BYREF
  __int64 v39; // [rsp+28h] [rbp-18h] BYREF
  _QWORD v40[2]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  HSTRING string; // [rsp+70h] [rbp+30h] BYREF
  __int64 (__fastcall ***v43)(_QWORD, GUID *, __int64 *); // [rsp+78h] [rbp+38h] BYREF

  *a3 = 0;
  if ( !SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18005B328, (const unsigned __int16 *)a3) )
  {
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18005B348, v6) )
    {
      Boolean = SystemSettings::DataModel::PropValueHelper::CreateString(&sourceString, a3);
      if ( Boolean >= 0 )
        return 0;
      v14 = 132;
LABEL_67:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\resourceaccount.cpp",
        (const char *)(unsigned int)Boolean,
        v38);
      return (unsigned int)Boolean;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18005B370, v13) )
    {
      v39 = 0;
      v16 = *((_QWORD *)this + 27);
      v17 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v16 + 128LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
      v18 = v17(v16, 1, &v39);
      Boolean = v18;
      if ( v18 < 0 )
      {
        v19 = (unsigned int)v18;
        v20 = 137;
LABEL_19:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v20,
          (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\resourceaccount.cpp",
          (const char *)v19,
          v38);
LABEL_34:
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
        return (unsigned int)Boolean;
      }
      v40[0] = 0;
      v21 = v39;
      Boolean = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStreamReference *> *>(v39);
      if ( Boolean >= 0 )
        Boolean = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v21 + 64LL))(v21, v40);
      if ( Boolean < 0 )
      {
        v19 = (unsigned int)Boolean;
        v20 = 140;
        goto LABEL_19;
      }
      if ( v40[0] )
      {
        string = 0;
        v22 = *(__int64 (__fastcall **)(_QWORD, HSTRING *))(*(_QWORD *)v40[0] + 48LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&string);
        v23 = v22(v40[0], &string);
        Boolean = v23;
        if ( v23 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x91,
            (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\resourceaccount.cpp",
            (const char *)(unsigned int)v23,
            v38);
LABEL_33:
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&string);
          goto LABEL_34;
        }
        v43 = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
        v24 = string;
        Boolean = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStreamWithContentType *> *>(string);
        if ( Boolean >= 0 )
          Boolean = (*(__int64 (__fastcall **)(HSTRING, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v24 + 64LL))(
                      v24,
                      &v43);
        if ( Boolean < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x94,
            (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\resourceaccount.cpp",
            (const char *)(unsigned int)Boolean,
            v38);
LABEL_32:
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
          goto LABEL_33;
        }
        v38 = 0;
        v25 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v43;
        v26 = **v43;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
        v27 = v26(v25, &GUID_905a0fe1_bc53_11df_8c49_001e4fc686da, &v38);
        Boolean = v27;
        if ( v27 < 0 )
        {
          v28 = 151;
LABEL_31:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v28,
            (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\resourceaccount.cpp",
            (const char *)(unsigned int)v27,
            v38);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
          goto LABEL_32;
        }
        v27 = Microsoft::WRL::ComPtr<Windows::Storage::Streams::IRandomAccessStream>::CopyTo<IInspectable>(&v38, a3);
        Boolean = v27;
        if ( v27 < 0 )
        {
          v28 = 152;
          goto LABEL_31;
        }
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&string);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
      return 0;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18005B388, v15) )
    {
      v43 = 0;
      v40[0] = 0;
      LODWORD(string) = 4;
      v39 = 0;
      Microsoft::WRL::ComPtr<SystemSettings::WorkAccess::DisconnectWorkAccount>::InternalRelease(&v43);
      v30 = Microsoft::WRL::Details::MakeAndInitialize<SystemSettings::WorkAccess::DisconnectWorkAccount,SystemSettings::WorkAccess::DisconnectWorkAccount,Windows::Security::Credentials::IWebAccount * &,enum SystemSettings::WorkAccess::WorkAccountType &,Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics * &>(
              &v43,
              &v39,
              &string,
              v40);
      Boolean = v30;
      if ( v30 < 0 )
      {
        v31 = 161;
LABEL_42:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v31,
          (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\resourceaccount.cpp",
          (const char *)(unsigned int)v30,
          v38);
        Microsoft::WRL::ComPtr<SystemSettings::WorkAccess::DisconnectWorkAccount>::InternalRelease(&v43);
        return (unsigned int)Boolean;
      }
      v30 = Microsoft::WRL::Details::RuntimeClassBaseT<1>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,SystemSettings::DataModel::ISettingItem,SystemSettings::DataModel::ISettingItemTelemetry,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>>(
              v43,
              &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
              a3);
      Boolean = v30;
      if ( v30 < 0 )
      {
        v31 = 162;
        goto LABEL_42;
      }
    }
    else
    {
      if ( !SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18005B3B0, v29) )
      {
        if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18005B3D0, v32) )
        {
          v43 = 0;
          LODWORD(string) = 4;
          v40[0] = 0;
          Microsoft::WRL::ComPtr<SystemSettings::WorkAccess::DisconnectWorkAccount>::InternalRelease(&v43);
          v34 = Microsoft::WRL::Details::MakeAndInitialize<SystemSettings::WorkAccess::InfoWorkAccount,SystemSettings::WorkAccess::InfoWorkAccount,std::nullptr_t,enum SystemSettings::WorkAccess::WorkAccountType>(
                  &v43,
                  v40,
                  &string);
          Boolean = v34;
          if ( v34 >= 0 )
          {
            v34 = Microsoft::WRL::Details::RuntimeClassBaseT<1>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,SystemSettings::DataModel::ISettingItem,SystemSettings::DataModel::ISettingItemTelemetry,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>>(
                    v43,
                    &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
                    a3);
            Boolean = v34;
            if ( v34 >= 0 )
            {
              Microsoft::WRL::ComPtr<SystemSettings::WorkAccess::DisconnectWorkAccount>::InternalRelease(&v43);
              return 0;
            }
            v35 = 174;
          }
          else
          {
            v35 = 173;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v35,
            (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\resourceaccount.cpp",
            (const char *)(unsigned int)v34,
            v38);
          Microsoft::WRL::ComPtr<SystemSettings::WorkAccess::DisconnectWorkAccount>::InternalRelease(&v43);
          return (unsigned int)Boolean;
        }
        if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18005B3E8, v33) )
        {
          Boolean = SystemSettings::DataModel::PropValueHelper::CreateBoolean(0, a3);
          if ( Boolean >= 0 )
            return 0;
          v14 = 178;
        }
        else if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18005B408, v36) )
        {
          Boolean = SystemSettings::DataModel::PropValueHelper::CreateBoolean(1u, a3);
          if ( Boolean >= 0 )
            return 0;
          v14 = 182;
        }
        else if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18005B428, v37) )
        {
          Boolean = SystemSettings::DataModel::PropValueHelper::CreateBoolean(0, a3);
          if ( Boolean >= 0 )
            return 0;
          v14 = 186;
        }
        else
        {
          Boolean = -2147024809;
          v14 = 190;
        }
        goto LABEL_67;
      }
      v43 = 0;
      v40[0] = 0;
      LODWORD(string) = 4;
      v39 = 0;
      Microsoft::WRL::ComPtr<SystemSettings::WorkAccess::DisconnectWorkAccount>::InternalRelease(&v43);
      v30 = Microsoft::WRL::Details::MakeAndInitialize<SystemSettings::WorkAccess::ManageWorkAccount,SystemSettings::WorkAccess::ManageWorkAccount,Windows::Security::Credentials::IWebAccount * &,enum SystemSettings::WorkAccess::WorkAccountType &,Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics * &>(
              &v43,
              &v39,
              &string,
              v40);
      Boolean = v30;
      if ( v30 < 0 )
      {
        v31 = 167;
        goto LABEL_42;
      }
      v30 = Microsoft::WRL::Details::RuntimeClassBaseT<1>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,SystemSettings::DataModel::ISettingItem,SystemSettings::DataModel::ISettingItemTelemetry,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>>(
              v43,
              &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
              a3);
      Boolean = v30;
      if ( v30 < 0 )
      {
        v31 = 168;
        goto LABEL_42;
      }
    }
    Microsoft::WRL::ComPtr<SystemSettings::WorkAccess::DisconnectWorkAccount>::InternalRelease(&v43);
    return 0;
  }
  string = 0;
  v7 = *((_QWORD *)this + 27);
  v8 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v7 + 64LL);
  WindowsDeleteString(0);
  string = 0;
  v9 = v8(v7, &string);
  Boolean = v9;
  if ( v9 >= 0 )
  {
    v9 = SystemSettings::DataModel::PropValueHelper::CreateString(string, a3);
    Boolean = v9;
    if ( v9 < 0 )
    {
      v11 = 127;
      goto LABEL_6;
    }
    WindowsDeleteString(string);
    return 0;
  }
  v11 = 126;
LABEL_6:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v11,
    (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\resourceaccount.cpp",
    (const char *)(unsigned int)v9,
    v38);
  WindowsDeleteString(string);
  return (unsigned int)Boolean;
}

```

## disassembly

```asm
0x180012ce0  mov     [rsp-18h+arg_0], rbx
0x180012ce5  mov     [rsp-18h+arg_8], rsi
0x180012cea  push    rbp
0x180012ceb  push    rdi
0x180012cec  push    r14
0x180012cee  mov     rbp, rsp
0x180012cf1  sub     rsp, 40h
0x180012cf5  mov     rsi, r8
0x180012cf8  mov     rbx, rdx
0x180012cfb  mov     rdi, rcx
0x180012cfe  xor     r14d, r14d
0x180012d01  mov     [r8], r14
0x180012d04  lea     rdx, stru_18005B328; HSTRING
0x180012d0b  mov     rcx, rbx; this
0x180012d0e  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180012d13  test    al, al
0x180012d15  jz      loc_180012DB1
0x180012d1b  mov     [rbp+string], r14
0x180012d1f  mov     rdi, [rdi+0D8h]
0x180012d26  mov     rax, [rdi]
0x180012d29  mov     rbx, [rax+40h]
0x180012d2d  xor     ecx, ecx; string
0x180012d2f  call    cs:__imp_WindowsDeleteString
0x180012d36  nop     dword ptr [rax+rax+00h]
0x180012d3b  mov     [rbp+string], r14
0x180012d3f  lea     rdx, [rbp+string]
0x180012d43  mov     rcx, rdi
0x180012d46  mov     rax, rbx
0x180012d49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d4e  mov     ebx, eax
0x180012d50  test    eax, eax
0x180012d52  jns     short loc_180012D5A
0x180012d54  lea     edx, [r14+7Eh]
0x180012d58  jmp     short loc_180012D71
0x180012d5a  mov     rdx, rsi; struct IInspectable **
0x180012d5d  mov     rcx, [rbp+string]; HSTRING
0x180012d61  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(HSTRING__ *,IInspectable * *)
0x180012d66  mov     ebx, eax
0x180012d68  test    eax, eax
0x180012d6a  jns     short loc_180012D9A
0x180012d6c  mov     edx, 7Fh; void *
0x180012d71  mov     r9d, eax; char *
0x180012d74  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\settingshandlers\\w"...
0x180012d7b  mov     rcx, [rbp+18h]; this
0x180012d7f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012d84  nop
0x180012d85  mov     rcx, [rbp+string]; string
0x180012d89  call    cs:__imp_WindowsDeleteString
0x180012d90  nop     dword ptr [rax+rax+00h]
0x180012d95  jmp     loc_180013271
0x180012d9a  mov     rcx, [rbp+string]; string
0x180012d9e  call    cs:__imp_WindowsDeleteString
0x180012da5  nop     dword ptr [rax+rax+00h]
0x180012daa  xor     eax, eax
0x180012dac  jmp     loc_180013273
0x180012db1  lea     rdx, stru_18005B348; HSTRING
0x180012db8  mov     rcx, rbx; this
0x180012dbb  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180012dc0  test    al, al
0x180012dc2  jz      short loc_180012DE3
0x180012dc4  mov     rdx, rsi; struct IInspectable **
0x180012dc7  lea     rcx, sourceString; unsigned __int16 *
0x180012dce  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x180012dd3  mov     ebx, eax
0x180012dd5  test    eax, eax
0x180012dd7  jns     short loc_180012DAA
0x180012dd9  mov     edx, 84h
0x180012dde  jmp     loc_18001325E
0x180012de3  lea     rdx, stru_18005B370; HSTRING
0x180012dea  mov     rcx, rbx; this
0x180012ded  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180012df2  test    al, al
0x180012df4  jz      loc_180012FEB
0x180012dfa  mov     [rbp+var_18], r14
0x180012dfe  mov     rdi, [rdi+0D8h]
0x180012e05  mov     rax, [rdi]
0x180012e08  mov     rbx, [rax+80h]
0x180012e0f  lea     rcx, [rbp+var_18]
0x180012e13  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180012e18  lea     r8, [rbp+var_18]
0x180012e1c  mov     edx, 1
0x180012e21  mov     rcx, rdi
0x180012e24  mov     rax, rbx
0x180012e27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e2c  mov     ebx, eax
0x180012e2e  test    eax, eax
0x180012e30  jns     short loc_180012E3C
0x180012e32  mov     r9d, eax
0x180012e35  mov     edx, 89h
0x180012e3a  jmp     short loc_180012E73
0x180012e3c  mov     [rbp+var_10], r14
0x180012e40  mov     rdi, [rbp+var_18]
0x180012e44  mov     rcx, rdi
0x180012e47  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@PEAUIRandomAccessStreamReference@Streams@Storage@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAUIRandomAccessStreamReference@Streams@Storage@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStreamReference *> *>(Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStreamReference *> *,tagCOWAIT_FLAGS,ulong,bool *)
0x180012e4c  mov     ebx, eax
0x180012e4e  test    eax, eax
0x180012e50  js      short loc_180012E67
0x180012e52  mov     rax, [rdi]
0x180012e55  lea     rdx, [rbp+var_10]
0x180012e59  mov     rcx, rdi
0x180012e5c  mov     rax, [rax+40h]
0x180012e60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e65  mov     ebx, eax
0x180012e67  test    ebx, ebx
0x180012e69  jns     short loc_180012E88
0x180012e6b  mov     r9d, ebx; char *
0x180012e6e  mov     edx, 8Ch; void *
0x180012e73  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\settingshandlers\\w"...
0x180012e7a  mov     rcx, [rbp+18h]; this
0x180012e7e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012e83  jmp     loc_180012FB1
0x180012e88  mov     rax, [rbp+var_10]
0x180012e8c  test    rax, rax
0x180012e8f  jz      loc_180012FDD
0x180012e95  mov     [rbp+string], r14
0x180012e99  mov     rax, [rax]
0x180012e9c  mov     rbx, [rax+30h]
0x180012ea0  lea     rcx, [rbp+string]
0x180012ea4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180012ea9  lea     rdx, [rbp+string]
0x180012ead  mov     rcx, [rbp+var_10]
0x180012eb1  mov     rax, rbx
0x180012eb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012eb9  mov     ebx, eax
0x180012ebb  test    eax, eax
0x180012ebd  jns     short loc_180012EDC
0x180012ebf  mov     rcx, [rbp+18h]; this
0x180012ec3  mov     r9d, eax; char *
0x180012ec6  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\settingshandlers\\w"...
0x180012ecd  mov     edx, 91h; void *
0x180012ed2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012ed7  jmp     loc_180012FA7
0x180012edc  mov     [rbp+arg_18], r14
0x180012ee0  lea     rcx, [rbp+arg_18]
0x180012ee4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180012ee9  mov     rdi, [rbp+string]
0x180012eed  mov     rcx, rdi
0x180012ef0  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@PEAUIRandomAccessStreamWithContentType@Streams@Storage@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAUIRandomAccessStreamWithContentType@Streams@Storage@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStreamWithContentType *> *>(Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStreamWithContentType *> *,tagCOWAIT_FLAGS,ulong,bool *)
0x180012ef5  mov     ebx, eax
0x180012ef7  test    eax, eax
0x180012ef9  js      short loc_180012F10
0x180012efb  mov     rax, [rdi]
0x180012efe  lea     rdx, [rbp+arg_18]
0x180012f02  mov     rcx, rdi
0x180012f05  mov     rax, [rax+40h]
0x180012f09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f0e  mov     ebx, eax
0x180012f10  test    ebx, ebx
0x180012f12  jns     short loc_180012F2E
0x180012f14  mov     rcx, [rbp+18h]; this
0x180012f18  mov     r9d, ebx; char *
0x180012f1b  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\settingshandlers\\w"...
0x180012f22  mov     edx, 94h; void *
0x180012f27  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012f2c  jmp     short loc_180012F9D
0x180012f2e  mov     [rbp+var_20], r14
0x180012f32  mov     rdi, [rbp+arg_18]
0x180012f36  mov     rax, [rdi]
0x180012f39  mov     rbx, [rax]
0x180012f3c  lea     rcx, [rbp+var_20]
0x180012f40  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180012f45  lea     r8, [rbp+var_20]
0x180012f49  lea     rdx, _GUID_905a0fe1_bc53_11df_8c49_001e4fc686da
0x180012f50  mov     rcx, rdi
0x180012f53  mov     rax, rbx
0x180012f56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f5b  mov     ebx, eax
0x180012f5d  test    eax, eax
0x180012f5f  jns     short loc_180012F68
0x180012f61  mov     edx, 97h
0x180012f66  jmp     short loc_180012F7F
0x180012f68  mov     rdx, rsi
0x180012f6b  lea     rcx, [rbp+var_20]
0x180012f6f  call    ??$CopyTo@UIInspectable@@@?$ComPtr@UIRandomAccessStream@Streams@Storage@Windows@@@WRL@Microsoft@@QEBAJPEAPEAUIInspectable@@@Z; Microsoft::WRL::ComPtr<Windows::Storage::Streams::IRandomAccessStream>::CopyTo<IInspectable>(IInspectable * *)
0x180012f74  mov     ebx, eax
0x180012f76  test    eax, eax
0x180012f78  jns     short loc_180012FBF
0x180012f7a  mov     edx, 98h; void *
0x180012f7f  mov     r9d, eax; char *
0x180012f82  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\settingshandlers\\w"...
0x180012f89  mov     rcx, [rbp+18h]; this
0x180012f8d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012f92  nop
0x180012f93  lea     rcx, [rbp+var_20]
0x180012f97  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180012f9c  nop
0x180012f9d  lea     rcx, [rbp+arg_18]
0x180012fa1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180012fa6  nop
0x180012fa7  lea     rcx, [rbp+string]
0x180012fab  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180012fb0  nop
0x180012fb1  lea     rcx, [rbp+var_18]
0x180012fb5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180012fba  jmp     loc_180013271
0x180012fbf  lea     rcx, [rbp+var_20]
0x180012fc3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180012fc8  nop
0x180012fc9  lea     rcx, [rbp+arg_18]
0x180012fcd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180012fd2  nop
0x180012fd3  lea     rcx, [rbp+string]
0x180012fd7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180012fdc  nop
0x180012fdd  lea     rcx, [rbp+var_18]
0x180012fe1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180012fe6  jmp     loc_180012DAA
0x180012feb  lea     rdx, stru_18005B388; HSTRING
0x180012ff2  mov     rcx, rbx; this
0x180012ff5  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180012ffa  test    al, al
0x180012ffc  jz      loc_18001308E
0x180013002  mov     [rbp+arg_18], r14
0x180013006  mov     [rbp+var_10], r14
0x18001300a  mov     dword ptr [rbp+string], 4
0x180013011  mov     [rbp+var_18], r14
0x180013015  lea     rcx, [rbp+arg_18]
0x180013019  call    ?InternalRelease@?$ComPtr@VDisconnectWorkAccount@WorkAccess@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::WorkAccess::DisconnectWorkAccount>::InternalRelease(void)
0x18001301e  lea     r9, [rbp+var_10]
0x180013022  lea     r8, [rbp+string]
0x180013026  lea     rdx, [rbp+var_18]
0x18001302a  lea     rcx, [rbp+arg_18]
0x18001302e  call    ??$MakeAndInitialize@VDisconnectWorkAccount@WorkAccess@SystemSettings@@V123@AEAPEAUIWebAccount@Credentials@Security@Windows@@AEAW4WorkAccountType@23@AEAPEAUITokenBrokerInternalStatics@Web@Authentication@6Internal@7@@Details@WRL@Microsoft@@YAJPEAPEAVDisconnectWorkAccount@WorkAccess@SystemSettings@@AEAPEAUIWebAccount@Credentials@Security@Windows@@AEAW4WorkAccountType@45@AEAPEAUITokenBrokerInternalStatics@Web@Authentication@8Internal@9@@Z; Microsoft::WRL::Details::MakeAndInitialize<SystemSettings::WorkAccess::DisconnectWorkAccount,SystemSettings::WorkAccess::DisconnectWorkAccount,Windows::Security::Credentials::IWebAccount * &,SystemSettings::WorkAccess::WorkAccountType &,Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics * &>(SystemSettings::WorkAccess::DisconnectWorkAccount * *,Windows::Security::Credentials::IWebAccount * &,SystemSettings::WorkAccess::WorkAccountType &,Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics * &)
0x180013033  mov     ebx, eax
0x180013035  test    eax, eax
0x180013037  jns     short loc_180013040
0x180013039  mov     edx, 0A1h
0x18001303e  jmp     short loc_18001305E
0x180013040  mov     r8, rsi
0x180013043  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x18001304a  mov     rcx, [rbp+arg_18]
0x18001304e  call    ??$AsIID@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UISettingItem@DataModel@SystemSettings@@UISettingItemTelemetry@56@UISettingsAppNotification@56@UISettingItem2@56@VFtmBase@23@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$00@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UISettingItem@DataModel@SystemSettings@@UISettingItemTelemetry@56@UISettingsAppNotification@56@UISettingItem2@56@VFtmBase@23@@123@AEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassBaseT<1>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,SystemSettings::DataModel::ISettingItem,SystemSettings::DataModel::ISettingItemTelemetry,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,SystemSettings::DataModel::ISettingItem,SystemSettings::DataModel::ISettingItemTelemetry,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase> *,_GUID const &,void * *)
0x180013053  mov     ebx, eax
0x180013055  test    eax, eax
0x180013057  jns     short loc_180013080
0x180013059  mov     edx, 0A2h; void *
0x18001305e  mov     r9d, eax; char *
0x180013061  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\settingshandlers\\w"...
0x180013068  mov     rcx, [rbp+18h]; this
0x18001306c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013071  nop
0x180013072  lea     rcx, [rbp+arg_18]
0x180013076  call    ?InternalRelease@?$ComPtr@VDisconnectWorkAccount@WorkAccess@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::WorkAccess::DisconnectWorkAccount>::InternalRelease(void)
0x18001307b  jmp     loc_180013271
0x180013080  lea     rcx, [rbp+arg_18]
0x180013084  call    ?InternalRelease@?$ComPtr@VDisconnectWorkAccount@WorkAccess@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::WorkAccess::DisconnectWorkAccount>::InternalRelease(void)
0x180013089  jmp     loc_180012DAA
0x18001308e  lea     rdx, stru_18005B3B0; HSTRING
0x180013095  mov     rcx, rbx; this
0x180013098  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18001309d  test    al, al
0x18001309f  jz      loc_180013130
0x1800130a5  mov     [rbp+arg_18], r14
0x1800130a9  mov     [rbp+var_10], r14
0x1800130ad  mov     dword ptr [rbp+string], 4
0x1800130b4  mov     [rbp+var_18], r14
0x1800130b8  lea     rcx, [rbp+arg_18]
0x1800130bc  call    ?InternalRelease@?$ComPtr@VDisconnectWorkAccount@WorkAccess@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::WorkAccess::DisconnectWorkAccount>::InternalRelease(void)
0x1800130c1  lea     r9, [rbp+var_10]
0x1800130c5  lea     r8, [rbp+string]
0x1800130c9  lea     rdx, [rbp+var_18]
0x1800130cd  lea     rcx, [rbp+arg_18]
0x1800130d1  call    ??$MakeAndInitialize@VManageWorkAccount@WorkAccess@SystemSettings@@V123@AEAPEAUIWebAccount@Credentials@Security@Windows@@AEAW4WorkAccountType@23@AEAPEAUITokenBrokerInternalStatics@Web@Authentication@6Internal@7@@Details@WRL@Microsoft@@YAJPEAPEAVManageWorkAccount@WorkAccess@SystemSettings@@AEAPEAUIWebAccount@Credentials@Security@Windows@@AEAW4WorkAccountType@45@AEAPEAUITokenBrokerInternalStatics@Web@Authentication@8Internal@9@@Z; Microsoft::WRL::Details::MakeAndInitialize<SystemSettings::WorkAccess::ManageWorkAccount,SystemSettings::WorkAccess::ManageWorkAccount,Windows::Security::Credentials::IWebAccount * &,SystemSettings::WorkAccess::WorkAccountType &,Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics * &>(SystemSettings::WorkAccess::ManageWorkAccount * *,Windows::Security::Credentials::IWebAccount * &,SystemSettings::WorkAccess::WorkAccountType &,Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics * &)
0x1800130d6  mov     ebx, eax
0x1800130d8  test    eax, eax
0x1800130da  jns     short loc_1800130E3
0x1800130dc  mov     edx, 0A7h
0x1800130e1  jmp     short loc_180013101
0x1800130e3  mov     r8, rsi
0x1800130e6  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x1800130ed  mov     rcx, [rbp+arg_18]
0x1800130f1  call    ??$AsIID@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UISettingItem@DataModel@SystemSettings@@UISettingItemTelemetry@56@UISettingsAppNotification@56@UISettingItem2@56@VFtmBase@23@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$00@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UISettingItem@DataModel@SystemSettings@@UISettingItemTelemetry@56@UISettingsAppNotification@56@UISettingItem2@56@VFtmBase@23@@123@AEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassBaseT<1>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,SystemSettings::DataModel::ISettingItem,SystemSettings::DataModel::ISettingItemTelemetry,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,SystemSettings::DataModel::ISettingItem,SystemSettings::DataModel::ISettingItemTelemetry,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase> *,_GUID const &,void * *)
0x1800130f6  mov     ebx, eax
0x1800130f8  test    eax, eax
0x1800130fa  jns     short loc_180013122
0x1800130fc  mov     edx, 0A8h; void *
0x180013101  mov     r9d, eax; char *
0x180013104  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\settingshandlers\\w"...
0x18001310b  mov     rcx, [rbp+18h]; this
0x18001310f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013114  lea     rcx, [rbp+arg_18]
0x180013118  call    ?InternalRelease@?$ComPtr@VDisconnectWorkAccount@WorkAccess@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::WorkAccess::DisconnectWorkAccount>::InternalRelease(void)
0x18001311d  jmp     loc_180013271
0x180013122  lea     rcx, [rbp+arg_18]
0x180013126  call    ?InternalRelease@?$ComPtr@VDisconnectWorkAccount@WorkAccess@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::WorkAccess::DisconnectWorkAccount>::InternalRelease(void)
0x18001312b  jmp     loc_180012DAA
0x180013130  lea     rdx, stru_18005B3D0; HSTRING
0x180013137  mov     rcx, rbx; this
0x18001313a  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18001313f  test    al, al
0x180013141  jz      loc_1800131CA
0x180013147  mov     [rbp+arg_18], r14
0x18001314b  mov     dword ptr [rbp+string], 4
0x180013152  mov     [rbp+var_10], r14
0x180013156  lea     rcx, [rbp+arg_18]
0x18001315a  call    ?InternalRelease@?$ComPtr@VDisconnectWorkAccount@WorkAccess@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::WorkAccess::DisconnectWorkAccount>::InternalRelease(void)
0x18001315f  lea     r8, [rbp+string]
0x180013163  lea     rdx, [rbp+var_10]
0x180013167  lea     rcx, [rbp+arg_18]
0x18001316b  call    ??$MakeAndInitialize@VInfoWorkAccount@WorkAccess@SystemSettings@@V123@$$TW4WorkAccountType@23@@Details@WRL@Microsoft@@YAJPEAPEAVInfoWorkAccount@WorkAccess@SystemSettings@@$$QEA$$T$$QEAW4WorkAccountType@45@@Z; Microsoft::WRL::Details::MakeAndInitialize<SystemSettings::WorkAccess::InfoWorkAccount,SystemSettings::WorkAccess::InfoWorkAccount,std::nullptr_t,SystemSettings::WorkAccess::WorkAccountType>(SystemSettings::WorkAccess::InfoWorkAccount * *,SystemSettings::WorkAccess::$$T$$QEAW4WorkAccountType &&)
  ... truncated ...
```
