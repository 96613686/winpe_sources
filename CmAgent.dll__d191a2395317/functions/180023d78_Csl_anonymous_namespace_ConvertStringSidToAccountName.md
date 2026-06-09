# Csl::_anonymous_namespace_::ConvertStringSidToAccountName

- ea: `0x180023d78`
- end: `0x180024078`
- name: `Csl::_anonymous_namespace_::ConvertStringSidToAccountName`
- size: `768`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180023844`
- `0x180024080`

## callees

- `0x180002534`
- `0x180002c48`
- `0x180002f1c`
- `0x1800045e4`
- `0x180007b2c`
- `0x180007b4c`
- `0x180009e10`
- `0x18000af30`
- `0x180023d78`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023e1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023e1c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023dcd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023f30`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023ffc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002404d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023dcd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023f30`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023ffc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002404d`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180023e10`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180023ef0`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180023e10`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180023ef0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180023d9f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180023d9f`

## string_xrefs

- `0x180023db3`: `onecore\base\gendrv\silos\csl\lib\cslsecurity.cpp`
- `0x180023e39`: `onecore\base\gendrv\silos\csl\lib\cslsecurity.cpp`
- `0x180023f04`: `onecore\base\gendrv\silos\csl\lib\cslsecurity.cpp`
- `0x180023f79`: `onecore\base\gendrv\silos\csl\lib\cslsecurity.cpp`
- `0x180024010`: `onecore\base\gendrv\silos\csl\lib\cslsecurity.cpp`
- `0x18002402d`: `onecore\base\gendrv\silos\csl\lib\cslsecurity.cpp`

## pseudocode

```c
__int64 __fastcall Csl::_anonymous_namespace_::ConvertStringSidToAccountName(const WCHAR *a1, __int64 a2)
{
  const char *v3; // r9
  unsigned int LastError; // eax
  unsigned int v5; // ebx
  DWORD v7; // eax
  unsigned __int64 v8; // rdi
  unsigned __int64 v9; // rsi
  void *v10; // rax
  void *v11; // rbx
  unsigned __int64 v12; // r14
  void *v13; // rax
  void *ReferencedDomainName; // rsi
  const char *v15; // r9
  unsigned int v16; // edi
  const struct std::nothrow_t *v17; // rdx
  const struct std::nothrow_t *v18; // rdx
  const struct std::nothrow_t *v19; // rdx
  const struct std::nothrow_t *v20; // rdx
  const struct std::nothrow_t *v21; // rdx
  const struct std::nothrow_t *v22; // rdx
  enum _SID_NAME_USE peUse; // [rsp+40h] [rbp-30h] BYREF
  PSID Sid; // [rsp+48h] [rbp-28h] BYREF
  void *v25[2]; // [rsp+50h] [rbp-20h] BYREF
  _WORD v26[8]; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  DWORD cchReferencedDomainName; // [rsp+B0h] [rbp+40h] BYREF
  DWORD cchName; // [rsp+B8h] [rbp+48h] BYREF

  Sid = 0;
  if ( !ConvertStringSidToSidW(a1, &Sid) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x7B,
                  (int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslsecurity.cpp",
                  v3);
LABEL_3:
    v5 = LastError;
    if ( Sid )
      LocalFree(Sid);
    return v5;
  }
  cchName = 0;
  cchReferencedDomainName = 0;
  peUse = 0;
  LookupAccountSidW(0, Sid, 0, &cchName, 0, &cchReferencedDomainName, &peUse);
  v7 = GetLastError();
  if ( v7 != 122 )
  {
    if ( v7 )
    {
      LastError = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0x8C,
                    (int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslsecurity.cpp",
                    (const char *)v7);
      goto LABEL_3;
    }
    goto LABEL_29;
  }
  v8 = -1;
  v9 = 2LL * cchName;
  if ( !is_mul_ok(cchName, 2u) )
    v9 = -1;
  v10 = operator new[](v9, (const struct std::nothrow_t *)&std::nothrow);
  v11 = v10;
  if ( v10 )
  {
    memset_0(v10, 0, v9);
    v12 = 2LL * cchReferencedDomainName;
    if ( !is_mul_ok(cchReferencedDomainName, 2u) )
      v12 = -1;
    v13 = operator new[](v12, (const struct std::nothrow_t *)&std::nothrow);
    ReferencedDomainName = v13;
    if ( v13 )
    {
      memset_0(v13, 0, v12);
      if ( !LookupAccountSidW(
              0,
              Sid,
              (LPWSTR)v11,
              &cchName,
              (LPWSTR)ReferencedDomainName,
              &cchReferencedDomainName,
              &peUse) )
      {
        v16 = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x9B,
                (int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslsecurity.cpp",
                v15);
        operator delete(ReferencedDomainName, v17);
        operator delete(v11, v18);
        if ( Sid )
          LocalFree(Sid);
        return v16;
      }
      v26[0] = 0;
      v25[0] = v26;
      v25[1] = v26;
      do
        ++v8;
      while ( *((_WORD *)v11 + v8) );
      if ( utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
             (__int64)v25,
             v11,
             v8) )
      {
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::operator=(
          a2,
          (__int64)v25);
        if ( v25[0] != v26 )
          operator delete(v25[0], (const struct std::nothrow_t *)&std::nothrow);
        operator delete(ReferencedDomainName, v21);
        operator delete(v11, v22);
LABEL_29:
        if ( Sid )
          LocalFree(Sid);
        return 0;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9E,
        (int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslsecurity.cpp",
        (const char *)0x8007000ELL);
      if ( v25[0] != v26 )
        operator delete(v25[0], (const struct std::nothrow_t *)&std::nothrow);
      operator delete(ReferencedDomainName, v19);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x93,
        (int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslsecurity.cpp",
        (const char *)0x8007000ELL);
    }
    operator delete(v11, v20);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x91,
      (int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslsecurity.cpp",
      (const char *)0x8007000ELL);
  }
  if ( Sid )
    LocalFree(Sid);
  return 2147942414LL;
}

```

