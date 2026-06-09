# Csl::_anonymous_namespace_::ConvertAccountNameToStringSid

- ea: `0x180023b1c`
- end: `0x180023d70`
- name: `Csl::_anonymous_namespace_::ConvertAccountNameToStringSid`
- size: `596`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800239d0`

## callees

- `0x180002534`
- `0x180002c48`
- `0x180002f1c`
- `0x1800045e4`
- `0x180007b2c`
- `0x180007b4c`
- `0x18000af30`
- `0x180023b1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023b76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023b76`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023cbc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023d19`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023d52`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023cbc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023d19`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023d52`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023bb7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023bb7`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180023b6a`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180023c4d`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180023b6a`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180023c4d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180023c8c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180023c8c`

## string_xrefs

- `0x180023b8f`: `onecore\base\gendrv\silos\csl\lib\cslsecurity.cpp`
- `0x180023bcf`: `onecore\base\gendrv\silos\csl\lib\cslsecurity.cpp`
- `0x180023c61`: `onecore\base\gendrv\silos\csl\lib\cslsecurity.cpp`
- `0x180023ca0`: `onecore\base\gendrv\silos\csl\lib\cslsecurity.cpp`
- `0x180023cf5`: `onecore\base\gendrv\silos\csl\lib\cslsecurity.cpp`
- `0x180023d36`: `onecore\base\gendrv\silos\csl\lib\cslsecurity.cpp`

## pseudocode

```c
__int64 __fastcall Csl::_anonymous_namespace_::ConvertAccountNameToStringSid(__int64 a1, __int64 a2)
{
  DWORD LastError; // eax
  HLOCAL v5; // rbx
  const char *v6; // r9
  unsigned __int64 v7; // rdi
  unsigned __int64 v8; // r14
  void *v9; // rax
  void *ReferencedDomainName; // rsi
  const char *v11; // r9
  const struct std::nothrow_t *v12; // rdx
  unsigned int v13; // edi
  const char *v14; // r9
  const struct std::nothrow_t *v15; // rdx
  LPWSTR StringSid; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]
  DWORD cchReferencedDomainName; // [rsp+90h] [rbp+40h] BYREF
  int v19; // [rsp+94h] [rbp+44h]
  DWORD cbSid; // [rsp+A0h] [rbp+50h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+A8h] [rbp+58h] BYREF

  v19 = HIDWORD(a1);
  cbSid = 0;
  cchReferencedDomainName = 0;
  peUse = 0;
  LookupAccountNameW(0, L"WDAGUtilityAccount", 0, &cbSid, 0, &cchReferencedDomainName, &peUse);
  LastError = GetLastError();
  if ( LastError == 122 )
  {
    v5 = LocalAlloc(0x40u, cbSid);
    if ( !v5 )
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0xD2,
               (int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslsecurity.cpp",
               v6);
    v7 = -1;
    v8 = 2LL * cchReferencedDomainName;
    if ( !is_mul_ok(cchReferencedDomainName, 2u) )
      v8 = -1;
    v9 = operator new[](v8, (const struct std::nothrow_t *)&std::nothrow);
    ReferencedDomainName = v9;
    if ( v9 )
    {
      memset_0(v9, 0, v8);
      if ( LookupAccountNameW(
             0,
             L"WDAGUtilityAccount",
             v5,
             &cbSid,
             (LPWSTR)ReferencedDomainName,
             &cchReferencedDomainName,
             &peUse) )
      {
        StringSid = 0;
        if ( ConvertSidToStringSidW(v5, &StringSid) )
        {
          if ( StringSid )
          {
            do
              ++v7;
            while ( StringSid[v7] );
          }
          else
          {
            v7 = 0;
          }
          if ( utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                 a2,
                 StringSid,
                 v7) )
          {
            if ( StringSid )
              LocalFree(StringSid);
            operator delete(ReferencedDomainName, v15);
            v13 = 0;
            goto LABEL_27;
          }
          v13 = -2147024882;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xE4,
            (int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslsecurity.cpp",
            (const char *)0x8007000ELL);
        }
        else
        {
          v13 = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xE2,
                  (int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslsecurity.cpp",
                  v14);
        }
        if ( StringSid )
          LocalFree(StringSid);
      }
      else
      {
        v13 = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0xDE,
                (int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslsecurity.cpp",
                v11);
      }
      operator delete(ReferencedDomainName, v12);
    }
    else
    {
      v13 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD5,
        (int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslsecurity.cpp",
        (const char *)0x8007000ELL);
    }
LABEL_27:
    LocalFree(v5);
    return v13;
  }
  if ( LastError )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0xCE,
             (int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslsecurity.cpp",
             (const char *)LastError);
  else
    return 0;
}

```

