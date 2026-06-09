# GetUserSidFromToken

- ea: `0x140010698`
- end: `0x1400107f9`
- name: `GetUserSidFromToken`
- size: `353`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140038a68`

## callees

- `0x140008de4`
- `0x140008e08`
- `0x14000ce30`
- `0x14000ce9c`
- `0x14001048c`
- `0x1400105b0`
- `0x140010698`
- `0x140045dc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001071c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001071c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140010700`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14001077e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140010700`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14001077e`

## string_xrefs

- `0x140010792`: `C:\__w\1\s\src\Client\lib\util\SecurityUtil.cpp`
- `0x1400107c0`: `C:\__w\1\s\src\Client\lib\util\SecurityUtil.cpp`

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
0x140010698  mov     [rsp+arg_10], rbx
0x14001069d  push    rbp
0x14001069e  push    rsi
0x14001069f  push    rdi
0x1400106a0  sub     rsp, 40h
0x1400106a4  mov     rax, cs:__security_cookie
0x1400106ab  xor     rax, rsp
0x1400106ae  mov     [rsp+58h+var_20], rax
0x1400106b3  xor     ebx, ebx
0x1400106b5  mov     [rsp+58h+TokenInformationLength], 0
0x1400106bd  mov     rsi, rdx
0x1400106c0  mov     rbp, rcx
0x1400106c3  test    rdx, rdx
0x1400106c6  jnz     short loc_1400106DA
0x1400106c8  mov     edi, 80004003h
0x1400106cd  mov     edx, 1CBh
0x1400106d2  mov     r9d, edi
0x1400106d5  jmp     loc_1400107BB
0x1400106da  test    rbp, rbp
0x1400106dd  jnz     short loc_1400106EC
0x1400106df  mov     rcx, rsi
0x1400106e2  call    SusAllocLocalSystemSid
0x1400106e7  jmp     loc_14001079E
0x1400106ec  xor     r9d, r9d; TokenInformationLength
0x1400106ef  lea     rax, [rsp+58h+TokenInformationLength]
0x1400106f4  xor     r8d, r8d; TokenInformation
0x1400106f7  mov     qword ptr [rsp+58h+ReturnLength], rax; ReturnLength
0x1400106fc  lea     edx, [r9+1]; TokenInformationClass
0x140010700  call    cs:__imp_GetTokenInformation
0x140010706  test    eax, eax
0x140010708  jz      short loc_14001071C
0x14001070a  mov     edi, 80240FFFh
0x14001070f  mov     edx, 1D8h
0x140010714  mov     r9d, edi
0x140010717  jmp     loc_1400107BB
0x14001071c  call    cs:__imp_GetLastError
0x140010722  cmp     eax, 7Ah ; 'z'
0x140010725  jz      short loc_14001072E
0x140010727  mov     edx, 1DBh
0x14001072c  jmp     short loc_14001078D
0x14001072e  mov     r9d, [rsp+58h+TokenInformationLength]
0x140010733  mov     ecx, r9d; unsigned __int64
0x140010736  test    r9d, r9d
0x140010739  jz      short loc_140010769
0x14001073b  mov     edx, 1; unsigned __int64
0x140010740  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x140010745  mov     rbx, rax
0x140010748  neg     rax
0x14001074b  sbb     edi, edi
0x14001074d  not     edi
0x14001074f  and     edi, 8007000Eh
0x140010755  test    rbx, rbx
0x140010758  jnz     short loc_140010764
0x14001075a  mov     r9d, edi
0x14001075d  mov     edx, 1DCh
0x140010762  jmp     short loc_1400107BB
0x140010764  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x140010769  lea     rax, [rsp+58h+TokenInformationLength]
0x14001076e  mov     r8, rbx; TokenInformation
0x140010771  mov     edx, 1; TokenInformationClass
0x140010776  mov     qword ptr [rsp+58h+ReturnLength], rax; int
0x14001077b  mov     rcx, rbp; TokenHandle
0x14001077e  call    cs:__imp_GetTokenInformation
0x140010784  test    eax, eax
0x140010786  jnz     short loc_1400107A2
0x140010788  mov     edx, 1DDh; void *
0x14001078d  mov     rcx, [rsp+58h]; this
0x140010792  lea     r8, aCW1SSrcClientL_23; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x140010799  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14001079e  mov     edi, eax
0x1400107a0  jmp     short loc_1400107D0
0x1400107a2  mov     rcx, [rbx]; pSourceSid
0x1400107a5  mov     rdx, rsi
0x1400107a8  call    CopySidAlloc
0x1400107ad  mov     edi, eax
0x1400107af  test    eax, eax
0x1400107b1  jns     short loc_1400107CE
0x1400107b3  mov     r9d, eax; char *
0x1400107b6  mov     edx, 1DEh; void *
0x1400107bb  mov     rcx, [rsp+58h]; this
0x1400107c0  lea     r8, aCW1SSrcClientL_23; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1400107c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400107cc  jmp     short loc_1400107D0
0x1400107ce  xor     edi, edi
0x1400107d0  test    rbx, rbx
0x1400107d3  jz      short loc_1400107DD
0x1400107d5  mov     rcx, rbx; lpMem
0x1400107d8  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1400107dd  mov     eax, edi
0x1400107df  mov     rcx, [rsp+58h+var_20]
0x1400107e4  xor     rcx, rsp; StackCookie
0x1400107e7  call    __security_check_cookie
0x1400107ec  mov     rbx, [rsp+58h+arg_10]
0x1400107f1  add     rsp, 40h
0x1400107f5  pop     rdi
0x1400107f6  pop     rsi
0x1400107f7  pop     rbp
0x1400107f8  retn
```
