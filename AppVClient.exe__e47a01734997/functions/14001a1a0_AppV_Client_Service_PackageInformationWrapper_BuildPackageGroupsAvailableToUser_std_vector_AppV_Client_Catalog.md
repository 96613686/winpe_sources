# AppV::Client::Service::PackageInformationWrapper::BuildPackageGroupsAvailableToUser(std::vector<AppV::Client::CatalogPackageIdentity,std::allocator<AppV::Client::CatalogPackageIdentity>> const &,std::vector<AppV::Client::CatalogPackageIdentity,std::allocator<AppV::Client::CatalogPackageIdentity>> const &,tagSAFEARRAY * *)

- ea: `0x14001a1a0`
- end: `0x14001a609`
- name: `?BuildPackageGroupsAvailableToUser@PackageInformationWrapper@Service@Client@AppV@@AEAA_KAEBV?$vector@UCatalogPackageIdentity@Client@AppV@@V?$allocator@UCatalogPackageIdentity@Client@AppV@@@std@@@std@@0PEAPEAUtagSAFEARRAY@@@Z`
- size: `1129`
- prototype: `__int64 __fastcall(AppV::Client::Service::PackageInformationWrapper *this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14001c604`

## callees

- `0x1400042a4`
- `0x140019704`
- `0x140019f3c`
- `0x14001a1a0`
- `0x14001aa14`
- `0x14001d344`
- `0x14001d3c4`
- `0x14001d488`
- `0x14001d4b0`
- `0x14006a010`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14001a44b`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14001a5cb`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14001a44b`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14001a5cb`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x14001a441`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x14001a572`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x14001a5c1`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x14001a441`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x14001a572`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x14001a5c1`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall AppV::Client::Service::PackageInformationWrapper::BuildPackageGroupsAvailableToUser(
        AppV::Client::Service::PackageInformationWrapper *this,
        __int64 *a2,
        __int64 *a3,
        SAFEARRAY **a4)
{
  __int64 v7; // r15
  _QWORD *v8; // rax
  _QWORD *v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rcx
  unsigned __int64 v12; // rbx
  __int64 *j; // rcx
  int v14; // edi
  __int64 *v15; // rbx
  char IsPackageInSet; // al
  int v17; // ecx
  __int64 *i; // rax
  __int64 v19; // r8
  __int64 v20; // rcx
  unsigned int v21; // r14d
  const struct AppV::Client::PackageIdentity *k; // rbx
  __int64 v23; // rcx
  __int64 v24; // rsi
  __int64 (__fastcall *v25)(__int64, _QWORD, const struct AppV::Client::PackageIdentity *, _QWORD, _QWORD **); // rdi
  _QWORD *v26; // rax
  __int16 v27; // cx
  int v28; // eax
  unsigned __int64 v29; // rdi
  SAFEARRAY *v30; // rcx
  __int64 *v32; // rsi
  const struct AppV::Client::PackageIdentity *m; // rbx
  __int64 v34; // rsi
  __int64 (__fastcall *v35)(__int64, __int64, const struct AppV::Client::PackageIdentity *, _QWORD, _QWORD **); // rdi
  _QWORD *v36; // rax
  __int64 v37; // rdx
  SAFEARRAY *v38; // rax
  SAFEARRAY *v39; // rcx
  __int64 v40; // [rsp+38h] [rbp-39h] BYREF
  _QWORD *v41; // [rsp+40h] [rbp-31h] BYREF
  unsigned __int64 v42; // [rsp+48h] [rbp-29h]
  __int64 v43[2]; // [rsp+50h] [rbp-21h] BYREF
  _QWORD *v44; // [rsp+60h] [rbp-11h] BYREF
  __int64 v45; // [rsp+68h] [rbp-9h]
  _BYTE v46[8]; // [rsp+70h] [rbp-1h] BYREF
  SAFEARRAY *psa[2]; // [rsp+78h] [rbp+7h]
  int v48; // [rsp+88h] [rbp+17h]

  LODWORD(v7) = 0;
  v43[1] = 0;
  v8 = operator new(0x60u);
  *v8 = v8;
  v8[1] = v8;
  v8[2] = v8;
  *((_WORD *)v8 + 12) = 257;
  v43[0] = (__int64)v8;
  v42 = 0;
  v9 = operator new(0x60u);
  *v9 = v9;
  v9[1] = v9;
  v9[2] = v9;
  *((_WORD *)v9 + 12) = 257;
  v41 = v9;
  v12 = AppV::Client::Service::PackageInformationWrapper::BuildAvailableObjectSet<std::vector<AppV::Client::CatalogPackageIdentity>,AppV::Client::PackageIdentity>(
          v10,
          a2,
          v43);
  if ( (v12 & 0x8000000000LL) == 0
    || (v12 = AppV::Client::Service::PackageInformationWrapper::BuildAvailableObjectSet<std::vector<AppV::Client::CatalogPackageIdentity>,AppV::Client::PackageIdentity>(
                v11,
                a3,
                (__int64 *)&v41),
        (v12 & 0x8000000000LL) == 0) )
  {
LABEL_50:
    std::_Tree<std::_Tset_traits<AppV::Client::PackageIdentity,std::less<AppV::Client::PackageIdentity>,std::allocator<AppV::Client::PackageIdentity>,0>>::~_Tree<std::_Tset_traits<AppV::Client::PackageIdentity,std::less<AppV::Client::PackageIdentity>,std::allocator<AppV::Client::PackageIdentity>,0>>(&v41);
    std::_Tree<std::_Tset_traits<AppV::Client::PackageIdentity,std::less<AppV::Client::PackageIdentity>,std::allocator<AppV::Client::PackageIdentity>,0>>::~_Tree<std::_Tset_traits<AppV::Client::PackageIdentity,std::less<AppV::Client::PackageIdentity>,std::allocator<AppV::Client::PackageIdentity>,0>>(v43);
    return v12;
  }
  v14 = 0;
  v15 = *(__int64 **)v43[0];
  while ( v15 != (__int64 *)v43[0] )
  {
    IsPackageInSet = AppV::Client::Service::PackageInformationWrapper::IsPackageInSet(j, v15 + 4, &v41);
    v17 = v14 + 1;
    if ( IsPackageInSet )
      v17 = v14;
    v14 = v17;
    j = (__int64 *)v15[2];
    if ( *((_BYTE *)j + 25) )
    {
      for ( i = (__int64 *)v15[1]; !*((_BYTE *)i + 25) && v15 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        v15 = i;
      v15 = i;
    }
    else
    {
      v15 = (__int64 *)v15[2];
      for ( j = (__int64 *)*j; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v15 = j;
    }
  }
  if ( v42 > 0xFFFFFFFF || (v19 = (unsigned int)(v42 + v14), (unsigned int)v19 < (unsigned int)v42) )
    msl::utilities::SafeIntErrorPolicy_SafeIntException::SafeIntOnOverflow();
  *(_OWORD *)psa = 0;
  v48 = 0;
  v46[0] = 0;
  v40 = 0;
  v12 = AppV::Client::Service::PackageInformationWrapper::CreatePropertiesSafeArray(0xFFFFFFFFLL, v46, v19, &v40);
  if ( (v12 & 0x8000000000LL) == 0 )
  {
    v39 = psa[0];
    if ( psa[0] )
    {
      if ( v46[0] )
      {
        SafeArrayUnaccessData(psa[0]);
        v39 = psa[0];
      }
      SafeArrayDestroy(v39);
    }
    goto LABEL_50;
  }
  v21 = 0;
  for ( k = (const struct AppV::Client::PackageIdentity *)*a3;
        k != (const struct AppV::Client::PackageIdentity *)a3[1];
        k = (const struct AppV::Client::PackageIdentity *)((char *)k + 72) )
  {
    if ( *((_BYTE *)k + 64) != (_BYTE)v7 )
    {
      v23 = 5LL * v21;
      v24 = v40 + 40LL * v21;
      *(_WORD *)(v24 + 28) = -1;
      *(_WORD *)(v24 + 30) = v7;
      v7 = *((_QWORD *)this + 1);
      if ( v7 )
      {
        v25 = *(__int64 (__fastcall **)(__int64, _QWORD, const struct AppV::Client::PackageIdentity *, _QWORD, _QWORD **))(*(_QWORD *)v7 + 40LL);
        v44 = 0;
        v45 = 0;
        v26 = operator new(0x60u);
        *v26 = v26;
        v26[1] = v26;
        v26[2] = v26;
        *((_WORD *)v26 + 12) = 257;
        v44 = v26;
        LOBYTE(v25) = v25(v7, 0, k, 0, &v44);
        std::_Tree<std::_Tset_traits<AppV::Client::PackageIdentity,std::less<AppV::Client::PackageIdentity>,std::allocator<AppV::Client::PackageIdentity>,0>>::~_Tree<std::_Tset_traits<AppV::Client::PackageIdentity,std::less<AppV::Client::PackageIdentity>,std::allocator<AppV::Client::PackageIdentity>,0>>(&v44);
        LODWORD(v7) = 0;
        if ( (_BYTE)v25 )
          *(_WORD *)(v24 + 30) = -1;
      }
      v27 = ((unsigned __int8)AppV::Client::Service::PackageInformationWrapper::IsPackageInSet(v23, k, v43) ^ 1) - 1;
      *(_WORD *)(v24 + 32) = v27;
      *(_WORD *)(v24 + 34) = v7;
      v28 = v7;
      LOBYTE(v28) = v27 != -1;
      if ( (unsigned __int8)AppV::Client::Service::PackageInformationWrapper::IsPackageOrConnectionGroupPending(
                              *((_QWORD *)this + 1),
                              k,
                              2,
                              2,
                              v28 + 1) )
        *(_WORD *)(v24 + 34) = -1;
      v29 = AppV::Client::Service::PackageInformationWrapper::SetCommonPackageGroupInformation(
              this,
              k,
              (struct PackageGroupProperties *)v24);
      if ( (v29 & 0x8000000000LL) == 0 )
      {
LABEL_30:
        v30 = psa[0];
        if ( psa[0] )
        {
          if ( v46[0] != (_BYTE)v7 )
          {
            SafeArrayUnaccessData(psa[0]);
            v30 = psa[0];
          }
          SafeArrayDestroy(v30);
        }
        std::_Tree<std::_Tset_traits<AppV::Client::PackageIdentity,std::less<AppV::Client::PackageIdentity>,std::allocator<AppV::Client::PackageIdentity>,0>>::~_Tree<std::_Tset_traits<AppV::Client::PackageIdentity,std::less<AppV::Client::PackageIdentity>,std::allocator<AppV::Client::PackageIdentity>,0>>(&v41);
        std::_Tree<std::_Tset_traits<AppV::Client::PackageIdentity,std::less<AppV::Client::PackageIdentity>,std::allocator<AppV::Client::PackageIdentity>,0>>::~_Tree<std::_Tset_traits<AppV::Client::PackageIdentity,std::less<AppV::Client::PackageIdentity>,std::allocator<AppV::Client::PackageIdentity>,0>>(v43);
        return v29;
      }
      ++v21;
    }
  }
  v32 = a2;
  for ( m = (const struct AppV::Client::PackageIdentity *)*a2;
        m != (const struct AppV::Client::PackageIdentity *)v32[1];
        m = (const struct AppV::Client::PackageIdentity *)((char *)m + 72) )
  {
    if ( *((_BYTE *)m + 64) != (_BYTE)v7
      && !(unsigned __int8)AppV::Client::Service::PackageInformationWrapper::IsPackageInSet(v20, m, &v41) )
    {
      v34 = v40 + 40LL * v21;
      *(_DWORD *)(v34 + 28) = 0;
      *(_WORD *)(v34 + 32) = -1;
      *(_WORD *)(v34 + 34) = v7;
      v7 = *((_QWORD *)this + 1);
      if ( v7 )
      {
        v35 = *(__int64 (__fastcall **)(__int64, __int64, const struct AppV::Client::PackageIdentity *, _QWORD, _QWORD **))(*(_QWORD *)v7 + 40LL);
        v44 = 0;
        v45 = 0;
        v36 = operator new(0x60u);
        *v36 = v36;
        v36[1] = v36;
        v36[2] = v36;
        *((_WORD *)v36 + 12) = 257;
        v44 = v36;
        LOBYTE(v37) = 1;
        LOBYTE(v35) = v35(v7, v37, m, 0, &v44);
        std::_Tree<std::_Tset_traits<AppV::Client::PackageIdentity,std::less<AppV::Client::PackageIdentity>,std::allocator<AppV::Client::PackageIdentity>,0>>::~_Tree<std::_Tset_traits<AppV::Client::PackageIdentity,std::less<AppV::Client::PackageIdentity>,std::allocator<AppV::Client::PackageIdentity>,0>>(&v44);
        LODWORD(v7) = 0;
        if ( (_BYTE)v35 )
          *(_WORD *)(v34 + 34) = -1;
      }
      v29 = AppV::Client::Service::PackageInformationWrapper::SetCommonPackageGroupInformation(
              this,
              m,
              (struct PackageGroupProperties *)v34);
      if ( (v29 & 0x8000000000LL) == 0 )
        goto LABEL_30;
      ++v21;
      v32 = a2;
    }
  }
  SafeArrayUnaccessData(psa[0]);
  v38 = psa[0];
  *(_OWORD *)psa = 0;
  v48 = v7;
  v46[0] = v7;
  *a4 = v38;
  std::_Tree<std::_Tset_traits<AppV::Client::PackageIdentity,std::less<AppV::Client::PackageIdentity>,std::allocator<AppV::Client::PackageIdentity>,0>>::~_Tree<std::_Tset_traits<AppV::Client::PackageIdentity,std::less<AppV::Client::PackageIdentity>,std::allocator<AppV::Client::PackageIdentity>,0>>(&v41);
  std::_Tree<std::_Tset_traits<AppV::Client::PackageIdentity,std::less<AppV::Client::PackageIdentity>,std::allocator<AppV::Client::PackageIdentity>,0>>::~_Tree<std::_Tset_traits<AppV::Client::PackageIdentity,std::less<AppV::Client::PackageIdentity>,std::allocator<AppV::Client::PackageIdentity>,0>>(v43);
  return 0x8000000000LL;
}

```

## disassembly

```asm
0x14001a1a0  mov     rax, rsp
0x14001a1a3  mov     [rax+8], rbx
0x14001a1a7  mov     [rax+20h], r9
0x14001a1ab  mov     [rax+10h], rdx
0x14001a1af  push    rbp
0x14001a1b0  push    rsi
0x14001a1b1  push    rdi
0x14001a1b2  push    r12
0x14001a1b4  push    r13
0x14001a1b6  push    r14
0x14001a1b8  push    r15
0x14001a1ba  lea     rbp, [rax-5Fh]
0x14001a1be  sub     rsp, 90h
0x14001a1c5  mov     r12, r8
0x14001a1c8  mov     rsi, rdx
0x14001a1cb  mov     r13, rcx
0x14001a1ce  xor     r15d, r15d
0x14001a1d1  mov     [rbp+57h+var_78], r15
0x14001a1d5  mov     [rbp+57h+var_70], r15
0x14001a1d9  lea     edi, [r15+60h]
0x14001a1dd  mov     ecx, edi; Size
0x14001a1df  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001a1e4  mov     [rax], rax
0x14001a1e7  mov     [rax+8], rax
0x14001a1eb  mov     [rax+10h], rax
0x14001a1ef  mov     word ptr [rax+18h], 101h
0x14001a1f5  mov     [rbp+57h+var_78], rax
0x14001a1f9  mov     [rbp+57h+var_88], r15
0x14001a1fd  mov     [rbp+57h+var_80], r15
0x14001a201  mov     ecx, edi; Size
0x14001a203  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001a208  mov     [rax], rax
0x14001a20b  mov     [rax+8], rax
0x14001a20f  mov     [rax+10h], rax
0x14001a213  mov     word ptr [rax+18h], 101h
0x14001a219  mov     [rbp+57h+var_88], rax
0x14001a21d  lea     r8, [rbp+57h+var_78]
0x14001a221  mov     rdx, rsi
0x14001a224  call    ??$BuildAvailableObjectSet@V?$vector@UCatalogPackageIdentity@Client@AppV@@V?$allocator@UCatalogPackageIdentity@Client@AppV@@@std@@@std@@UPackageIdentity@Client@AppV@@@PackageInformationWrapper@Service@Client@AppV@@AEAA_KAEBV?$vector@UCatalogPackageIdentity@Client@AppV@@V?$allocator@UCatalogPackageIdentity@Client@AppV@@@std@@@std@@AEAV?$set@UPackageIdentity@Client@AppV@@U?$less@UPackageIdentity@Client@AppV@@@std@@V?$allocator@UPackageIdentity@Client@AppV@@@5@@5@@Z; AppV::Client::Service::PackageInformationWrapper::BuildAvailableObjectSet<std::vector<AppV::Client::CatalogPackageIdentity>,AppV::Client::PackageIdentity>(std::vector<AppV::Client::CatalogPackageIdentity> const &,std::set<AppV::Client::PackageIdentity> &)
0x14001a229  mov     rbx, rax
0x14001a22c  bt      rax, 27h ; '''
0x14001a231  jnb     loc_14001A5D2
0x14001a237  lea     r8, [rbp+57h+var_88]
0x14001a23b  mov     rdx, r12
0x14001a23e  call    ??$BuildAvailableObjectSet@V?$vector@UCatalogPackageIdentity@Client@AppV@@V?$allocator@UCatalogPackageIdentity@Client@AppV@@@std@@@std@@UPackageIdentity@Client@AppV@@@PackageInformationWrapper@Service@Client@AppV@@AEAA_KAEBV?$vector@UCatalogPackageIdentity@Client@AppV@@V?$allocator@UCatalogPackageIdentity@Client@AppV@@@std@@@std@@AEAV?$set@UPackageIdentity@Client@AppV@@U?$less@UPackageIdentity@Client@AppV@@@std@@V?$allocator@UPackageIdentity@Client@AppV@@@5@@5@@Z; AppV::Client::Service::PackageInformationWrapper::BuildAvailableObjectSet<std::vector<AppV::Client::CatalogPackageIdentity>,AppV::Client::PackageIdentity>(std::vector<AppV::Client::CatalogPackageIdentity> const &,std::set<AppV::Client::PackageIdentity> &)
0x14001a243  mov     rbx, rax
0x14001a246  bt      rax, 27h ; '''
0x14001a24b  jnb     loc_14001A5D2
0x14001a251  mov     edi, r15d
0x14001a254  mov     rbx, [rbp+57h+var_78]
0x14001a258  mov     rbx, [rbx]
0x14001a25b  cmp     rbx, [rbp+57h+var_78]
0x14001a25f  jz      short loc_14001A2BD
0x14001a261  lea     rdx, [rbx+20h]
0x14001a265  lea     r8, [rbp+57h+var_88]
0x14001a269  call    ?IsPackageInSet@PackageInformationWrapper@Service@Client@AppV@@AEAA_NAEBUPackageIdentity@34@AEBV?$set@UPackageIdentity@Client@AppV@@U?$less@UPackageIdentity@Client@AppV@@@std@@V?$allocator@UPackageIdentity@Client@AppV@@@5@@std@@@Z; AppV::Client::Service::PackageInformationWrapper::IsPackageInSet(AppV::Client::PackageIdentity const &,std::set<AppV::Client::PackageIdentity> const &)
0x14001a26e  lea     ecx, [rdi+1]
0x14001a271  test    al, al
0x14001a273  cmovnz  ecx, edi
0x14001a276  mov     edi, ecx
0x14001a278  mov     rcx, [rbx+10h]
0x14001a27c  cmp     [rcx+19h], r15b
0x14001a280  jz      short loc_14001A2A0
0x14001a282  mov     rax, [rbx+8]
0x14001a286  jmp     short loc_14001A295
0x14001a288  cmp     rbx, [rax+10h]
0x14001a28c  jnz     short loc_14001A29B
0x14001a28e  mov     rbx, rax
0x14001a291  mov     rax, [rax+8]
0x14001a295  cmp     [rax+19h], r15b
0x14001a299  jz      short loc_14001A288
0x14001a29b  mov     rbx, rax
0x14001a29e  jmp     short loc_14001A25B
0x14001a2a0  mov     rbx, rcx
0x14001a2a3  mov     rcx, [rcx]
0x14001a2a6  cmp     [rcx+19h], r15b
0x14001a2aa  jnz     short loc_14001A25B
0x14001a2ac  mov     rbx, rcx
0x14001a2af  mov     rax, [rcx]
0x14001a2b2  mov     rcx, rax
0x14001a2b5  cmp     [rax+19h], r15b
0x14001a2b9  jz      short loc_14001A2AC
0x14001a2bb  jmp     short loc_14001A25B
0x14001a2bd  mov     rax, [rbp+57h+var_80]
0x14001a2c1  mov     ecx, 0FFFFFFFFh
0x14001a2c6  cmp     rax, rcx
0x14001a2c9  ja      loc_14001A603
0x14001a2cf  lea     r8d, [rax+rdi]
0x14001a2d3  cmp     r8d, eax
0x14001a2d6  jb      loc_14001A603
0x14001a2dc  xorps   xmm0, xmm0
0x14001a2df  movdqu  xmmword ptr [rbp+57h+psa], xmm0
0x14001a2e4  mov     [rbp+57h+var_40], r15d
0x14001a2e8  mov     [rbp+57h+var_58], r15b
0x14001a2ec  mov     [rbp+57h+var_90], r15
0x14001a2f0  lea     r9, [rbp+57h+var_90]
0x14001a2f4  lea     rdx, [rbp+57h+var_58]
0x14001a2f8  call    ?CreatePropertiesSafeArray@PackageInformationWrapper@Service@Client@AppV@@AEAA_KAEAV?$safe_array_with_structs@UPackageGroupProperties@@@utility@appv@@IAEAPEAUPackageGroupProperties@@@Z; AppV::Client::Service::PackageInformationWrapper::CreatePropertiesSafeArray(appv::utility::safe_array_with_structs<PackageGroupProperties> &,uint,PackageGroupProperties * &)
0x14001a2fd  mov     rbx, rax
0x14001a300  bt      rax, 27h ; '''
0x14001a305  jnb     loc_14001A5B2
0x14001a30b  mov     r14d, r15d
0x14001a30e  mov     rbx, [r12]
0x14001a312  or      edi, 0FFFFFFFFh
0x14001a315  cmp     rbx, [r12+8]
0x14001a31a  jz      loc_14001A46D
0x14001a320  cmp     [rbx+40h], r15b
0x14001a324  jz      loc_14001A429
0x14001a32a  mov     eax, r14d
0x14001a32d  lea     rcx, [rax+rax*4]
0x14001a331  mov     rax, [rbp+57h+var_90]
0x14001a335  lea     rsi, [rax+rcx*8]
0x14001a339  mov     [rsi+1Ch], di
0x14001a33d  mov     [rsi+1Eh], r15w
0x14001a342  mov     r15, [r13+8]
0x14001a346  test    r15, r15
0x14001a349  jz      short loc_14001A3BD
0x14001a34b  mov     rax, [r15]
0x14001a34e  mov     rdi, [rax+28h]
0x14001a352  mov     [rbp+57h+var_68], 0
0x14001a35a  mov     [rbp+57h+var_60], 0
0x14001a362  mov     ecx, 60h ; '`'; Size
0x14001a367  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001a36c  mov     [rax], rax
0x14001a36f  mov     [rax+8], rax
0x14001a373  mov     [rax+10h], rax
0x14001a377  mov     word ptr [rax+18h], 101h
0x14001a37d  mov     [rbp+57h+var_68], rax
0x14001a381  lea     rax, [rbp+57h+var_68]
0x14001a385  mov     [rsp+20h], rax
0x14001a38a  xor     r9d, r9d
0x14001a38d  mov     r8, rbx
0x14001a390  xor     edx, edx
0x14001a392  mov     rcx, r15
0x14001a395  mov     rax, rdi
0x14001a398  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a39d  mov     dil, al
0x14001a3a0  lea     rcx, [rbp+57h+var_68]
0x14001a3a4  call    ??1?$_Tree@V?$_Tset_traits@UPackageIdentity@Client@AppV@@U?$less@UPackageIdentity@Client@AppV@@@std@@V?$allocator@UPackageIdentity@Client@AppV@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<AppV::Client::PackageIdentity,std::less<AppV::Client::PackageIdentity>,std::allocator<AppV::Client::PackageIdentity>,0>>::~_Tree<std::_Tset_traits<AppV::Client::PackageIdentity,std::less<AppV::Client::PackageIdentity>,std::allocator<AppV::Client::PackageIdentity>,0>>(void)
0x14001a3a9  xor     r15d, r15d
0x14001a3ac  test    dil, dil
0x14001a3af  jz      short loc_14001A3BA
0x14001a3b1  or      edi, 0FFFFFFFFh
0x14001a3b4  mov     [rsi+1Eh], di
0x14001a3b8  jmp     short loc_14001A3BD
0x14001a3ba  or      edi, 0FFFFFFFFh
0x14001a3bd  lea     r8, [rbp+57h+var_78]
0x14001a3c1  mov     rdx, rbx
0x14001a3c4  call    ?IsPackageInSet@PackageInformationWrapper@Service@Client@AppV@@AEAA_NAEBUPackageIdentity@34@AEBV?$set@UPackageIdentity@Client@AppV@@U?$less@UPackageIdentity@Client@AppV@@@std@@V?$allocator@UPackageIdentity@Client@AppV@@@5@@std@@@Z; AppV::Client::Service::PackageInformationWrapper::IsPackageInSet(AppV::Client::PackageIdentity const &,std::set<AppV::Client::PackageIdentity> const &)
0x14001a3c9  mov     edx, 1
0x14001a3ce  xor     al, dl
0x14001a3d0  movzx   ecx, al
0x14001a3d3  sub     cx, dx
0x14001a3d6  mov     [rsi+20h], cx
0x14001a3da  mov     [rsi+22h], r15w
0x14001a3df  mov     eax, r15d
0x14001a3e2  cmp     di, cx
0x14001a3e5  setnz   al
0x14001a3e8  add     eax, edx
0x14001a3ea  mov     [rsp+20h], eax
0x14001a3ee  lea     eax, [rdx+1]
0x14001a3f1  mov     r9d, eax
0x14001a3f4  mov     r8d, eax
0x14001a3f7  mov     rdx, rbx
0x14001a3fa  mov     rcx, [r13+8]
0x14001a3fe  call    ?IsPackageOrConnectionGroupPending@PackageInformationWrapper@Service@Client@AppV@@CA_NPEBVVirtualEnvironmentUtils@34@AEBUPackageIdentity@34@W4PendingType@1234@W4PendingTarget@1234@W4PendingDeployment@1234@@Z; AppV::Client::Service::PackageInformationWrapper::IsPackageOrConnectionGroupPending(AppV::Client::VirtualEnvironmentUtils const *,AppV::Client::PackageIdentity const &,AppV::Client::Service::PackageInformationWrapper::PendingType,AppV::Client::Service::PackageInformationWrapper::PendingTarget,AppV::Client::Service::PackageInformationWrapper::PendingDeployment)
0x14001a403  test    al, al
0x14001a405  jz      short loc_14001A40B
0x14001a407  mov     [rsi+22h], di
0x14001a40b  mov     r8, rsi; struct PackageGroupProperties *
0x14001a40e  mov     rdx, rbx; struct AppV::Client::PackageIdentity *
0x14001a411  mov     rcx, r13; this
0x14001a414  call    ?SetCommonPackageGroupInformation@PackageInformationWrapper@Service@Client@AppV@@AEAA_KAEBUPackageIdentity@34@AEAUPackageGroupProperties@@@Z; AppV::Client::Service::PackageInformationWrapper::SetCommonPackageGroupInformation(AppV::Client::PackageIdentity const &,PackageGroupProperties &)
0x14001a419  mov     rdi, rax
0x14001a41c  bt      rax, 27h ; '''
0x14001a421  jnb     short loc_14001A432
0x14001a423  inc     r14d
0x14001a426  or      edi, 0FFFFFFFFh
0x14001a429  add     rbx, 48h ; 'H'
0x14001a42d  jmp     loc_14001A315
0x14001a432  mov     rcx, [rbp+57h+psa]; psa
0x14001a436  test    rcx, rcx
0x14001a439  jz      short loc_14001A452
0x14001a43b  cmp     [rbp+57h+var_58], r15b
0x14001a43f  jz      short loc_14001A44B
0x14001a441  call    cs:__imp_SafeArrayUnaccessData
0x14001a447  mov     rcx, [rbp+57h+psa]; psa
0x14001a44b  call    cs:__imp_SafeArrayDestroy
0x14001a451  nop
0x14001a452  lea     rcx, [rbp+57h+var_88]
0x14001a456  call    ??1?$_Tree@V?$_Tset_traits@UPackageIdentity@Client@AppV@@U?$less@UPackageIdentity@Client@AppV@@@std@@V?$allocator@UPackageIdentity@Client@AppV@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<AppV::Client::PackageIdentity,std::less<AppV::Client::PackageIdentity>,std::allocator<AppV::Client::PackageIdentity>,0>>::~_Tree<std::_Tset_traits<AppV::Client::PackageIdentity,std::less<AppV::Client::PackageIdentity>,std::allocator<AppV::Client::PackageIdentity>,0>>(void)
0x14001a45b  nop
0x14001a45c  lea     rcx, [rbp+57h+var_78]
0x14001a460  call    ??1?$_Tree@V?$_Tset_traits@UPackageIdentity@Client@AppV@@U?$less@UPackageIdentity@Client@AppV@@@std@@V?$allocator@UPackageIdentity@Client@AppV@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<AppV::Client::PackageIdentity,std::less<AppV::Client::PackageIdentity>,std::allocator<AppV::Client::PackageIdentity>,0>>::~_Tree<std::_Tset_traits<AppV::Client::PackageIdentity,std::less<AppV::Client::PackageIdentity>,std::allocator<AppV::Client::PackageIdentity>,0>>(void)
0x14001a465  mov     rax, rdi
0x14001a468  jmp     loc_14001A5E8
0x14001a46d  mov     rsi, [rbp+57h+arg_8]
0x14001a471  mov     rbx, [rsi]
0x14001a474  cmp     rbx, [rsi+8]
0x14001a478  jz      loc_14001A56E
0x14001a47e  cmp     [rbx+40h], r15b
0x14001a482  jz      loc_14001A565
0x14001a488  lea     r8, [rbp+57h+var_88]
0x14001a48c  mov     rdx, rbx
0x14001a48f  call    ?IsPackageInSet@PackageInformationWrapper@Service@Client@AppV@@AEAA_NAEBUPackageIdentity@34@AEBV?$set@UPackageIdentity@Client@AppV@@U?$less@UPackageIdentity@Client@AppV@@@std@@V?$allocator@UPackageIdentity@Client@AppV@@@5@@std@@@Z; AppV::Client::Service::PackageInformationWrapper::IsPackageInSet(AppV::Client::PackageIdentity const &,std::set<AppV::Client::PackageIdentity> const &)
0x14001a494  test    al, al
0x14001a496  jnz     loc_14001A565
0x14001a49c  mov     eax, r14d
0x14001a49f  lea     rcx, [rax+rax*4]
0x14001a4a3  mov     rax, [rbp+57h+var_90]
0x14001a4a7  lea     rsi, [rax+rcx*8]
0x14001a4ab  mov     dword ptr [rsi+1Ch], 0
0x14001a4b2  mov     [rsi+20h], di
0x14001a4b6  mov     [rsi+22h], r15w
0x14001a4bb  mov     r15, [r13+8]
0x14001a4bf  test    r15, r15
0x14001a4c2  jz      short loc_14001A539
0x14001a4c4  mov     rax, [r15]
0x14001a4c7  mov     rdi, [rax+28h]
0x14001a4cb  mov     [rbp+57h+var_68], 0
0x14001a4d3  mov     [rbp+57h+var_60], 0
0x14001a4db  mov     ecx, 60h ; '`'; Size
0x14001a4e0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001a4e5  mov     [rax], rax
0x14001a4e8  mov     [rax+8], rax
0x14001a4ec  mov     [rax+10h], rax
0x14001a4f0  mov     r12d, 1
0x14001a4f6  mov     word ptr [rax+18h], 101h
0x14001a4fc  mov     [rbp+57h+var_68], rax
0x14001a500  lea     rax, [rbp+57h+var_68]
0x14001a504  mov     [rsp+20h], rax
0x14001a509  xor     r9d, r9d
0x14001a50c  mov     r8, rbx
0x14001a50f  mov     dl, r12b
0x14001a512  mov     rcx, r15
0x14001a515  mov     rax, rdi
0x14001a518  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a51d  mov     dil, al
0x14001a520  lea     rcx, [rbp+57h+var_68]
0x14001a524  call    ??1?$_Tree@V?$_Tset_traits@UPackageIdentity@Client@AppV@@U?$less@UPackageIdentity@Client@AppV@@@std@@V?$allocator@UPackageIdentity@Client@AppV@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<AppV::Client::PackageIdentity,std::less<AppV::Client::PackageIdentity>,std::allocator<AppV::Client::PackageIdentity>,0>>::~_Tree<std::_Tset_traits<AppV::Client::PackageIdentity,std::less<AppV::Client::PackageIdentity>,std::allocator<AppV::Client::PackageIdentity>,0>>(void)
0x14001a529  xor     r15d, r15d
0x14001a52c  test    dil, dil
0x14001a52f  jz      short loc_14001A53F
0x14001a531  mov     word ptr [rsi+22h], 0FFFFh
0x14001a537  jmp     short loc_14001A53F
0x14001a539  mov     r12d, 1
0x14001a53f  mov     r8, rsi; struct PackageGroupProperties *
0x14001a542  mov     rdx, rbx; struct AppV::Client::PackageIdentity *
0x14001a545  mov     rcx, r13; this
0x14001a548  call    ?SetCommonPackageGroupInformation@PackageInformationWrapper@Service@Client@AppV@@AEAA_KAEBUPackageIdentity@34@AEAUPackageGroupProperties@@@Z; AppV::Client::Service::PackageInformationWrapper::SetCommonPackageGroupInformation(AppV::Client::PackageIdentity const &,PackageGroupProperties &)
0x14001a54d  mov     rdi, rax
0x14001a550  bt      rax, 27h ; '''
0x14001a555  jnb     loc_14001A432
0x14001a55b  add     r14d, r12d
0x14001a55e  mov     rsi, [rbp+57h+arg_8]
0x14001a562  or      edi, 0FFFFFFFFh
0x14001a565  add     rbx, 48h ; 'H'
0x14001a569  jmp     loc_14001A474
0x14001a56e  mov     rcx, [rbp+57h+psa]; psa
0x14001a572  call    cs:__imp_SafeArrayUnaccessData
0x14001a578  mov     rax, [rbp+57h+psa]
0x14001a57c  xorps   xmm0, xmm0
0x14001a57f  movdqu  xmmword ptr [rbp+57h+psa], xmm0
0x14001a584  mov     [rbp+57h+var_40], r15d
0x14001a588  mov     [rbp+57h+var_58], r15b
0x14001a58c  mov     rcx, [rbp+57h+arg_18]
0x14001a590  mov     [rcx], rax
0x14001a593  lea     rcx, [rbp+57h+var_88]
0x14001a597  call    ??1?$_Tree@V?$_Tset_traits@UPackageIdentity@Client@AppV@@U?$less@UPackageIdentity@Client@AppV@@@std@@V?$allocator@UPackageIdentity@Client@AppV@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<AppV::Client::PackageIdentity,std::less<AppV::Client::PackageIdentity>,std::allocator<AppV::Client::PackageIdentity>,0>>::~_Tree<std::_Tset_traits<AppV::Client::PackageIdentity,std::less<AppV::Client::PackageIdentity>,std::allocator<AppV::Client::PackageIdentity>,0>>(void)
0x14001a59c  nop
0x14001a59d  lea     rcx, [rbp+57h+var_78]
0x14001a5a1  call    ??1?$_Tree@V?$_Tset_traits@UPackageIdentity@Client@AppV@@U?$less@UPackageIdentity@Client@AppV@@@std@@V?$allocator@UPackageIdentity@Client@AppV@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<AppV::Client::PackageIdentity,std::less<AppV::Client::PackageIdentity>,std::allocator<AppV::Client::PackageIdentity>,0>>::~_Tree<std::_Tset_traits<AppV::Client::PackageIdentity,std::less<AppV::Client::PackageIdentity>,std::allocator<AppV::Client::PackageIdentity>,0>>(void)
0x14001a5a6  mov     rax, 8000000000h
0x14001a5b0  jmp     short loc_14001A5E8
0x14001a5b2  mov     rcx, [rbp+57h+psa]; psa
0x14001a5b6  test    rcx, rcx
0x14001a5b9  jz      short loc_14001A5D2
0x14001a5bb  cmp     [rbp+57h+var_58], r15b
0x14001a5bf  jz      short loc_14001A5CB
0x14001a5c1  call    cs:__imp_SafeArrayUnaccessData
0x14001a5c7  mov     rcx, [rbp+57h+psa]; psa
0x14001a5cb  call    cs:__imp_SafeArrayDestroy
0x14001a5d1  nop
0x14001a5d2  lea     rcx, [rbp+57h+var_88]
0x14001a5d6  call    ??1?$_Tree@V?$_Tset_traits@UPackageIdentity@Client@AppV@@U?$less@UPackageIdentity@Client@AppV@@@std@@V?$allocator@UPackageIdentity@Client@AppV@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<AppV::Client::PackageIdentity,std::less<AppV::Client::PackageIdentity>,std::allocator<AppV::Client::PackageIdentity>,0>>::~_Tree<std::_Tset_traits<AppV::Client::PackageIdentity,std::less<AppV::Client::PackageIdentity>,std::allocator<AppV::Client::PackageIdentity>,0>>(void)
0x14001a5db  nop
0x14001a5dc  lea     rcx, [rbp+57h+var_78]
0x14001a5e0  call    ??1?$_Tree@V?$_Tset_traits@UPackageIdentity@Client@AppV@@U?$less@UPackageIdentity@Client@AppV@@@std@@V?$allocator@UPackageIdentity@Client@AppV@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<AppV::Client::PackageIdentity,std::less<AppV::Client::PackageIdentity>,std::allocator<AppV::Client::PackageIdentity>,0>>::~_Tree<std::_Tset_traits<AppV::Client::PackageIdentity,std::less<AppV::Client::PackageIdentity>,std::allocator<AppV::Client::PackageIdentity>,0>>(void)
0x14001a5e5  mov     rax, rbx
0x14001a5e8  mov     rbx, [rsp+0C0h+arg_0]
0x14001a5f0  add     rsp, 90h
0x14001a5f7  pop     r15
0x14001a5f9  pop     r14
0x14001a5fb  pop     r13
0x14001a5fd  pop     r12
0x14001a5ff  pop     rdi
0x14001a600  pop     rsi
0x14001a601  pop     rbp
0x14001a602  retn
0x14001a603  call    ?SafeIntOnOverflow@SafeIntErrorPolicy_SafeIntException@utilities@msl@@SAXXZ; msl::utilities::SafeIntErrorPolicy_SafeIntException::SafeIntOnOverflow(void)
  ... truncated ...
```
