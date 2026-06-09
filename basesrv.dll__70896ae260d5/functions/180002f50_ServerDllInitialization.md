# ServerDllInitialization

- ea: `0x180002f50`
- end: `0x18000416e`
- name: `ServerDllInitialization`
- size: `4638`
- prototype: `NTSTATUS __fastcall(__int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180002f50`
- `0x180004180`
- `0x180004210`
- `0x180004d80`
- `0x1800076fc`
- `0x18000d6fb`
- `0x18000d730`

## import_xrefs

- `ntdll!swprintf_s` at `0x180003205`
- `ntdll!swprintf_s` at `0x180003235`
- `ntdll!swprintf_s` at `0x180003a63`
- `ntdll!swprintf_s` at `0x180003205`
- `ntdll!swprintf_s` at `0x180003235`
- `ntdll!swprintf_s` at `0x180003a63`
- `ntdll!RtlAllocateHeap` at `0x1800032c2`
- `ntdll!RtlAllocateHeap` at `0x180003348`
- `ntdll!RtlAllocateHeap` at `0x18000339f`
- `ntdll!RtlAllocateHeap` at `0x18000340e`
- `ntdll!RtlAllocateHeap` at `0x180003472`
- `ntdll!RtlAllocateHeap` at `0x1800034df`
- `ntdll!RtlAllocateHeap` at `0x1800037d4`
- `ntdll!RtlAllocateHeap` at `0x18000381d`
- `ntdll!RtlAllocateHeap` at `0x18000386f`
- `ntdll!RtlAllocateHeap` at `0x1800032c2`
- `ntdll!RtlAllocateHeap` at `0x180003348`
- `ntdll!RtlAllocateHeap` at `0x18000339f`
- `ntdll!RtlAllocateHeap` at `0x18000340e`
- `ntdll!RtlAllocateHeap` at `0x180003472`
- `ntdll!RtlAllocateHeap` at `0x1800034df`
- `ntdll!RtlAllocateHeap` at `0x1800037d4`
- `ntdll!RtlAllocateHeap` at `0x18000381d`
- `ntdll!RtlAllocateHeap` at `0x18000386f`
- `ntdll!NtQuerySystemInformation` at `0x18000330c`
- `ntdll!NtQuerySystemInformation` at `0x18000364c`
- `ntdll!NtQuerySystemInformation` at `0x18000330c`
- `ntdll!NtQuerySystemInformation` at `0x18000364c`
- `ntdll!RtlQueryRegistryValuesEx` at `0x18000353d`
- `ntdll!RtlQueryRegistryValuesEx` at `0x180003598`
- `ntdll!RtlQueryRegistryValuesEx` at `0x1800035df`
- `ntdll!RtlQueryRegistryValuesEx` at `0x1800037b5`
- `ntdll!RtlQueryRegistryValuesEx` at `0x18000353d`
- `ntdll!RtlQueryRegistryValuesEx` at `0x180003598`
- `ntdll!RtlQueryRegistryValuesEx` at `0x1800035df`
- `ntdll!RtlQueryRegistryValuesEx` at `0x1800037b5`
- `ntdll!wcsncpy_s` at `0x180003611`
- `ntdll!wcsncpy_s` at `0x180003611`
- `ntdll!RtlInitUnicodeStringEx` at `0x180003626`
- `ntdll!RtlInitUnicodeStringEx` at `0x180003626`
- `ntdll!NtOpenKey` at `0x1800036bf`
- `ntdll!NtOpenKey` at `0x1800036bf`
- `ntdll!NtQueryValueKey` at `0x1800036f9`
- `ntdll!NtQueryValueKey` at `0x1800036f9`
- `ntdll!_wcsicmp` at `0x180003741`
- `ntdll!_wcsicmp` at `0x18000375f`
- `ntdll!_wcsicmp` at `0x180003741`
- `ntdll!_wcsicmp` at `0x18000375f`
- `ntdll!NtClose` at `0x180003781`
- `ntdll!NtClose` at `0x180003ad5`
- `ntdll!NtClose` at `0x180003c18`
- `ntdll!NtClose` at `0x180003ca1`
- `ntdll!NtClose` at `0x180003d13`
- `ntdll!NtClose` at `0x180003db0`
- `ntdll!NtClose` at `0x180003ea7`
- `ntdll!NtClose` at `0x180003781`
- `ntdll!NtClose` at `0x180003ad5`
- `ntdll!NtClose` at `0x180003c18`
- `ntdll!NtClose` at `0x180003ca1`
- `ntdll!NtClose` at `0x180003d13`
- `ntdll!NtClose` at `0x180003db0`
- `ntdll!NtClose` at `0x180003ea7`
- `ntdll!RtlCreateSecurityDescriptor` at `0x1800037f4`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18000383d`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18000388f`
- `ntdll!RtlCreateSecurityDescriptor` at `0x1800037f4`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18000383d`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18000388f`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1800038e7`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18000392b`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180003956`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180003ddf`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1800038e7`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18000392b`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180003956`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180003ddf`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x180003909`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x180003909`
- `ntdll!NtCreateDirectoryObject` at `0x18000399f`
- `ntdll!NtCreateDirectoryObject` at `0x1800039e8`
- `ntdll!NtCreateDirectoryObject` at `0x180003b27`
- `ntdll!NtCreateDirectoryObject` at `0x180003e2f`
- `ntdll!NtCreateDirectoryObject` at `0x18000399f`
- `ntdll!NtCreateDirectoryObject` at `0x1800039e8`
- `ntdll!NtCreateDirectoryObject` at `0x180003b27`
- `ntdll!NtCreateDirectoryObject` at `0x180003e2f`
- `ntdll!NtSetInformationObject` at `0x180003a21`
- `ntdll!NtSetInformationObject` at `0x180003a21`
- `ntdll!NtCreateSymbolicLinkObject` at `0x180003abd`
- `ntdll!NtCreateSymbolicLinkObject` at `0x180003bf0`
- `ntdll!NtCreateSymbolicLinkObject` at `0x180003c79`
- `ntdll!NtCreateSymbolicLinkObject` at `0x180003ceb`
- `ntdll!NtCreateSymbolicLinkObject` at `0x180003d88`
- `ntdll!NtCreateSymbolicLinkObject` at `0x180003e7f`
- `ntdll!NtCreateSymbolicLinkObject` at `0x180003abd`
- `ntdll!NtCreateSymbolicLinkObject` at `0x180003bf0`
- `ntdll!NtCreateSymbolicLinkObject` at `0x180003c79`
- `ntdll!NtCreateSymbolicLinkObject` at `0x180003ceb`
- `ntdll!NtCreateSymbolicLinkObject` at `0x180003d88`
- `ntdll!NtCreateSymbolicLinkObject` at `0x180003e7f`
- `ntdll!NtQueryInformationProcess` at `0x180003b57`
- `ntdll!NtQueryInformationProcess` at `0x180003b57`
- `ntdll!RtlInitializeCriticalSectionAndSpinCount` at `0x180003b99`
- `ntdll!RtlInitializeCriticalSectionAndSpinCount` at `0x180003b99`
- `ntdll!RtlAppendUnicodeToString` at `0x180003f51`
- `ntdll!RtlAppendUnicodeToString` at `0x180003f51`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180003f65`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180003f65`
- `ntdll!NtCreateFile` at `0x180003fdb`
- `ntdll!NtCreateFile` at `0x180003fdb`
- `ntdll!RtlFreeHeap` at `0x180003ffe`
- `ntdll!RtlFreeHeap` at `0x180004017`
- `ntdll!RtlFreeHeap` at `0x180004030`
- `ntdll!RtlFreeHeap` at `0x180004049`
- `ntdll!RtlFreeHeap` at `0x180004061`
- `ntdll!RtlFreeHeap` at `0x180004079`
- `ntdll!RtlFreeHeap` at `0x180004097`
- `ntdll!RtlFreeHeap` at `0x1800040b4`
- `ntdll!RtlFreeHeap` at `0x180003ffe`
- `ntdll!RtlFreeHeap` at `0x180004017`
- `ntdll!RtlFreeHeap` at `0x180004030`
- `ntdll!RtlFreeHeap` at `0x180004049`
- `ntdll!RtlFreeHeap` at `0x180004061`
- `ntdll!RtlFreeHeap` at `0x180004079`
- `ntdll!RtlFreeHeap` at `0x180004097`
- `ntdll!RtlFreeHeap` at `0x1800040b4`
- `ntdll!RtlDeleteCriticalSection` at `0x180004129`
- `ntdll!RtlDeleteCriticalSection` at `0x180004129`
- `ntdll!wcscpy_s` at `0x1800031e5`
- `ntdll!wcscpy_s` at `0x1800031e5`
- `ntdll!wcscat_s` at `0x180003196`
- `ntdll!wcscat_s` at `0x180003196`
- `ntdll!RtlCreateUnicodeString` at `0x18000316f`
- `ntdll!RtlCreateUnicodeString` at `0x1800031b0`
- `ntdll!RtlCreateUnicodeString` at `0x18000316f`
- `ntdll!RtlCreateUnicodeString` at `0x1800031b0`
- `ntdll!RtlExpandEnvironmentStrings_U` at `0x180003131`
- `ntdll!RtlExpandEnvironmentStrings_U` at `0x180003131`
- `ntdll!RtlInitializeCriticalSection` at `0x1800030dd`
- `ntdll!RtlInitializeCriticalSection` at `0x1800040c7`
- `ntdll!RtlInitializeCriticalSection` at `0x1800040da`
- `ntdll!RtlInitializeCriticalSection` at `0x1800040f4`
- `ntdll!RtlInitializeCriticalSection` at `0x1800030dd`
- `ntdll!RtlInitializeCriticalSection` at `0x1800040c7`
- `ntdll!RtlInitializeCriticalSection` at `0x1800040da`
- `ntdll!RtlInitializeCriticalSection` at `0x1800040f4`
- `ntdll!RtlCreateTagHeap` at `0x180003059`
- `ntdll!RtlCreateTagHeap` at `0x180003086`
- `ntdll!RtlCreateTagHeap` at `0x180003059`
- `ntdll!RtlCreateTagHeap` at `0x180003086`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180003015`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180003015`
- `ntdll!RtlInitUnicodeString` at `0x180003275`
- `ntdll!RtlInitUnicodeString` at `0x18000328c`
- `ntdll!RtlInitUnicodeString` at `0x1800032a3`
- `ntdll!RtlInitUnicodeString` at `0x180003a7a`
- `ntdll!RtlInitUnicodeString` at `0x180003c2f`
- `ntdll!RtlInitUnicodeString` at `0x180003d2a`
- `ntdll!RtlInitUnicodeString` at `0x180003d41`
- `ntdll!RtlInitUnicodeString` at `0x180003dc7`
- `ntdll!RtlInitUnicodeString` at `0x180003275`
- `ntdll!RtlInitUnicodeString` at `0x18000328c`
- `ntdll!RtlInitUnicodeString` at `0x1800032a3`
- `ntdll!RtlInitUnicodeString` at `0x180003a7a`
- `ntdll!RtlInitUnicodeString` at `0x180003c2f`
- `ntdll!RtlInitUnicodeString` at `0x180003d2a`
- `ntdll!RtlInitUnicodeString` at `0x180003d41`
- `ntdll!RtlInitUnicodeString` at `0x180003dc7`
- `ntdll!RtlGetAce` at `0x180003ec7`
- `ntdll!RtlGetAce` at `0x180003f22`
- `ntdll!RtlGetAce` at `0x180003ec7`
- `ntdll!RtlGetAce` at `0x180003f22`

