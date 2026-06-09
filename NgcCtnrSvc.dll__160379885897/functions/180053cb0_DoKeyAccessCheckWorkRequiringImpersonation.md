# DoKeyAccessCheckWorkRequiringImpersonation

- ea: `0x180053cb0`
- end: `0x180053dd7`
- name: `DoKeyAccessCheckWorkRequiringImpersonation`
- size: `295`
- prototype: `__int64 __fastcall(void *, unsigned int, int, HANDLE *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180053ae4`

## callees

- `0x18002dd34`
- `0x180053cb0`
- `0x18005f2fc`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180053d70`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180053d70`
- `RPCRT4!RpcImpersonateClient` at `0x180053cd8`
- `RPCRT4!RpcImpersonateClient` at `0x180053cd8`
- `RPCRT4!RpcRevertToSelf` at `0x180053d5c`
- `RPCRT4!RpcRevertToSelf` at `0x180053d96`
- `RPCRT4!RpcRevertToSelf` at `0x180053d5c`
- `RPCRT4!RpcRevertToSelf` at `0x180053d96`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180053d3f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180053d3f`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x180053db6`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x180053db6`

## pseudocode

```c
__int64 __fastcall DoKeyAccessCheckWorkRequiringImpersonation(void *a1, unsigned int a2, int a3, HANDLE *a4)
{
  unsigned int v5; // eax
  __int64 v6; // rdx
  __int64 v7; // rcx
  unsigned int v8; // esi
  int CallerToken; // ebx
  BOOL v10; // edi
  HANDLE v11; // rsi
  DWORD ReturnLength; // [rsp+30h] [rbp-10h] BYREF
  HANDLE hObject; // [rsp+38h] [rbp-8h] BYREF
  unsigned int TokenInformation; // [rsp+68h] [rbp+28h] BYREF
  int v16; // [rsp+70h] [rbp+30h] BYREF

  v16 = a3;
  TokenInformation = a2;
  hObject = 0;
  v5 = RpcImpersonateClient(a1);
  v8 = v5;
  if ( v5 && v5 != 1725 )
    return v5;
  v10 = v5 == 0;
  CallerToken = GetCallerToken(v7, v6, &hObject);
  if ( CallerToken >= 0 )
  {
    LOBYTE(v16) = 0;
    TokenInformation = 0;
    ReturnLength = 0;
    if ( GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFALL, TokenSessionId, &TokenInformation, 4u, &ReturnLength) )
    {
      if ( !v8 )
      {
        RpcRevertToSelf();
        v10 = 0;
      }
      if ( !(unsigned __int8)IsWinStationIsSessionRemoteablePresent()
        || !(unsigned __int8)WinStationIsSessionRemoteable(0, TokenInformation, &v16)
        || !(_BYTE)v16 )
      {
        v11 = 0;
        *a4 = hObject;
        goto LABEL_8;
      }
    }
    CallerToken = -2146893808;
  }
  v11 = hObject;
LABEL_8:
  if ( v10 )
    RpcRevertToSelf();
  if ( v11 )
    CloseHandle(v11);
  return (unsigned int)CallerToken;
}

```

## disassembly

```asm
0x180053cb0  mov     rax, rsp
0x180053cb3  mov     [rax+8], rbx
0x180053cb7  mov     [rax+20h], rsi
0x180053cbb  mov     [rax+18h], r8d
0x180053cbf  mov     [rax+10h], edx
0x180053cc2  push    rbp
0x180053cc3  push    rdi
0x180053cc4  push    r14
0x180053cc6  mov     rbp, rsp
0x180053cc9  sub     rsp, 40h
0x180053ccd  mov     r14, r9
0x180053cd0  mov     [rbp+hObject], 0
0x180053cd8  call    cs:__imp_RpcImpersonateClient
0x180053cdf  nop     dword ptr [rax+rax+00h]
0x180053ce4  mov     esi, eax
0x180053ce6  test    eax, eax
0x180053ce8  jz      short loc_180053CF8
0x180053cea  cmp     eax, 6BDh
0x180053cef  jz      short loc_180053CF8
0x180053cf1  mov     ebx, eax
0x180053cf3  jmp     loc_180053D7C
0x180053cf8  xor     edi, edi
0x180053cfa  lea     r8, [rbp+hObject]
0x180053cfe  test    esi, esi
0x180053d00  setz    dil
0x180053d04  call    GetCallerToken
0x180053d09  mov     ebx, eax
0x180053d0b  test    eax, eax
0x180053d0d  js      short loc_180053D54
0x180053d0f  mov     r9d, 4; TokenInformationLength
0x180053d15  mov     byte ptr [rbp+arg_10], 0
0x180053d19  lea     rax, [rbp+var_10]
0x180053d1d  mov     [rbp+TokenInformation], 0
0x180053d24  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180053d28  mov     [rbp+var_10], 0
0x180053d2f  mov     rcx, 0FFFFFFFFFFFFFFFAh; TokenHandle
0x180053d36  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x180053d3b  lea     edx, [r9+8]; TokenInformationClass
0x180053d3f  call    cs:__imp_GetTokenInformation
0x180053d46  nop     dword ptr [rax+rax+00h]
0x180053d4b  test    eax, eax
0x180053d4d  jnz     short loc_180053D92
0x180053d4f  mov     ebx, 80090010h
0x180053d54  mov     rsi, [rbp+hObject]
0x180053d58  test    edi, edi
0x180053d5a  jz      short loc_180053D68
0x180053d5c  call    cs:__imp_RpcRevertToSelf
0x180053d63  nop     dword ptr [rax+rax+00h]
0x180053d68  test    rsi, rsi
0x180053d6b  jz      short loc_180053D7C
0x180053d6d  mov     rcx, rsi; hObject
0x180053d70  call    cs:__imp_CloseHandle
0x180053d77  nop     dword ptr [rax+rax+00h]
0x180053d7c  mov     rsi, [rsp+40h+arg_18]
0x180053d81  mov     eax, ebx
0x180053d83  mov     rbx, [rsp+40h+arg_0]
0x180053d88  add     rsp, 40h
0x180053d8c  pop     r14
0x180053d8e  pop     rdi
0x180053d8f  pop     rbp
0x180053d90  retn
0x180053d92  test    esi, esi
0x180053d94  jnz     short loc_180053DA4
0x180053d96  call    cs:__imp_RpcRevertToSelf
0x180053d9d  nop     dword ptr [rax+rax+00h]
0x180053da2  xor     edi, edi
0x180053da4  call    IsWinStationIsSessionRemoteablePresent
0x180053da9  test    al, al
0x180053dab  jz      short loc_180053DCC
0x180053dad  mov     edx, [rbp+TokenInformation]
0x180053db0  lea     r8, [rbp+arg_10]
0x180053db4  xor     ecx, ecx
0x180053db6  call    cs:__imp_WinStationIsSessionRemoteable
0x180053dbd  nop     dword ptr [rax+rax+00h]
0x180053dc2  test    al, al
0x180053dc4  jz      short loc_180053DCC
0x180053dc6  cmp     byte ptr [rbp+arg_10], 0
0x180053dca  jnz     short loc_180053D4F
0x180053dcc  mov     rax, [rbp+hObject]
0x180053dd0  xor     esi, esi
0x180053dd2  mov     [r14], rax
0x180053dd5  jmp     short loc_180053D58
```
