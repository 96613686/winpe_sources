# BaseGetNamedObjectDirectory

- ea: `0x18006e3f0`
- end: `0x18006e589`
- name: `BaseGetNamedObjectDirectory`
- size: `409`
- prototype: ``
- caller_count: `14`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180012f90`
- `0x1800136b0`
- `0x1800138c0`
- `0x18006c380`
- `0x18006d010`
- `0x18006d2d0`
- `0x18006db00`
- `0x18006dc60`
- `0x18006de04`
- `0x18006e160`
- `0x18006e2f0`
- `0x1800a4820`
- `0x1800b6d00`
- `0x1801074e0`

## callees

- `0x18006e3f0`
- `0x18006e604`

## import_xrefs

- `ntdll!NtClose` at `0x18006e4e0`
- `ntdll!NtClose` at `0x18006e4f0`
- `ntdll!NtClose` at `0x18006e57e`
- `ntdll!NtClose` at `0x18006e4e0`
- `ntdll!NtClose` at `0x18006e4f0`
- `ntdll!NtClose` at `0x18006e57e`
- `ntdll!NtOpenProcessToken` at `0x18006e46e`
- `ntdll!NtOpenProcessToken` at `0x18006e46e`
- `ntdll!NtOpenThreadToken` at `0x18006e516`
- `ntdll!NtOpenThreadToken` at `0x18006e516`
- `ntdll!NtSetInformationThread` at `0x18006e53e`
- `ntdll!NtSetInformationThread` at `0x18006e573`
- `ntdll!NtSetInformationThread` at `0x18006e53e`
- `ntdll!NtSetInformationThread` at `0x18006e573`

## pseudocode

```c
__int64 __fastcall BaseGetNamedObjectDirectory(_QWORD *a1)
{
  int v3; // esi
  int NamedObjectDirectoryForToken; // edi
  HANDLE v5; // rcx
  HANDLE v6; // [rsp+60h] [rbp+8h] BYREF
  HANDLE Handle; // [rsp+68h] [rbp+10h] BYREF
  HANDLE TokenHandle; // [rsp+70h] [rbp+18h] BYREF
  __int64 ThreadInformation; // [rsp+78h] [rbp+20h] BYREF

  ThreadInformation = 0;
  if ( !a1 )
    return 3221225485LL;
  if ( BaseNamedObjectDirectory )
  {
    *a1 = BaseNamedObjectDirectory;
    return 0;
  }
  *a1 = 0;
  Handle = 0;
  TokenHandle = 0;
  v6 = 0;
  v3 = 0;
  if ( !NtCurrentTeb()->IsImpersonating )
    goto LABEL_6;
  NamedObjectDirectoryForToken = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 4u, 1u, &v6);
  if ( NamedObjectDirectoryForToken >= 0 )
  {
    ThreadInformation = 0;
    NamedObjectDirectoryForToken = NtSetInformationThread(
                                     (HANDLE)0xFFFFFFFFFFFFFFFELL,
                                     ThreadImpersonationToken,
                                     &ThreadInformation,
                                     8u);
    if ( NamedObjectDirectoryForToken >= 0 )
    {
      v3 = 1;
LABEL_6:
      NamedObjectDirectoryForToken = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, &TokenHandle);
      if ( NamedObjectDirectoryForToken >= 0 )
      {
        NamedObjectDirectoryForToken = BasepGetNamedObjectDirectoryForToken(TokenHandle, 0, 1, 15, &Handle);
        if ( NamedObjectDirectoryForToken >= 0 )
        {
          if ( !_InterlockedCompareExchange64(&BaseNamedObjectDirectory, (signed __int64)Handle, 0) )
            Handle = 0;
          *a1 = BaseNamedObjectDirectory;
        }
      }
    }
  }
  v5 = v6;
  if ( v6 )
  {
    if ( v3 )
    {
      NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &v6, 8u);
      v5 = v6;
    }
    NtClose(v5);
  }
  if ( TokenHandle )
    NtClose(TokenHandle);
  if ( Handle )
    NtClose(Handle);
  return (unsigned int)NamedObjectDirectoryForToken;
}

