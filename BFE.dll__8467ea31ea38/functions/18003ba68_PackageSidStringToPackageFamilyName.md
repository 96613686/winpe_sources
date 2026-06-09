# PackageSidStringToPackageFamilyName

- ea: `0x18003ba68`
- end: `0x18003bf2a`
- name: `PackageSidStringToPackageFamilyName`
- size: `1218`
- prototype: `__int64 __fastcall(PCWSTR sourceString)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180013480`

## callees

- `0x180022730`
- `0x18003ba68`
- `0x18003bf30`
- `0x18003bf5c`
- `0x1800545bc`
- `0x180058b30`
- `0x180075228`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003bc01`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003bc01`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bbd2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bc4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003be39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003beb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bbd2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bc4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003be39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003beb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003bacb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003bb42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003bacb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003bb42`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18003bca2`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18003bce0`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18003bca2`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18003bce0`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003bae8`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003bae8`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18003baa0`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18003baa0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PackageSidStringToPackageFamilyName(PCWSTR sourceString, _QWORD *a2)
{
  int v4; // eax
  int ActivationFactory; // ebx
  HRESULT v6; // eax
  int v7; // edx
  unsigned int v8; // r8d
  _QWORD *v9; // rbx
  __int64 v10; // rsi
  unsigned int v11; // r8d
  unsigned __int64 v12; // rdx
  HRESULT v13; // eax
  int v14; // edx
  unsigned int v15; // r8d
  int v16; // eax
  int v17; // eax
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, HSTRING *); // rbx
  int v20; // eax
  PCWSTR StringRawBuffer; // rsi
  __int64 v22; // rbx
  int v23; // eax
  int v24; // edi
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rcx
  __int64 v39; // rcx
  __int64 v40; // rcx
  __int64 v41; // rcx
  HSTRING_HEADER hstringHeader; // [rsp+28h] [rbp-58h] BYREF
  HSTRING string; // [rsp+40h] [rbp-40h] BYREF
  __int64 v44; // [rsp+48h] [rbp-38h] BYREF
  _QWORD *v45; // [rsp+50h] [rbp-30h] BYREF
  __int64 v46; // [rsp+58h] [rbp-28h] BYREF
  HSTRING v47; // [rsp+60h] [rbp-20h] BYREF
  int v48; // [rsp+68h] [rbp-18h] BYREF
  UINT32 length; // [rsp+6Ch] [rbp-14h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  *a2 = 0;
  v4 = RoInitialize(1);
  ActivationFactory = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A,
      (unsigned int)"onecore\\net\\netio\\wfp\\bfe\\pfnutil\\pfn_helper.cpp",
      (const char *)(unsigned int)v4,
      0);
    return (unsigned int)ActivationFactory;
  }
  v45 = 0;
  string = 0;
  v6 = WindowsCreateStringReference(L"Windows.Internal.StateRepository.PackageFamily", 0x2Eu, &hstringHeader, &string);
  if ( v6 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v6, v7, v8);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_86f5b0ee_9560_4d76_a06a_ca4c8bfe4426, &v45);
  if ( ActivationFactory < 0 )
  {
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageFamilyStatics>::InternalRelease((__int64 *)&v45);
LABEL_26:
    RoUninitialize();
    return (unsigned int)ActivationFactory;
  }
  v44 = 0;
  v9 = v45;
  v10 = *v45;
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageFamilyStatics>::InternalRelease(&v44);
  string = 0;
  v12 = -1;
  do
    ++v12;
  while ( sourceString[v12] );
  if ( v12 > 0xFFFFFFFF )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v12, v11);
    __debugbreak();
  }
  if ( (int)v12 + 1 < (unsigned int)v12 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v12, v11);
    __debugbreak();
  }
  v13 = WindowsCreateStringReference(sourceString, v12, &hstringHeader, &string);
  if ( v13 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v13, v14, v15);
    JUMPOUT(0x18003BF29LL);
  }
  ActivationFactory = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64 *))(v10 + 160))(v9, string, &v44);
  if ( ActivationFactory < 0 )
  {
    v29 = v44;
    if ( v44 )
    {
      v44 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    }
    v30 = (__int64)v45;
    if ( v45 )
    {
      v45 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    }
    goto LABEL_26;
  }
  v48 = 0;
  v16 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v44 + 56LL))(v44, &v48);
  ActivationFactory = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x31,
      (unsigned int)"onecore\\net\\netio\\wfp\\bfe\\pfnutil\\pfn_helper.cpp",
      (const char *)(unsigned int)v16,
      0);
    v36 = v44;
    if ( v44 )
    {
      v44 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    }
    v37 = (__int64)v45;
    if ( v45 )
    {
      v45 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    }
    goto LABEL_26;
  }
  if ( v48 != 1 )
  {
    v34 = v44;
    if ( v44 )
    {
      v44 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    }
    v35 = (__int64)v45;
    if ( v45 )
    {
      v45 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    }
    ActivationFactory = -2147023728;
    goto LABEL_26;
  }
  v46 = 0;
  v17 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v44 + 48LL))(v44, 0, &v46);
  ActivationFactory = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3B,
      (unsigned int)"onecore\\net\\netio\\wfp\\bfe\\pfnutil\\pfn_helper.cpp",
      (const char *)(unsigned int)v17,
      0);
    v31 = v46;
    if ( v46 )
    {
      v46 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    }
    v32 = v44;
    if ( v44 )
    {
      v44 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    }
    v33 = (__int64)v45;
    if ( v45 )
    {
      v45 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    }
    goto LABEL_26;
  }
  v47 = 0;
  v18 = v46;
  v19 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v46 + 88LL);
  WindowsDeleteString(0);
  v47 = 0;
  v20 = v19(v18, &v47);
  ActivationFactory = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3F,
      (unsigned int)"onecore\\net\\netio\\wfp\\bfe\\pfnutil\\pfn_helper.cpp",
      (const char *)(unsigned int)v20,
      0);
    WindowsDeleteString(v47);
    v47 = 0;
    v38 = v46;
    if ( v46 )
    {
      v46 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    }
    v39 = v44;
    if ( v44 )
    {
      v44 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
    }
    v40 = (__int64)v45;
    if ( v45 )
    {
      v45 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    }
    goto LABEL_26;
  }
  length = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(v47, &length);
  v22 = 2LL * (length + 1);
  v23 = WfpMemAlloc(v22, 8u);
  v24 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x47,
      (unsigned int)"onecore\\net\\netio\\wfp\\bfe\\pfnutil\\pfn_helper.cpp",
      (const char *)(unsigned int)v23,
      0);
    WindowsDeleteString(v47);
    v47 = 0;
    v41 = v46;
    if ( v46 )
    {
      v46 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    }
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageFamilyStatics>::InternalRelease(&v44);
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageFamilyStatics>::InternalRelease((__int64 *)&v45);
    ActivationFactory = v24;
    goto LABEL_26;
  }
  memcpy_s(0, v22, StringRawBuffer, v22);
  *a2 = 0;
  WindowsDeleteString(v47);
  v47 = 0;
  v25 = v46;
  if ( v46 )
  {
    v46 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  }
  v26 = v44;
  if ( v44 )
  {
    v44 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  }
  v27 = (__int64)v45;
  if ( v45 )
  {
    v45 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  }
  RoUninitialize();
  return 0;
}

