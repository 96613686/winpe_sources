# LUAIsUserUACAdminEx

- ea: `0x18007a868`
- end: `0x18007a930`
- name: `LUAIsUserUACAdminEx`
- size: `200`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18007a758`

## callees

- `0x18007a5cc`
- `0x18007a670`
- `0x18007a6ac`
- `0x18007a868`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007a90f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007a90f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007a8ef`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007a8ef`

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
0x18007a868  mov     [rsp+arg_0], rbx
0x18007a86d  mov     [rsp+arg_18], rsi
0x18007a872  push    rdi
0x18007a873  sub     rsp, 30h
0x18007a877  mov     rbx, rdx
0x18007a87a  mov     dword ptr [rdx], 0
0x18007a880  mov     rdi, rcx
0x18007a883  call    Feature_ShadowAdmin__private_IsEnabledDeviceUsageNoInline
0x18007a888  test    eax, eax
0x18007a88a  jnz     short loc_18007A896
0x18007a88c  mov     eax, 0C0000002h
0x18007a891  jmp     loc_18007A920
0x18007a896  lea     r8, [rsp+38h+TokenInformation]
0x18007a89b  mov     [rsp+38h+arg_8], 0
0x18007a8a3  lea     rdx, [rsp+38h+arg_8]
0x18007a8a8  mov     dword ptr [rsp+38h+TokenInformation], 0
0x18007a8b0  mov     rcx, rdi; TokenHandle
0x18007a8b3  call    LUAIsElevatedToken
0x18007a8b8  mov     esi, eax
0x18007a8ba  test    eax, eax
0x18007a8bc  js      short loc_18007A91E
0x18007a8be  cmp     [rsp+38h+arg_8], 0
0x18007a8c3  mov     rcx, rdi; void *
0x18007a8c6  jnz     short loc_18007A917
0x18007a8c8  mov     r9d, 8; TokenInformationLength
0x18007a8ce  mov     [rsp+38h+TokenInformation], 0
0x18007a8d7  lea     rax, [rsp+38h+arg_8]
0x18007a8dc  mov     [rsp+38h+arg_8], r9d
0x18007a8e1  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x18007a8e6  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18007a8eb  lea     edx, [r9+0Bh]; TokenInformationClass
0x18007a8ef  call    cs:__imp_GetTokenInformation
0x18007a8f5  test    eax, eax
0x18007a8f7  jz      short loc_18007A91E
0x18007a8f9  mov     rcx, [rsp+38h+TokenInformation]; void *
0x18007a8fe  test    rcx, rcx
0x18007a901  jz      short loc_18007A91E
0x18007a903  call    ?_LUAIsTokenAdmin@@YAHPEAX@Z; _LUAIsTokenAdmin(void *)
0x18007a908  mov     rcx, [rsp+38h+TokenInformation]; hObject
0x18007a90d  mov     [rbx], eax
0x18007a90f  call    cs:__imp_CloseHandle
0x18007a915  jmp     short loc_18007A91E
0x18007a917  call    ?_LUAIsTokenAdmin@@YAHPEAX@Z; _LUAIsTokenAdmin(void *)
0x18007a91c  mov     [rbx], eax
0x18007a91e  mov     eax, esi
0x18007a920  mov     rbx, [rsp+38h+arg_0]
0x18007a925  mov     rsi, [rsp+38h+arg_18]
0x18007a92a  add     rsp, 30h
0x18007a92e  pop     rdi
0x18007a92f  retn
```
