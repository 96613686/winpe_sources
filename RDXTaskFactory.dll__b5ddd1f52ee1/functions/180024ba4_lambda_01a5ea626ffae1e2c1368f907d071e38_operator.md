# _lambda_01a5ea626ffae1e2c1368f907d071e38_::operator()

- ea: `0x180024ba4`
- end: `0x1800252f4`
- name: `_lambda_01a5ea626ffae1e2c1368f907d071e38_::operator()`
- size: `1872`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180025e30`

## callees

- `0x180003390`
- `0x18000e330`
- `0x18001094c`
- `0x18001096c`
- `0x180024710`
- `0x1800248ac`
- `0x180024ba4`
- `0x180025d04`
- `0x180050010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180024c0e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180024da6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180024ec6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180024c0e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180024da6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180024ec6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180024bf5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180024d8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180024ead`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180024bf5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180024d8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180024ead`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180024c2b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180024dcc`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180024ee3`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180024c2b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180024dcc`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180024ee3`

## string_xrefs

- `0x18002511a`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\signintomsatask.cpp`
- `0x18002512b`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\signintomsatask.cpp`
- `0x180025143`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\signintomsatask.cpp`
- `0x180025154`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\signintomsatask.cpp`
- `0x180025169`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\signintomsatask.cpp`
- `0x18002517a`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\signintomsatask.cpp`
- `0x180025192`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\signintomsatask.cpp`
- `0x1800251a3`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\signintomsatask.cpp`
- `0x1800251bb`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\signintomsatask.cpp`
- `0x1800251cc`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\signintomsatask.cpp`
- `0x1800251e1`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\signintomsatask.cpp`
- `0x1800251f2`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\signintomsatask.cpp`
- `0x180025207`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\signintomsatask.cpp`
- `0x180025218`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\signintomsatask.cpp`
- `0x18002522d`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\signintomsatask.cpp`
- `0x18002523e`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\signintomsatask.cpp`
- `0x180025256`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\signintomsatask.cpp`
- `0x180025267`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\signintomsatask.cpp`
- `0x18002527c`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\signintomsatask.cpp`
- `0x18002528d`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\signintomsatask.cpp`
- `0x1800252a4`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\signintomsatask.cpp`
- `0x1800252b9`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\signintomsatask.cpp`
- `0x1800252ca`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\signintomsatask.cpp`
- `0x1800252e1`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\signintomsatask.cpp`
- `0x180024bee`: `Windows.Internal.Security.Authentication.Web.TokenBrokerInternal`
- `0x180024ea6`: `Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager`
- `0x180024d86`: `Windows.Security.Authentication.Web.Core.WebTokenRequest`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
_DWORD **__fastcall lambda_01a5ea626ffae1e2c1368f907d071e38_::operator()(_DWORD **a1)
{
  int ActivationFactory; // eax
  const char *v2; // r9
  __int64 v3; // rax
  int v4; // eax
  __int64 v5; // rdx
  __int64 v6; // r8
  const char *v7; // r9
  int (__fastcall ***v8)(_QWORD, GUID *, __int64 *); // rbx
  int DefaultSignInAccount; // eax
  const char *v10; // r9
  __int64 v11; // rax
  int v12; // eax
  const char *v13; // r9
  __int64 v14; // rax
  int v15; // eax
  const char *v16; // r9
  int v17; // eax
  const char *v18; // r9
  __int64 v19; // rbx
  __int64 (__fastcall *v20)(__int64, __int64, _QWORD, HSTRING); // rsi
  HSTRING v21; // rdi
  int v22; // eax
  const char *v23; // r9
  wil *v24; // rcx
  int v25; // edx
  _DWORD **result; // rax
  _DWORD *v27; // rcx
  int v28; // [rsp+20h] [rbp-108h]
  __int64 v29; // [rsp+48h] [rbp-E0h]
  __int64 v30; // [rsp+50h] [rbp-D8h] BYREF
  __int64 *v31; // [rsp+70h] [rbp-B8h] BYREF
  int (__fastcall ***v32)(_QWORD, GUID *, __int64 *); // [rsp+78h] [rbp-B0h] BYREF
  __int64 v33; // [rsp+88h] [rbp-A0h] BYREF
  __int64 *v34; // [rsp+90h] [rbp-98h] BYREF
  __int64 *v35; // [rsp+98h] [rbp-90h] BYREF
  _DWORD **v36; // [rsp+A0h] [rbp-88h]
  HSTRING v37; // [rsp+A8h] [rbp-80h] BYREF
  HSTRING_HEADER v38; // [rsp+B0h] [rbp-78h] BYREF
  HSTRING string; // [rsp+C8h] [rbp-60h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+D0h] [rbp-58h] BYREF
  _QWORD v41[4]; // [rsp+E8h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  v36 = a1;
  v35 = 0;
  if ( WindowsCreateStringReference(
         L"Windows.Internal.Security.Authentication.Web.TokenBrokerInternal",
         0x40u,
         &v38,
         &v37) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  ActivationFactory = RoGetActivationFactory(v37, &GUID_07650a66_66ea_489d_aa90_0dabc75f3567, &v35);
  try
  {
    if ( ActivationFactory >= 0 )
    {
      if ( v35 )
      {
        v32 = 0;
        v3 = *v35;
        v32 = 0;
        v4 = (*(__int64 (__fastcall **)(__int64 *, int (__fastcall ****)(_QWORD, GUID *, __int64 *)))(v3 + 232))(
               v35,
               &v32);
        if ( v4 >= 0 )
        {
          v8 = v32;
          if ( v32 )
          {
            v34 = 0;
            DefaultSignInAccount = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>>(
                                     v32,
                                     v5,
                                     v6);
            if ( DefaultSignInAccount >= 0 )
              DefaultSignInAccount = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64 **))(*v8)[8])(
                                       v8,
                                       &v34);
            if ( DefaultSignInAccount >= 0 )
            {
              if ( v34 )
              {
                v31 = 0;
                v11 = *v34;
                v31 = 0;
                v12 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v11 + 48))(v34, &v31);
                if ( v12 >= 0 )
                {
                  if ( v31 )
                  {
                    v30 = 0;
                    v14 = *v31;
                    v30 = 0;
                    v15 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v14 + 48))(v31, &v30);
                    if ( v15 >= 0 )
                    {
                      if ( v30 )
                      {
                        if ( WindowsCreateStringReference(
                               L"Windows.Security.Authentication.Web.Core.WebTokenRequest",
                               0x38u,
                               &hstringHeader,
                               &string) < 0 )
                          RaiseException(0xC000000D, 1u, 0, 0);
                        v33 = 0;
                        v17 = RoGetActivationFactory(string, &GUID_6cf2141c_0ff0_4c67_b84f_99ddbe4a72c9, &v33);
                        if ( v17 >= 0 )
                        {
                          v19 = v33;
                          if ( v33 )
                          {
                            v29 = 0;
                            v20 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, HSTRING))(*(_QWORD *)v33 + 56LL);
                            v29 = 0;
                            Windows::Internal::StringReference::_ConstructorHelper(
                              (Windows::Internal::StringReference *)&v37,
                              L"{229AE4A6-1AF1-478E-8D91-8C54A57621CE}");
                            v21 = v37;
                            Windows::Internal::StringReference::_ConstructorHelper(
                              (Windows::Internal::StringReference *)v41,
                              L"DefaultAccount");
                            v22 = v20(v19, v30, v41[0], v21);
                            if ( v22 >= 0 )
                              wil::details::in1diag3::_Throw_NullAlloc(
                                retaddr,
                                (void *)0xBF,
                                (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\signintomsatask.cpp",
                                v23);
                            wil::details::in1diag3::Throw_Hr(
                              retaddr,
                              (void *)0xBE,
                              (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\signintomsatask.cpp",
                              (const char *)(unsigned int)v22,
                              0);
                          }
                          wil::details::in1diag3::_Throw_NullAlloc(
                            retaddr,
                            (void *)0xBA,
                            (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\signintomsatask.cpp",
                            v18);
                        }
                        wil::details::in1diag3::Throw_Hr(
                          retaddr,
                          (void *)0xB9,
                          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\signintomsatask.cpp",
                          (const char *)(unsigned int)v17,
                          v28);
                      }
                      wil::details::in1diag3::_Throw_NullAlloc(
                        retaddr,
                        (void *)0xB5,
                        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\signintomsatask.cpp",
                        v16);
                    }
                    wil::details::in1diag3::Throw_Hr(
                      retaddr,
                      (void *)0xB4,
                      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\signintomsatask.cpp",
                      (const char *)(unsigned int)v15,
                      v28);
                  }
                  wil::details::in1diag3::_Throw_NullAlloc(
                    retaddr,
                    (void *)0xB1,
                    (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\signintomsatask.cpp",
                    v13);
                }
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0xAF,
                  (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\signintomsatask.cpp",
                  (const char *)(unsigned int)v12,
                  v28);
              }
              wil::details::in1diag3::_Throw_NullAlloc(
                retaddr,
                (void *)0xAD,
                (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\signintomsatask.cpp",
                v10);
            }
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0xAC,
              (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\signintomsatask.cpp",
              (const char *)(unsigned int)DefaultSignInAccount,
              v28);
          }
          wil::details::in1diag3::_Throw_NullAlloc(
            retaddr,
            (void *)0xAA,
            (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\signintomsatask.cpp",
            v7);
        }
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xA9,
          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\signintomsatask.cpp",
          (const char *)(unsigned int)v4,
          v28);
      }
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0xA6,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\signintomsatask.cpp",
        v2);
    }
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA5,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\signintomsatask.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v28);
  }
  catch ( ... )
  {
    v25 = wil::ResultFromCaughtException(v24);
    result = v36;
    v27 = *v36;
    if ( v25 == -2147024882 )
      *v27 = -2147023579;
    else
      *v27 = v25;
  }
  return result;
}

