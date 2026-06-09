# BfeConnectionInit

- ea: `0x18004047c`
- end: `0x1800407b7`
- name: `BfeConnectionInit`
- size: `827`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180040430`

## callees

- `0x180004070`
- `0x180004094`
- `0x180004798`
- `0x18000e7e0`
- `0x180012d8c`
- `0x1800197d0`
- `0x180024e40`
- `0x180031aa8`
- `0x18004047c`
- `0x1800486c8`
- `0x180049910`
- `0x180049a78`
- `0x18005aa60`
- `0x18005bc6c`
- `0x18006a534`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180040550`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800405bb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180040550`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800405bb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800404dd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800404dd`

## string_xrefs

- `0x1800404c3`: `System\CurrentControlSet\Services\BFE\Parameters\Policy\Options`
- `0x1800404f3`: `RegOpenKeyExW`
- `0x180040507`: `BfeRegOpenKey`

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
  dword_1800F5D68 = v0 != 0;
  if ( (unsigned __int8)IsEvtGetChannelConfigPropertyPresent()
    && (unsigned __int8)IsEvtGetChannelConfigPropertyPresent()
    && (unsigned __int8)IsEvtGetChannelConfigPropertyPresent() )
  {
    BfeConnectionEventLogReadChannelsConfig();
  }
  v6 = BfeObjectSecurityLoad(ParentDescriptor, 0, (__int64)&qword_1800F5D70);
  if ( v6 )
    goto LABEL_34;
  v6 = WfpCriticalSectionCreate(&stru_1800F5D78);
  if ( v6
    || (v6 = BfeChangeSourceCreate(
               (unsigned int)BfeConnectionSubDestroy,
               (unsigned int)BfeConnectionSubQueryPublic,
               (unsigned int)BfeDestroy_FWPM_PROVIDER_CONTEXT_ENUM_TEMPLATE0,
               (unsigned int)BfeConnectionNotify,
               (__int64)&qword_1800F5DA8)) != 0
    || (v6 = WfpHashtableCreate(qword_1800F5E18)) != 0
    || (dword_1800F5E10 = 1, (v6 = WfpHashtableCreate(qword_1800F5E48)) != 0)
    || (dword_1800F5E40 = 1, (v6 = BfeConnectionRegisterEventProvider()) != 0)
    || (v6 = WfpCriticalSectionCreate(&CriticalSection)) != 0 )
  {
LABEL_34:
    BfeConnectionShutdown();
    goto LABEL_35;
  }
  xmmword_1800F5DE0 = 0;
  xmmword_1800F5DF0 = 0;
  xmmword_1800F5E00 = 0;
  return v6;
}

