# BfeProviderContextInit

- ea: `0x18003faf8`
- end: `0x18003fe58`
- name: `BfeProviderContextInit`
- size: `864`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003f7c0`

## callees

- `0x180004070`
- `0x18000e7e0`
- `0x180012d8c`
- `0x1800197d0`
- `0x180024e40`
- `0x18003faf8`
- `0x18003fe60`
- `0x18005aa60`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003fcf0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003fd60`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003fcf0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003fd60`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003fc7b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003fc7b`

## string_xrefs

- `0x18003fb40`: `System\CurrentControlSet\Services\BFE\Parameters\Policy\Options`
- `0x18003fc91`: `RegOpenKeyExW`
- `0x18003fca9`: `BfeRegOpenKey`

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
  __int64 (__fastcall *v35)(); // [rsp+120h] [rbp+20h]
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
0x18003faf8  push    rbp
0x18003fafa  push    rbx
0x18003fafb  push    rsi
0x18003fafc  push    rdi
0x18003fafd  push    r12
0x18003faff  push    r13
0x18003fb01  push    r14
0x18003fb03  push    r15
0x18003fb05  lea     rbp, [rsp-68h]
0x18003fb0a  sub     rsp, 168h
0x18003fb11  mov     rax, cs:__security_cookie
0x18003fb18  xor     rax, rsp
0x18003fb1b  mov     [rbp+0A0h+var_50], rax
0x18003fb1f  xor     r13d, r13d
0x18003fb22  mov     [rsp+1A0h+var_160], 1
0x18003fb2b  lea     rax, FWPM_OBJECT_TYPE_PROVIDER_CONTEXTS
0x18003fb32  mov     [rsp+1A0h+var_128], 10h
0x18003fb3b  mov     [rsp+1A0h+var_158], rax
0x18003fb40  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\BF"...
0x18003fb47  lea     rax, aProvidercontex; "ProviderContext"
0x18003fb4e  mov     [rbp+0A0h+var_120], 80320006h
0x18003fb55  mov     [rsp+1A0h+var_150], rax
0x18003fb5a  lea     r9d, [r13+1]; samDesired
0x18003fb5e  lea     rax, BfeFwpmProviderContextCopy
0x18003fb65  mov     [rbp+0A0h+var_F8], r13
0x18003fb69  mov     [rsp+1A0h+var_148], rax
0x18003fb6e  xor     r8d, r8d; ulOptions
0x18003fb71  lea     rax, BfeDestroy_FWPM_PROVIDER_CONTEXT
0x18003fb78  mov     [rbp+0A0h+var_E0], r13
0x18003fb7c  mov     [rsp+1A0h+var_140], rax
0x18003fb81  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003fb88  lea     rax, FWPM_PROVIDER_CONTEXT_MARSHAL_Encode
0x18003fb8f  mov     [rbp+0A0h+var_D8], r13
0x18003fb93  mov     [rsp+1A0h+var_138], rax
0x18003fb98  mov     r12d, r13d
0x18003fb9b  lea     rax, FWPM_PROVIDER_CONTEXT_MARSHAL_Decode
0x18003fba2  mov     [rbp+0A0h+var_C8], r13
0x18003fba6  mov     [rsp+1A0h+var_130], rax
0x18003fbab  mov     esi, r13d
0x18003fbae  xor     eax, eax
0x18003fbb0  mov     [rbp+0A0h+var_B0], r13
0x18003fbb4  mov     [rbp+0A0h+var_11C], eax
0x18003fbb7  mov     r14d, r13d
0x18003fbba  lea     rax, aOLsgLsdAOiciGa_0; "O:LSG:LSD:(A;OICI;GA;;;BA)(A;OICI;GRGWG"...
0x18003fbc1  mov     [rbp+0A0h+var_A0], 15491543h
0x18003fbc9  mov     [rbp+0A0h+var_118], rax
0x18003fbcd  lea     rax, BfeProviderContextCreate
0x18003fbd4  mov     [rbp+0A0h+var_110], rax
0x18003fbd8  lea     rax, BfeProviderContextDestroy
0x18003fbdf  mov     [rbp+0A0h+var_108], rax
0x18003fbe3  lea     rax, BfeProviderContextGetId
0x18003fbea  mov     [rbp+0A0h+var_100], rax
0x18003fbee  lea     rax, BfeProviderContextGetPublicState
0x18003fbf5  mov     [rbp+0A0h+var_F0], rax
0x18003fbf9  lea     rax, BfeFwpmProviderContextLocalize
0x18003fc00  mov     [rbp+0A0h+var_E8], rax
0x18003fc04  lea     rax, BfeProviderContextIsMatch
0x18003fc0b  mov     [rbp+0A0h+var_D0], rax
0x18003fc0f  lea     rax, BfeDestroy_FWPM_CALLOUT_SUBSCRIPTION0
0x18003fc16  mov     [rbp+0A0h+var_C0], rax
0x18003fc1a  lea     rax, BfeFwpmProviderContextSubscriptionCopy
0x18003fc21  mov     [rbp+0A0h+var_B8], rax
0x18003fc25  lea     rax, BfeProviderContextChangeNotify
0x18003fc2c  mov     [rbp+0A0h+var_A8], rax
0x18003fc30  lea     rax, BfeProviderContextAudit
0x18003fc37  mov     [rbp+0A0h+var_98], rax
0x18003fc3b  lea     rax, FwppXmlWrite_FWPM_PROVIDER_CONTEXT
0x18003fc42  mov     [rbp+0A0h+var_90], rax
0x18003fc46  lea     rax, BfeFwpmProviderContextValidate
0x18003fc4d  mov     [rbp+0A0h+var_80], rax
0x18003fc51  lea     rax, [rbp+0A0h+hKey]
0x18003fc55  mov     [rsp+1A0h+phkResult], rax; phkResult
0x18003fc5a  mov     [rbp+0A0h+var_88], r13
0x18003fc5e  mov     [rbp+0A0h+cbData], 4
0x18003fc65  mov     [rbp+0A0h+Type], r13d
0x18003fc69  mov     [rbp+0A0h+var_68], r13d
0x18003fc6d  mov     [rsp+1A0h+lpData], r13
0x18003fc72  mov     [rsp+1A0h+var_168], r13
0x18003fc77  mov     [rbp+0A0h+hKey], r13
0x18003fc7b  call    cs:__imp_RegOpenKeyExW
0x18003fc82  nop     dword ptr [rax+rax+00h]
0x18003fc87  test    eax, 0FFFFFFFDh
0x18003fc8c  jz      short loc_18003FCBD
0x18003fc8e  mov     r8d, eax
0x18003fc91  lea     rdx, aRegopenkeyexw; "RegOpenKeyExW"
0x18003fc98  call    WfpReportSysErrorAsWinError
0x18003fc9d  mov     rdi, rax
0x18003fca0  test    rax, rax
0x18003fca3  jz      loc_18003FDA5
0x18003fca9  lea     rdx, aBferegopenkey; "BfeRegOpenKey"
0x18003fcb0  mov     rcx, rax
0x18003fcb3  call    WfpReportError
0x18003fcb8  jmp     loc_18003FDA5
0x18003fcbd  cmp     eax, 2
0x18003fcc0  jz      loc_18003FDA2
0x18003fcc6  mov     eax, [rbp+0A0h+cbData]
0x18003fcc9  mov     rbx, [rbp+0A0h+hKey]
0x18003fccd  test    eax, eax
0x18003fccf  jnz     short loc_18003FD23
0x18003fcd1  lea     rax, [rbp+0A0h+cbData]
0x18003fcd5  xor     r8d, r8d; lpReserved
0x18003fcd8  mov     [rsp+1A0h+lpcbData], rax; lpcbData
0x18003fcdd  lea     r9, [rbp+0A0h+Type]; lpType
0x18003fce1  lea     rdx, ValueName; "EnableCGA"
0x18003fce8  mov     [rsp+1A0h+phkResult], r13; lpData
0x18003fced  mov     rcx, rbx; hKey
0x18003fcf0  call    cs:__imp_RegQueryValueExW
0x18003fcf7  nop     dword ptr [rax+rax+00h]
0x18003fcfc  cmp     eax, 2
0x18003fcff  jz      loc_18003FD9D
0x18003fd05  test    eax, eax
0x18003fd07  jz      short loc_18003FD20
0x18003fd09  mov     r8d, eax
0x18003fd0c  lea     rdx, aRegqueryvaluee; "RegQueryValueExW"
0x18003fd13  call    WfpReportSysErrorAsWinError
0x18003fd18  mov     rdi, rax
0x18003fd1b  jmp     loc_18003FDA8
0x18003fd20  mov     eax, [rbp+0A0h+cbData]
0x18003fd23  mov     ecx, eax; dwBytes
0x18003fd25  lea     r8, [rsp+1A0h+lpData]
0x18003fd2a  xor     edx, edx; dwFlags
0x18003fd2c  mov     [rbp+0A0h+var_68], eax
0x18003fd2f  call    WfpMemAlloc
0x18003fd34  mov     rdi, rax
0x18003fd37  test    rax, rax
0x18003fd3a  jnz     short loc_18003FDA8
0x18003fd3c  mov     r15, [rsp+1A0h+lpData]
0x18003fd41  lea     rax, [rbp+0A0h+var_68]
0x18003fd45  mov     [rsp+1A0h+lpcbData], rax; lpcbData
0x18003fd4a  lea     r9, [rbp+0A0h+Type]; lpType
0x18003fd4e  xor     r8d, r8d; lpReserved
0x18003fd51  mov     [rsp+1A0h+phkResult], r15; lpData
0x18003fd56  lea     rdx, ValueName; "EnableCGA"
0x18003fd5d  mov     rcx, rbx; hKey
0x18003fd60  call    cs:__imp_RegQueryValueExW
0x18003fd67  nop     dword ptr [rax+rax+00h]
0x18003fd6c  cmp     eax, 2
0x18003fd6f  jz      short loc_18003FDA8
0x18003fd71  cmp     eax, 0EAh
0x18003fd76  jz      short loc_18003FDA8
0x18003fd78  test    eax, eax
0x18003fd7a  jnz     short loc_18003FD09
0x18003fd7c  cmp     [rbp+0A0h+Type], 4
0x18003fd80  jnz     short loc_18003FDA8
0x18003fd82  mov     eax, [rbp+0A0h+cbData]
0x18003fd85  cmp     [rbp+0A0h+var_68], eax
0x18003fd88  jnz     short loc_18003FDA8
0x18003fd8a  mov     rsi, r15
0x18003fd8d  mov     [rsp+1A0h+var_168], r15
0x18003fd92  mov     [rsp+1A0h+lpData], r13
0x18003fd97  lea     r14d, [rdi+1]
0x18003fd9b  jmp     short loc_18003FDA8
0x18003fd9d  mov     rdi, r13
0x18003fda0  jmp     short loc_18003FDA8
0x18003fda2  mov     rdi, r13
0x18003fda5  mov     rbx, r13
0x18003fda8  lea     rcx, [rsp+1A0h+lpData]
0x18003fdad  call    WfpMemFree
0x18003fdb2  mov     rcx, rbx
0x18003fdb5  call    BfeRegCloseKey
0x18003fdba  test    rdi, rdi
0x18003fdbd  jz      short loc_18003FDD0
0x18003fdbf  lea     rdx, aBferegqueryval; "BfeRegQueryValue"
0x18003fdc6  mov     rcx, rdi
0x18003fdc9  call    WfpReportError
0x18003fdce  jmp     short loc_18003FDD8
0x18003fdd0  test    r14d, r14d
0x18003fdd3  jz      short loc_18003FDD8
0x18003fdd5  mov     r12d, [rsi]
0x18003fdd8  lea     rcx, [rsp+1A0h+var_168]
0x18003fddd  call    WfpMemFree
0x18003fde2  test    rdi, rdi
0x18003fde5  jz      short loc_18003FDF8
0x18003fde7  lea     rdx, aBferegquerydwo; "BfeRegQueryDWord"
0x18003fdee  mov     rcx, rdi
0x18003fdf1  call    WfpReportError
0x18003fdf6  jmp     short loc_18003FE25
0x18003fdf8  test    r14d, r14d
0x18003fdfb  jz      short loc_18003FE0C
0x18003fdfd  mov     cs:gBfeProvCtxtComponent, 1
0x18003fe07  test    r12d, r12d
0x18003fe0a  jnz     short loc_18003FE13
0x18003fe0c  mov     cs:gBfeProvCtxtComponent, r13d
0x18003fe13  lea     rcx, [rsp+1A0h+var_160]
0x18003fe18  call    BfeObjectTypeRegister
0x18003fe1d  mov     rdi, rax
0x18003fe20  test    rax, rax
0x18003fe23  jz      short loc_18003FE34
0x18003fe25  lea     rdx, aBfeprovidercon_0; "BfeProviderContextInit"
0x18003fe2c  mov     rcx, rdi
0x18003fe2f  call    WfpReportError
0x18003fe34  mov     rax, rdi
0x18003fe37  mov     rcx, [rbp+0A0h+var_50]
0x18003fe3b  xor     rcx, rsp; StackCookie
0x18003fe3e  call    __security_check_cookie
0x18003fe43  add     rsp, 168h
0x18003fe4a  pop     r15
0x18003fe4c  pop     r14
0x18003fe4e  pop     r13
0x18003fe50  pop     r12
0x18003fe52  pop     rdi
0x18003fe53  pop     rsi
0x18003fe54  pop     rbx
0x18003fe55  pop     rbp
0x18003fe56  retn
```
