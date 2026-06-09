# AppxRemovePackageForUserSid

- ea: `0x18008c2f0`
- end: `0x18008c9fd`
- name: `AppxRemovePackageForUserSid`
- size: `1805`
- prototype: `__int64 __fastcall(PCWSTR packageFullName, const wchar_t *)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation`

## callees

- `0x180008a1c`
- `0x18000b644`
- `0x180016ee0`
- `0x180018010`
- `0x180020d70`
- `0x180026e00`
- `0x180026e5c`
- `0x180035d98`
- `0x180051870`
- `0x1800522e8`
- `0x1800805e4`
- `0x1800863b4`
- `0x18008aff4`
- `0x18008c2f0`
- `0x1800cad70`
- `0x1800e6010`

## import_xrefs

- `AppXAllUserStore!AddEndOfLifePackageMarking` at `0x18008c561`
- `AppXAllUserStore!AddEndOfLifePackageMarking` at `0x18008c561`
- `AppXAllUserStore!IsPackagePinned` at `0x18008c5fe`
- `AppXAllUserStore!IsPackagePinned` at `0x18008c5fe`
- `AppXAllUserStore!IsNonInboxAllUserPackage` at `0x18008c61f`
- `AppXAllUserStore!IsNonInboxAllUserPackage` at `0x18008c61f`
- `AppXAllUserStore!IsPackageEndOfLife` at `0x18008c7f9`
- `AppXAllUserStore!IsPackageEndOfLife` at `0x18008c7f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008c7b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008c815`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008c86d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008c911`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008c7b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008c815`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008c86d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008c911`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008c7e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008c7e8`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x18008c5c6`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x18008c5c6`

## pseudocode

