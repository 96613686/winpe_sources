# DeclaredConfigurationStore_EnableDisableScheduledTask(ushort const *,ushort const *,bool)

- ea: `0x180101a18`
- end: `0x180101fd9`
- name: `?DeclaredConfigurationStore_EnableDisableScheduledTask@@YAJPEBG0_N@Z`
- size: `1473`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, bool)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800ab0f0`
- `0x180113390`

## callees

- `0x18000b9e0`
- `0x18000be80`
- `0x1800117dc`
- `0x180011fe0`
- `0x180018cc4`
- `0x18001c9a4`
- `0x18009a2e4`
- `0x1800a2e5c`
- `0x180101a18`
- `0x180139010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180101d48`
- `OLEAUT32!__imp_SysFreeString` at `0x180101e3b`
- `OLEAUT32!__imp_SysFreeString` at `0x180101d48`
- `OLEAUT32!__imp_SysFreeString` at `0x180101e3b`
- `OLEAUT32!__imp_VariantInit` at `0x180101b08`
- `OLEAUT32!__imp_VariantInit` at `0x180101b2a`
- `OLEAUT32!__imp_VariantInit` at `0x180101b49`
- `OLEAUT32!__imp_VariantInit` at `0x180101b63`
- `OLEAUT32!__imp_VariantInit` at `0x180101b08`
- `OLEAUT32!__imp_VariantInit` at `0x180101b2a`
- `OLEAUT32!__imp_VariantInit` at `0x180101b49`
- `OLEAUT32!__imp_VariantInit` at `0x180101b63`
- `OLEAUT32!__imp_VariantClear` at `0x180101bf4`
- `OLEAUT32!__imp_VariantClear` at `0x180101c00`
- `OLEAUT32!__imp_VariantClear` at `0x180101c0f`
- `OLEAUT32!__imp_VariantClear` at `0x180101c1e`
- `OLEAUT32!__imp_VariantClear` at `0x180101bf4`
- `OLEAUT32!__imp_VariantClear` at `0x180101c00`
- `OLEAUT32!__imp_VariantClear` at `0x180101c0f`
- `OLEAUT32!__imp_VariantClear` at `0x180101c1e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180101a98`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180101a98`

## string_xrefs

