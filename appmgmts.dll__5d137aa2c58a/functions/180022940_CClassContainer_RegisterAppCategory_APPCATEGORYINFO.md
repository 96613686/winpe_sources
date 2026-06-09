# CClassContainer::RegisterAppCategory(_APPCATEGORYINFO *)

- ea: `0x180022940`
- end: `0x180022d62`
- name: `?RegisterAppCategory@CClassContainer@@UEAAJPEAU_APPCATEGORYINFO@@@Z`
- size: `1058`
- prototype: `__int64 __fastcall(CClassContainer *this, struct _APPCATEGORYINFO *)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config`

## callees

- `0x1800016d0`
- `0x180008f58`
- `0x18001d130`
- `0x18001e82c`
- `0x180022940`
- `0x18002350c`
- `0x180023cdc`
- `0x180023eb0`
- `0x1800242f4`
- `0x18002435c`
- `0x1800243f0`
- `0x180024458`
- `0x180024d54`
- `0x180024d94`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022baa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022c87`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022cfe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022baa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022c87`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022cfe`
- `adsldpc!ADSIGetObjectAttributes` at `0x180022b32`
- `adsldpc!ADSIGetObjectAttributes` at `0x180022b32`
- `adsldpc!BuildADsPathFromParent` at `0x180022ade`
- `adsldpc!BuildADsPathFromParent` at `0x180022ade`
- `adsldpc!ADSICloseDSObject` at `0x180022bc3`
- `adsldpc!ADSICloseDSObject` at `0x180022d14`
- `adsldpc!ADSICloseDSObject` at `0x180022d24`
- `adsldpc!ADSICloseDSObject` at `0x180022bc3`
- `adsldpc!ADSICloseDSObject` at `0x180022d14`
- `adsldpc!ADSICloseDSObject` at `0x180022d24`
- `adsldpc!ADSICreateDSObject` at `0x180022b96`
- `adsldpc!ADSICreateDSObject` at `0x180022b96`
- `adsldpc!ADSISetObjectAttributes` at `0x180022cd3`
- `adsldpc!ADSISetObjectAttributes` at `0x180022cd3`
- `adsldpc!FreeADsMem` at `0x180022c04`
- `adsldpc!FreeADsMem` at `0x180022ce9`
- `adsldpc!FreeADsMem` at `0x180022c04`
- `adsldpc!FreeADsMem` at `0x180022ce9`

## pseudocode

```c
__int64 __fastcall CClassContainer::RegisterAppCategory(CClassContainer *this, struct _APPCATEGORYINFO *a2)
{
  unsigned int v2; // esi
  unsigned __int16 **v5; // r14
  __int64 v6; // r10
  unsigned __int64 v7; // rax
  unsigned int v8; // ebx
  const unsigned __int16 *v9; // rdx
  int RootPath; // edi
  unsigned int v11; // esi
  unsigned int v12; // eax
  const unsigned __int16 **v13; // r13
  unsigned int v14; // eax
  unsigned int v15; // r9d
  int v16; // r12d
  __int64 i; // rbx
  __int64 v18; // rdx
  __int128 v19; // xmm1
  unsigned int Description; // eax
  unsigned int v21; // r9d
  void *v23; // [rsp+30h] [rbp-D0h] BYREF
  int v24; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v25; // [rsp+3Ch] [rbp-C4h] BYREF
  LPVOID pMem; // [rsp+40h] [rbp-C0h] BYREF
  int v27; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID v28; // [rsp+50h] [rbp-B0h] BYREF
  void *v29; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v30; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 **v31; // [rsp+68h] [rbp-98h] BYREF
  const unsigned __int16 *v32; // [rsp+70h] [rbp-90h] BYREF
  _OWORD v33[2]; // [rsp+80h] [rbp-80h] BYREF
  struct _ads_attr_info v34; // [rsp+A0h] [rbp-60h] BYREF
  struct _ads_attr_info v35; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 v36[144]; // [rsp+160h] [rbp+60h] BYREF
  unsigned __int16 v37[264]; // [rsp+280h] [rbp+180h] BYREF
  unsigned __int16 v38[264]; // [rsp+490h] [rbp+390h] BYREF
  unsigned __int16 v39[7]; // [rsp+6A0h] [rbp+5A0h] BYREF
  _BYTE v40[514]; // [rsp+6AEh] [rbp+5AEh] BYREF

  v2 = 0;
  pMem = 0;
  v29 = 0;
  v23 = 0;
  v5 = 0;
  v25 = 0;
  v31 = 0;
  v32 = L"localizedDescription";
  v28 = 0;
  v24 = 0;
  if ( !a2 )
    return 2147942487LL;
  if ( !a2->pszDescription )
    return 2147942487LL;
  if ( (unsigned int)IsNullGuid(&a2->AppCategoryId) )
    return 2147942487LL;
  v7 = -1;
  do
    ++v7;
  while ( *(_WORD *)(v6 + 2 * v7) );
  if ( v7 > 0x7F )
    return 2147942487LL;
  v8 = 0;
  RootPath = GetRootPath(0, v39);
  if ( RootPath >= 0 )
  {
    RootPath = StringCchPrintfW(
                 v37,
                 0x104u,
                 L"%s%s%s",
                 L"LDAP://",
                 L"CN=AppCategories,CN=Default Domain Policy,CN=System,",
                 v40);
    if ( RootPath >= 0 )
    {
      v11 = 101;
      if ( (gCsOptions & 1) != 0 )
        v12 = GetADsOpenObjectFlags() | 0x21;
      else
        v12 = 101;
      v13 = (const unsigned __int16 **)((char *)this + 592);
      RootPath = DSServerOpenDSObject(v13, v37, v12, &v29);
      if ( RootPath < 0
        || (RDNFromGUID(&a2->AppCategoryId, v38),
            RootPath = StringCchPrintfW(v36, 0x90u, L"%x %s %s", a2->Locale, L"::", a2->pszDescription),
            RootPath < 0) )
      {
        v2 = 0;
      }
      else
      {
        BuildADsPathFromParent(v37, v38, (unsigned __int16 **)&pMem);
        if ( (gCsOptions & 1) != 0 )
          v14 = GetADsOpenObjectFlags() | 0x21;
        else
          v14 = 101;
        if ( (int)DSServerOpenDSObject(v13, (const unsigned __int16 *)pMem, v14, &v23) < 0
          || (RootPath = ADSIGetObjectAttributes(v23, &v32, 1, &v28, &v24), RootPath < 0) )
        {
          v30 = L"categoryRegistration";
          v16 = 0;
          PackStrArrToAttr(&v34, (WCHAR *)L"objectclass", &v30, 1u);
          PackGUIDToAttr(&v35, L"categoryId", &a2->AppCategoryId);
          ADSICreateDSObject(v29, v38, &v34, 2);
          for ( i = 0; i != 2; ++i )
            LocalFree(*((HLOCAL *)&v34.pADsValues + 4 * i));
          if ( v23 )
          {
            ADSICloseDSObject(v23, v18);
            v23 = 0;
          }
          if ( (gCsOptions & 1) != 0 )
            v11 = GetADsOpenObjectFlags() | 0x21;
          RootPath = DSServerOpenDSObject(v13, (const unsigned __int16 *)pMem, v11, &v23);
        }
        else
        {
          v16 = 1;
        }
        v2 = 0;
        if ( pMem )
          FreeADsMem(pMem);
        v8 = 0;
        if ( RootPath >= 0 )
        {
          if ( v16 )
          {
            if ( v24 )
            {
              v19 = *((_OWORD *)v28 + 1);
              v33[0] = *(_OWORD *)v28;
              v33[1] = v19;
              UnpackStrArrFrom<_ads_attr_info>((__int64)v33, &v31, &v25);
              v5 = v31;
            }
            Description = FindDescription(v5, v25, &a2->Locale, 0, 0);
            if ( Description )
            {
              PackStrArrToAttrEx(&v34, L"localizedDescription", &v5[Description - 1], v21, 0);
              v8 = 1;
            }
            LocalFree(v5);
          }
          v30 = v36;
          PackStrArrToAttrEx(&v34 + v8++, L"localizedDescription", &v30, v15, 1);
          v27 = 0;
          RootPath = ADSISetObjectAttributes(v23, &v34, v8, &v27);
        }
      }
    }
  }
  if ( v28 )
    FreeADsMem(v28);
  if ( v8 )
  {
    do
      LocalFree(*((HLOCAL *)&v34.pADsValues + 4 * v2++));
    while ( v2 < v8 );
  }
  if ( v23 )
    ADSICloseDSObject(v23, v9);
  if ( v29 )
    ADSICloseDSObject(v29, v9);
  return RemapErrorCode(RootPath, v9);
}

