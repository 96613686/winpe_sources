# HiveListEnumerator::UnloadHiveByNtPath(ushort const *,ushort const *,bool)

- ea: `0x14005861c`
- end: `0x140058937`
- name: `?UnloadHiveByNtPath@HiveListEnumerator@@KA_NPEBG0_N@Z`
- size: `795`
- prototype: `bool __fastcall(PCWSTR SourceString, PCWSTR, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140056ee0`

## callees

- `0x140055d10`
- `0x14005861c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400586b6`
- `KERNEL32!GetLastError` at `0x1400587fc`
- `KERNEL32!GetLastError` at `0x140058896`
- `KERNEL32!GetLastError` at `0x1400586b6`
- `KERNEL32!GetLastError` at `0x1400587fc`
- `KERNEL32!GetLastError` at `0x140058896`
- `KERNEL32!Sleep` at `0x140058878`
- `KERNEL32!Sleep` at `0x140058878`
- `KERNEL32!SetLastError` at `0x140058749`
- `KERNEL32!SetLastError` at `0x140058749`
- `ntdll!NtOpenFile` at `0x1400587ca`
- `ntdll!NtOpenFile` at `0x1400587ca`
- `ntdll!NtUnloadKey2` at `0x140058692`
- `ntdll!NtUnloadKey2` at `0x140058692`
- `ntdll!NtClose` at `0x1400588ff`
- `ntdll!NtClose` at `0x1400588ff`
- `ntdll!RtlInitUnicodeString` at `0x14005865d`
- `ntdll!RtlInitUnicodeString` at `0x14005877f`
- `ntdll!RtlInitUnicodeString` at `0x14005865d`
- `ntdll!RtlInitUnicodeString` at `0x14005877f`
- `ntdll!RtlNtStatusToDosError` at `0x1400586a8`
- `ntdll!RtlNtStatusToDosError` at `0x1400587e0`
- `ntdll!RtlNtStatusToDosError` at `0x1400586a8`
- `ntdll!RtlNtStatusToDosError` at `0x1400587e0`
- `WDSCORE!WdsSetupLogMessageW` at `0x14005873b`
- `WDSCORE!WdsSetupLogMessageW` at `0x140058865`
- `WDSCORE!WdsSetupLogMessageW` at `0x14005873b`
- `WDSCORE!WdsSetupLogMessageW` at `0x140058865`
- `WDSCORE!CurrentIP` at `0x1400586c4`
- `WDSCORE!CurrentIP` at `0x14005880a`
- `WDSCORE!CurrentIP` at `0x1400588a4`
- `WDSCORE!CurrentIP` at `0x1400586c4`
- `WDSCORE!CurrentIP` at `0x14005880a`
- `WDSCORE!CurrentIP` at `0x1400588a4`

## string_xrefs

- `0x1400586fa`: `HiveListEnumerator::UnloadHiveByNtPath`
- `0x14005875f`: `HiveListEnumerator::UnloadHiveByNtPath`
- `0x140058819`: `Hive file %s is in use; will attempt retries to ensure it is unloaded.`

## pseudocode

