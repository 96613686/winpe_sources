# FwMoneisPlumbCloudResourceNrpt(void)

- ea: `0x180047fa4`
- end: `0x180048398`
- name: `?FwMoneisPlumbCloudResourceNrpt@@YAKXZ`
- size: `1012`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800522f0`

## callees

- `0x180005954`
- `0x1800277b0`
- `0x1800284c4`
- `0x18002a03c`
- `0x18003104c`
- `0x180047fa4`
- `0x1800483a0`
- `0x18005a648`
- `0x18005e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800482de`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800482de`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180048250`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180048250`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180048260`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180048260`
- `ntdll!RtlNtStatusToDosError` at `0x1800482a5`
- `ntdll!RtlNtStatusToDosError` at `0x1800482a5`
- `fwbase!FwBaseFree` at `0x180048330`
- `fwbase!FwBaseFree` at `0x180048344`
- `fwbase!FwBaseFree` at `0x18004834e`
- `fwbase!FwBaseFree` at `0x18004835a`
- `fwbase!FwBaseFree` at `0x18004836a`
- `fwbase!FwBaseFree` at `0x180048375`
- `fwbase!FwBaseFree` at `0x180048330`
- `fwbase!FwBaseFree` at `0x180048344`
- `fwbase!FwBaseFree` at `0x18004834e`
- `fwbase!FwBaseFree` at `0x18004835a`
- `fwbase!FwBaseFree` at `0x18004836a`
- `fwbase!FwBaseFree` at `0x180048375`
- `fwbase!FwRegQueryString` at `0x1800480c3`
- `fwbase!FwRegQueryString` at `0x1800480c3`
- `fwbase!FwRegSetDWord` at `0x180048325`
- `fwbase!FwRegSetDWord` at `0x180048325`
- `fwbase!FwParseEdpCloudResourceStringToNrptRuleList` at `0x18004820e`
- `fwbase!FwParseEdpCloudResourceStringToNrptRuleList` at `0x18004820e`
- `fwbase!FwHResultToWindowsError` at `0x180048119`
- `fwbase!FwHResultToWindowsError` at `0x1800481a2`
- `fwbase!FwHResultToWindowsError` at `0x180048119`
- `fwbase!FwHResultToWindowsError` at `0x1800481a2`
- `fwbase!FwStringCopy` at `0x1800480f5`
- `fwbase!FwStringCopy` at `0x18004819a`
- `fwbase!FwStringCopy` at `0x1800480f5`
- `fwbase!FwStringCopy` at `0x18004819a`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_FreeStringValue` at `0x180048102`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_FreeStringValue` at `0x180048102`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyString` at `0x1800480e5`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyString` at `0x1800480e5`

## string_xrefs

- `0x180048249`: `ntdll.dll`
- `0x180047fc9`: `SYSTEM\CurrentControlSet\Services\dnscache`
- `0x180048281`: `SYSTEM\CurrentControlSet\Services\dnscache`
- `0x18004828d`: `TargetPath`
- `0x180048294`: `Dnscache`

## pseudocode

