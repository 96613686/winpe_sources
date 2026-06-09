# AppV::Client::Service::ApplicationInformationWrapperT<AppV::Client::Service::Empty>::ConvertApplicationListToSafeArray(std::vector<AppV::Shared::VirtualApplication::VirtualApplicationData,std::allocator<AppV::Shared::VirtualApplication::VirtualApplicationData>> &,tagSAFEARRAY * *)

- ea: `0x140022c90`
- end: `0x140022fdd`
- name: `?ConvertApplicationListToSafeArray@?$ApplicationInformationWrapperT@VEmpty@Service@Client@AppV@@@Service@Client@AppV@@AEAA_KAEAV?$vector@UVirtualApplicationData@VirtualApplication@Shared@AppV@@V?$allocator@UVirtualApplicationData@VirtualApplication@Shared@AppV@@@std@@@std@@PEAPEAUtagSAFEARRAY@@@Z`
- size: `845`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x140024460`
- `0x1400246d4`

## callees

- `0x140004280`
- `0x140006304`
- `0x140018bec`
- `0x14001dbe8`
- `0x140022c90`
- `0x14003924c`
- `0x14006a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140022d2d`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140022f59`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140022d2d`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140022f59`
- `OLEAUT32!__imp_SysAllocString` at `0x140022e18`
- `OLEAUT32!__imp_SysAllocString` at `0x140022e45`
- `OLEAUT32!__imp_SysAllocString` at `0x140022e67`
- `OLEAUT32!__imp_SysAllocString` at `0x140022e80`
- `OLEAUT32!__imp_SysAllocString` at `0x140022e99`
- `OLEAUT32!__imp_SysAllocString` at `0x140022eb8`
- `OLEAUT32!__imp_SysAllocString` at `0x140022e18`
- `OLEAUT32!__imp_SysAllocString` at `0x140022e45`
- `OLEAUT32!__imp_SysAllocString` at `0x140022e67`
- `OLEAUT32!__imp_SysAllocString` at `0x140022e80`
- `OLEAUT32!__imp_SysAllocString` at `0x140022e99`
- `OLEAUT32!__imp_SysAllocString` at `0x140022eb8`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x140022fac`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x140022fac`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x140022f33`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x140022fa2`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x140022f33`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x140022fa2`
- `OLEAUT32!__imp_GetRecordInfoFromGuids` at `0x140022d0b`
- `OLEAUT32!__imp_GetRecordInfoFromGuids` at `0x140022d0b`

## string_xrefs

