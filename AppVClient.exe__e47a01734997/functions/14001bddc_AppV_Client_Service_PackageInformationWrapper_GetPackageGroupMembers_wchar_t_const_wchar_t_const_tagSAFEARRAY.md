# AppV::Client::Service::PackageInformationWrapper::GetPackageGroupMembers(wchar_t * const,wchar_t * const,tagSAFEARRAY * *)

- ea: `0x14001bddc`
- end: `0x14001bfe8`
- name: `?GetPackageGroupMembers@PackageInformationWrapper@Service@Client@AppV@@QEAA_KQEA_W0PEAPEAUtagSAFEARRAY@@@Z`
- size: `524`
- prototype: `unsigned __int64 __fastcall(AppV::Client::Service::PackageInformationWrapper *__hidden this, wchar_t *const, wchar_t *const, struct tagSAFEARRAY **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x140027930`

## callees

- `0x140018bec`
- `0x140019ff0`
- `0x14001ab08`
- `0x14001b994`
- `0x14001bddc`
- `0x14001d040`
- `0x14001d5e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14001bf9d`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14001bf9d`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14001bf12`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14001bf7c`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14001bf12`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14001bf7c`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x14001bf08`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x14001bf2e`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x14001bf72`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x14001bf08`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x14001bf2e`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x14001bf72`

## string_xrefs

- `0x14001bf96`: `admin\appman\appv\client\host\service\packageinformationwrapper.cpp`
- `0x14001bfad`: `admin\appman\appv\client\host\service\packageinformationwrapper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall AppV::Client::Service::PackageInformationWrapper::GetPackageGroupMembers(
        const struct AppV::Client::ClientCatalog **this,
        wchar_t *const a2,
        wchar_t *const a3,
        struct tagSAFEARRAY **a4)
{
  __int64 v6; // rcx
  __int64 PackageGroupMembers; // rbx
  unsigned int v8; // edi
  struct AppV::Client::PackageIdentity *v9; // rbx
  __int64 v10; // r12
  unsigned __int64 PackagePublishedState; // r14
  SAFEARRAY *v12; // rcx
  struct tagSAFEARRAY *v14; // rax
  SAFEARRAY *v15; // rcx
  char *v16; // rax
  const char *v17; // rax
  struct AppV::Client::PackageIdentity *v18[2]; // [rsp+40h] [rbp-29h] BYREF
  __int64 v19; // [rsp+50h] [rbp-19h]
  _BYTE v20[8]; // [rsp+58h] [rbp-11h] BYREF
  SAFEARRAY *psa[2]; // [rsp+60h] [rbp-9h]
  int v22; // [rsp+70h] [rbp+7h]
  __int64 v23; // [rsp+D8h] [rbp+6Fh] BYREF

