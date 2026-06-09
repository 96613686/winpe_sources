# ATL::CAccessToken::GetInfoConvert<ATL::CSid,_TOKEN_USER>(ATL::CSid *,_TOKEN_INFORMATION_CLASS,_TOKEN_USER *)

- ea: `0x18001f09c`
- end: `0x18001f29f`
- name: `??$GetInfoConvert@VCSid@ATL@@U_TOKEN_USER@@@CAccessToken@ATL@@IEBA_NPEAVCSid@1@W4_TOKEN_INFORMATION_CLASS@@PEAU_TOKEN_USER@@@Z`
- size: `515`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `14`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180011fa0`
- `0x18001733c`
- `0x180017c0c`
- `0x180019870`
- `0x180019bb0`
- `0x18001de04`
- `0x18001ee04`
- `0x1800567ac`
- `0x18005ccf8`
- `0x18006a280`
- `0x18009772c`
- `0x18009b528`
- `0x1800c157c`
- `0x180117508`

## callees

- `0x18001e838`
- `0x18001e8f0`
- `0x18001f09c`
- `0x18001f2a8`
- `0x18005013c`
- `0x18009e2e4`
- `0x1800a98c0`
- `0x180152970`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001f187`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001f23e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001f187`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001f23e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001f1b9`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001f1b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f0f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f0f2`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001f21f`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001f21f`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001f1ef`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001f1ef`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001f207`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001f207`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001f0ec`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001f16f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001f0ec`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001f16f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall ATL::CAccessToken::GetInfoConvert<ATL::CSid,_TOKEN_USER>(__int64 a1, __int64 a2)
{
  unsigned __int64 v4; // rdx
  void **v5; // rbx
  DWORD v6; // eax
  DWORD v7; // r9d
  unsigned __int64 v8; // rcx
  void *v9; // rsp
  void *v10; // rsp
  void **p_TokenInformation; // r14
  void **v12; // rsi
  void **v14; // rax
  void *v15; // r14
  DWORD LengthSid; // eax
  int LastErrorAsHResult; // eax
  void **TokenInformation; // [rsp+30h] [rbp+0h] BYREF
  DWORD ReturnLength; // [rsp+38h] [rbp+8h] BYREF

  if ( !a2 )
    return 0;
  ReturnLength = 0;
  GetTokenInformation(*(HANDLE *)(a1 + 8), TokenUser, 0, 0, &ReturnLength);
  if ( GetLastError() != 122 )
    return 0;
  v5 = 0;
  TokenInformation = 0;
  v6 = ReturnLength;
  if ( ReturnLength > 0x400 )
    goto LABEL_13;
  if ( !ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable((ATL::_ATL_SAFE_ALLOCA_IMPL *)ReturnLength, v4) )
  {
    v6 = ReturnLength;
LABEL_13:
    v14 = (void **)malloc(v6 + 16LL);
    v12 = v14;
    if ( v14 )
    {
      *v14 = 0;
      v5 = v14;
      TokenInformation = v14;
      p_TokenInformation = v14 + 2;
    }
    else
    {
      p_TokenInformation = 0;
    }
    v7 = ReturnLength;
    goto LABEL_8;
  }
  v7 = ReturnLength;
  v8 = ReturnLength + 15LL;
  if ( v8 <= ReturnLength )
    v8 = 0xFFFFFFFFFFFFFF0LL;
  v9 = alloca(v8 & 0xFFFFFFFFFFFFFFF0uLL);
  v10 = alloca(v8 & 0xFFFFFFFFFFFFFFF0uLL);
  p_TokenInformation = (void **)&TokenInformation;
  v12 = 0;
LABEL_8:
  if ( !p_TokenInformation )
  {
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&TokenInformation);
    return 0;
  }
  if ( !GetTokenInformation(*(HANDLE *)(a1 + 8), TokenUser, p_TokenInformation, v7, &ReturnLength) )
  {
    for ( ; v5; v12 = v5 )
    {
      v5 = (void **)*v5;
      free(v12);
    }
    return 0;
  }
  v15 = *p_TokenInformation;
  if ( !*(_BYTE *)(a2 + 76) || (void *)(a2 + 8) != v15 )
  {
    ATL::CSid::Clear((ATL::CSid *)a2);
    if ( !IsValidSid(v15) || (LengthSid = GetLengthSid(v15), LengthSid > 0x44) )
      ATL::AtlThrowImpl(-2147024809);
    *(_BYTE *)(a2 + 76) = 1;
    if ( !CopySid(LengthSid, (PSID)(a2 + 8), v15) )
    {
      LastErrorAsHResult = LocationHelper::GetLastErrorAsHResult();
      *(_BYTE *)(a2 + 76) = 0;
      ATL::AtlThrowImpl(LastErrorAsHResult);
    }
    *(_DWORD *)(a2 + 80) = 8;
  }
  for ( ; v5; v12 = v5 )
  {
    v5 = (void **)*v5;
    free(v12);
  }
  return 1;
}

```