```

## disassembly

```asm
0x18003ba68  mov     [rsp-28h+arg_10], rbx
0x18003ba6d  push    rbp
0x18003ba6e  push    rsi
0x18003ba6f  push    rdi
0x18003ba70  push    r14
0x18003ba72  push    r15
0x18003ba74  mov     rbp, rsp
0x18003ba77  sub     rsp, 80h
0x18003ba7e  mov     rax, cs:__security_cookie
0x18003ba85  xor     rax, rsp
0x18003ba88  mov     [rbp+var_10], rax
0x18003ba8c  mov     r14, rdx
0x18003ba8f  mov     rdi, rcx
0x18003ba92  xor     r15d, r15d
0x18003ba95  mov     [rbp+Destination], r15
0x18003ba99  mov     [rdx], r15
0x18003ba9c  lea     ecx, [r15+1]
0x18003baa0  call    cs:__imp_RoInitialize
0x18003baa6  mov     ebx, eax
0x18003baa8  test    eax, eax
0x18003baaa  js      loc_18003BEEF
0x18003bab0  mov     [rbp+var_30], r15
0x18003bab4  mov     [rbp+string], r15
0x18003bab8  lea     r9, [rbp+string]; string
0x18003babc  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18003bac0  lea     edx, [r15+2Eh]; length
0x18003bac4  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_PackageFamily@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x18003bacb  call    cs:__imp_WindowsCreateStringReference
0x18003bad1  test    eax, eax
0x18003bad3  js      loc_18003BF0C
0x18003bad9  lea     r8, [rbp+var_30]
0x18003badd  lea     rdx, _GUID_86f5b0ee_9560_4d76_a06a_ca4c8bfe4426
0x18003bae4  mov     rcx, [rbp+string]
0x18003bae8  call    cs:__imp_RoGetActivationFactory
0x18003baee  mov     ebx, eax
0x18003baf0  test    eax, eax
0x18003baf2  js      loc_18003BF14
0x18003baf8  mov     [rbp+var_38], r15
0x18003bafc  mov     rbx, [rbp+var_30]
0x18003bb00  mov     rsi, [rbx]
0x18003bb03  lea     rcx, [rbp+var_38]
0x18003bb07  call    ?InternalRelease@?$ComPtr@UIPackageFamilyStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageFamilyStatics>::InternalRelease(void)
0x18003bb0c  mov     [rbp+string], r15
0x18003bb10  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18003bb14  inc     rdx; int
0x18003bb17  cmp     [rdi+rdx*2], r15w
0x18003bb1c  jnz     short loc_18003BB14
0x18003bb1e  mov     eax, 0FFFFFFFFh
0x18003bb23  cmp     rdx, rax
0x18003bb26  ja      loc_18003BD16
0x18003bb2c  lea     eax, [rdx+1]
0x18003bb2f  cmp     eax, edx
0x18003bb31  jb      loc_18003BD0B
0x18003bb37  lea     r9, [rbp+string]; string
0x18003bb3b  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18003bb3f  mov     rcx, rdi; sourceString
0x18003bb42  call    cs:__imp_WindowsCreateStringReference
0x18003bb48  test    eax, eax
0x18003bb4a  js      loc_18003BF22
0x18003bb50  lea     r8, [rbp+var_38]
0x18003bb54  mov     rdx, [rbp+string]
0x18003bb58  mov     rcx, rbx
0x18003bb5b  mov     rax, [rsi+0A0h]
0x18003bb62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bb67  mov     ebx, eax
0x18003bb69  test    eax, eax
0x18003bb6b  js      loc_18003BCAC
0x18003bb71  mov     [rbp+var_18], r15d
0x18003bb75  mov     rcx, [rbp+var_38]
0x18003bb79  mov     rax, [rcx]
0x18003bb7c  lea     rdx, [rbp+var_18]
0x18003bb80  mov     rax, [rax+38h]
0x18003bb84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bb89  mov     ebx, eax
0x18003bb8b  test    eax, eax
0x18003bb8d  js      loc_18003BDCB
0x18003bb93  cmp     [rbp+var_18], 1
0x18003bb97  jnz     loc_18003BD8D
0x18003bb9d  mov     [rbp+var_28], r15
0x18003bba1  mov     rcx, [rbp+var_38]
0x18003bba5  mov     rax, [rcx]
0x18003bba8  lea     r8, [rbp+var_28]
0x18003bbac  xor     edx, edx
0x18003bbae  mov     rax, [rax+30h]
0x18003bbb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bbb7  mov     ebx, eax
0x18003bbb9  test    eax, eax
0x18003bbbb  js      loc_18003BD21
0x18003bbc1  mov     [rbp+var_20], r15
0x18003bbc5  mov     rdi, [rbp+var_28]
0x18003bbc9  mov     rax, [rdi]
0x18003bbcc  mov     rbx, [rax+58h]
0x18003bbd0  xor     ecx, ecx; string
0x18003bbd2  call    cs:__imp_WindowsDeleteString
0x18003bbd8  mov     [rbp+var_20], r15
0x18003bbdc  lea     rdx, [rbp+var_20]
0x18003bbe0  mov     rcx, rdi
0x18003bbe3  mov     rax, rbx
0x18003bbe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bbeb  mov     ebx, eax
0x18003bbed  test    eax, eax
0x18003bbef  js      loc_18003BE1D
0x18003bbf5  mov     [rbp+length], r15d
0x18003bbf9  lea     rdx, [rbp+length]; length
0x18003bbfd  mov     rcx, [rbp+var_20]; string
0x18003bc01  call    cs:__imp_WindowsGetStringRawBuffer
0x18003bc07  mov     rsi, rax
0x18003bc0a  mov     ebx, [rbp+length]
0x18003bc0d  inc     ebx
0x18003bc0f  add     rbx, rbx
0x18003bc12  lea     r8, [rbp+Destination]
0x18003bc16  mov     edx, 8; dwFlags
0x18003bc1b  mov     rcx, rbx; dwBytes
0x18003bc1e  call    WfpMemAlloc
0x18003bc23  mov     rdi, rax
0x18003bc26  test    eax, eax
0x18003bc28  js      loc_18003BE96
0x18003bc2e  mov     r9, rbx; SourceSize
0x18003bc31  mov     r8, rsi; Source
0x18003bc34  mov     rdx, rbx; DestinationSize
0x18003bc37  mov     rbx, [rbp+Destination]
0x18003bc3b  mov     rcx, rbx; Destination
0x18003bc3e  call    memcpy_s
0x18003bc43  mov     [r14], rbx
0x18003bc46  mov     rcx, [rbp+var_20]; string
0x18003bc4a  call    cs:__imp_WindowsDeleteString
0x18003bc50  mov     [rbp+var_20], r15
0x18003bc54  mov     rcx, [rbp+var_28]
0x18003bc58  test    rcx, rcx
0x18003bc5b  jz      short loc_18003BC6E
0x18003bc5d  mov     [rbp+var_28], r15
0x18003bc61  mov     rax, [rcx]
0x18003bc64  mov     rax, [rax+10h]
0x18003bc68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bc6d  nop
0x18003bc6e  mov     rcx, [rbp+var_38]
0x18003bc72  test    rcx, rcx
0x18003bc75  jz      short loc_18003BC88
0x18003bc77  mov     [rbp+var_38], r15
0x18003bc7b  mov     rax, [rcx]
0x18003bc7e  mov     rax, [rax+10h]
0x18003bc82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bc87  nop
0x18003bc88  mov     rcx, [rbp+var_30]
0x18003bc8c  test    rcx, rcx
0x18003bc8f  jz      short loc_18003BCA2
0x18003bc91  mov     [rbp+var_30], r15
0x18003bc95  mov     rax, [rcx]
0x18003bc98  mov     rax, [rax+10h]
0x18003bc9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bca1  nop
0x18003bca2  call    cs:__imp_RoUninitialize
0x18003bca8  xor     eax, eax
0x18003bcaa  jmp     short loc_18003BCE8
0x18003bcac  mov     rcx, [rbp+var_38]
0x18003bcb0  test    rcx, rcx
0x18003bcb3  jz      short loc_18003BCC6
0x18003bcb5  mov     [rbp+var_38], r15
0x18003bcb9  mov     rdx, [rcx]
0x18003bcbc  mov     rax, [rdx+10h]
0x18003bcc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bcc5  nop
0x18003bcc6  mov     rcx, [rbp+var_30]
0x18003bcca  test    rcx, rcx
0x18003bccd  jz      short loc_18003BCE0
0x18003bccf  mov     [rbp+var_30], r15
0x18003bcd3  mov     rax, [rcx]
0x18003bcd6  mov     rax, [rax+10h]
0x18003bcda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bcdf  nop
0x18003bce0  call    cs:__imp_RoUninitialize
0x18003bce6  mov     eax, ebx
0x18003bce8  mov     rcx, [rbp+var_10]
0x18003bcec  xor     rcx, rsp; StackCookie
0x18003bcef  call    __security_check_cookie
0x18003bcf4  mov     rbx, [rsp+80h+arg_10]
0x18003bcfc  add     rsp, 80h
0x18003bd03  pop     r15
0x18003bd05  pop     r14
0x18003bd07  pop     rdi
0x18003bd08  pop     rsi
0x18003bd09  pop     rbp
0x18003bd0a  retn
0x18003bd0b  mov     ecx, 80070216h; this
0x18003bd10  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18003bd15  int     3; Trap to Debugger
0x18003bd16  mov     ecx, 80070216h; this
0x18003bd1b  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18003bd20  int     3; Trap to Debugger
0x18003bd21  mov     rcx, [rbp+28h]; this
0x18003bd25  mov     r9d, eax; char *
0x18003bd28  lea     r8, aOnecoreNetNeti_0; "onecore\\net\\netio\\wfp\\bfe\\pfnutil"...
0x18003bd2f  mov     edx, 3Bh ; ';'; void *
0x18003bd34  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003bd39  nop
0x18003bd3a  mov     rcx, [rbp+var_28]
0x18003bd3e  test    rcx, rcx
0x18003bd41  jz      short loc_18003BD54
0x18003bd43  mov     [rbp+var_28], r15
0x18003bd47  mov     rax, [rcx]
0x18003bd4a  mov     rax, [rax+10h]
0x18003bd4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bd53  nop
0x18003bd54  mov     rcx, [rbp+var_38]
0x18003bd58  test    rcx, rcx
0x18003bd5b  jz      short loc_18003BD6E
0x18003bd5d  mov     [rbp+var_38], r15
0x18003bd61  mov     rax, [rcx]
0x18003bd64  mov     rax, [rax+10h]
0x18003bd68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bd6d  nop
0x18003bd6e  mov     rcx, [rbp+var_30]
0x18003bd72  test    rcx, rcx
0x18003bd75  jz      short loc_18003BD88
0x18003bd77  mov     [rbp+var_30], r15
0x18003bd7b  mov     rax, [rcx]
0x18003bd7e  mov     rax, [rax+10h]
0x18003bd82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bd87  nop
0x18003bd88  jmp     loc_18003BCE0
0x18003bd8d  mov     rcx, [rbp+var_38]
0x18003bd91  test    rcx, rcx
0x18003bd94  jz      short loc_18003BDA7
0x18003bd96  mov     [rbp+var_38], r15
0x18003bd9a  mov     rax, [rcx]
0x18003bd9d  mov     rax, [rax+10h]
0x18003bda1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bda6  nop
0x18003bda7  mov     rcx, [rbp+var_30]
0x18003bdab  test    rcx, rcx
0x18003bdae  jz      short loc_18003BDC1
0x18003bdb0  mov     [rbp+var_30], r15
0x18003bdb4  mov     rax, [rcx]
0x18003bdb7  mov     rax, [rax+10h]
0x18003bdbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bdc0  nop
0x18003bdc1  mov     ebx, 80070490h
0x18003bdc6  jmp     loc_18003BCE0
0x18003bdcb  mov     rcx, [rbp+28h]; this
0x18003bdcf  mov     r9d, eax; char *
0x18003bdd2  lea     r8, aOnecoreNetNeti_0; "onecore\\net\\netio\\wfp\\bfe\\pfnutil"...
0x18003bdd9  mov     edx, 31h ; '1'; void *
0x18003bdde  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003bde3  nop
0x18003bde4  mov     rcx, [rbp+var_38]
0x18003bde8  test    rcx, rcx
0x18003bdeb  jz      short loc_18003BDFE
0x18003bded  mov     [rbp+var_38], r15
0x18003bdf1  mov     rax, [rcx]
0x18003bdf4  mov     rax, [rax+10h]
0x18003bdf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bdfd  nop
0x18003bdfe  mov     rcx, [rbp+var_30]
0x18003be02  test    rcx, rcx
0x18003be05  jz      short loc_18003BE18
0x18003be07  mov     [rbp+var_30], r15
0x18003be0b  mov     rax, [rcx]
0x18003be0e  mov     rax, [rax+10h]
0x18003be12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003be17  nop
0x18003be18  jmp     loc_18003BCE0
0x18003be1d  mov     rcx, [rbp+28h]; this
0x18003be21  mov     r9d, eax; char *
0x18003be24  lea     r8, aOnecoreNetNeti_0; "onecore\\net\\netio\\wfp\\bfe\\pfnutil"...
0x18003be2b  mov     edx, 3Fh ; '?'; void *
0x18003be30  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003be35  mov     rcx, [rbp+var_20]; string
0x18003be39  call    cs:__imp_WindowsDeleteString
0x18003be3f  mov     [rbp+var_20], r15
0x18003be43  mov     rcx, [rbp+var_28]
0x18003be47  test    rcx, rcx
0x18003be4a  jz      short loc_18003BE5D
0x18003be4c  mov     [rbp+var_28], r15
0x18003be50  mov     rax, [rcx]
0x18003be53  mov     rax, [rax+10h]
0x18003be57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003be5c  nop
0x18003be5d  mov     rcx, [rbp+var_38]
0x18003be61  test    rcx, rcx
0x18003be64  jz      short loc_18003BE77
0x18003be66  mov     [rbp+var_38], r15
0x18003be6a  mov     rax, [rcx]
0x18003be6d  mov     rax, [rax+10h]
0x18003be71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003be76  nop
0x18003be77  mov     rcx, [rbp+var_30]
0x18003be7b  test    rcx, rcx
0x18003be7e  jz      short loc_18003BE91
0x18003be80  mov     [rbp+var_30], r15
0x18003be84  mov     rax, [rcx]
0x18003be87  mov     rax, [rax+10h]
0x18003be8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003be90  nop
0x18003be91  jmp     loc_18003BCE0
0x18003be96  mov     rcx, [rbp+28h]; this
0x18003be9a  mov     r9d, edi; char *
0x18003be9d  lea     r8, aOnecoreNetNeti_0; "onecore\\net\\netio\\wfp\\bfe\\pfnutil"...
0x18003bea4  mov     edx, 47h ; 'G'; void *
0x18003bea9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003beae  mov     rcx, [rbp+var_20]; string
  ... truncated ...
```
