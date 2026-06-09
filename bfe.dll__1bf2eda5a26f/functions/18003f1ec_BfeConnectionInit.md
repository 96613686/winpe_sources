# BfeConnectionInit

- ea: `0x18003f1ec`
- end: `0x18003f514`
- name: `BfeConnectionInit`
- size: `808`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003f1a0`

## callees

- `0x1800039e4`
- `0x1800040ac`
- `0x18000474c`
- `0x18000e000`
- `0x18001236c`
- `0x180018b74`
- `0x180022730`
- `0x180030180`
- `0x18003f1ec`
- `0x1800469ec`
- `0x180047af4`
- `0x180047b8c`
- `0x180058b30`
- `0x180059d1c`
- `0x180067fac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003f2ba`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003f31f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003f2ba`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003f31f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003f24d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003f24d`

## string_xrefs

- `0x18003f233`: `System\CurrentControlSet\Services\BFE\Parameters\Policy\Options`
- `0x18003f25d`: `RegOpenKeyExW`
- `0x18003f271`: `BfeRegOpenKey`

## pseudocode

```c
__int64 BfeConnectionInit()
{
  int v0; // r15d
  _DWORD *v1; // rsi
  int v2; // r12d
  unsigned int v3; // eax
  __int64 v4; // rcx
  __int64 v5; // rax
  __int64 v6; // rbx
  HKEY v7; // rdi
  LPBYTE v8; // r14
  unsigned int v9; // eax
  __int64 v10; // rcx
  LPBYTE lpData; // [rsp+30h] [rbp-40h] BYREF
  LPBYTE v13; // [rsp+38h] [rbp-38h] BYREF
  DWORD cbData; // [rsp+40h] [rbp-30h]
  DWORD lpcbData; // [rsp+48h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-20h] BYREF
  DWORD Type; // [rsp+58h] [rbp-18h] BYREF

  v0 = 0;
  cbData = 4;
  v1 = 0;
  Type = 0;
  lpcbData = 0;
  lpData = 0;
  v13 = 0;
  hKey = 0;
  v2 = 0;
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
    v7 = 0;
  }
  else if ( v3 == 2 )
  {
    v7 = 0;
    v6 = 0;
  }
  else
  {
    v7 = hKey;
    lpcbData = cbData;
    v6 = WfpMemAlloc(cbData, 0);
    if ( !v6 )
    {
      v8 = lpData;
      v9 = RegQueryValueExW(v7, L"CollectConnections", 0, &Type, lpData, &lpcbData);
      if ( v9 != 2 && v9 != 234 )
      {
        if ( v9 )
        {
          v6 = WfpReportSysErrorAsWinError(v10, "RegQueryValueExW", v9);
        }
        else if ( Type == 4 && lpcbData == cbData )
        {
          lpData = 0;
          v1 = v8;
          v2 = 1;
          v13 = v8;
        }
      }
    }
  }
  WfpMemFree(&lpData);
  BfeRegCloseKey(v7);
  if ( v6 )
  {
    WfpReportError(v6, "BfeRegQueryValue");
  }
  else if ( v2 )
  {
    v0 = *v1;
  }
  WfpMemFree(&v13);
  if ( v6 )
  {
    WfpReportError(v6, "BfeRegQueryDWord");
    BfeConnectionShutdown();
LABEL_35:
    WfpReportError(v6, "BfeConnectionInit");
    return v6;
  }
  LODWORD(qword_1800F2668[220]) = v0 != 0;
  if ( (unsigned __int8)IsEvtGetChannelConfigPropertyPresent()
    && (unsigned __int8)IsEvtGetChannelConfigPropertyPresent()
    && (unsigned __int8)IsEvtGetChannelConfigPropertyPresent() )
  {
    BfeConnectionEventLogReadChannelsConfig();
  }
  v6 = BfeObjectSecurityLoad((PSECURITY_DESCRIPTOR)qword_1800F2668[173], 0, (__int64)&qword_1800F2668[221]);
  if ( v6 )
    goto LABEL_34;
  v6 = WfpCriticalSectionCreate(&qword_1800F2668[222]);
  if ( v6
    || (v6 = BfeChangeSourceCreate(
               (unsigned int)BfeConnectionSubDestroy,
               (unsigned int)BfeConnectionSubQueryPublic,
               (unsigned int)BfeDestroy_FWPM_PROVIDER_CONTEXT_ENUM_TEMPLATE0,
               (unsigned int)BfeConnectionNotify,
               (__int64)&qword_1800F2668[228])) != 0
    || (v6 = WfpHashtableCreate(&qword_1800F2668[242])) != 0
    || (LODWORD(qword_1800F2668[241]) = 1, (v6 = WfpHashtableCreate(&qword_1800F2668[248])) != 0)
    || (LODWORD(qword_1800F2668[247]) = 1, (v6 = BfeConnectionRegisterEventProvider()) != 0)
    || (v6 = WfpCriticalSectionCreate(&qword_1800F2668[229])) != 0 )
  {
LABEL_34:
    BfeConnectionShutdown();
    goto LABEL_35;
  }
  *(_OWORD *)&qword_1800F2668[235] = 0;
  *(_OWORD *)&qword_1800F2668[237] = 0;
  *(_OWORD *)&qword_1800F2668[239] = 0;
  return v6;
}