```

## disassembly

```asm
0x180022940  mov     [rsp-8+arg_10], rbx
0x180022945  push    rbp
0x180022946  push    rsi
0x180022947  push    rdi
0x180022948  push    r12
0x18002294a  push    r13
0x18002294c  push    r14
0x18002294e  push    r15
0x180022950  lea     rbp, [rsp-7C0h]
0x180022958  sub     rsp, 8C0h
0x18002295f  mov     rax, cs:__security_cookie
0x180022966  xor     rax, rsp
0x180022969  mov     [rbp+7F0h+var_40], rax
0x180022970  xor     esi, esi
0x180022972  lea     rax, aLocalizeddescr; "localizedDescription"
0x180022979  mov     [rsp+8F0h+pMem], rsi
0x18002297e  mov     r15, rdx
0x180022981  mov     [rsp+8F0h+var_898], rsi
0x180022986  mov     r13, rcx
0x180022989  mov     [rsp+8F0h+var_8C0], rsi
0x18002298e  mov     r14d, esi
0x180022991  mov     [rsp+8F0h+var_8B4], esi
0x180022995  mov     [rsp+8F0h+var_888], rsi
0x18002299a  mov     [rsp+8F0h+var_880], rax
0x18002299f  mov     [rsp+8F0h+var_8A0], rsi
0x1800229a4  mov     [rsp+8F0h+var_8B8], esi
0x1800229a8  test    rdx, rdx
0x1800229ab  jz      loc_180022D33
0x1800229b1  mov     r10, [rdx+8]
0x1800229b5  test    r10, r10
0x1800229b8  jz      loc_180022D33
0x1800229be  lea     rcx, [rdx+10h]; struct _GUID *
0x1800229c2  call    ?IsNullGuid@@YAHAEBU_GUID@@@Z; IsNullGuid(_GUID const &)
0x1800229c7  test    eax, eax
0x1800229c9  jnz     loc_180022D33
0x1800229cf  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800229d3  inc     rax
0x1800229d6  cmp     [r10+rax*2], si
0x1800229db  jnz     short loc_1800229D3
0x1800229dd  cmp     rax, 7Fh
0x1800229e1  ja      loc_180022D33
0x1800229e7  lea     rdx, [rbp+7F0h+var_250]; unsigned __int16 *
0x1800229ee  xor     ecx, ecx; struct CServerContext *
0x1800229f0  mov     ebx, esi
0x1800229f2  call    ?GetRootPath@@YAJPEAVCServerContext@@PEAGK@Z; GetRootPath(CServerContext *,ushort *,ulong)
0x1800229f7  mov     edi, eax
0x1800229f9  test    eax, eax
0x1800229fb  js      loc_180022CDF
0x180022a01  lea     rax, [rbp+7F0h+var_242]
0x180022a08  mov     edx, 104h; unsigned __int64
0x180022a0d  mov     [rsp+8F0h+var_8C8], rax
0x180022a12  lea     r9, aLdap; "LDAP://"
0x180022a19  lea     rax, aCnAppcategorie; "CN=AppCategories,CN=Default Domain Poli"...
0x180022a20  lea     r8, aSSS; "%s%s%s"
0x180022a27  mov     qword ptr [rsp+8F0h+var_8D0], rax
0x180022a2c  lea     rcx, [rbp+7F0h+var_670]; unsigned __int16 *
0x180022a33  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180022a38  mov     edi, eax
0x180022a3a  test    eax, eax
0x180022a3c  js      loc_180022CDF
0x180022a42  test    byte ptr cs:?gCsOptions@@3KA, 1; ulong gCsOptions
0x180022a49  mov     esi, 65h ; 'e'
0x180022a4e  jz      short loc_180022A5A
0x180022a50  call    ?GetADsOpenObjectFlags@@YAKXZ; GetADsOpenObjectFlags(void)
0x180022a55  or      eax, 21h
0x180022a58  jmp     short loc_180022A5C
0x180022a5a  mov     eax, esi
0x180022a5c  add     r13, 250h
0x180022a63  lea     r9, [rsp+8F0h+var_898]; void **
0x180022a68  mov     rcx, r13; struct CServerContext *
0x180022a6b  lea     rdx, [rbp+7F0h+var_670]; unsigned __int16 *
0x180022a72  mov     r8d, eax; int
0x180022a75  call    ?DSServerOpenDSObject@@YAJPEAVCServerContext@@PEBGJPEAPEAX@Z; DSServerOpenDSObject(CServerContext *,ushort const *,long,void * *)
0x180022a7a  mov     edi, eax
0x180022a7c  test    eax, eax
0x180022a7e  js      loc_180022CDD
0x180022a84  lea     rdx, [rbp+7F0h+var_460]; unsigned __int16 *
0x180022a8b  lea     rcx, [r15+10h]; struct _GUID *
0x180022a8f  call    ?RDNFromGUID@@YAHAEBU_GUID@@PEAG@Z; RDNFromGUID(_GUID const &,ushort *)
0x180022a94  mov     rax, [r15+8]
0x180022a98  lea     r8, aXSS; "%x %s %s"
0x180022a9f  mov     r9d, [r15]
0x180022aa2  lea     rcx, [rbp+7F0h+var_790]; unsigned __int16 *
0x180022aa6  mov     [rsp+8F0h+var_8C8], rax
0x180022aab  mov     edx, 90h; unsigned __int64
0x180022ab0  lea     rax, asc_180031214; "::"
0x180022ab7  mov     qword ptr [rsp+8F0h+var_8D0], rax
0x180022abc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180022ac1  mov     edi, eax
0x180022ac3  test    eax, eax
0x180022ac5  js      loc_180022CDD
0x180022acb  lea     r8, [rsp+8F0h+pMem]
0x180022ad0  lea     rdx, [rbp+7F0h+var_460]
0x180022ad7  lea     rcx, [rbp+7F0h+var_670]
0x180022ade  call    cs:__imp_?BuildADsPathFromParent@@YAJPEAG0PEAPEAG@Z; BuildADsPathFromParent(ushort *,ushort *,ushort * *)
0x180022ae4  mov     ebx, 1
0x180022ae9  test    byte ptr cs:?gCsOptions@@3KA, bl; ulong gCsOptions
0x180022aef  jz      short loc_180022AFB
0x180022af1  call    ?GetADsOpenObjectFlags@@YAKXZ; GetADsOpenObjectFlags(void)
0x180022af6  or      eax, 21h
0x180022af9  jmp     short loc_180022AFD
0x180022afb  mov     eax, esi
0x180022afd  mov     rdx, [rsp+8F0h+pMem]; unsigned __int16 *
0x180022b02  lea     r9, [rsp+8F0h+var_8C0]; void **
0x180022b07  mov     r8d, eax; int
0x180022b0a  mov     rcx, r13; struct CServerContext *
0x180022b0d  call    ?DSServerOpenDSObject@@YAJPEAVCServerContext@@PEBGJPEAPEAX@Z; DSServerOpenDSObject(CServerContext *,ushort const *,long,void * *)
0x180022b12  test    eax, eax
0x180022b14  js      short loc_180022B46
0x180022b16  mov     rcx, [rsp+8F0h+var_8C0]
0x180022b1b  lea     rax, [rsp+8F0h+var_8B8]
0x180022b20  lea     r9, [rsp+8F0h+var_8A0]
0x180022b25  mov     qword ptr [rsp+8F0h+var_8D0], rax
0x180022b2a  mov     r8d, ebx
0x180022b2d  lea     rdx, [rsp+8F0h+var_880]
0x180022b32  call    cs:__imp_ADSIGetObjectAttributes
0x180022b38  mov     edi, eax
0x180022b3a  test    eax, eax
0x180022b3c  js      short loc_180022B46
0x180022b3e  mov     r12d, ebx
0x180022b41  jmp     loc_180022BF8
0x180022b46  lea     rax, aCategoryregist; "categoryRegistration"
0x180022b4d  mov     r9d, ebx; unsigned int
0x180022b50  lea     r8, [rsp+8F0h+var_890]; unsigned __int16 **
0x180022b55  mov     [rsp+8F0h+var_890], rax
0x180022b5a  lea     rdx, aObjectclass; "objectclass"
0x180022b61  xor     r12d, r12d
0x180022b64  lea     rcx, [rbp+7F0h+var_850]; struct _ads_attr_info *
0x180022b68  call    ?PackStrArrToAttr@@YAXPEAU_ads_attr_info@@PEBGPEAPEAGK@Z; PackStrArrToAttr(_ads_attr_info *,ushort const *,ushort * *,ulong)
0x180022b6d  lea     r8, [r15+10h]; struct _GUID *
0x180022b71  lea     rdx, aCategoryid_0; "categoryId"
0x180022b78  lea     rcx, [rbp+7F0h+var_830]; struct _ads_attr_info *
0x180022b7c  call    ?PackGUIDToAttr@@YAXPEAU_ads_attr_info@@PEBGPEAU_GUID@@@Z; PackGUIDToAttr(_ads_attr_info *,ushort const *,_GUID *)
0x180022b81  mov     rcx, [rsp+8F0h+var_898]
0x180022b86  lea     r9d, [r12+2]
0x180022b8b  lea     r8, [rbp+7F0h+var_850]
0x180022b8f  lea     rdx, [rbp+7F0h+var_460]
0x180022b96  call    cs:__imp_ADSICreateDSObject
0x180022b9c  xor     ebx, ebx
0x180022b9e  mov     rcx, rbx
0x180022ba1  shl     rcx, 5
0x180022ba5  mov     rcx, [rbp+rcx+7F0h+var_850.pADsValues]; hMem
0x180022baa  call    cs:__imp_LocalFree
0x180022bb0  inc     rbx
0x180022bb3  cmp     rbx, 2
0x180022bb7  jnz     short loc_180022B9E
0x180022bb9  mov     rcx, [rsp+8F0h+var_8C0]
0x180022bbe  test    rcx, rcx
0x180022bc1  jz      short loc_180022BCE
0x180022bc3  call    cs:__imp_ADSICloseDSObject
0x180022bc9  mov     [rsp+8F0h+var_8C0], r12
0x180022bce  test    byte ptr cs:?gCsOptions@@3KA, 1; ulong gCsOptions
0x180022bd5  jz      short loc_180022BE1
0x180022bd7  call    ?GetADsOpenObjectFlags@@YAKXZ; GetADsOpenObjectFlags(void)
0x180022bdc  mov     esi, eax
0x180022bde  or      esi, 21h
0x180022be1  mov     rdx, [rsp+8F0h+pMem]; unsigned __int16 *
0x180022be6  lea     r9, [rsp+8F0h+var_8C0]; void **
0x180022beb  mov     r8d, esi; int
0x180022bee  mov     rcx, r13; struct CServerContext *
0x180022bf1  call    ?DSServerOpenDSObject@@YAJPEAVCServerContext@@PEBGJPEAPEAX@Z; DSServerOpenDSObject(CServerContext *,ushort const *,long,void * *)
0x180022bf6  mov     edi, eax
0x180022bf8  mov     rcx, [rsp+8F0h+pMem]; pMem
0x180022bfd  xor     esi, esi
0x180022bff  test    rcx, rcx
0x180022c02  jz      short loc_180022C0A
0x180022c04  call    cs:__imp_FreeADsMem
0x180022c0a  mov     ebx, esi
0x180022c0c  test    edi, edi
0x180022c0e  js      loc_180022CDF
0x180022c14  test    r12d, r12d
0x180022c17  jz      short loc_180022C8D
0x180022c19  cmp     [rsp+8F0h+var_8B8], esi
0x180022c1d  jz      short loc_180022C4B
0x180022c1f  mov     rax, [rsp+8F0h+var_8A0]
0x180022c24  lea     r8, [rsp+8F0h+var_8B4]
0x180022c29  lea     rdx, [rsp+8F0h+var_888]
0x180022c2e  lea     rcx, [rbp+7F0h+var_870]
0x180022c32  movups  xmm0, xmmword ptr [rax]
0x180022c35  movups  xmm1, xmmword ptr [rax+10h]
0x180022c39  movaps  [rbp+7F0h+var_870], xmm0
0x180022c3d  movaps  [rbp+7F0h+var_860], xmm1
0x180022c41  call    ??$UnpackStrArrFrom@U_ads_attr_info@@@@YAJU_ads_attr_info@@PEAPEAPEAGPEAK@Z; UnpackStrArrFrom<_ads_attr_info>(_ads_attr_info,ushort * * *,ulong *)
0x180022c46  mov     r14, [rsp+8F0h+var_888]
0x180022c4b  mov     edx, [rsp+8F0h+var_8B4]; unsigned int
0x180022c4f  xor     r9d, r9d; unsigned __int16 *
0x180022c52  mov     r8, r15; unsigned int *
0x180022c55  mov     [rsp+8F0h+var_8D0], esi; int
0x180022c59  mov     rcx, r14; unsigned __int16 **
0x180022c5c  call    ?FindDescription@@YAKPEAPEAGKPEAKPEAGH@Z; FindDescription(ushort * *,ulong,ulong *,ushort *,int)
0x180022c61  test    eax, eax
0x180022c63  jz      short loc_180022C84
0x180022c65  dec     eax
0x180022c67  mov     [rsp+8F0h+var_8D0], esi; int
0x180022c6b  lea     rdx, aLocalizeddescr; "localizedDescription"
0x180022c72  lea     rcx, [rbp+7F0h+var_850]; struct _ads_attr_info *
0x180022c76  lea     r8, [r14+rax*8]; unsigned __int16 **
0x180022c7a  call    ?PackStrArrToAttrEx@@YAXPEAU_ads_attr_info@@PEBGPEAPEAGKH@Z; PackStrArrToAttrEx(_ads_attr_info *,ushort const *,ushort * *,ulong,int)
0x180022c7f  mov     ebx, 1
0x180022c84  mov     rcx, r14; hMem
0x180022c87  call    cs:__imp_LocalFree
0x180022c8d  lea     rax, [rbp+7F0h+var_790]
0x180022c91  mov     [rsp+8F0h+var_8D0], 1; int
0x180022c99  mov     [rsp+8F0h+var_890], rax
0x180022c9e  lea     rcx, [rbp+7F0h+var_850]
0x180022ca2  mov     eax, ebx
0x180022ca4  lea     r8, [rsp+8F0h+var_890]; unsigned __int16 **
0x180022ca9  shl     rax, 5
0x180022cad  lea     rdx, aLocalizeddescr; "localizedDescription"
0x180022cb4  add     rcx, rax; struct _ads_attr_info *
0x180022cb7  call    ?PackStrArrToAttrEx@@YAXPEAU_ads_attr_info@@PEBGPEAPEAGKH@Z; PackStrArrToAttrEx(_ads_attr_info *,ushort const *,ushort * *,ulong,int)
0x180022cbc  mov     rcx, [rsp+8F0h+var_8C0]
0x180022cc1  lea     r9, [rsp+8F0h+var_8A8]
0x180022cc6  inc     ebx
0x180022cc8  mov     [rsp+8F0h+var_8A8], esi
0x180022ccc  mov     r8d, ebx
0x180022ccf  lea     rdx, [rbp+7F0h+var_850]
0x180022cd3  call    cs:__imp_ADSISetObjectAttributes
0x180022cd9  mov     edi, eax
0x180022cdb  jmp     short loc_180022CDF
0x180022cdd  xor     esi, esi
0x180022cdf  mov     rcx, [rsp+8F0h+var_8A0]; pMem
0x180022ce4  test    rcx, rcx
0x180022ce7  jz      short loc_180022CEF
0x180022ce9  call    cs:__imp_FreeADsMem
0x180022cef  test    ebx, ebx
0x180022cf1  jz      short loc_180022D0A
0x180022cf3  mov     ecx, esi
0x180022cf5  shl     rcx, 5
0x180022cf9  mov     rcx, [rbp+rcx+7F0h+var_850.pADsValues]; hMem
0x180022cfe  call    cs:__imp_LocalFree
0x180022d04  inc     esi
0x180022d06  cmp     esi, ebx
0x180022d08  jb      short loc_180022CF3
0x180022d0a  mov     rcx, [rsp+8F0h+var_8C0]
0x180022d0f  test    rcx, rcx
0x180022d12  jz      short loc_180022D1A
0x180022d14  call    cs:__imp_ADSICloseDSObject
0x180022d1a  mov     rcx, [rsp+8F0h+var_898]
0x180022d1f  test    rcx, rcx
0x180022d22  jz      short loc_180022D2A
0x180022d24  call    cs:__imp_ADSICloseDSObject
0x180022d2a  mov     ecx, edi; int
0x180022d2c  call    ?RemapErrorCode@@YAJJPEBG@Z; RemapErrorCode(long,ushort const *)
0x180022d31  jmp     short loc_180022D38
0x180022d33  mov     eax, 80070057h
0x180022d38  mov     rcx, [rbp+7F0h+var_40]
0x180022d3f  xor     rcx, rsp; StackCookie
0x180022d42  call    __security_check_cookie
0x180022d47  mov     rbx, [rsp+8F0h+arg_10]
0x180022d4f  add     rsp, 8C0h
0x180022d56  pop     r15
0x180022d58  pop     r14
0x180022d5a  pop     r13
0x180022d5c  pop     r12
0x180022d5e  pop     rdi
0x180022d5f  pop     rsi
0x180022d60  pop     rbp
0x180022d61  retn
```
