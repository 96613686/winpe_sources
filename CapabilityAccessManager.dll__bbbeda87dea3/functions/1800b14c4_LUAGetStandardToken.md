# LUAGetStandardToken

- ea: `0x1800b14c4`
- end: `0x1800b15e3`
- name: `LUAGetStandardToken`
- size: `287`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, PHANDLE NewTokenHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180064304`

## callees

- `0x1800b1488`
- `0x1800b14c4`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x1800b152d`
- `ntdll!NtQueryInformationToken` at `0x1800b155f`
- `ntdll!NtQueryInformationToken` at `0x1800b158b`
- `ntdll!NtQueryInformationToken` at `0x1800b15ce`
- `ntdll!NtQueryInformationToken` at `0x1800b152d`
- `ntdll!NtQueryInformationToken` at `0x1800b155f`
- `ntdll!NtQueryInformationToken` at `0x1800b158b`
- `ntdll!NtQueryInformationToken` at `0x1800b15ce`
- `ntdll!NtDuplicateToken` at `0x1800b15ae`
- `ntdll!NtDuplicateToken` at `0x1800b15ae`

## pseudocode

```c
__int64 __fastcall LUAGetStandardToken(HANDLE TokenHandle, PHANDLE NewTokenHandle)
{
  NTSTATUS v5; // ecx
  TOKEN_TYPE TokenType; // [rsp+30h] [rbp-10h] BYREF
  void *v7; // [rsp+38h] [rbp-8h] BYREF
  ULONG ReturnLength; // [rsp+68h] [rbp+28h] BYREF
  int TokenInformation; // [rsp+70h] [rbp+30h] BYREF
  int v10; // [rsp+78h] [rbp+38h] BYREF

  ReturnLength = 0;
  TokenType = 0;
  v10 = 0;
  TokenInformation = 0;
  v7 = 0;
  *NewTokenHandle = 0;
  if ( !(unsigned int)Feature_ShadowAdmin__private_IsEnabledDeviceUsageNoInline() )
    return 3221225474LL;
  v5 = NtQueryInformationToken(TokenHandle, TokenElevationType, &TokenInformation, 4u, &ReturnLength);
  if ( v5 >= 0 )
  {
    if ( TokenInformation == 3 )
      goto LABEL_8;
    if ( TokenInformation != 1 )
    {
      v5 = NtQueryInformationToken(TokenHandle, TokenLinkedToken, &v7, 8u, &ReturnLength);
      if ( v5 >= 0 )
        *NewTokenHandle = v7;
      return (unsigned int)v5;
    }
    v5 = NtQueryInformationToken(TokenHandle, TokenElevation, &v10, 4u, &ReturnLength);
    if ( v5 >= 0 && !v10 )
    {
LABEL_8:
      v5 = NtQueryInformationToken(TokenHandle, TokenType, &TokenType, 4u, &ReturnLength);
      if ( v5 >= 0 )
        return (unsigned int)NtDuplicateToken(TokenHandle, 0, 0, 0, TokenType, NewTokenHandle);
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800b14c4  push    rbp
0x1800b14c6  push    rbx
0x1800b14c7  push    rdi
0x1800b14c8  mov     rbp, rsp
0x1800b14cb  sub     rsp, 40h
0x1800b14cf  mov     rdi, rdx
0x1800b14d2  mov     [rbp+arg_8], 0
0x1800b14d9  mov     rbx, rcx
0x1800b14dc  mov     [rbp+TokenType], 0
0x1800b14e3  mov     [rbp+arg_18], 0
0x1800b14ea  mov     [rbp+TokenInformation], 0
0x1800b14f1  mov     [rbp+var_8], 0
0x1800b14f9  mov     qword ptr [rdx], 0
0x1800b1500  call    Feature_ShadowAdmin__private_IsEnabledDeviceUsageNoInline
0x1800b1505  test    eax, eax
0x1800b1507  jnz     short loc_1800B1513
0x1800b1509  mov     eax, 0C0000002h
0x1800b150e  jmp     loc_1800B15B8
0x1800b1513  mov     r9d, 4; TokenInformationLength
0x1800b1519  lea     rax, [rbp+arg_8]
0x1800b151d  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1800b1521  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x1800b1526  mov     rcx, rbx; TokenHandle
0x1800b1529  lea     edx, [r9+0Eh]; TokenInformationClass
0x1800b152d  call    cs:__imp_NtQueryInformationToken
0x1800b1533  mov     ecx, eax
0x1800b1535  test    eax, eax
0x1800b1537  js      short loc_1800B15B6
0x1800b1539  cmp     [rbp+TokenInformation], 3
0x1800b153d  jz      short loc_1800B1571
0x1800b153f  cmp     [rbp+TokenInformation], 1
0x1800b1543  lea     rax, [rbp+arg_8]
0x1800b1547  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x1800b154c  mov     rcx, rbx; TokenHandle
0x1800b154f  jnz     short loc_1800B15C0
0x1800b1551  mov     r9d, 4; TokenInformationLength
0x1800b1557  lea     r8, [rbp+arg_18]; TokenInformation
0x1800b155b  lea     edx, [r9+10h]; TokenInformationClass
0x1800b155f  call    cs:__imp_NtQueryInformationToken
0x1800b1565  mov     ecx, eax
0x1800b1567  test    eax, eax
0x1800b1569  js      short loc_1800B15B6
0x1800b156b  cmp     [rbp+arg_18], 0
0x1800b156f  jnz     short loc_1800B15B6
0x1800b1571  mov     r9d, 4; TokenInformationLength
0x1800b1577  lea     rax, [rbp+arg_8]
0x1800b157b  lea     r8, [rbp+TokenType]; TokenInformation
0x1800b157f  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x1800b1584  mov     rcx, rbx; TokenHandle
0x1800b1587  lea     edx, [r9+4]; TokenInformationClass
0x1800b158b  call    cs:__imp_NtQueryInformationToken
0x1800b1591  mov     ecx, eax
0x1800b1593  test    eax, eax
0x1800b1595  js      short loc_1800B15B6
0x1800b1597  mov     eax, [rbp+TokenType]
0x1800b159a  xor     r9d, r9d; EffectiveOnly
0x1800b159d  mov     [rsp+40h+NewTokenHandle], rdi; NewTokenHandle
0x1800b15a2  xor     r8d, r8d; ObjectAttributes
0x1800b15a5  xor     edx, edx; DesiredAccess
0x1800b15a7  mov     dword ptr [rsp+40h+ReturnLength], eax; TokenType
0x1800b15ab  mov     rcx, rbx; ExistingTokenHandle
0x1800b15ae  call    cs:__imp_NtDuplicateToken
0x1800b15b4  mov     ecx, eax
0x1800b15b6  mov     eax, ecx
0x1800b15b8  add     rsp, 40h
0x1800b15bc  pop     rdi
0x1800b15bd  pop     rbx
0x1800b15be  pop     rbp
0x1800b15bf  retn
0x1800b15c0  mov     r9d, 8; TokenInformationLength
0x1800b15c6  lea     r8, [rbp+var_8]; TokenInformation
0x1800b15ca  lea     edx, [r9+0Bh]; TokenInformationClass
0x1800b15ce  call    cs:__imp_NtQueryInformationToken
0x1800b15d4  mov     ecx, eax
0x1800b15d6  test    eax, eax
0x1800b15d8  js      short loc_1800B15B6
0x1800b15da  mov     rax, [rbp+var_8]
0x1800b15de  mov     [rdi], rax
0x1800b15e1  jmp     short loc_1800B15B6
```
