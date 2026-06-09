# AccessCheckByTypeResultListAndAuditAlarmA

- ea: `0x180031f60`
- end: `0x1800320ec`
- name: `AccessCheckByTypeResultListAndAuditAlarmA`
- size: `396`
- prototype: `BOOL __stdcall(LPCSTR SubsystemName, LPVOID HandleId, LPCSTR ObjectTypeName, LPCSTR ObjectName, PSECURITY_DESCRIPTOR SecurityDescriptor, PSID PrincipalSelfSid, DWORD DesiredAccess, AUDIT_EVENT_TYPE AuditType, DWORD Flags, POBJECT_TYPE_LIST ObjectTypeList, DWORD ObjectTypeListLength, PGENERIC_MAPPING GenericMapping, BOOL ObjectCreation, LPDWORD GrantedAccess, LPDWORD AccessStatusList, LPBOOL pfGenerateOnClose)`
- caller_count: `0`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180031f60`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x1800320a2`
- `ntdll!RtlFreeUnicodeString` at `0x1800320ac`
- `ntdll!RtlFreeUnicodeString` at `0x1800320c6`
- `ntdll!RtlFreeUnicodeString` at `0x1800320d0`
- `ntdll!RtlFreeUnicodeString` at `0x1800320a2`
- `ntdll!RtlFreeUnicodeString` at `0x1800320ac`
- `ntdll!RtlFreeUnicodeString` at `0x1800320c6`
- `ntdll!RtlFreeUnicodeString` at `0x1800320d0`
- `ntdll!RtlInitAnsiString` at `0x180031f9e`
- `ntdll!RtlInitAnsiString` at `0x180031fc4`
- `ntdll!RtlInitAnsiString` at `0x180031fec`
- `ntdll!RtlInitAnsiString` at `0x180031f9e`
- `ntdll!RtlInitAnsiString` at `0x180031fc4`
- `ntdll!RtlInitAnsiString` at `0x180031fec`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180031faf`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180031fd5`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180032000`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180031faf`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180031fd5`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180032000`
- `api-ms-win-security-base-l1-1-0!AccessCheckByTypeResultListAndAuditAlarmW` at `0x180032096`
- `api-ms-win-security-base-l1-1-0!AccessCheckByTypeResultListAndAuditAlarmW` at `0x180032096`
- `KERNEL32!BaseSetLastNTError` at `0x1800320d8`
- `KERNEL32!BaseSetLastNTError` at `0x1800320d8`

## pseudocode

```c
BOOL __stdcall AccessCheckByTypeResultListAndAuditAlarmA(
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
        LPDWORD AccessStatusList,
        LPBOOL pfGenerateOnClose)
{
  struct _TEB *v19; // rdi
  NTSTATUS v20; // eax
  NTSTATUS v21; // ebx
  BOOL v22; // ebx
  struct _UNICODE_STRING *p_UnicodeString; // rcx
  __int64 v25; // rcx
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
    v25 = (unsigned int)v20;
  }
  else
  {
    RtlInitAnsiString(&DestinationString, ObjectTypeName);
    v21 = RtlAnsiStringToUnicodeString(&v28, &DestinationString, 1u);
    if ( v21 < 0 )
    {
      p_UnicodeString = &UnicodeString;
    }
    else
    {
      RtlInitAnsiString(&DestinationString, ObjectName);
      v21 = RtlAnsiStringToUnicodeString(&v19->StaticUnicodeString, &DestinationString, 0);
      if ( v21 >= 0 )
      {
        v22 = AccessCheckByTypeResultListAndAuditAlarmW(
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
                AccessStatusList,
                pfGenerateOnClose);
        RtlFreeUnicodeString(&UnicodeString);
        RtlFreeUnicodeString(&v28);
        return v22;
      }
      RtlFreeUnicodeString(&UnicodeString);
      p_UnicodeString = &v28;
    }
    RtlFreeUnicodeString(p_UnicodeString);
    v25 = (unsigned int)v21;
  }
  BaseSetLastNTError(v25);
  return 0;
}

```

## disassembly

