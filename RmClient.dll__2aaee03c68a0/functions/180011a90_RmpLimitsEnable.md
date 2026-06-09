# RmpLimitsEnable

- ea: `0x180011a90`
- end: `0x180011ef2`
- name: `RmpLimitsEnable`
- size: `1122`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800081b0`

## callees

- `0x180007ce8`
- `0x18000ed44`
- `0x180010fb0`
- `0x180011a90`
- `0x180011f00`
- `0x18001ae8e`
- `0x18001aec0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180011c62`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180011c62`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180011d88`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180011db2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180011d88`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180011db2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011ec3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011ec3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011b60`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011b60`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180011ba8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180011ba8`
- `ntdll!TpReleaseJobNotification` at `0x180011ea4`
- `ntdll!TpReleaseJobNotification` at `0x180011ea4`
- `ntdll!TpAllocJobNotification` at `0x180011d78`
- `ntdll!TpAllocJobNotification` at `0x180011d78`
- `ntdll!NtSetInformationJobObject` at `0x180011ce5`
- `ntdll!NtSetInformationJobObject` at `0x180011d1f`
- `ntdll!NtSetInformationJobObject` at `0x180011d55`
- `ntdll!NtSetInformationJobObject` at `0x180011ce5`
- `ntdll!NtSetInformationJobObject` at `0x180011d1f`
- `ntdll!NtSetInformationJobObject` at `0x180011d55`
- `ntdll!RtlTryAcquireSRWLockExclusive` at `0x180011b1e`
- `ntdll!RtlTryAcquireSRWLockExclusive` at `0x180011b1e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180011e94`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180011e94`
- `ntdll!NtCreateJobObject` at `0x180011c94`
- `ntdll!NtCreateJobObject` at `0x180011c94`
- `ntdll!NtAssignProcessToJobObject` at `0x180011d96`
- `ntdll!NtAssignProcessToJobObject` at `0x180011d96`
- `ntdll!NtClose` at `0x180011eb4`
- `ntdll!NtClose` at `0x180011eb4`
- `ntdll!NtSetInformationProcess` at `0x180011dc9`
- `ntdll!NtSetInformationProcess` at `0x180011dc9`

## string_xrefs

- `0x180011c5b`: `verifier.dll`

## pseudocode