```c
__int64 FwMoneisPlumbCloudResourceNrpt(void)
{
  unsigned int v0; // edi
  FwPolicy2 *v1; // rcx
  __int64 v2; // rdx
  __int64 v3; // r9
  unsigned int v4; // ebx
  unsigned int v5; // eax
  ULONG v6; // eax
  unsigned int v7; // eax
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  NTSTATUS v10; // eax
  _QWORD *v11; // rsi
  _QWORD *v12; // rbx
  __int64 v14; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v15; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD *v16; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v17; // [rsp+58h] [rbp-A8h] BYREF
  int v18; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD v19[3]; // [rsp+64h] [rbp-9Ch] BYREF
  _OWORD v20[4]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v21[22]; // [rsp+B0h] [rbp-50h]
  _BYTE v22[442]; // [rsp+C6h] [rbp-3Ah] BYREF

  v20[0] = *(_OWORD *)L"SYSTEM\\CurrentControlSet\\Services\\dnscache";
  v20[1] = *(_OWORD *)L"urrentControlSet\\Services\\dnscache";
  v20[2] = *(_OWORD *)L"ntrolSet\\Services\\dnscache";
  v20[3] = *(_OWORD *)L"\\Services\\dnscache";
  *(_OWORD *)v21 = *(_OWORD *)L"s\\dnscache";
  *(_QWORD *)&v21[14] = *(_QWORD *)L"che";
  v18 = 0;
  v14 = 0;
  v17 = 0;
  v15 = 0;
  v19[0] = 0;
  v16 = 0;
  memset_0(v22, 0, 0x1B2u);
  if ( !(unsigned __int8)IsPolicyManager_GetPolicyStringPresent() )
  {
    v0 = 50;
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v2 = 432;
      v3 = 50;
LABEL_5:
      WPP_SF_d(*((_QWORD *)v1 + 2), v2, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v3);
      goto LABEL_41;
    }
    goto LABEL_41;
  }
  v4 = FwRegQueryString(
         -2147483646,
         L"Software\\Policies\\Microsoft\\Windows\\NetworkIsolation",
         L"CloudResources",
         &v14,
         &v18);
  if ( !v18 )
  {
    PolicyManager_GetPolicyString(L"NetworkIsolation", L"EnterpriseCloudResources", &v15);
    v4 = FwStringCopy(v15, &v14);
    PolicyManager_FreeStringValue(v15);
  }
  if ( !v14 )
  {
    v0 = 0;
    goto LABEL_41;
  }
  v5 = FwHResultToWindowsError(v4);
  v0 = v5;
  if ( !v5 )
  {
    v6 = FwMoneisUnPlumbCloudResourceNrpt();
    v0 = v6;
    if ( v6 == 2 )
    {
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 434, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
    }
    else if ( v6 )
    {
      v1 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_41;
      v2 = 435;
      goto LABEL_26;
    }
    v7 = FwStringCopy(v14, &v17);
    v6 = FwHResultToWindowsError(v7);
    v0 = v6;
    if ( v6 )
    {
      v1 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_41;
      v2 = 436;
    }
    else
    {
      v6 = FwParseEdpCloudResourceStringToNrptRuleList(v17, 0, &v16, v19);
      v0 = v6;
      if ( v6 )
      {
        v1 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_41;
        v2 = 437;
      }
      else
      {
        RasAddNrptRules(v16, v19[0]);
        ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
        ProcAddress = GetProcAddress(ModuleHandleW, "RtlGetPersistedStateLocation");
        if ( !ProcAddress
          || (v10 = ((__int64 (__fastcall *)(const wchar_t *, const wchar_t *, const wchar_t *, _QWORD, _OWORD *, int, _QWORD))ProcAddress)(
                      L"Dnscache",
                      L"TargetPath",
                      L"SYSTEM\\CurrentControlSet\\Services\\dnscache",
                      0,
                      v20,
                      520,
                      0),
              v6 = RtlNtStatusToDosError(v10),
              (v0 = v6) == 0) )
        {
          if ( (unsigned int)_o_wcscat_s(v20, 260, L"\\Parameters") )
          {
            v0 = 87;
            v1 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v2 = 439;
              v3 = 87;
              goto LABEL_5;
            }
          }
          else
          {
            FwRegSetDWord(-2147483646, v20, L"ShortnameProxyDefault", 1);
          }
          goto LABEL_41;
        }
        v1 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_41;
        v2 = 438;
      }
    }
LABEL_26:
    v3 = v6;
    goto LABEL_5;
  }
  v1 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v2 = 433;
    v3 = v5;
    goto LABEL_5;
  }
LABEL_41:
  FwBaseFree(v14);
  v11 = v16;
  if ( v16 )
  {
    do
    {
      FwBaseFree(v11[5]);
      FwBaseFree(v11[7]);
      v12 = (_QWORD *)*v11;
      FwBaseFree(v11);
      v11 = v12;
    }
    while ( v12 );
  }
  FwBaseFree(0);
  FwBaseFree(v17);
  return v0;
}

```

## disassembly

