# sub_1800D5ADC

- ea: `0x1800d5adc`
- end: `0x1800d610c`
- name: `sub_1800D5ADC`
- size: `1584`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800537d4`

## callees

- `0x1800044c0`
- `0x18000500c`
- `0x18000ef10`
- `0x18003c3c8`
- `0x1800d5adc`
- `0x1801479f8`
- `0x18014ef50`
- `0x1801517a8`
- `0x180159010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcstoui64` at `0x1800d5f08`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoui64` at `0x1800d5f08`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800d6047`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800d6047`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800d5fa2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800d5fa2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d5dfb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d5ef9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d601d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d602c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d6091`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d5dfb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d5ef9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d601d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d602c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d6091`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d5eea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d5f8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d5fb7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d5fc3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d6003`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d600d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d6059`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d6063`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d60d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d5eea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d5f8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d5fb7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d5fc3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d6003`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d600d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d6059`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d6063`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d60d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800d5b51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800d5b51`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800d5c47`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800d5c47`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800d5b8b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800d5b8b`

## string_xrefs

- `0x1800d5f52`: `Windows::Services::Store::Internal::ConvertPUIDFromDecToHex`
- `0x1800d607e`: `Windows::Services::Store::Internal::ConvertPUIDFromDecToHex`
- `0x1800d5e06`: `https://login.microsoft.com`

## pseudocode