## disassembly

```asm
0x18001f09c  push    rbp
0x18001f09e  push    rsi
0x18001f09f  push    rdi
0x18001f0a0  push    r14
0x18001f0a2  push    r15
0x18001f0a4  sub     rsp, 50h
0x18001f0a8  lea     rbp, [rsp+30h]
0x18001f0ad  mov     [rbp+40h+arg_10], rbx
0x18001f0b1  mov     rax, cs:__security_cookie
0x18001f0b8  xor     rax, rbp
0x18001f0bb  mov     [rbp+40h+var_30], rax
0x18001f0bf  mov     rdi, rdx
0x18001f0c2  mov     r15, rcx
0x18001f0c5  test    rdx, rdx
0x18001f0c8  jz      loc_18001F195
0x18001f0ce  mov     [rbp+40h+var_38], 0
0x18001f0d5  lea     rax, [rbp+40h+var_38]
0x18001f0d9  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x18001f0de  xor     r9d, r9d; TokenInformationLength
0x18001f0e1  xor     r8d, r8d; TokenInformation
0x18001f0e4  lea     edx, [r9+1]; TokenInformationClass
0x18001f0e8  mov     rcx, [rcx+8]; TokenHandle
0x18001f0ec  call    cs:__imp_GetTokenInformation
0x18001f0f2  call    cs:__imp_GetLastError
0x18001f0f8  cmp     eax, 7Ah ; 'z'
0x18001f0fb  jnz     loc_18001F195
0x18001f101  xor     ebx, ebx
0x18001f103  mov     [rbp+40h+TokenInformation], rbx
0x18001f107  mov     eax, [rbp+40h+var_38]
0x18001f10a  cmp     eax, 400h
0x18001f10f  ja      loc_18001F1B3
0x18001f115  mov     ecx, eax; this
0x18001f117  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x18001f11c  test    al, al
0x18001f11e  jz      loc_18001F253
0x18001f124  mov     r9d, [rbp+40h+var_38]
0x18001f128  lea     rcx, [r9+0Fh]
0x18001f12c  cmp     rcx, r9
0x18001f12f  ja      short loc_18001F13B
0x18001f131  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18001f13b  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18001f13f  mov     rax, rcx
0x18001f142  call    _alloca_probe
0x18001f147  sub     rsp, rcx
0x18001f14a  lea     r14, [rsp+70h+TokenInformation]
0x18001f14f  xor     esi, esi
0x18001f151  test    r14, r14
0x18001f154  jz      loc_18001F272
0x18001f15a  lea     rax, [rbp+40h+var_38]
0x18001f15e  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x18001f163  mov     r8, r14; TokenInformation
0x18001f166  mov     edx, 1; TokenInformationClass
0x18001f16b  mov     rcx, [r15+8]; TokenHandle
0x18001f16f  call    cs:__imp_GetTokenInformation
0x18001f175  test    eax, eax
0x18001f177  jnz     short loc_18001F1D7
0x18001f179  test    rbx, rbx
0x18001f17c  jz      short loc_18001F195
0x18001f17e  mov     rdi, [rbx]
0x18001f181  mov     rbx, rdi
0x18001f184  mov     rcx, rsi; Block
0x18001f187  call    cs:__imp_free
0x18001f18d  mov     rsi, rdi
0x18001f190  test    rdi, rdi
0x18001f193  jnz     short loc_18001F17E
0x18001f195  xor     al, al
0x18001f197  mov     rcx, [rbp+40h+var_30]
0x18001f19b  xor     rcx, rbp; StackCookie
0x18001f19e  call    __security_check_cookie
0x18001f1a3  mov     rbx, [rbp+40h+arg_10]
0x18001f1a7  lea     rsp, [rbp+20h]
0x18001f1ab  pop     r15
0x18001f1ad  pop     r14
0x18001f1af  pop     rdi
0x18001f1b0  pop     rsi
0x18001f1b1  pop     rbp
0x18001f1b2  retn
0x18001f1b3  mov     ecx, eax
0x18001f1b5  add     rcx, 10h; Size
0x18001f1b9  call    cs:__imp_malloc
0x18001f1bf  mov     rsi, rax
0x18001f1c2  test    rax, rax
0x18001f1c5  jnz     loc_18001F25B
0x18001f1cb  xor     r14d, r14d
0x18001f1ce  mov     r9d, [rbp+40h+var_38]
0x18001f1d2  jmp     loc_18001F151
0x18001f1d7  mov     r14, [r14]
0x18001f1da  cmp     byte ptr [rdi+4Ch], 0
0x18001f1de  jnz     loc_18001F280
0x18001f1e4  mov     rcx, rdi; this
0x18001f1e7  call    ?Clear@CSid@ATL@@AEAAXXZ; ATL::CSid::Clear(void)
0x18001f1ec  mov     rcx, r14; pSid
0x18001f1ef  call    cs:__imp_IsValidSid
0x18001f1f5  test    eax, eax
0x18001f1f7  jnz     short loc_18001F204
0x18001f1f9  mov     ecx, 80070057h; int
0x18001f1fe  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001f204  mov     rcx, r14; pSid
0x18001f207  call    cs:__imp_GetLengthSid
0x18001f20d  cmp     eax, 44h ; 'D'
0x18001f210  ja      short loc_18001F1F9
0x18001f212  mov     byte ptr [rdi+4Ch], 1
0x18001f216  lea     rdx, [rdi+8]; pDestinationSid
0x18001f21a  mov     r8, r14; pSourceSid
0x18001f21d  mov     ecx, eax; nDestinationSidLength
0x18001f21f  call    cs:__imp_CopySid
0x18001f225  test    eax, eax
0x18001f227  jz      short loc_18001F28E
0x18001f229  mov     dword ptr [rdi+50h], 8
0x18001f230  test    rbx, rbx
0x18001f233  jz      short loc_18001F24C
0x18001f235  mov     rdi, [rbx]
0x18001f238  mov     rbx, rdi
0x18001f23b  mov     rcx, rsi; Block
0x18001f23e  call    cs:__imp_free
0x18001f244  mov     rsi, rdi
0x18001f247  test    rdi, rdi
0x18001f24a  jnz     short loc_18001F235
0x18001f24c  mov     al, 1
0x18001f24e  jmp     loc_18001F197
0x18001f253  mov     eax, [rbp+40h+var_38]
0x18001f256  jmp     loc_18001F1B3
0x18001f25b  mov     qword ptr [rax], 0
0x18001f262  mov     rbx, rax
0x18001f265  mov     [rbp+40h+TokenInformation], rax
0x18001f269  lea     r14, [rax+10h]
0x18001f26d  jmp     loc_18001F1CE
0x18001f272  lea     rcx, [rbp+40h+TokenInformation]
0x18001f276  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001f27b  jmp     loc_18001F195
0x18001f280  lea     rax, [rdi+8]
0x18001f284  cmp     rax, r14
0x18001f287  jz      short loc_18001F230
0x18001f289  jmp     loc_18001F1E4
0x18001f28e  call    ?GetLastErrorAsHResult@LocationHelper@@SAJXZ; LocationHelper::GetLastErrorAsHResult(void)
0x18001f293  mov     byte ptr [rdi+4Ch], 0
0x18001f297  mov     ecx, eax; int
0x18001f299  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
