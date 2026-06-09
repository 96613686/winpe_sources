# ServerDllInitialization

- ea: `0x180002f10`
- end: `0x18000414b`
- name: `ServerDllInitialization`
- size: `4667`
- prototype: `NTSTATUS __fastcall(__int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180002f10`
- `0x180004160`
- `0x1800041f0`
- `0x180004d70`
- `0x180007a00`
- `0x18000db05`
- `0x18000db40`

## import_xrefs

- `ntdll!swprintf_s` at `0x1800031c8`
- `ntdll!swprintf_s` at `0x1800031f8`
- `ntdll!swprintf_s` at `0x180003a32`
- `ntdll!swprintf_s` at `0x1800031c8`
- `ntdll!swprintf_s` at `0x1800031f8`
- `ntdll!swprintf_s` at `0x180003a32`
- `ntdll!RtlAllocateHeap` at `0x180003285`
- `ntdll!RtlAllocateHeap` at `0x18000330e`
- `ntdll!RtlAllocateHeap` at `0x180003365`
- `ntdll!RtlAllocateHeap` at `0x1800033d4`
- `ntdll!RtlAllocateHeap` at `0x180003438`
- `ntdll!RtlAllocateHeap` at `0x1800034a5`
- `ntdll!RtlAllocateHeap` at `0x18000379f`
- `ntdll!RtlAllocateHeap` at `0x1800037e8`
- `ntdll!RtlAllocateHeap` at `0x18000383d`
- `ntdll!RtlAllocateHeap` at `0x180003285`
- `ntdll!RtlAllocateHeap` at `0x18000330e`
- `ntdll!RtlAllocateHeap` at `0x180003365`
- `ntdll!RtlAllocateHeap` at `0x1800033d4`
- `ntdll!RtlAllocateHeap` at `0x180003438`
- `ntdll!RtlAllocateHeap` at `0x1800034a5`
- `ntdll!RtlAllocateHeap` at `0x18000379f`
- `ntdll!RtlAllocateHeap` at `0x1800037e8`
- `ntdll!RtlAllocateHeap` at `0x18000383d`
- `ntdll!NtQuerySystemInformation` at `0x1800032d2`
- `ntdll!NtQuerySystemInformation` at `0x180003617`
- `ntdll!NtQuerySystemInformation` at `0x1800032d2`
- `ntdll!NtQuerySystemInformation` at `0x180003617`
- `ntdll!RtlQueryRegistryValuesEx` at `0x180003504`
- `ntdll!RtlQueryRegistryValuesEx` at `0x180003560`
- `ntdll!RtlQueryRegistryValuesEx` at `0x1800035a8`
- `ntdll!RtlQueryRegistryValuesEx` at `0x180003780`
- `ntdll!RtlQueryRegistryValuesEx` at `0x180003504`
- `ntdll!RtlQueryRegistryValuesEx` at `0x180003560`
- `ntdll!RtlQueryRegistryValuesEx` at `0x1800035a8`
- `ntdll!RtlQueryRegistryValuesEx` at `0x180003780`
- `ntdll!wcsncpy_s` at `0x1800035da`
- `ntdll!wcsncpy_s` at `0x1800035da`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800035ef`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800035ef`
- `ntdll!NtOpenKey` at `0x18000368a`
- `ntdll!NtOpenKey` at `0x18000368a`
- `ntdll!NtQueryValueKey` at `0x1800036c4`
- `ntdll!NtQueryValueKey` at `0x1800036c4`
- `ntdll!_wcsicmp` at `0x18000370b`
- `ntdll!_wcsicmp` at `0x180003729`
- `ntdll!_wcsicmp` at `0x18000370b`
- `ntdll!_wcsicmp` at `0x180003729`
- `ntdll!NtClose` at `0x18000374b`
- `ntdll!NtClose` at `0x180003aa4`
- `ntdll!NtClose` at `0x180003be8`
- `ntdll!NtClose` at `0x180003c71`
- `ntdll!NtClose` at `0x180003ce3`
- `ntdll!NtClose` at `0x180003d80`
- `ntdll!NtClose` at `0x180003e77`
- `ntdll!NtClose` at `0x18000374b`
- `ntdll!NtClose` at `0x180003aa4`
- `ntdll!NtClose` at `0x180003be8`
- `ntdll!NtClose` at `0x180003c71`
- `ntdll!NtClose` at `0x180003ce3`
- `ntdll!NtClose` at `0x180003d80`
- `ntdll!NtClose` at `0x180003e77`
- `ntdll!RtlCreateSecurityDescriptor` at `0x1800037bf`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180003808`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18000385d`
- `ntdll!RtlCreateSecurityDescriptor` at `0x1800037bf`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180003808`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18000385d`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1800038b5`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1800038f9`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180003924`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180003daf`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1800038b5`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1800038f9`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180003924`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180003daf`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x1800038d7`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x1800038d7`
- `ntdll!NtCreateDirectoryObject` at `0x18000396d`
- `ntdll!NtCreateDirectoryObject` at `0x1800039b6`
- `ntdll!NtCreateDirectoryObject` at `0x180003af6`
- `ntdll!NtCreateDirectoryObject` at `0x180003dff`
- `ntdll!NtCreateDirectoryObject` at `0x18000396d`
- `ntdll!NtCreateDirectoryObject` at `0x1800039b6`
- `ntdll!NtCreateDirectoryObject` at `0x180003af6`
- `ntdll!NtCreateDirectoryObject` at `0x180003dff`
- `ntdll!NtSetInformationObject` at `0x1800039f0`
- `ntdll!NtSetInformationObject` at `0x1800039f0`
- `ntdll!NtCreateSymbolicLinkObject` at `0x180003a8c`
- `ntdll!NtCreateSymbolicLinkObject` at `0x180003bc0`
- `ntdll!NtCreateSymbolicLinkObject` at `0x180003c49`
- `ntdll!NtCreateSymbolicLinkObject` at `0x180003cbb`
- `ntdll!NtCreateSymbolicLinkObject` at `0x180003d58`
- `ntdll!NtCreateSymbolicLinkObject` at `0x180003e4f`
- `ntdll!NtCreateSymbolicLinkObject` at `0x180003a8c`
- `ntdll!NtCreateSymbolicLinkObject` at `0x180003bc0`
- `ntdll!NtCreateSymbolicLinkObject` at `0x180003c49`
- `ntdll!NtCreateSymbolicLinkObject` at `0x180003cbb`
- `ntdll!NtCreateSymbolicLinkObject` at `0x180003d58`
- `ntdll!NtCreateSymbolicLinkObject` at `0x180003e4f`
- `ntdll!NtQueryInformationProcess` at `0x180003b27`
- `ntdll!NtQueryInformationProcess` at `0x180003b27`
- `ntdll!RtlInitializeCriticalSectionAndSpinCount` at `0x180003b69`
- `ntdll!RtlInitializeCriticalSectionAndSpinCount` at `0x180003b69`
- `ntdll!RtlAppendUnicodeToString` at `0x180003f28`
- `ntdll!RtlAppendUnicodeToString` at `0x180003f28`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180003f3c`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180003f3c`
- `ntdll!NtCreateFile` at `0x180003fb2`
- `ntdll!NtCreateFile` at `0x180003fb2`
- `ntdll!RtlFreeHeap` at `0x180003fd5`
- `ntdll!RtlFreeHeap` at `0x180003fee`
- `ntdll!RtlFreeHeap` at `0x180004007`
- `ntdll!RtlFreeHeap` at `0x180004020`
- `ntdll!RtlFreeHeap` at `0x180004038`
- `ntdll!RtlFreeHeap` at `0x180004050`
- `ntdll!RtlFreeHeap` at `0x18000406e`
- `ntdll!RtlFreeHeap` at `0x18000408b`
- `ntdll!RtlFreeHeap` at `0x180003fd5`
- `ntdll!RtlFreeHeap` at `0x180003fee`
- `ntdll!RtlFreeHeap` at `0x180004007`
- `ntdll!RtlFreeHeap` at `0x180004020`
- `ntdll!RtlFreeHeap` at `0x180004038`
- `ntdll!RtlFreeHeap` at `0x180004050`
- `ntdll!RtlFreeHeap` at `0x18000406e`
- `ntdll!RtlFreeHeap` at `0x18000408b`
- `ntdll!RtlDeleteCriticalSection` at `0x180004100`
- `ntdll!RtlDeleteCriticalSection` at `0x180004100`
- `ntdll!wcscpy_s` at `0x1800031a8`
- `ntdll!wcscpy_s` at `0x1800031a8`
- `ntdll!wcscat_s` at `0x180003159`
- `ntdll!wcscat_s` at `0x180003159`
- `ntdll!RtlCreateUnicodeString` at `0x180003132`
- `ntdll!RtlCreateUnicodeString` at `0x180003173`
- `ntdll!RtlCreateUnicodeString` at `0x180003132`
- `ntdll!RtlCreateUnicodeString` at `0x180003173`
- `ntdll!RtlExpandEnvironmentStrings_U` at `0x1800030f2`
- `ntdll!RtlExpandEnvironmentStrings_U` at `0x1800030f2`
- `ntdll!RtlInitializeCriticalSection` at `0x180003096`
- `ntdll!RtlInitializeCriticalSection` at `0x18000409e`
- `ntdll!RtlInitializeCriticalSection` at `0x1800040b1`
- `ntdll!RtlInitializeCriticalSection` at `0x1800040cb`
- `ntdll!RtlInitializeCriticalSection` at `0x180003096`
- `ntdll!RtlInitializeCriticalSection` at `0x18000409e`
- `ntdll!RtlInitializeCriticalSection` at `0x1800040b1`
- `ntdll!RtlInitializeCriticalSection` at `0x1800040cb`
- `ntdll!RtlCreateTagHeap` at `0x180003012`
- `ntdll!RtlCreateTagHeap` at `0x18000303f`
- `ntdll!RtlCreateTagHeap` at `0x180003012`
- `ntdll!RtlCreateTagHeap` at `0x18000303f`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180002fce`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180002fce`
- `ntdll!RtlInitUnicodeString` at `0x180003238`
- `ntdll!RtlInitUnicodeString` at `0x18000324f`
- `ntdll!RtlInitUnicodeString` at `0x180003266`
- `ntdll!RtlInitUnicodeString` at `0x180003a49`
- `ntdll!RtlInitUnicodeString` at `0x180003bff`
- `ntdll!RtlInitUnicodeString` at `0x180003cfa`
- `ntdll!RtlInitUnicodeString` at `0x180003d11`
- `ntdll!RtlInitUnicodeString` at `0x180003d97`
- `ntdll!RtlInitUnicodeString` at `0x180003238`
- `ntdll!RtlInitUnicodeString` at `0x18000324f`
- `ntdll!RtlInitUnicodeString` at `0x180003266`
- `ntdll!RtlInitUnicodeString` at `0x180003a49`
- `ntdll!RtlInitUnicodeString` at `0x180003bff`
- `ntdll!RtlInitUnicodeString` at `0x180003cfa`
- `ntdll!RtlInitUnicodeString` at `0x180003d11`
- `ntdll!RtlInitUnicodeString` at `0x180003d97`
- `ntdll!RtlGetAce` at `0x180003e97`
- `ntdll!RtlGetAce` at `0x180003ef2`
- `ntdll!RtlGetAce` at `0x180003e97`
- `ntdll!RtlGetAce` at `0x180003ef2`

