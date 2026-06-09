# TsSessionRefreshUserSid(TSSession *)

- ea: `0x180015910`
- end: `0x180015d38`
- name: `?TsSessionRefreshUserSid@@YAJPEAVTSSession@@@Z`
- size: `1064`
- prototype: `__int64 __fastcall(struct TSSession *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180028a44`

## callees

- `0x18000a384`
- `0x18000bbb0`
- `0x1800109d0`
- `0x180015064`
- `0x180015910`
- `0x180015d40`
- `0x18001a3fc`
- `0x18001ada0`
- `0x18002ac98`
- `0x18002acfc`
- `0x180031960`
- `0x1800327e0`
- `0x1800327f8`
- `0x180043114`
- `0x180048920`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180015a66`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180015ad0`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180015a66`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180015ad0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800159f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800159f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015c8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015ca8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015c8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015ca8`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180015bd3`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180015bd3`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180015bbb`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180015bbb`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180015b90`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180015b90`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180015c52`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180015c52`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x1800159ec`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180015b0d`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x1800159ec`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180015b0d`

## pseudocode

```c
__int64 __fastcall TsSessionRefreshUserSid(struct TSSession *a1)
{
  __int64 v1; // rax
  unsigned __int16 *v3; // r14
  unsigned int v4; // ebx
  __int64 v5; // rdx
  BOOL v7; // r15d
  const char *v8; // r9
  size_t v9; // rcx
  __int64 v10; // rax
  void *v11; // rsp
  DWORD *p_cchReferencedDomainName; // rdi
  DWORD *v13; // rax
  unsigned __int64 v14; // rcx
  unsigned __int64 v15; // rdx
  __int64 v16; // rax
  void *v17; // rsp
  DWORD *v18; // rbx
  DWORD *v19; // rax
  PSID *v20; // rdi
  void *v21; // rdx
  unsigned __int64 LengthSid; // r15
  void *v23; // rax
  void *v24; // r14
  PSID v25; // rcx
  _BYTE v26[32]; // [rsp+0h] [rbp-40h] BYREF
  LPWSTR ReferencedDomainName; // [rsp+20h] [rbp-20h]
  DWORD cchReferencedDomainName; // [rsp+40h] [rbp+0h] BYREF
  DWORD cbSid; // [rsp+44h] [rbp+4h] BYREF
  LPWSTR StringSid; // [rsp+48h] [rbp+8h] BYREF
  void *v31; // [rsp+50h] [rbp+10h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+58h] [rbp+18h] BYREF
  WCHAR v33[24]; // [rsp+60h] [rbp+20h] BYREF
  unsigned __int16 v34[48]; // [rsp+90h] [rbp+50h] BYREF
  _BYTE Sid[256]; // [rsp+F0h] [rbp+B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+1E8h]

  v1 = *((_QWORD *)a1 + 3);
  v3 = (unsigned __int16 *)(v1 + 130);
  if ( *(_WORD *)(v1 + 96) )
  {
    ReferencedDomainName = (LPWSTR)(v1 + 130);
    v4 = StringCchPrintfW(v34, 0x2Fu, L"%s\\%s");
    if ( (v4 & 0x80000000) != 0 )
    {
      v5 = 629;
LABEL_4:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v5,
        (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\ts.cpp",
        (const char *)v4,
        (int)ReferencedDomainName);
      return v4;
    }
    v3 = v34;
  }
  if ( !*v3 )
  {
    *((_BYTE *)a1 + 1092) = 1;
    ResetUserSettings(a1);
    return *((_BYTE *)a1 + 1092) == 0 ? 0x80070490 : 0;
  }
  cbSid = 256;
  cchReferencedDomainName = 17;
  peUse = 0;
  v7 = LookupAccountNameW(0, v3, Sid, &cbSid, v33, &cchReferencedDomainName, &peUse);
  if ( GetLastError() == 122 )
  {
    v9 = (2LL * (cchReferencedDomainName + 1) + 16)
       & -(__int64)(2 * (unsigned __int64)(cchReferencedDomainName + 1) < 2
                                                                        * (unsigned __int64)(cchReferencedDomainName + 1)
                                                                        + 16);
    if ( !v9 )
      goto LABEL_31;
    if ( v9 > 0x400 )
    {
      v13 = (DWORD *)malloc(v9);
      p_cchReferencedDomainName = v13;
      if ( !v13 )
        goto LABEL_18;
      *v13 = 56797;
    }
    else
    {
      v10 = v9 + 15;
      if ( v9 + 15 < v9 )
        v10 = 0xFFFFFFFFFFFFFF0LL;
      v11 = alloca(v10 & 0xFFFFFFFFFFFFFFF0uLL);
      p_cchReferencedDomainName = &cchReferencedDomainName;
      if ( v26 == (_BYTE *)-64LL )
        goto LABEL_31;
      cchReferencedDomainName = 52428;
    }
    p_cchReferencedDomainName += 4;
LABEL_18:
    if ( p_cchReferencedDomainName )
    {
      v14 = cbSid + 16LL;
      v15 = v14 & -(__int64)(cbSid < v14);
      if ( !v15 )
        goto LABEL_30;
      if ( v15 > 0x400 )
      {
        v19 = (DWORD *)malloc(v14 & -(__int64)(cbSid < v14));
        v18 = v19;
        if ( !v19 )
          goto LABEL_28;
        *v19 = 56797;
      }
      else
      {
        v16 = v15 + 15;
        if ( v15 + 15 < v15 )
          v16 = 0xFFFFFFFFFFFFFF0LL;
        v17 = alloca(v16 & 0xFFFFFFFFFFFFFFF0uLL);
        v18 = &cchReferencedDomainName;
        if ( v26 == (_BYTE *)-64LL )
          goto LABEL_30;
        cchReferencedDomainName = 52428;
      }
      v18 += 4;
LABEL_28:
      if ( v18 )
      {
        v7 = LookupAccountNameW(0, v3, v18, &cbSid, (LPWSTR)p_cchReferencedDomainName, &cchReferencedDomainName, &peUse);
        freea(v18);
        freea(p_cchReferencedDomainName);
        goto LABEL_33;
      }
LABEL_30:
      v4 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x28B,
        (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\ts.cpp",
        (const char *)0x8007000ELL,
        (int)ReferencedDomainName);
      freea(p_cchReferencedDomainName);
      return v4;
    }
LABEL_31:
    v4 = -2147024882;
    v5 = 648;
    goto LABEL_4;
  }
  v18 = (DWORD *)Sid;
LABEL_33:
  if ( !v7 )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x290,
             (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\ts.cpp",
             v8);
  if ( !IsValidSid(v18) )
  {
    v4 = -2147024809;
    v5 = 658;
    goto LABEL_4;
  }
  v20 = (PSID *)((char *)a1 + 1096);
  v21 = (void *)*((_QWORD *)a1 + 137);
  if ( !v21 || !EqualSid(v18, v21) )
  {
    *((_BYTE *)a1 + 1092) = 0;
    LengthSid = GetLengthSid(v18);
    v23 = operator new(LengthSid);
    v24 = v23;
    if ( !v23 )
    {
      v4 = -2147024882;
      v31 = 0;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x29B,
        (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\ts.cpp",
        (const char *)0x8007000ELL,
        (int)ReferencedDomainName);
LABEL_52:
      Microsoft::WRL::Details::MakeAllocator<CAudioSessionPropertyStore>::~MakeAllocator<CAudioSessionPropertyStore>(&v31);
      return v4;
    }
    memset_0(v23, 0, (unsigned int)LengthSid);
    v31 = v24;
    memcpy_0(v24, v18, (unsigned int)LengthSid);
    if ( v20 != &v31 )
    {
      v25 = *v20;
      v31 = 0;
      *v20 = v24;
      if ( v25 )
        operator delete(v25);
    }
    StringSid = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      (char *)a1 + 1104,
      0);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &StringSid,
      0);
    if ( ConvertSidToStringSidW(*v20, &StringSid) )
    {
      if ( !StringSid )
      {
        v4 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2A4,
          (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\ts.cpp",
          (const char *)0x8007000ELL,
          (int)ReferencedDomainName);
        if ( StringSid )
          CoTaskMemFree(StringSid);
        goto LABEL_52;
      }
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
        (char *)a1 + 1104,
        &StringSid);
    }
    if ( StringSid )
      CoTaskMemFree(StringSid);
    Microsoft::WRL::Details::MakeAllocator<CAudioSessionPropertyStore>::~MakeAllocator<CAudioSessionPropertyStore>(&v31);
  }
  return *((_BYTE *)a1 + 1092) == 0 ? 0x80070490 : 0;
}

```

