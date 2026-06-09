# DeleteAWAAccount(ushort const *,ushort const *)

- ea: `0x1400337d8`
- end: `0x140033b11`
- name: `?DeleteAWAAccount@@YAJPEBG0@Z`
- size: `825`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140019a6c`
- `0x140033dd0`

## callees

- `0x1400042f0`
- `0x140008a40`
- `0x14000b84c`
- `0x140033450`
- `0x1400337d8`
- `0x14005d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140033845`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14003388f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1400339a1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140033845`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14003388f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1400339a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140033817`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140033858`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140033876`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140033988`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140033817`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140033858`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140033876`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140033988`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1400338c0`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1400339d2`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1400338c0`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1400339d2`

## string_xrefs

- `0x14003386f`: `Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager`
- `0x140033981`: `Windows.Internal.Security.Authentication.Web.TokenBrokerInternal`

## pseudocode

```c
__int64 __fastcall DeleteAWAAccount(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  unsigned __int64 v3; // rbx
  int ActivationFactory; // eax
  __int64 v5; // rcx
  int v6; // ebx
  void (*v7)(void); // rax
  HRESULT v9; // edx
  __int64 v10; // r8
  int (__fastcall ***v11)(_QWORD, GUID *, __int64 *); // rcx
  void (*v12)(void); // rax
  __int64 v13; // rcx
  int (__fastcall ***v14)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v15; // rcx
  HSTRING v16; // rbx
  int v17; // eax
  __int64 v18; // rcx
  void (*v19)(void); // rax
  __int64 v20; // rcx
  void (*v21)(void); // rax
  __int64 v22; // rdi
  __int64 (__fastcall *v23)(__int64, __int64, _QWORD); // rbx
  __int64 v24; // r8
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  int (__fastcall ***v28)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v29; // [rsp+30h] [rbp-69h] BYREF
  int (__fastcall ***v30)(_QWORD, GUID *, __int64 *); // [rsp+38h] [rbp-61h] BYREF
  __int64 v31; // [rsp+40h] [rbp-59h] BYREF
  __int64 v32; // [rsp+48h] [rbp-51h] BYREF
  __int64 v33; // [rsp+50h] [rbp-49h] BYREF
  int (__fastcall ***v34)(_QWORD, GUID *, __int64 *); // [rsp+58h] [rbp-41h] BYREF
  HSTRING v35; // [rsp+60h] [rbp-39h] BYREF
  HSTRING_HEADER v36; // [rsp+68h] [rbp-31h] BYREF
  HSTRING string; // [rsp+80h] [rbp-19h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+88h] [rbp-11h] BYREF
  HSTRING v39; // [rsp+A0h] [rbp+7h] BYREF
  HSTRING_HEADER v40; // [rsp+A8h] [rbp+Fh] BYREF

  if ( a2 )
  {
    WindowsCreateStringReference(L"https://login.windows.net", 0x19u, &hstringHeader, &string);
    v3 = -1;
    do
      ++v3;
    while ( a2[v3] );
    if ( v3 > 0xFFFFFFFF )
    {
      LODWORD(v3) = -1;
      RaiseException(0xC000000D, 1u, 0, 0);
    }
    WindowsCreateStringReference(a2, v3, &v40, &v39);
    v29 = 0;
    if ( WindowsCreateStringReference(
           L"Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager",
           0x45u,
           &v36,
           &v35) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    ActivationFactory = RoGetActivationFactory(v35, &GUID_6aca7c92_a581_4479_9c10_752eff44fd34, &v29);
    v5 = v29;
    v6 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      if ( !v29 )
        return (unsigned int)v6;
      v29 = 0;
      v7 = *(void (**)(void))(*(_QWORD *)v5 + 16LL);
LABEL_11:
      v7();
      return (unsigned int)v6;
    }
    v30 = 0;
    v6 = (*(__int64 (__fastcall **)(__int64, HSTRING, _QWORD))(*(_QWORD *)v29 + 88LL))(v29, string, &v30);
    if ( v6 < 0 )
    {
      v11 = v30;
      if ( !v30 )
      {
LABEL_17:
        v13 = v29;
        if ( !v29 )
          return (unsigned int)v6;
        v29 = 0;
        v7 = *(void (**)(void))(*(_QWORD *)v13 + 16LL);
        goto LABEL_11;
      }
      v30 = 0;
      v12 = (void (*)(void))(*v11)[2];
LABEL_16:
      v12();
      goto LABEL_17;
    }
    v14 = v30;
    v32 = 0;
    v6 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(
           v30,
           v9,
           v10);
    if ( v6 < 0 )
      goto LABEL_40;
    v6 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64 *))(*v14)[8])(v14, &v32);
    if ( v6 < 0 )
      goto LABEL_40;
    v31 = 0;
    if ( WindowsCreateStringReference(
           L"Windows.Internal.Security.Authentication.Web.TokenBrokerInternal",
           0x40u,
           &v36,
           &v35) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v15 = v31;
    v16 = v35;
    if ( v31 )
    {
      v31 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
    v17 = RoGetActivationFactory(v16, &GUID_07650a66_66ea_489d_aa90_0dabc75f3567, &v31);
    v18 = v31;
    v6 = v17;
    if ( v17 < 0 )
    {
      if ( v31 )
      {
        v31 = 0;
        v19 = *(void (**)(void))(*(_QWORD *)v18 + 16LL);
LABEL_39:
        v19();
        goto LABEL_40;
      }
      goto LABEL_40;
    }
    v33 = 0;
    v6 = (*(__int64 (__fastcall **)(__int64, __int64, HSTRING, __int64 *))(*(_QWORD *)v31 + 72LL))(v31, v32, v39, &v33);
    if ( v6 >= 0 )
    {
      v22 = v31;
      v34 = 0;
      v23 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v31 + 120LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncAction>::InternalRelease(&v34);
      v6 = v23(v22, v33, &v34);
      if ( v6 >= 0 )
      {
        v6 = WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(
               v34,
               8u,
               v24);
        if ( v6 >= 0 )
        {
          Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncAction>::InternalRelease(&v34);
          v25 = v33;
          if ( !v33 )
            goto LABEL_37;
          v33 = 0;
          v21 = *(void (**)(void))(*(_QWORD *)v25 + 16LL);
LABEL_36:
          v21();
LABEL_37:
          v26 = v31;
          if ( v31 )
          {
            v31 = 0;
            v19 = *(void (**)(void))(*(_QWORD *)v26 + 16LL);
            goto LABEL_39;
          }
LABEL_40:
          v27 = v32;
          if ( v32 )
          {
            v32 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
          }
          v28 = v30;
          if ( !v30 )
            goto LABEL_17;
          v30 = 0;
          v12 = (void (*)(void))(*v28)[2];
          goto LABEL_16;
        }
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncAction>::InternalRelease(&v34);
    }
    v20 = v33;
    if ( !v33 )
      goto LABEL_37;
    v33 = 0;
    v21 = *(void (**)(void))(*(_QWORD *)v20 + 16LL);
    goto LABEL_36;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x1400337d8  push    rbp
0x1400337da  push    rbx
0x1400337db  push    rsi
0x1400337dc  push    rdi
0x1400337dd  lea     rbp, [rsp-3Fh]
0x1400337e2  sub     rsp, 0D8h
0x1400337e9  mov     rax, cs:__security_cookie
0x1400337f0  xor     rax, rsp
0x1400337f3  mov     [rbp+57h+var_30], rax
0x1400337f7  xor     esi, esi
0x1400337f9  mov     rdi, rdx
0x1400337fc  test    rdx, rdx
0x1400337ff  jz      loc_140033AF4
0x140033805  lea     r9, [rbp+57h+string]; string
0x140033809  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x14003380d  lea     edx, [rsi+19h]; length
0x140033810  lea     rcx, aHttpsLoginWind; "https://login.windows.net"
0x140033817  call    cs:__imp_WindowsCreateStringReference
0x14003381d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140033821  inc     rbx
0x140033824  cmp     [rdi+rbx*2], si
0x140033828  jnz     short loc_140033821
0x14003382a  mov     eax, 0FFFFFFFFh
0x14003382f  cmp     rbx, rax
0x140033832  jbe     short loc_14003384B
0x140033834  xor     r9d, r9d; lpArguments
0x140033837  xor     r8d, r8d; nNumberOfArguments
0x14003383a  mov     ecx, 0C000000Dh; dwExceptionCode
0x14003383f  mov     ebx, eax
0x140033841  lea     edx, [r9+1]; dwExceptionFlags
0x140033845  call    cs:__imp_RaiseException
0x14003384b  lea     r9, [rbp+57h+var_50]; string
0x14003384f  mov     edx, ebx; length
0x140033851  lea     r8, [rbp+57h+var_48]; hstringHeader
0x140033855  mov     rcx, rdi; sourceString
0x140033858  call    cs:__imp_WindowsCreateStringReference
0x14003385e  lea     r9, [rbp+57h+var_90]; string
0x140033862  mov     [rbp+57h+var_C0], rsi
0x140033866  lea     r8, [rbp+57h+var_88]; hstringHeader
0x14003386a  mov     edx, 45h ; 'E'; length
0x14003386f  lea     rcx, ?RuntimeClass_Windows_Security_Authentication_Web_Core_WebAuthenticationCoreManager@@3QBGB; "Windows.Security.Authentication.Web.Cor"...
0x140033876  call    cs:__imp_WindowsCreateStringReference
0x14003387c  test    eax, eax
0x14003387e  jns     short loc_140033895
0x140033880  xor     r9d, r9d; lpArguments
0x140033883  xor     r8d, r8d; nNumberOfArguments
0x140033886  mov     ecx, 0C000000Dh; dwExceptionCode
0x14003388b  lea     edx, [r9+1]; dwExceptionFlags
0x14003388f  call    cs:__imp_RaiseException
0x140033895  mov     rcx, [rbp+57h+var_C0]
0x140033899  mov     rbx, [rbp+57h+var_90]
0x14003389d  test    rcx, rcx
0x1400338a0  jz      short loc_1400338B2
0x1400338a2  mov     [rbp+57h+var_C0], rsi
0x1400338a6  mov     rax, [rcx]
0x1400338a9  mov     rax, [rax+10h]
0x1400338ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400338b2  lea     r8, [rbp+57h+var_C0]
0x1400338b6  mov     rcx, rbx
0x1400338b9  lea     rdx, _GUID_6aca7c92_a581_4479_9c10_752eff44fd34
0x1400338c0  call    cs:__imp_RoGetActivationFactory
0x1400338c6  mov     rcx, [rbp+57h+var_C0]
0x1400338ca  mov     ebx, eax
0x1400338cc  test    eax, eax
0x1400338ce  jns     short loc_1400338EC
0x1400338d0  test    rcx, rcx
0x1400338d3  jz      short loc_1400338E5
0x1400338d5  mov     [rbp+57h+var_C0], rsi
0x1400338d9  mov     rdx, [rcx]
0x1400338dc  mov     rax, [rdx+10h]
0x1400338e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400338e5  mov     eax, ebx
0x1400338e7  jmp     loc_140033AF9
0x1400338ec  mov     rdx, [rbp+57h+string]
0x1400338f0  lea     r8, [rbp+57h+var_B8]
0x1400338f4  mov     [rbp+57h+var_B8], rsi
0x1400338f8  mov     rax, [rcx]
0x1400338fb  mov     rax, [rax+58h]
0x1400338ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140033904  mov     ebx, eax
0x140033906  test    eax, eax
0x140033908  jns     short loc_140033939
0x14003390a  mov     rcx, [rbp+57h+var_B8]
0x14003390e  test    rcx, rcx
0x140033911  jz      short loc_140033923
0x140033913  mov     [rbp+57h+var_B8], rsi
0x140033917  mov     rdx, [rcx]
0x14003391a  mov     rax, [rdx+10h]
0x14003391e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140033923  mov     rcx, [rbp+57h+var_C0]
0x140033927  test    rcx, rcx
0x14003392a  jz      short loc_1400338E5
0x14003392c  mov     [rbp+57h+var_C0], rsi
0x140033930  mov     rax, [rcx]
0x140033933  mov     rax, [rax+10h]
0x140033937  jmp     short loc_1400338E0
0x140033939  mov     rdi, [rbp+57h+var_B8]
0x14003393d  mov     rcx, rdi
0x140033940  mov     [rbp+57h+var_A8], rsi
0x140033944  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,tagCOWAIT_FLAGS,void *)
0x140033949  mov     ebx, eax
0x14003394b  test    eax, eax
0x14003394d  js      loc_140033ABE
0x140033953  mov     rax, [rdi]
0x140033956  lea     rdx, [rbp+57h+var_A8]
0x14003395a  mov     rcx, rdi
0x14003395d  mov     rax, [rax+40h]
0x140033961  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140033966  mov     ebx, eax
0x140033968  test    eax, eax
0x14003396a  js      loc_140033ABE
0x140033970  lea     r9, [rbp+57h+var_90]; string
0x140033974  mov     [rbp+57h+var_B0], rsi
0x140033978  lea     r8, [rbp+57h+var_88]; hstringHeader
0x14003397c  mov     edx, 40h ; '@'; length
0x140033981  lea     rcx, ?RuntimeClass_Windows_Internal_Security_Authentication_Web_TokenBrokerInternal@@3QBGB; "Windows.Internal.Security.Authenticatio"...
0x140033988  call    cs:__imp_WindowsCreateStringReference
0x14003398e  test    eax, eax
0x140033990  jns     short loc_1400339A7
0x140033992  xor     r9d, r9d; lpArguments
0x140033995  xor     r8d, r8d; nNumberOfArguments
0x140033998  mov     ecx, 0C000000Dh; dwExceptionCode
0x14003399d  lea     edx, [r9+1]; dwExceptionFlags
0x1400339a1  call    cs:__imp_RaiseException
0x1400339a7  mov     rcx, [rbp+57h+var_B0]
0x1400339ab  mov     rbx, [rbp+57h+var_90]
0x1400339af  test    rcx, rcx
0x1400339b2  jz      short loc_1400339C4
0x1400339b4  mov     [rbp+57h+var_B0], rsi
0x1400339b8  mov     rax, [rcx]
0x1400339bb  mov     rax, [rax+10h]
0x1400339bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400339c4  lea     r8, [rbp+57h+var_B0]
0x1400339c8  mov     rcx, rbx
0x1400339cb  lea     rdx, _GUID_07650a66_66ea_489d_aa90_0dabc75f3567
0x1400339d2  call    cs:__imp_RoGetActivationFactory
0x1400339d8  mov     rcx, [rbp+57h+var_B0]
0x1400339dc  mov     ebx, eax
0x1400339de  test    eax, eax
0x1400339e0  jns     short loc_1400339FB
0x1400339e2  test    rcx, rcx
0x1400339e5  jz      loc_140033ABE
0x1400339eb  mov     [rbp+57h+var_B0], rsi
0x1400339ef  mov     rdx, [rcx]
0x1400339f2  mov     rax, [rdx+10h]
0x1400339f6  jmp     loc_140033AB9
0x1400339fb  mov     r8, [rbp+57h+var_50]
0x1400339ff  lea     r9, [rbp+57h+var_A0]
0x140033a03  mov     rdx, [rbp+57h+var_A8]
0x140033a07  mov     [rbp+57h+var_A0], rsi
0x140033a0b  mov     rax, [rcx]
0x140033a0e  mov     rax, [rax+48h]
0x140033a12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140033a17  mov     ebx, eax
0x140033a19  test    eax, eax
0x140033a1b  jns     short loc_140033A33
0x140033a1d  mov     rcx, [rbp+57h+var_A0]
0x140033a21  test    rcx, rcx
0x140033a24  jz      short loc_140033AA5
0x140033a26  mov     [rbp+57h+var_A0], rsi
0x140033a2a  mov     rdx, [rcx]
0x140033a2d  mov     rax, [rdx+10h]
0x140033a31  jmp     short loc_140033AA0
0x140033a33  mov     rdi, [rbp+57h+var_B0]
0x140033a37  lea     rcx, [rbp+57h+var_98]
0x140033a3b  mov     [rbp+57h+var_98], rsi
0x140033a3f  mov     rax, [rdi]
0x140033a42  mov     rbx, [rax+78h]
0x140033a46  call    ?InternalRelease@?$ComPtr@UIAsyncAction@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncAction>::InternalRelease(void)
0x140033a4b  mov     rdx, [rbp+57h+var_A0]
0x140033a4f  lea     r8, [rbp+57h+var_98]
0x140033a53  mov     rcx, rdi
0x140033a56  mov     rax, rbx
0x140033a59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140033a5e  mov     ebx, eax
0x140033a60  test    eax, eax
0x140033a62  jns     short loc_140033A6F
0x140033a64  lea     rcx, [rbp+57h+var_98]
0x140033a68  call    ?InternalRelease@?$ComPtr@UIAsyncAction@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncAction>::InternalRelease(void)
0x140033a6d  jmp     short loc_140033A1D
0x140033a6f  mov     rcx, [rbp+57h+var_98]
0x140033a73  mov     edx, 8
0x140033a78  call    ??$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)
0x140033a7d  lea     rcx, [rbp+57h+var_98]
0x140033a81  mov     ebx, eax
0x140033a83  test    eax, eax
0x140033a85  js      short loc_140033A68
0x140033a87  call    ?InternalRelease@?$ComPtr@UIAsyncAction@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncAction>::InternalRelease(void)
0x140033a8c  mov     rcx, [rbp+57h+var_A0]
0x140033a90  test    rcx, rcx
0x140033a93  jz      short loc_140033AA5
0x140033a95  mov     [rbp+57h+var_A0], rsi
0x140033a99  mov     rax, [rcx]
0x140033a9c  mov     rax, [rax+10h]
0x140033aa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140033aa5  mov     rcx, [rbp+57h+var_B0]
0x140033aa9  test    rcx, rcx
0x140033aac  jz      short loc_140033ABE
0x140033aae  mov     [rbp+57h+var_B0], rsi
0x140033ab2  mov     rax, [rcx]
0x140033ab5  mov     rax, [rax+10h]
0x140033ab9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140033abe  mov     rcx, [rbp+57h+var_A8]
0x140033ac2  test    rcx, rcx
0x140033ac5  jz      short loc_140033AD7
0x140033ac7  mov     [rbp+57h+var_A8], rsi
0x140033acb  mov     rax, [rcx]
0x140033ace  mov     rax, [rax+10h]
0x140033ad2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140033ad7  mov     rcx, [rbp+57h+var_B8]
0x140033adb  test    rcx, rcx
0x140033ade  jz      loc_140033923
0x140033ae4  mov     [rbp+57h+var_B8], rsi
0x140033ae8  mov     rax, [rcx]
0x140033aeb  mov     rax, [rax+10h]
0x140033aef  jmp     loc_14003391E
0x140033af4  mov     eax, 80070057h
0x140033af9  mov     rcx, [rbp+57h+var_30]
0x140033afd  xor     rcx, rsp; StackCookie
0x140033b00  call    __security_check_cookie
0x140033b05  add     rsp, 0D8h
0x140033b0c  pop     rdi
0x140033b0d  pop     rsi
0x140033b0e  pop     rbx
0x140033b0f  pop     rbp
0x140033b10  retn
```
