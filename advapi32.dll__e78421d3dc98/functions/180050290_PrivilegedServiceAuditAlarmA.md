# PrivilegedServiceAuditAlarmA

- ea: `0x180050290`
- end: `0x18005034b`
- name: `PrivilegedServiceAuditAlarmA`
- size: `187`
- prototype: `BOOL __stdcall(LPCSTR SubsystemName, LPCSTR ServiceName, HANDLE ClientToken, PPRIVILEGE_SET Privileges, BOOL AccessGranted)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180050290`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18005033a`
- `ntdll!RtlFreeUnicodeString` at `0x18005033a`
- `ntdll!RtlInitAnsiString` at `0x1800502c7`
- `ntdll!RtlInitAnsiString` at `0x1800502f6`
- `ntdll!RtlInitAnsiString` at `0x1800502c7`
- `ntdll!RtlInitAnsiString` at `0x1800502f6`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x1800502d8`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180050309`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x1800502d8`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180050309`
- `api-ms-win-security-base-l1-1-0!PrivilegedServiceAuditAlarmW` at `0x18005032d`
- `api-ms-win-security-base-l1-1-0!PrivilegedServiceAuditAlarmW` at `0x18005032d`
- `KERNEL32!BaseSetLastNTError` at `0x1800502e4`
- `KERNEL32!BaseSetLastNTError` at `0x1800502e4`

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
0x180050290  push    rbx
0x180050292  push    rbp
0x180050293  push    rsi
0x180050294  push    rdi
0x180050295  sub     rsp, 58h
0x180050299  xorps   xmm0, xmm0
0x18005029c  xorps   xmm1, xmm1
0x18005029f  movups  xmmword ptr [rsp+78h+UnicodeString.Length], xmm0
0x1800502a4  mov     rdi, rcx
0x1800502a7  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x1800502ac  movups  xmmword ptr [rsp+78h+DestinationString.Length], xmm1
0x1800502b1  mov     rax, gs:30h
0x1800502ba  mov     rsi, r9
0x1800502bd  mov     rbp, r8
0x1800502c0  lea     rbx, [rax+1258h]
0x1800502c7  call    cs:__imp_RtlInitAnsiString
0x1800502cd  xor     r8d, r8d; AllocateDestinationString
0x1800502d0  lea     rdx, [rsp+78h+DestinationString]; SourceString
0x1800502d5  mov     rcx, rbx; DestinationString
0x1800502d8  call    cs:__imp_RtlAnsiStringToUnicodeString
0x1800502de  test    eax, eax
0x1800502e0  jns     short loc_1800502EE
0x1800502e2  mov     ecx, eax
0x1800502e4  call    cs:__imp_BaseSetLastNTError
0x1800502ea  xor     eax, eax
0x1800502ec  jmp     short loc_180050342
0x1800502ee  mov     rdx, rdi; SourceString
0x1800502f1  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x1800502f6  call    cs:__imp_RtlInitAnsiString
0x1800502fc  mov     r8b, 1; AllocateDestinationString
0x1800502ff  lea     rdx, [rsp+78h+DestinationString]; SourceString
0x180050304  lea     rcx, [rsp+78h+UnicodeString]; DestinationString
0x180050309  call    cs:__imp_RtlAnsiStringToUnicodeString
0x18005030f  test    eax, eax
0x180050311  js      short loc_1800502E2
0x180050313  mov     eax, [rsp+78h+AccessGranted]
0x18005031a  mov     r9, rsi; Privileges
0x18005031d  mov     rdx, [rbx+8]; ServiceName
0x180050321  mov     r8, rbp; ClientToken
0x180050324  mov     rcx, [rsp+78h+UnicodeString.Buffer]; SubsystemName
0x180050329  mov     [rsp+78h+var_58], eax; AccessGranted
0x18005032d  call    cs:__imp_PrivilegedServiceAuditAlarmW
0x180050333  lea     rcx, [rsp+78h+UnicodeString]; UnicodeString
0x180050338  mov     ebx, eax
0x18005033a  call    cs:__imp_RtlFreeUnicodeString
0x180050340  mov     eax, ebx
0x180050342  add     rsp, 58h
0x180050346  pop     rdi
0x180050347  pop     rsi
0x180050348  pop     rbp
0x180050349  pop     rbx
0x18005034a  retn
```
