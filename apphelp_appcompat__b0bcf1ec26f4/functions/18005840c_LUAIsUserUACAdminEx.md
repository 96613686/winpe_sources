# LUAIsUserUACAdminEx

- ea: `0x18005840c`
- end: `0x1800584d4`
- name: `LUAIsUserUACAdminEx`
- size: `200`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800582fc`

## callees

- `0x180058168`
- `0x18005820c`
- `0x180058250`
- `0x18005840c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800584b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800584b3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180058493`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180058493`

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
0x18005840c  mov     [rsp+arg_0], rbx
0x180058411  mov     [rsp+arg_18], rsi
0x180058416  push    rdi
0x180058417  sub     rsp, 30h
0x18005841b  mov     rbx, rdx
0x18005841e  mov     dword ptr [rdx], 0
0x180058424  mov     rdi, rcx
0x180058427  call    Feature_ShadowAdmin__private_IsEnabledDeviceUsageNoInline
0x18005842c  test    eax, eax
0x18005842e  jnz     short loc_18005843A
0x180058430  mov     eax, 0C0000002h
0x180058435  jmp     loc_1800584C4
0x18005843a  lea     r8, [rsp+38h+TokenInformation]
0x18005843f  mov     [rsp+38h+arg_8], 0
0x180058447  lea     rdx, [rsp+38h+arg_8]
0x18005844c  mov     dword ptr [rsp+38h+TokenInformation], 0
0x180058454  mov     rcx, rdi; TokenHandle
0x180058457  call    LUAIsElevatedToken
0x18005845c  mov     esi, eax
0x18005845e  test    eax, eax
0x180058460  js      short loc_1800584C2
0x180058462  cmp     [rsp+38h+arg_8], 0
0x180058467  mov     rcx, rdi; void *
0x18005846a  jnz     short loc_1800584BB
0x18005846c  mov     r9d, 8; TokenInformationLength
0x180058472  mov     [rsp+38h+TokenInformation], 0
0x18005847b  lea     rax, [rsp+38h+arg_8]
0x180058480  mov     [rsp+38h+arg_8], r9d
0x180058485  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x18005848a  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18005848f  lea     edx, [r9+0Bh]; TokenInformationClass
0x180058493  call    cs:__imp_GetTokenInformation
0x180058499  test    eax, eax
0x18005849b  jz      short loc_1800584C2
0x18005849d  mov     rcx, [rsp+38h+TokenInformation]; void *
0x1800584a2  test    rcx, rcx
0x1800584a5  jz      short loc_1800584C2
0x1800584a7  call    ?_LUAIsTokenAdmin@@YAHPEAX@Z; _LUAIsTokenAdmin(void *)
0x1800584ac  mov     rcx, [rsp+38h+TokenInformation]; hObject
0x1800584b1  mov     [rbx], eax
0x1800584b3  call    cs:__imp_CloseHandle
0x1800584b9  jmp     short loc_1800584C2
0x1800584bb  call    ?_LUAIsTokenAdmin@@YAHPEAX@Z; _LUAIsTokenAdmin(void *)
0x1800584c0  mov     [rbx], eax
0x1800584c2  mov     eax, esi
0x1800584c4  mov     rbx, [rsp+38h+arg_0]
0x1800584c9  mov     rsi, [rsp+38h+arg_18]
0x1800584ce  add     rsp, 30h
0x1800584d2  pop     rdi
0x1800584d3  retn
```
