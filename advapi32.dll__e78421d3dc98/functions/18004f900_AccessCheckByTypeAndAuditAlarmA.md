# AccessCheckByTypeAndAuditAlarmA

- ea: `0x18004f900`
- end: `0x18004fa83`
- name: `AccessCheckByTypeAndAuditAlarmA`
- size: `387`
- prototype: `BOOL __stdcall(LPCSTR SubsystemName, LPVOID HandleId, LPCSTR ObjectTypeName, LPCSTR ObjectName, PSECURITY_DESCRIPTOR SecurityDescriptor, PSID PrincipalSelfSid, DWORD DesiredAccess, AUDIT_EVENT_TYPE AuditType, DWORD Flags, POBJECT_TYPE_LIST ObjectTypeList, DWORD ObjectTypeListLength, PGENERIC_MAPPING GenericMapping, BOOL ObjectCreation, LPDWORD GrantedAccess, LPBOOL AccessStatus, LPBOOL pfGenerateOnClose)`
- caller_count: `0`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18004f900`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18004f990`
- `ntdll!RtlFreeUnicodeString` at `0x18004f9c5`
- `ntdll!RtlFreeUnicodeString` at `0x18004fa63`
- `ntdll!RtlFreeUnicodeString` at `0x18004fa6d`
- `ntdll!RtlFreeUnicodeString` at `0x18004f990`
- `ntdll!RtlFreeUnicodeString` at `0x18004f9c5`
- `ntdll!RtlFreeUnicodeString` at `0x18004fa63`
- `ntdll!RtlFreeUnicodeString` at `0x18004fa6d`
- `ntdll!RtlInitAnsiString` at `0x18004f93e`
- `ntdll!RtlInitAnsiString` at `0x18004f96f`
- `ntdll!RtlInitAnsiString` at `0x18004f9a1`
- `ntdll!RtlInitAnsiString` at `0x18004f93e`
- `ntdll!RtlInitAnsiString` at `0x18004f96f`
- `ntdll!RtlInitAnsiString` at `0x18004f9a1`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18004f94f`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18004f980`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18004f9b5`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18004f94f`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18004f980`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18004f9b5`
- `api-ms-win-security-base-l1-1-0!AccessCheckByTypeAndAuditAlarmW` at `0x18004fa57`
- `api-ms-win-security-base-l1-1-0!AccessCheckByTypeAndAuditAlarmW` at `0x18004fa57`
- `KERNEL32!BaseSetLastNTError` at `0x18004f95b`
- `KERNEL32!BaseSetLastNTError` at `0x18004f95b`

## pseudocode

```c
BOOL __stdcall AccessCheckByTypeAndAuditAlarmA(
        LPCSTR SubsystemName,
        LPVOID HandleId,
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
        LPBOOL AccessStatus,
        LPBOOL pfGenerateOnClose)
{
  struct _TEB *v19; // rdi
  NTSTATUS v20; // eax
  __int64 v21; // rcx
  NTSTATUS v23; // ebx
  struct _UNICODE_STRING *p_UnicodeString; // rcx
  BOOL v25; // ebx
  struct _STRING DestinationString; // [rsp+80h] [rbp-29h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+90h] [rbp-19h] BYREF
  struct _UNICODE_STRING v28; // [rsp+A0h] [rbp-9h] BYREF

  DestinationString = 0;
  UnicodeString = 0;
  v28 = 0;
  v19 = NtCurrentTeb();
  RtlInitAnsiString(&DestinationString, SubsystemName);
  v20 = RtlAnsiStringToUnicodeString(&UnicodeString, &DestinationString, 1u);
  if ( v20 < 0 )
  {
    v21 = (unsigned int)v20;
LABEL_3:
    BaseSetLastNTError(v21);
    return 0;
  }
  RtlInitAnsiString(&DestinationString, ObjectTypeName);
  v23 = RtlAnsiStringToUnicodeString(&v28, &DestinationString, 1u);
  if ( v23 < 0 )
  {
    p_UnicodeString = &UnicodeString;
LABEL_6:
    RtlFreeUnicodeString(p_UnicodeString);
    v21 = (unsigned int)v23;
    goto LABEL_3;
  }
  RtlInitAnsiString(&DestinationString, ObjectName);
  v23 = RtlAnsiStringToUnicodeString(&v19->StaticUnicodeString, &DestinationString, 0);
  if ( v23 < 0 )
  {
    RtlFreeUnicodeString(&UnicodeString);
    p_UnicodeString = &v28;
    goto LABEL_6;
  }
  v25 = AccessCheckByTypeAndAuditAlarmW(
          UnicodeString.Buffer,
          HandleId,
          v28.Buffer,
          v19->StaticUnicodeString.Buffer,
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
          AccessStatus,
          pfGenerateOnClose);
  RtlFreeUnicodeString(&UnicodeString);
  RtlFreeUnicodeString(&v28);
  return v25;
}

```

