# _lambda_1892f77f5bd001fd775bf723ec43e763_::operator()(Windows::Internal::CHSTRINGResult &)

- ea: `0x1800109c8`
- end: `0x180010b37`
- name: `??R_lambda_1892f77f5bd001fd775bf723ec43e763_@@QEBAJAEAVCHSTRINGResult@Internal@Windows@@@Z`
- size: `367`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18009b990`

## callees

- `0x180005174`
- `0x180010810`
- `0x1800109c8`
- `0x180010c8c`
- `0x1800124a8`
- `0x18001a540`
- `0x1800dc010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180010a0a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180010a0a`

## string_xrefs

- `0x180010a1f`: `onecoreuap\shell\cloudexperiencehost\onecore\winrtapi\commoncoreutilstatics.cpp`
- `0x180010a67`: `onecoreuap\shell\cloudexperiencehost\onecore\winrtapi\commoncoreutilstatics.cpp`
- `0x180010ab3`: `onecoreuap\shell\cloudexperiencehost\onecore\winrtapi\commoncoreutilstatics.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall _lambda_1892f77f5bd001fd775bf723ec43e763_::operator()(__int64 a1, __int64 a2)
{
  HRESULT v3; // eax
  __int64 v4; // rax
  int v5; // eax
  int v6; // eax
  char v7; // r8
  HSTRING v8; // rcx
  const char *v9; // r9
  __int64 result; // rax
  int ppv; // [rsp+20h] [rbp-68h]
  int v12; // [rsp+30h] [rbp-58h] BYREF
  __int64 v13; // [rsp+38h] [rbp-50h] BYREF
  LPVOID v14; // [rsp+40h] [rbp-48h] BYREF
  HSTRING Reserved1; // [rsp+48h] [rbp-40h] BYREF
  HSTRING v16; // [rsp+50h] [rbp-38h] BYREF
  HSTRING_HEADER v17; // [rsp+58h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v14 = 0;
  v3 = CoCreateInstance(&CLSID_FlightClientAPI, 0, 1u, &GUID_79588f37_5be1_4a35_b23d_29832257cada, &v14);
  try
  {
    if ( v3 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x7D,
        (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\commoncoreutilstatics.cpp",
        (const char *)(unsigned int)v3,
        ppv);
    v13 = 0;
    v4 = *(_QWORD *)v14;
    v13 = 0;
    v5 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(v4 + 32))(v14, &v13);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x80,
        (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\commoncoreutilstatics.cpp",
        (const char *)(unsigned int)v5,
        ppv);
    v16 = 0;
    v12 = 0;
    v6 = (*(__int64 (__fastcall **)(__int64, HSTRING *, int *))(*(_QWORD *)v13 + 32LL))(v13, &v16, &v12);
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x85,
        (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\commoncoreutilstatics.cpp",
        (const char *)(unsigned int)v6,
        ppv);
    v8 = (HSTRING)&dword_1800F98D4;
    if ( v16 )
      v8 = v16;
    Reserved1 = v8;
    Reserved1 = (HSTRING)Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                           &v17,
                           (const WCHAR **)&Reserved1,
                           v7)[1].Reserved.Reserved1;
    Microsoft::WRL::Wrappers::HString::Set((HSTRING *)(a2 + 16), &Reserved1);
    wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(&v13);
    wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(&v14);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x88,
                           (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\commoncoreutilstatics.cpp",
                           v9);
  }
  return result;
}