```

## disassembly

```asm
0x180024ba4  mov     r11, rsp
0x180024ba7  mov     [r11+10h], rbx
0x180024bab  mov     [r11+18h], rsi
0x180024baf  push    rdi
0x180024bb0  push    r14
0x180024bb2  push    r15
0x180024bb4  sub     rsp, 110h
0x180024bbb  mov     rax, cs:__security_cookie
0x180024bc2  xor     rax, rsp
0x180024bc5  mov     [rsp+128h+var_20], rax
0x180024bcd  mov     r14, rcx
0x180024bd0  mov     [rsp+128h+var_88], rcx
0x180024bd8  xor     r15d, r15d
0x180024bdb  mov     [r11-90h], r15
0x180024be2  lea     r9, [r11-80h]; string
0x180024be6  lea     r8, [r11-78h]; hstringHeader
0x180024bea  lea     edx, [r15+40h]; length
0x180024bee  lea     rcx, ?RuntimeClass_Windows_Internal_Security_Authentication_Web_TokenBrokerInternal@@3QBGB; "Windows.Internal.Security.Authenticatio"...
0x180024bf5  call    cs:__imp_WindowsCreateStringReference
0x180024bfb  test    eax, eax
0x180024bfd  jns     short loc_180024C14
0x180024bff  xor     r9d, r9d; lpArguments
0x180024c02  xor     r8d, r8d; nNumberOfArguments
0x180024c05  lea     edx, [r15+1]; dwExceptionFlags
0x180024c09  mov     ecx, 0C000000Dh; dwExceptionCode
0x180024c0e  call    cs:__imp_RaiseException
0x180024c14  lea     r8, [rsp+128h+var_90]
0x180024c1c  lea     rdx, _GUID_07650a66_66ea_489d_aa90_0dabc75f3567
0x180024c23  mov     rcx, [rsp+128h+var_80]
0x180024c2b  call    cs:__imp_RoGetActivationFactory
0x180024c31  mov     rcx, [rsp+128h]; this
0x180024c39  test    eax, eax
0x180024c3b  js      loc_180025117
0x180024c41  mov     rax, [rsp+128h]
0x180024c49  mov     rcx, [rsp+128h+var_90]
0x180024c51  test    rcx, rcx
0x180024c54  jz      loc_18002512B
0x180024c5a  mov     [rsp+128h+var_B0], r15
0x180024c5f  mov     rax, [rcx]
0x180024c62  mov     [rsp+128h+var_B0], r15
0x180024c67  lea     rdx, [rsp+128h+var_B0]
0x180024c6c  mov     rax, [rax+0E8h]
0x180024c73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024c78  mov     rcx, [rsp+128h]; this
0x180024c80  test    eax, eax
0x180024c82  js      loc_180025140
0x180024c88  mov     rcx, [rsp+128h]; this
0x180024c90  mov     rbx, [rsp+128h+var_B0]
0x180024c95  test    rbx, rbx
0x180024c98  jz      loc_180025154
0x180024c9e  mov     [rsp+128h+var_98], r15
0x180024ca6  mov     rcx, rbx
0x180024ca9  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *> *,tagCOWAIT_FLAGS,void *)
0x180024cae  test    eax, eax
0x180024cb0  js      short loc_180024CC9
0x180024cb2  mov     rax, [rbx]
0x180024cb5  lea     rdx, [rsp+128h+var_98]
0x180024cbd  mov     rcx, rbx
0x180024cc0  mov     rax, [rax+40h]
0x180024cc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024cc9  mov     rcx, [rsp+128h]; this
0x180024cd1  test    eax, eax
0x180024cd3  js      loc_180025166
0x180024cd9  mov     rax, [rsp+128h]
0x180024ce1  mov     rcx, [rsp+128h+var_98]
0x180024ce9  test    rcx, rcx
0x180024cec  jz      loc_18002517A
0x180024cf2  mov     [rsp+128h+var_B8], r15
0x180024cf7  mov     rax, [rcx]
0x180024cfa  mov     [rsp+128h+var_B8], r15
0x180024cff  lea     rdx, [rsp+128h+var_B8]
0x180024d04  mov     rax, [rax+30h]
0x180024d08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d0d  mov     rcx, [rsp+128h]; this
0x180024d15  test    eax, eax
0x180024d17  js      loc_18002518F
0x180024d1d  mov     rax, [rsp+128h]
0x180024d25  mov     rcx, [rsp+128h+var_B8]
0x180024d2a  test    rcx, rcx
0x180024d2d  jz      loc_1800251A3
0x180024d33  mov     [rsp+128h+var_D8], r15
0x180024d38  mov     rax, [rcx]
0x180024d3b  mov     [rsp+128h+var_D8], r15
0x180024d40  lea     rdx, [rsp+128h+var_D8]
0x180024d45  mov     rax, [rax+30h]
0x180024d49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d4e  mov     rcx, [rsp+128h]; this
0x180024d56  test    eax, eax
0x180024d58  js      loc_1800251B8
0x180024d5e  mov     rcx, [rsp+128h]; this
0x180024d66  cmp     [rsp+128h+var_D8], r15
0x180024d6b  jz      loc_1800251CC
0x180024d71  lea     r9, [rsp+128h+string]; string
0x180024d79  lea     r8, [rsp+128h+hstringHeader]; hstringHeader
0x180024d81  mov     edx, 38h ; '8'; length
0x180024d86  lea     rcx, ?RuntimeClass_Windows_Security_Authentication_Web_Core_WebTokenRequest@@3QBGB; "Windows.Security.Authentication.Web.Cor"...
0x180024d8d  call    cs:__imp_WindowsCreateStringReference
0x180024d93  test    eax, eax
0x180024d95  jns     short loc_180024DAD
0x180024d97  xor     r9d, r9d; lpArguments
0x180024d9a  xor     r8d, r8d; nNumberOfArguments
0x180024d9d  lea     edx, [r9+1]; dwExceptionFlags
0x180024da1  mov     ecx, 0C000000Dh; dwExceptionCode
0x180024da6  call    cs:__imp_RaiseException
0x180024dac  nop
0x180024dad  mov     [rsp+128h+var_A0], r15
0x180024db5  lea     r8, [rsp+128h+var_A0]
0x180024dbd  lea     rdx, _GUID_6cf2141c_0ff0_4c67_b84f_99ddbe4a72c9
0x180024dc4  mov     rcx, [rsp+128h+string]
0x180024dcc  call    cs:__imp_RoGetActivationFactory
0x180024dd2  mov     rcx, [rsp+128h]; this
0x180024dda  test    eax, eax
0x180024ddc  js      loc_1800251DE
0x180024de2  mov     rcx, [rsp+128h]; this
0x180024dea  mov     rbx, [rsp+128h+var_A0]
0x180024df2  test    rbx, rbx
0x180024df5  jz      loc_1800251F2
0x180024dfb  mov     [rsp+128h+var_E0], r15
0x180024e00  mov     rax, [rbx]
0x180024e03  mov     rsi, [rax+38h]
0x180024e07  mov     [rsp+128h+var_E0], r15
0x180024e0c  mov     rdx, cs:off_180054C80; unsigned __int16 *
0x180024e13  lea     rcx, [rsp+128h+var_80]; this
0x180024e1b  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x180024e20  mov     rdi, [rsp+128h+var_80]
0x180024e28  mov     rdx, cs:off_180054C78; unsigned __int16 *
0x180024e2f  lea     rcx, [rsp+128h+var_40]; this
0x180024e37  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x180024e3c  lea     rax, [rsp+128h+var_E0]
0x180024e41  mov     [rsp+128h+var_100], rax
0x180024e46  mov     [rsp+128h+var_108], r15d; int
0x180024e4b  mov     r9, rdi
0x180024e4e  mov     r8, [rsp+128h+var_40]
0x180024e56  mov     rdx, [rsp+128h+var_D8]
0x180024e5b  mov     rcx, rbx
0x180024e5e  mov     rax, rsi
0x180024e61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e66  mov     rcx, [rsp+128h]; this
0x180024e6e  test    eax, eax
0x180024e70  js      loc_180025204
0x180024e76  mov     rcx, [rsp+128h]; this
0x180024e7e  cmp     [rsp+128h+var_E0], r15
0x180024e83  jz      loc_180025218
0x180024e89  mov     [rsp+128h+var_A8], r15
0x180024e91  lea     r9, [rsp+128h+var_80]; string
0x180024e99  lea     r8, [rsp+128h+var_78]; hstringHeader
0x180024ea1  mov     edx, 45h ; 'E'; length
0x180024ea6  lea     rcx, ?RuntimeClass_Windows_Security_Authentication_Web_Core_WebAuthenticationCoreManager@@3QBGB; "Windows.Security.Authentication.Web.Cor"...
0x180024ead  call    cs:__imp_WindowsCreateStringReference
0x180024eb3  test    eax, eax
0x180024eb5  jns     short loc_180024ECC
0x180024eb7  xor     r9d, r9d; lpArguments
0x180024eba  xor     r8d, r8d; nNumberOfArguments
0x180024ebd  lea     edx, [r9+1]; dwExceptionFlags
0x180024ec1  mov     ecx, 0C000000Dh; dwExceptionCode
0x180024ec6  call    cs:__imp_RaiseException
0x180024ecc  lea     r8, [rsp+128h+var_A8]
0x180024ed4  lea     rdx, _GUID_6aca7c92_a581_4479_9c10_752eff44fd34
0x180024edb  mov     rcx, [rsp+128h+var_80]
0x180024ee3  call    cs:__imp_RoGetActivationFactory
0x180024ee9  mov     rcx, [rsp+128h]; this
0x180024ef1  test    eax, eax
0x180024ef3  js      loc_18002522A
0x180024ef9  mov     rax, [rsp+128h]
0x180024f01  mov     rcx, [rsp+128h+var_A8]
0x180024f09  test    rcx, rcx
0x180024f0c  jz      loc_18002523E
0x180024f12  mov     [rsp+128h+var_C0], r15
0x180024f17  mov     rax, [rcx]
0x180024f1a  mov     [rsp+128h+var_C0], r15
0x180024f1f  lea     r8, [rsp+128h+var_C0]
0x180024f24  mov     rdx, [rsp+128h+var_E0]
0x180024f29  mov     rax, [rax+30h]
0x180024f2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f32  mov     rcx, [rsp+128h]; this
0x180024f3a  test    eax, eax
0x180024f3c  js      loc_180025253
0x180024f42  mov     rcx, [rsp+128h]; this
0x180024f4a  mov     rbx, [rsp+128h+var_C0]
0x180024f4f  test    rbx, rbx
0x180024f52  jz      loc_180025267
0x180024f58  mov     [rsp+128h+var_C8], r15
0x180024f5d  mov     rcx, rbx
0x180024f60  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,void *)
0x180024f65  test    eax, eax
0x180024f67  js      short loc_180024F7D
0x180024f69  mov     rax, [rbx]
0x180024f6c  lea     rdx, [rsp+128h+var_C8]
0x180024f71  mov     rcx, rbx
0x180024f74  mov     rax, [rax+40h]
0x180024f78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f7d  mov     rcx, [rsp+128h]; this
0x180024f85  test    eax, eax
0x180024f87  js      loc_180025279
0x180024f8d  mov     rax, [rsp+128h]
0x180024f95  mov     rcx, [rsp+128h+var_C8]
0x180024f9a  test    rcx, rcx
0x180024f9d  jz      loc_18002528D
0x180024fa3  mov     [rsp+128h+var_E8], r15d
0x180024fa8  mov     rax, [rcx]
0x180024fab  lea     rdx, [rsp+128h+var_E8]
0x180024fb0  mov     rax, [rax+38h]
0x180024fb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024fb9  mov     rcx, [rsp+128h]; this
0x180024fc1  test    eax, eax
0x180024fc3  js      loc_1800252A1
0x180024fc9  mov     eax, [rsp+128h+var_E8]
0x180024fcd  add     eax, 0FFFFFFFDh
0x180024fd0  test    eax, 0FFFFFFFDh
0x180024fd5  jnz     loc_180025074
0x180024fdb  mov     [rsp+128h+var_D0], r15
0x180024fe0  mov     rcx, [rsp+128h+var_C8]
0x180024fe5  mov     rax, [rcx]
0x180024fe8  lea     rdx, [rsp+128h+var_D0]
0x180024fed  mov     rax, [rax+40h]
0x180024ff1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ff6  mov     rcx, [rsp+128h]; this
0x180024ffe  test    eax, eax
0x180025000  js      loc_1800252B6
0x180025006  mov     rax, [rsp+128h]
0x18002500e  mov     rcx, [rsp+128h+var_D0]
0x180025013  test    rcx, rcx
0x180025016  jz      loc_1800252CA
0x18002501c  mov     [rsp+128h+var_E4], r15d
0x180025021  mov     rax, [rcx]
0x180025024  lea     rdx, [rsp+128h+var_E4]
0x180025029  mov     rax, [rax+30h]
0x18002502d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025032  mov     rcx, [rsp+128h]; this
0x18002503a  test    eax, eax
0x18002503c  js      loc_1800252DE
0x180025042  mov     ecx, [rsp+128h+var_E4]
0x180025046  test    ecx, ecx
0x180025048  jle     short loc_180025053
0x18002504a  movzx   ecx, cx
0x18002504d  or      ecx, 80070000h
0x180025053  mov     rax, [r14]
0x180025056  mov     [rax], ecx
0x180025058  mov     rcx, [rsp+128h+var_D0]
0x18002505d  test    rcx, rcx
0x180025060  jz      short loc_180025074
0x180025062  mov     [rsp+128h+var_D0], r15
0x180025067  mov     rax, [rcx]
0x18002506a  mov     rax, [rax+10h]
0x18002506e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025073  nop
0x180025074  lea     rcx, [rsp+128h+var_C8]
0x180025079  call    ??1?$com_ptr_t@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(void)
0x18002507e  nop
0x18002507f  lea     rcx, [rsp+128h+var_C0]
0x180025084  call    ??1?$com_ptr_t@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(void)
0x180025089  nop
0x18002508a  lea     rcx, [rsp+128h+var_A8]
0x180025092  call    ??1?$com_ptr_t@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(void)
0x180025097  nop
0x180025098  lea     rcx, [rsp+128h+var_E0]
0x18002509d  call    ??1?$com_ptr_t@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(void)
0x1800250a2  nop
0x1800250a3  lea     rcx, [rsp+128h+var_A0]
0x1800250ab  call    ??1?$com_ptr_t@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(void)
0x1800250b0  nop
0x1800250b1  lea     rcx, [rsp+128h+var_D8]
0x1800250b6  call    ??1?$com_ptr_t@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(void)
0x1800250bb  nop
0x1800250bc  lea     rcx, [rsp+128h+var_B8]
0x1800250c1  call    ??1?$com_ptr_t@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(void)
0x1800250c6  nop
0x1800250c7  lea     rcx, [rsp+128h+var_98]
0x1800250cf  call    ??1?$com_ptr_t@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(void)
0x1800250d4  nop
0x1800250d5  lea     rcx, [rsp+128h+var_B0]
0x1800250da  call    ??1?$com_ptr_t@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(void)
0x1800250df  nop
0x1800250e0  lea     rcx, [rsp+128h+var_90]
0x1800250e8  call    ??1?$com_ptr_t@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(void)
0x1800250ed  nop
0x1800250ee  mov     rcx, [rsp+128h+var_20]
0x1800250f6  xor     rcx, rsp; StackCookie
0x1800250f9  call    __security_check_cookie
0x1800250fe  lea     r11, [rsp+128h+var_18]
0x180025106  mov     rbx, [r11+28h]
0x18002510a  mov     rsi, [r11+30h]
0x18002510e  mov     rsp, r11
0x180025111  pop     r15
0x180025113  pop     r14
0x180025115  pop     rdi
0x180025116  retn
0x180025117  mov     r9d, eax; char *
0x18002511a  lea     r8, aPcshellShellRe_18; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180025121  mov     edx, 0A5h; void *
0x180025126  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002512b  lea     r8, aPcshellShellRe_18; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180025132  mov     edx, 0A6h; void *
0x180025137  mov     rcx, rax; this
0x18002513a  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180025140  mov     r9d, eax; char *
0x180025143  lea     r8, aPcshellShellRe_18; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002514a  mov     edx, 0A9h; void *
0x18002514f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180025154  lea     r8, aPcshellShellRe_18; "pcshell\\shell\\retaildemo\\desktoptask"...
  ... truncated ...
```
