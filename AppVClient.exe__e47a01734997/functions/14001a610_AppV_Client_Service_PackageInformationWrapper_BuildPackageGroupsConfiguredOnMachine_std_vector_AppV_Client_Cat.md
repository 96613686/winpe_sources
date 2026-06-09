# AppV::Client::Service::PackageInformationWrapper::BuildPackageGroupsConfiguredOnMachine(std::vector<AppV::Client::CatalogPackageIdentity,std::allocator<AppV::Client::CatalogPackageIdentity>> const &,std::vector<AppV::Client::CatalogPackageIdentity,std::allocator<AppV::Client::CatalogPackageIdentity>> const &,tagSAFEARRAY * *)

- ea: `0x14001a610`
- end: `0x14001a849`
- name: `?BuildPackageGroupsConfiguredOnMachine@PackageInformationWrapper@Service@Client@AppV@@AEAA_KAEBV?$vector@UCatalogPackageIdentity@Client@AppV@@V?$allocator@UCatalogPackageIdentity@Client@AppV@@@std@@@std@@0PEAPEAUtagSAFEARRAY@@@Z`
- size: `569`
- prototype: `__int64 __fastcall(AppV::Client::Service::PackageInformationWrapper *this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14001c604`

## callees

- `0x1400042a4`
- `0x140019704`
- `0x140019f3c`
- `0x14001a610`
- `0x14001aa14`
- `0x14001d344`
- `0x14001d3c4`
- `0x14001d4b0`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14001a840`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14001a840`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x14001a7e2`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x14001a836`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x14001a7e2`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x14001a836`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
unsigned __int64 __fastcall AppV::Client::Service::PackageInformationWrapper::BuildPackageGroupsConfiguredOnMachine(
        AppV::Client::Service::PackageInformationWrapper *this,
        __int64 *a2,
        __int64 *a3,
        SAFEARRAY **a4)
{
  _QWORD *v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rcx
  unsigned __int64 v11; // rbx
  SAFEARRAY *v12; // rcx
  bool v13; // zf
  unsigned int v14; // esi
  __int64 v15; // rdx
  __int64 v16; // r13
  const struct AppV::Client::PackageIdentity *v17; // r14
  _WORD *v18; // rbx
  SAFEARRAY *v19; // rax
  __int64 v21; // [rsp+30h] [rbp-48h] BYREF
  __int64 v22[2]; // [rsp+38h] [rbp-40h] BYREF
  _BYTE v23[8]; // [rsp+48h] [rbp-30h] BYREF
  SAFEARRAY *psa[2]; // [rsp+50h] [rbp-28h]
  int v25; // [rsp+60h] [rbp-18h]

  v22[1] = 0;
  v8 = operator new(0x60u);
  *v8 = v8;
  v8[1] = v8;
  v8[2] = v8;
  *((_WORD *)v8 + 12) = 257;
  v22[0] = (__int64)v8;
  v11 = AppV::Client::Service::PackageInformationWrapper::BuildAvailableObjectSet<std::vector<AppV::Client::CatalogPackageIdentity>,AppV::Client::PackageIdentity>(
          v9,
          a3,
          v22);
  if ( (v11 & 0x8000000000LL) == 0 )
    goto LABEL_16;
  *(_OWORD *)psa = 0;
  v25 = 0;
  v23[0] = 0;
  v21 = 0;
  v11 = AppV::Client::Service::PackageInformationWrapper::CreatePropertiesSafeArray(
          v10,
          v23,
          0x8E38E38E38E38E39uLL * ((a2[1] - *a2) >> 3),
          &v21);
  if ( (v11 & 0x8000000000LL) == 0 )
  {
    v12 = psa[0];
    if ( !psa[0] )
      goto LABEL_16;
    v13 = v23[0] == 0;
    goto LABEL_19;
  }
  v14 = 0;
  v15 = *a2;
  if ( !(0x8E38E38E38E38E39uLL * ((a2[1] - *a2) >> 3)) )
  {
LABEL_15:
    SafeArrayUnaccessData(psa[0]);
    v19 = psa[0];
    *(_OWORD *)psa = 0;
    v25 = 0;
    v23[0] = 0;
    *a4 = v19;
    v11 = 0x8000000000LL;
    goto LABEL_16;
  }
  v16 = v21;
  while ( 1 )
  {
    v17 = (const struct AppV::Client::PackageIdentity *)(v15 + 72LL * v14);
    v18 = (_WORD *)(v16 + 40LL * v14);
    v18[14] = 0;
    if ( (unsigned __int8)AppV::Client::Service::PackageInformationWrapper::IsPackageInSet(v14, v17, v22) )
      v18[14] = -1;
    v18[15] = 0;
    if ( (unsigned __int8)AppV::Client::Service::PackageInformationWrapper::IsPackageOrConnectionGroupPending(
                            *((_QWORD *)this + 1),
                            v17,
                            2,
                            1,
                            (unsigned int)(v18[14] != 0xFFFF) + 1) )
      v18[15] = -1;
    v18[16] = -(*((_BYTE *)v17 + 64) != 0);
    v18[17] = 0;
    if ( (unsigned __int8)AppV::Client::Service::PackageInformationWrapper::IsPackageOrConnectionGroupPending(
                            *((_QWORD *)this + 1),
                            v17,
                            2,
                            2,
                            2 - (unsigned int)(*((_BYTE *)v17 + 64) != 0)) )
      v18[17] = -1;
    v11 = AppV::Client::Service::PackageInformationWrapper::SetCommonPackageGroupInformation(
            this,
            v17,
            (struct PackageGroupProperties *)(v16 + 40LL * v14));
    if ( (v11 & 0x8000000000LL) == 0 )
      break;
    ++v14;
    v15 = *a2;
    if ( v14 >= 0x8E38E38E38E38E39uLL * ((a2[1] - *a2) >> 3) )
      goto LABEL_15;
  }
  v12 = psa[0];
  if ( psa[0] )
  {
    v13 = v23[0] == 0;
LABEL_19:
    if ( !v13 )
    {
      SafeArrayUnaccessData(v12);
      v12 = psa[0];
    }
    SafeArrayDestroy(v12);
  }
LABEL_16:
  std::_Tree<std::_Tset_traits<AppV::Client::PackageIdentity,std::less<AppV::Client::PackageIdentity>,std::allocator<AppV::Client::PackageIdentity>,0>>::~_Tree<std::_Tset_traits<AppV::Client::PackageIdentity,std::less<AppV::Client::PackageIdentity>,std::allocator<AppV::Client::PackageIdentity>,0>>(v22);
  return v11;
}

