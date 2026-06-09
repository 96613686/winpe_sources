# RaCheckRpcAllowed

- ea: `0x18000cfe0`
- end: `0x18000d2c2`
- name: `RaCheckRpcAllowed`
- size: `738`
- prototype: `__int64 __fastcall(PSID *, char, _QWORD *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180008ff0`
- `0x18000cfe0`
- `0x18000d360`
- `0x18000d3d0`
- `0x18000d760`
- `0x18000d860`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d165`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d1d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d221`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d165`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d1d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d221`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d294`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d294`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000d15b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000d15b`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000d0b8`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000d0cd`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000d0e2`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000d0f7`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000d0b8`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000d0cd`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000d0e2`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000d0f7`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000d1c8`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000d217`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000d1c8`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000d217`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x18000d1ae`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x18000d1ae`

## pseudocode

```c
__int64 __fastcall RaCheckRpcAllowed(PSID *a1, char a2, _QWORD *a3)
{
  PSID *v4; // rsi
  DWORD TokenUserInfo; // ebx
  __int64 v8; // r8
  HANDLE v9; // rdi
  __int64 v10; // r8
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r8
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  int TokenInformation; // [rsp+30h] [rbp-20h] BYREF
  DWORD ReturnLength; // [rsp+34h] [rbp-1Ch] BYREF
  HANDLE TokenHandle; // [rsp+38h] [rbp-18h] BYREF
  PSID *v20; // [rsp+40h] [rbp-10h]
  WINBOOL IsMember; // [rsp+98h] [rbp+48h] BYREF

  TokenInformation = 0;
  v4 = 0;
  ReturnLength = 0;
  v20 = 0;
  IsMember = 0;
  TokenHandle = 0;
  TokenUserInfo = RaQueryRpcClientToken(&TokenHandle);
  if ( TokenUserInfo )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, v8, TokenUserInfo);
    v9 = TokenHandle;
    goto LABEL_44;
  }
  v9 = TokenHandle;
  TokenUserInfo = RaGetTokenUserInfo(TokenHandle);
  if ( TokenUserInfo )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, v10, TokenUserInfo);
    v4 = v20;
    goto LABEL_44;
  }
  v4 = v20;
  if ( !EqualSid(*v20, *a1) && !EqualSid(*v4, a1[1]) && !EqualSid(*v4, a1[2]) )
  {
    if ( EqualSid(*v4, a1[3]) )
    {
      TokenUserInfo = 740;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_44;
      v12 = 30;
      goto LABEL_18;
    }
    if ( !GetTokenInformation(v9, TokenSessionId, &TokenInformation, 4u, &ReturnLength) )
    {
      TokenUserInfo = GetLastError();
      if ( TokenUserInfo )
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
          goto LABEL_44;
        v15 = 31;
        goto LABEL_24;
      }
    }
    if ( (a2 & 1) != 0 || TokenInformation != WTSGetActiveConsoleSessionId() )
    {
      if ( !CheckTokenMembership(v9, a1[4], &IsMember) )
      {
        TokenUserInfo = GetLastError();
        if ( TokenUserInfo )
        {
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
            goto LABEL_44;
          v15 = 32;
          goto LABEL_24;
        }
      }
      if ( !IsMember )
      {
        if ( !CheckTokenMembership(v9, a1[5], &IsMember) )
        {
          TokenUserInfo = GetLastError();
          if ( TokenUserInfo )
          {
            v14 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
              goto LABEL_44;
            v15 = 33;
LABEL_24:
            WPP_SF_D(v14[2], v15, v13, TokenUserInfo);
            goto LABEL_44;
          }
        }
        if ( !IsMember )
        {
          TokenUserInfo = 740;
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
            goto LABEL_44;
          v12 = 34;
LABEL_18:
          WPP_SF_(v11[2], v12, WPP_72d4f3fa78ee36ae180552022609e6f2_Traceguids);
          goto LABEL_44;
        }
      }
    }
  }
  if ( a3 )
  {
    *a3 = v9;
    v9 = 0;
  }
LABEL_44:
  if ( v9 )
    CloseHandle(v9);
  if ( v4 )
    RaFreeTokenUserInfo(v4);
  return TokenUserInfo;
}

