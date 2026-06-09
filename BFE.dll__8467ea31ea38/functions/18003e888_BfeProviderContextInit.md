# BfeProviderContextInit

- ea: `0x18003e888`
- end: `0x18003ebd5`
- name: `BfeProviderContextInit`
- size: `845`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003e520`

## callees

- `0x1800039e4`
- `0x18000e000`
- `0x18001236c`
- `0x180018b74`
- `0x180022730`
- `0x18003e888`
- `0x18003ebdc`
- `0x180058b30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003ea7a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003eae4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003ea7a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003eae4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ea0b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ea0b`

## string_xrefs

- `0x18003e8d0`: `System\CurrentControlSet\Services\BFE\Parameters\Policy\Options`
- `0x18003ea1b`: `RegOpenKeyExW`
- `0x18003ea33`: `BfeRegOpenKey`

## pseudocode

```c
__int64 BfeProviderContextInit()
{
  int v0; // r12d
  LPBYTE v1; // rsi
  int v2; // r14d
  unsigned int v3; // eax
  __int64 v4; // rcx
  __int64 v5; // rax
  __int64 v6; // rdi
  HKEY v7; // rbx
  unsigned int v8; // eax
  __int64 v9; // rcx
  LPBYTE lpData; // [rsp+30h] [rbp-D0h] BYREF
  LPBYTE v12; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v13[8]; // [rsp+40h] [rbp-C0h] BYREF
  int v14; // [rsp+80h] [rbp-80h]
  int v15; // [rsp+84h] [rbp-7Ch]
  const wchar_t *v16; // [rsp+88h] [rbp-78h]
  __int64 (__fastcall *v17)(); // [rsp+90h] [rbp-70h]
  __int64 (__fastcall *v18)(); // [rsp+98h] [rbp-68h]
  __int64 (__fastcall *v19)(); // [rsp+A0h] [rbp-60h]
  __int64 v20; // [rsp+A8h] [rbp-58h]
  __int64 (__fastcall *v21)(); // [rsp+B0h] [rbp-50h]
  __int64 (__fastcall *v22)(); // [rsp+B8h] [rbp-48h]
  __int64 v23; // [rsp+C0h] [rbp-40h]
  __int64 v24; // [rsp+C8h] [rbp-38h]
  __int64 (__fastcall *v25)(_QWORD, _QWORD); // [rsp+D0h] [rbp-30h]
  __int64 v26; // [rsp+D8h] [rbp-28h]
  __int64 (__fastcall *v27)(); // [rsp+E0h] [rbp-20h]
  __int64 (__fastcall *v28)(); // [rsp+E8h] [rbp-18h]
  __int64 v29; // [rsp+F0h] [rbp-10h]
  __int64 (__fastcall *v30)(int, int, int, int, __int64); // [rsp+F8h] [rbp-8h]
  __int64 v31; // [rsp+100h] [rbp+0h]
  __int64 (__fastcall *v32)(); // [rsp+108h] [rbp+8h]
  __int64 (__fastcall *v33)(); // [rsp+110h] [rbp+10h]
  __int64 v34; // [rsp+118h] [rbp+18h]
  __int64 (__fastcall *v35)(_QWORD); // [rsp+120h] [rbp+20h]
  DWORD cbData; // [rsp+130h] [rbp+30h]
  DWORD lpcbData; // [rsp+138h] [rbp+38h] BYREF
  HKEY hKey; // [rsp+140h] [rbp+40h] BYREF
  DWORD Type; // [rsp+148h] [rbp+48h] BYREF

  v13[0] = 1;
  v13[7] = 16;
  v13[1] = FWPM_OBJECT_TYPE_PROVIDER_CONTEXTS;
  v14 = -2144206842;
  v13[2] = L"ProviderContext";
  v20 = 0;
  v13[3] = BfeFwpmProviderContextCopy;
  v23 = 0;
  v13[4] = BfeDestroy_FWPM_PROVIDER_CONTEXT;
  v24 = 0;
  v13[5] = &FWPM_PROVIDER_CONTEXT_MARSHAL_Encode;
  v0 = 0;
  v26 = 0;
  v13[6] = &FWPM_PROVIDER_CONTEXT_MARSHAL_Decode;
  v1 = 0;
  v29 = 0;
  v15 = 0;
  v2 = 0;
  v31 = 357111107;
  v16 = L"O:LSG:LSD:(A;OICI;GA;;;BA)(A;OICI;GRGWGX;;;NO)(A;OICI;GRGWGX;;;S-1-5-80-3088073201-1464728630-1879813800-1107566"
         "885-823218052)(A;OICI;GRGX;;;S-1-5-80-3635958274-2059881490-2225992882-984577281-633327304)(A;OICI;GRGWGX;;;S-1"
         "-5-80-3044542841-3639452079-4096941652-1606687743-1256249853)(A;OICI;GRGWGX;;;S-1-5-80-979556362-403687129-3954"
         "533659-2335141334-1547273080)(A;OICI;GRGX;;;S-1-5-80-3139157870-2983391045-3678747466-658725712-1809340420)(A;O"
         "ICI;GRGWGX;;;S-1-5-80-1510742542-3632397484-604094731-3920060944-1272132581)(A;OICI;0x441;;;WD)(A;OICI;0x10000;"
         ";;CO)(A;OICI;0x50;;;WD)";
  v17 = BfeProviderContextCreate;
  v18 = BfeProviderContextDestroy;
  v19 = BfeProviderContextGetId;
  v21 = BfeProviderContextGetPublicState;
  v22 = BfeFwpmProviderContextLocalize;
  v25 = BfeProviderContextIsMatch;
  v27 = BfeDestroy_FWPM_CALLOUT_SUBSCRIPTION0;
  v28 = BfeFwpmProviderContextSubscriptionCopy;
  v30 = BfeProviderContextChangeNotify;
  v32 = BfeProviderContextAudit;
  v33 = FwppXmlWrite_FWPM_PROVIDER_CONTEXT;
  v35 = BfeFwpmProviderContextValidate;
  v34 = 0;
  cbData = 4;
  Type = 0;
  lpcbData = 0;
  lpData = 0;
  v12 = 0;
  hKey = 0;
  v3 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\BFE\\Parameters\\Policy\\Options",
         0,
         1u,
         &hKey);
  if ( (v3 & 0xFFFFFFFD) != 0 )
  {
    v5 = WfpReportSysErrorAsWinError(v4, "RegOpenKeyExW", v3);
    v6 = v5;
    if ( v5 )
      WfpReportError(v5, "BfeRegOpenKey");
    goto LABEL_15;
  }
  if ( v3 == 2 )
  {
    v6 = 0;
LABEL_15:
    v7 = 0;
    goto LABEL_16;
  }
  v7 = hKey;
  lpcbData = cbData;
  v6 = WfpMemAlloc(cbData, 0);
  if ( !v6 )
  {
    v8 = RegQueryValueExW(v7, L"EnableCGA", 0, &Type, lpData, &lpcbData);
    if ( v8 != 2 && v8 != 234 )
    {
      if ( v8 )
      {
        v6 = WfpReportSysErrorAsWinError(v9, "RegQueryValueExW", v8);
      }
      else if ( Type == 4 && lpcbData == cbData )
      {
        v1 = lpData;
        v12 = lpData;
        lpData = 0;
        v2 = 1;
      }
    }
  }