```

## disassembly

```asm
0x18004047c  push    rbp
0x18004047e  push    rbx
0x18004047f  push    rsi
0x180040480  push    rdi
0x180040481  push    r12
0x180040483  push    r14
0x180040485  push    r15
0x180040487  mov     rbp, rsp
0x18004048a  sub     rsp, 70h
0x18004048e  mov     rax, cs:__security_cookie
0x180040495  xor     rax, rsp
0x180040498  mov     [rbp+var_10], rax
0x18004049c  xor     r15d, r15d
0x18004049f  mov     [rbp+cbData], 4
0x1800404a6  xor     esi, esi
0x1800404a8  mov     [rbp+Type], r15d
0x1800404ac  lea     rax, [rbp+hKey]
0x1800404b0  mov     [rbp+var_28], r15d
0x1800404b4  xor     r8d, r8d; ulOptions
0x1800404b7  mov     [rbp+lpData], r15
0x1800404bb  lea     r9d, [r15+1]; samDesired
0x1800404bf  mov     [rbp+var_38], rsi
0x1800404c3  lea     rdx, aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\BF"...
0x1800404ca  mov     [rbp+hKey], rsi
0x1800404ce  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800404d5  mov     [rsp+70h+phkResult], rax; phkResult
0x1800404da  xor     r12d, r12d
0x1800404dd  call    cs:__imp_RegOpenKeyExW
0x1800404e4  nop     dword ptr [rax+rax+00h]
0x1800404e9  test    eax, 0FFFFFFFDh
0x1800404ee  jz      short loc_18004051D
0x1800404f0  mov     r8d, eax
0x1800404f3  lea     rdx, aRegopenkeyexw; "RegOpenKeyExW"
0x1800404fa  call    WfpReportSysErrorAsWinError
0x1800404ff  mov     rbx, rax
0x180040502  test    rax, rax
0x180040505  jz      short loc_180040516
0x180040507  lea     rdx, aBferegopenkey; "BfeRegOpenKey"
0x18004050e  mov     rcx, rax
0x180040511  call    WfpReportError
0x180040516  xor     edi, edi
0x180040518  jmp     loc_1800405FA
0x18004051d  cmp     eax, 2
0x180040520  jz      loc_1800405F6
0x180040526  mov     eax, [rbp+cbData]
0x180040529  mov     rdi, [rbp+hKey]
0x18004052d  test    eax, eax
0x18004052f  jnz     short loc_180040580
0x180040531  lea     rax, [rbp+cbData]
0x180040535  xor     r8d, r8d; lpReserved
0x180040538  mov     [rsp+70h+lpcbData], rax; lpcbData
0x18004053d  lea     r9, [rbp+Type]; lpType
0x180040541  lea     rdx, aCollectconnect; "CollectConnections"
0x180040548  mov     [rsp+70h+phkResult], rsi; lpData
0x18004054d  mov     rcx, rdi; hKey
0x180040550  call    cs:__imp_RegQueryValueExW
0x180040557  nop     dword ptr [rax+rax+00h]
0x18004055c  cmp     eax, 2
0x18004055f  jz      loc_1800405F8
0x180040565  test    eax, eax
0x180040567  jz      short loc_18004057D
0x180040569  mov     r8d, eax
0x18004056c  lea     rdx, aRegqueryvaluee; "RegQueryValueExW"
0x180040573  call    WfpReportSysErrorAsWinError
0x180040578  mov     rbx, rax
0x18004057b  jmp     short loc_1800405FA
0x18004057d  mov     eax, [rbp+cbData]
0x180040580  mov     ecx, eax; dwBytes
0x180040582  lea     r8, [rbp+lpData]
0x180040586  xor     edx, edx; dwFlags
0x180040588  mov     [rbp+var_28], eax
0x18004058b  call    WfpMemAlloc
0x180040590  mov     rbx, rax
0x180040593  test    rax, rax
0x180040596  jnz     short loc_1800405FA
0x180040598  mov     r14, [rbp+lpData]
0x18004059c  lea     rax, [rbp+var_28]
0x1800405a0  mov     [rsp+70h+lpcbData], rax; lpcbData
0x1800405a5  lea     r9, [rbp+Type]; lpType
0x1800405a9  xor     r8d, r8d; lpReserved
0x1800405ac  mov     [rsp+70h+phkResult], r14; lpData
0x1800405b1  lea     rdx, aCollectconnect; "CollectConnections"
0x1800405b8  mov     rcx, rdi; hKey
0x1800405bb  call    cs:__imp_RegQueryValueExW
0x1800405c2  nop     dword ptr [rax+rax+00h]
0x1800405c7  cmp     eax, 2
0x1800405ca  jz      short loc_1800405FA
0x1800405cc  cmp     eax, 0EAh
0x1800405d1  jz      short loc_1800405FA
0x1800405d3  test    eax, eax
0x1800405d5  jnz     short loc_180040569
0x1800405d7  cmp     [rbp+Type], 4
0x1800405db  jnz     short loc_1800405FA
0x1800405dd  mov     eax, [rbp+cbData]
0x1800405e0  cmp     [rbp+var_28], eax
0x1800405e3  jnz     short loc_1800405FA
0x1800405e5  mov     [rbp+lpData], r12
0x1800405e9  mov     rsi, r14
0x1800405ec  lea     r12d, [rbx+1]
0x1800405f0  mov     [rbp+var_38], r14
0x1800405f4  jmp     short loc_1800405FA
0x1800405f6  xor     edi, edi
0x1800405f8  xor     ebx, ebx
0x1800405fa  lea     rcx, [rbp+lpData]
0x1800405fe  call    WfpMemFree
0x180040603  mov     rcx, rdi
0x180040606  call    BfeRegCloseKey
0x18004060b  test    rbx, rbx
0x18004060e  jz      short loc_180040621
0x180040610  lea     rdx, aBferegqueryval; "BfeRegQueryValue"
0x180040617  mov     rcx, rbx
0x18004061a  call    WfpReportError
0x18004061f  jmp     short loc_180040629
0x180040621  test    r12d, r12d
0x180040624  jz      short loc_180040629
0x180040626  mov     r15d, [rsi]
0x180040629  lea     rcx, [rbp+var_38]
0x18004062d  call    WfpMemFree
0x180040632  test    rbx, rbx
0x180040635  jz      short loc_180040650
0x180040637  lea     rdx, aBferegquerydwo; "BfeRegQueryDWord"
0x18004063e  mov     rcx, rbx
0x180040641  call    WfpReportError
0x180040646  call    BfeConnectionShutdown
0x18004064b  jmp     loc_180040789
0x180040650  xor     eax, eax
0x180040652  test    r15d, r15d
0x180040655  setnz   al
0x180040658  mov     cs:dword_1800F5D68, eax
0x18004065e  call    IsEvtGetChannelConfigPropertyPresent
0x180040663  test    al, al
0x180040665  jz      short loc_18004067E
0x180040667  call    IsEvtGetChannelConfigPropertyPresent
0x18004066c  test    al, al
0x18004066e  jz      short loc_18004067E
0x180040670  call    IsEvtGetChannelConfigPropertyPresent
0x180040675  test    al, al
0x180040677  jz      short loc_18004067E
0x180040679  call    BfeConnectionEventLogReadChannelsConfig
0x18004067e  mov     rcx, cs:ParentDescriptor; ParentDescriptor
0x180040685  lea     rax, qword_1800F5D70
0x18004068c  mov     [rsp+70h+lpcbData], rax; __int64
0x180040691  lea     r8, aOCodA0x000007f; "O:COD:(A;;0x000007FF;;;BA)(A;;0x000006A"...
0x180040698  xor     r9d, r9d
0x18004069b  mov     dword ptr [rsp+70h+phkResult], 0; IsContainerObject
0x1800406a3  lea     rdx, FWPM_OBJECT_TYPE_CONNECTIONS
0x1800406aa  call    BfeObjectSecurityLoad
0x1800406af  mov     rbx, rax
0x1800406b2  test    rax, rax
0x1800406b5  jnz     loc_18004077F
0x1800406bb  lea     rcx, stru_1800F5D78
0x1800406c2  call    WfpCriticalSectionCreate
0x1800406c7  mov     rbx, rax
0x1800406ca  test    rax, rax
0x1800406cd  jnz     loc_18004077F
0x1800406d3  lea     rax, qword_1800F5DA8
0x1800406da  lea     r9, BfeConnectionNotify
0x1800406e1  mov     [rsp+70h+phkResult], rax
0x1800406e6  lea     r8, BfeDestroy_FWPM_PROVIDER_CONTEXT_ENUM_TEMPLATE0
0x1800406ed  lea     rdx, BfeConnectionSubQueryPublic
0x1800406f4  lea     rcx, BfeConnectionSubDestroy
0x1800406fb  call    BfeChangeSourceCreate
0x180040700  mov     rbx, rax
0x180040703  test    rax, rax
0x180040706  jnz     short loc_18004077F
0x180040708  lea     rcx, qword_1800F5E18
0x18004070f  call    WfpHashtableCreate
0x180040714  mov     rbx, rax
0x180040717  test    rax, rax
0x18004071a  jnz     short loc_18004077F
0x18004071c  lea     rcx, qword_1800F5E48
0x180040723  mov     cs:dword_1800F5E10, 1
0x18004072d  call    WfpHashtableCreate
0x180040732  mov     rbx, rax
0x180040735  test    rax, rax
0x180040738  jnz     short loc_18004077F
0x18004073a  mov     cs:dword_1800F5E40, 1
0x180040744  call    BfeConnectionRegisterEventProvider
0x180040749  mov     rbx, rax
0x18004074c  test    rax, rax
0x18004074f  jnz     short loc_18004077F
0x180040751  lea     rcx, CriticalSection
0x180040758  call    WfpCriticalSectionCreate
0x18004075d  mov     rbx, rax
0x180040760  test    rax, rax
0x180040763  jnz     short loc_18004077F
0x180040765  xorps   xmm0, xmm0
0x180040768  movups  cs:xmmword_1800F5DE0, xmm0
0x18004076f  movups  cs:xmmword_1800F5DF0, xmm0
0x180040776  movups  cs:xmmword_1800F5E00, xmm0
0x18004077d  jmp     short loc_180040798
0x18004077f  call    BfeConnectionShutdown
0x180040784  test    rbx, rbx
0x180040787  jz      short loc_180040798
0x180040789  lea     rdx, aBfeconnectioni; "BfeConnectionInit"
0x180040790  mov     rcx, rbx
0x180040793  call    WfpReportError
0x180040798  mov     rax, rbx
0x18004079b  mov     rcx, [rbp+var_10]
0x18004079f  xor     rcx, rsp; StackCookie
0x1800407a2  call    __security_check_cookie
0x1800407a7  add     rsp, 70h
0x1800407ab  pop     r15
0x1800407ad  pop     r14
0x1800407af  pop     r12
0x1800407b1  pop     rdi
0x1800407b2  pop     rsi
0x1800407b3  pop     rbx
0x1800407b4  pop     rbp
0x1800407b5  retn
```