## disassembly

```asm
0x180015910  push    rbp
0x180015912  push    rdi
0x180015913  push    r12
0x180015915  push    r14
0x180015917  push    r15
0x180015919  sub     rsp, 200h
0x180015920  lea     rbp, [rsp+40h]
0x180015925  mov     [rbp+1E0h+arg_8], rbx
0x18001592c  mov     [rbp+1E0h+arg_10], rsi
0x180015933  mov     rax, cs:__security_cookie
0x18001593a  xor     rax, rbp
0x18001593d  mov     [rbp+1E0h+var_30], rax
0x180015944  mov     rax, [rcx+18h]
0x180015948  xor     r12d, r12d
0x18001594b  mov     rsi, rcx
0x18001594e  lea     r9, [rax+60h]
0x180015952  lea     r14, [rax+82h]
0x180015959  cmp     [r9], r12w
0x18001595d  jz      short loc_1800159A5
0x18001595f  lea     r8, aSS; "%s\\%s"
0x180015966  mov     [rsp+220h+ReferencedDomainName], r14; int
0x18001596b  lea     edx, [r12+2Fh]; unsigned __int64
0x180015970  lea     rcx, [rbp+1E0h+var_190]; unsigned __int16 *
0x180015974  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180015979  mov     ebx, eax
0x18001597b  test    eax, eax
0x18001597d  jns     short loc_1800159A1
0x18001597f  mov     edx, 275h; void *
0x180015984  mov     rcx, [rbp+1E8h]; this
0x18001598b  lea     r8, aClientcoreMult_10; "clientcore\\multimedia\\audiocore\\serv"...
0x180015992  mov     r9d, ebx; char *
0x180015995  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001599a  mov     eax, ebx
0x18001599c  jmp     loc_180015D0B
0x1800159a1  lea     r14, [rbp+1E0h+var_190]
0x1800159a5  cmp     [r14], r12w
0x1800159a9  jz      loc_180015CEB
0x1800159af  lea     rax, [rbp+1E0h+var_1C8]
0x1800159b3  mov     [rbp+1E0h+cbSid], 100h
0x1800159ba  mov     [rsp+220h+peUse], rax; peUse
0x1800159bf  lea     r9, [rbp+1E0h+cbSid]; cbSid
0x1800159c3  lea     rax, [rbp+1E0h+var_1E0]
0x1800159c7  mov     [rbp+1E0h+var_1E0], 11h
0x1800159ce  mov     [rsp+220h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800159d3  lea     r8, [rbp+1E0h+Sid]; Sid
0x1800159da  lea     rax, [rbp+1E0h+var_1C0]
0x1800159de  mov     [rbp+1E0h+var_1C8], r12d
0x1800159e2  mov     rdx, r14; lpAccountName
0x1800159e5  mov     [rsp+220h+ReferencedDomainName], rax; int
0x1800159ea  xor     ecx, ecx; lpSystemName
0x1800159ec  call    cs:__imp_LookupAccountNameW
0x1800159f2  mov     r15d, eax
0x1800159f5  call    cs:__imp_GetLastError
0x1800159fb  cmp     eax, 7Ah ; 'z'
0x1800159fe  jnz     loc_180015B64
0x180015a04  mov     ecx, [rbp+1E0h+var_1E0]
0x180015a07  inc     ecx
0x180015a09  add     rcx, rcx
0x180015a0c  lea     rax, [rcx+10h]
0x180015a10  cmp     rcx, rax
0x180015a13  sbb     rcx, rcx
0x180015a16  and     rcx, rax; Size
0x180015a19  jz      loc_180015B55
0x180015a1f  mov     rbx, 0FFFFFFFFFFFFFF0h
0x180015a29  mov     r15d, 0DDDDh
0x180015a2f  cmp     rcx, 400h
0x180015a36  ja      short loc_180015A66
0x180015a38  lea     rax, [rcx+0Fh]
0x180015a3c  cmp     rax, rcx
0x180015a3f  ja      short loc_180015A44
0x180015a41  mov     rax, rbx
0x180015a44  and     rax, 0FFFFFFFFFFFFFFF0h
0x180015a48  call    _alloca_probe
0x180015a4d  sub     rsp, rax
0x180015a50  lea     rdi, [rsp+220h+var_1E0]
0x180015a55  test    rdi, rdi
0x180015a58  jz      loc_180015B55
0x180015a5e  mov     dword ptr [rdi], 0CCCCh
0x180015a64  jmp     short loc_180015A77
0x180015a66  call    cs:__imp_malloc
0x180015a6c  mov     rdi, rax
0x180015a6f  test    rax, rax
0x180015a72  jz      short loc_180015A7B
0x180015a74  mov     [rax], r15d
0x180015a77  add     rdi, 10h
0x180015a7b  test    rdi, rdi
0x180015a7e  jz      loc_180015B55
0x180015a84  mov     eax, [rbp+1E0h+cbSid]
0x180015a87  lea     rcx, [rax+10h]
0x180015a8b  cmp     rax, rcx
0x180015a8e  sbb     rdx, rdx
0x180015a91  and     rdx, rcx
0x180015a94  jz      loc_180015B28
0x180015a9a  cmp     rdx, 400h
0x180015aa1  ja      short loc_180015ACD
0x180015aa3  lea     rax, [rdx+0Fh]
0x180015aa7  cmp     rax, rdx
0x180015aaa  ja      short loc_180015AAF
0x180015aac  mov     rax, rbx
0x180015aaf  and     rax, 0FFFFFFFFFFFFFFF0h
0x180015ab3  call    _alloca_probe
0x180015ab8  sub     rsp, rax
0x180015abb  lea     rbx, [rsp+220h+var_1E0]
0x180015ac0  test    rbx, rbx
0x180015ac3  jz      short loc_180015B28
0x180015ac5  mov     dword ptr [rbx], 0CCCCh
0x180015acb  jmp     short loc_180015AE1
0x180015acd  mov     rcx, rdx; Size
0x180015ad0  call    cs:__imp_malloc
0x180015ad6  mov     rbx, rax
0x180015ad9  test    rax, rax
0x180015adc  jz      short loc_180015AE5
0x180015ade  mov     [rax], r15d
0x180015ae1  add     rbx, 10h
0x180015ae5  test    rbx, rbx
0x180015ae8  jz      short loc_180015B28
0x180015aea  lea     rax, [rbp+1E0h+var_1C8]
0x180015aee  mov     r8, rbx; Sid
0x180015af1  mov     [rsp+220h+peUse], rax; peUse
0x180015af6  lea     r9, [rbp+1E0h+cbSid]; cbSid
0x180015afa  lea     rax, [rbp+1E0h+var_1E0]
0x180015afe  mov     rdx, r14; lpAccountName
0x180015b01  mov     [rsp+220h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180015b06  xor     ecx, ecx; lpSystemName
0x180015b08  mov     [rsp+220h+ReferencedDomainName], rdi; ReferencedDomainName
0x180015b0d  call    cs:__imp_LookupAccountNameW
0x180015b13  mov     rcx, rbx; Memory
0x180015b16  mov     r15d, eax
0x180015b19  call    _freea
0x180015b1e  mov     rcx, rdi; Memory
0x180015b21  call    _freea
0x180015b26  jmp     short loc_180015B6B
0x180015b28  mov     rcx, [rbp+1E8h]; this
0x180015b2f  lea     r8, aClientcoreMult_10; "clientcore\\multimedia\\audiocore\\serv"...
0x180015b36  mov     ebx, 8007000Eh
0x180015b3b  mov     edx, 28Bh; void *
0x180015b40  mov     r9d, ebx; char *
0x180015b43  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015b48  mov     rcx, rdi; Memory
0x180015b4b  call    _freea
0x180015b50  jmp     loc_18001599A
0x180015b55  mov     ebx, 8007000Eh
0x180015b5a  mov     edx, 288h
0x180015b5f  jmp     loc_180015984
0x180015b64  lea     rbx, [rbp+1E0h+Sid]
0x180015b6b  test    r15d, r15d
0x180015b6e  jnz     short loc_180015B8D
0x180015b70  mov     rcx, [rbp+1E8h]; this
0x180015b77  lea     r8, aClientcoreMult_10; "clientcore\\multimedia\\audiocore\\serv"...
0x180015b7e  mov     edx, 290h; void *
0x180015b83  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180015b88  jmp     loc_180015D0B
0x180015b8d  mov     rcx, rbx; pSid
0x180015b90  call    cs:__imp_IsValidSid
0x180015b96  test    eax, eax
0x180015b98  jnz     short loc_180015BA9
0x180015b9a  mov     ebx, 80070057h
0x180015b9f  mov     edx, 292h
0x180015ba4  jmp     loc_180015984
0x180015ba9  lea     rdi, [rsi+448h]
0x180015bb0  mov     rdx, [rdi]; pSid2
0x180015bb3  test    rdx, rdx
0x180015bb6  jz      short loc_180015BC9
0x180015bb8  mov     rcx, rbx; pSid1
0x180015bbb  call    cs:__imp_EqualSid
0x180015bc1  test    eax, eax
0x180015bc3  jnz     loc_180015CFA
0x180015bc9  mov     rcx, rbx; pSid
0x180015bcc  mov     [rsi+444h], r12b
0x180015bd3  call    cs:__imp_GetLengthSid
0x180015bd9  mov     ecx, eax; unsigned __int64
0x180015bdb  mov     r15d, eax
0x180015bde  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180015be3  mov     r14, rax
0x180015be6  test    rax, rax
0x180015be9  jz      loc_180015CB9
0x180015bef  mov     r8d, r15d; Size
0x180015bf2  xor     edx, edx; Val
0x180015bf4  mov     rcx, rax; void *
0x180015bf7  call    memset_0
0x180015bfc  mov     r8d, r15d; Size
0x180015bff  mov     [rbp+1E0h+var_1D0], r14
0x180015c03  mov     rdx, rbx; Src
0x180015c06  mov     rcx, r14; void *
0x180015c09  call    memcpy_0
0x180015c0e  lea     rax, [rbp+1E0h+var_1D0]
0x180015c12  cmp     rdi, rax
0x180015c15  jz      short loc_180015C2B
0x180015c17  mov     rcx, [rdi]; void *
0x180015c1a  mov     [rbp+1E0h+var_1D0], r12
0x180015c1e  mov     [rdi], r14
0x180015c21  test    rcx, rcx
0x180015c24  jz      short loc_180015C2B
0x180015c26  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180015c2b  lea     rbx, [rsi+450h]
0x180015c32  mov     [rbp+1E0h+StringSid], r12
0x180015c36  mov     rcx, rbx
0x180015c39  xor     edx, edx
0x180015c3b  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180015c40  xor     edx, edx
0x180015c42  lea     rcx, [rbp+1E0h+StringSid]
0x180015c46  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180015c4b  mov     rcx, [rdi]; Sid
0x180015c4e  lea     rdx, [rbp+1E0h+StringSid]; StringSid
0x180015c52  call    cs:__imp_ConvertSidToStringSidW
0x180015c58  test    eax, eax
0x180015c5a  jz      short loc_180015C9F
0x180015c5c  cmp     [rbp+1E0h+StringSid], r12
0x180015c60  jnz     short loc_180015C93
0x180015c62  mov     rcx, [rbp+1E8h]; this
0x180015c69  lea     r8, aClientcoreMult_10; "clientcore\\multimedia\\audiocore\\serv"...
0x180015c70  mov     ebx, 8007000Eh
0x180015c75  mov     edx, 2A4h; void *
0x180015c7a  mov     r9d, ebx; char *
0x180015c7d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015c82  mov     rcx, [rbp+1E0h+StringSid]; pv
0x180015c86  test    rcx, rcx
0x180015c89  jz      short loc_180015CDD
0x180015c8b  call    cs:__imp_CoTaskMemFree
0x180015c91  jmp     short loc_180015CDD
0x180015c93  lea     rdx, [rbp+1E0h+StringSid]
0x180015c97  mov     rcx, rbx
0x180015c9a  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180015c9f  mov     rcx, [rbp+1E0h+StringSid]; pv
0x180015ca3  test    rcx, rcx
0x180015ca6  jz      short loc_180015CAE
0x180015ca8  call    cs:__imp_CoTaskMemFree
0x180015cae  lea     rcx, [rbp+1E0h+var_1D0]
0x180015cb2  call    ??1?$MakeAllocator@VCAudioSessionPropertyStore@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<CAudioSessionPropertyStore>::~MakeAllocator<CAudioSessionPropertyStore>(void)
0x180015cb7  jmp     short loc_180015CFA
0x180015cb9  mov     rcx, [rbp+1E8h]; this
0x180015cc0  lea     r8, aClientcoreMult_10; "clientcore\\multimedia\\audiocore\\serv"...
0x180015cc7  mov     ebx, 8007000Eh
0x180015ccc  mov     [rbp+1E0h+var_1D0], r12
0x180015cd0  mov     r9d, ebx; char *
0x180015cd3  mov     edx, 29Bh; void *
0x180015cd8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015cdd  lea     rcx, [rbp+1E0h+var_1D0]
0x180015ce1  call    ??1?$MakeAllocator@VCAudioSessionPropertyStore@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<CAudioSessionPropertyStore>::~MakeAllocator<CAudioSessionPropertyStore>(void)
0x180015ce6  jmp     loc_18001599A
0x180015ceb  mov     rcx, rsi; struct TSSession *
0x180015cee  mov     byte ptr [rsi+444h], 1
0x180015cf5  call    ?ResetUserSettings@@YAXPEAVTSSession@@@Z; ResetUserSettings(TSSession *)
0x180015cfa  mov     al, [rsi+444h]
0x180015d00  neg     al
0x180015d02  sbb     eax, eax
0x180015d04  not     eax
0x180015d06  and     eax, 80070490h
0x180015d0b  mov     rcx, [rbp+1E0h+var_30]
0x180015d12  xor     rcx, rbp; StackCookie
0x180015d15  call    __security_check_cookie
0x180015d1a  mov     rbx, [rbp+1E0h+arg_8]
0x180015d21  mov     rsi, [rbp+1E0h+arg_10]
0x180015d28  lea     rsp, [rbp+1C0h]
0x180015d2f  pop     r15
0x180015d31  pop     r14
0x180015d33  pop     r12
0x180015d35  pop     rdi
0x180015d36  pop     rbp
0x180015d37  retn
```
