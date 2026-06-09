# BingMapsJson::ReverseGeocodeJsonParser::ParseCivicAddress(std::unique_ptr<__MIDL___MIDL_itf_locationcommondata_0000_0000_0019,std::default_delete<__MIDL___MIDL_itf_locationcommondata_0000_0000_0019>> &)

- ea: `0x180143f78`
- end: `0x1801446b4`
- name: `?ParseCivicAddress@ReverseGeocodeJsonParser@BingMapsJson@@QEAAJAEAV?$unique_ptr@U__MIDL___MIDL_itf_locationcommondata_0000_0000_0019@@U?$default_delete@U__MIDL___MIDL_itf_locationcommondata_0000_0000_0019@@@std@@@std@@@Z`
- size: `1852`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18011de80`

## callees

- `0x180014340`
- `0x1800448f4`
- `0x1800a98c0`
- `0x180143f78`
- `0x18015e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801442c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180144344`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801443b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180144429`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801444a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180144517`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18014458d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801442c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180144344`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801443b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180144429`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801444a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180144517`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18014458d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014427d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801442f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180144369`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801443df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180144457`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801444cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180144543`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801445af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801445bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801445cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801445d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801445e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801445f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180144603`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014427d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801442f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180144369`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801443df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180144457`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801444cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180144543`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801445af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801445bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801445cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801445d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801445e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801445f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180144603`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
__int64 __fastcall BingMapsJson::ReverseGeocodeJsonParser::ParseCivicAddress(__int64 *a1, unsigned __int16 **a2)
{
  __int64 v3; // rdi
  __int64 (__fastcall *v5)(__int64, __int64, __int64 *); // rbx
  int v6; // ebx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, __int64, __int64 *); // rbx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, __int64, __int64 *); // rbx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rdi
  int (__fastcall *v27)(__int64, __int64, HSTRING *); // rbx
  unsigned __int16 *StringRawBuffer; // rax
  __int64 v29; // rdi
  int (__fastcall *v30)(__int64, __int64, HSTRING *); // rbx
  unsigned __int16 *v31; // rax
  __int64 v32; // rdi
  int (__fastcall *v33)(__int64, __int64, HSTRING *); // rbx
  unsigned __int16 *v34; // rax
  __int64 v35; // rdi
  int (__fastcall *v36)(__int64, __int64, HSTRING *); // rbx
  unsigned __int16 *v37; // rax
  __int64 v38; // rdi
  int (__fastcall *v39)(__int64, __int64, HSTRING *); // rbx
  unsigned __int16 *v40; // rax
  __int64 v41; // rdi
  int (__fastcall *v42)(__int64, __int64, HSTRING *); // rbx
  unsigned __int16 *v43; // rax
  __int64 v44; // rdi
  int (__fastcall *v45)(__int64, __int64, HSTRING *); // rbx
  unsigned __int16 *v46; // rax
  __int64 v47; // rcx
  __int64 v48; // rcx
  __int64 v49; // rcx
  __int64 v50; // rcx
  __int64 v51; // rcx
  HSTRING_HEADER hstringHeader; // [rsp+20h] [rbp-59h] BYREF
  __int64 v53; // [rsp+38h] [rbp-41h]
  __int64 v54; // [rsp+40h] [rbp-39h] BYREF
  __int64 v55; // [rsp+48h] [rbp-31h] BYREF
  __int64 v56; // [rsp+50h] [rbp-29h] BYREF
  __int64 v57; // [rsp+58h] [rbp-21h] BYREF
  __int64 v58; // [rsp+60h] [rbp-19h] BYREF
  HSTRING v59; // [rsp+68h] [rbp-11h] BYREF
  HSTRING v60; // [rsp+70h] [rbp-9h] BYREF
  HSTRING v61; // [rsp+78h] [rbp-1h] BYREF
  HSTRING v62; // [rsp+80h] [rbp+7h] BYREF
  HSTRING v63; // [rsp+88h] [rbp+Fh] BYREF
  HSTRING v64; // [rsp+90h] [rbp+17h] BYREF
  HSTRING string; // [rsp+98h] [rbp+1Fh] BYREF

  v3 = *a1;
  if ( !*a1 )
    return 2147942413LL;
  v54 = 0;
  v5 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v3 + 72LL);
  v53 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"resourceSets", 0xDu, 0xCu);
  v6 = v5(v3, v53, &v54);
  if ( v6 < 0 )
  {
    v7 = v54;
    if ( v54 )
    {
      v54 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    }
    return (unsigned int)v6;
  }
  v56 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v54 + 48LL))(v54, 0, &v56);
  if ( v6 < 0 )
  {
    v8 = v56;
    if ( v56 )
    {
      v56 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
    v9 = v54;
    if ( v54 )
    {
      v54 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
    return (unsigned int)v6;
  }
  v57 = 0;
  v10 = v56;
  v11 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v56 + 72LL);
  v53 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"resources", 0xAu, 9u);
  v6 = v11(v10, v53, &v57);
  if ( v6 < 0 )
  {
    v12 = v57;
    if ( v57 )
    {
      v57 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
    v13 = v56;
    if ( v56 )
    {
      v56 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    v14 = v54;
    if ( v54 )
    {
      v54 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    return (unsigned int)v6;
  }
  v58 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v57 + 48LL))(v57, 0, &v58);
  if ( v6 < 0 )
  {
    v15 = v58;
    if ( v58 )
    {
      v58 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
    v16 = v57;
    if ( v57 )
    {
      v57 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
    v17 = v56;
    if ( v56 )
    {
      v56 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    v18 = v54;
    if ( v54 )
    {
      v54 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    return (unsigned int)v6;
  }
  v55 = 0;
  v19 = v58;
  v20 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v58 + 64LL);
  v53 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"address", 8u, 7u);
  v6 = v20(v19, v53, &v55);
  if ( v6 < 0 )
  {
    v21 = v55;
    if ( v55 )
    {
      v55 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    }
    v22 = v58;
    if ( v58 )
    {
      v58 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    }
    v23 = v57;
    if ( v57 )
    {
      v57 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    }
    v24 = v56;
    if ( v56 )
    {
      v56 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    }
    v25 = v54;
    if ( v54 )
    {
      v54 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    }
    return (unsigned int)v6;
  }
  string = 0;
  v26 = v55;
  v27 = *(int (__fastcall **)(__int64, __int64, HSTRING *))(*(_QWORD *)v55 + 80LL);
  WindowsDeleteString(0);
  string = 0;
  v53 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"formattedAddress", 0x11u, 0x10u);
  if ( v27(v26, v53, &string) >= 0 )
  {
    StringRawBuffer = (unsigned __int16 *)WindowsGetStringRawBuffer(string, 0);
    StringCchCopyW(*a2 + 395, 0x100u, StringRawBuffer);
  }
  v64 = 0;
  v29 = v55;
  v30 = *(int (__fastcall **)(__int64, __int64, HSTRING *))(*(_QWORD *)v55 + 80LL);
  WindowsDeleteString(0);
  v64 = 0;
  v53 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"addressLine", 0xCu, 0xBu);
  if ( v30(v29, v53, &v64) >= 0 )
  {
    v31 = (unsigned __int16 *)WindowsGetStringRawBuffer(v64, 0);
    StringCchCopyW(*a2, 0x4Cu, v31);
  }
  v63 = 0;
  v32 = v55;
  v33 = *(int (__fastcall **)(__int64, __int64, HSTRING *))(*(_QWORD *)v55 + 80LL);
  WindowsDeleteString(0);
  v63 = 0;
  v53 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"adminDistrict", 0xEu, 0xDu);
  if ( v33(v32, v53, &v63) >= 0 )
  {
    v34 = (unsigned __int16 *)WindowsGetStringRawBuffer(v63, 0);
    StringCchCopyW(*a2 + 228, 0x4Cu, v34);
  }
  v62 = 0;
  v35 = v55;
  v36 = *(int (__fastcall **)(__int64, __int64, HSTRING *))(*(_QWORD *)v55 + 80LL);
  WindowsDeleteString(0);
  v62 = 0;
  v53 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"countryRegionIso2", 0x12u, 0x11u);
  if ( v36(v35, v53, &v62) >= 0 )
  {
    v37 = (unsigned __int16 *)WindowsGetStringRawBuffer(v62, 0);
    StringCchCopyW(*a2 + 651, 0xBu, v37);
  }
  v61 = 0;
  v38 = v55;
  v39 = *(int (__fastcall **)(__int64, __int64, HSTRING *))(*(_QWORD *)v55 + 80LL);
  WindowsDeleteString(0);
  v61 = 0;
  v53 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"countryRegion", 0xEu, 0xDu);
  if ( v39(v38, v53, &v61) >= 0 )
  {
    v40 = (unsigned __int16 *)WindowsGetStringRawBuffer(v61, 0);
    StringCchCopyW(*a2 + 304, 0x4Cu, v40);
  }
  v60 = 0;
  v41 = v55;
  v42 = *(int (__fastcall **)(__int64, __int64, HSTRING *))(*(_QWORD *)v55 + 80LL);
  WindowsDeleteString(0);
  v60 = 0;
  v53 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"locality", 9u, 8u);
  if ( v42(v41, v53, &v60) >= 0 )
  {
    v43 = (unsigned __int16 *)WindowsGetStringRawBuffer(v60, 0);
    StringCchCopyW(*a2 + 152, 0x4Cu, v43);
  }
  v59 = 0;
  v44 = v55;
  v45 = *(int (__fastcall **)(__int64, __int64, HSTRING *))(*(_QWORD *)v55 + 80LL);
  WindowsDeleteString(0);
  v59 = 0;
  v53 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"postalCode", 0xBu, 0xAu);
  if ( v45(v44, v53, &v59) >= 0 )
  {
    v46 = (unsigned __int16 *)WindowsGetStringRawBuffer(v59, 0);
    StringCchCopyW(*a2 + 380, 0xFu, v46);
  }
  WindowsDeleteString(v59);
  v59 = 0;
  WindowsDeleteString(v60);
  v60 = 0;
  WindowsDeleteString(v61);
  v61 = 0;
  WindowsDeleteString(v62);
  v62 = 0;
  WindowsDeleteString(v63);
  v63 = 0;
  WindowsDeleteString(v64);
  v64 = 0;
  WindowsDeleteString(string);
  string = 0;
  v47 = v55;
  if ( v55 )
  {
    v55 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
  }
  v48 = v58;
  if ( v58 )
  {
    v58 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
  }
  v49 = v57;
  if ( v57 )
  {
    v57 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
  }
  v50 = v56;
  if ( v56 )
  {
    v56 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
  }
  v51 = v54;
  if ( v54 )
  {
    v54 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
  }
  return 0;
}

