# SyncProviderTelemetryHelpers::GetFilePath(IShellItem *,ushort * *)

- ea: `0x1800047b0`
- end: `0x1800049d1`
- name: `?GetFilePath@SyncProviderTelemetryHelpers@@SAJPEAUIShellItem@@PEAPEAG@Z`
- size: `545`
- prototype: `__int64 __fastcall(struct IShellItem *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001966c`

## callees

- `0x1800033d0`
- `0x1800047b0`
- `0x1800049e0`
- `0x180004a10`
- `0x180011ac4`
- `0x1800125f8`
- `0x180019f70`
- `0x180021ec0`
- `0x180051010`

## import_xrefs

- `SHELL32!SHCreateItemFromIDList` at `0x18000491a`
- `SHELL32!SHCreateItemFromIDList` at `0x18000491a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004885`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000498e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004885`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000498e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800048f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004983`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800048f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004983`

## string_xrefs

- `0x1800047ed`: `onecoreuap\internal\shell\inc\private\piiSafeShellitemParsingName.h`
- `0x18000486f`: `onecoreuap\internal\shell\inc\private\piiSafeShellitemParsingName.h`
- `0x1800048cf`: `onecoreuap\internal\shell\inc\private\piiSafeShellitemParsingName.h`
- `0x18000492d`: `onecoreuap\internal\shell\inc\private\piiSafeShellitemParsingName.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall SyncProviderTelemetryHelpers::GetFilePath(struct IShellItem *a1, unsigned __int16 **a2)
{
  int v4; // eax
  int v5; // ebx
  int v6; // eax
  void *v7; // rcx
  HRESULT v8; // eax
  void *v9; // rcx
  int v11; // eax
  PROPVARIANT pvar[2]; // [rsp+20h] [rbp-40h] BYREF
  int v13; // [rsp+30h] [rbp-30h]
  LPVOID *p_pv; // [rsp+40h] [rbp-20h] BYREF
  __int64 v15; // [rsp+48h] [rbp-18h] BYREF
  char v16; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  LPVOID pv; // [rsp+88h] [rbp+28h] BYREF
  void *ppv; // [rsp+90h] [rbp+30h] BYREF
  __int64 v20; // [rsp+98h] [rbp+38h] BYREF

  *a2 = 0;
  v20 = 0;
  v4 = wil::PropertyStoreHelperBase<IPropertyStore>::InitFromItem(&v20, a1);
  v5 = v4;
  if ( v4 >= 0 )
  {
    LODWORD(pv) = 0;
    *(_OWORD *)pvar = PKEY_Home_GraphFileType;
    v13 = 19;
    if ( (int)wil::PropertyStoreHelperBase<IPropertyStore>::GetUInt32<_tagpropertykey>(&v20, pvar, &pv) >= 0
      && (_DWORD)pv )
    {
      LOWORD(pvar[0]) = 0;
      v6 = (*(__int64 (__fastcall **)(__int64, __int64 *, PROPVARIANT *))(*(_QWORD *)v20 + 40LL))(
             v20,
             PKEY_DelegateIDList,
             pvar);
      v5 = v6;
      if ( v6 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xEA,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\piiSafeShellitemParsingName.h",
          (const char *)(unsigned int)v6,
          (int)pvar[0]);
LABEL_7:
        PropVariantClear(pvar);
        goto LABEL_20;
      }
      pv = 0;
      p_pv = &pv;
      v15 = 0;
      v16 = 1;
      v5 = PropVariantToIDList(pvar, &v15);
      wil::details::out_param_t<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>((__int64)&p_pv);
      if ( v5 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xEC,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\piiSafeShellitemParsingName.h",
          (const char *)(unsigned int)v5,
          (int)pvar[0]);
        goto LABEL_10;
      }
      ppv = 0;
      Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&ppv);
      v8 = SHCreateItemFromIDList((LPCITEMIDLIST)pv, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
      v5 = v8;
      if ( v8 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xEE,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\piiSafeShellitemParsingName.h",
          (const char *)(unsigned int)v8,
          (int)pvar[0]);
LABEL_14:
        Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&ppv);