  if ( !a2 || !a3 || !a4 )
  {
    v16 = strrchr("admin\\appman\\appv\\client\\host\\service\\packageinformationwrapper.cpp", 92);
    if ( v16 )
      v17 = v16 + 1;
    else
      v17 = "admin\\appman\\appv\\client\\host\\service\\packageinformationwrapper.cpp";
    return (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v17) << 52)
         | 0x1C2300000057LL;
  }
  *(_OWORD *)v18 = 0;
  v19 = 0;
  PackageGroupMembers = AppV::Client::Service::PackageInformationWrapper::GetPackageGroupMembers(this, a2, a3, v18);
  if ( (PackageGroupMembers & 0x8000000000LL) == 0 )
  {
LABEL_21:
    std::vector<AppV::Client::PackageIdentity>::~vector<AppV::Client::PackageIdentity>(v18);
    return PackageGroupMembers;
  }
  *(_OWORD *)psa = 0;
  v22 = 0;
  v20[0] = 0;
  v23 = 0;
  PackageGroupMembers = AppV::Client::Service::PackageInformationWrapper::CreatePropertiesSafeArray(
                          v6,
                          v20,
                          (v18[1] - v18[0]) >> 6,
                          &v23);
  if ( (PackageGroupMembers & 0x8000000000LL) == 0 )
  {
    v15 = psa[0];
    if ( psa[0] )
    {
      if ( v20[0] )
      {
        SafeArrayUnaccessData(psa[0]);
        v15 = psa[0];
      }
      SafeArrayDestroy(v15);
    }
    goto LABEL_21;
  }
  v8 = 0;
  v9 = v18[0];
  v10 = v23;
  while ( 1 )
  {
    if ( v9 == v18[1] )
    {
      SafeArrayUnaccessData(psa[0]);
      v14 = psa[0];
      *(_OWORD *)psa = 0;
      v22 = 0;
      v20[0] = 0;
      *a4 = v14;
      std::vector<AppV::Client::PackageIdentity>::~vector<AppV::Client::PackageIdentity>(v18);
      return 0x8000000000LL;
    }
    PackagePublishedState = AppV::Client::Service::PackageInformationWrapper::GetPackagePublishedState(
                              *this,
                              this[1],
                              v9,
                              0,
                              (__int16 *)(v10 + 48LL * v8 + 32),
                              (__int16 *)(v10 + 48LL * v8 + 34),
                              (__int16 *)(v10 + 48LL * v8 + 36),
                              (__int16 *)(v10 + 48LL * v8 + 38));
    if ( (PackagePublishedState & 0x8000000000LL) == 0 )
      break;
    PackagePublishedState = AppV::Client::Service::PackageInformationWrapper::SetCommonPackageInformation(
                              (AppV::Client::Service::PackageInformationWrapper *)this,
                              v9,
                              (struct PackageProperties *)(v10 + 48LL * v8));
    if ( (PackagePublishedState & 0x8000000000LL) == 0 )
      break;
    v9 = (struct AppV::Client::PackageIdentity *)((char *)v9 + 64);
    ++v8;
  }
  v12 = psa[0];
  if ( psa[0] )
  {
    if ( v20[0] )
    {
      SafeArrayUnaccessData(psa[0]);
      v12 = psa[0];
    }
    SafeArrayDestroy(v12);
  }
  std::vector<AppV::Client::PackageIdentity>::~vector<AppV::Client::PackageIdentity>(v18);
  return PackagePublishedState;
}

