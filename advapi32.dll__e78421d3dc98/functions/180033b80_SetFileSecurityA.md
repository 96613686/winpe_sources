# SetFileSecurityA

- ea: `0x180033b80`
- end: `0x180033c0c`
- name: `SetFileSecurityA`
- size: `140`
- prototype: `BOOL __stdcall(LPCSTR lpFileName, SECURITY_INFORMATION SecurityInformation, PSECURITY_DESCRIPTOR pSecurityDescriptor)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180033b80`

## import_xrefs

- `ntdll!RtlOemStringToUnicodeString` at `0x180033bf8`
- `ntdll!RtlOemStringToUnicodeString` at `0x180033bf8`
- `ntdll!RtlInitAnsiString` at `0x180033bb4`
- `ntdll!RtlInitAnsiString` at `0x180033bb4`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180033bcf`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180033bcf`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x180033be2`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x180033be2`
- `KERNEL32!BaseSetLastNTError` at `0x180033c02`
- `KERNEL32!BaseSetLastNTError` at `0x180033c02`
- `KERNEL32!AreFileApisANSI` at `0x180033bba`
- `KERNEL32!AreFileApisANSI` at `0x180033bba`

## pseudocode

```c
BOOL __stdcall SetFileSecurityA(
        LPCSTR lpFileName,
        SECURITY_INFORMATION SecurityInformation,
        PSECURITY_DESCRIPTOR pSecurityDescriptor)
{
  UNICODE_STRING *p_StaticUnicodeString; // rbx
  NTSTATUS v6; // eax
  struct _STRING DestinationString; // [rsp+20h] [rbp-18h] BYREF

  DestinationString = 0;
  p_StaticUnicodeString = &NtCurrentTeb()->StaticUnicodeString;
  RtlInitAnsiString(&DestinationString, lpFileName);
  if ( AreFileApisANSI() )
    v6 = RtlAnsiStringToUnicodeString(p_StaticUnicodeString, &DestinationString, 0);
  else
    v6 = RtlOemStringToUnicodeString(p_StaticUnicodeString, &DestinationString, 0);
  if ( v6 >= 0 )
    return SetFileSecurityW(p_StaticUnicodeString->Buffer, SecurityInformation, pSecurityDescriptor);
  BaseSetLastNTError((unsigned int)v6);
  return 0;
}

```

## disassembly

```asm
0x180033b80  mov     [rsp+arg_0], rbx
0x180033b85  mov     [rsp+arg_8], rsi
0x180033b8a  push    rdi
0x180033b8b  sub     rsp, 30h
0x180033b8f  xorps   xmm0, xmm0
0x180033b92  mov     esi, edx
0x180033b94  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x180033b99  mov     rax, gs:30h
0x180033ba2  mov     rdx, rcx; SourceString
0x180033ba5  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x180033baa  mov     rdi, r8
0x180033bad  lea     rbx, [rax+1258h]
0x180033bb4  call    cs:__imp_RtlInitAnsiString
0x180033bba  call    cs:__imp_AreFileApisANSI
0x180033bc0  xor     r8d, r8d; AllocateDestinationString
0x180033bc3  lea     rdx, [rsp+38h+DestinationString]; SourceString
0x180033bc8  mov     rcx, rbx; DestinationString
0x180033bcb  test    eax, eax
0x180033bcd  jz      short loc_180033BF8
0x180033bcf  call    cs:__imp_RtlAnsiStringToUnicodeString
0x180033bd5  test    eax, eax
0x180033bd7  js      short loc_180033C00
0x180033bd9  mov     rcx, [rbx+8]; lpFileName
0x180033bdd  mov     r8, rdi; pSecurityDescriptor
0x180033be0  mov     edx, esi; SecurityInformation
0x180033be2  call    cs:__imp_SetFileSecurityW
0x180033be8  mov     rbx, [rsp+38h+arg_0]
0x180033bed  mov     rsi, [rsp+38h+arg_8]
0x180033bf2  add     rsp, 30h
0x180033bf6  pop     rdi
0x180033bf7  retn
0x180033bf8  call    cs:__imp_RtlOemStringToUnicodeString
0x180033bfe  jmp     short loc_180033BD5
0x180033c00  mov     ecx, eax
0x180033c02  call    cs:__imp_BaseSetLastNTError
0x180033c08  xor     eax, eax
0x180033c0a  jmp     short loc_180033BE8
```
