# AccessCheckAndAuditAlarmA

- ea: `0x18004f7a0`
- end: `0x18004f8ed`
- name: `AccessCheckAndAuditAlarmA`
- size: `333`
- prototype: `BOOL __stdcall(LPCSTR SubsystemName, LPVOID HandleId, LPSTR ObjectTypeName, LPSTR ObjectName, PSECURITY_DESCRIPTOR SecurityDescriptor, DWORD DesiredAccess, PGENERIC_MAPPING GenericMapping, BOOL ObjectCreation, LPDWORD GrantedAccess, LPBOOL AccessStatus, LPBOOL pfGenerateOnClose)`
- caller_count: `0`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18004f7a0`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18004f830`
- `ntdll!RtlFreeUnicodeString` at `0x18004f865`
- `ntdll!RtlFreeUnicodeString` at `0x18004f8cd`
- `ntdll!RtlFreeUnicodeString` at `0x18004f8d7`
- `ntdll!RtlFreeUnicodeString` at `0x18004f830`
- `ntdll!RtlFreeUnicodeString` at `0x18004f865`
- `ntdll!RtlFreeUnicodeString` at `0x18004f8cd`
- `ntdll!RtlFreeUnicodeString` at `0x18004f8d7`
- `ntdll!RtlInitAnsiString` at `0x18004f7de`
- `ntdll!RtlInitAnsiString` at `0x18004f80f`
- `ntdll!RtlInitAnsiString` at `0x18004f841`
- `ntdll!RtlInitAnsiString` at `0x18004f7de`
- `ntdll!RtlInitAnsiString` at `0x18004f80f`
- `ntdll!RtlInitAnsiString` at `0x18004f841`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18004f7ef`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18004f820`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18004f855`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18004f7ef`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18004f820`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18004f855`
- `api-ms-win-security-base-l1-1-0!AccessCheckAndAuditAlarmW` at `0x18004f8c1`
- `api-ms-win-security-base-l1-1-0!AccessCheckAndAuditAlarmW` at `0x18004f8c1`
- `KERNEL32!BaseSetLastNTError` at `0x18004f7fb`
- `KERNEL32!BaseSetLastNTError` at `0x18004f7fb`

## pseudocode

```c
BOOL __stdcall AccessCheckAndAuditAlarmA(
        LPCSTR SubsystemName,
        LPVOID HandleId,
        LPSTR ObjectTypeName,
        LPSTR ObjectName,
        PSECURITY_DESCRIPTOR SecurityDescriptor,
        DWORD DesiredAccess,
        PGENERIC_MAPPING GenericMapping,
        BOOL ObjectCreation,
        LPDWORD GrantedAccess,
        LPBOOL AccessStatus,
        LPBOOL pfGenerateOnClose)
{
  struct _TEB *v14; // rdi
  NTSTATUS v15; // eax
  __int64 v16; // rcx
  NTSTATUS v18; // ebx
  struct _UNICODE_STRING *p_UnicodeString; // rcx
  BOOL v20; // ebx
  struct _STRING DestinationString; // [rsp+60h] [rbp-29h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+70h] [rbp-19h] BYREF
  struct _UNICODE_STRING v23; // [rsp+80h] [rbp-9h] BYREF

  DestinationString = 0;
  UnicodeString = 0;
  v23 = 0;
  v14 = NtCurrentTeb();
  RtlInitAnsiString(&DestinationString, SubsystemName);
  v15 = RtlAnsiStringToUnicodeString(&UnicodeString, &DestinationString, 1u);
  if ( v15 < 0 )
  {
    v16 = (unsigned int)v15;
LABEL_3:
    BaseSetLastNTError(v16);
    return 0;
  }
  RtlInitAnsiString(&DestinationString, ObjectTypeName);
  v18 = RtlAnsiStringToUnicodeString(&v23, &DestinationString, 1u);
  if ( v18 < 0 )
  {
    p_UnicodeString = &UnicodeString;
LABEL_6:
    RtlFreeUnicodeString(p_UnicodeString);
    v16 = (unsigned int)v18;
    goto LABEL_3;
  }
  RtlInitAnsiString(&DestinationString, ObjectName);
  v18 = RtlAnsiStringToUnicodeString(&v14->StaticUnicodeString, &DestinationString, 0);
  if ( v18 < 0 )
  {
    RtlFreeUnicodeString(&UnicodeString);
    p_UnicodeString = &v23;
    goto LABEL_6;
  }
  v20 = AccessCheckAndAuditAlarmW(
          UnicodeString.Buffer,
          HandleId,
          v23.Buffer,
          v14->StaticUnicodeString.Buffer,
          SecurityDescriptor,
          DesiredAccess,
          GenericMapping,
          ObjectCreation,
          GrantedAccess,
          AccessStatus,
          pfGenerateOnClose);
  RtlFreeUnicodeString(&UnicodeString);
  RtlFreeUnicodeString(&v23);
  return v20;
}

```

## disassembly