## disassembly

```asm
0x18004f900  push    rbp
0x18004f902  push    rbx
0x18004f903  push    rsi
0x18004f904  push    rdi
0x18004f905  push    r14
0x18004f907  lea     rbp, [rsp-7]
0x18004f90c  sub     rsp, 0B0h
0x18004f913  xorps   xmm0, xmm0
0x18004f916  mov     r14, rdx
0x18004f919  xorps   xmm1, xmm1
0x18004f91c  mov     rdx, rcx; SourceString
0x18004f91f  movups  xmmword ptr [rbp+27h+DestinationString.Length], xmm0
0x18004f923  lea     rcx, [rbp+27h+DestinationString]; DestinationString
0x18004f927  mov     rsi, r9
0x18004f92a  movups  xmmword ptr [rbp+27h+UnicodeString.Length], xmm1
0x18004f92e  mov     rbx, r8
0x18004f931  movups  xmmword ptr [rbp+27h+var_30.Length], xmm0
0x18004f935  mov     rdi, gs:30h
0x18004f93e  call    cs:__imp_RtlInitAnsiString
0x18004f944  mov     r8b, 1; AllocateDestinationString
0x18004f947  lea     rdx, [rbp+27h+DestinationString]; SourceString
0x18004f94b  lea     rcx, [rbp+27h+UnicodeString]; DestinationString
0x18004f94f  call    cs:__imp_RtlAnsiStringToUnicodeString
0x18004f955  test    eax, eax
0x18004f957  jns     short loc_18004F968
0x18004f959  mov     ecx, eax
0x18004f95b  call    cs:__imp_BaseSetLastNTError
0x18004f961  xor     eax, eax
0x18004f963  jmp     loc_18004FA75
0x18004f968  mov     rdx, rbx; SourceString
0x18004f96b  lea     rcx, [rbp+27h+DestinationString]; DestinationString
0x18004f96f  call    cs:__imp_RtlInitAnsiString
0x18004f975  mov     r8b, 1; AllocateDestinationString
0x18004f978  lea     rdx, [rbp+27h+DestinationString]; SourceString
0x18004f97c  lea     rcx, [rbp+27h+var_30]; DestinationString
0x18004f980  call    cs:__imp_RtlAnsiStringToUnicodeString
0x18004f986  mov     ebx, eax
0x18004f988  test    eax, eax
0x18004f98a  jns     short loc_18004F99A
0x18004f98c  lea     rcx, [rbp+27h+UnicodeString]; UnicodeString
0x18004f990  call    cs:__imp_RtlFreeUnicodeString
0x18004f996  mov     ecx, ebx
0x18004f998  jmp     short loc_18004F95B
0x18004f99a  mov     rdx, rsi; SourceString
0x18004f99d  lea     rcx, [rbp+27h+DestinationString]; DestinationString
0x18004f9a1  call    cs:__imp_RtlInitAnsiString
0x18004f9a7  xor     r8d, r8d; AllocateDestinationString
0x18004f9aa  lea     rdx, [rbp+27h+DestinationString]; SourceString
0x18004f9ae  lea     rcx, [rdi+1258h]; DestinationString
0x18004f9b5  call    cs:__imp_RtlAnsiStringToUnicodeString
0x18004f9bb  mov     ebx, eax
0x18004f9bd  test    eax, eax
0x18004f9bf  jns     short loc_18004F9D1
0x18004f9c1  lea     rcx, [rbp+27h+UnicodeString]; UnicodeString
0x18004f9c5  call    cs:__imp_RtlFreeUnicodeString
0x18004f9cb  lea     rcx, [rbp+27h+var_30]
0x18004f9cf  jmp     short loc_18004F990
0x18004f9d1  mov     rax, [rbp+27h+pfGenerateOnClose]
0x18004f9d8  mov     rdx, r14; HandleId
0x18004f9db  mov     r9, [rdi+1260h]; ObjectName
0x18004f9e2  mov     r8, [rbp+27h+var_30.Buffer]; ObjectTypeName
0x18004f9e6  mov     rcx, [rbp+27h+UnicodeString.Buffer]; SubsystemName
0x18004f9ea  mov     [rsp+0D0h+var_58], rax; pfGenerateOnClose
0x18004f9ef  mov     rax, [rbp+27h+AccessStatus]
0x18004f9f6  mov     [rsp+0D0h+var_60], rax; AccessStatus
0x18004f9fb  mov     rax, [rbp+27h+GrantedAccess]
0x18004fa02  mov     [rsp+0D0h+var_68], rax; GrantedAccess
0x18004fa07  mov     eax, [rbp+27h+ObjectCreation]
0x18004fa0d  mov     [rsp+0D0h+var_70], eax; ObjectCreation
0x18004fa11  mov     rax, [rbp+27h+GenericMapping]
0x18004fa18  mov     [rsp+0D0h+var_78], rax; GenericMapping
0x18004fa1d  mov     eax, [rbp+27h+ObjectTypeListLength]
0x18004fa23  mov     [rsp+0D0h+var_80], eax; ObjectTypeListLength
0x18004fa27  mov     rax, [rbp+27h+ObjectTypeList]
0x18004fa2b  mov     [rsp+0D0h+var_88], rax; ObjectTypeList
0x18004fa30  mov     eax, [rbp+27h+Flags]
0x18004fa33  mov     [rsp+0D0h+var_90], eax; Flags
0x18004fa37  mov     eax, [rbp+27h+AuditType]
0x18004fa3a  mov     [rsp+0D0h+var_98], eax; AuditType
0x18004fa3e  mov     eax, [rbp+27h+DesiredAccess]
0x18004fa41  mov     [rsp+0D0h+var_A0], eax; DesiredAccess
0x18004fa45  mov     rax, [rbp+27h+PrincipalSelfSid]
0x18004fa49  mov     [rsp+0D0h+var_A8], rax; PrincipalSelfSid
0x18004fa4e  mov     rax, [rbp+27h+SecurityDescriptor]
0x18004fa52  mov     [rsp+0D0h+var_B0], rax; SecurityDescriptor
0x18004fa57  call    cs:__imp_AccessCheckByTypeAndAuditAlarmW
0x18004fa5d  lea     rcx, [rbp+27h+UnicodeString]; UnicodeString
0x18004fa61  mov     ebx, eax
0x18004fa63  call    cs:__imp_RtlFreeUnicodeString
0x18004fa69  lea     rcx, [rbp+27h+var_30]; UnicodeString
0x18004fa6d  call    cs:__imp_RtlFreeUnicodeString
0x18004fa73  mov     eax, ebx
0x18004fa75  add     rsp, 0B0h
0x18004fa7c  pop     r14
0x18004fa7e  pop     rdi
0x18004fa7f  pop     rsi
0x18004fa80  pop     rbx
0x18004fa81  pop     rbp
0x18004fa82  retn
```
