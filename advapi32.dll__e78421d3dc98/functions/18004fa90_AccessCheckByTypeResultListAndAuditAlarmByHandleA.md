# AccessCheckByTypeResultListAndAuditAlarmByHandleA

- ea: `0x18004fa90`
- end: `0x18004fc22`
- name: `AccessCheckByTypeResultListAndAuditAlarmByHandleA`
- size: `402`
- prototype: `BOOL __stdcall(LPCSTR SubsystemName, LPVOID HandleId, HANDLE ClientToken, LPCSTR ObjectTypeName, LPCSTR ObjectName, PSECURITY_DESCRIPTOR SecurityDescriptor, PSID PrincipalSelfSid, DWORD DesiredAccess, AUDIT_EVENT_TYPE AuditType, DWORD Flags, POBJECT_TYPE_LIST ObjectTypeList, DWORD ObjectTypeListLength, PGENERIC_MAPPING GenericMapping, BOOL ObjectCreation, LPDWORD GrantedAccess, LPDWORD AccessStatusList, LPBOOL pfGenerateOnClose)`
- caller_count: `0`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18004fa90`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18004fb20`
- `ntdll!RtlFreeUnicodeString` at `0x18004fb56`
- `ntdll!RtlFreeUnicodeString` at `0x18004fc02`
- `ntdll!RtlFreeUnicodeString` at `0x18004fc0c`
- `ntdll!RtlFreeUnicodeString` at `0x18004fb20`
- `ntdll!RtlFreeUnicodeString` at `0x18004fb56`
- `ntdll!RtlFreeUnicodeString` at `0x18004fc02`
- `ntdll!RtlFreeUnicodeString` at `0x18004fc0c`
- `ntdll!RtlInitAnsiString` at `0x18004face`
- `ntdll!RtlInitAnsiString` at `0x18004faff`
- `ntdll!RtlInitAnsiString` at `0x18004fb32`
- `ntdll!RtlInitAnsiString` at `0x18004face`
- `ntdll!RtlInitAnsiString` at `0x18004faff`
- `ntdll!RtlInitAnsiString` at `0x18004fb32`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18004fadf`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18004fb10`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18004fb46`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18004fadf`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18004fb10`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18004fb46`
- `api-ms-win-security-base-l1-1-0!AccessCheckByTypeResultListAndAuditAlarmByHandleW` at `0x18004fbf6`
- `api-ms-win-security-base-l1-1-0!AccessCheckByTypeResultListAndAuditAlarmByHandleW` at `0x18004fbf6`
- `KERNEL32!BaseSetLastNTError` at `0x18004faeb`
- `KERNEL32!BaseSetLastNTError` at `0x18004faeb`

## pseudocode

```c
BOOL __stdcall AccessCheckByTypeResultListAndAuditAlarmByHandleA(
        LPCSTR SubsystemName,
        LPVOID HandleId,
        HANDLE ClientToken,
        LPCSTR ObjectTypeName,
        LPCSTR ObjectName,
        PSECURITY_DESCRIPTOR SecurityDescriptor,
        PSID PrincipalSelfSid,
        DWORD DesiredAccess,
        AUDIT_EVENT_TYPE AuditType,
        DWORD Flags,
        POBJECT_TYPE_LIST ObjectTypeList,
        DWORD ObjectTypeListLength,
        PGENERIC_MAPPING GenericMapping,
        BOOL ObjectCreation,
        LPDWORD GrantedAccess,
        LPDWORD AccessStatusList,
        LPBOOL pfGenerateOnClose)
{
  struct _TEB *v20; // rdi
  NTSTATUS v21; // eax
  __int64 v22; // rcx
  NTSTATUS v24; // ebx
  struct _UNICODE_STRING *p_UnicodeString; // rcx
  BOOL v26; // ebx
  struct _STRING DestinationString; // [rsp+90h] [rbp-29h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+A0h] [rbp-19h] BYREF
  struct _UNICODE_STRING v29; // [rsp+B0h] [rbp-9h] BYREF

  DestinationString = 0;
  UnicodeString = 0;
  v29 = 0;
  v20 = NtCurrentTeb();
  RtlInitAnsiString(&DestinationString, SubsystemName);
  v21 = RtlAnsiStringToUnicodeString(&UnicodeString, &DestinationString, 1u);
  if ( v21 < 0 )
  {
    v22 = (unsigned int)v21;
LABEL_3:
    BaseSetLastNTError(v22);
    return 0;
  }
  RtlInitAnsiString(&DestinationString, ObjectTypeName);
  v24 = RtlAnsiStringToUnicodeString(&v29, &DestinationString, 1u);
  if ( v24 < 0 )
  {
    p_UnicodeString = &UnicodeString;
LABEL_6:
    RtlFreeUnicodeString(p_UnicodeString);
    v22 = (unsigned int)v24;
    goto LABEL_3;
  }
  RtlInitAnsiString(&DestinationString, ObjectName);
  v24 = RtlAnsiStringToUnicodeString(&v20->StaticUnicodeString, &DestinationString, 0);
  if ( v24 < 0 )
  {
    RtlFreeUnicodeString(&UnicodeString);
    p_UnicodeString = &v29;
    goto LABEL_6;
  }
  v26 = AccessCheckByTypeResultListAndAuditAlarmByHandleW(
          UnicodeString.Buffer,
          HandleId,
          ClientToken,
          v29.Buffer,
          v20->StaticUnicodeString.Buffer,
          SecurityDescriptor,
          PrincipalSelfSid,
          DesiredAccess,
          AuditType,
          Flags,
          ObjectTypeList,
          ObjectTypeListLength,
          GenericMapping,
          ObjectCreation,
          GrantedAccess,
          AccessStatusList,
          pfGenerateOnClose);
  RtlFreeUnicodeString(&UnicodeString);
  RtlFreeUnicodeString(&v29);
  return v26;
}

```