- `0x140022d26`: `admin\appman\appv\client\host\service\ApplicationInformationWrapper.h`
- `0x140022d3d`: `admin\appman\appv\client\host\service\ApplicationInformationWrapper.h`
- `0x140022f52`: `admin\appman\appv\client\host\service\ApplicationInformationWrapper.h`
- `0x140022f69`: `admin\appman\appv\client\host\service\ApplicationInformationWrapper.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall AppV::Client::Service::ApplicationInformationWrapperT<AppV::Client::Service::Empty>::ConvertApplicationListToSafeArray(
        __int64 a1,
        __int64 *a2,
        SAFEARRAY **a3)
{
  __int64 v5; // rdi
  __int64 v6; // rbx
  __int64 v7; // rsi
  __int64 RecordInfoFromGuids; // r14
  char *v9; // rax
  const char *v10; // rax
  unsigned __int64 v11; // rbx
  __int64 v12; // rcx
  unsigned __int64 v13; // r14
  __int64 v14; // rbx
  __int64 v15; // rsi
  __int64 v16; // rax
  __int64 v17; // rax
  const OLECHAR *v18; // rcx
  const OLECHAR *v19; // rcx
  const OLECHAR *v20; // rcx
  const OLECHAR *v21; // rcx
  BSTR v22; // rax
  char *v24; // rax
  const char *v25; // rax
  SAFEARRAY *v26; // rcx
  IRecordInfo *ppRecInfo; // [rsp+30h] [rbp-29h] BYREF
  __int64 v28; // [rsp+38h] [rbp-21h] BYREF
  _BYTE v29[8]; // [rsp+40h] [rbp-19h] BYREF
  SAFEARRAY *psa[2]; // [rsp+48h] [rbp-11h]
  int v31; // [rsp+58h] [rbp-1h]
  char *v32[4]; // [rsp+60h] [rbp+7h] BYREF

  *(_OWORD *)psa = 0;
  v31 = 0;
  v29[0] = 0;
  v5 = 0;
  v28 = 0;
  v6 = a2[1];
  v7 = *a2;
  ppRecInfo = 0;
  RecordInfoFromGuids = (unsigned int)GetRecordInfoFromGuids(
                                        &LIBID_AppVClientLib,
                                        1u,
                                        0,
                                        0,
                                        &GUID_96e2969c_49e4_4989_b957_17950f5e25d8,
                                        &ppRecInfo);
  if ( (int)RecordInfoFromGuids >= 0 )
  {
    v11 = appv::utility::safe_array_with_structs<VirtualApplicationProperties>::create_safe_array(
            v29,
            &ppRecInfo,
            -286331153 * (unsigned int)((v6 - v7) >> 4),
            &v28);
    if ( ppRecInfo )
      ((void (__fastcall *)(IRecordInfo *))ppRecInfo->lpVtbl->Release)(ppRecInfo);
    v5 = v28;
  }
  else
  {
    v9 = strrchr("admin\\appman\\appv\\client\\host\\service\\ApplicationInformationWrapper.h", 92);
    if ( v9 )
      v10 = v9 + 1;
    else
      v10 = "admin\\appman\\appv\\client\\host\\service\\ApplicationInformationWrapper.h";
    v11 = RecordInfoFromGuids
        | (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v10) << 52)
        | 0x182300000000LL;
    if ( ppRecInfo )
      ((void (__fastcall *)(IRecordInfo *))ppRecInfo->lpVtbl->Release)(ppRecInfo);
  }
  if ( (v11 & 0x8000000000LL) != 0 )
  {
    v12 = *a2;
    if ( !(0xEEEEEEEEEEEEEEEFuLL * ((a2[1] - *a2) >> 4)) )
    {
LABEL_33:
      SafeArrayUnaccessData(psa[0]);
      *a3 = psa[0];
      return 0x8000000000LL;
    }
    v13 = 0;
    while ( 1 )
    {
      v14 = 56 * v13;
      v15 = v12 + 240 * v13;
      v16 = softricity::shared::tostring(v32, v15);
      if ( *(_QWORD *)(v16 + 24) > 7u )
        v16 = *(_QWORD *)v16;
      *(_QWORD *)(v14 + v5) = SysAllocString((const OLECHAR *)v16);
      std::wstring::~wstring(v32);
      v17 = softricity::shared::tostring(v32, v15 + 16);
      if ( *(_QWORD *)(v17 + 24) > 7u )
        v17 = *(_QWORD *)v17;
      *(_QWORD *)(v14 + v5 + 8) = SysAllocString((const OLECHAR *)v17);
      std::wstring::~wstring(v32);
      v18 = (const OLECHAR *)(v15 + 32);
      if ( *(_QWORD *)(v15 + 56) > 7u )
        v18 = *(const OLECHAR **)v18;
      *(_QWORD *)(v14 + v5 + 16) = SysAllocString(v18);
      v19 = (const OLECHAR *)(v15 + 64);
      if ( *(_QWORD *)(v15 + 88) > 7u )
        v19 = *(const OLECHAR **)v19;
      *(_QWORD *)(v14 + v5 + 24) = SysAllocString(v19);
      v20 = (const OLECHAR *)(v15 + 96);
      if ( *(_QWORD *)(v15 + 120) > 7u )
        v20 = *(const OLECHAR **)v20;
      *(_QWORD *)(v14 + v5 + 32) = SysAllocString(v20);
      v21 = (const OLECHAR *)(v15 + 192);
      if ( *(_QWORD *)(v15 + 216) > 7u )
        v21 = *(const OLECHAR **)v21;
      v22 = SysAllocString(v21);
      *(_QWORD *)(v14 + v5 + 40) = v22;
      *(_WORD *)(v14 + v5 + 48) = *(_WORD *)(v15 + 224);
      *(_WORD *)(v14 + v5 + 50) = *(_WORD *)(v15 + 226);
      if ( !*(_QWORD *)(v14 + v5)
        || !*(_QWORD *)(v14 + v5 + 8)
        || !*(_QWORD *)(v14 + v5 + 16)
        || !*(_QWORD *)(v14 + v5 + 24)
        || !*(_QWORD *)(v14 + v5 + 32)
        || !v22 )
      {
        break;
      }
      ++v13;
      v12 = *a2;
      if ( v13 >= 0xEEEEEEEEEEEEEEEFuLL * ((a2[1] - *a2) >> 4) )
        goto LABEL_33;
    }
    v24 = strrchr("admin\\appman\\appv\\client\\host\\service\\ApplicationInformationWrapper.h", 92);
    if ( v24 )
      v25 = v24 + 1;
    else
      v25 = "admin\\appman\\appv\\client\\host\\service\\ApplicationInformationWrapper.h";
    v11 = (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v25) << 52)
        | 0x22230000000ELL;
  }
  v26 = psa[0];
  if ( psa[0] )
  {
    if ( v29[0] )
    {
      SafeArrayUnaccessData(psa[0]);
      v26 = psa[0];
    }
    SafeArrayDestroy(v26);
  }
  return v11;
}

```

