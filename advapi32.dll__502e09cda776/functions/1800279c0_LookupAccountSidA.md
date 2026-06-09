# LookupAccountSidA

- ea: `0x1800279c0`
- end: `0x180027ca8`
- name: `LookupAccountSidA`
- size: `744`
- prototype: `BOOL __stdcall(LPCSTR lpSystemName, PSID Sid, LPSTR Name, LPDWORD cchName, LPSTR ReferencedDomainName, LPDWORD cchReferencedDomainName, PSID_NAME_USE peUse)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800279c0`
- `0x180027df0`
- `0x18002c1cc`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x180027ad7`
- `ntdll!RtlFreeUnicodeString` at `0x180027b22`
- `ntdll!RtlFreeUnicodeString` at `0x180027b5e`
- `ntdll!RtlFreeUnicodeString` at `0x180027bb2`
- `ntdll!RtlFreeUnicodeString` at `0x180027ad7`
- `ntdll!RtlFreeUnicodeString` at `0x180027b22`
- `ntdll!RtlFreeUnicodeString` at `0x180027b5e`
- `ntdll!RtlFreeUnicodeString` at `0x180027bb2`
- `ntdll!RtlInitAnsiString` at `0x180027a6f`
- `ntdll!RtlInitAnsiString` at `0x180027a6f`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x180027c07`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x180027c57`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x180027c07`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x180027c57`
- `ntdll!RtlInitUnicodeString` at `0x180027bf0`
- `ntdll!RtlInitUnicodeString` at `0x180027c40`
- `ntdll!RtlInitUnicodeString` at `0x180027bf0`
- `ntdll!RtlInitUnicodeString` at `0x180027c40`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180027a86`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180027a86`
- `KERNELBASE!LocalAlloc` at `0x180027b05`
- `KERNELBASE!LocalAlloc` at `0x180027b41`
- `KERNELBASE!LocalAlloc` at `0x180027b05`
- `KERNELBASE!LocalAlloc` at `0x180027b41`
- `KERNEL32!LocalFree` at `0x180027aa9`
- `KERNEL32!LocalFree` at `0x180027c80`
- `KERNEL32!LocalFree` at `0x180027c94`
- `KERNEL32!LocalFree` at `0x180027aa9`
- `KERNEL32!LocalFree` at `0x180027c80`
- `KERNEL32!LocalFree` at `0x180027c94`
- `KERNEL32!BaseSetLastNTError` at `0x180027a98`
- `KERNEL32!BaseSetLastNTError` at `0x180027c69`
- `KERNEL32!BaseSetLastNTError` at `0x180027a98`
- `KERNEL32!BaseSetLastNTError` at `0x180027c69`
- `KERNEL32!SetLastError` at `0x180027aba`
- `KERNEL32!SetLastError` at `0x180027aba`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalA` at `0x180027a36`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalA` at `0x180027a36`

## pseudocode

```c
BOOL __stdcall LookupAccountSidA(
        LPCSTR lpSystemName,
        PSID Sid,
        LPSTR Name,
        LPDWORD cchName,
        LPSTR ReferencedDomainName,
        LPDWORD cchReferencedDomainName,
        PSID_NAME_USE peUse)
{
  wchar_t *Buffer; // r14
  BOOL v12; // ebx
  NTSTATUS v14; // eax
  HLOCAL v15; // rbx
  DWORD v16; // r15d
  WCHAR *v17; // rsi
  int v18; // r14d
  NTSTATUS v19; // eax
  struct _STRING DestinationString; // [rsp+40h] [rbp-30h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+50h] [rbp-20h] BYREF
  UNICODE_STRING SourceString; // [rsp+60h] [rbp-10h] BYREF
  DWORD v23; // [rsp+B0h] [rbp+40h]

  Buffer = 0;
  DestinationString = 0;
  SourceString = 0;
  UnicodeString = 0;
  if ( lpSystemName )
  {
    RtlInitAnsiString(&DestinationString, lpSystemName);
    v14 = RtlAnsiStringToUnicodeString(&UnicodeString, &DestinationString, 1u);
    if ( v14 < 0 )
    {
      BaseSetLastNTError((unsigned int)v14);
      return 0;
    }
    Buffer = UnicodeString.Buffer;
  }
  if ( (unsigned int)IsLocalServer(Buffer) )
  {
    v12 = LookupAccountSidLocalA(Sid, Name, cchName, ReferencedDomainName, cchReferencedDomainName, peUse);
    if ( lpSystemName )
      RtlFreeUnicodeString(&UnicodeString);
    return v12;
  }
  v15 = 0;
  v16 = *cchName;
  v23 = *cchReferencedDomainName;
  if ( *cchName )
  {
    v15 = LocalAlloc(0, 2LL * v16);
    if ( !v15 )
    {
      if ( lpSystemName )
        RtlFreeUnicodeString(&UnicodeString);
LABEL_8:
      SetLastError(0xEu);
      return 0;
    }
  }
  v17 = 0;
  if ( *cchReferencedDomainName )
  {
    v17 = (WCHAR *)LocalAlloc(0, 2LL * *cchReferencedDomainName);
    if ( !v17 )
    {
      if ( lpSystemName )
        RtlFreeUnicodeString(&UnicodeString);
      if ( v15 )
        LocalFree(v15);
      goto LABEL_8;
    }
  }
  v18 = LookupAccountSidInternal(
          Buffer,
          (__int64)Sid,
          (WCHAR *)v15,
          cchName,
          v17,
          cchReferencedDomainName,
          (__int64)peUse,
          0);
  if ( lpSystemName )
    RtlFreeUnicodeString(&UnicodeString);
  if ( v18 )
  {
    if ( Name )
    {
      DestinationString.Buffer = Name;
      DestinationString.MaximumLength = v16;
      if ( v16 > 0xFFFF )
        DestinationString.MaximumLength = -1;
      DestinationString.Length = 0;
      RtlInitUnicodeString(&SourceString, (PCWSTR)v15);
      v19 = RtlUnicodeStringToAnsiString(&DestinationString, &SourceString, 0);
      if ( v19 < 0 )
        goto LABEL_32;
    }
    if ( ReferencedDomainName )
    {
      DestinationString.Buffer = ReferencedDomainName;
      DestinationString.MaximumLength = v23;
      if ( v23 > 0xFFFF )
        DestinationString.MaximumLength = -1;
      DestinationString.Length = 0;
      RtlInitUnicodeString(&SourceString, v17);
      v19 = RtlUnicodeStringToAnsiString(&DestinationString, &SourceString, 0);
      if ( v19 < 0 )
      {
LABEL_32:
        BaseSetLastNTError((unsigned int)v19);
        v18 = 0;
      }
    }
  }
  if ( v15 )
    LocalFree(v15);
  if ( v17 )
    LocalFree(v17);
  return v18;
}

