# LUAIsUserUACAdminEx

- ea: `0x18005834c`
- end: `0x180058414`
- name: `LUAIsUserUACAdminEx`
- size: `200`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18005823c`

## callees

- `0x1800580a8`
- `0x18005814c`
- `0x180058190`
- `0x18005834c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800583f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800583f3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800583d3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800583d3`

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
0x18005834c  mov     [rsp+arg_0], rbx
0x180058351  mov     [rsp+arg_18], rsi
0x180058356  push    rdi
0x180058357  sub     rsp, 30h
0x18005835b  mov     rbx, rdx
0x18005835e  mov     dword ptr [rdx], 0
0x180058364  mov     rdi, rcx
0x180058367  call    Feature_ShadowAdmin__private_IsEnabledDeviceUsageNoInline
0x18005836c  test    eax, eax
0x18005836e  jnz     short loc_18005837A
0x180058370  mov     eax, 0C0000002h
0x180058375  jmp     loc_180058404
0x18005837a  lea     r8, [rsp+38h+TokenInformation]
0x18005837f  mov     [rsp+38h+arg_8], 0
0x180058387  lea     rdx, [rsp+38h+arg_8]
0x18005838c  mov     dword ptr [rsp+38h+TokenInformation], 0
0x180058394  mov     rcx, rdi; TokenHandle
0x180058397  call    LUAIsElevatedToken
0x18005839c  mov     esi, eax
0x18005839e  test    eax, eax
0x1800583a0  js      short loc_180058402
0x1800583a2  cmp     [rsp+38h+arg_8], 0
0x1800583a7  mov     rcx, rdi; void *
0x1800583aa  jnz     short loc_1800583FB
0x1800583ac  mov     r9d, 8; TokenInformationLength
0x1800583b2  mov     [rsp+38h+TokenInformation], 0
0x1800583bb  lea     rax, [rsp+38h+arg_8]
0x1800583c0  mov     [rsp+38h+arg_8], r9d
0x1800583c5  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x1800583ca  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1800583cf  lea     edx, [r9+0Bh]; TokenInformationClass
0x1800583d3  call    cs:__imp_GetTokenInformation
0x1800583d9  test    eax, eax
0x1800583db  jz      short loc_180058402
0x1800583dd  mov     rcx, [rsp+38h+TokenInformation]; void *
0x1800583e2  test    rcx, rcx
0x1800583e5  jz      short loc_180058402
0x1800583e7  call    ?_LUAIsTokenAdmin@@YAHPEAX@Z; _LUAIsTokenAdmin(void *)
0x1800583ec  mov     rcx, [rsp+38h+TokenInformation]; hObject
0x1800583f1  mov     [rbx], eax
0x1800583f3  call    cs:__imp_CloseHandle
0x1800583f9  jmp     short loc_180058402
0x1800583fb  call    ?_LUAIsTokenAdmin@@YAHPEAX@Z; _LUAIsTokenAdmin(void *)
0x180058400  mov     [rbx], eax
0x180058402  mov     eax, esi
0x180058404  mov     rbx, [rsp+38h+arg_0]
0x180058409  mov     rsi, [rsp+38h+arg_18]
0x18005840e  add     rsp, 30h
0x180058412  pop     rdi
0x180058413  retn
```
