# GetUserSidFromToken

- ea: `0x18000a06c`
- end: `0x18000a1cd`
- name: `GetUserSidFromToken`
- size: `353`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800465f0`

## callees

- `0x180002214`
- `0x180003180`
- `0x180009e60`
- `0x180009f84`
- `0x18000a06c`
- `0x18000dce4`
- `0x18000dd60`
- `0x180061960`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a0f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a0f0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000a0d4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000a152`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000a0d4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000a152`

## string_xrefs

- `0x18000a166`: `C:\__w\1\s\src\Client\lib\util\SecurityUtil.cpp`
- `0x18000a194`: `C:\__w\1\s\src\Client\lib\util\SecurityUtil.cpp`

## pseudocode

```c
__int64 __fastcall GetUserSidFromToken(HANDLE TokenHandle, _QWORD *a2)
{
  PSID *v2; // rbx
  unsigned int v5; // edi
  __int64 v6; // rdx
  __int64 v7; // r9
  unsigned int LastError; // eax
  const char *v9; // r9
  __int64 v10; // rdx
  DWORD v11; // r9d
  int v12; // eax
  int ReturnLength; // [rsp+20h] [rbp-38h]
  DWORD TokenInformationLength; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v2 = 0;
  TokenInformationLength = 0;
  if ( !a2 )
  {
    v5 = -2147467261;
    v6 = 459;
    v7 = 2147500035LL;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SecurityUtil.cpp",
      (const char *)v7,
      ReturnLength);
    goto LABEL_21;
  }
  if ( !TokenHandle )
  {
    LastError = SusAllocLocalSystemSid(a2);
LABEL_16:
    v5 = LastError;
    goto LABEL_21;
  }
  if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
  {
    v5 = -2145120257;
    v6 = 472;
    v7 = 2149847039LL;
    goto LABEL_19;
  }
  if ( GetLastError() != 122 )
  {
    v10 = 475;
LABEL_15:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v10,
                  (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SecurityUtil.cpp",
                  v9);
    goto LABEL_16;
  }
  v11 = TokenInformationLength;
  if ( TokenInformationLength )
  {
    v2 = (PSID *)SafeSusAllocArray(TokenInformationLength, 1u);
    v5 = v2 == 0 ? 0x8007000E : 0;
    if ( !v2 )
    {
      v7 = v5;
      v6 = 476;
      goto LABEL_19;
    }
    v11 = TokenInformationLength;
  }
  if ( !GetTokenInformation(TokenHandle, TokenUser, v2, v11, &TokenInformationLength) )
  {
    v10 = 477;
    goto LABEL_15;
  }
  v12 = CopySidAlloc(*v2, a2);
  v5 = v12;
  if ( v12 < 0 )
  {
    v7 = (unsigned int)v12;
    v6 = 478;
    goto LABEL_19;
  }
  v5 = 0;
LABEL_21:
  if ( v2 )
    SusFree(v2);
  return v5;
}