- `0x180101de0`: `Refresh schedule created by Declared Configuration to refresh any settings changed on the device`
- `0x180101aac`: `Failed to create instance for CLSID_TaskScheduler`
- `0x180101d90`: `Failed to Get task folder %ws`
- `0x180101c30`: `Failed to Connect to TaskService`
- `0x180101f55`: `DeclaredConfigurationStore_EnableDisableScheduledTask`
- `0x180101eed`: `Failed to enable the task`
- `0x180101e7c`: `Failed to Get get the task %ws`
- `0x180101eff`: `Failed to disable the task`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall DeclaredConfigurationStore_EnableDisableScheduledTask(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned __int8 a3)
{
  unsigned __int16 v3; // r14
  HRESULT v5; // ebx
  LPVOID v7; // rdi
  __int64 (__fastcall *v8)(LPVOID, VARIANTARG *, __int128 *, __int128 *); // rbx
  __int128 v9; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v11; // xmm8
  IRecordInfo *v12; // xmm9_8
  __int128 v13; // xmm6
  IRecordInfo *v14; // xmm7_8
  int v15; // ebx
  int v16; // ecx
  int v17; // eax
  unsigned int v18; // ebx
  LPVOID v19; // rbx
  __int64 v20; // rdi
  __int64 *v21; // rax
  __int64 v22; // rdx
  int v23; // edi
  BSTR *v24; // rbx
  BSTR v25; // rcx
  _QWORD *v26; // rbx
  __int64 v27; // rdi
  __int64 *v28; // rax
  __int64 v29; // rdx
  int v30; // edi
  BSTR *v31; // rbx
  BSTR v32; // rcx
  int v33; // eax
  int v34; // ecx
  unsigned int v35; // ebx
  const wchar_t *v36; // r8
  char *v37; // [rsp+28h] [rbp-3B0h]
  LPVOID ppv; // [rsp+30h] [rbp-3A8h] BYREF
  __int64 v39; // [rsp+38h] [rbp-3A0h] BYREF
  _QWORD *v40; // [rsp+40h] [rbp-398h] BYREF
  void *Block; // [rsp+50h] [rbp-388h] BYREF
  VARIANTARG v42; // [rsp+58h] [rbp-380h] BYREF
  VARIANTARG v43; // [rsp+70h] [rbp-368h] BYREF
  VARIANTARG v44; // [rsp+88h] [rbp-350h] BYREF
  VARIANTARG pvarg; // [rsp+A0h] [rbp-338h] BYREF
  int v46[4]; // [rsp+C0h] [rbp-318h] BYREF
  IRecordInfo *v47; // [rsp+D0h] [rbp-308h]
  __int128 v48; // [rsp+E0h] [rbp-2F8h] BYREF
  IRecordInfo *v49; // [rsp+F0h] [rbp-2E8h]
  __int128 v50; // [rsp+100h] [rbp-2D8h] BYREF
  IRecordInfo *v51; // [rsp+110h] [rbp-2C8h]
  VARIANTARG v52; // [rsp+120h] [rbp-2B8h] BYREF
  unsigned __int16 v53[264]; // [rsp+140h] [rbp-298h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3D8h] [rbp+0h]

  v3 = a3;
  ppv = 0;
  v40 = 0;
  v39 = 0;
  v5 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &ppv);
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xCA3,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\cdndownload\\objectmodel\\lib\\cdndownloadapi.cpp",
      (const char *)(unsigned int)v5,
      (int)"Failed to create instance for CLSID_TaskScheduler",
      v37);
    ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(&v39);
    ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(&v40);
    ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(&ppv);
    return (unsigned int)v5;
  }
  v7 = ppv;
  v8 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int128 *, __int128 *))(*(_QWORD *)ppv + 80LL);
  VariantInit(&pvarg);
  v9 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  VariantInit(&v44);
  v11 = *(_OWORD *)&v44.vt;
  v12 = v44.pRecInfo;
  VariantInit(&v43);
  v13 = *(_OWORD *)&v43.vt;
  v14 = v43.pRecInfo;
  VariantInit(&v42);
  *(_OWORD *)v46 = v9;
  v47 = pRecInfo;
  v48 = v11;
  v49 = v12;
  v50 = v13;
  v51 = v14;
  v52 = v42;
  v15 = v8(v7, &v52, &v50, &v48);
  VariantClear(&v42);
  VariantClear(&v43);
  VariantClear(&v44);
  VariantClear(&pvarg);
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xCA6,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\cdndownload\\objectmodel\\lib\\cdndownloadapi.cpp",
      (const char *)(unsigned int)v15,
      (int)"Failed to Connect to TaskService",
      v37);
    ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(&v39);
    ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(&v40);
    ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(&ppv);
    return (unsigned int)v15;
  }
  if ( a2 )
  {
    v17 = StringCchPrintfW(v53, 0x104u, L"\\Microsoft\\Windows\\EnterpriseMgmt\\%s", a2);
    v18 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCAD,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\cdndownload\\objectmodel\\lib\\cdndownloadapi.cpp",
        (const char *)(unsigned int)v17,
        (int)v46);
      ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(&v39);
      ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(&v40);
      ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(&ppv);
      return v18;
    }
    v19 = ppv;
    v20 = *(_QWORD *)ppv;
    v21 = *(__int64 **)_bstr_t::_bstr_t((_bstr_t *)&Block, v53);
    if ( v21 )
      v22 = *v21;
    else
      v22 = 0;
    v23 = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD **))(v20 + 56))(v19, v22, &v40);
    v24 = (BSTR *)Block;
    if ( Block && _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v24 )
    {
      if ( *v24 )
      {
        SysFreeString(*v24);
        *v24 = 0;
      }
      v25 = v24[1];
      if ( v25 )
      {
        operator delete(v25);
        v24[1] = 0;
      }
      operator delete(v24);
    }
    if ( v23 < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0xCB7,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\cdndownload\\objectmodel\\lib\\cdndownloadapi.cpp",
        (const char *)(unsigned int)v23,
        (int)"Failed to Get task folder %ws",
        L"\\Microsoft\\Windows\\EnterpriseMgmt");
      ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(&v39);
      ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(&v40);
      ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(&ppv);
      return (unsigned int)v23;
    }
    v26 = v40;
    v27 = *v40;
    v28 = *(__int64 **)_bstr_t::_bstr_t(
                         (_bstr_t *)&Block,
                         L"Refresh schedule created by Declared Configuration to refresh any settings changed on the device");
    if ( v28 )
      v29 = *v28;
    else
      v29 = 0;
    v30 = (*(__int64 (__fastcall **)(_QWORD *, __int64, __int64 *))(v27 + 104))(v26, v29, &v39);
    v31 = (BSTR *)Block;
    if ( Block && _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v31 )
    {
      if ( *v31 )
      {
        SysFreeString(*v31);
        *v31 = 0;
      }
      v32 = v31[1];
      if ( v32 )
      {
        operator delete(v32);
        v31[1] = 0;
      }
      operator delete(v31);
    }
    if ( v30 < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0xCBA,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\cdndownload\\objectmodel\\lib\\cdndownloadapi.cpp",
        (const char *)(unsigned int)v30,
        (int)"Failed to Get get the task %ws",
        (const char *)L"Refresh schedule created by Declared Configuration to refresh any settings changed on the device");
      ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(&v39);
      ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(&v40);
      ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(&ppv);
      return (unsigned int)v30;
    }
    v33 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v39 + 88LL))(v39, v3);
    v35 = v33;
    if ( v33 >= 0 )
      goto LABEL_41;
    if ( (_BYTE)v3 )
    {
      if ( byte_180189FC1 < 0 )
      {
        v36 = L"Failed to enable the task";
LABEL_40:
        McTemplateU0zzd_EventWriteTransfer(
          v34,
          (unsigned int)OrchestratorGenericFailure,
          (_DWORD)v36,
          (unsigned int)L"Refresh schedule created by Declared Configuration to refresh any settings changed on the device",
          v33);
      }
    }
    else if ( byte_180189FC1 < 0 )
    {
      v36 = L"Failed to disable the task";
      goto LABEL_40;
    }
