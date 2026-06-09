# CDBFolder::GetAliasesFromScopeItems_Old(IObjectArray *,IShellItemArray * *)

- ea: `0x180084c10`
- end: `0x180084ec8`
- name: `?GetAliasesFromScopeItems_Old@CDBFolder@@AEAAJPEAUIObjectArray@@PEAPEAUIShellItemArray@@@Z`
- size: `696`
- prototype: `int(CDBFolder *__hidden this, struct IObjectArray *, struct IShellItemArray **)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18005feb0`

## callees

- `0x180014ae0`
- `0x180016d1c`
- `0x18004fe14`
- `0x180056d84`
- `0x180061108`
- `0x180062160`
- `0x180063a68`
- `0x180063f24`
- `0x180084c10`
- `0x1800ea010`

## import_xrefs

- `Windows.Storage!SHGetIDListFromObject` at `0x180084d5a`
- `Windows.Storage!SHGetIDListFromObject` at `0x180084d5a`
- `Windows.Storage!SHCreateShellItemArrayFromIDLists` at `0x180084ddb`
- `Windows.Storage!SHCreateShellItemArrayFromIDLists` at `0x180084ddb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180084d97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180084e27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180084d97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180084e27`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CDBFolder::GetAliasesFromScopeItems_Old(
        CDBFolder *this,
        struct IObjectArray *a2,
        struct IShellItemArray **a3)
{
  HRESULT v5; // ebx
  __int64 v6; // rdx
  unsigned int v7; // edi
  struct IObjectArrayVtbl *lpVtbl; // rax
  int v9; // eax
  __int64 v10; // rax
  int v11; // eax
  LPVOID v12; // rdx
  int appended; // eax
  void *v14; // rcx
  HRESULT v15; // eax
  __int64 v16; // r9
  __int64 v17; // rdx
  unsigned __int64 v18; // r9
  __int64 v19; // rdx
  void *v20; // rcx
  __int64 v21; // rdx
  int v23; // [rsp+20h] [rbp-48h]
  __int64 v24; // [rsp+30h] [rbp-38h] BYREF
  __int64 *v25; // [rsp+38h] [rbp-30h] BYREF
  LPVOID *p_pv; // [rsp+40h] [rbp-28h] BYREF
  LPITEMIDLIST ppidl; // [rsp+48h] [rbp-20h] BYREF
  char v28; // [rsp+50h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+30h]
  CDBFolder *v30; // [rsp+A0h] [rbp+38h] BYREF
  int v31; // [rsp+A8h] [rbp+40h] BYREF
  LPVOID pv; // [rsp+B0h] [rbp+48h] BYREF
  IUnknown *punk; // [rsp+B8h] [rbp+50h] BYREF