```

## disassembly

```asm
0x18003f1ec  push    rbp
0x18003f1ee  push    rbx
0x18003f1ef  push    rsi
0x18003f1f0  push    rdi
0x18003f1f1  push    r12
0x18003f1f3  push    r14
0x18003f1f5  push    r15
0x18003f1f7  mov     rbp, rsp
0x18003f1fa  sub     rsp, 70h
0x18003f1fe  mov     rax, cs:__security_cookie
0x18003f205  xor     rax, rsp
0x18003f208  mov     [rbp+var_10], rax
0x18003f20c  xor     r15d, r15d
0x18003f20f  mov     [rbp+cbData], 4
0x18003f216  xor     esi, esi
0x18003f218  mov     [rbp+Type], r15d
0x18003f21c  lea     rax, [rbp+hKey]
0x18003f220  mov     [rbp+var_28], r15d
0x18003f224  xor     r8d, r8d; ulOptions
0x18003f227  mov     [rbp+lpData], r15
0x18003f22b  lea     r9d, [r15+1]; samDesired
0x18003f22f  mov     [rbp+var_38], rsi
0x18003f233  lea     rdx, aSystemCurrentc_3; "System\\CurrentControlSet\\Services\\BF"...
0x18003f23a  mov     [rbp+hKey], rsi
0x18003f23e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003f245  mov     [rsp+70h+phkResult], rax; phkResult
0x18003f24a  xor     r12d, r12d
0x18003f24d  call    cs:__imp_RegOpenKeyExW
0x18003f253  test    eax, 0FFFFFFFDh
0x18003f258  jz      short loc_18003F287
0x18003f25a  mov     r8d, eax
0x18003f25d  lea     rdx, aRegopenkeyexw; "RegOpenKeyExW"
0x18003f264  call    WfpReportSysErrorAsWinError
0x18003f269  mov     rbx, rax
0x18003f26c  test    rax, rax
0x18003f26f  jz      short loc_18003F280
0x18003f271  lea     rdx, aBferegopenkey; "BfeRegOpenKey"
0x18003f278  mov     rcx, rax
0x18003f27b  call    WfpReportError
0x18003f280  xor     edi, edi
0x18003f282  jmp     loc_18003F358
0x18003f287  cmp     eax, 2
0x18003f28a  jz      loc_18003F354
0x18003f290  mov     eax, [rbp+cbData]
0x18003f293  mov     rdi, [rbp+hKey]
0x18003f297  test    eax, eax
0x18003f299  jnz     short loc_18003F2E4
0x18003f29b  lea     rax, [rbp+cbData]
0x18003f29f  xor     r8d, r8d; lpReserved
0x18003f2a2  mov     [rsp+70h+lpcbData], rax; lpcbData
0x18003f2a7  lea     r9, [rbp+Type]; lpType
0x18003f2ab  lea     rdx, aCollectconnect; "CollectConnections"
0x18003f2b2  mov     [rsp+70h+phkResult], rsi; lpData
0x18003f2b7  mov     rcx, rdi; hKey
0x18003f2ba  call    cs:__imp_RegQueryValueExW
0x18003f2c0  cmp     eax, 2
0x18003f2c3  jz      loc_18003F356
0x18003f2c9  test    eax, eax
0x18003f2cb  jz      short loc_18003F2E1
0x18003f2cd  mov     r8d, eax
0x18003f2d0  lea     rdx, aRegqueryvaluee; "RegQueryValueExW"
0x18003f2d7  call    WfpReportSysErrorAsWinError
0x18003f2dc  mov     rbx, rax
0x18003f2df  jmp     short loc_18003F358
0x18003f2e1  mov     eax, [rbp+cbData]
0x18003f2e4  mov     ecx, eax; dwBytes
0x18003f2e6  lea     r8, [rbp+lpData]
0x18003f2ea  xor     edx, edx; dwFlags
0x18003f2ec  mov     [rbp+var_28], eax
0x18003f2ef  call    WfpMemAlloc
0x18003f2f4  mov     rbx, rax
0x18003f2f7  test    rax, rax
0x18003f2fa  jnz     short loc_18003F358
0x18003f2fc  mov     r14, [rbp+lpData]
0x18003f300  lea     rax, [rbp+var_28]
0x18003f304  mov     [rsp+70h+lpcbData], rax; lpcbData
0x18003f309  lea     r9, [rbp+Type]; lpType
0x18003f30d  xor     r8d, r8d; lpReserved
0x18003f310  mov     [rsp+70h+phkResult], r14; lpData
0x18003f315  lea     rdx, aCollectconnect; "CollectConnections"
0x18003f31c  mov     rcx, rdi; hKey
0x18003f31f  call    cs:__imp_RegQueryValueExW
0x18003f325  cmp     eax, 2
0x18003f328  jz      short loc_18003F358
0x18003f32a  cmp     eax, 0EAh
0x18003f32f  jz      short loc_18003F358
0x18003f331  test    eax, eax
0x18003f333  jnz     short loc_18003F2CD
0x18003f335  cmp     [rbp+Type], 4
0x18003f339  jnz     short loc_18003F358
0x18003f33b  mov     eax, [rbp+cbData]
0x18003f33e  cmp     [rbp+var_28], eax
0x18003f341  jnz     short loc_18003F358
0x18003f343  mov     [rbp+lpData], r12
0x18003f347  mov     rsi, r14
0x18003f34a  lea     r12d, [rbx+1]
0x18003f34e  mov     [rbp+var_38], r14
0x18003f352  jmp     short loc_18003F358
0x18003f354  xor     edi, edi
0x18003f356  xor     ebx, ebx
0x18003f358  lea     rcx, [rbp+lpData]
0x18003f35c  call    WfpMemFree
0x18003f361  mov     rcx, rdi
0x18003f364  call    BfeRegCloseKey
0x18003f369  test    rbx, rbx
0x18003f36c  jz      short loc_18003F37F
0x18003f36e  lea     rdx, aBferegqueryval; "BfeRegQueryValue"
0x18003f375  mov     rcx, rbx
0x18003f378  call    WfpReportError
0x18003f37d  jmp     short loc_18003F387
0x18003f37f  test    r12d, r12d
0x18003f382  jz      short loc_18003F387
0x18003f384  mov     r15d, [rsi]
0x18003f387  lea     rcx, [rbp+var_38]
0x18003f38b  call    WfpMemFree
0x18003f390  test    rbx, rbx
0x18003f393  jz      short loc_18003F3AE
0x18003f395  lea     rdx, aBferegquerydwo; "BfeRegQueryDWord"
0x18003f39c  mov     rcx, rbx
0x18003f39f  call    WfpReportError
0x18003f3a4  call    BfeConnectionShutdown
0x18003f3a9  jmp     loc_18003F4E7
0x18003f3ae  xor     eax, eax
0x18003f3b0  test    r15d, r15d
0x18003f3b3  setnz   al
0x18003f3b6  mov     dword ptr cs:qword_1800F2668+6E0h, eax
0x18003f3bc  call    IsEvtGetChannelConfigPropertyPresent
0x18003f3c1  test    al, al
0x18003f3c3  jz      short loc_18003F3DC
0x18003f3c5  call    IsEvtGetChannelConfigPropertyPresent
0x18003f3ca  test    al, al
0x18003f3cc  jz      short loc_18003F3DC
0x18003f3ce  call    IsEvtGetChannelConfigPropertyPresent
0x18003f3d3  test    al, al
0x18003f3d5  jz      short loc_18003F3DC
0x18003f3d7  call    BfeConnectionEventLogReadChannelsConfig
0x18003f3dc  mov     rcx, cs:qword_1800F2668+568h; ParentDescriptor
0x18003f3e3  lea     rax, qword_1800F2668+6E8h
0x18003f3ea  mov     [rsp+70h+lpcbData], rax; __int64
0x18003f3ef  lea     r8, aOCodA0x000007f; "O:COD:(A;;0x000007FF;;;BA)(A;;0x000006A"...
0x18003f3f6  xor     r9d, r9d
0x18003f3f9  mov     dword ptr [rsp+70h+phkResult], 0; IsContainerObject
0x18003f401  lea     rdx, FWPM_OBJECT_TYPE_CONNECTIONS
0x18003f408  call    BfeObjectSecurityLoad
0x18003f40d  mov     rbx, rax
0x18003f410  test    rax, rax
0x18003f413  jnz     loc_18003F4DD
0x18003f419  lea     rcx, qword_1800F2668+6F0h
0x18003f420  call    WfpCriticalSectionCreate
0x18003f425  mov     rbx, rax
0x18003f428  test    rax, rax
0x18003f42b  jnz     loc_18003F4DD
0x18003f431  lea     rax, qword_1800F2668+720h
0x18003f438  lea     r9, BfeConnectionNotify
0x18003f43f  mov     [rsp+70h+phkResult], rax
0x18003f444  lea     r8, BfeDestroy_FWPM_PROVIDER_CONTEXT_ENUM_TEMPLATE0
0x18003f44b  lea     rdx, BfeConnectionSubQueryPublic
0x18003f452  lea     rcx, BfeConnectionSubDestroy
0x18003f459  call    BfeChangeSourceCreate
0x18003f45e  mov     rbx, rax
0x18003f461  test    rax, rax
0x18003f464  jnz     short loc_18003F4DD
0x18003f466  lea     rcx, qword_1800F2668+790h
0x18003f46d  call    WfpHashtableCreate
0x18003f472  mov     rbx, rax
0x18003f475  test    rax, rax
0x18003f478  jnz     short loc_18003F4DD
0x18003f47a  lea     rcx, qword_1800F2668+7C0h
0x18003f481  mov     dword ptr cs:qword_1800F2668+788h, 1
0x18003f48b  call    WfpHashtableCreate
0x18003f490  mov     rbx, rax
0x18003f493  test    rax, rax
0x18003f496  jnz     short loc_18003F4DD
0x18003f498  mov     dword ptr cs:qword_1800F2668+7B8h, 1
0x18003f4a2  call    BfeConnectionRegisterEventProvider
0x18003f4a7  mov     rbx, rax
0x18003f4aa  test    rax, rax
0x18003f4ad  jnz     short loc_18003F4DD
0x18003f4af  lea     rcx, qword_1800F2668+728h
0x18003f4b6  call    WfpCriticalSectionCreate
0x18003f4bb  mov     rbx, rax
0x18003f4be  test    rax, rax
0x18003f4c1  jnz     short loc_18003F4DD
0x18003f4c3  xorps   xmm0, xmm0
0x18003f4c6  movups  xmmword ptr cs:qword_1800F2668+758h, xmm0
0x18003f4cd  movups  xmmword ptr cs:qword_1800F2668+768h, xmm0
0x18003f4d4  movups  xmmword ptr cs:qword_1800F2668+778h, xmm0
0x18003f4db  jmp     short loc_18003F4F6
0x18003f4dd  call    BfeConnectionShutdown
0x18003f4e2  test    rbx, rbx
0x18003f4e5  jz      short loc_18003F4F6
0x18003f4e7  lea     rdx, aBfeconnectioni; "BfeConnectionInit"
0x18003f4ee  mov     rcx, rbx
0x18003f4f1  call    WfpReportError
0x18003f4f6  mov     rax, rbx
0x18003f4f9  mov     rcx, [rbp+var_10]
0x18003f4fd  xor     rcx, rsp; StackCookie
0x18003f500  call    __security_check_cookie
0x18003f505  add     rsp, 70h
0x18003f509  pop     r15
0x18003f50b  pop     r14
0x18003f50d  pop     r12
0x18003f50f  pop     rdi
0x18003f510  pop     rsi
0x18003f511  pop     rbx
0x18003f512  pop     rbp
0x18003f513  retn
```
