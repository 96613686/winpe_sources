# DeclaredConfigurationStore_DeleteScheduledTask(ushort const *,ushort const *)

- ea: `0x180101544`
- end: `0x180101a11`
- name: `?DeclaredConfigurationStore_DeleteScheduledTask@@YAJPEBG0@Z`
- size: `1229`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800abdf0`
- `0x180113390`
- `0x18011440c`

## callees

- `0x18000b9e0`
- `0x18000be80`
- `0x1800117dc`
- `0x180011fe0`
- `0x18001c9a4`
- `0x18009a2e4`
- `0x1800a2e5c`
- `0x180101544`
- `0x180139010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180101897`
- `OLEAUT32!__imp_SysFreeString` at `0x180101973`
- `OLEAUT32!__imp_SysFreeString` at `0x180101897`
- `OLEAUT32!__imp_SysFreeString` at `0x180101973`
- `OLEAUT32!__imp_VariantInit` at `0x18010161d`
- `OLEAUT32!__imp_VariantInit` at `0x18010163f`
- `OLEAUT32!__imp_VariantInit` at `0x18010165e`
- `OLEAUT32!__imp_VariantInit` at `0x180101675`
- `OLEAUT32!__imp_VariantInit` at `0x18010161d`
- `OLEAUT32!__imp_VariantInit` at `0x18010163f`
- `OLEAUT32!__imp_VariantInit` at `0x18010165e`
- `OLEAUT32!__imp_VariantInit` at `0x180101675`
- `OLEAUT32!__imp_VariantClear` at `0x180101706`
- `OLEAUT32!__imp_VariantClear` at `0x180101712`
- `OLEAUT32!__imp_VariantClear` at `0x180101721`
- `OLEAUT32!__imp_VariantClear` at `0x180101730`
- `OLEAUT32!__imp_VariantClear` at `0x180101706`
- `OLEAUT32!__imp_VariantClear` at `0x180101712`
- `OLEAUT32!__imp_VariantClear` at `0x180101721`
- `OLEAUT32!__imp_VariantClear` at `0x180101730`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801015b8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801015b8`

## string_xrefs

