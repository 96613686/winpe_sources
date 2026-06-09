# CStorageProviderRootsCache::InitializeContextMenuVerbs(Windows::Internal::StateRepository::IApplication *,Windows::Foundation::Collections::IPropertySet *)

- ea: `0x18000593c`
- end: `0x180006065`
- name: `?InitializeContextMenuVerbs@CStorageProviderRootsCache@@AEAAJPEAUIApplication@StateRepository@Internal@Windows@@PEAUIPropertySet@Collections@Foundation@5@@Z`
- size: `1833`
- prototype: `__int64 __fastcall(CStorageProviderRootsCache *__hidden this, struct Windows::Internal::StateRepository::IApplication *, struct Windows::Foundation::Collections::IPropertySet *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000d188`

## callees

- `0x180004a54`
- `0x18000593c`
- `0x18000618c`
- `0x180006c54`
- `0x180006e78`
- `0x1800077c8`
- `0x180007920`
- `0x1800079a0`
- `0x180007a04`
- `0x180007a64`
- `0x18000ce80`
- `0x180023fe8`
- `0x180037780`
- `0x180043c98`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180005f9e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180005fec`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180005f9e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180005fec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005c10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005c9a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005cdd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005c10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005c9a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005cdd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180005a04`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180005b21`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180005a04`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180005b21`

## string_xrefs

- `0x180005dac`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x180005f2a`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x180006035`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x18000604e`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
__int64 __fastcall CStorageProviderRootsCache::InitializeContextMenuVerbs(
        CStorageProviderRootsCache *this,
        struct Windows::Internal::StateRepository::IApplication *a2,
        struct Windows::Foundation::Collections::IPropertySet *a3)
{
  char *v6; // rsi
  __int64 (__fastcall *v7)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, _QWORD **); // rbx
  int v8; // eax
  _QWORD *v9; // rbx
  __int64 v10; // rdi
  unsigned int v11; // eax
  UINT32 v12; // edx
  HRESULT v13; // eax
  int v14; // eax
  unsigned __int16 **v15; // r8
  int v16; // ebx
  LPVOID v17; // rcx
  _QWORD *v18; // rcx
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, GUID *, _QWORD **); // rbx
  int v21; // eax
  int v22; // ebx
  _QWORD *v23; // rbx
  __int64 v24; // rdi
  unsigned int v25; // eax
  UINT32 v26; // edx
  HRESULT v27; // eax
  int v28; // eax
  LPVOID v29; // rcx
  _QWORD *v30; // rcx
  LPVOID v31; // rcx
  _QWORD *v32; // rcx
  unsigned int k; // ebx
  void *v34; // rcx
  __int64 v35; // rcx
  unsigned __int64 v36; // rcx
  LPVOID *v37; // rbx
  unsigned __int64 v38; // rcx
  int v39; // eax
  void *v40; // rbx
  __int64 v41; // rcx
  LPVOID v43; // rcx
  _QWORD *v44; // rcx
  int v45; // eax
  unsigned int v46; // ebx
  LPVOID v47; // rcx
  _QWORD *v48; // rcx
  int v49; // eax
  unsigned int i; // ebx
  int v51; // eax
  int v52; // edi
  _QWORD *v53; // rcx
  LPVOID v54; // rcx
  _QWORD *v55; // rcx
  unsigned int j; // ebx
  unsigned __int64 v57; // r9
  __int64 v58; // rdx
  unsigned __int64 v59; // r9
  __int64 v60; // rdx
  void **v61; // [rsp+20h] [rbp-49h]
  LPVOID pv; // [rsp+30h] [rbp-39h] BYREF
  _QWORD *v63; // [rsp+38h] [rbp-31h] BYREF
  unsigned int v64; // [rsp+40h] [rbp-29h] BYREF
  struct _GUID v65; // [rsp+48h] [rbp-21h] BYREF
  _BYTE v66[8]; // [rsp+58h] [rbp-11h] BYREF
  __int64 v67; // [rsp+60h] [rbp-9h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp-1h] BYREF
  HSTRING string; // [rsp+80h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v6 = (char *)this + 592;
  CTSimpleArray<wistd::unique_ptr<StateRepoHelpers::ExplorerCommandVerb,wistd::default_delete<StateRepoHelpers::ExplorerCommandVerb>>,4294967294,CTPolicyCoTaskMem<wistd::unique_ptr<StateRepoHelpers::ExplorerCommandVerb,wistd::default_delete<StateRepoHelpers::ExplorerCommandVerb>>>,CSimpleArrayStandardCompareHelper<wistd::unique_ptr<StateRepoHelpers::ExplorerCommandVerb,wistd::default_delete<StateRepoHelpers::ExplorerCommandVerb>>>,CSimpleArrayStandardMergeHelper<wistd::unique_ptr<StateRepoHelpers::ExplorerCommandVerb,wistd::default_delete<StateRepoHelpers::ExplorerCommandVerb>>>>::RemoveAll((char *)this + 592);
  v64 = 0;
  *(_QWORD *)v65.Data4 = 0;
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(v65.Data4);
  *(_QWORD *)v65.Data4 = 0;
  v63 = 0;
  v7 = **(__int64 (__fastcall ***)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, _QWORD **))a3;
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v63);
  v8 = v7(a3, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v63);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2C,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\StateRepoUtil.h",
      (const char *)(unsigned int)v8,
      (int)v61);
    goto LABEL_26;
  }
  pv = 0;
  v9 = v63;
  v10 = *v63;
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&pv);
  string = 0;
  v11 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x16u);
  v12 = v11 - 1;
  if ( v11 > 0x16 )
    v12 = 22;
  v13 = WindowsCreateStringReference(L"CloudFilesContextMenus", v12, &hstringHeader, &string);
  if ( v13 < 0 )
  {
    RaiseException(v13, 1u, 0, 0);
    __debugbreak();
  }
  v14 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, LPVOID *))(v10 + 48))(v9, string, &pv);
  if ( v14 < 0 )
  {
    if ( v14 != -2147483637 )
    {
      v57 = (unsigned int)v14;
      v58 = 47;
      goto LABEL_85;
    }
    v31 = pv;
    if ( pv )
    {
      pv = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v31 + 16LL))(v31);
    }