## string_xrefs

- `0x180003183`: `\system32`
- `0x180003d36`: `\Sessions\BNOLINKS`

## pseudocode

```c
NTSTATUS __fastcall ServerDllInitialization(__int64 a1)
{
  ULONG v2; // esi
  void *v3; // r15
  int CurrentServiceSessionId; // eax
  bool v5; // zf
  struct _PEB *v6; // rax
  ULONG TagHeap; // eax
  ULONG v8; // eax
  NTSTATUS result; // eax
  unsigned __int64 v10; // rax
  _QWORD *Heap; // rax
  NTSTATUS SystemInformation; // ebx
  ULONG v13; // edx
  PVOID v14; // rcx
  CHAR *v15; // rax
  CHAR *v16; // rdi
  STRING *v17; // rbx
  ULONG v18; // edx
  PVOID v19; // rcx
  PVOID v20; // rax
  PVOID v21; // rdi
  __int64 v22; // rbx
  ULONG v23; // edx
  PVOID v24; // rcx
  PVOID v25; // rax
  PVOID v26; // rdi
  __int64 v27; // rbx
  ULONG v28; // edx
  PVOID v29; // rcx
  PVOID v30; // rax
  PVOID v31; // rdi
  __int64 v32; // rbx
  ULONG v33; // edx
  PVOID v34; // rcx
  PVOID v35; // rax
  PVOID v36; // rdi
  __int64 v37; // rbx
  __int64 v38; // rax
  __int64 v39; // rcx
  PVOID v40; // rax
  void *v41; // rdi
  _QWORD *v42; // rax
  _QWORD *v43; // r14
  PVOID v44; // rax
  PACL *v45; // rcx
  ULONG v46; // eax
  NTSTATUS v47; // eax
  __int64 v48; // rcx
  struct _ACL *v49; // rsi
  ULONG i; // ebx
  _DWORD *v51; // rdx
  int v52; // r8d
  int v53; // eax
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
  struct _UNICODE_STRING Destination; // [rsp+100h] [rbp+0h] BYREF
  struct _UNICODE_STRING v72; // [rsp+110h] [rbp+10h] BYREF
  struct _UNICODE_STRING v73; // [rsp+120h] [rbp+20h] BYREF
  struct _UNICODE_STRING Name; // [rsp+130h] [rbp+30h] BYREF
  struct _UNICODE_STRING v75; // [rsp+140h] [rbp+40h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+150h] [rbp+50h] BYREF
  _DWORD v77[3]; // [rsp+160h] [rbp+60h] BYREF
  __int64 v78; // [rsp+16Ch] [rbp+6Ch]
  WCHAR SourceString[2]; // [rsp+180h] [rbp+80h] BYREF
  __int64 v80; // [rsp+184h] [rbp+84h]
  wchar_t String1[294]; // [rsp+18Ch] [rbp+8Ch] BYREF
  char v82; // [rsp+3D8h] [rbp+2D8h] BYREF
  wchar_t Buffer[256]; // [rsp+4A0h] [rbp+3A0h] BYREF
  WCHAR v84[256]; // [rsp+6A0h] [rbp+5A0h] BYREF
  wchar_t v85[256]; // [rsp+8A0h] [rbp+7A0h] BYREF
  wchar_t v86[256]; // [rsp+AA0h] [rbp+9A0h] BYREF
  char v87; // [rsp+CA0h] [rbp+BA0h] BYREF

  v77[0] = 4;
  ResultLength = 0;
  *(_DWORD *)(&Destination.MaximumLength + 1) = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  KeyHandle = 0;
  v2 = 192;
  Dacl = 0;
  v3 = 0;
  IoStatusBlock = 0;
  v66 = 0;
  v67 = 0;
  Sacl = 0;
  SymbolicLinkHandle = 0;
  Name = 0;
  ProcessInformation = 0;
  v75 = 0;
  v69 = 0;
  Source = 0;
  v77[1] = 1048578;
  v73 = 0;
  v77[2] = 8;
  v72 = 0;
  v78 = 1048580;
  SessionId = NtCurrentPeb()->SessionId;
  CurrentServiceSessionId = RtlGetCurrentServiceSessionId();
  v5 = SessionId == CurrentServiceSessionId;
  ServiceSessionId = CurrentServiceSessionId;
  v6 = NtCurrentPeb();
  if ( v5 )
    v2 = 208;
  BaseSrvHeap = v6->ProcessHeap;
  TagHeap = RtlCreateTagHeap(BaseSrvHeap, 0, (PWSTR)L"BASESRV!", (PWSTR)L"TMP");
  BaseSrvSharedHeap = *(PVOID *)(a1 + 96);
  BaseSrvTag = TagHeap;
  v8 = RtlCreateTagHeap(BaseSrvSharedHeap, 0, (PWSTR)L"BASESHR!", (PWSTR)L"INIT");
  *(_DWORD *)(a1 + 32) = 0;
  BaseSrvSharedTag = v8;
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
      v10 = Destination.Length & 0xFFFE;
      if ( v10 >= 0x320 )
        _report_rangecheckfailure();
      *(WCHAR *)((char *)SourceString + v10) = 0;
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
          RtlInitUnicodeString(&v72, v84);
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
            v13 = BaseSrvSharedTag;
            v14 = BaseSrvSharedHeap;
            *(struct _UNICODE_STRING *)BaseSrvpStaticServerData = BaseSrvWindowsDirectory;
            v15 = (CHAR *)RtlAllocateHeap(v14, v13, BaseSrvWindowsDirectory.MaximumLength);
            v16 = v15;
            if ( v15 )
            {
              v17 = (STRING *)BaseSrvpStaticServerData;
              memcpy_0(v15, *(const void **)(BaseSrvpStaticServerData + 8), BaseSrvWindowsDirectory.MaximumLength);
              v18 = BaseSrvSharedTag;
              v19 = BaseSrvSharedHeap;
              v17->Buffer = v16;
              v17[1] = BaseSrvWindowsSystemDirectory;
              v20 = RtlAllocateHeap(v19, v18, BaseSrvWindowsSystemDirectory.MaximumLength);
              v21 = v20;
              if ( v20 )
              {
                v22 = BaseSrvpStaticServerData;
                memcpy_0(
                  v20,
                  *(const void **)(BaseSrvpStaticServerData + 24),
                  BaseSrvWindowsSystemDirectory.MaximumLength);
                v23 = BaseSrvSharedTag;
                v24 = BaseSrvSharedHeap;
                *(_QWORD *)(v22 + 24) = v21;
                *(_QWORD *)(v22 + 2048) = 0;
                *(_DWORD *)(v22 + 2040) = 0;
                *(struct _UNICODE_STRING *)(v22 + 32) = DestinationString;
                *(_WORD *)(v22 + 34) = DestinationString.Length + 2;
                v25 = RtlAllocateHeap(v24, v23, DestinationString.Length + 2LL);
                v26 = v25;
                if ( v25 )
                {
                  v27 = BaseSrvpStaticServerData;
                  memcpy_0(
                    v25,
                    *(const void **)(BaseSrvpStaticServerData + 40),
                    *(unsigned __int16 *)(BaseSrvpStaticServerData + 34));
                  v28 = BaseSrvSharedTag;
                  v29 = BaseSrvSharedHeap;
                  *(_QWORD *)(v27 + 40) = v26;
                  *(UNICODE_STRING *)(v27 + 2520) = Source;
                  *(_WORD *)(v27 + 2522) = Source.Length + 2;
                  v30 = RtlAllocateHeap(v29, v28, Source.Length + 2LL);
                  v31 = v30;
                  if ( v30 )
                  {
                    v32 = BaseSrvpStaticServerData;
                    memcpy_0(
                      v30,
                      *(const void **)(BaseSrvpStaticServerData + 2528),
                      *(unsigned __int16 *)(BaseSrvpStaticServerData + 2522));
                    v33 = BaseSrvSharedTag;
                    v34 = BaseSrvSharedHeap;
                    *(_QWORD *)(v32 + 2528) = v31;
                    *(struct _UNICODE_STRING *)(v32 + 2544) = v72;
                    *(_WORD *)(v32 + 2546) = v72.Length + 2;
                    v35 = RtlAllocateHeap(v34, v33, v72.Length + 2LL);
                    v36 = v35;
                    if ( v35 )
                    {
                      v37 = BaseSrvpStaticServerData;
                      memcpy_0(
                        v35,
                        *(const void **)(BaseSrvpStaticServerData + 2552),
                        *(unsigned __int16 *)(BaseSrvpStaticServerData + 2546));
                      *(_QWORD *)(v37 + 2552) = v36;
                      *(_BYTE *)(v37 + 2056) = 0;
                      RtlQueryRegistryValuesEx(2, L"Session Manager", &BaseServerRegistryConfigurationTable2);
                      v38 = BaseSrvpStaticServerData;
                      *(_DWORD *)(BaseSrvpStaticServerData + 54) = 0;
                      *(_WORD *)(v38 + 58) = 0;
                      if ( !SkipIniFileMappings )
                      {
                        *(_DWORD *)&BaseSrvCSDString.Length = 13107200;
                        BaseSrvCSDString.Buffer = (PWSTR)&v82;
                        if ( (int)RtlQueryRegistryValuesEx(3, &dword_18001069C, &BaseServerRegistryConfigurationTable1) >= 0 )
                        {
                          v39 = BaseSrvpStaticServerData;
                          *(_WORD *)(BaseSrvpStaticServerData + 54) = BaseSrvCSDNumber;
                          *(_WORD *)(v39 + 56) = word_1800130AA;
                        }
                        if ( (int)RtlQueryRegistryValuesEx(3, &dword_18001069C, &BaseServerRegistryConfigurationTable) >= 0 )
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
                          if ( (_DWORD)v80 == 4 )
                          {
                            *(_BYTE *)(BaseSrvpStaticServerData + 2036) = *(_DWORD *)String1 != 0;
                          }
                          else if ( (_DWORD)v80 == 1 && (!_wcsicmp(String1, L"yes") || !_wcsicmp(String1, L"1")) )
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
                        &BnoRegistryConfigurationTable);
                      v40 = RtlAllocateHeap(BaseSrvHeap, BaseSrvTag, 0x400u);
                      v41 = v40;
                      if ( v40 )
                      {
                        SystemInformation = RtlCreateSecurityDescriptor(v40, 1u);
                        if ( SystemInformation < 0 )
                          goto LABEL_100;
                        v42 = RtlAllocateHeap(BaseSrvHeap, BaseSrvTag, 0x28u);
                        v43 = v42;
                        if ( v42 )
                        {
                          SystemInformation = RtlCreateSecurityDescriptor(v42, 1u);
                          if ( SystemInformation < 0 )
                            goto LABEL_100;
                          if ( !InteractiveUserNameSpaceSeparation )
                            goto LABEL_45;
                          v44 = RtlAllocateHeap(BaseSrvHeap, BaseSrvTag, 0x28u);
                          v3 = v44;
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
                              SystemInformation = RtlSetDaclSecurityDescriptor(v41, 1u, Dacl, 0);
                              if ( SystemInformation < 0 )
                                goto LABEL_100;
                              SystemInformation = RtlSetSaclSecurityDescriptor(v41, 1u, Sacl, 0);
                              if ( SystemInformation < 0 )
                                goto LABEL_100;
                              SystemInformation = RtlSetDaclSecurityDescriptor(v43, 1u, v67, 0);
                              if ( SystemInformation < 0 )
                                goto LABEL_100;
                              if ( InteractiveUserNameSpaceSeparation )
                              {
                                SystemInformation = RtlSetDaclSecurityDescriptor(v3, 1u, v69, 0);
                                if ( SystemInformation < 0 )
                                  goto LABEL_100;
                              }
                              ObjectAttributes.Length = 48;
                              ObjectAttributes.ObjectName = &DestinationString;
                              ObjectAttributes.RootDirectory = 0;
                              ObjectAttributes.Attributes = v2;
                              ObjectAttributes.SecurityDescriptor = v41;
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
                              ObjectAttributes.SecurityDescriptor = v43;
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
                                  RtlInitUnicodeString(&v75, v86);
                                  ObjectAttributes.Length = 48;
                                  ObjectAttributes.ObjectName = &v75;
                                  ObjectAttributes.RootDirectory = 0;
                                  ObjectAttributes.Attributes = v2;
                                  ObjectAttributes.SecurityDescriptor = v41;
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
                                    ObjectAttributes.ObjectName = &v72,
                                    ObjectAttributes.RootDirectory = 0,
                                    ObjectAttributes.Attributes = v2,
                                    ObjectAttributes.SecurityDescriptor = v3,
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
                                  ObjectAttributes.ObjectName = (PUNICODE_STRING)&qword_18000F540;
                                  ObjectAttributes.Length = 48;
                                  ObjectAttributes.Attributes = v2;
                                  ObjectAttributes.SecurityDescriptor = v41;
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
                                    ObjectAttributes.ObjectName = (PUNICODE_STRING)&qword_18000F870;
                                    ObjectAttributes.Attributes = v2;
                                    ObjectAttributes.SecurityDescriptor = v41;
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
                                      ObjectAttributes.SecurityDescriptor = v41;
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
                                        ObjectAttributes.SecurityDescriptor = v41;
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
                                          SystemInformation = RtlSetDaclSecurityDescriptor(v41, 1u, v66, 0);
                                          if ( SystemInformation >= 0 )
                                          {
                                            ObjectAttributes.RootDirectory = BaseSrvNamedObjectDirectory;
                                            ObjectAttributes.Length = 48;
                                            ObjectAttributes.ObjectName = &DestinationString;
                                            ObjectAttributes.Attributes = v2;
                                            ObjectAttributes.SecurityDescriptor = v41;
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
                                              ObjectAttributes.ObjectName = (PUNICODE_STRING)&qword_18000F540;
                                              ObjectAttributes.SecurityDescriptor = v41;
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
                                                v49 = (struct _ACL *)v43[4];
                                                Ace = 0;
                                                for ( i = 0; RtlGetAce(v49, i, &Ace) >= 0; ++i )
                                                {
                                                  v51 = v77;
                                                  v52 = *((_DWORD *)Ace + 1);
                                                  *((_WORD *)Ace + 2) = 0;
                                                  v53 = 4;
                                                  do
                                                  {
                                                    if ( v53 == (unsigned __int16)(v53 & v52) )
                                                      *((_DWORD *)Ace + 1) |= v51[1];
                                                    v53 = v51[2];
                                                    v51 += 2;
                                                  }
                                                  while ( v53 );
                                                }
                                                v73.MaximumLength = 548;
                                                v73.Buffer = (PWSTR)&v87;
                                                RtlAppendUnicodeToString(&v73, L"\\Device\\NamedPipe");
                                                RtlAppendUnicodeStringToString(&v73, &Source);
                                                ObjectAttributes.Length = 48;
                                                ObjectAttributes.RootDirectory = 0;
                                                ObjectAttributes.Attributes = 64;
                                                ObjectAttributes.ObjectName = &v73;
                                                ObjectAttributes.SecurityDescriptor = v43;
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
                                                  RtlFreeHeap(BaseSrvHeap, 0, v41);
                                                  RtlFreeHeap(BaseSrvHeap, 0, v43);
                                                  if ( v69 )
                                                    RtlFreeHeap(BaseSrvHeap, 0, v69);
                                                  if ( v3 )
                                                    RtlFreeHeap(BaseSrvHeap, 0, v3);
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
0x180002f50  push    rbp
0x180002f52  push    rbx
0x180002f53  push    rsi
0x180002f54  push    r12
0x180002f56  push    r15
0x180002f58  lea     rbp, [rsp-0DE0h]
0x180002f60  sub     rsp, 0EE0h
0x180002f67  mov     rax, cs:__security_cookie
0x180002f6e  xor     rax, rsp
0x180002f71  mov     [rbp+0E00h+var_30], rax
0x180002f78  xor     r12d, r12d
0x180002f7b  mov     [rbp+0E00h+var_DA0], 4
0x180002f82  xorps   xmm0, xmm0
0x180002f85  mov     [rbp+0E00h+var_E48], r12d
0x180002f89  xor     eax, eax
0x180002f8b  mov     dword ptr [rbp+0E00h+Destination+4], r12d
0x180002f8f  xorps   xmm1, xmm1
0x180002f92  mov     [rbp+0E00h+ObjectAttributes.SecurityDescriptor], rax
0x180002f96  movups  xmmword ptr [rbp+0E00h+DestinationString.Length], xmm0
0x180002f9a  mov     dword ptr [rbp+0E00h+ObjectAttributes.SecurityQualityOfService], eax
0x180002f9d  mov     rbx, rcx
0x180002fa0  movups  xmmword ptr [rsp+0F00h+ObjectAttributes.Length], xmm0
0x180002fa5  mov     [rbp+0E00h+KeyHandle], r12
0x180002fa9  mov     esi, 0C0h
0x180002fae  movups  xmmword ptr [rsp+0F00h+ObjectAttributes.ObjectName], xmm0
0x180002fb3  mov     [rbp+0E00h+Dacl], r12
0x180002fb7  mov     r15d, r12d
0x180002fba  movups  xmmword ptr [rbp+0E00h+IoStatusBlock], xmm0
0x180002fbe  mov     [rbp+0E00h+var_E30], r12
0x180002fc2  mov     [rbp+0E00h+var_E28], r12
0x180002fc6  mov     [rbp+0E00h+Sacl], r12
0x180002fca  mov     [rbp+0E00h+SymbolicLinkHandle], r12
0x180002fce  movups  xmmword ptr [rbp+0E00h+Name.Length], xmm0
0x180002fd2  mov     [rbp+0E00h+ProcessInformation], r12d
0x180002fd6  movups  xmmword ptr [rbp+0E00h+var_DC0.Length], xmm1
0x180002fda  mov     [rbp+0E00h+var_E18], r12
0x180002fde  movups  xmmword ptr [rbp+0E00h+Source.Length], xmm0
0x180002fe2  mov     [rbp+0E00h+var_D9C], 100002h
0x180002fe9  movups  xmmword ptr [rbp+0E00h+var_DE0.Length], xmm1
0x180002fed  mov     [rbp+0E00h+var_D98], 8
0x180002ff4  movups  xmmword ptr [rbp+0E00h+var_DF0.Length], xmm0
0x180002ff8  mov     rax, gs:60h
0x180003001  mov     [rbp+0E00h+var_D94], 100004h
0x180003009  mov     ecx, [rax+2C0h]
0x18000300f  mov     cs:SessionId, ecx
0x180003015  call    cs:__imp_RtlGetCurrentServiceSessionId
0x18000301c  nop     dword ptr [rax+rax+00h]
0x180003021  cmp     cs:SessionId, eax
0x180003027  mov     ecx, 0D0h
0x18000302c  mov     cs:ServiceSessionId, eax
0x180003032  lea     r9, TagSubName; "TMP"
0x180003039  mov     rax, gs:60h
0x180003042  lea     r8, TagName; "BASESRV!"
0x180003049  cmovz   esi, ecx
0x18000304c  xor     edx, edx; Flags
0x18000304e  mov     rcx, [rax+30h]; HeapHandle
0x180003052  mov     cs:BaseSrvHeap, rcx
0x180003059  call    cs:__imp_RtlCreateTagHeap
0x180003060  nop     dword ptr [rax+rax+00h]
0x180003065  mov     rcx, [rbx+60h]; HeapHandle
0x180003069  lea     r9, aInit; "INIT"
0x180003070  lea     r8, aBaseshr; "BASESHR!"
0x180003077  mov     cs:BaseSrvSharedHeap, rcx
0x18000307e  xor     edx, edx; Flags
0x180003080  mov     cs:BaseSrvTag, eax
0x180003086  call    cs:__imp_RtlCreateTagHeap
0x18000308d  nop     dword ptr [rax+rax+00h]
0x180003092  lea     rcx, BaseSrvDosDeviceCritSec; CriticalSection
0x180003099  mov     [rbx+20h], r12d
0x18000309d  mov     cs:BaseSrvSharedTag, eax
0x1800030a3  lea     rax, BaseServerApiDispatchTable
0x1800030aa  mov     [rbx+28h], rax
0x1800030ae  lea     rax, BaseServerApiServerValidTable
0x1800030b5  mov     [rbx+30h], rax
0x1800030b9  lea     rax, BaseClientConnectRoutine
0x1800030c0  mov     [rbx+48h], rax
0x1800030c4  lea     rax, BaseClientDisconnectRoutine
0x1800030cb  mov     [rbx+50h], rax
0x1800030cf  mov     dword ptr [rbx+24h], 1Fh
0x1800030d6  mov     dword ptr [rbx+40h], 8
0x1800030dd  call    cs:__imp_RtlInitializeCriticalSection
0x1800030e4  nop     dword ptr [rax+rax+00h]
0x1800030e9  test    eax, eax
0x1800030eb  js      loc_18000414F
0x1800030f1  mov     [rsp+0F00h+arg_8], rdi
0x1800030f9  lea     rax, [rbp+0E00h+SourceString]
0x180003100  mov     [rsp+0F00h+arg_10], r13
0x180003108  lea     r8, [rbp+0E00h+Destination]; Destination
0x18000310c  mov     [rsp+0F00h+arg_18], r14
0x180003114  lea     rdx, UnexpandedSystemRootString; Source
0x18000311b  xor     r9d, r9d; Length
0x18000311e  mov     [rbp+0E00h+Destination.Buffer], rax
0x180003122  xor     ecx, ecx; Environment
0x180003124  mov     dword ptr [rbp+0E00h+Destination.Length], 3200000h
0x18000312b  mov     r14d, 320h
0x180003131  call    cs:__imp_RtlExpandEnvironmentStrings_U
0x180003138  nop     dword ptr [rax+rax+00h]
0x18000313d  movzx   eax, [rbp+0E00h+Destination.Length]
0x180003141  cmp     ax, r14w
0x180003145  jnb     loc_18000411D
0x18000314b  and     rax, 0FFFFFFFFFFFFFFFEh
0x18000314f  cmp     rax, r14
0x180003152  jnb     loc_180004117
0x180003158  lea     rdx, [rbp+0E00h+SourceString]; SourceString
0x18000315f  mov     [rbp+rax+0E00h+SourceString], r12w
0x180003168  lea     rcx, BaseSrvWindowsDirectory; DestinationString
0x18000316f  call    cs:__imp_RtlCreateUnicodeString
0x180003176  nop     dword ptr [rax+rax+00h]
0x18000317b  test    al, al
0x18000317d  jz      loc_18000411D
0x180003183  lea     r8, aSystem32; "\\system32"
0x18000318a  mov     edx, 190h; SizeInWords
0x18000318f  lea     rcx, [rbp+0E00h+SourceString]; Destination
0x180003196  call    cs:__imp_wcscat_s
0x18000319d  nop     dword ptr [rax+rax+00h]
0x1800031a2  lea     rdx, [rbp+0E00h+SourceString]; SourceString
0x1800031a9  lea     rcx, BaseSrvWindowsSystemDirectory; DestinationString
0x1800031b0  call    cs:__imp_RtlCreateUnicodeString
0x1800031b7  nop     dword ptr [rax+rax+00h]
0x1800031bc  test    al, al
0x1800031be  jz      loc_18000411D
0x1800031c4  mov     eax, cs:SessionId
0x1800031ca  lea     rcx, [rbp+0E00h+Buffer]; Buffer
0x1800031d1  cmp     eax, cs:ServiceSessionId
0x1800031d7  mov     edx, 100h; BufferCount
0x1800031dc  jnz     short loc_1800031F3
0x1800031de  lea     r8, aBasenamedobjec; "\\BaseNamedObjects"
0x1800031e5  call    cs:__imp_wcscpy_s
0x1800031ec  nop     dword ptr [rax+rax+00h]
0x1800031f1  jmp     short loc_180003211
0x1800031f3  lea     r9, aSessions; "\\Sessions"
0x1800031fa  mov     [rsp+0F00h+Length], eax
0x1800031fe  lea     r8, aWsLdBasenamedo; "%ws\\%ld\\BaseNamedObjects"
0x180003205  call    cs:__imp_swprintf_s
0x18000320c  nop     dword ptr [rax+rax+00h]
0x180003211  mov     eax, cs:SessionId
0x180003217  lea     r9, aSessions; "\\Sessions"
0x18000321e  lea     r8, aWsLdAppcontain; "%ws\\%ld\\AppContainerNamedObjects"
0x180003225  mov     [rsp+0F00h+Length], eax
0x180003229  mov     edx, 100h; BufferCount
0x18000322e  lea     rcx, [rbp+0E00h+var_660]; Buffer
0x180003235  call    cs:__imp_swprintf_s
0x18000323c  nop     dword ptr [rax+rax+00h]
0x180003241  mov     eax, cs:SessionId
0x180003247  lea     r9, aSessions; "\\Sessions"
0x18000324e  lea     r8, aWsLdBasenamedo; "%ws\\%ld\\BaseNamedObjects"
0x180003255  mov     [rsp+0F00h+Length], eax
0x180003259  mov     edx, 100h
0x18000325e  lea     rcx, [rbp+0E00h+var_860]
0x180003265  call    RtlStringCchPrintfW
0x18000326a  lea     rdx, [rbp+0E00h+Buffer]; SourceString
0x180003271  lea     rcx, [rbp+0E00h+DestinationString]; DestinationString
0x180003275  call    cs:__imp_RtlInitUnicodeString
0x18000327c  nop     dword ptr [rax+rax+00h]
0x180003281  lea     rdx, [rbp+0E00h+var_860]; SourceString
0x180003288  lea     rcx, [rbp+0E00h+var_DF0]; DestinationString
0x18000328c  call    cs:__imp_RtlInitUnicodeString
0x180003293  nop     dword ptr [rax+rax+00h]
0x180003298  lea     rdx, [rbp+0E00h+var_660]; SourceString
0x18000329f  lea     rcx, [rbp+0E00h+Source]; DestinationString
0x1800032a3  call    cs:__imp_RtlInitUnicodeString
0x1800032aa  nop     dword ptr [rax+rax+00h]
0x1800032af  mov     edx, cs:BaseSrvSharedTag; Flags
0x1800032b5  mov     r8d, 0A00h; Size
0x1800032bb  mov     rcx, cs:BaseSrvSharedHeap; HeapHandle
0x1800032c2  call    cs:__imp_RtlAllocateHeap
0x1800032c9  nop     dword ptr [rax+rax+00h]
0x1800032ce  mov     cs:BaseSrvpStaticServerData, rax
0x1800032d5  test    rax, rax
0x1800032d8  jz      loc_18000411D
0x1800032de  mov     [rbx+60h], rax
0x1800032e2  lea     rdx, [rax+140h]; SystemInformation
0x1800032e9  xor     r9d, r9d; ReturnLength
0x1800032ec  mov     [rax+9E8h], rax
0x1800032f3  mov     dword ptr [rax+9C8h], 0FFFFFFFFh
0x1800032fd  mov     [rax+9D0h], r12d
0x180003304  lea     ecx, [r9+3]; SystemInformationClass
0x180003308  lea     r8d, [r9+30h]; SystemInformationLength
0x18000330c  call    cs:__imp_NtQuerySystemInformation
0x180003313  nop     dword ptr [rax+rax+00h]
0x180003318  mov     ebx, eax
0x18000331a  test    eax, eax
0x18000331c  js      loc_180004122
0x180003322  mov     rax, cs:BaseSrvpStaticServerData
0x180003329  movups  xmm0, xmmword ptr cs:BaseSrvWindowsDirectory.Length
0x180003330  mov     edx, cs:BaseSrvSharedTag; Flags
0x180003336  mov     rcx, cs:BaseSrvSharedHeap; HeapHandle
0x18000333d  movups  xmmword ptr [rax], xmm0
0x180003340  movzx   r8d, cs:BaseSrvWindowsDirectory.MaximumLength; Size
0x180003348  call    cs:__imp_RtlAllocateHeap
0x18000334f  nop     dword ptr [rax+rax+00h]
0x180003354  mov     rdi, rax
0x180003357  test    rax, rax
0x18000335a  jz      loc_18000411D
0x180003360  mov     rbx, cs:BaseSrvpStaticServerData
0x180003367  mov     rcx, rax; void *
0x18000336a  movzx   r8d, cs:BaseSrvWindowsDirectory.MaximumLength; Size
0x180003372  mov     rdx, [rbx+8]; Src
0x180003376  call    memcpy_0
0x18000337b  mov     edx, cs:BaseSrvSharedTag; Flags
0x180003381  mov     rcx, cs:BaseSrvSharedHeap; HeapHandle
0x180003388  mov     [rbx+8], rdi
0x18000338c  movups  xmm0, xmmword ptr cs:BaseSrvWindowsSystemDirectory.Length
0x180003393  movups  xmmword ptr [rbx+10h], xmm0
0x180003397  movzx   r8d, cs:BaseSrvWindowsSystemDirectory.MaximumLength; Size
0x18000339f  call    cs:__imp_RtlAllocateHeap
0x1800033a6  nop     dword ptr [rax+rax+00h]
0x1800033ab  mov     rdi, rax
0x1800033ae  test    rax, rax
0x1800033b1  jz      loc_18000411D
0x1800033b7  mov     rbx, cs:BaseSrvpStaticServerData
0x1800033be  mov     rcx, rax; void *
0x1800033c1  movzx   r8d, cs:BaseSrvWindowsSystemDirectory.MaximumLength; Size
0x1800033c9  mov     rdx, [rbx+18h]; Src
0x1800033cd  call    memcpy_0
0x1800033d2  mov     edx, cs:BaseSrvSharedTag; Flags
0x1800033d8  mov     rcx, cs:BaseSrvSharedHeap; HeapHandle
0x1800033df  mov     [rbx+18h], rdi
0x1800033e3  mov     [rbx+800h], r12
0x1800033ea  mov     [rbx+7F8h], r12d
0x1800033f1  movups  xmm0, xmmword ptr [rbp+0E00h+DestinationString.Length]
0x1800033f5  movups  xmmword ptr [rbx+20h], xmm0
0x1800033f9  movzx   eax, [rbp+0E00h+DestinationString.Length]
0x1800033fd  add     ax, 2
0x180003401  mov     [rbx+22h], ax
0x180003405  movzx   r8d, [rbp+0E00h+DestinationString.Length]
0x18000340a  add     r8, 2; Size
0x18000340e  call    cs:__imp_RtlAllocateHeap
0x180003415  nop     dword ptr [rax+rax+00h]
0x18000341a  mov     rdi, rax
0x18000341d  test    rax, rax
0x180003420  jz      loc_18000411D
0x180003426  mov     rbx, cs:BaseSrvpStaticServerData
0x18000342d  mov     rcx, rax; void *
0x180003430  movzx   r8d, word ptr [rbx+22h]; Size
0x180003435  mov     rdx, [rbx+28h]; Src
0x180003439  call    memcpy_0
0x18000343e  mov     edx, cs:BaseSrvSharedTag; Flags
0x180003444  mov     rcx, cs:BaseSrvSharedHeap; HeapHandle
0x18000344b  mov     [rbx+28h], rdi
0x18000344f  movups  xmm0, xmmword ptr [rbp+0E00h+Source.Length]
0x180003453  movups  xmmword ptr [rbx+9D8h], xmm0
0x18000345a  movzx   eax, [rbp+0E00h+Source.Length]
0x18000345e  add     ax, 2
0x180003462  mov     [rbx+9DAh], ax
0x180003469  movzx   r8d, [rbp+0E00h+Source.Length]
0x18000346e  add     r8, 2; Size
0x180003472  call    cs:__imp_RtlAllocateHeap
0x180003479  nop     dword ptr [rax+rax+00h]
0x18000347e  mov     rdi, rax
0x180003481  test    rax, rax
0x180003484  jz      loc_18000411D
0x18000348a  mov     rbx, cs:BaseSrvpStaticServerData
0x180003491  mov     rcx, rax; void *
0x180003494  movzx   r8d, word ptr [rbx+9DAh]; Size
0x18000349c  mov     rdx, [rbx+9E0h]; Src
0x1800034a3  call    memcpy_0
0x1800034a8  mov     edx, cs:BaseSrvSharedTag; Flags
0x1800034ae  mov     rcx, cs:BaseSrvSharedHeap; HeapHandle
0x1800034b5  mov     [rbx+9E0h], rdi
0x1800034bc  movups  xmm0, xmmword ptr [rbp+0E00h+var_DF0.Length]
0x1800034c0  movups  xmmword ptr [rbx+9F0h], xmm0
0x1800034c7  movzx   eax, [rbp+0E00h+var_DF0.Length]
0x1800034cb  add     ax, 2
0x1800034cf  mov     [rbx+9F2h], ax
0x1800034d6  movzx   r8d, [rbp+0E00h+var_DF0.Length]
0x1800034db  add     r8, 2; Size
0x1800034df  call    cs:__imp_RtlAllocateHeap
0x1800034e6  nop     dword ptr [rax+rax+00h]
0x1800034eb  mov     rdi, rax
0x1800034ee  test    rax, rax
0x1800034f1  jz      loc_18000411D
0x1800034f7  mov     rbx, cs:BaseSrvpStaticServerData
0x1800034fe  mov     rcx, rax; void *
0x180003501  movzx   r8d, word ptr [rbx+9F2h]; Size
0x180003509  mov     rdx, [rbx+9F8h]; Src
0x180003510  call    memcpy_0
0x180003515  xor     r9d, r9d
0x180003518  mov     [rbx+9F8h], rdi
0x18000351f  lea     r8, BaseServerRegistryConfigurationTable2
0x180003526  mov     [rbx+808h], r12b
0x18000352d  lea     rdx, aSessionManager_0; "Session Manager"
0x180003534  mov     qword ptr [rsp+0F00h+Length], r12
0x180003539  lea     ecx, [r9+2]
0x18000353d  call    cs:__imp_RtlQueryRegistryValuesEx
0x180003544  nop     dword ptr [rax+rax+00h]
0x180003549  mov     rax, cs:BaseSrvpStaticServerData
0x180003550  mov     [rax+36h], r12d
0x180003554  mov     [rax+3Ah], r12w
0x180003559  cmp     cs:SkipIniFileMappings, r12d
0x180003560  jnz     loc_18000363C
0x180003566  xor     r9d, r9d
0x180003569  mov     dword ptr cs:BaseSrvCSDString.Length, 0C80000h
0x180003573  lea     rax, [rbp+0E00h+var_B28]
0x18000357a  mov     qword ptr [rsp+0F00h+Length], r12
0x18000357f  lea     r8, BaseServerRegistryConfigurationTable1
0x180003586  mov     cs:BaseSrvCSDString.Buffer, rax
0x18000358d  lea     rdx, dword_18001069C
0x180003594  lea     ecx, [r9+3]
0x180003598  call    cs:__imp_RtlQueryRegistryValuesEx
  ... truncated ...
```
