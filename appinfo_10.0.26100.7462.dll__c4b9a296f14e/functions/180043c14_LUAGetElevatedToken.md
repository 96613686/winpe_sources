# LUAGetElevatedToken

- ea: `0x180043c14`
- end: `0x180043d25`
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

- `0x180043c14`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x180043c59`
- `ntdll!NtQueryInformationToken` at `0x180043c95`
- `ntdll!NtQueryInformationToken` at `0x180043d0a`
- `ntdll!NtQueryInformationToken` at `0x180043c59`
- `ntdll!NtQueryInformationToken` at `0x180043c95`
- `ntdll!NtQueryInformationToken` at `0x180043d0a`
- `ntdll!NtDuplicateToken` at `0x180043ce3`
- `ntdll!NtDuplicateToken` at `0x180043ce3`

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
0x180043c14  push    rbp
0x180043c16  push    rbx
0x180043c17  push    rdi
0x180043c18  mov     rbp, rsp
0x180043c1b  sub     rsp, 70h
0x180043c1f  and     qword ptr [rdx], 0
0x180043c23  lea     rax, [rbp+arg_10]
0x180043c27  and     [rbp+arg_10], 0
0x180043c2b  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180043c2f  and     [rbp+arg_18], 0
0x180043c33  mov     r9d, 4; TokenInformationLength
0x180043c39  and     [rbp+TokenInformation], 0
0x180043c3d  mov     rdi, rdx
0x180043c40  and     [rbp+var_40], 0
0x180043c45  mov     rbx, rcx
0x180043c48  and     dword ptr [rbp+ObjectAttributes+4], 0
0x180043c4c  and     dword ptr [rbp+ObjectAttributes+1Ch], 0
0x180043c50  lea     edx, [r9+0Eh]; TokenInformationClass
0x180043c54  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x180043c59  call    cs:__imp_NtQueryInformationToken
0x180043c60  nop     dword ptr [rax+rax+00h]
0x180043c65  mov     ecx, eax
0x180043c67  test    eax, eax
0x180043c69  js      loc_180043CF1
0x180043c6f  cmp     [rbp+TokenInformation], 2
0x180043c73  jz      short loc_180043CAD
0x180043c75  cmp     [rbp+TokenInformation], 1
0x180043c79  lea     rax, [rbp+arg_10]
0x180043c7d  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x180043c82  mov     rcx, rbx; TokenHandle
0x180043c85  jnz     short loc_180043CFC
0x180043c87  mov     r9d, 4; TokenInformationLength
0x180043c8d  lea     r8, [rbp+arg_18]; TokenInformation
0x180043c91  lea     edx, [r9+10h]; TokenInformationClass
0x180043c95  call    cs:__imp_NtQueryInformationToken
0x180043c9c  nop     dword ptr [rax+rax+00h]
0x180043ca1  mov     ecx, eax
0x180043ca3  test    eax, eax
0x180043ca5  js      short loc_180043CF1
0x180043ca7  cmp     [rbp+arg_18], 0
0x180043cab  jz      short loc_180043CF1
0x180043cad  and     [rbp+ObjectAttributes.RootDirectory], 0
0x180043cb2  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180043cb6  and     [rbp+ObjectAttributes.Attributes], 0
0x180043cba  xorps   xmm0, xmm0
0x180043cbd  and     [rbp+ObjectAttributes.ObjectName], 0
0x180043cc2  xor     r9d, r9d; EffectiveOnly
0x180043cc5  mov     [rsp+70h+NewTokenHandle], rdi; NewTokenHandle
0x180043cca  xor     edx, edx; DesiredAccess
0x180043ccc  mov     rcx, rbx; ExistingTokenHandle
0x180043ccf  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180043cd6  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180043cdb  mov     dword ptr [rsp+70h+ReturnLength], 1; TokenType
0x180043ce3  call    cs:__imp_NtDuplicateToken
0x180043cea  nop     dword ptr [rax+rax+00h]
0x180043cef  mov     ecx, eax
0x180043cf1  mov     eax, ecx
0x180043cf3  add     rsp, 70h
0x180043cf7  pop     rdi
0x180043cf8  pop     rbx
0x180043cf9  pop     rbp
0x180043cfa  retn
0x180043cfc  mov     r9d, 8; TokenInformationLength
0x180043d02  lea     r8, [rbp+var_40]; TokenInformation
0x180043d06  lea     edx, [r9+0Bh]; TokenInformationClass
0x180043d0a  call    cs:__imp_NtQueryInformationToken
0x180043d11  nop     dword ptr [rax+rax+00h]
0x180043d16  mov     ecx, eax
0x180043d18  test    eax, eax
0x180043d1a  js      short loc_180043CF1
0x180043d1c  mov     rax, [rbp+var_40]
0x180043d20  mov     [rdi], rax
0x180043d23  jmp     short loc_180043CF1
```
