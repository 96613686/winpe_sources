# ShouldSecurebootSkipUpdateOnARM(int *,ushort const * *,ulong *)

- ea: `0x18003dea4`
- end: `0x18003e10a`
- name: `?ShouldSecurebootSkipUpdateOnARM@@YAJPEAHPEAPEBGPEAK@Z`
- size: `614`
- prototype: `__int64 __fastcall(int *, const unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18003d8e0`

## callees

- `0x1800394b0`
- `0x18003c0b8`
- `0x18003c688`
- `0x18003c89c`
- `0x18003d04c`
- `0x18003dea4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003e0c5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003e0de`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003e0c5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003e0de`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003e0b7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003e0d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003e0b7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003e0d0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18003def4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18003def4`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x18003df56`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x18003dfcb`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x18003df56`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x18003dfcb`

## string_xrefs

- `0x18003df31`: `VendorIdentifierRegistryFailed`
- `0x18003df4c`: `Qualcomm`
- `0x18003df40`: `Check if this is a known bad Qualcomm processor ProcessorManufacturer:%ls`
- `0x18003df64`: `Proceeding with update as manufacturer is not Qualcomm ProcessorManufacturer:%ls`
- `0x18003df96`: `ProcessorNameStringRegistryFailed`
- `0x18003e021`: `Skipping DB update on Qualcomm device as UefiSecAppVersionRT is not found`
- `0x18003e062`: `Qualcomm fix present, proceeding with DB update uefiSecAppVersionRTVariable:%lx`
- `0x18003e098`: `ShouldSecurebootSkipUpdateOnARM returned: %x\nProcessorManufacturer: %ls\nProcessorNameString: %ls\nuefiSecAppVersionRTVariable: %lx`
- `0x18003e074`: `Skipping DB update on Qualcomm device due to known bad processor without fix uefiSecAppVersionRTVariable:%lx`
- `0x18003e0eb`: `ShouldSecurebootSkipUpdateOnARM`

## pseudocode

