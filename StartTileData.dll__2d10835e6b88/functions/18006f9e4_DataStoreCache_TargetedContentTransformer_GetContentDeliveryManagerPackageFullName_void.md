# DataStoreCache::TargetedContentTransformer::GetContentDeliveryManagerPackageFullName(void)

- ea: `0x18006f9e4`
- end: `0x18006fd61`
- name: `?GetContentDeliveryManagerPackageFullName@TargetedContentTransformer@DataStoreCache@@AEAA?AVHString@Wrappers@WRL@Microsoft@@XZ`
- size: `893`
- prototype: `struct Microsoft::WRL::Wrappers::HString __high(void)`
- caller_count: `3`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18006f4ac`
- `0x180070474`
- `0x180375e00`

## callees

- `0x18000ce94`
- `0x18001dac0`
- `0x180035a98`
- `0x18006f9e4`
- `0x180201e50`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006fcaa`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006fcaa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006fa55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006fa55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18006fbe6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18006fbe6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006fb6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006fbd7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006fb6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006fbd7`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18006fa72`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18006fa72`

## string_xrefs

- `0x18006fc8c`: `shellcommon\shell\datastorecache\transformers\targetedcontenttransformer\lib\targetedcontenttransformer.cpp`
- `0x18006fcb4`: `shellcommon\shell\datastorecache\transformers\targetedcontenttransformer\lib\targetedcontenttransformer.cpp`
- `0x18006fcc9`: `shellcommon\shell\datastorecache\transformers\targetedcontenttransformer\lib\targetedcontenttransformer.cpp`
- `0x18006fcde`: `shellcommon\shell\datastorecache\transformers\targetedcontenttransformer\lib\targetedcontenttransformer.cpp`
- `0x18006fcf3`: `shellcommon\shell\datastorecache\transformers\targetedcontenttransformer\lib\targetedcontenttransformer.cpp`
- `0x18006fd0b`: `shellcommon\shell\datastorecache\transformers\targetedcontenttransformer\lib\targetedcontenttransformer.cpp`
- `0x18006fd37`: `shellcommon\shell\datastorecache\transformers\targetedcontenttransformer\lib\targetedcontenttransformer.cpp`
- `0x18006fd4f`: `shellcommon\shell\datastorecache\transformers\targetedcontenttransformer\lib\targetedcontenttransformer.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
HSTRING *__fastcall DataStoreCache::TargetedContentTransformer::GetContentDeliveryManagerPackageFullName(
        __int64 a1,
        HSTRING *a2)
{
  HSTRING *v4; // r15
  HRESULT v5; // eax
  int ActivationFactory; // eax
  wil::details::in1diag3 *v7; // rcx
  __int64 v8; // rax
  int v9; // eax
  int v10; // eax
  HSTRING *v11; // rbx
  unsigned __int64 v12; // r12
  int v13; // eax
  int v14; // edi
  int v15; // r13d
  __int64 (__fastcall *v16)(HSTRING *, HSTRING *); // rdi
  int v17; // eax
  HSTRING v18; // rbx
  int v20; // eax
  HSTRING *v21; // r14
  int v22; // [rsp+20h] [rbp-60h] BYREF
  void *v23; // [rsp+28h] [rbp-58h] BYREF
  unsigned __int64 v24; // [rsp+30h] [rbp-50h] BYREF
  __int64 *v25; // [rsp+38h] [rbp-48h] BYREF
  HSTRING *v26; // [rsp+40h] [rbp-40h]
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-30h] BYREF
  HSTRING string; // [rsp+68h] [rbp-18h] BYREF
  HSTRING *v29; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  v26 = a2;
  v4 = (HSTRING *)(a1 + 280);
  if ( *(_QWORD *)(a1 + 280) )
    goto LABEL_16;
  if ( !*(_QWORD *)(a1 + 272) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x568,
      (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\targetedcontenttransformer\\lib\\targetedcontenttransformer.cpp",
      (const char *)0x80270254LL,
      v22);
  v25 = 0;
  string = 0;
  v5 = WindowsCreateStringReference(L"Windows.Internal.StateRepository.Package", 0x28u, &hstringHeader, &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
LABEL_27:
    wil::details::in1diag3::Throw_Hr(
      v7,
      (void *)0x56B,
      (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\targetedcontenttransformer\\lib\\targetedcontenttransformer.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v22);
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_0450ce77_af0d_40ac_93fd_1e5d48c89419, &v25);
  v7 = retaddr;
  if ( ActivationFactory < 0 )
    goto LABEL_27;
  v23 = 0;
  v8 = *v25;
  v23 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, void **))(v8 + 208))(v25, *(_QWORD *)(a1 + 272), &v23);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x56F,
      (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\targetedcontenttransformer\\lib\\targetedcontenttransformer.cpp",
      (const char *)(unsigned int)v9,
      v22);
  v22 = 0;
  v10 = (*(__int64 (__fastcall **)(void *, int *))(*(_QWORD *)v23 + 56LL))(v23, &v22);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x572,
      (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\targetedcontenttransformer\\lib\\targetedcontenttransformer.cpp",
      (const char *)(unsigned int)v10,
      v22);
  if ( !v22 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x573,
      (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\targetedcontenttransformer\\lib\\targetedcontenttransformer.cpp",
      (const char *)0x80070490LL,
      0);
  v11 = 0;
  v26 = 0;
  v12 = 0;
  hstringHeader.Reserved.Reserved1 = v23;
  *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = &string;
  LODWORD(string) = 0;
  v29 = 0;
  v13 = (*(__int64 (__fastcall **)(void *, char *))(*(_QWORD *)v23 + 56LL))(v23, &hstringHeader.Reserved.Reserved2[8]);
  **(_DWORD **)&hstringHeader.Reserved.Reserved2[16] = v13;
  wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<Windows::Services::Store::StoreAvailability *>>::get_at_current(
    &hstringHeader,
    0);
  v14 = 0;
  v15 = *(_DWORD *)&hstringHeader.Reserved.Reserved2[8];
  while ( (int)**(_DWORD **)&hstringHeader.Reserved.Reserved2[16] >= 0 && v14 != v15 )
  {
    v24 = 0;
    v20 = (*((__int64 (__fastcall **)(HSTRING *, unsigned __int64 *))*v29 + 13))(v29, &v24);
    if ( v20 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x57B,
        (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\targetedcontenttransformer\\lib\\targetedcontenttransformer.cpp",
        (const char *)(unsigned int)v20,
        v22);
    if ( v24 > v12 )
    {
      v12 = v24;
      v21 = v11;
      v11 = v29;
      v26 = v29;
      if ( v29 )
        (*((void (__fastcall **)(HSTRING *))*v29 + 1))(v29);
      if ( v21 )
        (*((void (__fastcall **)(HSTRING *))*v21 + 2))(v21);
    }
    wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<Windows::Services::Store::StoreAvailability *>>::get_at_current(
      &hstringHeader,
      (unsigned int)++v14);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
  if ( !v11 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x583,
      (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\targetedcontenttransformer\\lib\\targetedcontenttransformer.cpp",
      (const char *)0x80070002LL,
      v22);
  v16 = (__int64 (__fastcall *)(HSTRING *, HSTRING *))*((_QWORD *)*v11 + 14);
  WindowsDeleteString(*v4);
  *v4 = 0;
  v17 = v16(v11, v4);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x584,
      (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\targetedcontenttransformer\\lib\\targetedcontenttransformer.cpp",
      (const char *)(unsigned int)v17,
      v22);
  (*((void (__fastcall **)(HSTRING *))*v11 + 2))(v11);
  if ( v23 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v23 + 16LL))(v23);
  if ( v25 )
    (*(void (__fastcall **)(__int64 *))(*v25 + 16))(v25);
LABEL_16:
  *a2 = 0;
  v18 = *v4;
  WindowsDeleteString(0);
  *a2 = 0;
  WindowsDuplicateString(v18, a2);
  return a2;
}

```

## disassembly

```asm
0x18006f9e4  mov     [rsp-38h+arg_10], rbx
0x18006f9e9  push    rbp
0x18006f9ea  push    rsi
0x18006f9eb  push    rdi
0x18006f9ec  push    r12
0x18006f9ee  push    r13
0x18006f9f0  push    r14
0x18006f9f2  push    r15
0x18006f9f4  mov     rbp, rsp
0x18006f9f7  sub     rsp, 80h
0x18006f9fe  mov     rax, cs:__security_cookie
0x18006fa05  xor     rax, rsp
0x18006fa08  mov     [rbp+var_8], rax
0x18006fa0c  mov     rsi, rdx
0x18006fa0f  mov     rbx, rcx
0x18006fa12  mov     [rbp+var_40], rdx
0x18006fa16  xor     r14d, r14d
0x18006fa19  lea     r15, [rcx+118h]
0x18006fa20  cmp     [r15], r14
0x18006fa23  jnz     loc_18006FBCF
0x18006fa29  mov     rcx, [rbp+38h]; this
0x18006fa2d  cmp     [rbx+110h], r14
0x18006fa34  jz      loc_18006FD31
0x18006fa3a  mov     [rbp+var_48], r14
0x18006fa3e  mov     [rbp+string], r14
0x18006fa42  lea     r9, [rbp+string]; string
0x18006fa46  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18006fa4a  lea     edx, [r14+28h]; length
0x18006fa4e  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_Package@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x18006fa55  call    cs:__imp_WindowsCreateStringReference
0x18006fa5b  test    eax, eax
0x18006fa5d  js      loc_18006FC9E
0x18006fa63  lea     r8, [rbp+var_48]
0x18006fa67  lea     rdx, _GUID_0450ce77_af0d_40ac_93fd_1e5d48c89419
0x18006fa6e  mov     rcx, [rbp+string]
0x18006fa72  call    cs:__imp_RoGetActivationFactory
0x18006fa78  mov     rcx, [rbp+38h]
0x18006fa7c  test    eax, eax
0x18006fa7e  js      loc_18006FCB1
0x18006fa84  mov     [rbp+var_58], r14
0x18006fa88  mov     rcx, [rbp+var_48]
0x18006fa8c  mov     rax, [rcx]
0x18006fa8f  mov     [rbp+var_58], r14
0x18006fa93  lea     r8, [rbp+var_58]
0x18006fa97  mov     rdx, [rbx+110h]
0x18006fa9e  mov     rax, [rax+0D0h]
0x18006faa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006faaa  mov     rcx, [rbp+38h]; this
0x18006faae  test    eax, eax
0x18006fab0  js      loc_18006FCC6
0x18006fab6  mov     [rbp+var_60], r14d
0x18006faba  mov     rcx, [rbp+var_58]
0x18006fabe  mov     rax, [rcx]
0x18006fac1  lea     rdx, [rbp+var_60]
0x18006fac5  mov     rax, [rax+38h]
0x18006fac9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006face  mov     rcx, [rbp+38h]; this
0x18006fad2  test    eax, eax
0x18006fad4  js      loc_18006FCDB
0x18006fada  cmp     [rbp+var_60], r14d
0x18006fade  setnbe  al
0x18006fae1  mov     rcx, [rbp+38h]; this
0x18006fae5  test    al, al
0x18006fae7  jz      loc_18006FD49
0x18006faed  mov     ebx, r14d
0x18006faf0  mov     [rbp+var_40], rbx
0x18006faf4  mov     r12d, r14d
0x18006faf7  mov     rcx, [rbp+var_58]
0x18006fafb  mov     qword ptr [rbp+hstringHeader.Reserved], rcx
0x18006faff  lea     rax, [rbp+string]
0x18006fb03  mov     qword ptr [rbp+hstringHeader.Reserved+10h], rax
0x18006fb07  mov     dword ptr [rbp+string], r14d
0x18006fb0b  mov     [rbp+var_10], r14
0x18006fb0f  mov     rax, [rcx]
0x18006fb12  lea     rdx, [rbp+hstringHeader.Reserved+8]
0x18006fb16  mov     rax, [rax+38h]
0x18006fb1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fb1f  mov     ecx, eax
0x18006fb21  mov     rax, qword ptr [rbp+hstringHeader.Reserved+10h]
0x18006fb25  mov     [rax], ecx
0x18006fb27  xor     edx, edx
0x18006fb29  lea     rcx, [rbp+hstringHeader]
0x18006fb2d  call    ?get_at_current@?$vector_range_nothrow@U?$IVectorView@PEAVStoreAvailability@Store@Services@Windows@@@Collections@Foundation@Windows@@@wil@@QEAAXI@Z; wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<Windows::Services::Store::StoreAvailability *>>::get_at_current(uint)
0x18006fb32  mov     edi, r14d
0x18006fb35  mov     r13d, dword ptr [rbp+hstringHeader.Reserved+8]
0x18006fb39  mov     rax, qword ptr [rbp+hstringHeader.Reserved+10h]
0x18006fb3d  cmp     [rax], r14d
0x18006fb40  jge     loc_18006FC16
0x18006fb46  lea     rcx, [rbp+var_10]
0x18006fb4a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006fb4f  test    rbx, rbx
0x18006fb52  setz    al
0x18006fb55  mov     rcx, [rbp+38h]; this
0x18006fb59  test    al, al
0x18006fb5b  jnz     loc_18006FD05
0x18006fb61  mov     rax, [rbx]
0x18006fb64  mov     rdi, [rax+70h]
0x18006fb68  mov     rcx, [r15]; string
0x18006fb6b  call    cs:__imp_WindowsDeleteString
0x18006fb71  mov     [r15], r14
0x18006fb74  mov     rdx, r15
0x18006fb77  mov     rcx, rbx
0x18006fb7a  mov     rax, rdi
0x18006fb7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fb82  mov     rcx, [rbp+38h]; this
0x18006fb86  test    eax, eax
0x18006fb88  js      loc_18006FCF0
0x18006fb8e  test    rbx, rbx
0x18006fb91  jz      short loc_18006FBA3
0x18006fb93  mov     rax, [rbx]
0x18006fb96  mov     rcx, rbx
0x18006fb99  mov     rax, [rax+10h]
0x18006fb9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fba2  nop
0x18006fba3  mov     rcx, [rbp+var_58]
0x18006fba7  test    rcx, rcx
0x18006fbaa  jz      short loc_18006FBB9
0x18006fbac  mov     rax, [rcx]
0x18006fbaf  mov     rax, [rax+10h]
0x18006fbb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fbb8  nop
0x18006fbb9  mov     rcx, [rbp+var_48]
0x18006fbbd  test    rcx, rcx
0x18006fbc0  jz      short loc_18006FBCF
0x18006fbc2  mov     rax, [rcx]
0x18006fbc5  mov     rax, [rax+10h]
0x18006fbc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fbce  nop
0x18006fbcf  mov     [rsi], r14
0x18006fbd2  mov     rbx, [r15]
0x18006fbd5  xor     ecx, ecx; string
0x18006fbd7  call    cs:__imp_WindowsDeleteString
0x18006fbdd  mov     [rsi], r14
0x18006fbe0  mov     rdx, rsi; newString
0x18006fbe3  mov     rcx, rbx; string
0x18006fbe6  call    cs:__imp_WindowsDuplicateString
0x18006fbec  mov     rax, rsi
0x18006fbef  mov     rcx, [rbp+var_8]
0x18006fbf3  xor     rcx, rsp; StackCookie
0x18006fbf6  call    __security_check_cookie
0x18006fbfb  mov     rbx, [rsp+80h+arg_10]
0x18006fc03  add     rsp, 80h
0x18006fc0a  pop     r15
0x18006fc0c  pop     r14
0x18006fc0e  pop     r13
0x18006fc10  pop     r12
0x18006fc12  pop     rdi
0x18006fc13  pop     rsi
0x18006fc14  pop     rbp
0x18006fc15  retn
0x18006fc16  cmp     edi, r13d
0x18006fc19  jz      loc_18006FB46
0x18006fc1f  mov     [rbp+var_50], r14
0x18006fc23  mov     rcx, [rbp+var_10]
0x18006fc27  mov     rax, [rcx]
0x18006fc2a  lea     rdx, [rbp+var_50]
0x18006fc2e  mov     rax, [rax+68h]
0x18006fc32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fc37  mov     rcx, [rbp+38h]; this
0x18006fc3b  test    eax, eax
0x18006fc3d  js      short loc_18006FC89
0x18006fc3f  cmp     [rbp+var_50], r12
0x18006fc43  jbe     short loc_18006FC77
0x18006fc45  mov     r12, [rbp+var_50]
0x18006fc49  mov     rax, [rbp+var_10]
0x18006fc4d  mov     r14, rbx
0x18006fc50  mov     rbx, rax
0x18006fc53  mov     [rbp+var_40], rax
0x18006fc57  test    rax, rax
0x18006fc5a  jz      short loc_18006FC6B
0x18006fc5c  mov     rax, [rax]
0x18006fc5f  mov     rcx, rbx
0x18006fc62  mov     rax, [rax+8]
0x18006fc66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fc6b  test    r14, r14
0x18006fc6e  jnz     loc_18006FD1D
0x18006fc74  xor     r14d, r14d
0x18006fc77  inc     edi
0x18006fc79  mov     edx, edi
0x18006fc7b  lea     rcx, [rbp+hstringHeader]
0x18006fc7f  call    ?get_at_current@?$vector_range_nothrow@U?$IVectorView@PEAVStoreAvailability@Store@Services@Windows@@@Collections@Foundation@Windows@@@wil@@QEAAXI@Z; wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<Windows::Services::Store::StoreAvailability *>>::get_at_current(uint)
0x18006fc84  jmp     loc_18006FB39
0x18006fc89  mov     r9d, eax; char *
0x18006fc8c  lea     r8, aShellcommonShe_103; "shellcommon\\shell\\datastorecache\\tra"...
0x18006fc93  mov     edx, 57Bh; void *
0x18006fc98  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006fc9e  xor     r9d, r9d; lpArguments
0x18006fca1  xor     r8d, r8d; nNumberOfArguments
0x18006fca4  lea     edx, [r9+1]; dwExceptionFlags
0x18006fca8  mov     ecx, eax; dwExceptionCode
0x18006fcaa  call    cs:__imp_RaiseException
0x18006fcb0  nop
0x18006fcb1  mov     r9d, eax; char *
0x18006fcb4  lea     r8, aShellcommonShe_103; "shellcommon\\shell\\datastorecache\\tra"...
0x18006fcbb  mov     edx, 56Bh; void *
0x18006fcc0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006fcc6  mov     r9d, eax; char *
0x18006fcc9  lea     r8, aShellcommonShe_103; "shellcommon\\shell\\datastorecache\\tra"...
0x18006fcd0  mov     edx, 56Fh; void *
0x18006fcd5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006fcdb  mov     r9d, eax; char *
0x18006fcde  lea     r8, aShellcommonShe_103; "shellcommon\\shell\\datastorecache\\tra"...
0x18006fce5  mov     edx, 572h; void *
0x18006fcea  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006fcf0  mov     r9d, eax; char *
0x18006fcf3  lea     r8, aShellcommonShe_103; "shellcommon\\shell\\datastorecache\\tra"...
0x18006fcfa  mov     edx, 584h; void *
0x18006fcff  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006fd05  mov     r9d, 80070002h; char *
0x18006fd0b  lea     r8, aShellcommonShe_103; "shellcommon\\shell\\datastorecache\\tra"...
0x18006fd12  mov     edx, 583h; void *
0x18006fd17  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006fd1d  mov     rax, [r14]
0x18006fd20  mov     rcx, r14
0x18006fd23  mov     rax, [rax+10h]
0x18006fd27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fd2c  jmp     loc_18006FC74
0x18006fd31  mov     r9d, 80270254h; char *
0x18006fd37  lea     r8, aShellcommonShe_103; "shellcommon\\shell\\datastorecache\\tra"...
0x18006fd3e  mov     edx, 568h; void *
0x18006fd43  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006fd49  mov     r9d, 80070490h; char *
0x18006fd4f  lea     r8, aShellcommonShe_103; "shellcommon\\shell\\datastorecache\\tra"...
0x18006fd56  mov     edx, 573h; void *
0x18006fd5b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
