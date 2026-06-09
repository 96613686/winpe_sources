# AppV::Client::Service::AppVClientImpl::SetVirtualProcessesBuffer(std::vector<AppV::Client::VirtualProcessInformation,std::allocator<AppV::Client::VirtualProcessInformation>> &,tagSAFEARRAY * *)

- ea: `0x140037360`
- end: `0x1400376fb`
- name: `?SetVirtualProcessesBuffer@AppVClientImpl@Service@Client@AppV@@AEAA_KAEAV?$vector@UVirtualProcessInformation@Client@AppV@@V?$allocator@UVirtualProcessInformation@Client@AppV@@@std@@@std@@PEAPEAUtagSAFEARRAY@@@Z`
- size: `923`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x140023c60`
- `0x140028520`

## callees

- `0x140004280`
- `0x140006304`
- `0x140018bec`
- `0x14001d8e0`
- `0x14001dbe8`
- `0x140037360`
- `0x14006a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1400373e8`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14003764a`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1400373e8`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14003764a`
- `OLEAUT32!__imp_SysAllocString` at `0x1400374c1`
- `OLEAUT32!__imp_SysAllocString` at `0x1400374fb`
- `OLEAUT32!__imp_SysAllocString` at `0x140037523`
- `OLEAUT32!__imp_SysAllocString` at `0x140037542`
- `OLEAUT32!__imp_SysAllocString` at `0x140037561`
- `OLEAUT32!__imp_SysAllocString` at `0x1400374c1`
- `OLEAUT32!__imp_SysAllocString` at `0x1400374fb`
- `OLEAUT32!__imp_SysAllocString` at `0x140037523`
- `OLEAUT32!__imp_SysAllocString` at `0x140037542`
- `OLEAUT32!__imp_SysAllocString` at `0x140037561`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x140037629`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1400376cb`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x140037629`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1400376cb`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1400375da`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x14003761f`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1400376c1`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1400375da`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x14003761f`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1400376c1`
- `OLEAUT32!__imp_GetRecordInfoFromGuids` at `0x1400373d1`
- `OLEAUT32!__imp_GetRecordInfoFromGuids` at `0x1400373d1`

## string_xrefs