```c
__int64 __fastcall ShouldSecurebootSkipUpdateOnARM(int *a1, const unsigned __int16 **a2, unsigned int *a3)
{
  const unsigned __int16 *v3; // r15
  unsigned int v4; // esi
  WCHAR *v5; // rdi
  WCHAR *v6; // r14
  int v7; // ebx
  int HWSystemInformationFromRegistry; // eax
  int v9; // eax
  __int64 v10; // r12
  int UefiSecAppVersionRTVariable; // eax
  const unsigned __int16 *v12; // rcx
  HANDLE ProcessHeap; // rax
  HANDLE v14; // rax
  PCWSTR pszFirst; // [rsp+30h] [rbp-48h] BYREF
  PCWSTR v17; // [rsp+38h] [rbp-40h] BYREF
  struct _SYSTEM_INFO SystemInfo; // [rsp+40h] [rbp-38h] BYREF
  unsigned int v22; // [rsp+D8h] [rbp+60h] BYREF

  v3 = L"Passed";
  v4 = 0;
  v5 = 0;
  *a1 = 0;
  v6 = 0;
  pszFirst = 0;
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  v17 = 0;
  v22 = 0;
  GetSystemInfo(&SystemInfo);
  if ( SystemInfo.wProcessorArchitecture == 12 || (v7 = 0, SystemInfo.wProcessorArchitecture == 5) )
  {
    HWSystemInformationFromRegistry = GetHWSystemInformationFromRegistry(
                                        L"HARDWARE\\DESCRIPTION\\System\\CentralProcessor\\0",
                                        L"VendorIdentifier",
                                        (unsigned __int16 **)&pszFirst);
    v5 = (WCHAR *)pszFirst;
    v7 = HWSystemInformationFromRegistry;
    if ( HWSystemInformationFromRegistry < 0 )
    {
      v3 = L"VendorIdentifierRegistryFailed";
      goto LABEL_21;
    }
    SBServicingLogMessage(
      (wchar_t *)L"Check if this is a known bad Qualcomm processor ProcessorManufacturer:%ls",
      pszFirst);
    if ( !StrStrIW(v5, L"Qualcomm") )
    {
      SBServicingLogMessage(
        (wchar_t *)L"Proceeding with update as manufacturer is not Qualcomm ProcessorManufacturer:%ls",
        v5);
      goto LABEL_21;
    }
    v9 = GetHWSystemInformationFromRegistry(
           L"HARDWARE\\DESCRIPTION\\System\\CentralProcessor\\0",
           L"ProcessorNameString",
           (unsigned __int16 **)&v17);
    v6 = (WCHAR *)v17;
    v7 = v9;
    if ( v9 < 0 )
    {
      v3 = L"ProcessorNameStringRegistryFailed";
      goto LABEL_21;
    }
    SBServicingLogMessage((wchar_t *)L"ProcessorManufacturer: %ls ProcessorNameString: %ls", v5, v17);
    v10 = 0;
    while ( !StrStrIW(v6, *((PCWSTR *)&g_BadARMProcessorNameVersionMap + 2 * v10)) )
    {
      if ( (unsigned __int64)++v10 >= 0xC )
        goto LABEL_21;
    }
    SBServicingLogMessage(
      (wchar_t *)L"Matched %s:%lx",
      *((_QWORD *)&g_BadARMProcessorNameVersionMap + 2 * v10),
      *((unsigned int *)&g_BadARMProcessorNameVersionMap + 4 * v10 + 2));
    UefiSecAppVersionRTVariable = GetUefiSecAppVersionRTVariable(&v22);
    v7 = UefiSecAppVersionRTVariable;
    if ( UefiSecAppVersionRTVariable >= 0 )
    {
      v4 = v22;
      if ( !(unsigned int)IsUefiSecAppVersionRTLower(v22, *((_DWORD *)&g_BadARMProcessorNameVersionMap + 4 * v10 + 2)) )
      {
        SBServicingLogMessage(
          (wchar_t *)L"Qualcomm fix present, proceeding with DB update uefiSecAppVersionRTVariable:%lx",
          v4);
        goto LABEL_21;
      }
      *a1 = 1;
      SBServicingLogMessage(
        (wchar_t *)L"Skipping DB update on Qualcomm device due to known bad processor without fix uefiSecAppVersionRTVariable:%lx",
        v4);
      v12 = L"ProcessorArchitectureARM64_UefiSecAppVersionRT_Lower";
    }
    else
    {
      if ( UefiSecAppVersionRTVariable != -805306112 )
      {
        v4 = v22;
        v3 = L"GetUefiSecAppVersionRTVariableFailed";
        goto LABEL_21;
      }
      *a1 = 1;
      SBServicingLogMessage((wchar_t *)L"Skipping DB update on Qualcomm device as UefiSecAppVersionRT is not found");
      v4 = v22;
      v12 = L"ProcessorArchitectureARM64_UefiSecAppVersionRT_NotFound";
      v7 = 0;
    }
    *a2 = v12;
  }
LABEL_21:
  *a3 = v4;
  SBServicingLogMessage(
    (wchar_t *)L"ShouldSecurebootSkipUpdateOnARM returned: %x\n"
                "ProcessorManufacturer: %ls\n"
                "ProcessorNameString: %ls\n"
                "uefiSecAppVersionRTVariable: %lx",
    (unsigned int)v7,
    v5,
    v6,
    v4);
  if ( v5 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v5);
  }
  if ( v6 )
  {
    v14 = GetProcessHeap();
    HeapFree(v14, 0, v6);
  }
  if ( v7 < 0 )
    SBServicingCoreTelemetryProvider::SBServicingCoreFunctionFailed(L"ShouldSecurebootSkipUpdateOnARM", v3);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18003dea4  mov     [rsp-40h+arg_10], r8
0x18003dea9  mov     [rsp-40h+arg_8], rdx
0x18003deae  mov     [rsp-40h+arg_0], rcx
0x18003deb3  push    rbp
0x18003deb4  push    rbx
0x18003deb5  push    rsi
0x18003deb6  push    rdi
0x18003deb7  push    r12
0x18003deb9  push    r13
0x18003debb  push    r14
0x18003debd  push    r15
0x18003debf  mov     rbp, rsp
0x18003dec2  sub     rsp, 78h
0x18003dec6  xorps   xmm0, xmm0
0x18003dec9  lea     r15, aPassed; "Passed"
0x18003ded0  xor     esi, esi
0x18003ded2  xor     edi, edi
0x18003ded4  mov     [rcx], esi
0x18003ded6  xor     r14d, r14d
0x18003ded9  lea     rcx, [rbp+SystemInfo]; lpSystemInfo
0x18003dedd  mov     [rbp+pszFirst], rdi
0x18003dee1  movups  xmmword ptr [rbp+SystemInfo], xmm0
0x18003dee5  mov     [rbp+var_40], r14
0x18003dee9  movups  xmmword ptr [rbp+SystemInfo.lpMaximumApplicationAddress], xmm0
0x18003deed  mov     [rbp+arg_18], esi
0x18003def0  movups  xmmword ptr [rbp+SystemInfo.dwNumberOfProcessors], xmm0
0x18003def4  call    cs:__imp_GetSystemInfo
0x18003defa  lea     eax, [rdi+0Ch]
0x18003defd  cmp     word ptr [rbp+SystemInfo], ax
0x18003df01  jz      short loc_18003DF10
0x18003df03  xor     ebx, ebx
0x18003df05  cmp     word ptr [rbp+SystemInfo], 5
0x18003df0a  jnz     loc_18003E094
0x18003df10  lea     r8, [rbp+pszFirst]; unsigned __int16 **
0x18003df14  lea     rdx, aVendoridentifi; "VendorIdentifier"
0x18003df1b  lea     rcx, aHardwareDescri_0; "HARDWARE\\DESCRIPTION\\System\\CentralP"...
0x18003df22  call    ?GetHWSystemInformationFromRegistry@@YAJPEBG0PEAPEAG@Z; GetHWSystemInformationFromRegistry(ushort const *,ushort const *,ushort * *)
0x18003df27  mov     rdi, [rbp+pszFirst]
0x18003df2b  mov     ebx, eax
0x18003df2d  test    eax, eax
0x18003df2f  jns     short loc_18003DF3D
0x18003df31  lea     r15, aVendoridentifi_0; "VendorIdentifierRegistryFailed"
0x18003df38  jmp     loc_18003E094
0x18003df3d  mov     rdx, rdi
0x18003df40  lea     rcx, aCheckIfThisIsA; "Check if this is a known bad Qualcomm p"...
0x18003df47  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18003df4c  lea     rdx, aQualcomm; "Qualcomm"
0x18003df53  mov     rcx, rdi; pszFirst
0x18003df56  call    cs:__imp_StrStrIW
0x18003df5c  test    rax, rax
0x18003df5f  jnz     short loc_18003DF75
0x18003df61  mov     rdx, rdi
0x18003df64  lea     rcx, aProceedingWith; "Proceeding with update as manufacturer "...
0x18003df6b  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18003df70  jmp     loc_18003E094
0x18003df75  lea     r8, [rbp+var_40]; unsigned __int16 **
0x18003df79  lea     rdx, aProcessornames_0; "ProcessorNameString"
0x18003df80  lea     rcx, aHardwareDescri_0; "HARDWARE\\DESCRIPTION\\System\\CentralP"...
0x18003df87  call    ?GetHWSystemInformationFromRegistry@@YAJPEBG0PEAPEAG@Z; GetHWSystemInformationFromRegistry(ushort const *,ushort const *,ushort * *)
0x18003df8c  mov     r14, [rbp+var_40]
0x18003df90  mov     ebx, eax
0x18003df92  test    eax, eax
0x18003df94  jns     short loc_18003DFA2
0x18003df96  lea     r15, aProcessornames; "ProcessorNameStringRegistryFailed"
0x18003df9d  jmp     loc_18003E094
0x18003dfa2  mov     r8, r14
0x18003dfa5  lea     rcx, aProcessormanuf; "ProcessorManufacturer: %ls ProcessorNam"...
0x18003dfac  mov     rdx, rdi
0x18003dfaf  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18003dfb4  xor     r12d, r12d
0x18003dfb7  lea     rax, ?g_BadARMProcessorNameVersionMap@@3QBUPROCESSOR_NAME_VERSION_TABLE@@B; PROCESSOR_NAME_VERSION_TABLE const near * const g_BadARMProcessorNameVersionMap
0x18003dfbe  mov     r13, r12
0x18003dfc1  mov     rcx, r14; pszFirst
0x18003dfc4  add     r13, r13
0x18003dfc7  mov     rdx, [rax+r13*8]; pszSrch
0x18003dfcb  call    cs:__imp_StrStrIW
0x18003dfd1  test    rax, rax
0x18003dfd4  jnz     short loc_18003DFEB
0x18003dfd6  inc     r12
0x18003dfd9  lea     rax, ?g_BadARMProcessorNameVersionMap@@3QBUPROCESSOR_NAME_VERSION_TABLE@@B; PROCESSOR_NAME_VERSION_TABLE const near * const g_BadARMProcessorNameVersionMap
0x18003dfe0  cmp     r12, 0Ch
0x18003dfe4  jb      short loc_18003DFBE
0x18003dfe6  jmp     loc_18003E094
0x18003dfeb  lea     rsi, ?g_BadARMProcessorNameVersionMap@@3QBUPROCESSOR_NAME_VERSION_TABLE@@B; PROCESSOR_NAME_VERSION_TABLE const near * const g_BadARMProcessorNameVersionMap
0x18003dff2  mov     r8d, [rsi+r13*8+8]
0x18003dff7  lea     rcx, aMatchedSLx; "Matched %s:%lx"
0x18003dffe  mov     rdx, [rsi+r13*8]
0x18003e002  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18003e007  lea     rcx, [rbp+arg_18]; unsigned int *
0x18003e00b  call    ?GetUefiSecAppVersionRTVariable@@YAJPEAK@Z; GetUefiSecAppVersionRTVariable(ulong *)
0x18003e010  mov     ebx, eax
0x18003e012  test    eax, eax
0x18003e014  jns     short loc_18003E04D
0x18003e016  cmp     eax, 0D0000100h
0x18003e01b  jnz     short loc_18003E041
0x18003e01d  mov     rax, [rbp+arg_0]
0x18003e021  lea     rcx, aSkippingDbUpda_0; "Skipping DB update on Qualcomm device a"...
0x18003e028  mov     dword ptr [rax], 1
0x18003e02e  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18003e033  mov     esi, [rbp+arg_18]
0x18003e036  lea     rcx, aProcessorarchi_0; "ProcessorArchitectureARM64_UefiSecAppVe"...
0x18003e03d  xor     ebx, ebx
0x18003e03f  jmp     short loc_18003E08D
0x18003e041  mov     esi, [rbp+arg_18]
0x18003e044  lea     r15, aGetuefisecappv; "GetUefiSecAppVersionRTVariableFailed"
0x18003e04b  jmp     short loc_18003E094
0x18003e04d  mov     edx, [rsi+r13*8+8]; unsigned int
0x18003e052  mov     esi, [rbp+arg_18]
0x18003e055  mov     ecx, esi; unsigned int
0x18003e057  call    ?IsUefiSecAppVersionRTLower@@YAHII@Z; IsUefiSecAppVersionRTLower(uint,uint)
0x18003e05c  mov     edx, esi
0x18003e05e  test    eax, eax
0x18003e060  jnz     short loc_18003E070
0x18003e062  lea     rcx, aQualcommFixPre; "Qualcomm fix present, proceeding with D"...
0x18003e069  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18003e06e  jmp     short loc_18003E094
0x18003e070  mov     rax, [rbp+arg_0]
0x18003e074  lea     rcx, aSkippingDbUpda; "Skipping DB update on Qualcomm device d"...
0x18003e07b  mov     dword ptr [rax], 1
0x18003e081  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18003e086  lea     rcx, aProcessorarchi; "ProcessorArchitectureARM64_UefiSecAppVe"...
0x18003e08d  mov     rax, [rbp+arg_8]
0x18003e091  mov     [rax], rcx
0x18003e094  mov     rax, [rbp+arg_10]
0x18003e098  lea     rcx, aShouldsecurebo_2; "ShouldSecurebootSkipUpdateOnARM returne"...
0x18003e09f  mov     r9, r14
0x18003e0a2  mov     [rsp+78h+var_58], esi
0x18003e0a6  mov     r8, rdi
0x18003e0a9  mov     edx, ebx
0x18003e0ab  mov     [rax], esi
0x18003e0ad  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18003e0b2  test    rdi, rdi
0x18003e0b5  jz      short loc_18003E0CB
0x18003e0b7  call    cs:__imp_GetProcessHeap
0x18003e0bd  mov     r8, rdi; lpMem
0x18003e0c0  xor     edx, edx; dwFlags
0x18003e0c2  mov     rcx, rax; hHeap
0x18003e0c5  call    cs:__imp_HeapFree
0x18003e0cb  test    r14, r14
0x18003e0ce  jz      short loc_18003E0E4
0x18003e0d0  call    cs:__imp_GetProcessHeap
0x18003e0d6  mov     r8, r14; lpMem
0x18003e0d9  xor     edx, edx; dwFlags
0x18003e0db  mov     rcx, rax; hHeap
0x18003e0de  call    cs:__imp_HeapFree
0x18003e0e4  test    ebx, ebx
0x18003e0e6  jns     short loc_18003E0F7
0x18003e0e8  mov     rdx, r15; unsigned __int16 *
0x18003e0eb  lea     rcx, aShouldsecurebo_1; "ShouldSecurebootSkipUpdateOnARM"
0x18003e0f2  call    ?SBServicingCoreFunctionFailed@SBServicingCoreTelemetryProvider@@SAXPEBG0@Z; SBServicingCoreTelemetryProvider::SBServicingCoreFunctionFailed(ushort const *,ushort const *)
0x18003e0f7  mov     eax, ebx
0x18003e0f9  add     rsp, 78h
0x18003e0fd  pop     r15
0x18003e0ff  pop     r14
0x18003e101  pop     r13
0x18003e103  pop     r12
0x18003e105  pop     rdi
0x18003e106  pop     rsi
0x18003e107  pop     rbx
0x18003e108  pop     rbp
0x18003e109  retn
```
