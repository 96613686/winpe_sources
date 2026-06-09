# RaGetTokenUserInfo

- ea: `0x18000d3d0`
- end: `0x18000d57f`
- name: `RaGetTokenUserInfo`
- size: `431`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000cfe0`

## callees

- `0x180004390`
- `0x180004b80`
- `0x180008ff0`
- `0x18000d3d0`
- `0x18000d860`
- `0x18000d8a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d456`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d51e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d456`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d51e`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000d410`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000d410`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000d406`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000d514`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000d406`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000d514`

## string_xrefs

- `0x18000d4a2`: `RaGetTokenUserInfo`
- `0x18000d55f`: `RaGetTokenUserInfo`

## pseudocode

```c
__int64 __fastcall RaGetTokenUserInfo(HANDLE TokenHandle, _QWORD *a2)
{
  unsigned int v4; // ebx
  DWORD LastError; // eax
  __int64 v6; // r8
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r8
  LPVOID v10; // rdi
  DWORD TokenInformationLength; // [rsp+60h] [rbp+18h] BYREF
  LPVOID TokenInformation; // [rsp+68h] [rbp+20h] BYREF

  TokenInformation = 0;
  TokenInformationLength = 0;
  if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
  {
    DebugBreak();
    v4 = 1003;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_72d4f3fa78ee36ae180552022609e6f2_Traceguids);
    goto LABEL_21;
  }
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError != 122 && LastError )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_21;
    v8 = 24;
LABEL_10:
    WPP_SF_D(v7[2], v8, v6, v4);
    goto LABEL_21;
  }
  v4 = AllocateMemory(TokenInformationLength, &TokenInformation, (int)"RaGetTokenUserInfo", 182);
  if ( v4 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, v9, TokenInformationLength, v4);
  }
  else
  {
    v10 = TokenInformation;
    if ( GetTokenInformation(TokenHandle, TokenUser, TokenInformation, TokenInformationLength, &TokenInformationLength)
      || (v4 = GetLastError()) == 0 )
    {
      *a2 = v10;
      TokenInformation = 0;
      goto LABEL_21;
    }
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v8 = 26;
      goto LABEL_10;
    }
  }
LABEL_21:
  FreeMemory(&TokenInformation, (int)"RaGetTokenUserInfo", 198);
  return v4;
}