```c
__int64 __fastcall RmpLimitsEnable(LPCWSTR lpValueName)
{
  int v2; // edi
  int v3; // ebx
  LSTATUS v4; // eax
  bool v5; // cc
  unsigned int v6; // r9d
  char Variant; // al
  unsigned __int64 v8; // rbx
  HANDLE CurrentProcess; // rax
  int v10; // ecx
  HANDLE v11; // rax
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  void *JobHandle; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cbData; // [rsp+58h] [rbp-A8h] BYREF
  int v18; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned __int64 v19; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v20; // [rsp+68h] [rbp-98h] BYREF
  __int64 v21; // [rsp+70h] [rbp-90h] BYREF
  int v22; // [rsp+78h] [rbp-88h] BYREF
  int v23; // [rsp+7Ch] [rbp-84h] BYREF
  HKEY hKey; // [rsp+80h] [rbp-80h] BYREF
  int *v25; // [rsp+88h] [rbp-78h] BYREF
  BYTE Data[8]; // [rsp+90h] [rbp-70h] BYREF
  int v27; // [rsp+98h] [rbp-68h]
  __int128 ProcessInformation; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v29; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v30; // [rsp+C0h] [rbp-40h]
  __int128 v31; // [rsp+D0h] [rbp-30h]
  __int64 v32; // [rsp+E0h] [rbp-20h]
  _BYTE JobInformation[16]; // [rsp+F0h] [rbp-10h] BYREF
  int v34; // [rsp+100h] [rbp+0h]
  unsigned __int64 v35; // [rsp+168h] [rbp+68h]

  cbData = 0;
  v20 = 0;
  v19 = 0;
  memset_0(JobInformation, 0, 0x98u);
  v18 = 0;
  hKey = 0;
  v32 = 0;
  v29 = 0;
  *(_QWORD *)Data = 0;
  v30 = 0;
  v27 = 0;
  v31 = 0;
  JobHandle = 0;
  ProcessInformation = 0;
  v21 = 0;
  if ( !(unsigned __int8)RtlTryAcquireSRWLockExclusive(&RmpGlobalLimitsContext) )
  {
    v2 = 0;
LABEL_3:
    v3 = -1073740528;
    goto LABEL_42;
  }
  v2 = 1;
  if ( qword_18002EBF8 )
    goto LABEL_3;
  v4 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows NT\\CurrentVersion\\ResourceManager\\Limits",
         0,
         1u,
         &hKey);
  v3 = v4;
  v5 = v4 <= 0;
  if ( v4 || (cbData = 12, v4 = RegQueryValueExW(hKey, lpValueName, 0, 0, Data, &cbData), v3 = v4, v5 = v4 <= 0, v4) )
  {
    if ( !v5 )
      v3 = (unsigned __int16)v4 | 0xC0070000;
  }
  else
  {
    if ( cbData != 12 || (v27 & 0xFFFFFFFC) != 0 )
      goto LABEL_10;
    if ( *(_DWORD *)&Data[4] )
    {
      if ( *(_DWORD *)Data >= *(_DWORD *)&Data[4] )
        goto LABEL_10;
    }
    else if ( (v27 & 1) != 0 )
    {
LABEL_10:
      v3 = -1073739509;
      goto LABEL_42;
    }
    v3 = RtlULongLongMult(*(unsigned int *)&Data[4], 0x100000u, &v20);
    if ( v3 >= 0 )
    {
      v3 = RtlULongLongMult(*(unsigned int *)Data, v6, &v19);
      if ( v3 >= 0 )
      {
        Variant = wil::details::FeatureImpl<__WilFeatureTraits_Feature_ResourceManagerLimits>::__private_GetVariant(`wil::Feature<__WilFeatureTraits_Feature_ResourceManagerLimits>::GetImpl'::`2'::impl);
        if ( Variant )
        {
          switch ( Variant )
          {
            case 1:
              *(_DWORD *)&Data[4] = 0;
              break;
            case 2:
              *(_DWORD *)Data = 0;
              break;
            case 3:
              *(_QWORD *)Data = 0;
              break;
            default:
              v3 = -1073741464;
              goto LABEL_42;
          }
        }
        if ( (v27 & 2) == 0 && GetModuleHandleW(L"verifier.dll") )
        {
          v3 = -1073740764;
          goto LABEL_42;
        }
        if ( !*(_DWORD *)Data && !*(_DWORD *)&Data[4] )
        {
LABEL_41:
          v3 = 0;
          goto LABEL_42;
        }
        v3 = NtCreateJobObject(&JobHandle, 0x1F003Fu, 0);
        if ( v3 >= 0 )
        {
          memset_0(JobInformation, 0, 0x98u);
          v34 = 6144;
          if ( v20 )
          {
            v35 = v20;
            v34 = 6656;
          }
          v3 = NtSetInformationJobObject(JobHandle, JobObjectExtendedLimitInformation, JobInformation, 0x98u);
          if ( v3 >= 0 )
          {
            v8 = v19;
            if ( !v19 )
              goto LABEL_56;
            v18 = 2048;
            NtSetInformationJobObject(JobHandle, (JOBOBJECTINFOCLASS)16, &v18, 4u);
            v29 = 0;
            v31 = v8;
            v32 = 512;
            v30 = 0;
            NtSetInformationJobObject(JobHandle, MaxJobObjectInfoClass, &v29, 0x38u);
            v3 = TpAllocJobNotification(&v21, JobHandle, RmpLimitsDumpCallback, &RmpGlobalLimitsContext, 0);
            if ( v3 >= 0 )
            {
LABEL_56:
              CurrentProcess = GetCurrentProcess();
              v3 = NtAssignProcessToJobObject(JobHandle, CurrentProcess);
              if ( v3 >= 0 )
              {
                v10 = v27;
                if ( (v27 & 1) != 0 )
                {
                  *(_QWORD *)&ProcessInformation = 1;
                  *((_QWORD *)&ProcessInformation + 1) = 1;
                  v11 = GetCurrentProcess();
                  NtSetInformationProcess(
                    v11,
                    ProcessMemoryAllocationMode|ProcessUserModeIOPL,
                    &ProcessInformation,
                    0x10u);
                  v10 = v27;
                }
                dword_18002EC08 = *(_DWORD *)Data;
                dword_18002EC0C = *(_DWORD *)&Data[4];
                qword_18002EBF8 = (__int64)JobHandle;
                qword_18002EC00 = v21;
                dword_18002EC10 = v10;
                JobHandle = 0;
                v21 = 0;
                goto LABEL_41;
              }
            }
          }
        }
      }
    }
  }