```c
__int64 __fastcall sub_1800D5ADC(__int64 a1, HSTRING a2, _DWORD *a3)
{
  HRESULT v7; // eax
  int ActivationFactory; // eax
  unsigned int v9; // ebx
  __int64 v10; // rcx
  int v11; // eax
  __int64 v12; // rcx
  HRESULT v13; // eax
  LPVOID v14; // rcx
  __int64 v15; // rcx
  int v16; // eax
  HSTRING v17; // rcx
  LPVOID v18; // rcx
  __int64 v19; // rcx
  int v20; // eax
  HSTRING v21; // rcx
  LPVOID v22; // rcx
  __int64 v23; // rcx
  LPVOID v24; // rdi
  __int64 (__fastcall *v25)(LPVOID, HSTRING, PCWSTR, const WCHAR *, _DWORD *); // rbx
  PCWSTR StringRawBuffer; // rax
  int v27; // eax
  HSTRING v28; // rcx
  LPVOID v29; // rcx
  __int64 v30; // rcx
  HSTRING v31; // rcx
  LPVOID v32; // rcx
  __int64 v33; // rcx
  PCWSTR v34; // rax
  __int64 v35; // rax
  unsigned int v36; // r14d
  int v37; // r15d
  HSTRING v38; // rdi
  unsigned __int64 v39; // rbx
  int v40; // eax
  const WCHAR *v41; // rbx
  const WCHAR *v42; // rax
  HSTRING v43; // [rsp+50h] [rbp-29h] BYREF
  __int64 v44; // [rsp+58h] [rbp-21h] BYREF
  LPVOID ppv; // [rsp+60h] [rbp-19h] BYREF
  HSTRING v46; // [rsp+68h] [rbp-11h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp-9h] BYREF
  HSTRING string; // [rsp+88h] [rbp+Fh] BYREF
  void *retaddr; // [rsp+D8h] [rbp+5Fh]

  *a3 = 0;
  if ( (unsigned __int8)sub_18014EF50(a1, a2) )
  {
    if ( !a1 )
      return 2147942487LL;
    v46 = 0;
    v44 = 0;
    string = 0;
    v7 = WindowsCreateStringReference(L"Windows.System.Internal.UserManager", 0x23u, &hstringHeader, &string);
    if ( v7 < 0 )
    {
      sub_18003C3C8((unsigned int)v7);
      JUMPOUT(0x1800D610BLL);
    }
    ActivationFactory = RoGetActivationFactory(string, qword_1801A8180, &v44);
    v9 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      sub_18000EF10(
        retaddr,
        63,
        "onecoreuap\\enduser\\winstore\\licensing\\winrt\\lib\\windows\\trialownership.cpp",
        (unsigned int)ActivationFactory);
      v10 = v44;
      if ( v44 )
      {
        v44 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      }
      return v9;
    }
    v11 = (*(__int64 (__fastcall **)(__int64, __int64, HSTRING *))(*(_QWORD *)v44 + 136LL))(v44, a1, &v46);
    v9 = v11;
    if ( v11 < 0 )
    {
      sub_18000EF10(
        retaddr,
        64,
        "onecoreuap\\enduser\\winstore\\licensing\\winrt\\lib\\windows\\trialownership.cpp",
        (unsigned int)v11);
      v12 = v44;
      if ( v44 )
      {
        v44 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
      }
      return v9;
    }
    ppv = 0;
    v13 = CoCreateInstance(&stru_1801FAEC8, 0, 0x17u, &stru_1801FAED8, &ppv);
    v9 = v13;
    if ( v13 < 0 )
    {
      sub_18000EF10(
        retaddr,
        67,
        "onecoreuap\\enduser\\winstore\\licensing\\winrt\\lib\\windows\\trialownership.cpp",
        (unsigned int)v13);
      v14 = ppv;
      if ( ppv )
      {
        ppv = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v14 + 16LL))(v14);
      }
      v15 = v44;
      if ( v44 )
      {
        v44 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      }
      return v9;
    }
    v43 = 0;
    v16 = (**(__int64 (__fastcall ***)(LPVOID, __int64 *, HSTRING *))ppv)(ppv, qword_1801F84B8, &v43);
    v9 = v16;
    if ( v16 < 0 )
    {
      sub_18000EF10(
        retaddr,
        70,
        "onecoreuap\\enduser\\winstore\\licensing\\winrt\\lib\\windows\\trialownership.cpp",
        (unsigned int)v16);
      v17 = v43;
      if ( v43 )
      {
        v43 = 0;
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v17 + 16LL))(v17);
      }
      v18 = ppv;
      if ( ppv )
      {
        ppv = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v18 + 16LL))(v18);
      }
      v19 = v44;
      if ( v44 )
      {
        v44 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      }
      return v9;
    }
    v20 = (*(__int64 (__fastcall **)(HSTRING, LPVOID, __int64, __int64, __int64, _DWORD, int, _QWORD, int))(*(_QWORD *)v43 + 32LL))(
            v43,
            ppv,
            0xFFFFFFFFLL,
            0xFFFFFFFFLL,
            -1,
            0,
            3,
            0,
            64);
    v9 = v20;
    if ( v20 < 0 )
    {
      sub_18000EF10(
        retaddr,
        71,
        "onecoreuap\\enduser\\winstore\\licensing\\winrt\\lib\\windows\\trialownership.cpp",
        (unsigned int)v20);
      v21 = v43;
      if ( v43 )
      {
        v43 = 0;
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v21 + 16LL))(v21);
      }
      v22 = ppv;
      if ( ppv )
      {
        ppv = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v22 + 16LL))(v22);
      }
      v23 = v44;
      if ( v44 )
      {
        v44 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
      }
      return v9;
    }
    v24 = ppv;
    v25 = *(__int64 (__fastcall **)(LPVOID, HSTRING, PCWSTR, const WCHAR *, _DWORD *))(*(_QWORD *)ppv + 544LL);
    StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
    v27 = v25(v24, v46, StringRawBuffer, L"https://login.microsoft.com", a3);
    v9 = v27;
    if ( v27 < 0 )
    {
      sub_18000EF10(
        retaddr,
        73,
        "onecoreuap\\enduser\\winstore\\licensing\\winrt\\lib\\windows\\trialownership.cpp",
        (unsigned int)v27);
      v28 = v43;
      if ( v43 )
      {
        v43 = 0;
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v28 + 16LL))(v28);
      }
      v29 = ppv;
      if ( ppv )
      {
        ppv = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v29 + 16LL))(v29);
      }
      v30 = v44;
      if ( v44 )
      {
        v44 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
      }
      return v9;
    }
    v31 = v43;
    if ( v43 )
    {
      v43 = 0;
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v31 + 16LL))(v31);
    }
    v32 = ppv;
    if ( ppv )
    {
      ppv = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v32 + 16LL))(v32);
    }
    v33 = v44;
    if ( v44 )
    {
      v44 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    }
    return 0;
  }
  WindowsDeleteString(0);
  v46 = 0;
  v34 = WindowsGetStringRawBuffer(a2, 0);
  v35 = o__wcstoui64(v34, 0, 10);
  if ( (unsigned __int64)(v35 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v36 = -2147024809;
    v37 = 25;
    WindowsGetStringRawBuffer(a2, 0);
  }
  else
  {
    if ( (unsigned int)sub_18000500C(&hstringHeader, 17, 16, L"%016llX", v35) == 16 )
    {
      v38 = 0;
      v43 = 0;
      v39 = -1;
      do
        ++v39;
      while ( *(_WORD *)&hstringHeader.Reserved.Reserved2[2 * v39] );
      if ( v39 <= 0xFFFFFFFF )
      {
        WindowsDeleteString(0);
        v43 = 0;
        WindowsCreateString((PCNZWCH)&hstringHeader, v39, &v43);
        v38 = v43;
      }
      v43 = 0;
      v46 = v38;
      WindowsDeleteString(0);
      v43 = 0;
      WindowsDeleteString(0);
      v43 = 0;
      v40 = sub_1801479F8(L"PrimaryWebAccountId");
      v9 = v40;
      if ( v40 < 0 )
      {
        sub_18000EF10(
          retaddr,
          89,
          "onecoreuap\\enduser\\winstore\\licensing\\winrt\\lib\\windows\\trialownership.cpp",
          (unsigned int)v40);
        WindowsDeleteString(v43);
        WindowsDeleteString(v38);
        return v9;
      }
      v41 = WindowsGetStringRawBuffer(v38, 0);
      v42 = WindowsGetStringRawBuffer(v43, 0);
      if ( CompareStringOrdinal(v42, -1, v41, -1, 1) == 2 )
        *a3 = 1;
      WindowsDeleteString(v43);
      WindowsDeleteString(v38);
      return 0;
    }
    v36 = -2143330041;
    v37 = 34;
  }
  sub_1801517A8(
    1,
    (unsigned int)"onecoreuap\\enduser\\winstore\\licensing\\winrt\\lib\\windows\\trialownership.cpp",
    v37,
    (unsigned int)"Windows::Services::Store::Internal::ConvertPUIDFromDecToHex",
    -2147024809);
  sub_18000EF10(retaddr, 86, "onecoreuap\\enduser\\winstore\\licensing\\winrt\\lib\\windows\\trialownership.cpp", v36);
  WindowsDeleteString(0);
  return v36;
}

```

