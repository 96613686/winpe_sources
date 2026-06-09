# AccessCheckByTypeResultListAndAuditAlarmA

- ea: `0x180035850`
- end: `0x180035a25`
- name: `AccessCheckByTypeResultListAndAuditAlarmA`
- size: `469`
- prototype: `BOOL __stdcall(LPCSTR SubsystemName, LPVOID HandleId, LPCSTR ObjectTypeName, LPCSTR ObjectName, PSECURITY_DESCRIPTOR SecurityDescriptor, PSID PrincipalSelfSid, DWORD DesiredAccess, AUDIT_EVENT_TYPE AuditType, DWORD Flags, POBJECT_TYPE_LIST ObjectTypeList, DWORD ObjectTypeListLength, PGENERIC_MAPPING GenericMapping, BOOL ObjectCreation, LPDWORD GrantedAccess, LPDWORD AccessStatusList, LPBOOL pfGenerateOnClose)`
- caller_count: `0`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180035850`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x1800359bc`
- `ntdll!RtlFreeUnicodeString` at `0x1800359cc`
- `ntdll!RtlFreeUnicodeString` at `0x1800359ed`
- `ntdll!RtlFreeUnicodeString` at `0x1800359fd`
- `ntdll!RtlFreeUnicodeString` at `0x1800359bc`
- `ntdll!RtlFreeUnicodeString` at `0x1800359cc`
- `ntdll!RtlFreeUnicodeString` at `0x1800359ed`
- `ntdll!RtlFreeUnicodeString` at `0x1800359fd`
- `ntdll!RtlInitAnsiString` at `0x18003588e`
- `ntdll!RtlInitAnsiString` at `0x1800358c0`
- `ntdll!RtlInitAnsiString` at `0x1800358f4`
- `ntdll!RtlInitAnsiString` at `0x18003588e`
- `ntdll!RtlInitAnsiString` at `0x1800358c0`
- `ntdll!RtlInitAnsiString` at `0x1800358f4`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x1800358a5`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x1800358d7`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18003590e`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x1800358a5`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x1800358d7`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18003590e`
- `api-ms-win-security-base-l1-1-0!AccessCheckByTypeResultListAndAuditAlarmW` at `0x1800359aa`
- `api-ms-win-security-base-l1-1-0!AccessCheckByTypeResultListAndAuditAlarmW` at `0x1800359aa`
- `KERNEL32!BaseSetLastNTError` at `0x180035a0b`
- `KERNEL32!BaseSetLastNTError` at `0x180035a0b`

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
0x180035850  push    rbp
0x180035852  push    rbx
0x180035853  push    rsi
0x180035854  push    rdi
0x180035855  push    r14
0x180035857  lea     rbp, [rsp-7]
0x18003585c  sub     rsp, 0B0h
0x180035863  xorps   xmm0, xmm0
0x180035866  mov     r14, rdx
0x180035869  xorps   xmm1, xmm1
0x18003586c  mov     rdx, rcx; SourceString
0x18003586f  movups  xmmword ptr [rbp+27h+DestinationString.Length], xmm0
0x180035873  lea     rcx, [rbp+27h+DestinationString]; DestinationString
0x180035877  mov     rsi, r9
0x18003587a  movups  xmmword ptr [rbp+27h+UnicodeString.Length], xmm1
0x18003587e  mov     rbx, r8
0x180035881  movups  xmmword ptr [rbp+27h+var_30.Length], xmm0
0x180035885  mov     rdi, gs:30h
0x18003588e  call    cs:__imp_RtlInitAnsiString
0x180035895  nop     dword ptr [rax+rax+00h]
0x18003589a  mov     r8b, 1; AllocateDestinationString
0x18003589d  lea     rdx, [rbp+27h+DestinationString]; SourceString
0x1800358a1  lea     rcx, [rbp+27h+UnicodeString]; DestinationString
0x1800358a5  call    cs:__imp_RtlAnsiStringToUnicodeString
0x1800358ac  nop     dword ptr [rax+rax+00h]
0x1800358b1  test    eax, eax
0x1800358b3  js      loc_180035A1B
0x1800358b9  mov     rdx, rbx; SourceString
0x1800358bc  lea     rcx, [rbp+27h+DestinationString]; DestinationString
0x1800358c0  call    cs:__imp_RtlInitAnsiString
0x1800358c7  nop     dword ptr [rax+rax+00h]
0x1800358cc  mov     r8b, 1; AllocateDestinationString
0x1800358cf  lea     rdx, [rbp+27h+DestinationString]; SourceString
0x1800358d3  lea     rcx, [rbp+27h+var_30]; DestinationString
0x1800358d7  call    cs:__imp_RtlAnsiStringToUnicodeString
0x1800358de  nop     dword ptr [rax+rax+00h]
0x1800358e3  mov     ebx, eax
0x1800358e5  test    eax, eax
0x1800358e7  js      loc_180035A1F
0x1800358ed  mov     rdx, rsi; SourceString
0x1800358f0  lea     rcx, [rbp+27h+DestinationString]; DestinationString
0x1800358f4  call    cs:__imp_RtlInitAnsiString
0x1800358fb  nop     dword ptr [rax+rax+00h]
0x180035900  xor     r8d, r8d; AllocateDestinationString
0x180035903  lea     rdx, [rbp+27h+DestinationString]; SourceString
0x180035907  lea     rcx, [rdi+1258h]; DestinationString
0x18003590e  call    cs:__imp_RtlAnsiStringToUnicodeString
0x180035915  nop     dword ptr [rax+rax+00h]
0x18003591a  mov     ebx, eax
0x18003591c  test    eax, eax
0x18003591e  js      loc_1800359E9
0x180035924  mov     rax, [rbp+27h+pfGenerateOnClose]
0x18003592b  mov     rdx, r14; HandleId
0x18003592e  mov     r9, [rdi+1260h]; ObjectName
0x180035935  mov     r8, [rbp+27h+var_30.Buffer]; ObjectTypeName
0x180035939  mov     rcx, [rbp+27h+UnicodeString.Buffer]; SubsystemName
0x18003593d  mov     [rsp+0D0h+var_58], rax; pfGenerateOnClose
0x180035942  mov     rax, [rbp+27h+AccessStatusList]
0x180035949  mov     [rsp+0D0h+var_60], rax; AccessStatusList
0x18003594e  mov     rax, [rbp+27h+GrantedAccess]
0x180035955  mov     [rsp+0D0h+GrantedAccessList], rax; GrantedAccessList
0x18003595a  mov     eax, [rbp+27h+ObjectCreation]
0x180035960  mov     [rsp+0D0h+var_70], eax; ObjectCreation
0x180035964  mov     rax, [rbp+27h+GenericMapping]
0x18003596b  mov     [rsp+0D0h+var_78], rax; GenericMapping
0x180035970  mov     eax, [rbp+27h+ObjectTypeListLength]
0x180035976  mov     [rsp+0D0h+var_80], eax; ObjectTypeListLength
0x18003597a  mov     rax, [rbp+27h+ObjectTypeList]
0x18003597e  mov     [rsp+0D0h+var_88], rax; ObjectTypeList
0x180035983  mov     eax, [rbp+27h+Flags]
0x180035986  mov     [rsp+0D0h+var_90], eax; Flags
0x18003598a  mov     eax, [rbp+27h+AuditType]
0x18003598d  mov     [rsp+0D0h+var_98], eax; AuditType
0x180035991  mov     eax, [rbp+27h+DesiredAccess]
0x180035994  mov     [rsp+0D0h+var_A0], eax; DesiredAccess
0x180035998  mov     rax, [rbp+27h+PrincipalSelfSid]
0x18003599c  mov     [rsp+0D0h+var_A8], rax; PrincipalSelfSid
0x1800359a1  mov     rax, [rbp+27h+SecurityDescriptor]
0x1800359a5  mov     [rsp+0D0h+var_B0], rax; SecurityDescriptor
0x1800359aa  call    cs:__imp_AccessCheckByTypeResultListAndAuditAlarmW
0x1800359b1  nop     dword ptr [rax+rax+00h]
0x1800359b6  lea     rcx, [rbp+27h+UnicodeString]; UnicodeString
0x1800359ba  mov     ebx, eax
0x1800359bc  call    cs:__imp_RtlFreeUnicodeString
0x1800359c3  nop     dword ptr [rax+rax+00h]
0x1800359c8  lea     rcx, [rbp+27h+var_30]; UnicodeString
0x1800359cc  call    cs:__imp_RtlFreeUnicodeString
0x1800359d3  nop     dword ptr [rax+rax+00h]
0x1800359d8  mov     eax, ebx
0x1800359da  add     rsp, 0B0h
0x1800359e1  pop     r14
0x1800359e3  pop     rdi
0x1800359e4  pop     rsi
0x1800359e5  pop     rbx
0x1800359e6  pop     rbp
0x1800359e7  retn
0x1800359e9  lea     rcx, [rbp+27h+UnicodeString]; UnicodeString
0x1800359ed  call    cs:__imp_RtlFreeUnicodeString
0x1800359f4  nop     dword ptr [rax+rax+00h]
0x1800359f9  lea     rcx, [rbp+27h+var_30]; UnicodeString
0x1800359fd  call    cs:__imp_RtlFreeUnicodeString
0x180035a04  nop     dword ptr [rax+rax+00h]
0x180035a09  mov     ecx, ebx
0x180035a0b  call    cs:__imp_BaseSetLastNTError
0x180035a12  nop     dword ptr [rax+rax+00h]
0x180035a17  xor     eax, eax
0x180035a19  jmp     short loc_1800359DA
0x180035a1b  mov     ecx, eax
0x180035a1d  jmp     short loc_180035A0B
0x180035a1f  lea     rcx, [rbp+27h+UnicodeString]
0x180035a23  jmp     short loc_1800359FD
```
