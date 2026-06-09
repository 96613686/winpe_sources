# CCacheServer::CheckAccess(void)

- ea: `0x18010f064`
- end: `0x18010f263`
- name: `?CheckAccess@CCacheServer@@AEAAJXZ`
- size: `511`
- prototype: `__int64 __fastcall(CCacheServer *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800438a0`

## callees

- `0x1800701d0`
- `0x18010f064`
- `0x18014a7a0`
- `0x18014b3b4`
- `0x1801e1790`
- `0x1801e3c24`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18010f0f6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18010f0f6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18010f10f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18010f10f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18010f196`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18010f196`
- `RPCRT4!RpcRevertToSelf` at `0x18010f11d`
- `RPCRT4!RpcRevertToSelf` at `0x18010f23a`
- `RPCRT4!RpcRevertToSelf` at `0x18010f11d`
- `RPCRT4!RpcRevertToSelf` at `0x18010f23a`
- `RPCRT4!RpcImpersonateClient` at `0x18010f0d8`
- `RPCRT4!RpcImpersonateClient` at `0x18010f0d8`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18010f171`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18010f171`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18010f154`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18010f154`

## pseudocode

```c
__int64 __fastcall CCacheServer::CheckAccess(PSID **this)
{
  RPC_STATUS v2; // eax
  signed int v3; // ebx
  HANDLE CurrentThread; // rax
  RPC_STATUS v5; // eax
  unsigned int v6; // edi
  int LastError; // eax
  int v9; // eax
  DWORD ReturnLength; // [rsp+38h] [rbp-90h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp-88h] BYREF
  PSID TokenInformation[12]; // [rsp+50h] [rbp-78h] BYREF

  TokenHandle = 0;
  memset_0(TokenInformation, 0, 0x58u);
  ReturnLength = 0;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_q(1036, 38, &WPP_0418b76b4b82361365e20b3333b0b600_Traceguids, this);
  v2 = RpcImpersonateClient(0);
  v3 = v2;
  if ( v2 > 0 )
    v3 = (unsigned __int16)v2 | 0x80070000;
  if ( v3 < 0 )
  {
LABEL_18:
    v6 = v3;
    goto LABEL_13;
  }
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0x20008u, 1, &TokenHandle) )
  {
    LastError = WxGetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    if ( v3 < 0 )
    {
      v6 = v3;
    }
    else
    {
      v6 = -2147418113;
      v3 = -2147418113;
    }
    goto LABEL_29;
  }
  v5 = RpcRevertToSelf();
  v3 = v5;
  if ( v5 > 0 )
    v3 = (unsigned __int16)v5 | 0x80070000;
  if ( v3 < 0 )
  {
    v6 = v3;
LABEL_29:
    RpcRevertToSelf();
    goto LABEL_13;
  }
  if ( GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0x58u, &ReturnLength) )
  {
    if ( EqualSid(TokenInformation[0], *this[18]) )
    {
      v3 = 0;
      v6 = 0;
      goto LABEL_13;
    }
    v3 = -2147024891;
    goto LABEL_18;
  }
  v9 = WxGetLastError();
  v3 = v9;
  if ( v9 > 0 )
    v3 = (unsigned __int16)v9 | 0x80070000;
  if ( v3 < 0 )
  {
    v6 = v3;
  }
  else
  {
    v6 = -2147418113;
    v3 = -2147418113;
  }
LABEL_13:
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 39, &WPP_0418b76b4b82361365e20b3333b0b600_Traceguids, (unsigned int)v3);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v6;
}

```

## disassembly

