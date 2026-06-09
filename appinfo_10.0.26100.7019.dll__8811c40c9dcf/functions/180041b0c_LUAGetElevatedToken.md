# LUAGetElevatedToken

- ea: `0x180041b0c`
- end: `0x180041c1d`
- name: `LUAGetElevatedToken`
- size: `273`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, PHANDLE NewTokenHandle)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001e424`
- `0x1800249f0`

## callees

- `0x180041b0c`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x180041b51`
- `ntdll!NtQueryInformationToken` at `0x180041b8d`
- `ntdll!NtQueryInformationToken` at `0x180041c02`
- `ntdll!NtQueryInformationToken` at `0x180041b51`
- `ntdll!NtQueryInformationToken` at `0x180041b8d`
- `ntdll!NtQueryInformationToken` at `0x180041c02`
- `ntdll!NtDuplicateToken` at `0x180041bdb`
- `ntdll!NtDuplicateToken` at `0x180041bdb`

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
0x180041b0c  push    rbp
0x180041b0e  push    rbx
0x180041b0f  push    rdi
0x180041b10  mov     rbp, rsp
0x180041b13  sub     rsp, 70h
0x180041b17  and     qword ptr [rdx], 0
0x180041b1b  lea     rax, [rbp+arg_10]
0x180041b1f  and     [rbp+arg_10], 0
0x180041b23  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180041b27  and     [rbp+arg_18], 0
0x180041b2b  mov     r9d, 4; TokenInformationLength
0x180041b31  and     [rbp+TokenInformation], 0
0x180041b35  mov     rdi, rdx
0x180041b38  and     [rbp+var_40], 0
0x180041b3d  mov     rbx, rcx
0x180041b40  and     dword ptr [rbp+ObjectAttributes+4], 0
0x180041b44  and     dword ptr [rbp+ObjectAttributes+1Ch], 0
0x180041b48  lea     edx, [r9+0Eh]; TokenInformationClass
0x180041b4c  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x180041b51  call    cs:__imp_NtQueryInformationToken
0x180041b58  nop     dword ptr [rax+rax+00h]
0x180041b5d  mov     ecx, eax
0x180041b5f  test    eax, eax
0x180041b61  js      loc_180041BE9
0x180041b67  cmp     [rbp+TokenInformation], 2
0x180041b6b  jz      short loc_180041BA5
0x180041b6d  cmp     [rbp+TokenInformation], 1
0x180041b71  lea     rax, [rbp+arg_10]
0x180041b75  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x180041b7a  mov     rcx, rbx; TokenHandle
0x180041b7d  jnz     short loc_180041BF4
0x180041b7f  mov     r9d, 4; TokenInformationLength
0x180041b85  lea     r8, [rbp+arg_18]; TokenInformation
0x180041b89  lea     edx, [r9+10h]; TokenInformationClass
0x180041b8d  call    cs:__imp_NtQueryInformationToken
0x180041b94  nop     dword ptr [rax+rax+00h]
0x180041b99  mov     ecx, eax
0x180041b9b  test    eax, eax
0x180041b9d  js      short loc_180041BE9
0x180041b9f  cmp     [rbp+arg_18], 0
0x180041ba3  jz      short loc_180041BE9
0x180041ba5  and     [rbp+ObjectAttributes.RootDirectory], 0
0x180041baa  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180041bae  and     [rbp+ObjectAttributes.Attributes], 0
0x180041bb2  xorps   xmm0, xmm0
0x180041bb5  and     [rbp+ObjectAttributes.ObjectName], 0
0x180041bba  xor     r9d, r9d; EffectiveOnly
0x180041bbd  mov     [rsp+70h+NewTokenHandle], rdi; NewTokenHandle
0x180041bc2  xor     edx, edx; DesiredAccess
0x180041bc4  mov     rcx, rbx; ExistingTokenHandle
0x180041bc7  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180041bce  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180041bd3  mov     dword ptr [rsp+70h+ReturnLength], 1; TokenType
0x180041bdb  call    cs:__imp_NtDuplicateToken
0x180041be2  nop     dword ptr [rax+rax+00h]
0x180041be7  mov     ecx, eax
0x180041be9  mov     eax, ecx
0x180041beb  add     rsp, 70h
0x180041bef  pop     rdi
0x180041bf0  pop     rbx
0x180041bf1  pop     rbp
0x180041bf2  retn
0x180041bf4  mov     r9d, 8; TokenInformationLength
0x180041bfa  lea     r8, [rbp+var_40]; TokenInformation
0x180041bfe  lea     edx, [r9+0Bh]; TokenInformationClass
0x180041c02  call    cs:__imp_NtQueryInformationToken
0x180041c09  nop     dword ptr [rax+rax+00h]
0x180041c0e  mov     ecx, eax
0x180041c10  test    eax, eax
0x180041c12  js      short loc_180041BE9
0x180041c14  mov     rax, [rbp+var_40]
0x180041c18  mov     [rdi], rax
0x180041c1b  jmp     short loc_180041BE9
```