- `0x1400373e1`: `admin\appman\appv\client\host\service\publicapi.cpp`
- `0x1400373f8`: `admin\appman\appv\client\host\service\publicapi.cpp`
- `0x140037643`: `admin\appman\appv\client\host\service\publicapi.cpp`
- `0x14003765a`: `admin\appman\appv\client\host\service\publicapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall AppV::Client::Service::AppVClientImpl::SetVirtualProcessesBuffer(
        __int64 a1,
        __int64 *a2,
        SAFEARRAY **a3)
{
  HRESULT RecordInfoFromGuids; // eax
  __int64 v6; // rdi
  char *v7; // rax
  const char *v8; // rax
  unsigned __int64 v9; // rbx
  __int64 v10; // rdx
  unsigned int v11; // r15d
  __int64 v12; // rdi
  __int64 v13; // r14
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  BSTR v19; // rax
  SAFEARRAY *v20; // rax
  char v21; // dl
  SAFEARRAY *v22; // rcx
  char *v24; // rax
  const char *v25; // rax
  SAFEARRAY *v26; // rcx
  IRecordInfo *ppRecInfo; // [rsp+30h] [rbp-39h] BYREF
  _BYTE v28[8]; // [rsp+38h] [rbp-31h] BYREF
  SAFEARRAY *psa[2]; // [rsp+40h] [rbp-29h]
  int v30; // [rsp+50h] [rbp-19h]
  __int64 v31; // [rsp+58h] [rbp-11h] BYREF
  char *v32[4]; // [rsp+60h] [rbp-9h] BYREF

  *(_OWORD *)psa = 0;
  v30 = 0;
  v28[0] = 0;
  v31 = 0;
  ppRecInfo = 0;
  RecordInfoFromGuids = GetRecordInfoFromGuids(
                          &LIBID_AppVClientLib,
                          1u,
                          0,
                          0,
                          &GUID_ce1d8fb6_4b1b_45c9_b04b_2aece0cc1555,
                          &ppRecInfo);
  v6 = (unsigned int)RecordInfoFromGuids;
  if ( RecordInfoFromGuids < 0 )
  {
    v7 = strrchr("admin\\appman\\appv\\client\\host\\service\\publicapi.cpp", 92);
    if ( v7 )
      v8 = v7 + 1;
    else
      v8 = "admin\\appman\\appv\\client\\host\\service\\publicapi.cpp";
    v9 = v6
       | (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v8) << 52)
       | 0xEC2300000000LL;
    if ( ppRecInfo )
      ((void (__fastcall *)(IRecordInfo *))ppRecInfo->lpVtbl->Release)(ppRecInfo);
LABEL_42:
    v26 = psa[0];
    if ( psa[0] )
    {
      if ( v28[0] )
      {
        SafeArrayUnaccessData(psa[0]);
        v26 = psa[0];
      }
      SafeArrayDestroy(v26);
    }
    return v9;
  }
  v9 = appv::utility::safe_array_with_structs<PackageProperties>::create_safe_array(
         v28,
         &ppRecInfo,
         0xCF3CF3CF3CF3CF3DuLL * ((a2[1] - *a2) >> 3),
         &v31);
  if ( (v9 & 0x8000000000LL) == 0 )
  {
    if ( ppRecInfo )
      ((void (__fastcall *)(IRecordInfo *))ppRecInfo->lpVtbl->Release)(ppRecInfo);
    goto LABEL_42;
  }
  v10 = *a2;
  if ( 0xCF3CF3CF3CF3CF3DuLL * ((a2[1] - *a2) >> 3) )
  {
    v11 = 0;
    v12 = v31;
    while ( 1 )
    {
      v13 = 168LL * v11;
      v14 = softricity::shared::tostring(v32, v13 + v10 + 104);
      if ( *(_QWORD *)(v14 + 24) > 7u )
        v14 = *(_QWORD *)v14;
      *(_QWORD *)(v12 + 48LL * v11) = SysAllocString((const OLECHAR *)v14);
      std::wstring::~wstring(v32);
      v15 = softricity::shared::tostring(v32, v13 + *a2 + 120);
      if ( *(_QWORD *)(v15 + 24) > 7u )
        v15 = *(_QWORD *)v15;
      *(_QWORD *)(v12 + 48LL * v11 + 8) = SysAllocString((const OLECHAR *)v15);
      std::wstring::~wstring(v32);
      v16 = v13 + *a2 + 8;
      if ( *(_QWORD *)(v16 + 24) > 7u )
        v16 = *(_QWORD *)v16;
      *(_QWORD *)(v12 + 48LL * v11 + 16) = SysAllocString((const OLECHAR *)v16);
      v17 = v13 + *a2 + 40;
      if ( *(_QWORD *)(v17 + 24) > 7u )
        v17 = *(_QWORD *)v17;
      *(_QWORD *)(v12 + 48LL * v11 + 24) = SysAllocString((const OLECHAR *)v17);
      v18 = v13 + *a2 + 72;
      if ( *(_QWORD *)(v18 + 24) > 7u )
        v18 = *(_QWORD *)v18;
      v19 = SysAllocString((const OLECHAR *)v18);
      *(_QWORD *)(v12 + 48LL * v11 + 40) = v19;
      *(_DWORD *)(v12 + 48LL * v11 + 32) = *(_DWORD *)(v13 + *a2);
      if ( !*(_QWORD *)(v12 + 48LL * v11)
        || !*(_QWORD *)(v12 + 48LL * v11 + 8)
        || !*(_QWORD *)(v12 + 48LL * v11 + 16)
        || !*(_QWORD *)(v12 + 48LL * v11 + 24)
        || !v19 )
      {
        break;
      }
      ++v11;
      v10 = *a2;
      if ( v11 >= 0xCF3CF3CF3CF3CF3DuLL * ((a2[1] - *a2) >> 3) )
        goto LABEL_27;
    }
    v24 = strrchr("admin\\appman\\appv\\client\\host\\service\\publicapi.cpp", 92);
    if ( v24 )
      v25 = v24 + 1;
    else
      v25 = "admin\\appman\\appv\\client\\host\\service\\publicapi.cpp";
    v9 = (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v25) << 52)
       | 0xEE230000000ELL;
    if ( ppRecInfo )
      ((void (__fastcall *)(IRecordInfo *))ppRecInfo->lpVtbl->Release)(ppRecInfo);
    goto LABEL_42;
  }
LABEL_27:
  SafeArrayUnaccessData(psa[0]);
  v20 = psa[0];
  *(_OWORD *)psa = 0;
  v30 = 0;
  v21 = 0;
  v28[0] = 0;
  *a3 = v20;
  if ( ppRecInfo )
  {
    ((void (__fastcall *)(IRecordInfo *))ppRecInfo->lpVtbl->Release)(ppRecInfo);
    v21 = v28[0];
  }
  v22 = psa[0];
  if ( psa[0] )
  {
    if ( v21 )
    {
      SafeArrayUnaccessData(psa[0]);
      v22 = psa[0];
    }
    SafeArrayDestroy(v22);
  }
  return 0x8000000000LL;
}

```

