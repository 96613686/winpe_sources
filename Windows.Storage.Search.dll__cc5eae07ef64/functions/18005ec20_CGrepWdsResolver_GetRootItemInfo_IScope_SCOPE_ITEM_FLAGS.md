# CGrepWdsResolver::_GetRootItemInfo(IScope *,SCOPE_ITEM_FLAGS *)

- ea: `0x18005ec20`
- end: `0x18005ee9d`
- name: `?_GetRootItemInfo@CGrepWdsResolver@@AEAAJPEAUIScope@@PEAW4SCOPE_ITEM_FLAGS@@@Z`
- size: `637`
- prototype: `__int64 __fastcall(CGrepWdsResolver *__hidden this, struct IScope *, enum SCOPE_ITEM_FLAGS *)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, service_task, installer_update, broker_com_uri`

## callers

- `0x180060340`

## callees

- `0x180015588`
- `0x18002da80`
- `0x18003d6b0`
- `0x18005832c`
- `0x18005ec20`
- `0x18006c5c8`
- `0x18009b884`
- `0x18009cadc`
- `0x1800ea010`

## import_xrefs

- `SHCORE!__imp_PathIsNetworkPathW` at `0x18005ed9e`
- `SHCORE!__imp_PathIsNetworkPathW` at `0x18005ed9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005ed6d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005edef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005ed6d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005edef`
- `api-ms-win-core-path-l1-1-0!PathIsUNCEx` at `0x18005ee09`
- `api-ms-win-core-path-l1-1-0!PathIsUNCEx` at `0x18005ee09`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x18005ee1c`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x18005ee1c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CGrepWdsResolver::_GetRootItemInfo(
        CGrepWdsResolver *this,
        struct IScope *a2,
        enum SCOPE_ITEM_FLAGS *a3)
{
  int v5; // ebx
  int v6; // eax
  struct IShellItem **v7; // rdi
  __int64 v8; // rdx
  struct IShellItem *v9; // rcx
  struct IShellItem *v10; // rdi
  HRESULT (__stdcall *GetDisplayName)(IShellItem *, SIGDN, LPWSTR *); // rbx
  LPCWSTR *v12; // r14
  const WCHAR *v13; // rcx
  PWSTR v14; // rax
  const unsigned __int16 *v15; // r8
  unsigned __int64 v16; // rax
  int v17; // eax
  int v19; // [rsp+20h] [rbp-20h] BYREF
  __int64 v20; // [rsp+28h] [rbp-18h] BYREF
  _QWORD v21[2]; // [rsp+30h] [rbp-10h] BYREF
  int v22; // [rsp+88h] [rbp+48h] BYREF
  PCWSTR ppszServer; // [rsp+90h] [rbp+50h] BYREF
  int v24; // [rsp+98h] [rbp+58h] BYREF

  *(_DWORD *)a3 = 0;
  v21[0] = 0;
  v5 = (**(__int64 (__fastcall ***)(struct IScope *, GUID *, _QWORD *))a2)(
         a2,
         &GUID_bb15caac_019b_4065_a1c3_37c4fc1c599a,
         v21);
  if ( v5 >= 0 )
  {
    v20 = 0;
    v5 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64 *))(*(_QWORD *)v21[0] + 96LL))(
           v21[0],
           &GUID_dd400ff4_a119_405f_970e_a9a5e7e828c0,
           &v20);
    if ( v5 < 0 )
      goto LABEL_30;
    v24 = 0;
    v5 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v20 + 32LL))(v20, &v24);
    if ( v5 < 0 )
      goto LABEL_30;
    v22 = 0;
    v5 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v20 + 64LL))(v20, &v22);
    if ( v5 < 0 )
      goto LABEL_30;
    v6 = v22;
    if ( (v22 & 1) != 0 )
      goto LABEL_29;
    v7 = (struct IShellItem **)((char *)this + 32);
    v5 = (*(__int64 (__fastcall **)(__int64, GUID *, char *))(*(_QWORD *)v20 + 120LL))(
           v20,
           &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93,
           (char *)this + 32);
    if ( v5 < 0 )
      goto LABEL_30;
    LOBYTE(v8) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_FolderOnDemand_SearchHydrationFix>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_Servicing_FolderOnDemand_SearchHydrationFix>::GetImpl'::`2'::impl,
      v8);
    v9 = *v7;
    v19 = 0;
    if ( ((int (__fastcall *)(struct IShellItem *, __int64 *, int *))v9->lpVtbl[2].Release)(
           v9,
           PKEY_FileReparsePointTag,
           &v19) >= 0 )
    {
      LODWORD(ppszServer) = 0;
      if ( (int)IShellItem_GetFilePlaceholderStatus(*v7, (unsigned int *)&ppszServer) < 0
        || ((unsigned __int8)ppszServer & 8) == 0 )
      {
        v22 |= 1u;
      }
    }
    v10 = *v7;
    GetDisplayName = v10->lpVtbl->GetDisplayName;
    v12 = (LPCWSTR *)((char *)this + 584);
    CoTaskMemFree(*((LPVOID *)this + 73));
    v5 = ((__int64 (__fastcall *)(struct IShellItem *, __int64, char *))GetDisplayName)(
           v10,
           2147647488LL,
           (char *)this + 584);
    if ( v5 < 0 )
      goto LABEL_30;
    v6 = v22;
    if ( (v22 & 1) != 0 )
      goto LABEL_29;
    *((_DWORD *)this + 10) = PathIsNetworkPathW(*v12);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_50465617>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_50465617>::GetImpl'::`2'::impl) )
    {
      if ( *((_DWORD *)this + 10) && (v22 & 0x400) == 0 )
        goto LABEL_16;
    }
    else if ( *((_DWORD *)this + 10) )
    {
LABEL_16:
      ppszServer = 0;
      v5 = PathConvertToUNC(*v12, (unsigned __int16 **)&ppszServer);
      if ( v5 < 0 )
        goto LABEL_30;
      CoTaskMemFree((LPVOID)*v12);
      v13 = ppszServer;
      v5 = -2147024809;
      *v12 = ppszServer;
      ppszServer = 0;
      if ( !PathIsUNCEx(v13, &ppszServer) )
      {
LABEL_27:
        if ( v5 >= 0 )
        {
          v6 = v22;
LABEL_29:
          *(_DWORD *)a3 = v6;
        }
LABEL_30:
        ATL::CComPtr<IResultShape>::~CComPtr<IResultShape>(&v20);
        goto LABEL_31;
      }
      v14 = StrChrW(ppszServer, 0x5Cu);
      v15 = ppszServer;
      if ( v14 )
      {
        v16 = v14 - ppszServer;
        if ( !v16 )
          goto LABEL_27;
        v17 = StringCchCopyNW((unsigned __int16 *)this + 30, 0x104u, ppszServer, v16);
        goto LABEL_26;
      }
      if ( !*ppszServer )
        goto LABEL_27;
LABEL_25:
      v17 = StringCchCopyW((unsigned __int16 *)this + 30, 0x104u, v15);
LABEL_26:
      v5 = v17;
      goto LABEL_27;
    }
    v15 = L".";
    goto LABEL_25;
  }
