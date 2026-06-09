# GetFileSecurityA

- ea: `0x180038fb0`
- end: `0x180039067`
- name: `GetFileSecurityA`
- size: `183`
- prototype: `BOOL __stdcall(LPCSTR lpFileName, SECURITY_INFORMATION RequestedInformation, PSECURITY_DESCRIPTOR pSecurityDescriptor, DWORD nLength, LPDWORD lpnLengthNeeded)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180038fb0`

## import_xrefs

- `ntdll!RtlOemStringToUnicodeString` at `0x180039016`
- `ntdll!RtlOemStringToUnicodeString` at `0x180039016`
- `ntdll!RtlInitAnsiString` at `0x180038fe1`
- `ntdll!RtlInitAnsiString` at `0x180038fe1`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180039008`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180039008`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180039051`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180039051`
- `KERNEL32!BaseSetLastNTError` at `0x180039028`
- `KERNEL32!BaseSetLastNTError` at `0x180039028`
- `KERNEL32!AreFileApisANSI` at `0x180038fed`
- `KERNEL32!AreFileApisANSI` at `0x180038fed`

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
0x180038fb0  push    rbx
0x180038fb2  push    rbp
0x180038fb3  push    rsi
0x180038fb4  push    rdi
0x180038fb5  sub     rsp, 48h
0x180038fb9  xorps   xmm0, xmm0
0x180038fbc  mov     ebp, edx
0x180038fbe  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x180038fc3  mov     rax, gs:30h
0x180038fcc  mov     rdx, rcx; SourceString
0x180038fcf  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x180038fd4  mov     edi, r9d
0x180038fd7  mov     rsi, r8
0x180038fda  lea     rbx, [rax+1258h]
0x180038fe1  call    cs:__imp_RtlInitAnsiString
0x180038fe8  nop     dword ptr [rax+rax+00h]
0x180038fed  call    cs:__imp_AreFileApisANSI
0x180038ff4  nop     dword ptr [rax+rax+00h]
0x180038ff9  xor     r8d, r8d; AllocateDestinationString
0x180038ffc  lea     rdx, [rsp+68h+DestinationString]; SourceString
0x180039001  mov     rcx, rbx; DestinationString
0x180039004  test    eax, eax
0x180039006  jz      short loc_180039016
0x180039008  call    cs:__imp_RtlAnsiStringToUnicodeString
0x18003900f  nop     dword ptr [rax+rax+00h]
0x180039014  jmp     short loc_180039022
0x180039016  call    cs:__imp_RtlOemStringToUnicodeString
0x18003901d  nop     dword ptr [rax+rax+00h]
0x180039022  test    eax, eax
0x180039024  jns     short loc_180039038
0x180039026  mov     ecx, eax
0x180039028  call    cs:__imp_BaseSetLastNTError
0x18003902f  nop     dword ptr [rax+rax+00h]
0x180039034  xor     eax, eax
0x180039036  jmp     short loc_18003905D
0x180039038  mov     rax, [rsp+68h+lpnLengthNeeded]
0x180039040  mov     r9d, edi; nLength
0x180039043  mov     rcx, [rbx+8]; lpFileName
0x180039047  mov     r8, rsi; pSecurityDescriptor
0x18003904a  mov     edx, ebp; RequestedInformation
0x18003904c  mov     [rsp+68h+var_48], rax; lpnLengthNeeded
0x180039051  call    cs:__imp_GetFileSecurityW
0x180039058  nop     dword ptr [rax+rax+00h]
0x18003905d  add     rsp, 48h
0x180039061  pop     rdi
0x180039062  pop     rsi
0x180039063  pop     rbp
0x180039064  pop     rbx
0x180039065  retn
```
