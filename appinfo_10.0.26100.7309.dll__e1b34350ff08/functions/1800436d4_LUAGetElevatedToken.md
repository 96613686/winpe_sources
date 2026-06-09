# LUAGetElevatedToken

- ea: `0x1800436d4`
- end: `0x1800437e5`
- name: `LUAGetElevatedToken`
- size: `273`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, PHANDLE NewTokenHandle)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001e804`
- `0x1800230e0`

## callees

- `0x1800436d4`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x180043719`
- `ntdll!NtQueryInformationToken` at `0x180043755`
- `ntdll!NtQueryInformationToken` at `0x1800437ca`
- `ntdll!NtQueryInformationToken` at `0x180043719`
- `ntdll!NtQueryInformationToken` at `0x180043755`
- `ntdll!NtQueryInformationToken` at `0x1800437ca`
- `ntdll!NtDuplicateToken` at `0x1800437a3`
- `ntdll!NtDuplicateToken` at `0x1800437a3`

## pseudocode

```c
__int64 __fastcall LUAGetElevatedToken(HANDLE TokenHandle, PHANDLE NewTokenHandle)
{
  NTSTATUS v4; // ecx
  void *v6; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+38h] [rbp-38h] BYREF
  int TokenInformation; // [rsp+98h] [rbp+28h] BYREF
  ULONG ReturnLength; // [rsp+A0h] [rbp+30h] BYREF
  int v10; // [rsp+A8h] [rbp+38h] BYREF

  *NewTokenHandle = 0;
  ReturnLength = 0;
  v10 = 0;
  TokenInformation = 0;
  v6 = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  v4 = NtQueryInformationToken(TokenHandle, TokenElevationType, &TokenInformation, 4u, &ReturnLength);
  if ( v4 >= 0 )
  {
    if ( TokenInformation == 2 )
    {
LABEL_6:
      memset(&ObjectAttributes.RootDirectory, 0, 20);
      ObjectAttributes.Length = 48;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      return (unsigned int)NtDuplicateToken(TokenHandle, 0, &ObjectAttributes, 0, TokenPrimary, NewTokenHandle);
    }
    if ( TokenInformation == 1 )
    {
      v4 = NtQueryInformationToken(TokenHandle, TokenElevation, &v10, 4u, &ReturnLength);
      if ( v4 >= 0 && v10 )
        goto LABEL_6;
    }
    else
    {
      v4 = NtQueryInformationToken(TokenHandle, TokenLinkedToken, &v6, 8u, &ReturnLength);
      if ( v4 >= 0 )
        *NewTokenHandle = v6;
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800436d4  push    rbp
0x1800436d6  push    rbx
0x1800436d7  push    rdi
0x1800436d8  mov     rbp, rsp
0x1800436db  sub     rsp, 70h
0x1800436df  and     qword ptr [rdx], 0
0x1800436e3  lea     rax, [rbp+arg_10]
0x1800436e7  and     [rbp+arg_10], 0
0x1800436eb  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1800436ef  and     [rbp+arg_18], 0
0x1800436f3  mov     r9d, 4; TokenInformationLength
0x1800436f9  and     [rbp+TokenInformation], 0
0x1800436fd  mov     rdi, rdx
0x180043700  and     [rbp+var_40], 0
0x180043705  mov     rbx, rcx
0x180043708  and     dword ptr [rbp+ObjectAttributes+4], 0
0x18004370c  and     dword ptr [rbp+ObjectAttributes+1Ch], 0
0x180043710  lea     edx, [r9+0Eh]; TokenInformationClass
0x180043714  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x180043719  call    cs:__imp_NtQueryInformationToken
0x180043720  nop     dword ptr [rax+rax+00h]
0x180043725  mov     ecx, eax
0x180043727  test    eax, eax
0x180043729  js      loc_1800437B1
0x18004372f  cmp     [rbp+TokenInformation], 2
0x180043733  jz      short loc_18004376D
0x180043735  cmp     [rbp+TokenInformation], 1
0x180043739  lea     rax, [rbp+arg_10]
0x18004373d  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x180043742  mov     rcx, rbx; TokenHandle
0x180043745  jnz     short loc_1800437BC
0x180043747  mov     r9d, 4; TokenInformationLength
0x18004374d  lea     r8, [rbp+arg_18]; TokenInformation
0x180043751  lea     edx, [r9+10h]; TokenInformationClass
0x180043755  call    cs:__imp_NtQueryInformationToken
0x18004375c  nop     dword ptr [rax+rax+00h]
0x180043761  mov     ecx, eax
0x180043763  test    eax, eax
0x180043765  js      short loc_1800437B1
0x180043767  cmp     [rbp+arg_18], 0
0x18004376b  jz      short loc_1800437B1
0x18004376d  and     [rbp+ObjectAttributes.RootDirectory], 0
0x180043772  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180043776  and     [rbp+ObjectAttributes.Attributes], 0
0x18004377a  xorps   xmm0, xmm0
0x18004377d  and     [rbp+ObjectAttributes.ObjectName], 0
0x180043782  xor     r9d, r9d; EffectiveOnly
0x180043785  mov     [rsp+70h+NewTokenHandle], rdi; NewTokenHandle
0x18004378a  xor     edx, edx; DesiredAccess
0x18004378c  mov     rcx, rbx; ExistingTokenHandle
0x18004378f  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180043796  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18004379b  mov     dword ptr [rsp+70h+ReturnLength], 1; TokenType
0x1800437a3  call    cs:__imp_NtDuplicateToken
0x1800437aa  nop     dword ptr [rax+rax+00h]
0x1800437af  mov     ecx, eax
0x1800437b1  mov     eax, ecx
0x1800437b3  add     rsp, 70h
0x1800437b7  pop     rdi
0x1800437b8  pop     rbx
0x1800437b9  pop     rbp
0x1800437ba  retn
0x1800437bc  mov     r9d, 8; TokenInformationLength
0x1800437c2  lea     r8, [rbp+var_40]; TokenInformation
0x1800437c6  lea     edx, [r9+0Bh]; TokenInformationClass
0x1800437ca  call    cs:__imp_NtQueryInformationToken
0x1800437d1  nop     dword ptr [rax+rax+00h]
0x1800437d6  mov     ecx, eax
0x1800437d8  test    eax, eax
0x1800437da  js      short loc_1800437B1
0x1800437dc  mov     rax, [rbp+var_40]
0x1800437e0  mov     [rdi], rax
0x1800437e3  jmp     short loc_1800437B1
```