```

## disassembly

```asm
0x1800109c8  push    rbx
0x1800109ca  sub     rsp, 80h
0x1800109d1  mov     rax, cs:__security_cookie
0x1800109d8  xor     rax, rsp
0x1800109db  mov     [rsp+88h+var_10], rax
0x1800109e0  mov     rbx, rdx
0x1800109e3  mov     [rsp+88h+var_48], 0
0x1800109ec  lea     rax, [rsp+88h+var_48]
0x1800109f1  mov     qword ptr [rsp+88h+ppv], rax; int
0x1800109f6  lea     r9, _GUID_79588f37_5be1_4a35_b23d_29832257cada; riid
0x1800109fd  xor     edx, edx; pUnkOuter
0x1800109ff  lea     r8d, [rdx+1]; dwClsContext
0x180010a03  lea     rcx, CLSID_FlightClientAPI; rclsid
0x180010a0a  call    cs:__imp_CoCreateInstance
0x180010a10  mov     rcx, [rsp+88h]; this
0x180010a18  test    eax, eax
0x180010a1a  jns     short loc_180010A30
0x180010a1c  mov     r9d, eax; char *
0x180010a1f  lea     r8, aOnecoreuapShel_23; "onecoreuap\\shell\\cloudexperiencehost"...
0x180010a26  mov     edx, 7Dh ; '}'; void *
0x180010a2b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180010a30  mov     [rsp+88h+var_50], 0
0x180010a39  mov     rcx, [rsp+88h+var_48]
0x180010a3e  mov     rax, [rcx]
0x180010a41  mov     [rsp+88h+var_50], 0
0x180010a4a  lea     rdx, [rsp+88h+var_50]
0x180010a4f  mov     rax, [rax+20h]
0x180010a53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a58  mov     rcx, [rsp+88h]; this
0x180010a60  test    eax, eax
0x180010a62  jns     short loc_180010A78
0x180010a64  mov     r9d, eax; char *
0x180010a67  lea     r8, aOnecoreuapShel_23; "onecoreuap\\shell\\cloudexperiencehost"...
0x180010a6e  mov     edx, 80h; void *
0x180010a73  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180010a78  mov     [rsp+88h+var_38], 0
0x180010a81  mov     [rsp+88h+var_58], 0
0x180010a89  mov     rcx, [rsp+88h+var_50]
0x180010a8e  mov     rax, [rcx]
0x180010a91  lea     r8, [rsp+88h+var_58]
0x180010a96  lea     rdx, [rsp+88h+var_38]
0x180010a9b  mov     rax, [rax+20h]
0x180010a9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010aa4  mov     rcx, [rsp+88h]; this
0x180010aac  test    eax, eax
0x180010aae  jns     short loc_180010AC4
0x180010ab0  mov     r9d, eax; char *
0x180010ab3  lea     r8, aOnecoreuapShel_23; "onecoreuap\\shell\\cloudexperiencehost"...
0x180010aba  mov     edx, 85h; void *
0x180010abf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180010ac4  lea     rcx, dword_1800F98D4
0x180010acb  mov     rax, [rsp+88h+var_38]
0x180010ad0  test    rax, rax
0x180010ad3  cmovnz  rcx, rax
0x180010ad7  mov     [rsp+88h+var_40], rcx
0x180010adc  lea     rdx, [rsp+88h+var_40]
0x180010ae1  lea     rcx, [rsp+88h+var_30]
0x180010ae6  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180010aeb  mov     rcx, [rax+18h]
0x180010aef  mov     [rsp+88h+var_40], rcx
0x180010af4  lea     rcx, [rbx+10h]; newString
0x180010af8  lea     rdx, [rsp+88h+var_40]; HSTRING *
0x180010afd  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x180010b02  nop
0x180010b03  lea     rcx, [rsp+88h+var_50]
0x180010b08  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVLaunchUriResult@System@Windows@@@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(void)
0x180010b0d  nop
0x180010b0e  lea     rcx, [rsp+88h+var_48]
0x180010b13  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVLaunchUriResult@System@Windows@@@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(void)
0x180010b18  nop
0x180010b19  xor     eax, eax
0x180010b1b  jmp     short loc_180010B21
0x180010b1d  mov     eax, [rsp+88h+var_58]
0x180010b21  mov     rcx, [rsp+88h+var_10]
0x180010b26  xor     rcx, rsp; StackCookie
0x180010b29  call    __security_check_cookie
0x180010b2e  add     rsp, 80h
0x180010b35  pop     rbx
0x180010b36  retn
```
