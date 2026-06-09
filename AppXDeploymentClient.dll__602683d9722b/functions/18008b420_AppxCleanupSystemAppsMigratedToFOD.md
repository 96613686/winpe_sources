# AppxCleanupSystemAppsMigratedToFOD

- ea: `0x18008b420`
- end: `0x18008b96e`
- name: `AppxCleanupSystemAppsMigratedToFOD`
- size: `1358`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x180008a1c`
- `0x18000b614`
- `0x18000b644`
- `0x180020d70`
- `0x180026e00`
- `0x180026e5c`
- `0x180051870`
- `0x18008b420`
- `0x1800e6010`

## import_xrefs

- `AppXAllUserStore!AddEndOfLifePackageMarking` at `0x18008b7a0`
- `AppXAllUserStore!AddEndOfLifePackageMarking` at `0x18008b7a0`
- `AppXAllUserStore!IsInboxPackage` at `0x18008b660`
- `AppXAllUserStore!IsInboxPackage` at `0x18008b660`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008b626`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008b75c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008b7c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008b80f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008b83e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008b8f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008b626`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008b75c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008b7c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008b80f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008b83e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008b8f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008b653`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008b785`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008b794`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008b653`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008b785`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008b794`

## pseudocode

```c
__int64 AppxCleanupSystemAppsMigratedToFOD()
{
  int v0; // eax
  unsigned int v1; // ebx
  int v2; // eax
  __int64 v3; // rdi
  __int64 (__fastcall *v4)(__int64, __int64, __int64 *); // rbx
  int v5; // eax
  __int64 v6; // rdx
  unsigned int i; // r15d
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, _QWORD, __int64 *); // rbx
  int v10; // eax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, HSTRING *); // rbx
  int v13; // eax
  PCWSTR StringRawBuffer; // rax
  int v15; // eax
  unsigned int j; // r14d
  __int64 v17; // rcx
  int v18; // eax
  int v19; // eax
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, HSTRING *); // rbx
  int v22; // eax
  PCWSTR v23; // rbx
  PCWSTR v24; // rax
  int v25; // eax
  __int64 v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // rdx
  __int64 v32; // rdx
  _BYTE v34[8]; // [rsp+20h] [rbp-69h] BYREF
  HSTRING string; // [rsp+28h] [rbp-61h] BYREF
  __int64 v36; // [rsp+30h] [rbp-59h] BYREF
  __int64 v37; // [rsp+38h] [rbp-51h] BYREF
  __int64 v38; // [rsp+40h] [rbp-49h] BYREF
  __int64 v39; // [rsp+48h] [rbp-41h] BYREF
  __int64 v40; // [rsp+50h] [rbp-39h] BYREF
  HSTRING v41; // [rsp+58h] [rbp-31h] BYREF
  unsigned int v42; // [rsp+60h] [rbp-29h] BYREF
  int v43; // [rsp+64h] [rbp-25h] BYREF
  int v44; // [rsp+68h] [rbp-21h] BYREF
  unsigned int v45; // [rsp+6Ch] [rbp-1Dh] BYREF
  int v46; // [rsp+70h] [rbp-19h] BYREF
  __int64 v47; // [rsp+78h] [rbp-11h] BYREF
  __int64 v48; // [rsp+80h] [rbp-9h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+88h] [rbp-1h] BYREF
  __int64 v50; // [rsp+A0h] [rbp+17h]
  void *retaddr; // [rsp+E8h] [rbp+5Fh]

  v48 = 0;
  v50 = 0;
  sub_180020D70(&hstringHeader, L"Windows.Internal.StateRepository.Package");
  v0 = sub_180026E00(v50, &v48);
  v1 = v0;
  if ( v0 < 0 )
  {
    sub_180008A1C(retaddr, 2101, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v0);
    goto LABEL_64;
  }
  v39 = 0;
  v50 = 0;
  sub_180020D70(&hstringHeader, L"Windows.Internal.StateRepository.PackageUser");
  v2 = sub_180026E5C(v50, &v39);
  v1 = v2;
  if ( v2 < 0 )
  {
    sub_180008A1C(retaddr, 2105, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v2);
LABEL_5:
    sub_18000B644(&v39);
    goto LABEL_64;
  }
  v3 = v48;
  v36 = 0;
  v4 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v48 + 552LL);
  sub_18000B644(&v36);
  v5 = v4(v3, 2, &v36);
  v1 = v5;
  if ( v5 < 0 )
  {
    v6 = 2108;
    goto LABEL_8;
  }
  v42 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v36 + 56LL))(v36, &v42);
  v1 = v5;
  if ( v5 < 0 )
  {
    v6 = 2111;
LABEL_8:
    sub_180008A1C(retaddr, v6, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v5);
LABEL_9:
    sub_18000B644(&v36);
    goto LABEL_5;
  }
  for ( i = 0; i < v42; ++i )
  {
    v8 = v36;
    v38 = 0;
    v9 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v36 + 48LL);
    sub_18000B644(&v38);
    v10 = v9(v8, i, &v38);
    v1 = v10;
    if ( v10 < 0 )
    {
      v32 = 2115;
      goto LABEL_61;
    }
    v34[0] = 0;
    v10 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v38 + 120LL))(v38, v34);
    v1 = v10;
    if ( v10 < 0 )
    {
      v32 = 2121;
      goto LABEL_61;
    }
    v43 = 0;
    v10 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v38 + 128LL))(v38, &v43);
    v1 = v10;
    if ( v10 < 0 )
    {
      v32 = 2124;
LABEL_61:
      sub_180008A1C(retaddr, v32, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v10);
      goto LABEL_62;
    }
    if ( v34[0] && v43 != 8 )
    {
      v11 = v38;
      string = 0;
      v12 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v38 + 112LL);
      WindowsDeleteString(0);
      string = 0;
      v13 = v12(v11, &string);
      v1 = v13;
      if ( v13 < 0 )
      {
        v31 = 2128;
        goto LABEL_56;
      }
      v44 = 0;
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v13 = IsInboxPackage(StringRawBuffer, &v44);
      v1 = v13;
      if ( v13 < 0 )
      {
        v31 = 2131;
LABEL_56:
        sub_180008A1C(retaddr, v31, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v13);
        goto LABEL_57;
      }
      if ( !v44 )
      {
        v37 = 0;
        v15 = (*(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v39 + 288LL))(v39, string, &v37);
        v1 = v15;
        if ( v15 < 0 )
        {
          v29 = 2136;
          goto LABEL_51;
        }
        v45 = 0;
        v15 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v37 + 56LL))(v37, &v45);
        v1 = v15;
        if ( v15 < 0 )
        {
          v29 = 2139;
LABEL_51:
          sub_180008A1C(
            retaddr,
            v29,
            "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp",
            (unsigned int)v15);
LABEL_52:
          v30 = v37;
          if ( v37 )
          {
            v37 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
          }
LABEL_57:
          WindowsDeleteString(string);
          string = 0;
LABEL_62:
          sub_18000B644(&v38);
          goto LABEL_9;
        }
        for ( j = 0; ; ++j )
        {
          v17 = v37;
          if ( j >= v45 )
            break;
          v40 = 0;
          v18 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v37 + 48LL))(v37, j, &v40);
          v1 = v18;
          if ( v18 < 0 )
          {
            v27 = 2143;
            goto LABEL_46;
          }
          v46 = 0;
          v18 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v40 + 224LL))(v40, &v46);
          v1 = v18;
          if ( v18 < 0 )
          {
            v27 = 2146;
LABEL_46:
            sub_180008A1C(
              retaddr,
              v27,
              "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp",
              (unsigned int)v18);
            goto LABEL_47;
          }
          if ( v46 == 2 )
          {
            v47 = 0;
            v19 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v40 + 128LL))(v40, &v47);
            v1 = v19;
            if ( v19 < 0 )
            {
              sub_180008A1C(
                retaddr,
                2150,
                "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp",
                (unsigned int)v19);
LABEL_43:
              sub_18000B644(&v47);
LABEL_47:
              v28 = v40;
              if ( v40 )
              {
                v40 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
              }
              goto LABEL_52;
            }
            v20 = v47;
            v41 = 0;
            v21 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v47 + 64LL);
            WindowsDeleteString(0);
            v41 = 0;
            v22 = v21(v20, &v41);
            v1 = v22;
            if ( v22 < 0 )
            {
              sub_180008A1C(
                retaddr,
                2153,
                "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp",
                (unsigned int)v22);
              WindowsDeleteString(v41);
              v41 = 0;
              goto LABEL_43;
            }
            v23 = WindowsGetStringRawBuffer(string, 0);
            v24 = WindowsGetStringRawBuffer(v41, 0);
            v25 = AddEndOfLifePackageMarking(v24, v23);
            if ( v25 < 0 )
              sub_18000B614(
                retaddr,
                2155,
                "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp",
                (unsigned int)v25);
            WindowsDeleteString(v41);
            v41 = 0;
            sub_18000B644(&v47);
          }
          v26 = v40;
          if ( v40 )
          {
            v40 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
          }
        }
        if ( v37 )
        {
          v37 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
        }
      }
      WindowsDeleteString(string);
    }
    sub_18000B644(&v38);
  }
  sub_18000B644(&v36);
  sub_18000B644(&v39);
  v1 = 0;
