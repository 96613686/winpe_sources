# LUAIsUserUACAdminEx

- ea: `0x180027544`
- end: `0x18002760c`
- name: `LUAIsUserUACAdminEx`
- size: `200`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180027434`

## callees

- `0x180027260`
- `0x180027344`
- `0x180027388`
- `0x180027544`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800275eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800275eb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800275cb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800275cb`

## pseudocode

```c
__int64 __fastcall LUAIsUserUACAdminEx(HANDLE TokenHandle, _DWORD *a2)
{
  NTSTATUS v5; // esi
  int v6; // eax
  void *v7; // rcx
  DWORD ReturnLength; // [rsp+48h] [rbp+10h] BYREF
  void *TokenInformation; // [rsp+50h] [rbp+18h] BYREF

  *a2 = 0;
  if ( !(unsigned int)Feature_ShadowAdmin__private_IsEnabledDeviceUsageNoInline() )
    return 3221225474LL;
  ReturnLength = 0;
  LODWORD(TokenInformation) = 0;
  v5 = LUAIsElevatedToken(TokenHandle, &ReturnLength, &TokenInformation);
  if ( v5 >= 0 )
  {
    if ( ReturnLength )
    {
      *a2 = _LUAIsTokenAdmin(TokenHandle);
    }
    else
    {
      TokenInformation = 0;
      ReturnLength = 8;
      if ( GetTokenInformation(TokenHandle, TokenLinkedToken, &TokenInformation, 8u, &ReturnLength) )
      {
        if ( TokenInformation )
        {
          v6 = _LUAIsTokenAdmin(TokenInformation);
          v7 = TokenInformation;
          *a2 = v6;
          CloseHandle(v7);
        }
      }
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180027544  mov     [rsp+arg_0], rbx
0x180027549  mov     [rsp+arg_18], rsi
0x18002754e  push    rdi
0x18002754f  sub     rsp, 30h
0x180027553  mov     rbx, rdx
0x180027556  mov     dword ptr [rdx], 0
0x18002755c  mov     rdi, rcx
0x18002755f  call    Feature_ShadowAdmin__private_IsEnabledDeviceUsageNoInline
0x180027564  test    eax, eax
0x180027566  jnz     short loc_180027572
0x180027568  mov     eax, 0C0000002h
0x18002756d  jmp     loc_1800275FC
0x180027572  lea     r8, [rsp+38h+TokenInformation]
0x180027577  mov     [rsp+38h+arg_8], 0
0x18002757f  lea     rdx, [rsp+38h+arg_8]
0x180027584  mov     dword ptr [rsp+38h+TokenInformation], 0
0x18002758c  mov     rcx, rdi; TokenHandle
0x18002758f  call    LUAIsElevatedToken
0x180027594  mov     esi, eax
0x180027596  test    eax, eax
0x180027598  js      short loc_1800275FA
0x18002759a  cmp     [rsp+38h+arg_8], 0
0x18002759f  mov     rcx, rdi; void *
0x1800275a2  jnz     short loc_1800275F3
0x1800275a4  mov     r9d, 8; TokenInformationLength
0x1800275aa  mov     [rsp+38h+TokenInformation], 0
0x1800275b3  lea     rax, [rsp+38h+arg_8]
0x1800275b8  mov     [rsp+38h+arg_8], r9d
0x1800275bd  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x1800275c2  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1800275c7  lea     edx, [r9+0Bh]; TokenInformationClass
0x1800275cb  call    cs:__imp_GetTokenInformation
0x1800275d1  test    eax, eax
0x1800275d3  jz      short loc_1800275FA
0x1800275d5  mov     rcx, [rsp+38h+TokenInformation]; void *
0x1800275da  test    rcx, rcx
0x1800275dd  jz      short loc_1800275FA
0x1800275df  call    ?_LUAIsTokenAdmin@@YAHPEAX@Z; _LUAIsTokenAdmin(void *)
0x1800275e4  mov     rcx, [rsp+38h+TokenInformation]; hObject
0x1800275e9  mov     [rbx], eax
0x1800275eb  call    cs:__imp_CloseHandle
0x1800275f1  jmp     short loc_1800275FA
0x1800275f3  call    ?_LUAIsTokenAdmin@@YAHPEAX@Z; _LUAIsTokenAdmin(void *)
0x1800275f8  mov     [rbx], eax
0x1800275fa  mov     eax, esi
0x1800275fc  mov     rbx, [rsp+38h+arg_0]
0x180027601  mov     rsi, [rsp+38h+arg_18]
0x180027606  add     rsp, 30h
0x18002760a  pop     rdi
0x18002760b  retn
```
