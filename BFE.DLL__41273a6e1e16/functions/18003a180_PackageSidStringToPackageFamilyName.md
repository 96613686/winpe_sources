# PackageSidStringToPackageFamilyName

- ea: `0x18003a180`
- end: `0x18003a685`
- name: `PackageSidStringToPackageFamilyName`
- size: `1285`
- prototype: `__int64 __fastcall(PCWSTR sourceString)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180013f60`

## callees

- `0x180024e40`
- `0x18003a180`
- `0x18003a68c`
- `0x18003a6bc`
- `0x180056400`
- `0x18005aa60`
- `0x180077c80`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003a337`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003a337`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a302`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a386`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a588`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a607`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a302`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a386`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a588`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a607`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003a1e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003a26c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003a1e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003a26c`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18003a3e4`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18003a428`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18003a3e4`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18003a428`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003a20c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003a20c`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18003a1b8`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18003a1b8`

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
  _QWORD *v27; // rcx
  __int64 v29; // rcx
  _QWORD *v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rcx
  _QWORD *v33; // rcx
  __int64 v34; // rcx
  _QWORD *v35; // rcx
  __int64 v36; // rcx
  _QWORD *v37; // rcx
  __int64 v38; // rcx
  __int64 v39; // rcx
  _QWORD *v40; // rcx
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
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageFamilyStatics>::InternalRelease(&v45);
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
    JUMPOUT(0x18003A684LL);
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
    v30 = v45;
    if ( v45 )
    {
      v45 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v30 + 16LL))(v30);
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
    v37 = v45;
    if ( v45 )
    {
      v45 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v37 + 16LL))(v37);
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
    v35 = v45;
    if ( v45 )
    {
      v45 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v35 + 16LL))(v35);
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
    v33 = v45;
    if ( v45 )
    {
      v45 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v33 + 16LL))(v33);
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
    v40 = v45;
    if ( v45 )
    {
      v45 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v40 + 16LL))(v40);
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
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageFamilyStatics>::InternalRelease(&v45);
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
  v27 = v45;
  if ( v45 )
  {
    v45 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v27 + 16LL))(v27);
  }
  RoUninitialize();
  return 0;
}

