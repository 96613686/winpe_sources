# BfeNetEventControllerInit

- ea: `0x180049bb8`
- end: `0x180049f39`
- name: `BfeNetEventControllerInit`
- size: `897`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180067c2c`

## callees

- `0x180004070`
- `0x180004798`
- `0x18000e7e0`
- `0x180012d8c`
- `0x1800135ac`
- `0x1800197d0`
- `0x180024e40`
- `0x180031694`
- `0x180031aa8`
- `0x180049a78`
- `0x180049bb8`
- `0x18005aa60`
- `0x180067d58`
- `0x180067df4`

## import_xrefs

- `ntdll!TpSetTimer` at `0x180049f28`
- `ntdll!TpSetTimer` at `0x180049f28`
- `ntdll!TpAllocTimer` at `0x180049edf`
- `ntdll!TpAllocTimer` at `0x180049edf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180049ca1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180049d0f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180049ca1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180049d0f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180049c2e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180049c2e`

## string_xrefs

- `0x180049c44`: `RegOpenKeyExW`
- `0x180049c14`: `System\CurrentControlSet\Services\BFE\Parameters\Policy\Options`
- `0x180049e0a`: `System\CurrentControlSet\Services\BFE\Parameters\Policy\Options`
- `0x180049c58`: `BfeRegOpenKey`

## pseudocode

```c
__int64 BfeNetEventControllerInit()
{
  int v0; // r14d
  int v1; // esi
  int *v2; // r12
  int v3; // r15d
  unsigned int v4; // eax
  __int64 v5; // rcx
  __int64 v6; // rax
  __int64 DWord; // rbx
  HKEY v8; // rdi
  LPBYTE v9; // r13
  unsigned int v10; // eax
  __int64 v11; // rcx
  int v12; // ecx
  int v13; // r9d
  int v15; // eax
  __int64 v16; // rcx
  int v17; // [rsp+30h] [rbp-39h] BYREF
  int v18; // [rsp+34h] [rbp-35h] BYREF
  LPBYTE lpData; // [rsp+38h] [rbp-31h] BYREF
  LPBYTE v20; // [rsp+40h] [rbp-29h] BYREF
  DWORD cbData; // [rsp+48h] [rbp-21h]
  DWORD lpcbData; // [rsp+50h] [rbp-19h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-11h] BYREF
  DWORD Type; // [rsp+60h] [rbp-9h] BYREF
  __int64 v25; // [rsp+68h] [rbp-1h] BYREF

  v0 = 0;
  cbData = 4;
  v1 = 0;
  v18 = 0;
  v25 = 0;
  v2 = 0;
  Type = 0;
  v3 = 1;
  lpcbData = 0;
  lpData = 0;
  v20 = 0;
  v17 = 0;
  hKey = 0;
  v4 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\BFE\\Parameters\\Policy\\Options",
         0,
         1u,
         &hKey);
  if ( (v4 & 0xFFFFFFFD) != 0 )
  {
    v6 = WfpReportSysErrorAsWinError(v5, "RegOpenKeyExW", v4);
    DWord = v6;
    if ( v6 )
      WfpReportError(v6, "BfeRegOpenKey");
    v8 = 0;
  }
  else if ( v4 == 2 )
  {
    v8 = 0;
    DWord = 0;
  }
  else
  {
    v8 = hKey;
    lpcbData = cbData;
    DWord = WfpMemAlloc(cbData, 0);
    if ( !DWord )
    {
      v9 = lpData;
      v10 = RegQueryValueExW(v8, L"CollectNetEvents", 0, &Type, lpData, &lpcbData);
      if ( v10 != 2 && v10 != 234 )
      {
        if ( v10 )
        {
          DWord = WfpReportSysErrorAsWinError(v11, "RegQueryValueExW", v10);
        }
        else if ( Type == 4 && lpcbData == cbData )
        {
          lpData = 0;
          v2 = (int *)v9;
          v1 = 1;
          v20 = v9;
          v17 = 1;
        }
      }
    }
  }
  WfpMemFree(&lpData);
  BfeRegCloseKey(v8);
  if ( DWord )
  {
    WfpReportError(DWord, "BfeRegQueryValue");
  }
  else if ( v1 )
  {
    v0 = *v2;
    v18 = *v2;
  }
  WfpMemFree(&v20);
  if ( DWord )
  {
    WfpReportError(DWord, "BfeRegQueryDWord");
  }
  else
  {
    if ( v1 && !v0 )
      v3 = 0;
    gBfeEventController = v3;
    DWord = BfeRegQueryDWord(
              v12,
              (unsigned int)L"System\\CurrentControlSet\\Services\\BFE\\Parameters\\Policy\\Options",
              (unsigned int)L"NetEventMatchAnyKeywords",
              v13,
              (__int64)&v18,
              (__int64)&v17);
    if ( !DWord )
    {
      if ( v17 )
        dword_1800F5F64 = v18;
      DWord = BfeObjectSecurityLoad(ParentDescriptor, 0, (__int64)&CreatorDescriptor);
      if ( !DWord )
      {
        DWord = WfpCriticalSectionCreate(&stru_1800F5F80);
        if ( !DWord )
        {
          DWord = BfeChangeSourceCreate(
                    (unsigned int)BfeNetEventSubDestroy,
                    (unsigned int)BfeNetEventSubQueryPublic,
                    (unsigned int)BfeDestroy_FWPM_NET_EVENT_SUBSCRIPTION,
                    (unsigned int)BfeNetEventNotify,
                    (__int64)&qword_1800F5FB0);
          if ( !DWord )
          {
            if ( !gBfeEventController )
              return DWord;
            v15 = TpAllocTimer(&qword_1800F5FC0, BfeEventControllerDelayStart, 0, 0);
            if ( v15 >= 0 )
            {
              v25 = -600000000;
              TpSetTimer(qword_1800F5FC0, &v25, 0, 0);
              return DWord;
            }
            DWord = WfpReportSysErrorAsNtStatus(v16, "TpAllocTimer", (unsigned int)v15);
            if ( !DWord )
              return DWord;
          }
        }
      }
    }
  }
  BfeNetEventControllerShutdown();
  BfeIkeEventControllerShutdown();
  WfpReportError(DWord, "BfeNetEventControllerInit");
  return DWord;
}