```c
char __fastcall HiveListEnumerator::UnloadHiveByNtPath(PCWSTR SourceString, PCWSTR a2)
{
  ULONG v4; // esi
  int v5; // eax
  DWORD LastError; // edi
  __int64 v7; // rbx
  struct tagLOG_PARTIAL_MSG *v8; // rax
  int v10; // r14d
  int v11; // eax
  DWORD v12; // edi
  __int64 v13; // rbx
  struct tagLOG_PARTIAL_MSG *v14; // rax
  DWORD v15; // edi
  __int64 v16; // rbx
  struct tagLOG_PARTIAL_MSG *v17; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-19h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+78h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES TargetKey; // [rsp+88h] [rbp+7h] BYREF
  void *FileHandle; // [rsp+100h] [rbp+7Fh] BYREF

  *(&TargetKey.Length + 1) = 0;
  *(&TargetKey.Attributes + 1) = 0;
  v4 = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  TargetKey.Length = 48;
  TargetKey.ObjectName = &DestinationString;
  TargetKey.RootDirectory = 0;
  TargetKey.Attributes = 64;
  *(_OWORD *)&TargetKey.SecurityDescriptor = 0;
  v5 = NtUnloadKey2(&TargetKey, 1u);
  if ( v5 < 0 )
  {
    v4 = RtlNtStatusToDosError(v5);
    LastError = GetLastError();
    v7 = CurrentIP();
    v8 = ConstructPartialMsgW(
           0x2000000,
           "Failed to %sunload hive loaded at [%s]. Error: 0x%08X",
           (const char *)L"force-",
           (const char *)SourceString,
           v4);
    WdsSetupLogMessageW(
      v8,
      0,
      L"D",
      0,
      377,
      L"base\\ntsetup\\setupplatform\\lib\\static\\utilities.cpp",
      L"HiveListEnumerator::UnloadHiveByNtPath",
      v7,
      LastError,
      0,
      0);
LABEL_3:
    SetLastError(v4);
    return 0;
  }
  v10 = 0;
  while ( 1 )
  {
    FileHandle = 0;
    IoStatusBlock = 0;
    RtlInitUnicodeString(&DestinationString, a2);
    TargetKey.ObjectName = &DestinationString;
    TargetKey.Length = 48;
    TargetKey.RootDirectory = 0;
    TargetKey.Attributes = 64;
    *(_OWORD *)&TargetKey.SecurityDescriptor = 0;
    v11 = NtOpenFile(&FileHandle, 0x40000000u, &TargetKey, &IoStatusBlock, 0, 0x4000u);
    if ( v11 >= 0 )
      break;
    v4 = RtlNtStatusToDosError(v11);
    if ( v4 != 32 )
    {
      v15 = GetLastError();
      v16 = CurrentIP();
      v17 = ConstructPartialMsgW(
              50331648,
              "Could not get exclusive lock on hive file %s. Error: 0x%08X",
              (const char *)a2,
              v4);
      WdsSetupLogMessageW(
        v17,
        0,
        L"D",
        0,
        446,
        L"base\\ntsetup\\setupplatform\\lib\\static\\utilities.cpp",
        L"HiveListEnumerator::UnloadHiveByNtPath",
        v16,
        v15,
        0,
        0);
      goto LABEL_3;
    }
    if ( !v10 )
    {
      v12 = GetLastError();
      v13 = CurrentIP();
      v14 = ConstructPartialMsgW(
              50331648,
              "Hive file %s is in use; will attempt retries to ensure it is unloaded.",
              (const char *)a2);
      WdsSetupLogMessageW(
        v14,
        0,
        L"D",
        0,
        457,
        L"base\\ntsetup\\setupplatform\\lib\\static\\utilities.cpp",
        L"HiveListEnumerator::UnloadHiveByNtPath",
        v13,
        v12,
        0,
        0);
    }
    Sleep(0x1F4u);
    if ( (unsigned int)++v10 >= 0x3C )
      goto LABEL_3;
  }
  NtClose(FileHandle);
  if ( v4 )
    goto LABEL_3;
  return 1;
}

```

## disassembly

