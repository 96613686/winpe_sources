# LUAGetElevatedToken

- ea: `0x180045e88`
- end: `0x180045f9b`
- name: `LUAGetElevatedToken`
- size: `275`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, PHANDLE NewTokenHandle)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180021968`
- `0x180026ba0`

## callees

- `0x180045e88`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x180045ee3`
- `ntdll!NtQueryInformationToken` at `0x180045f15`
- `ntdll!NtQueryInformationToken` at `0x180045f86`
- `ntdll!NtQueryInformationToken` at `0x180045ee3`
- `ntdll!NtQueryInformationToken` at `0x180045f15`
- `ntdll!NtQueryInformationToken` at `0x180045f86`
- `ntdll!NtDuplicateToken` at `0x180045f66`
- `ntdll!NtDuplicateToken` at `0x180045f66`

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
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v4 = NtQueryInformationToken(TokenHandle, TokenElevationType, &TokenInformation, 4u, &ReturnLength);
  if ( v4 >= 0 )
  {
    if ( TokenInformation == 2 )
    {
LABEL_6:
      ObjectAttributes.Length = 48;
      memset(&ObjectAttributes.RootDirectory, 0, 20);
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
0x180045e88  push    rbp
0x180045e8a  push    rbx
0x180045e8b  push    rdi
0x180045e8c  mov     rbp, rsp
0x180045e8f  sub     rsp, 70h
0x180045e93  xorps   xmm0, xmm0
0x180045e96  mov     qword ptr [rdx], 0
0x180045e9d  mov     r9d, 4; TokenInformationLength
0x180045ea3  mov     [rbp+arg_10], 0
0x180045eaa  mov     rdi, rdx
0x180045ead  mov     [rbp+arg_18], 0
0x180045eb4  lea     rax, [rbp+arg_10]
0x180045eb8  mov     [rbp+TokenInformation], 0
0x180045ebf  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180045ec3  mov     [rbp+var_40], 0
0x180045ecb  lea     edx, [r9+0Eh]; TokenInformationClass
0x180045ecf  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x180045ed4  mov     rbx, rcx
0x180045ed7  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180045edb  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180045edf  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180045ee3  call    cs:__imp_NtQueryInformationToken
0x180045ee9  mov     ecx, eax
0x180045eeb  test    eax, eax
0x180045eed  js      short loc_180045F6E
0x180045eef  cmp     [rbp+TokenInformation], 2
0x180045ef3  jz      short loc_180045F27
0x180045ef5  cmp     [rbp+TokenInformation], 1
0x180045ef9  lea     rax, [rbp+arg_10]
0x180045efd  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x180045f02  mov     rcx, rbx; TokenHandle
0x180045f05  jnz     short loc_180045F78
0x180045f07  mov     r9d, 4; TokenInformationLength
0x180045f0d  lea     r8, [rbp+arg_18]; TokenInformation
0x180045f11  lea     edx, [r9+10h]; TokenInformationClass
0x180045f15  call    cs:__imp_NtQueryInformationToken
0x180045f1b  mov     ecx, eax
0x180045f1d  test    eax, eax
0x180045f1f  js      short loc_180045F6E
0x180045f21  cmp     [rbp+arg_18], 0
0x180045f25  jz      short loc_180045F6E
0x180045f27  xorps   xmm0, xmm0
0x180045f2a  mov     [rsp+70h+NewTokenHandle], rdi; NewTokenHandle
0x180045f2f  xor     r9d, r9d; EffectiveOnly
0x180045f32  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180045f39  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180045f3d  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x180045f45  xor     edx, edx; DesiredAccess
0x180045f47  mov     [rbp+ObjectAttributes.Attributes], 0
0x180045f4e  mov     rcx, rbx; ExistingTokenHandle
0x180045f51  mov     [rbp+ObjectAttributes.ObjectName], 0
0x180045f59  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180045f5e  mov     dword ptr [rsp+70h+ReturnLength], 1; TokenType
0x180045f66  call    cs:__imp_NtDuplicateToken
0x180045f6c  mov     ecx, eax
0x180045f6e  mov     eax, ecx
0x180045f70  add     rsp, 70h
0x180045f74  pop     rdi
0x180045f75  pop     rbx
0x180045f76  pop     rbp
0x180045f77  retn
0x180045f78  mov     r9d, 8; TokenInformationLength
0x180045f7e  lea     r8, [rbp+var_40]; TokenInformation
0x180045f82  lea     edx, [r9+0Bh]; TokenInformationClass
0x180045f86  call    cs:__imp_NtQueryInformationToken
0x180045f8c  mov     ecx, eax
0x180045f8e  test    eax, eax
0x180045f90  js      short loc_180045F6E
0x180045f92  mov     rax, [rbp+var_40]
0x180045f96  mov     [rdi], rax
0x180045f99  jmp     short loc_180045F6E
```
