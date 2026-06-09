# RoutingApplicationInfo::GetPackageDisplayName(ushort const *,ushort * const)

- ea: `0x18003cee0`
- end: `0x18003d3e2`
- name: `?GetPackageDisplayName@RoutingApplicationInfo@@UEAAJPEBGQEAG@Z`
- size: `1282`
- prototype: `__int64 __fastcall(RoutingApplicationInfo *__hidden this, const unsigned __int16 *, unsigned __int16 *const)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180041820`

## callees

- `0x1800049a0`
- `0x18000c964`
- `0x18001e61c`
- `0x1800201ec`
- `0x18003cee0`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003d14e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003d18a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003d25c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003d2bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003d14e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003d18a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003d25c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003d2bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003cf29`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003cf29`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003d1f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003d1f2`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003cf63`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003cf63`

## string_xrefs

- `0x18003cf76`: `onecoreuap\ds\nfc\product\semanagement\common\routingmgr\src\routingapplicationinfo.cpp`
- `0x18003cfe9`: `onecoreuap\ds\nfc\product\semanagement\common\routingmgr\src\routingapplicationinfo.cpp`
- `0x18003d059`: `onecoreuap\ds\nfc\product\semanagement\common\routingmgr\src\routingapplicationinfo.cpp`
- `0x18003d0d5`: `onecoreuap\ds\nfc\product\semanagement\common\routingmgr\src\routingapplicationinfo.cpp`
- `0x18003d174`: `onecoreuap\ds\nfc\product\semanagement\common\routingmgr\src\routingapplicationinfo.cpp`
- `0x18003d246`: `onecoreuap\ds\nfc\product\semanagement\common\routingmgr\src\routingapplicationinfo.cpp`
- `0x18003d38f`: `onecoreuap\ds\nfc\product\semanagement\common\routingmgr\src\routingapplicationinfo.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall RoutingApplicationInfo::GetPackageDisplayName(
        RoutingApplicationInfo *this,
        unsigned __int16 *a2,
        unsigned __int16 *const a3)
{
  unsigned __int16 *v4; // r14
  HRESULT v5; // eax
  int v6; // edx
  unsigned int v7; // r8d
  int ActivationFactory; // eax
  unsigned int v9; // ebx
  __int64 v10; // rcx
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, _QWORD, __int64 *); // rbx
  __int64 v14; // rax
  int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // rcx
  int v18; // eax
  __int64 v19; // rcx
  __int64 v20; // rcx
  int v21; // eax
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, HSTRING *); // rbx
  int v27; // eax
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rbx
  PCWSTR StringRawBuffer; // rax
  __int64 v33; // rdx
  unsigned __int16 v34; // cx
  unsigned __int16 *v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rcx
  __int64 v39; // rcx
  __int64 v40; // rcx
  __int64 v41; // rcx
  __int64 v42; // rbx
  __int64 v43; // rdx
  unsigned __int16 v44; // ax
  unsigned __int16 *v45; // rcx
  __int64 v46; // rcx
  __int64 v47; // rcx
  __int64 v48; // [rsp+20h] [rbp-50h] BYREF
  __int64 v49; // [rsp+28h] [rbp-48h] BYREF
  HSTRING v50; // [rsp+30h] [rbp-40h] BYREF
  __int64 v51; // [rsp+38h] [rbp-38h] BYREF
  int v52; // [rsp+40h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-28h] BYREF
  HSTRING string; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  v4 = a2;
  v50 = (HSTRING)a2;
  v48 = 0;
  string = 0;
  v5 = WindowsCreateStringReference(L"Windows.Internal.StateRepository.Application", 0x2Cu, &hstringHeader, &string);
  if ( v5 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v5, v6, v7);
    JUMPOUT(0x18003D3E1LL);
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_07adcc9a_e505_48c2_b471_45af8561f6af, &v48);
  v9 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\routingmgr\\src\\routingapplicationinfo.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v48);
    v10 = v48;
    if ( v48 )
    {
      v48 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
    return v9;
  }
  v49 = 0;
  v12 = v48;
  v13 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v48 + 256LL);
  v14 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v50);
  v15 = v13(v12, *(_QWORD *)(v14 + 24), &v49);
  v9 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\routingmgr\\src\\routingapplicationinfo.cpp",
      (const char *)(unsigned int)v15,
      v48);
    v16 = v49;
    if ( v49 )
    {
      v49 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
    v17 = v48;
    if ( v48 )
    {
      v48 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    return v9;
  }
  v52 = 0;
  v18 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v49 + 56LL))(v49, &v52);
  v9 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x30,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\routingmgr\\src\\routingapplicationinfo.cpp",
      (const char *)(unsigned int)v18,
      v48);
    v19 = v49;
    if ( v49 )
    {
      v49 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
    v20 = v48;
    if ( v48 )
    {
      v48 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    }
    return v9;
  }
  if ( v52 )
  {
    v51 = 0;
    v21 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v49 + 48LL))(v49, 0, &v51);
    v9 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x37,
        (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\routingmgr\\src\\routingapplicationinfo.cpp",
        (const char *)(unsigned int)v21,
        v48);
      v22 = v51;
      if ( v51 )
      {
        v51 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
      }
      v23 = v49;
      if ( v49 )
      {
        v49 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
      }
      v24 = v48;
      if ( v48 )
      {
        v48 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
      }
      return v9;
    }
    v50 = 0;
    v25 = v51;
    v26 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v51 + 632LL);
    WindowsDeleteString(0);
    v50 = 0;
    v27 = v26(v25, &v50);
    v9 = v27;
    if ( v27 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3A,
        (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\routingmgr\\src\\routingapplicationinfo.cpp",
        (const char *)(unsigned int)v27,
        v48);
      WindowsDeleteString(v50);
      v50 = 0;
      v28 = v51;
      if ( v51 )
      {
        v51 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
      }
      v29 = v49;
      if ( v49 )
      {
        v49 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
      }
      v30 = v48;
      if ( v48 )
      {
        v48 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
      }
      return v9;
    }
    v31 = 2147483646;
    StringRawBuffer = WindowsGetStringRawBuffer(v50, 0);
    v33 = 260;
    do
    {
      if ( !v31 )
        break;
      v34 = *StringRawBuffer;
      if ( !*StringRawBuffer )
        break;
      ++StringRawBuffer;
      *a3++ = v34;
      --v31;
      --v33;
    }
    while ( v33 );
    v9 = v33 == 0 ? 0x8007007A : 0;
    v35 = a3 - 1;
    if ( v33 )
      v35 = a3;
    *v35 = 0;
    if ( !v33 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3C,
        (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\routingmgr\\src\\routingapplicationinfo.cpp",
        (const char *)v9,
        v48);
      WindowsDeleteString(v50);
      v50 = 0;
      v36 = v51;
      if ( v51 )
      {
        v51 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
      }
      v37 = v49;
      if ( v49 )
      {
        v49 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
      }
      v38 = v48;
      if ( v48 )
      {
        v48 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
      }
      return v9;
    }
    WindowsDeleteString(v50);
    v50 = 0;
    v39 = v51;
    if ( v51 )
    {
      v51 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
    }
  }
  else
  {
    v42 = 2147483646;
    v43 = 260;
    do
    {
      if ( !v42 )
        break;
      v44 = *v4;
      if ( !*v4 )
        break;
      ++v4;
      *a3++ = v44;
      --v42;
      --v43;
    }
    while ( v43 );
    v9 = v43 == 0 ? 0x8007007A : 0;
    v45 = a3 - 1;
    if ( v43 )
      v45 = a3;
    *v45 = 0;
    if ( !v43 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x40,
        (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\routingmgr\\src\\routingapplicationinfo.cpp",
        (const char *)v9,
        v48);
      v46 = v49;
      if ( v49 )
      {
        v49 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
      }
      v47 = v48;
      if ( v48 )
      {
        v48 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
      }
      return v9;
    }
  }
  v40 = v49;
  if ( v49 )
  {
    v49 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
  }
  v41 = v48;
  if ( v48 )
  {
    v48 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
  }
  return 0;
}