LABEL_31:
  ATL::CComPtr<IResultShape>::~CComPtr<IResultShape>(v21);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18005ec20  push    rbp
0x18005ec22  push    rbx
0x18005ec23  push    rsi
0x18005ec24  push    rdi
0x18005ec25  push    r12
0x18005ec27  push    r14
0x18005ec29  push    r15
0x18005ec2b  mov     rbp, rsp
0x18005ec2e  sub     rsp, 40h
0x18005ec32  mov     r15, r8
0x18005ec35  mov     r9, rdx
0x18005ec38  mov     rsi, rcx
0x18005ec3b  xor     r12d, r12d
0x18005ec3e  mov     [r8], r12d
0x18005ec41  mov     [rbp+var_10], r12
0x18005ec45  mov     rax, [rdx]
0x18005ec48  lea     r8, [rbp+var_10]
0x18005ec4c  lea     rdx, _GUID_bb15caac_019b_4065_a1c3_37c4fc1c599a
0x18005ec53  mov     rcx, r9
0x18005ec56  mov     rax, [rax]
0x18005ec59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ec5e  mov     ebx, eax
0x18005ec60  test    eax, eax
0x18005ec62  js      loc_18005EE83
0x18005ec68  mov     [rbp+var_18], r12
0x18005ec6c  mov     rcx, [rbp+var_10]
0x18005ec70  mov     rax, [rcx]
0x18005ec73  lea     r8, [rbp+var_18]
0x18005ec77  lea     rdx, _GUID_dd400ff4_a119_405f_970e_a9a5e7e828c0
0x18005ec7e  mov     rax, [rax+60h]
0x18005ec82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ec87  mov     ebx, eax
0x18005ec89  test    eax, eax
0x18005ec8b  js      loc_18005EE79
0x18005ec91  mov     [rbp+arg_18], r12d
0x18005ec95  mov     rcx, [rbp+var_18]
0x18005ec99  mov     rax, [rcx]
0x18005ec9c  lea     rdx, [rbp+arg_18]
0x18005eca0  mov     rax, [rax+20h]
0x18005eca4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005eca9  mov     ebx, eax
0x18005ecab  test    eax, eax
0x18005ecad  js      loc_18005EE79
0x18005ecb3  mov     [rbp+arg_8], r12d
0x18005ecb7  mov     rcx, [rbp+var_18]
0x18005ecbb  mov     rax, [rcx]
0x18005ecbe  lea     rdx, [rbp+arg_8]
0x18005ecc2  mov     rax, [rax+40h]
0x18005ecc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005eccb  mov     ebx, eax
0x18005eccd  test    eax, eax
0x18005eccf  js      loc_18005EE79
0x18005ecd5  mov     eax, [rbp+arg_8]
0x18005ecd8  test    al, 1
0x18005ecda  jnz     loc_18005EE76
0x18005ece0  mov     rcx, [rbp+var_18]
0x18005ece4  lea     rdi, [rsi+20h]
0x18005ece8  mov     rax, [rcx]
0x18005eceb  mov     r8, rdi
0x18005ecee  lea     rdx, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93
0x18005ecf5  mov     rax, [rax+78h]
0x18005ecf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ecfe  mov     ebx, eax
0x18005ed00  test    eax, eax
0x18005ed02  js      loc_18005EE79
0x18005ed08  mov     dl, 1
0x18005ed0a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_FolderOnDemand_SearchHydrationFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_FolderOnDemand_SearchHydrationFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_FolderOnDemand_SearchHydrationFix> `wil::Feature<__WilFeatureTraits_Feature_Servicing_FolderOnDemand_SearchHydrationFix>::GetImpl(void)'::`2'::impl
0x18005ed11  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_FolderOnDemand_SearchHydrationFix@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_FolderOnDemand_SearchHydrationFix>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18005ed16  mov     rcx, [rdi]
0x18005ed19  mov     [rbp+var_20], r12d
0x18005ed1d  mov     rax, [rcx]
0x18005ed20  lea     r8, [rbp+var_20]
0x18005ed24  lea     rdx, PKEY_FileReparsePointTag
0x18005ed2b  mov     rax, [rax+90h]
0x18005ed32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ed37  test    eax, eax
0x18005ed39  js      short loc_18005ED59
0x18005ed3b  mov     dword ptr [rbp+ppszServer], r12d
0x18005ed3f  lea     rdx, [rbp+ppszServer]; unsigned int *
0x18005ed43  mov     rcx, [rdi]; struct IShellItem *
0x18005ed46  call    ?IShellItem_GetFilePlaceholderStatus@@YAJPEAUIShellItem@@PEAK@Z; IShellItem_GetFilePlaceholderStatus(IShellItem *,ulong *)
0x18005ed4b  test    eax, eax
0x18005ed4d  js      short loc_18005ED55
0x18005ed4f  test    byte ptr [rbp+ppszServer], 8
0x18005ed53  jnz     short loc_18005ED59
0x18005ed55  or      [rbp+arg_8], 1
0x18005ed59  mov     rdi, [rdi]
0x18005ed5c  mov     rax, [rdi]
0x18005ed5f  mov     rbx, [rax+28h]
0x18005ed63  lea     r14, [rsi+248h]
0x18005ed6a  mov     rcx, [r14]; pv
0x18005ed6d  call    cs:__imp_CoTaskMemFree
0x18005ed73  mov     r8, r14
0x18005ed76  mov     edx, 80028000h
0x18005ed7b  mov     rcx, rdi
0x18005ed7e  mov     rax, rbx
0x18005ed81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ed86  mov     ebx, eax
0x18005ed88  test    eax, eax
0x18005ed8a  js      loc_18005EE79
0x18005ed90  mov     eax, [rbp+arg_8]
0x18005ed93  test    al, 1
0x18005ed95  jnz     loc_18005EE76
0x18005ed9b  mov     rcx, [r14]; pszPath
0x18005ed9e  call    cs:__imp_PathIsNetworkPathW
0x18005eda4  mov     [rsi+28h], eax
0x18005eda7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_50465617@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_50465617@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_50465617> `wil::Feature<__WilFeatureTraits_Feature_50465617>::GetImpl(void)'::`2'::impl
0x18005edae  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_50465617@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_50465617>::__private_IsEnabled(void)
0x18005edb3  test    al, al
0x18005edb5  jz      loc_18005EE4E
0x18005edbb  cmp     [rsi+28h], r12d
0x18005edbf  jz      loc_18005EE58
0x18005edc5  test    [rbp+arg_8], 400h
0x18005edcc  jnz     loc_18005EE58
0x18005edd2  mov     [rbp+ppszServer], r12
0x18005edd6  lea     rdx, [rbp+ppszServer]; unsigned __int16 **
0x18005edda  mov     rcx, [r14]; lpLocalPath
0x18005eddd  call    ?PathConvertToUNC@@YAJPEBGPEAPEAG@Z; PathConvertToUNC(ushort const *,ushort * *)
0x18005ede2  test    eax, eax
0x18005ede4  mov     ebx, eax
0x18005ede6  js      loc_18005EE79
0x18005edec  mov     rcx, [r14]; pv
0x18005edef  call    cs:__imp_CoTaskMemFree
0x18005edf5  mov     rcx, [rbp+ppszServer]; pszPath
0x18005edf9  mov     ebx, 80070057h
0x18005edfe  mov     [r14], rcx
0x18005ee01  mov     [rbp+ppszServer], r12
0x18005ee05  lea     rdx, [rbp+ppszServer]; ppszServer
0x18005ee09  call    cs:__imp_PathIsUNCEx
0x18005ee0f  test    eax, eax
0x18005ee11  jz      short loc_18005EE6F
0x18005ee13  mov     edx, 5Ch ; '\'; wMatch
0x18005ee18  mov     rcx, [rbp+ppszServer]; pszStart
0x18005ee1c  call    cs:__imp_StrChrW
0x18005ee22  test    rax, rax
0x18005ee25  mov     r8, [rbp+ppszServer]; unsigned __int16 *
0x18005ee29  jnz     short loc_18005EE33
0x18005ee2b  cmp     [r8], r12w
0x18005ee2f  jz      short loc_18005EE6F
0x18005ee31  jmp     short loc_18005EE5F
0x18005ee33  sub     rax, r8
0x18005ee36  sar     rax, 1
0x18005ee39  jz      short loc_18005EE6F
0x18005ee3b  mov     r9, rax; unsigned __int64
0x18005ee3e  mov     edx, 104h; unsigned __int64
0x18005ee43  lea     rcx, [rsi+3Ch]; unsigned __int16 *
0x18005ee47  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18005ee4c  jmp     short loc_18005EE6D
0x18005ee4e  cmp     [rsi+28h], r12d
0x18005ee52  jnz     loc_18005EDD2
0x18005ee58  lea     r8, asc_1800FF108; "."
0x18005ee5f  mov     edx, 104h; unsigned __int64
0x18005ee64  lea     rcx, [rsi+3Ch]; unsigned __int16 *
0x18005ee68  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18005ee6d  mov     ebx, eax
0x18005ee6f  test    ebx, ebx
0x18005ee71  js      short loc_18005EE79
0x18005ee73  mov     eax, [rbp+arg_8]
0x18005ee76  mov     [r15], eax
0x18005ee79  lea     rcx, [rbp+var_18]
0x18005ee7d  call    ??1?$CComPtr@UIResultShape@@@ATL@@QEAA@XZ; ATL::CComPtr<IResultShape>::~CComPtr<IResultShape>(void)
0x18005ee82  nop
0x18005ee83  lea     rcx, [rbp+var_10]
0x18005ee87  call    ??1?$CComPtr@UIResultShape@@@ATL@@QEAA@XZ; ATL::CComPtr<IResultShape>::~CComPtr<IResultShape>(void)
0x18005ee8c  mov     eax, ebx
0x18005ee8e  add     rsp, 40h
0x18005ee92  pop     r15
0x18005ee94  pop     r14
0x18005ee96  pop     r12
0x18005ee98  pop     rdi
0x18005ee99  pop     rsi
0x18005ee9a  pop     rbx
0x18005ee9b  pop     rbp
0x18005ee9c  retn
```