```asm
0x18004f7a0  push    rbp
0x18004f7a2  push    rbx
0x18004f7a3  push    rsi
0x18004f7a4  push    rdi
0x18004f7a5  push    r14
0x18004f7a7  lea     rbp, [rsp-7]
0x18004f7ac  sub     rsp, 90h
0x18004f7b3  xorps   xmm0, xmm0
0x18004f7b6  mov     r14, rdx
0x18004f7b9  xorps   xmm1, xmm1
0x18004f7bc  mov     rdx, rcx; SourceString
0x18004f7bf  movups  xmmword ptr [rbp+27h+DestinationString.Length], xmm0
0x18004f7c3  lea     rcx, [rbp+27h+DestinationString]; DestinationString
0x18004f7c7  mov     rsi, r9
0x18004f7ca  movups  xmmword ptr [rbp+27h+UnicodeString.Length], xmm1
0x18004f7ce  mov     rbx, r8
0x18004f7d1  movups  xmmword ptr [rbp+27h+var_30.Length], xmm0
0x18004f7d5  mov     rdi, gs:30h
0x18004f7de  call    cs:__imp_RtlInitAnsiString
0x18004f7e4  mov     r8b, 1; AllocateDestinationString
0x18004f7e7  lea     rdx, [rbp+27h+DestinationString]; SourceString
0x18004f7eb  lea     rcx, [rbp+27h+UnicodeString]; DestinationString
0x18004f7ef  call    cs:__imp_RtlAnsiStringToUnicodeString
0x18004f7f5  test    eax, eax
0x18004f7f7  jns     short loc_18004F808
0x18004f7f9  mov     ecx, eax
0x18004f7fb  call    cs:__imp_BaseSetLastNTError
0x18004f801  xor     eax, eax
0x18004f803  jmp     loc_18004F8DF
0x18004f808  mov     rdx, rbx; SourceString
0x18004f80b  lea     rcx, [rbp+27h+DestinationString]; DestinationString
0x18004f80f  call    cs:__imp_RtlInitAnsiString
0x18004f815  mov     r8b, 1; AllocateDestinationString
0x18004f818  lea     rdx, [rbp+27h+DestinationString]; SourceString
0x18004f81c  lea     rcx, [rbp+27h+var_30]; DestinationString
0x18004f820  call    cs:__imp_RtlAnsiStringToUnicodeString
0x18004f826  mov     ebx, eax
0x18004f828  test    eax, eax
0x18004f82a  jns     short loc_18004F83A
0x18004f82c  lea     rcx, [rbp+27h+UnicodeString]; UnicodeString
0x18004f830  call    cs:__imp_RtlFreeUnicodeString
0x18004f836  mov     ecx, ebx
0x18004f838  jmp     short loc_18004F7FB
0x18004f83a  mov     rdx, rsi; SourceString
0x18004f83d  lea     rcx, [rbp+27h+DestinationString]; DestinationString
0x18004f841  call    cs:__imp_RtlInitAnsiString
0x18004f847  xor     r8d, r8d; AllocateDestinationString
0x18004f84a  lea     rdx, [rbp+27h+DestinationString]; SourceString
0x18004f84e  lea     rcx, [rdi+1258h]; DestinationString
0x18004f855  call    cs:__imp_RtlAnsiStringToUnicodeString
0x18004f85b  mov     ebx, eax
0x18004f85d  test    eax, eax
0x18004f85f  jns     short loc_18004F871
0x18004f861  lea     rcx, [rbp+27h+UnicodeString]; UnicodeString
0x18004f865  call    cs:__imp_RtlFreeUnicodeString
0x18004f86b  lea     rcx, [rbp+27h+var_30]
0x18004f86f  jmp     short loc_18004F830
0x18004f871  mov     rax, [rbp+27h+pfGenerateOnClose]
0x18004f878  mov     rdx, r14; HandleId
0x18004f87b  mov     r9, [rdi+1260h]; ObjectName
0x18004f882  mov     r8, [rbp+27h+var_30.Buffer]; ObjectTypeName
0x18004f886  mov     rcx, [rbp+27h+UnicodeString.Buffer]; SubsystemName
0x18004f88a  mov     [rsp+0B0h+var_60], rax; pfGenerateOnClose
0x18004f88f  mov     rax, [rbp+27h+AccessStatus]
0x18004f893  mov     [rsp+0B0h+var_68], rax; AccessStatus
0x18004f898  mov     rax, [rbp+27h+GrantedAccess]
0x18004f89c  mov     [rsp+0B0h+var_70], rax; GrantedAccess
0x18004f8a1  mov     eax, [rbp+27h+ObjectCreation]
0x18004f8a4  mov     [rsp+0B0h+var_78], eax; ObjectCreation
0x18004f8a8  mov     rax, [rbp+27h+GenericMapping]
0x18004f8ac  mov     [rsp+0B0h+var_80], rax; GenericMapping
0x18004f8b1  mov     eax, [rbp+27h+DesiredAccess]
0x18004f8b4  mov     [rsp+0B0h+var_88], eax; DesiredAccess
0x18004f8b8  mov     rax, [rbp+27h+SecurityDescriptor]
0x18004f8bc  mov     [rsp+0B0h+var_90], rax; SecurityDescriptor
0x18004f8c1  call    cs:__imp_AccessCheckAndAuditAlarmW
0x18004f8c7  lea     rcx, [rbp+27h+UnicodeString]; UnicodeString
0x18004f8cb  mov     ebx, eax
0x18004f8cd  call    cs:__imp_RtlFreeUnicodeString
0x18004f8d3  lea     rcx, [rbp+27h+var_30]; UnicodeString
0x18004f8d7  call    cs:__imp_RtlFreeUnicodeString
0x18004f8dd  mov     eax, ebx
0x18004f8df  add     rsp, 90h
0x18004f8e6  pop     r14
0x18004f8e8  pop     rdi
0x18004f8e9  pop     rsi
0x18004f8ea  pop     rbx
0x18004f8eb  pop     rbp
0x18004f8ec  retn
```