```

## disassembly

```asm
0x18000d3d0  mov     rax, rsp
0x18000d3d3  mov     [rax+8], rbx
0x18000d3d7  push    rbp
0x18000d3d8  push    rsi
0x18000d3d9  push    rdi
0x18000d3da  sub     rsp, 30h
0x18000d3de  xor     r9d, r9d; TokenInformationLength
0x18000d3e1  mov     qword ptr [rax+20h], 0
0x18000d3e9  mov     dword ptr [rax+18h], 0
0x18000d3f0  lea     rax, [rax+18h]
0x18000d3f4  mov     rsi, rdx
0x18000d3f7  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18000d3fc  xor     r8d, r8d; TokenInformation
0x18000d3ff  mov     rbp, rcx
0x18000d402  lea     edx, [r9+1]; TokenInformationClass
0x18000d406  call    cs:__imp_GetTokenInformation
0x18000d40c  test    eax, eax
0x18000d40e  jz      short loc_18000D456
0x18000d410  call    cs:__imp_DebugBreak
0x18000d416  mov     ebx, 3EBh
0x18000d41b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d422  lea     rax, WPP_GLOBAL_Control
0x18000d429  cmp     rcx, rax
0x18000d42c  jz      loc_18000D559
0x18000d432  test    byte ptr [rcx+1Ch], 4
0x18000d436  jz      loc_18000D559
0x18000d43c  mov     rcx, [rcx+10h]
0x18000d440  lea     r8, WPP_72d4f3fa78ee36ae180552022609e6f2_Traceguids
0x18000d447  mov     edx, 17h
0x18000d44c  call    WPP_SF_
0x18000d451  jmp     loc_18000D559
0x18000d456  call    cs:__imp_GetLastError
0x18000d45c  mov     ebx, eax
0x18000d45e  cmp     eax, 7Ah ; 'z'
0x18000d461  jz      short loc_18000D49E
0x18000d463  test    eax, eax
0x18000d465  jz      short loc_18000D49E
0x18000d467  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d46e  lea     rax, WPP_GLOBAL_Control
0x18000d475  cmp     rcx, rax
0x18000d478  jz      loc_18000D559
0x18000d47e  test    byte ptr [rcx+1Ch], 4
0x18000d482  jz      loc_18000D559
0x18000d488  mov     edx, 18h
0x18000d48d  mov     rcx, [rcx+10h]
0x18000d491  mov     r9d, ebx
0x18000d494  call    WPP_SF_D
0x18000d499  jmp     loc_18000D559
0x18000d49e  mov     ecx, [rsp+48h+TokenInformationLength]; dwBytes
0x18000d4a2  lea     r8, aRagettokenuser_0; "RaGetTokenUserInfo"
0x18000d4a9  mov     r9d, 0B6h
0x18000d4af  lea     rdx, [rsp+48h+TokenInformation]
0x18000d4b4  call    AllocateMemory
0x18000d4b9  mov     ebx, eax
0x18000d4bb  test    eax, eax
0x18000d4bd  jz      short loc_18000D4F5
0x18000d4bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d4c6  lea     rax, WPP_GLOBAL_Control
0x18000d4cd  cmp     rcx, rax
0x18000d4d0  jz      loc_18000D559
0x18000d4d6  test    byte ptr [rcx+1Ch], 4
0x18000d4da  jz      short loc_18000D559
0x18000d4dc  mov     r9d, [rsp+48h+TokenInformationLength]
0x18000d4e1  mov     edx, 19h
0x18000d4e6  mov     rcx, [rcx+10h]
0x18000d4ea  mov     dword ptr [rsp+48h+ReturnLength], ebx
0x18000d4ee  call    WPP_SF_DD
0x18000d4f3  jmp     short loc_18000D559
0x18000d4f5  mov     rdi, [rsp+48h+TokenInformation]
0x18000d4fa  lea     rax, [rsp+48h+TokenInformationLength]
0x18000d4ff  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x18000d504  mov     r8, rdi; TokenInformation
0x18000d507  mov     edx, 1; TokenInformationClass
0x18000d50c  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18000d511  mov     rcx, rbp; TokenHandle
0x18000d514  call    cs:__imp_GetTokenInformation
0x18000d51a  test    eax, eax
0x18000d51c  jnz     short loc_18000D54D
0x18000d51e  call    cs:__imp_GetLastError
0x18000d524  mov     ebx, eax
0x18000d526  test    eax, eax
0x18000d528  jz      short loc_18000D54D
0x18000d52a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d531  lea     rax, WPP_GLOBAL_Control
0x18000d538  cmp     rcx, rax
0x18000d53b  jz      short loc_18000D559
0x18000d53d  test    byte ptr [rcx+1Ch], 4
0x18000d541  jz      short loc_18000D559
0x18000d543  mov     edx, 1Ah
0x18000d548  jmp     loc_18000D48D
0x18000d54d  mov     [rsi], rdi
0x18000d550  mov     [rsp+48h+TokenInformation], 0
0x18000d559  mov     r8d, 0C6h
0x18000d55f  lea     rdx, aRagettokenuser_0; "RaGetTokenUserInfo"
0x18000d566  lea     rcx, [rsp+48h+TokenInformation]
0x18000d56b  call    FreeMemory
0x18000d570  mov     eax, ebx
0x18000d572  mov     rbx, [rsp+48h+arg_0]
0x18000d577  add     rsp, 30h
0x18000d57b  pop     rdi
0x18000d57c  pop     rsi
0x18000d57d  pop     rbp
0x18000d57e  retn
```
