# Windows::Internal::ApplicationModel::Sync::ImportAccountsOperation::s_DuplicateDeviceAccountConfiguration(Windows::ApplicationModel::UserDataAccounts::SystemAccess::IDeviceAccountConfiguration *,Windows::ApplicationModel::UserDataAccounts::SystemAccess::IDeviceAccountConfiguration * *)

- ea: `0x18004a0a0`
- end: `0x18004a6dd`
- name: `?s_DuplicateDeviceAccountConfiguration@ImportAccountsOperation@Sync@ApplicationModel@Internal@Windows@@CAJPEAUIDeviceAccountConfiguration@SystemAccess@UserDataAccounts@35@PEAPEAU67835@@Z`
- size: `1597`
- prototype: `__int64 __fastcall(struct Windows::ApplicationModel::UserDataAccounts::SystemAccess::IDeviceAccountConfiguration *, struct Windows::ApplicationModel::UserDataAccounts::SystemAccess::IDeviceAccountConfiguration **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800490b8`

## callees

- `0x180006eac`
- `0x18000e87c`
- `0x180011ffc`
- `0x180048864`
- `0x18004a0a0`
- `0x180069730`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a12c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a168`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a19f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a1f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a24c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a2a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a305`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a363`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a3c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a6a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a12c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a168`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a19f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a1f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a24c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a2a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a305`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a363`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a3c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a6a4`

## string_xrefs

- `0x18004a0df`: `Windows.ApplicationModel.UserDataAccounts.SystemAccess.DeviceAccountConfiguration`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Internal::ApplicationModel::Sync::ImportAccountsOperation::s_DuplicateDeviceAccountConfiguration(
        struct Windows::ApplicationModel::UserDataAccounts::SystemAccess::IDeviceAccountConfiguration *a1,
        struct Windows::ApplicationModel::UserDataAccounts::SystemAccess::IDeviceAccountConfiguration **a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  __int64 (__fastcall *v6)(struct Windows::ApplicationModel::UserDataAccounts::SystemAccess::IDeviceAccountConfiguration *, HSTRING *); // rbx
  int v7; // eax
  __int64 v8; // rdx
  __int64 (__fastcall *v9)(struct Windows::ApplicationModel::UserDataAccounts::SystemAccess::IDeviceAccountConfiguration *, HSTRING *); // rbx
  __int64 (__fastcall *v10)(struct Windows::ApplicationModel::UserDataAccounts::SystemAccess::IDeviceAccountConfiguration *, HSTRING *); // rbx
  __int64 (__fastcall *v11)(struct Windows::ApplicationModel::UserDataAccounts::SystemAccess::IDeviceAccountConfiguration *, HSTRING *); // rbx
  __int64 (__fastcall *v12)(struct Windows::ApplicationModel::UserDataAccounts::SystemAccess::IDeviceAccountConfiguration *, HSTRING *); // rbx
  __int64 (__fastcall *v13)(struct Windows::ApplicationModel::UserDataAccounts::SystemAccess::IDeviceAccountConfiguration *, HSTRING *); // rbx
  __int64 (__fastcall *v14)(struct Windows::ApplicationModel::UserDataAccounts::SystemAccess::IDeviceAccountConfiguration *, HSTRING *); // rbx
  __int64 (__fastcall *v15)(struct Windows::ApplicationModel::UserDataAccounts::SystemAccess::IDeviceAccountConfiguration *, HSTRING *); // rbx
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // rdx
  __int64 v20; // rdx
  HSTRING string; // [rsp+20h] [rbp-50h] BYREF
  _BYTE v23[8]; // [rsp+28h] [rbp-48h] BYREF
  __int64 v24; // [rsp+30h] [rbp-40h] BYREF
  unsigned int v25; // [rsp+38h] [rbp-38h] BYREF
  unsigned int v26; // [rsp+3Ch] [rbp-34h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-30h] BYREF
  __int64 v28; // [rsp+58h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  *a2 = 0;
  v24 = 0;
  v28 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.ApplicationModel.UserDataAccounts.SystemAccess.DeviceAccountConfiguration",
    0x52u,
    0x51u);
  v4 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::ApplicationModel::UserDataAccounts::SystemAccess::IDeviceAccountConfiguration>>(
         v28,
         &v24);
  v5 = v4;
  if ( v4 >= 0 )
  {
    string = 0;
    v6 = *(__int64 (__fastcall **)(struct Windows::ApplicationModel::UserDataAccounts::SystemAccess::IDeviceAccountConfiguration *, HSTRING *))(*(_QWORD *)a1 + 48LL);
    WindowsDeleteString(0);
    string = 0;
    v7 = v6(a1, &string);
    v5 = v7;
    if ( v7 >= 0 )
    {
      v7 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v24 + 56LL))(v24, string);
      v5 = v7;
      if ( v7 >= 0 )
      {
        v9 = *(__int64 (__fastcall **)(struct Windows::ApplicationModel::UserDataAccounts::SystemAccess::IDeviceAccountConfiguration *, HSTRING *))(*(_QWORD *)a1 + 64LL);
        WindowsDeleteString(string);
        string = 0;
        v7 = v9(a1, &string);
        v5 = v7;
        if ( v7 >= 0 )
        {
          v7 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v24 + 72LL))(v24, string);
          v5 = v7;
          if ( v7 >= 0 )
          {
            v10 = *(__int64 (__fastcall **)(struct Windows::ApplicationModel::UserDataAccounts::SystemAccess::IDeviceAccountConfiguration *, HSTRING *))(*(_QWORD *)a1 + 96LL);
            WindowsDeleteString(string);
            string = 0;
            v7 = v10(a1, &string);
            v5 = v7;
            if ( v7 >= 0 )
            {
              v7 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v24 + 104LL))(v24, string);
              v5 = v7;
              if ( v7 >= 0 )
              {
                v11 = *(__int64 (__fastcall **)(struct Windows::ApplicationModel::UserDataAccounts::SystemAccess::IDeviceAccountConfiguration *, HSTRING *))(*(_QWORD *)a1 + 112LL);
                WindowsDeleteString(string);
                string = 0;
                v7 = v11(a1, &string);
                v5 = v7;
                if ( v7 >= 0 )
                {
                  v7 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v24 + 120LL))(v24, string);
                  v5 = v7;
                  if ( v7 >= 0 )
                  {
                    v12 = *(__int64 (__fastcall **)(struct Windows::ApplicationModel::UserDataAccounts::SystemAccess::IDeviceAccountConfiguration *, HSTRING *))(*(_QWORD *)a1 + 176LL);
                    WindowsDeleteString(string);
                    string = 0;
                    v7 = v12(a1, &string);
                    v5 = v7;
                    if ( v7 >= 0 )
                    {
                      v7 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v24 + 184LL))(v24, string);
                      v5 = v7;
                      if ( v7 >= 0 )
                      {
                        v13 = *(__int64 (__fastcall **)(struct Windows::ApplicationModel::UserDataAccounts::SystemAccess::IDeviceAccountConfiguration *, HSTRING *))(*(_QWORD *)a1 + 224LL);
                        WindowsDeleteString(string);
                        string = 0;
                        v7 = v13(a1, &string);
                        v5 = v7;
                        if ( v7 >= 0 )
                        {
                          v7 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v24 + 232LL))(v24, string);
                          v5 = v7;
                          if ( v7 >= 0 )
                          {
                            v14 = *(__int64 (__fastcall **)(struct Windows::ApplicationModel::UserDataAccounts::SystemAccess::IDeviceAccountConfiguration *, HSTRING *))(*(_QWORD *)a1 + 240LL);
                            WindowsDeleteString(string);
                            string = 0;
                            v7 = v14(a1, &string);
                            v5 = v7;
                            if ( v7 >= 0 )
                            {
                              v7 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v24 + 248LL))(v24, string);
                              v5 = v7;
                              if ( v7 >= 0 )
                              {
                                v15 = *(__int64 (__fastcall **)(struct Windows::ApplicationModel::UserDataAccounts::SystemAccess::IDeviceAccountConfiguration *, HSTRING *))(*(_QWORD *)a1 + 288LL);
                                WindowsDeleteString(string);
                                string = 0;
                                v7 = v15(a1, &string);
                                v5 = v7;
                                if ( v7 >= 0 )
                                {
                                  v7 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v24 + 296LL))(
                                         v24,
                                         string);
                                  v5 = v7;
                                  if ( v7 >= 0 )
                                  {
                                    v26 = 0;
                                    v7 = (*(__int64 (__fastcall **)(struct Windows::ApplicationModel::UserDataAccounts::SystemAccess::IDeviceAccountConfiguration *, unsigned int *))(*(_QWORD *)a1 + 80LL))(
                                           a1,
                                           &v26);
                                    v5 = v7;
                                    if ( v7 >= 0 )
                                    {
                                      v7 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v24 + 88LL))(
                                             v24,
                                             v26);
                                      v5 = v7;
                                      if ( v7 >= 0 )
                                      {
                                        v23[0] = 0;
                                        v7 = (*(__int64 (__fastcall **)(struct Windows::ApplicationModel::UserDataAccounts::SystemAccess::IDeviceAccountConfiguration *, _BYTE *))(*(_QWORD *)a1 + 128LL))(
                                               a1,
                                               v23);
                                        v5 = v7;
                                        if ( v7 >= 0 )
                                        {
                                          LOBYTE(v16) = v23[0];
                                          v7 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v24 + 136LL))(
                                                 v24,
                                                 v16);
                                          v5 = v7;
                                          if ( v7 >= 0 )
                                          {
                                            v7 = (*(__int64 (__fastcall **)(struct Windows::ApplicationModel::UserDataAccounts::SystemAccess::IDeviceAccountConfiguration *, _BYTE *))(*(_QWORD *)a1 + 144LL))(
                                                   a1,
                                                   v23);
                                            v5 = v7;
                                            if ( v7 >= 0 )
                                            {
                                              LOBYTE(v17) = v23[0];
                                              v7 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v24 + 152LL))(
                                                     v24,
                                                     v17);
                                              v5 = v7;
                                              if ( v7 >= 0 )
                                              {
                                                v7 = (*(__int64 (__fastcall **)(struct Windows::ApplicationModel::UserDataAccounts::SystemAccess::IDeviceAccountConfiguration *, _BYTE *))(*(_QWORD *)a1 + 160LL))(
                                                       a1,
                                                       v23);
                                                v5 = v7;
                                                if ( v7 >= 0 )
                                                {
                                                  LOBYTE(v18) = v23[0];
                                                  v7 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v24 + 168LL))(
                                                         v24,
                                                         v18);
                                                  v5 = v7;
                                                  if ( v7 >= 0 )
                                                  {
                                                    v7 = (*(__int64 (__fastcall **)(struct Windows::ApplicationModel::UserDataAccounts::SystemAccess::IDeviceAccountConfiguration *, _BYTE *))(*(_QWORD *)a1 + 208LL))(
                                                           a1,
                                                           v23);
                                                    v5 = v7;
                                                    if ( v7 >= 0 )
                                                    {
                                                      LOBYTE(v19) = v23[0];
                                                      v7 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v24 + 216LL))(
                                                             v24,
                                                             v19);
                                                      v5 = v7;
                                                      if ( v7 >= 0 )
                                                      {
                                                        v7 = (*(__int64 (__fastcall **)(struct Windows::ApplicationModel::UserDataAccounts::SystemAccess::IDeviceAccountConfiguration *, _BYTE *))(*(_QWORD *)a1 + 272LL))(
                                                               a1,
                                                               v23);
                                                        v5 = v7;
                                                        if ( v7 >= 0 )
                                                        {
                                                          LOBYTE(v20) = v23[0];
                                                          v7 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v24 + 280LL))(
                                                                 v24,
                                                                 v20);
                                                          v5 = v7;
                                                          if ( v7 >= 0 )
                                                          {
                                                            v25 = 0;
                                                            v7 = (*(__int64 (__fastcall **)(struct Windows::ApplicationModel::UserDataAccounts::SystemAccess::IDeviceAccountConfiguration *, unsigned int *))(*(_QWORD *)a1 + 192LL))(
                                                                   a1,
                                                                   &v25);
                                                            v5 = v7;
                                                            if ( v7 >= 0 )
                                                            {
                                                              v7 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v24 + 200LL))(
                                                                     v24,
                                                                     v25);
                                                              v5 = v7;
                                                              if ( v7 >= 0 )
                                                              {
                                                                v7 = (*(__int64 (__fastcall **)(struct Windows::ApplicationModel::UserDataAccounts::SystemAccess::IDeviceAccountConfiguration *, unsigned int *))(*(_QWORD *)a1 + 256LL))(
                                                                       a1,
                                                                       &v25);
                                                                v5 = v7;
                                                                if ( v7 >= 0 )
                                                                {
                                                                  v7 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v24 + 264LL))(
                                                                         v24,
                                                                         v25);
                                                                  v5 = v7;
                                                                  if ( v7 >= 0 )
                                                                  {
                                                                    v7 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct Windows::ApplicationModel::UserDataAccounts::SystemAccess::IDeviceAccountConfiguration **))v24)(
                                                                           v24,
                                                                           &GUID_ad0123a3_fbdc_4d1b_be43_5a27ea4a1b63,
                                                                           a2);
                                                                    v5 = v7;
                                                                    if ( v7 >= 0 )
                                                                    {
                                                                      WindowsDeleteString(string);
                                                                      v5 = 0;
                                                                      goto LABEL_71;
                                                                    }
                                                                    v8 = 263;
                                                                  }
                                                                  else
                                                                  {
                                                                    v8 = 261;
                                                                  }
                                                                }
                                                                else
                                                                {
                                                                  v8 = 260;
                                                                }
                                                              }
                                                              else
                                                              {
                                                                v8 = 259;
                                                              }
                                                            }
                                                            else
                                                            {
                                                              v8 = 258;
                                                            }
                                                          }
                                                          else
                                                          {
                                                            v8 = 255;
                                                          }
                                                        }
                                                        else
                                                        {
                                                          v8 = 254;
                                                        }
                                                      }
                                                      else
                                                      {
                                                        v8 = 253;
                                                      }
                                                    }
                                                    else
                                                    {
                                                      v8 = 252;
                                                    }
                                                  }
                                                  else
                                                  {
                                                    v8 = 251;
                                                  }
                                                }
                                                else
                                                {
                                                  v8 = 250;
                                                }
                                              }
                                              else
                                              {
                                                v8 = 249;
                                              }
                                            }
                                            else
                                            {
                                              v8 = 248;
                                            }
                                          }
                                          else
                                          {
                                            v8 = 247;
                                          }
                                        }
                                        else
                                        {
                                          v8 = 246;
                                        }
                                      }
                                      else
                                      {
                                        v8 = 243;
                                      }
                                    }
                                    else
                                    {
                                      v8 = 242;
                                    }
                                  }
                                  else
                                  {
                                    v8 = 239;
                                  }
                                }
                                else
                                {
                                  v8 = 238;
                                }
                              }
                              else
                              {
                                v8 = 237;
                              }
                            }
                            else
                            {
                              v8 = 236;
                            }
                          }
                          else
                          {
                            v8 = 235;
                          }
                        }
                        else
                        {
                          v8 = 234;
                        }
                      }
                      else
                      {
                        v8 = 233;
                      }
                    }
                    else
                    {
                      v8 = 232;
                    }
                  }
                  else
                  {
                    v8 = 231;
                  }
                }
                else
                {
                  v8 = 230;
                }
              }
              else
              {
                v8 = 229;
              }
            }
            else
            {
              v8 = 228;
            }
          }
          else
          {
            v8 = 227;
          }
        }
        else
        {
          v8 = 226;
        }
      }
      else
      {
        v8 = 225;
      }
    }
    else
    {
      v8 = 224;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\importaccountsoperation.cpp",
      (const char *)(unsigned int)v7,
      (int)string);
    WindowsDeleteString(string);
LABEL_71:
    string = 0;
    goto LABEL_72;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xDD,
    (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\importaccountsoperation.cpp",
    (const char *)(unsigned int)v4,
    (int)string);
LABEL_72:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
  return v5;
}

```

