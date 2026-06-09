# ATL::CAccessToken::GetInfoConvert<ATL::CSid,_TOKEN_USER>(ATL::CSid *,_TOKEN_INFORMATION_CLASS,_TOKEN_USER *)

- ea: `0x18000d730`
- end: `0x18000d922`
- name: `??$GetInfoConvert@VCSid@ATL@@U_TOKEN_USER@@@CAccessToken@ATL@@IEBA_NPEAVCSid@1@W4_TOKEN_INFORMATION_CLASS@@PEAU_TOKEN_USER@@@Z`
- size: `498`
- prototype: `char __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x180015250`
- `0x180035814`

## callees

- `0x1800032e0`
- `0x18000d730`
- `0x180010458`
- `0x18001047c`
- `0x180012ea8`
- `0x180018450`
- `0x1801adab0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000d81b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000d866`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000d8f4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000d81b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000d866`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000d8f4`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000d7e9`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000d7e9`
- `KERNEL32!GetLastError` at `0x18000d789`
- `KERNEL32!GetLastError` at `0x18000d789`
- `ADVAPI32!CopySid` at `0x18000d8db`
- `ADVAPI32!CopySid` at `0x18000d8db`
- `ADVAPI32!GetLengthSid` at `0x18000d8c4`
- `ADVAPI32!GetLengthSid` at `0x18000d8c4`
- `ADVAPI32!IsValidSid` at `0x18000d8b7`
- `ADVAPI32!IsValidSid` at `0x18000d8b7`
- `ADVAPI32!GetTokenInformation` at `0x18000d783`
- `ADVAPI32!GetTokenInformation` at `0x18000d854`
- `ADVAPI32!GetTokenInformation` at `0x18000d783`
- `ADVAPI32!GetTokenInformation` at `0x18000d854`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
char __fastcall ATL::CAccessToken::GetInfoConvert<ATL::CSid,_TOKEN_USER>(__int64 a1, __int64 a2)
{
  unsigned __int64 v4; // rdx
  _QWORD *v5; // rbx
  DWORD v6; // eax
  DWORD v7; // r9d
  unsigned __int64 v8; // rcx
  void *v9; // rsp
  void *v10; // rsp
  DWORD *p_TokenInformation; // rsi
  _QWORD *v12; // rax
  void *v13; // rcx
  void *v15; // rcx
  void *v16; // rsi
  DWORD LengthSid; // eax
  void *v18; // rcx
  int Error; // eax
  DWORD TokenInformation; // [rsp+30h] [rbp+0h] BYREF
  _QWORD *v21; // [rsp+38h] [rbp+8h]
  __int64 v22; // [rsp+40h] [rbp+10h]

  v22 = -2;
  if ( !a2 )
    return 0;
  TokenInformation = 0;
  GetTokenInformation(*(HANDLE *)(a1 + 8), TokenUser, 0, 0, &TokenInformation);
  if ( GetLastError() != 122 )
    return 0;
  v5 = 0;
  v21 = 0;
  v6 = TokenInformation;
  if ( TokenInformation > 0x400 )
    goto LABEL_9;
  if ( !ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable((ATL::_ATL_SAFE_ALLOCA_IMPL *)TokenInformation, v4) )
  {
    v6 = TokenInformation;
LABEL_9:
    v12 = malloc(v6 + 16LL);
    if ( v12 )
    {
      *v12 = 0;
      v5 = v12;
      v21 = v12;
      p_TokenInformation = (DWORD *)(v12 + 2);
    }
    else
    {
      p_TokenInformation = 0;
    }
    v7 = TokenInformation;
    goto LABEL_13;
  }
  v7 = TokenInformation;
  v8 = TokenInformation + 15LL;
  if ( v8 <= TokenInformation )
    v8 = 0xFFFFFFFFFFFFFF0LL;
  v9 = alloca(v8 & 0xFFFFFFFFFFFFFFF0uLL);
  v10 = alloca(v8 & 0xFFFFFFFFFFFFFFF0uLL);
  p_TokenInformation = &TokenInformation;
LABEL_13:
  if ( !p_TokenInformation )
  {
    while ( v5 )
    {
      v13 = v5;
      v5 = (_QWORD *)*v5;
      free(v13);
    }
    return 0;
  }
  if ( !GetTokenInformation(*(HANDLE *)(a1 + 8), TokenUser, p_TokenInformation, v7, &TokenInformation) )
  {
    while ( v5 )
    {
      v15 = v5;
      v5 = (_QWORD *)*v5;
      free(v15);
    }
    return 0;
  }
  v16 = *(void **)p_TokenInformation;
  if ( !*(_BYTE *)(a2 + 76) || (void *)(a2 + 8) != v16 )
  {
    *(_DWORD *)(a2 + 80) = 7;
    ATL::CSimpleStringT<unsigned short,0>::Empty(a2 + 88);
    ATL::CSimpleStringT<unsigned short,0>::Empty(a2 + 96);
    ATL::CSimpleStringT<unsigned short,0>::Empty(a2 + 104);
    ATL::CSimpleStringT<unsigned short,0>::Empty(a2 + 112);
    *(_BYTE *)(a2 + 76) = 0;
    if ( !IsValidSid(v16) || (LengthSid = GetLengthSid(v16), LengthSid > 0x44) )
      ATL::AtlThrowImpl(-2147024809);
    *(_BYTE *)(a2 + 76) = 1;
    if ( !CopySid(LengthSid, (PSID)(a2 + 8), v16) )
    {
      Error = ATL::AtlHresultFromLastError();
      *(_BYTE *)(a2 + 76) = 0;
      ATL::AtlThrowImpl(Error);
    }
    *(_DWORD *)(a2 + 80) = 8;
  }
  while ( v5 )
  {
    v18 = v5;
    v5 = (_QWORD *)*v5;
    free(v18);
  }
  return 1;
}