LABEL_26:
    v32 = v63;
    if ( !v63 )
      goto LABEL_36;
    v63 = 0;
    goto LABEL_35;
  }
  v16 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, unsigned __int8 *))pv)(
          pv,
          &GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c,
          v65.Data4);
  if ( (unsigned int)(v16 + 2147467263) <= 1 )
  {
    v17 = pv;
    if ( pv )
    {
      pv = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v17 + 16LL))(v17);
    }
    v18 = v63;
    if ( v63 )
    {
      v63 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v18 + 16LL))(v18);
    }
    if ( v16 < 0 )
      goto LABEL_36;
LABEL_12:
    *(_QWORD *)&v65.Data1 = 0;
    v67 = 0;
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v67);
    v19 = *(_QWORD *)v65.Data4;
    v67 = 0;
    v63 = 0;
    v20 = ***(__int64 (__fastcall ****)(__int64, GUID *, _QWORD **))v65.Data4;
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v63);
    v21 = v20(v19, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v63);
    v22 = v21;
    if ( v21 >= 0 )
    {
      pv = 0;
      v23 = v63;
      v24 = *v63;
      Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&pv);
      string = 0;
      v25 = Microsoft::WRL::Wrappers::HStringReference::AddOne(4u);
      v26 = v25 - 1;
      if ( v25 > 4 )
        v26 = 4;
      v27 = WindowsCreateStringReference(L"Verb", v26, &hstringHeader, &string);
      if ( v27 < 0 )
      {
        RaiseException(v27, 1u, 0, 0);
        __debugbreak();
      }
      v28 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, LPVOID *))(v24 + 48))(v23, string, &pv);
      v22 = v28;
      if ( v28 < 0 )
      {
        if ( v28 == -2147483637 )
        {
          v43 = pv;
          if ( pv )
          {
            pv = 0;
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v43 + 16LL))(v43);
          }
          v44 = v63;
          if ( v63 )
          {
            v63 = 0;
            (*(void (__fastcall **)(_QWORD *))(*v44 + 16LL))(v44);
          }
          goto LABEL_52;
        }
        v59 = (unsigned int)v28;
        v60 = 47;
      }
      else
      {
        v22 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))pv)(
                pv,
                &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62,
                &v67);
        if ( (unsigned int)(v22 + 2147467263) <= 1 )
        {
          v29 = pv;
          if ( pv )
          {
            pv = 0;
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v29 + 16LL))(v29);
          }
          v30 = v63;
          if ( v63 )
          {
            v63 = 0;
            (*(void (__fastcall **)(_QWORD *))(*v30 + 16LL))(v30);
          }
          goto LABEL_61;
        }
        if ( v22 >= 0 )
        {
          v47 = pv;
          if ( pv )
          {
            pv = 0;
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v47 + 16LL))(v47);
          }
          v48 = v63;
          if ( v63 )
          {
            v63 = 0;
            (*(void (__fastcall **)(_QWORD *))(*v48 + 16LL))(v48);
          }
          v22 = 0;
          goto LABEL_61;
        }
        v59 = (unsigned int)v22;
        v60 = 50;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v60,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\StateRepoUtil.h",
        (const char *)v59,
        (int)v61);
      Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&pv);
      Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v63);
      goto LABEL_61;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2C,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\StateRepoUtil.h",
      (const char *)(unsigned int)v21,
      (int)v61);
    v53 = v63;
    if ( v63 )
    {
      v63 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v53 + 16LL))(v53);
    }
