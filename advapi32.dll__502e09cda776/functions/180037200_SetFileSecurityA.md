# SetFileSecurityA

- ea: `0x180037200`
- end: `0x1800372b1`
- name: `SetFileSecurityA`
- size: `177`
- prototype: `BOOL __stdcall(LPCSTR lpFileName, SECURITY_INFORMATION SecurityInformation, PSECURITY_DESCRIPTOR pSecurityDescriptor)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180037200`

## import_xrefs

- `ntdll!RtlOemStringToUnicodeString` at `0x180037291`
- `ntdll!RtlOemStringToUnicodeString` at `0x180037291`
- `ntdll!RtlInitAnsiString` at `0x180037234`
- `ntdll!RtlInitAnsiString` at `0x180037234`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18003725b`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18003725b`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x180037274`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x180037274`
- `KERNEL32!BaseSetLastNTError` at `0x1800372a1`
- `KERNEL32!BaseSetLastNTError` at `0x1800372a1`
- `KERNEL32!AreFileApisANSI` at `0x180037240`
- `KERNEL32!AreFileApisANSI` at `0x180037240`

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
0x180037200  mov     [rsp+arg_0], rbx
0x180037205  mov     [rsp+arg_8], rsi
0x18003720a  push    rdi
0x18003720b  sub     rsp, 30h
0x18003720f  xorps   xmm0, xmm0
0x180037212  mov     esi, edx
0x180037214  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x180037219  mov     rax, gs:30h
0x180037222  mov     rdx, rcx; SourceString
0x180037225  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x18003722a  mov     rdi, r8
0x18003722d  lea     rbx, [rax+1258h]
0x180037234  call    cs:__imp_RtlInitAnsiString
0x18003723b  nop     dword ptr [rax+rax+00h]
0x180037240  call    cs:__imp_AreFileApisANSI
0x180037247  nop     dword ptr [rax+rax+00h]
0x18003724c  xor     r8d, r8d; AllocateDestinationString
0x18003724f  lea     rdx, [rsp+38h+DestinationString]; SourceString
0x180037254  mov     rcx, rbx; DestinationString
0x180037257  test    eax, eax
0x180037259  jz      short loc_180037291
0x18003725b  call    cs:__imp_RtlAnsiStringToUnicodeString
0x180037262  nop     dword ptr [rax+rax+00h]
0x180037267  test    eax, eax
0x180037269  js      short loc_18003729F
0x18003726b  mov     rcx, [rbx+8]; lpFileName
0x18003726f  mov     r8, rdi; pSecurityDescriptor
0x180037272  mov     edx, esi; SecurityInformation
0x180037274  call    cs:__imp_SetFileSecurityW
0x18003727b  nop     dword ptr [rax+rax+00h]
0x180037280  mov     rbx, [rsp+38h+arg_0]
0x180037285  mov     rsi, [rsp+38h+arg_8]
0x18003728a  add     rsp, 30h
0x18003728e  pop     rdi
0x18003728f  retn
0x180037291  call    cs:__imp_RtlOemStringToUnicodeString
0x180037298  nop     dword ptr [rax+rax+00h]
0x18003729d  jmp     short loc_180037267
0x18003729f  mov     ecx, eax
0x1800372a1  call    cs:__imp_BaseSetLastNTError
0x1800372a8  nop     dword ptr [rax+rax+00h]
0x1800372ad  xor     eax, eax
0x1800372af  jmp     short loc_180037280
```
