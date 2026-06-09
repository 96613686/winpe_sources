# DetectDomainJoinStatus(int *)

- ea: `0x18000ba68`
- end: `0x18000bef8`
- name: `?DetectDomainJoinStatus@@YAJPEAH@Z`
- size: `1168`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000bf00`

## callees

- `0x180009e04`
- `0x18000ba68`
- `0x180050300`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000be2b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000be2b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000bae3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000bae3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bb03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bb60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bbfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bc7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bda6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bdbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bb03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bb60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bbfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bc7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bda6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bdbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be4b`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000bac7`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000bac7`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18000bbf0`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18000bbf0`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18000bec1`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18000bec1`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x18000bc72`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x18000bc72`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18000bed0`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18000bed0`
- `WDSCORE!CurrentIP` at `0x18000bb0b`
- `WDSCORE!CurrentIP` at `0x18000bb68`
- `WDSCORE!CurrentIP` at `0x18000bc05`
- `WDSCORE!CurrentIP` at `0x18000bc87`
- `WDSCORE!CurrentIP` at `0x18000bd1a`
- `WDSCORE!CurrentIP` at `0x18000bdc3`
- `WDSCORE!CurrentIP` at `0x18000be53`
- `WDSCORE!CurrentIP` at `0x18000bb0b`
- `WDSCORE!CurrentIP` at `0x18000bb68`
- `WDSCORE!CurrentIP` at `0x18000bc05`
- `WDSCORE!CurrentIP` at `0x18000bc87`
- `WDSCORE!CurrentIP` at `0x18000bd1a`
- `WDSCORE!CurrentIP` at `0x18000bdc3`
- `WDSCORE!CurrentIP` at `0x18000be53`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000bbda`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000bc5d`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000bcdf`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000bd85`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000be22`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000beb2`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000bbda`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000bc5d`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000bcdf`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000bd85`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000be22`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000beb2`

## string_xrefs

- `0x18000bb39`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x18000bba9`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x18000bdf1`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x18000be81`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x18000bac0`: `dsreg.dll`
- `0x18000bdcc`: `DetectDomainJoinStatus: Failed to load DsrIsDeviceJoined from dsreg.dll. Error: 0x%08X`
- `0x18000be5c`: `DetectDomainJoinStatus: Failed to load dsreg.dll. Error: 0x%08X`
- `0x18000bc0e`: `DetectDomainJoinStatus: Failed to open LSA policy. NTSTATUS: 0x%08X`

## pseudocode

