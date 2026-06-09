# ObjectOpenAuditAlarmA

- ea: `0x180050090`
- end: `0x1800501e5`
- name: `ObjectOpenAuditAlarmA`
- size: `341`
- prototype: `BOOL __stdcall(LPCSTR SubsystemName, LPVOID HandleId, LPSTR ObjectTypeName, LPSTR ObjectName, PSECURITY_DESCRIPTOR pSecurityDescriptor, HANDLE ClientToken, DWORD DesiredAccess, DWORD GrantedAccess, PPRIVILEGE_SET Privileges, BOOL ObjectCreation, BOOL AccessGranted, LPBOOL GenerateOnClose)`
- caller_count: `0`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180050090`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x180050120`
- `ntdll!RtlFreeUnicodeString` at `0x180050155`
- `ntdll!RtlFreeUnicodeString` at `0x1800501c5`
- `ntdll!RtlFreeUnicodeString` at `0x1800501cf`
- `ntdll!RtlFreeUnicodeString` at `0x180050120`
- `ntdll!RtlFreeUnicodeString` at `0x180050155`
- `ntdll!RtlFreeUnicodeString` at `0x1800501c5`
- `ntdll!RtlFreeUnicodeString` at `0x1800501cf`
- `ntdll!RtlInitAnsiString` at `0x1800500ce`
- `ntdll!RtlInitAnsiString` at `0x1800500ff`
- `ntdll!RtlInitAnsiString` at `0x180050131`
- `ntdll!RtlInitAnsiString` at `0x1800500ce`
- `ntdll!RtlInitAnsiString` at `0x1800500ff`
- `ntdll!RtlInitAnsiString` at `0x180050131`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x1800500df`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180050110`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180050145`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x1800500df`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180050110`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180050145`
- `api-ms-win-security-base-l1-1-0!ObjectOpenAuditAlarmW` at `0x1800501b9`
- `api-ms-win-security-base-l1-1-0!ObjectOpenAuditAlarmW` at `0x1800501b9`
- `KERNEL32!BaseSetLastNTError` at `0x1800500eb`
- `KERNEL32!BaseSetLastNTError` at `0x1800500eb`

## pseudocode

```c
BOOL __stdcall ObjectOpenAuditAlarmA(
        LPCSTR SubsystemName,
        LPVOID HandleId,
        LPSTR ObjectTypeName,
        LPSTR ObjectName,
        PSECURITY_DESCRIPTOR pSecurityDescriptor,
        HANDLE ClientToken,
        DWORD DesiredAccess,
        DWORD GrantedAccess,
        PPRIVILEGE_SET Privileges,
        BOOL ObjectCreation,
        BOOL AccessGranted,
        LPBOOL GenerateOnClose)
{
  struct _TEB *v15; // rdi
  NTSTATUS v16; // eax
  __int64 v17; // rcx
  NTSTATUS v19; // ebx
  struct _UNICODE_STRING *p_UnicodeString; // rcx
  BOOL v21; // ebx
  struct _STRING DestinationString; // [rsp+60h] [rbp-29h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+70h] [rbp-19h] BYREF
  struct _UNICODE_STRING v24; // [rsp+80h] [rbp-9h] BYREF

  DestinationString = 0;
  UnicodeString = 0;
  v24 = 0;
  v15 = NtCurrentTeb();
  RtlInitAnsiString(&DestinationString, SubsystemName);
  v16 = RtlAnsiStringToUnicodeString(&UnicodeString, &DestinationString, 1u);
  if ( v16 < 0 )
  {
    v17 = (unsigned int)v16;
LABEL_3:
    BaseSetLastNTError(v17);
    return 0;
  }
  RtlInitAnsiString(&DestinationString, ObjectTypeName);
  v19 = RtlAnsiStringToUnicodeString(&v24, &DestinationString, 1u);
  if ( v19 < 0 )
  {
    p_UnicodeString = &UnicodeString;
LABEL_6:
    RtlFreeUnicodeString(p_UnicodeString);
    v17 = (unsigned int)v19;
    goto LABEL_3;
  }
  RtlInitAnsiString(&DestinationString, ObjectName);
  v19 = RtlAnsiStringToUnicodeString(&v15->StaticUnicodeString, &DestinationString, 0);
  if ( v19 < 0 )
  {
    RtlFreeUnicodeString(&UnicodeString);
    p_UnicodeString = &v24;
    goto LABEL_6;
  }
  v21 = ObjectOpenAuditAlarmW(
          UnicodeString.Buffer,
          HandleId,
          v24.Buffer,
          v15->StaticUnicodeString.Buffer,
          pSecurityDescriptor,
          ClientToken,
          DesiredAccess,
          GrantedAccess,
          Privileges,
          ObjectCreation,
          AccessGranted,
          GenerateOnClose);
  RtlFreeUnicodeString(&UnicodeString);
  RtlFreeUnicodeString(&v24);
  return v21;
}

```

## disassembly

