# BaseFormatObjectAttributes

- ea: `0x18006cdc0`
- end: `0x18006cfdf`
- name: `BaseFormatObjectAttributes`
- size: `543`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18006c53c`
- `0x18006c8a0`
- `0x18006c9b0`
- `0x18007f610`
- `0x1800c7b90`
- `0x1800e9050`
- `0x18017fc00`

## callees

- `0x18006cdc0`
- `0x18006e604`
- `0x180197010`

## import_xrefs

- `ntdll!NtClose` at `0x18006cf11`
- `ntdll!NtClose` at `0x18006cf21`
- `ntdll!NtClose` at `0x18006cfca`
- `ntdll!NtClose` at `0x18006cf11`
- `ntdll!NtClose` at `0x18006cf21`
- `ntdll!NtClose` at `0x18006cfca`
- `ntdll!NtOpenProcessToken` at `0x18006cea5`
- `ntdll!NtOpenProcessToken` at `0x18006cea5`
- `ntdll!NtOpenThreadToken` at `0x18006cf54`
- `ntdll!NtOpenThreadToken` at `0x18006cf54`
- `ntdll!NtSetInformationThread` at `0x18006cf7d`
- `ntdll!NtSetInformationThread` at `0x18006cfbf`
- `ntdll!NtSetInformationThread` at `0x18006cf7d`
- `ntdll!NtSetInformationThread` at `0x18006cfbf`

## pseudocode

```c
__int64 __fastcall BaseFormatObjectAttributes(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4)
{
  __int64 v7; // rbx
  __int64 v9; // r12
  int v10; // ebp
  __int64 v11; // r15
  void (__fastcall *v12)(__int64); // rax
  int NamedObjectDirectoryForToken; // r13d
  HANDLE v14; // rcx
  HANDLE v15; // [rsp+30h] [rbp-68h] BYREF
  HANDLE Handle; // [rsp+38h] [rbp-60h] BYREF
  HANDLE TokenHandle; // [rsp+40h] [rbp-58h] BYREF
  _QWORD ThreadInformation[10]; // [rsp+48h] [rbp-50h] BYREF
  int v19; // [rsp+A8h] [rbp+10h]

  if ( a2 )
  {
    v9 = *(_QWORD *)(a2 + 8);
    v10 = *(_DWORD *)(a2 + 16) != 0 ? 2 : 0;
    if ( !a3 )
    {
      v11 = 0;
      goto LABEL_7;
    }
  }
  else
  {
    v7 = 0;
    if ( !a3 )
    {
LABEL_3:
      *a4 = v7;
      return 0;
    }
    v10 = 0;
    v9 = 0;
  }
  v11 = BaseNamedObjectDirectory;
  v15 = 0;
  TokenHandle = 0;
  ThreadInformation[0] = 0;
  Handle = 0;
  if ( BaseNamedObjectDirectory )
  {
LABEL_6:
    v10 |= 0x80u;
LABEL_7:
    v12 = (void (__fastcall *)(__int64))pfnAdjustObjectAttributesForPrivateNamespace;
    *(_DWORD *)a1 = 48;
    *(_QWORD *)(a1 + 8) = v11;
    *(_DWORD *)(a1 + 24) = v10;
    *(_QWORD *)(a1 + 16) = a3;
    *(_QWORD *)(a1 + 32) = v9;
    *(_QWORD *)(a1 + 40) = 0;
    if ( v12 )
      v12(a1);
    v7 = a1;
    goto LABEL_3;
  }
  v11 = 0;
  v19 = 0;
  if ( NtCurrentTeb()->IsImpersonating )
  {
    NamedObjectDirectoryForToken = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 4u, 1u, &v15);
    if ( NamedObjectDirectoryForToken < 0 )
      goto LABEL_16;
    ThreadInformation[0] = 0;
    NamedObjectDirectoryForToken = NtSetInformationThread(
                                     (HANDLE)0xFFFFFFFFFFFFFFFELL,
                                     ThreadImpersonationToken,
                                     ThreadInformation,
                                     8u);
    if ( NamedObjectDirectoryForToken < 0 )
      goto LABEL_16;
    v19 = 1;
  }
  NamedObjectDirectoryForToken = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, &TokenHandle);
  if ( NamedObjectDirectoryForToken >= 0 )
  {
    NamedObjectDirectoryForToken = BasepGetNamedObjectDirectoryForToken(TokenHandle, 0, 1, 15, &Handle);
    if ( NamedObjectDirectoryForToken >= 0 )
    {
      if ( !_InterlockedCompareExchange64(&BaseNamedObjectDirectory, (signed __int64)Handle, 0) )
        Handle = 0;
      v11 = BaseNamedObjectDirectory;
    }
  }
