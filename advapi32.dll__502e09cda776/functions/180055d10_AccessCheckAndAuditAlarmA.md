# AccessCheckAndAuditAlarmA

- ea: `0x180055d10`
- end: `0x180055ea6`
- name: `AccessCheckAndAuditAlarmA`
- size: `406`
- prototype: `BOOL __stdcall(LPCSTR SubsystemName, LPVOID HandleId, LPSTR ObjectTypeName, LPSTR ObjectName, PSECURITY_DESCRIPTOR SecurityDescriptor, DWORD DesiredAccess, PGENERIC_MAPPING GenericMapping, BOOL ObjectCreation, LPDWORD GrantedAccess, LPBOOL AccessStatus, LPBOOL pfGenerateOnClose)`
- caller_count: `0`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180055d10`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x180055dbe`
- `ntdll!RtlFreeUnicodeString` at `0x180055e05`
- `ntdll!RtlFreeUnicodeString` at `0x180055e79`
- `ntdll!RtlFreeUnicodeString` at `0x180055e89`
- `ntdll!RtlFreeUnicodeString` at `0x180055dbe`
- `ntdll!RtlFreeUnicodeString` at `0x180055e05`
- `ntdll!RtlFreeUnicodeString` at `0x180055e79`
- `ntdll!RtlFreeUnicodeString` at `0x180055e89`
- `ntdll!RtlInitAnsiString` at `0x180055d4e`
- `ntdll!RtlInitAnsiString` at `0x180055d91`
- `ntdll!RtlInitAnsiString` at `0x180055dd5`
- `ntdll!RtlInitAnsiString` at `0x180055d4e`
- `ntdll!RtlInitAnsiString` at `0x180055d91`
- `ntdll!RtlInitAnsiString` at `0x180055dd5`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180055d65`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180055da8`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180055def`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180055d65`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180055da8`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180055def`
- `api-ms-win-security-base-l1-1-0!AccessCheckAndAuditAlarmW` at `0x180055e67`
- `api-ms-win-security-base-l1-1-0!AccessCheckAndAuditAlarmW` at `0x180055e67`
- `KERNEL32!BaseSetLastNTError` at `0x180055d77`
- `KERNEL32!BaseSetLastNTError` at `0x180055d77`

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
0x180055d10  push    rbp
0x180055d12  push    rbx
0x180055d13  push    rsi
0x180055d14  push    rdi
0x180055d15  push    r14
0x180055d17  lea     rbp, [rsp-7]
0x180055d1c  sub     rsp, 90h
0x180055d23  xorps   xmm0, xmm0
0x180055d26  mov     r14, rdx
0x180055d29  xorps   xmm1, xmm1
0x180055d2c  mov     rdx, rcx; SourceString
0x180055d2f  movups  xmmword ptr [rbp+27h+DestinationString.Length], xmm0
0x180055d33  lea     rcx, [rbp+27h+DestinationString]; DestinationString
0x180055d37  mov     rsi, r9
0x180055d3a  movups  xmmword ptr [rbp+27h+UnicodeString.Length], xmm1
0x180055d3e  mov     rbx, r8
0x180055d41  movups  xmmword ptr [rbp+27h+var_30.Length], xmm0
0x180055d45  mov     rdi, gs:30h
0x180055d4e  call    cs:__imp_RtlInitAnsiString
0x180055d55  nop     dword ptr [rax+rax+00h]
0x180055d5a  mov     r8b, 1; AllocateDestinationString
0x180055d5d  lea     rdx, [rbp+27h+DestinationString]; SourceString
0x180055d61  lea     rcx, [rbp+27h+UnicodeString]; DestinationString
0x180055d65  call    cs:__imp_RtlAnsiStringToUnicodeString
0x180055d6c  nop     dword ptr [rax+rax+00h]
0x180055d71  test    eax, eax
0x180055d73  jns     short loc_180055D8A
0x180055d75  mov     ecx, eax
0x180055d77  call    cs:__imp_BaseSetLastNTError
0x180055d7e  nop     dword ptr [rax+rax+00h]
0x180055d83  xor     eax, eax
0x180055d85  jmp     loc_180055E97
0x180055d8a  mov     rdx, rbx; SourceString
0x180055d8d  lea     rcx, [rbp+27h+DestinationString]; DestinationString
0x180055d91  call    cs:__imp_RtlInitAnsiString
0x180055d98  nop     dword ptr [rax+rax+00h]
0x180055d9d  mov     r8b, 1; AllocateDestinationString
0x180055da0  lea     rdx, [rbp+27h+DestinationString]; SourceString
0x180055da4  lea     rcx, [rbp+27h+var_30]; DestinationString
0x180055da8  call    cs:__imp_RtlAnsiStringToUnicodeString
0x180055daf  nop     dword ptr [rax+rax+00h]
0x180055db4  mov     ebx, eax
0x180055db6  test    eax, eax
0x180055db8  jns     short loc_180055DCE
0x180055dba  lea     rcx, [rbp+27h+UnicodeString]; UnicodeString
0x180055dbe  call    cs:__imp_RtlFreeUnicodeString
0x180055dc5  nop     dword ptr [rax+rax+00h]
0x180055dca  mov     ecx, ebx
0x180055dcc  jmp     short loc_180055D77
0x180055dce  mov     rdx, rsi; SourceString
0x180055dd1  lea     rcx, [rbp+27h+DestinationString]; DestinationString
0x180055dd5  call    cs:__imp_RtlInitAnsiString
0x180055ddc  nop     dword ptr [rax+rax+00h]
0x180055de1  xor     r8d, r8d; AllocateDestinationString
0x180055de4  lea     rdx, [rbp+27h+DestinationString]; SourceString
0x180055de8  lea     rcx, [rdi+1258h]; DestinationString
0x180055def  call    cs:__imp_RtlAnsiStringToUnicodeString
0x180055df6  nop     dword ptr [rax+rax+00h]
0x180055dfb  mov     ebx, eax
0x180055dfd  test    eax, eax
0x180055dff  jns     short loc_180055E17
0x180055e01  lea     rcx, [rbp+27h+UnicodeString]; UnicodeString
0x180055e05  call    cs:__imp_RtlFreeUnicodeString
0x180055e0c  nop     dword ptr [rax+rax+00h]
0x180055e11  lea     rcx, [rbp+27h+var_30]
0x180055e15  jmp     short loc_180055DBE
0x180055e17  mov     rax, [rbp+27h+pfGenerateOnClose]
0x180055e1e  mov     rdx, r14; HandleId
0x180055e21  mov     r9, [rdi+1260h]; ObjectName
0x180055e28  mov     r8, [rbp+27h+var_30.Buffer]; ObjectTypeName
0x180055e2c  mov     rcx, [rbp+27h+UnicodeString.Buffer]; SubsystemName
0x180055e30  mov     [rsp+0B0h+var_60], rax; pfGenerateOnClose
0x180055e35  mov     rax, [rbp+27h+AccessStatus]
0x180055e39  mov     [rsp+0B0h+var_68], rax; AccessStatus
0x180055e3e  mov     rax, [rbp+27h+GrantedAccess]
0x180055e42  mov     [rsp+0B0h+var_70], rax; GrantedAccess
0x180055e47  mov     eax, [rbp+27h+ObjectCreation]
0x180055e4a  mov     [rsp+0B0h+var_78], eax; ObjectCreation
0x180055e4e  mov     rax, [rbp+27h+GenericMapping]
0x180055e52  mov     [rsp+0B0h+var_80], rax; GenericMapping
0x180055e57  mov     eax, [rbp+27h+DesiredAccess]
0x180055e5a  mov     [rsp+0B0h+var_88], eax; DesiredAccess
0x180055e5e  mov     rax, [rbp+27h+SecurityDescriptor]
0x180055e62  mov     [rsp+0B0h+var_90], rax; SecurityDescriptor
0x180055e67  call    cs:__imp_AccessCheckAndAuditAlarmW
0x180055e6e  nop     dword ptr [rax+rax+00h]
0x180055e73  lea     rcx, [rbp+27h+UnicodeString]; UnicodeString
0x180055e77  mov     ebx, eax
0x180055e79  call    cs:__imp_RtlFreeUnicodeString
0x180055e80  nop     dword ptr [rax+rax+00h]
0x180055e85  lea     rcx, [rbp+27h+var_30]; UnicodeString
0x180055e89  call    cs:__imp_RtlFreeUnicodeString
0x180055e90  nop     dword ptr [rax+rax+00h]
0x180055e95  mov     eax, ebx
0x180055e97  add     rsp, 90h
0x180055e9e  pop     r14
0x180055ea0  pop     rdi
0x180055ea1  pop     rsi
0x180055ea2  pop     rbx
0x180055ea3  pop     rbp
0x180055ea4  retn
```