```

## disassembly

```asm
0x180049bb8  push    rbp
0x180049bba  push    rbx
0x180049bbb  push    rsi
0x180049bbc  push    rdi
0x180049bbd  push    r12
0x180049bbf  push    r13
0x180049bc1  push    r14
0x180049bc3  push    r15
0x180049bc5  lea     rbp, [rsp-1Fh]
0x180049bca  sub     rsp, 88h
0x180049bd1  mov     rax, cs:__security_cookie
0x180049bd8  xor     rax, rsp
0x180049bdb  mov     [rbp+57h+var_50], rax
0x180049bdf  xor     r14d, r14d
0x180049be2  mov     [rbp+57h+cbData], 4
0x180049be9  xor     esi, esi
0x180049beb  mov     [rbp+57h+var_8C], r14d
0x180049bef  lea     rax, [rbp+57h+hKey]
0x180049bf3  mov     [rbp+57h+var_58], r14
0x180049bf7  xor     r12d, r12d
0x180049bfa  mov     [rbp+57h+Type], r14d
0x180049bfe  lea     r15d, [r14+1]
0x180049c02  mov     [rbp+57h+var_70], r14d
0x180049c06  mov     r9d, r15d; samDesired
0x180049c09  mov     [rbp+57h+lpData], r14
0x180049c0d  xor     r8d, r8d; ulOptions
0x180049c10  mov     [rbp+57h+var_80], r12
0x180049c14  lea     rdx, aSystemCurrentc_4; "System\\CurrentControlSet\\Services\\BF"...
0x180049c1b  mov     [rbp+57h+var_90], esi
0x180049c1e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180049c25  mov     [rbp+57h+hKey], rsi
0x180049c29  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180049c2e  call    cs:__imp_RegOpenKeyExW
0x180049c35  nop     dword ptr [rax+rax+00h]
0x180049c3a  test    eax, 0FFFFFFFDh
0x180049c3f  jz      short loc_180049C6E
0x180049c41  mov     r8d, eax
0x180049c44  lea     rdx, aRegopenkeyexw; "RegOpenKeyExW"
0x180049c4b  call    WfpReportSysErrorAsWinError
0x180049c50  mov     rbx, rax
0x180049c53  test    rax, rax
0x180049c56  jz      short loc_180049C67
0x180049c58  lea     rdx, aBferegopenkey; "BfeRegOpenKey"
0x180049c5f  mov     rcx, rax
0x180049c62  call    WfpReportError
0x180049c67  xor     edi, edi
0x180049c69  jmp     loc_180049D51
0x180049c6e  cmp     eax, 2
0x180049c71  jz      loc_180049D4D
0x180049c77  mov     eax, [rbp+57h+cbData]
0x180049c7a  mov     rdi, [rbp+57h+hKey]
0x180049c7e  test    eax, eax
0x180049c80  jnz     short loc_180049CD4
0x180049c82  lea     rax, [rbp+57h+cbData]
0x180049c86  xor     r8d, r8d; lpReserved
0x180049c89  mov     [rsp+0C0h+lpcbData], rax; lpcbData
0x180049c8e  lea     r9, [rbp+57h+Type]; lpType
0x180049c92  lea     rdx, aCollectneteven; "CollectNetEvents"
0x180049c99  mov     [rsp+0C0h+phkResult], rsi; lpData
0x180049c9e  mov     rcx, rdi; hKey
0x180049ca1  call    cs:__imp_RegQueryValueExW
0x180049ca8  nop     dword ptr [rax+rax+00h]
0x180049cad  cmp     eax, 2
0x180049cb0  jz      loc_180049D4F
0x180049cb6  test    eax, eax
0x180049cb8  jz      short loc_180049CD1
0x180049cba  mov     r8d, eax
0x180049cbd  lea     rdx, aRegqueryvaluee; "RegQueryValueExW"
0x180049cc4  call    WfpReportSysErrorAsWinError
0x180049cc9  mov     rbx, rax
0x180049ccc  jmp     loc_180049D51
0x180049cd1  mov     eax, [rbp+57h+cbData]
0x180049cd4  mov     ecx, eax; dwBytes
0x180049cd6  lea     r8, [rbp+57h+lpData]
0x180049cda  xor     edx, edx; dwFlags
0x180049cdc  mov     [rbp+57h+var_70], eax
0x180049cdf  call    WfpMemAlloc
0x180049ce4  mov     rbx, rax
0x180049ce7  test    rax, rax
0x180049cea  jnz     short loc_180049D51
0x180049cec  mov     r13, [rbp+57h+lpData]
0x180049cf0  lea     rax, [rbp+57h+var_70]
0x180049cf4  mov     [rsp+0C0h+lpcbData], rax; lpcbData
0x180049cf9  lea     r9, [rbp+57h+Type]; lpType
0x180049cfd  xor     r8d, r8d; lpReserved
0x180049d00  mov     [rsp+0C0h+phkResult], r13; lpData
0x180049d05  lea     rdx, aCollectneteven; "CollectNetEvents"
0x180049d0c  mov     rcx, rdi; hKey
0x180049d0f  call    cs:__imp_RegQueryValueExW
0x180049d16  nop     dword ptr [rax+rax+00h]
0x180049d1b  cmp     eax, 2
0x180049d1e  jz      short loc_180049D51
0x180049d20  cmp     eax, 0EAh
0x180049d25  jz      short loc_180049D51
0x180049d27  test    eax, eax
0x180049d29  jnz     short loc_180049CBA
0x180049d2b  cmp     [rbp+57h+Type], 4
0x180049d2f  jnz     short loc_180049D51
0x180049d31  mov     eax, [rbp+57h+cbData]
0x180049d34  cmp     [rbp+57h+var_70], eax
0x180049d37  jnz     short loc_180049D51
0x180049d39  mov     [rbp+57h+lpData], rsi
0x180049d3d  mov     r12, r13
0x180049d40  mov     esi, r15d
0x180049d43  mov     [rbp+57h+var_80], r13
0x180049d47  mov     [rbp+57h+var_90], r15d
0x180049d4b  jmp     short loc_180049D51
0x180049d4d  xor     edi, edi
0x180049d4f  xor     ebx, ebx
0x180049d51  lea     rcx, [rbp+57h+lpData]
0x180049d55  call    WfpMemFree
0x180049d5a  mov     rcx, rdi
0x180049d5d  call    BfeRegCloseKey
0x180049d62  test    rbx, rbx
0x180049d65  jz      short loc_180049D78
0x180049d67  lea     rdx, aBferegqueryval; "BfeRegQueryValue"
0x180049d6e  mov     rcx, rbx
0x180049d71  call    WfpReportError
0x180049d76  jmp     short loc_180049D84
0x180049d78  test    esi, esi
0x180049d7a  jz      short loc_180049D84
0x180049d7c  mov     r14d, [r12]
0x180049d80  mov     [rbp+57h+var_8C], r14d
0x180049d84  lea     rcx, [rbp+57h+var_80]
0x180049d88  call    WfpMemFree
0x180049d8d  test    rbx, rbx
0x180049d90  jz      short loc_180049DE3
0x180049d92  lea     rdx, aBferegquerydwo; "BfeRegQueryDWord"
0x180049d99  mov     rcx, rbx
0x180049d9c  call    WfpReportError
0x180049da1  call    BfeNetEventControllerShutdown
0x180049da6  call    BfeIkeEventControllerShutdown
0x180049dab  test    rbx, rbx
0x180049dae  jz      short loc_180049DBF
0x180049db0  lea     rdx, aBfeneteventcon; "BfeNetEventControllerInit"
0x180049db7  mov     rcx, rbx
0x180049dba  call    WfpReportError
0x180049dbf  mov     rax, rbx
0x180049dc2  mov     rcx, [rbp+57h+var_50]
0x180049dc6  xor     rcx, rsp; StackCookie
0x180049dc9  call    __security_check_cookie
0x180049dce  add     rsp, 88h
0x180049dd5  pop     r15
0x180049dd7  pop     r14
0x180049dd9  pop     r13
0x180049ddb  pop     r12
0x180049ddd  pop     rdi
0x180049dde  pop     rsi
0x180049ddf  pop     rbx
0x180049de0  pop     rbp
0x180049de1  retn
0x180049de3  test    esi, esi
0x180049de5  jz      short loc_180049DEF
0x180049de7  test    r14d, r14d
0x180049dea  jnz     short loc_180049DEF
0x180049dec  xor     r15d, r15d
0x180049def  lea     rax, [rbp+57h+var_90]
0x180049df3  mov     cs:gBfeEventController, r15d
0x180049dfa  mov     [rsp+0C0h+lpcbData], rax
0x180049dff  lea     r8, aNeteventmatcha; "NetEventMatchAnyKeywords"
0x180049e06  lea     rax, [rbp+57h+var_8C]
0x180049e0a  lea     rdx, aSystemCurrentc_4; "System\\CurrentControlSet\\Services\\BF"...
0x180049e11  mov     [rsp+0C0h+phkResult], rax
0x180049e16  call    BfeRegQueryDWord
0x180049e1b  mov     rbx, rax
0x180049e1e  test    rax, rax
0x180049e21  jnz     loc_180049DA1
0x180049e27  cmp     [rbp+57h+var_90], eax
0x180049e2a  jz      short loc_180049E35
0x180049e2c  mov     eax, [rbp+57h+var_8C]
0x180049e2f  mov     cs:dword_1800F5F64, eax
0x180049e35  mov     rcx, cs:ParentDescriptor; ParentDescriptor
0x180049e3c  lea     rax, CreatorDescriptor
0x180049e43  mov     [rsp+0C0h+lpcbData], rax; __int64
0x180049e48  lea     rdx, FWPM_OBJECT_TYPE_NET_EVENTS
0x180049e4f  xor     r9d, r9d
0x180049e52  mov     dword ptr [rsp+0C0h+phkResult], 0; IsContainerObject
0x180049e5a  xor     r8d, r8d
0x180049e5d  call    BfeObjectSecurityLoad
0x180049e62  mov     rbx, rax
0x180049e65  test    rax, rax
0x180049e68  jnz     loc_180049DA1
0x180049e6e  lea     rcx, stru_1800F5F80
0x180049e75  call    WfpCriticalSectionCreate
0x180049e7a  mov     rbx, rax
0x180049e7d  test    rax, rax
0x180049e80  jnz     loc_180049DA1
0x180049e86  lea     rax, qword_1800F5FB0
0x180049e8d  lea     r9, BfeNetEventNotify
0x180049e94  mov     [rsp+0C0h+phkResult], rax
0x180049e99  lea     r8, BfeDestroy_FWPM_NET_EVENT_SUBSCRIPTION
0x180049ea0  lea     rdx, BfeNetEventSubQueryPublic
0x180049ea7  lea     rcx, BfeNetEventSubDestroy
0x180049eae  call    BfeChangeSourceCreate
0x180049eb3  mov     rbx, rax
0x180049eb6  test    rax, rax
0x180049eb9  jnz     loc_180049DA1
0x180049ebf  cmp     cs:gBfeEventController, eax
0x180049ec5  jz      loc_180049DBF
0x180049ecb  xor     r9d, r9d
0x180049ece  lea     rdx, BfeEventControllerDelayStart
0x180049ed5  xor     r8d, r8d
0x180049ed8  lea     rcx, qword_1800F5FC0
0x180049edf  call    cs:__imp_TpAllocTimer
0x180049ee6  nop     dword ptr [rax+rax+00h]
0x180049eeb  test    eax, eax
0x180049eed  jns     short loc_180049F0F
0x180049eef  mov     r8d, eax
0x180049ef2  lea     rdx, aTpalloctimer; "TpAllocTimer"
0x180049ef9  call    WfpReportSysErrorAsNtStatus
0x180049efe  mov     rbx, rax
0x180049f01  test    rax, rax
0x180049f04  jnz     loc_180049DA1
0x180049f0a  jmp     loc_180049DBF
0x180049f0f  mov     rcx, cs:qword_1800F5FC0
0x180049f16  lea     rdx, [rbp+57h+var_58]
0x180049f1a  xor     r9d, r9d
0x180049f1d  mov     [rbp+57h+var_58], 0FFFFFFFFDC3CBA00h
0x180049f25  xor     r8d, r8d
0x180049f28  call    cs:__imp_TpSetTimer
0x180049f2f  nop     dword ptr [rax+rax+00h]
0x180049f34  jmp     loc_180049DBF
```