## string_xrefs

- `0x180003146`: `\system32`
- `0x180003d06`: `\Sessions\BNOLINKS`

## pseudocode

```c
NTSTATUS __fastcall ServerDllInitialization(__int64 a1)
{
  ULONG v2; // esi
  int CurrentServiceSessionId; // eax
  bool v4; // zf
  struct _PEB *v5; // rax
  ULONG TagHeap; // eax
  ULONG v7; // eax
  NTSTATUS result; // eax
  unsigned __int64 v9; // rcx
  _QWORD *Heap; // rax
  NTSTATUS SystemInformation; // ebx
  ULONG v12; // edx
  PVOID v13; // rcx
  CHAR *v14; // rax
  CHAR *v15; // rdi
  STRING *v16; // rbx
  ULONG v17; // edx
  PVOID v18; // rcx
  PVOID v19; // rax
  PVOID v20; // rdi
  __int64 v21; // rbx
  ULONG v22; // edx
  PVOID v23; // rcx
  PVOID v24; // rax
  PVOID v25; // rdi
  __int64 v26; // rbx
  ULONG v27; // edx
  PVOID v28; // rcx
  PVOID v29; // rax
  PVOID v30; // rdi
  __int64 v31; // rbx
  ULONG v32; // edx
  PVOID v33; // rcx
  PVOID v34; // rax
  PVOID v35; // rdi
  __int64 v36; // rbx
  __int64 v37; // rcx
  __int64 v38; // rcx
  PVOID v39; // rax
  void *v40; // rdi
  _QWORD *v41; // rax
  _QWORD *v42; // r14
  void *v43; // r15
  PVOID v44; // rax
  PACL *v45; // rcx
  ULONG v46; // eax
  NTSTATUS v47; // eax
  __int64 v48; // rcx
  struct _ACL *v49; // rsi
  ULONG i; // ebx
  _DWORD *v51; // rdx
  int v52; // eax
  int v53; // r8d
  __int64 v54; // rbx
  ULONG Length[2]; // [rsp+20h] [rbp-E0h]
  ULONG Lengthb[2]; // [rsp+20h] [rbp-E0h]
  ULONG Lengtha[2]; // [rsp+20h] [rbp-E0h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-A0h] BYREF
  void *SymbolicLinkHandle; // [rsp+90h] [rbp-70h] BYREF
  int ProcessInformation; // [rsp+98h] [rbp-68h] BYREF
  PVOID Ace; // [rsp+A0h] [rbp-60h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+A8h] [rbp-58h] BYREF
  ULONG ResultLength; // [rsp+B8h] [rbp-48h] BYREF
  void *KeyHandle; // [rsp+C0h] [rbp-40h] BYREF
  PACL Dacl; // [rsp+C8h] [rbp-38h] BYREF
  PACL v66; // [rsp+D0h] [rbp-30h] BYREF
  PACL v67; // [rsp+D8h] [rbp-28h] BYREF
  PACL Sacl; // [rsp+E0h] [rbp-20h] BYREF
  PACL v69; // [rsp+E8h] [rbp-18h] BYREF
  UNICODE_STRING Source; // [rsp+F0h] [rbp-10h] BYREF
  struct _UNICODE_STRING v71; // [rsp+100h] [rbp+0h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+110h] [rbp+10h] BYREF
  struct _UNICODE_STRING v73; // [rsp+120h] [rbp+20h] BYREF
  struct _UNICODE_STRING Name; // [rsp+130h] [rbp+30h] BYREF
  _DWORD v75[3]; // [rsp+140h] [rbp+40h] BYREF
  __int64 v76; // [rsp+14Ch] [rbp+4Ch]
  struct _UNICODE_STRING v77; // [rsp+158h] [rbp+58h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+168h] [rbp+68h] BYREF
  WCHAR SourceString[2]; // [rsp+180h] [rbp+80h] BYREF
  int v80; // [rsp+184h] [rbp+84h]
  wchar_t String1[294]; // [rsp+18Ch] [rbp+8Ch] BYREF
  char v82; // [rsp+3D8h] [rbp+2D8h] BYREF
  wchar_t Buffer[256]; // [rsp+4A0h] [rbp+3A0h] BYREF
  WCHAR v84[256]; // [rsp+6A0h] [rbp+5A0h] BYREF
  wchar_t v85[256]; // [rsp+8A0h] [rbp+7A0h] BYREF
  wchar_t v86[256]; // [rsp+AA0h] [rbp+9A0h] BYREF
  char v87; // [rsp+CA0h] [rbp+BA0h] BYREF

  v75[0] = 4;
  v75[1] = 1048578;
  ResultLength = 0;
  KeyHandle = 0;
  Dacl = 0;
  DestinationString = 0;
  v66 = 0;
  v2 = 192;
  memset(&ObjectAttributes, 0, 44);
  v67 = 0;
  IoStatusBlock = 0;
  Sacl = 0;
  Destination = 0;
  SymbolicLinkHandle = 0;
  Name = 0;
  ProcessInformation = 0;
  v77 = 0;
  v69 = 0;
  Source = 0;
  v75[2] = 8;
  v71 = 0;
  v76 = 1048580;
  v73 = 0;
  SessionId = NtCurrentPeb()->SessionId;
  CurrentServiceSessionId = RtlGetCurrentServiceSessionId();
  v4 = SessionId == CurrentServiceSessionId;
  ServiceSessionId = CurrentServiceSessionId;
  v5 = NtCurrentPeb();
  if ( v4 )
    v2 = 208;
  BaseSrvHeap = v5->ProcessHeap;
  TagHeap = RtlCreateTagHeap(BaseSrvHeap, 0, (PWSTR)L"BASESRV!", (PWSTR)L"TMP");
  BaseSrvSharedHeap = *(PVOID *)(a1 + 96);
  BaseSrvTag = TagHeap;
  v7 = RtlCreateTagHeap(BaseSrvSharedHeap, 0, (PWSTR)L"BASESHR!", (PWSTR)L"INIT");
  *(_DWORD *)(a1 + 32) = 0;
  BaseSrvSharedTag = v7;
  *(_QWORD *)(a1 + 40) = BaseServerApiDispatchTable;
  *(_QWORD *)(a1 + 48) = BaseServerApiServerValidTable;
  *(_QWORD *)(a1 + 72) = BaseClientConnectRoutine;
  *(_QWORD *)(a1 + 80) = BaseClientDisconnectRoutine;
  *(_DWORD *)(a1 + 36) = 31;
  *(_DWORD *)(a1 + 64) = 8;
  result = RtlInitializeCriticalSection(&BaseSrvDosDeviceCritSec);
  if ( result >= 0 )
  {
    Destination.Buffer = SourceString;
    *(_DWORD *)&Destination.Length = 52428800;
    RtlExpandEnvironmentStrings_U(0, (PUNICODE_STRING)&UnexpandedSystemRootString, &Destination, 0);
    if ( Destination.Length < 0x320u )
    {
      v9 = Destination.Length & 0xFFFE;
      if ( v9 >= 0x320 )
        _report_rangecheckfailure();
      *(WCHAR *)((char *)SourceString + v9) = 0;
      if ( RtlCreateUnicodeString(&BaseSrvWindowsDirectory, SourceString) )
      {
        wcscat_s(SourceString, 0x190u, L"\\system32");
        if ( RtlCreateUnicodeString((PUNICODE_STRING)&BaseSrvWindowsSystemDirectory, SourceString) )
        {
          if ( SessionId == ServiceSessionId )
            wcscpy_s(Buffer, 0x100u, L"\\BaseNamedObjects");
          else
            swprintf_s(Buffer, 0x100u, L"%ws\\%ld\\BaseNamedObjects", L"\\Sessions", SessionId);
          Length[0] = SessionId;
          swprintf_s(v85, 0x100u, L"%ws\\%ld\\AppContainerNamedObjects", L"\\Sessions", *(_QWORD *)Length);
          Lengthb[0] = SessionId;
          RtlStringCchPrintfW(v84, 256, L"%ws\\%ld\\BaseNamedObjects", L"\\Sessions", *(_QWORD *)Lengthb);
          RtlInitUnicodeString(&DestinationString, Buffer);
          RtlInitUnicodeString(&v73, v84);
          RtlInitUnicodeString(&Source, v85);
          Heap = RtlAllocateHeap(BaseSrvSharedHeap, BaseSrvSharedTag, 0xA00u);
          BaseSrvpStaticServerData = (__int64)Heap;
          if ( Heap )
          {
            *(_QWORD *)(a1 + 96) = Heap;
            Heap[317] = Heap;
            *((_DWORD *)Heap + 626) = -1;
            *((_DWORD *)Heap + 628) = 0;
            SystemInformation = NtQuerySystemInformation(SystemTimeOfDayInformation, Heap + 40, 0x30u, 0);
            if ( SystemInformation < 0 )
              goto LABEL_100;
            v12 = BaseSrvSharedTag;
            v13 = BaseSrvSharedHeap;
            *(struct _UNICODE_STRING *)BaseSrvpStaticServerData = BaseSrvWindowsDirectory;
            v14 = (CHAR *)RtlAllocateHeap(v13, v12, BaseSrvWindowsDirectory.MaximumLength);
            v15 = v14;
            if ( v14 )
            {
              v16 = (STRING *)BaseSrvpStaticServerData;
              memcpy_0(v14, *(const void **)(BaseSrvpStaticServerData + 8), BaseSrvWindowsDirectory.MaximumLength);
              v17 = BaseSrvSharedTag;
              v18 = BaseSrvSharedHeap;
              v16->Buffer = v15;
              v16[1] = BaseSrvWindowsSystemDirectory;
              v19 = RtlAllocateHeap(v18, v17, BaseSrvWindowsSystemDirectory.MaximumLength);
              v20 = v19;
              if ( v19 )
              {
                v21 = BaseSrvpStaticServerData;
                memcpy_0(
                  v19,
                  *(const void **)(BaseSrvpStaticServerData + 24),
                  BaseSrvWindowsSystemDirectory.MaximumLength);
                v22 = BaseSrvSharedTag;
                v23 = BaseSrvSharedHeap;
                *(_QWORD *)(v21 + 24) = v20;
                *(_QWORD *)(v21 + 2048) = 0;
                *(_DWORD *)(v21 + 2040) = 0;
                *(struct _UNICODE_STRING *)(v21 + 32) = DestinationString;
                *(_WORD *)(v21 + 34) = DestinationString.Length + 2;
                v24 = RtlAllocateHeap(v23, v22, DestinationString.Length + 2LL);
                v25 = v24;
                if ( v24 )
                {
                  v26 = BaseSrvpStaticServerData;
                  memcpy_0(
                    v24,
                    *(const void **)(BaseSrvpStaticServerData + 40),
                    *(unsigned __int16 *)(BaseSrvpStaticServerData + 34));
                  v27 = BaseSrvSharedTag;
                  v28 = BaseSrvSharedHeap;
                  *(_QWORD *)(v26 + 40) = v25;
                  *(UNICODE_STRING *)(v26 + 2520) = Source;
                  *(_WORD *)(v26 + 2522) = Source.Length + 2;
                  v29 = RtlAllocateHeap(v28, v27, Source.Length + 2LL);
                  v30 = v29;
                  if ( v29 )
                  {
                    v31 = BaseSrvpStaticServerData;
                    memcpy_0(
                      v29,
                      *(const void **)(BaseSrvpStaticServerData + 2528),
                      *(unsigned __int16 *)(BaseSrvpStaticServerData + 2522));
                    v32 = BaseSrvSharedTag;
                    v33 = BaseSrvSharedHeap;
                    *(_QWORD *)(v31 + 2528) = v30;
                    *(struct _UNICODE_STRING *)(v31 + 2544) = v73;
                    *(_WORD *)(v31 + 2546) = v73.Length + 2;
                    v34 = RtlAllocateHeap(v33, v32, v73.Length + 2LL);
                    v35 = v34;
                    if ( v34 )
                    {
                      v36 = BaseSrvpStaticServerData;
                      memcpy_0(
                        v34,
                        *(const void **)(BaseSrvpStaticServerData + 2552),
                        *(unsigned __int16 *)(BaseSrvpStaticServerData + 2546));
                      *(_QWORD *)(v36 + 2552) = v35;
                      *(_BYTE *)(v36 + 2056) = 0;
                      RtlQueryRegistryValuesEx(2, L"Session Manager", &BaseServerRegistryConfigurationTable2, 0, 0);
                      v37 = BaseSrvpStaticServerData;
                      *(_DWORD *)(BaseSrvpStaticServerData + 54) = 0;
                      *(_WORD *)(v37 + 58) = 0;
                      if ( !SkipIniFileMappings )
                      {
                        *(_DWORD *)&BaseSrvCSDString.Length = 13107200;
                        BaseSrvCSDString.Buffer = (PWSTR)&v82;
                        if ( (int)RtlQueryRegistryValuesEx(
                                    3,
                                    &qword_1800105E8,
                                    &BaseServerRegistryConfigurationTable1,
                                    0,
                                    0) >= 0 )
                        {
                          v38 = BaseSrvpStaticServerData;
                          *(_WORD *)(BaseSrvpStaticServerData + 54) = BaseSrvCSDNumber;
                          *(_WORD *)(v38 + 56) = word_1800130AA;
                        }
                        if ( (int)RtlQueryRegistryValuesEx(
                                    3,
                                    &qword_1800105E8,
                                    &BaseServerRegistryConfigurationTable,
                                    0,
                                    0) >= 0 )
                          wcsncpy_s(
                            (wchar_t *)(BaseSrvpStaticServerData + 58),
                            0x80u,
                            BaseSrvCSDString.Buffer,
                            (unsigned __int64)BaseSrvCSDString.Length >> 1);
                        SystemInformation = RtlInitUnicodeStringEx(&BaseSrvCSDString, 0);
                        if ( SystemInformation < 0 )
                          goto LABEL_100;
                      }
                      SystemInformation = NtQuerySystemInformation(SystemBasicInformation, SysInfo, 0x40u, 0);
                      if ( SystemInformation < 0 )
                        goto LABEL_100;
                      if ( !SkipIniFileMappings )
                      {
                        SystemInformation = BaseSrvInitializeIniFileMappings();
                        if ( SystemInformation < 0 )
                          goto LABEL_100;
                      }
                      *(_BYTE *)(BaseSrvpStaticServerData + 2036) = 0;
                      ObjectAttributes.ObjectName = (PUNICODE_STRING)L"ln";
                      ObjectAttributes.Length = 48;
                      ObjectAttributes.RootDirectory = 0;
                      ObjectAttributes.Attributes = 64;
                      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
                      if ( NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
                      {
                        if ( NtQueryValueKey(
                               KeyHandle,
                               (PUNICODE_STRING)&ValueName,
                               KeyValuePartialInformation,
                               SourceString,
                               0x320u,
                               &ResultLength) >= 0 )
                        {
                          if ( v80 == 4 )
                          {
                            *(_BYTE *)(BaseSrvpStaticServerData + 2036) = *(_DWORD *)String1 != 0;
                          }
                          else if ( v80 == 1 && (!_wcsicmp(String1, L"yes") || !_wcsicmp(String1, L"1")) )
                          {
                            *(_BYTE *)(BaseSrvpStaticServerData + 2036) = 1;
                          }
                        }
                        NtClose(KeyHandle);
                      }
                      *(_BYTE *)(BaseSrvpStaticServerData + 2037) = 0;
                      RtlQueryRegistryValuesEx(
                        2,
                        L"Session Manager\\NamespaceSeparation",
                        &BnoRegistryConfigurationTable,
                        0,
                        0);
                      v39 = RtlAllocateHeap(BaseSrvHeap, BaseSrvTag, 0x400u);
                      v40 = v39;
                      if ( v39 )
                      {
                        SystemInformation = RtlCreateSecurityDescriptor(v39, 1u);
                        if ( SystemInformation < 0 )
                          goto LABEL_100;
                        v41 = RtlAllocateHeap(BaseSrvHeap, BaseSrvTag, 0x28u);
                        v42 = v41;
                        if ( v41 )
                        {
                          SystemInformation = RtlCreateSecurityDescriptor(v41, 1u);
                          if ( SystemInformation < 0 )
                            goto LABEL_100;
                          v43 = 0;
                          if ( !InteractiveUserNameSpaceSeparation )
                            goto LABEL_45;
                          v44 = RtlAllocateHeap(BaseSrvHeap, BaseSrvTag, 0x28u);
                          v43 = v44;
                          if ( v44 )
                          {
                            SystemInformation = RtlCreateSecurityDescriptor(v44, 1u);
                            if ( SystemInformation < 0 )
                              goto LABEL_100;
                            if ( InteractiveUserNameSpaceSeparation )
                            {
                              v45 = &v69;
LABEL_46:
                              SystemInformation = CreateBaseAcls(
                                                    (unsigned int)&Dacl,
                                                    (unsigned int)&v66,
                                                    (unsigned int)&v67,
                                                    (unsigned int)&Sacl,
                                                    (__int64)v45);
                              if ( SystemInformation < 0 )
                                goto LABEL_100;
                              SystemInformation = RtlSetDaclSecurityDescriptor(v40, 1u, Dacl, 0);
                              if ( SystemInformation < 0 )
                                goto LABEL_100;
                              SystemInformation = RtlSetSaclSecurityDescriptor(v40, 1u, Sacl, 0);
                              if ( SystemInformation < 0 )
                                goto LABEL_100;
                              SystemInformation = RtlSetDaclSecurityDescriptor(v42, 1u, v67, 0);
                              if ( SystemInformation < 0 )
                                goto LABEL_100;
                              if ( InteractiveUserNameSpaceSeparation )
                              {
                                SystemInformation = RtlSetDaclSecurityDescriptor(v43, 1u, v69, 0);
                                if ( SystemInformation < 0 )
                                  goto LABEL_100;
                              }
                              ObjectAttributes.Length = 48;
                              ObjectAttributes.ObjectName = &DestinationString;
                              ObjectAttributes.RootDirectory = 0;
                              ObjectAttributes.Attributes = v2;
                              ObjectAttributes.SecurityDescriptor = v40;
                              ObjectAttributes.SecurityQualityOfService = 0;
                              SystemInformation = NtCreateDirectoryObject(
                                                    &BaseSrvNamedObjectDirectory,
                                                    0xF000Fu,
                                                    &ObjectAttributes);
                              if ( SystemInformation < 0 )
                                goto LABEL_100;
                              ObjectAttributes.Length = 48;
                              ObjectAttributes.ObjectName = &Source;
                              ObjectAttributes.RootDirectory = 0;
                              ObjectAttributes.Attributes = v2;
                              ObjectAttributes.SecurityDescriptor = v42;
                              ObjectAttributes.SecurityQualityOfService = 0;
                              SystemInformation = NtCreateDirectoryObject(
                                                    &BaseSrvLowBoxObjectDirectory,
                                                    0xF000Fu,
                                                    &ObjectAttributes);
                              if ( SystemInformation < 0 )
                                goto LABEL_100;
                              v46 = SessionId;
                              if ( SessionId == ServiceSessionId )
                              {
                                SystemInformation = NtSetInformationObject(
                                                      BaseSrvNamedObjectDirectory,
                                                      ObjectSessionInformation,
                                                      0,
                                                      0);
                                if ( SystemInformation < 0 )
                                  goto LABEL_100;
                                v46 = SessionId;
                                if ( SessionId )
                                {
                                  Lengtha[0] = SessionId;
                                  swprintf_s(
                                    v86,
                                    0x100u,
                                    L"%ws\\%ld\\BaseNamedObjects",
                                    L"\\Sessions",
                                    *(_QWORD *)Lengtha);
                                  RtlInitUnicodeString(&v77, v86);
                                  ObjectAttributes.Length = 48;
                                  ObjectAttributes.ObjectName = &v77;
                                  ObjectAttributes.RootDirectory = 0;
                                  ObjectAttributes.Attributes = v2;
                                  ObjectAttributes.SecurityDescriptor = v40;
                                  ObjectAttributes.SecurityQualityOfService = 0;
                                  result = NtCreateSymbolicLinkObject(
                                             &SymbolicLinkHandle,
                                             0xF0001u,
                                             &ObjectAttributes,
                                             (PUNICODE_STRING)&::Name);
                                  if ( result < 0 )
                                    return result;
                                  NtClose(SymbolicLinkHandle);
                                  v46 = SessionId;
                                }
                              }
                              if ( !InteractiveUserNameSpaceSeparation
                                || v46
                                || (ObjectAttributes.Length = 48,
                                    ObjectAttributes.ObjectName = &v73,
                                    ObjectAttributes.RootDirectory = 0,
                                    ObjectAttributes.Attributes = v2,
                                    ObjectAttributes.SecurityDescriptor = v43,
                                    ObjectAttributes.SecurityQualityOfService = 0,
                                    SystemInformation = NtCreateDirectoryObject(
                                                          &BaseSrvUserObjectDirectory,
                                                          0xF000Fu,
                                                          &ObjectAttributes),
                                    SystemInformation >= 0) )
                              {
                                v47 = NtQueryInformationProcess(
                                        (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                                        ProcessLUIDDeviceMapsEnabled,
                                        &ProcessInformation,
                                        4u,
                                        0);
                                v48 = BaseSrvpStaticServerData;
                                *(_BYTE *)(BaseSrvpStaticServerData + 2508) = v47 >= 0 && ProcessInformation != 0;
                                if ( *(_BYTE *)(v48 + 2508) != 1
                                  || (SystemInformation = RtlInitializeCriticalSectionAndSpinCount(
                                                            &BaseSrvDDDBSMCritSec,
                                                            0x80000000),
                                      SystemInformation >= 0) )
                                {
                                  ObjectAttributes.RootDirectory = BaseSrvNamedObjectDirectory;
                                  ObjectAttributes.ObjectName = (PUNICODE_STRING)&qword_18000F550;
                                  ObjectAttributes.Length = 48;
                                  ObjectAttributes.Attributes = v2;
                                  ObjectAttributes.SecurityDescriptor = v40;
                                  ObjectAttributes.SecurityQualityOfService = 0;
                                  SystemInformation = NtCreateSymbolicLinkObject(
                                                        &SymbolicLinkHandle,
                                                        0xF0001u,
                                                        &ObjectAttributes,
                                                        (PUNICODE_STRING)&::Name);
                                  if ( SystemInformation >= 0 )
                                  {
                                    if ( SessionId == ServiceSessionId )
                                      NtClose(SymbolicLinkHandle);
                                    RtlInitUnicodeString(&Name, Buffer);
                                    ObjectAttributes.RootDirectory = BaseSrvNamedObjectDirectory;
                                    ObjectAttributes.Length = 48;
                                    ObjectAttributes.ObjectName = (PUNICODE_STRING)&qword_18000F880;
                                    ObjectAttributes.Attributes = v2;
                                    ObjectAttributes.SecurityDescriptor = v40;
                                    ObjectAttributes.SecurityQualityOfService = 0;
                                    SystemInformation = NtCreateSymbolicLinkObject(
                                                          &SymbolicLinkHandle,
                                                          0xF0001u,
                                                          &ObjectAttributes,
                                                          &Name);
                                    if ( SystemInformation >= 0 )
                                    {
                                      if ( SessionId == ServiceSessionId )
                                        NtClose(SymbolicLinkHandle);
                                      ObjectAttributes.RootDirectory = BaseSrvNamedObjectDirectory;
                                      ObjectAttributes.Length = 48;
                                      ObjectAttributes.ObjectName = (PUNICODE_STRING)L"02";
                                      ObjectAttributes.Attributes = v2;
                                      ObjectAttributes.SecurityDescriptor = v40;
                                      ObjectAttributes.SecurityQualityOfService = 0;
                                      SystemInformation = NtCreateSymbolicLinkObject(
                                                            &SymbolicLinkHandle,
                                                            0xF0001u,
                                                            &ObjectAttributes,
                                                            &Source);
                                      if ( SystemInformation >= 0 )
                                      {
                                        if ( SessionId == ServiceSessionId )
                                          NtClose(SymbolicLinkHandle);
                                        RtlInitUnicodeString(&DestinationString, L"Session");
                                        RtlInitUnicodeString(&Name, L"\\Sessions\\BNOLINKS");
                                        ObjectAttributes.RootDirectory = BaseSrvNamedObjectDirectory;
                                        ObjectAttributes.Length = 48;
                                        ObjectAttributes.ObjectName = &DestinationString;
                                        ObjectAttributes.Attributes = v2;
                                        ObjectAttributes.SecurityDescriptor = v40;
                                        ObjectAttributes.SecurityQualityOfService = 0;
                                        SystemInformation = NtCreateSymbolicLinkObject(
                                                              &SymbolicLinkHandle,
                                                              0xF0001u,
                                                              &ObjectAttributes,
                                                              &Name);
                                        if ( SystemInformation >= 0 )
                                        {
                                          if ( SessionId == ServiceSessionId )
                                            NtClose(SymbolicLinkHandle);
                                          RtlInitUnicodeString(&DestinationString, L"Restricted");
                                          SystemInformation = RtlSetDaclSecurityDescriptor(v40, 1u, v66, 0);
                                          if ( SystemInformation >= 0 )
                                          {
                                            ObjectAttributes.RootDirectory = BaseSrvNamedObjectDirectory;
                                            ObjectAttributes.Length = 48;
                                            ObjectAttributes.ObjectName = &DestinationString;
                                            ObjectAttributes.Attributes = v2;
                                            ObjectAttributes.SecurityDescriptor = v40;
                                            ObjectAttributes.SecurityQualityOfService = 0;
                                            SystemInformation = NtCreateDirectoryObject(
                                                                  &BaseSrvRestrictedObjectDirectory,
                                                                  0xF000Fu,
                                                                  &ObjectAttributes);
                                            if ( SystemInformation >= 0 )
                                            {
                                              ObjectAttributes.RootDirectory = BaseSrvRestrictedObjectDirectory;
                                              ObjectAttributes.Length = 48;
                                              ObjectAttributes.Attributes = v2;
                                              ObjectAttributes.ObjectName = (PUNICODE_STRING)&qword_18000F550;
                                              ObjectAttributes.SecurityDescriptor = v40;
                                              ObjectAttributes.SecurityQualityOfService = 0;
                                              SystemInformation = NtCreateSymbolicLinkObject(
                                                                    &SymbolicLinkHandle,
                                                                    0xF0001u,
                                                                    &ObjectAttributes,
                                                                    (PUNICODE_STRING)&::Name);
                                              if ( SystemInformation >= 0 )
                                              {
                                                if ( SessionId == ServiceSessionId )
                                                  NtClose(SymbolicLinkHandle);
                                                v49 = (struct _ACL *)v42[4];
                                                Ace = 0;
                                                for ( i = 0; RtlGetAce(v49, i, &Ace) >= 0; ++i )
                                                {
                                                  v51 = v75;
                                                  v52 = 4;
                                                  v53 = *((_DWORD *)Ace + 1);
                                                  *((_WORD *)Ace + 2) = 0;
                                                  do
                                                  {
                                                    if ( v52 == (unsigned __int16)(v52 & v53) )
                                                      *((_DWORD *)Ace + 1) |= v51[1];
                                                    v52 = v51[2];
                                                    v51 += 2;
                                                  }
                                                  while ( v52 );
                                                }
                                                *(_QWORD *)&v71.Length = 35913728;
                                                v71.Buffer = (PWSTR)&v87;
                                                RtlAppendUnicodeToString(&v71, L"\\Device\\NamedPipe");
                                                RtlAppendUnicodeStringToString(&v71, &Source);
                                                ObjectAttributes.Length = 48;
                                                ObjectAttributes.RootDirectory = 0;
                                                ObjectAttributes.Attributes = 64;
                                                ObjectAttributes.ObjectName = &v71;
                                                ObjectAttributes.SecurityDescriptor = v42;
                                                ObjectAttributes.SecurityQualityOfService = 0;
                                                SystemInformation = NtCreateFile(
                                                                      &BaseSrvLowBoxPipePrefix,
                                                                      0x1F01FFu,
                                                                      &ObjectAttributes,
                                                                      &IoStatusBlock,
                                                                      0,
                                                                      0x80u,
                                                                      3u,
                                                                      2u,
                                                                      1u,
                                                                      0,
                                                                      0);
                                                if ( SystemInformation >= 0 )
                                                {
                                                  RtlFreeHeap(BaseSrvHeap, 0, Dacl);
                                                  RtlFreeHeap(BaseSrvHeap, 0, v66);
                                                  RtlFreeHeap(BaseSrvHeap, 0, v67);
                                                  RtlFreeHeap(BaseSrvHeap, 0, Sacl);
                                                  RtlFreeHeap(BaseSrvHeap, 0, v40);
                                                  RtlFreeHeap(BaseSrvHeap, 0, v42);
                                                  if ( v69 )
                                                    RtlFreeHeap(BaseSrvHeap, 0, v69);
                                                  if ( v43 )
                                                    RtlFreeHeap(BaseSrvHeap, 0, v43);
                                                  RtlInitializeCriticalSection(&BaseSrvVDMCriticalSection);
                                                  RtlInitializeCriticalSection(&BaseSrvVDMNTVDMCplCriticalSection);
                                                  v54 = BaseSrvpStaticServerData;
                                                  if ( RtlInitializeCriticalSection(&NlsCacheCriticalSection) >= 0 )
                                                    pNlsRegUserInfo = (void *)(v54 + 376);
                                                  return 0;
                                                }
                                              }
                                            }
                                          }
                                        }
                                      }
                                    }
                                  }
                                }
                              }
LABEL_100:
                              RtlDeleteCriticalSection(&BaseSrvDosDeviceCritSec);
                              return SystemInformation;
                            }
LABEL_45:
                            v45 = 0;
                            goto LABEL_46;
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
    SystemInformation = -1073741801;
    goto LABEL_100;
  }
  return result;
}

```