```asm
0x14005861c  mov     rax, rsp
0x14005861f  mov     [rax+8], rbx
0x140058623  mov     [rax+10h], rsi
0x140058627  mov     [rax+18h], rdi
0x14005862b  push    rbp
0x14005862c  push    r12
0x14005862e  push    r13
0x140058630  push    r14
0x140058632  push    r15
0x140058634  lea     rbp, [rax-5Fh]
0x140058638  sub     rsp, 0B0h
0x14005863f  xor     ebx, ebx
0x140058641  mov     r13, rdx
0x140058644  mov     rdx, rcx; SourceString
0x140058647  mov     dword ptr [rbp+57h+TargetKey+4], ebx
0x14005864a  mov     r14, rcx
0x14005864d  mov     dword ptr [rbp+57h+TargetKey+1Ch], ebx
0x140058650  xorps   xmm0, xmm0
0x140058653  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140058657  mov     esi, ebx
0x140058659  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14005865d  call    cs:__imp_RtlInitUnicodeString
0x140058664  nop     dword ptr [rax+rax+00h]
0x140058669  lea     rax, [rbp+57h+DestinationString]
0x14005866d  mov     [rbp+57h+TargetKey.Length], 30h ; '0'
0x140058674  xorps   xmm0, xmm0
0x140058677  mov     [rbp+57h+TargetKey.ObjectName], rax
0x14005867b  lea     edx, [rbx+1]; Flags
0x14005867e  mov     [rbp+57h+TargetKey.RootDirectory], rbx
0x140058682  lea     rcx, [rbp+57h+TargetKey]; TargetKey
0x140058686  mov     [rbp+57h+TargetKey.Attributes], 40h ; '@'
0x14005868d  movdqu  xmmword ptr [rbp+57h+TargetKey.SecurityDescriptor], xmm0
0x140058692  call    cs:__imp_NtUnloadKey2
0x140058699  nop     dword ptr [rax+rax+00h]
0x14005869e  test    eax, eax
0x1400586a0  jns     loc_14005875C
0x1400586a6  mov     ecx, eax; Status
0x1400586a8  call    cs:__imp_RtlNtStatusToDosError
0x1400586af  nop     dword ptr [rax+rax+00h]
0x1400586b4  mov     esi, eax
0x1400586b6  call    cs:__imp_GetLastError
0x1400586bd  nop     dword ptr [rax+rax+00h]
0x1400586c2  mov     edi, eax
0x1400586c4  call    cs:__imp_CurrentIP
0x1400586cb  nop     dword ptr [rax+rax+00h]
0x1400586d0  mov     r9, r14
0x1400586d3  mov     [rsp+0D0h+ShareAccess], esi
0x1400586d7  lea     r8, aForce; "force-"
0x1400586de  mov     ecx, 2000000h; unsigned int
0x1400586e3  lea     rdx, aFailedToSunloa; "Failed to %sunload hive loaded at [%s]."...
0x1400586ea  mov     rbx, rax
0x1400586ed  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1400586f2  mov     [rsp+0D0h+var_80], 0
0x1400586fa  lea     r15, aHivelistenumer_0; "HiveListEnumerator::UnloadHiveByNtPath"
0x140058701  mov     qword ptr [rsp+0D0h+var_88], 0
0x14005870a  lea     r12, aBaseNtsetupSet_0; "base\\ntsetup\\setupplatform\\lib\\stat"...
0x140058711  mov     dword ptr [rsp+0D0h+var_90], edi
0x140058715  mov     qword ptr [rsp+0D0h+var_98], rbx
0x14005871a  mov     [rsp+0D0h+var_A0], r15
0x14005871f  mov     qword ptr [rsp+0D0h+OpenOptions], r12
0x140058724  mov     [rsp+0D0h+ShareAccess], 179h
0x14005872c  xor     r9d, r9d
0x14005872f  lea     r8, aD; "D"
0x140058736  xor     edx, edx
0x140058738  mov     rcx, rax
0x14005873b  call    cs:__imp_WdsSetupLogMessageW
0x140058742  nop     dword ptr [rax+rax+00h]
0x140058747  mov     ecx, esi; dwErrCode
0x140058749  call    cs:__imp_SetLastError
0x140058750  nop     dword ptr [rax+rax+00h]
0x140058755  xor     al, al
0x140058757  jmp     loc_140058915
0x14005875c  mov     r14d, ebx
0x14005875f  lea     r15, aHivelistenumer_0; "HiveListEnumerator::UnloadHiveByNtPath"
0x140058766  lea     r12, aBaseNtsetupSet_0; "base\\ntsetup\\setupplatform\\lib\\stat"...
0x14005876d  xorps   xmm0, xmm0
0x140058770  mov     [rbp+57h+FileHandle], rbx
0x140058774  mov     rdx, r13; SourceString
0x140058777  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14005877b  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x14005877f  call    cs:__imp_RtlInitUnicodeString
0x140058786  nop     dword ptr [rax+rax+00h]
0x14005878b  lea     rax, [rbp+57h+DestinationString]
0x14005878f  mov     [rsp+0D0h+OpenOptions], 4000h; OpenOptions
0x140058797  xorps   xmm0, xmm0
0x14005879a  mov     [rbp+57h+TargetKey.ObjectName], rax
0x14005879e  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1400587a2  mov     [rbp+57h+TargetKey.Length], 30h ; '0'
0x1400587a9  lea     r8, [rbp+57h+TargetKey]; ObjectAttributes
0x1400587ad  mov     [rbp+57h+TargetKey.RootDirectory], rbx
0x1400587b1  mov     edx, 40000000h; DesiredAccess
0x1400587b6  mov     [rbp+57h+TargetKey.Attributes], 40h ; '@'
0x1400587bd  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x1400587c1  mov     [rsp+0D0h+ShareAccess], ebx; ShareAccess
0x1400587c5  movdqu  xmmword ptr [rbp+57h+TargetKey.SecurityDescriptor], xmm0
0x1400587ca  call    cs:__imp_NtOpenFile
0x1400587d1  nop     dword ptr [rax+rax+00h]
0x1400587d6  test    eax, eax
0x1400587d8  jns     loc_1400588FB
0x1400587de  mov     ecx, eax; Status
0x1400587e0  call    cs:__imp_RtlNtStatusToDosError
0x1400587e7  nop     dword ptr [rax+rax+00h]
0x1400587ec  mov     esi, eax
0x1400587ee  cmp     eax, 20h ; ' '
0x1400587f1  jnz     loc_140058896
0x1400587f7  test    r14d, r14d
0x1400587fa  jnz     short loc_140058873
0x1400587fc  call    cs:__imp_GetLastError
0x140058803  nop     dword ptr [rax+rax+00h]
0x140058808  mov     edi, eax
0x14005880a  call    cs:__imp_CurrentIP
0x140058811  nop     dword ptr [rax+rax+00h]
0x140058816  mov     r8, r13
0x140058819  lea     rdx, aHiveFileSIsInU; "Hive file %s is in use; will attempt re"...
0x140058820  mov     ecx, 3000000h; unsigned int
0x140058825  mov     rbx, rax
0x140058828  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x14005882d  mov     [rsp+0D0h+var_80], r14d
0x140058832  lea     r8, aD; "D"
0x140058839  mov     qword ptr [rsp+0D0h+var_88], 0
0x140058842  xor     r9d, r9d
0x140058845  mov     dword ptr [rsp+0D0h+var_90], edi
0x140058849  xor     edx, edx
0x14005884b  mov     qword ptr [rsp+0D0h+var_98], rbx
0x140058850  mov     rcx, rax
0x140058853  mov     [rsp+0D0h+var_A0], r15
0x140058858  mov     qword ptr [rsp+0D0h+OpenOptions], r12
0x14005885d  mov     [rsp+0D0h+ShareAccess], 1C9h
0x140058865  call    cs:__imp_WdsSetupLogMessageW
0x14005886c  nop     dword ptr [rax+rax+00h]
0x140058871  xor     ebx, ebx
0x140058873  mov     ecx, 1F4h; dwMilliseconds
0x140058878  call    cs:__imp_Sleep
0x14005887f  nop     dword ptr [rax+rax+00h]
0x140058884  inc     r14d
0x140058887  cmp     r14d, 3Ch ; '<'
0x14005888b  jb      loc_14005876D
0x140058891  jmp     loc_140058747
0x140058896  call    cs:__imp_GetLastError
0x14005889d  nop     dword ptr [rax+rax+00h]
0x1400588a2  mov     edi, eax
0x1400588a4  call    cs:__imp_CurrentIP
0x1400588ab  nop     dword ptr [rax+rax+00h]
0x1400588b0  mov     r9d, esi
0x1400588b3  lea     rdx, aCouldNotGetExc; "Could not get exclusive lock on hive fi"...
0x1400588ba  mov     r8, r13
0x1400588bd  mov     ecx, 3000000h; unsigned int
0x1400588c2  mov     rbx, rax
0x1400588c5  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1400588ca  mov     [rsp+0D0h+var_80], 0
0x1400588d2  mov     qword ptr [rsp+0D0h+var_88], 0
0x1400588db  mov     dword ptr [rsp+0D0h+var_90], edi
0x1400588df  mov     qword ptr [rsp+0D0h+var_98], rbx
0x1400588e4  mov     [rsp+0D0h+var_A0], r15
0x1400588e9  mov     qword ptr [rsp+0D0h+OpenOptions], r12
0x1400588ee  mov     [rsp+0D0h+ShareAccess], 1BEh
0x1400588f6  jmp     loc_14005872C
0x1400588fb  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1400588ff  call    cs:__imp_NtClose
0x140058906  nop     dword ptr [rax+rax+00h]
0x14005890b  test    esi, esi
0x14005890d  jnz     loc_140058747
0x140058913  mov     al, 1
0x140058915  lea     r11, [rsp+0D0h+var_20]
0x14005891d  mov     rbx, [r11+30h]
0x140058921  mov     rsi, [r11+38h]
0x140058925  mov     rdi, [r11+40h]
0x140058929  mov     rsp, r11
0x14005892c  pop     r15
0x14005892e  pop     r14
0x140058930  pop     r13
0x140058932  pop     r12
0x140058934  pop     rbp
0x140058935  retn
```
