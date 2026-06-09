# CheckLowboxAccess

- ea: `0x1800019b0`
- end: `0x180001a8b`
- name: `CheckLowboxAccess`
- size: `219`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800016d0`

## callees

- `0x1800019b0`

## import_xrefs

- `ntdll!NtClose` at `0x180001a4f`
- `ntdll!NtClose` at `0x180001a4f`
- `ntdll!NtQueryInformationToken` at `0x180001a30`
- `ntdll!NtQueryInformationToken` at `0x180001a30`
- `ntdll!NtOpenThreadToken` at `0x180001a07`
- `ntdll!NtOpenThreadToken` at `0x180001a07`
- `RPCRT4!RpcImpersonateClient` at `0x1800019e0`
- `RPCRT4!RpcImpersonateClient` at `0x1800019e0`
- `RPCRT4!RpcRevertToSelfEx` at `0x180001a5b`
- `RPCRT4!RpcRevertToSelfEx` at `0x180001a5b`

## pseudocode

```c
__int64 __fastcall CheckLowboxAccess(_DWORD *a1)
{
  RPC_STATUS v2; // ebx
  int v3; // ebp
  RPC_STATUS v4; // edi
  int v5; // esi
  int TokenInformation; // [rsp+60h] [rbp+8h] BYREF
  ULONG ReturnLength; // [rsp+68h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+70h] [rbp+18h] BYREF

  *a1 = 0;
  v2 = 0;
  TokenHandle = 0;
  TokenInformation = 0;
  v3 = 0;
  ReturnLength = 0;
  v4 = RpcImpersonateClient(0);
  v5 = 1;
  if ( !v4 )
  {
    v3 = 1;
    if ( NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 0, &TokenHandle) < 0 )
    {
      v4 = 5;
    }
    else
    {
      v4 = NtQueryInformationToken(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength);
      if ( v4 >= 0 && !TokenInformation )
        *a1 = 1;
    }
  }
  if ( TokenHandle )
    NtClose(TokenHandle);
  if ( !v3 || (v2 = RpcRevertToSelfEx(0), v2 >= 0) )
    v5 = 0;
  if ( !v5 )
    return (unsigned int)v4;
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800019b0  mov     [rsp+arg_18], rbx
0x1800019b5  push    rbp
0x1800019b6  push    rsi
0x1800019b7  push    rdi
0x1800019b8  push    r14
0x1800019ba  push    r15
0x1800019bc  sub     rsp, 30h
0x1800019c0  xor     r15d, r15d
0x1800019c3  mov     r14, rcx
0x1800019c6  mov     [rcx], r15d
0x1800019c9  mov     ebx, r15d
0x1800019cc  xor     ecx, ecx; BindingHandle
0x1800019ce  mov     [rsp+58h+TokenHandle], r15
0x1800019d3  mov     [rsp+58h+TokenInformation], r15d
0x1800019d8  mov     ebp, r15d
0x1800019db  mov     [rsp+58h+arg_8], r15d
0x1800019e0  call    cs:__imp_RpcImpersonateClient
0x1800019e6  mov     edi, eax
0x1800019e8  mov     esi, 1
0x1800019ed  test    eax, eax
0x1800019ef  jnz     short loc_180001A45
0x1800019f1  lea     r9, [rsp+58h+TokenHandle]; TokenHandle
0x1800019f6  xor     r8d, r8d; OpenAsSelf
0x1800019f9  mov     edx, 8; DesiredAccess
0x1800019fe  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180001a05  mov     ebp, esi
0x180001a07  call    cs:__imp_NtOpenThreadToken
0x180001a0d  test    eax, eax
0x180001a0f  js      short loc_180001A84
0x180001a11  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x180001a16  lea     rax, [rsp+58h+arg_8]
0x180001a1b  mov     r9d, 4; TokenInformationLength
0x180001a21  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180001a26  lea     r8, [rsp+58h+TokenInformation]; TokenInformation
0x180001a2b  mov     edx, 1Dh; TokenInformationClass
0x180001a30  call    cs:__imp_NtQueryInformationToken
0x180001a36  mov     edi, eax
0x180001a38  test    eax, eax
0x180001a3a  js      short loc_180001A45
0x180001a3c  cmp     [rsp+58h+TokenInformation], ebx
0x180001a40  jnz     short loc_180001A45
0x180001a42  mov     [r14], esi
0x180001a45  mov     rcx, [rsp+58h+TokenHandle]; Handle
0x180001a4a  test    rcx, rcx
0x180001a4d  jz      short loc_180001A55
0x180001a4f  call    cs:__imp_NtClose
0x180001a55  test    ebp, ebp
0x180001a57  jz      short loc_180001A7F
0x180001a59  xor     ecx, ecx; BindingHandle
0x180001a5b  call    cs:__imp_RpcRevertToSelfEx
0x180001a61  mov     ebx, eax
0x180001a63  test    eax, eax
0x180001a65  jns     short loc_180001A7F
0x180001a67  test    esi, esi
0x180001a69  cmovz   ebx, edi
0x180001a6c  mov     eax, ebx
0x180001a6e  mov     rbx, [rsp+58h+arg_18]
0x180001a73  add     rsp, 30h
0x180001a77  pop     r15
0x180001a79  pop     r14
0x180001a7b  pop     rdi
0x180001a7c  pop     rsi
0x180001a7d  pop     rbp
0x180001a7e  retn
0x180001a7f  mov     esi, r15d
0x180001a82  jmp     short loc_180001A67
0x180001a84  mov     edi, 5
0x180001a89  jmp     short loc_180001A45
```