## disassembly

```asm
0x18004a0a0  mov     [rsp-18h+arg_10], rbx
0x18004a0a5  mov     [rsp-18h+arg_18], rsi
0x18004a0aa  push    rbp
0x18004a0ab  push    rdi
0x18004a0ac  push    r14
0x18004a0ae  mov     rbp, rsp
0x18004a0b1  sub     rsp, 70h
0x18004a0b5  mov     rax, cs:__security_cookie
0x18004a0bc  xor     rax, rsp
0x18004a0bf  mov     [rbp+var_10], rax
0x18004a0c3  mov     rsi, rdx
0x18004a0c6  mov     rdi, rcx
0x18004a0c9  xor     r14d, r14d
0x18004a0cc  mov     [rdx], r14
0x18004a0cf  mov     [rbp+var_40], r14
0x18004a0d3  mov     [rbp+var_18], r14
0x18004a0d7  lea     r9d, [r14+51h]; unsigned int
0x18004a0db  lea     r8d, [r14+52h]; unsigned int
0x18004a0df  lea     rdx, ?RuntimeClass_Windows_ApplicationModel_UserDataAccounts_SystemAccess_DeviceAccountConfiguration@@3QBGB; "Windows.ApplicationModel.UserDataAccoun"...
0x18004a0e6  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18004a0ea  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18004a0ef  lea     rdx, [rbp+var_40]
0x18004a0f3  mov     rcx, [rbp+var_18]
0x18004a0f7  call    ??$ActivateInstance@V?$ComPtr@UIDeviceAccountConfiguration@SystemAccess@UserDataAccounts@ApplicationModel@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIDeviceAccountConfiguration@SystemAccess@UserDataAccounts@ApplicationModel@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::ApplicationModel::UserDataAccounts::SystemAccess::IDeviceAccountConfiguration>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::ApplicationModel::UserDataAccounts::SystemAccess::IDeviceAccountConfiguration>>)
0x18004a0fc  mov     ebx, eax
0x18004a0fe  test    eax, eax
0x18004a100  jns     short loc_18004A11F
0x18004a102  mov     rcx, [rbp+18h]; this
0x18004a106  mov     r9d, eax; char *
0x18004a109  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\accountscontrol\\api"...
0x18004a110  mov     edx, 0DDh; void *
0x18004a115  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004a11a  jmp     loc_18004A6B1
0x18004a11f  mov     [rbp+string], r14
0x18004a123  mov     rax, [rdi]
0x18004a126  mov     rbx, [rax+30h]
0x18004a12a  xor     ecx, ecx; string
0x18004a12c  call    cs:__imp_WindowsDeleteString
0x18004a132  mov     [rbp+string], r14
0x18004a136  lea     rdx, [rbp+string]
0x18004a13a  mov     rcx, rdi
0x18004a13d  mov     rax, rbx
0x18004a140  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a145  mov     ebx, eax
0x18004a147  test    eax, eax
0x18004a149  jns     short loc_18004A173
0x18004a14b  mov     edx, 0E0h; void *
0x18004a150  mov     rcx, [rbp+18h]; this
0x18004a154  mov     r9d, eax; char *
0x18004a157  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\accountscontrol\\api"...
0x18004a15e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004a163  nop
0x18004a164  mov     rcx, [rbp+string]; string
0x18004a168  call    cs:__imp_WindowsDeleteString
0x18004a16e  jmp     loc_18004A6AD
0x18004a173  mov     rcx, [rbp+var_40]
0x18004a177  mov     rax, [rcx]
0x18004a17a  mov     rdx, [rbp+string]
0x18004a17e  mov     rax, [rax+38h]
0x18004a182  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a187  mov     ebx, eax
0x18004a189  test    eax, eax
0x18004a18b  jns     short loc_18004A194
0x18004a18d  mov     edx, 0E1h
0x18004a192  jmp     short loc_18004A150
0x18004a194  mov     rax, [rdi]
0x18004a197  mov     rbx, [rax+40h]
0x18004a19b  mov     rcx, [rbp+string]; string
0x18004a19f  call    cs:__imp_WindowsDeleteString
0x18004a1a5  mov     [rbp+string], r14
0x18004a1a9  lea     rdx, [rbp+string]
0x18004a1ad  mov     rcx, rdi
0x18004a1b0  mov     rax, rbx
0x18004a1b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a1b8  mov     ebx, eax
0x18004a1ba  test    eax, eax
0x18004a1bc  jns     short loc_18004A1C5
0x18004a1be  mov     edx, 0E2h
0x18004a1c3  jmp     short loc_18004A150
0x18004a1c5  mov     rcx, [rbp+var_40]
0x18004a1c9  mov     rax, [rcx]
0x18004a1cc  mov     rdx, [rbp+string]
0x18004a1d0  mov     rax, [rax+48h]
0x18004a1d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a1d9  mov     ebx, eax
0x18004a1db  test    eax, eax
0x18004a1dd  jns     short loc_18004A1E9
0x18004a1df  mov     edx, 0E3h
0x18004a1e4  jmp     loc_18004A150
0x18004a1e9  mov     rax, [rdi]
0x18004a1ec  mov     rbx, [rax+60h]
0x18004a1f0  mov     rcx, [rbp+string]; string
0x18004a1f4  call    cs:__imp_WindowsDeleteString
0x18004a1fa  mov     [rbp+string], r14
0x18004a1fe  lea     rdx, [rbp+string]
0x18004a202  mov     rcx, rdi
0x18004a205  mov     rax, rbx
0x18004a208  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a20d  mov     ebx, eax
0x18004a20f  test    eax, eax
0x18004a211  jns     short loc_18004A21D
0x18004a213  mov     edx, 0E4h
0x18004a218  jmp     loc_18004A150
0x18004a21d  mov     rcx, [rbp+var_40]
0x18004a221  mov     rax, [rcx]
0x18004a224  mov     rdx, [rbp+string]
0x18004a228  mov     rax, [rax+68h]
0x18004a22c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a231  mov     ebx, eax
0x18004a233  test    eax, eax
0x18004a235  jns     short loc_18004A241
0x18004a237  mov     edx, 0E5h
0x18004a23c  jmp     loc_18004A150
0x18004a241  mov     rax, [rdi]
0x18004a244  mov     rbx, [rax+70h]
0x18004a248  mov     rcx, [rbp+string]; string
0x18004a24c  call    cs:__imp_WindowsDeleteString
0x18004a252  mov     [rbp+string], r14
0x18004a256  lea     rdx, [rbp+string]
0x18004a25a  mov     rcx, rdi
0x18004a25d  mov     rax, rbx
0x18004a260  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a265  mov     ebx, eax
0x18004a267  test    eax, eax
0x18004a269  jns     short loc_18004A275
0x18004a26b  mov     edx, 0E6h
0x18004a270  jmp     loc_18004A150
0x18004a275  mov     rcx, [rbp+var_40]
0x18004a279  mov     rax, [rcx]
0x18004a27c  mov     rdx, [rbp+string]
0x18004a280  mov     rax, [rax+78h]
0x18004a284  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a289  mov     ebx, eax
0x18004a28b  test    eax, eax
0x18004a28d  jns     short loc_18004A299
0x18004a28f  mov     edx, 0E7h
0x18004a294  jmp     loc_18004A150
0x18004a299  mov     rax, [rdi]
0x18004a29c  mov     rbx, [rax+0B0h]
0x18004a2a3  mov     rcx, [rbp+string]; string
0x18004a2a7  call    cs:__imp_WindowsDeleteString
0x18004a2ad  mov     [rbp+string], r14
0x18004a2b1  lea     rdx, [rbp+string]
0x18004a2b5  mov     rcx, rdi
0x18004a2b8  mov     rax, rbx
0x18004a2bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a2c0  mov     ebx, eax
0x18004a2c2  test    eax, eax
0x18004a2c4  jns     short loc_18004A2D0
0x18004a2c6  mov     edx, 0E8h
0x18004a2cb  jmp     loc_18004A150
0x18004a2d0  mov     rcx, [rbp+var_40]
0x18004a2d4  mov     rax, [rcx]
0x18004a2d7  mov     rdx, [rbp+string]
0x18004a2db  mov     rax, [rax+0B8h]
0x18004a2e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a2e7  mov     ebx, eax
0x18004a2e9  test    eax, eax
0x18004a2eb  jns     short loc_18004A2F7
0x18004a2ed  mov     edx, 0E9h
0x18004a2f2  jmp     loc_18004A150
0x18004a2f7  mov     rax, [rdi]
0x18004a2fa  mov     rbx, [rax+0E0h]
0x18004a301  mov     rcx, [rbp+string]; string
0x18004a305  call    cs:__imp_WindowsDeleteString
0x18004a30b  mov     [rbp+string], r14
0x18004a30f  lea     rdx, [rbp+string]
0x18004a313  mov     rcx, rdi
0x18004a316  mov     rax, rbx
0x18004a319  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a31e  mov     ebx, eax
0x18004a320  test    eax, eax
0x18004a322  jns     short loc_18004A32E
0x18004a324  mov     edx, 0EAh
0x18004a329  jmp     loc_18004A150
0x18004a32e  mov     rcx, [rbp+var_40]
0x18004a332  mov     rax, [rcx]
0x18004a335  mov     rdx, [rbp+string]
0x18004a339  mov     rax, [rax+0E8h]
0x18004a340  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a345  mov     ebx, eax
0x18004a347  test    eax, eax
0x18004a349  jns     short loc_18004A355
0x18004a34b  mov     edx, 0EBh
0x18004a350  jmp     loc_18004A150
0x18004a355  mov     rax, [rdi]
0x18004a358  mov     rbx, [rax+0F0h]
0x18004a35f  mov     rcx, [rbp+string]; string
0x18004a363  call    cs:__imp_WindowsDeleteString
0x18004a369  mov     [rbp+string], r14
0x18004a36d  lea     rdx, [rbp+string]
0x18004a371  mov     rcx, rdi
0x18004a374  mov     rax, rbx
0x18004a377  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a37c  mov     ebx, eax
0x18004a37e  test    eax, eax
0x18004a380  jns     short loc_18004A38C
0x18004a382  mov     edx, 0ECh
0x18004a387  jmp     loc_18004A150
0x18004a38c  mov     rcx, [rbp+var_40]
0x18004a390  mov     rax, [rcx]
0x18004a393  mov     rdx, [rbp+string]
0x18004a397  mov     rax, [rax+0F8h]
0x18004a39e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a3a3  mov     ebx, eax
0x18004a3a5  test    eax, eax
0x18004a3a7  jns     short loc_18004A3B3
0x18004a3a9  mov     edx, 0EDh
0x18004a3ae  jmp     loc_18004A150
0x18004a3b3  mov     rax, [rdi]
0x18004a3b6  mov     rbx, [rax+120h]
0x18004a3bd  mov     rcx, [rbp+string]; string
0x18004a3c1  call    cs:__imp_WindowsDeleteString
0x18004a3c7  mov     [rbp+string], r14
0x18004a3cb  lea     rdx, [rbp+string]
0x18004a3cf  mov     rcx, rdi
0x18004a3d2  mov     rax, rbx
0x18004a3d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a3da  mov     ebx, eax
0x18004a3dc  test    eax, eax
0x18004a3de  jns     short loc_18004A3EA
0x18004a3e0  mov     edx, 0EEh
0x18004a3e5  jmp     loc_18004A150
0x18004a3ea  mov     rcx, [rbp+var_40]
0x18004a3ee  mov     rax, [rcx]
0x18004a3f1  mov     rdx, [rbp+string]
0x18004a3f5  mov     rax, [rax+128h]
0x18004a3fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a401  mov     ebx, eax
0x18004a403  test    eax, eax
0x18004a405  jns     short loc_18004A411
0x18004a407  mov     edx, 0EFh
0x18004a40c  jmp     loc_18004A150
0x18004a411  mov     [rbp+var_34], r14d
0x18004a415  mov     rax, [rdi]
0x18004a418  lea     rdx, [rbp+var_34]
0x18004a41c  mov     rcx, rdi
0x18004a41f  mov     rax, [rax+50h]
0x18004a423  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a428  mov     ebx, eax
0x18004a42a  test    eax, eax
0x18004a42c  jns     short loc_18004A438
0x18004a42e  mov     edx, 0F2h
0x18004a433  jmp     loc_18004A150
0x18004a438  mov     rcx, [rbp+var_40]
0x18004a43c  mov     rax, [rcx]
0x18004a43f  mov     edx, [rbp+var_34]
0x18004a442  mov     rax, [rax+58h]
0x18004a446  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a44b  mov     ebx, eax
0x18004a44d  test    eax, eax
0x18004a44f  jns     short loc_18004A45B
0x18004a451  mov     edx, 0F3h
0x18004a456  jmp     loc_18004A150
0x18004a45b  mov     [rbp+var_48], r14b
0x18004a45f  mov     rax, [rdi]
0x18004a462  lea     rdx, [rbp+var_48]
0x18004a466  mov     rcx, rdi
0x18004a469  mov     rax, [rax+80h]
0x18004a470  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a475  mov     ebx, eax
0x18004a477  test    eax, eax
0x18004a479  jns     short loc_18004A485
0x18004a47b  mov     edx, 0F6h
0x18004a480  jmp     loc_18004A150
0x18004a485  mov     rcx, [rbp+var_40]
0x18004a489  mov     rax, [rcx]
0x18004a48c  mov     dl, [rbp+var_48]
0x18004a48f  mov     rax, [rax+88h]
0x18004a496  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a49b  mov     ebx, eax
0x18004a49d  test    eax, eax
0x18004a49f  jns     short loc_18004A4AB
0x18004a4a1  mov     edx, 0F7h
0x18004a4a6  jmp     loc_18004A150
0x18004a4ab  mov     rax, [rdi]
0x18004a4ae  lea     rdx, [rbp+var_48]
0x18004a4b2  mov     rcx, rdi
0x18004a4b5  mov     rax, [rax+90h]
0x18004a4bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a4c1  mov     ebx, eax
0x18004a4c3  test    eax, eax
0x18004a4c5  jns     short loc_18004A4D1
0x18004a4c7  mov     edx, 0F8h
0x18004a4cc  jmp     loc_18004A150
0x18004a4d1  mov     rcx, [rbp+var_40]
0x18004a4d5  mov     rax, [rcx]
0x18004a4d8  mov     dl, [rbp+var_48]
0x18004a4db  mov     rax, [rax+98h]
0x18004a4e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a4e7  mov     ebx, eax
0x18004a4e9  test    eax, eax
0x18004a4eb  jns     short loc_18004A4F7
0x18004a4ed  mov     edx, 0F9h
0x18004a4f2  jmp     loc_18004A150
0x18004a4f7  mov     rax, [rdi]
0x18004a4fa  lea     rdx, [rbp+var_48]
0x18004a4fe  mov     rcx, rdi
0x18004a501  mov     rax, [rax+0A0h]
0x18004a508  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
