# LookupAccountSidA

- ea: `0x180025320`
- end: `0x18002558e`
- name: `LookupAccountSidA`
- size: `622`
- prototype: `BOOL __stdcall(LPCSTR lpSystemName, PSID Sid, LPSTR Name, LPDWORD cchName, LPSTR ReferencedDomainName, LPDWORD cchReferencedDomainName, PSID_NAME_USE peUse)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180025320`
- `0x1800256d8`
- `0x180027848`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18002540e`
- `ntdll!RtlFreeUnicodeString` at `0x18002544a`
- `ntdll!RtlFreeUnicodeString` at `0x18002547a`
- `ntdll!RtlFreeUnicodeString` at `0x1800254c8`
- `ntdll!RtlFreeUnicodeString` at `0x18002540e`
- `ntdll!RtlFreeUnicodeString` at `0x18002544a`
- `ntdll!RtlFreeUnicodeString` at `0x18002547a`
- `ntdll!RtlFreeUnicodeString` at `0x1800254c8`
- `ntdll!RtlInitAnsiString` at `0x1800253c4`
- `ntdll!RtlInitAnsiString` at `0x1800253c4`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x180025511`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x180025555`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x180025511`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x180025555`
- `ntdll!RtlInitUnicodeString` at `0x180025500`
- `ntdll!RtlInitUnicodeString` at `0x180025544`
- `ntdll!RtlInitUnicodeString` at `0x180025500`
- `ntdll!RtlInitUnicodeString` at `0x180025544`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x1800253d5`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x1800253d5`
- `KERNELBASE!LocalAlloc` at `0x180025433`
- `KERNELBASE!LocalAlloc` at `0x180025463`
- `KERNELBASE!LocalAlloc` at `0x180025433`
- `KERNELBASE!LocalAlloc` at `0x180025463`
- `KERNEL32!LocalFree` at `0x1800253ec`
- `KERNEL32!LocalFree` at `0x180025572`
- `KERNEL32!LocalFree` at `0x180025580`
- `KERNEL32!LocalFree` at `0x1800253ec`
- `KERNEL32!LocalFree` at `0x180025572`
- `KERNEL32!LocalFree` at `0x180025580`
- `KERNEL32!BaseSetLastNTError` at `0x1800253e1`
- `KERNEL32!BaseSetLastNTError` at `0x180025561`
- `KERNEL32!BaseSetLastNTError` at `0x1800253e1`
- `KERNEL32!BaseSetLastNTError` at `0x180025561`
- `KERNEL32!SetLastError` at `0x1800253f7`
- `KERNEL32!SetLastError` at `0x1800253f7`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalA` at `0x180025396`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalA` at `0x180025396`

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
0x180025320  mov     [rsp-38h+arg_10], rbx
0x180025325  mov     [rsp-38h+arg_18], r9
0x18002532a  mov     [rsp-38h+arg_8], rdx
0x18002532f  push    rbp
0x180025330  push    rsi
0x180025331  push    rdi
0x180025332  push    r12
0x180025334  push    r13
0x180025336  push    r14
0x180025338  push    r15
0x18002533a  mov     rbp, rsp
0x18002533d  sub     rsp, 70h
0x180025341  xorps   xmm0, xmm0
0x180025344  xor     r14d, r14d
0x180025347  xorps   xmm1, xmm1
0x18002534a  mov     rsi, r9
0x18002534d  mov     r13, r8
0x180025350  mov     rbx, rdx
0x180025353  mov     rdi, rcx
0x180025356  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18002535a  movups  xmmword ptr [rbp+SourceString.Length], xmm1
0x18002535e  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x180025362  test    rcx, rcx
0x180025365  jnz     short loc_1800253BD
0x180025367  mov     rcx, r14; String2
0x18002536a  call    IsLocalServer
0x18002536f  test    eax, eax
0x180025371  jz      loc_180025416
0x180025377  mov     rax, [rbp+peUse]
0x18002537b  mov     r8, rsi; cchName
0x18002537e  mov     r9, [rbp+ReferencedDomainName]; ReferencedDomainName
0x180025382  mov     rdx, r13; Name
0x180025385  mov     [rsp+70h+var_48], rax; peUse
0x18002538a  mov     rcx, rbx; Sid
0x18002538d  mov     rax, [rbp+cchReferencedDomainName]
0x180025391  mov     [rsp+70h+var_50], rax; cchReferencedDomainName
0x180025396  call    cs:__imp_LookupAccountSidLocalA
0x18002539c  mov     ebx, eax
0x18002539e  test    rdi, rdi
0x1800253a1  jnz     short loc_18002540A
0x1800253a3  mov     eax, ebx
0x1800253a5  mov     rbx, [rsp+70h+arg_10]
0x1800253ad  add     rsp, 70h
0x1800253b1  pop     r15
0x1800253b3  pop     r14
0x1800253b5  pop     r13
0x1800253b7  pop     r12
0x1800253b9  pop     rdi
0x1800253ba  pop     rsi
0x1800253bb  pop     rbp
0x1800253bc  retn
0x1800253bd  mov     rdx, rdi; SourceString
0x1800253c0  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800253c4  call    cs:__imp_RtlInitAnsiString
0x1800253ca  mov     r8b, 1; AllocateDestinationString
0x1800253cd  lea     rdx, [rbp+DestinationString]; SourceString
0x1800253d1  lea     rcx, [rbp+UnicodeString]; DestinationString
0x1800253d5  call    cs:__imp_RtlAnsiStringToUnicodeString
0x1800253db  test    eax, eax
0x1800253dd  jns     short loc_180025401
0x1800253df  mov     ecx, eax
0x1800253e1  call    cs:__imp_BaseSetLastNTError
0x1800253e7  jmp     short loc_1800253FD
0x1800253e9  mov     rcx, rbx; hMem
0x1800253ec  call    cs:__imp_LocalFree
0x1800253f2  mov     ecx, 0Eh; dwErrCode
0x1800253f7  call    cs:__imp_SetLastError
0x1800253fd  xor     eax, eax
0x1800253ff  jmp     short loc_1800253A5
0x180025401  mov     r14, [rbp+UnicodeString.Buffer]
0x180025405  jmp     loc_180025367
0x18002540a  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x18002540e  call    cs:__imp_RtlFreeUnicodeString
0x180025414  jmp     short loc_1800253A3
0x180025416  mov     r12, [rbp+cchReferencedDomainName]
0x18002541a  xor     ebx, ebx
0x18002541c  mov     r15d, [rsi]
0x18002541f  mov     eax, [r12]
0x180025423  mov     [rbp+arg_0], eax
0x180025426  test    r15d, r15d
0x180025429  jz      short loc_180025452
0x18002542b  mov     edx, r15d
0x18002542e  xor     ecx, ecx; uFlags
0x180025430  add     rdx, rdx; uBytes
0x180025433  call    cs:__imp_LocalAlloc
0x180025439  mov     rbx, rax
0x18002543c  test    rax, rax
0x18002543f  jnz     short loc_180025452
0x180025441  test    rdi, rdi
0x180025444  jz      short loc_1800253F2
0x180025446  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x18002544a  call    cs:__imp_RtlFreeUnicodeString
0x180025450  jmp     short loc_1800253F2
0x180025452  xor     esi, esi
0x180025454  cmp     [r12], esi
0x180025458  jbe     short loc_18002548E
0x18002545a  mov     edx, [r12]
0x18002545e  xor     ecx, ecx; uFlags
0x180025460  add     rdx, rdx; uBytes
0x180025463  call    cs:__imp_LocalAlloc
0x180025469  mov     rsi, rax
0x18002546c  test    rax, rax
0x18002546f  jnz     short loc_18002548E
0x180025471  test    rdi, rdi
0x180025474  jz      short loc_180025480
0x180025476  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x18002547a  call    cs:__imp_RtlFreeUnicodeString
0x180025480  test    rbx, rbx
0x180025483  jz      loc_1800253F2
0x180025489  jmp     loc_1800253E9
0x18002548e  mov     rax, [rbp+peUse]
0x180025492  mov     r8, rbx
0x180025495  mov     r9, [rbp+arg_18]
0x180025499  mov     rcx, r14; SourceString
0x18002549c  mov     rdx, [rbp+arg_8]
0x1800254a0  mov     [rsp+70h+var_38], 0; int
0x1800254a8  mov     [rsp+70h+var_40], rax; __int64
0x1800254ad  mov     [rsp+70h+var_48], r12; __int64
0x1800254b2  mov     [rsp+70h+var_50], rsi; __int64
0x1800254b7  call    LookupAccountSidInternal
0x1800254bc  mov     r14d, eax
0x1800254bf  test    rdi, rdi
0x1800254c2  jz      short loc_1800254CE
0x1800254c4  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x1800254c8  call    cs:__imp_RtlFreeUnicodeString
0x1800254ce  test    r14d, r14d
0x1800254d1  jz      loc_18002556A
0x1800254d7  mov     edi, 0FFFFh
0x1800254dc  test    r13, r13
0x1800254df  jz      short loc_18002551B
0x1800254e1  mov     [rbp+DestinationString.Buffer], r13
0x1800254e5  mov     [rbp+DestinationString.MaximumLength], r15w
0x1800254ea  cmp     r15d, edi
0x1800254ed  jbe     short loc_1800254F3
0x1800254ef  mov     [rbp+DestinationString.MaximumLength], di
0x1800254f3  xor     eax, eax
0x1800254f5  lea     rcx, [rbp+SourceString]; DestinationString
0x1800254f9  mov     rdx, rbx; SourceString
0x1800254fc  mov     [rbp+DestinationString.Length], ax
0x180025500  call    cs:__imp_RtlInitUnicodeString
0x180025506  xor     r8d, r8d; AllocateDestinationString
0x180025509  lea     rdx, [rbp+SourceString]; SourceString
0x18002550d  lea     rcx, [rbp+DestinationString]; DestinationString
0x180025511  call    cs:__imp_RtlUnicodeStringToAnsiString
0x180025517  test    eax, eax
0x180025519  js      short loc_18002555F
0x18002551b  mov     rax, [rbp+ReferencedDomainName]
0x18002551f  test    rax, rax
0x180025522  jz      short loc_18002556A
0x180025524  mov     [rbp+DestinationString.Buffer], rax
0x180025528  mov     eax, [rbp+arg_0]
0x18002552b  mov     [rbp+DestinationString.MaximumLength], ax
0x18002552f  cmp     eax, edi
0x180025531  jbe     short loc_180025537
0x180025533  mov     [rbp+DestinationString.MaximumLength], di
0x180025537  xor     eax, eax
0x180025539  lea     rcx, [rbp+SourceString]; DestinationString
0x18002553d  mov     rdx, rsi; SourceString
0x180025540  mov     [rbp+DestinationString.Length], ax
0x180025544  call    cs:__imp_RtlInitUnicodeString
0x18002554a  xor     r8d, r8d; AllocateDestinationString
0x18002554d  lea     rdx, [rbp+SourceString]; SourceString
0x180025551  lea     rcx, [rbp+DestinationString]; DestinationString
0x180025555  call    cs:__imp_RtlUnicodeStringToAnsiString
0x18002555b  test    eax, eax
0x18002555d  jns     short loc_18002556A
0x18002555f  mov     ecx, eax
0x180025561  call    cs:__imp_BaseSetLastNTError
0x180025567  xor     r14d, r14d
0x18002556a  test    rbx, rbx
0x18002556d  jz      short loc_180025578
0x18002556f  mov     rcx, rbx; hMem
0x180025572  call    cs:__imp_LocalFree
0x180025578  test    rsi, rsi
0x18002557b  jz      short loc_180025586
0x18002557d  mov     rcx, rsi; hMem
0x180025580  call    cs:__imp_LocalFree
0x180025586  mov     eax, r14d
0x180025589  jmp     loc_1800253A5
```
