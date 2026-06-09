# NetrWorkstationStatisticsGet

- ea: `0x18000abe0`
- end: `0x18000ad87`
- name: `NetrWorkstationStatisticsGet`
- size: `423`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180007c80`
- `0x18000abe0`
- `0x18000ad90`

## import_xrefs

- `ntdll!RtlAdjustPrivilege` at `0x18000ac77`
- `ntdll!RtlAdjustPrivilege` at `0x18000ac77`
- `ntdll!NtAccessCheckAndAuditAlarm` at `0x18000ace0`
- `ntdll!NtAccessCheckAndAuditAlarm` at `0x18000ace0`
- `ntdll!RtlInitUnicodeString` at `0x18000ac38`
- `ntdll!RtlInitUnicodeString` at `0x18000ac4d`
- `ntdll!RtlInitUnicodeString` at `0x18000ac5f`
- `ntdll!RtlInitUnicodeString` at `0x18000ac38`
- `ntdll!RtlInitUnicodeString` at `0x18000ac4d`
- `ntdll!RtlInitUnicodeString` at `0x18000ac5f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ad02`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ad02`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ad78`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ad78`
- `RPCRT4!RpcImpersonateClient` at `0x18000ac7f`
- `RPCRT4!RpcImpersonateClient` at `0x18000ac7f`
- `RPCRT4!RpcRevertToSelf` at `0x18000ace8`
- `RPCRT4!RpcRevertToSelf` at `0x18000ace8`

## string_xrefs

- `0x18000ac3e`: `WkstaConfigurationInfo`

## pseudocode

```c
__int64 __fastcall NetrWorkstationStatisticsGet(__int64 a1, __int64 a2, int a3, int a4, _QWORD *a5)
{
  PSECURITY_DESCRIPTOR SecurityDescriptor; // rbx
  NTSTATUS v6; // ebx
  HLOCAL v7; // rax
  void *v8; // rbx
  NTSTATUS StatisticsFromRedir; // edi
  unsigned __int8 GenerateOnClose[4]; // [rsp+60h] [rbp-48h] BYREF
  int AccessStatus; // [rsp+64h] [rbp-44h] BYREF
  DWORD GrantedAccess; // [rsp+68h] [rbp-40h] BYREF
  struct _UNICODE_STRING ObjectName; // [rsp+70h] [rbp-38h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-28h] BYREF
  struct _UNICODE_STRING SubsystemName; // [rsp+90h] [rbp-18h] BYREF
  unsigned __int8 OldValue; // [rsp+C0h] [rbp+18h] BYREF

  if ( a3 )
    return 124;
  if ( a4 )
    return 87;
  SecurityDescriptor = ConfigurationInfoSd;
  OldValue = 0;
  GrantedAccess = 0;
  GenerateOnClose[0] = 0;
  AccessStatus = 0;
  SubsystemName = 0;
  DestinationString = 0;
  ObjectName = 0;
  RtlInitUnicodeString(&SubsystemName, L"Workstation");
  RtlInitUnicodeString(&DestinationString, L"WkstaConfigurationInfo");
  RtlInitUnicodeString(&ObjectName, L"-");
  RtlAdjustPrivilege(0x15u, 1u, 0, &OldValue);
  if ( RpcImpersonateClient(0) )
    return 5;
  v6 = NtAccessCheckAndAuditAlarm(
         &SubsystemName,
         0,
         &DestinationString,
         &ObjectName,
         SecurityDescriptor,
         2u,
         &WsConfigInfoMapping,
         0,
         &GrantedAccess,
         &AccessStatus,
         GenerateOnClose);
  RpcRevertToSelf();
  if ( v6 < 0 || AccessStatus )
    return 5;
  v7 = LocalAlloc(0x40u, 0xD8u);
  v8 = v7;
  if ( !v7 )
    return 8;
  StatisticsFromRedir = GetStatisticsFromRedir(v7);
  if ( StatisticsFromRedir < 0 )
  {
    LocalFree(v8);
    return NetpNtStatusToApiStatus(StatisticsFromRedir);
  }
  else
  {
    *a5 = v8;
    return 0;
  }
}

```

## disassembly