LABEL_61:
    if ( v22 >= 0 )
    {
      pv = 0;
      v49 = (*(__int64 (__fastcall **)(__int64, unsigned int *, LPVOID *))(*(_QWORD *)v67 + 304LL))(v67, &v64, &pv);
      v46 = v49;
      if ( v49 >= 0 )
      {
        hstringHeader.Reserved.Reserved1 = &v64;
        *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = &pv;
        hstringHeader.Reserved.Reserved2[16] = 1;
        for ( i = 0; i < v64; ++i )
        {
          v51 = CStorageProviderRootsCache::AddContextMenuVerb(this, a2, *((struct IInspectable **)pv + i));
          v52 = v51;
          if ( v51 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xAD4,
              (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
              (const char *)(unsigned int)v51,
              (int)v61);
            for ( j = 0; j < v64; ++j )
              (*(void (__fastcall **)(_QWORD))(**((_QWORD **)pv + j) + 16LL))(*((_QWORD *)pv + j));
            v46 = v52;
            goto LABEL_80;
          }
        }
        for ( k = 0; k < v64; ++k )
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)pv + k) + 16LL))(*((_QWORD *)pv + k));
        v34 = pv;
        pv = 0;
        CoTaskMemFree(v34);
        goto LABEL_31;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAC7,
        (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
        (const char *)(unsigned int)v49,
        (int)v61);
LABEL_80:
      CCoTaskMemPtr<IInspectable *>::~CCoTaskMemPtr<IInspectable *>(&pv);
      goto LABEL_81;
    }
LABEL_52:
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v65);
    if ( StateRepoHelpers::LookupInPropertySet(
           *(StateRepoHelpers **)v65.Data4,
           (struct IInspectable *)L"Verb",
           (const unsigned __int16 *)&GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
           &v65,
           v61) < 0
      || (v64 = 1,
          v45 = CStorageProviderRootsCache::AddContextMenuVerb(this, a2, *(struct IInspectable **)&v65.Data1),
          v46 = v45,
          v45 >= 0) )
    {
LABEL_31:
      v35 = v67;
      if ( v67 )
      {
        v67 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
      }
      v32 = *(_QWORD **)&v65.Data1;
      if ( !*(_QWORD *)&v65.Data1 )
        goto LABEL_36;
      *(_QWORD *)&v65.Data1 = 0;
LABEL_35:
      (*(void (__fastcall **)(_QWORD *))(*v32 + 16LL))(v32);
      goto LABEL_36;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xADA,
      (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
      (const char *)(unsigned int)v45,
      (int)v61);
LABEL_81:
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v67);
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v65);
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(v65.Data4);
    return v46;
  }
  if ( v16 >= 0 )
  {
    v54 = pv;
    if ( pv )
    {
      pv = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v54 + 16LL))(v54);
    }
    v55 = v63;
    if ( v63 )
    {
      v63 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v55 + 16LL))(v55);
    }
    goto LABEL_12;
  }
  v57 = (unsigned int)v16;
  v58 = 50;
