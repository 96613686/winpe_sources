# OpenMutexW

- ea: `0x1800af490`
- end: `0x1800af6e9`
- name: `OpenMutexW`
- size: `601`
- prototype: `HANDLE __stdcall(DWORD dwDesiredAccess, BOOL bInheritHandle, LPCWSTR lpName)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18016da28`

## callees

- `0x1800134a0`
- `0x18006e604`
- `0x1800af490`
- `0x180197010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800af4db`
- `ntdll!RtlInitUnicodeString` at `0x1800af4db`
- `ntdll!NtOpenMutant` at `0x1800af545`
- `ntdll!NtOpenMutant` at `0x1800af545`
- `ntdll!NtClose` at `0x1800af636`
- `ntdll!NtClose` at `0x1800af645`
- `ntdll!NtClose` at `0x1800af6de`
- `ntdll!NtClose` at `0x1800af636`
- `ntdll!NtClose` at `0x1800af645`
- `ntdll!NtClose` at `0x1800af6de`
- `ntdll!NtOpenProcessToken` at `0x1800af5c8`
- `ntdll!NtOpenProcessToken` at `0x1800af5c8`
- `ntdll!NtOpenThreadToken` at `0x1800af676`
- `ntdll!NtOpenThreadToken` at `0x1800af676`
- `ntdll!NtSetInformationThread` at `0x1800af69d`
- `ntdll!NtSetInformationThread` at `0x1800af6d4`
- `ntdll!NtSetInformationThread` at `0x1800af69d`
- `ntdll!NtSetInformationThread` at `0x1800af6d4`

## pseudocode

```c
HANDLE __stdcall OpenMutexW(DWORD dwDesiredAccess, BOOL bInheritHandle, LPCWSTR lpName)
{
  void *v5; // rbx
  NTSTATUS v6; // eax
  int v8; // r15d
  int NamedObjectDirectoryForToken; // r14d
  HANDLE v10; // rcx
  HANDLE TokenHandle; // [rsp+38h] [rbp-29h] BYREF
  __int64 ThreadInformation; // [rsp+40h] [rbp-21h] BYREF
  HANDLE MutantHandle; // [rsp+48h] [rbp-19h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-11h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-1h] BYREF
  HANDLE v16; // [rsp+D8h] [rbp+77h] BYREF
  HANDLE Handle; // [rsp+E0h] [rbp+7Fh] BYREF

  MutantHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  if ( !lpName )
  {
    BaseSetLastNTError(3221225485LL);
    return 0;
  }
  RtlInitUnicodeString(&DestinationString, lpName);
  v5 = (void *)BaseNamedObjectDirectory;
  v16 = 0;
  TokenHandle = 0;
  ThreadInformation = 0;
  Handle = 0;
  if ( BaseNamedObjectDirectory )
    goto LABEL_3;
  v5 = 0;
  v8 = 0;
  if ( NtCurrentTeb()->IsImpersonating )
  {
    NamedObjectDirectoryForToken = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 4u, 1u, &v16);
    if ( NamedObjectDirectoryForToken < 0 )
      goto LABEL_15;
    ThreadInformation = 0;
    NamedObjectDirectoryForToken = NtSetInformationThread(
                                     (HANDLE)0xFFFFFFFFFFFFFFFELL,
                                     ThreadImpersonationToken,
                                     &ThreadInformation,
                                     8u);
    if ( NamedObjectDirectoryForToken < 0 )
      goto LABEL_15;
    v8 = 1;
  }
  NamedObjectDirectoryForToken = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, &TokenHandle);
  if ( NamedObjectDirectoryForToken >= 0 )
  {
    NamedObjectDirectoryForToken = BasepGetNamedObjectDirectoryForToken(TokenHandle, 0, 1, 15, &Handle);
    if ( NamedObjectDirectoryForToken >= 0 )
    {
      if ( !_InterlockedCompareExchange64(&BaseNamedObjectDirectory, (signed __int64)Handle, 0) )
        Handle = 0;
      v5 = (void *)BaseNamedObjectDirectory;
    }
  }
LABEL_15:
  v10 = v16;
  if ( v16 )
  {
    if ( v8 )
    {
      NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &v16, 8u);
      v10 = v16;
    }
    NtClose(v10);
  }
  if ( TokenHandle )
    NtClose(TokenHandle);
  if ( Handle )
    NtClose(Handle);
  if ( NamedObjectDirectoryForToken < 0 )
  {
    BaseSetLastNTError((unsigned int)NamedObjectDirectoryForToken);
    return 0;
  }
LABEL_3:
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = v5;
  ObjectAttributes.Attributes = bInheritHandle ? 2 : 0;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( pfnAdjustObjectAttributesForPrivateNamespace )
    pfnAdjustObjectAttributesForPrivateNamespace(&ObjectAttributes);
  v6 = NtOpenMutant(&MutantHandle, dwDesiredAccess, &ObjectAttributes);
  if ( v6 >= 0 )
    return MutantHandle;
  BaseSetLastNTError((unsigned int)v6);
  return 0;
}

```