```

## disassembly

```asm
0x18003cee0  mov     [rsp-28h+arg_0], rbx
0x18003cee5  push    rbp
0x18003cee6  push    rsi
0x18003cee7  push    rdi
0x18003cee8  push    r14
0x18003ceea  push    r15
0x18003ceec  mov     rbp, rsp
0x18003ceef  sub     rsp, 70h
0x18003cef3  mov     rax, cs:__security_cookie
0x18003cefa  xor     rax, rsp
0x18003cefd  mov     [rbp+var_8], rax
0x18003cf01  mov     rsi, r8
0x18003cf04  mov     r14, rdx
0x18003cf07  mov     [rbp+var_40], rdx
0x18003cf0b  xor     r15d, r15d
0x18003cf0e  mov     [rbp+var_50], r15
0x18003cf12  mov     [rbp+string], r15
0x18003cf16  lea     r9, [rbp+string]; string
0x18003cf1a  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18003cf1e  lea     edx, [r15+2Ch]; length
0x18003cf22  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_Application@@3QBGB; "Windows.Internal.StateRepository.Applic"...
0x18003cf29  call    cs:__imp_WindowsCreateStringReference
0x18003cf2f  test    eax, eax
0x18003cf31  js      loc_18003D3DA
0x18003cf37  mov     rbx, [rbp+string]
0x18003cf3b  mov     rcx, [rbp+var_50]
0x18003cf3f  test    rcx, rcx
0x18003cf42  jz      short loc_18003CF55
0x18003cf44  mov     [rbp+var_50], r15
0x18003cf48  mov     rax, [rcx]
0x18003cf4b  mov     rax, [rax+10h]
0x18003cf4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cf54  nop
0x18003cf55  lea     r8, [rbp+var_50]
0x18003cf59  lea     rdx, _GUID_07adcc9a_e505_48c2_b471_45af8561f6af
0x18003cf60  mov     rcx, rbx
0x18003cf63  call    cs:__imp_RoGetActivationFactory
0x18003cf69  mov     ebx, eax
0x18003cf6b  test    eax, eax
0x18003cf6d  jns     short loc_18003CFA9
0x18003cf6f  mov     rcx, [rbp+28h]; this
0x18003cf73  mov     r9d, eax; char *
0x18003cf76  lea     r8, aOnecoreuapDsNf_14; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x18003cf7d  mov     edx, 2Ah ; '*'; void *
0x18003cf82  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003cf87  nop
0x18003cf88  mov     rcx, [rbp+var_50]
0x18003cf8c  test    rcx, rcx
0x18003cf8f  jz      short loc_18003CFA2
0x18003cf91  mov     [rbp+var_50], r15
0x18003cf95  mov     rax, [rcx]
0x18003cf98  mov     rax, [rax+10h]
0x18003cf9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cfa1  nop
0x18003cfa2  mov     eax, ebx
0x18003cfa4  jmp     loc_18003D317
0x18003cfa9  mov     [rbp+var_48], r15
0x18003cfad  mov     rdi, [rbp+var_50]
0x18003cfb1  mov     rax, [rdi]
0x18003cfb4  mov     rbx, [rax+100h]
0x18003cfbb  lea     rdx, [rbp+var_40]
0x18003cfbf  lea     rcx, [rbp+hstringHeader]
0x18003cfc3  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18003cfc8  nop
0x18003cfc9  lea     r8, [rbp+var_48]
0x18003cfcd  mov     rdx, [rax+18h]
0x18003cfd1  mov     rcx, rdi
0x18003cfd4  mov     rax, rbx
0x18003cfd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cfdc  mov     ebx, eax
0x18003cfde  test    eax, eax
0x18003cfe0  jns     short loc_18003D034
0x18003cfe2  mov     rcx, [rbp+28h]; this
0x18003cfe6  mov     r9d, eax; char *
0x18003cfe9  lea     r8, aOnecoreuapDsNf_14; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x18003cff0  mov     edx, 2Dh ; '-'; void *
0x18003cff5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003cffa  nop
0x18003cffb  mov     rcx, [rbp+var_48]
0x18003cfff  test    rcx, rcx
0x18003d002  jz      short loc_18003D015
0x18003d004  mov     [rbp+var_48], r15
0x18003d008  mov     rax, [rcx]
0x18003d00b  mov     rax, [rax+10h]
0x18003d00f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d014  nop
0x18003d015  mov     rcx, [rbp+var_50]
0x18003d019  test    rcx, rcx
0x18003d01c  jz      short loc_18003D02F
0x18003d01e  mov     [rbp+var_50], r15
0x18003d022  mov     rax, [rcx]
0x18003d025  mov     rax, [rax+10h]
0x18003d029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d02e  nop
0x18003d02f  jmp     loc_18003CFA2
0x18003d034  mov     [rbp+var_30], r15d
0x18003d038  mov     rcx, [rbp+var_48]
0x18003d03c  mov     rax, [rcx]
0x18003d03f  lea     rdx, [rbp+var_30]
0x18003d043  mov     rax, [rax+38h]
0x18003d047  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d04c  mov     ebx, eax
0x18003d04e  test    eax, eax
0x18003d050  jns     short loc_18003D0A4
0x18003d052  mov     rcx, [rbp+28h]; this
0x18003d056  mov     r9d, eax; char *
0x18003d059  lea     r8, aOnecoreuapDsNf_14; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x18003d060  mov     edx, 30h ; '0'; void *
0x18003d065  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d06a  nop
0x18003d06b  mov     rcx, [rbp+var_48]
0x18003d06f  test    rcx, rcx
0x18003d072  jz      short loc_18003D085
0x18003d074  mov     [rbp+var_48], r15
0x18003d078  mov     rax, [rcx]
0x18003d07b  mov     rax, [rax+10h]
0x18003d07f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d084  nop
0x18003d085  mov     rcx, [rbp+var_50]
0x18003d089  test    rcx, rcx
0x18003d08c  jz      short loc_18003D09F
0x18003d08e  mov     [rbp+var_50], r15
0x18003d092  mov     rax, [rcx]
0x18003d095  mov     rax, [rax+10h]
0x18003d099  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d09e  nop
0x18003d09f  jmp     loc_18003CFA2
0x18003d0a4  cmp     [rbp+var_30], r15d
0x18003d0a8  jz      loc_18003D337
0x18003d0ae  mov     [rbp+var_38], r15
0x18003d0b2  mov     rcx, [rbp+var_48]
0x18003d0b6  mov     rax, [rcx]
0x18003d0b9  lea     r8, [rbp+var_38]
0x18003d0bd  xor     edx, edx
0x18003d0bf  mov     rax, [rax+30h]
0x18003d0c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d0c8  mov     ebx, eax
0x18003d0ca  test    eax, eax
0x18003d0cc  jns     short loc_18003D13A
0x18003d0ce  mov     rcx, [rbp+28h]; this
0x18003d0d2  mov     r9d, eax; char *
0x18003d0d5  lea     r8, aOnecoreuapDsNf_14; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x18003d0dc  mov     edx, 37h ; '7'; void *
0x18003d0e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d0e6  nop
0x18003d0e7  mov     rcx, [rbp+var_38]
0x18003d0eb  test    rcx, rcx
0x18003d0ee  jz      short loc_18003D101
0x18003d0f0  mov     [rbp+var_38], r15
0x18003d0f4  mov     rax, [rcx]
0x18003d0f7  mov     rax, [rax+10h]
0x18003d0fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d100  nop
0x18003d101  mov     rcx, [rbp+var_48]
0x18003d105  test    rcx, rcx
0x18003d108  jz      short loc_18003D11B
0x18003d10a  mov     [rbp+var_48], r15
0x18003d10e  mov     rax, [rcx]
0x18003d111  mov     rax, [rax+10h]
0x18003d115  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d11a  nop
0x18003d11b  mov     rcx, [rbp+var_50]
0x18003d11f  test    rcx, rcx
0x18003d122  jz      short loc_18003D135
0x18003d124  mov     [rbp+var_50], r15
0x18003d128  mov     rax, [rcx]
0x18003d12b  mov     rax, [rax+10h]
0x18003d12f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d134  nop
0x18003d135  jmp     loc_18003CFA2
0x18003d13a  mov     [rbp+var_40], r15
0x18003d13e  mov     rdi, [rbp+var_38]
0x18003d142  mov     rax, [rdi]
0x18003d145  mov     rbx, [rax+278h]
0x18003d14c  xor     ecx, ecx; string
0x18003d14e  call    cs:__imp_WindowsDeleteString
0x18003d154  mov     [rbp+var_40], r15
0x18003d158  lea     rdx, [rbp+var_40]
0x18003d15c  mov     rcx, rdi
0x18003d15f  mov     rax, rbx
0x18003d162  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d167  mov     ebx, eax
0x18003d169  test    eax, eax
0x18003d16b  jns     short loc_18003D1E7
0x18003d16d  mov     rcx, [rbp+28h]; this
0x18003d171  mov     r9d, eax; char *
0x18003d174  lea     r8, aOnecoreuapDsNf_14; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x18003d17b  mov     edx, 3Ah ; ':'; void *
0x18003d180  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d185  nop
0x18003d186  mov     rcx, [rbp+var_40]; string
0x18003d18a  call    cs:__imp_WindowsDeleteString
0x18003d190  mov     [rbp+var_40], r15
0x18003d194  mov     rcx, [rbp+var_38]
0x18003d198  test    rcx, rcx
0x18003d19b  jz      short loc_18003D1AE
0x18003d19d  mov     [rbp+var_38], r15
0x18003d1a1  mov     rax, [rcx]
0x18003d1a4  mov     rax, [rax+10h]
0x18003d1a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d1ad  nop
0x18003d1ae  mov     rcx, [rbp+var_48]
0x18003d1b2  test    rcx, rcx
0x18003d1b5  jz      short loc_18003D1C8
0x18003d1b7  mov     [rbp+var_48], r15
0x18003d1bb  mov     rax, [rcx]
0x18003d1be  mov     rax, [rax+10h]
0x18003d1c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d1c7  nop
0x18003d1c8  mov     rcx, [rbp+var_50]
0x18003d1cc  test    rcx, rcx
0x18003d1cf  jz      short loc_18003D1E2
0x18003d1d1  mov     [rbp+var_50], r15
0x18003d1d5  mov     rax, [rcx]
0x18003d1d8  mov     rax, [rax+10h]
0x18003d1dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d1e1  nop
0x18003d1e2  jmp     loc_18003CFA2
0x18003d1e7  mov     ebx, 7FFFFFFEh
0x18003d1ec  xor     edx, edx; length
0x18003d1ee  mov     rcx, [rbp+var_40]; string
0x18003d1f2  call    cs:__imp_WindowsGetStringRawBuffer
0x18003d1f8  mov     edx, 104h
0x18003d1fd  test    rbx, rbx
0x18003d200  jz      short loc_18003D21E
0x18003d202  movzx   ecx, word ptr [rax]
0x18003d205  test    cx, cx
0x18003d208  jz      short loc_18003D21E
0x18003d20a  add     rax, 2
0x18003d20e  mov     [rsi], cx
0x18003d211  add     rsi, 2
0x18003d215  dec     rbx
0x18003d218  sub     rdx, 1
0x18003d21c  jnz     short loc_18003D1FD
0x18003d21e  mov     rax, rdx
0x18003d221  neg     rax
0x18003d224  sbb     ebx, ebx
0x18003d226  not     ebx
0x18003d228  and     ebx, 8007007Ah
0x18003d22e  lea     rcx, [rsi-2]
0x18003d232  test    rdx, rdx
0x18003d235  cmovnz  rcx, rsi
0x18003d239  mov     [rcx], r15w
0x18003d23d  jnz     short loc_18003D2B9
0x18003d23f  mov     rcx, [rbp+28h]; this
0x18003d243  mov     r9d, ebx; char *
0x18003d246  lea     r8, aOnecoreuapDsNf_14; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x18003d24d  mov     edx, 3Ch ; '<'; void *
0x18003d252  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d257  nop
0x18003d258  mov     rcx, [rbp+var_40]; string
0x18003d25c  call    cs:__imp_WindowsDeleteString
0x18003d262  mov     [rbp+var_40], r15
0x18003d266  mov     rcx, [rbp+var_38]
0x18003d26a  test    rcx, rcx
0x18003d26d  jz      short loc_18003D280
0x18003d26f  mov     [rbp+var_38], r15
0x18003d273  mov     rax, [rcx]
0x18003d276  mov     rax, [rax+10h]
0x18003d27a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d27f  nop
0x18003d280  mov     rcx, [rbp+var_48]
0x18003d284  test    rcx, rcx
0x18003d287  jz      short loc_18003D29A
0x18003d289  mov     [rbp+var_48], r15
0x18003d28d  mov     rax, [rcx]
0x18003d290  mov     rax, [rax+10h]
0x18003d294  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d299  nop
0x18003d29a  mov     rcx, [rbp+var_50]
0x18003d29e  test    rcx, rcx
0x18003d2a1  jz      short loc_18003D2B4
0x18003d2a3  mov     [rbp+var_50], r15
0x18003d2a7  mov     rdx, [rcx]
0x18003d2aa  mov     rax, [rdx+10h]
0x18003d2ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d2b3  nop
0x18003d2b4  jmp     loc_18003CFA2
0x18003d2b9  mov     rcx, [rbp+var_40]; string
0x18003d2bd  call    cs:__imp_WindowsDeleteString
0x18003d2c3  mov     [rbp+var_40], r15
0x18003d2c7  mov     rcx, [rbp+var_38]
0x18003d2cb  test    rcx, rcx
0x18003d2ce  jz      short loc_18003D2E1
0x18003d2d0  mov     [rbp+var_38], r15
0x18003d2d4  mov     rax, [rcx]
0x18003d2d7  mov     rax, [rax+10h]
0x18003d2db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d2e0  nop
0x18003d2e1  mov     rcx, [rbp+var_48]
0x18003d2e5  test    rcx, rcx
0x18003d2e8  jz      short loc_18003D2FB
0x18003d2ea  mov     [rbp+var_48], r15
0x18003d2ee  mov     rax, [rcx]
0x18003d2f1  mov     rax, [rax+10h]
0x18003d2f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d2fa  nop
0x18003d2fb  mov     rcx, [rbp+var_50]
0x18003d2ff  test    rcx, rcx
0x18003d302  jz      short loc_18003D315
  ... truncated ...
```
