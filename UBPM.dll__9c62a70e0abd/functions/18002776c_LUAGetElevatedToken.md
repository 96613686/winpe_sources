# LUAGetElevatedToken

- ea: `0x18002776c`
- end: `0x180027898`
- name: `LUAGetElevatedToken`
- size: `300`
- prototype: `__int64 __fastcall(HANDLE ExistingTokenHandle, PHANDLE NewTokenHandle)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800275bc`

## callees

- `0x18002776c`

## import_xrefs

- `ntdll!NtDuplicateToken` at `0x180027888`
- `ntdll!NtDuplicateToken` at `0x180027888`
- `ntdll!NtQueryInformationToken` at `0x1800277c7`
- `ntdll!NtQueryInformationToken` at `0x1800277ff`
- `ntdll!NtQueryInformationToken` at `0x180027831`
- `ntdll!NtQueryInformationToken` at `0x1800277c7`
- `ntdll!NtQueryInformationToken` at `0x1800277ff`
- `ntdll!NtQueryInformationToken` at `0x180027831`

## pseudocode

```c
__int64 __fastcall LUAGetElevatedToken(HANDLE ExistingTokenHandle, PHANDLE NewTokenHandle)
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
  v4 = NtQueryInformationToken(ExistingTokenHandle, TokenElevationType, &TokenInformation, 4u, &ReturnLength);
  if ( v4 < 0 )
    return (unsigned int)v4;
  if ( TokenInformation == 2 )
  {
LABEL_9:
    ObjectAttributes.Length = 48;
    memset(&ObjectAttributes.RootDirectory, 0, 20);
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    return (unsigned int)NtDuplicateToken(ExistingTokenHandle, 0, &ObjectAttributes, 0, TokenPrimary, NewTokenHandle);
  }
  if ( TokenInformation == 1 )
  {
    v4 = NtQueryInformationToken(ExistingTokenHandle, TokenElevation, &v10, 4u, &ReturnLength);
    if ( v4 < 0 || !v10 )
      return (unsigned int)v4;
    goto LABEL_9;
  }
  v4 = NtQueryInformationToken(ExistingTokenHandle, TokenLinkedToken, &v6, 8u, &ReturnLength);
  if ( v4 >= 0 )
    *NewTokenHandle = v6;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18002776c  push    rbp
0x18002776e  push    rbx
0x18002776f  push    rdi
0x180027770  mov     rbp, rsp
0x180027773  sub     rsp, 70h
0x180027777  xorps   xmm0, xmm0
0x18002777a  mov     qword ptr [rdx], 0
0x180027781  mov     r9d, 4; TokenInformationLength
0x180027787  mov     [rbp+arg_10], 0
0x18002778e  mov     rdi, rdx
0x180027791  mov     [rbp+arg_18], 0
0x180027798  lea     rax, [rbp+arg_10]
0x18002779c  mov     [rbp+TokenInformation], 0
0x1800277a3  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1800277a7  mov     [rbp+var_40], 0
0x1800277af  lea     edx, [r9+0Eh]; TokenInformationClass
0x1800277b3  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x1800277b8  mov     rbx, rcx
0x1800277bb  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1800277bf  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1800277c3  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800277c7  call    cs:__imp_NtQueryInformationToken
0x1800277ce  nop     dword ptr [rax+rax+00h]
0x1800277d3  mov     ecx, eax
0x1800277d5  test    eax, eax
0x1800277d7  js      short loc_180027818
0x1800277d9  cmp     [rbp+TokenInformation], 2
0x1800277dd  jz      short loc_180027849
0x1800277df  cmp     [rbp+TokenInformation], 1
0x1800277e3  lea     rax, [rbp+arg_10]
0x1800277e7  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x1800277ec  mov     rcx, rbx; TokenHandle
0x1800277ef  jz      short loc_180027823
0x1800277f1  mov     r9d, 8; TokenInformationLength
0x1800277f7  lea     r8, [rbp+var_40]; TokenInformation
0x1800277fb  lea     edx, [r9+0Bh]; TokenInformationClass
0x1800277ff  call    cs:__imp_NtQueryInformationToken
0x180027806  nop     dword ptr [rax+rax+00h]
0x18002780b  mov     ecx, eax
0x18002780d  test    eax, eax
0x18002780f  js      short loc_180027818
0x180027811  mov     rax, [rbp+var_40]
0x180027815  mov     [rdi], rax
0x180027818  mov     eax, ecx
0x18002781a  add     rsp, 70h
0x18002781e  pop     rdi
0x18002781f  pop     rbx
0x180027820  pop     rbp
0x180027821  retn
0x180027823  mov     r9d, 4; TokenInformationLength
0x180027829  lea     r8, [rbp+arg_18]; TokenInformation
0x18002782d  lea     edx, [r9+10h]; TokenInformationClass
0x180027831  call    cs:__imp_NtQueryInformationToken
0x180027838  nop     dword ptr [rax+rax+00h]
0x18002783d  mov     ecx, eax
0x18002783f  test    eax, eax
0x180027841  js      short loc_180027818
0x180027843  cmp     [rbp+arg_18], 0
0x180027847  jz      short loc_180027818
0x180027849  xorps   xmm0, xmm0
0x18002784c  mov     [rsp+70h+NewTokenHandle], rdi; NewTokenHandle
0x180027851  xor     r9d, r9d; EffectiveOnly
0x180027854  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18002785b  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18002785f  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x180027867  xor     edx, edx; DesiredAccess
0x180027869  mov     [rbp+ObjectAttributes.Attributes], 0
0x180027870  mov     rcx, rbx; ExistingTokenHandle
0x180027873  mov     [rbp+ObjectAttributes.ObjectName], 0
0x18002787b  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180027880  mov     dword ptr [rsp+70h+ReturnLength], 1; TokenType
0x180027888  call    cs:__imp_NtDuplicateToken
0x18002788f  nop     dword ptr [rax+rax+00h]
0x180027894  mov     ecx, eax
0x180027896  jmp     short loc_180027818
```
