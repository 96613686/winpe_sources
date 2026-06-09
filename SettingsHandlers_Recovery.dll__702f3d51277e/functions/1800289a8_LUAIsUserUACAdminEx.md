# LUAIsUserUACAdminEx

- ea: `0x1800289a8`
- end: `0x180028a70`
- name: `LUAIsUserUACAdminEx`
- size: `200`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180028898`

## callees

- `0x18002870c`
- `0x1800287b0`
- `0x1800287ec`
- `0x1800289a8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028a4f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028a4f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180028a2f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180028a2f`

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
0x1800289a8  mov     [rsp+arg_0], rbx
0x1800289ad  mov     [rsp+arg_18], rsi
0x1800289b2  push    rdi
0x1800289b3  sub     rsp, 30h
0x1800289b7  mov     rbx, rdx
0x1800289ba  mov     dword ptr [rdx], 0
0x1800289c0  mov     rdi, rcx
0x1800289c3  call    Feature_ShadowAdmin__private_IsEnabledDeviceUsageNoInline
0x1800289c8  test    eax, eax
0x1800289ca  jnz     short loc_1800289D6
0x1800289cc  mov     eax, 0C0000002h
0x1800289d1  jmp     loc_180028A60
0x1800289d6  lea     r8, [rsp+38h+TokenInformation]
0x1800289db  mov     [rsp+38h+arg_8], 0
0x1800289e3  lea     rdx, [rsp+38h+arg_8]
0x1800289e8  mov     dword ptr [rsp+38h+TokenInformation], 0
0x1800289f0  mov     rcx, rdi; TokenHandle
0x1800289f3  call    LUAIsElevatedToken
0x1800289f8  mov     esi, eax
0x1800289fa  test    eax, eax
0x1800289fc  js      short loc_180028A5E
0x1800289fe  cmp     [rsp+38h+arg_8], 0
0x180028a03  mov     rcx, rdi; void *
0x180028a06  jnz     short loc_180028A57
0x180028a08  mov     r9d, 8; TokenInformationLength
0x180028a0e  mov     [rsp+38h+TokenInformation], 0
0x180028a17  lea     rax, [rsp+38h+arg_8]
0x180028a1c  mov     [rsp+38h+arg_8], r9d
0x180028a21  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x180028a26  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180028a2b  lea     edx, [r9+0Bh]; TokenInformationClass
0x180028a2f  call    cs:__imp_GetTokenInformation
0x180028a35  test    eax, eax
0x180028a37  jz      short loc_180028A5E
0x180028a39  mov     rcx, [rsp+38h+TokenInformation]; void *
0x180028a3e  test    rcx, rcx
0x180028a41  jz      short loc_180028A5E
0x180028a43  call    ?_LUAIsTokenAdmin@@YAHPEAX@Z; _LUAIsTokenAdmin(void *)
0x180028a48  mov     rcx, [rsp+38h+TokenInformation]; hObject
0x180028a4d  mov     [rbx], eax
0x180028a4f  call    cs:__imp_CloseHandle
0x180028a55  jmp     short loc_180028A5E
0x180028a57  call    ?_LUAIsTokenAdmin@@YAHPEAX@Z; _LUAIsTokenAdmin(void *)
0x180028a5c  mov     [rbx], eax
0x180028a5e  mov     eax, esi
0x180028a60  mov     rbx, [rsp+38h+arg_0]
0x180028a65  mov     rsi, [rsp+38h+arg_18]
0x180028a6a  add     rsp, 30h
0x180028a6e  pop     rdi
0x180028a6f  retn
```
