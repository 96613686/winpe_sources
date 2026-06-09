# CloudServiceAccountProvider::_GetWebAccountProvider(ushort const *,ushort const *,Windows::Security::Credentials::IWebAccountProvider * *)

- ea: `0x18008de94`
- end: `0x18008e1c0`
- name: `?_GetWebAccountProvider@CloudServiceAccountProvider@@AEAAJPEBG0PEAPEAUIWebAccountProvider@Credentials@Security@Windows@@@Z`
- size: `812`
- prototype: `__int64 __fastcall(CloudServiceAccountProvider *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct Windows::Security::Credentials::IWebAccountProvider **)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18008e1d0`

## callees

- `0x18002cf18`
- `0x180030bd0`
- `0x18006b108`
- `0x180084738`
- `0x18008b3c8`
- `0x18008c530`
- `0x18008de94`
- `0x1800c6940`
- `0x1800c8010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18008e0b6`
- `msvcrt!_wcsicmp` at `0x18008e0b6`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18008df07`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18008df07`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008e0aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008e0aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e063`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e098`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e0d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e063`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e098`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e0d4`

## string_xrefs

- `0x18008ded8`: `Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager`

## pseudocode

```c
__int64 __fastcall CloudServiceAccountProvider::_GetWebAccountProvider(
        CloudServiceAccountProvider *this,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct Windows::Security::Credentials::IWebAccountProvider **a4)
{
  int ActivationFactory; // eax
  char v6; // r8
  int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // rsi
  __int64 (__fastcall *v10)(__int64, PVOID, PVOID, int (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rdi
  PVOID Reserved1; // rbx
  char v12; // r8
  HSTRING_HEADER *v13; // rax
  int v14; // eax
  int (__fastcall ***v15)(_QWORD, GUID *, __int64 *); // rdx
  int (__fastcall ***v16)(_QWORD, GUID *, __int64 *); // rdi
  struct Windows::Security::Credentials::IWebAccountProvider *v17; // rdi
  __int64 (__fastcall *v18)(struct Windows::Security::Credentials::IWebAccountProvider *, GUID *, const WCHAR **); // rbx
  int v19; // eax
  const WCHAR *v20; // rdi
  __int64 (__fastcall *v21)(const WCHAR *, HSTRING *); // rbx
  int v22; // eax
  const wchar_t *StringRawBuffer; // rax
  struct Windows::Security::Credentials::IWebAccountProvider *v24; // rdi
  int (__fastcall ***v25)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v26; // rcx
  struct Windows::Security::Credentials::IWebAccountProvider *v28; // rcx
  int (__fastcall ***v29)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v30; // rcx
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-39h] BYREF
  __int64 v32; // [rsp+48h] [rbp-21h]
  HSTRING_HEADER v33; // [rsp+50h] [rbp-19h] BYREF
  HSTRING string; // [rsp+70h] [rbp+7h] BYREF
  const WCHAR *v35; // [rsp+78h] [rbp+Fh] BYREF
  __int64 v36; // [rsp+80h] [rbp+17h] BYREF
  struct Windows::Security::Credentials::IWebAccountProvider *v37; // [rsp+88h] [rbp+1Fh] BYREF
  int (__fastcall ***v38)(_QWORD, GUID *, __int64 *); // [rsp+90h] [rbp+27h] BYREF

  string = (HSTRING)a2;
  *a4 = 0;
  v36 = 0;
  v35 = L"consumers";
  v32 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager",
    0x46u,
    0x45u);
  ActivationFactory = RoGetActivationFactory(v32, &GUID_6aca7c92_a581_4479_9c10_752eff44fd34, &v36);
  v7 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    Log_HREvent_65(ActivationFactory);
    v8 = v36;
    if ( v36 )
    {
      v36 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
    return (unsigned int)v7;
  }
  v9 = v36;
  v38 = 0;
  v10 = *(__int64 (__fastcall **)(__int64, PVOID, PVOID, int (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v36 + 96LL);
  Reserved1 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v35, v6)[1].Reserved.Reserved1;
  v13 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v33, (const WCHAR **)&string, v12);
  v14 = v10(v9, v13[1].Reserved.Reserved1, Reserved1, &v38);
  v7 = v14;
  if ( v14 < 0 )
  {
    Log_HREvent_65(v14);
    v15 = v38;
    if ( v38 )
    {
      v38 = 0;
      ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v15)[2])(v15);
    }