LABEL_16:
  WfpMemFree(&lpData);
  BfeRegCloseKey(v7);
  if ( v6 )
  {
    WfpReportError(v6, "BfeRegQueryValue");
  }
  else if ( v2 )
  {
    v0 = *(_DWORD *)v1;
  }
  WfpMemFree(&v12);
  if ( v6 )
  {
    WfpReportError(v6, "BfeRegQueryDWord");
LABEL_26:
    WfpReportError(v6, "BfeProviderContextInit");
    return v6;
  }
  if ( !v2 || (gBfeProvCtxtComponent = 1, !v0) )
    gBfeProvCtxtComponent = 0;
  v6 = BfeObjectTypeRegister(v13);
  if ( v6 )
    goto LABEL_26;
  return v6;
}

```

## disassembly

```asm
0x18003e888  push    rbp
0x18003e88a  push    rbx
0x18003e88b  push    rsi
0x18003e88c  push    rdi
0x18003e88d  push    r12
0x18003e88f  push    r13
0x18003e891  push    r14
0x18003e893  push    r15
0x18003e895  lea     rbp, [rsp-68h]
0x18003e89a  sub     rsp, 168h
0x18003e8a1  mov     rax, cs:__security_cookie
0x18003e8a8  xor     rax, rsp
0x18003e8ab  mov     [rbp+0A0h+var_50], rax
0x18003e8af  xor     r13d, r13d
0x18003e8b2  mov     [rsp+1A0h+var_160], 1
0x18003e8bb  lea     rax, FWPM_OBJECT_TYPE_PROVIDER_CONTEXTS
0x18003e8c2  mov     [rsp+1A0h+var_128], 10h
0x18003e8cb  mov     [rsp+1A0h+var_158], rax
0x18003e8d0  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\BF"...
0x18003e8d7  lea     rax, aProvidercontex; "ProviderContext"
0x18003e8de  mov     [rbp+0A0h+var_120], 80320006h
0x18003e8e5  mov     [rsp+1A0h+var_150], rax
0x18003e8ea  lea     r9d, [r13+1]; samDesired
0x18003e8ee  lea     rax, BfeFwpmProviderContextCopy
0x18003e8f5  mov     [rbp+0A0h+var_F8], r13
0x18003e8f9  mov     [rsp+1A0h+var_148], rax
0x18003e8fe  xor     r8d, r8d; ulOptions
0x18003e901  lea     rax, BfeDestroy_FWPM_PROVIDER_CONTEXT
0x18003e908  mov     [rbp+0A0h+var_E0], r13
0x18003e90c  mov     [rsp+1A0h+var_140], rax
0x18003e911  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003e918  lea     rax, FWPM_PROVIDER_CONTEXT_MARSHAL_Encode
0x18003e91f  mov     [rbp+0A0h+var_D8], r13
0x18003e923  mov     [rsp+1A0h+var_138], rax
0x18003e928  mov     r12d, r13d
0x18003e92b  lea     rax, FWPM_PROVIDER_CONTEXT_MARSHAL_Decode
0x18003e932  mov     [rbp+0A0h+var_C8], r13
0x18003e936  mov     [rsp+1A0h+var_130], rax
0x18003e93b  mov     esi, r13d
0x18003e93e  xor     eax, eax
0x18003e940  mov     [rbp+0A0h+var_B0], r13
0x18003e944  mov     [rbp+0A0h+var_11C], eax
0x18003e947  mov     r14d, r13d
0x18003e94a  lea     rax, aOLsgLsdAOiciGa_0; "O:LSG:LSD:(A;OICI;GA;;;BA)(A;OICI;GRGWG"...
0x18003e951  mov     [rbp+0A0h+var_A0], 15491543h
0x18003e959  mov     [rbp+0A0h+var_118], rax
0x18003e95d  lea     rax, BfeProviderContextCreate
0x18003e964  mov     [rbp+0A0h+var_110], rax
0x18003e968  lea     rax, BfeProviderContextDestroy
0x18003e96f  mov     [rbp+0A0h+var_108], rax
0x18003e973  lea     rax, BfeProviderContextGetId
0x18003e97a  mov     [rbp+0A0h+var_100], rax
0x18003e97e  lea     rax, BfeProviderContextGetPublicState
0x18003e985  mov     [rbp+0A0h+var_F0], rax
0x18003e989  lea     rax, BfeFwpmProviderContextLocalize
0x18003e990  mov     [rbp+0A0h+var_E8], rax
0x18003e994  lea     rax, BfeProviderContextIsMatch
0x18003e99b  mov     [rbp+0A0h+var_D0], rax
0x18003e99f  lea     rax, BfeDestroy_FWPM_CALLOUT_SUBSCRIPTION0
0x18003e9a6  mov     [rbp+0A0h+var_C0], rax
0x18003e9aa  lea     rax, BfeFwpmProviderContextSubscriptionCopy
0x18003e9b1  mov     [rbp+0A0h+var_B8], rax
0x18003e9b5  lea     rax, BfeProviderContextChangeNotify
0x18003e9bc  mov     [rbp+0A0h+var_A8], rax
0x18003e9c0  lea     rax, BfeProviderContextAudit
0x18003e9c7  mov     [rbp+0A0h+var_98], rax
0x18003e9cb  lea     rax, FwppXmlWrite_FWPM_PROVIDER_CONTEXT
0x18003e9d2  mov     [rbp+0A0h+var_90], rax
0x18003e9d6  lea     rax, BfeFwpmProviderContextValidate
0x18003e9dd  mov     [rbp+0A0h+var_80], rax
0x18003e9e1  lea     rax, [rbp+0A0h+hKey]
0x18003e9e5  mov     [rsp+1A0h+phkResult], rax; phkResult
0x18003e9ea  mov     [rbp+0A0h+var_88], r13
0x18003e9ee  mov     [rbp+0A0h+cbData], 4
0x18003e9f5  mov     [rbp+0A0h+Type], r13d
0x18003e9f9  mov     [rbp+0A0h+var_68], r13d
0x18003e9fd  mov     [rsp+1A0h+lpData], r13
0x18003ea02  mov     [rsp+1A0h+var_168], r13
0x18003ea07  mov     [rbp+0A0h+hKey], r13
0x18003ea0b  call    cs:__imp_RegOpenKeyExW
0x18003ea11  test    eax, 0FFFFFFFDh
0x18003ea16  jz      short loc_18003EA47
0x18003ea18  mov     r8d, eax
0x18003ea1b  lea     rdx, aRegopenkeyexw; "RegOpenKeyExW"
0x18003ea22  call    WfpReportSysErrorAsWinError
0x18003ea27  mov     rdi, rax
0x18003ea2a  test    rax, rax
0x18003ea2d  jz      loc_18003EB23
0x18003ea33  lea     rdx, aBferegopenkey; "BfeRegOpenKey"
0x18003ea3a  mov     rcx, rax
0x18003ea3d  call    WfpReportError
0x18003ea42  jmp     loc_18003EB23
0x18003ea47  cmp     eax, 2
0x18003ea4a  jz      loc_18003EB20
0x18003ea50  mov     eax, [rbp+0A0h+cbData]
0x18003ea53  mov     rbx, [rbp+0A0h+hKey]
0x18003ea57  test    eax, eax
0x18003ea59  jnz     short loc_18003EAA7
0x18003ea5b  lea     rax, [rbp+0A0h+cbData]
0x18003ea5f  xor     r8d, r8d; lpReserved
0x18003ea62  mov     [rsp+1A0h+lpcbData], rax; lpcbData
0x18003ea67  lea     r9, [rbp+0A0h+Type]; lpType
0x18003ea6b  lea     rdx, aEnablecga; "EnableCGA"
0x18003ea72  mov     [rsp+1A0h+phkResult], r13; lpData
0x18003ea77  mov     rcx, rbx; hKey
0x18003ea7a  call    cs:__imp_RegQueryValueExW
0x18003ea80  cmp     eax, 2
0x18003ea83  jz      loc_18003EB1B
0x18003ea89  test    eax, eax
0x18003ea8b  jz      short loc_18003EAA4
0x18003ea8d  mov     r8d, eax
0x18003ea90  lea     rdx, aRegqueryvaluee; "RegQueryValueExW"
0x18003ea97  call    WfpReportSysErrorAsWinError
0x18003ea9c  mov     rdi, rax
0x18003ea9f  jmp     loc_18003EB26
0x18003eaa4  mov     eax, [rbp+0A0h+cbData]
0x18003eaa7  mov     ecx, eax; dwBytes
0x18003eaa9  lea     r8, [rsp+1A0h+lpData]
0x18003eaae  xor     edx, edx; dwFlags
0x18003eab0  mov     [rbp+0A0h+var_68], eax
0x18003eab3  call    WfpMemAlloc
0x18003eab8  mov     rdi, rax
0x18003eabb  test    rax, rax
0x18003eabe  jnz     short loc_18003EB26
0x18003eac0  mov     r15, [rsp+1A0h+lpData]
0x18003eac5  lea     rax, [rbp+0A0h+var_68]
0x18003eac9  mov     [rsp+1A0h+lpcbData], rax; lpcbData
0x18003eace  lea     r9, [rbp+0A0h+Type]; lpType
0x18003ead2  xor     r8d, r8d; lpReserved
0x18003ead5  mov     [rsp+1A0h+phkResult], r15; lpData
0x18003eada  lea     rdx, aEnablecga; "EnableCGA"
0x18003eae1  mov     rcx, rbx; hKey
0x18003eae4  call    cs:__imp_RegQueryValueExW
0x18003eaea  cmp     eax, 2
0x18003eaed  jz      short loc_18003EB26
0x18003eaef  cmp     eax, 0EAh
0x18003eaf4  jz      short loc_18003EB26
0x18003eaf6  test    eax, eax
0x18003eaf8  jnz     short loc_18003EA8D
0x18003eafa  cmp     [rbp+0A0h+Type], 4
0x18003eafe  jnz     short loc_18003EB26
0x18003eb00  mov     eax, [rbp+0A0h+cbData]
0x18003eb03  cmp     [rbp+0A0h+var_68], eax
0x18003eb06  jnz     short loc_18003EB26
0x18003eb08  mov     rsi, r15
0x18003eb0b  mov     [rsp+1A0h+var_168], r15
0x18003eb10  mov     [rsp+1A0h+lpData], r13
0x18003eb15  lea     r14d, [rdi+1]
0x18003eb19  jmp     short loc_18003EB26
0x18003eb1b  mov     rdi, r13
0x18003eb1e  jmp     short loc_18003EB26
0x18003eb20  mov     rdi, r13
0x18003eb23  mov     rbx, r13
0x18003eb26  lea     rcx, [rsp+1A0h+lpData]
0x18003eb2b  call    WfpMemFree
0x18003eb30  mov     rcx, rbx
0x18003eb33  call    BfeRegCloseKey
0x18003eb38  test    rdi, rdi
0x18003eb3b  jz      short loc_18003EB4E
0x18003eb3d  lea     rdx, aBferegqueryval; "BfeRegQueryValue"
0x18003eb44  mov     rcx, rdi
0x18003eb47  call    WfpReportError
0x18003eb4c  jmp     short loc_18003EB56
0x18003eb4e  test    r14d, r14d
0x18003eb51  jz      short loc_18003EB56
0x18003eb53  mov     r12d, [rsi]
0x18003eb56  lea     rcx, [rsp+1A0h+var_168]
0x18003eb5b  call    WfpMemFree
0x18003eb60  test    rdi, rdi
0x18003eb63  jz      short loc_18003EB76
0x18003eb65  lea     rdx, aBferegquerydwo; "BfeRegQueryDWord"
0x18003eb6c  mov     rcx, rdi
0x18003eb6f  call    WfpReportError
0x18003eb74  jmp     short loc_18003EBA3
0x18003eb76  test    r14d, r14d
0x18003eb79  jz      short loc_18003EB8A
0x18003eb7b  mov     cs:gBfeProvCtxtComponent, 1
0x18003eb85  test    r12d, r12d
0x18003eb88  jnz     short loc_18003EB91
0x18003eb8a  mov     cs:gBfeProvCtxtComponent, r13d
0x18003eb91  lea     rcx, [rsp+1A0h+var_160]
0x18003eb96  call    BfeObjectTypeRegister
0x18003eb9b  mov     rdi, rax
0x18003eb9e  test    rax, rax
0x18003eba1  jz      short loc_18003EBB2
0x18003eba3  lea     rdx, aBfeprovidercon_0; "BfeProviderContextInit"
0x18003ebaa  mov     rcx, rdi
0x18003ebad  call    WfpReportError
0x18003ebb2  mov     rax, rdi
0x18003ebb5  mov     rcx, [rbp+0A0h+var_50]
0x18003ebb9  xor     rcx, rsp; StackCookie
0x18003ebbc  call    __security_check_cookie
0x18003ebc1  add     rsp, 168h
0x18003ebc8  pop     r15
0x18003ebca  pop     r14
0x18003ebcc  pop     r13
0x18003ebce  pop     r12
0x18003ebd0  pop     rdi
0x18003ebd1  pop     rsi
0x18003ebd2  pop     rbx
0x18003ebd3  pop     rbp
0x18003ebd4  retn
```