```

## disassembly

```asm
0x18000cfe0  mov     [rsp-28h+arg_0], rbx
0x18000cfe5  mov     [rsp-28h+arg_8], rsi
0x18000cfea  push    rbp
0x18000cfeb  push    rdi
0x18000cfec  push    r12
0x18000cfee  push    r14
0x18000cff0  push    r15
0x18000cff2  mov     rbp, rsp
0x18000cff5  sub     rsp, 50h
0x18000cff9  mov     r14, rcx
0x18000cffc  mov     [rbp+TokenInformation], 0
0x18000d003  xor     esi, esi
0x18000d005  mov     [rbp+var_1C], 0
0x18000d00c  lea     rcx, [rbp+TokenHandle]
0x18000d010  mov     [rbp+var_10], rsi
0x18000d014  mov     r15, r8
0x18000d017  mov     [rbp+IsMember], 0
0x18000d01e  mov     r12d, edx
0x18000d021  mov     [rbp+TokenHandle], 0
0x18000d029  call    RaQueryRpcClientToken
0x18000d02e  mov     ebx, eax
0x18000d030  test    eax, eax
0x18000d032  jz      short loc_18000D065
0x18000d034  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d03b  lea     rax, WPP_GLOBAL_Control
0x18000d042  cmp     rcx, rax
0x18000d045  jz      short loc_18000D05C
0x18000d047  test    byte ptr [rcx+1Ch], 4
0x18000d04b  jz      short loc_18000D05C
0x18000d04d  mov     rcx, [rcx+10h]
0x18000d051  lea     edx, [rsi+1Ch]
0x18000d054  mov     r9d, ebx
0x18000d057  call    WPP_SF_D
0x18000d05c  mov     rdi, [rbp+TokenHandle]
0x18000d060  jmp     loc_18000D28C
0x18000d065  mov     rdi, [rbp+TokenHandle]
0x18000d069  lea     rdx, [rbp+var_10]
0x18000d06d  mov     rcx, rdi; TokenHandle
0x18000d070  call    RaGetTokenUserInfo
0x18000d075  mov     ebx, eax
0x18000d077  test    eax, eax
0x18000d079  jz      short loc_18000D0AE
0x18000d07b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d082  lea     rax, WPP_GLOBAL_Control
0x18000d089  cmp     rcx, rax
0x18000d08c  jz      short loc_18000D0A5
0x18000d08e  test    byte ptr [rcx+1Ch], 4
0x18000d092  jz      short loc_18000D0A5
0x18000d094  mov     rcx, [rcx+10h]
0x18000d098  mov     edx, 1Dh
0x18000d09d  mov     r9d, ebx
0x18000d0a0  call    WPP_SF_D
0x18000d0a5  mov     rsi, [rbp+var_10]
0x18000d0a9  jmp     loc_18000D28C
0x18000d0ae  mov     rsi, [rbp+var_10]
0x18000d0b2  mov     rdx, [r14]; pSid2
0x18000d0b5  mov     rcx, [rsi]; pSid1
0x18000d0b8  call    cs:__imp_EqualSid
0x18000d0be  test    eax, eax
0x18000d0c0  jnz     loc_18000D282
0x18000d0c6  mov     rdx, [r14+8]; pSid2
0x18000d0ca  mov     rcx, [rsi]; pSid1
0x18000d0cd  call    cs:__imp_EqualSid
0x18000d0d3  test    eax, eax
0x18000d0d5  jnz     loc_18000D282
0x18000d0db  mov     rdx, [r14+10h]; pSid2
0x18000d0df  mov     rcx, [rsi]; pSid1
0x18000d0e2  call    cs:__imp_EqualSid
0x18000d0e8  test    eax, eax
0x18000d0ea  jnz     loc_18000D282
0x18000d0f0  mov     rdx, [r14+18h]; pSid2
0x18000d0f4  mov     rcx, [rsi]; pSid1
0x18000d0f7  call    cs:__imp_EqualSid
0x18000d0fd  test    eax, eax
0x18000d0ff  jz      short loc_18000D141
0x18000d101  mov     ebx, 2E4h
0x18000d106  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d10d  lea     rax, WPP_GLOBAL_Control
0x18000d114  cmp     rcx, rax
0x18000d117  jz      loc_18000D28C
0x18000d11d  test    byte ptr [rcx+1Ch], 4
0x18000d121  jz      loc_18000D28C
0x18000d127  mov     edx, 1Eh
0x18000d12c  mov     rcx, [rcx+10h]
0x18000d130  lea     r8, WPP_72d4f3fa78ee36ae180552022609e6f2_Traceguids
0x18000d137  call    WPP_SF_
0x18000d13c  jmp     loc_18000D28C
0x18000d141  mov     r9d, 4; TokenInformationLength
0x18000d147  lea     rax, [rbp+var_1C]
0x18000d14b  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18000d14f  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x18000d154  mov     rcx, rdi; TokenHandle
0x18000d157  lea     edx, [r9+8]; TokenInformationClass
0x18000d15b  call    cs:__imp_GetTokenInformation
0x18000d161  test    eax, eax
0x18000d163  jnz     short loc_18000D1A8
0x18000d165  call    cs:__imp_GetLastError
0x18000d16b  mov     ebx, eax
0x18000d16d  test    eax, eax
0x18000d16f  jz      short loc_18000D1A8
0x18000d171  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d178  lea     rax, WPP_GLOBAL_Control
0x18000d17f  cmp     rcx, rax
0x18000d182  jz      loc_18000D28C
0x18000d188  test    byte ptr [rcx+1Ch], 4
0x18000d18c  jz      loc_18000D28C
0x18000d192  mov     edx, 1Fh
0x18000d197  mov     rcx, [rcx+10h]
0x18000d19b  mov     r9d, ebx
0x18000d19e  call    WPP_SF_D
0x18000d1a3  jmp     loc_18000D28C
0x18000d1a8  test    r12b, 1
0x18000d1ac  jnz     short loc_18000D1BD
0x18000d1ae  call    cs:__imp_WTSGetActiveConsoleSessionId
0x18000d1b4  cmp     [rbp+TokenInformation], eax
0x18000d1b7  jz      loc_18000D27E
0x18000d1bd  mov     rdx, [r14+20h]; SidToCheck
0x18000d1c1  lea     r8, [rbp+IsMember]; IsMember
0x18000d1c5  mov     rcx, rdi; TokenHandle
0x18000d1c8  call    cs:__imp_CheckTokenMembership
0x18000d1ce  test    eax, eax
0x18000d1d0  jnz     short loc_18000D206
0x18000d1d2  call    cs:__imp_GetLastError
0x18000d1d8  mov     ebx, eax
0x18000d1da  test    eax, eax
0x18000d1dc  jz      short loc_18000D206
0x18000d1de  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d1e5  lea     rax, WPP_GLOBAL_Control
0x18000d1ec  cmp     rcx, rax
0x18000d1ef  jz      loc_18000D28C
0x18000d1f5  test    byte ptr [rcx+1Ch], 4
0x18000d1f9  jz      loc_18000D28C
0x18000d1ff  mov     edx, 20h ; ' '
0x18000d204  jmp     short loc_18000D197
0x18000d206  cmp     [rbp+IsMember], 0
0x18000d20a  jnz     short loc_18000D27E
0x18000d20c  mov     rdx, [r14+28h]; SidToCheck
0x18000d210  lea     r8, [rbp+IsMember]; IsMember
0x18000d214  mov     rcx, rdi; TokenHandle
0x18000d217  call    cs:__imp_CheckTokenMembership
0x18000d21d  test    eax, eax
0x18000d21f  jnz     short loc_18000D250
0x18000d221  call    cs:__imp_GetLastError
0x18000d227  mov     ebx, eax
0x18000d229  test    eax, eax
0x18000d22b  jz      short loc_18000D250
0x18000d22d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d234  lea     rax, WPP_GLOBAL_Control
0x18000d23b  cmp     rcx, rax
0x18000d23e  jz      short loc_18000D28C
0x18000d240  test    byte ptr [rcx+1Ch], 4
0x18000d244  jz      short loc_18000D28C
0x18000d246  mov     edx, 21h ; '!'
0x18000d24b  jmp     loc_18000D197
0x18000d250  cmp     [rbp+IsMember], 0
0x18000d254  jnz     short loc_18000D27E
0x18000d256  mov     ebx, 2E4h
0x18000d25b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d262  lea     rax, WPP_GLOBAL_Control
0x18000d269  cmp     rcx, rax
0x18000d26c  jz      short loc_18000D28C
0x18000d26e  test    byte ptr [rcx+1Ch], 4
0x18000d272  jz      short loc_18000D28C
0x18000d274  mov     edx, 22h ; '"'
0x18000d279  jmp     loc_18000D12C
0x18000d27e  test    ebx, ebx
0x18000d280  jnz     short loc_18000D28C
0x18000d282  test    r15, r15
0x18000d285  jz      short loc_18000D28C
0x18000d287  mov     [r15], rdi
0x18000d28a  xor     edi, edi
0x18000d28c  test    rdi, rdi
0x18000d28f  jz      short loc_18000D29A
0x18000d291  mov     rcx, rdi; hObject
0x18000d294  call    cs:__imp_CloseHandle
0x18000d29a  test    rsi, rsi
0x18000d29d  jz      short loc_18000D2A7
0x18000d29f  mov     rcx, rsi
0x18000d2a2  call    RaFreeTokenUserInfo
0x18000d2a7  lea     r11, [rsp+50h+var_s0]
0x18000d2ac  mov     eax, ebx
0x18000d2ae  mov     rbx, [r11+30h]
0x18000d2b2  mov     rsi, [r11+38h]
0x18000d2b6  mov     rsp, r11
0x18000d2b9  pop     r15
0x18000d2bb  pop     r14
0x18000d2bd  pop     r12
0x18000d2bf  pop     rdi
0x18000d2c0  pop     rbp
0x18000d2c1  retn
```
