# AppV::Client::Service::PackageInformationWrapper::BuildPackagesSafeArray(std::vector<AppV::Client::Service::PackageData,std::allocator<AppV::Client::Service::PackageData>> const &,tagSAFEARRAY * *)

- ea: `0x14001a850`
- end: `0x14001aa0e`
- name: `?BuildPackagesSafeArray@PackageInformationWrapper@Service@Client@AppV@@AEAA_KAEBV?$vector@UPackageData@Service@Client@AppV@@V?$allocator@UPackageData@Service@Client@AppV@@@std@@@std@@PEAPEAUtagSAFEARRAY@@@Z`
- size: `446`
- prototype: `__int64 __fastcall(AppV::Client::Service::PackageInformationWrapper *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x14001d280`

## callees

- `0x14001a850`
- `0x14001ab08`
- `0x14001d3c4`
- `0x14001d5e0`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14001a9f4`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14001a9f4`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x14001a9b2`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x14001a9ea`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x14001a9b2`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x14001a9ea`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AppV::Client::Service::PackageInformationWrapper::BuildPackagesSafeArray(
        AppV::Client::Service::PackageInformationWrapper *this,
        __int64 *a2,
        SAFEARRAY **a3)
{
  unsigned int v6; // esi
  __int64 v7; // rdi
  __int64 v8; // rdx
  __int64 v9; // r13
  const struct AppV::Client::PackageIdentity *v10; // r14
  _WORD *v11; // rdi
  SAFEARRAY *v13; // rcx
  bool v14; // zf
  _BYTE v15[8]; // [rsp+30h] [rbp-28h] BYREF
  SAFEARRAY *psa[2]; // [rsp+38h] [rbp-20h]
  int v17; // [rsp+48h] [rbp-10h]
  __int64 v18; // [rsp+A8h] [rbp+50h] BYREF

  *(_OWORD *)psa = 0;
  v6 = 0;
  v17 = 0;
  v15[0] = 0;
  v18 = 0;
  v7 = AppV::Client::Service::PackageInformationWrapper::CreatePropertiesSafeArray(
         this,
         v15,
         0x8E38E38E38E38E39uLL * ((a2[1] - *a2) >> 3),
         &v18);
  if ( (v7 & 0x8000000000LL) != 0 )
  {
    v8 = *a2;
    if ( !(0x8E38E38E38E38E39uLL * ((a2[1] - *a2) >> 3)) )
    {
LABEL_10:
      SafeArrayUnaccessData(psa[0]);
      *a3 = psa[0];
      return 0x8000000000LL;
    }
    v9 = v18;
    while ( 1 )
    {
      v10 = (const struct AppV::Client::PackageIdentity *)(v8 + 72LL * v6);
      v11 = (_WORD *)(v9 + 48LL * v6);
      v11[16] = -(*((_BYTE *)v10 + 65) != 0);
      v11[17] = 0;
      if ( (unsigned __int8)AppV::Client::Service::PackageInformationWrapper::IsPackageOrConnectionGroupPending(
                              *((_QWORD *)this + 1),
                              v10,
                              1,
                              1,
                              2 - (unsigned int)(*((_BYTE *)v10 + 65) != 0)) )
        v11[17] = -1;
      v11[18] = -(*((_BYTE *)v10 + 64) != 0);
      v11[19] = 0;
      if ( (unsigned __int8)AppV::Client::Service::PackageInformationWrapper::IsPackageOrConnectionGroupPending(
                              *((_QWORD *)this + 1),
                              v10,
                              1,
                              2,
                              2 - (unsigned int)(*((_BYTE *)v10 + 64) != 0)) )
        v11[19] = -1;
      v7 = AppV::Client::Service::PackageInformationWrapper::SetCommonPackageInformation(
             this,
             v10,
             (struct PackageProperties *)(v9 + 48LL * v6));
      if ( (v7 & 0x8000000000LL) == 0 )
        break;
      ++v6;
      v8 = *a2;
      if ( v6 >= 0x8E38E38E38E38E39uLL * ((a2[1] - *a2) >> 3) )
        goto LABEL_10;
    }
    v13 = psa[0];
    if ( psa[0] )
    {
      v14 = v15[0] == 0;
LABEL_15:
      if ( !v14 )
      {
        SafeArrayUnaccessData(v13);
        v13 = psa[0];
      }
      SafeArrayDestroy(v13);
    }
  }
  else
  {
    v13 = psa[0];
    if ( psa[0] )
    {
      v14 = v15[0] == 0;
      goto LABEL_15;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x14001a850  push    rbp
0x14001a852  push    rbx
0x14001a853  push    rsi
0x14001a854  push    rdi
0x14001a855  push    r12
0x14001a857  push    r13
0x14001a859  push    r14
0x14001a85b  push    r15
0x14001a85d  mov     rbp, rsp
0x14001a860  sub     rsp, 58h
0x14001a864  mov     r12, r8
0x14001a867  mov     rbx, rdx
0x14001a86a  mov     r15, rcx
0x14001a86d  xorps   xmm0, xmm0
0x14001a870  movdqu  xmmword ptr [rbp+psa], xmm0
0x14001a875  xor     esi, esi
0x14001a877  mov     [rbp+var_10], esi
0x14001a87a  mov     [rbp+var_28], sil
0x14001a87e  mov     [rbp+arg_8], rsi
0x14001a882  mov     r8, [rdx+8]
0x14001a886  sub     r8, [rdx]
0x14001a889  sar     r8, 3
0x14001a88d  mov     r14, 8E38E38E38E38E39h
0x14001a897  imul    r8, r14
0x14001a89b  lea     r9, [rbp+arg_8]
0x14001a89f  lea     rdx, [rbp+var_28]
0x14001a8a3  call    ?CreatePropertiesSafeArray@PackageInformationWrapper@Service@Client@AppV@@AEAA_KAEAV?$safe_array_with_structs@UPackageProperties@@@utility@appv@@IAEAPEAUPackageProperties@@@Z; AppV::Client::Service::PackageInformationWrapper::CreatePropertiesSafeArray(appv::utility::safe_array_with_structs<PackageProperties> &,uint,PackageProperties * &)
0x14001a8a8  mov     rdi, rax
0x14001a8ab  bt      rax, 27h ; '''
0x14001a8b0  jnb     loc_14001A9DB
0x14001a8b6  mov     rdx, [rbx]
0x14001a8b9  mov     rax, [rbx+8]
0x14001a8bd  sub     rax, rdx
0x14001a8c0  sar     rax, 3
0x14001a8c4  imul    rax, r14
0x14001a8c8  test    rax, rax
0x14001a8cb  jz      loc_14001A9AE
0x14001a8d1  mov     r13, [rbp+arg_8]
0x14001a8d5  mov     ecx, esi
0x14001a8d7  lea     rax, [rcx+rcx*8]
0x14001a8db  lea     r14, [rdx+rax*8]
0x14001a8df  lea     rdi, [rcx+rcx*2]
0x14001a8e3  shl     rdi, 4
0x14001a8e7  add     rdi, r13
0x14001a8ea  mov     al, [r14+41h]
0x14001a8ee  neg     al
0x14001a8f0  sbb     cx, cx
0x14001a8f3  mov     [rdi+20h], cx
0x14001a8f7  xor     eax, eax
0x14001a8f9  mov     [rdi+22h], ax
0x14001a8fd  mov     al, [r14+41h]
0x14001a901  neg     al
0x14001a903  sbb     ecx, ecx
0x14001a905  add     ecx, 2
0x14001a908  mov     [rsp+58h+var_38], ecx
0x14001a90c  mov     r9d, 1
0x14001a912  mov     r8d, r9d
0x14001a915  mov     rdx, r14
0x14001a918  mov     rcx, [r15+8]
0x14001a91c  call    ?IsPackageOrConnectionGroupPending@PackageInformationWrapper@Service@Client@AppV@@CA_NPEBVVirtualEnvironmentUtils@34@AEBUPackageIdentity@34@W4PendingType@1234@W4PendingTarget@1234@W4PendingDeployment@1234@@Z; AppV::Client::Service::PackageInformationWrapper::IsPackageOrConnectionGroupPending(AppV::Client::VirtualEnvironmentUtils const *,AppV::Client::PackageIdentity const &,AppV::Client::Service::PackageInformationWrapper::PendingType,AppV::Client::Service::PackageInformationWrapper::PendingTarget,AppV::Client::Service::PackageInformationWrapper::PendingDeployment)
0x14001a921  test    al, al
0x14001a923  jz      short loc_14001A92B
0x14001a925  mov     word ptr [rdi+22h], 0FFFFh
0x14001a92b  mov     al, [r14+40h]
0x14001a92f  neg     al
0x14001a931  sbb     cx, cx
0x14001a934  mov     [rdi+24h], cx
0x14001a938  xor     eax, eax
0x14001a93a  mov     [rdi+26h], ax
0x14001a93e  mov     al, [r14+40h]
0x14001a942  neg     al
0x14001a944  sbb     ecx, ecx
0x14001a946  add     ecx, 2
0x14001a949  mov     [rsp+58h+var_38], ecx
0x14001a94d  mov     r9d, 2
0x14001a953  lea     r8d, [r9-1]
0x14001a957  mov     rdx, r14
0x14001a95a  mov     rcx, [r15+8]
0x14001a95e  call    ?IsPackageOrConnectionGroupPending@PackageInformationWrapper@Service@Client@AppV@@CA_NPEBVVirtualEnvironmentUtils@34@AEBUPackageIdentity@34@W4PendingType@1234@W4PendingTarget@1234@W4PendingDeployment@1234@@Z; AppV::Client::Service::PackageInformationWrapper::IsPackageOrConnectionGroupPending(AppV::Client::VirtualEnvironmentUtils const *,AppV::Client::PackageIdentity const &,AppV::Client::Service::PackageInformationWrapper::PendingType,AppV::Client::Service::PackageInformationWrapper::PendingTarget,AppV::Client::Service::PackageInformationWrapper::PendingDeployment)
0x14001a963  test    al, al
0x14001a965  jz      short loc_14001A96D
0x14001a967  mov     word ptr [rdi+26h], 0FFFFh
0x14001a96d  mov     r8, rdi; struct PackageProperties *
0x14001a970  mov     rdx, r14; struct AppV::Client::PackageIdentity *
0x14001a973  mov     rcx, r15; this
0x14001a976  call    ?SetCommonPackageInformation@PackageInformationWrapper@Service@Client@AppV@@AEAA_KAEBUPackageIdentity@34@AEAUPackageProperties@@@Z; AppV::Client::Service::PackageInformationWrapper::SetCommonPackageInformation(AppV::Client::PackageIdentity const &,PackageProperties &)
0x14001a97b  mov     rdi, rax
0x14001a97e  bt      rax, 27h ; '''
0x14001a983  jnb     short loc_14001A9CC
0x14001a985  inc     esi
0x14001a987  mov     rdx, [rbx]
0x14001a98a  mov     rcx, [rbx+8]
0x14001a98e  sub     rcx, rdx
0x14001a991  sar     rcx, 3
0x14001a995  mov     rax, 8E38E38E38E38E39h
0x14001a99f  imul    rcx, rax
0x14001a9a3  mov     eax, esi
0x14001a9a5  cmp     rax, rcx
0x14001a9a8  jb      loc_14001A8D5
0x14001a9ae  mov     rcx, [rbp+psa]; psa
0x14001a9b2  call    cs:__imp_SafeArrayUnaccessData
0x14001a9b8  mov     rax, [rbp+psa]
0x14001a9bc  mov     [r12], rax
0x14001a9c0  mov     rax, 8000000000h
0x14001a9ca  jmp     short loc_14001A9FD
0x14001a9cc  mov     rcx, [rbp+psa]
0x14001a9d0  test    rcx, rcx
0x14001a9d3  jz      short loc_14001A9FA
0x14001a9d5  cmp     [rbp+var_28], 0
0x14001a9d9  jmp     short loc_14001A9E8
0x14001a9db  mov     rcx, [rbp+psa]; psa
0x14001a9df  test    rcx, rcx
0x14001a9e2  jz      short loc_14001A9FA
0x14001a9e4  cmp     [rbp+var_28], sil
0x14001a9e8  jz      short loc_14001A9F4
0x14001a9ea  call    cs:__imp_SafeArrayUnaccessData
0x14001a9f0  mov     rcx, [rbp+psa]; psa
0x14001a9f4  call    cs:__imp_SafeArrayDestroy
0x14001a9fa  mov     rax, rdi
0x14001a9fd  add     rsp, 58h
0x14001aa01  pop     r15
0x14001aa03  pop     r14
0x14001aa05  pop     r13
0x14001aa07  pop     r12
0x14001aa09  pop     rdi
0x14001aa0a  pop     rsi
0x14001aa0b  pop     rbx
0x14001aa0c  pop     rbp
0x14001aa0d  retn
```