```

## disassembly

```asm
0x14001bddc  push    rbp
0x14001bdde  push    rbx
0x14001bddf  push    rsi
0x14001bde0  push    rdi
0x14001bde1  push    r12
0x14001bde3  push    r13
0x14001bde5  push    r14
0x14001bde7  push    r15
0x14001bde9  lea     rbp, [rsp-1Fh]
0x14001bdee  sub     rsp, 88h
0x14001bdf5  mov     rsi, r9
0x14001bdf8  mov     r15, rcx
0x14001bdfb  xor     r14d, r14d
0x14001bdfe  test    rdx, rdx
0x14001be01  jz      loc_14001BF91
0x14001be07  test    r8, r8
0x14001be0a  jz      loc_14001BF91
0x14001be10  test    r9, r9
0x14001be13  jz      loc_14001BF91
0x14001be19  xorps   xmm0, xmm0
0x14001be1c  movdqu  xmmword ptr [rbp+57h+var_80], xmm0
0x14001be21  mov     [rbp+57h+var_70], r14
0x14001be25  lea     r9, [rbp+57h+var_80]
0x14001be29  call    ?GetPackageGroupMembers@PackageInformationWrapper@Service@Client@AppV@@QEAA_KQEA_W0AEAV?$vector@UPackageIdentity@Client@AppV@@V?$allocator@UPackageIdentity@Client@AppV@@@std@@@std@@@Z; AppV::Client::Service::PackageInformationWrapper::GetPackageGroupMembers(wchar_t * const,wchar_t * const,std::vector<AppV::Client::PackageIdentity> &)
0x14001be2e  mov     rbx, rax
0x14001be31  bt      rax, 27h ; '''
0x14001be36  jnb     loc_14001BF83
0x14001be3c  xorps   xmm0, xmm0
0x14001be3f  movdqu  xmmword ptr [rbp+57h+psa], xmm0
0x14001be44  mov     [rbp+57h+var_50], r14d
0x14001be48  mov     [rbp+57h+var_68], r14b
0x14001be4c  mov     [rbp+57h+arg_8], r14
0x14001be50  mov     r8, [rbp+57h+var_80+8]
0x14001be54  sub     r8, [rbp+57h+var_80]
0x14001be58  sar     r8, 6
0x14001be5c  lea     r9, [rbp+57h+arg_8]
0x14001be60  lea     rdx, [rbp+57h+var_68]
0x14001be64  call    ?CreatePropertiesSafeArray@PackageInformationWrapper@Service@Client@AppV@@AEAA_KAEAV?$safe_array_with_structs@UPackageProperties@@@utility@appv@@IAEAPEAUPackageProperties@@@Z; AppV::Client::Service::PackageInformationWrapper::CreatePropertiesSafeArray(appv::utility::safe_array_with_structs<PackageProperties> &,uint,PackageProperties * &)
0x14001be69  mov     rbx, rax
0x14001be6c  bt      rax, 27h ; '''
0x14001be71  jnb     loc_14001BF63
0x14001be77  mov     edi, r14d
0x14001be7a  mov     rbx, [rbp+57h+var_80]
0x14001be7e  mov     r12, [rbp+57h+arg_8]
0x14001be82  cmp     rbx, [rbp+57h+var_80+8]
0x14001be86  jz      loc_14001BF2A
0x14001be8c  mov     eax, edi
0x14001be8e  lea     r13, [rax+rax*2]
0x14001be92  shl     r13, 4
0x14001be96  add     r13, r12
0x14001be99  lea     rax, [r13+26h]
0x14001be9d  lea     rcx, [r13+24h]
0x14001bea1  lea     rdx, [r13+22h]
0x14001bea5  lea     r9, [r13+20h]
0x14001bea9  mov     [rsp+0C0h+var_88], rax; __int16 *
0x14001beae  mov     [rsp+0C0h+var_90], rcx; __int16 *
0x14001beb3  mov     [rsp+0C0h+var_98], rdx; __int16 *
0x14001beb8  mov     [rsp+0C0h+var_A0], r9; __int16 *
0x14001bebd  xor     r9d, r9d; __int16 *
0x14001bec0  mov     r8, rbx; struct AppV::Client::PackageIdentity *
0x14001bec3  mov     rdx, [r15+8]; struct AppV::Client::VirtualEnvironmentUtils *
0x14001bec7  mov     rcx, [r15]; struct AppV::Client::ClientCatalog *
0x14001beca  call    ?GetPackagePublishedState@PackageInformationWrapper@Service@Client@AppV@@SA_KPEBVClientCatalog@34@PEBVVirtualEnvironmentUtils@34@AEBUPackageIdentity@34@PEAF3333@Z; AppV::Client::Service::PackageInformationWrapper::GetPackagePublishedState(AppV::Client::ClientCatalog const *,AppV::Client::VirtualEnvironmentUtils const *,AppV::Client::PackageIdentity const &,short *,short *,short *,short *,short *)
0x14001becf  mov     r14, rax
0x14001bed2  bt      rax, 27h ; '''
0x14001bed7  jnb     short loc_14001BEF9
0x14001bed9  mov     r8, r13; struct PackageProperties *
0x14001bedc  mov     rdx, rbx; struct AppV::Client::PackageIdentity *
0x14001bedf  mov     rcx, r15; this
0x14001bee2  call    ?SetCommonPackageInformation@PackageInformationWrapper@Service@Client@AppV@@AEAA_KAEBUPackageIdentity@34@AEAUPackageProperties@@@Z; AppV::Client::Service::PackageInformationWrapper::SetCommonPackageInformation(AppV::Client::PackageIdentity const &,PackageProperties &)
0x14001bee7  mov     r14, rax
0x14001beea  bt      rax, 27h ; '''
0x14001beef  jnb     short loc_14001BEF9
0x14001bef1  add     rbx, 40h ; '@'
0x14001bef5  inc     edi
0x14001bef7  jmp     short loc_14001BE82
0x14001bef9  mov     rcx, [rbp+57h+psa]; psa
0x14001befd  test    rcx, rcx
0x14001bf00  jz      short loc_14001BF19
0x14001bf02  cmp     [rbp+57h+var_68], 0
0x14001bf06  jz      short loc_14001BF12
0x14001bf08  call    cs:__imp_SafeArrayUnaccessData
0x14001bf0e  mov     rcx, [rbp+57h+psa]; psa
0x14001bf12  call    cs:__imp_SafeArrayDestroy
0x14001bf18  nop
0x14001bf19  lea     rcx, [rbp+57h+var_80]
0x14001bf1d  call    ??1?$vector@UPackageIdentity@Client@AppV@@V?$allocator@UPackageIdentity@Client@AppV@@@std@@@std@@QEAA@XZ; std::vector<AppV::Client::PackageIdentity>::~vector<AppV::Client::PackageIdentity>(void)
0x14001bf22  mov     rax, r14
0x14001bf25  jmp     loc_14001BFD4
0x14001bf2a  mov     rcx, [rbp+57h+psa]; psa
0x14001bf2e  call    cs:__imp_SafeArrayUnaccessData
0x14001bf34  mov     rax, [rbp+57h+psa]
0x14001bf38  xorps   xmm0, xmm0
0x14001bf3b  movdqu  xmmword ptr [rbp+57h+psa], xmm0
0x14001bf40  mov     [rbp+57h+var_50], 0
0x14001bf47  mov     [rbp+57h+var_68], 0
0x14001bf4b  mov     [rsi], rax
0x14001bf4e  lea     rcx, [rbp+57h+var_80]
0x14001bf52  call    ??1?$vector@UPackageIdentity@Client@AppV@@V?$allocator@UPackageIdentity@Client@AppV@@@std@@@std@@QEAA@XZ; std::vector<AppV::Client::PackageIdentity>::~vector<AppV::Client::PackageIdentity>(void)
0x14001bf57  mov     rax, 8000000000h
0x14001bf61  jmp     short loc_14001BFD4
0x14001bf63  mov     rcx, [rbp+57h+psa]; psa
0x14001bf67  test    rcx, rcx
0x14001bf6a  jz      short loc_14001BF83
0x14001bf6c  cmp     [rbp+57h+var_68], r14b
0x14001bf70  jz      short loc_14001BF7C
0x14001bf72  call    cs:__imp_SafeArrayUnaccessData
0x14001bf78  mov     rcx, [rbp+57h+psa]; psa
0x14001bf7c  call    cs:__imp_SafeArrayDestroy
0x14001bf82  nop
0x14001bf83  lea     rcx, [rbp+57h+var_80]
0x14001bf87  call    ??1?$vector@UPackageIdentity@Client@AppV@@V?$allocator@UPackageIdentity@Client@AppV@@@std@@@std@@QEAA@XZ; std::vector<AppV::Client::PackageIdentity>::~vector<AppV::Client::PackageIdentity>(void)
0x14001bf8c  mov     rax, rbx
0x14001bf8f  jmp     short loc_14001BFD4
0x14001bf91  mov     edx, 5Ch ; '\'; Ch
0x14001bf96  lea     rcx, aAdminAppmanApp_11; "admin\\appman\\appv\\client\\host\\serv"...
0x14001bf9d  call    cs:__imp_strrchr
0x14001bfa3  test    rax, rax
0x14001bfa6  jz      short loc_14001BFAD
0x14001bfa8  inc     rax
0x14001bfab  jmp     short loc_14001BFB4
0x14001bfad  lea     rax, aAdminAppmanApp_11; "admin\\appman\\appv\\client\\host\\serv"...
0x14001bfb4  mov     rdx, rax; char *
0x14001bfb7  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14001bfbe  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14001bfc3  shl     rax, 34h
0x14001bfc7  mov     rcx, 1C2300000057h
0x14001bfd1  or      rax, rcx
0x14001bfd4  add     rsp, 88h
0x14001bfdb  pop     r15
0x14001bfdd  pop     r14
0x14001bfdf  pop     r13
0x14001bfe1  pop     r12
0x14001bfe3  pop     rdi
0x14001bfe4  pop     rsi
0x14001bfe5  pop     rbx
0x14001bfe6  pop     rbp
0x14001bfe7  retn
```
