# LocationCallerInfoHelper::ImpersonateAndGetUserSid(ATL::CSid &)

- ea: `0x1800c157c`
- end: `0x1800c1666`
- name: `?ImpersonateAndGetUserSid@LocationCallerInfoHelper@@SAJAEAVCSid@ATL@@@Z`
- size: `234`
- prototype: `__int64 __fastcall(struct ATL::CSid *)`
- caller_count: `8`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180086910`
- `0x1800a5d80`
- `0x1800c2190`
- `0x1800c22c0`
- `0x1800c28e0`
- `0x1800c2a80`
- `0x1800c2c40`
- `0x1800c2ea0`

## callees

- `0x180018228`
- `0x18001e170`
- `0x18001f09c`
- `0x1800a98c0`
- `0x1800c157c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800c15c1`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800c15c1`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800c15f6`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800c1626`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800c1637`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800c15f6`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800c1626`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800c1637`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall LocationCallerInfoHelper::ImpersonateAndGetUserSid(struct ATL::CSid *a1)
{
  HRESULT v2; // edi
  void **v4; // [rsp+28h] [rbp-50h] BYREF
  __int128 v5; // [rsp+30h] [rbp-48h]
  __int64 v6; // [rsp+40h] [rbp-38h]

  v4 = &ATL::CAccessToken::`vftable';
  v5 = 0;
  v6 = 0;
  v2 = CoImpersonateClient();
  if ( (int)(v2 + 0x80000000) < 0 || v2 == -2147417833 )
  {
    if ( ATL::CAccessToken::GetEffectiveToken((ATL::CAccessToken *)&v4, 8u)
      && ATL::CAccessToken::GetInfoConvert<ATL::CSid,_TOKEN_USER>((__int64)&v4, (__int64)a1) )
    {
      if ( v2 >= 0 )
        CoRevertToSelf();
      v2 = 0;
    }
    else
    {
      if ( v2 >= 0 )
        CoRevertToSelf();
      v2 = -2147467259;
    }
  }
  else if ( v2 >= 0 )
  {
    CoRevertToSelf();
  }
  v4 = &ATL::CAccessToken::`vftable';
  ATL::CAccessToken::Clear((ATL::CAccessToken *)&v4);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800c157c  push    rbx
0x1800c157e  push    rbp
0x1800c157f  push    rsi
0x1800c1580  push    rdi
0x1800c1581  sub     rsp, 58h
0x1800c1585  mov     rax, cs:__security_cookie
0x1800c158c  xor     rax, rsp
0x1800c158f  mov     [rsp+78h+var_30], rax
0x1800c1594  mov     rsi, rcx
0x1800c1597  xorps   xmm0, xmm0
0x1800c159a  movups  [rsp+78h+var_50], xmm0
0x1800c159f  movups  [rsp+78h+var_40], xmm0
0x1800c15a4  lea     rbp, ??_7CAccessToken@ATL@@6B@; const ATL::CAccessToken::`vftable'
0x1800c15ab  mov     qword ptr [rsp+78h+var_50], rbp
0x1800c15b0  movdqu  [rsp+78h+var_50+8], xmm0
0x1800c15b6  mov     qword ptr [rsp+78h+var_40+8], 0
0x1800c15bf  xor     bl, bl
0x1800c15c1  call    cs:__imp_CoImpersonateClient
0x1800c15c7  mov     edi, eax
0x1800c15c9  mov     [rsp+78h+var_54], eax
0x1800c15cd  movzx   ebx, bl
0x1800c15d0  mov     eax, 1
0x1800c15d5  test    edi, edi
0x1800c15d7  cmovns  ebx, eax
0x1800c15da  mov     [rsp+78h+var_58], bl
0x1800c15de  mov     ecx, 80000000h
0x1800c15e3  lea     eax, [rdi+rcx]
0x1800c15e6  test    ecx, eax
0x1800c15e8  jnz     short loc_1800C15FE
0x1800c15ea  cmp     edi, 80010117h
0x1800c15f0  jz      short loc_1800C15FE
0x1800c15f2  test    bl, bl
0x1800c15f4  jz      short loc_1800C163F
0x1800c15f6  call    cs:__imp_CoRevertToSelf
0x1800c15fc  jmp     short loc_1800C163F
0x1800c15fe  mov     edx, 8; unsigned int
0x1800c1603  lea     rcx, [rsp+78h+var_50]; this
0x1800c1608  call    ?GetEffectiveToken@CAccessToken@ATL@@QEAA_NK@Z; ATL::CAccessToken::GetEffectiveToken(ulong)
0x1800c160d  test    al, al
0x1800c160f  jz      short loc_1800C1622
0x1800c1611  mov     rdx, rsi
0x1800c1614  lea     rcx, [rsp+78h+var_50]
0x1800c1619  call    ??$GetInfoConvert@VCSid@ATL@@U_TOKEN_USER@@@CAccessToken@ATL@@IEBA_NPEAVCSid@1@W4_TOKEN_INFORMATION_CLASS@@PEAU_TOKEN_USER@@@Z; ATL::CAccessToken::GetInfoConvert<ATL::CSid,_TOKEN_USER>(ATL::CSid *,_TOKEN_INFORMATION_CLASS,_TOKEN_USER *)
0x1800c161e  test    al, al
0x1800c1620  jnz     short loc_1800C1633
0x1800c1622  test    bl, bl
0x1800c1624  jz      short loc_1800C162C
0x1800c1626  call    cs:__imp_CoRevertToSelf
0x1800c162c  mov     edi, 80004005h
0x1800c1631  jmp     short loc_1800C163F
0x1800c1633  test    bl, bl
0x1800c1635  jz      short loc_1800C163D
0x1800c1637  call    cs:__imp_CoRevertToSelf
0x1800c163d  xor     edi, edi
0x1800c163f  mov     qword ptr [rsp+78h+var_50], rbp
0x1800c1644  lea     rcx, [rsp+78h+var_50]; this
0x1800c1649  call    ?Clear@CAccessToken@ATL@@MEAAXXZ; ATL::CAccessToken::Clear(void)
0x1800c164e  mov     eax, edi
0x1800c1650  mov     rcx, [rsp+78h+var_30]
0x1800c1655  xor     rcx, rsp; StackCookie
0x1800c1658  call    __security_check_cookie
0x1800c165d  add     rsp, 58h
0x1800c1661  pop     rdi
0x1800c1662  pop     rsi
0x1800c1663  pop     rbp
0x1800c1664  pop     rbx
0x1800c1665  retn
```