LABEL_85:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v58,
    (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\StateRepoUtil.h",
    (const char *)v57,
    (int)v61);
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&pv);
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v63);
LABEL_36:
  v36 = *((_QWORD *)v6 + 1);
  if ( v36 > 1 )
  {
    v37 = (LPVOID *)(v6 + 16);
    *((_QWORD *)v6 + 2) = 0;
    *(_QWORD *)&v65.Data1 = 0;
    v38 = v36 >> 1;
    if ( is_mul_ok(v38, 8u)
      && CTCoAllocPolicy::Realloc((void *)v38, (v38 * (unsigned __int128)8uLL) >> 64, 0, 8 * v38, (void **)v6 + 2) >= 0 )
    {
      CTSimpleArray_wistd::unique_ptr_StateRepoHelpers::ExplorerCommandVerb_wistd::default_delete_StateRepoHelpers::ExplorerCommandVerb____4294967294_CTPolicyCoTaskMem_wistd::unique_ptr_StateRepoHelpers::ExplorerCommandVerb_wistd::default_delete_StateRepoHelpers::ExplorerCommandVerb______CSimpleArrayStandardCompareHelper_wistd::unique_ptr_StateRepoHelpers::ExplorerCommandVerb_wistd::default_delete_StateRepoHelpers::ExplorerCommandVerb______CSimpleArrayStandardMergeHelper_wistd::unique_ptr_StateRepoHelpers::ExplorerCommandVerb_wistd::default_delete_StateRepoHelpers::ExplorerCommandVerb_______::_MergeSort__CStorageProviderRootsCache::InitializeContextMenuVerbs_::_2_::SortById_(
        v6,
        v66,
        0,
        *((_QWORD *)v6 + 1));
      CoTaskMemFree(*v37);
      *v37 = 0;
    }
  }
  *(_QWORD *)&v65.Data1 = 0;
  v39 = Windows::Internal::SyncRootHelpers::ConvertFullIdentifierToProviderIdentifier(
          *(Windows::Internal::SyncRootHelpers **)this,
          (const unsigned __int16 *)&v65,
          v15);
  if ( v39 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xAF1,
      (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
      (const char *)(unsigned int)v39,
      (int)v61);
  v40 = *(void **)&v65.Data1;
  CloudFilesTelemetry::InitStateRepoVerbs<unsigned short *,unsigned int &>(&v65, &v64);
  if ( v40 )
    CoTaskMemFree(v40);
  v41 = *(_QWORD *)v65.Data4;
  if ( *(_QWORD *)v65.Data4 )
  {
    *(_QWORD *)v65.Data4 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
  }
  return 0;
}