LABEL_10:
        v7 = pv;
        pv = 0;
        if ( v7 )
          CoTaskMemFree(v7);
        goto LABEL_7;
      }
      v5 = (*(__int64 (__fastcall **)(void *, __int64, unsigned __int16 **))(*(_QWORD *)ppv + 40LL))(
             ppv,
             2147844096LL,
             a2);
      if ( v5 < 0 )
        goto LABEL_14;
      Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&ppv);
      v9 = pv;
      pv = 0;
      if ( v9 )
        CoTaskMemFree(v9);
      PropVariantClear(pvar);
    }
    else
    {
      v11 = ((__int64 (__fastcall *)(struct IShellItem *, __int64, unsigned __int16 **))a1->lpVtbl->GetDisplayName)(
              a1,
              2147844096LL,
              a2);
      if ( v11 < 0 )
      {
        v5 = v11;
        goto LABEL_20;
      }
    }
    v5 = 0;
    goto LABEL_20;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xE1,
    (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\piiSafeShellitemParsingName.h",
    (const char *)(unsigned int)v4,
    (int)pvar[0]);
LABEL_20:
  Microsoft::WRL::ComPtr<IDBFolderPriv>::~ComPtr<IDBFolderPriv>(&v20);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800047b0  mov     [rsp-18h+arg_0], rbx
