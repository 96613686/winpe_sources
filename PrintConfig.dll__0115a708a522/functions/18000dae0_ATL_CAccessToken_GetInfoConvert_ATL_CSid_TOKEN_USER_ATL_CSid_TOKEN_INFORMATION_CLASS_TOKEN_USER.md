# ATL::CAccessToken::GetInfoConvert<ATL::CSid,_TOKEN_USER>(ATL::CSid *,_TOKEN_INFORMATION_CLASS,_TOKEN_USER *)

- ea: `0x18000dae0`
- end: `0x18000dd0f`
- name: `??$GetInfoConvert@VCSid@ATL@@U_TOKEN_USER@@@CAccessToken@ATL@@IEBA_NPEAVCSid@1@W4_TOKEN_INFORMATION_CLASS@@PEAU_TOKEN_USER@@@Z`
- size: `559`
- prototype: `char __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x180015bc0`
- `0x180036a4c`

## callees

- `0x180003400`
- `0x18000dae0`
- `0x1800109c0`
- `0x1800109e8`
- `0x18001365c`
- `0x180018fb0`
- `0x1801b5620`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000dbdd`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000dc35`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000dcdb`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000dbdd`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000dc35`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000dcdb`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000dba5`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000dba5`
- `KERNEL32!GetLastError` at `0x18000db3f`
- `KERNEL32!GetLastError` at `0x18000db3f`
- `ADVAPI32!CopySid` at `0x18000dcbc`
- `ADVAPI32!CopySid` at `0x18000dcbc`
- `ADVAPI32!GetLengthSid` at `0x18000dc9f`
- `ADVAPI32!GetLengthSid` at `0x18000dc9f`
- `ADVAPI32!IsValidSid` at `0x18000dc8c`
- `ADVAPI32!IsValidSid` at `0x18000dc8c`
- `ADVAPI32!GetTokenInformation` at `0x18000db33`
- `ADVAPI32!GetTokenInformation` at `0x18000dc1d`
- `ADVAPI32!GetTokenInformation` at `0x18000db33`
- `ADVAPI32!GetTokenInformation` at `0x18000dc1d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall ATL::CAccessToken::GetInfoConvert<ATL::CSid,_TOKEN_USER>(__int64 a1, __int64 a2)
{
  _QWORD *v4; // rbx
  DWORD v5; // eax
  DWORD v6; // r9d
  unsigned __int64 v7; // rcx
  void *v8; // rsp
  void *v9; // rsp
  DWORD *p_TokenInformation; // rsi
  _QWORD *v11; // rax
  void *v12; // rcx
  void *v14; // rcx
  void *v15; // rsi
  DWORD LengthSid; // eax
  void *v17; // rcx
  signed int Error; // eax
  DWORD TokenInformation; // [rsp+30h] [rbp+0h] BYREF
  _QWORD *v20; // [rsp+38h] [rbp+8h]
  __int64 v21; // [rsp+40h] [rbp+10h]

  v21 = -2;
  if ( !a2 )
    return 0;
  TokenInformation = 0;
  GetTokenInformation(*(HANDLE *)(a1 + 8), TokenUser, 0, 0, &TokenInformation);
  if ( GetLastError() != 122 )
    return 0;
  v4 = 0;
  v20 = 0;
  v5 = TokenInformation;
  if ( TokenInformation > 0x400 )
    goto LABEL_9;
  if ( !ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(TokenInformation) )
  {
    v5 = TokenInformation;
LABEL_9:
    v11 = malloc(v5 + 16LL);
    if ( v11 )
    {
      *v11 = 0;
      v4 = v11;
      v20 = v11;
      p_TokenInformation = (DWORD *)(v11 + 2);
    }
    else
    {
      p_TokenInformation = 0;
    }
    v6 = TokenInformation;
    goto LABEL_13;
  }
  v6 = TokenInformation;
  v7 = TokenInformation + 15LL;
  if ( v7 <= TokenInformation )
    v7 = 0xFFFFFFFFFFFFFF0LL;
  v8 = alloca(v7 & 0xFFFFFFFFFFFFFFF0uLL);
  v9 = alloca(v7 & 0xFFFFFFFFFFFFFFF0uLL);
  p_TokenInformation = &TokenInformation;
LABEL_13:
  if ( !p_TokenInformation )
  {
    while ( v4 )
    {
      v12 = v4;
      v4 = (_QWORD *)*v4;
      free(v12);
    }
    return 0;
  }
  if ( !GetTokenInformation(*(HANDLE *)(a1 + 8), TokenUser, p_TokenInformation, v6, &TokenInformation) )
  {
    while ( v4 )
    {
      v14 = v4;
      v4 = (_QWORD *)*v4;
      free(v14);
    }
    return 0;
  }
  v15 = *(void **)p_TokenInformation;
  if ( !*(_BYTE *)(a2 + 76) || (void *)(a2 + 8) != v15 )
  {
    *(_DWORD *)(a2 + 80) = 7;
    ATL::CSimpleStringT<unsigned short,0>::Empty((int **)(a2 + 88));
    ATL::CSimpleStringT<unsigned short,0>::Empty((int **)(a2 + 96));
    ATL::CSimpleStringT<unsigned short,0>::Empty((int **)(a2 + 104));
    ATL::CSimpleStringT<unsigned short,0>::Empty((int **)(a2 + 112));
    *(_BYTE *)(a2 + 76) = 0;
    if ( !IsValidSid(v15) || (LengthSid = GetLengthSid(v15), LengthSid > 0x44) )
      ATL::AtlThrowImpl(-2147024809);
    *(_BYTE *)(a2 + 76) = 1;
    if ( !CopySid(LengthSid, (PSID)(a2 + 8), v15) )
    {
      Error = ATL::AtlHresultFromLastError();
      *(_BYTE *)(a2 + 76) = 0;
      ATL::AtlThrowImpl(Error);
    }
    *(_DWORD *)(a2 + 80) = 8;
  }
  while ( v4 )
  {
    v17 = v4;
    v4 = (_QWORD *)*v4;
    free(v17);
  }
  return 1;
}

```