```

## disassembly

```asm
0x18000593c  mov     [rsp-8+arg_18], rbx
0x180005941  push    rbp
0x180005942  push    rsi
0x180005943  push    rdi
0x180005944  push    r12
0x180005946  push    r13
0x180005948  push    r14
0x18000594a  push    r15
0x18000594c  lea     rbp, [rsp-27h]
0x180005951  sub     rsp, 90h
0x180005958  mov     rax, cs:__security_cookie
0x18000595f  xor     rax, rsp
0x180005962  mov     [rbp+57h+var_38], rax
0x180005966  mov     rdi, r8
0x180005969  mov     r15, rdx
0x18000596c  mov     r14, rcx
0x18000596f  lea     rsi, [rcx+250h]
0x180005976  mov     rcx, rsi
0x180005979  call    ?RemoveAll@?$CTSimpleArray@V?$unique_ptr@UExplorerCommandVerb@StateRepoHelpers@@U?$default_delete@UExplorerCommandVerb@StateRepoHelpers@@@wistd@@@wistd@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@V?$unique_ptr@UExplorerCommandVerb@StateRepoHelpers@@U?$default_delete@UExplorerCommandVerb@StateRepoHelpers@@@wistd@@@wistd@@@@V?$CSimpleArrayStandardCompareHelper@V?$unique_ptr@UExplorerCommandVerb@StateRepoHelpers@@U?$default_delete@UExplorerCommandVerb@StateRepoHelpers@@@wistd@@@wistd@@@@V?$CSimpleArrayStandardMergeHelper@V?$unique_ptr@UExplorerCommandVerb@StateRepoHelpers@@U?$default_delete@UExplorerCommandVerb@StateRepoHelpers@@@wistd@@@wistd@@@@@@QEAAXXZ; CTSimpleArray<wistd::unique_ptr<StateRepoHelpers::ExplorerCommandVerb,wistd::default_delete<StateRepoHelpers::ExplorerCommandVerb>>,4294967294,CTPolicyCoTaskMem<wistd::unique_ptr<StateRepoHelpers::ExplorerCommandVerb,wistd::default_delete<StateRepoHelpers::ExplorerCommandVerb>>>,CSimpleArrayStandardCompareHelper<wistd::unique_ptr<StateRepoHelpers::ExplorerCommandVerb,wistd::default_delete<StateRepoHelpers::ExplorerCommandVerb>>>,CSimpleArrayStandardMergeHelper<wistd::unique_ptr<StateRepoHelpers::ExplorerCommandVerb,wistd::default_delete<StateRepoHelpers::ExplorerCommandVerb>>>>::RemoveAll(void)
0x18000597e  xor     r13d, r13d
0x180005981  mov     [rbp+57h+var_80], r13d
0x180005985  mov     qword ptr [rbp+57h+var_78.Data4], r13
0x180005989  lea     rcx, [rbp+57h+var_78.Data4]
0x18000598d  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180005992  mov     qword ptr [rbp+57h+var_78.Data4], r13
0x180005996  mov     [rbp+57h+var_88], r13
0x18000599a  mov     rax, [rdi]
0x18000599d  mov     rbx, [rax]
0x1800059a0  lea     rcx, [rbp+57h+var_88]
0x1800059a4  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x1800059a9  lea     r8, [rbp+57h+var_88]
0x1800059ad  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x1800059b4  mov     rcx, rdi
0x1800059b7  mov     rax, rbx
0x1800059ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059bf  test    eax, eax
0x1800059c1  js      loc_180005E8C
0x1800059c7  mov     [rbp+57h+pv], r13
0x1800059cb  mov     rbx, [rbp+57h+var_88]
0x1800059cf  mov     rdi, [rbx]
0x1800059d2  lea     rcx, [rbp+57h+pv]
0x1800059d6  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x1800059db  mov     [rbp+57h+string], r13
0x1800059df  lea     r12d, [r13+16h]
0x1800059e3  mov     ecx, r12d; unsigned int
0x1800059e6  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800059eb  lea     edx, [rax-1]
0x1800059ee  cmp     eax, r12d
0x1800059f1  cmova   edx, r12d; length
0x1800059f5  lea     r9, [rbp+57h+string]; string
0x1800059f9  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800059fd  lea     rcx, sourceString; "CloudFilesContextMenus"
0x180005a04  call    cs:__imp_WindowsCreateStringReference
0x180005a0a  test    eax, eax
0x180005a0c  js      loc_180005F92
0x180005a12  lea     r8, [rbp+57h+pv]
0x180005a16  mov     rdx, [rbp+57h+string]
0x180005a1a  mov     rcx, rbx
0x180005a1d  mov     rax, [rdi+30h]
0x180005a21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a26  nop
0x180005a27  test    eax, eax
0x180005a29  js      loc_180005BB0
0x180005a2f  mov     rcx, [rbp+57h+pv]
0x180005a33  mov     rax, [rcx]
0x180005a36  lea     r8, [rbp+57h+var_78.Data4]
0x180005a3a  lea     rdx, _GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c
0x180005a41  mov     rax, [rax]
0x180005a44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a49  mov     ebx, eax
0x180005a4b  lea     ecx, [rax+7FFFBFFFh]
0x180005a51  cmp     ecx, 1
0x180005a54  ja      loc_180005EE2
0x180005a5a  mov     rcx, [rbp+57h+pv]
0x180005a5e  test    rcx, rcx
0x180005a61  jz      short loc_180005A74
0x180005a63  mov     [rbp+57h+pv], r13
0x180005a67  mov     rax, [rcx]
0x180005a6a  mov     rax, [rax+10h]
0x180005a6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a73  nop
0x180005a74  mov     rcx, [rbp+57h+var_88]
0x180005a78  test    rcx, rcx
0x180005a7b  jz      short loc_180005A8E
0x180005a7d  mov     [rbp+57h+var_88], r13
0x180005a81  mov     rax, [rcx]
0x180005a84  mov     rax, [rax+10h]
0x180005a88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a8d  nop
0x180005a8e  test    ebx, ebx
0x180005a90  js      loc_180005C4B
0x180005a96  mov     qword ptr [rbp+57h+var_78.Data1], r13
0x180005a9a  mov     [rbp+57h+var_60], r13
0x180005a9e  lea     rcx, [rbp+57h+var_60]
0x180005aa2  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180005aa7  mov     rdi, qword ptr [rbp+57h+var_78.Data4]
0x180005aab  mov     [rbp+57h+var_60], r13
0x180005aaf  mov     [rbp+57h+var_88], r13
0x180005ab3  mov     rax, [rdi]
0x180005ab6  mov     rbx, [rax]
0x180005ab9  lea     rcx, [rbp+57h+var_88]
0x180005abd  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180005ac2  lea     r8, [rbp+57h+var_88]
0x180005ac6  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x180005acd  mov     rcx, rdi
0x180005ad0  mov     rax, rbx
0x180005ad3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ad8  mov     ebx, eax
0x180005ada  test    eax, eax
0x180005adc  js      loc_180005EAA
0x180005ae2  mov     [rbp+57h+pv], r13
0x180005ae6  mov     rbx, [rbp+57h+var_88]
0x180005aea  mov     rdi, [rbx]
0x180005aed  lea     rcx, [rbp+57h+pv]
0x180005af1  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180005af6  mov     [rbp+57h+string], r13
0x180005afa  mov     r12d, 4
0x180005b00  mov     ecx, r12d; unsigned int
0x180005b03  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180005b08  lea     edx, [rax-1]
0x180005b0b  cmp     eax, r12d
0x180005b0e  cmova   edx, r12d; length
0x180005b12  lea     r9, [rbp+57h+string]; string
0x180005b16  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180005b1a  lea     rcx, aVerb; "Verb"
0x180005b21  call    cs:__imp_WindowsCreateStringReference
0x180005b27  test    eax, eax
0x180005b29  js      loc_180005FE0
0x180005b2f  lea     r8, [rbp+57h+pv]
0x180005b33  mov     rdx, [rbp+57h+string]
0x180005b37  mov     rcx, rbx
0x180005b3a  mov     rax, [rdi+30h]
0x180005b3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b43  mov     ebx, eax
0x180005b45  test    eax, eax
0x180005b47  js      loc_180005D27
0x180005b4d  mov     rcx, [rbp+57h+pv]
0x180005b51  mov     rax, [rcx]
0x180005b54  lea     r8, [rbp+57h+var_60]
0x180005b58  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x180005b5f  mov     rax, [rax]
0x180005b62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b67  mov     ebx, eax
0x180005b69  add     eax, 7FFFBFFFh
0x180005b6e  cmp     eax, 1
0x180005b71  ja      loc_180005DC2
0x180005b77  mov     rcx, [rbp+57h+pv]
0x180005b7b  test    rcx, rcx
0x180005b7e  jz      short loc_180005B91
0x180005b80  mov     [rbp+57h+pv], r13
0x180005b84  mov     rax, [rcx]
0x180005b87  mov     rax, [rax+10h]
0x180005b8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b90  nop
0x180005b91  mov     rcx, [rbp+57h+var_88]
0x180005b95  test    rcx, rcx
0x180005b98  jz      short loc_180005BAB
0x180005b9a  mov     [rbp+57h+var_88], r13
0x180005b9e  mov     rax, [rcx]
0x180005ba1  mov     rax, [rax+10h]
0x180005ba5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005baa  nop
0x180005bab  jmp     loc_180005E01
0x180005bb0  cmp     eax, 8000000Bh
0x180005bb5  jnz     loc_180005FA5
0x180005bbb  mov     rcx, [rbp+57h+pv]
0x180005bbf  test    rcx, rcx
0x180005bc2  jz      short loc_180005BD5
0x180005bc4  mov     [rbp+57h+pv], r13
0x180005bc8  mov     rax, [rcx]
0x180005bcb  mov     rax, [rax+10h]
0x180005bcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bd4  nop
0x180005bd5  mov     rcx, [rbp+57h+var_88]
0x180005bd9  test    rcx, rcx
0x180005bdc  jz      short loc_180005C4B
0x180005bde  mov     [rbp+57h+var_88], r13
0x180005be2  jmp     short loc_180005C3E
0x180005be4  mov     ebx, r13d
0x180005be7  test    eax, eax
0x180005be9  jz      short loc_180005C08
0x180005beb  mov     ecx, ebx
0x180005bed  mov     rax, [rbp+57h+pv]
0x180005bf1  mov     rcx, [rax+rcx*8]
0x180005bf5  mov     rax, [rcx]
0x180005bf8  mov     rax, [rax+10h]
0x180005bfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c01  inc     ebx
0x180005c03  cmp     ebx, [rbp+57h+var_80]
0x180005c06  jb      short loc_180005BEB
0x180005c08  mov     rcx, [rbp+57h+pv]; pv
0x180005c0c  mov     [rbp+57h+pv], r13
0x180005c10  call    cs:__imp_CoTaskMemFree
0x180005c16  nop
0x180005c17  mov     rcx, [rbp+57h+var_60]
0x180005c1b  test    rcx, rcx
0x180005c1e  jz      short loc_180005C31
0x180005c20  mov     [rbp+57h+var_60], r13
0x180005c24  mov     rax, [rcx]
0x180005c27  mov     rax, [rax+10h]
0x180005c2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c30  nop
0x180005c31  mov     rcx, qword ptr [rbp+57h+var_78.Data1]
0x180005c35  test    rcx, rcx
0x180005c38  jz      short loc_180005C4B
0x180005c3a  mov     qword ptr [rbp+57h+var_78.Data1], r13
0x180005c3e  mov     rax, [rcx]
0x180005c41  mov     rax, [rax+10h]
0x180005c45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c4a  nop
0x180005c4b  mov     rcx, [rsi+8]
0x180005c4f  cmp     rcx, 1
0x180005c53  jbe     short loc_180005CA3
0x180005c55  lea     rbx, [rsi+10h]
0x180005c59  mov     [rbx], r13
0x180005c5c  mov     qword ptr [rbp+57h+var_78.Data1], r13
0x180005c60  shr     rcx, 1; void *
0x180005c63  mov     eax, 8
0x180005c68  mul     rcx
0x180005c6b  test    rdx, rdx
0x180005c6e  jnz     short loc_180005CA3
0x180005c70  mov     [rsp+0C0h+var_A0], rbx; int
0x180005c75  mov     r9, rax; unsigned __int64
0x180005c78  xor     r8d, r8d; void *
0x180005c7b  call    ?Realloc@CTCoAllocPolicy@@SAJPEAXK0_KPEAPEAX@Z; CTCoAllocPolicy::Realloc(void *,ulong,void *,unsigned __int64,void * *)
0x180005c80  test    eax, eax
0x180005c82  js      short loc_180005CA3
0x180005c84  mov     r9, [rsi+8]
0x180005c88  xor     r8d, r8d
0x180005c8b  lea     rdx, [rbp+57h+var_68]
0x180005c8f  mov     rcx, rsi
0x180005c92  call    CTSimpleArray_wistd__unique_ptr_StateRepoHelpers__ExplorerCommandVerb_wistd__default_delete_StateRepoHelpers__ExplorerCommandVerb____4294967294_CTPolicyCoTaskMem_wistd__unique_ptr_StateRepoHelpers__ExplorerCommandVerb_wistd__default_delete_StateRepoHelpers__ExplorerCommandVerb______CSimpleArrayStandardCompareHelper_wistd__unique_ptr_StateRepoHelpers__ExplorerCommandVerb_wistd__default_delete_StateRepoHelpers__ExplorerCommandVerb______CSimpleArrayStandardMergeHelper_wistd__unique_ptr_StateRepoHelpers__ExplorerCommandVerb_wistd__default_delete_StateRepoHelpers__ExplorerCommandVerb__________MergeSort__CStorageProviderRootsCache__InitializeContextMenuVerbs____2___SortById_
0x180005c97  mov     rcx, [rbx]; pv
0x180005c9a  call    cs:__imp_CoTaskMemFree
0x180005ca0  mov     [rbx], r13
0x180005ca3  mov     qword ptr [rbp+57h+var_78.Data1], r13
0x180005ca7  lea     rdx, [rbp+57h+var_78]; unsigned __int16 *
0x180005cab  mov     rcx, [r14]; this
0x180005cae  call    ?ConvertFullIdentifierToProviderIdentifier@SyncRootHelpers@Internal@Windows@@YAJPEBGPEAPEAG@Z; Windows::Internal::SyncRootHelpers::ConvertFullIdentifierToProviderIdentifier(ushort const *,ushort * *)
0x180005cb3  mov     rcx, [rbp+5Fh]; this
0x180005cb7  test    eax, eax
0x180005cb9  js      loc_18000604B
0x180005cbf  mov     rbx, qword ptr [rbp+57h+var_78.Data1]
0x180005cc3  mov     qword ptr [rbp+57h+var_78.Data1], rbx
0x180005cc7  lea     rdx, [rbp+57h+var_80]
0x180005ccb  lea     rcx, [rbp+57h+var_78]
0x180005ccf  call    ??$InitStateRepoVerbs@PEAGAEAI@CloudFilesTelemetry@@SAX$$QEAPEAGAEAI@Z; CloudFilesTelemetry::InitStateRepoVerbs<ushort *,uint &>(ushort * &&,uint &)
0x180005cd4  nop
0x180005cd5  test    rbx, rbx
0x180005cd8  jz      short loc_180005CE4
0x180005cda  mov     rcx, rbx; pv
0x180005cdd  call    cs:__imp_CoTaskMemFree
0x180005ce3  nop
0x180005ce4  mov     rcx, qword ptr [rbp+57h+var_78.Data4]
0x180005ce8  test    rcx, rcx
0x180005ceb  jz      short loc_180005CFE
0x180005ced  mov     qword ptr [rbp+57h+var_78.Data4], r13
0x180005cf1  mov     rax, [rcx]
0x180005cf4  mov     rax, [rax+10h]
0x180005cf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cfd  nop
0x180005cfe  xor     eax, eax
0x180005d00  mov     rcx, [rbp+57h+var_38]
0x180005d04  xor     rcx, rsp; StackCookie
0x180005d07  call    __security_check_cookie
0x180005d0c  mov     rbx, [rsp+0C0h+arg_18]
0x180005d14  add     rsp, 90h
0x180005d1b  pop     r15
0x180005d1d  pop     r14
0x180005d1f  pop     r13
0x180005d21  pop     r12
0x180005d23  pop     rdi
0x180005d24  pop     rsi
0x180005d25  pop     rbp
0x180005d26  retn
0x180005d27  cmp     eax, 8000000Bh
0x180005d2c  jnz     loc_180005FF3
0x180005d32  mov     rcx, [rbp+57h+pv]
0x180005d36  test    rcx, rcx
0x180005d39  jz      short loc_180005D4C
0x180005d3b  mov     [rbp+57h+pv], r13
0x180005d3f  mov     rax, [rcx]
0x180005d42  mov     rax, [rax+10h]
0x180005d46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d4b  nop
0x180005d4c  mov     rcx, [rbp+57h+var_88]
0x180005d50  test    rcx, rcx
0x180005d53  jnz     loc_180005E77
0x180005d59  lea     rcx, [rbp+57h+var_78]
0x180005d5d  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180005d62  lea     r9, [rbp+57h+var_78]; struct _GUID *
0x180005d66  lea     r8, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; unsigned __int16 *
0x180005d6d  lea     rdx, aVerb; "Verb"
0x180005d74  mov     rcx, qword ptr [rbp+57h+var_78.Data4]; this
0x180005d78  call    ?LookupInPropertySet@StateRepoHelpers@@YAJPEAUIInspectable@@PEBGAEBU_GUID@@PEAPEAX@Z; StateRepoHelpers::LookupInPropertySet(IInspectable *,ushort const *,_GUID const &,void * *)
0x180005d7d  test    eax, eax
0x180005d7f  js      loc_180005C17
0x180005d85  mov     [rbp+57h+var_80], 1
0x180005d8c  mov     r8, qword ptr [rbp+57h+var_78.Data1]; struct IInspectable *
0x180005d90  mov     rdx, r15; struct Windows::Internal::StateRepository::IApplication *
  ... truncated ...
```