  v30 = this;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_FileExplorerDehydratedThumbnailsRenderFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_FileExplorerDehydratedThumbnailsRenderFix>::GetImpl'::`2'::impl) )
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45690266>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FI45690266>::GetImpl'::`2'::impl);
  *a3 = 0;
  LODWORD(v30) = 0;
  v5 = ((__int64 (__fastcall *)(struct IObjectArray *, CDBFolder **))a2->lpVtbl->GetCount)(a2, &v30);
  if ( v5 >= 0 )
  {
    if ( !(_DWORD)v30 )
    {
      v5 = -2147467259;
      v6 = 8879;
      goto LABEL_5;
    }
    v24 = 0;
    if ( (unsigned int)CDPA_Base<CResultArray::CResultRange,CTContainer_PolicyUnOwned<CResultArray::CResultRange>>::Create(
                         &v24,
                         (unsigned int)v30) )
    {
      v7 = 0;
      if ( (_DWORD)v30 )
      {
        while ( 1 )
        {
          lpVtbl = a2->lpVtbl;
          v25 = 0;
          v9 = ((__int64 (__fastcall *)(struct IObjectArray *, _QWORD, GUID *, __int64 **))lpVtbl->GetAt)(
                 a2,
                 v7,
                 &GUID_dd400ff4_a119_405f_970e_a9a5e7e828c0,
                 &v25);
          v5 = v9;
          if ( v9 < 0 )
            break;
          v31 = 0;
          v9 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v25 + 32))(v25, &v31);
          v5 = v9;
          if ( v9 < 0 )
          {
            v21 = 8891;
            goto LABEL_32;
          }
          if ( v31 == 1 )
          {
            punk = 0;
            v10 = *v25;
            punk = 0;
            v11 = (*(__int64 (__fastcall **)(__int64 *, GUID *, IUnknown **))(v10 + 120))(
                    v25,
                    &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                    &punk);
            v5 = v11;
            if ( v11 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x22C0,
                (unsigned int)"onecoreuap\\shell\\windows.storage.search\\dbfolder.cpp",
                (const char *)(unsigned int)v11,
                v23);
              goto LABEL_29;
            }
            pv = 0;
            p_pv = &pv;
            ppidl = 0;
            v28 = 1;
            v5 = SHGetIDListFromObject(punk, &ppidl);
            wil::details::out_param_t<wistd::unique_ptr<_ITEMIDLIST_RELATIVE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMIDLIST_RELATIVE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
            if ( v5 < 0 )
            {
              v18 = (unsigned int)v5;
              v19 = 8899;
              goto LABEL_26;
            }
            v12 = pv;
            pv = 0;
            appended = CDPA_Base<IScopeItem,CTContainer_PolicyUnOwned<IScopeItem>>::AppendPtr(&v24, v12);
            v5 = appended;
            if ( appended < 0 )
            {
              v18 = (unsigned int)appended;
              v19 = 8901;
LABEL_26:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v19,
                (unsigned int)"onecoreuap\\shell\\windows.storage.search\\dbfolder.cpp",
                (const char *)v18,
                v23);
              v20 = pv;
              pv = 0;
              if ( v20 )
                CoTaskMemFree(v20);
LABEL_29:
              wil::com_ptr_t<IInitializeSortColumnArray,wil::err_exception_policy>::~com_ptr_t<IInitializeSortColumnArray,wil::err_exception_policy>(&punk);
              goto LABEL_33;
            }
            v14 = pv;
            pv = 0;
            if ( v14 )
              CoTaskMemFree(v14);
            wil::com_ptr_t<IInitializeSortColumnArray,wil::err_exception_policy>::~com_ptr_t<IInitializeSortColumnArray,wil::err_exception_policy>(&punk);
          }
          wil::com_ptr_t<IInitializeSortColumnArray,wil::err_exception_policy>::~com_ptr_t<IInitializeSortColumnArray,wil::err_exception_policy>(&v25);
          if ( ++v7 >= (unsigned int)v30 )
            goto LABEL_20;
        }
        v21 = 8888;
LABEL_32:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v21,
          (unsigned int)"onecoreuap\\shell\\windows.storage.search\\dbfolder.cpp",
          (const char *)(unsigned int)v9,
          v23);
LABEL_33:
        wil::com_ptr_t<IInitializeSortColumnArray,wil::err_exception_policy>::~com_ptr_t<IInitializeSortColumnArray,wil::err_exception_policy>(&v25);
        goto LABEL_39;
      }
LABEL_20:
      if ( v24 && *(_DWORD *)v24 )
      {
        v15 = SHCreateShellItemArrayFromIDLists(*(_DWORD *)v24, *(LPCITEMIDLIST **)(v24 + 8), a3);
        v5 = v15;
        if ( v15 >= 0 )
        {
          CDPA_Base<unsigned short,CTContainer_PolicyCoTaskMem>::~CDPA_Base<unsigned short,CTContainer_PolicyCoTaskMem>(&v24);
          return 0;
        }
        v16 = (unsigned int)v15;
        v17 = 8906;
        goto LABEL_38;
      }
      v17 = 8905;
    }
    else
    {
      v17 = 8883;
    }
    v5 = -2147467259;
    v16 = 2147500037LL;
LABEL_38:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecoreuap\\shell\\windows.storage.search\\dbfolder.cpp",
      (const char *)v16,
      v23);
