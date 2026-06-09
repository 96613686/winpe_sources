# AccessCheckByTypeAndAuditAlarmA

- ea: `0x180055eb0`
- end: `0x18005607c`
- name: `AccessCheckByTypeAndAuditAlarmA`
- size: `460`
- prototype: `BOOL __stdcall(LPCSTR SubsystemName, LPVOID HandleId, LPCSTR ObjectTypeName, LPCSTR ObjectName, PSECURITY_DESCRIPTOR SecurityDescriptor, PSID PrincipalSelfSid, DWORD DesiredAccess, AUDIT_EVENT_TYPE AuditType, DWORD Flags, POBJECT_TYPE_LIST ObjectTypeList, DWORD ObjectTypeListLength, PGENERIC_MAPPING GenericMapping, BOOL ObjectCreation, LPDWORD GrantedAccess, LPBOOL AccessStatus, LPBOOL pfGenerateOnClose)`
- caller_count: `0`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180055eb0`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x180055f5e`
- `ntdll!RtlFreeUnicodeString` at `0x180055fa5`
- `ntdll!RtlFreeUnicodeString` at `0x18005604f`
- `ntdll!RtlFreeUnicodeString` at `0x18005605f`
- `ntdll!RtlFreeUnicodeString` at `0x180055f5e`
- `ntdll!RtlFreeUnicodeString` at `0x180055fa5`
- `ntdll!RtlFreeUnicodeString` at `0x18005604f`
- `ntdll!RtlFreeUnicodeString` at `0x18005605f`
- `ntdll!RtlInitAnsiString` at `0x180055eee`
- `ntdll!RtlInitAnsiString` at `0x180055f31`
- `ntdll!RtlInitAnsiString` at `0x180055f75`
- `ntdll!RtlInitAnsiString` at `0x180055eee`
- `ntdll!RtlInitAnsiString` at `0x180055f31`
- `ntdll!RtlInitAnsiString` at `0x180055f75`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180055f05`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180055f48`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180055f8f`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180055f05`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180055f48`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180055f8f`
- `api-ms-win-security-base-l1-1-0!AccessCheckByTypeAndAuditAlarmW` at `0x18005603d`
- `api-ms-win-security-base-l1-1-0!AccessCheckByTypeAndAuditAlarmW` at `0x18005603d`
- `KERNEL32!BaseSetLastNTError` at `0x180055f17`
- `KERNEL32!BaseSetLastNTError` at `0x180055f17`

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
0x180055eb0  push    rbp
0x180055eb2  push    rbx
0x180055eb3  push    rsi
0x180055eb4  push    rdi
0x180055eb5  push    r14
0x180055eb7  lea     rbp, [rsp-7]
0x180055ebc  sub     rsp, 0B0h
0x180055ec3  xorps   xmm0, xmm0
0x180055ec6  mov     r14, rdx
0x180055ec9  xorps   xmm1, xmm1
0x180055ecc  mov     rdx, rcx; SourceString
0x180055ecf  movups  xmmword ptr [rbp+27h+DestinationString.Length], xmm0
0x180055ed3  lea     rcx, [rbp+27h+DestinationString]; DestinationString
0x180055ed7  mov     rsi, r9
0x180055eda  movups  xmmword ptr [rbp+27h+UnicodeString.Length], xmm1
0x180055ede  mov     rbx, r8
0x180055ee1  movups  xmmword ptr [rbp+27h+var_30.Length], xmm0
0x180055ee5  mov     rdi, gs:30h
0x180055eee  call    cs:__imp_RtlInitAnsiString
0x180055ef5  nop     dword ptr [rax+rax+00h]
0x180055efa  mov     r8b, 1; AllocateDestinationString
0x180055efd  lea     rdx, [rbp+27h+DestinationString]; SourceString
0x180055f01  lea     rcx, [rbp+27h+UnicodeString]; DestinationString
0x180055f05  call    cs:__imp_RtlAnsiStringToUnicodeString
0x180055f0c  nop     dword ptr [rax+rax+00h]
0x180055f11  test    eax, eax
0x180055f13  jns     short loc_180055F2A
0x180055f15  mov     ecx, eax
0x180055f17  call    cs:__imp_BaseSetLastNTError
0x180055f1e  nop     dword ptr [rax+rax+00h]
0x180055f23  xor     eax, eax
0x180055f25  jmp     loc_18005606D
0x180055f2a  mov     rdx, rbx; SourceString
0x180055f2d  lea     rcx, [rbp+27h+DestinationString]; DestinationString
0x180055f31  call    cs:__imp_RtlInitAnsiString
0x180055f38  nop     dword ptr [rax+rax+00h]
0x180055f3d  mov     r8b, 1; AllocateDestinationString
0x180055f40  lea     rdx, [rbp+27h+DestinationString]; SourceString
0x180055f44  lea     rcx, [rbp+27h+var_30]; DestinationString
0x180055f48  call    cs:__imp_RtlAnsiStringToUnicodeString
0x180055f4f  nop     dword ptr [rax+rax+00h]
0x180055f54  mov     ebx, eax
0x180055f56  test    eax, eax
0x180055f58  jns     short loc_180055F6E
0x180055f5a  lea     rcx, [rbp+27h+UnicodeString]; UnicodeString
0x180055f5e  call    cs:__imp_RtlFreeUnicodeString
0x180055f65  nop     dword ptr [rax+rax+00h]
0x180055f6a  mov     ecx, ebx
0x180055f6c  jmp     short loc_180055F17
0x180055f6e  mov     rdx, rsi; SourceString
0x180055f71  lea     rcx, [rbp+27h+DestinationString]; DestinationString
0x180055f75  call    cs:__imp_RtlInitAnsiString
0x180055f7c  nop     dword ptr [rax+rax+00h]
0x180055f81  xor     r8d, r8d; AllocateDestinationString
0x180055f84  lea     rdx, [rbp+27h+DestinationString]; SourceString
0x180055f88  lea     rcx, [rdi+1258h]; DestinationString
0x180055f8f  call    cs:__imp_RtlAnsiStringToUnicodeString
0x180055f96  nop     dword ptr [rax+rax+00h]
0x180055f9b  mov     ebx, eax
0x180055f9d  test    eax, eax
0x180055f9f  jns     short loc_180055FB7
0x180055fa1  lea     rcx, [rbp+27h+UnicodeString]; UnicodeString
0x180055fa5  call    cs:__imp_RtlFreeUnicodeString
0x180055fac  nop     dword ptr [rax+rax+00h]
0x180055fb1  lea     rcx, [rbp+27h+var_30]
0x180055fb5  jmp     short loc_180055F5E
0x180055fb7  mov     rax, [rbp+27h+pfGenerateOnClose]
0x180055fbe  mov     rdx, r14; HandleId
0x180055fc1  mov     r9, [rdi+1260h]; ObjectName
0x180055fc8  mov     r8, [rbp+27h+var_30.Buffer]; ObjectTypeName
0x180055fcc  mov     rcx, [rbp+27h+UnicodeString.Buffer]; SubsystemName
0x180055fd0  mov     [rsp+0D0h+var_58], rax; pfGenerateOnClose
0x180055fd5  mov     rax, [rbp+27h+AccessStatus]
0x180055fdc  mov     [rsp+0D0h+var_60], rax; AccessStatus
0x180055fe1  mov     rax, [rbp+27h+GrantedAccess]
0x180055fe8  mov     [rsp+0D0h+var_68], rax; GrantedAccess
0x180055fed  mov     eax, [rbp+27h+ObjectCreation]
0x180055ff3  mov     [rsp+0D0h+var_70], eax; ObjectCreation
0x180055ff7  mov     rax, [rbp+27h+GenericMapping]
0x180055ffe  mov     [rsp+0D0h+var_78], rax; GenericMapping
0x180056003  mov     eax, [rbp+27h+ObjectTypeListLength]
0x180056009  mov     [rsp+0D0h+var_80], eax; ObjectTypeListLength
0x18005600d  mov     rax, [rbp+27h+ObjectTypeList]
0x180056011  mov     [rsp+0D0h+var_88], rax; ObjectTypeList
0x180056016  mov     eax, [rbp+27h+Flags]
0x180056019  mov     [rsp+0D0h+var_90], eax; Flags
0x18005601d  mov     eax, [rbp+27h+AuditType]
0x180056020  mov     [rsp+0D0h+var_98], eax; AuditType
0x180056024  mov     eax, [rbp+27h+DesiredAccess]
0x180056027  mov     [rsp+0D0h+var_A0], eax; DesiredAccess
0x18005602b  mov     rax, [rbp+27h+PrincipalSelfSid]
0x18005602f  mov     [rsp+0D0h+var_A8], rax; PrincipalSelfSid
0x180056034  mov     rax, [rbp+27h+SecurityDescriptor]
0x180056038  mov     [rsp+0D0h+var_B0], rax; SecurityDescriptor
0x18005603d  call    cs:__imp_AccessCheckByTypeAndAuditAlarmW
0x180056044  nop     dword ptr [rax+rax+00h]
0x180056049  lea     rcx, [rbp+27h+UnicodeString]; UnicodeString
0x18005604d  mov     ebx, eax
0x18005604f  call    cs:__imp_RtlFreeUnicodeString
0x180056056  nop     dword ptr [rax+rax+00h]
0x18005605b  lea     rcx, [rbp+27h+var_30]; UnicodeString
0x18005605f  call    cs:__imp_RtlFreeUnicodeString
0x180056066  nop     dword ptr [rax+rax+00h]
0x18005606b  mov     eax, ebx
0x18005606d  add     rsp, 0B0h
0x180056074  pop     r14
0x180056076  pop     rdi
0x180056077  pop     rsi
0x180056078  pop     rbx
0x180056079  pop     rbp
0x18005607a  retn
```
