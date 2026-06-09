# LUAIsUserUACAdminEx

- ea: `0x18004e2d4`
- end: `0x18004e3a9`
- name: `LUAIsUserUACAdminEx`
- size: `213`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18004e190`

## callees

- `0x18004dfd8`
- `0x18004e094`
- `0x18004e0d4`
- `0x18004e2d4`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004e381`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004e381`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004e35b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004e35b`

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
0x18004e2d4  mov     [rsp+arg_0], rbx
0x18004e2d9  mov     [rsp+arg_18], rsi
0x18004e2de  push    rdi
0x18004e2df  sub     rsp, 30h
0x18004e2e3  mov     rbx, rdx
0x18004e2e6  mov     dword ptr [rdx], 0
0x18004e2ec  mov     rdi, rcx
0x18004e2ef  call    Feature_ShadowAdmin__private_IsEnabledDeviceUsageNoInline
0x18004e2f4  test    eax, eax
0x18004e2f6  jnz     short loc_18004E302
0x18004e2f8  mov     eax, 0C0000002h
0x18004e2fd  jmp     loc_18004E398
0x18004e302  lea     r8, [rsp+38h+TokenInformation]
0x18004e307  mov     [rsp+38h+arg_8], 0
0x18004e30f  lea     rdx, [rsp+38h+arg_8]
0x18004e314  mov     dword ptr [rsp+38h+TokenInformation], 0
0x18004e31c  mov     rcx, rdi; TokenHandle
0x18004e31f  call    LUAIsElevatedToken
0x18004e324  mov     esi, eax
0x18004e326  test    eax, eax
0x18004e328  js      short loc_18004E396
0x18004e32a  cmp     [rsp+38h+arg_8], 0
0x18004e32f  mov     rcx, rdi; void *
0x18004e332  jnz     short loc_18004E38F
0x18004e334  mov     r9d, 8; TokenInformationLength
0x18004e33a  mov     [rsp+38h+TokenInformation], 0
0x18004e343  lea     rax, [rsp+38h+arg_8]
0x18004e348  mov     [rsp+38h+arg_8], r9d
0x18004e34d  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x18004e352  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18004e357  lea     edx, [r9+0Bh]; TokenInformationClass
0x18004e35b  call    cs:__imp_GetTokenInformation
0x18004e362  nop     dword ptr [rax+rax+00h]
0x18004e367  test    eax, eax
0x18004e369  jz      short loc_18004E396
0x18004e36b  mov     rcx, [rsp+38h+TokenInformation]; void *
0x18004e370  test    rcx, rcx
0x18004e373  jz      short loc_18004E396
0x18004e375  call    ?_LUAIsTokenAdmin@@YAHPEAX@Z; _LUAIsTokenAdmin(void *)
0x18004e37a  mov     rcx, [rsp+38h+TokenInformation]; hObject
0x18004e37f  mov     [rbx], eax
0x18004e381  call    cs:__imp_CloseHandle
0x18004e388  nop     dword ptr [rax+rax+00h]
0x18004e38d  jmp     short loc_18004E396
0x18004e38f  call    ?_LUAIsTokenAdmin@@YAHPEAX@Z; _LUAIsTokenAdmin(void *)
0x18004e394  mov     [rbx], eax
0x18004e396  mov     eax, esi
0x18004e398  mov     rbx, [rsp+38h+arg_0]
0x18004e39d  mov     rsi, [rsp+38h+arg_18]
0x18004e3a2  add     rsp, 30h
0x18004e3a6  pop     rdi
0x18004e3a7  retn
```