```c
__int64 __fastcall AppxRemovePackageForUserSid(PCWSTR packageFullName, const wchar_t *a2)
{
  __int64 v4; // rdx
  int v5; // ebx
  __int64 v6; // rsi
  __int64 (__fastcall *v7)(__int64, PVOID, PVOID, __int64 *); // rdi
  PVOID Reserved1; // rbx
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, _QWORD, _BYTE *); // rbx
  __int64 v13; // rax
  unsigned int v14; // eax
  int v15; // eax
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, _QWORD, __int64 *); // rbx
  __int64 v18; // rax
  __int64 v19; // rdx
  __int64 v20; // rcx
  unsigned int v21; // r15d
  int v22; // eax
  int v23; // eax
  PCWSTR v24; // rdi
  __int64 (__fastcall *v25)(PCWSTR, HSTRING *); // rbx
  PCWSTR StringRawBuffer; // rax
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v31; // rdx
  __int64 v32; // rcx
  char v33; // [rsp+40h] [rbp-C0h] BYREF
  char v34; // [rsp+41h] [rbp-BFh] BYREF
  _BYTE v35[6]; // [rsp+42h] [rbp-BEh] BYREF
  __int64 v36; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v37; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v38; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v39; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v40; // [rsp+68h] [rbp-98h] BYREF
  HSTRING string; // [rsp+70h] [rbp-90h] BYREF
  PCWSTR v42; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v43; // [rsp+80h] [rbp-80h] BYREF
  int v44; // [rsp+84h] [rbp-7Ch] BYREF
  int v45; // [rsp+88h] [rbp-78h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+8Ch] [rbp-74h] BYREF
  HSTRING_HEADER v47; // [rsp+90h] [rbp-70h] BYREF
  __int64 v48; // [rsp+A8h] [rbp-58h]
  HSTRING_HEADER hstringHeader; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+D0h] [rbp-30h] BYREF
  void *retaddr; // [rsp+198h] [rbp+98h]

  v42 = packageFullName;
  if ( !packageFullName )
  {
    v4 = 1787;
LABEL_3:
    v5 = -2147024809;
LABEL_4:
    sub_180008A1C(retaddr, v4, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v5);
    return (unsigned int)v5;
  }
  if ( !a2 )
  {
    v4 = 1788;
    goto LABEL_3;
  }
  v33 = 0;
  v5 = sub_1800CAD70(&v33);
  if ( v5 < 0 )
  {
    v4 = 1792;
    goto LABEL_4;
  }
  if ( !v33 )
  {
    v5 = -2147024891;
    v4 = 1793;
    goto LABEL_4;
  }
  *(_WORD *)(*(_QWORD *)&qword_1801534C8 + 8LL) = 257;
  sub_1800863B4(&v40);
  v6 = v40;
  if ( !v40 )
  {
    v5 = -2147024882;
    v4 = 1803;
    goto LABEL_4;
  }
  v36 = 0;
  v34 = 0;
  v7 = *(__int64 (__fastcall **)(__int64, PVOID, PVOID, __int64 *))(*(_QWORD *)v40 + 168LL);
  sub_180016EE0(&v47, packageFullName);
  Reserved1 = v47.Reserved.Reserved1;
  sub_180016EE0(&hstringHeader, a2);
  v5 = v7(v6, hstringHeader.Reserved.Reserved1, Reserved1, &v36);
  if ( v5 < 0 )
  {
    v9 = 1811;
LABEL_15:
    sub_180008A1C(retaddr, v9, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v5);
    goto LABEL_16;
  }
  if ( !v36 )
  {
    v5 = -2147009295;
    sub_180008A1C(retaddr, 1812, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", 2147958001LL);
    goto LABEL_80;
  }
  v5 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v36 + 64LL))(v36, &v34);
  if ( v5 < 0 )
  {
    v9 = 1815;
    goto LABEL_15;
  }
  if ( v34 )
  {
    v5 = -2147024809;
    v9 = 1816;
    goto LABEL_15;
  }
  v38 = 0;
  v48 = 0;
  sub_180020D70(&v47, L"Windows.Internal.StateRepository.Package");
  v5 = sub_180026E00(v48, &v38);
  if ( v5 < 0 )
  {
    v10 = 1822;
LABEL_26:
    sub_180008A1C(retaddr, v10, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v5);
LABEL_27:
    sub_18000B644(&v38);
LABEL_16:
    sub_18000B644(&v36);
    if ( !v6 )
      return (unsigned int)v5;
LABEL_81:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    return (unsigned int)v5;
  }
  v11 = v38;
  v35[0] = 0;
  v12 = *(__int64 (__fastcall **)(__int64, _QWORD, _BYTE *))(*(_QWORD *)v38 + 536LL);
  v13 = sub_180018010(&hstringHeader);
  v5 = v12(v11, *(_QWORD *)(v13 + 24), v35);
  if ( v5 < 0 )
  {
    v10 = 1827;
    goto LABEL_26;
  }
  if ( !v35[0] )
  {
    v5 = -2147009286;
    sub_180008A1C(retaddr, 1828, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", 2147958010LL);
    goto LABEL_79;
  }
  v5 = AddEndOfLifePackageMarking(a2, packageFullName);
  if ( v5 < 0 )
  {
    sub_1800805E4(
      retaddr,
      1835,
      "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp",
      (unsigned int)v5,
      "Could not queue removal of package %ls for user %ls",
      packageFullName,
      a2);
    goto LABEL_27;
  }
  memset(packageFamilyName, 0, 0x82u);
  packageFamilyNameLength = 65;
  v14 = PackageFamilyNameFromFullName(packageFullName, &packageFamilyNameLength, packageFamilyName);
  if ( v14 )
  {
    v5 = sub_180035D98(retaddr, 1839, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", v14);
LABEL_79:
    sub_18000B644(&v38);
LABEL_80:
    sub_18000B644(&v36);
    if ( !v6 )
      return (unsigned int)v5;
    goto LABEL_81;
  }
  v45 = 0;
  v5 = IsPackagePinned(packageFamilyName, &v45);
  if ( v5 < 0 )
  {
    v10 = 1842;
    goto LABEL_26;
  }
  v44 = 0;
  v5 = IsNonInboxAllUserPackage(packageFullName, &v44);
  if ( v5 < 0 )
  {
    v10 = 1845;
    goto LABEL_26;
  }
  if ( !v44 && !v45 )
  {
    v40 = 0;
    v48 = 0;
    sub_180020D70(&v47, L"Windows.Internal.StateRepository.PackageUser");
    v15 = sub_180026E5C(v48, &v40);
    v5 = v15;
    if ( v15 < 0 )
    {
      sub_180008A1C(retaddr, 1850, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v15);
LABEL_43:
      sub_18000B644(&v40);
      goto LABEL_27;
    }
    v16 = v40;
    v37 = 0;
    v17 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v40 + 288LL);
    v18 = sub_180018010(&hstringHeader);
    v5 = v17(v16, *(_QWORD *)(v18 + 24), &v37);
    if ( v5 < 0 )
    {
      v19 = 1852;
LABEL_46:
      sub_180008A1C(retaddr, v19, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v5);
LABEL_47:
      v20 = v37;
      if ( v37 )
      {
        v37 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      }
      goto LABEL_43;
    }
    v43 = 0;
    v5 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v37 + 56LL))(v37, &v43);
    if ( v5 < 0 )
    {
      v19 = 1856;
      goto LABEL_46;
    }
    v21 = 0;
    if ( v43 )
    {
      while ( 1 )
      {
        v39 = 0;
        v22 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v37 + 48LL))(v37, v21, &v39);
        v5 = v22;
        if ( v22 < 0 )
          break;
        v42 = 0;
        v23 = (*(__int64 (__fastcall **)(__int64, PCWSTR *))(*(_QWORD *)v39 + 128LL))(v39, &v42);
        v5 = v23;
        if ( v23 < 0 )
        {
          sub_180008A1C(
            retaddr,
            1863,
            "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp",
            (unsigned int)v23);
          goto LABEL_72;
        }
        v24 = v42;
        string = 0;
        v25 = *(__int64 (__fastcall **)(PCWSTR, HSTRING *))(*(_QWORD *)v42 + 64LL);
        WindowsDeleteString(0);
        string = 0;
        v5 = v25(v24, &string);
        if ( v5 < 0 )
        {
          v31 = 1866;
LABEL_71:
          sub_180008A1C(retaddr, v31, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v5);
          WindowsDeleteString(string);
          string = 0;
LABEL_72:
          sub_18000B644(&v42);
          goto LABEL_73;
        }
        v33 = 0;
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        v5 = IsPackageEndOfLife(StringRawBuffer, packageFullName, &v33);
        if ( v5 < 0 )
        {
          v31 = 1869;
          goto LABEL_71;
        }
        if ( !v33 )
        {
          WindowsDeleteString(string);
          string = 0;
          sub_18000B644(&v42);
          v28 = v39;
          if ( v39 )
          {
            v39 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
          }
          goto LABEL_64;
        }
        WindowsDeleteString(string);
        string = 0;
        sub_18000B644(&v42);
        v27 = v39;
        if ( v39 )
        {
          v39 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
        }
        if ( ++v21 >= v43 )
          goto LABEL_60;
      }
      sub_180008A1C(retaddr, 1860, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v22);
LABEL_73:
      v32 = v39;
      if ( v39 )
      {
        v39 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
      }
      goto LABEL_47;
    }
LABEL_60:
    v5 = sub_18008AFF4(v6, packageFullName);
    if ( v5 < 0 )
    {
      v19 = 1880;
      goto LABEL_46;
    }
LABEL_64:
    v29 = v37;
    if ( v37 )
    {
      v37 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    }
    sub_18000B644(&v40);
  }
  sub_18000B644(&v38);
  sub_18000B644(&v36);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  return 0;
}

```