- `0x18010191d`: `Refresh schedule created by Declared Configuration to refresh any settings changed on the device`
- `0x1801015cc`: `Failed to create instance for CLSID_TaskScheduler`
- `0x1801018d8`: `Failed to Get task folder %ws`
- `0x180101742`: `Failed to Connect to TaskService`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
__int64 __fastcall DeclaredConfigurationStore_DeleteScheduledTask(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2)
{
  HRESULT v3; // ebx
  LPVOID v5; // rdi
  __int64 (__fastcall *v6)(LPVOID, VARIANTARG *, __int128 *, __int128 *); // rbx
  __int128 v7; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v9; // xmm8
  IRecordInfo *v10; // xmm9_8
  __int128 v11; // xmm6
  IRecordInfo *v12; // xmm7_8
  int v13; // ebx
  int v14; // eax
  unsigned int v15; // ebx
  int v16; // eax
  unsigned int v17; // ebx
  LPVOID v18; // rbx
  __int64 v19; // rsi
  __int64 *v20; // rax
  __int64 v21; // rdx
  int v22; // esi
  BSTR *v23; // rbx
  BSTR v24; // rcx
  _QWORD *v25; // rbx
  __int64 v26; // rdi
  __int64 *v27; // rax
  __int64 v28; // rdx
  unsigned int v29; // edi
  BSTR *v30; // rbx
  BSTR v31; // rcx
  unsigned int v32; // ebx
  char *v33; // [rsp+28h] [rbp-390h]
  LPVOID ppv; // [rsp+30h] [rbp-388h] BYREF
  _QWORD *v35; // [rsp+38h] [rbp-380h] BYREF
  void *Block; // [rsp+48h] [rbp-370h] BYREF
  VARIANTARG v37; // [rsp+50h] [rbp-368h] BYREF
  VARIANTARG v38; // [rsp+68h] [rbp-350h] BYREF
  VARIANTARG v39; // [rsp+80h] [rbp-338h] BYREF
  VARIANTARG pvarg; // [rsp+98h] [rbp-320h] BYREF
  int v41[4]; // [rsp+B0h] [rbp-308h] BYREF
  IRecordInfo *v42; // [rsp+C0h] [rbp-2F8h]
  __int128 v43; // [rsp+D0h] [rbp-2E8h] BYREF
  IRecordInfo *v44; // [rsp+E0h] [rbp-2D8h]
  __int128 v45; // [rsp+F0h] [rbp-2C8h] BYREF
  IRecordInfo *v46; // [rsp+100h] [rbp-2B8h]
  VARIANTARG v47; // [rsp+110h] [rbp-2A8h] BYREF
  unsigned __int16 v48[264]; // [rsp+130h] [rbp-288h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3B8h] [rbp+0h]

  ppv = 0;
  v35 = 0;
  v3 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &ppv);
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xC6F,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\cdndownload\\objectmodel\\lib\\cdndownloadapi.cpp",
      (const char *)(unsigned int)v3,
      (int)"Failed to create instance for CLSID_TaskScheduler",
      v33);
    ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(&v35);
    ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(&ppv);
    return (unsigned int)v3;
  }
  v5 = ppv;
  v6 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int128 *, __int128 *))(*(_QWORD *)ppv + 80LL);
  VariantInit(&pvarg);
  v7 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  VariantInit(&v39);
  v9 = *(_OWORD *)&v39.vt;
  v10 = v39.pRecInfo;
  VariantInit(&v38);
  v11 = *(_OWORD *)&v38.vt;
  v12 = v38.pRecInfo;
  VariantInit(&v37);
  *(_OWORD *)v41 = v7;
  v42 = pRecInfo;
  v43 = v9;
  v44 = v10;
  v45 = v11;
  v46 = v12;
  v47 = v37;
  v13 = v6(v5, &v47, &v45, &v43);
  VariantClear(&v37);
  VariantClear(&v38);
  VariantClear(&v39);
  VariantClear(&pvarg);
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xC72,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\cdndownload\\objectmodel\\lib\\cdndownloadapi.cpp",
      (const char *)(unsigned int)v13,
      (int)"Failed to Connect to TaskService",
      v33);
    ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(&v35);
    ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(&ppv);
    return (unsigned int)v13;
  }
  if ( a2 )
  {
    v14 = StringCchPrintfW(v48, 0x104u, L"\\Microsoft\\Windows\\EnterpriseMgmt\\%s", a2);
    v15 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC79,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\cdndownload\\objectmodel\\lib\\cdndownloadapi.cpp",
        (const char *)(unsigned int)v14,
        (int)v41);
      ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(&v35);
      ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(&ppv);
      return v15;
    }
  }
  else
  {
    v16 = StringCchPrintfW(v48, 0x104u, L"\\Microsoft\\Windows\\EnterpriseMgmt");
    v17 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC7F,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\cdndownload\\objectmodel\\lib\\cdndownloadapi.cpp",
        (const char *)(unsigned int)v16,
        (int)v41);
      ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(&v35);
      ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(&ppv);
      return v17;
    }
  }
  v18 = ppv;
  v19 = *(_QWORD *)ppv;
  v20 = *(__int64 **)_bstr_t::_bstr_t((_bstr_t *)&Block, v48);
  if ( v20 )
    v21 = *v20;
  else
    v21 = 0;
  v22 = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD **))(v19 + 56))(v18, v21, &v35);
  v23 = (BSTR *)Block;
  if ( Block && _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v23 )
  {
    if ( *v23 )
    {
      SysFreeString(*v23);
      *v23 = 0;
    }
    v24 = v23[1];
    if ( v24 )
    {
      operator delete(v24);
      v23[1] = 0;
    }
    operator delete(v23);
  }
  if ( v22 >= 0 )
  {
    v25 = v35;
    v26 = *v35;
    v27 = *(__int64 **)_bstr_t::_bstr_t(
                         (_bstr_t *)&Block,
                         L"Refresh schedule created by Declared Configuration to refresh any settings changed on the device");
    if ( v27 )
      v28 = *v27;
    else
      v28 = 0;
    v29 = (*(__int64 (__fastcall **)(_QWORD *, __int64, _QWORD))(v26 + 120))(v25, v28, 0);
    v30 = (BSTR *)Block;
    if ( Block && _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v30 )
    {
      if ( *v30 )
      {
        SysFreeString(*v30);
        *v30 = 0;
      }
      v31 = v30[1];
      if ( v31 )
      {
        operator delete(v31);
        v30[1] = 0;
      }
      operator delete(v30);
    }
    v32 = 0;
    if ( v29 != -2147024894 )
      v32 = v29;
    ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(&v35);
    ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(&ppv);
    return v32;
  }
  else
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xC83,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\cdndownload\\objectmodel\\lib\\cdndownloadapi.cpp",
      (const char *)(unsigned int)v22,
      (int)"Failed to Get task folder %ws",
      L"\\Microsoft\\Windows\\EnterpriseMgmt");
    ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(&v35);
    ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(&ppv);
    return (unsigned int)v22;
  }
}