LABEL_29:
    v30 = v36;
    if ( v36 )
    {
      v36 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    }
    return (unsigned int)v7;
  }
  v16 = v38;
  v37 = 0;
  v7 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(v38);
  if ( v7 < 0
    || (v7 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), struct Windows::Security::Credentials::IWebAccountProvider **))(*v16)[8])(
               v16,
               &v37),
        v7 < 0) )
  {
    Log_HREvent_65(v7);
    goto LABEL_25;
  }
  v17 = v37;
  if ( v37 )
  {
    v35 = 0;
    v18 = **(__int64 (__fastcall ***)(struct Windows::Security::Credentials::IWebAccountProvider *, GUID *, const WCHAR **))v37;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
    v19 = v18(v17, &GUID_4a01eb05_4e42_41d4_b518_e008a5163614, &v35);
    v7 = v19;
    if ( v19 < 0 )
    {
      Log_HREvent_65(v19);
LABEL_12:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
LABEL_25:
      v28 = v37;
      if ( v37 )
      {
        v37 = 0;
        (*(void (__fastcall **)(struct Windows::Security::Credentials::IWebAccountProvider *))(*(_QWORD *)v28 + 16LL))(v28);
      }
      v29 = v38;
      if ( v38 )
      {
        v38 = 0;
        ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v29)[2])(v29);
      }
      goto LABEL_29;
    }
    v20 = v35;
    string = 0;
    v21 = *(__int64 (__fastcall **)(const WCHAR *, HSTRING *))(*(_QWORD *)v35 + 56LL);
    WindowsDeleteString(0);
    string = 0;
    v22 = v21(v20, &string);
    v7 = v22;
    if ( v22 < 0 )
    {
      Log_HREvent_65(v22);
      WindowsDeleteString(string);
      string = 0;
      goto LABEL_12;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    if ( !_wcsicmp(L"consumers", StringRawBuffer) )
    {
      Microsoft::WRL::ComPtr<Windows::Phone::Restricted::Cellular::Rcs::IImsClientWatcher>::InternalAddRef(&v37);
      *a4 = v37;
    }
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
    v24 = v37;
    if ( v37 )
    {
      v37 = 0;
      (*(void (__fastcall **)(struct Windows::Security::Credentials::IWebAccountProvider *))(*(_QWORD *)v24 + 16LL))(v24);
    }
  }
  v25 = v38;
  if ( v38 )
  {
    v38 = 0;
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v25)[2])(v25);
  }
  v26 = v36;
  if ( v36 )
  {
    v36 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  }
  return 0;
}

