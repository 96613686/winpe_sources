# LicenseManagerCore::GetLeasesForKey(Microsoft::WRL::ComPtr<ILicenseIdentityContext> const &,Microsoft::WRL::ComPtr<IStoredKeyDocument> const &,Microsoft::WRL::ComPtr<IStoredLeaseDocument>)

- ea: `0x180019efc`
- end: `0x18001a196`
- name: `?GetLeasesForKey@LicenseManagerCore@@AEBA?AV?$vector@V?$ComPtr@UIStoredLeaseDocument@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIStoredLeaseDocument@@@WRL@Microsoft@@@std@@@std@@AEBV?$ComPtr@UILicenseIdentityContext@@@WRL@Microsoft@@AEBV?$ComPtr@UIStoredKeyDocument@@@56@V?$ComPtr@UIStoredLeaseDocument@@@56@@Z`
- size: `666`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180019d00`
- `0x18001a8a0`
- `0x1800579a8`

## callees

- `0x18000b7fc`
- `0x180019efc`
- `0x18001b53c`
- `0x18001d648`
- `0x1800593bc`
- `0x180067954`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001a041`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001a041`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a080`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a091`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a114`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a14e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a080`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a091`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a114`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a14e`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
_QWORD *__fastcall LicenseManagerCore::GetLeasesForKey(__int64 a1, _QWORD *a2, _QWORD *a3, _QWORD *a4, _QWORD **a5)
{
  int v6; // eax
  const WCHAR *v7; // r14
  _QWORD *v8; // rsi
  _QWORD *v9; // r15
  __int64 *v10; // rcx
  __int64 v11; // rax
  int v12; // eax
  int v13; // r12d
  __int64 *v14; // rcx
  __int64 v15; // rax
  int v16; // eax
  _QWORD *v17; // rdx
  __int64 v18; // rdi
  __int64 *v19; // rdx
  unsigned int i; // edi
  __int64 v21; // rcx
  __int64 v22; // rcx
  LPVOID *bIgnoreCase; // [rsp+20h] [rbp-38h]
  __int64 v25; // [rsp+38h] [rbp-20h] BYREF
  LPVOID v26; // [rsp+40h] [rbp-18h]
  int v27; // [rsp+48h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+40h]
  LPCWCH lpString2; // [rsp+A0h] [rbp+48h] BYREF
  _QWORD *v30; // [rsp+A8h] [rbp+50h]
  LPCWCH lpString1; // [rsp+B0h] [rbp+58h] BYREF
  LPVOID pv; // [rsp+B8h] [rbp+60h] BYREF

  v30 = a2;
  v26 = 0;
  v27 = 0;
  LODWORD(lpString2) = 0;
  pv = 0;
  bIgnoreCase = &pv;
  v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, LPCWCH *))(**(_QWORD **)(a1 + 184) + 88LL))(
         *(_QWORD *)(a1 + 184),
         *a4,
         *a3,
         &lpString2);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x679,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\managercore.cpp",
      (const char *)(unsigned int)v6,
      (int)&pv);
  v7 = (const WCHAR *)(unsigned int)lpString2;
  v8 = pv;
  v26 = pv;
  v27 = (int)lpString2;
  lpString1 = 0;
  v9 = a5;
  v10 = *a5;
  if ( *a5 )
  {
    v11 = *v10;
    lpString1 = 0;
    v12 = (*(__int64 (__fastcall **)(__int64 *, LPCWCH *))(v11 + 24))(v10, &lpString1);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x680,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\managercore.cpp",
        (const char *)(unsigned int)v12,
        (int)&pv);
  }
  *a2 = 0;
  a2[1] = 0;
  a2[2] = 0;
  lpString2 = v7;
  if ( (_DWORD)v7 )
    std::vector<Microsoft::WRL::ComPtr<IStoredLeaseDocument>>::_Reallocate<0>(a2, &lpString2);
  v13 = 0;
  if ( (_DWORD)v7 )
  {
    while ( 1 )
    {
      if ( !lpString1 )
        goto LABEL_19;
      lpString2 = 0;
      v14 = (__int64 *)v8[v13];
      v15 = *v14;
      lpString2 = 0;
      v16 = (*(__int64 (__fastcall **)(__int64 *, LPCWCH *))(v15 + 24))(v14, &lpString2);
      if ( v16 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x68A,
          (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\managercore.cpp",
          (const char *)(unsigned int)v16,
          (int)bIgnoreCase);
      if ( CompareStringOrdinal(lpString1, -1, lpString2, -1, 0) != 2 )
        break;
      v17 = (_QWORD *)a2[1];
      if ( v17 == (_QWORD *)a2[2] )
      {
        std::vector<Microsoft::WRL::ComPtr<IStoredLeaseDocument>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<IStoredLeaseDocument> const &>(
          a2,
          v17,
          v9);
      }
      else
      {
        *v17 = *v9;
        Microsoft::WRL::ComPtr<ClipKeyDocument>::InternalAddRef(v17);
        a2[1] += 8LL;
      }
      if ( lpString2 )
        CoTaskMemFree((LPVOID)lpString2);
LABEL_28:
      if ( ++v13 >= (unsigned int)v7 )
        goto LABEL_29;
    }
    if ( lpString2 )
      CoTaskMemFree((LPVOID)lpString2);
LABEL_19:
    v18 = v8[v13];
    v25 = v18;
    if ( v18 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 8LL))(v18);
    v19 = (__int64 *)a2[1];
    if ( v19 == (__int64 *)a2[2] )
    {
      std::vector<Microsoft::WRL::ComPtr<IStoredLeaseDocument>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<IStoredLeaseDocument>>(
        a2,
        v19,
        &v25);
      v18 = v25;
    }
    else
    {
      *v19 = 0;
      if ( v19 != &v25 )
      {
        *v19 = v18;
        v18 = 0;
      }
      a2[1] += 8LL;
    }
    if ( v18 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    goto LABEL_28;
  }
LABEL_29:
  if ( lpString1 )
    CoTaskMemFree((LPVOID)lpString1);
  if ( v8 )
  {
    for ( i = 0; i < (unsigned int)v7; ++i )
    {
      v21 = v8[i];
      if ( v21 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      v8[i] = 0;
    }
    CoTaskMemFree(v8);
  }
  v22 = *v9;
  if ( *v9 )
  {
    *v9 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  }
  return a2;
}

```

## disassembly

```asm
0x180019efc  mov     [rsp-40h+arg_8], rdx
0x180019f01  push    rbp
0x180019f02  push    rbx
0x180019f03  push    rsi
0x180019f04  push    rdi
0x180019f05  push    r12
0x180019f07  push    r13
0x180019f09  push    r14
0x180019f0b  push    r15
0x180019f0d  mov     rbp, rsp
0x180019f10  sub     rsp, 58h
0x180019f14  mov     r10, r9
0x180019f17  mov     rbx, rdx
0x180019f1a  xor     r13d, r13d
0x180019f1d  mov     [rbp+var_28], r13d
0x180019f21  mov     [rbp+var_18], r13
0x180019f25  mov     [rbp+var_10], r13d
0x180019f29  mov     dword ptr [rbp+lpString2], r13d
0x180019f2d  mov     [rbp+pv], r13
0x180019f31  mov     rcx, [rcx+0B8h]
0x180019f38  mov     rax, [rcx]
0x180019f3b  lea     rdx, [rbp+pv]
0x180019f3f  mov     qword ptr [rsp+58h+bIgnoreCase], rdx; int
0x180019f44  lea     r9, [rbp+lpString2]
0x180019f48  mov     r8, [r8]
0x180019f4b  mov     rdx, [r10]
0x180019f4e  mov     rax, [rax+58h]
0x180019f52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f57  mov     rcx, [rbp+40h]; this
0x180019f5b  test    eax, eax
0x180019f5d  jns     short loc_180019F74
0x180019f5f  mov     r9d, eax; char *
0x180019f62  lea     r8, aOnecoreuapEndu_17; "onecoreuap\\enduser\\winstore\\licensem"...
0x180019f69  mov     edx, 679h; void *
0x180019f6e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180019f74  mov     r14d, dword ptr [rbp+lpString2]
0x180019f78  mov     rsi, [rbp+pv]
0x180019f7c  mov     [rbp+var_18], rsi
0x180019f80  mov     [rbp+var_10], r14d
0x180019f84  mov     [rbp+lpString1], r13
0x180019f88  mov     r15, [rbp+arg_20]
0x180019f8c  mov     rcx, [r15]
0x180019f8f  test    rcx, rcx
0x180019f92  jz      short loc_180019FC5
0x180019f94  mov     rax, [rcx]
0x180019f97  mov     [rbp+lpString1], r13
0x180019f9b  lea     rdx, [rbp+lpString1]
0x180019f9f  mov     rax, [rax+18h]
0x180019fa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019fa8  mov     rcx, [rbp+40h]; this
0x180019fac  test    eax, eax
0x180019fae  jns     short loc_180019FC5
0x180019fb0  mov     r9d, eax; char *
0x180019fb3  lea     r8, aOnecoreuapEndu_17; "onecoreuap\\enduser\\winstore\\licensem"...
0x180019fba  mov     edx, 680h; void *
0x180019fbf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180019fc5  mov     [rbx], r13
0x180019fc8  mov     [rbx+8], r13
0x180019fcc  mov     [rbx+10h], r13
0x180019fd0  mov     [rbp+var_28], 1
0x180019fd7  mov     [rbp+lpString2], r14
0x180019fdb  test    r14d, r14d
0x180019fde  jz      short loc_180019FEC
0x180019fe0  lea     rdx, [rbp+lpString2]
0x180019fe4  mov     rcx, rbx
0x180019fe7  call    ??$_Reallocate@$0A@@?$vector@V?$ComPtr@UIStoredLeaseDocument@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIStoredLeaseDocument@@@WRL@Microsoft@@@std@@@std@@AEAAXAEA_K@Z; std::vector<Microsoft::WRL::ComPtr<IStoredLeaseDocument>>::_Reallocate<0>(unsigned __int64 &)
0x180019fec  mov     r12d, r13d
0x180019fef  test    r14d, r14d
0x180019ff2  jz      loc_18001A10B
0x180019ff8  cmp     [rbp+lpString1], r13
0x180019ffc  jz      loc_18001A097
0x18001a002  mov     [rbp+lpString2], r13
0x18001a006  mov     eax, r12d
0x18001a009  mov     rcx, [rsi+rax*8]
0x18001a00d  mov     rax, [rcx]
0x18001a010  mov     [rbp+lpString2], r13
0x18001a014  lea     rdx, [rbp+lpString2]
0x18001a018  mov     rax, [rax+18h]
0x18001a01c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a021  mov     rcx, [rbp+40h]; this
0x18001a025  test    eax, eax
0x18001a027  js      loc_18001A181
0x18001a02d  mov     [rsp+58h+bIgnoreCase], r13d; bIgnoreCase
0x18001a032  or      r9d, 0FFFFFFFFh; cchCount2
0x18001a036  mov     r8, [rbp+lpString2]; lpString2
0x18001a03a  or      edx, r9d; cchCount1
0x18001a03d  mov     rcx, [rbp+lpString1]; lpString1
0x18001a041  call    cs:__imp_CompareStringOrdinal
0x18001a047  cmp     eax, 2
0x18001a04a  jnz     short loc_18001A088
0x18001a04c  mov     rdx, [rbx+8]
0x18001a050  cmp     rdx, [rbx+10h]
0x18001a054  jz      short loc_18001A06B
0x18001a056  mov     rax, [r15]
0x18001a059  mov     [rdx], rax
0x18001a05c  mov     rcx, rdx
0x18001a05f  call    ?InternalAddRef@?$ComPtr@VClipKeyDocument@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<ClipKeyDocument>::InternalAddRef(void)
0x18001a064  add     qword ptr [rbx+8], 8
0x18001a069  jmp     short loc_18001A077
0x18001a06b  mov     r8, r15
0x18001a06e  mov     rcx, rbx
0x18001a071  call    ??$_Emplace_reallocate@AEBV?$ComPtr@UIStoredLeaseDocument@@@WRL@Microsoft@@@?$vector@V?$ComPtr@UIStoredLeaseDocument@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIStoredLeaseDocument@@@WRL@Microsoft@@@std@@@std@@AEAAPEAV?$ComPtr@UIStoredLeaseDocument@@@WRL@Microsoft@@QEAV234@AEBV234@@Z; std::vector<Microsoft::WRL::ComPtr<IStoredLeaseDocument>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<IStoredLeaseDocument> const &>(Microsoft::WRL::ComPtr<IStoredLeaseDocument> * const,Microsoft::WRL::ComPtr<IStoredLeaseDocument> const &)
0x18001a076  nop
0x18001a077  mov     rcx, [rbp+lpString2]; pv
0x18001a07b  test    rcx, rcx
0x18001a07e  jz      short loc_18001A0FF
0x18001a080  call    cs:__imp_CoTaskMemFree
0x18001a086  jmp     short loc_18001A0FF
0x18001a088  mov     rcx, [rbp+lpString2]; pv
0x18001a08c  test    rcx, rcx
0x18001a08f  jz      short loc_18001A097
0x18001a091  call    cs:__imp_CoTaskMemFree
0x18001a097  mov     eax, r12d
0x18001a09a  mov     rdi, [rsi+rax*8]
0x18001a09e  mov     [rbp+var_20], rdi
0x18001a0a2  test    rdi, rdi
0x18001a0a5  jz      short loc_18001A0B7
0x18001a0a7  mov     rax, [rdi]
0x18001a0aa  mov     rcx, rdi
0x18001a0ad  mov     rax, [rax+8]
0x18001a0b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a0b6  nop
0x18001a0b7  mov     rdx, [rbx+8]
0x18001a0bb  cmp     rdx, [rbx+10h]
0x18001a0bf  jz      short loc_18001A0DA
0x18001a0c1  mov     [rdx], r13
0x18001a0c4  lea     rax, [rbp+var_20]
0x18001a0c8  cmp     rdx, rax
0x18001a0cb  jz      short loc_18001A0D3
0x18001a0cd  mov     [rdx], rdi
0x18001a0d0  mov     rdi, r13
0x18001a0d3  add     qword ptr [rbx+8], 8
0x18001a0d8  jmp     short loc_18001A0EA
0x18001a0da  lea     r8, [rbp+var_20]
0x18001a0de  mov     rcx, rbx
0x18001a0e1  call    ??$_Emplace_reallocate@V?$ComPtr@UIStoredLeaseDocument@@@WRL@Microsoft@@@?$vector@V?$ComPtr@UIStoredLeaseDocument@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIStoredLeaseDocument@@@WRL@Microsoft@@@std@@@std@@AEAAPEAV?$ComPtr@UIStoredLeaseDocument@@@WRL@Microsoft@@QEAV234@$$QEAV234@@Z; std::vector<Microsoft::WRL::ComPtr<IStoredLeaseDocument>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<IStoredLeaseDocument>>(Microsoft::WRL::ComPtr<IStoredLeaseDocument> * const,Microsoft::WRL::ComPtr<IStoredLeaseDocument> &&)
0x18001a0e6  mov     rdi, [rbp+var_20]
0x18001a0ea  test    rdi, rdi
0x18001a0ed  jz      short loc_18001A0FF
0x18001a0ef  mov     rax, [rdi]
0x18001a0f2  mov     rcx, rdi
0x18001a0f5  mov     rax, [rax+10h]
0x18001a0f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a0fe  nop
0x18001a0ff  inc     r12d
0x18001a102  cmp     r12d, r14d
0x18001a105  jb      loc_180019FF8
0x18001a10b  mov     rcx, [rbp+lpString1]; pv
0x18001a10f  test    rcx, rcx
0x18001a112  jz      short loc_18001A11B
0x18001a114  call    cs:__imp_CoTaskMemFree
0x18001a11a  nop
0x18001a11b  test    rsi, rsi
0x18001a11e  jz      short loc_18001A155
0x18001a120  mov     edi, r13d
0x18001a123  test    r14d, r14d
0x18001a126  jz      short loc_18001A14B
0x18001a128  mov     r12d, edi
0x18001a12b  mov     rcx, [rsi+r12*8]
0x18001a12f  test    rcx, rcx
0x18001a132  jz      short loc_18001A140
0x18001a134  mov     rax, [rcx]
0x18001a137  mov     rax, [rax+10h]
0x18001a13b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a140  mov     [rsi+r12*8], r13
0x18001a144  inc     edi
0x18001a146  cmp     edi, r14d
0x18001a149  jb      short loc_18001A128
0x18001a14b  mov     rcx, rsi; pv
0x18001a14e  call    cs:__imp_CoTaskMemFree
0x18001a154  nop
0x18001a155  mov     rcx, [r15]
0x18001a158  test    rcx, rcx
0x18001a15b  jz      short loc_18001A16D
0x18001a15d  mov     [r15], r13
0x18001a160  mov     rax, [rcx]
0x18001a163  mov     rax, [rax+10h]
0x18001a167  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a16c  nop
0x18001a16d  mov     rax, rbx
0x18001a170  add     rsp, 58h
0x18001a174  pop     r15
0x18001a176  pop     r14
0x18001a178  pop     r13
0x18001a17a  pop     r12
0x18001a17c  pop     rdi
0x18001a17d  pop     rsi
0x18001a17e  pop     rbx
0x18001a17f  pop     rbp
0x18001a180  retn
0x18001a181  mov     r9d, eax; char *
0x18001a184  lea     r8, aOnecoreuapEndu_17; "onecoreuap\\enduser\\winstore\\licensem"...
0x18001a18b  mov     edx, 68Ah; void *
0x18001a190  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