```

## disassembly

```asm
0x18000d730  push    rbp
0x18000d732  push    rbx
0x18000d733  push    rsi
0x18000d734  push    rdi
0x18000d735  push    r14
0x18000d737  sub     rsp, 50h
0x18000d73b  lea     rbp, [rsp+30h]
0x18000d740  mov     [rbp+40h+var_30], 0FFFFFFFFFFFFFFFEh
0x18000d748  mov     rax, cs:__security_cookie
0x18000d74f  xor     rax, rbp
0x18000d752  mov     [rbp+40h+var_28], rax
0x18000d756  mov     rdi, rdx
0x18000d759  mov     r14, rcx
0x18000d75c  test    rdx, rdx
0x18000d75f  jz      loc_18000D826
0x18000d765  mov     [rbp+40h+TokenInformation], 0
0x18000d76c  lea     rax, [rbp+40h+TokenInformation]
0x18000d770  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x18000d775  xor     r9d, r9d; TokenInformationLength
0x18000d778  xor     r8d, r8d; TokenInformation
0x18000d77b  lea     edx, [r9+1]; TokenInformationClass
0x18000d77f  mov     rcx, [rcx+8]; TokenHandle
0x18000d783  call    cs:__imp_GetTokenInformation
0x18000d789  call    cs:__imp_GetLastError
0x18000d78f  cmp     eax, 7Ah ; 'z'
0x18000d792  jnz     loc_18000D826
0x18000d798  xor     ebx, ebx
0x18000d79a  mov     [rbp+40h+var_38], rbx
0x18000d79e  mov     eax, [rbp+40h+TokenInformation]
0x18000d7a1  cmp     eax, 400h
0x18000d7a6  ja      short loc_18000D7E3
0x18000d7a8  mov     ecx, eax; this
0x18000d7aa  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x18000d7af  test    al, al
0x18000d7b1  jz      short loc_18000D7E0
0x18000d7b3  mov     r9d, [rbp+40h+TokenInformation]
0x18000d7b7  lea     rcx, [r9+0Fh]
0x18000d7bb  cmp     rcx, r9
0x18000d7be  ja      short loc_18000D7CA
0x18000d7c0  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18000d7ca  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18000d7ce  mov     rax, rcx
0x18000d7d1  call    _alloca_probe
0x18000d7d6  sub     rsp, rcx
0x18000d7d9  lea     rsi, [rsp+70h+TokenInformation]
0x18000d7de  jmp     short loc_18000D80E
0x18000d7e0  mov     eax, [rbp+40h+TokenInformation]
0x18000d7e3  mov     ecx, eax
0x18000d7e5  add     rcx, 10h; Size
0x18000d7e9  call    cs:__imp_malloc
0x18000d7ef  test    rax, rax
0x18000d7f2  jnz     short loc_18000D7F8
0x18000d7f4  xor     esi, esi
0x18000d7f6  jmp     short loc_18000D80A
0x18000d7f8  mov     qword ptr [rax], 0
0x18000d7ff  mov     rbx, rax
0x18000d802  mov     [rbp+40h+var_38], rax
0x18000d806  lea     rsi, [rax+10h]
0x18000d80a  mov     r9d, [rbp+40h+TokenInformation]; TokenInformationLength
0x18000d80e  test    rsi, rsi
0x18000d811  jnz     short loc_18000D83F
0x18000d813  jmp     short loc_18000D821
0x18000d815  mov     rcx, rbx; Block
0x18000d818  mov     rbx, [rbx]
0x18000d81b  call    cs:__imp_free
0x18000d821  test    rbx, rbx
0x18000d824  jnz     short loc_18000D815
0x18000d826  xor     al, al
0x18000d828  mov     rcx, [rbp+40h+var_28]
0x18000d82c  xor     rcx, rbp; StackCookie
0x18000d82f  call    __security_check_cookie
0x18000d834  lea     rsp, [rbp+20h]
0x18000d838  pop     r14
0x18000d83a  pop     rdi
0x18000d83b  pop     rsi
0x18000d83c  pop     rbx
0x18000d83d  pop     rbp
0x18000d83e  retn
0x18000d83f  lea     rax, [rbp+40h+TokenInformation]
0x18000d843  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x18000d848  mov     r8, rsi; TokenInformation
0x18000d84b  mov     edx, 1; TokenInformationClass
0x18000d850  mov     rcx, [r14+8]; TokenHandle
0x18000d854  call    cs:__imp_GetTokenInformation
0x18000d85a  test    eax, eax
0x18000d85c  jnz     short loc_18000D873
0x18000d85e  jmp     short loc_18000D86C
0x18000d860  mov     rcx, rbx; Block
0x18000d863  mov     rbx, [rbx]
0x18000d866  call    cs:__imp_free
0x18000d86c  test    rbx, rbx
0x18000d86f  jnz     short loc_18000D860
0x18000d871  jmp     short loc_18000D826
0x18000d873  mov     rsi, [rsi]
0x18000d876  lea     r14, [rdi+8]
0x18000d87a  cmp     byte ptr [rdi+4Ch], 0
0x18000d87e  jz      short loc_18000D885
0x18000d880  cmp     r14, rsi
0x18000d883  jz      short loc_18000D8EC
0x18000d885  mov     dword ptr [rdi+50h], 7
0x18000d88c  lea     rcx, [rdi+58h]
0x18000d890  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x18000d895  lea     rcx, [rdi+60h]
0x18000d899  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x18000d89e  lea     rcx, [rdi+68h]
0x18000d8a2  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x18000d8a7  lea     rcx, [rdi+70h]
0x18000d8ab  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x18000d8b0  mov     byte ptr [rdi+4Ch], 0
0x18000d8b4  mov     rcx, rsi; pSid
0x18000d8b7  call    cs:__imp_IsValidSid
0x18000d8bd  test    eax, eax
0x18000d8bf  jz      short loc_18000D917
0x18000d8c1  mov     rcx, rsi; pSid
0x18000d8c4  call    cs:__imp_GetLengthSid
0x18000d8ca  cmp     eax, 44h ; 'D'
0x18000d8cd  ja      short loc_18000D917
0x18000d8cf  mov     byte ptr [rdi+4Ch], 1
0x18000d8d3  mov     r8, rsi; pSourceSid
0x18000d8d6  mov     rdx, r14; pDestinationSid
0x18000d8d9  mov     ecx, eax; nDestinationSidLength
0x18000d8db  call    cs:__imp_CopySid
0x18000d8e1  test    eax, eax
0x18000d8e3  jz      short loc_18000D906
0x18000d8e5  mov     dword ptr [rdi+50h], 8
0x18000d8ec  jmp     short loc_18000D8FA
0x18000d8ee  mov     rcx, rbx; Block
0x18000d8f1  mov     rbx, [rbx]
0x18000d8f4  call    cs:__imp_free
0x18000d8fa  test    rbx, rbx
0x18000d8fd  jnz     short loc_18000D8EE
0x18000d8ff  mov     al, 1
0x18000d901  jmp     loc_18000D828
0x18000d906  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000d90b  mov     byte ptr [rdi+4Ch], 0
0x18000d90f  mov     ecx, eax; int
0x18000d911  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000d917  mov     ecx, 80070057h; int
0x18000d91c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