LABEL_41:
    ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(&v39);
    ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(&v40);
    ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(&ppv);
    return v35;
  }
  if ( byte_180189FC1 < 0 )
    McTemplateU0zzd_EventWriteTransfer(
      v16,
      (unsigned int)OrchestratorGenericFailure,
      (unsigned int)L"DeclaredConfigurationStore_EnableDisableScheduledTask",
      (unsigned int)L"enrollmentId cannot be null",
      87);
  ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(&v39);
  ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(&v40);
  ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(&ppv);
  return 2147942487LL;
}

```

## disassembly

```asm
0x180101a18  mov     rax, rsp
0x180101a1b  mov     [rax+8], rbx
0x180101a1f  push    rsi
0x180101a20  push    rdi
0x180101a21  push    r14
0x180101a23  sub     rsp, 3C0h
0x180101a2a  movaps  xmmword ptr [rax-28h], xmm6
0x180101a2e  movaps  xmmword ptr [rax-38h], xmm7
0x180101a32  movaps  xmmword ptr [rax-48h], xmm8
0x180101a37  movaps  xmmword ptr [rax-58h], xmm9
0x180101a3c  movaps  xmmword ptr [rax-68h], xmm10
0x180101a41  movaps  xmmword ptr [rax-78h], xmm11
0x180101a46  mov     rax, cs:__security_cookie
0x180101a4d  xor     rax, rsp
0x180101a50  mov     [rsp+3D8h+var_88], rax
0x180101a58  movzx   r14d, r8b
0x180101a5c  mov     rsi, rdx
0x180101a5f  mov     [rsp+3D8h+var_3A8], 0
0x180101a68  mov     [rsp+3D8h+var_398], 0
0x180101a71  mov     [rsp+3D8h+var_3A0], 0
0x180101a7a  lea     rax, [rsp+3D8h+var_3A8]
0x180101a7f  mov     [rsp+3D8h+ppv], rax; ppv
0x180101a84  lea     r9, IID_ITaskService; riid
0x180101a8b  xor     edx, edx; pUnkOuter
0x180101a8d  lea     r8d, [rdx+1]; dwClsContext
0x180101a91  lea     rcx, CLSID_TaskScheduler; rclsid
0x180101a98  call    cs:__imp_CoCreateInstance
0x180101a9e  mov     ebx, eax
0x180101aa0  test    eax, eax
0x180101aa2  jns     short loc_180101AF4
0x180101aa4  mov     rcx, [rsp+3D8h]; this
0x180101aac  lea     rax, aFailedToCreate; "Failed to create instance for CLSID_Tas"...
0x180101ab3  mov     [rsp+3D8h+ppv], rax; int
0x180101ab8  mov     r9d, ebx; char *
0x180101abb  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\cdnd"...
0x180101ac2  mov     edx, 0CA3h; void *
0x180101ac7  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180101acc  nop
0x180101acd  lea     rcx, [rsp+3D8h+var_3A0]
0x180101ad2  call    ??1?$CComPtrBase@UIClientSecurity@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(void)
0x180101ad7  nop
0x180101ad8  lea     rcx, [rsp+3D8h+var_398]
0x180101add  call    ??1?$CComPtrBase@UIClientSecurity@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(void)
0x180101ae2  nop
0x180101ae3  lea     rcx, [rsp+3D8h+var_3A8]
0x180101ae8  call    ??1?$CComPtrBase@UIClientSecurity@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(void)
0x180101aed  mov     eax, ebx
0x180101aef  jmp     loc_180101F96
0x180101af4  mov     rdi, [rsp+3D8h+var_3A8]
0x180101af9  mov     rax, [rdi]
0x180101afc  mov     rbx, [rax+50h]
0x180101b00  lea     rcx, [rsp+3D8h+pvarg]; pvarg
0x180101b08  call    cs:__imp_VariantInit
0x180101b0e  nop
0x180101b0f  movups  xmm10, xmmword ptr [rsp+3D8h+pvarg]
0x180101b18  movsd   xmm11, qword ptr [rsp+3D8h+pvarg+10h]
0x180101b22  lea     rcx, [rsp+3D8h+var_350]; pvarg
0x180101b2a  call    cs:__imp_VariantInit
0x180101b30  nop
0x180101b31  movups  xmm8, xmmword ptr [rsp+3D8h+var_350]
0x180101b3a  movsd   xmm9, qword ptr [rsp+3D8h+var_350+10h]
0x180101b44  lea     rcx, [rsp+3D8h+var_368]; pvarg
0x180101b49  call    cs:__imp_VariantInit
0x180101b4f  nop
0x180101b50  movups  xmm6, xmmword ptr [rsp+3D8h+var_368]
0x180101b55  movsd   xmm7, qword ptr [rsp+3D8h+var_368+10h]
0x180101b5e  lea     rcx, [rsp+3D8h+var_380]; pvarg
0x180101b63  call    cs:__imp_VariantInit
0x180101b69  nop
0x180101b6a  movups  xmm0, xmmword ptr [rsp+3D8h+var_380]
0x180101b6f  movsd   xmm1, qword ptr [rsp+3D8h+var_380+10h]
0x180101b75  movaps  xmmword ptr [rsp+3D8h+var_318], xmm10
0x180101b7e  movsd   [rsp+3D8h+var_308], xmm11
0x180101b88  movaps  [rsp+3D8h+var_2F8], xmm8
0x180101b91  movsd   [rsp+3D8h+var_2E8], xmm9
0x180101b9b  movaps  [rsp+3D8h+var_2D8], xmm6
0x180101ba3  movsd   [rsp+3D8h+var_2C8], xmm7
0x180101bac  movaps  [rsp+3D8h+var_2B8], xmm0
0x180101bb4  movsd   [rsp+3D8h+var_2A8], xmm1
0x180101bbd  lea     rax, [rsp+3D8h+var_318]
0x180101bc5  mov     [rsp+3D8h+ppv], rax; int
0x180101bca  lea     r9, [rsp+3D8h+var_2F8]
0x180101bd2  lea     r8, [rsp+3D8h+var_2D8]
0x180101bda  lea     rdx, [rsp+3D8h+var_2B8]
0x180101be2  mov     rcx, rdi
0x180101be5  mov     rax, rbx
0x180101be8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180101bed  mov     ebx, eax
0x180101bef  lea     rcx, [rsp+3D8h+var_380]; pvarg
0x180101bf4  call    cs:__imp_VariantClear
0x180101bfa  nop
0x180101bfb  lea     rcx, [rsp+3D8h+var_368]; pvarg
0x180101c00  call    cs:__imp_VariantClear
0x180101c06  nop
0x180101c07  lea     rcx, [rsp+3D8h+var_350]; pvarg
0x180101c0f  call    cs:__imp_VariantClear
0x180101c15  nop
0x180101c16  lea     rcx, [rsp+3D8h+pvarg]; pvarg
0x180101c1e  call    cs:__imp_VariantClear
0x180101c24  test    ebx, ebx
0x180101c26  jns     short loc_180101C78
0x180101c28  mov     rcx, [rsp+3D8h]; this
0x180101c30  lea     rax, aFailedToConnec; "Failed to Connect to TaskService"
0x180101c37  mov     [rsp+3D8h+ppv], rax; int
0x180101c3c  mov     r9d, ebx; char *
0x180101c3f  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\cdnd"...
0x180101c46  mov     edx, 0CA6h; void *
0x180101c4b  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180101c50  nop
0x180101c51  lea     rcx, [rsp+3D8h+var_3A0]
0x180101c56  call    ??1?$CComPtrBase@UIClientSecurity@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(void)
0x180101c5b  nop
0x180101c5c  lea     rcx, [rsp+3D8h+var_398]
0x180101c61  call    ??1?$CComPtrBase@UIClientSecurity@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(void)
0x180101c66  nop
0x180101c67  lea     rcx, [rsp+3D8h+var_3A8]
0x180101c6c  call    ??1?$CComPtrBase@UIClientSecurity@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(void)
0x180101c71  mov     eax, ebx
0x180101c73  jmp     loc_180101F96
0x180101c78  test    rsi, rsi
0x180101c7b  jz      loc_180101F3D
0x180101c81  mov     r9, rsi
0x180101c84  lea     r8, aMicrosoftWindo; "\\Microsoft\\Windows\\EnterpriseMgmt\\%"...
0x180101c8b  mov     edx, 104h; unsigned __int64
0x180101c90  lea     rcx, [rsp+3D8h+var_298]; unsigned __int16 *
0x180101c98  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180101c9d  mov     ebx, eax
0x180101c9f  test    eax, eax
0x180101ca1  jns     short loc_180101CE7
0x180101ca3  mov     rcx, [rsp+3D8h]; this
0x180101cab  mov     r9d, eax; char *
0x180101cae  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\cdnd"...
0x180101cb5  mov     edx, 0CADh; void *
0x180101cba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180101cbf  nop
0x180101cc0  lea     rcx, [rsp+3D8h+var_3A0]
0x180101cc5  call    ??1?$CComPtrBase@UIClientSecurity@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(void)
0x180101cca  nop
0x180101ccb  lea     rcx, [rsp+3D8h+var_398]
0x180101cd0  call    ??1?$CComPtrBase@UIClientSecurity@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(void)
0x180101cd5  nop
0x180101cd6  lea     rcx, [rsp+3D8h+var_3A8]
0x180101cdb  call    ??1?$CComPtrBase@UIClientSecurity@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(void)
0x180101ce0  mov     eax, ebx
0x180101ce2  jmp     loc_180101F96
0x180101ce7  mov     rbx, [rsp+3D8h+var_3A8]
0x180101cec  mov     rdi, [rbx]
0x180101cef  lea     rdx, [rsp+3D8h+var_298]; unsigned __int16 *
0x180101cf7  lea     rcx, [rsp+3D8h+Block]; this
0x180101cfc  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180101d01  nop
0x180101d02  mov     rax, [rax]
0x180101d05  test    rax, rax
0x180101d08  jz      short loc_180101D0F
0x180101d0a  mov     rdx, [rax]
0x180101d0d  jmp     short loc_180101D11
0x180101d0f  xor     edx, edx
0x180101d11  lea     r8, [rsp+3D8h+var_398]
0x180101d16  mov     rcx, rbx
0x180101d19  mov     rax, [rdi+38h]
0x180101d1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180101d22  mov     edi, eax
0x180101d24  mov     rbx, [rsp+3D8h+Block]
0x180101d29  test    rbx, rbx
0x180101d2c  jz      short loc_180101D78
0x180101d2e  or      ecx, 0FFFFFFFFh
0x180101d31  lock xadd [rbx+10h], ecx
0x180101d36  cmp     ecx, 1
0x180101d39  jnz     short loc_180101D78
0x180101d3b  test    rbx, rbx
0x180101d3e  jz      short loc_180101D78
0x180101d40  mov     rcx, [rbx]; bstrString
0x180101d43  test    rcx, rcx
0x180101d46  jz      short loc_180101D55
0x180101d48  call    cs:__imp_SysFreeString
0x180101d4e  mov     qword ptr [rbx], 0
0x180101d55  mov     rcx, [rbx+8]; Block
0x180101d59  test    rcx, rcx
0x180101d5c  jz      short loc_180101D6B
0x180101d5e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180101d63  mov     qword ptr [rbx+8], 0
0x180101d6b  mov     edx, 18h
0x180101d70  mov     rcx, rbx; Block
0x180101d73  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180101d78  test    edi, edi
0x180101d7a  jns     short loc_180101DD8
0x180101d7c  mov     rcx, [rsp+3D8h]; this
0x180101d84  lea     rax, aMicrosoftWindo_0; "\\Microsoft\\Windows\\EnterpriseMgmt"
0x180101d8b  mov     [rsp+3D8h+var_3B0], rax; char *
0x180101d90  lea     rax, aFailedToGetTas; "Failed to Get task folder %ws"
0x180101d97  mov     [rsp+3D8h+ppv], rax; int
0x180101d9c  mov     r9d, edi; char *
0x180101d9f  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\cdnd"...
0x180101da6  mov     edx, 0CB7h; void *
0x180101dab  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180101db0  nop
0x180101db1  lea     rcx, [rsp+3D8h+var_3A0]
0x180101db6  call    ??1?$CComPtrBase@UIClientSecurity@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(void)
0x180101dbb  nop
0x180101dbc  lea     rcx, [rsp+3D8h+var_398]
0x180101dc1  call    ??1?$CComPtrBase@UIClientSecurity@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(void)
0x180101dc6  nop
0x180101dc7  lea     rcx, [rsp+3D8h+var_3A8]
0x180101dcc  call    ??1?$CComPtrBase@UIClientSecurity@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(void)
0x180101dd1  mov     eax, edi
0x180101dd3  jmp     loc_180101F96
0x180101dd8  mov     rbx, [rsp+3D8h+var_398]
0x180101ddd  mov     rdi, [rbx]
0x180101de0  lea     rsi, aRefreshSchedul; "Refresh schedule created by Declared Co"...
0x180101de7  mov     rdx, rsi; unsigned __int16 *
0x180101dea  lea     rcx, [rsp+3D8h+Block]; this
0x180101def  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180101df4  nop
0x180101df5  mov     rax, [rax]
0x180101df8  test    rax, rax
0x180101dfb  jz      short loc_180101E02
0x180101dfd  mov     rdx, [rax]
0x180101e00  jmp     short loc_180101E04
0x180101e02  xor     edx, edx
0x180101e04  lea     r8, [rsp+3D8h+var_3A0]
0x180101e09  mov     rcx, rbx
0x180101e0c  mov     rax, [rdi+68h]
0x180101e10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180101e15  mov     edi, eax
0x180101e17  mov     rbx, [rsp+3D8h+Block]
0x180101e1c  test    rbx, rbx
0x180101e1f  jz      short loc_180101E6B
0x180101e21  or      ecx, 0FFFFFFFFh
0x180101e24  lock xadd [rbx+10h], ecx
0x180101e29  cmp     ecx, 1
0x180101e2c  jnz     short loc_180101E6B
0x180101e2e  test    rbx, rbx
0x180101e31  jz      short loc_180101E6B
0x180101e33  mov     rcx, [rbx]; bstrString
0x180101e36  test    rcx, rcx
0x180101e39  jz      short loc_180101E48
0x180101e3b  call    cs:__imp_SysFreeString
0x180101e41  mov     qword ptr [rbx], 0
0x180101e48  mov     rcx, [rbx+8]; Block
0x180101e4c  test    rcx, rcx
0x180101e4f  jz      short loc_180101E5E
0x180101e51  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180101e56  mov     qword ptr [rbx+8], 0
0x180101e5e  mov     edx, 18h
0x180101e63  mov     rcx, rbx; Block
0x180101e66  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180101e6b  test    edi, edi
0x180101e6d  jns     short loc_180101EC4
0x180101e6f  mov     rcx, [rsp+3D8h]; this
0x180101e77  mov     [rsp+3D8h+var_3B0], rsi; char *
0x180101e7c  lea     rax, aFailedToGetGet; "Failed to Get get the task %ws"
0x180101e83  mov     [rsp+3D8h+ppv], rax; int
0x180101e88  mov     r9d, edi; char *
0x180101e8b  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\cdnd"...
0x180101e92  mov     edx, 0CBAh; void *
0x180101e97  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180101e9c  nop
0x180101e9d  lea     rcx, [rsp+3D8h+var_3A0]
0x180101ea2  call    ??1?$CComPtrBase@UIClientSecurity@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(void)
0x180101ea7  nop
0x180101ea8  lea     rcx, [rsp+3D8h+var_398]
0x180101ead  call    ??1?$CComPtrBase@UIClientSecurity@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(void)
0x180101eb2  nop
0x180101eb3  lea     rcx, [rsp+3D8h+var_3A8]
0x180101eb8  call    ??1?$CComPtrBase@UIClientSecurity@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(void)
0x180101ebd  mov     eax, edi
0x180101ebf  jmp     loc_180101F96
0x180101ec4  mov     rcx, [rsp+3D8h+var_3A0]
0x180101ec9  mov     rax, [rcx]
0x180101ecc  movzx   edx, r14w
0x180101ed0  mov     rax, [rax+58h]
0x180101ed4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180101ed9  mov     ebx, eax
0x180101edb  test    eax, eax
0x180101edd  jns     short loc_180101F1A
0x180101edf  test    r14b, r14b
0x180101ee2  jz      short loc_180101EF6
0x180101ee4  cmp     cs:byte_180189FC1, 0
0x180101eeb  jge     short loc_180101F1A
0x180101eed  lea     r8, aFailedToEnable; "Failed to enable the task"
0x180101ef4  jmp     short loc_180101F06
0x180101ef6  cmp     cs:byte_180189FC1, 0
0x180101efd  jge     short loc_180101F1A
0x180101eff  lea     r8, aFailedToDisabl; "Failed to disable the task"
0x180101f06  mov     dword ptr [rsp+3D8h+ppv], eax
0x180101f0a  mov     r9, rsi
0x180101f0d  lea     rdx, OrchestratorGenericFailure
0x180101f14  call    McTemplateU0zzd_EventWriteTransfer
0x180101f19  nop
0x180101f1a  lea     rcx, [rsp+3D8h+var_3A0]
0x180101f1f  call    ??1?$CComPtrBase@UIClientSecurity@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(void)
0x180101f24  nop
0x180101f25  lea     rcx, [rsp+3D8h+var_398]
0x180101f2a  call    ??1?$CComPtrBase@UIClientSecurity@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(void)
0x180101f2f  nop
0x180101f30  lea     rcx, [rsp+3D8h+var_3A8]
0x180101f35  call    ??1?$CComPtrBase@UIClientSecurity@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(void)
0x180101f3a  nop
0x180101f3b  jmp     short loc_180101F94
0x180101f3d  cmp     cs:byte_180189FC1, 0
  ... truncated ...
```