```

## disassembly

```asm
0x18006e3f0  push    rbx
0x18006e3f2  push    rbp
0x18006e3f3  sub     rsp, 48h
0x18006e3f7  xor     ebp, ebp
0x18006e3f9  mov     rbx, rcx
0x18006e3fc  mov     [rsp+58h+ThreadInformation], rbp
0x18006e401  test    rcx, rcx
0x18006e404  jz      short loc_18006E41E
0x18006e406  mov     rax, cs:BaseNamedObjectDirectory
0x18006e40d  test    rax, rax
0x18006e410  jz      short loc_18006E42A
0x18006e412  mov     [rcx], rax
0x18006e415  xor     eax, eax
0x18006e417  add     rsp, 48h
0x18006e41b  pop     rbp
0x18006e41c  pop     rbx
0x18006e41d  retn
0x18006e41e  mov     eax, 0C000000Dh
0x18006e423  add     rsp, 48h
0x18006e427  pop     rbp
0x18006e428  pop     rbx
0x18006e429  retn
0x18006e42a  mov     [rcx], rbp
0x18006e42d  mov     [rsp+58h+Handle], rbp
0x18006e432  mov     [rsp+58h+TokenHandle], rbp
0x18006e437  mov     [rsp+58h+arg_0], rbp
0x18006e43c  mov     rax, gs:30h
0x18006e445  mov     [rsp+58h+var_18], rsi
0x18006e44a  mov     esi, ebp
0x18006e44c  mov     [rsp+58h+var_20], rdi
0x18006e451  cmp     [rax+179Ch], ebp
0x18006e457  jnz     loc_18006E502
0x18006e45d  lea     r8, [rsp+58h+TokenHandle]; TokenHandle
0x18006e462  mov     edx, 8; DesiredAccess
0x18006e467  mov     rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18006e46e  call    cs:__imp_NtOpenProcessToken
0x18006e474  mov     edi, eax
0x18006e476  test    eax, eax
0x18006e478  js      short loc_18006E4C3
0x18006e47a  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x18006e47f  lea     rax, [rsp+58h+Handle]
0x18006e484  xor     edx, edx
0x18006e486  mov     [rsp+58h+var_38], rax; __int64
0x18006e48b  mov     r9d, 0Fh
0x18006e491  mov     r8d, 1
0x18006e497  call    BasepGetNamedObjectDirectoryForToken
0x18006e49c  mov     edi, eax
0x18006e49e  test    eax, eax
0x18006e4a0  js      short loc_18006E4C3
0x18006e4a2  mov     rcx, [rsp+58h+Handle]
0x18006e4a7  xor     eax, eax
0x18006e4a9  lock cmpxchg cs:BaseNamedObjectDirectory, rcx
0x18006e4b2  jnz     short loc_18006E4B9
0x18006e4b4  mov     [rsp+58h+Handle], rbp
0x18006e4b9  mov     rax, cs:BaseNamedObjectDirectory
0x18006e4c0  mov     [rbx], rax
0x18006e4c3  mov     rcx, [rsp+58h+arg_0]
0x18006e4c8  test    rcx, rcx
0x18006e4cb  jnz     loc_18006E558
0x18006e4d1  mov     rcx, [rsp+58h+TokenHandle]; Handle
0x18006e4d6  mov     rsi, [rsp+58h+var_18]
0x18006e4db  test    rcx, rcx
0x18006e4de  jz      short loc_18006E4E6
0x18006e4e0  call    cs:__imp_NtClose
0x18006e4e6  mov     rcx, [rsp+58h+Handle]; Handle
0x18006e4eb  test    rcx, rcx
0x18006e4ee  jz      short loc_18006E4F6
0x18006e4f0  call    cs:__imp_NtClose
0x18006e4f6  mov     eax, edi
0x18006e4f8  mov     rdi, [rsp+58h+var_20]
0x18006e4fd  jmp     loc_18006E417
0x18006e502  lea     r9, [rsp+58h+arg_0]; TokenHandle
0x18006e507  mov     r8b, 1; OpenAsSelf
0x18006e50a  mov     edx, 4; DesiredAccess
0x18006e50f  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18006e516  call    cs:__imp_NtOpenThreadToken
0x18006e51c  mov     edi, eax
0x18006e51e  test    eax, eax
0x18006e520  js      short loc_18006E4C3
0x18006e522  mov     r9d, 8; ThreadInformationLength
0x18006e528  mov     [rsp+58h+ThreadInformation], rbp
0x18006e52d  lea     r8, [rsp+58h+ThreadInformation]; ThreadInformation
0x18006e532  mov     edx, 5; ThreadInformationClass
0x18006e537  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18006e53e  call    cs:__imp_NtSetInformationThread
0x18006e544  mov     edi, eax
0x18006e546  test    eax, eax
0x18006e548  js      loc_18006E4C3
0x18006e54e  mov     esi, 1
0x18006e553  jmp     loc_18006E45D
0x18006e558  test    esi, esi
0x18006e55a  jz      short loc_18006E57E
0x18006e55c  mov     r9d, 8; ThreadInformationLength
0x18006e562  lea     r8, [rsp+58h+arg_0]; ThreadInformation
0x18006e567  mov     edx, 5; ThreadInformationClass
0x18006e56c  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18006e573  call    cs:__imp_NtSetInformationThread
0x18006e579  mov     rcx, [rsp+58h+arg_0]; Handle
0x18006e57e  call    cs:__imp_NtClose
0x18006e584  jmp     loc_18006E4D1
```