## disassembly

```asm
0x180023b1c  mov     r11, rsp
0x180023b1f  mov     [r11+8], rcx
0x180023b23  push    rbp
0x180023b24  push    rbx
0x180023b25  push    rsi
0x180023b26  push    rdi
0x180023b27  push    r12
0x180023b29  push    r14
0x180023b2b  push    r15
0x180023b2d  mov     rbp, rsp
0x180023b30  sub     rsp, 50h
0x180023b34  xor     r12d, r12d
0x180023b37  lea     rax, [rbp+arg_18]
0x180023b3b  mov     [r11-58h], rax
0x180023b3f  lea     r9, [rbp+cbSid]; cbSid
0x180023b43  lea     rax, [rbp+arg_0]
0x180023b47  mov     [rbp+cbSid], r12d
0x180023b4b  mov     r15, rdx
0x180023b4e  mov     [r11-60h], rax
0x180023b52  xor     r8d, r8d; Sid
0x180023b55  mov     [r11-68h], r12
0x180023b59  lea     rdx, AccountName; "WDAGUtilityAccount"
0x180023b60  mov     [rbp+arg_0], r12d
0x180023b64  xor     ecx, ecx; lpSystemName
0x180023b66  mov     [rbp+arg_18], r12d
0x180023b6a  call    cs:__imp_LookupAccountNameW
0x180023b71  nop     dword ptr [rax+rax+00h]
0x180023b76  call    cs:__imp_GetLastError
0x180023b7d  nop     dword ptr [rax+rax+00h]
0x180023b82  cmp     eax, 7Ah ; 'z'
0x180023b85  jz      short loc_180023BAF
0x180023b87  test    eax, eax
0x180023b89  jz      short loc_180023BA8
0x180023b8b  mov     rcx, [rbp+38h]; this
0x180023b8f  lea     r8, aOnecoreBaseGen_11; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x180023b96  mov     r9d, eax; char *
0x180023b99  mov     edx, 0CEh; void *
0x180023b9e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180023ba3  jmp     loc_180023D60
0x180023ba8  xor     eax, eax
0x180023baa  jmp     loc_180023D60
0x180023baf  mov     edx, [rbp+cbSid]; uBytes
0x180023bb2  mov     ecx, 40h ; '@'; uFlags
0x180023bb7  call    cs:__imp_LocalAlloc
0x180023bbe  nop     dword ptr [rax+rax+00h]
0x180023bc3  mov     rbx, rax
0x180023bc6  test    rax, rax
0x180023bc9  jnz     short loc_180023BE5
0x180023bcb  mov     rcx, [rbp+38h]; this
0x180023bcf  lea     r8, aOnecoreBaseGen_11; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x180023bd6  mov     edx, 0D2h; void *
0x180023bdb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180023be0  jmp     loc_180023D60
0x180023be5  mov     ecx, [rbp+arg_0]
0x180023be8  mov     eax, 2
0x180023bed  mul     rcx
0x180023bf0  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180023bf7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180023bfe  mov     r14, rax
0x180023c01  cmovb   r14, rdi
0x180023c05  mov     rcx, r14; unsigned __int64
0x180023c08  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180023c0d  mov     rsi, rax
0x180023c10  test    rax, rax
0x180023c13  jz      loc_180023D32
0x180023c19  mov     r8, r14; Size
0x180023c1c  xor     edx, edx; Val
0x180023c1e  mov     rcx, rax; void *
0x180023c21  call    memset_0
0x180023c26  lea     rax, [rbp+arg_18]
0x180023c2a  mov     r8, rbx; Sid
0x180023c2d  mov     [rsp+50h+peUse], rax; peUse
0x180023c32  lea     r9, [rbp+cbSid]; cbSid
0x180023c36  lea     rax, [rbp+arg_0]
0x180023c3a  xor     ecx, ecx; lpSystemName
0x180023c3c  mov     [rsp+50h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180023c41  lea     rdx, AccountName; "WDAGUtilityAccount"
0x180023c48  mov     [rsp+50h+ReferencedDomainName], rsi; int
0x180023c4d  call    cs:__imp_LookupAccountNameW
0x180023c54  nop     dword ptr [rax+rax+00h]
0x180023c59  test    eax, eax
0x180023c5b  jnz     short loc_180023C81
0x180023c5d  mov     rcx, [rbp+38h]; this
0x180023c61  lea     r8, aOnecoreBaseGen_11; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x180023c68  mov     edx, 0DEh; void *
0x180023c6d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180023c72  mov     edi, eax
0x180023c74  mov     rcx, rsi; void *
0x180023c77  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180023c7c  jmp     loc_180023D4F
0x180023c81  lea     rdx, [rbp+StringSid]; StringSid
0x180023c85  mov     [rbp+StringSid], r12
0x180023c89  mov     rcx, rbx; Sid
0x180023c8c  call    cs:__imp_ConvertSidToStringSidW
0x180023c93  nop     dword ptr [rax+rax+00h]
0x180023c98  test    eax, eax
0x180023c9a  jnz     short loc_180023CCA
0x180023c9c  mov     rcx, [rbp+38h]; this
0x180023ca0  lea     r8, aOnecoreBaseGen_11; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x180023ca7  mov     edx, 0E2h; void *
0x180023cac  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180023cb1  mov     edi, eax
0x180023cb3  mov     rcx, [rbp+StringSid]; hMem
0x180023cb7  test    rcx, rcx
0x180023cba  jz      short loc_180023C74
0x180023cbc  call    cs:__imp_LocalFree
0x180023cc3  nop     dword ptr [rax+rax+00h]
0x180023cc8  jmp     short loc_180023C74
0x180023cca  mov     rdx, [rbp+StringSid]
0x180023cce  test    rdx, rdx
0x180023cd1  jz      short loc_180023CDF
0x180023cd3  inc     rdi
0x180023cd6  cmp     [rdx+rdi*2], r12w
0x180023cdb  jnz     short loc_180023CD3
0x180023cdd  jmp     short loc_180023CE2
0x180023cdf  mov     rdi, r12
0x180023ce2  mov     r8, rdi
0x180023ce5  mov     rcx, r15
0x180023ce8  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180023ced  test    al, al
0x180023cef  jnz     short loc_180023D10
0x180023cf1  mov     rcx, [rbp+38h]; this
0x180023cf5  lea     r8, aOnecoreBaseGen_11; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x180023cfc  mov     edi, 8007000Eh
0x180023d01  mov     edx, 0E4h; void *
0x180023d06  mov     r9d, edi; char *
0x180023d09  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023d0e  jmp     short loc_180023CB3
0x180023d10  mov     rcx, [rbp+StringSid]; hMem
0x180023d14  test    rcx, rcx
0x180023d17  jz      short loc_180023D25
0x180023d19  call    cs:__imp_LocalFree
0x180023d20  nop     dword ptr [rax+rax+00h]
0x180023d25  mov     rcx, rsi; void *
0x180023d28  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180023d2d  mov     edi, r12d
0x180023d30  jmp     short loc_180023D4F
0x180023d32  mov     rcx, [rbp+38h]; this
0x180023d36  lea     r8, aOnecoreBaseGen_11; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x180023d3d  mov     edi, 8007000Eh
0x180023d42  mov     edx, 0D5h; void *
0x180023d47  mov     r9d, edi; char *
0x180023d4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023d4f  mov     rcx, rbx; hMem
0x180023d52  call    cs:__imp_LocalFree
0x180023d59  nop     dword ptr [rax+rax+00h]
0x180023d5e  mov     eax, edi
0x180023d60  add     rsp, 50h
0x180023d64  pop     r15
0x180023d66  pop     r14
0x180023d68  pop     r12
0x180023d6a  pop     rdi
0x180023d6b  pop     rsi
0x180023d6c  pop     rbx
0x180023d6d  pop     rbp
0x180023d6e  retn
```
