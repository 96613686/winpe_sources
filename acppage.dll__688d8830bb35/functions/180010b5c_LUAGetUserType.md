# LUAGetUserType

- ea: `0x180010b5c`
- end: `0x180010c5b`
- name: `LUAGetUserType`
- size: `255`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000cb60`

## callees

- `0x180010b5c`
- `0x180010c64`

## import_xrefs

- `ntdll!NtOpenThreadToken` at `0x180010b9a`
- `ntdll!NtOpenThreadToken` at `0x180010b9a`
- `ntdll!NtClose` at `0x180010c46`
- `ntdll!NtClose` at `0x180010c46`
- `ntdll!NtQueryInformationToken` at `0x180010c1d`
- `ntdll!NtQueryInformationToken` at `0x180010c1d`
- `ntdll!NtOpenProcessToken` at `0x180010bb3`
- `ntdll!NtOpenProcessToken` at `0x180010bb3`

## pseudocode

```c
__int64 __fastcall LUAGetUserType(__int64 a1, int *a2)
{
  NTSTATUS v3; // ebx
  void *v4; // rsi
  int v5; // ecx
  int TokenInformation; // [rsp+50h] [rbp+20h] BYREF
  int TokenInformation_4; // [rsp+54h] [rbp+24h]
  ULONG ReturnLength; // [rsp+60h] [rbp+30h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp+38h] BYREF

  TokenInformation_4 = HIDWORD(a1);
  TokenHandle = 0;
  TokenInformation = 0;
  ReturnLength = 0;
  v3 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 0, &TokenHandle);
  if ( v3 == -1073741700 )
    v3 = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, &TokenHandle);
  if ( v3 >= 0 )
  {
    v4 = TokenHandle;
    v3 = LUAIsElevatedToken(TokenHandle);
    if ( v3 >= 0 )
    {
      *a2 = TokenInformation ? 0 : 2 - (ReturnLength != 0);
      TokenInformation = 0;
      ReturnLength = 4;
      v3 = NtQueryInformationToken(TokenHandle, TokenUIAccess, &TokenInformation, 4u, &ReturnLength);
      if ( v3 >= 0 )
      {
        if ( TokenInformation )
        {
          v5 = *a2;
          if ( (unsigned int)(*a2 - 16) > 2 )
            v5 += 16;
          *a2 = v5;
        }
      }
    }
    if ( v4 )
      NtClose(v4);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180010b5c  mov     [rsp-18h+arg_8], rbx
0x180010b61  mov     [rsp-18h+TokenInformation], rcx
0x180010b66  push    rbp
0x180010b67  push    rsi
0x180010b68  push    rdi
0x180010b69  mov     rbp, rsp
0x180010b6c  sub     rsp, 30h
0x180010b70  xor     r8d, r8d; OpenAsSelf
0x180010b73  mov     [rbp+TokenHandle], 0
0x180010b7b  mov     rdi, rdx
0x180010b7e  mov     dword ptr [rbp+TokenInformation], 0
0x180010b85  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180010b89  mov     [rbp+arg_10], 0
0x180010b90  lea     esi, [r8+8]
0x180010b94  mov     edx, esi; DesiredAccess
0x180010b96  lea     rcx, [r8-2]; ThreadHandle
0x180010b9a  call    cs:__imp_NtOpenThreadToken
0x180010ba0  mov     ebx, eax
0x180010ba2  cmp     eax, 0C000007Ch
0x180010ba7  jnz     short loc_180010BBB
0x180010ba9  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180010bad  mov     edx, esi; DesiredAccess
0x180010baf  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180010bb3  call    cs:__imp_NtOpenProcessToken
0x180010bb9  mov     ebx, eax
0x180010bbb  test    ebx, ebx
0x180010bbd  js      loc_180010C4C
0x180010bc3  mov     rsi, [rbp+TokenHandle]
0x180010bc7  lea     r8, [rbp+arg_10]
0x180010bcb  mov     rcx, rsi; TokenHandle
0x180010bce  lea     rdx, [rbp+TokenInformation]
0x180010bd2  call    LUAIsElevatedToken
0x180010bd7  mov     ebx, eax
0x180010bd9  test    eax, eax
0x180010bdb  js      short loc_180010C3E
0x180010bdd  cmp     dword ptr [rbp+TokenInformation], 0
0x180010be1  jz      short loc_180010BEB
0x180010be3  mov     dword ptr [rdi], 0
0x180010be9  jmp     short loc_180010BF7
0x180010beb  mov     eax, [rbp+arg_10]
0x180010bee  neg     eax
0x180010bf0  sbb     ecx, ecx
0x180010bf2  add     ecx, 2
0x180010bf5  mov     [rdi], ecx
0x180010bf7  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180010bfb  lea     rax, [rbp+arg_10]
0x180010bff  mov     r9d, 4; TokenInformationLength
0x180010c05  mov     dword ptr [rbp+TokenInformation], 0
0x180010c0c  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180010c10  mov     [rbp+arg_10], r9d
0x180010c14  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180010c19  lea     edx, [r9+16h]; TokenInformationClass
0x180010c1d  call    cs:__imp_NtQueryInformationToken
0x180010c23  mov     ebx, eax
0x180010c25  test    eax, eax
0x180010c27  js      short loc_180010C3E
0x180010c29  cmp     dword ptr [rbp+TokenInformation], 0
0x180010c2d  jz      short loc_180010C3E
0x180010c2f  mov     ecx, [rdi]
0x180010c31  lea     eax, [rcx-10h]
0x180010c34  cmp     eax, 2
0x180010c37  jbe     short loc_180010C3C
0x180010c39  add     ecx, 10h
0x180010c3c  mov     [rdi], ecx
0x180010c3e  test    rsi, rsi
0x180010c41  jz      short loc_180010C4C
0x180010c43  mov     rcx, rsi; Handle
0x180010c46  call    cs:__imp_NtClose
0x180010c4c  mov     eax, ebx
0x180010c4e  mov     rbx, [rsp+30h+arg_8]
0x180010c53  add     rsp, 30h
0x180010c57  pop     rdi
0x180010c58  pop     rsi
0x180010c59  pop     rbp
0x180010c5a  retn
```