```

## disassembly

```asm
0x18008de94  mov     [rsp-8+arg_0], rbx
0x18008de99  mov     [rsp-8+arg_10], rsi
0x18008de9e  push    rbp
0x18008de9f  push    rdi
0x18008dea0  push    r12
0x18008dea2  push    r14
0x18008dea4  push    r15
0x18008dea6  lea     rbp, [rsp-37h]
0x18008deab  sub     rsp, 0A0h
0x18008deb2  mov     rax, cs:__security_cookie
0x18008deb9  xor     rax, rsp
0x18008debc  mov     [rbp+57h+var_28], rax
0x18008dec0  xor     r15d, r15d
0x18008dec3  mov     [rbp+57h+string], rdx
0x18008dec7  mov     r14, r9
0x18008deca  mov     [r9], r15
0x18008decd  lea     r12, aConsumers; "consumers"
0x18008ded4  mov     [rbp+57h+var_40], r15
0x18008ded8  lea     rdx, ?RuntimeClass_Windows_Security_Authentication_Web_Core_WebAuthenticationCoreManager@@3QBGB; "Windows.Security.Authentication.Web.Cor"...
0x18008dedf  mov     [rbp+57h+var_48], r12
0x18008dee3  lea     r9d, [r15+45h]; unsigned int
0x18008dee7  mov     [rbp+57h+var_78], r15
0x18008deeb  lea     r8d, [r15+46h]; unsigned int
0x18008deef  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18008def3  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18008def8  mov     rcx, [rbp+57h+var_78]
0x18008defc  lea     r8, [rbp+57h+var_40]
0x18008df00  lea     rdx, _GUID_6aca7c92_a581_4479_9c10_752eff44fd34
0x18008df07  call    cs:__imp_RoGetActivationFactory
0x18008df0d  mov     ebx, eax
0x18008df0f  test    eax, eax
0x18008df11  jns     short loc_18008DF44
0x18008df13  lea     edx, [r15+1]
0x18008df17  mov     r9d, 82h
0x18008df1d  mov     ecx, eax; int
0x18008df1f  call    Log_HREvent_65
0x18008df24  mov     rdx, [rbp+57h+var_40]
0x18008df28  test    rdx, rdx
0x18008df2b  jz      loc_18008E196
0x18008df31  mov     [rbp+57h+var_40], r15
0x18008df35  mov     rcx, [rdx]
0x18008df38  mov     rax, [rcx+10h]
0x18008df3c  mov     rcx, rdx
0x18008df3f  jmp     loc_18008E191
0x18008df44  mov     rsi, [rbp+57h+var_40]
0x18008df48  lea     rdx, [rbp+57h+var_48]
0x18008df4c  mov     [rbp+57h+var_30], r15
0x18008df50  lea     rcx, [rbp+57h+hstringHeader]
0x18008df54  mov     rax, [rsi]
0x18008df57  mov     rdi, [rax+60h]
0x18008df5b  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18008df60  lea     rdx, [rbp+57h+string]
0x18008df64  lea     rcx, [rbp+57h+var_70]
0x18008df68  mov     rbx, [rax+18h]
0x18008df6c  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18008df71  lea     r9, [rbp+57h+var_30]
0x18008df75  mov     r8, rbx
0x18008df78  mov     rcx, rsi
0x18008df7b  mov     rdx, [rax+18h]
0x18008df7f  mov     rax, rdi
0x18008df82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008df87  mov     ebx, eax
0x18008df89  test    eax, eax
0x18008df8b  jns     short loc_18008DFBF
0x18008df8d  mov     edx, 1
0x18008df92  mov     r9d, 86h
0x18008df98  mov     ecx, eax; int
0x18008df9a  call    Log_HREvent_65
0x18008df9f  mov     rdx, [rbp+57h+var_30]
0x18008dfa3  test    rdx, rdx
0x18008dfa6  jz      loc_18008E17D
0x18008dfac  mov     [rbp+57h+var_30], r15
0x18008dfb0  mov     rcx, [rdx]
0x18008dfb3  mov     rax, [rcx+10h]
0x18008dfb7  mov     rcx, rdx
0x18008dfba  jmp     loc_18008E178
0x18008dfbf  mov     rdi, [rbp+57h+var_30]
0x18008dfc3  mov     rcx, rdi
0x18008dfc6  mov     [rbp+57h+var_38], r15
0x18008dfca  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,tagCOWAIT_FLAGS,void *)
0x18008dfcf  mov     ebx, eax
0x18008dfd1  test    eax, eax
0x18008dfd3  js      loc_18008E139
0x18008dfd9  mov     rax, [rdi]
0x18008dfdc  lea     rdx, [rbp+57h+var_38]
0x18008dfe0  mov     rcx, rdi
0x18008dfe3  mov     rax, [rax+40h]
0x18008dfe7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008dfec  mov     ebx, eax
0x18008dfee  test    eax, eax
0x18008dff0  js      loc_18008E139
0x18008dff6  mov     rdi, [rbp+57h+var_38]
0x18008dffa  test    rdi, rdi
0x18008dffd  jz      loc_18008E103
0x18008e003  mov     [rbp+57h+var_48], r15
0x18008e007  lea     rcx, [rbp+57h+var_48]
0x18008e00b  mov     rax, [rdi]
0x18008e00e  mov     rbx, [rax]
0x18008e011  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18008e016  lea     r8, [rbp+57h+var_48]
0x18008e01a  mov     rcx, rdi
0x18008e01d  lea     rdx, _GUID_4a01eb05_4e42_41d4_b518_e008a5163614
0x18008e024  mov     rax, rbx
0x18008e027  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e02c  mov     ebx, eax
0x18008e02e  test    eax, eax
0x18008e030  jns     short loc_18008E052
0x18008e032  mov     edx, 1
0x18008e037  mov     r9d, 8Eh
0x18008e03d  mov     ecx, eax; int
0x18008e03f  call    Log_HREvent_65
0x18008e044  lea     rcx, [rbp+57h+var_48]
0x18008e048  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18008e04d  jmp     loc_18008E14B
0x18008e052  mov     rdi, [rbp+57h+var_48]
0x18008e056  xor     ecx, ecx; string
0x18008e058  mov     [rbp+57h+string], r15
0x18008e05c  mov     rax, [rdi]
0x18008e05f  mov     rbx, [rax+38h]
0x18008e063  call    cs:__imp_WindowsDeleteString
0x18008e069  lea     rdx, [rbp+57h+string]
0x18008e06d  mov     [rbp+57h+string], r15
0x18008e071  mov     rcx, rdi
0x18008e074  mov     rax, rbx
0x18008e077  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e07c  mov     ebx, eax
0x18008e07e  test    eax, eax
0x18008e080  jns     short loc_18008E0A4
0x18008e082  mov     edx, 1
0x18008e087  mov     r9d, 91h
0x18008e08d  mov     ecx, eax; int
0x18008e08f  call    Log_HREvent_65
0x18008e094  mov     rcx, [rbp+57h+string]; string
0x18008e098  call    cs:__imp_WindowsDeleteString
0x18008e09e  mov     [rbp+57h+string], r15
0x18008e0a2  jmp     short loc_18008E044
0x18008e0a4  mov     rcx, [rbp+57h+string]; string
0x18008e0a8  xor     edx, edx; length
0x18008e0aa  call    cs:__imp_WindowsGetStringRawBuffer
0x18008e0b0  mov     rdx, rax; String2
0x18008e0b3  mov     rcx, r12; String1
0x18008e0b6  call    cs:__imp__wcsicmp
0x18008e0bc  test    eax, eax
0x18008e0be  jnz     short loc_18008E0D0
0x18008e0c0  lea     rcx, [rbp+57h+var_38]
0x18008e0c4  call    ?InternalAddRef@?$ComPtr@UIImsClientWatcher@Rcs@Cellular@Restricted@Phone@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Phone::Restricted::Cellular::Rcs::IImsClientWatcher>::InternalAddRef(void)
0x18008e0c9  mov     rax, [rbp+57h+var_38]
0x18008e0cd  mov     [r14], rax
0x18008e0d0  mov     rcx, [rbp+57h+string]; string
0x18008e0d4  call    cs:__imp_WindowsDeleteString
0x18008e0da  lea     rcx, [rbp+57h+var_48]
0x18008e0de  mov     [rbp+57h+string], r15
0x18008e0e2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18008e0e7  mov     rdi, [rbp+57h+var_38]
0x18008e0eb  test    rdi, rdi
0x18008e0ee  jz      short loc_18008E103
0x18008e0f0  mov     [rbp+57h+var_38], r15
0x18008e0f4  mov     rcx, rdi
0x18008e0f7  mov     rax, [rdi]
0x18008e0fa  mov     rax, [rax+10h]
0x18008e0fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e103  mov     rcx, [rbp+57h+var_30]
0x18008e107  test    rcx, rcx
0x18008e10a  jz      short loc_18008E11C
0x18008e10c  mov     [rbp+57h+var_30], r15
0x18008e110  mov     rax, [rcx]
0x18008e113  mov     rax, [rax+10h]
0x18008e117  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e11c  mov     rcx, [rbp+57h+var_40]
0x18008e120  test    rcx, rcx
0x18008e123  jz      short loc_18008E135
0x18008e125  mov     [rbp+57h+var_40], r15
0x18008e129  mov     rax, [rcx]
0x18008e12c  mov     rax, [rax+10h]
0x18008e130  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e135  xor     eax, eax
0x18008e137  jmp     short loc_18008E198
0x18008e139  mov     edx, 1
0x18008e13e  mov     r9d, 89h
0x18008e144  mov     ecx, ebx; int
0x18008e146  call    Log_HREvent_65
0x18008e14b  mov     rcx, [rbp+57h+var_38]
0x18008e14f  test    rcx, rcx
0x18008e152  jz      short loc_18008E164
0x18008e154  mov     [rbp+57h+var_38], r15
0x18008e158  mov     rax, [rcx]
0x18008e15b  mov     rax, [rax+10h]
0x18008e15f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e164  mov     rcx, [rbp+57h+var_30]
0x18008e168  test    rcx, rcx
0x18008e16b  jz      short loc_18008E17D
0x18008e16d  mov     [rbp+57h+var_30], r15
0x18008e171  mov     rax, [rcx]
0x18008e174  mov     rax, [rax+10h]
0x18008e178  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e17d  mov     rcx, [rbp+57h+var_40]
0x18008e181  test    rcx, rcx
0x18008e184  jz      short loc_18008E196
0x18008e186  mov     [rbp+57h+var_40], r15
0x18008e18a  mov     rax, [rcx]
0x18008e18d  mov     rax, [rax+10h]
0x18008e191  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e196  mov     eax, ebx
0x18008e198  mov     rcx, [rbp+57h+var_28]
0x18008e19c  xor     rcx, rsp; StackCookie
0x18008e19f  call    __security_check_cookie
0x18008e1a4  lea     r11, [rsp+0C0h+var_20]
0x18008e1ac  mov     rbx, [r11+30h]
0x18008e1b0  mov     rsi, [r11+40h]
0x18008e1b4  mov     rsp, r11
0x18008e1b7  pop     r15
0x18008e1b9  pop     r14
0x18008e1bb  pop     r12
0x18008e1bd  pop     rdi
0x18008e1be  pop     rbp
0x18008e1bf  retn
```