```

## disassembly

```asm
0x18000a06c  mov     [rsp+arg_10], rbx
0x18000a071  push    rbp
0x18000a072  push    rsi
0x18000a073  push    rdi
0x18000a074  sub     rsp, 40h
0x18000a078  mov     rax, cs:__security_cookie
0x18000a07f  xor     rax, rsp
0x18000a082  mov     [rsp+58h+var_20], rax
0x18000a087  xor     ebx, ebx
0x18000a089  mov     [rsp+58h+TokenInformationLength], 0
0x18000a091  mov     rsi, rdx
0x18000a094  mov     rbp, rcx
0x18000a097  test    rdx, rdx
0x18000a09a  jnz     short loc_18000A0AE
0x18000a09c  mov     edi, 80004003h
0x18000a0a1  mov     edx, 1CBh
0x18000a0a6  mov     r9d, edi
0x18000a0a9  jmp     loc_18000A18F
0x18000a0ae  test    rbp, rbp
0x18000a0b1  jnz     short loc_18000A0C0
0x18000a0b3  mov     rcx, rsi
0x18000a0b6  call    SusAllocLocalSystemSid
0x18000a0bb  jmp     loc_18000A172
0x18000a0c0  xor     r9d, r9d; TokenInformationLength
0x18000a0c3  lea     rax, [rsp+58h+TokenInformationLength]
0x18000a0c8  xor     r8d, r8d; TokenInformation
0x18000a0cb  mov     qword ptr [rsp+58h+ReturnLength], rax; ReturnLength
0x18000a0d0  lea     edx, [r9+1]; TokenInformationClass
0x18000a0d4  call    cs:__imp_GetTokenInformation
0x18000a0da  test    eax, eax
0x18000a0dc  jz      short loc_18000A0F0
0x18000a0de  mov     edi, 80240FFFh
0x18000a0e3  mov     edx, 1D8h
0x18000a0e8  mov     r9d, edi
0x18000a0eb  jmp     loc_18000A18F
0x18000a0f0  call    cs:__imp_GetLastError
0x18000a0f6  cmp     eax, 7Ah ; 'z'
0x18000a0f9  jz      short loc_18000A102
0x18000a0fb  mov     edx, 1DBh
0x18000a100  jmp     short loc_18000A161
0x18000a102  mov     r9d, [rsp+58h+TokenInformationLength]
0x18000a107  mov     ecx, r9d; unsigned __int64
0x18000a10a  test    r9d, r9d
0x18000a10d  jz      short loc_18000A13D
0x18000a10f  mov     edx, 1; unsigned __int64
0x18000a114  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x18000a119  mov     rbx, rax
0x18000a11c  neg     rax
0x18000a11f  sbb     edi, edi
0x18000a121  not     edi
0x18000a123  and     edi, 8007000Eh
0x18000a129  test    rbx, rbx
0x18000a12c  jnz     short loc_18000A138
0x18000a12e  mov     r9d, edi
0x18000a131  mov     edx, 1DCh
0x18000a136  jmp     short loc_18000A18F
0x18000a138  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x18000a13d  lea     rax, [rsp+58h+TokenInformationLength]
0x18000a142  mov     r8, rbx; TokenInformation
0x18000a145  mov     edx, 1; TokenInformationClass
0x18000a14a  mov     qword ptr [rsp+58h+ReturnLength], rax; int
0x18000a14f  mov     rcx, rbp; TokenHandle
0x18000a152  call    cs:__imp_GetTokenInformation
0x18000a158  test    eax, eax
0x18000a15a  jnz     short loc_18000A176
0x18000a15c  mov     edx, 1DDh; void *
0x18000a161  mov     rcx, [rsp+58h]; this
0x18000a166  lea     r8, aCW1SSrcClientL_17; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000a16d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000a172  mov     edi, eax
0x18000a174  jmp     short loc_18000A1A4
0x18000a176  mov     rcx, [rbx]; pSourceSid
0x18000a179  mov     rdx, rsi
0x18000a17c  call    CopySidAlloc
0x18000a181  mov     edi, eax
0x18000a183  test    eax, eax
0x18000a185  jns     short loc_18000A1A2
0x18000a187  mov     r9d, eax; char *
0x18000a18a  mov     edx, 1DEh; void *
0x18000a18f  mov     rcx, [rsp+58h]; this
0x18000a194  lea     r8, aCW1SSrcClientL_17; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000a19b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a1a0  jmp     short loc_18000A1A4
0x18000a1a2  xor     edi, edi
0x18000a1a4  test    rbx, rbx
0x18000a1a7  jz      short loc_18000A1B1
0x18000a1a9  mov     rcx, rbx; lpMem
0x18000a1ac  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18000a1b1  mov     eax, edi
0x18000a1b3  mov     rcx, [rsp+58h+var_20]
0x18000a1b8  xor     rcx, rsp; StackCookie
0x18000a1bb  call    __security_check_cookie
0x18000a1c0  mov     rbx, [rsp+58h+arg_10]
0x18000a1c5  add     rsp, 40h
0x18000a1c9  pop     rdi
0x18000a1ca  pop     rsi
0x18000a1cb  pop     rbp
0x18000a1cc  retn
```