## disassembly

```asm
0x180002f10  push    rbp
0x180002f12  push    rbx
0x180002f13  push    rsi
0x180002f14  push    r12
0x180002f16  lea     rbp, [rsp-0DE8h]
0x180002f1e  sub     rsp, 0EE8h
0x180002f25  mov     rax, cs:__security_cookie
0x180002f2c  xor     rax, rsp
0x180002f2f  mov     [rbp+0E00h+var_30], rax
0x180002f36  xorps   xmm0, xmm0
0x180002f39  mov     [rbp+0E00h+var_DC0], 4
0x180002f40  xor     r12d, r12d
0x180002f43  mov     [rbp+0E00h+var_DBC], 100002h
0x180002f4a  movups  xmmword ptr [rsp+0F00h+ObjectAttributes.ObjectName], xmm0
0x180002f4f  mov     [rbp+0E00h+var_E48], r12d
0x180002f53  xor     eax, eax
0x180002f55  xorps   xmm1, xmm1
0x180002f58  mov     [rbp+0E00h+KeyHandle], r12
0x180002f5c  movups  xmmword ptr [rsp+0F00h+ObjectAttributes+1Ch], xmm0
0x180002f61  mov     [rbp+0E00h+Dacl], r12
0x180002f65  mov     rbx, rcx
0x180002f68  movups  xmmword ptr [rbp+0E00h+DestinationString.Length], xmm0
0x180002f6c  mov     [rbp+0E00h+var_E30], r12
0x180002f70  mov     esi, 0C0h
0x180002f75  movups  xmmword ptr [rsp+0F00h+ObjectAttributes.Length], xmm0
0x180002f7a  mov     [rbp+0E00h+var_E28], r12
0x180002f7e  movups  xmmword ptr [rbp+0E00h+IoStatusBlock], xmm0
0x180002f82  mov     [rbp+0E00h+Sacl], r12
0x180002f86  movups  xmmword ptr [rbp+0E00h+Destination.Length], xmm0
0x180002f8a  mov     [rbp+0E00h+SymbolicLinkHandle], r12
0x180002f8e  movups  xmmword ptr [rbp+0E00h+Name.Length], xmm0
0x180002f92  mov     [rbp+0E00h+ProcessInformation], r12d
0x180002f96  movups  xmmword ptr [rbp+0E00h+var_DA8.Length], xmm1
0x180002f9a  mov     [rbp+0E00h+var_E18], r12
0x180002f9e  movups  xmmword ptr [rbp+0E00h+Source.Length], xmm0
0x180002fa2  mov     [rbp+0E00h+var_DB8], 8
0x180002fa9  movups  xmmword ptr [rbp+0E00h+var_E00.Length], xmm1
0x180002fad  mov     [rbp+0E00h+var_DB4], 100004h
0x180002fb5  movups  xmmword ptr [rbp+0E00h+var_DE0.Length], xmm0
0x180002fb9  mov     rax, gs:60h
0x180002fc2  mov     ecx, [rax+2C0h]
0x180002fc8  mov     cs:SessionId, ecx
0x180002fce  call    cs:__imp_RtlGetCurrentServiceSessionId
0x180002fd5  nop     dword ptr [rax+rax+00h]
0x180002fda  cmp     cs:SessionId, eax
0x180002fe0  mov     ecx, 0D0h
0x180002fe5  mov     cs:ServiceSessionId, eax
0x180002feb  lea     r9, TagSubName; "TMP"
0x180002ff2  mov     rax, gs:60h
0x180002ffb  lea     r8, TagName; "BASESRV!"
0x180003002  cmovz   esi, ecx
0x180003005  xor     edx, edx; Flags
0x180003007  mov     rcx, [rax+30h]; HeapHandle
0x18000300b  mov     cs:BaseSrvHeap, rcx
0x180003012  call    cs:__imp_RtlCreateTagHeap
0x180003019  nop     dword ptr [rax+rax+00h]
0x18000301e  mov     rcx, [rbx+60h]; HeapHandle
0x180003022  lea     r9, aInit; "INIT"
0x180003029  lea     r8, aBaseshr; "BASESHR!"
0x180003030  mov     cs:BaseSrvSharedHeap, rcx
0x180003037  xor     edx, edx; Flags
0x180003039  mov     cs:BaseSrvTag, eax
0x18000303f  call    cs:__imp_RtlCreateTagHeap
0x180003046  nop     dword ptr [rax+rax+00h]
0x18000304b  lea     rcx, BaseSrvDosDeviceCritSec; CriticalSection
0x180003052  mov     [rbx+20h], r12d
0x180003056  mov     cs:BaseSrvSharedTag, eax
0x18000305c  lea     rax, BaseServerApiDispatchTable
0x180003063  mov     [rbx+28h], rax
0x180003067  lea     rax, BaseServerApiServerValidTable
0x18000306e  mov     [rbx+30h], rax
0x180003072  lea     rax, BaseClientConnectRoutine
0x180003079  mov     [rbx+48h], rax
0x18000307d  lea     rax, BaseClientDisconnectRoutine
0x180003084  mov     [rbx+50h], rax
0x180003088  mov     dword ptr [rbx+24h], 1Fh
0x18000308f  mov     dword ptr [rbx+40h], 8
0x180003096  call    cs:__imp_RtlInitializeCriticalSection
0x18000309d  nop     dword ptr [rax+rax+00h]
0x1800030a2  test    eax, eax
0x1800030a4  js      loc_18000412E
0x1800030aa  mov     [rsp+0F00h+arg_8], rdi
0x1800030b2  lea     rax, [rbp+0E00h+SourceString]
0x1800030b9  mov     [rsp+0F00h+arg_10], r13
0x1800030c1  lea     r8, [rbp+0E00h+Destination]; Destination
0x1800030c5  mov     [rsp+0F00h+arg_18], r14
0x1800030cd  lea     rdx, UnexpandedSystemRootString; Source
0x1800030d4  xor     r9d, r9d; Length
0x1800030d7  mov     [rsp+0F00h+var_20], r15
0x1800030df  xor     ecx, ecx; Environment
0x1800030e1  mov     [rbp+0E00h+Destination.Buffer], rax
0x1800030e5  mov     r14d, 320h
0x1800030eb  mov     dword ptr [rbp+0E00h+Destination.Length], 3200000h
0x1800030f2  call    cs:__imp_RtlExpandEnvironmentStrings_U
0x1800030f9  nop     dword ptr [rax+rax+00h]
0x1800030fe  movzx   eax, [rbp+0E00h+Destination.Length]
0x180003102  cmp     ax, r14w
0x180003106  jnb     loc_1800040F4
0x18000310c  mov     ecx, eax
0x18000310e  and     rcx, 0FFFFFFFFFFFFFFFEh
0x180003112  cmp     rcx, r14
0x180003115  jnb     loc_1800040EE
0x18000311b  mov     [rbp+rcx+0E00h+SourceString], r12w
0x180003124  lea     rdx, [rbp+0E00h+SourceString]; SourceString
0x18000312b  lea     rcx, BaseSrvWindowsDirectory; DestinationString
0x180003132  call    cs:__imp_RtlCreateUnicodeString
0x180003139  nop     dword ptr [rax+rax+00h]
0x18000313e  test    al, al
0x180003140  jz      loc_1800040F4
0x180003146  lea     r8, aSystem32; "\\system32"
0x18000314d  mov     edx, 190h; SizeInWords
0x180003152  lea     rcx, [rbp+0E00h+SourceString]; Destination
0x180003159  call    cs:__imp_wcscat_s
0x180003160  nop     dword ptr [rax+rax+00h]
0x180003165  lea     rdx, [rbp+0E00h+SourceString]; SourceString
0x18000316c  lea     rcx, BaseSrvWindowsSystemDirectory; DestinationString
0x180003173  call    cs:__imp_RtlCreateUnicodeString
0x18000317a  nop     dword ptr [rax+rax+00h]
0x18000317f  test    al, al
0x180003181  jz      loc_1800040F4
0x180003187  mov     eax, cs:SessionId
0x18000318d  lea     rcx, [rbp+0E00h+Buffer]; Buffer
0x180003194  cmp     eax, cs:ServiceSessionId
0x18000319a  mov     edx, 100h; BufferCount
0x18000319f  jnz     short loc_1800031B6
0x1800031a1  lea     r8, aBasenamedobjec; "\\BaseNamedObjects"
0x1800031a8  call    cs:__imp_wcscpy_s
0x1800031af  nop     dword ptr [rax+rax+00h]
0x1800031b4  jmp     short loc_1800031D4
0x1800031b6  lea     r9, aSessions; "\\Sessions"
0x1800031bd  mov     [rsp+0F00h+Length], eax
0x1800031c1  lea     r8, aWsLdBasenamedo; "%ws\\%ld\\BaseNamedObjects"
0x1800031c8  call    cs:__imp_swprintf_s
0x1800031cf  nop     dword ptr [rax+rax+00h]
0x1800031d4  mov     eax, cs:SessionId
0x1800031da  lea     r9, aSessions; "\\Sessions"
0x1800031e1  lea     r8, aWsLdAppcontain; "%ws\\%ld\\AppContainerNamedObjects"
0x1800031e8  mov     [rsp+0F00h+Length], eax
0x1800031ec  mov     edx, 100h; BufferCount
0x1800031f1  lea     rcx, [rbp+0E00h+var_660]; Buffer
0x1800031f8  call    cs:__imp_swprintf_s
0x1800031ff  nop     dword ptr [rax+rax+00h]
0x180003204  mov     eax, cs:SessionId
0x18000320a  lea     r9, aSessions; "\\Sessions"
0x180003211  lea     r8, aWsLdBasenamedo; "%ws\\%ld\\BaseNamedObjects"
0x180003218  mov     [rsp+0F00h+Length], eax
0x18000321c  mov     edx, 100h
0x180003221  lea     rcx, [rbp+0E00h+var_860]
0x180003228  call    RtlStringCchPrintfW
0x18000322d  lea     rdx, [rbp+0E00h+Buffer]; SourceString
0x180003234  lea     rcx, [rbp+0E00h+DestinationString]; DestinationString
0x180003238  call    cs:__imp_RtlInitUnicodeString
0x18000323f  nop     dword ptr [rax+rax+00h]
0x180003244  lea     rdx, [rbp+0E00h+var_860]; SourceString
0x18000324b  lea     rcx, [rbp+0E00h+var_DE0]; DestinationString
0x18000324f  call    cs:__imp_RtlInitUnicodeString
0x180003256  nop     dword ptr [rax+rax+00h]
0x18000325b  lea     rdx, [rbp+0E00h+var_660]; SourceString
0x180003262  lea     rcx, [rbp+0E00h+Source]; DestinationString
0x180003266  call    cs:__imp_RtlInitUnicodeString
0x18000326d  nop     dword ptr [rax+rax+00h]
0x180003272  mov     edx, cs:BaseSrvSharedTag; Flags
0x180003278  mov     r8d, 0A00h; Size
0x18000327e  mov     rcx, cs:BaseSrvSharedHeap; HeapHandle
0x180003285  call    cs:__imp_RtlAllocateHeap
0x18000328c  nop     dword ptr [rax+rax+00h]
0x180003291  mov     cs:BaseSrvpStaticServerData, rax
0x180003298  test    rax, rax
0x18000329b  jz      loc_1800040F4
0x1800032a1  mov     [rbx+60h], rax
0x1800032a5  lea     rdx, [rax+140h]; SystemInformation
0x1800032ac  mov     [rax+9E8h], rax
0x1800032b3  xor     r9d, r9d; ReturnLength
0x1800032b6  mov     dword ptr [rax+9C8h], 0FFFFFFFFh
0x1800032c0  mov     ecx, 3; SystemInformationClass
0x1800032c5  mov     r8d, 30h ; '0'; SystemInformationLength
0x1800032cb  mov     [rax+9D0h], r12d
0x1800032d2  call    cs:__imp_NtQuerySystemInformation
0x1800032d9  nop     dword ptr [rax+rax+00h]
0x1800032de  mov     ebx, eax
0x1800032e0  test    eax, eax
0x1800032e2  js      loc_1800040F9
0x1800032e8  mov     rax, cs:BaseSrvpStaticServerData
0x1800032ef  movups  xmm0, xmmword ptr cs:BaseSrvWindowsDirectory.Length
0x1800032f6  mov     edx, cs:BaseSrvSharedTag; Flags
0x1800032fc  mov     rcx, cs:BaseSrvSharedHeap; HeapHandle
0x180003303  movups  xmmword ptr [rax], xmm0
0x180003306  movzx   r8d, cs:BaseSrvWindowsDirectory.MaximumLength; Size
0x18000330e  call    cs:__imp_RtlAllocateHeap
0x180003315  nop     dword ptr [rax+rax+00h]
0x18000331a  mov     rdi, rax
0x18000331d  test    rax, rax
0x180003320  jz      loc_1800040F4
0x180003326  mov     rbx, cs:BaseSrvpStaticServerData
0x18000332d  mov     rcx, rax; void *
0x180003330  movzx   r8d, cs:BaseSrvWindowsDirectory.MaximumLength; Size
0x180003338  mov     rdx, [rbx+8]; Src
0x18000333c  call    memcpy_0
0x180003341  mov     edx, cs:BaseSrvSharedTag; Flags
0x180003347  mov     rcx, cs:BaseSrvSharedHeap; HeapHandle
0x18000334e  mov     [rbx+8], rdi
0x180003352  movups  xmm0, xmmword ptr cs:BaseSrvWindowsSystemDirectory.Length
0x180003359  movups  xmmword ptr [rbx+10h], xmm0
0x18000335d  movzx   r8d, cs:BaseSrvWindowsSystemDirectory.MaximumLength; Size
0x180003365  call    cs:__imp_RtlAllocateHeap
0x18000336c  nop     dword ptr [rax+rax+00h]
0x180003371  mov     rdi, rax
0x180003374  test    rax, rax
0x180003377  jz      loc_1800040F4
0x18000337d  mov     rbx, cs:BaseSrvpStaticServerData
0x180003384  mov     rcx, rax; void *
0x180003387  movzx   r8d, cs:BaseSrvWindowsSystemDirectory.MaximumLength; Size
0x18000338f  mov     rdx, [rbx+18h]; Src
0x180003393  call    memcpy_0
0x180003398  mov     edx, cs:BaseSrvSharedTag; Flags
0x18000339e  mov     rcx, cs:BaseSrvSharedHeap; HeapHandle
0x1800033a5  mov     [rbx+18h], rdi
0x1800033a9  mov     [rbx+800h], r12
0x1800033b0  mov     [rbx+7F8h], r12d
0x1800033b7  movups  xmm0, xmmword ptr [rbp+0E00h+DestinationString.Length]
0x1800033bb  movups  xmmword ptr [rbx+20h], xmm0
0x1800033bf  movzx   eax, [rbp+0E00h+DestinationString.Length]
0x1800033c3  add     ax, 2
0x1800033c7  mov     [rbx+22h], ax
0x1800033cb  movzx   r8d, [rbp+0E00h+DestinationString.Length]
0x1800033d0  add     r8, 2; Size
0x1800033d4  call    cs:__imp_RtlAllocateHeap
0x1800033db  nop     dword ptr [rax+rax+00h]
0x1800033e0  mov     rdi, rax
0x1800033e3  test    rax, rax
0x1800033e6  jz      loc_1800040F4
0x1800033ec  mov     rbx, cs:BaseSrvpStaticServerData
0x1800033f3  mov     rcx, rax; void *
0x1800033f6  movzx   r8d, word ptr [rbx+22h]; Size
0x1800033fb  mov     rdx, [rbx+28h]; Src
0x1800033ff  call    memcpy_0
0x180003404  mov     edx, cs:BaseSrvSharedTag; Flags
0x18000340a  mov     rcx, cs:BaseSrvSharedHeap; HeapHandle
0x180003411  mov     [rbx+28h], rdi
0x180003415  movups  xmm0, xmmword ptr [rbp+0E00h+Source.Length]
0x180003419  movups  xmmword ptr [rbx+9D8h], xmm0
0x180003420  movzx   eax, [rbp+0E00h+Source.Length]
0x180003424  add     ax, 2
0x180003428  mov     [rbx+9DAh], ax
0x18000342f  movzx   r8d, [rbp+0E00h+Source.Length]
0x180003434  add     r8, 2; Size
0x180003438  call    cs:__imp_RtlAllocateHeap
0x18000343f  nop     dword ptr [rax+rax+00h]
0x180003444  mov     rdi, rax
0x180003447  test    rax, rax
0x18000344a  jz      loc_1800040F4
0x180003450  mov     rbx, cs:BaseSrvpStaticServerData
0x180003457  mov     rcx, rax; void *
0x18000345a  movzx   r8d, word ptr [rbx+9DAh]; Size
0x180003462  mov     rdx, [rbx+9E0h]; Src
0x180003469  call    memcpy_0
0x18000346e  mov     edx, cs:BaseSrvSharedTag; Flags
0x180003474  mov     rcx, cs:BaseSrvSharedHeap; HeapHandle
0x18000347b  mov     [rbx+9E0h], rdi
0x180003482  movups  xmm0, xmmword ptr [rbp+0E00h+var_DE0.Length]
0x180003486  movups  xmmword ptr [rbx+9F0h], xmm0
0x18000348d  movzx   eax, [rbp+0E00h+var_DE0.Length]
0x180003491  add     ax, 2
0x180003495  mov     [rbx+9F2h], ax
0x18000349c  movzx   r8d, [rbp+0E00h+var_DE0.Length]
0x1800034a1  add     r8, 2; Size
0x1800034a5  call    cs:__imp_RtlAllocateHeap
0x1800034ac  nop     dword ptr [rax+rax+00h]
0x1800034b1  mov     rdi, rax
0x1800034b4  test    rax, rax
0x1800034b7  jz      loc_1800040F4
0x1800034bd  mov     rbx, cs:BaseSrvpStaticServerData
0x1800034c4  mov     rcx, rax; void *
0x1800034c7  movzx   r8d, word ptr [rbx+9F2h]; Size
0x1800034cf  mov     rdx, [rbx+9F8h]; Src
0x1800034d6  call    memcpy_0
0x1800034db  xor     r9d, r9d
0x1800034de  mov     [rbx+9F8h], rdi
0x1800034e5  lea     r8, BaseServerRegistryConfigurationTable2
0x1800034ec  mov     [rbx+808h], r12b
0x1800034f3  lea     rdx, aSessionManager_0; "Session Manager"
0x1800034fa  mov     qword ptr [rsp+0F00h+Length], r12
0x1800034ff  mov     ecx, 2
0x180003504  call    cs:__imp_RtlQueryRegistryValuesEx
0x18000350b  nop     dword ptr [rax+rax+00h]
0x180003510  mov     rcx, cs:BaseSrvpStaticServerData
0x180003517  mov     [rcx+36h], r12d
0x18000351b  mov     [rcx+3Ah], r12w
0x180003520  cmp     cs:SkipIniFileMappings, r12d
0x180003527  jnz     loc_180003605
0x18000352d  lea     rax, [rbp+0E00h+var_B28]
0x180003534  mov     dword ptr cs:BaseSrvCSDString.Length, 0C80000h
0x18000353e  xor     r9d, r9d
0x180003541  mov     cs:BaseSrvCSDString.Buffer, rax
0x180003548  lea     r8, BaseServerRegistryConfigurationTable1
0x18000354f  mov     qword ptr [rsp+0F00h+Length], r12
0x180003554  lea     rdx, qword_1800105E8
0x18000355b  mov     ecx, 3
0x180003560  call    cs:__imp_RtlQueryRegistryValuesEx
0x180003567  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