```

## disassembly

```asm
0x180101544  mov     rax, rsp
0x180101547  mov     [rax+8], rbx
0x18010154b  mov     [rax+18h], rsi
0x18010154f  push    rdi
0x180101550  sub     rsp, 3B0h
0x180101557  movaps  xmmword ptr [rax-18h], xmm6
0x18010155b  movaps  xmmword ptr [rax-28h], xmm7
0x18010155f  movaps  xmmword ptr [rax-38h], xmm8
0x180101564  movaps  xmmword ptr [rax-48h], xmm9
0x180101569  movaps  xmmword ptr [rax-58h], xmm10
0x18010156e  movaps  xmmword ptr [rax-68h], xmm11
0x180101573  mov     rax, cs:__security_cookie
0x18010157a  xor     rax, rsp
0x18010157d  mov     [rsp+3B8h+var_78], rax
0x180101585  mov     rsi, rdx
0x180101588  mov     [rsp+3B8h+var_388], 0
0x180101591  mov     [rsp+3B8h+var_380], 0
0x18010159a  lea     rax, [rsp+3B8h+var_388]
0x18010159f  mov     [rsp+3B8h+ppv], rax; ppv
0x1801015a4  lea     r9, IID_ITaskService; riid
0x1801015ab  xor     edx, edx; pUnkOuter
0x1801015ad  lea     r8d, [rdx+1]; dwClsContext
0x1801015b1  lea     rcx, CLSID_TaskScheduler; rclsid
0x1801015b8  call    cs:__imp_CoCreateInstance
0x1801015be  mov     ebx, eax
0x1801015c0  test    eax, eax
0x1801015c2  jns     short loc_180101609
0x1801015c4  mov     rcx, [rsp+3B8h]; this
0x1801015cc  lea     rax, aFailedToCreate; "Failed to create instance for CLSID_Tas"...
0x1801015d3  mov     [rsp+3B8h+ppv], rax; int
0x1801015d8  mov     r9d, ebx; char *
0x1801015db  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\cdnd"...
0x1801015e2  mov     edx, 0C6Fh; void *
0x1801015e7  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1801015ec  nop
0x1801015ed  lea     rcx, [rsp+3B8h+var_380]
0x1801015f2  call    ??1?$CComPtrBase@UIClientSecurity@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(void)
0x1801015f7  nop
0x1801015f8  lea     rcx, [rsp+3B8h+var_388]
0x1801015fd  call    ??1?$CComPtrBase@UIClientSecurity@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(void)
0x180101602  mov     eax, ebx
0x180101604  jmp     loc_1801019CD
0x180101609  mov     rdi, [rsp+3B8h+var_388]
0x18010160e  mov     rax, [rdi]
0x180101611  mov     rbx, [rax+50h]
0x180101615  lea     rcx, [rsp+3B8h+pvarg]; pvarg
0x18010161d  call    cs:__imp_VariantInit
0x180101623  nop
0x180101624  movups  xmm10, xmmword ptr [rsp+3B8h+pvarg]
0x18010162d  movsd   xmm11, qword ptr [rsp+3B8h+pvarg+10h]
0x180101637  lea     rcx, [rsp+3B8h+var_338]; pvarg
0x18010163f  call    cs:__imp_VariantInit
0x180101645  nop
0x180101646  movups  xmm8, xmmword ptr [rsp+3B8h+var_338]
0x18010164f  movsd   xmm9, qword ptr [rsp+3B8h+var_338+10h]
0x180101659  lea     rcx, [rsp+3B8h+var_350]; pvarg
0x18010165e  call    cs:__imp_VariantInit
0x180101664  nop
0x180101665  movups  xmm6, xmmword ptr [rsp+3B8h+var_350]
0x18010166a  movsd   xmm7, qword ptr [rsp+3B8h+var_350+10h]
0x180101670  lea     rcx, [rsp+3B8h+var_368]; pvarg
0x180101675  call    cs:__imp_VariantInit
0x18010167b  nop
0x18010167c  movups  xmm0, xmmword ptr [rsp+3B8h+var_368]
0x180101681  movsd   xmm1, qword ptr [rsp+3B8h+var_368+10h]
0x180101687  movaps  xmmword ptr [rsp+3B8h+var_308], xmm10
0x180101690  movsd   [rsp+3B8h+var_2F8], xmm11
0x18010169a  movaps  [rsp+3B8h+var_2E8], xmm8
0x1801016a3  movsd   [rsp+3B8h+var_2D8], xmm9
0x1801016ad  movaps  [rsp+3B8h+var_2C8], xmm6
0x1801016b5  movsd   [rsp+3B8h+var_2B8], xmm7
0x1801016be  movaps  [rsp+3B8h+var_2A8], xmm0
0x1801016c6  movsd   [rsp+3B8h+var_298], xmm1
0x1801016cf  lea     rax, [rsp+3B8h+var_308]
0x1801016d7  mov     [rsp+3B8h+ppv], rax; int
0x1801016dc  lea     r9, [rsp+3B8h+var_2E8]
0x1801016e4  lea     r8, [rsp+3B8h+var_2C8]
0x1801016ec  lea     rdx, [rsp+3B8h+var_2A8]
0x1801016f4  mov     rcx, rdi
0x1801016f7  mov     rax, rbx
0x1801016fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801016ff  mov     ebx, eax
0x180101701  lea     rcx, [rsp+3B8h+var_368]; pvarg
0x180101706  call    cs:__imp_VariantClear
0x18010170c  nop
0x18010170d  lea     rcx, [rsp+3B8h+var_350]; pvarg
0x180101712  call    cs:__imp_VariantClear
0x180101718  nop
0x180101719  lea     rcx, [rsp+3B8h+var_338]; pvarg
0x180101721  call    cs:__imp_VariantClear
0x180101727  nop
0x180101728  lea     rcx, [rsp+3B8h+pvarg]; pvarg
0x180101730  call    cs:__imp_VariantClear
0x180101736  test    ebx, ebx
0x180101738  jns     short loc_18010177F
0x18010173a  mov     rcx, [rsp+3B8h]; this
0x180101742  lea     rax, aFailedToConnec; "Failed to Connect to TaskService"
0x180101749  mov     [rsp+3B8h+ppv], rax; int
0x18010174e  mov     r9d, ebx; char *
0x180101751  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\cdnd"...
0x180101758  mov     edx, 0C72h; void *
0x18010175d  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180101762  nop
0x180101763  lea     rcx, [rsp+3B8h+var_380]
0x180101768  call    ??1?$CComPtrBase@UIClientSecurity@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(void)
0x18010176d  nop
0x18010176e  lea     rcx, [rsp+3B8h+var_388]
0x180101773  call    ??1?$CComPtrBase@UIClientSecurity@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(void)
0x180101778  mov     eax, ebx
0x18010177a  jmp     loc_1801019CD
0x18010177f  mov     edx, 104h; unsigned __int64
0x180101784  lea     rcx, [rsp+3B8h+var_288]; unsigned __int16 *
0x18010178c  test    rsi, rsi
0x18010178f  jz      short loc_1801017E8
0x180101791  mov     r9, rsi
0x180101794  lea     r8, aMicrosoftWindo; "\\Microsoft\\Windows\\EnterpriseMgmt\\%"...
0x18010179b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801017a0  mov     ebx, eax
0x1801017a2  test    eax, eax
0x1801017a4  jns     short loc_1801017DF
0x1801017a6  mov     rcx, [rsp+3B8h]; this
0x1801017ae  mov     r9d, eax; char *
0x1801017b1  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\cdnd"...
0x1801017b8  mov     edx, 0C79h; void *
0x1801017bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801017c2  nop
0x1801017c3  lea     rcx, [rsp+3B8h+var_380]
0x1801017c8  call    ??1?$CComPtrBase@UIClientSecurity@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(void)
0x1801017cd  nop
0x1801017ce  lea     rcx, [rsp+3B8h+var_388]
0x1801017d3  call    ??1?$CComPtrBase@UIClientSecurity@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(void)
0x1801017d8  mov     eax, ebx
0x1801017da  jmp     loc_1801019CD
0x1801017df  lea     rdi, aMicrosoftWindo_0; "\\Microsoft\\Windows\\EnterpriseMgmt"
0x1801017e6  jmp     short loc_180101836
0x1801017e8  lea     rdi, aMicrosoftWindo_0; "\\Microsoft\\Windows\\EnterpriseMgmt"
0x1801017ef  mov     r8, rdi; unsigned __int16 *
0x1801017f2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801017f7  mov     ebx, eax
0x1801017f9  test    eax, eax
0x1801017fb  jns     short loc_180101836
0x1801017fd  mov     rcx, [rsp+3B8h]; this
0x180101805  mov     r9d, eax; char *
0x180101808  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\cdnd"...
0x18010180f  mov     edx, 0C7Fh; void *
0x180101814  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180101819  nop
0x18010181a  lea     rcx, [rsp+3B8h+var_380]
0x18010181f  call    ??1?$CComPtrBase@UIClientSecurity@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(void)
0x180101824  nop
0x180101825  lea     rcx, [rsp+3B8h+var_388]
0x18010182a  call    ??1?$CComPtrBase@UIClientSecurity@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(void)
0x18010182f  mov     eax, ebx
0x180101831  jmp     loc_1801019CD
0x180101836  mov     rbx, [rsp+3B8h+var_388]
0x18010183b  mov     rsi, [rbx]
0x18010183e  lea     rdx, [rsp+3B8h+var_288]; unsigned __int16 *
0x180101846  lea     rcx, [rsp+3B8h+Block]; this
0x18010184b  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180101850  nop
0x180101851  mov     rax, [rax]
0x180101854  test    rax, rax
0x180101857  jz      short loc_18010185E
0x180101859  mov     rdx, [rax]
0x18010185c  jmp     short loc_180101860
0x18010185e  xor     edx, edx
0x180101860  lea     r8, [rsp+3B8h+var_380]
0x180101865  mov     rcx, rbx
0x180101868  mov     rax, [rsi+38h]
0x18010186c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180101871  mov     esi, eax
0x180101873  mov     rbx, [rsp+3B8h+Block]
0x180101878  test    rbx, rbx
0x18010187b  jz      short loc_1801018C7
0x18010187d  or      ecx, 0FFFFFFFFh
0x180101880  lock xadd [rbx+10h], ecx
0x180101885  cmp     ecx, 1
0x180101888  jnz     short loc_1801018C7
0x18010188a  test    rbx, rbx
0x18010188d  jz      short loc_1801018C7
0x18010188f  mov     rcx, [rbx]; bstrString
0x180101892  test    rcx, rcx
0x180101895  jz      short loc_1801018A4
0x180101897  call    cs:__imp_SysFreeString
0x18010189d  mov     qword ptr [rbx], 0
0x1801018a4  mov     rcx, [rbx+8]; Block
0x1801018a8  test    rcx, rcx
0x1801018ab  jz      short loc_1801018BA
0x1801018ad  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801018b2  mov     qword ptr [rbx+8], 0
0x1801018ba  mov     edx, 18h
0x1801018bf  mov     rcx, rbx; Block
0x1801018c2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801018c7  test    esi, esi
0x1801018c9  jns     short loc_180101915
0x1801018cb  mov     rcx, [rsp+3B8h]; this
0x1801018d3  mov     [rsp+3B8h+var_390], rdi; char *
0x1801018d8  lea     rax, aFailedToGetTas; "Failed to Get task folder %ws"
0x1801018df  mov     [rsp+3B8h+ppv], rax; int
0x1801018e4  mov     r9d, esi; char *
0x1801018e7  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\cdnd"...
0x1801018ee  mov     edx, 0C83h; void *
0x1801018f3  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1801018f8  nop
0x1801018f9  lea     rcx, [rsp+3B8h+var_380]
0x1801018fe  call    ??1?$CComPtrBase@UIClientSecurity@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(void)
0x180101903  nop
0x180101904  lea     rcx, [rsp+3B8h+var_388]
0x180101909  call    ??1?$CComPtrBase@UIClientSecurity@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(void)
0x18010190e  mov     eax, esi
0x180101910  jmp     loc_1801019CD
0x180101915  mov     rbx, [rsp+3B8h+var_380]
0x18010191a  mov     rdi, [rbx]
0x18010191d  lea     rdx, aRefreshSchedul; "Refresh schedule created by Declared Co"...
0x180101924  lea     rcx, [rsp+3B8h+Block]; this
0x180101929  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18010192e  nop
0x18010192f  mov     rax, [rax]
0x180101932  test    rax, rax
0x180101935  jz      short loc_18010193C
0x180101937  mov     rdx, [rax]
0x18010193a  jmp     short loc_18010193E
0x18010193c  xor     edx, edx
0x18010193e  xor     r8d, r8d
0x180101941  mov     rcx, rbx
0x180101944  mov     rax, [rdi+78h]
0x180101948  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010194d  mov     edi, eax
0x18010194f  mov     rbx, [rsp+3B8h+Block]
0x180101954  test    rbx, rbx
0x180101957  jz      short loc_1801019A4
0x180101959  or      ecx, 0FFFFFFFFh
0x18010195c  lock xadd [rbx+10h], ecx
0x180101961  cmp     ecx, 1
0x180101964  jnz     short loc_1801019A4
0x180101966  test    rbx, rbx
0x180101969  jz      short loc_1801019A4
0x18010196b  mov     rcx, [rbx]; bstrString
0x18010196e  test    rcx, rcx
0x180101971  jz      short loc_180101980
0x180101973  call    cs:__imp_SysFreeString
0x180101979  mov     qword ptr [rbx], 0
0x180101980  mov     rcx, [rbx+8]; Block
0x180101984  test    rcx, rcx
0x180101987  jz      short loc_180101996
0x180101989  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18010198e  mov     qword ptr [rbx+8], 0
0x180101996  mov     edx, 18h
0x18010199b  mov     rcx, rbx; Block
0x18010199e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801019a3  nop
0x1801019a4  xor     ebx, ebx
0x1801019a6  cmp     edi, 80070002h
0x1801019ac  cmovnz  ebx, edi
0x1801019af  lea     rcx, [rsp+3B8h+var_380]
0x1801019b4  call    ??1?$CComPtrBase@UIClientSecurity@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(void)
0x1801019b9  nop
0x1801019ba  lea     rcx, [rsp+3B8h+var_388]
0x1801019bf  call    ??1?$CComPtrBase@UIClientSecurity@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(void)
0x1801019c4  nop
0x1801019c5  jmp     short loc_1801019CB
0x1801019c7  mov     ebx, [rsp+3B8h+var_378]
0x1801019cb  mov     eax, ebx
0x1801019cd  mov     rcx, [rsp+3B8h+var_78]
0x1801019d5  xor     rcx, rsp; StackCookie
0x1801019d8  call    __security_check_cookie
0x1801019dd  lea     r11, [rsp+3B8h+var_8]
0x1801019e5  mov     rbx, [r11+10h]
0x1801019e9  mov     rsi, [r11+20h]
0x1801019ed  movaps  xmm6, xmmword ptr [r11-10h]
0x1801019f2  movaps  xmm7, xmmword ptr [r11-20h]
0x1801019f7  movaps  xmm8, xmmword ptr [r11-30h]
0x1801019fc  movaps  xmm9, xmmword ptr [r11-40h]
0x180101a01  movaps  xmm10, xmmword ptr [r11-50h]
0x180101a06  movaps  xmm11, xmmword ptr [r11-60h]
0x180101a0b  mov     rsp, r11
0x180101a0e  pop     rdi
0x180101a0f  retn
```