## disassembly

```asm
0x140022c90  mov     [rsp-8+arg_0], rbx
0x140022c95  mov     [rsp-8+arg_18], rsi
0x140022c9a  push    rbp
0x140022c9b  push    rdi
0x140022c9c  push    r12
0x140022c9e  push    r14
0x140022ca0  push    r15
0x140022ca2  lea     rbp, [rsp-37h]
0x140022ca7  sub     rsp, 90h
0x140022cae  mov     rax, cs:__security_cookie
0x140022cb5  xor     rax, rsp
0x140022cb8  mov     [rbp+57h+var_30], rax
0x140022cbc  mov     r12, r8
0x140022cbf  mov     r15, rdx
0x140022cc2  xorps   xmm0, xmm0
0x140022cc5  movdqu  xmmword ptr [rbp+57h+psa], xmm0
0x140022cca  mov     [rbp+57h+var_58], 0
0x140022cd1  mov     [rbp+57h+var_70], 0
0x140022cd5  xor     edi, edi
0x140022cd7  mov     [rbp+57h+var_78], rdi
0x140022cdb  mov     rbx, [rdx+8]
0x140022cdf  mov     rsi, [rdx]
0x140022ce2  mov     [rbp+57h+var_80], rdi
0x140022ce6  lea     rax, [rbp+57h+var_80]
0x140022cea  mov     [rsp+0B0h+ppRecInfo], rax; ppRecInfo
0x140022cef  lea     rax, _GUID_96e2969c_49e4_4989_b957_17950f5e25d8
0x140022cf6  mov     [rsp+0B0h+rGuidTypeInfo], rax; rGuidTypeInfo
0x140022cfb  xor     r9d, r9d; lcid
0x140022cfe  xor     r8d, r8d; uVerMinor
0x140022d01  lea     edx, [rdi+1]; uVerMajor
0x140022d04  lea     rcx, LIBID_AppVClientLib; rGuidTypeLib
0x140022d0b  call    cs:__imp_GetRecordInfoFromGuids
0x140022d11  mov     r14d, eax
0x140022d14  mov     rax, 0EEEEEEEEEEEEEEEFh
0x140022d1e  test    r14d, r14d
0x140022d21  jns     short loc_140022D82
0x140022d23  lea     edx, [rdi+5Ch]; Ch
0x140022d26  lea     rcx, aAdminAppmanApp_23; "admin\\appman\\appv\\client\\host\\serv"...
0x140022d2d  call    cs:__imp_strrchr
0x140022d33  test    rax, rax
0x140022d36  jz      short loc_140022D3D
0x140022d38  inc     rax
0x140022d3b  jmp     short loc_140022D44
0x140022d3d  lea     rax, aAdminAppmanApp_23; "admin\\appman\\appv\\client\\host\\serv"...
0x140022d44  mov     rdx, rax; char *
0x140022d47  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140022d4e  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140022d53  mov     rbx, rax
0x140022d56  shl     rbx, 34h
0x140022d5a  or      rbx, r14
0x140022d5d  mov     rax, 182300000000h
0x140022d67  or      rbx, rax
0x140022d6a  mov     rcx, [rbp+57h+var_80]
0x140022d6e  test    rcx, rcx
0x140022d71  jz      short loc_140022D80
0x140022d73  mov     rax, [rcx]
0x140022d76  mov     rax, [rax+10h]
0x140022d7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140022d7f  nop
0x140022d80  jmp     short loc_140022DBE
0x140022d82  sub     rbx, rsi
0x140022d85  sar     rbx, 4
0x140022d89  imul    rbx, rax
0x140022d8d  lea     r9, [rbp+57h+var_78]
0x140022d91  mov     r8d, ebx
0x140022d94  lea     rdx, [rbp+57h+var_80]
0x140022d98  lea     rcx, [rbp+57h+var_70]
0x140022d9c  call    ?create_safe_array@?$safe_array_with_structs@UVirtualApplicationProperties@@@utility@appv@@QEAA_KAEBV?$CComPtr@UIRecordInfo@@@ATL@@IAEAPEAUVirtualApplicationProperties@@@Z; appv::utility::safe_array_with_structs<VirtualApplicationProperties>::create_safe_array(ATL::CComPtr<IRecordInfo> const &,uint,VirtualApplicationProperties * &)
0x140022da1  mov     rbx, rax
0x140022da4  mov     rcx, [rbp+57h+var_80]
0x140022da8  test    rcx, rcx
0x140022dab  jz      short loc_140022DBA
0x140022dad  mov     rax, [rcx]
0x140022db0  mov     rax, [rax+10h]
0x140022db4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140022db9  nop
0x140022dba  mov     rdi, [rbp+57h+var_78]
0x140022dbe  bt      rbx, 27h ; '''
0x140022dc3  jnb     loc_140022F93
0x140022dc9  mov     rcx, [r15]
0x140022dcc  mov     rax, [r15+8]
0x140022dd0  sub     rax, rcx
0x140022dd3  sar     rax, 4
0x140022dd7  mov     rdx, 0EEEEEEEEEEEEEEEFh
0x140022de1  imul    rax, rdx
0x140022de5  test    rax, rax
0x140022de8  jz      loc_140022F2F
0x140022dee  xor     r14d, r14d
0x140022df1  imul    rbx, r14, 38h ; '8'
0x140022df5  imul    rsi, r14, 0F0h
0x140022dfc  add     rsi, rcx
0x140022dff  mov     rdx, rsi
0x140022e02  lea     rcx, [rbp+57h+var_50]
0x140022e06  call    ?tostring@shared@softricity@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_GUID@@_N@Z; softricity::shared::tostring(_GUID const &,bool)
0x140022e0b  cmp     qword ptr [rax+18h], 7
0x140022e10  jbe     short loc_140022E15
0x140022e12  mov     rax, [rax]
0x140022e15  mov     rcx, rax; psz
0x140022e18  call    cs:__imp_SysAllocString
0x140022e1e  mov     [rbx+rdi], rax
0x140022e22  lea     rcx, [rbp+57h+var_50]
0x140022e26  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140022e2b  lea     rdx, [rsi+10h]
0x140022e2f  lea     rcx, [rbp+57h+var_50]
0x140022e33  call    ?tostring@shared@softricity@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_GUID@@_N@Z; softricity::shared::tostring(_GUID const &,bool)
0x140022e38  cmp     qword ptr [rax+18h], 7
0x140022e3d  jbe     short loc_140022E42
0x140022e3f  mov     rax, [rax]
0x140022e42  mov     rcx, rax; psz
0x140022e45  call    cs:__imp_SysAllocString
0x140022e4b  mov     [rbx+rdi+8], rax
0x140022e50  lea     rcx, [rbp+57h+var_50]
0x140022e54  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140022e59  lea     rcx, [rsi+20h]
0x140022e5d  cmp     qword ptr [rsi+38h], 7
0x140022e62  jbe     short loc_140022E67
0x140022e64  mov     rcx, [rcx]; psz
0x140022e67  call    cs:__imp_SysAllocString
0x140022e6d  mov     [rbx+rdi+10h], rax
0x140022e72  lea     rcx, [rsi+40h]
0x140022e76  cmp     qword ptr [rsi+58h], 7
0x140022e7b  jbe     short loc_140022E80
0x140022e7d  mov     rcx, [rcx]; psz
0x140022e80  call    cs:__imp_SysAllocString
0x140022e86  mov     [rbx+rdi+18h], rax
0x140022e8b  lea     rcx, [rsi+60h]
0x140022e8f  cmp     qword ptr [rsi+78h], 7
0x140022e94  jbe     short loc_140022E99
0x140022e96  mov     rcx, [rcx]; psz
0x140022e99  call    cs:__imp_SysAllocString
0x140022e9f  mov     [rbx+rdi+20h], rax
0x140022ea4  lea     rcx, [rsi+0C0h]
0x140022eab  cmp     qword ptr [rsi+0D8h], 7
0x140022eb3  jbe     short loc_140022EB8
0x140022eb5  mov     rcx, [rcx]; psz
0x140022eb8  call    cs:__imp_SysAllocString
0x140022ebe  mov     [rbx+rdi+28h], rax
0x140022ec3  movzx   ecx, word ptr [rsi+0E0h]
0x140022eca  mov     [rbx+rdi+30h], cx
0x140022ecf  movzx   ecx, word ptr [rsi+0E2h]
0x140022ed6  mov     [rbx+rdi+32h], cx
0x140022edb  cmp     qword ptr [rbx+rdi], 0
0x140022ee0  jz      short loc_140022F4D
0x140022ee2  cmp     qword ptr [rbx+rdi+8], 0
0x140022ee8  jz      short loc_140022F4D
0x140022eea  cmp     qword ptr [rbx+rdi+10h], 0
0x140022ef0  jz      short loc_140022F4D
0x140022ef2  cmp     qword ptr [rbx+rdi+18h], 0
0x140022ef8  jz      short loc_140022F4D
0x140022efa  cmp     qword ptr [rbx+rdi+20h], 0
0x140022f00  jz      short loc_140022F4D
0x140022f02  test    rax, rax
0x140022f05  jz      short loc_140022F4D
0x140022f07  inc     r14
0x140022f0a  mov     rcx, [r15]
0x140022f0d  mov     rax, [r15+8]
0x140022f11  sub     rax, rcx
0x140022f14  sar     rax, 4
0x140022f18  mov     rdx, 0EEEEEEEEEEEEEEEFh
0x140022f22  imul    rax, rdx
0x140022f26  cmp     r14, rax
0x140022f29  jb      loc_140022DF1
0x140022f2f  mov     rcx, [rbp+57h+psa]; psa
0x140022f33  call    cs:__imp_SafeArrayUnaccessData
0x140022f39  mov     rax, [rbp+57h+psa]
0x140022f3d  mov     [r12], rax
0x140022f41  mov     rax, 8000000000h
0x140022f4b  jmp     short loc_140022FB5
0x140022f4d  mov     edx, 5Ch ; '\'; Ch
0x140022f52  lea     rcx, aAdminAppmanApp_23; "admin\\appman\\appv\\client\\host\\serv"...
0x140022f59  call    cs:__imp_strrchr
0x140022f5f  test    rax, rax
0x140022f62  jz      short loc_140022F69
0x140022f64  inc     rax
0x140022f67  jmp     short loc_140022F70
0x140022f69  lea     rax, aAdminAppmanApp_23; "admin\\appman\\appv\\client\\host\\serv"...
0x140022f70  mov     rdx, rax; char *
0x140022f73  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140022f7a  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140022f7f  mov     rbx, rax
0x140022f82  shl     rbx, 34h
0x140022f86  mov     rax, 22230000000Eh
0x140022f90  or      rbx, rax
0x140022f93  mov     rcx, [rbp+57h+psa]; psa
0x140022f97  test    rcx, rcx
0x140022f9a  jz      short loc_140022FB2
0x140022f9c  cmp     [rbp+57h+var_70], 0
0x140022fa0  jz      short loc_140022FAC
0x140022fa2  call    cs:__imp_SafeArrayUnaccessData
0x140022fa8  mov     rcx, [rbp+57h+psa]; psa
0x140022fac  call    cs:__imp_SafeArrayDestroy
0x140022fb2  mov     rax, rbx
0x140022fb5  mov     rcx, [rbp+57h+var_30]
0x140022fb9  xor     rcx, rsp; StackCookie
0x140022fbc  call    __security_check_cookie
0x140022fc1  lea     r11, [rsp+0B0h+var_20]
0x140022fc9  mov     rbx, [r11+30h]
0x140022fcd  mov     rsi, [r11+48h]
0x140022fd1  mov     rsp, r11
0x140022fd4  pop     r15
0x140022fd6  pop     r14
0x140022fd8  pop     r12
0x140022fda  pop     rdi
0x140022fdb  pop     rbp
0x140022fdc  retn
```
