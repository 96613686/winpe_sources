# PrivilegedServiceAuditAlarmA

- ea: `0x1800569e0`
- end: `0x180056ac6`
- name: `PrivilegedServiceAuditAlarmA`
- size: `230`
- prototype: `BOOL __stdcall(LPCSTR SubsystemName, LPCSTR ServiceName, HANDLE ClientToken, PPRIVILEGE_SET Privileges, BOOL AccessGranted)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800569e0`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x180056aae`
- `ntdll!RtlFreeUnicodeString` at `0x180056aae`
- `ntdll!RtlInitAnsiString` at `0x180056a17`
- `ntdll!RtlInitAnsiString` at `0x180056a58`
- `ntdll!RtlInitAnsiString` at `0x180056a17`
- `ntdll!RtlInitAnsiString` at `0x180056a58`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180056a2e`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180056a71`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180056a2e`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180056a71`
- `api-ms-win-security-base-l1-1-0!PrivilegedServiceAuditAlarmW` at `0x180056a9b`
- `api-ms-win-security-base-l1-1-0!PrivilegedServiceAuditAlarmW` at `0x180056a9b`
- `KERNEL32!BaseSetLastNTError` at `0x180056a40`
- `KERNEL32!BaseSetLastNTError` at `0x180056a40`

## pseudocode

```c
BOOL __stdcall PrivilegedServiceAuditAlarmA(
        LPCSTR SubsystemName,
        LPCSTR ServiceName,
        HANDLE ClientToken,
        PPRIVILEGE_SET Privileges,
        BOOL AccessGranted)
{
  UNICODE_STRING *p_StaticUnicodeString; // rbx
  NTSTATUS v9; // eax
  BOOL v11; // ebx
  struct _STRING DestinationString; // [rsp+30h] [rbp-48h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+40h] [rbp-38h] BYREF

  UnicodeString = 0;
  DestinationString = 0;
  p_StaticUnicodeString = &NtCurrentTeb()->StaticUnicodeString;
  RtlInitAnsiString(&DestinationString, ServiceName);
  v9 = RtlAnsiStringToUnicodeString(p_StaticUnicodeString, &DestinationString, 0);
  if ( v9 < 0
    || (RtlInitAnsiString(&DestinationString, SubsystemName),
        v9 = RtlAnsiStringToUnicodeString(&UnicodeString, &DestinationString, 1u),
        v9 < 0) )
  {
    BaseSetLastNTError((unsigned int)v9);
    return 0;
  }
  else
  {
    v11 = PrivilegedServiceAuditAlarmW(
            UnicodeString.Buffer,
            p_StaticUnicodeString->Buffer,
            ClientToken,
            Privileges,
            AccessGranted);
    RtlFreeUnicodeString(&UnicodeString);
    return v11;
  }
}

```

## disassembly

```asm
0x1800569e0  push    rbx
0x1800569e2  push    rbp
0x1800569e3  push    rsi
0x1800569e4  push    rdi
0x1800569e5  sub     rsp, 58h
0x1800569e9  xorps   xmm0, xmm0
0x1800569ec  xorps   xmm1, xmm1
0x1800569ef  movups  xmmword ptr [rsp+78h+UnicodeString.Length], xmm0
0x1800569f4  mov     rdi, rcx
0x1800569f7  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x1800569fc  movups  xmmword ptr [rsp+78h+DestinationString.Length], xmm1
0x180056a01  mov     rax, gs:30h
0x180056a0a  mov     rsi, r9
0x180056a0d  mov     rbp, r8
0x180056a10  lea     rbx, [rax+1258h]
0x180056a17  call    cs:__imp_RtlInitAnsiString
0x180056a1e  nop     dword ptr [rax+rax+00h]
0x180056a23  xor     r8d, r8d; AllocateDestinationString
0x180056a26  lea     rdx, [rsp+78h+DestinationString]; SourceString
0x180056a2b  mov     rcx, rbx; DestinationString
0x180056a2e  call    cs:__imp_RtlAnsiStringToUnicodeString
0x180056a35  nop     dword ptr [rax+rax+00h]
0x180056a3a  test    eax, eax
0x180056a3c  jns     short loc_180056A50
0x180056a3e  mov     ecx, eax
0x180056a40  call    cs:__imp_BaseSetLastNTError
0x180056a47  nop     dword ptr [rax+rax+00h]
0x180056a4c  xor     eax, eax
0x180056a4e  jmp     short loc_180056ABC
0x180056a50  mov     rdx, rdi; SourceString
0x180056a53  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x180056a58  call    cs:__imp_RtlInitAnsiString
0x180056a5f  nop     dword ptr [rax+rax+00h]
0x180056a64  mov     r8b, 1; AllocateDestinationString
0x180056a67  lea     rdx, [rsp+78h+DestinationString]; SourceString
0x180056a6c  lea     rcx, [rsp+78h+UnicodeString]; DestinationString
0x180056a71  call    cs:__imp_RtlAnsiStringToUnicodeString
0x180056a78  nop     dword ptr [rax+rax+00h]
0x180056a7d  test    eax, eax
0x180056a7f  js      short loc_180056A3E
0x180056a81  mov     eax, [rsp+78h+AccessGranted]
0x180056a88  mov     r9, rsi; Privileges
0x180056a8b  mov     rdx, [rbx+8]; ServiceName
0x180056a8f  mov     r8, rbp; ClientToken
0x180056a92  mov     rcx, [rsp+78h+UnicodeString.Buffer]; SubsystemName
0x180056a97  mov     [rsp+78h+var_58], eax; AccessGranted
0x180056a9b  call    cs:__imp_PrivilegedServiceAuditAlarmW
0x180056aa2  nop     dword ptr [rax+rax+00h]
0x180056aa7  lea     rcx, [rsp+78h+UnicodeString]; UnicodeString
0x180056aac  mov     ebx, eax
0x180056aae  call    cs:__imp_RtlFreeUnicodeString
0x180056ab5  nop     dword ptr [rax+rax+00h]
0x180056aba  mov     eax, ebx
0x180056abc  add     rsp, 58h
0x180056ac0  pop     rdi
0x180056ac1  pop     rsi
0x180056ac2  pop     rbp
0x180056ac3  pop     rbx
0x180056ac4  retn
```
