# GetFileSecurityA

- ea: `0x180035410`
- end: `0x1800354a2`
- name: `GetFileSecurityA`
- size: `146`
- prototype: `BOOL __stdcall(LPCSTR lpFileName, SECURITY_INFORMATION RequestedInformation, PSECURITY_DESCRIPTOR pSecurityDescriptor, DWORD nLength, LPDWORD lpnLengthNeeded)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180035410`

## import_xrefs

- `ntdll!RtlOemStringToUnicodeString` at `0x180035464`
- `ntdll!RtlOemStringToUnicodeString` at `0x180035464`
- `ntdll!RtlInitAnsiString` at `0x180035441`
- `ntdll!RtlInitAnsiString` at `0x180035441`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18003545c`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18003545c`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180035493`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180035493`
- `KERNEL32!BaseSetLastNTError` at `0x180035470`
- `KERNEL32!BaseSetLastNTError` at `0x180035470`
- `KERNEL32!AreFileApisANSI` at `0x180035447`
- `KERNEL32!AreFileApisANSI` at `0x180035447`

## pseudocode

```c
BOOL __stdcall GetFileSecurityA(
        LPCSTR lpFileName,
        SECURITY_INFORMATION RequestedInformation,
        PSECURITY_DESCRIPTOR pSecurityDescriptor,
        DWORD nLength,
        LPDWORD lpnLengthNeeded)
{
  UNICODE_STRING *p_StaticUnicodeString; // rbx
  NTSTATUS v9; // eax
  struct _STRING DestinationString; // [rsp+30h] [rbp-38h] BYREF

  DestinationString = 0;
  p_StaticUnicodeString = &NtCurrentTeb()->StaticUnicodeString;
  RtlInitAnsiString(&DestinationString, lpFileName);
  if ( AreFileApisANSI() )
    v9 = RtlAnsiStringToUnicodeString(p_StaticUnicodeString, &DestinationString, 0);
  else
    v9 = RtlOemStringToUnicodeString(p_StaticUnicodeString, &DestinationString, 0);
  if ( v9 >= 0 )
    return GetFileSecurityW(
             p_StaticUnicodeString->Buffer,
             RequestedInformation,
             pSecurityDescriptor,
             nLength,
             lpnLengthNeeded);
  BaseSetLastNTError((unsigned int)v9);
  return 0;
}

```

## disassembly

```asm
0x180035410  push    rbx
0x180035412  push    rbp
0x180035413  push    rsi
0x180035414  push    rdi
0x180035415  sub     rsp, 48h
0x180035419  xorps   xmm0, xmm0
0x18003541c  mov     ebp, edx
0x18003541e  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x180035423  mov     rax, gs:30h
0x18003542c  mov     rdx, rcx; SourceString
0x18003542f  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x180035434  mov     edi, r9d
0x180035437  mov     rsi, r8
0x18003543a  lea     rbx, [rax+1258h]
0x180035441  call    cs:__imp_RtlInitAnsiString
0x180035447  call    cs:__imp_AreFileApisANSI
0x18003544d  xor     r8d, r8d; AllocateDestinationString
0x180035450  lea     rdx, [rsp+68h+DestinationString]; SourceString
0x180035455  mov     rcx, rbx; DestinationString
0x180035458  test    eax, eax
0x18003545a  jz      short loc_180035464
0x18003545c  call    cs:__imp_RtlAnsiStringToUnicodeString
0x180035462  jmp     short loc_18003546A
0x180035464  call    cs:__imp_RtlOemStringToUnicodeString
0x18003546a  test    eax, eax
0x18003546c  jns     short loc_18003547A
0x18003546e  mov     ecx, eax
0x180035470  call    cs:__imp_BaseSetLastNTError
0x180035476  xor     eax, eax
0x180035478  jmp     short loc_180035499
0x18003547a  mov     rax, [rsp+68h+lpnLengthNeeded]
0x180035482  mov     r9d, edi; nLength
0x180035485  mov     rcx, [rbx+8]; lpFileName
0x180035489  mov     r8, rsi; pSecurityDescriptor
0x18003548c  mov     edx, ebp; RequestedInformation
0x18003548e  mov     [rsp+68h+var_48], rax; lpnLengthNeeded
0x180035493  call    cs:__imp_GetFileSecurityW
0x180035499  add     rsp, 48h
0x18003549d  pop     rdi
0x18003549e  pop     rsi
0x18003549f  pop     rbp
0x1800354a0  pop     rbx
0x1800354a1  retn
```