## disassembly

```asm
0x18004fa90  push    rbp
0x18004fa92  push    rbx
0x18004fa93  push    rsi
0x18004fa94  push    rdi
0x18004fa95  push    r14
0x18004fa97  lea     rbp, [rsp-7]
0x18004fa9c  sub     rsp, 0C0h
0x18004faa3  xorps   xmm0, xmm0
0x18004faa6  mov     r14, rdx
0x18004faa9  xorps   xmm1, xmm1
0x18004faac  mov     rdx, rcx; SourceString
0x18004faaf  movups  xmmword ptr [rbp+27h+DestinationString.Length], xmm0
0x18004fab3  lea     rcx, [rbp+27h+DestinationString]; DestinationString
0x18004fab7  mov     rbx, r9
0x18004faba  movups  xmmword ptr [rbp+27h+UnicodeString.Length], xmm1
0x18004fabe  mov     rsi, r8
0x18004fac1  movups  xmmword ptr [rbp+27h+var_30.Length], xmm0
0x18004fac5  mov     rdi, gs:30h
0x18004face  call    cs:__imp_RtlInitAnsiString
0x18004fad4  mov     r8b, 1; AllocateDestinationString
0x18004fad7  lea     rdx, [rbp+27h+DestinationString]; SourceString
0x18004fadb  lea     rcx, [rbp+27h+UnicodeString]; DestinationString
0x18004fadf  call    cs:__imp_RtlAnsiStringToUnicodeString
0x18004fae5  test    eax, eax
0x18004fae7  jns     short loc_18004FAF8
0x18004fae9  mov     ecx, eax
0x18004faeb  call    cs:__imp_BaseSetLastNTError
0x18004faf1  xor     eax, eax
0x18004faf3  jmp     loc_18004FC14
0x18004faf8  mov     rdx, rbx; SourceString
0x18004fafb  lea     rcx, [rbp+27h+DestinationString]; DestinationString
0x18004faff  call    cs:__imp_RtlInitAnsiString
0x18004fb05  mov     r8b, 1; AllocateDestinationString
0x18004fb08  lea     rdx, [rbp+27h+DestinationString]; SourceString
0x18004fb0c  lea     rcx, [rbp+27h+var_30]; DestinationString
0x18004fb10  call    cs:__imp_RtlAnsiStringToUnicodeString
0x18004fb16  mov     ebx, eax
0x18004fb18  test    eax, eax
0x18004fb1a  jns     short loc_18004FB2A
0x18004fb1c  lea     rcx, [rbp+27h+UnicodeString]; UnicodeString
0x18004fb20  call    cs:__imp_RtlFreeUnicodeString
0x18004fb26  mov     ecx, ebx
0x18004fb28  jmp     short loc_18004FAEB
0x18004fb2a  mov     rdx, [rbp+27h+ObjectName]; SourceString
0x18004fb2e  lea     rcx, [rbp+27h+DestinationString]; DestinationString
0x18004fb32  call    cs:__imp_RtlInitAnsiString
0x18004fb38  xor     r8d, r8d; AllocateDestinationString
0x18004fb3b  lea     rdx, [rbp+27h+DestinationString]; SourceString
0x18004fb3f  lea     rcx, [rdi+1258h]; DestinationString
0x18004fb46  call    cs:__imp_RtlAnsiStringToUnicodeString
0x18004fb4c  mov     ebx, eax
0x18004fb4e  test    eax, eax
0x18004fb50  jns     short loc_18004FB62
0x18004fb52  lea     rcx, [rbp+27h+UnicodeString]; UnicodeString
0x18004fb56  call    cs:__imp_RtlFreeUnicodeString
0x18004fb5c  lea     rcx, [rbp+27h+var_30]
0x18004fb60  jmp     short loc_18004FB20
0x18004fb62  mov     rax, [rbp+27h+pfGenerateOnClose]
0x18004fb69  mov     r8, rsi; ClientToken
0x18004fb6c  mov     r9, [rbp+27h+var_30.Buffer]; ObjectTypeName
0x18004fb70  mov     rdx, r14; HandleId
0x18004fb73  mov     rcx, [rbp+27h+UnicodeString.Buffer]; SubsystemName
0x18004fb77  mov     [rsp+0E0h+var_60], rax; pfGenerateOnClose
0x18004fb7f  mov     rax, [rbp+27h+AccessStatusList]
0x18004fb86  mov     [rsp+0E0h+var_68], rax; AccessStatusList
0x18004fb8b  mov     rax, [rbp+27h+GrantedAccess]
0x18004fb92  mov     [rsp+0E0h+GrantedAccessList], rax; GrantedAccessList
0x18004fb97  mov     eax, [rbp+27h+ObjectCreation]
0x18004fb9d  mov     [rsp+0E0h+var_78], eax; ObjectCreation
0x18004fba1  mov     rax, [rbp+27h+GenericMapping]
0x18004fba8  mov     [rsp+0E0h+var_80], rax; GenericMapping
0x18004fbad  mov     eax, [rbp+27h+ObjectTypeListLength]
0x18004fbb3  mov     [rsp+0E0h+var_88], eax; ObjectTypeListLength
0x18004fbb7  mov     rax, [rbp+27h+ObjectTypeList]
0x18004fbbe  mov     [rsp+0E0h+var_90], rax; ObjectTypeList
0x18004fbc3  mov     eax, [rbp+27h+Flags]
0x18004fbc6  mov     [rsp+0E0h+var_98], eax; Flags
0x18004fbca  mov     eax, [rbp+27h+AuditType]
0x18004fbcd  mov     [rsp+0E0h+var_A0], eax; AuditType
0x18004fbd1  mov     eax, [rbp+27h+DesiredAccess]
0x18004fbd4  mov     [rsp+0E0h+var_A8], eax; DesiredAccess
0x18004fbd8  mov     rax, [rbp+27h+PrincipalSelfSid]
0x18004fbdc  mov     [rsp+0E0h+var_B0], rax; PrincipalSelfSid
0x18004fbe1  mov     rax, [rbp+27h+SecurityDescriptor]
0x18004fbe5  mov     [rsp+0E0h+var_B8], rax; SecurityDescriptor
0x18004fbea  mov     rax, [rdi+1260h]
0x18004fbf1  mov     [rsp+0E0h+var_C0], rax; ObjectName
0x18004fbf6  call    cs:__imp_AccessCheckByTypeResultListAndAuditAlarmByHandleW
0x18004fbfc  lea     rcx, [rbp+27h+UnicodeString]; UnicodeString
0x18004fc00  mov     ebx, eax
0x18004fc02  call    cs:__imp_RtlFreeUnicodeString
0x18004fc08  lea     rcx, [rbp+27h+var_30]; UnicodeString
0x18004fc0c  call    cs:__imp_RtlFreeUnicodeString
0x18004fc12  mov     eax, ebx
0x18004fc14  add     rsp, 0C0h
0x18004fc1b  pop     r14
0x18004fc1d  pop     rdi
0x18004fc1e  pop     rsi
0x18004fc1f  pop     rbx
0x18004fc20  pop     rbp
0x18004fc21  retn
```
