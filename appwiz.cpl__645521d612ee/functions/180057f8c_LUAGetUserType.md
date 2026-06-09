# LUAGetUserType

- ea: `0x180057f8c`
- end: `0x180058081`
- name: `LUAGetUserType`
- size: `245`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18004fc80`

## callees

- `0x180057f8c`
- `0x180058088`

## import_xrefs

- `ntdll!NtOpenThreadToken` at `0x180057fc0`
- `ntdll!NtOpenThreadToken` at `0x180057fc0`
- `ntdll!NtClose` at `0x18005806c`
- `ntdll!NtClose` at `0x18005806c`
- `ntdll!NtQueryInformationToken` at `0x180058043`
- `ntdll!NtQueryInformationToken` at `0x180058043`
- `ntdll!NtOpenProcessToken` at `0x180057fd9`
- `ntdll!NtOpenProcessToken` at `0x180057fd9`

## pseudocode

```c
__int64 __fastcall LUAGetUserType(void *a1, int *a2)
{
  void *v2; // rsi
  NTSTATUS v4; // ebx
  int v5; // ecx
  void *TokenHandle; // [rsp+50h] [rbp+20h] BYREF
  int TokenInformation; // [rsp+60h] [rbp+30h] BYREF
  ULONG ReturnLength; // [rsp+68h] [rbp+38h] BYREF

  TokenHandle = a1;
  v2 = 0;
  TokenInformation = 0;
  ReturnLength = 0;
  if ( a1 )
  {
LABEL_6:
    v4 = LUAIsElevatedToken(a1);
    if ( v4 >= 0 )
    {
      *a2 = TokenInformation ? 0 : 2 - (ReturnLength != 0);
      TokenInformation = 0;
      ReturnLength = 4;
      v4 = NtQueryInformationToken(TokenHandle, TokenUIAccess, &TokenInformation, 4u, &ReturnLength);
      if ( v4 >= 0 )
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
    if ( v2 )
      NtClose(v2);
    return (unsigned int)v4;
  }
  v4 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 0, &TokenHandle);
  if ( v4 == -1073741700 )
    v4 = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, &TokenHandle);
  if ( v4 >= 0 )
  {
    a1 = TokenHandle;
    v2 = TokenHandle;
    goto LABEL_6;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180057f8c  mov     [rsp-18h+arg_8], rbx
0x180057f91  mov     [rsp-18h+TokenHandle], rcx
0x180057f96  push    rbp
0x180057f97  push    rsi
0x180057f98  push    rdi
0x180057f99  mov     rbp, rsp
0x180057f9c  sub     rsp, 30h
0x180057fa0  xor     esi, esi
0x180057fa2  mov     rdi, rdx
0x180057fa5  mov     [rbp+TokenInformation], esi
0x180057fa8  mov     [rbp+arg_18], esi
0x180057fab  test    rcx, rcx
0x180057fae  jnz     short loc_180057FF0
0x180057fb0  lea     esi, [rcx+8]
0x180057fb3  xor     r8d, r8d; OpenAsSelf
0x180057fb6  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180057fba  mov     edx, esi; DesiredAccess
0x180057fbc  lea     rcx, [r8-2]; ThreadHandle
0x180057fc0  call    cs:__imp_NtOpenThreadToken
0x180057fc6  mov     ebx, eax
0x180057fc8  cmp     eax, 0C000007Ch
0x180057fcd  jnz     short loc_180057FE1
0x180057fcf  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180057fd3  mov     edx, esi; DesiredAccess
0x180057fd5  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180057fd9  call    cs:__imp_NtOpenProcessToken
0x180057fdf  mov     ebx, eax
0x180057fe1  test    ebx, ebx
0x180057fe3  js      loc_180058072
0x180057fe9  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180057fed  mov     rsi, rcx
0x180057ff0  lea     r8, [rbp+arg_18]
0x180057ff4  lea     rdx, [rbp+TokenInformation]
0x180057ff8  call    LUAIsElevatedToken
0x180057ffd  mov     ebx, eax
0x180057fff  test    eax, eax
0x180058001  js      short loc_180058064
0x180058003  cmp     [rbp+TokenInformation], 0
0x180058007  jz      short loc_180058011
0x180058009  mov     dword ptr [rdi], 0
0x18005800f  jmp     short loc_18005801D
0x180058011  mov     eax, [rbp+arg_18]
0x180058014  neg     eax
0x180058016  sbb     ecx, ecx
0x180058018  add     ecx, 2
0x18005801b  mov     [rdi], ecx
0x18005801d  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180058021  lea     rax, [rbp+arg_18]
0x180058025  mov     r9d, 4; TokenInformationLength
0x18005802b  mov     [rbp+TokenInformation], 0
0x180058032  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180058036  mov     [rbp+arg_18], r9d
0x18005803a  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18005803f  lea     edx, [r9+16h]; TokenInformationClass
0x180058043  call    cs:__imp_NtQueryInformationToken
0x180058049  mov     ebx, eax
0x18005804b  test    eax, eax
0x18005804d  js      short loc_180058064
0x18005804f  cmp     [rbp+TokenInformation], 0
0x180058053  jz      short loc_180058064
0x180058055  mov     ecx, [rdi]
0x180058057  lea     eax, [rcx-10h]
0x18005805a  cmp     eax, 2
0x18005805d  jbe     short loc_180058062
0x18005805f  add     ecx, 10h
0x180058062  mov     [rdi], ecx
0x180058064  test    rsi, rsi
0x180058067  jz      short loc_180058072
0x180058069  mov     rcx, rsi; Handle
0x18005806c  call    cs:__imp_NtClose
0x180058072  mov     eax, ebx
0x180058074  mov     rbx, [rsp+30h+arg_8]
0x180058079  add     rsp, 30h
0x18005807d  pop     rdi
0x18005807e  pop     rsi
0x18005807f  pop     rbp
0x180058080  retn
```