## disassembly

```asm
0x1800af490  mov     r11, rsp
0x1800af493  push    rbp
0x1800af494  push    rsi
0x1800af495  push    rdi
0x1800af496  push    r12
0x1800af498  lea     rbp, [r11-5Fh]
0x1800af49c  sub     rsp, 98h
0x1800af4a3  xorps   xmm0, xmm0
0x1800af4a6  xor     r12d, r12d
0x1800af4a9  xor     eax, eax
0x1800af4ab  mov     [rbp+57h+MutantHandle], r12
0x1800af4af  mov     edi, edx
0x1800af4b1  mov     esi, ecx
0x1800af4b3  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800af4b7  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1800af4bb  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800af4bf  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800af4c3  test    r8, r8
0x1800af4c6  jz      loc_1800AF575
0x1800af4cc  mov     [r11+8], rbx
0x1800af4d0  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800af4d4  mov     rdx, r8; SourceString
0x1800af4d7  mov     [r11+10h], r14
0x1800af4db  call    cs:__imp_RtlInitUnicodeString
0x1800af4e1  mov     rbx, cs:BaseNamedObjectDirectory
0x1800af4e8  mov     [rbp+57h+arg_10], r12
0x1800af4ec  mov     [rbp+57h+TokenHandle], r12
0x1800af4f0  mov     [rbp+57h+ThreadInformation], r12
0x1800af4f4  mov     [rbp+57h+Handle], r12
0x1800af4f8  test    rbx, rbx
0x1800af4fb  jz      loc_1800AF594
0x1800af501  neg     edi
0x1800af503  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800af50a  xorps   xmm0, xmm0
0x1800af50d  mov     [rbp+57h+ObjectAttributes.RootDirectory], rbx
0x1800af511  sbb     eax, eax
0x1800af513  and     eax, 2
0x1800af516  mov     [rbp+57h+ObjectAttributes.Attributes], eax
0x1800af519  lea     rax, [rbp+57h+DestinationString]
0x1800af51d  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800af521  mov     rax, cs:pfnAdjustObjectAttributesForPrivateNamespace
0x1800af528  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800af52d  test    rax, rax
0x1800af530  jz      short loc_1800AF53B
0x1800af532  lea     rcx, [rbp+57h+ObjectAttributes]
0x1800af536  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af53b  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800af53f  mov     edx, esi; DesiredAccess
0x1800af541  lea     rcx, [rbp+57h+MutantHandle]; MutantHandle
0x1800af545  call    cs:__imp_NtOpenMutant
0x1800af54b  test    eax, eax
0x1800af54d  jns     short loc_1800AF58E
0x1800af54f  mov     ecx, eax
0x1800af551  call    BaseSetLastNTError
0x1800af556  xor     eax, eax
0x1800af558  mov     rbx, [rsp+0B0h+arg_0]
0x1800af560  mov     r14, [rsp+0B0h+arg_8]
0x1800af568  add     rsp, 98h
0x1800af56f  pop     r12
0x1800af571  pop     rdi
0x1800af572  pop     rsi
0x1800af573  pop     rbp
0x1800af574  retn
0x1800af575  mov     ecx, 0C000000Dh
0x1800af57a  call    BaseSetLastNTError
0x1800af57f  xor     eax, eax
0x1800af581  add     rsp, 98h
0x1800af588  pop     r12
0x1800af58a  pop     rdi
0x1800af58b  pop     rsi
0x1800af58c  pop     rbp
0x1800af58d  retn
0x1800af58e  mov     rax, [rbp+57h+MutantHandle]
0x1800af592  jmp     short loc_1800AF558
0x1800af594  mov     rax, gs:30h
0x1800af59d  mov     rbx, r12
0x1800af5a0  mov     [rsp+90h], r15
0x1800af5a8  mov     r15d, r12d
0x1800af5ab  cmp     [rax+179Ch], r12d
0x1800af5b2  jnz     loc_1800AF663
0x1800af5b8  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x1800af5bc  mov     edx, 8; DesiredAccess
0x1800af5c1  mov     rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1800af5c8  call    cs:__imp_NtOpenProcessToken
0x1800af5ce  mov     r14d, eax
0x1800af5d1  test    eax, eax
0x1800af5d3  js      short loc_1800AF618
0x1800af5d5  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1800af5d9  lea     rax, [rbp+57h+Handle]
0x1800af5dd  xor     edx, edx
0x1800af5df  mov     [rsp+20h], rax; __int64
0x1800af5e4  mov     r9d, 0Fh
0x1800af5ea  mov     r8d, 1
0x1800af5f0  call    BasepGetNamedObjectDirectoryForToken
0x1800af5f5  mov     r14d, eax
0x1800af5f8  test    eax, eax
0x1800af5fa  js      short loc_1800AF618
0x1800af5fc  mov     rcx, [rbp+57h+Handle]
0x1800af600  xor     eax, eax
0x1800af602  lock cmpxchg cs:BaseNamedObjectDirectory, rcx
0x1800af60b  jnz     short loc_1800AF611
0x1800af60d  mov     [rbp+57h+Handle], r12
0x1800af611  mov     rbx, cs:BaseNamedObjectDirectory
0x1800af618  mov     rcx, [rbp+57h+arg_10]
0x1800af61c  test    rcx, rcx
0x1800af61f  jnz     loc_1800AF6B9
0x1800af625  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x1800af629  mov     r15, [rsp+90h]
0x1800af631  test    rcx, rcx
0x1800af634  jz      short loc_1800AF63C
0x1800af636  call    cs:__imp_NtClose
0x1800af63c  mov     rcx, [rbp+57h+Handle]; Handle
0x1800af640  test    rcx, rcx
0x1800af643  jz      short loc_1800AF64B
0x1800af645  call    cs:__imp_NtClose
0x1800af64b  test    r14d, r14d
0x1800af64e  jns     loc_1800AF501
0x1800af654  mov     ecx, r14d
0x1800af657  call    BaseSetLastNTError
0x1800af65c  xor     eax, eax
0x1800af65e  jmp     loc_1800AF558
0x1800af663  lea     r9, [rbp+57h+arg_10]; TokenHandle
0x1800af667  mov     r8b, 1; OpenAsSelf
0x1800af66a  mov     edx, 4; DesiredAccess
0x1800af66f  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800af676  call    cs:__imp_NtOpenThreadToken
0x1800af67c  mov     r14d, eax
0x1800af67f  test    eax, eax
0x1800af681  js      short loc_1800AF618
0x1800af683  mov     r9d, 8; ThreadInformationLength
0x1800af689  mov     [rbp+57h+ThreadInformation], r12
0x1800af68d  lea     r8, [rbp+57h+ThreadInformation]; ThreadInformation
0x1800af691  mov     edx, 5; ThreadInformationClass
0x1800af696  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800af69d  call    cs:__imp_NtSetInformationThread
0x1800af6a3  mov     r14d, eax
0x1800af6a6  test    eax, eax
0x1800af6a8  js      loc_1800AF618
0x1800af6ae  mov     r15d, 1
0x1800af6b4  jmp     loc_1800AF5B8
0x1800af6b9  test    r15d, r15d
0x1800af6bc  jz      short loc_1800AF6DE
0x1800af6be  mov     r9d, 8; ThreadInformationLength
0x1800af6c4  lea     r8, [rbp+57h+arg_10]; ThreadInformation
0x1800af6c8  mov     edx, 5; ThreadInformationClass
0x1800af6cd  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800af6d4  call    cs:__imp_NtSetInformationThread
0x1800af6da  mov     rcx, [rbp+57h+arg_10]; Handle
0x1800af6de  call    cs:__imp_NtClose
0x1800af6e4  jmp     loc_1800AF625
```