LABEL_39:
    CDPA_Base<unsigned short,CTContainer_PolicyCoTaskMem>::~CDPA_Base<unsigned short,CTContainer_PolicyCoTaskMem>(&v24);
    return (unsigned int)v5;
  }
  v6 = 8878;
LABEL_5:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"onecoreuap\\shell\\windows.storage.search\\dbfolder.cpp",
    (const char *)(unsigned int)v5,
    v23);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180084c10  mov     [rsp-30h+arg_0], rcx
0x180084c15  push    rbp
0x180084c16  push    rbx
0x180084c17  push    rsi
0x180084c18  push    rdi
0x180084c19  push    r14
0x180084c1b  push    r15
0x180084c1d  mov     rbp, rsp
0x180084c20  sub     rsp, 68h
0x180084c24  mov     r14, r8
0x180084c27  mov     rsi, rdx
0x180084c2a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_FileExplorerDehydratedThumbnailsRenderFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_FileExplorerDehydratedThumbnailsRenderFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_FileExplorerDehydratedThumbnailsRenderFix> `wil::Feature<__WilFeatureTraits_Feature_Servicing_FileExplorerDehydratedThumbnailsRenderFix>::GetImpl(void)'::`2'::impl
0x180084c31  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_FileExplorerDehydratedThumbnailsRenderFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_FileExplorerDehydratedThumbnailsRenderFix>::__private_IsEnabled(void)
0x180084c36  xor     r15d, r15d
0x180084c39  test    al, al
0x180084c3b  jnz     short loc_180084C49
0x180084c3d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FI45690266@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FI45690266@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45690266> `wil::Feature<__WilFeatureTraits_Feature_FI45690266>::GetImpl(void)'::`2'::impl
0x180084c44  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FI45690266@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45690266>::__private_IsEnabled(void)
0x180084c49  mov     [r14], r15
0x180084c4c  mov     dword ptr [rbp+arg_0], r15d
0x180084c50  mov     rax, [rsi]
0x180084c53  lea     rdx, [rbp+arg_0]
0x180084c57  mov     rcx, rsi
0x180084c5a  mov     rax, [rax+18h]
0x180084c5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084c63  mov     ebx, eax
0x180084c65  test    eax, eax
0x180084c67  jns     short loc_180084C86
0x180084c69  mov     edx, 22AEh; void *
0x180084c6e  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\windows.storage.sear"...
0x180084c75  mov     r9d, ebx; char *
0x180084c78  mov     rcx, [rbp+30h]; this
0x180084c7c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180084c81  jmp     loc_180084EB9
0x180084c86  mov     edx, dword ptr [rbp+arg_0]
0x180084c89  test    edx, edx
0x180084c8b  jnz     short loc_180084C99
0x180084c8d  mov     ebx, 80004005h
0x180084c92  mov     edx, 22AFh
0x180084c97  jmp     short loc_180084C6E
0x180084c99  mov     [rbp+var_38], r15
0x180084c9d  lea     rcx, [rbp+var_38]
0x180084ca1  call    ?Create@?$CDPA_Base@VCResultRange@CResultArray@@V?$CTContainer_PolicyUnOwned@VCResultRange@CResultArray@@@@@@QEAAHH@Z; CDPA_Base<CResultArray::CResultRange,CTContainer_PolicyUnOwned<CResultArray::CResultRange>>::Create(int)
0x180084ca6  test    eax, eax
0x180084ca8  jz      loc_180084E92
0x180084cae  mov     edi, r15d
0x180084cb1  cmp     dword ptr [rbp+arg_0], r15d
0x180084cb5  jbe     loc_180084DBC
0x180084cbb  mov     rax, [rsi]
0x180084cbe  mov     [rbp+var_30], r15
0x180084cc2  lea     r9, [rbp+var_30]
0x180084cc6  lea     r8, _GUID_dd400ff4_a119_405f_970e_a9a5e7e828c0
0x180084ccd  mov     edx, edi
0x180084ccf  mov     rcx, rsi
0x180084cd2  mov     rax, [rax+20h]
0x180084cd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084cdb  mov     ebx, eax
0x180084cdd  test    eax, eax
0x180084cdf  js      loc_180084E5A
0x180084ce5  mov     [rbp+arg_8], r15d
0x180084ce9  mov     rcx, [rbp+var_30]
0x180084ced  mov     rax, [rcx]
0x180084cf0  lea     rdx, [rbp+arg_8]
0x180084cf4  mov     rax, [rax+20h]
0x180084cf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084cfd  mov     ebx, eax
0x180084cff  test    eax, eax
0x180084d01  js      loc_180084E53
0x180084d07  cmp     [rbp+arg_8], 1
0x180084d0b  jnz     loc_180084DA8
0x180084d11  mov     [rbp+punk], r15
0x180084d15  mov     rcx, [rbp+var_30]
0x180084d19  mov     rax, [rcx]
0x180084d1c  mov     [rbp+punk], r15
0x180084d20  lea     r8, [rbp+punk]
0x180084d24  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe
0x180084d2b  mov     rax, [rax+78h]
0x180084d2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084d34  mov     ebx, eax
0x180084d36  test    eax, eax
0x180084d38  js      loc_180084E2F
0x180084d3e  mov     [rbp+pv], r15
0x180084d42  lea     rax, [rbp+pv]
0x180084d46  mov     [rbp+var_28], rax
0x180084d4a  mov     [rbp+ppidl], r15
0x180084d4e  mov     [rbp+var_18], 1
0x180084d52  lea     rdx, [rbp+ppidl]; ppidl
0x180084d56  mov     rcx, [rbp+punk]; punk
0x180084d5a  call    cs:__imp_SHGetIDListFromObject
0x180084d60  mov     ebx, eax
0x180084d62  lea     rcx, [rbp+var_28]
0x180084d66  call    ??1?$out_param_t@V?$unique_ptr@U_ITEMIDLIST_RELATIVE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_ITEMIDLIST_RELATIVE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMIDLIST_RELATIVE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180084d6b  test    ebx, ebx
0x180084d6d  js      loc_180084E02
0x180084d73  mov     rdx, [rbp+pv]
0x180084d77  mov     [rbp+pv], r15
0x180084d7b  lea     rcx, [rbp+var_38]
0x180084d7f  call    ?AppendPtr@?$CDPA_Base@UIScopeItem@@V?$CTContainer_PolicyUnOwned@UIScopeItem@@@@@@QEAAJPEAUIScopeItem@@PEAH@Z; CDPA_Base<IScopeItem,CTContainer_PolicyUnOwned<IScopeItem>>::AppendPtr(IScopeItem *,int *)
0x180084d84  mov     ebx, eax
0x180084d86  test    eax, eax
0x180084d88  js      short loc_180084DF8
0x180084d8a  mov     rcx, [rbp+pv]; pv
0x180084d8e  mov     [rbp+pv], r15
0x180084d92  test    rcx, rcx
0x180084d95  jz      short loc_180084D9E
0x180084d97  call    cs:__imp_CoTaskMemFree
0x180084d9d  nop
0x180084d9e  lea     rcx, [rbp+punk]
0x180084da2  call    ??1?$com_ptr_t@UIInitializeSortColumnArray@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IInitializeSortColumnArray,wil::err_exception_policy>::~com_ptr_t<IInitializeSortColumnArray,wil::err_exception_policy>(void)
0x180084da7  nop
0x180084da8  lea     rcx, [rbp+var_30]
0x180084dac  call    ??1?$com_ptr_t@UIInitializeSortColumnArray@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IInitializeSortColumnArray,wil::err_exception_policy>::~com_ptr_t<IInitializeSortColumnArray,wil::err_exception_policy>(void)
0x180084db1  inc     edi
0x180084db3  cmp     edi, dword ptr [rbp+arg_0]
0x180084db6  jb      loc_180084CBB
0x180084dbc  mov     rcx, [rbp+var_38]
0x180084dc0  test    rcx, rcx
0x180084dc3  jz      loc_180084E8B
0x180084dc9  cmp     [rcx], r15d
0x180084dcc  jz      loc_180084E8B
0x180084dd2  mov     r8, r14; ppsiItemArray
0x180084dd5  mov     rdx, [rcx+8]; rgpidl
0x180084dd9  mov     ecx, [rcx]; cidl
0x180084ddb  call    cs:__imp_SHCreateShellItemArrayFromIDLists
0x180084de1  mov     ebx, eax
0x180084de3  test    eax, eax
0x180084de5  jns     loc_180084E7E
0x180084deb  mov     r9d, eax
0x180084dee  mov     edx, 22CAh
0x180084df3  jmp     loc_180084E9F
0x180084df8  mov     r9d, eax
0x180084dfb  mov     edx, 22C5h
0x180084e00  jmp     short loc_180084E0A
0x180084e02  mov     r9d, ebx; char *
0x180084e05  mov     edx, 22C3h; void *
0x180084e0a  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\windows.storage.sear"...
0x180084e11  mov     rcx, [rbp+30h]; this
0x180084e15  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180084e1a  mov     rcx, [rbp+pv]; pv
0x180084e1e  mov     [rbp+pv], r15
0x180084e22  test    rcx, rcx
0x180084e25  jz      short loc_180084E48
0x180084e27  call    cs:__imp_CoTaskMemFree
0x180084e2d  jmp     short loc_180084E48
0x180084e2f  mov     rcx, [rbp+30h]; this
0x180084e33  mov     r9d, eax; char *
0x180084e36  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\windows.storage.sear"...
0x180084e3d  mov     edx, 22C0h; void *
0x180084e42  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180084e47  nop
0x180084e48  lea     rcx, [rbp+punk]
0x180084e4c  call    ??1?$com_ptr_t@UIInitializeSortColumnArray@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IInitializeSortColumnArray,wil::err_exception_policy>::~com_ptr_t<IInitializeSortColumnArray,wil::err_exception_policy>(void)
0x180084e51  jmp     short loc_180084E73
0x180084e53  mov     edx, 22BBh
0x180084e58  jmp     short loc_180084E5F
0x180084e5a  mov     edx, 22B8h; void *
0x180084e5f  mov     r9d, eax; char *
0x180084e62  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\windows.storage.sear"...
0x180084e69  mov     rcx, [rbp+30h]; this
0x180084e6d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180084e72  nop
0x180084e73  lea     rcx, [rbp+var_30]
0x180084e77  call    ??1?$com_ptr_t@UIInitializeSortColumnArray@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IInitializeSortColumnArray,wil::err_exception_policy>::~com_ptr_t<IInitializeSortColumnArray,wil::err_exception_policy>(void)
0x180084e7c  jmp     short loc_180084EB0
0x180084e7e  lea     rcx, [rbp+var_38]
0x180084e82  call    ??1?$CDPA_Base@GVCTContainer_PolicyCoTaskMem@@@@QEAA@XZ; CDPA_Base<ushort,CTContainer_PolicyCoTaskMem>::~CDPA_Base<ushort,CTContainer_PolicyCoTaskMem>(void)
0x180084e87  xor     eax, eax
0x180084e89  jmp     short loc_180084EBB
0x180084e8b  mov     edx, 22C9h
0x180084e90  jmp     short loc_180084E97
0x180084e92  mov     edx, 22B3h; void *
0x180084e97  mov     ebx, 80004005h
0x180084e9c  mov     r9d, ebx; char *
0x180084e9f  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\windows.storage.sear"...
0x180084ea6  mov     rcx, [rbp+30h]; this
0x180084eaa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180084eaf  nop
0x180084eb0  lea     rcx, [rbp+var_38]
0x180084eb4  call    ??1?$CDPA_Base@GVCTContainer_PolicyCoTaskMem@@@@QEAA@XZ; CDPA_Base<ushort,CTContainer_PolicyCoTaskMem>::~CDPA_Base<ushort,CTContainer_PolicyCoTaskMem>(void)
0x180084eb9  mov     eax, ebx
0x180084ebb  add     rsp, 68h
0x180084ebf  pop     r15
0x180084ec1  pop     r14
0x180084ec3  pop     rdi
0x180084ec4  pop     rsi
0x180084ec5  pop     rbx
0x180084ec6  pop     rbp
0x180084ec7  retn
```
