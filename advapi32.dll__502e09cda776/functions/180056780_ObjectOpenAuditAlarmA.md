# ObjectOpenAuditAlarmA

- ea: `0x180056780`
- end: `0x18005691e`
- name: `ObjectOpenAuditAlarmA`
- size: `414`
- prototype: `BOOL __stdcall(LPCSTR SubsystemName, LPVOID HandleId, LPSTR ObjectTypeName, LPSTR ObjectName, PSECURITY_DESCRIPTOR pSecurityDescriptor, HANDLE ClientToken, DWORD DesiredAccess, DWORD GrantedAccess, PPRIVILEGE_SET Privileges, BOOL ObjectCreation, BOOL AccessGranted, LPBOOL GenerateOnClose)`
- caller_count: `0`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180056780`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18005682e`
- `ntdll!RtlFreeUnicodeString` at `0x180056875`
- `ntdll!RtlFreeUnicodeString` at `0x1800568f1`
- `ntdll!RtlFreeUnicodeString` at `0x180056901`
- `ntdll!RtlFreeUnicodeString` at `0x18005682e`
- `ntdll!RtlFreeUnicodeString` at `0x180056875`
- `ntdll!RtlFreeUnicodeString` at `0x1800568f1`
- `ntdll!RtlFreeUnicodeString` at `0x180056901`
- `ntdll!RtlInitAnsiString` at `0x1800567be`
- `ntdll!RtlInitAnsiString` at `0x180056801`
- `ntdll!RtlInitAnsiString` at `0x180056845`
- `ntdll!RtlInitAnsiString` at `0x1800567be`
- `ntdll!RtlInitAnsiString` at `0x180056801`
- `ntdll!RtlInitAnsiString` at `0x180056845`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x1800567d5`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180056818`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18005685f`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x1800567d5`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180056818`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18005685f`
- `api-ms-win-security-base-l1-1-0!ObjectOpenAuditAlarmW` at `0x1800568df`
- `api-ms-win-security-base-l1-1-0!ObjectOpenAuditAlarmW` at `0x1800568df`
- `KERNEL32!BaseSetLastNTError` at `0x1800567e7`
- `KERNEL32!BaseSetLastNTError` at `0x1800567e7`

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
0x180056780  push    rbp
0x180056782  push    rbx
0x180056783  push    rsi
0x180056784  push    rdi
0x180056785  push    r14
0x180056787  lea     rbp, [rsp-7]
0x18005678c  sub     rsp, 90h
0x180056793  xorps   xmm0, xmm0
0x180056796  mov     r14, rdx
0x180056799  xorps   xmm1, xmm1
0x18005679c  mov     rdx, rcx; SourceString
0x18005679f  movups  xmmword ptr [rbp+27h+DestinationString.Length], xmm0
0x1800567a3  lea     rcx, [rbp+27h+DestinationString]; DestinationString
0x1800567a7  mov     rsi, r9
0x1800567aa  movups  xmmword ptr [rbp+27h+UnicodeString.Length], xmm1
0x1800567ae  mov     rbx, r8
0x1800567b1  movups  xmmword ptr [rbp+27h+var_30.Length], xmm0
0x1800567b5  mov     rdi, gs:30h
0x1800567be  call    cs:__imp_RtlInitAnsiString
0x1800567c5  nop     dword ptr [rax+rax+00h]
0x1800567ca  mov     r8b, 1; AllocateDestinationString
0x1800567cd  lea     rdx, [rbp+27h+DestinationString]; SourceString
0x1800567d1  lea     rcx, [rbp+27h+UnicodeString]; DestinationString
0x1800567d5  call    cs:__imp_RtlAnsiStringToUnicodeString
0x1800567dc  nop     dword ptr [rax+rax+00h]
0x1800567e1  test    eax, eax
0x1800567e3  jns     short loc_1800567FA
0x1800567e5  mov     ecx, eax
0x1800567e7  call    cs:__imp_BaseSetLastNTError
0x1800567ee  nop     dword ptr [rax+rax+00h]
0x1800567f3  xor     eax, eax
0x1800567f5  jmp     loc_18005690F
0x1800567fa  mov     rdx, rbx; SourceString
0x1800567fd  lea     rcx, [rbp+27h+DestinationString]; DestinationString
0x180056801  call    cs:__imp_RtlInitAnsiString
0x180056808  nop     dword ptr [rax+rax+00h]
0x18005680d  mov     r8b, 1; AllocateDestinationString
0x180056810  lea     rdx, [rbp+27h+DestinationString]; SourceString
0x180056814  lea     rcx, [rbp+27h+var_30]; DestinationString
0x180056818  call    cs:__imp_RtlAnsiStringToUnicodeString
0x18005681f  nop     dword ptr [rax+rax+00h]
0x180056824  mov     ebx, eax
0x180056826  test    eax, eax
0x180056828  jns     short loc_18005683E
0x18005682a  lea     rcx, [rbp+27h+UnicodeString]; UnicodeString
0x18005682e  call    cs:__imp_RtlFreeUnicodeString
0x180056835  nop     dword ptr [rax+rax+00h]
0x18005683a  mov     ecx, ebx
0x18005683c  jmp     short loc_1800567E7
0x18005683e  mov     rdx, rsi; SourceString
0x180056841  lea     rcx, [rbp+27h+DestinationString]; DestinationString
0x180056845  call    cs:__imp_RtlInitAnsiString
0x18005684c  nop     dword ptr [rax+rax+00h]
0x180056851  xor     r8d, r8d; AllocateDestinationString
0x180056854  lea     rdx, [rbp+27h+DestinationString]; SourceString
0x180056858  lea     rcx, [rdi+1258h]; DestinationString
0x18005685f  call    cs:__imp_RtlAnsiStringToUnicodeString
0x180056866  nop     dword ptr [rax+rax+00h]
0x18005686b  mov     ebx, eax
0x18005686d  test    eax, eax
0x18005686f  jns     short loc_180056887
0x180056871  lea     rcx, [rbp+27h+UnicodeString]; UnicodeString
0x180056875  call    cs:__imp_RtlFreeUnicodeString
0x18005687c  nop     dword ptr [rax+rax+00h]
0x180056881  lea     rcx, [rbp+27h+var_30]
0x180056885  jmp     short loc_18005682E
0x180056887  mov     rax, [rbp+27h+GenerateOnClose]
0x18005688e  mov     rdx, r14; HandleId
0x180056891  mov     r9, [rdi+1260h]; ObjectName
0x180056898  mov     r8, [rbp+27h+var_30.Buffer]; ObjectTypeName
0x18005689c  mov     rcx, [rbp+27h+UnicodeString.Buffer]; SubsystemName
0x1800568a0  mov     [rsp+0B0h+var_58], rax; GenerateOnClose
0x1800568a5  mov     eax, [rbp+27h+AccessGranted]
0x1800568ab  mov     [rsp+0B0h+var_60], eax; AccessGranted
0x1800568af  mov     eax, [rbp+27h+ObjectCreation]
0x1800568b2  mov     [rsp+0B0h+var_68], eax; ObjectCreation
0x1800568b6  mov     rax, [rbp+27h+Privileges]
0x1800568ba  mov     [rsp+0B0h+var_70], rax; Privileges
0x1800568bf  mov     eax, [rbp+27h+GrantedAccess]
0x1800568c2  mov     [rsp+0B0h+var_78], eax; GrantedAccess
0x1800568c6  mov     eax, [rbp+27h+DesiredAccess]
0x1800568c9  mov     [rsp+0B0h+var_80], eax; DesiredAccess
0x1800568cd  mov     rax, [rbp+27h+ClientToken]
0x1800568d1  mov     [rsp+0B0h+var_88], rax; ClientToken
0x1800568d6  mov     rax, [rbp+27h+pSecurityDescriptor]
0x1800568da  mov     [rsp+0B0h+var_90], rax; pSecurityDescriptor
0x1800568df  call    cs:__imp_ObjectOpenAuditAlarmW
0x1800568e6  nop     dword ptr [rax+rax+00h]
0x1800568eb  lea     rcx, [rbp+27h+UnicodeString]; UnicodeString
0x1800568ef  mov     ebx, eax
0x1800568f1  call    cs:__imp_RtlFreeUnicodeString
0x1800568f8  nop     dword ptr [rax+rax+00h]
0x1800568fd  lea     rcx, [rbp+27h+var_30]; UnicodeString
0x180056901  call    cs:__imp_RtlFreeUnicodeString
0x180056908  nop     dword ptr [rax+rax+00h]
0x18005690d  mov     eax, ebx
0x18005690f  add     rsp, 90h
0x180056916  pop     r14
0x180056918  pop     rdi
0x180056919  pop     rsi
0x18005691a  pop     rbx
0x18005691b  pop     rbp
0x18005691c  retn
```