LABEL_42:
  if ( (unsigned int)dword_18002E000 > 4 && tlgKeywordOn((__int64)&dword_18002E000, 5) )
  {
    v23 = v27;
    LODWORD(v19) = *(_DWORD *)Data;
    LODWORD(v20) = *(_DWORD *)&Data[4];
    v22 = v3;
    v25 = (int *)lpValueName;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v12,
      (unsigned __int8 *)&byte_180026B5F,
      v13,
      v14,
      &v25,
      (__int64)&v20,
      (__int64)&v19,
      (__int64)&v23,
      (__int64)&v22);
  }
  if ( v2 )
    RtlReleaseSRWLockExclusive(&RmpGlobalLimitsContext);
  if ( v21 )
    TpReleaseJobNotification();
  if ( JobHandle )
    NtClose(JobHandle);
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180011a90  mov     [rsp-8+arg_8], rbx
0x180011a95  mov     [rsp-8+arg_10], rsi
0x180011a9a  push    rbp
0x180011a9b  push    rdi
0x180011a9c  push    r14
0x180011a9e  lea     rbp, [rsp-0A0h]
0x180011aa6  sub     rsp, 1A0h
0x180011aad  mov     rax, cs:__security_cookie
0x180011ab4  xor     rax, rsp
0x180011ab7  mov     [rbp+0B0h+var_20], rax
0x180011abe  xor     r14d, r14d
0x180011ac1  mov     rsi, rcx
0x180011ac4  lea     rcx, [rbp+0B0h+JobInformation]; void *
0x180011ac8  mov     [rsp+1B0h+cbData], r14d
0x180011acd  xor     edx, edx; Val
0x180011acf  mov     [rsp+1B0h+var_148], r14
0x180011ad4  mov     r8d, 98h; Size
0x180011ada  mov     [rsp+1B0h+var_150], r14
0x180011adf  call    memset_0
0x180011ae4  xorps   xmm0, xmm0
0x180011ae7  mov     [rsp+1B0h+var_154], r14d
0x180011aec  xor     eax, eax
0x180011aee  mov     [rbp+0B0h+hKey], r14
0x180011af2  lea     rcx, ?RmpGlobalLimitsContext@@3U_RM_LIMITS_CONTEXT@@A; _RM_LIMITS_CONTEXT RmpGlobalLimitsContext
0x180011af9  mov     [rbp+0B0h+var_D0], rax
0x180011afd  movups  [rbp+0B0h+var_100], xmm0
0x180011b01  mov     qword ptr [rbp+0B0h+Data], rax
0x180011b05  movups  [rbp+0B0h+var_F0], xmm0
0x180011b09  mov     [rbp+0B0h+var_118], eax
0x180011b0c  movups  [rbp+0B0h+var_E0], xmm0
0x180011b10  mov     [rsp+1B0h+JobHandle], r14
0x180011b15  movups  [rbp+0B0h+ProcessInformation], xmm0
0x180011b19  mov     [rsp+1B0h+var_140], r14
0x180011b1e  call    cs:__imp_RtlTryAcquireSRWLockExclusive
0x180011b24  test    al, al
0x180011b26  jnz     short loc_180011B35
0x180011b28  mov     edi, r14d
0x180011b2b  mov     ebx, 0C0000510h
0x180011b30  jmp     loc_180011E0F
0x180011b35  cmp     cs:qword_18002EBF8, r14
0x180011b3c  mov     edi, 1
0x180011b41  jnz     short loc_180011B2B
0x180011b43  lea     rax, [rbp+0B0h+hKey]
0x180011b47  mov     r9d, edi; samDesired
0x180011b4a  xor     r8d, r8d; ulOptions
0x180011b4d  mov     [rsp+1B0h+phkResult], rax; phkResult
0x180011b52  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows NT\\Curren"...
0x180011b59  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180011b60  call    cs:__imp_RegOpenKeyExW
0x180011b66  mov     ebx, eax
0x180011b68  test    eax, eax
0x180011b6a  jz      short loc_180011B80
0x180011b6c  jle     loc_180011E0F
0x180011b72  movzx   ebx, ax
0x180011b75  or      ebx, 0C0070000h
0x180011b7b  jmp     loc_180011E0F
0x180011b80  mov     rcx, [rbp+0B0h+hKey]; hKey
0x180011b84  lea     rax, [rsp+1B0h+cbData]
0x180011b89  mov     [rsp+1B0h+lpcbData], rax; lpcbData
0x180011b8e  xor     r9d, r9d; lpType
0x180011b91  lea     rax, [rbp+0B0h+Data]
0x180011b95  mov     [rsp+1B0h+cbData], 0Ch
0x180011b9d  xor     r8d, r8d; lpReserved
0x180011ba0  mov     [rsp+1B0h+phkResult], rax; lpData
0x180011ba5  mov     rdx, rsi; lpValueName
0x180011ba8  call    cs:__imp_RegQueryValueExW
0x180011bae  mov     ebx, eax
0x180011bb0  test    eax, eax
0x180011bb2  jnz     short loc_180011B6C
0x180011bb4  cmp     [rsp+1B0h+cbData], 0Ch
0x180011bb9  jz      short loc_180011BC5
0x180011bbb  mov     ebx, 0C000090Bh
0x180011bc0  jmp     loc_180011E0F
0x180011bc5  test    [rbp+0B0h+var_118], 0FFFFFFFCh
0x180011bcc  jnz     short loc_180011BBB
0x180011bce  mov     eax, dword ptr [rbp+0B0h+Data+4]
0x180011bd1  test    eax, eax
0x180011bd3  jz      short loc_180011BDC
0x180011bd5  cmp     dword ptr [rbp+0B0h+Data], eax
0x180011bd8  jb      short loc_180011BE2
0x180011bda  jmp     short loc_180011BBB
0x180011bdc  test    byte ptr [rbp+0B0h+var_118], dil
0x180011be0  jnz     short loc_180011BBB
0x180011be2  mov     r9d, 100000h
0x180011be8  lea     r8, [rsp+1B0h+var_148]; unsigned __int64 *
0x180011bed  mov     edx, r9d; unsigned __int64
0x180011bf0  mov     rcx, rax; unsigned __int64
0x180011bf3  call    ?RtlULongLongMult@@YAJ_K0PEA_K@Z; RtlULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180011bf8  mov     ebx, eax
0x180011bfa  test    eax, eax
0x180011bfc  js      loc_180011E0F
0x180011c02  mov     ecx, dword ptr [rbp+0B0h+Data]; unsigned __int64
0x180011c05  lea     r8, [rsp+1B0h+var_150]; unsigned __int64 *
0x180011c0a  mov     edx, r9d; unsigned __int64
0x180011c0d  call    ?RtlULongLongMult@@YAJ_K0PEA_K@Z; RtlULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180011c12  mov     ebx, eax
0x180011c14  test    eax, eax
0x180011c16  js      loc_180011E0F
0x180011c1c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ResourceManagerLimits@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ResourceManagerLimits@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ResourceManagerLimits> `wil::Feature<__WilFeatureTraits_Feature_ResourceManagerLimits>::GetImpl(void)'::`2'::impl
0x180011c23  call    ?__private_GetVariant@?$FeatureImpl@U__WilFeatureTraits_Feature_ResourceManagerLimits@@@details@wil@@QEAA?AW4Variant_ResourceManagerLimits@@W4VariantReportingKind@3@_N@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ResourceManagerLimits>::__private_GetVariant(wil::VariantReportingKind,bool)
0x180011c28  movzx   ecx, al
0x180011c2b  test    al, al
0x180011c2d  jz      short loc_180011C55
0x180011c2f  sub     ecx, edi
0x180011c31  jz      short loc_180011C51
0x180011c33  sub     ecx, edi
0x180011c35  jz      short loc_180011C4B
0x180011c37  cmp     ecx, edi
0x180011c39  jz      short loc_180011C45
0x180011c3b  mov     ebx, 0C0000168h
0x180011c40  jmp     loc_180011E0F
0x180011c45  mov     qword ptr [rbp+0B0h+Data], r14
0x180011c49  jmp     short loc_180011C55
0x180011c4b  mov     dword ptr [rbp+0B0h+Data], r14d
0x180011c4f  jmp     short loc_180011C55
0x180011c51  mov     dword ptr [rbp+0B0h+Data+4], r14d
0x180011c55  test    byte ptr [rbp+0B0h+var_118], 2
0x180011c59  jnz     short loc_180011C77
0x180011c5b  lea     rcx, aVerifierDll; "verifier.dll"
0x180011c62  call    cs:__imp_GetModuleHandleW
0x180011c68  test    rax, rax
0x180011c6b  jz      short loc_180011C77
0x180011c6d  mov     ebx, 0C0000424h
0x180011c72  jmp     loc_180011E0F
0x180011c77  cmp     dword ptr [rbp+0B0h+Data], r14d
0x180011c7b  jnz     short loc_180011C87
0x180011c7d  cmp     dword ptr [rbp+0B0h+Data+4], r14d
0x180011c81  jz      loc_180011E0C
0x180011c87  xor     r8d, r8d; ObjectAttributes
0x180011c8a  lea     rcx, [rsp+1B0h+JobHandle]; JobHandle
0x180011c8f  mov     edx, 1F003Fh; DesiredAccess
0x180011c94  call    cs:__imp_NtCreateJobObject
0x180011c9a  mov     ebx, eax
0x180011c9c  test    eax, eax
0x180011c9e  js      loc_180011E0F
0x180011ca4  xor     edx, edx; Val
0x180011ca6  lea     rcx, [rbp+0B0h+JobInformation]; void *
0x180011caa  mov     r8d, 98h; Size
0x180011cb0  call    memset_0
0x180011cb5  mov     rax, [rsp+1B0h+var_148]
0x180011cba  mov     [rbp+0B0h+var_B0], 1800h
0x180011cc1  test    rax, rax
0x180011cc4  jz      short loc_180011CD1
0x180011cc6  mov     [rbp+0B0h+var_48], rax
0x180011cca  mov     [rbp+0B0h+var_B0], 1A00h
0x180011cd1  mov     rcx, [rsp+1B0h+JobHandle]; JobHandle
0x180011cd6  lea     r8, [rbp+0B0h+JobInformation]; JobInformation
0x180011cda  mov     r9d, 98h; JobInformationLength
0x180011ce0  mov     edx, 9; JobInformationClass
0x180011ce5  call    cs:__imp_NtSetInformationJobObject
0x180011ceb  mov     ebx, eax
0x180011ced  test    eax, eax
0x180011cef  js      loc_180011E0F
0x180011cf5  mov     rbx, [rsp+1B0h+var_150]
0x180011cfa  test    rbx, rbx
0x180011cfd  jz      loc_180011D88
0x180011d03  mov     rcx, [rsp+1B0h+JobHandle]; JobHandle
0x180011d08  lea     r8, [rsp+1B0h+var_154]; JobInformation
0x180011d0d  mov     r9d, 4; JobInformationLength
0x180011d13  mov     [rsp+1B0h+var_154], 800h
0x180011d1b  lea     edx, [r9+0Ch]; JobInformationClass
0x180011d1f  call    cs:__imp_NtSetInformationJobObject
0x180011d25  mov     rcx, [rsp+1B0h+JobHandle]; JobHandle
0x180011d2a  lea     r8, [rbp+0B0h+var_100]; JobInformation
0x180011d2e  xor     eax, eax
0x180011d30  xorps   xmm0, xmm0
0x180011d33  movups  [rbp+0B0h+var_E0], xmm0
0x180011d37  mov     [rbp+0B0h+var_D0], rax
0x180011d3b  movups  [rbp+0B0h+var_100], xmm0
0x180011d3f  lea     r9d, [rax+38h]; JobInformationLength
0x180011d43  mov     qword ptr [rbp+0B0h+var_E0], rbx
0x180011d47  lea     edx, [rax+0Ch]; JobInformationClass
0x180011d4a  mov     dword ptr [rbp+0B0h+var_D0], 200h
0x180011d51  movups  [rbp+0B0h+var_F0], xmm0
0x180011d55  call    cs:__imp_NtSetInformationJobObject
0x180011d5b  mov     rdx, [rsp+1B0h+JobHandle]
0x180011d60  lea     r9, ?RmpGlobalLimitsContext@@3U_RM_LIMITS_CONTEXT@@A; _RM_LIMITS_CONTEXT RmpGlobalLimitsContext
0x180011d67  lea     r8, RmpLimitsDumpCallback
0x180011d6e  mov     [rsp+1B0h+phkResult], r14
0x180011d73  lea     rcx, [rsp+1B0h+var_140]
0x180011d78  call    cs:__imp_TpAllocJobNotification
0x180011d7e  mov     ebx, eax
0x180011d80  test    eax, eax
0x180011d82  js      loc_180011E0F
0x180011d88  call    cs:__imp_GetCurrentProcess
0x180011d8e  mov     rcx, [rsp+1B0h+JobHandle]; JobHandle
0x180011d93  mov     rdx, rax; ProcessHandle
0x180011d96  call    cs:__imp_NtAssignProcessToJobObject
0x180011d9c  mov     ebx, eax
0x180011d9e  test    eax, eax
0x180011da0  js      short loc_180011E0F
0x180011da2  mov     ecx, [rbp+0B0h+var_118]
0x180011da5  test    dil, cl
0x180011da8  jz      short loc_180011DD2
0x180011daa  mov     qword ptr [rbp+0B0h+ProcessInformation], rdi
0x180011dae  mov     qword ptr [rbp+0B0h+ProcessInformation+8], rdi
0x180011db2  call    cs:__imp_GetCurrentProcess
0x180011db8  mov     r9d, 10h; ProcessInformationLength
0x180011dbe  lea     r8, [rbp+0B0h+ProcessInformation]; ProcessInformation
0x180011dc2  mov     rcx, rax; ProcessHandle
0x180011dc5  lea     edx, [r9+2Eh]; ProcessInformationClass
0x180011dc9  call    cs:__imp_NtSetInformationProcess
0x180011dcf  mov     ecx, [rbp+0B0h+var_118]
0x180011dd2  mov     eax, dword ptr [rbp+0B0h+Data]
0x180011dd5  mov     cs:dword_18002EC08, eax
0x180011ddb  mov     eax, dword ptr [rbp+0B0h+Data+4]
0x180011dde  mov     cs:dword_18002EC0C, eax
0x180011de4  mov     rax, [rsp+1B0h+JobHandle]
0x180011de9  mov     cs:qword_18002EBF8, rax
0x180011df0  mov     rax, [rsp+1B0h+var_140]
0x180011df5  mov     cs:qword_18002EC00, rax
0x180011dfc  mov     cs:dword_18002EC10, ecx
0x180011e02  mov     [rsp+1B0h+JobHandle], r14
0x180011e07  mov     [rsp+1B0h+var_140], r14
0x180011e0c  mov     ebx, r14d
0x180011e0f  mov     eax, cs:dword_18002E000
0x180011e15  cmp     eax, 4
0x180011e18  jbe     short loc_180011E89
0x180011e1a  mov     edx, 5
0x180011e1f  lea     rcx, dword_18002E000
0x180011e26  call    _tlgKeywordOn
0x180011e2b  test    al, al
0x180011e2d  jz      short loc_180011E89
0x180011e2f  mov     eax, [rbp+0B0h+var_118]
0x180011e32  lea     rdx, byte_180026B5F
0x180011e39  mov     [rsp+1B0h+var_134], eax
0x180011e3d  mov     eax, dword ptr [rbp+0B0h+Data]
0x180011e40  mov     dword ptr [rsp+1B0h+var_150], eax
0x180011e44  mov     eax, dword ptr [rbp+0B0h+Data+4]
0x180011e47  mov     dword ptr [rsp+1B0h+var_148], eax
0x180011e4b  lea     rax, [rsp+1B0h+var_138]
0x180011e50  mov     [rsp+1B0h+var_170], rax
0x180011e55  lea     rax, [rsp+1B0h+var_134]
0x180011e5a  mov     [rsp+1B0h+var_178], rax
0x180011e5f  lea     rax, [rsp+1B0h+var_150]
0x180011e64  mov     [rsp+1B0h+var_180], rax
0x180011e69  lea     rax, [rsp+1B0h+var_148]
0x180011e6e  mov     [rsp+1B0h+lpcbData], rax
0x180011e73  lea     rax, [rbp+0B0h+var_128]
0x180011e77  mov     [rsp+1B0h+phkResult], rax
0x180011e7c  mov     [rsp+1B0h+var_138], ebx
0x180011e80  mov     [rbp+0B0h+var_128], rsi
0x180011e84  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180011e89  test    edi, edi
0x180011e8b  jz      short loc_180011E9A
0x180011e8d  lea     rcx, ?RmpGlobalLimitsContext@@3U_RM_LIMITS_CONTEXT@@A; _RM_LIMITS_CONTEXT RmpGlobalLimitsContext
0x180011e94  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180011e9a  mov     rcx, [rsp+1B0h+var_140]
0x180011e9f  test    rcx, rcx
0x180011ea2  jz      short loc_180011EAA
0x180011ea4  call    cs:__imp_TpReleaseJobNotification
0x180011eaa  mov     rcx, [rsp+1B0h+JobHandle]; Handle
0x180011eaf  test    rcx, rcx
0x180011eb2  jz      short loc_180011EBA
0x180011eb4  call    cs:__imp_NtClose
0x180011eba  mov     rcx, [rbp+0B0h+hKey]; hKey
0x180011ebe  test    rcx, rcx
0x180011ec1  jz      short loc_180011EC9
0x180011ec3  call    cs:__imp_RegCloseKey
0x180011ec9  mov     eax, ebx
0x180011ecb  mov     rcx, [rbp+0B0h+var_20]
0x180011ed2  xor     rcx, rsp; StackCookie
0x180011ed5  call    __security_check_cookie
0x180011eda  lea     r11, [rsp+1B0h+var_10]
0x180011ee2  mov     rbx, [r11+28h]
0x180011ee6  mov     rsi, [r11+30h]
0x180011eea  mov     rsp, r11
0x180011eed  pop     r14
0x180011eef  pop     rdi
0x180011ef0  pop     rbp
0x180011ef1  retn
```