```

## disassembly

```asm
0x180143f78  mov     [rsp-8+arg_10], rbx
0x180143f7d  push    rbp
0x180143f7e  push    rsi
0x180143f7f  push    rdi
0x180143f80  push    r14
0x180143f82  push    r15
0x180143f84  lea     rbp, [rsp-37h]
0x180143f89  sub     rsp, 0B0h
0x180143f90  mov     rax, cs:__security_cookie
0x180143f97  xor     rax, rsp
0x180143f9a  mov     [rbp+57h+var_30], rax
0x180143f9e  mov     rsi, rdx
0x180143fa1  mov     rdi, [rcx]
0x180143fa4  xor     r14d, r14d
0x180143fa7  test    rdi, rdi
0x180143faa  jnz     short loc_180143FB6
0x180143fac  mov     eax, 8007000Dh
0x180143fb1  jmp     loc_180144691
0x180143fb6  mov     [rbp+57h+var_90], r14
0x180143fba  mov     rax, [rdi]
0x180143fbd  mov     rbx, [rax+48h]
0x180143fc1  mov     [rbp+57h+var_98], r14
0x180143fc5  mov     r15d, 0Ch
0x180143fcb  mov     r9d, r15d; unsigned int
0x180143fce  lea     r8d, [r15+1]; unsigned int
0x180143fd2  lea     rdx, aResourcesets; "resourceSets"
0x180143fd9  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180143fdd  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180143fe2  nop
0x180143fe3  lea     r8, [rbp+57h+var_90]
0x180143fe7  mov     rdx, [rbp+57h+var_98]
0x180143feb  mov     rcx, rdi
0x180143fee  mov     rax, rbx
0x180143ff1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180143ff6  mov     ebx, eax
0x180143ff8  test    eax, eax
0x180143ffa  jns     short loc_18014401D
0x180143ffc  mov     rcx, [rbp+57h+var_90]
0x180144000  test    rcx, rcx
0x180144003  jz      short loc_180144016
0x180144005  mov     [rbp+57h+var_90], r14
0x180144009  mov     rdx, [rcx]
0x18014400c  mov     rax, [rdx+10h]
0x180144010  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180144015  nop
0x180144016  mov     eax, ebx
0x180144018  jmp     loc_180144691
0x18014401d  mov     [rbp+57h+var_80], r14
0x180144021  mov     rcx, [rbp+57h+var_90]
0x180144025  mov     rax, [rcx]
0x180144028  lea     r8, [rbp+57h+var_80]
0x18014402c  xor     edx, edx
0x18014402e  mov     rax, [rax+30h]
0x180144032  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180144037  mov     ebx, eax
0x180144039  test    eax, eax
0x18014403b  jns     short loc_180144073
0x18014403d  mov     rcx, [rbp+57h+var_80]
0x180144041  test    rcx, rcx
0x180144044  jz      short loc_180144057
0x180144046  mov     [rbp+57h+var_80], r14
0x18014404a  mov     rdx, [rcx]
0x18014404d  mov     rax, [rdx+10h]
0x180144051  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180144056  nop
0x180144057  mov     rcx, [rbp+57h+var_90]
0x18014405b  test    rcx, rcx
0x18014405e  jz      short loc_180144071
0x180144060  mov     [rbp+57h+var_90], r14
0x180144064  mov     rax, [rcx]
0x180144067  mov     rax, [rax+10h]
0x18014406b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180144070  nop
0x180144071  jmp     short loc_180144016
0x180144073  mov     [rbp+57h+var_78], r14
0x180144077  mov     rdi, [rbp+57h+var_80]
0x18014407b  mov     rax, [rdi]
0x18014407e  mov     rbx, [rax+48h]
0x180144082  mov     [rbp+57h+var_98], r14
0x180144086  mov     r9d, 9; unsigned int
0x18014408c  lea     r8d, [r9+1]; unsigned int
0x180144090  lea     rdx, aResources; "resources"
0x180144097  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18014409b  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801440a0  nop
0x1801440a1  lea     r8, [rbp+57h+var_78]
0x1801440a5  mov     rdx, [rbp+57h+var_98]
0x1801440a9  mov     rcx, rdi
0x1801440ac  mov     rax, rbx
0x1801440af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801440b4  mov     ebx, eax
0x1801440b6  test    eax, eax
0x1801440b8  jns     short loc_18014410D
0x1801440ba  mov     rcx, [rbp+57h+var_78]
0x1801440be  test    rcx, rcx
0x1801440c1  jz      short loc_1801440D4
0x1801440c3  mov     [rbp+57h+var_78], r14
0x1801440c7  mov     rdx, [rcx]
0x1801440ca  mov     rax, [rdx+10h]
0x1801440ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801440d3  nop
0x1801440d4  mov     rcx, [rbp+57h+var_80]
0x1801440d8  test    rcx, rcx
0x1801440db  jz      short loc_1801440EE
0x1801440dd  mov     [rbp+57h+var_80], r14
0x1801440e1  mov     rax, [rcx]
0x1801440e4  mov     rax, [rax+10h]
0x1801440e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801440ed  nop
0x1801440ee  mov     rcx, [rbp+57h+var_90]
0x1801440f2  test    rcx, rcx
0x1801440f5  jz      short loc_180144108
0x1801440f7  mov     [rbp+57h+var_90], r14
0x1801440fb  mov     rax, [rcx]
0x1801440fe  mov     rax, [rax+10h]
0x180144102  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180144107  nop
0x180144108  jmp     loc_180144016
0x18014410d  mov     [rbp+57h+var_70], r14
0x180144111  mov     rcx, [rbp+57h+var_78]
0x180144115  mov     rax, [rcx]
0x180144118  lea     r8, [rbp+57h+var_70]
0x18014411c  xor     edx, edx
0x18014411e  mov     rax, [rax+30h]
0x180144122  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180144127  mov     ebx, eax
0x180144129  test    eax, eax
0x18014412b  jns     short loc_18014419A
0x18014412d  mov     rcx, [rbp+57h+var_70]
0x180144131  test    rcx, rcx
0x180144134  jz      short loc_180144147
0x180144136  mov     [rbp+57h+var_70], r14
0x18014413a  mov     rdx, [rcx]
0x18014413d  mov     rax, [rdx+10h]
0x180144141  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180144146  nop
0x180144147  mov     rcx, [rbp+57h+var_78]
0x18014414b  test    rcx, rcx
0x18014414e  jz      short loc_180144161
0x180144150  mov     [rbp+57h+var_78], r14
0x180144154  mov     rax, [rcx]
0x180144157  mov     rax, [rax+10h]
0x18014415b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180144160  nop
0x180144161  mov     rcx, [rbp+57h+var_80]
0x180144165  test    rcx, rcx
0x180144168  jz      short loc_18014417B
0x18014416a  mov     [rbp+57h+var_80], r14
0x18014416e  mov     rax, [rcx]
0x180144171  mov     rax, [rax+10h]
0x180144175  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014417a  nop
0x18014417b  mov     rcx, [rbp+57h+var_90]
0x18014417f  test    rcx, rcx
0x180144182  jz      short loc_180144195
0x180144184  mov     [rbp+57h+var_90], r14
0x180144188  mov     rax, [rcx]
0x18014418b  mov     rax, [rax+10h]
0x18014418f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180144194  nop
0x180144195  jmp     loc_180144016
0x18014419a  mov     [rbp+57h+var_88], r14
0x18014419e  mov     rdi, [rbp+57h+var_70]
0x1801441a2  mov     rax, [rdi]
0x1801441a5  mov     rbx, [rax+40h]
0x1801441a9  mov     [rbp+57h+var_98], r14
0x1801441ad  mov     r9d, 7; unsigned int
0x1801441b3  lea     r8d, [r9+1]; unsigned int
0x1801441b7  lea     rdx, aAddress; "address"
0x1801441be  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1801441c2  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801441c7  nop
0x1801441c8  lea     r8, [rbp+57h+var_88]
0x1801441cc  mov     rdx, [rbp+57h+var_98]
0x1801441d0  mov     rcx, rdi
0x1801441d3  mov     rax, rbx
0x1801441d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801441db  mov     ebx, eax
0x1801441dd  test    eax, eax
0x1801441df  jns     loc_18014426C
0x1801441e5  mov     rcx, [rbp+57h+var_88]
0x1801441e9  test    rcx, rcx
0x1801441ec  jz      short loc_1801441FF
0x1801441ee  mov     [rbp+57h+var_88], r14
0x1801441f2  mov     rdx, [rcx]
0x1801441f5  mov     rax, [rdx+10h]
0x1801441f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801441fe  nop
0x1801441ff  mov     rcx, [rbp+57h+var_70]
0x180144203  test    rcx, rcx
0x180144206  jz      short loc_180144219
0x180144208  mov     [rbp+57h+var_70], r14
0x18014420c  mov     rax, [rcx]
0x18014420f  mov     rax, [rax+10h]
0x180144213  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180144218  nop
0x180144219  mov     rcx, [rbp+57h+var_78]
0x18014421d  test    rcx, rcx
0x180144220  jz      short loc_180144233
0x180144222  mov     [rbp+57h+var_78], r14
0x180144226  mov     rax, [rcx]
0x180144229  mov     rax, [rax+10h]
0x18014422d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180144232  nop
0x180144233  mov     rcx, [rbp+57h+var_80]
0x180144237  test    rcx, rcx
0x18014423a  jz      short loc_18014424D
0x18014423c  mov     [rbp+57h+var_80], r14
0x180144240  mov     rax, [rcx]
0x180144243  mov     rax, [rax+10h]
0x180144247  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014424c  nop
0x18014424d  mov     rcx, [rbp+57h+var_90]
0x180144251  test    rcx, rcx
0x180144254  jz      short loc_180144267
0x180144256  mov     [rbp+57h+var_90], r14
0x18014425a  mov     rax, [rcx]
0x18014425d  mov     rax, [rax+10h]
0x180144261  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180144266  nop
0x180144267  jmp     loc_180144016
0x18014426c  mov     [rbp+57h+string], r14
0x180144270  mov     rdi, [rbp+57h+var_88]
0x180144274  mov     rax, [rdi]
0x180144277  mov     rbx, [rax+50h]
0x18014427b  xor     ecx, ecx; string
0x18014427d  call    cs:__imp_WindowsDeleteString
0x180144283  mov     [rbp+57h+string], r14
0x180144287  mov     [rbp+57h+var_98], r14
0x18014428b  mov     r9d, 10h; unsigned int
0x180144291  lea     r8d, [r9+1]; unsigned int
0x180144295  lea     rdx, aFormattedaddre; "formattedAddress"
0x18014429c  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1801442a0  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801442a5  nop
0x1801442a6  lea     r8, [rbp+57h+string]
0x1801442aa  mov     rdx, [rbp+57h+var_98]
0x1801442ae  mov     rcx, rdi
0x1801442b1  mov     rax, rbx
0x1801442b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801442b9  nop
0x1801442ba  shr     eax, 1Fh
0x1801442bd  xor     al, 1
0x1801442bf  jz      short loc_1801442E4
0x1801442c1  xor     edx, edx; length
0x1801442c3  mov     rcx, [rbp+57h+string]; string
0x1801442c7  call    cs:__imp_WindowsGetStringRawBuffer
0x1801442cd  mov     rcx, [rsi]
0x1801442d0  add     rcx, 316h; unsigned __int16 *
0x1801442d7  mov     r8, rax; unsigned __int16 *
0x1801442da  mov     edx, 100h; unsigned __int64
0x1801442df  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1801442e4  mov     [rbp+57h+var_40], r14
0x1801442e8  mov     rdi, [rbp+57h+var_88]
0x1801442ec  mov     rax, [rdi]
0x1801442ef  mov     rbx, [rax+50h]
0x1801442f3  xor     ecx, ecx; string
0x1801442f5  call    cs:__imp_WindowsDeleteString
0x1801442fb  mov     [rbp+57h+var_40], r14
0x1801442ff  mov     [rbp+57h+var_98], r14
0x180144303  mov     r9d, 0Bh; unsigned int
0x180144309  mov     r8d, r15d; unsigned int
0x18014430c  lea     rdx, aAddressline; "addressLine"
0x180144313  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180144317  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18014431c  nop
0x18014431d  lea     r8, [rbp+57h+var_40]
0x180144321  mov     rdx, [rbp+57h+var_98]
0x180144325  mov     rcx, rdi
0x180144328  mov     rax, rbx
0x18014432b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180144330  nop
0x180144331  shr     eax, 1Fh
0x180144334  mov     r15d, 4Ch ; 'L'
0x18014433a  xor     al, 1
0x18014433c  jz      short loc_180144358
0x18014433e  xor     edx, edx; length
0x180144340  mov     rcx, [rbp+57h+var_40]; string
0x180144344  call    cs:__imp_WindowsGetStringRawBuffer
0x18014434a  mov     r8, rax; unsigned __int16 *
0x18014434d  mov     edx, r15d; unsigned __int64
0x180144350  mov     rcx, [rsi]; unsigned __int16 *
0x180144353  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180144358  mov     [rbp+57h+var_48], r14
0x18014435c  mov     rdi, [rbp+57h+var_88]
0x180144360  mov     rax, [rdi]
0x180144363  mov     rbx, [rax+50h]
0x180144367  xor     ecx, ecx; string
0x180144369  call    cs:__imp_WindowsDeleteString
0x18014436f  mov     [rbp+57h+var_48], r14
0x180144373  mov     [rbp+57h+var_98], r14
0x180144377  mov     r9d, 0Dh; unsigned int
0x18014437d  lea     r8d, [r9+1]; unsigned int
0x180144381  lea     rdx, aAdmindistrict; "adminDistrict"
0x180144388  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18014438c  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180144391  nop
0x180144392  lea     r8, [rbp+57h+var_48]
0x180144396  mov     rdx, [rbp+57h+var_98]
0x18014439a  mov     rcx, rdi
  ... truncated ...
```
