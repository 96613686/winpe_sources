# sub_1800AFFA8

- ea: `0x1800affa8`
- end: `0x1800b0368`
- name: `sub_1800AFFA8`
- size: `960`
- prototype: ``
- caller_count: `4`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180024b10`
- `0x180035b70`
- `0x180045970`
- `0x18004bb64`

## callees

- `0x1800044c0`
- `0x1800113fc`
- `0x18001b940`
- `0x180038a50`
- `0x18003c3c8`
- `0x1800affa8`
- `0x1800b0518`
- `0x1800b200c`
- `0x1800b2710`
- `0x1801519b8`
- `0x180159010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800affde`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b0195`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b01e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b025b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b02e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b030a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b032e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800affde`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b0195`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b01e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b025b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b02e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b030a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b032e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b0054`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b0054`

## string_xrefs

- `0x1800b0230`: `ChkHr(spPackageManager->FindPackageByUserSecurityIdPackageFullName(sidString.Get(), fullName.Get(), ppPackage))`
- `0x1800b01b5`: `ChkHr(GetSidForUser(user, sidString.GetAddressOf()))`

## pseudocode

```c
__int64 __fastcall sub_1800AFFA8(__int64 a1, _QWORD *a2)
{
  int v4; // eax
  unsigned int v5; // edi
  HSTRING v6; // rcx
  HSTRING v7; // rbx
  HRESULT v8; // eax
  int v9; // eax
  __int64 v10; // rcx
  int v11; // eax
  __int64 v12; // rcx
  int v13; // eax
  __int64 v14; // rcx
  int v15; // eax
  __int64 v16; // rcx
  int v17; // eax
  __int64 v18; // rcx
  int v19; // eax
  __int64 v20; // rcx
  __int64 v21; // rcx
  _BYTE v23[8]; // [rsp+30h] [rbp-50h] BYREF
  __int64 v24; // [rsp+38h] [rbp-48h] BYREF
  HSTRING v25; // [rsp+40h] [rbp-40h] BYREF
  HSTRING v26; // [rsp+48h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-30h] BYREF
  HSTRING string; // [rsp+68h] [rbp-18h] BYREF

  *a2 = 0;
  WindowsDeleteString(0);
  v26 = 0;
  v4 = sub_1800B0518(&v26);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v7 = v26;
    if ( v26 )
    {
      v24 = 0;
      string = 0;
      v8 = WindowsCreateStringReference(L"Windows.Management.Deployment.PackageManager", 0x2Cu, &hstringHeader, &string);
      if ( v8 < 0 )
      {
        sub_18003C3C8((unsigned int)v8);
        JUMPOUT(0x1800B0367LL);
      }
      v9 = sub_1800113FC(string, &v24);
      v5 = v9;
      if ( v9 >= 0 )
      {
        v23[0] = 0;
        v11 = sub_1800B2710(v23);
        v5 = v11;
        if ( v11 >= 0 )
        {
          if ( v23[0] )
          {
            v13 = (*(__int64 (__fastcall **)(__int64, HSTRING, _QWORD *))(*(_QWORD *)v24 + 136LL))(v24, v7, a2);
            v5 = v13;
            if ( v13 < 0 )
            {
              sub_1801519B8(
                (unsigned int)"onecoreuap\\enduser\\winstore\\licensing\\winrt\\lib\\windows\\clientprocessutils.cpp",
                642,
                (unsigned int)"ClientProcessUtils::GetCallingAppPackage",
                (unsigned int)"ChkHr(spPackageManager->FindPackageByPackageFullName(fullName.Get(), ppPackage))",
                v13);
              sub_18001B940(v5);
              v14 = v24;
              if ( v24 )
              {
                v24 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
              }
              goto LABEL_35;
            }
          }
          else
          {
            v25 = 0;
            WindowsDeleteString(0);
            v25 = 0;
            v15 = sub_1800B200C(a1, &v25);
            v5 = v15;
            if ( v15 < 0 )
            {
              sub_1801519B8(
                (unsigned int)"onecoreuap\\enduser\\winstore\\licensing\\winrt\\lib\\windows\\clientprocessutils.cpp",
                647,
                (unsigned int)"ClientProcessUtils::GetCallingAppPackage",
                (unsigned int)"ChkHr(GetSidForUser(user, sidString.GetAddressOf()))",
                v15);
              sub_18001B940(v5);
              WindowsDeleteString(v25);
              v25 = 0;
              v16 = v24;
              if ( v24 )
              {
                v24 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
              }
              goto LABEL_35;
            }
            v17 = (*(__int64 (__fastcall **)(__int64, HSTRING, HSTRING, _QWORD *))(*(_QWORD *)v24 + 168LL))(
                    v24,
                    v25,
                    v7,
                    a2);
            v5 = v17;
            if ( v17 < 0 )
            {
              sub_1801519B8(
                (unsigned int)"onecoreuap\\enduser\\winstore\\licensing\\winrt\\lib\\windows\\clientprocessutils.cpp",
                648,
                (unsigned int)"ClientProcessUtils::GetCallingAppPackage",
                (unsigned int)"ChkHr(spPackageManager->FindPackageByUserSecurityIdPackageFullName(sidString.Get(), fullNa"
                              "me.Get(), ppPackage))",
                v17);
              sub_18001B940(v5);
              WindowsDeleteString(v25);
              v25 = 0;
              v18 = v24;
              if ( v24 )
              {
                v24 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
              }
              goto LABEL_35;
            }
            if ( !*a2 )
            {
              v19 = (*(__int64 (__fastcall **)(__int64, HSTRING, _QWORD *))(*(_QWORD *)v24 + 136LL))(v24, v7, a2);
              if ( v19 != -2147024891 )
              {
                v5 = v19;
                if ( v19 < 0 )
                {
                  sub_1801519B8(
                    (unsigned int)"onecoreuap\\enduser\\winstore\\licensing\\winrt\\lib\\windows\\clientprocessutils.cpp",
                    657,
                    (unsigned int)"ClientProcessUtils::GetCallingAppPackage",
                    (unsigned int)"ChkHr(hr)",
                    v19);
                  sub_18001B940(v5);
                  WindowsDeleteString(v25);
                  v25 = 0;
                  v20 = v24;
                  if ( v24 )
                  {
                    v24 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
                  }
                  goto LABEL_35;
                }
              }
            }
            WindowsDeleteString(v25);
          }
          v21 = v24;
          if ( v24 )
          {
            v24 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
          }
          goto LABEL_35;
        }
        sub_1801519B8(
          (unsigned int)"onecoreuap\\enduser\\winstore\\licensing\\winrt\\lib\\windows\\clientprocessutils.cpp",
          639,
          (unsigned int)"ClientProcessUtils::GetCallingAppPackage",
          (unsigned int)"ChkHr(ClientProcessUtils::IsCallerERA(&isERA))",
          v11);
        sub_18001B940(v5);
        v12 = v24;
        if ( v24 )
        {
          v24 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
        }
      }
      else
      {
        sub_1801519B8(
          (unsigned int)"onecoreuap\\enduser\\winstore\\licensing\\winrt\\lib\\windows\\clientprocessutils.cpp",
          636,
          (unsigned int)"ClientProcessUtils::GetCallingAppPackage",
          (unsigned int)"ChkHr(ActivateInstance( HStringReference(RuntimeClass_Windows_Management_Deployment_PackageManag"
                        "er).Get(), &spPackageManager))",
          v9);
        sub_18001B940(v5);
        v10 = v24;
        if ( v24 )
        {
          v24 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
        }
      }
    }
LABEL_35:
    v6 = v7;
    goto LABEL_36;
  }
  sub_1801519B8(
    (unsigned int)"onecoreuap\\enduser\\winstore\\licensing\\winrt\\lib\\windows\\clientprocessutils.cpp",
    630,
    (unsigned int)"ClientProcessUtils::GetCallingAppPackage",
    (unsigned int)"ChkHr(GetCallingAppPackageFullName(fullName.GetAddressOf()))",
    v4);
  sub_18001B940(v5);
  v6 = v26;
LABEL_36:
  WindowsDeleteString(v6);
  sub_180038A50(v5);
  return v5;
}

```