## disassembly

```asm
0x1800d5adc  mov     [rsp-8+arg_18], rbx
0x1800d5ae1  push    rbp
0x1800d5ae2  push    rsi
0x1800d5ae3  push    rdi
0x1800d5ae4  push    r12
0x1800d5ae6  push    r13
0x1800d5ae8  push    r14
0x1800d5aea  push    r15
0x1800d5aec  lea     rbp, [rsp-27h]
0x1800d5af1  sub     rsp, 0A0h
0x1800d5af8  mov     rax, cs:__security_cookie
0x1800d5aff  xor     rax, rsp
0x1800d5b02  mov     [rbp+57h+var_38], rax
0x1800d5b06  mov     r15, r8
0x1800d5b09  mov     r13, rdx
0x1800d5b0c  mov     rsi, rcx
0x1800d5b0f  xor     r12d, r12d
0x1800d5b12  mov     [r8], r12d
0x1800d5b15  call    sub_18014EF50
0x1800d5b1a  test    al, al
0x1800d5b1c  jz      loc_1800D5EE4
0x1800d5b22  test    rsi, rsi
0x1800d5b25  jnz     short loc_1800D5B31
0x1800d5b27  mov     eax, 80070057h
0x1800d5b2c  jmp     loc_1800D60DD
0x1800d5b31  mov     [rbp+57h+var_68], r12
0x1800d5b35  mov     [rbp+57h+var_78], r12
0x1800d5b39  mov     [rbp+57h+string], r12
0x1800d5b3d  lea     r9, [rbp+57h+string]; string
0x1800d5b41  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800d5b45  mov     edx, 23h ; '#'; length
0x1800d5b4a  lea     rcx, aWindowsSystemI; "Windows.System.Internal.UserManager"
0x1800d5b51  call    cs:WindowsCreateStringReference
0x1800d5b57  test    eax, eax
0x1800d5b59  js      loc_1800D6104
0x1800d5b5f  mov     rbx, [rbp+57h+string]
0x1800d5b63  mov     rcx, [rbp+57h+var_78]
0x1800d5b67  test    rcx, rcx
0x1800d5b6a  jz      short loc_1800D5B7D
0x1800d5b6c  mov     [rbp+57h+var_78], r12
0x1800d5b70  mov     rax, [rcx]
0x1800d5b73  mov     rax, [rax+10h]
0x1800d5b77  call    j__guard_dispatch_icall
0x1800d5b7c  nop
0x1800d5b7d  lea     r8, [rbp+57h+var_78]
0x1800d5b81  lea     rdx, qword_1801A8180
0x1800d5b88  mov     rcx, rbx
0x1800d5b8b  call    cs:RoGetActivationFactory
0x1800d5b91  mov     ebx, eax
0x1800d5b93  test    eax, eax
0x1800d5b95  jns     short loc_1800D5BD1
0x1800d5b97  mov     rcx, [rbp+5Fh]
0x1800d5b9b  mov     r9d, eax
0x1800d5b9e  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\licensin"...
0x1800d5ba5  mov     edx, 3Fh ; '?'
0x1800d5baa  call    sub_18000EF10
0x1800d5baf  nop
0x1800d5bb0  mov     rcx, [rbp+57h+var_78]
0x1800d5bb4  test    rcx, rcx
0x1800d5bb7  jz      short loc_1800D5BCA
0x1800d5bb9  mov     [rbp+57h+var_78], r12
0x1800d5bbd  mov     rax, [rcx]
0x1800d5bc0  mov     rax, [rax+10h]
0x1800d5bc4  call    j__guard_dispatch_icall
0x1800d5bc9  nop
0x1800d5bca  mov     eax, ebx
0x1800d5bcc  jmp     loc_1800D60DD
0x1800d5bd1  mov     rcx, [rbp+57h+var_78]
0x1800d5bd5  mov     rax, [rcx]
0x1800d5bd8  lea     r8, [rbp+57h+var_68]
0x1800d5bdc  mov     rdx, rsi
0x1800d5bdf  mov     rax, [rax+88h]
0x1800d5be6  call    j__guard_dispatch_icall
0x1800d5beb  mov     ebx, eax
0x1800d5bed  test    eax, eax
0x1800d5bef  jns     short loc_1800D5C26
0x1800d5bf1  mov     rcx, [rbp+5Fh]
0x1800d5bf5  mov     r9d, eax
0x1800d5bf8  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\licensin"...
0x1800d5bff  mov     edx, 40h ; '@'
0x1800d5c04  call    sub_18000EF10
0x1800d5c09  nop
0x1800d5c0a  mov     rcx, [rbp+57h+var_78]
0x1800d5c0e  test    rcx, rcx
0x1800d5c11  jz      short loc_1800D5C24
0x1800d5c13  mov     [rbp+57h+var_78], r12
0x1800d5c17  mov     rax, [rcx]
0x1800d5c1a  mov     rax, [rax+10h]
0x1800d5c1e  call    j__guard_dispatch_icall
0x1800d5c23  nop
0x1800d5c24  jmp     short loc_1800D5BCA
0x1800d5c26  mov     [rbp+57h+var_70], r12
0x1800d5c2a  lea     rax, [rbp+57h+var_70]
0x1800d5c2e  mov     [rsp+0D0h+ppv], rax; ppv
0x1800d5c33  lea     r9, stru_1801FAED8; riid
0x1800d5c3a  xor     edx, edx; pUnkOuter
0x1800d5c3c  lea     r8d, [rdx+17h]; dwClsContext
0x1800d5c40  lea     rcx, stru_1801FAEC8; rclsid
0x1800d5c47  call    cs:__imp_CoCreateInstance
0x1800d5c4d  mov     ebx, eax
0x1800d5c4f  test    eax, eax
0x1800d5c51  jns     short loc_1800D5CA5
0x1800d5c53  mov     rcx, [rbp+5Fh]
0x1800d5c57  mov     r9d, eax
0x1800d5c5a  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\licensin"...
0x1800d5c61  mov     edx, 43h ; 'C'
0x1800d5c66  call    sub_18000EF10
0x1800d5c6b  nop
0x1800d5c6c  mov     rcx, [rbp+57h+var_70]
0x1800d5c70  test    rcx, rcx
0x1800d5c73  jz      short loc_1800D5C86
0x1800d5c75  mov     [rbp+57h+var_70], r12
0x1800d5c79  mov     rax, [rcx]
0x1800d5c7c  mov     rax, [rax+10h]
0x1800d5c80  call    j__guard_dispatch_icall
0x1800d5c85  nop
0x1800d5c86  mov     rcx, [rbp+57h+var_78]
0x1800d5c8a  test    rcx, rcx
0x1800d5c8d  jz      short loc_1800D5CA0
0x1800d5c8f  mov     [rbp+57h+var_78], r12
0x1800d5c93  mov     rax, [rcx]
0x1800d5c96  mov     rax, [rax+10h]
0x1800d5c9a  call    j__guard_dispatch_icall
0x1800d5c9f  nop
0x1800d5ca0  jmp     loc_1800D5BCA
0x1800d5ca5  mov     [rbp+57h+var_80], r12
0x1800d5ca9  mov     rcx, [rbp+57h+var_70]
0x1800d5cad  mov     rax, [rcx]
0x1800d5cb0  lea     r8, [rbp+57h+var_80]
0x1800d5cb4  lea     rdx, qword_1801F84B8
0x1800d5cbb  mov     rax, [rax]
0x1800d5cbe  call    j__guard_dispatch_icall
0x1800d5cc3  mov     ebx, eax
0x1800d5cc5  test    eax, eax
0x1800d5cc7  jns     short loc_1800D5D35
0x1800d5cc9  mov     rcx, [rbp+5Fh]
0x1800d5ccd  mov     r9d, eax
0x1800d5cd0  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\licensin"...
0x1800d5cd7  mov     edx, 46h ; 'F'
0x1800d5cdc  call    sub_18000EF10
0x1800d5ce1  nop
0x1800d5ce2  mov     rcx, [rbp+57h+var_80]
0x1800d5ce6  test    rcx, rcx
0x1800d5ce9  jz      short loc_1800D5CFC
0x1800d5ceb  mov     [rbp+57h+var_80], r12
0x1800d5cef  mov     rax, [rcx]
0x1800d5cf2  mov     rax, [rax+10h]
0x1800d5cf6  call    j__guard_dispatch_icall
0x1800d5cfb  nop
0x1800d5cfc  mov     rcx, [rbp+57h+var_70]
0x1800d5d00  test    rcx, rcx
0x1800d5d03  jz      short loc_1800D5D16
0x1800d5d05  mov     [rbp+57h+var_70], r12
0x1800d5d09  mov     rax, [rcx]
0x1800d5d0c  mov     rax, [rax+10h]
0x1800d5d10  call    j__guard_dispatch_icall
0x1800d5d15  nop
0x1800d5d16  mov     rcx, [rbp+57h+var_78]
0x1800d5d1a  test    rcx, rcx
0x1800d5d1d  jz      short loc_1800D5D30
0x1800d5d1f  mov     [rbp+57h+var_78], r12
0x1800d5d23  mov     rax, [rcx]
0x1800d5d26  mov     rax, [rax+10h]
0x1800d5d2a  call    j__guard_dispatch_icall
0x1800d5d2f  nop
0x1800d5d30  jmp     loc_1800D5BCA
0x1800d5d35  mov     rcx, [rbp+57h+var_80]
0x1800d5d39  mov     rax, [rcx]
0x1800d5d3c  mov     [rsp+0D0h+var_90], 40h ; '@'
0x1800d5d44  mov     [rsp+0D0h+var_98], r12
0x1800d5d49  mov     dword ptr [rsp+0D0h+var_A0], 3
0x1800d5d51  mov     dword ptr [rsp+0D0h+var_A8], r12d
0x1800d5d56  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800d5d5a  mov     [rsp+0D0h+ppv], r14
0x1800d5d5f  mov     edx, 0FFFFFFFFh
0x1800d5d64  mov     r9d, edx
0x1800d5d67  mov     r8d, edx
0x1800d5d6a  mov     rdx, [rbp+57h+var_70]
0x1800d5d6e  mov     rax, [rax+20h]
0x1800d5d72  call    j__guard_dispatch_icall
0x1800d5d77  mov     ebx, eax
0x1800d5d79  test    eax, eax
0x1800d5d7b  jns     short loc_1800D5DE8
0x1800d5d7d  mov     rcx, [rbp+5Fh]
0x1800d5d81  mov     r9d, eax
0x1800d5d84  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\licensin"...
0x1800d5d8b  lea     edx, [r14+48h]
0x1800d5d8f  call    sub_18000EF10
0x1800d5d94  nop
0x1800d5d95  mov     rcx, [rbp+57h+var_80]
0x1800d5d99  test    rcx, rcx
0x1800d5d9c  jz      short loc_1800D5DAF
0x1800d5d9e  mov     [rbp+57h+var_80], r12
0x1800d5da2  mov     rax, [rcx]
0x1800d5da5  mov     rax, [rax+10h]
0x1800d5da9  call    j__guard_dispatch_icall
0x1800d5dae  nop
0x1800d5daf  mov     rcx, [rbp+57h+var_70]
0x1800d5db3  test    rcx, rcx
0x1800d5db6  jz      short loc_1800D5DC9
0x1800d5db8  mov     [rbp+57h+var_70], r12
0x1800d5dbc  mov     rax, [rcx]
0x1800d5dbf  mov     rax, [rax+10h]
0x1800d5dc3  call    j__guard_dispatch_icall
0x1800d5dc8  nop
0x1800d5dc9  mov     rcx, [rbp+57h+var_78]
0x1800d5dcd  test    rcx, rcx
0x1800d5dd0  jz      short loc_1800D5DE3
0x1800d5dd2  mov     [rbp+57h+var_78], r12
0x1800d5dd6  mov     rax, [rcx]
0x1800d5dd9  mov     rax, [rax+10h]
0x1800d5ddd  call    j__guard_dispatch_icall
0x1800d5de2  nop
0x1800d5de3  jmp     loc_1800D5BCA
0x1800d5de8  mov     rdi, [rbp+57h+var_70]
0x1800d5dec  mov     rax, [rdi]
0x1800d5def  mov     rbx, [rax+220h]
0x1800d5df6  xor     edx, edx; length
0x1800d5df8  mov     rcx, r13; string
0x1800d5dfb  call    cs:WindowsGetStringRawBuffer
0x1800d5e01  mov     [rsp+0D0h+ppv], r15
0x1800d5e06  lea     r9, aHttpsLoginMicr; "https://login.microsoft.com"
0x1800d5e0d  mov     r8, rax
0x1800d5e10  mov     rdx, [rbp+57h+var_68]
0x1800d5e14  mov     rcx, rdi
0x1800d5e17  mov     rax, rbx
0x1800d5e1a  call    j__guard_dispatch_icall
0x1800d5e1f  mov     ebx, eax
0x1800d5e21  test    eax, eax
0x1800d5e23  jns     short loc_1800D5E91
0x1800d5e25  mov     rcx, [rbp+5Fh]
0x1800d5e29  mov     r9d, eax
0x1800d5e2c  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\licensin"...
0x1800d5e33  mov     edx, 49h ; 'I'
0x1800d5e38  call    sub_18000EF10
0x1800d5e3d  nop
0x1800d5e3e  mov     rcx, [rbp+57h+var_80]
0x1800d5e42  test    rcx, rcx
0x1800d5e45  jz      short loc_1800D5E58
0x1800d5e47  mov     [rbp+57h+var_80], r12
0x1800d5e4b  mov     rax, [rcx]
0x1800d5e4e  mov     rax, [rax+10h]
0x1800d5e52  call    j__guard_dispatch_icall
0x1800d5e57  nop
0x1800d5e58  mov     rcx, [rbp+57h+var_70]
0x1800d5e5c  test    rcx, rcx
0x1800d5e5f  jz      short loc_1800D5E72
0x1800d5e61  mov     [rbp+57h+var_70], r12
0x1800d5e65  mov     rax, [rcx]
0x1800d5e68  mov     rax, [rax+10h]
0x1800d5e6c  call    j__guard_dispatch_icall
0x1800d5e71  nop
0x1800d5e72  mov     rcx, [rbp+57h+var_78]
0x1800d5e76  test    rcx, rcx
0x1800d5e79  jz      short loc_1800D5E8C
0x1800d5e7b  mov     [rbp+57h+var_78], r12
0x1800d5e7f  mov     rax, [rcx]
0x1800d5e82  mov     rax, [rax+10h]
0x1800d5e86  call    j__guard_dispatch_icall
0x1800d5e8b  nop
0x1800d5e8c  jmp     loc_1800D5BCA
0x1800d5e91  mov     rcx, [rbp+57h+var_80]
0x1800d5e95  test    rcx, rcx
0x1800d5e98  jz      short loc_1800D5EAB
0x1800d5e9a  mov     [rbp+57h+var_80], r12
0x1800d5e9e  mov     rax, [rcx]
0x1800d5ea1  mov     rax, [rax+10h]
0x1800d5ea5  call    j__guard_dispatch_icall
0x1800d5eaa  nop
0x1800d5eab  mov     rcx, [rbp+57h+var_70]
0x1800d5eaf  test    rcx, rcx
0x1800d5eb2  jz      short loc_1800D5EC5
0x1800d5eb4  mov     [rbp+57h+var_70], r12
0x1800d5eb8  mov     rax, [rcx]
0x1800d5ebb  mov     rax, [rax+10h]
0x1800d5ebf  call    j__guard_dispatch_icall
0x1800d5ec4  nop
0x1800d5ec5  mov     rcx, [rbp+57h+var_78]
0x1800d5ec9  test    rcx, rcx
0x1800d5ecc  jz      short loc_1800D5EDF
0x1800d5ece  mov     [rbp+57h+var_78], r12
0x1800d5ed2  mov     rax, [rcx]
0x1800d5ed5  mov     rax, [rax+10h]
0x1800d5ed9  call    j__guard_dispatch_icall
0x1800d5ede  nop
0x1800d5edf  jmp     loc_1800D6069
0x1800d5ee4  mov     [rbp+57h+var_68], r12
0x1800d5ee8  xor     ecx, ecx; string
0x1800d5eea  call    cs:WindowsDeleteString
0x1800d5ef0  mov     [rbp+57h+var_68], r12
0x1800d5ef4  xor     edx, edx; length
0x1800d5ef6  mov     rcx, r13; string
0x1800d5ef9  call    cs:WindowsGetStringRawBuffer
0x1800d5eff  mov     rcx, rax
0x1800d5f02  xor     edx, edx
0x1800d5f04  lea     r8d, [rdx+0Ah]
0x1800d5f08  call    cs:_o__wcstoui64
0x1800d5f0e  lea     rcx, [rax-1]
0x1800d5f12  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800d5f16  ja      loc_1800D606D
  ... truncated ...
```