0x1800047b5  push    rbp
0x1800047b6  push    rsi
0x1800047b7  push    rdi
0x1800047b8  mov     rbp, rsp
0x1800047bb  sub     rsp, 60h
0x1800047bf  mov     rsi, rdx
0x1800047c2  mov     rdi, rcx
0x1800047c5  mov     qword ptr [rdx], 0
0x1800047cc  mov     [rbp+arg_18], 0
0x1800047d4  mov     rdx, rcx
0x1800047d7  lea     rcx, [rbp+arg_18]
0x1800047db  call    ?InitFromItem@?$PropertyStoreHelperBase@UIPropertyStore@@@wil@@QEAAJPEAUIUnknown@@W4GETPROPERTYSTOREFLAGS@@@Z; wil::PropertyStoreHelperBase<IPropertyStore>::InitFromItem(IUnknown *,GETPROPERTYSTOREFLAGS)
0x1800047e0  mov     ebx, eax
0x1800047e2  test    eax, eax
0x1800047e4  jns     short loc_180004803
0x1800047e6  mov     rcx, [rbp+18h]; this
0x1800047ea  mov     r9d, eax; char *
0x1800047ed  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\priva"...
0x1800047f4  mov     edx, 0E1h; void *
0x1800047f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800047fe  jmp     loc_180004996
0x180004803  mov     dword ptr [rbp+pv], 0
0x18000480a  movups  xmm0, cs:PKEY_Home_GraphFileType
0x180004811  movaps  xmmword ptr [rbp+pvar], xmm0
0x180004815  mov     eax, cs:dword_180058580
0x18000481b  mov     [rbp+var_30], eax
0x18000481e  lea     r8, [rbp+pv]
0x180004822  lea     rdx, [rbp+pvar]
0x180004826  lea     rcx, [rbp+arg_18]
0x18000482a  call    ??$GetUInt32@U_tagpropertykey@@@?$PropertyStoreHelperBase@UIPropertyStore@@@wil@@QEBAJU_tagpropertykey@@PEAK@Z; wil::PropertyStoreHelperBase<IPropertyStore>::GetUInt32<_tagpropertykey>(_tagpropertykey,ulong *)
0x18000482f  test    eax, eax
0x180004831  js      loc_1800049B1
0x180004837  cmp     dword ptr [rbp+pv], 0
0x18000483b  jz      loc_1800049B1
0x180004841  xor     eax, eax
0x180004843  mov     word ptr [rbp+pvar], ax
0x180004847  mov     rcx, [rbp+arg_18]
0x18000484b  mov     rax, [rcx]
0x18000484e  lea     r8, [rbp+pvar]
0x180004852  lea     rdx, PKEY_DelegateIDList
0x180004859  mov     rax, [rax+28h]
0x18000485d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004862  mov     ebx, eax
0x180004864  test    eax, eax
0x180004866  jns     short loc_180004890
0x180004868  mov     rcx, [rbp+18h]; this
0x18000486c  mov     r9d, eax; char *
0x18000486f  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\priva"...
0x180004876  mov     edx, 0EAh; void *
0x18000487b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004880  nop
0x180004881  lea     rcx, [rbp+pvar]; pvar
0x180004885  call    cs:__imp_PropVariantClear
0x18000488b  jmp     loc_180004996
0x180004890  mov     [rbp+pv], 0
0x180004898  lea     rax, [rbp+pv]
0x18000489c  mov     [rbp+var_20], rax
0x1800048a0  mov     [rbp+var_18], 0
0x1800048a8  mov     [rbp+var_10], 1
0x1800048ac  lea     rdx, [rbp+var_18]
0x1800048b0  lea     rcx, [rbp+pvar]
0x1800048b4  call    PropVariantToIDList
0x1800048b9  mov     ebx, eax
0x1800048bb  lea     rcx, [rbp+var_20]
0x1800048bf  call    ??1?$out_param_t@V?$unique_ptr@U_ITEMIDLIST_ABSOLUTE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1800048c4  test    ebx, ebx
0x1800048c6  jns     short loc_1800048FA
0x1800048c8  mov     rcx, [rbp+18h]; this
0x1800048cc  mov     r9d, ebx; char *
0x1800048cf  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\priva"...
0x1800048d6  mov     edx, 0ECh; void *
0x1800048db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800048e0  nop
0x1800048e1  mov     rcx, [rbp+pv]; pv
0x1800048e5  mov     [rbp+pv], 0
0x1800048ed  test    rcx, rcx
0x1800048f0  jz      short loc_180004881
0x1800048f2  call    cs:__imp_CoTaskMemFree
0x1800048f8  jmp     short loc_180004881
0x1800048fa  mov     [rbp+ppv], 0
0x180004902  lea     rcx, [rbp+ppv]
0x180004906  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18000490b  lea     r8, [rbp+ppv]; ppv
0x18000490f  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180004916  mov     rcx, [rbp+pv]; pidl
0x18000491a  call    cs:__imp_SHCreateItemFromIDList
0x180004920  mov     ebx, eax
0x180004922  test    eax, eax
0x180004924  jns     short loc_18000494A
0x180004926  mov     rcx, [rbp+18h]; this
0x18000492a  mov     r9d, eax; char *
0x18000492d  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\priva"...
0x180004934  mov     edx, 0EEh; void *
0x180004939  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000493e  nop
0x18000493f  lea     rcx, [rbp+ppv]
0x180004943  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180004948  jmp     short loc_1800048E1
0x18000494a  mov     rcx, [rbp+ppv]
0x18000494e  mov     rax, [rcx]
0x180004951  mov     r8, rsi
0x180004954  mov     edx, 80058000h
0x180004959  mov     rax, [rax+28h]
0x18000495d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004962  mov     ebx, eax
0x180004964  lea     rcx, [rbp+ppv]
0x180004968  test    eax, eax
0x18000496a  js      short loc_180004943
0x18000496c  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180004971  nop
0x180004972  mov     rcx, [rbp+pv]; pv
0x180004976  mov     [rbp+pv], 0
0x18000497e  test    rcx, rcx
0x180004981  jz      short loc_18000498A
0x180004983  call    cs:__imp_CoTaskMemFree
0x180004989  nop
0x18000498a  lea     rcx, [rbp+pvar]; pvar
0x18000498e  call    cs:__imp_PropVariantClear
0x180004994  xor     ebx, ebx
0x180004996  lea     rcx, [rbp+arg_18]
0x18000499a  call    ??1?$ComPtr@UIDBFolderPriv@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<IDBFolderPriv>::~ComPtr<IDBFolderPriv>(void)
0x18000499f  mov     eax, ebx
0x1800049a1  mov     rbx, [rsp+60h+arg_0]
0x1800049a9  add     rsp, 60h
0x1800049ad  pop     rdi
0x1800049ae  pop     rsi
0x1800049af  pop     rbp
0x1800049b0  retn
0x1800049b1  mov     rax, [rdi]
0x1800049b4  mov     r8, rsi
0x1800049b7  mov     edx, 80058000h
0x1800049bc  mov     rcx, rdi
0x1800049bf  mov     rax, [rax+28h]
0x1800049c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049c8  test    eax, eax
0x1800049ca  jns     short loc_180004994
0x1800049cc  mov     ebx, eax
0x1800049ce  jmp     short loc_180004996
```