## disassembly

```asm
0x1800affa8  mov     [rsp-28h+arg_10], rbx
0x1800affad  push    rbp
0x1800affae  push    rsi
0x1800affaf  push    rdi
0x1800affb0  push    r14
0x1800affb2  push    r15
0x1800affb4  mov     rbp, rsp
0x1800affb7  sub     rsp, 80h
0x1800affbe  mov     rax, cs:__security_cookie
0x1800affc5  xor     rax, rsp
0x1800affc8  mov     [rbp+var_10], rax
0x1800affcc  mov     rsi, rdx
0x1800affcf  mov     r14, rcx
0x1800affd2  xor     r15d, r15d
0x1800affd5  mov     [rdx], r15
0x1800affd8  mov     [rbp+var_38], r15
0x1800affdc  xor     ecx, ecx; string
0x1800affde  call    cs:WindowsDeleteString
0x1800affe4  mov     [rbp+var_38], r15
0x1800affe8  lea     rcx, [rbp+var_38]
0x1800affec  call    sub_1800B0518
0x1800afff1  mov     edi, eax
0x1800afff3  test    eax, eax
0x1800afff5  jns     short loc_1800B002B
0x1800afff7  mov     [rsp+80h+var_60], eax
0x1800afffb  lea     r9, aChkhrGetcallin_1; "ChkHr(GetCallingAppPackageFullName(full"...
0x1800b0002  lea     r8, aClientprocessu_7; "ClientProcessUtils::GetCallingAppPackag"...
0x1800b0009  mov     edx, 276h
0x1800b000e  lea     rcx, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\licensin"...
0x1800b0015  call    sub_1801519B8
0x1800b001a  mov     ecx, edi
0x1800b001c  call    sub_18001B940
0x1800b0021  nop
0x1800b0022  mov     rcx, [rbp+var_38]
0x1800b0026  jmp     loc_1800B032E
0x1800b002b  mov     rbx, [rbp+var_38]
0x1800b002f  test    rbx, rbx
0x1800b0032  jz      loc_1800B032B
0x1800b0038  mov     [rbp+var_48], r15
0x1800b003c  mov     [rbp+string], r15
0x1800b0040  lea     r9, [rbp+string]; string
0x1800b0044  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800b0048  mov     edx, 2Ch ; ','; length
0x1800b004d  lea     rcx, aWindowsManagem; "Windows.Management.Deployment.PackageMa"...
0x1800b0054  call    cs:WindowsCreateStringReference
0x1800b005a  test    eax, eax
0x1800b005c  js      loc_1800B0360
0x1800b0062  lea     rdx, [rbp+var_48]
0x1800b0066  mov     rcx, [rbp+string]
0x1800b006a  call    sub_1800113FC
0x1800b006f  mov     edi, eax
0x1800b0071  test    eax, eax
0x1800b0073  jns     short loc_1800B00BF
0x1800b0075  mov     [rsp+80h+var_60], eax
0x1800b0079  lea     r9, aChkhrActivatei_4; "ChkHr(ActivateInstance( HStringReferenc"...
0x1800b0080  lea     r8, aClientprocessu_7; "ClientProcessUtils::GetCallingAppPackag"...
0x1800b0087  mov     edx, 27Ch
0x1800b008c  lea     rcx, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\licensin"...
0x1800b0093  call    sub_1801519B8
0x1800b0098  mov     ecx, edi
0x1800b009a  call    sub_18001B940
0x1800b009f  nop
0x1800b00a0  mov     rcx, [rbp+var_48]
0x1800b00a4  test    rcx, rcx
0x1800b00a7  jz      short loc_1800B00BA
0x1800b00a9  mov     [rbp+var_48], r15
0x1800b00ad  mov     rax, [rcx]
0x1800b00b0  mov     rax, [rax+10h]
0x1800b00b4  call    j__guard_dispatch_icall
0x1800b00b9  nop
0x1800b00ba  jmp     loc_1800B032B
0x1800b00bf  mov     [rbp+var_50], r15b
0x1800b00c3  lea     rcx, [rbp+var_50]
0x1800b00c7  call    sub_1800B2710
0x1800b00cc  mov     edi, eax
0x1800b00ce  test    eax, eax
0x1800b00d0  jns     short loc_1800B011C
0x1800b00d2  mov     [rsp+80h+var_60], eax
0x1800b00d6  lea     r9, aChkhrClientpro_13; "ChkHr(ClientProcessUtils::IsCallerERA(&"...
0x1800b00dd  lea     r8, aClientprocessu_7; "ClientProcessUtils::GetCallingAppPackag"...
0x1800b00e4  mov     edx, 27Fh
0x1800b00e9  lea     rcx, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\licensin"...
0x1800b00f0  call    sub_1801519B8
0x1800b00f5  mov     ecx, edi
0x1800b00f7  call    sub_18001B940
0x1800b00fc  nop
0x1800b00fd  mov     rcx, [rbp+var_48]
0x1800b0101  test    rcx, rcx
0x1800b0104  jz      short loc_1800B0117
0x1800b0106  mov     [rbp+var_48], r15
0x1800b010a  mov     rax, [rcx]
0x1800b010d  mov     rax, [rax+10h]
0x1800b0111  call    j__guard_dispatch_icall
0x1800b0116  nop
0x1800b0117  jmp     loc_1800B032B
0x1800b011c  cmp     [rbp+var_50], r15b
0x1800b0120  jz      short loc_1800B018F
0x1800b0122  mov     rcx, [rbp+var_48]
0x1800b0126  mov     rax, [rcx]
0x1800b0129  mov     r8, rsi
0x1800b012c  mov     rdx, rbx
0x1800b012f  mov     rax, [rax+88h]
0x1800b0136  call    j__guard_dispatch_icall
0x1800b013b  mov     edi, eax
0x1800b013d  test    eax, eax
0x1800b013f  jns     loc_1800B0311
0x1800b0145  mov     [rsp+80h+var_60], eax
0x1800b0149  lea     r9, aChkhrSppackage_2; "ChkHr(spPackageManager->FindPackageByPa"...
0x1800b0150  lea     r8, aClientprocessu_7; "ClientProcessUtils::GetCallingAppPackag"...
0x1800b0157  mov     edx, 282h
0x1800b015c  lea     rcx, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\licensin"...
0x1800b0163  call    sub_1801519B8
0x1800b0168  mov     ecx, edi
0x1800b016a  call    sub_18001B940
0x1800b016f  nop
0x1800b0170  mov     rcx, [rbp+var_48]
0x1800b0174  test    rcx, rcx
0x1800b0177  jz      short loc_1800B018A
0x1800b0179  mov     [rbp+var_48], r15
0x1800b017d  mov     rax, [rcx]
0x1800b0180  mov     rax, [rax+10h]
0x1800b0184  call    j__guard_dispatch_icall
0x1800b0189  nop
0x1800b018a  jmp     loc_1800B032B
0x1800b018f  mov     [rbp+var_40], r15
0x1800b0193  xor     ecx, ecx; string
0x1800b0195  call    cs:WindowsDeleteString
0x1800b019b  mov     [rbp+var_40], r15
0x1800b019f  lea     rdx, [rbp+var_40]
0x1800b01a3  mov     rcx, r14
0x1800b01a6  call    sub_1800B200C
0x1800b01ab  mov     edi, eax
0x1800b01ad  test    eax, eax
0x1800b01af  jns     short loc_1800B0209
0x1800b01b1  mov     [rsp+80h+var_60], eax
0x1800b01b5  lea     r9, aChkhrGetsidfor; "ChkHr(GetSidForUser(user, sidString.Get"...
0x1800b01bc  lea     r8, aClientprocessu_7; "ClientProcessUtils::GetCallingAppPackag"...
0x1800b01c3  mov     edx, 287h
0x1800b01c8  lea     rcx, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\licensin"...
0x1800b01cf  call    sub_1801519B8
0x1800b01d4  mov     ecx, edi
0x1800b01d6  call    sub_18001B940
0x1800b01db  nop
0x1800b01dc  mov     rcx, [rbp+var_40]; string
0x1800b01e0  call    cs:WindowsDeleteString
0x1800b01e6  mov     [rbp+var_40], r15
0x1800b01ea  mov     rcx, [rbp+var_48]
0x1800b01ee  test    rcx, rcx
0x1800b01f1  jz      short loc_1800B0204
0x1800b01f3  mov     [rbp+var_48], r15
0x1800b01f7  mov     rax, [rcx]
0x1800b01fa  mov     rax, [rax+10h]
0x1800b01fe  call    j__guard_dispatch_icall
0x1800b0203  nop
0x1800b0204  jmp     loc_1800B032B
0x1800b0209  mov     rcx, [rbp+var_48]
0x1800b020d  mov     rax, [rcx]
0x1800b0210  mov     r9, rsi
0x1800b0213  mov     r8, rbx
0x1800b0216  mov     rdx, [rbp+var_40]
0x1800b021a  mov     rax, [rax+0A8h]
0x1800b0221  call    j__guard_dispatch_icall
0x1800b0226  mov     edi, eax
0x1800b0228  test    eax, eax
0x1800b022a  jns     short loc_1800B0284
0x1800b022c  mov     [rsp+80h+var_60], eax
0x1800b0230  lea     r9, aChkhrSppackage_3; "ChkHr(spPackageManager->FindPackageByUs"...
0x1800b0237  lea     r8, aClientprocessu_7; "ClientProcessUtils::GetCallingAppPackag"...
0x1800b023e  mov     edx, 288h
0x1800b0243  lea     rcx, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\licensin"...
0x1800b024a  call    sub_1801519B8
0x1800b024f  mov     ecx, edi
0x1800b0251  call    sub_18001B940
0x1800b0256  nop
0x1800b0257  mov     rcx, [rbp+var_40]; string
0x1800b025b  call    cs:WindowsDeleteString
0x1800b0261  mov     [rbp+var_40], r15
0x1800b0265  mov     rcx, [rbp+var_48]
0x1800b0269  test    rcx, rcx
0x1800b026c  jz      short loc_1800B027F
0x1800b026e  mov     [rbp+var_48], r15
0x1800b0272  mov     rax, [rcx]
0x1800b0275  mov     rax, [rax+10h]
0x1800b0279  call    j__guard_dispatch_icall
0x1800b027e  nop
0x1800b027f  jmp     loc_1800B032B
0x1800b0284  cmp     [rsi], r15
0x1800b0287  jnz     short loc_1800B0306
0x1800b0289  mov     rcx, [rbp+var_48]
0x1800b028d  mov     rax, [rcx]
0x1800b0290  mov     r8, rsi
0x1800b0293  mov     rdx, rbx
0x1800b0296  mov     rax, [rax+88h]
0x1800b029d  call    j__guard_dispatch_icall
0x1800b02a2  mov     esi, eax
0x1800b02a4  cmp     eax, 80070005h
0x1800b02a9  jz      short loc_1800B0306
0x1800b02ab  mov     edi, eax
0x1800b02ad  test    eax, eax
0x1800b02af  jns     short loc_1800B0306
0x1800b02b1  mov     [rsp+80h+var_60], eax
0x1800b02b5  lea     r9, aChkhrHr; "ChkHr(hr)"
0x1800b02bc  lea     r8, aClientprocessu_7; "ClientProcessUtils::GetCallingAppPackag"...
0x1800b02c3  mov     edx, 291h
0x1800b02c8  lea     rcx, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\licensin"...
0x1800b02cf  call    sub_1801519B8
0x1800b02d4  mov     ecx, edi
0x1800b02d6  call    sub_18001B940
0x1800b02db  nop
0x1800b02dc  mov     rcx, [rbp+var_40]; string
0x1800b02e0  call    cs:WindowsDeleteString
0x1800b02e6  mov     [rbp+var_40], r15
0x1800b02ea  mov     rcx, [rbp+var_48]
0x1800b02ee  test    rcx, rcx
0x1800b02f1  jz      short loc_1800B0304
0x1800b02f3  mov     [rbp+var_48], r15
0x1800b02f7  mov     rax, [rcx]
0x1800b02fa  mov     rax, [rax+10h]
0x1800b02fe  call    j__guard_dispatch_icall
0x1800b0303  nop
0x1800b0304  jmp     short loc_1800B032B
0x1800b0306  mov     rcx, [rbp+var_40]; string
0x1800b030a  call    cs:WindowsDeleteString
0x1800b0310  nop
0x1800b0311  mov     rcx, [rbp+var_48]
0x1800b0315  test    rcx, rcx
0x1800b0318  jz      short loc_1800B032B
0x1800b031a  mov     [rbp+var_48], r15
0x1800b031e  mov     rax, [rcx]
0x1800b0321  mov     rax, [rax+10h]
0x1800b0325  call    j__guard_dispatch_icall
0x1800b032a  nop
0x1800b032b  mov     rcx, rbx; string
0x1800b032e  call    cs:WindowsDeleteString
0x1800b0334  mov     ecx, edi
0x1800b0336  call    sub_180038A50
0x1800b033b  mov     eax, edi
0x1800b033d  mov     rcx, [rbp+var_10]
0x1800b0341  xor     rcx, rsp; StackCookie
0x1800b0344  call    __security_check_cookie
0x1800b0349  mov     rbx, [rsp+80h+arg_10]
0x1800b0351  add     rsp, 80h
0x1800b0358  pop     r15
0x1800b035a  pop     r14
0x1800b035c  pop     rdi
0x1800b035d  pop     rsi
0x1800b035e  pop     rbp
0x1800b035f  retn
0x1800b0360  mov     ecx, eax
0x1800b0362  call    sub_18003C3C8
```