## disassembly

```asm
0x140037360  mov     [rsp-8+arg_0], rbx
0x140037365  push    rbp
0x140037366  push    rsi
0x140037367  push    rdi
0x140037368  push    r12
0x14003736a  push    r13
0x14003736c  push    r14
0x14003736e  push    r15
0x140037370  lea     rbp, [rsp-27h]
0x140037375  sub     rsp, 90h
0x14003737c  mov     rax, cs:__security_cookie
0x140037383  xor     rax, rsp
0x140037386  mov     [rbp+57h+var_40], rax
0x14003738a  mov     r12, r8
0x14003738d  mov     rsi, rdx
0x140037390  xorps   xmm0, xmm0
0x140037393  movdqu  xmmword ptr [rbp+57h+psa], xmm0
0x140037398  xor     r13d, r13d
0x14003739b  mov     [rbp+57h+var_70], r13d
0x14003739f  mov     [rbp+57h+var_88], r13b
0x1400373a3  mov     [rbp+57h+var_68], r13
0x1400373a7  mov     [rbp+57h+var_90], r13
0x1400373ab  lea     rax, [rbp+57h+var_90]
0x1400373af  mov     [rsp+0C0h+ppRecInfo], rax; ppRecInfo
0x1400373b4  lea     rax, _GUID_ce1d8fb6_4b1b_45c9_b04b_2aece0cc1555
0x1400373bb  mov     [rsp+0C0h+rGuidTypeInfo], rax; rGuidTypeInfo
0x1400373c0  xor     r9d, r9d; lcid
0x1400373c3  xor     r8d, r8d; uVerMinor
0x1400373c6  lea     edx, [r13+1]; uVerMajor
0x1400373ca  lea     rcx, LIBID_AppVClientLib; rGuidTypeLib
0x1400373d1  call    cs:__imp_GetRecordInfoFromGuids
0x1400373d7  mov     edi, eax
0x1400373d9  test    eax, eax
0x1400373db  jns     short loc_140037440
0x1400373dd  lea     edx, [r13+5Ch]; Ch
0x1400373e1  lea     rcx, aAdminAppmanApp_4; "admin\\appman\\appv\\client\\host\\serv"...
0x1400373e8  call    cs:__imp_strrchr
0x1400373ee  test    rax, rax
0x1400373f1  jz      short loc_1400373F8
0x1400373f3  inc     rax
0x1400373f6  jmp     short loc_1400373FF
0x1400373f8  lea     rax, aAdminAppmanApp_4; "admin\\appman\\appv\\client\\host\\serv"...
0x1400373ff  mov     rdx, rax; char *
0x140037402  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140037409  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14003740e  mov     rbx, rax
0x140037411  shl     rbx, 34h
0x140037415  or      rbx, rdi
0x140037418  mov     rax, 0EC2300000000h
0x140037422  or      rbx, rax
0x140037425  mov     rcx, [rbp+57h+var_90]
0x140037429  test    rcx, rcx
0x14003742c  jz      short loc_14003743B
0x14003742e  mov     rax, [rcx]
0x140037431  mov     rax, [rax+10h]
0x140037435  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003743a  nop
0x14003743b  jmp     loc_1400376B2
0x140037440  mov     r8, [rsi+8]
0x140037444  sub     r8, [rsi]
0x140037447  sar     r8, 3
0x14003744b  mov     rdi, 0CF3CF3CF3CF3CF3Dh
0x140037455  imul    r8, rdi
0x140037459  lea     r9, [rbp+57h+var_68]
0x14003745d  lea     rdx, [rbp+57h+var_90]
0x140037461  lea     rcx, [rbp+57h+var_88]
0x140037465  call    ?create_safe_array@?$safe_array_with_structs@UPackageProperties@@@utility@appv@@QEAA_KAEBV?$CComPtr@UIRecordInfo@@@ATL@@IAEAPEAUPackageProperties@@@Z; appv::utility::safe_array_with_structs<PackageProperties>::create_safe_array(ATL::CComPtr<IRecordInfo> const &,uint,PackageProperties * &)
0x14003746a  mov     rbx, rax
0x14003746d  bt      rax, 27h ; '''
0x140037472  jnb     loc_14003769C
0x140037478  mov     rdx, [rsi]
0x14003747b  mov     rax, [rsi+8]
0x14003747f  sub     rax, rdx
0x140037482  sar     rax, 3
0x140037486  imul    rax, rdi
0x14003748a  test    rax, rax
0x14003748d  jz      loc_1400375D6
0x140037493  mov     r15d, r13d
0x140037496  mov     rdi, [rbp+57h+var_68]
0x14003749a  mov     ebx, r15d
0x14003749d  imul    r14, rbx, 0A8h
0x1400374a4  add     rdx, 68h ; 'h'
0x1400374a8  add     rdx, r14
0x1400374ab  lea     rcx, [rbp+57h+var_60]
0x1400374af  call    ?tostring@shared@softricity@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_GUID@@_N@Z; softricity::shared::tostring(_GUID const &,bool)
0x1400374b4  cmp     qword ptr [rax+18h], 7
0x1400374b9  jbe     short loc_1400374BE
0x1400374bb  mov     rax, [rax]
0x1400374be  mov     rcx, rax; psz
0x1400374c1  call    cs:__imp_SysAllocString
0x1400374c7  lea     rbx, [rbx+rbx*2]
0x1400374cb  add     rbx, rbx
0x1400374ce  mov     [rdi+rbx*8], rax
0x1400374d2  lea     rcx, [rbp+57h+var_60]
0x1400374d6  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400374db  mov     rdx, [rsi]
0x1400374de  add     rdx, 78h ; 'x'
0x1400374e2  add     rdx, r14
0x1400374e5  lea     rcx, [rbp+57h+var_60]
0x1400374e9  call    ?tostring@shared@softricity@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_GUID@@_N@Z; softricity::shared::tostring(_GUID const &,bool)
0x1400374ee  cmp     qword ptr [rax+18h], 7
0x1400374f3  jbe     short loc_1400374F8
0x1400374f5  mov     rax, [rax]
0x1400374f8  mov     rcx, rax; psz
0x1400374fb  call    cs:__imp_SysAllocString
0x140037501  mov     [rdi+rbx*8+8], rax
0x140037506  lea     rcx, [rbp+57h+var_60]
0x14003750a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14003750f  mov     rcx, [rsi]
0x140037512  add     rcx, 8
0x140037516  add     rcx, r14
0x140037519  cmp     qword ptr [rcx+18h], 7
0x14003751e  jbe     short loc_140037523
0x140037520  mov     rcx, [rcx]; psz
0x140037523  call    cs:__imp_SysAllocString
0x140037529  mov     [rdi+rbx*8+10h], rax
0x14003752e  mov     rcx, [rsi]
0x140037531  add     rcx, 28h ; '('
0x140037535  add     rcx, r14
0x140037538  cmp     qword ptr [rcx+18h], 7
0x14003753d  jbe     short loc_140037542
0x14003753f  mov     rcx, [rcx]; psz
0x140037542  call    cs:__imp_SysAllocString
0x140037548  mov     [rdi+rbx*8+18h], rax
0x14003754d  mov     rcx, [rsi]
0x140037550  add     rcx, 48h ; 'H'
0x140037554  add     rcx, r14
0x140037557  cmp     qword ptr [rcx+18h], 7
0x14003755c  jbe     short loc_140037561
0x14003755e  mov     rcx, [rcx]; psz
0x140037561  call    cs:__imp_SysAllocString
0x140037567  mov     [rdi+rbx*8+28h], rax
0x14003756c  mov     rcx, [rsi]
0x14003756f  mov     edx, [r14+rcx]
0x140037573  mov     [rdi+rbx*8+20h], edx
0x140037577  cmp     [rdi+rbx*8], r13
0x14003757b  jz      loc_14003763E
0x140037581  cmp     [rdi+rbx*8+8], r13
0x140037586  jz      loc_14003763E
0x14003758c  cmp     [rdi+rbx*8+10h], r13
0x140037591  jz      loc_14003763E
0x140037597  cmp     [rdi+rbx*8+18h], r13
0x14003759c  jz      loc_14003763E
0x1400375a2  test    rax, rax
0x1400375a5  jz      loc_14003763E
0x1400375ab  inc     r15d
0x1400375ae  mov     rdx, [rsi]
0x1400375b1  mov     rcx, [rsi+8]
0x1400375b5  sub     rcx, rdx
0x1400375b8  sar     rcx, 3
0x1400375bc  mov     rax, 0CF3CF3CF3CF3CF3Dh
0x1400375c6  imul    rcx, rax
0x1400375ca  mov     eax, r15d
0x1400375cd  cmp     rax, rcx
0x1400375d0  jb      loc_14003749A
0x1400375d6  mov     rcx, [rbp+57h+psa]; psa
0x1400375da  call    cs:__imp_SafeArrayUnaccessData
0x1400375e0  mov     rax, [rbp+57h+psa]
0x1400375e4  xorps   xmm0, xmm0
0x1400375e7  movdqu  xmmword ptr [rbp+57h+psa], xmm0
0x1400375ec  mov     [rbp+57h+var_70], r13d
0x1400375f0  mov     dl, r13b
0x1400375f3  mov     [rbp+57h+var_88], dl
0x1400375f6  mov     [r12], rax
0x1400375fa  mov     rcx, [rbp+57h+var_90]
0x1400375fe  test    rcx, rcx
0x140037601  jz      short loc_140037612
0x140037603  mov     rax, [rcx]
0x140037606  mov     rax, [rax+10h]
0x14003760a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003760f  mov     dl, [rbp+57h+var_88]
0x140037612  mov     rcx, [rbp+57h+psa]; psa
0x140037616  test    rcx, rcx
0x140037619  jz      short loc_14003762F
0x14003761b  test    dl, dl
0x14003761d  jz      short loc_140037629
0x14003761f  call    cs:__imp_SafeArrayUnaccessData
0x140037625  mov     rcx, [rbp+57h+psa]; psa
0x140037629  call    cs:__imp_SafeArrayDestroy
0x14003762f  mov     rax, 8000000000h
0x140037639  jmp     loc_1400376D4
0x14003763e  mov     edx, 5Ch ; '\'; Ch
0x140037643  lea     rcx, aAdminAppmanApp_4; "admin\\appman\\appv\\client\\host\\serv"...
0x14003764a  call    cs:__imp_strrchr
0x140037650  test    rax, rax
0x140037653  jz      short loc_14003765A
0x140037655  inc     rax
0x140037658  jmp     short loc_140037661
0x14003765a  lea     rax, aAdminAppmanApp_4; "admin\\appman\\appv\\client\\host\\serv"...
0x140037661  mov     rdx, rax; char *
0x140037664  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14003766b  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140037670  mov     rbx, rax
0x140037673  shl     rbx, 34h
0x140037677  mov     rax, 0EE230000000Eh
0x140037681  or      rbx, rax
0x140037684  mov     rcx, [rbp+57h+var_90]
0x140037688  test    rcx, rcx
0x14003768b  jz      short loc_14003769A
0x14003768d  mov     rdx, [rcx]
0x140037690  mov     rax, [rdx+10h]
0x140037694  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037699  nop
0x14003769a  jmp     short loc_1400376B2
0x14003769c  mov     rcx, [rbp+57h+var_90]
0x1400376a0  test    rcx, rcx
0x1400376a3  jz      short loc_1400376B2
0x1400376a5  mov     rax, [rcx]
0x1400376a8  mov     rax, [rax+10h]
0x1400376ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400376b1  nop
0x1400376b2  mov     rcx, [rbp+57h+psa]; psa
0x1400376b6  test    rcx, rcx
0x1400376b9  jz      short loc_1400376D1
0x1400376bb  cmp     [rbp+57h+var_88], r13b
0x1400376bf  jz      short loc_1400376CB
0x1400376c1  call    cs:__imp_SafeArrayUnaccessData
0x1400376c7  mov     rcx, [rbp+57h+psa]; psa
0x1400376cb  call    cs:__imp_SafeArrayDestroy
0x1400376d1  mov     rax, rbx
0x1400376d4  mov     rcx, [rbp+57h+var_40]
0x1400376d8  xor     rcx, rsp; StackCookie
0x1400376db  call    __security_check_cookie
0x1400376e0  mov     rbx, [rsp+0C0h+arg_0]
0x1400376e8  add     rsp, 90h
0x1400376ef  pop     r15
0x1400376f1  pop     r14
0x1400376f3  pop     r13
0x1400376f5  pop     r12
0x1400376f7  pop     rdi
0x1400376f8  pop     rsi
0x1400376f9  pop     rbp
0x1400376fa  retn
```