```asm
0x18000abe0  mov     rax, rsp
0x18000abe3  sub     rsp, 0A8h
0x18000abea  test    r8d, r8d
0x18000abed  jnz     loc_18000AD61
0x18000abf3  test    r9d, r9d
0x18000abf6  jnz     loc_18000AD6E
0x18000abfc  mov     [rax+8], rbx
0x18000ac00  lea     rdx, SourceName; "Workstation"
0x18000ac07  mov     rbx, cs:ConfigurationInfoSd
0x18000ac0e  lea     rcx, [rax-18h]; DestinationString
0x18000ac12  xorps   xmm0, xmm0
0x18000ac15  mov     [rax+10h], rsi
0x18000ac19  xor     esi, esi
0x18000ac1b  mov     [rax+18h], r9b
0x18000ac1f  xorps   xmm1, xmm1
0x18000ac22  mov     [rax-40h], esi
0x18000ac25  mov     [rax-48h], sil
0x18000ac29  mov     [rax-44h], esi
0x18000ac2c  movups  xmmword ptr [rax-18h], xmm0
0x18000ac30  movups  xmmword ptr [rax-28h], xmm1
0x18000ac34  movups  xmmword ptr [rax-38h], xmm0
0x18000ac38  call    cs:__imp_RtlInitUnicodeString
0x18000ac3e  lea     rdx, aWkstaconfigura; "WkstaConfigurationInfo"
0x18000ac45  lea     rcx, [rsp+0A8h+DestinationString]; DestinationString
0x18000ac4d  call    cs:__imp_RtlInitUnicodeString
0x18000ac53  lea     rdx, asc_18003AB90; "-"
0x18000ac5a  lea     rcx, [rsp+0A8h+ObjectName]; DestinationString
0x18000ac5f  call    cs:__imp_RtlInitUnicodeString
0x18000ac65  lea     r9, [rsp+0A8h+OldValue]; OldValue
0x18000ac6d  xor     r8d, r8d; ForThread
0x18000ac70  mov     dl, 1; NewValue
0x18000ac72  mov     ecx, 15h; Privilege
0x18000ac77  call    cs:__imp_RtlAdjustPrivilege
0x18000ac7d  xor     ecx, ecx; BindingHandle
0x18000ac7f  call    cs:__imp_RpcImpersonateClient
0x18000ac85  test    eax, eax
0x18000ac87  jnz     loc_18000AD5A
0x18000ac8d  lea     rax, [rsp+0A8h+var_48]
0x18000ac92  xor     edx, edx; HandleId
0x18000ac94  mov     [rsp+0A8h+GenerateOnClose], rax; GenerateOnClose
0x18000ac99  lea     r9, [rsp+0A8h+ObjectName]; ObjectName
0x18000ac9e  lea     rax, [rsp+0A8h+var_44]
0x18000aca3  mov     [rsp+0A8h+AccessStatus], rax; AccessStatus
0x18000aca8  lea     r8, [rsp+0A8h+DestinationString]; ObjectTypeName
0x18000acb0  lea     rax, [rsp+0A8h+var_40]
0x18000acb5  mov     [rsp+0A8h+GrantedAccess], rax; GrantedAccess
0x18000acba  lea     rcx, [rsp+0A8h+SubsystemName]; SubsystemName
0x18000acc2  mov     [rsp+0A8h+ObjectCreation], sil; ObjectCreation
0x18000acc7  lea     rax, WsConfigInfoMapping
0x18000acce  mov     [rsp+0A8h+GenericMapping], rax; GenericMapping
0x18000acd3  mov     [rsp+0A8h+DesiredAccess], 2; DesiredAccess
0x18000acdb  mov     [rsp+0A8h+SecurityDescriptor], rbx; SecurityDescriptor
0x18000ace0  call    cs:__imp_NtAccessCheckAndAuditAlarm
0x18000ace6  mov     ebx, eax
0x18000ace8  call    cs:__imp_RpcRevertToSelf
0x18000acee  test    ebx, ebx
0x18000acf0  js      short loc_18000AD5A
0x18000acf2  cmp     [rsp+0A8h+var_44], esi
0x18000acf6  jnz     short loc_18000AD5A
0x18000acf8  mov     edx, 0D8h; uBytes
0x18000acfd  mov     ecx, 40h ; '@'; uFlags
0x18000ad02  call    cs:__imp_LocalAlloc
0x18000ad08  mov     rbx, rax
0x18000ad0b  test    rax, rax
0x18000ad0e  jz      short loc_18000AD53
0x18000ad10  mov     rcx, rax; OutputBuffer
0x18000ad13  mov     [rsp+0A8h+var_8], rdi
0x18000ad1b  call    GetStatisticsFromRedir
0x18000ad20  mov     edi, eax
0x18000ad22  test    eax, eax
0x18000ad24  js      short loc_18000AD75
0x18000ad26  mov     rax, [rsp+0A8h+arg_20]
0x18000ad2e  mov     [rax], rbx
0x18000ad31  mov     eax, esi
0x18000ad33  mov     rdi, [rsp+0A8h+var_8]
0x18000ad3b  mov     rbx, [rsp+0A8h+arg_0]
0x18000ad43  mov     rsi, [rsp+0A8h+arg_8]
0x18000ad4b  add     rsp, 0A8h
0x18000ad52  retn
0x18000ad53  mov     eax, 8
0x18000ad58  jmp     short loc_18000AD3B
0x18000ad5a  mov     eax, 5
0x18000ad5f  jmp     short loc_18000AD3B
0x18000ad61  mov     eax, 7Ch ; '|'
0x18000ad66  add     rsp, 0A8h
0x18000ad6d  retn
0x18000ad6e  mov     eax, 57h ; 'W'
0x18000ad73  jmp     short loc_18000AD4B
0x18000ad75  mov     rcx, rbx; hMem
0x18000ad78  call    cs:__imp_LocalFree
0x18000ad7e  mov     ecx, edi; Status
0x18000ad80  call    NetpNtStatusToApiStatus
0x18000ad85  jmp     short loc_18000AD33
```