LABEL_64:
  sub_18000B644(&v48);
  return v1;
}

```

## disassembly

```asm
0x18008b420  push    rbp
0x18008b422  push    rbx
0x18008b423  push    rsi
0x18008b424  push    rdi
0x18008b425  push    r12
0x18008b427  push    r14
0x18008b429  push    r15
0x18008b42b  lea     rbp, [rsp-27h]
0x18008b430  sub     rsp, 0B0h
0x18008b437  mov     rax, cs:__security_cookie
0x18008b43e  xor     rax, rsp
0x18008b441  mov     [rbp+57h+var_38], rax
0x18008b445  xor     r12d, r12d
0x18008b448  lea     rdx, aWindowsInterna_0; "Windows.Internal.StateRepository.Packag"...
0x18008b44f  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18008b453  mov     [rbp+57h+var_60], r12
0x18008b457  mov     [rbp+57h+var_40], r12
0x18008b45b  lea     r9d, [r12+28h]
0x18008b460  lea     r8d, [r12+29h]
0x18008b465  call    sub_180020D70
0x18008b46a  mov     rcx, [rbp+57h+var_40]
0x18008b46e  lea     rdx, [rbp+57h+var_60]
0x18008b472  call    sub_180026E00
0x18008b477  mov     ebx, eax
0x18008b479  test    eax, eax
0x18008b47b  jns     short loc_18008B49A
0x18008b47d  mov     rcx, [rbp+5Fh]
0x18008b481  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\packagemanage"...
0x18008b488  mov     r9d, eax
0x18008b48b  mov     edx, 835h
0x18008b490  call    sub_180008A1C
0x18008b495  jmp     loc_18008B945
0x18008b49a  mov     r9d, 2Ch ; ','
0x18008b4a0  mov     [rbp+57h+var_98], r12
0x18008b4a4  lea     rdx, aWindowsInterna_11; "Windows.Internal.StateRepository.Packag"...
0x18008b4ab  mov     [rbp+57h+var_40], r12
0x18008b4af  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18008b4b3  lea     r8d, [r9+1]
0x18008b4b7  call    sub_180020D70
0x18008b4bc  mov     rcx, [rbp+57h+var_40]
0x18008b4c0  lea     rdx, [rbp+57h+var_98]
0x18008b4c4  call    sub_180026E5C
0x18008b4c9  mov     ebx, eax
0x18008b4cb  test    eax, eax
0x18008b4cd  jns     short loc_18008B4F5
0x18008b4cf  mov     rcx, [rbp+5Fh]
0x18008b4d3  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\packagemanage"...
0x18008b4da  mov     r9d, eax
0x18008b4dd  mov     edx, 839h
0x18008b4e2  call    sub_180008A1C
0x18008b4e7  lea     rcx, [rbp+57h+var_98]
0x18008b4eb  call    sub_18000B644
0x18008b4f0  jmp     loc_18008B945
0x18008b4f5  mov     rdi, [rbp+57h+var_60]
0x18008b4f9  lea     rcx, [rbp+57h+var_B0]
0x18008b4fd  mov     [rbp+57h+var_B0], r12
0x18008b501  mov     rax, [rdi]
0x18008b504  mov     rbx, [rax+228h]
0x18008b50b  call    sub_18000B644
0x18008b510  lea     r8, [rbp+57h+var_B0]
0x18008b514  mov     edx, 2
0x18008b519  mov     rcx, rdi
0x18008b51c  mov     rax, rbx
0x18008b51f  call    j__guard_dispatch_icall
0x18008b524  mov     ebx, eax
0x18008b526  test    eax, eax
0x18008b528  jns     short loc_18008B54D
0x18008b52a  mov     edx, 83Ch
0x18008b52f  mov     rcx, [rbp+5Fh]
0x18008b533  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\packagemanage"...
0x18008b53a  mov     r9d, eax
0x18008b53d  call    sub_180008A1C
0x18008b542  lea     rcx, [rbp+57h+var_B0]
0x18008b546  call    sub_18000B644
0x18008b54b  jmp     short loc_18008B4E7
0x18008b54d  mov     rcx, [rbp+57h+var_B0]
0x18008b551  lea     rdx, [rbp+57h+var_80]
0x18008b555  mov     [rbp+57h+var_80], r12d
0x18008b559  mov     rax, [rcx]
0x18008b55c  mov     rax, [rax+38h]
0x18008b560  call    j__guard_dispatch_icall
0x18008b565  mov     ebx, eax
0x18008b567  test    eax, eax
0x18008b569  jns     short loc_18008B572
0x18008b56b  mov     edx, 83Fh
0x18008b570  jmp     short loc_18008B52F
0x18008b572  mov     r15d, r12d
0x18008b575  lea     rsi, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\packagemanage"...
0x18008b57c  cmp     r15d, [rbp+57h+var_80]
0x18008b580  jnb     loc_18008B930
0x18008b586  mov     rdi, [rbp+57h+var_B0]
0x18008b58a  lea     rcx, [rbp+57h+var_A0]
0x18008b58e  mov     [rbp+57h+var_A0], r12
0x18008b592  mov     rax, [rdi]
0x18008b595  mov     rbx, [rax+30h]
0x18008b599  call    sub_18000B644
0x18008b59e  lea     r8, [rbp+57h+var_A0]
0x18008b5a2  mov     edx, r15d
0x18008b5a5  mov     rcx, rdi
0x18008b5a8  mov     rax, rbx
0x18008b5ab  call    j__guard_dispatch_icall
0x18008b5b0  mov     ebx, eax
0x18008b5b2  test    eax, eax
0x18008b5b4  js      loc_18008B90E
0x18008b5ba  mov     rcx, [rbp+57h+var_A0]
0x18008b5be  lea     rdx, [rbp+57h+var_C0]
0x18008b5c2  mov     [rbp+57h+var_C0], r12b
0x18008b5c6  mov     rax, [rcx]
0x18008b5c9  mov     rax, [rax+78h]
0x18008b5cd  call    j__guard_dispatch_icall
0x18008b5d2  mov     ebx, eax
0x18008b5d4  test    eax, eax
0x18008b5d6  js      loc_18008B907
0x18008b5dc  mov     rcx, [rbp+57h+var_A0]
0x18008b5e0  lea     rdx, [rbp+57h+var_7C]
0x18008b5e4  mov     [rbp+57h+var_7C], r12d
0x18008b5e8  mov     rax, [rcx]
0x18008b5eb  mov     rax, [rax+80h]
0x18008b5f2  call    j__guard_dispatch_icall
0x18008b5f7  mov     ebx, eax
0x18008b5f9  test    eax, eax
0x18008b5fb  js      loc_18008B900
0x18008b601  cmp     [rbp+57h+var_C0], r12b
0x18008b605  jz      loc_18008B815
0x18008b60b  cmp     [rbp+57h+var_7C], 8
0x18008b60f  jz      loc_18008B815
0x18008b615  mov     rdi, [rbp+57h+var_A0]
0x18008b619  xor     ecx, ecx; string
0x18008b61b  mov     [rbp+57h+string], r12
0x18008b61f  mov     rax, [rdi]
0x18008b622  mov     rbx, [rax+70h]
0x18008b626  call    cs:WindowsDeleteString
0x18008b62c  lea     rdx, [rbp+57h+string]
0x18008b630  mov     [rbp+57h+string], r12
0x18008b634  mov     rcx, rdi
0x18008b637  mov     rax, rbx
0x18008b63a  call    j__guard_dispatch_icall
0x18008b63f  mov     ebx, eax
0x18008b641  test    eax, eax
0x18008b643  js      loc_18008B8DC
0x18008b649  mov     rcx, [rbp+57h+string]; string
0x18008b64d  xor     edx, edx; length
0x18008b64f  mov     [rbp+57h+var_78], r12d
0x18008b653  call    cs:WindowsGetStringRawBuffer
0x18008b659  mov     rcx, rax
0x18008b65c  lea     rdx, [rbp+57h+var_78]
0x18008b660  call    cs:IsInboxPackage
0x18008b666  mov     ebx, eax
0x18008b668  test    eax, eax
0x18008b66a  js      loc_18008B8D5
0x18008b670  cmp     [rbp+57h+var_78], r12d
0x18008b674  jnz     loc_18008B80B
0x18008b67a  mov     rcx, [rbp+57h+var_98]
0x18008b67e  lea     r8, [rbp+57h+var_A8]
0x18008b682  mov     rdx, [rbp+57h+string]
0x18008b686  mov     [rbp+57h+var_A8], r12
0x18008b68a  mov     rax, [rcx]
0x18008b68d  mov     rax, [rax+120h]
0x18008b694  call    j__guard_dispatch_icall
0x18008b699  mov     ebx, eax
0x18008b69b  test    eax, eax
0x18008b69d  js      loc_18008B8A6
0x18008b6a3  mov     rcx, [rbp+57h+var_A8]
0x18008b6a7  lea     rdx, [rbp+57h+var_74]
0x18008b6ab  mov     [rbp+57h+var_74], r12d
0x18008b6af  mov     rax, [rcx]
0x18008b6b2  mov     rax, [rax+38h]
0x18008b6b6  call    j__guard_dispatch_icall
0x18008b6bb  mov     ebx, eax
0x18008b6bd  test    eax, eax
0x18008b6bf  js      loc_18008B89F
0x18008b6c5  mov     r14d, r12d
0x18008b6c8  mov     rcx, [rbp+57h+var_A8]
0x18008b6cc  cmp     r14d, [rbp+57h+var_74]
0x18008b6d0  jnb     loc_18008B7F6
0x18008b6d6  mov     [rbp+57h+var_90], r12
0x18008b6da  lea     r8, [rbp+57h+var_90]
0x18008b6de  mov     rax, [rcx]
0x18008b6e1  mov     edx, r14d
0x18008b6e4  mov     rax, [rax+30h]
0x18008b6e8  call    j__guard_dispatch_icall
0x18008b6ed  mov     ebx, eax
0x18008b6ef  test    eax, eax
0x18008b6f1  js      loc_18008B870
0x18008b6f7  mov     rcx, [rbp+57h+var_90]
0x18008b6fb  lea     rdx, [rbp+57h+var_70]
0x18008b6ff  mov     [rbp+57h+var_70], r12d
0x18008b703  mov     rax, [rcx]
0x18008b706  mov     rax, [rax+0E0h]
0x18008b70d  call    j__guard_dispatch_icall
0x18008b712  mov     ebx, eax
0x18008b714  test    eax, eax
0x18008b716  js      loc_18008B869
0x18008b71c  cmp     [rbp+57h+var_70], 2
0x18008b720  jnz     loc_18008B7D5
0x18008b726  mov     rcx, [rbp+57h+var_90]
0x18008b72a  lea     rdx, [rbp+57h+var_68]
0x18008b72e  mov     [rbp+57h+var_68], r12
0x18008b732  mov     rax, [rcx]
0x18008b735  mov     rax, [rax+80h]
0x18008b73c  call    j__guard_dispatch_icall
0x18008b741  mov     ebx, eax
0x18008b743  test    eax, eax
0x18008b745  js      loc_18008B84A
0x18008b74b  mov     rdi, [rbp+57h+var_68]
0x18008b74f  xor     ecx, ecx; string
0x18008b751  mov     [rbp+57h+var_88], r12
0x18008b755  mov     rax, [rdi]
0x18008b758  mov     rbx, [rax+40h]
0x18008b75c  call    cs:WindowsDeleteString
0x18008b762  lea     rdx, [rbp+57h+var_88]
0x18008b766  mov     [rbp+57h+var_88], r12
0x18008b76a  mov     rcx, rdi
0x18008b76d  mov     rax, rbx
0x18008b770  call    j__guard_dispatch_icall
0x18008b775  mov     ebx, eax
0x18008b777  test    eax, eax
0x18008b779  js      loc_18008B826
0x18008b77f  mov     rcx, [rbp+57h+string]; string
0x18008b783  xor     edx, edx; length
0x18008b785  call    cs:WindowsGetStringRawBuffer
0x18008b78b  mov     rcx, [rbp+57h+var_88]; string
0x18008b78f  xor     edx, edx; length
0x18008b791  mov     rbx, rax
0x18008b794  call    cs:WindowsGetStringRawBuffer
0x18008b79a  mov     rcx, rax
0x18008b79d  mov     rdx, rbx
0x18008b7a0  call    cs:AddEndOfLifePackageMarking
0x18008b7a6  test    eax, eax
0x18008b7a8  jns     short loc_18008B7BE
0x18008b7aa  mov     rcx, [rbp+5Fh]
0x18008b7ae  mov     r9d, eax
0x18008b7b1  mov     r8, rsi
0x18008b7b4  mov     edx, 86Bh
0x18008b7b9  call    sub_18000B614
0x18008b7be  mov     rcx, [rbp+57h+var_88]; string
0x18008b7c2  call    cs:WindowsDeleteString
0x18008b7c8  lea     rcx, [rbp+57h+var_68]
0x18008b7cc  mov     [rbp+57h+var_88], r12
0x18008b7d0  call    sub_18000B644
0x18008b7d5  mov     rcx, [rbp+57h+var_90]
0x18008b7d9  test    rcx, rcx
0x18008b7dc  jz      short loc_18008B7EE
0x18008b7de  mov     [rbp+57h+var_90], r12
0x18008b7e2  mov     rax, [rcx]
0x18008b7e5  mov     rax, [rax+10h]
0x18008b7e9  call    j__guard_dispatch_icall
0x18008b7ee  inc     r14d
0x18008b7f1  jmp     loc_18008B6C8
0x18008b7f6  test    rcx, rcx
0x18008b7f9  jz      short loc_18008B80B
0x18008b7fb  mov     [rbp+57h+var_A8], r12
0x18008b7ff  mov     rax, [rcx]
0x18008b802  mov     rax, [rax+10h]
0x18008b806  call    j__guard_dispatch_icall
0x18008b80b  mov     rcx, [rbp+57h+string]; string
0x18008b80f  call    cs:WindowsDeleteString
0x18008b815  lea     rcx, [rbp+57h+var_A0]
0x18008b819  call    sub_18000B644
0x18008b81e  inc     r15d
0x18008b821  jmp     loc_18008B57C
0x18008b826  mov     rcx, [rbp+5Fh]
0x18008b82a  mov     r9d, eax
0x18008b82d  mov     r8, rsi
0x18008b830  mov     edx, 869h
0x18008b835  call    sub_180008A1C
0x18008b83a  mov     rcx, [rbp+57h+var_88]; string
0x18008b83e  call    cs:WindowsDeleteString
0x18008b844  mov     [rbp+57h+var_88], r12
0x18008b848  jmp     short loc_18008B85E
0x18008b84a  mov     rcx, [rbp+5Fh]
0x18008b84e  mov     r9d, eax
0x18008b851  mov     r8, rsi
0x18008b854  mov     edx, 866h
0x18008b859  call    sub_180008A1C
0x18008b85e  lea     rcx, [rbp+57h+var_68]
0x18008b862  call    sub_18000B644
0x18008b867  jmp     short loc_18008B884
0x18008b869  mov     edx, 862h
0x18008b86e  jmp     short loc_18008B875
0x18008b870  mov     edx, 85Fh
0x18008b875  mov     rcx, [rbp+5Fh]
0x18008b879  mov     r8, rsi
0x18008b87c  mov     r9d, eax
0x18008b87f  call    sub_180008A1C
0x18008b884  mov     rcx, [rbp+57h+var_90]
0x18008b888  test    rcx, rcx
0x18008b88b  jz      short loc_18008B8BA
0x18008b88d  mov     [rbp+57h+var_90], r12
0x18008b891  mov     rax, [rcx]
0x18008b894  mov     rax, [rax+10h]
0x18008b898  call    j__guard_dispatch_icall
0x18008b89d  jmp     short loc_18008B8BA
0x18008b89f  mov     edx, 85Bh
0x18008b8a4  jmp     short loc_18008B8AB
0x18008b8a6  mov     edx, 858h
0x18008b8ab  mov     rcx, [rbp+5Fh]
0x18008b8af  mov     r8, rsi
0x18008b8b2  mov     r9d, eax
0x18008b8b5  call    sub_180008A1C
  ... truncated ...
```