```c
__int64 __fastcall DetectDomainJoinStatus(int *a1)
{
  HMODULE LibraryW; // rax
  HMODULE v3; // r13
  FARPROC ProcAddress; // rax
  int v5; // esi
  DWORD v6; // edi
  __int64 v7; // rbx
  struct tagLOG_PARTIAL_MSG *v8; // rax
  DWORD v9; // edi
  __int64 v10; // rax
  const wchar_t *v11; // r8
  __int64 v12; // rbx
  struct tagLOG_PARTIAL_MSG *v13; // rax
  NTSTATUS v14; // r12d
  DWORD v15; // edi
  __int64 v16; // rbx
  struct tagLOG_PARTIAL_MSG *v17; // rax
  DWORD v18; // edi
  __int64 v19; // rbx
  struct tagLOG_PARTIAL_MSG *v20; // rax
  int v21; // r12d
  DWORD v22; // edi
  __int64 v23; // rax
  const wchar_t *v24; // r8
  __int64 v25; // rbx
  struct tagLOG_PARTIAL_MSG *v26; // rax
  signed int v27; // eax
  DWORD v28; // edi
  __int64 v29; // rbx
  struct tagLOG_PARTIAL_MSG *v30; // rax
  signed int LastError; // eax
  DWORD v32; // edi
  __int64 v33; // rbx
  struct tagLOG_PARTIAL_MSG *v34; // rax
  int v35; // [rsp+60h] [rbp-49h]
  PVOID Buffer; // [rsp+70h] [rbp-39h] BYREF
  PVOID PolicyHandle; // [rsp+78h] [rbp-31h] BYREF
  int v39; // [rsp+80h] [rbp-29h] BYREF
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-21h] BYREF

  v39 = 0;
  PolicyHandle = 0;
  Buffer = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  if ( !a1 )
    return 2147942487LL;
  LibraryW = LoadLibraryW(L"dsreg.dll");
  v3 = LibraryW;
  if ( !LibraryW )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    v32 = GetLastError();
    v33 = CurrentIP();
    v34 = ConstructPartialMsgW(0x2000000, "DetectDomainJoinStatus: Failed to load dsreg.dll. Error: 0x%08X", v5);
    WdsSetupLogMessageW(
      v34,
      0,
      L"D",
      0,
      1143,
      L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
      L"DetectDomainJoinStatus",
      v33,
      v32,
      0,
      0);
    goto LABEL_29;
  }
  ProcAddress = GetProcAddress(LibraryW, "DsrIsDeviceJoined");
  if ( !ProcAddress )
  {
    v27 = GetLastError();
    v5 = v27;
    if ( v27 > 0 )
      v5 = (unsigned __int16)v27 | 0x80070000;
    v28 = GetLastError();
    v29 = CurrentIP();
    v30 = ConstructPartialMsgW(
            0x2000000,
            "DetectDomainJoinStatus: Failed to load DsrIsDeviceJoined from dsreg.dll. Error: 0x%08X",
            v5);
    WdsSetupLogMessageW(
      v30,
      0,
      L"D",
      0,
      1136,
      L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
      L"DetectDomainJoinStatus",
      v29,
      v28,
      0,
      0);
    goto LABEL_25;
  }
  v5 = ((__int64 (__fastcall *)(int *, _QWORD))ProcAddress)(&v39, 0);
  if ( v5 >= 0 )
  {
    v9 = GetLastError();
    v10 = CurrentIP();
    v11 = L"true";
    v12 = v10;
    if ( !v39 )
      v11 = L"false";
    v13 = ConstructPartialMsgW(0x4000000, "DetectDomainJoinStatus: Entra joined status: %s", v11);
    WdsSetupLogMessageW(
      v13,
      0,
      L"D",
      0,
      1131,
      L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
      L"DetectDomainJoinStatus",
      v12,
      v9,
      0,
      0);
    v14 = LsaOpenPolicy(0, &ObjectAttributes, 0x2000000u, &PolicyHandle);
    if ( v14 >= 0 )
    {
      v14 = LsaQueryInformationPolicy(PolicyHandle, PolicyPrimaryDomainInformation, &Buffer);
      if ( v14 >= 0 )
      {
        v21 = 1;
        if ( !Buffer || (v35 = 1, !*((_QWORD *)Buffer + 2)) )
          v35 = 0;
        v22 = GetLastError();
        v23 = CurrentIP();
        v24 = L"true";
        v25 = v23;
        if ( !v35 )
          v24 = L"false";
        v26 = ConstructPartialMsgW(0x4000000, "DetectDomainJoinStatus: AD joined status: %s", (const char *)v24);
        WdsSetupLogMessageW(
          v26,
          0,
          L"D",
          0,
          1176,
          L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
          L"DetectDomainJoinStatus",
          v25,
          v22,
          0,
          0);
        if ( !v39 && !v35 )
          v21 = 0;
        *a1 = v21;
        goto LABEL_25;
      }
    }
    else
    {
      v15 = GetLastError();
      v16 = CurrentIP();
      v17 = ConstructPartialMsgW(0x2000000, "DetectDomainJoinStatus: Failed to open LSA policy. NTSTATUS: 0x%08X", v14);
      WdsSetupLogMessageW(
        v17,
        0,
        L"D",
        0,
        1157,
        L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
        L"DetectDomainJoinStatus",
        v16,
        v15,
        0,
        0);
    }
    v18 = GetLastError();
    v19 = CurrentIP();
    v20 = ConstructPartialMsgW(
            0x2000000,
            "DetectDomainJoinStatus: Failed to query LSA policy information. NTSTATUS: 0x%08X",
            v14);
    WdsSetupLogMessageW(
      v20,
      0,
      L"D",
      0,
      1170,
      L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
      L"DetectDomainJoinStatus",
      v19,
      v18,
      0,
      0);
    v5 = v14 | 0x10000000;
  }
  else
  {
    v6 = GetLastError();
    v7 = CurrentIP();
    v8 = ConstructPartialMsgW(50331648, "DsrIsDeviceJoined Failed. Error: 0x%08x", v5);
    WdsSetupLogMessageW(
      v8,
      0,
      L"D",
      0,
      1128,
      L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
      L"DetectDomainJoinStatus",
      v7,
      v6,
      0,
      0);
  }
LABEL_25:
  FreeLibrary(v3);
LABEL_29:
  if ( Buffer )
    LsaFreeMemory(Buffer);
  if ( PolicyHandle )
    LsaClose(PolicyHandle);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000ba68  push    rbp
0x18000ba6a  push    rbx
0x18000ba6b  push    rsi
0x18000ba6c  push    rdi
0x18000ba6d  push    r12
0x18000ba6f  push    r13
0x18000ba71  push    r14
0x18000ba73  push    r15
0x18000ba75  lea     rbp, [rsp-1Fh]
0x18000ba7a  sub     rsp, 0C8h
0x18000ba81  mov     rax, cs:__security_cookie
0x18000ba88  xor     rax, rsp
0x18000ba8b  mov     [rbp+57h+var_48], rax
0x18000ba8f  xor     r12d, r12d
0x18000ba92  mov     [rbp+57h+var_98], rcx
0x18000ba96  mov     [rbp+57h+var_80], r12d
0x18000ba9a  xorps   xmm0, xmm0
0x18000ba9d  mov     [rbp+57h+PolicyHandle], r12
0x18000baa1  mov     [rbp+57h+Buffer], r12
0x18000baa5  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18000baa9  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18000baad  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000bab1  test    rcx, rcx
0x18000bab4  jnz     short loc_18000BAC0
0x18000bab6  mov     eax, 80070057h
0x18000babb  jmp     loc_18000BED8
0x18000bac0  lea     rcx, LibFileName; "dsreg.dll"
0x18000bac7  call    cs:__imp_LoadLibraryW
0x18000bacd  mov     r13, rax
0x18000bad0  test    rax, rax
0x18000bad3  jz      loc_18000BE36
0x18000bad9  lea     rdx, aDsrisdevicejoi_0; "DsrIsDeviceJoined"
0x18000bae0  mov     rcx, rax; hModule
0x18000bae3  call    cs:__imp_GetProcAddress
0x18000bae9  test    rax, rax
0x18000baec  jz      loc_18000BDA6
0x18000baf2  xor     edx, edx
0x18000baf4  lea     rcx, [rbp+57h+var_80]
0x18000baf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bafd  mov     esi, eax
0x18000baff  test    eax, eax
0x18000bb01  jns     short loc_18000BB60
0x18000bb03  call    cs:__imp_GetLastError
0x18000bb09  mov     edi, eax
0x18000bb0b  call    cs:__imp_CurrentIP
0x18000bb11  mov     r8d, esi
0x18000bb14  lea     rdx, aDsrisdevicejoi; "DsrIsDeviceJoined Failed. Error: 0x%08x"
0x18000bb1b  mov     ecx, 3000000h; unsigned int
0x18000bb20  mov     rbx, rax
0x18000bb23  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000bb28  mov     [rsp+100h+var_B0], r12d
0x18000bb2d  lea     r14, aDetectdomainjo_2; "DetectDomainJoinStatus"
0x18000bb34  mov     [rsp+100h+var_B8], r12
0x18000bb39  lea     r15, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x18000bb40  mov     [rsp+100h+var_C0], edi
0x18000bb44  mov     [rsp+100h+var_C8], rbx
0x18000bb49  mov     [rsp+100h+var_D0], r14
0x18000bb4e  mov     [rsp+100h+var_D8], r15
0x18000bb53  mov     [rsp+100h+var_E0], 468h
0x18000bb5b  jmp     loc_18000BE13
0x18000bb60  call    cs:__imp_GetLastError
0x18000bb66  mov     edi, eax
0x18000bb68  call    cs:__imp_CurrentIP
0x18000bb6e  cmp     [rbp+57h+var_80], r12d
0x18000bb72  lea     r8, aTrue; "true"
0x18000bb79  mov     rbx, rax
0x18000bb7c  lea     rdx, aDetectdomainjo; "DetectDomainJoinStatus: Entra joined st"...
0x18000bb83  lea     rax, aFalse; "false"
0x18000bb8a  mov     ecx, 4000000h; unsigned int
0x18000bb8f  cmovz   r8, rax
0x18000bb93  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000bb98  mov     [rsp+100h+var_B0], r12d
0x18000bb9d  lea     r14, aDetectdomainjo_2; "DetectDomainJoinStatus"
0x18000bba4  mov     [rsp+100h+var_B8], r12
0x18000bba9  lea     r15, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x18000bbb0  mov     [rsp+100h+var_C0], edi
0x18000bbb4  lea     r8, aD; "D"
0x18000bbbb  mov     [rsp+100h+var_C8], rbx
0x18000bbc0  xor     r9d, r9d
0x18000bbc3  mov     [rsp+100h+var_D0], r14
0x18000bbc8  xor     edx, edx
0x18000bbca  mov     [rsp+100h+var_D8], r15
0x18000bbcf  mov     rcx, rax
0x18000bbd2  mov     [rsp+100h+var_E0], 46Bh
0x18000bbda  call    cs:__imp_WdsSetupLogMessageW
0x18000bbe0  lea     r9, [rbp+57h+PolicyHandle]; PolicyHandle
0x18000bbe4  mov     r8d, 2000000h; DesiredAccess
0x18000bbea  lea     rdx, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18000bbee  xor     ecx, ecx; SystemName
0x18000bbf0  call    cs:__imp_LsaOpenPolicy
0x18000bbf6  mov     r12d, eax
0x18000bbf9  test    eax, eax
0x18000bbfb  jns     short loc_18000BC65
0x18000bbfd  call    cs:__imp_GetLastError
0x18000bc03  mov     edi, eax
0x18000bc05  call    cs:__imp_CurrentIP
0x18000bc0b  mov     r8d, r12d
0x18000bc0e  lea     rdx, aDetectdomainjo_5; "DetectDomainJoinStatus: Failed to open "...
0x18000bc15  mov     ecx, 2000000h; unsigned int
0x18000bc1a  mov     rbx, rax
0x18000bc1d  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000bc22  mov     [rsp+100h+var_B0], 0
0x18000bc2a  lea     r8, aD; "D"
0x18000bc31  mov     [rsp+100h+var_B8], 0
0x18000bc3a  xor     r9d, r9d
0x18000bc3d  mov     [rsp+100h+var_C0], edi
0x18000bc41  xor     edx, edx
0x18000bc43  mov     [rsp+100h+var_C8], rbx
0x18000bc48  mov     rcx, rax
0x18000bc4b  mov     [rsp+100h+var_D0], r14
0x18000bc50  mov     [rsp+100h+var_D8], r15
0x18000bc55  mov     [rsp+100h+var_E0], 485h
0x18000bc5d  call    cs:__imp_WdsSetupLogMessageW
0x18000bc63  jmp     short loc_18000BC7F
0x18000bc65  mov     rcx, [rbp+57h+PolicyHandle]; PolicyHandle
0x18000bc69  lea     r8, [rbp+57h+Buffer]; Buffer
0x18000bc6d  mov     edx, 3; InformationClass
0x18000bc72  call    cs:__imp_LsaQueryInformationPolicy
0x18000bc78  mov     r12d, eax
0x18000bc7b  test    eax, eax
0x18000bc7d  jns     short loc_18000BCF1
0x18000bc7f  call    cs:__imp_GetLastError
0x18000bc85  mov     edi, eax
0x18000bc87  call    cs:__imp_CurrentIP
0x18000bc8d  mov     r8d, r12d
0x18000bc90  lea     rdx, aDetectdomainjo_4; "DetectDomainJoinStatus: Failed to query"...
0x18000bc97  mov     ecx, 2000000h; unsigned int
0x18000bc9c  mov     rbx, rax
0x18000bc9f  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000bca4  mov     [rsp+100h+var_B0], 0
0x18000bcac  lea     r8, aD; "D"
0x18000bcb3  mov     [rsp+100h+var_B8], 0
0x18000bcbc  xor     r9d, r9d
0x18000bcbf  mov     [rsp+100h+var_C0], edi
0x18000bcc3  xor     edx, edx
0x18000bcc5  mov     [rsp+100h+var_C8], rbx
0x18000bcca  mov     rcx, rax
0x18000bccd  mov     [rsp+100h+var_D0], r14
0x18000bcd2  mov     [rsp+100h+var_D8], r15
0x18000bcd7  mov     [rsp+100h+var_E0], 492h
0x18000bcdf  call    cs:__imp_WdsSetupLogMessageW
0x18000bce5  mov     esi, r12d
0x18000bce8  bts     esi, 1Ch
0x18000bcec  jmp     loc_18000BE28
0x18000bcf1  mov     rax, [rbp+57h+Buffer]
0x18000bcf5  mov     r12d, 1
0x18000bcfb  test    rax, rax
0x18000bcfe  jz      short loc_18000BD0B
0x18000bd00  cmp     qword ptr [rax+10h], 0
0x18000bd05  mov     [rbp+57h+var_A0], r12d
0x18000bd09  jnz     short loc_18000BD12
0x18000bd0b  mov     [rbp+57h+var_A0], 0
0x18000bd12  call    cs:__imp_GetLastError
0x18000bd18  mov     edi, eax
0x18000bd1a  call    cs:__imp_CurrentIP
0x18000bd20  cmp     [rbp+57h+var_A0], 0
0x18000bd24  lea     rcx, aFalse; "false"
0x18000bd2b  lea     r8, aTrue; "true"
0x18000bd32  mov     rbx, rax
0x18000bd35  cmovz   r8, rcx
0x18000bd39  lea     rdx, aDetectdomainjo_3; "DetectDomainJoinStatus: AD joined statu"...
0x18000bd40  mov     ecx, 4000000h; unsigned int
0x18000bd45  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000bd4a  mov     [rsp+100h+var_B0], 0
0x18000bd52  lea     r8, aD; "D"
0x18000bd59  mov     [rsp+100h+var_B8], 0
0x18000bd62  xor     r9d, r9d
0x18000bd65  mov     [rsp+100h+var_C0], edi
0x18000bd69  xor     edx, edx
0x18000bd6b  mov     [rsp+100h+var_C8], rbx
0x18000bd70  mov     rcx, rax
0x18000bd73  mov     [rsp+100h+var_D0], r14
0x18000bd78  mov     [rsp+100h+var_D8], r15
0x18000bd7d  mov     [rsp+100h+var_E0], 498h
0x18000bd85  call    cs:__imp_WdsSetupLogMessageW
0x18000bd8b  cmp     [rbp+57h+var_80], 0
0x18000bd8f  jnz     short loc_18000BD9A
0x18000bd91  cmp     [rbp+57h+var_A0], 0
0x18000bd95  jnz     short loc_18000BD9A
0x18000bd97  xor     r12d, r12d
0x18000bd9a  mov     rax, [rbp+57h+var_98]
0x18000bd9e  mov     [rax], r12d
0x18000bda1  jmp     loc_18000BE28
0x18000bda6  call    cs:__imp_GetLastError
0x18000bdac  mov     esi, eax
0x18000bdae  test    eax, eax
0x18000bdb0  jle     short loc_18000BDBB
0x18000bdb2  movzx   esi, ax
0x18000bdb5  or      esi, 80070000h
0x18000bdbb  call    cs:__imp_GetLastError
0x18000bdc1  mov     edi, eax
0x18000bdc3  call    cs:__imp_CurrentIP
0x18000bdc9  mov     r8d, esi
0x18000bdcc  lea     rdx, aDetectdomainjo_1; "DetectDomainJoinStatus: Failed to load "...
0x18000bdd3  mov     ecx, 2000000h; unsigned int
0x18000bdd8  mov     rbx, rax
0x18000bddb  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000bde0  mov     [rsp+100h+var_B0], r12d
0x18000bde5  lea     r14, aDetectdomainjo_2; "DetectDomainJoinStatus"
0x18000bdec  mov     [rsp+100h+var_B8], r12
0x18000bdf1  lea     r15, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x18000bdf8  mov     [rsp+100h+var_C0], edi
0x18000bdfc  mov     [rsp+100h+var_C8], rbx
0x18000be01  mov     [rsp+100h+var_D0], r14
0x18000be06  mov     [rsp+100h+var_D8], r15
0x18000be0b  mov     [rsp+100h+var_E0], 470h
0x18000be13  xor     r9d, r9d
0x18000be16  lea     r8, aD; "D"
0x18000be1d  xor     edx, edx
0x18000be1f  mov     rcx, rax
0x18000be22  call    cs:__imp_WdsSetupLogMessageW
0x18000be28  mov     rcx, r13; hLibModule
0x18000be2b  call    cs:__imp_FreeLibrary
0x18000be31  jmp     loc_18000BEB8
0x18000be36  call    cs:__imp_GetLastError
0x18000be3c  mov     esi, eax
0x18000be3e  test    eax, eax
0x18000be40  jle     short loc_18000BE4B
0x18000be42  movzx   esi, ax
0x18000be45  or      esi, 80070000h
0x18000be4b  call    cs:__imp_GetLastError
0x18000be51  mov     edi, eax
0x18000be53  call    cs:__imp_CurrentIP
0x18000be59  mov     r8d, esi
0x18000be5c  lea     rdx, aDetectdomainjo_0; "DetectDomainJoinStatus: Failed to load "...
0x18000be63  mov     ecx, 2000000h; unsigned int
0x18000be68  mov     rbx, rax
0x18000be6b  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000be70  mov     [rsp+100h+var_B0], r12d
0x18000be75  lea     r14, aDetectdomainjo_2; "DetectDomainJoinStatus"
0x18000be7c  mov     [rsp+100h+var_B8], r12
0x18000be81  lea     r15, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x18000be88  mov     [rsp+100h+var_C0], edi
0x18000be8c  lea     r8, aD; "D"
0x18000be93  mov     [rsp+100h+var_C8], rbx
0x18000be98  xor     r9d, r9d
0x18000be9b  mov     [rsp+100h+var_D0], r14
0x18000bea0  xor     edx, edx
0x18000bea2  mov     [rsp+100h+var_D8], r15
0x18000bea7  mov     rcx, rax
0x18000beaa  mov     [rsp+100h+var_E0], 477h
0x18000beb2  call    cs:__imp_WdsSetupLogMessageW
0x18000beb8  mov     rcx, [rbp+57h+Buffer]; Buffer
0x18000bebc  test    rcx, rcx
0x18000bebf  jz      short loc_18000BEC7
0x18000bec1  call    cs:__imp_LsaFreeMemory
0x18000bec7  mov     rcx, [rbp+57h+PolicyHandle]; ObjectHandle
0x18000becb  test    rcx, rcx
0x18000bece  jz      short loc_18000BED6
0x18000bed0  call    cs:__imp_LsaClose
0x18000bed6  mov     eax, esi
0x18000bed8  mov     rcx, [rbp+57h+var_48]
0x18000bedc  xor     rcx, rsp; StackCookie
0x18000bedf  call    __security_check_cookie
0x18000bee4  add     rsp, 0C8h
0x18000beeb  pop     r15
0x18000beed  pop     r14
0x18000beef  pop     r13
0x18000bef1  pop     r12
0x18000bef3  pop     rdi
0x18000bef4  pop     rsi
0x18000bef5  pop     rbx
0x18000bef6  pop     rbp
0x18000bef7  retn
```