## disassembly

```asm
0x18008c2f0  mov     [rsp-8+arg_10], rbx
0x18008c2f5  mov     [rsp-8+arg_18], rsi
0x18008c2fa  push    rbp
0x18008c2fb  push    rdi
0x18008c2fc  push    r12
0x18008c2fe  push    r14
0x18008c300  push    r15
0x18008c302  lea     rbp, [rsp-70h]
0x18008c307  sub     rsp, 170h
0x18008c30e  mov     rax, cs:__security_cookie
0x18008c315  xor     rax, rsp
0x18008c318  mov     [rbp+90h+var_30], rax
0x18008c31c  xor     r12d, r12d
0x18008c31f  mov     [rsp+190h+var_118], rcx
0x18008c324  mov     r15, rdx
0x18008c327  mov     r14, rcx
0x18008c32a  test    rcx, rcx
0x18008c32d  jnz     short loc_18008C354
0x18008c32f  mov     edx, 6FBh
0x18008c334  mov     ebx, 80070057h
0x18008c339  mov     rcx, [rbp+98h]
0x18008c340  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\packagemanage"...
0x18008c347  mov     r9d, ebx
0x18008c34a  call    sub_180008A1C
0x18008c34f  jmp     loc_18008C9D3
0x18008c354  test    r15, r15
0x18008c357  jnz     short loc_18008C360
0x18008c359  mov     edx, 6FCh
0x18008c35e  jmp     short loc_18008C334
0x18008c360  lea     rcx, [rsp+190h+var_150]
0x18008c365  mov     [rsp+190h+var_150], r12b
0x18008c36a  call    sub_1800CAD70
0x18008c36f  mov     ebx, eax
0x18008c371  test    eax, eax
0x18008c373  jns     short loc_18008C37C
0x18008c375  mov     edx, 700h
0x18008c37a  jmp     short loc_18008C339
0x18008c37c  cmp     [rsp+190h+var_150], r12b
0x18008c381  jnz     short loc_18008C38F
0x18008c383  mov     ebx, 80070005h
0x18008c388  mov     edx, 701h
0x18008c38d  jmp     short loc_18008C339
0x18008c38f  mov     rax, cs:qword_1801534C8
0x18008c396  lea     rcx, [rsp+190h+var_128]
0x18008c39b  mov     word ptr [rax+8], 101h
0x18008c3a1  call    sub_1800863B4
0x18008c3a6  mov     rsi, [rsp+190h+var_128]
0x18008c3ab  test    rsi, rsi
0x18008c3ae  jnz     short loc_18008C3BF
0x18008c3b0  mov     ebx, 8007000Eh
0x18008c3b5  mov     edx, 70Bh
0x18008c3ba  jmp     loc_18008C339
0x18008c3bf  mov     [rsp+190h+var_148], r12
0x18008c3c4  lea     rcx, [rbp+90h+var_100]
0x18008c3c8  mov     [rsp+190h+var_14F], r12b
0x18008c3cd  mov     rdx, r14
0x18008c3d0  mov     rax, [rsi]
0x18008c3d3  mov     rdi, [rax+0A8h]
0x18008c3da  call    sub_180016EE0
0x18008c3df  mov     rbx, qword ptr [rbp+90h+var_100.Reserved]
0x18008c3e3  lea     rcx, [rbp+90h+hstringHeader]
0x18008c3e7  mov     rdx, r15
0x18008c3ea  call    sub_180016EE0
0x18008c3ef  mov     rdx, qword ptr [rbp+90h+hstringHeader.Reserved]
0x18008c3f3  lea     r9, [rsp+190h+var_148]
0x18008c3f8  mov     r8, rbx
0x18008c3fb  mov     rcx, rsi
0x18008c3fe  mov     rax, rdi
0x18008c401  call    j__guard_dispatch_icall
0x18008c406  mov     ebx, eax
0x18008c408  test    eax, eax
0x18008c40a  jns     short loc_18008C446
0x18008c40c  mov     edx, 713h
0x18008c411  mov     rcx, [rbp+98h]
0x18008c418  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\packagemanage"...
0x18008c41f  mov     r9d, ebx
0x18008c422  call    sub_180008A1C
0x18008c427  lea     rcx, [rsp+190h+var_148]
0x18008c42c  call    sub_18000B644
0x18008c431  test    rsi, rsi
0x18008c434  jz      loc_18008C9D3
0x18008c43a  mov     rax, [rsi]
0x18008c43d  mov     rax, [rax+10h]
0x18008c441  jmp     loc_18008C9CB
0x18008c446  mov     rcx, [rsp+190h+var_148]
0x18008c44b  test    rcx, rcx
0x18008c44e  jnz     short loc_18008C475
0x18008c450  mov     rcx, [rbp+98h]
0x18008c457  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\packagemanage"...
0x18008c45e  mov     ebx, 80073CF1h
0x18008c463  mov     edx, 714h
0x18008c468  mov     r9d, ebx
0x18008c46b  call    sub_180008A1C
0x18008c470  jmp     loc_18008C9B5
0x18008c475  mov     rax, [rcx]
0x18008c478  lea     rdx, [rsp+190h+var_14F]
0x18008c47d  mov     rax, [rax+40h]
0x18008c481  call    j__guard_dispatch_icall
0x18008c486  mov     ebx, eax
0x18008c488  test    eax, eax
0x18008c48a  jns     short loc_18008C496
0x18008c48c  mov     edx, 717h
0x18008c491  jmp     loc_18008C411
0x18008c496  cmp     [rsp+190h+var_14F], r12b
0x18008c49b  jz      short loc_18008C4AC
0x18008c49d  mov     ebx, 80070057h
0x18008c4a2  mov     edx, 718h
0x18008c4a7  jmp     loc_18008C411
0x18008c4ac  mov     r9d, 28h ; '('
0x18008c4b2  mov     [rsp+190h+var_138], r12
0x18008c4b7  lea     rdx, aWindowsInterna_0; "Windows.Internal.StateRepository.Packag"...
0x18008c4be  mov     [rbp+90h+var_E8], r12
0x18008c4c2  lea     rcx, [rbp+90h+var_100]; hstringHeader
0x18008c4c6  lea     r8d, [r9+1]
0x18008c4ca  call    sub_180020D70
0x18008c4cf  mov     rcx, [rbp+90h+var_E8]
0x18008c4d3  lea     rdx, [rsp+190h+var_138]
0x18008c4d8  call    sub_180026E00
0x18008c4dd  mov     ebx, eax
0x18008c4df  test    eax, eax
0x18008c4e1  jns     short loc_18008C50D
0x18008c4e3  mov     edx, 71Eh
0x18008c4e8  mov     rcx, [rbp+98h]
0x18008c4ef  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\packagemanage"...
0x18008c4f6  mov     r9d, ebx
0x18008c4f9  call    sub_180008A1C
0x18008c4fe  lea     rcx, [rsp+190h+var_138]
0x18008c503  call    sub_18000B644
0x18008c508  jmp     loc_18008C427
0x18008c50d  mov     rdi, [rsp+190h+var_138]
0x18008c512  lea     rdx, [rsp+190h+var_118]
0x18008c517  mov     [rsp+190h+var_14E], r12b
0x18008c51c  lea     rcx, [rbp+90h+hstringHeader]; hstringHeader
0x18008c520  mov     rax, [rdi]
0x18008c523  mov     rbx, [rax+218h]
0x18008c52a  call    sub_180018010
0x18008c52f  lea     r8, [rsp+190h+var_14E]
0x18008c534  mov     rcx, rdi
0x18008c537  mov     rdx, [rax+18h]
0x18008c53b  mov     rax, rbx
0x18008c53e  call    j__guard_dispatch_icall
0x18008c543  mov     ebx, eax
0x18008c545  test    eax, eax
0x18008c547  jns     short loc_18008C550
0x18008c549  mov     edx, 723h
0x18008c54e  jmp     short loc_18008C4E8
0x18008c550  cmp     [rsp+190h+var_14E], r12b
0x18008c555  jz      loc_18008C98B
0x18008c55b  mov     rdx, r14
0x18008c55e  mov     rcx, r15
0x18008c561  call    cs:AddEndOfLifePackageMarking
0x18008c567  mov     ebx, eax
0x18008c569  test    eax, eax
0x18008c56b  jns     short loc_18008C5A3
0x18008c56d  mov     rcx, [rbp+98h]
0x18008c574  lea     rax, aCouldNotQueueR; "Could not queue removal of package %ls "...
0x18008c57b  mov     [rsp+190h+var_160], r15
0x18008c580  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\packagemanage"...
0x18008c587  mov     [rsp+190h+var_168], r14
0x18008c58c  mov     r9d, ebx
0x18008c58f  mov     edx, 72Bh
0x18008c594  mov     [rsp+190h+var_170], rax
0x18008c599  call    sub_1800805E4
0x18008c59e  jmp     loc_18008C4FE
0x18008c5a3  xor     edx, edx; Val
0x18008c5a5  lea     rcx, [rbp+90h+packageFamilyName]; void *
0x18008c5a9  mov     r8d, 82h; Size
0x18008c5af  call    memset
0x18008c5b4  lea     r8, [rbp+90h+packageFamilyName]; packageFamilyName
0x18008c5b8  mov     [rbp+90h+packageFamilyNameLength], 41h ; 'A'
0x18008c5bf  lea     rdx, [rbp+90h+packageFamilyNameLength]; packageFamilyNameLength
0x18008c5c3  mov     rcx, r14; packageFullName
0x18008c5c6  call    cs:PackageFamilyNameFromFullName
0x18008c5cc  test    eax, eax
0x18008c5ce  jz      short loc_18008C5F2
0x18008c5d0  mov     rcx, [rbp+98h]
0x18008c5d7  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\packagemanage"...
0x18008c5de  mov     r9d, eax
0x18008c5e1  mov     edx, 72Fh
0x18008c5e6  call    sub_180035D98
0x18008c5eb  mov     ebx, eax
0x18008c5ed  jmp     loc_18008C9AB
0x18008c5f2  lea     rdx, [rbp+90h+var_108]
0x18008c5f6  mov     [rbp+90h+var_108], r12d
0x18008c5fa  lea     rcx, [rbp+90h+packageFamilyName]
0x18008c5fe  call    cs:IsPackagePinned
0x18008c604  mov     ebx, eax
0x18008c606  test    eax, eax
0x18008c608  jns     short loc_18008C614
0x18008c60a  mov     edx, 732h
0x18008c60f  jmp     loc_18008C4E8
0x18008c614  lea     rdx, [rbp+90h+var_10C]
0x18008c618  mov     [rbp+90h+var_10C], r12d
0x18008c61c  mov     rcx, r14
0x18008c61f  call    cs:IsNonInboxAllUserPackage
0x18008c625  mov     ebx, eax
0x18008c627  test    eax, eax
0x18008c629  jns     short loc_18008C635
0x18008c62b  mov     edx, 735h
0x18008c630  jmp     loc_18008C4E8
0x18008c635  cmp     [rbp+90h+var_10C], r12d
0x18008c639  jnz     loc_18008C8C2
0x18008c63f  cmp     [rbp+90h+var_108], r12d
0x18008c643  jnz     loc_18008C8C2
0x18008c649  mov     r9d, 2Ch ; ','
0x18008c64f  mov     [rsp+190h+var_128], r12
0x18008c654  lea     rdx, aWindowsInterna_11; "Windows.Internal.StateRepository.Packag"...
0x18008c65b  mov     [rbp+90h+var_E8], r12
0x18008c65f  lea     rcx, [rbp+90h+var_100]; hstringHeader
0x18008c663  lea     r8d, [r9+1]
0x18008c667  call    sub_180020D70
0x18008c66c  mov     rcx, [rbp+90h+var_E8]
0x18008c670  lea     rdx, [rsp+190h+var_128]
0x18008c675  call    sub_180026E5C
0x18008c67a  mov     ebx, eax
0x18008c67c  test    eax, eax
0x18008c67e  jns     short loc_18008C6AA
0x18008c680  mov     rcx, [rbp+98h]
0x18008c687  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\packagemanage"...
0x18008c68e  mov     r9d, eax
0x18008c691  mov     edx, 73Ah
0x18008c696  call    sub_180008A1C
0x18008c69b  lea     rcx, [rsp+190h+var_128]
0x18008c6a0  call    sub_18000B644
0x18008c6a5  jmp     loc_18008C4FE
0x18008c6aa  mov     rdi, [rsp+190h+var_128]
0x18008c6af  lea     rdx, [rsp+190h+var_118]
0x18008c6b4  mov     [rsp+190h+var_140], r12
0x18008c6b9  lea     rcx, [rbp+90h+hstringHeader]; hstringHeader
0x18008c6bd  mov     rax, [rdi]
0x18008c6c0  mov     rbx, [rax+120h]
0x18008c6c7  call    sub_180018010
0x18008c6cc  lea     r8, [rsp+190h+var_140]
0x18008c6d1  mov     rcx, rdi
0x18008c6d4  mov     rdx, [rax+18h]
0x18008c6d8  mov     rax, rbx
0x18008c6db  call    j__guard_dispatch_icall
0x18008c6e0  mov     ebx, eax
0x18008c6e2  test    eax, eax
0x18008c6e4  jns     short loc_18008C721
0x18008c6e6  mov     edx, 73Ch
0x18008c6eb  mov     rcx, [rbp+98h]
0x18008c6f2  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\packagemanage"...
0x18008c6f9  mov     r9d, ebx
0x18008c6fc  call    sub_180008A1C
0x18008c701  mov     rcx, [rsp+190h+var_140]
0x18008c706  test    rcx, rcx
0x18008c709  jz      short loc_18008C69B
0x18008c70b  mov     [rsp+190h+var_140], r12
0x18008c710  mov     rax, [rcx]
0x18008c713  mov     rax, [rax+10h]
0x18008c717  call    j__guard_dispatch_icall
0x18008c71c  jmp     loc_18008C69B
0x18008c721  mov     rcx, [rsp+190h+var_140]
0x18008c726  lea     rdx, [rbp+90h+var_110]
0x18008c72a  mov     [rbp+90h+var_110], r12d
0x18008c72e  mov     rax, [rcx]
0x18008c731  mov     rax, [rax+38h]
0x18008c735  call    j__guard_dispatch_icall
0x18008c73a  mov     ebx, eax
0x18008c73c  test    eax, eax
0x18008c73e  jns     short loc_18008C747
0x18008c740  mov     edx, 740h
0x18008c745  jmp     short loc_18008C6EB
0x18008c747  mov     r15d, r12d
0x18008c74a  cmp     [rbp+90h+var_110], r12d
0x18008c74e  jbe     loc_18008C852
0x18008c754  mov     rcx, [rsp+190h+var_140]
0x18008c759  lea     r8, [rsp+190h+var_130]
0x18008c75e  mov     [rsp+190h+var_130], r12
0x18008c763  mov     edx, r15d
0x18008c766  mov     rax, [rcx]
0x18008c769  mov     rax, [rax+30h]
0x18008c76d  call    j__guard_dispatch_icall
0x18008c772  mov     ebx, eax
0x18008c774  test    eax, eax
0x18008c776  js      loc_18008C96E
0x18008c77c  mov     rcx, [rsp+190h+var_130]
0x18008c781  lea     rdx, [rsp+190h+var_118]
0x18008c786  mov     [rsp+190h+var_118], r12
0x18008c78b  mov     rax, [rcx]
0x18008c78e  mov     rax, [rax+80h]
0x18008c795  call    j__guard_dispatch_icall
0x18008c79a  mov     ebx, eax
0x18008c79c  test    eax, eax
0x18008c79e  js      loc_18008C951
0x18008c7a4  mov     rdi, [rsp+190h+var_118]
0x18008c7a9  xor     ecx, ecx; string
0x18008c7ab  mov     [rsp+190h+string], r12
0x18008c7b0  mov     rax, [rdi]
0x18008c7b3  mov     rbx, [rax+40h]
0x18008c7b7  call    cs:WindowsDeleteString
0x18008c7bd  lea     rdx, [rsp+190h+string]
0x18008c7c2  mov     [rsp+190h+string], r12
0x18008c7c7  mov     rcx, rdi
0x18008c7ca  mov     rax, rbx
0x18008c7cd  call    j__guard_dispatch_icall
0x18008c7d2  mov     ebx, eax
0x18008c7d4  test    eax, eax
0x18008c7d6  js      loc_18008C94A
  ... truncated ...
```