## disassembly

```asm
0x18000dae0  push    rbp
0x18000dae2  push    rbx
0x18000dae3  push    rsi
0x18000dae4  push    rdi
0x18000dae5  push    r14
0x18000dae7  sub     rsp, 50h
0x18000daeb  lea     rbp, [rsp+30h]
0x18000daf0  mov     [rbp+40h+var_30], 0FFFFFFFFFFFFFFFEh
0x18000daf8  mov     rax, cs:__security_cookie
0x18000daff  xor     rax, rbp
0x18000db02  mov     [rbp+40h+var_28], rax
0x18000db06  mov     rdi, rdx
0x18000db09  mov     r14, rcx
0x18000db0c  test    rdx, rdx
0x18000db0f  jz      loc_18000DBEE
0x18000db15  mov     [rbp+40h+TokenInformation], 0
0x18000db1c  lea     rax, [rbp+40h+TokenInformation]
0x18000db20  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x18000db25  xor     r9d, r9d; TokenInformationLength
0x18000db28  xor     r8d, r8d; TokenInformation
0x18000db2b  lea     edx, [r9+1]; TokenInformationClass
0x18000db2f  mov     rcx, [rcx+8]; TokenHandle
0x18000db33  call    cs:__imp_GetTokenInformation
0x18000db3a  nop     dword ptr [rax+rax+00h]
0x18000db3f  call    cs:__imp_GetLastError
0x18000db46  nop     dword ptr [rax+rax+00h]
0x18000db4b  cmp     eax, 7Ah ; 'z'
0x18000db4e  jnz     loc_18000DBEE
0x18000db54  xor     ebx, ebx
0x18000db56  mov     [rbp+40h+var_38], rbx
0x18000db5a  mov     eax, [rbp+40h+TokenInformation]
0x18000db5d  cmp     eax, 400h
0x18000db62  ja      short loc_18000DB9F
0x18000db64  mov     ecx, eax; this
0x18000db66  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x18000db6b  test    al, al
0x18000db6d  jz      short loc_18000DB9C
0x18000db6f  mov     r9d, [rbp+40h+TokenInformation]
0x18000db73  lea     rcx, [r9+0Fh]
0x18000db77  cmp     rcx, r9
0x18000db7a  ja      short loc_18000DB86
0x18000db7c  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18000db86  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18000db8a  mov     rax, rcx
0x18000db8d  call    _alloca_probe
0x18000db92  sub     rsp, rcx
0x18000db95  lea     rsi, [rsp+70h+TokenInformation]
0x18000db9a  jmp     short loc_18000DBD0
0x18000db9c  mov     eax, [rbp+40h+TokenInformation]
0x18000db9f  mov     ecx, eax
0x18000dba1  add     rcx, 10h; Size
0x18000dba5  call    cs:__imp_malloc
0x18000dbac  nop     dword ptr [rax+rax+00h]
0x18000dbb1  test    rax, rax
0x18000dbb4  jnz     short loc_18000DBBA
0x18000dbb6  xor     esi, esi
0x18000dbb8  jmp     short loc_18000DBCC
0x18000dbba  mov     qword ptr [rax], 0
0x18000dbc1  mov     rbx, rax
0x18000dbc4  mov     [rbp+40h+var_38], rax
0x18000dbc8  lea     rsi, [rax+10h]
0x18000dbcc  mov     r9d, [rbp+40h+TokenInformation]; TokenInformationLength
0x18000dbd0  test    rsi, rsi
0x18000dbd3  jnz     short loc_18000DC08
0x18000dbd5  jmp     short loc_18000DBE9
0x18000dbd7  mov     rcx, rbx; Block
0x18000dbda  mov     rbx, [rbx]
0x18000dbdd  call    cs:__imp_free
0x18000dbe4  nop     dword ptr [rax+rax+00h]
0x18000dbe9  test    rbx, rbx
0x18000dbec  jnz     short loc_18000DBD7
0x18000dbee  xor     al, al
0x18000dbf0  mov     rcx, [rbp+40h+var_28]
0x18000dbf4  xor     rcx, rbp; StackCookie
0x18000dbf7  call    __security_check_cookie
0x18000dbfc  lea     rsp, [rbp+20h]
0x18000dc00  pop     r14
0x18000dc02  pop     rdi
0x18000dc03  pop     rsi
0x18000dc04  pop     rbx
0x18000dc05  pop     rbp
0x18000dc06  retn
0x18000dc08  lea     rax, [rbp+40h+TokenInformation]
0x18000dc0c  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x18000dc11  mov     r8, rsi; TokenInformation
0x18000dc14  mov     edx, 1; TokenInformationClass
0x18000dc19  mov     rcx, [r14+8]; TokenHandle
0x18000dc1d  call    cs:__imp_GetTokenInformation
0x18000dc24  nop     dword ptr [rax+rax+00h]
0x18000dc29  test    eax, eax
0x18000dc2b  jnz     short loc_18000DC48
0x18000dc2d  jmp     short loc_18000DC41
0x18000dc2f  mov     rcx, rbx; Block
0x18000dc32  mov     rbx, [rbx]
0x18000dc35  call    cs:__imp_free
0x18000dc3c  nop     dword ptr [rax+rax+00h]
0x18000dc41  test    rbx, rbx
0x18000dc44  jnz     short loc_18000DC2F
0x18000dc46  jmp     short loc_18000DBEE
0x18000dc48  mov     rsi, [rsi]
0x18000dc4b  lea     r14, [rdi+8]
0x18000dc4f  cmp     byte ptr [rdi+4Ch], 0
0x18000dc53  jz      short loc_18000DC5A
0x18000dc55  cmp     r14, rsi
0x18000dc58  jz      short loc_18000DCD3
0x18000dc5a  mov     dword ptr [rdi+50h], 7
0x18000dc61  lea     rcx, [rdi+58h]
0x18000dc65  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x18000dc6a  lea     rcx, [rdi+60h]
0x18000dc6e  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x18000dc73  lea     rcx, [rdi+68h]
0x18000dc77  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x18000dc7c  lea     rcx, [rdi+70h]
0x18000dc80  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x18000dc85  mov     byte ptr [rdi+4Ch], 0
0x18000dc89  mov     rcx, rsi; pSid
0x18000dc8c  call    cs:__imp_IsValidSid
0x18000dc93  nop     dword ptr [rax+rax+00h]
0x18000dc98  test    eax, eax
0x18000dc9a  jz      short loc_18000DD04
0x18000dc9c  mov     rcx, rsi; pSid
0x18000dc9f  call    cs:__imp_GetLengthSid
0x18000dca6  nop     dword ptr [rax+rax+00h]
0x18000dcab  cmp     eax, 44h ; 'D'
0x18000dcae  ja      short loc_18000DD04
0x18000dcb0  mov     byte ptr [rdi+4Ch], 1
0x18000dcb4  mov     r8, rsi; pSourceSid
0x18000dcb7  mov     rdx, r14; pDestinationSid
0x18000dcba  mov     ecx, eax; nDestinationSidLength
0x18000dcbc  call    cs:__imp_CopySid
0x18000dcc3  nop     dword ptr [rax+rax+00h]
0x18000dcc8  test    eax, eax
0x18000dcca  jz      short loc_18000DCF3
0x18000dccc  mov     dword ptr [rdi+50h], 8
0x18000dcd3  jmp     short loc_18000DCE7
0x18000dcd5  mov     rcx, rbx; Block
0x18000dcd8  mov     rbx, [rbx]
0x18000dcdb  call    cs:__imp_free
0x18000dce2  nop     dword ptr [rax+rax+00h]
0x18000dce7  test    rbx, rbx
0x18000dcea  jnz     short loc_18000DCD5
0x18000dcec  mov     al, 1
0x18000dcee  jmp     loc_18000DBF0
0x18000dcf3  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000dcf8  mov     byte ptr [rdi+4Ch], 0
0x18000dcfc  mov     ecx, eax; int
0x18000dcfe  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000dd04  mov     ecx, 80070057h; int
0x18000dd09  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