```asm
0x18010f064  mov     [rsp+arg_8], rbx
0x18010f069  mov     [rsp+arg_10], rbp
0x18010f06e  push    rdi
0x18010f06f  sub     rsp, 0C0h
0x18010f076  mov     rax, cs:__security_cookie
0x18010f07d  xor     rax, rsp
0x18010f080  mov     [rsp+0C8h+var_18], rax
0x18010f088  xor     edx, edx; Val
0x18010f08a  mov     [rsp+0C8h+var_94], 0
0x18010f092  mov     rdi, rcx
0x18010f095  mov     [rsp+0C8h+TokenHandle], 0
0x18010f09e  lea     rcx, [rsp+0C8h+TokenInformation]; void *
0x18010f0a3  lea     r8d, [rdx+58h]; Size
0x18010f0a7  call    memset_0
0x18010f0ac  mov     [rsp+0C8h+var_90], 0
0x18010f0b4  test    byte ptr cs:xmmword_180266B60+1, 10h
0x18010f0bb  jz      short loc_18010F0D6
0x18010f0bd  mov     edx, 26h ; '&'
0x18010f0c2  lea     r8, WPP_0418b76b4b82361365e20b3333b0b600_Traceguids
0x18010f0c9  mov     ecx, 40Ch
0x18010f0ce  mov     r9, rdi
0x18010f0d1  call    WPP_SF_q
0x18010f0d6  xor     ecx, ecx; BindingHandle
0x18010f0d8  call    cs:__imp_RpcImpersonateClient
0x18010f0de  mov     ebx, eax
0x18010f0e0  mov     ebp, 80070000h
0x18010f0e5  test    eax, eax
0x18010f0e7  jle     short loc_18010F0EE
0x18010f0e9  movzx   ebx, ax
0x18010f0ec  or      ebx, ebp
0x18010f0ee  test    ebx, ebx
0x18010f0f0  js      loc_18010F1DE
0x18010f0f6  call    cs:__imp_GetCurrentThread
0x18010f0fc  lea     r9, [rsp+0C8h+TokenHandle]; TokenHandle
0x18010f101  mov     edx, 20008h; DesiredAccess
0x18010f106  mov     rcx, rax; ThreadHandle
0x18010f109  mov     r8d, 1; OpenAsSelf
0x18010f10f  call    cs:__imp_OpenThreadToken
0x18010f115  test    eax, eax
0x18010f117  jz      loc_18010F1EA
0x18010f11d  call    cs:__imp_RpcRevertToSelf
0x18010f123  mov     ebx, eax
0x18010f125  test    eax, eax
0x18010f127  jle     short loc_18010F12E
0x18010f129  movzx   ebx, ax
0x18010f12c  or      ebx, ebp
0x18010f12e  test    ebx, ebx
0x18010f130  js      loc_18010F230
0x18010f136  mov     rcx, [rsp+0C8h+TokenHandle]; TokenHandle
0x18010f13b  lea     rax, [rsp+0C8h+var_90]
0x18010f140  mov     r9d, 58h ; 'X'; TokenInformationLength
0x18010f146  mov     [rsp+0C8h+ReturnLength], rax; ReturnLength
0x18010f14b  lea     r8, [rsp+0C8h+TokenInformation]; TokenInformation
0x18010f150  lea     edx, [r9-57h]; TokenInformationClass
0x18010f154  call    cs:__imp_GetTokenInformation
0x18010f15a  test    eax, eax
0x18010f15c  jz      loc_18010F207
0x18010f162  mov     rdx, [rdi+90h]
0x18010f169  mov     rcx, [rsp+0C8h+TokenInformation]; pSid1
0x18010f16e  mov     rdx, [rdx]; pSid2
0x18010f171  call    cs:__imp_EqualSid
0x18010f177  test    eax, eax
0x18010f179  jz      loc_18010F254
0x18010f17f  xor     ebx, ebx
0x18010f181  xor     edi, edi
0x18010f183  test    byte ptr cs:xmmword_180266B60+1, 10h
0x18010f18a  jnz     short loc_18010F1C3
0x18010f18c  mov     rcx, [rsp+0C8h+TokenHandle]; hObject
0x18010f191  test    rcx, rcx
0x18010f194  jz      short loc_18010F19C
0x18010f196  call    cs:__imp_CloseHandle
0x18010f19c  mov     eax, edi
0x18010f19e  mov     rcx, [rsp+0C8h+var_18]
0x18010f1a6  xor     rcx, rsp; StackCookie
0x18010f1a9  call    __security_check_cookie
0x18010f1ae  lea     r11, [rsp+0C8h+var_8]
0x18010f1b6  mov     rbx, [r11+18h]
0x18010f1ba  mov     rbp, [r11+20h]
0x18010f1be  mov     rsp, r11
0x18010f1c1  pop     rdi
0x18010f1c2  retn
0x18010f1c3  mov     edx, 27h ; '''
0x18010f1c8  lea     r8, WPP_0418b76b4b82361365e20b3333b0b600_Traceguids
0x18010f1cf  mov     ecx, 40Ch
0x18010f1d4  mov     r9d, ebx
0x18010f1d7  call    WPP_SF_d
0x18010f1dc  jmp     short loc_18010F18C
0x18010f1de  mov     [rsp+0C8h+var_94], 432h
0x18010f1e6  mov     edi, ebx
0x18010f1e8  jmp     short loc_18010F183
0x18010f1ea  call    WxGetLastError
0x18010f1ef  mov     ebx, eax
0x18010f1f1  test    eax, eax
0x18010f1f3  jle     short loc_18010F1FA
0x18010f1f5  movzx   ebx, ax
0x18010f1f8  or      ebx, ebp
0x18010f1fa  test    ebx, ebx
0x18010f1fc  js      short loc_18010F224
0x18010f1fe  mov     edi, 8000FFFFh
0x18010f203  mov     ebx, edi
0x18010f205  jmp     short loc_18010F226
0x18010f207  call    WxGetLastError
0x18010f20c  mov     ebx, eax
0x18010f20e  test    eax, eax
0x18010f210  jle     short loc_18010F217
0x18010f212  movzx   ebx, ax
0x18010f215  or      ebx, ebp
0x18010f217  test    ebx, ebx
0x18010f219  js      short loc_18010F245
0x18010f21b  mov     edi, 8000FFFFh
0x18010f220  mov     ebx, edi
0x18010f222  jmp     short loc_18010F247
0x18010f224  mov     edi, ebx
0x18010f226  mov     [rsp+0C8h+var_94], 435h
0x18010f22e  jmp     short loc_18010F23A
0x18010f230  mov     [rsp+0C8h+var_94], 43Ah
0x18010f238  mov     edi, ebx
0x18010f23a  call    cs:__imp_RpcRevertToSelf
0x18010f240  jmp     loc_18010F183
0x18010f245  mov     edi, ebx
0x18010f247  mov     [rsp+0C8h+var_94], 43Dh
0x18010f24f  jmp     loc_18010F183
0x18010f254  mov     ebx, 80070005h
0x18010f259  mov     [rsp+0C8h+var_94], 44Ah
0x18010f261  jmp     short loc_18010F1E6
```