## disassembly

```asm
0x180023d78  mov     [rsp-28h+arg_0], rbx
0x180023d7d  mov     [rsp-28h+arg_8], rsi
0x180023d82  push    rbp
0x180023d83  push    rdi
0x180023d84  push    r12
0x180023d86  push    r14
0x180023d88  push    r15
0x180023d8a  mov     rbp, rsp
0x180023d8d  sub     rsp, 70h
0x180023d91  mov     r15, rdx
0x180023d94  xor     r12d, r12d
0x180023d97  lea     rdx, [rbp+Sid]; Sid
0x180023d9b  mov     [rbp+Sid], r12
0x180023d9f  call    cs:__imp_ConvertStringSidToSidW
0x180023da6  nop     dword ptr [rax+rax+00h]
0x180023dab  test    eax, eax
0x180023dad  jnz     short loc_180023DE0
0x180023daf  mov     rcx, [rbp+28h]; this
0x180023db3  lea     r8, aOnecoreBaseGen_11; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x180023dba  lea     edx, [rax+7Bh]; void *
0x180023dbd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180023dc2  mov     rcx, [rbp+Sid]; hMem
0x180023dc6  mov     ebx, eax
0x180023dc8  test    rcx, rcx
0x180023dcb  jz      short loc_180023DD9
0x180023dcd  call    cs:__imp_LocalFree
0x180023dd4  nop     dword ptr [rax+rax+00h]
0x180023dd9  mov     eax, ebx
0x180023ddb  jmp     loc_18002405E
0x180023de0  mov     rdx, [rbp+Sid]; Sid
0x180023de4  lea     rax, [rbp+var_30]
0x180023de8  mov     [rsp+70h+peUse], rax; peUse
0x180023ded  lea     r9, [rbp+cchName]; cchName
0x180023df1  lea     rax, [rbp+arg_10]
0x180023df5  mov     [rbp+cchName], r12d
0x180023df9  mov     [rsp+70h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180023dfe  xor     r8d, r8d; Name
0x180023e01  xor     ecx, ecx; lpSystemName
0x180023e03  mov     [rsp+70h+ReferencedDomainName], r12; int
0x180023e08  mov     [rbp+arg_10], r12d
0x180023e0c  mov     [rbp+var_30], r12d
0x180023e10  call    cs:__imp_LookupAccountSidW
0x180023e17  nop     dword ptr [rax+rax+00h]
0x180023e1c  call    cs:__imp_GetLastError
0x180023e23  nop     dword ptr [rax+rax+00h]
0x180023e28  cmp     eax, 7Ah ; 'z'
0x180023e2b  jz      short loc_180023E52
0x180023e2d  test    eax, eax
0x180023e2f  jz      loc_180023FF3
0x180023e35  mov     rcx, [rbp+28h]; this
0x180023e39  lea     r8, aOnecoreBaseGen_11; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x180023e40  mov     r9d, eax; char *
0x180023e43  mov     edx, 8Ch; void *
0x180023e48  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180023e4d  jmp     loc_180023DC2
0x180023e52  mov     ecx, [rbp+cchName]
0x180023e55  mov     r14d, 2
0x180023e5b  mov     eax, r14d
0x180023e5e  mul     rcx
0x180023e61  lea     rdi, [r14-3]
0x180023e65  mov     rsi, rax
0x180023e68  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180023e6f  cmovb   rsi, rdi
0x180023e73  mov     rcx, rsi; unsigned __int64
0x180023e76  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180023e7b  mov     rbx, rax
0x180023e7e  test    rax, rax
0x180023e81  jz      loc_180024029
0x180023e87  mov     r8, rsi; Size
0x180023e8a  xor     edx, edx; Val
0x180023e8c  mov     rcx, rax; void *
0x180023e8f  call    memset_0
0x180023e94  mov     ecx, [rbp+arg_10]
0x180023e97  mov     eax, r14d
0x180023e9a  mul     rcx
0x180023e9d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180023ea4  mov     r14, rax
0x180023ea7  cmovb   r14, rdi
0x180023eab  mov     rcx, r14; unsigned __int64
0x180023eae  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180023eb3  mov     rsi, rax
0x180023eb6  test    rax, rax
0x180023eb9  jz      loc_18002400C
0x180023ebf  mov     r8, r14; Size
0x180023ec2  xor     edx, edx; Val
0x180023ec4  mov     rcx, rax; void *
0x180023ec7  call    memset_0
0x180023ecc  mov     rdx, [rbp+Sid]; Sid
0x180023ed0  lea     rax, [rbp+var_30]
0x180023ed4  mov     [rsp+70h+peUse], rax; peUse
0x180023ed9  lea     r9, [rbp+cchName]; cchName
0x180023edd  lea     rax, [rbp+arg_10]
0x180023ee1  mov     r8, rbx; Name
0x180023ee4  mov     [rsp+70h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180023ee9  xor     ecx, ecx; lpSystemName
0x180023eeb  mov     [rsp+70h+ReferencedDomainName], rsi; int
0x180023ef0  call    cs:__imp_LookupAccountSidW
0x180023ef7  nop     dword ptr [rax+rax+00h]
0x180023efc  test    eax, eax
0x180023efe  jnz     short loc_180023F43
0x180023f00  mov     rcx, [rbp+28h]; this
0x180023f04  lea     r8, aOnecoreBaseGen_11; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x180023f0b  mov     edx, 9Bh; void *
0x180023f10  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180023f15  mov     rcx, rsi; void *
0x180023f18  mov     edi, eax
0x180023f1a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180023f1f  mov     rcx, rbx; void *
0x180023f22  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180023f27  mov     rcx, [rbp+Sid]; hMem
0x180023f2b  test    rcx, rcx
0x180023f2e  jz      short loc_180023F3C
0x180023f30  call    cs:__imp_LocalFree
0x180023f37  nop     dword ptr [rax+rax+00h]
0x180023f3c  mov     eax, edi
0x180023f3e  jmp     loc_18002405E
0x180023f43  lea     rax, [rbp+var_10]
0x180023f47  mov     [rbp+var_10], r12w
0x180023f4c  mov     [rbp+var_20], rax
0x180023f50  lea     rax, [rbp+var_10]
0x180023f54  mov     [rbp+var_18], rax
0x180023f58  inc     rdi
0x180023f5b  cmp     [rbx+rdi*2], r12w
0x180023f60  jnz     short loc_180023F58
0x180023f62  mov     r8, rdi
0x180023f65  lea     rcx, [rbp+var_20]
0x180023f69  mov     rdx, rbx
0x180023f6c  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180023f71  test    al, al
0x180023f73  jnz     short loc_180023FBE
0x180023f75  mov     rcx, [rbp+28h]; this
0x180023f79  lea     r8, aOnecoreBaseGen_11; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x180023f80  mov     r9d, 8007000Eh; char *
0x180023f86  mov     edx, 9Eh; void *
0x180023f8b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023f90  mov     rcx, [rbp+var_20]; void *
0x180023f94  lea     rax, [rbp+var_10]
0x180023f98  cmp     rcx, rax
0x180023f9b  jz      short loc_180023FA9
0x180023f9d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180023fa4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180023fa9  mov     rcx, rsi; void *
0x180023fac  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180023fb1  mov     rcx, rbx; void *
0x180023fb4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180023fb9  jmp     loc_180024044
0x180023fbe  lea     rdx, [rbp+var_20]
0x180023fc2  mov     rcx, r15
0x180023fc5  call    ??4?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::operator=(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &&)
0x180023fca  mov     rcx, [rbp+var_20]; void *
0x180023fce  lea     rax, [rbp+var_10]
0x180023fd2  cmp     rcx, rax
0x180023fd5  jz      short loc_180023FE3
0x180023fd7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180023fde  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180023fe3  mov     rcx, rsi; void *
0x180023fe6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180023feb  mov     rcx, rbx; void *
0x180023fee  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180023ff3  mov     rcx, [rbp+Sid]; hMem
0x180023ff7  test    rcx, rcx
0x180023ffa  jz      short loc_180024008
0x180023ffc  call    cs:__imp_LocalFree
0x180024003  nop     dword ptr [rax+rax+00h]
0x180024008  xor     eax, eax
0x18002400a  jmp     short loc_18002405E
0x18002400c  mov     rcx, [rbp+28h]; this
0x180024010  lea     r8, aOnecoreBaseGen_11; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x180024017  mov     r9d, 8007000Eh; char *
0x18002401d  mov     edx, 93h; void *
0x180024022  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024027  jmp     short loc_180023FB1
0x180024029  mov     rcx, [rbp+28h]; this
0x18002402d  lea     r8, aOnecoreBaseGen_11; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x180024034  mov     r9d, 8007000Eh; char *
0x18002403a  mov     edx, 91h; void *
0x18002403f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024044  mov     rcx, [rbp+Sid]; hMem
0x180024048  test    rcx, rcx
0x18002404b  jz      short loc_180024059
0x18002404d  call    cs:__imp_LocalFree
0x180024054  nop     dword ptr [rax+rax+00h]
0x180024059  mov     eax, 8007000Eh
0x18002405e  lea     r11, [rsp+70h+var_s0]
0x180024063  mov     rbx, [r11+30h]
0x180024067  mov     rsi, [r11+38h]
0x18002406b  mov     rsp, r11
0x18002406e  pop     r15
0x180024070  pop     r14
0x180024072  pop     r12
0x180024074  pop     rdi
0x180024075  pop     rbp
0x180024076  retn
```