```

## disassembly

```asm
0x1800279c0  mov     [rsp-38h+arg_10], rbx
0x1800279c5  mov     [rsp-38h+arg_18], r9
0x1800279ca  mov     [rsp-38h+arg_8], rdx
0x1800279cf  push    rbp
0x1800279d0  push    rsi
0x1800279d1  push    rdi
0x1800279d2  push    r12
0x1800279d4  push    r13
0x1800279d6  push    r14
0x1800279d8  push    r15
0x1800279da  mov     rbp, rsp
0x1800279dd  sub     rsp, 70h
0x1800279e1  xorps   xmm0, xmm0
0x1800279e4  xor     r14d, r14d
0x1800279e7  xorps   xmm1, xmm1
0x1800279ea  mov     rsi, r9
0x1800279ed  mov     r13, r8
0x1800279f0  mov     rbx, rdx
0x1800279f3  mov     rdi, rcx
0x1800279f6  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1800279fa  movups  xmmword ptr [rbp+SourceString.Length], xmm1
0x1800279fe  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x180027a02  test    rcx, rcx
0x180027a05  jnz     short loc_180027A68
0x180027a07  mov     rcx, r14; String2
0x180027a0a  call    IsLocalServer
0x180027a0f  test    eax, eax
0x180027a11  jz      loc_180027AE8
0x180027a17  mov     rax, [rbp+peUse]
0x180027a1b  mov     r8, rsi; cchName
0x180027a1e  mov     r9, [rbp+ReferencedDomainName]; ReferencedDomainName
0x180027a22  mov     rdx, r13; Name
0x180027a25  mov     [rsp+70h+var_48], rax; peUse
0x180027a2a  mov     rcx, rbx; Sid
0x180027a2d  mov     rax, [rbp+cchReferencedDomainName]
0x180027a31  mov     [rsp+70h+var_50], rax; cchReferencedDomainName
0x180027a36  call    cs:__imp_LookupAccountSidLocalA
0x180027a3d  nop     dword ptr [rax+rax+00h]
0x180027a42  mov     ebx, eax
0x180027a44  test    rdi, rdi
0x180027a47  jnz     loc_180027AD3
0x180027a4d  mov     eax, ebx
0x180027a4f  mov     rbx, [rsp+70h+arg_10]
0x180027a57  add     rsp, 70h
0x180027a5b  pop     r15
0x180027a5d  pop     r14
0x180027a5f  pop     r13
0x180027a61  pop     r12
0x180027a63  pop     rdi
0x180027a64  pop     rsi
0x180027a65  pop     rbp
0x180027a66  retn
0x180027a68  mov     rdx, rdi; SourceString
0x180027a6b  lea     rcx, [rbp+DestinationString]; DestinationString
0x180027a6f  call    cs:__imp_RtlInitAnsiString
0x180027a76  nop     dword ptr [rax+rax+00h]
0x180027a7b  mov     r8b, 1; AllocateDestinationString
0x180027a7e  lea     rdx, [rbp+DestinationString]; SourceString
0x180027a82  lea     rcx, [rbp+UnicodeString]; DestinationString
0x180027a86  call    cs:__imp_RtlAnsiStringToUnicodeString
0x180027a8d  nop     dword ptr [rax+rax+00h]
0x180027a92  test    eax, eax
0x180027a94  jns     short loc_180027ACA
0x180027a96  mov     ecx, eax
0x180027a98  call    cs:__imp_BaseSetLastNTError
0x180027a9f  nop     dword ptr [rax+rax+00h]
0x180027aa4  jmp     short loc_180027AC6
0x180027aa6  mov     rcx, rbx; hMem
0x180027aa9  call    cs:__imp_LocalFree
0x180027ab0  nop     dword ptr [rax+rax+00h]
0x180027ab5  mov     ecx, 0Eh; dwErrCode
0x180027aba  call    cs:__imp_SetLastError
0x180027ac1  nop     dword ptr [rax+rax+00h]
0x180027ac6  xor     eax, eax
0x180027ac8  jmp     short loc_180027A4F
0x180027aca  mov     r14, [rbp+UnicodeString.Buffer]
0x180027ace  jmp     loc_180027A07
0x180027ad3  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x180027ad7  call    cs:__imp_RtlFreeUnicodeString
0x180027ade  nop     dword ptr [rax+rax+00h]
0x180027ae3  jmp     loc_180027A4D
0x180027ae8  mov     r12, [rbp+cchReferencedDomainName]
0x180027aec  xor     ebx, ebx
0x180027aee  mov     r15d, [rsi]
0x180027af1  mov     eax, [r12]
0x180027af5  mov     [rbp+arg_0], eax
0x180027af8  test    r15d, r15d
0x180027afb  jz      short loc_180027B30
0x180027afd  mov     edx, r15d
0x180027b00  xor     ecx, ecx; uFlags
0x180027b02  add     rdx, rdx; uBytes
0x180027b05  call    cs:__imp_LocalAlloc
0x180027b0c  nop     dword ptr [rax+rax+00h]
0x180027b11  mov     rbx, rax
0x180027b14  test    rax, rax
0x180027b17  jnz     short loc_180027B30
0x180027b19  test    rdi, rdi
0x180027b1c  jz      short loc_180027AB5
0x180027b1e  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x180027b22  call    cs:__imp_RtlFreeUnicodeString
0x180027b29  nop     dword ptr [rax+rax+00h]
0x180027b2e  jmp     short loc_180027AB5
0x180027b30  xor     esi, esi
0x180027b32  cmp     [r12], esi
0x180027b36  jbe     short loc_180027B78
0x180027b38  mov     edx, [r12]
0x180027b3c  xor     ecx, ecx; uFlags
0x180027b3e  add     rdx, rdx; uBytes
0x180027b41  call    cs:__imp_LocalAlloc
0x180027b48  nop     dword ptr [rax+rax+00h]
0x180027b4d  mov     rsi, rax
0x180027b50  test    rax, rax
0x180027b53  jnz     short loc_180027B78
0x180027b55  test    rdi, rdi
0x180027b58  jz      short loc_180027B6A
0x180027b5a  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x180027b5e  call    cs:__imp_RtlFreeUnicodeString
0x180027b65  nop     dword ptr [rax+rax+00h]
0x180027b6a  test    rbx, rbx
0x180027b6d  jz      loc_180027AB5
0x180027b73  jmp     loc_180027AA6
0x180027b78  mov     rax, [rbp+peUse]
0x180027b7c  mov     r8, rbx
0x180027b7f  mov     r9, [rbp+arg_18]
0x180027b83  mov     rcx, r14; SourceString
0x180027b86  mov     rdx, [rbp+arg_8]
0x180027b8a  mov     [rsp+70h+var_38], 0; int
0x180027b92  mov     [rsp+70h+var_40], rax; __int64
0x180027b97  mov     [rsp+70h+var_48], r12; __int64
0x180027b9c  mov     [rsp+70h+var_50], rsi; __int64
0x180027ba1  call    LookupAccountSidInternal
0x180027ba6  mov     r14d, eax
0x180027ba9  test    rdi, rdi
0x180027bac  jz      short loc_180027BBE
0x180027bae  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x180027bb2  call    cs:__imp_RtlFreeUnicodeString
0x180027bb9  nop     dword ptr [rax+rax+00h]
0x180027bbe  test    r14d, r14d
0x180027bc1  jz      loc_180027C78
0x180027bc7  mov     edi, 0FFFFh
0x180027bcc  test    r13, r13
0x180027bcf  jz      short loc_180027C17
0x180027bd1  mov     [rbp+DestinationString.Buffer], r13
0x180027bd5  mov     [rbp+DestinationString.MaximumLength], r15w
0x180027bda  cmp     r15d, edi
0x180027bdd  jbe     short loc_180027BE3
0x180027bdf  mov     [rbp+DestinationString.MaximumLength], di
0x180027be3  xor     eax, eax
0x180027be5  lea     rcx, [rbp+SourceString]; DestinationString
0x180027be9  mov     rdx, rbx; SourceString
0x180027bec  mov     [rbp+DestinationString.Length], ax
0x180027bf0  call    cs:__imp_RtlInitUnicodeString
0x180027bf7  nop     dword ptr [rax+rax+00h]
0x180027bfc  xor     r8d, r8d; AllocateDestinationString
0x180027bff  lea     rdx, [rbp+SourceString]; SourceString
0x180027c03  lea     rcx, [rbp+DestinationString]; DestinationString
0x180027c07  call    cs:__imp_RtlUnicodeStringToAnsiString
0x180027c0e  nop     dword ptr [rax+rax+00h]
0x180027c13  test    eax, eax
0x180027c15  js      short loc_180027C67
0x180027c17  mov     rax, [rbp+ReferencedDomainName]
0x180027c1b  test    rax, rax
0x180027c1e  jz      short loc_180027C78
0x180027c20  mov     [rbp+DestinationString.Buffer], rax
0x180027c24  mov     eax, [rbp+arg_0]
0x180027c27  mov     [rbp+DestinationString.MaximumLength], ax
0x180027c2b  cmp     eax, edi
0x180027c2d  jbe     short loc_180027C33
0x180027c2f  mov     [rbp+DestinationString.MaximumLength], di
0x180027c33  xor     eax, eax
0x180027c35  lea     rcx, [rbp+SourceString]; DestinationString
0x180027c39  mov     rdx, rsi; SourceString
0x180027c3c  mov     [rbp+DestinationString.Length], ax
0x180027c40  call    cs:__imp_RtlInitUnicodeString
0x180027c47  nop     dword ptr [rax+rax+00h]
0x180027c4c  xor     r8d, r8d; AllocateDestinationString
0x180027c4f  lea     rdx, [rbp+SourceString]; SourceString
0x180027c53  lea     rcx, [rbp+DestinationString]; DestinationString
0x180027c57  call    cs:__imp_RtlUnicodeStringToAnsiString
0x180027c5e  nop     dword ptr [rax+rax+00h]
0x180027c63  test    eax, eax
0x180027c65  jns     short loc_180027C78
0x180027c67  mov     ecx, eax
0x180027c69  call    cs:__imp_BaseSetLastNTError
0x180027c70  nop     dword ptr [rax+rax+00h]
0x180027c75  xor     r14d, r14d
0x180027c78  test    rbx, rbx
0x180027c7b  jz      short loc_180027C8C
0x180027c7d  mov     rcx, rbx; hMem
0x180027c80  call    cs:__imp_LocalFree
0x180027c87  nop     dword ptr [rax+rax+00h]
0x180027c8c  test    rsi, rsi
0x180027c8f  jz      short loc_180027CA0
0x180027c91  mov     rcx, rsi; hMem
0x180027c94  call    cs:__imp_LocalFree
0x180027c9b  nop     dword ptr [rax+rax+00h]
0x180027ca0  mov     eax, r14d
0x180027ca3  jmp     loc_180027A4F
```