```asm
0x180031f60  push    rbp
0x180031f62  push    rbx
0x180031f63  push    rsi
0x180031f64  push    rdi
0x180031f65  push    r14
0x180031f67  lea     rbp, [rsp-7]
0x180031f6c  sub     rsp, 0B0h
0x180031f73  xorps   xmm0, xmm0
0x180031f76  mov     r14, rdx
0x180031f79  xorps   xmm1, xmm1
0x180031f7c  mov     rdx, rcx; SourceString
0x180031f7f  movups  xmmword ptr [rbp+27h+DestinationString.Length], xmm0
0x180031f83  lea     rcx, [rbp+27h+DestinationString]; DestinationString
0x180031f87  mov     rsi, r9
0x180031f8a  movups  xmmword ptr [rbp+27h+UnicodeString.Length], xmm1
0x180031f8e  mov     rbx, r8
0x180031f91  movups  xmmword ptr [rbp+27h+var_30.Length], xmm0
0x180031f95  mov     rdi, gs:30h
0x180031f9e  call    cs:__imp_RtlInitAnsiString
0x180031fa4  mov     r8b, 1; AllocateDestinationString
0x180031fa7  lea     rdx, [rbp+27h+DestinationString]; SourceString
0x180031fab  lea     rcx, [rbp+27h+UnicodeString]; DestinationString
0x180031faf  call    cs:__imp_RtlAnsiStringToUnicodeString
0x180031fb5  test    eax, eax
0x180031fb7  js      loc_1800320E2
0x180031fbd  mov     rdx, rbx; SourceString
0x180031fc0  lea     rcx, [rbp+27h+DestinationString]; DestinationString
0x180031fc4  call    cs:__imp_RtlInitAnsiString
0x180031fca  mov     r8b, 1; AllocateDestinationString
0x180031fcd  lea     rdx, [rbp+27h+DestinationString]; SourceString
0x180031fd1  lea     rcx, [rbp+27h+var_30]; DestinationString
0x180031fd5  call    cs:__imp_RtlAnsiStringToUnicodeString
0x180031fdb  mov     ebx, eax
0x180031fdd  test    eax, eax
0x180031fdf  js      loc_1800320E6
0x180031fe5  mov     rdx, rsi; SourceString
0x180031fe8  lea     rcx, [rbp+27h+DestinationString]; DestinationString
0x180031fec  call    cs:__imp_RtlInitAnsiString
0x180031ff2  xor     r8d, r8d; AllocateDestinationString
0x180031ff5  lea     rdx, [rbp+27h+DestinationString]; SourceString
0x180031ff9  lea     rcx, [rdi+1258h]; DestinationString
0x180032000  call    cs:__imp_RtlAnsiStringToUnicodeString
0x180032006  mov     ebx, eax
0x180032008  test    eax, eax
0x18003200a  js      loc_1800320C2
0x180032010  mov     rax, [rbp+27h+pfGenerateOnClose]
0x180032017  mov     rdx, r14; HandleId
0x18003201a  mov     r9, [rdi+1260h]; ObjectName
0x180032021  mov     r8, [rbp+27h+var_30.Buffer]; ObjectTypeName
0x180032025  mov     rcx, [rbp+27h+UnicodeString.Buffer]; SubsystemName
0x180032029  mov     [rsp+0D0h+var_58], rax; pfGenerateOnClose
0x18003202e  mov     rax, [rbp+27h+AccessStatusList]
0x180032035  mov     [rsp+0D0h+var_60], rax; AccessStatusList
0x18003203a  mov     rax, [rbp+27h+GrantedAccess]
0x180032041  mov     [rsp+0D0h+GrantedAccessList], rax; GrantedAccessList
0x180032046  mov     eax, [rbp+27h+ObjectCreation]
0x18003204c  mov     [rsp+0D0h+var_70], eax; ObjectCreation
0x180032050  mov     rax, [rbp+27h+GenericMapping]
0x180032057  mov     [rsp+0D0h+var_78], rax; GenericMapping
0x18003205c  mov     eax, [rbp+27h+ObjectTypeListLength]
0x180032062  mov     [rsp+0D0h+var_80], eax; ObjectTypeListLength
0x180032066  mov     rax, [rbp+27h+ObjectTypeList]
0x18003206a  mov     [rsp+0D0h+var_88], rax; ObjectTypeList
0x18003206f  mov     eax, [rbp+27h+Flags]
0x180032072  mov     [rsp+0D0h+var_90], eax; Flags
0x180032076  mov     eax, [rbp+27h+AuditType]
0x180032079  mov     [rsp+0D0h+var_98], eax; AuditType
0x18003207d  mov     eax, [rbp+27h+DesiredAccess]
0x180032080  mov     [rsp+0D0h+var_A0], eax; DesiredAccess
0x180032084  mov     rax, [rbp+27h+PrincipalSelfSid]
0x180032088  mov     [rsp+0D0h+var_A8], rax; PrincipalSelfSid
0x18003208d  mov     rax, [rbp+27h+SecurityDescriptor]
0x180032091  mov     [rsp+0D0h+var_B0], rax; SecurityDescriptor
0x180032096  call    cs:__imp_AccessCheckByTypeResultListAndAuditAlarmW
0x18003209c  lea     rcx, [rbp+27h+UnicodeString]; UnicodeString
0x1800320a0  mov     ebx, eax
0x1800320a2  call    cs:__imp_RtlFreeUnicodeString
0x1800320a8  lea     rcx, [rbp+27h+var_30]; UnicodeString
0x1800320ac  call    cs:__imp_RtlFreeUnicodeString
0x1800320b2  mov     eax, ebx
0x1800320b4  add     rsp, 0B0h
0x1800320bb  pop     r14
0x1800320bd  pop     rdi
0x1800320be  pop     rsi
0x1800320bf  pop     rbx
0x1800320c0  pop     rbp
0x1800320c1  retn
0x1800320c2  lea     rcx, [rbp+27h+UnicodeString]; UnicodeString
0x1800320c6  call    cs:__imp_RtlFreeUnicodeString
0x1800320cc  lea     rcx, [rbp+27h+var_30]; UnicodeString
0x1800320d0  call    cs:__imp_RtlFreeUnicodeString
0x1800320d6  mov     ecx, ebx
0x1800320d8  call    cs:__imp_BaseSetLastNTError
0x1800320de  xor     eax, eax
0x1800320e0  jmp     short loc_1800320B4
0x1800320e2  mov     ecx, eax
0x1800320e4  jmp     short loc_1800320D8
0x1800320e6  lea     rcx, [rbp+27h+UnicodeString]
0x1800320ea  jmp     short loc_1800320D0
```