```asm
0x180050090  push    rbp
0x180050092  push    rbx
0x180050093  push    rsi
0x180050094  push    rdi
0x180050095  push    r14
0x180050097  lea     rbp, [rsp-7]
0x18005009c  sub     rsp, 90h
0x1800500a3  xorps   xmm0, xmm0
0x1800500a6  mov     r14, rdx
0x1800500a9  xorps   xmm1, xmm1
0x1800500ac  mov     rdx, rcx; SourceString
0x1800500af  movups  xmmword ptr [rbp+27h+DestinationString.Length], xmm0
0x1800500b3  lea     rcx, [rbp+27h+DestinationString]; DestinationString
0x1800500b7  mov     rsi, r9
0x1800500ba  movups  xmmword ptr [rbp+27h+UnicodeString.Length], xmm1
0x1800500be  mov     rbx, r8
0x1800500c1  movups  xmmword ptr [rbp+27h+var_30.Length], xmm0
0x1800500c5  mov     rdi, gs:30h
0x1800500ce  call    cs:__imp_RtlInitAnsiString
0x1800500d4  mov     r8b, 1; AllocateDestinationString
0x1800500d7  lea     rdx, [rbp+27h+DestinationString]; SourceString
0x1800500db  lea     rcx, [rbp+27h+UnicodeString]; DestinationString
0x1800500df  call    cs:__imp_RtlAnsiStringToUnicodeString
0x1800500e5  test    eax, eax
0x1800500e7  jns     short loc_1800500F8
0x1800500e9  mov     ecx, eax
0x1800500eb  call    cs:__imp_BaseSetLastNTError
0x1800500f1  xor     eax, eax
0x1800500f3  jmp     loc_1800501D7
0x1800500f8  mov     rdx, rbx; SourceString
0x1800500fb  lea     rcx, [rbp+27h+DestinationString]; DestinationString
0x1800500ff  call    cs:__imp_RtlInitAnsiString
0x180050105  mov     r8b, 1; AllocateDestinationString
0x180050108  lea     rdx, [rbp+27h+DestinationString]; SourceString
0x18005010c  lea     rcx, [rbp+27h+var_30]; DestinationString
0x180050110  call    cs:__imp_RtlAnsiStringToUnicodeString
0x180050116  mov     ebx, eax
0x180050118  test    eax, eax
0x18005011a  jns     short loc_18005012A
0x18005011c  lea     rcx, [rbp+27h+UnicodeString]; UnicodeString
0x180050120  call    cs:__imp_RtlFreeUnicodeString
0x180050126  mov     ecx, ebx
0x180050128  jmp     short loc_1800500EB
0x18005012a  mov     rdx, rsi; SourceString
0x18005012d  lea     rcx, [rbp+27h+DestinationString]; DestinationString
0x180050131  call    cs:__imp_RtlInitAnsiString
0x180050137  xor     r8d, r8d; AllocateDestinationString
0x18005013a  lea     rdx, [rbp+27h+DestinationString]; SourceString
0x18005013e  lea     rcx, [rdi+1258h]; DestinationString
0x180050145  call    cs:__imp_RtlAnsiStringToUnicodeString
0x18005014b  mov     ebx, eax
0x18005014d  test    eax, eax
0x18005014f  jns     short loc_180050161
0x180050151  lea     rcx, [rbp+27h+UnicodeString]; UnicodeString
0x180050155  call    cs:__imp_RtlFreeUnicodeString
0x18005015b  lea     rcx, [rbp+27h+var_30]
0x18005015f  jmp     short loc_180050120
0x180050161  mov     rax, [rbp+27h+GenerateOnClose]
0x180050168  mov     rdx, r14; HandleId
0x18005016b  mov     r9, [rdi+1260h]; ObjectName
0x180050172  mov     r8, [rbp+27h+var_30.Buffer]; ObjectTypeName
0x180050176  mov     rcx, [rbp+27h+UnicodeString.Buffer]; SubsystemName
0x18005017a  mov     [rsp+0B0h+var_58], rax; GenerateOnClose
0x18005017f  mov     eax, [rbp+27h+AccessGranted]
0x180050185  mov     [rsp+0B0h+var_60], eax; AccessGranted
0x180050189  mov     eax, [rbp+27h+ObjectCreation]
0x18005018c  mov     [rsp+0B0h+var_68], eax; ObjectCreation
0x180050190  mov     rax, [rbp+27h+Privileges]
0x180050194  mov     [rsp+0B0h+var_70], rax; Privileges
0x180050199  mov     eax, [rbp+27h+GrantedAccess]
0x18005019c  mov     [rsp+0B0h+var_78], eax; GrantedAccess
0x1800501a0  mov     eax, [rbp+27h+DesiredAccess]
0x1800501a3  mov     [rsp+0B0h+var_80], eax; DesiredAccess
0x1800501a7  mov     rax, [rbp+27h+ClientToken]
0x1800501ab  mov     [rsp+0B0h+var_88], rax; ClientToken
0x1800501b0  mov     rax, [rbp+27h+pSecurityDescriptor]
0x1800501b4  mov     [rsp+0B0h+var_90], rax; pSecurityDescriptor
0x1800501b9  call    cs:__imp_ObjectOpenAuditAlarmW
0x1800501bf  lea     rcx, [rbp+27h+UnicodeString]; UnicodeString
0x1800501c3  mov     ebx, eax
0x1800501c5  call    cs:__imp_RtlFreeUnicodeString
0x1800501cb  lea     rcx, [rbp+27h+var_30]; UnicodeString
0x1800501cf  call    cs:__imp_RtlFreeUnicodeString
0x1800501d5  mov     eax, ebx
0x1800501d7  add     rsp, 90h
0x1800501de  pop     r14
0x1800501e0  pop     rdi
0x1800501e1  pop     rsi
0x1800501e2  pop     rbx
0x1800501e3  pop     rbp
0x1800501e4  retn
```