```

## disassembly

```asm
0x14001a610  push    rbp
0x14001a612  push    rbx
0x14001a613  push    rsi
0x14001a614  push    rdi
0x14001a615  push    r12
0x14001a617  push    r13
0x14001a619  push    r14
0x14001a61b  push    r15
0x14001a61d  mov     rbp, rsp
0x14001a620  sub     rsp, 78h
0x14001a624  mov     r12, r9
0x14001a627  mov     rbx, r8
0x14001a62a  mov     rdi, rdx
0x14001a62d  mov     r15, rcx
0x14001a630  xor     r14d, r14d
0x14001a633  mov     [rbp+var_40], r14
0x14001a637  mov     [rbp+var_38], r14
0x14001a63b  lea     ecx, [r14+60h]; Size
0x14001a63f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001a644  mov     [rax], rax
0x14001a647  mov     [rax+8], rax
0x14001a64b  mov     [rax+10h], rax
0x14001a64f  mov     word ptr [rax+18h], 101h
0x14001a655  mov     [rbp+var_40], rax
0x14001a659  lea     r8, [rbp+var_40]
0x14001a65d  mov     rdx, rbx
0x14001a660  call    ??$BuildAvailableObjectSet@V?$vector@UCatalogPackageIdentity@Client@AppV@@V?$allocator@UCatalogPackageIdentity@Client@AppV@@@std@@@std@@UPackageIdentity@Client@AppV@@@PackageInformationWrapper@Service@Client@AppV@@AEAA_KAEBV?$vector@UCatalogPackageIdentity@Client@AppV@@V?$allocator@UCatalogPackageIdentity@Client@AppV@@@std@@@std@@AEAV?$set@UPackageIdentity@Client@AppV@@U?$less@UPackageIdentity@Client@AppV@@@std@@V?$allocator@UPackageIdentity@Client@AppV@@@5@@5@@Z; AppV::Client::Service::PackageInformationWrapper::BuildAvailableObjectSet<std::vector<AppV::Client::CatalogPackageIdentity>,AppV::Client::PackageIdentity>(std::vector<AppV::Client::CatalogPackageIdentity> const &,std::set<AppV::Client::PackageIdentity> &)
0x14001a665  mov     rbx, rax
0x14001a668  bt      rax, 27h ; '''
0x14001a66d  jnb     loc_14001A80A
0x14001a673  xorps   xmm0, xmm0
0x14001a676  movdqu  xmmword ptr [rbp+psa], xmm0
0x14001a67b  mov     [rbp+var_18], r14d
0x14001a67f  mov     [rbp+var_30], r14b
0x14001a683  mov     [rbp+var_48], r14
0x14001a687  mov     r8, [rdi+8]
0x14001a68b  sub     r8, [rdi]
0x14001a68e  sar     r8, 3
0x14001a692  mov     r13, 8E38E38E38E38E39h
0x14001a69c  imul    r8, r13
0x14001a6a0  lea     r9, [rbp+var_48]
0x14001a6a4  lea     rdx, [rbp+var_30]
0x14001a6a8  call    ?CreatePropertiesSafeArray@PackageInformationWrapper@Service@Client@AppV@@AEAA_KAEAV?$safe_array_with_structs@UPackageGroupProperties@@@utility@appv@@IAEAPEAUPackageGroupProperties@@@Z; AppV::Client::Service::PackageInformationWrapper::CreatePropertiesSafeArray(appv::utility::safe_array_with_structs<PackageGroupProperties> &,uint,PackageGroupProperties * &)
0x14001a6ad  mov     rbx, rax
0x14001a6b0  bt      rax, 27h ; '''
0x14001a6b5  jb      short loc_14001A6CD
0x14001a6b7  mov     rcx, [rbp+psa]
0x14001a6bb  test    rcx, rcx
0x14001a6be  jz      loc_14001A80A
0x14001a6c4  cmp     [rbp+var_30], r14b
0x14001a6c8  jmp     loc_14001A834
0x14001a6cd  mov     esi, r14d
0x14001a6d0  mov     rdx, [rdi]
0x14001a6d3  mov     rax, [rdi+8]
0x14001a6d7  sub     rax, rdx
0x14001a6da  sar     rax, 3
0x14001a6de  imul    rax, r13
0x14001a6e2  test    rax, rax
0x14001a6e5  jz      loc_14001A7DE
0x14001a6eb  mov     r13, [rbp+var_48]
0x14001a6ef  mov     ecx, esi
0x14001a6f1  lea     rax, [rcx+rcx*8]
0x14001a6f5  lea     r14, [rdx+rax*8]
0x14001a6f9  lea     rax, [rcx+rcx*4]
0x14001a6fd  lea     rbx, ds:0[rax*8]
0x14001a705  add     rbx, r13
0x14001a708  xor     eax, eax
0x14001a70a  mov     [rbx+1Ch], ax
0x14001a70e  lea     r8, [rbp+var_40]
0x14001a712  mov     rdx, r14
0x14001a715  call    ?IsPackageInSet@PackageInformationWrapper@Service@Client@AppV@@AEAA_NAEBUPackageIdentity@34@AEBV?$set@UPackageIdentity@Client@AppV@@U?$less@UPackageIdentity@Client@AppV@@@std@@V?$allocator@UPackageIdentity@Client@AppV@@@5@@std@@@Z; AppV::Client::Service::PackageInformationWrapper::IsPackageInSet(AppV::Client::PackageIdentity const &,std::set<AppV::Client::PackageIdentity> const &)
0x14001a71a  test    al, al
0x14001a71c  jz      short loc_14001A724
0x14001a71e  mov     word ptr [rbx+1Ch], 0FFFFh
0x14001a724  xor     eax, eax
0x14001a726  mov     [rbx+1Eh], ax
0x14001a72a  or      ecx, 0FFFFFFFFh
0x14001a72d  cmp     cx, [rbx+1Ch]
0x14001a731  setnz   al
0x14001a734  inc     eax
0x14001a736  mov     [rsp+78h+var_58], eax
0x14001a73a  lea     r9d, [rcx+2]
0x14001a73e  lea     r8d, [rcx+3]
0x14001a742  mov     rdx, r14
0x14001a745  mov     rcx, [r15+8]
0x14001a749  call    ?IsPackageOrConnectionGroupPending@PackageInformationWrapper@Service@Client@AppV@@CA_NPEBVVirtualEnvironmentUtils@34@AEBUPackageIdentity@34@W4PendingType@1234@W4PendingTarget@1234@W4PendingDeployment@1234@@Z; AppV::Client::Service::PackageInformationWrapper::IsPackageOrConnectionGroupPending(AppV::Client::VirtualEnvironmentUtils const *,AppV::Client::PackageIdentity const &,AppV::Client::Service::PackageInformationWrapper::PendingType,AppV::Client::Service::PackageInformationWrapper::PendingTarget,AppV::Client::Service::PackageInformationWrapper::PendingDeployment)
0x14001a74e  test    al, al
0x14001a750  jz      short loc_14001A758
0x14001a752  mov     word ptr [rbx+1Eh], 0FFFFh
0x14001a758  mov     al, [r14+40h]
0x14001a75c  neg     al
0x14001a75e  sbb     cx, cx
0x14001a761  mov     [rbx+20h], cx
0x14001a765  xor     eax, eax
0x14001a767  mov     [rbx+22h], ax
0x14001a76b  mov     al, [r14+40h]
0x14001a76f  neg     al
0x14001a771  sbb     ecx, ecx
0x14001a773  mov     eax, 2
0x14001a778  add     ecx, eax
0x14001a77a  mov     [rsp+78h+var_58], ecx
0x14001a77e  mov     r9d, eax
0x14001a781  mov     r8d, eax
0x14001a784  mov     rdx, r14
0x14001a787  mov     rcx, [r15+8]
0x14001a78b  call    ?IsPackageOrConnectionGroupPending@PackageInformationWrapper@Service@Client@AppV@@CA_NPEBVVirtualEnvironmentUtils@34@AEBUPackageIdentity@34@W4PendingType@1234@W4PendingTarget@1234@W4PendingDeployment@1234@@Z; AppV::Client::Service::PackageInformationWrapper::IsPackageOrConnectionGroupPending(AppV::Client::VirtualEnvironmentUtils const *,AppV::Client::PackageIdentity const &,AppV::Client::Service::PackageInformationWrapper::PendingType,AppV::Client::Service::PackageInformationWrapper::PendingTarget,AppV::Client::Service::PackageInformationWrapper::PendingDeployment)
0x14001a790  test    al, al
0x14001a792  jz      short loc_14001A79A
0x14001a794  mov     word ptr [rbx+22h], 0FFFFh
0x14001a79a  mov     r8, rbx; struct PackageGroupProperties *
0x14001a79d  mov     rdx, r14; struct AppV::Client::PackageIdentity *
0x14001a7a0  mov     rcx, r15; this
0x14001a7a3  call    ?SetCommonPackageGroupInformation@PackageInformationWrapper@Service@Client@AppV@@AEAA_KAEBUPackageIdentity@34@AEAUPackageGroupProperties@@@Z; AppV::Client::Service::PackageInformationWrapper::SetCommonPackageGroupInformation(AppV::Client::PackageIdentity const &,PackageGroupProperties &)
0x14001a7a8  mov     rbx, rax
0x14001a7ab  bt      rax, 27h ; '''
0x14001a7b0  jnb     short loc_14001A827
0x14001a7b2  inc     esi
0x14001a7b4  mov     rdx, [rdi]
0x14001a7b7  mov     rcx, [rdi+8]
0x14001a7bb  sub     rcx, rdx
0x14001a7be  sar     rcx, 3
0x14001a7c2  mov     rax, 8E38E38E38E38E39h
0x14001a7cc  imul    rcx, rax
0x14001a7d0  mov     eax, esi
0x14001a7d2  cmp     rax, rcx
0x14001a7d5  jb      loc_14001A6EF
0x14001a7db  xor     r14d, r14d
0x14001a7de  mov     rcx, [rbp+psa]; psa
0x14001a7e2  call    cs:__imp_SafeArrayUnaccessData
0x14001a7e8  mov     rax, [rbp+psa]
0x14001a7ec  xorps   xmm0, xmm0
0x14001a7ef  movdqu  xmmword ptr [rbp+psa], xmm0
0x14001a7f4  mov     [rbp+var_18], r14d
0x14001a7f8  mov     [rbp+var_30], r14b
0x14001a7fc  mov     [r12], rax
0x14001a800  mov     rbx, 8000000000h
0x14001a80a  lea     rcx, [rbp+var_40]
0x14001a80e  call    ??1?$_Tree@V?$_Tset_traits@UPackageIdentity@Client@AppV@@U?$less@UPackageIdentity@Client@AppV@@@std@@V?$allocator@UPackageIdentity@Client@AppV@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<AppV::Client::PackageIdentity,std::less<AppV::Client::PackageIdentity>,std::allocator<AppV::Client::PackageIdentity>,0>>::~_Tree<std::_Tset_traits<AppV::Client::PackageIdentity,std::less<AppV::Client::PackageIdentity>,std::allocator<AppV::Client::PackageIdentity>,0>>(void)
0x14001a813  mov     rax, rbx
0x14001a816  add     rsp, 78h
0x14001a81a  pop     r15
0x14001a81c  pop     r14
0x14001a81e  pop     r13
0x14001a820  pop     r12
0x14001a822  pop     rdi
0x14001a823  pop     rsi
0x14001a824  pop     rbx
0x14001a825  pop     rbp
0x14001a826  retn
0x14001a827  mov     rcx, [rbp+psa]; psa
0x14001a82b  test    rcx, rcx
0x14001a82e  jz      short loc_14001A80A
0x14001a830  cmp     [rbp+var_30], 0
0x14001a834  jz      short loc_14001A840
0x14001a836  call    cs:__imp_SafeArrayUnaccessData
0x14001a83c  mov     rcx, [rbp+psa]; psa
0x14001a840  call    cs:__imp_SafeArrayDestroy
0x14001a846  jmp     short loc_14001A80A
```