```asm
0x180047fa4  push    rbp
0x180047fa6  push    rbx
0x180047fa7  push    rsi
0x180047fa8  push    rdi
0x180047fa9  lea     rbp, [rsp-198h]
0x180047fb1  sub     rsp, 298h
0x180047fb8  mov     rax, cs:__security_cookie
0x180047fbf  xor     rax, rsp
0x180047fc2  mov     [rbp+1B0h+var_30], rax
0x180047fc9  movaps  xmm0, xmmword ptr cs:aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\dn"...
0x180047fd0  lea     rcx, [rbp+1B0h+var_1EA]; void *
0x180047fd4  movaps  xmm1, xmmword ptr cs:aSystemCurrentc+10h; "urrentControlSet\\Services\\dnscache"
0x180047fdb  xor     edx, edx; Val
0x180047fdd  movaps  [rsp+2B0h+var_240], xmm0
0x180047fe2  mov     r8d, 1B2h; Size
0x180047fe8  movaps  xmm0, xmmword ptr cs:aSystemCurrentc+20h; "ntrolSet\\Services\\dnscache"
0x180047fef  movaps  [rbp+1B0h+var_230], xmm1
0x180047ff3  movaps  xmm1, xmmword ptr cs:aSystemCurrentc+30h; "\\Services\\dnscache"
0x180047ffa  movaps  [rbp+1B0h+var_220], xmm0
0x180047ffe  movaps  xmm0, xmmword ptr cs:aSystemCurrentc+40h; "s\\dnscache"
0x180048005  movaps  [rbp+1B0h+var_210], xmm1
0x180048009  movsd   xmm1, qword ptr cs:aSystemCurrentc+4Eh; "che"
0x180048011  movaps  xmmword ptr [rbp+1B0h+var_200], xmm0
0x180048015  movsd   qword ptr [rbp+1B0h+var_200+0Eh], xmm1
0x18004801a  mov     [rsp+2B0h+var_250], 0
0x180048022  mov     [rsp+2B0h+var_270], 0
0x18004802b  mov     [rsp+2B0h+var_258], 0
0x180048034  mov     [rsp+2B0h+var_268], 0
0x18004803d  mov     [rsp+2B0h+var_24C], 0
0x180048045  mov     [rsp+2B0h+var_260], 0
0x18004804e  call    memset_0
0x180048053  call    IsPolicyManager_GetPolicyStringPresent
0x180048058  test    al, al
0x18004805a  jnz     short loc_18004809F
0x18004805c  mov     edi, 32h ; '2'
0x180048061  mov     rcx, cs:WPP_GLOBAL_Control
0x180048068  lea     rbx, WPP_GLOBAL_Control
0x18004806f  cmp     rcx, rbx
0x180048072  jz      loc_18004832B
0x180048078  test    byte ptr [rcx+1Ch], 1
0x18004807c  jz      loc_18004832B
0x180048082  mov     edx, 1B0h
0x180048087  mov     r9d, edi
0x18004808a  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x180048091  mov     rcx, [rcx+10h]
0x180048095  call    WPP_SF_d
0x18004809a  jmp     loc_18004832B
0x18004809f  lea     rax, [rsp+2B0h+var_250]
0x1800480a4  mov     rcx, 0FFFFFFFF80000002h
0x1800480ab  lea     r9, [rsp+2B0h+var_270]
0x1800480b0  mov     [rsp+2B0h+var_290], rax
0x1800480b5  lea     r8, aCloudresources; "CloudResources"
0x1800480bc  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x1800480c3  call    cs:__imp_FwRegQueryString
0x1800480c9  cmp     [rsp+2B0h+var_250], 0
0x1800480ce  mov     ebx, eax
0x1800480d0  jnz     short loc_180048108
0x1800480d2  lea     r8, [rsp+2B0h+var_268]
0x1800480d7  lea     rdx, aEnterpriseclou; "EnterpriseCloudResources"
0x1800480de  lea     rcx, aNetworkisolati_32; "NetworkIsolation"
0x1800480e5  call    cs:__imp_PolicyManager_GetPolicyString
0x1800480eb  mov     rcx, [rsp+2B0h+var_268]
0x1800480f0  lea     rdx, [rsp+2B0h+var_270]
0x1800480f5  call    cs:__imp_FwStringCopy
0x1800480fb  mov     rcx, [rsp+2B0h+var_268]
0x180048100  mov     ebx, eax
0x180048102  call    cs:__imp_PolicyManager_FreeStringValue
0x180048108  cmp     [rsp+2B0h+var_270], 0
0x18004810e  jnz     short loc_180048117
0x180048110  xor     edi, edi
0x180048112  jmp     loc_18004832B
0x180048117  mov     ecx, ebx
0x180048119  call    cs:__imp_FwHResultToWindowsError
0x18004811f  mov     edi, eax
0x180048121  test    eax, eax
0x180048123  jz      short loc_180048153
0x180048125  mov     rcx, cs:WPP_GLOBAL_Control
0x18004812c  lea     rbx, WPP_GLOBAL_Control
0x180048133  cmp     rcx, rbx
0x180048136  jz      loc_18004832B
0x18004813c  test    byte ptr [rcx+1Ch], 1
0x180048140  jz      loc_18004832B
0x180048146  mov     edx, 1B1h
0x18004814b  mov     r9d, eax
0x18004814e  jmp     loc_18004808A
0x180048153  call    ?FwMoneisUnPlumbCloudResourceNrpt@@YAKXZ; FwMoneisUnPlumbCloudResourceNrpt(void)
0x180048158  lea     rbx, WPP_GLOBAL_Control
0x18004815f  mov     edi, eax
0x180048161  lea     rsi, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x180048168  cmp     eax, 2
0x18004816b  jnz     short loc_1800481CF
0x18004816d  mov     rcx, cs:WPP_GLOBAL_Control
0x180048174  cmp     rcx, rbx
0x180048177  jz      short loc_180048190
0x180048179  test    byte ptr [rcx+1Ch], 4
0x18004817d  jz      short loc_180048190
0x18004817f  mov     rcx, [rcx+10h]
0x180048183  mov     edx, 1B2h
0x180048188  mov     r8, rsi
0x18004818b  call    WPP_SF_
0x180048190  mov     rcx, [rsp+2B0h+var_270]
0x180048195  lea     rdx, [rsp+2B0h+var_258]
0x18004819a  call    cs:__imp_FwStringCopy
0x1800481a0  mov     ecx, eax
0x1800481a2  call    cs:__imp_FwHResultToWindowsError
0x1800481a8  mov     edi, eax
0x1800481aa  test    eax, eax
0x1800481ac  jz      short loc_1800481FD
0x1800481ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800481b5  cmp     rcx, rbx
0x1800481b8  jz      loc_18004832B
0x1800481be  test    byte ptr [rcx+1Ch], 1
0x1800481c2  jz      loc_18004832B
0x1800481c8  mov     edx, 1B4h
0x1800481cd  jmp     short loc_1800481F2
0x1800481cf  test    eax, eax
0x1800481d1  jz      short loc_180048190
0x1800481d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800481da  cmp     rcx, rbx
0x1800481dd  jz      loc_18004832B
0x1800481e3  test    byte ptr [rcx+1Ch], 1
0x1800481e7  jz      loc_18004832B
0x1800481ed  mov     edx, 1B3h
0x1800481f2  mov     r9d, eax
0x1800481f5  mov     r8, rsi
0x1800481f8  jmp     loc_180048091
0x1800481fd  mov     rcx, [rsp+2B0h+var_258]
0x180048202  lea     r9, [rsp+2B0h+var_24C]
0x180048207  lea     r8, [rsp+2B0h+var_260]
0x18004820c  xor     edx, edx
0x18004820e  call    cs:__imp_FwParseEdpCloudResourceStringToNrptRuleList
0x180048214  mov     edi, eax
0x180048216  test    eax, eax
0x180048218  jz      short loc_18004823B
0x18004821a  mov     rcx, cs:WPP_GLOBAL_Control
0x180048221  cmp     rcx, rbx
0x180048224  jz      loc_18004832B
0x18004822a  test    byte ptr [rcx+1Ch], 1
0x18004822e  jz      loc_18004832B
0x180048234  mov     edx, 1B5h
0x180048239  jmp     short loc_1800481F2
0x18004823b  mov     edx, [rsp+2B0h+var_24C]
0x18004823f  mov     rcx, [rsp+2B0h+var_260]
0x180048244  call    RasAddNrptRules
0x180048249  lea     rcx, ModuleName; "ntdll.dll"
0x180048250  call    cs:__imp_GetModuleHandleW
0x180048256  mov     rcx, rax; hModule
0x180048259  lea     rdx, aRtlgetpersiste; "RtlGetPersistedStateLocation"
0x180048260  call    cs:__imp_GetProcAddress
0x180048266  test    rax, rax
0x180048269  jz      short loc_1800482CD
0x18004826b  mov     [rsp+2B0h+var_280], 0
0x180048274  lea     rcx, [rsp+2B0h+var_240]
0x180048279  mov     [rsp+2B0h+var_288], 208h
0x180048281  lea     r8, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\dn"...
0x180048288  mov     [rsp+2B0h+var_290], rcx
0x18004828d  lea     rdx, aTargetpath; "TargetPath"
0x180048294  lea     rcx, aDnscache; "Dnscache"
0x18004829b  xor     r9d, r9d
0x18004829e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800482a3  mov     ecx, eax; Status
0x1800482a5  call    cs:__imp_RtlNtStatusToDosError
0x1800482ab  mov     edi, eax
0x1800482ad  test    eax, eax
0x1800482af  jz      short loc_1800482CD
0x1800482b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800482b8  cmp     rcx, rbx
0x1800482bb  jz      short loc_18004832B
0x1800482bd  test    byte ptr [rcx+1Ch], 1
0x1800482c1  jz      short loc_18004832B
0x1800482c3  mov     edx, 1B6h
0x1800482c8  jmp     loc_1800481F2
0x1800482cd  lea     r8, aParameters; "\\Parameters"
0x1800482d4  mov     edx, 104h
0x1800482d9  lea     rcx, [rsp+2B0h+var_240]
0x1800482de  call    cs:__imp__o_wcscat_s
0x1800482e4  test    eax, eax
0x1800482e6  jz      short loc_18004830C
0x1800482e8  mov     edi, 57h ; 'W'
0x1800482ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800482f4  cmp     rcx, rbx
0x1800482f7  jz      short loc_18004832B
0x1800482f9  test    byte ptr [rcx+1Ch], 1
0x1800482fd  jz      short loc_18004832B
0x1800482ff  mov     edx, 1B7h
0x180048304  mov     r9d, edi
0x180048307  jmp     loc_1800481F5
0x18004830c  mov     r9d, 1
0x180048312  lea     r8, aShortnameproxy; "ShortnameProxyDefault"
0x180048319  lea     rdx, [rsp+2B0h+var_240]
0x18004831e  mov     rcx, 0FFFFFFFF80000002h
0x180048325  call    cs:__imp_FwRegSetDWord
0x18004832b  mov     rcx, [rsp+2B0h+var_270]
0x180048330  call    cs:__imp_FwBaseFree
0x180048336  mov     rsi, [rsp+2B0h+var_260]
0x18004833b  test    rsi, rsi
0x18004833e  jz      short loc_180048368
0x180048340  mov     rcx, [rsi+28h]
0x180048344  call    cs:__imp_FwBaseFree
0x18004834a  mov     rcx, [rsi+38h]
0x18004834e  call    cs:__imp_FwBaseFree
0x180048354  mov     rbx, [rsi]
0x180048357  mov     rcx, rsi
0x18004835a  call    cs:__imp_FwBaseFree
0x180048360  mov     rsi, rbx
0x180048363  test    rbx, rbx
0x180048366  jnz     short loc_180048340
0x180048368  xor     ecx, ecx
0x18004836a  call    cs:__imp_FwBaseFree
0x180048370  mov     rcx, [rsp+2B0h+var_258]
0x180048375  call    cs:__imp_FwBaseFree
0x18004837b  mov     eax, edi
0x18004837d  mov     rcx, [rbp+1B0h+var_30]
0x180048384  xor     rcx, rsp; StackCookie
0x180048387  call    __security_check_cookie
0x18004838c  add     rsp, 298h
0x180048393  pop     rdi
0x180048394  pop     rsi
0x180048395  pop     rbx
0x180048396  pop     rbp
0x180048397  retn
```