```

## disassembly

```asm
0x18003a180  mov     [rsp-28h+arg_10], rbx
0x18003a185  push    rbp
0x18003a186  push    rsi
0x18003a187  push    rdi
0x18003a188  push    r14
0x18003a18a  push    r15
0x18003a18c  mov     rbp, rsp
0x18003a18f  sub     rsp, 80h
0x18003a196  mov     rax, cs:__security_cookie
0x18003a19d  xor     rax, rsp
0x18003a1a0  mov     [rbp+var_10], rax
0x18003a1a4  mov     r14, rdx
0x18003a1a7  mov     rdi, rcx
0x18003a1aa  xor     r15d, r15d
0x18003a1ad  mov     [rbp+Destination], r15
0x18003a1b1  mov     [rdx], r15
0x18003a1b4  lea     ecx, [r15+1]
0x18003a1b8  call    cs:__imp_RoInitialize
0x18003a1bf  nop     dword ptr [rax+rax+00h]
0x18003a1c4  mov     ebx, eax
0x18003a1c6  test    eax, eax
0x18003a1c8  js      loc_18003A64A
0x18003a1ce  mov     [rbp+var_30], r15
0x18003a1d2  mov     [rbp+string], r15
0x18003a1d6  lea     r9, [rbp+string]; string
0x18003a1da  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18003a1de  lea     edx, [r15+2Eh]; length
0x18003a1e2  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_PackageFamily@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x18003a1e9  call    cs:__imp_WindowsCreateStringReference
0x18003a1f0  nop     dword ptr [rax+rax+00h]
0x18003a1f5  test    eax, eax
0x18003a1f7  js      loc_18003A667
0x18003a1fd  lea     r8, [rbp+var_30]
0x18003a201  lea     rdx, _GUID_86f5b0ee_9560_4d76_a06a_ca4c8bfe4426
0x18003a208  mov     rcx, [rbp+string]
0x18003a20c  call    cs:__imp_RoGetActivationFactory
0x18003a213  nop     dword ptr [rax+rax+00h]
0x18003a218  mov     ebx, eax
0x18003a21a  test    eax, eax
0x18003a21c  js      loc_18003A66F
0x18003a222  mov     [rbp+var_38], r15
0x18003a226  mov     rbx, [rbp+var_30]
0x18003a22a  mov     rsi, [rbx]
0x18003a22d  lea     rcx, [rbp+var_38]
0x18003a231  call    ?InternalRelease@?$ComPtr@UIPackageFamilyStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageFamilyStatics>::InternalRelease(void)
0x18003a236  mov     [rbp+string], r15
0x18003a23a  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18003a23e  inc     rdx; int
0x18003a241  cmp     [rdi+rdx*2], r15w
0x18003a246  jnz     short loc_18003A23E
0x18003a248  mov     eax, 0FFFFFFFFh
0x18003a24d  cmp     rdx, rax
0x18003a250  ja      loc_18003A465
0x18003a256  lea     eax, [rdx+1]
0x18003a259  cmp     eax, edx
0x18003a25b  jb      loc_18003A45A
0x18003a261  lea     r9, [rbp+string]; string
0x18003a265  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18003a269  mov     rcx, rdi; sourceString
0x18003a26c  call    cs:__imp_WindowsCreateStringReference
0x18003a273  nop     dword ptr [rax+rax+00h]
0x18003a278  test    eax, eax
0x18003a27a  js      loc_18003A67D
0x18003a280  lea     r8, [rbp+var_38]
0x18003a284  mov     rdx, [rbp+string]
0x18003a288  mov     rcx, rbx
0x18003a28b  mov     rax, [rsi+0A0h]
0x18003a292  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a297  mov     ebx, eax
0x18003a299  test    eax, eax
0x18003a29b  js      loc_18003A3F4
0x18003a2a1  mov     [rbp+var_18], r15d
0x18003a2a5  mov     rcx, [rbp+var_38]
0x18003a2a9  mov     rax, [rcx]
0x18003a2ac  lea     rdx, [rbp+var_18]
0x18003a2b0  mov     rax, [rax+38h]
0x18003a2b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a2b9  mov     ebx, eax
0x18003a2bb  test    eax, eax
0x18003a2bd  js      loc_18003A51A
0x18003a2c3  cmp     [rbp+var_18], 1
0x18003a2c7  jnz     loc_18003A4DC
0x18003a2cd  mov     [rbp+var_28], r15
0x18003a2d1  mov     rcx, [rbp+var_38]
0x18003a2d5  mov     rax, [rcx]
0x18003a2d8  lea     r8, [rbp+var_28]
0x18003a2dc  xor     edx, edx
0x18003a2de  mov     rax, [rax+30h]
0x18003a2e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a2e7  mov     ebx, eax
0x18003a2e9  test    eax, eax
0x18003a2eb  js      loc_18003A470
0x18003a2f1  mov     [rbp+var_20], r15
0x18003a2f5  mov     rdi, [rbp+var_28]
0x18003a2f9  mov     rax, [rdi]
0x18003a2fc  mov     rbx, [rax+58h]
0x18003a300  xor     ecx, ecx; string
0x18003a302  call    cs:__imp_WindowsDeleteString
0x18003a309  nop     dword ptr [rax+rax+00h]
0x18003a30e  mov     [rbp+var_20], r15
0x18003a312  lea     rdx, [rbp+var_20]
0x18003a316  mov     rcx, rdi
0x18003a319  mov     rax, rbx
0x18003a31c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a321  mov     ebx, eax
0x18003a323  test    eax, eax
0x18003a325  js      loc_18003A56C
0x18003a32b  mov     [rbp+length], r15d
0x18003a32f  lea     rdx, [rbp+length]; length
0x18003a333  mov     rcx, [rbp+var_20]; string
0x18003a337  call    cs:__imp_WindowsGetStringRawBuffer
0x18003a33e  nop     dword ptr [rax+rax+00h]
0x18003a343  mov     rsi, rax
0x18003a346  mov     ebx, [rbp+length]
0x18003a349  inc     ebx
0x18003a34b  add     rbx, rbx
0x18003a34e  lea     r8, [rbp+Destination]
0x18003a352  mov     edx, 8; dwFlags
0x18003a357  mov     rcx, rbx; dwBytes
0x18003a35a  call    WfpMemAlloc
0x18003a35f  mov     rdi, rax
0x18003a362  test    eax, eax
0x18003a364  js      loc_18003A5EB
0x18003a36a  mov     r9, rbx; SourceSize
0x18003a36d  mov     r8, rsi; Source
0x18003a370  mov     rdx, rbx; DestinationSize
0x18003a373  mov     rbx, [rbp+Destination]
0x18003a377  mov     rcx, rbx; Destination
0x18003a37a  call    memcpy_s
0x18003a37f  mov     [r14], rbx
0x18003a382  mov     rcx, [rbp+var_20]; string
0x18003a386  call    cs:__imp_WindowsDeleteString
0x18003a38d  nop     dword ptr [rax+rax+00h]
0x18003a392  mov     [rbp+var_20], r15
0x18003a396  mov     rcx, [rbp+var_28]
0x18003a39a  test    rcx, rcx
0x18003a39d  jz      short loc_18003A3B0
0x18003a39f  mov     [rbp+var_28], r15
0x18003a3a3  mov     rax, [rcx]
0x18003a3a6  mov     rax, [rax+10h]
0x18003a3aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a3af  nop
0x18003a3b0  mov     rcx, [rbp+var_38]
0x18003a3b4  test    rcx, rcx
0x18003a3b7  jz      short loc_18003A3CA
0x18003a3b9  mov     [rbp+var_38], r15
0x18003a3bd  mov     rax, [rcx]
0x18003a3c0  mov     rax, [rax+10h]
0x18003a3c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a3c9  nop
0x18003a3ca  mov     rcx, [rbp+var_30]
0x18003a3ce  test    rcx, rcx
0x18003a3d1  jz      short loc_18003A3E4
0x18003a3d3  mov     [rbp+var_30], r15
0x18003a3d7  mov     rax, [rcx]
0x18003a3da  mov     rax, [rax+10h]
0x18003a3de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a3e3  nop
0x18003a3e4  call    cs:__imp_RoUninitialize
0x18003a3eb  nop     dword ptr [rax+rax+00h]
0x18003a3f0  xor     eax, eax
0x18003a3f2  jmp     short loc_18003A436
0x18003a3f4  mov     rcx, [rbp+var_38]
0x18003a3f8  test    rcx, rcx
0x18003a3fb  jz      short loc_18003A40E
0x18003a3fd  mov     [rbp+var_38], r15
0x18003a401  mov     rdx, [rcx]
0x18003a404  mov     rax, [rdx+10h]
0x18003a408  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a40d  nop
0x18003a40e  mov     rcx, [rbp+var_30]
0x18003a412  test    rcx, rcx
0x18003a415  jz      short loc_18003A428
0x18003a417  mov     [rbp+var_30], r15
0x18003a41b  mov     rax, [rcx]
0x18003a41e  mov     rax, [rax+10h]
0x18003a422  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a427  nop
0x18003a428  call    cs:__imp_RoUninitialize
0x18003a42f  nop     dword ptr [rax+rax+00h]
0x18003a434  mov     eax, ebx
0x18003a436  mov     rcx, [rbp+var_10]
0x18003a43a  xor     rcx, rsp; StackCookie
0x18003a43d  call    __security_check_cookie
0x18003a442  mov     rbx, [rsp+80h+arg_10]
0x18003a44a  add     rsp, 80h
0x18003a451  pop     r15
0x18003a453  pop     r14
0x18003a455  pop     rdi
0x18003a456  pop     rsi
0x18003a457  pop     rbp
0x18003a458  retn
0x18003a45a  mov     ecx, 80070216h; this
0x18003a45f  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18003a464  int     3; Trap to Debugger
0x18003a465  mov     ecx, 80070216h; this
0x18003a46a  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18003a46f  int     3; Trap to Debugger
0x18003a470  mov     rcx, [rbp+28h]; this
0x18003a474  mov     r9d, eax; char *
0x18003a477  lea     r8, aOnecoreNetNeti_0; "onecore\\net\\netio\\wfp\\bfe\\pfnutil"...
0x18003a47e  mov     edx, 3Bh ; ';'; void *
0x18003a483  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a488  nop
0x18003a489  mov     rcx, [rbp+var_28]
0x18003a48d  test    rcx, rcx
0x18003a490  jz      short loc_18003A4A3
0x18003a492  mov     [rbp+var_28], r15
0x18003a496  mov     rax, [rcx]
0x18003a499  mov     rax, [rax+10h]
0x18003a49d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a4a2  nop
0x18003a4a3  mov     rcx, [rbp+var_38]
0x18003a4a7  test    rcx, rcx
0x18003a4aa  jz      short loc_18003A4BD
0x18003a4ac  mov     [rbp+var_38], r15
0x18003a4b0  mov     rax, [rcx]
0x18003a4b3  mov     rax, [rax+10h]
0x18003a4b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a4bc  nop
0x18003a4bd  mov     rcx, [rbp+var_30]
0x18003a4c1  test    rcx, rcx
0x18003a4c4  jz      short loc_18003A4D7
0x18003a4c6  mov     [rbp+var_30], r15
0x18003a4ca  mov     rax, [rcx]
0x18003a4cd  mov     rax, [rax+10h]
0x18003a4d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a4d6  nop
0x18003a4d7  jmp     loc_18003A428
0x18003a4dc  mov     rcx, [rbp+var_38]
0x18003a4e0  test    rcx, rcx
0x18003a4e3  jz      short loc_18003A4F6
0x18003a4e5  mov     [rbp+var_38], r15
0x18003a4e9  mov     rax, [rcx]
0x18003a4ec  mov     rax, [rax+10h]
0x18003a4f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a4f5  nop
0x18003a4f6  mov     rcx, [rbp+var_30]
0x18003a4fa  test    rcx, rcx
0x18003a4fd  jz      short loc_18003A510
0x18003a4ff  mov     [rbp+var_30], r15
0x18003a503  mov     rax, [rcx]
0x18003a506  mov     rax, [rax+10h]
0x18003a50a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a50f  nop
0x18003a510  mov     ebx, 80070490h
0x18003a515  jmp     loc_18003A428
0x18003a51a  mov     rcx, [rbp+28h]; this
0x18003a51e  mov     r9d, eax; char *
0x18003a521  lea     r8, aOnecoreNetNeti_0; "onecore\\net\\netio\\wfp\\bfe\\pfnutil"...
0x18003a528  mov     edx, 31h ; '1'; void *
0x18003a52d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a532  nop
0x18003a533  mov     rcx, [rbp+var_38]
0x18003a537  test    rcx, rcx
0x18003a53a  jz      short loc_18003A54D
0x18003a53c  mov     [rbp+var_38], r15
0x18003a540  mov     rax, [rcx]
0x18003a543  mov     rax, [rax+10h]
0x18003a547  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a54c  nop
0x18003a54d  mov     rcx, [rbp+var_30]
0x18003a551  test    rcx, rcx
0x18003a554  jz      short loc_18003A567
0x18003a556  mov     [rbp+var_30], r15
0x18003a55a  mov     rax, [rcx]
0x18003a55d  mov     rax, [rax+10h]
0x18003a561  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a566  nop
0x18003a567  jmp     loc_18003A428
0x18003a56c  mov     rcx, [rbp+28h]; this
0x18003a570  mov     r9d, eax; char *
0x18003a573  lea     r8, aOnecoreNetNeti_0; "onecore\\net\\netio\\wfp\\bfe\\pfnutil"...
0x18003a57a  mov     edx, 3Fh ; '?'; void *
0x18003a57f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a584  mov     rcx, [rbp+var_20]; string
0x18003a588  call    cs:__imp_WindowsDeleteString
0x18003a58f  nop     dword ptr [rax+rax+00h]
0x18003a594  mov     [rbp+var_20], r15
0x18003a598  mov     rcx, [rbp+var_28]
0x18003a59c  test    rcx, rcx
0x18003a59f  jz      short loc_18003A5B2
0x18003a5a1  mov     [rbp+var_28], r15
0x18003a5a5  mov     rax, [rcx]
0x18003a5a8  mov     rax, [rax+10h]
0x18003a5ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a5b1  nop
0x18003a5b2  mov     rcx, [rbp+var_38]
0x18003a5b6  test    rcx, rcx
0x18003a5b9  jz      short loc_18003A5CC
0x18003a5bb  mov     [rbp+var_38], r15
0x18003a5bf  mov     rax, [rcx]
0x18003a5c2  mov     rax, [rax+10h]
0x18003a5c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a5cb  nop
0x18003a5cc  mov     rcx, [rbp+var_30]
0x18003a5d0  test    rcx, rcx
0x18003a5d3  jz      short loc_18003A5E6
0x18003a5d5  mov     [rbp+var_30], r15
0x18003a5d9  mov     rax, [rcx]
  ... truncated ...
```
