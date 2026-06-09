# BfeNetEventControllerInit

- ea: `0x180047c98`
- end: `0x180047ff7`
- name: `BfeNetEventControllerInit`
- size: `863`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180065768`

## callees

- `0x1800039e4`
- `0x18000474c`
- `0x18000e000`
- `0x18001236c`
- `0x180012b54`
- `0x180018b74`
- `0x180022730`
- `0x18002fd7c`
- `0x180030180`
- `0x180047af4`
- `0x180047c98`
- `0x180058b30`
- `0x180065890`
- `0x18006591c`

## import_xrefs

- `ntdll!TpSetTimer` at `0x180047fec`
- `ntdll!TpSetTimer` at `0x180047fec`
- `ntdll!TpAllocTimer` at `0x180047fa9`
- `ntdll!TpAllocTimer` at `0x180047fa9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180047d7b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180047de0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180047d7b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180047de0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180047d0e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180047d0e`

## string_xrefs

- `0x180047d1e`: `RegOpenKeyExW`
- `0x180047cf4`: `System\CurrentControlSet\Services\BFE\Parameters\Policy\Options`
- `0x180047ed4`: `System\CurrentControlSet\Services\BFE\Parameters\Policy\Options`
- `0x180047d32`: `BfeRegOpenKey`

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
        dword_1800F2F44 = v18;
      DWord = BfeObjectSecurityLoad(
                ParentDescriptor,
                (__int64)&FWPM_OBJECT_TYPE_NET_EVENTS,
                0,
                0,
                0,
                &CreatorDescriptor);
      if ( !DWord )
      {
        DWord = WfpCriticalSectionCreate(&stru_1800F2F60);
        if ( !DWord )
        {
          DWord = BfeChangeSourceCreate(
                    (__int64)BfeNetEventSubDestroy,
                    (__int64)BfeNetEventSubQueryPublic,
                    (__int64)BfeDestroy_FWPM_NET_EVENT_SUBSCRIPTION,
                    (__int64)BfeNetEventNotify,
                    &qword_1800F2F90);
          if ( !DWord )
          {
            if ( !gBfeEventController )
              return DWord;
            v15 = TpAllocTimer(&qword_1800F2FA0, BfeEventControllerDelayStart, 0, 0);
            if ( v15 >= 0 )
            {
              v25 = -600000000;
              TpSetTimer(qword_1800F2FA0, &v25, 0, 0);
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
0x180047c98  push    rbp
0x180047c9a  push    rbx
0x180047c9b  push    rsi
0x180047c9c  push    rdi
0x180047c9d  push    r12
0x180047c9f  push    r13
0x180047ca1  push    r14
0x180047ca3  push    r15
0x180047ca5  lea     rbp, [rsp-1Fh]
0x180047caa  sub     rsp, 88h
0x180047cb1  mov     rax, cs:__security_cookie
0x180047cb8  xor     rax, rsp
0x180047cbb  mov     [rbp+57h+var_50], rax
0x180047cbf  xor     r14d, r14d
0x180047cc2  mov     [rbp+57h+cbData], 4
0x180047cc9  xor     esi, esi
0x180047ccb  mov     [rbp+57h+var_8C], r14d
0x180047ccf  lea     rax, [rbp+57h+hKey]
0x180047cd3  mov     [rbp+57h+var_58], r14
0x180047cd7  xor     r12d, r12d
0x180047cda  mov     [rbp+57h+Type], r14d
0x180047cde  lea     r15d, [r14+1]
0x180047ce2  mov     [rbp+57h+var_70], r14d
0x180047ce6  mov     r9d, r15d; samDesired
0x180047ce9  mov     [rbp+57h+lpData], r14
0x180047ced  xor     r8d, r8d; ulOptions
0x180047cf0  mov     [rbp+57h+var_80], r12
0x180047cf4  lea     rdx, aSystemCurrentc_4; "System\\CurrentControlSet\\Services\\BF"...
0x180047cfb  mov     [rbp+57h+var_90], esi
0x180047cfe  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180047d05  mov     [rbp+57h+hKey], rsi
0x180047d09  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180047d0e  call    cs:__imp_RegOpenKeyExW
0x180047d14  test    eax, 0FFFFFFFDh
0x180047d19  jz      short loc_180047D48
0x180047d1b  mov     r8d, eax
0x180047d1e  lea     rdx, aRegopenkeyexw; "RegOpenKeyExW"
0x180047d25  call    WfpReportSysErrorAsWinError
0x180047d2a  mov     rbx, rax
0x180047d2d  test    rax, rax
0x180047d30  jz      short loc_180047D41
0x180047d32  lea     rdx, aBferegopenkey; "BfeRegOpenKey"
0x180047d39  mov     rcx, rax
0x180047d3c  call    WfpReportError
0x180047d41  xor     edi, edi
0x180047d43  jmp     loc_180047E1C
0x180047d48  cmp     eax, 2
0x180047d4b  jz      loc_180047E18
0x180047d51  mov     eax, [rbp+57h+cbData]
0x180047d54  mov     rdi, [rbp+57h+hKey]
0x180047d58  test    eax, eax
0x180047d5a  jnz     short loc_180047DA5
0x180047d5c  lea     rax, [rbp+57h+cbData]
0x180047d60  xor     r8d, r8d; lpReserved
0x180047d63  mov     [rsp+0C0h+lpcbData], rax; lpcbData
0x180047d68  lea     r9, [rbp+57h+Type]; lpType
0x180047d6c  lea     rdx, aCollectneteven; "CollectNetEvents"
0x180047d73  mov     [rsp+0C0h+phkResult], rsi; lpData
0x180047d78  mov     rcx, rdi; hKey
0x180047d7b  call    cs:__imp_RegQueryValueExW
0x180047d81  cmp     eax, 2
0x180047d84  jz      loc_180047E1A
0x180047d8a  test    eax, eax
0x180047d8c  jz      short loc_180047DA2
0x180047d8e  mov     r8d, eax
0x180047d91  lea     rdx, aRegqueryvaluee; "RegQueryValueExW"
0x180047d98  call    WfpReportSysErrorAsWinError
0x180047d9d  mov     rbx, rax
0x180047da0  jmp     short loc_180047E1C
0x180047da2  mov     eax, [rbp+57h+cbData]
0x180047da5  mov     ecx, eax; dwBytes
0x180047da7  lea     r8, [rbp+57h+lpData]
0x180047dab  xor     edx, edx; dwFlags
0x180047dad  mov     [rbp+57h+var_70], eax
0x180047db0  call    WfpMemAlloc
0x180047db5  mov     rbx, rax
0x180047db8  test    rax, rax
0x180047dbb  jnz     short loc_180047E1C
0x180047dbd  mov     r13, [rbp+57h+lpData]
0x180047dc1  lea     rax, [rbp+57h+var_70]
0x180047dc5  mov     [rsp+0C0h+lpcbData], rax; lpcbData
0x180047dca  lea     r9, [rbp+57h+Type]; lpType
0x180047dce  xor     r8d, r8d; lpReserved
0x180047dd1  mov     [rsp+0C0h+phkResult], r13; lpData
0x180047dd6  lea     rdx, aCollectneteven; "CollectNetEvents"
0x180047ddd  mov     rcx, rdi; hKey
0x180047de0  call    cs:__imp_RegQueryValueExW
0x180047de6  cmp     eax, 2
0x180047de9  jz      short loc_180047E1C
0x180047deb  cmp     eax, 0EAh
0x180047df0  jz      short loc_180047E1C
0x180047df2  test    eax, eax
0x180047df4  jnz     short loc_180047D8E
0x180047df6  cmp     [rbp+57h+Type], 4
0x180047dfa  jnz     short loc_180047E1C
0x180047dfc  mov     eax, [rbp+57h+cbData]
0x180047dff  cmp     [rbp+57h+var_70], eax
0x180047e02  jnz     short loc_180047E1C
0x180047e04  mov     [rbp+57h+lpData], rsi
0x180047e08  mov     r12, r13
0x180047e0b  mov     esi, r15d
0x180047e0e  mov     [rbp+57h+var_80], r13
0x180047e12  mov     [rbp+57h+var_90], r15d
0x180047e16  jmp     short loc_180047E1C
0x180047e18  xor     edi, edi
0x180047e1a  xor     ebx, ebx
0x180047e1c  lea     rcx, [rbp+57h+lpData]
0x180047e20  call    WfpMemFree
0x180047e25  mov     rcx, rdi
0x180047e28  call    BfeRegCloseKey
0x180047e2d  test    rbx, rbx
0x180047e30  jz      short loc_180047E43
0x180047e32  lea     rdx, aBferegqueryval; "BfeRegQueryValue"
0x180047e39  mov     rcx, rbx
0x180047e3c  call    WfpReportError
0x180047e41  jmp     short loc_180047E4F
0x180047e43  test    esi, esi
0x180047e45  jz      short loc_180047E4F
0x180047e47  mov     r14d, [r12]
0x180047e4b  mov     [rbp+57h+var_8C], r14d
0x180047e4f  lea     rcx, [rbp+57h+var_80]
0x180047e53  call    WfpMemFree
0x180047e58  test    rbx, rbx
0x180047e5b  jz      short loc_180047EAD
0x180047e5d  lea     rdx, aBferegquerydwo; "BfeRegQueryDWord"
0x180047e64  mov     rcx, rbx
0x180047e67  call    WfpReportError
0x180047e6c  call    BfeNetEventControllerShutdown
0x180047e71  call    BfeIkeEventControllerShutdown
0x180047e76  test    rbx, rbx
0x180047e79  jz      short loc_180047E8A
0x180047e7b  lea     rdx, aBfeneteventcon; "BfeNetEventControllerInit"
0x180047e82  mov     rcx, rbx
0x180047e85  call    WfpReportError
0x180047e8a  mov     rax, rbx
0x180047e8d  mov     rcx, [rbp+57h+var_50]
0x180047e91  xor     rcx, rsp; StackCookie
0x180047e94  call    __security_check_cookie
0x180047e99  add     rsp, 88h
0x180047ea0  pop     r15
0x180047ea2  pop     r14
0x180047ea4  pop     r13
0x180047ea6  pop     r12
0x180047ea8  pop     rdi
0x180047ea9  pop     rsi
0x180047eaa  pop     rbx
0x180047eab  pop     rbp
0x180047eac  retn
0x180047ead  test    esi, esi
0x180047eaf  jz      short loc_180047EB9
0x180047eb1  test    r14d, r14d
0x180047eb4  jnz     short loc_180047EB9
0x180047eb6  xor     r15d, r15d
0x180047eb9  lea     rax, [rbp+57h+var_90]
0x180047ebd  mov     cs:gBfeEventController, r15d
0x180047ec4  mov     [rsp+0C0h+lpcbData], rax
0x180047ec9  lea     r8, aNeteventmatcha; "NetEventMatchAnyKeywords"
0x180047ed0  lea     rax, [rbp+57h+var_8C]
0x180047ed4  lea     rdx, aSystemCurrentc_4; "System\\CurrentControlSet\\Services\\BF"...
0x180047edb  mov     [rsp+0C0h+phkResult], rax
0x180047ee0  call    BfeRegQueryDWord
0x180047ee5  mov     rbx, rax
0x180047ee8  test    rax, rax
0x180047eeb  jnz     loc_180047E6C
0x180047ef1  cmp     [rbp+57h+var_90], eax
0x180047ef4  jz      short loc_180047EFF
0x180047ef6  mov     eax, [rbp+57h+var_8C]
0x180047ef9  mov     cs:dword_1800F2F44, eax
0x180047eff  mov     rcx, cs:ParentDescriptor; ParentDescriptor
0x180047f06  lea     rax, CreatorDescriptor
0x180047f0d  mov     [rsp+0C0h+lpcbData], rax; __int64
0x180047f12  lea     rdx, FWPM_OBJECT_TYPE_NET_EVENTS
0x180047f19  xor     r9d, r9d
0x180047f1c  mov     dword ptr [rsp+0C0h+phkResult], 0; IsContainerObject
0x180047f24  xor     r8d, r8d
0x180047f27  call    BfeObjectSecurityLoad
0x180047f2c  mov     rbx, rax
0x180047f2f  test    rax, rax
0x180047f32  jnz     loc_180047E6C
0x180047f38  lea     rcx, stru_1800F2F60
0x180047f3f  call    WfpCriticalSectionCreate
0x180047f44  mov     rbx, rax
0x180047f47  test    rax, rax
0x180047f4a  jnz     loc_180047E6C
0x180047f50  lea     rax, qword_1800F2F90
0x180047f57  lea     r9, BfeNetEventNotify
0x180047f5e  mov     [rsp+0C0h+phkResult], rax
0x180047f63  lea     r8, BfeDestroy_FWPM_NET_EVENT_SUBSCRIPTION
0x180047f6a  lea     rdx, BfeNetEventSubQueryPublic
0x180047f71  lea     rcx, BfeNetEventSubDestroy
0x180047f78  call    BfeChangeSourceCreate
0x180047f7d  mov     rbx, rax
0x180047f80  test    rax, rax
0x180047f83  jnz     loc_180047E6C
0x180047f89  cmp     cs:gBfeEventController, eax
0x180047f8f  jz      loc_180047E8A
0x180047f95  xor     r9d, r9d
0x180047f98  lea     rdx, BfeEventControllerDelayStart
0x180047f9f  xor     r8d, r8d
0x180047fa2  lea     rcx, qword_1800F2FA0
0x180047fa9  call    cs:__imp_TpAllocTimer
0x180047faf  test    eax, eax
0x180047fb1  jns     short loc_180047FD3
0x180047fb3  mov     r8d, eax
0x180047fb6  lea     rdx, aTpalloctimer; "TpAllocTimer"
0x180047fbd  call    WfpReportSysErrorAsNtStatus
0x180047fc2  mov     rbx, rax
0x180047fc5  test    rax, rax
0x180047fc8  jnz     loc_180047E6C
0x180047fce  jmp     loc_180047E8A
0x180047fd3  mov     rcx, cs:qword_1800F2FA0
0x180047fda  lea     rdx, [rbp+57h+var_58]
0x180047fde  xor     r9d, r9d
0x180047fe1  mov     [rbp+57h+var_58], 0FFFFFFFFDC3CBA00h
0x180047fe9  xor     r8d, r8d
0x180047fec  call    cs:__imp_TpSetTimer
0x180047ff2  jmp     loc_180047E8A
```