LABEL_16:
  v14 = v15;
  if ( v15 )
  {
    if ( v19 )
    {
      NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &v15, 8u);
      v14 = v15;
    }
    NtClose(v14);
  }
  if ( TokenHandle )
    NtClose(TokenHandle);
  if ( Handle )
    NtClose(Handle);
  if ( NamedObjectDirectoryForToken >= 0 )
    goto LABEL_6;
  return (unsigned int)NamedObjectDirectoryForToken;
}

```

## disassembly

```asm
0x18006cdc0  push    rbx
0x18006cdc2  push    rbp
0x18006cdc3  push    rsi
0x18006cdc4  push    rdi
0x18006cdc5  push    r12
0x18006cdc7  push    r13
0x18006cdc9  push    r14
0x18006cdcb  push    r15
0x18006cdcd  sub     rsp, 58h
0x18006cdd1  mov     rsi, r9
0x18006cdd4  mov     rdi, r8
0x18006cdd7  mov     r14, rcx
0x18006cdda  test    rdx, rdx
0x18006cddd  jnz     short loc_18006CE00
0x18006cddf  xor     ebx, ebx
0x18006cde1  test    r8, r8
0x18006cde4  jnz     loc_18006CFD5
0x18006cdea  mov     [rsi], rbx
0x18006cded  xor     eax, eax
0x18006cdef  add     rsp, 58h
0x18006cdf3  pop     r15
0x18006cdf5  pop     r14
0x18006cdf7  pop     r13
0x18006cdf9  pop     r12
0x18006cdfb  pop     rdi
0x18006cdfc  pop     rsi
0x18006cdfd  pop     rbp
0x18006cdfe  pop     rbx
0x18006cdff  retn
0x18006ce00  mov     eax, [rdx+10h]
0x18006ce03  mov     r12, [rdx+8]
0x18006ce07  neg     eax
0x18006ce09  sbb     ebp, ebp
0x18006ce0b  xor     ebx, ebx
0x18006ce0d  and     ebp, 2
0x18006ce10  test    rdi, rdi
0x18006ce13  jz      loc_18006CF38
0x18006ce19  mov     r15, cs:BaseNamedObjectDirectory
0x18006ce20  mov     [rsp+98h+var_68], rbx
0x18006ce25  mov     [rsp+98h+TokenHandle], rbx
0x18006ce2a  mov     [rsp+98h+ThreadInformation], rbx
0x18006ce2f  mov     [rsp+98h+Handle], rbx
0x18006ce34  test    r15, r15
0x18006ce37  jz      short loc_18006CE74
0x18006ce39  bts     ebp, 7
0x18006ce3d  mov     rax, cs:pfnAdjustObjectAttributesForPrivateNamespace
0x18006ce44  mov     dword ptr [r14], 30h ; '0'
0x18006ce4b  mov     [r14+8], r15
0x18006ce4f  mov     [r14+18h], ebp
0x18006ce53  mov     [r14+10h], rdi
0x18006ce57  mov     [r14+20h], r12
0x18006ce5b  mov     [r14+28h], rbx
0x18006ce5f  test    rax, rax
0x18006ce62  jz      short loc_18006CE6C
0x18006ce64  mov     rcx, r14
0x18006ce67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ce6c  mov     rbx, r14
0x18006ce6f  jmp     loc_18006CDEA
0x18006ce74  mov     rax, gs:30h
0x18006ce7d  mov     r15, rbx
0x18006ce80  mov     [rsp+98h+arg_8], ebx
0x18006ce87  cmp     dword ptr [rax+179Ch], 0
0x18006ce8e  jnz     loc_18006CF40
0x18006ce94  lea     r8, [rsp+98h+TokenHandle]; TokenHandle
0x18006ce99  mov     edx, 8; DesiredAccess
0x18006ce9e  mov     rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18006cea5  call    cs:__imp_NtOpenProcessToken
0x18006ceab  mov     r13d, eax
0x18006ceae  test    eax, eax
0x18006ceb0  js      short loc_18006CEF9
0x18006ceb2  mov     rcx, [rsp+98h+TokenHandle]; TokenHandle
0x18006ceb7  lea     rax, [rsp+98h+Handle]
0x18006cebc  xor     edx, edx
0x18006cebe  mov     [rsp+98h+var_78], rax; __int64
0x18006cec3  mov     r9d, 0Fh
0x18006cec9  mov     r8d, 1
0x18006cecf  call    BasepGetNamedObjectDirectoryForToken
0x18006ced4  mov     r13d, eax
0x18006ced7  test    eax, eax
0x18006ced9  js      short loc_18006CEF9
0x18006cedb  mov     rcx, [rsp+98h+Handle]
0x18006cee0  xor     eax, eax
0x18006cee2  lock cmpxchg cs:BaseNamedObjectDirectory, rcx
0x18006ceeb  jnz     short loc_18006CEF2
0x18006ceed  mov     [rsp+98h+Handle], rbx
0x18006cef2  mov     r15, cs:BaseNamedObjectDirectory
0x18006cef9  mov     rcx, [rsp+98h+var_68]
0x18006cefe  test    rcx, rcx
0x18006cf01  jnz     loc_18006CF9E
0x18006cf07  mov     rcx, [rsp+98h+TokenHandle]; Handle
0x18006cf0c  test    rcx, rcx
0x18006cf0f  jz      short loc_18006CF17
0x18006cf11  call    cs:__imp_NtClose
0x18006cf17  mov     rcx, [rsp+98h+Handle]; Handle
0x18006cf1c  test    rcx, rcx
0x18006cf1f  jz      short loc_18006CF27
0x18006cf21  call    cs:__imp_NtClose
0x18006cf27  test    r13d, r13d
0x18006cf2a  jns     loc_18006CE39
0x18006cf30  mov     eax, r13d
0x18006cf33  jmp     loc_18006CDEF
0x18006cf38  mov     r15, rbx
0x18006cf3b  jmp     loc_18006CE3D
0x18006cf40  lea     r9, [rsp+98h+var_68]; TokenHandle
0x18006cf45  mov     r8b, 1; OpenAsSelf
0x18006cf48  mov     edx, 4; DesiredAccess
0x18006cf4d  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18006cf54  call    cs:__imp_NtOpenThreadToken
0x18006cf5a  mov     r13d, eax
0x18006cf5d  test    eax, eax
0x18006cf5f  js      short loc_18006CEF9
0x18006cf61  mov     r9d, 8; ThreadInformationLength
0x18006cf67  mov     [rsp+98h+ThreadInformation], rbx
0x18006cf6c  lea     r8, [rsp+98h+ThreadInformation]; ThreadInformation
0x18006cf71  mov     edx, 5; ThreadInformationClass
0x18006cf76  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18006cf7d  call    cs:__imp_NtSetInformationThread
0x18006cf83  mov     r13d, eax
0x18006cf86  test    eax, eax
0x18006cf88  js      loc_18006CEF9
0x18006cf8e  mov     [rsp+98h+arg_8], 1
0x18006cf99  jmp     loc_18006CE94
0x18006cf9e  cmp     [rsp+98h+arg_8], 0
0x18006cfa6  jz      short loc_18006CFCA
0x18006cfa8  mov     r9d, 8; ThreadInformationLength
0x18006cfae  lea     r8, [rsp+98h+var_68]; ThreadInformation
0x18006cfb3  mov     edx, 5; ThreadInformationClass
0x18006cfb8  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18006cfbf  call    cs:__imp_NtSetInformationThread
0x18006cfc5  mov     rcx, [rsp+98h+var_68]; Handle
0x18006cfca  call    cs:__imp_NtClose
0x18006cfd0  jmp     loc_18006CF07
0x18006cfd5  mov     ebp, ebx
0x18006cfd7  mov     r12, rbx
0x18006cfda  jmp     loc_18006CE19
```
