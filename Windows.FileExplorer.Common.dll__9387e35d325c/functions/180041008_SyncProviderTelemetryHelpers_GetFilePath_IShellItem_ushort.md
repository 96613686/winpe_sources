# SyncProviderTelemetryHelpers::GetFilePath(IShellItem *,ushort * *)

- ea: `0x180041008`
- end: `0x180041219`
- name: `?GetFilePath@SyncProviderTelemetryHelpers@@SAJPEAUIShellItem@@PEAPEAG@Z`
- size: `529`
- prototype: `__int64 __fastcall(struct IShellItem *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x180041690`

## callees

- `0x180004a54`
- `0x1800077c8`
- `0x18001f138`
- `0x1800309ec`
- `0x180030a20`
- `0x180031a24`
- `0x180031c54`
- `0x18003cccc`
- `0x180041008`
- `0x180044114`
- `0x180089010`

## import_xrefs

- `Windows.Storage!SHCreateItemFromIDList` at `0x18004116e`
- `Windows.Storage!SHCreateItemFromIDList` at `0x18004116e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800410e5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800411d6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800410e5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800411d6`

## string_xrefs

- `0x18004104d`: `onecoreuap\internal\shell\inc\private\piiSafeShellitemParsingName.h`
- `0x1800410cf`: `onecoreuap\internal\shell\inc\private\piiSafeShellitemParsingName.h`
- `0x18004112f`: `onecoreuap\internal\shell\inc\private\piiSafeShellitemParsingName.h`
- `0x180041181`: `onecoreuap\internal\shell\inc\private\piiSafeShellitemParsingName.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SyncProviderTelemetryHelpers::GetFilePath(struct IShellItem *a1, struct IPropertyStore *a2)
{
  int v4; // eax
  int v5; // ebx
  int v6; // eax
  HRESULT v7; // eax
  int v9; // eax
  PROPVARIANT pvar[2]; // [rsp+20h] [rbp-40h] BYREF
  int v11; // [rsp+30h] [rbp-30h]
  LPCITEMIDLIST *p_pidl; // [rsp+40h] [rbp-20h] BYREF
  struct _ITEMIDLIST_ABSOLUTE *v13; // [rsp+48h] [rbp-18h] BYREF
  char v14; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  void *ppv; // [rsp+88h] [rbp+28h] BYREF
  LPCITEMIDLIST pidl; // [rsp+90h] [rbp+30h] BYREF
  __int64 v18; // [rsp+98h] [rbp+38h] BYREF

  a2->lpVtbl = 0;
  wil::PropertyStoreHelper::PropertyStoreHelper((wil::PropertyStoreHelper *)&v18, a2);
  v4 = wil::PropertyStoreHelperBase<IPropertyStore>::InitFromItem(&v18, a1, 8);
  v5 = v4;
  if ( v4 >= 0 )
  {
    LODWORD(ppv) = 0;
    *(_OWORD *)pvar = PKEY_Home_GraphFileType;
    v11 = 19;
    if ( (int)wil::PropertyStoreHelperBase<IPropertyStore>::GetUInt32<_tagpropertykey>(&v18, pvar, &ppv) >= 0
      && (_DWORD)ppv )
    {
      LOWORD(pvar[0]) = 0;
      v6 = (*(__int64 (__fastcall **)(__int64, __int64 *, PROPVARIANT *))(*(_QWORD *)v18 + 40LL))(
             v18,
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
        goto LABEL_17;
      }
      pidl = 0;
      p_pidl = &pidl;
      v13 = 0;
      v14 = 1;
      v5 = PropVariantToIDList((unsigned __int16 *)pvar, &v13);
      wil::details::out_param_t<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pidl);
      if ( v5 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xEC,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\piiSafeShellitemParsingName.h",
          (const char *)(unsigned int)v5,
          (int)pvar[0]);
LABEL_10:
        wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
          &pidl,
          0);
        goto LABEL_7;
      }
      ppv = 0;
      Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&ppv);
      v7 = SHCreateItemFromIDList(pidl, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
      v5 = v7;
      if ( v7 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xEE,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\piiSafeShellitemParsingName.h",
          (const char *)(unsigned int)v7,
          (int)pvar[0]);
LABEL_13:
        Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&ppv);
        goto LABEL_10;
      }
      v5 = (*(__int64 (__fastcall **)(void *, __int64, struct IPropertyStore *))(*(_QWORD *)ppv + 40LL))(
             ppv,
             2147844096LL,
             a2);
      if ( v5 < 0 )
        goto LABEL_13;
      Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&ppv);
      wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
        &pidl,
        0);
      PropVariantClear(pvar);
    }
    else
    {
      v9 = ((__int64 (__fastcall *)(struct IShellItem *, __int64, struct IPropertyStore *))a1->lpVtbl->GetDisplayName)(
             a1,
             2147844096LL,
             a2);
      if ( v9 < 0 )
      {
        v5 = v9;
        goto LABEL_17;
      }
    }
    v5 = 0;
    goto LABEL_17;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xE1,
    (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\piiSafeShellitemParsingName.h",
    (const char *)(unsigned int)v4,
    (int)pvar[0]);
LABEL_17:
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(&v18);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180041008  mov     [rsp-18h+arg_0], rbx
0x18004100d  push    rbp
0x18004100e  push    rsi
0x18004100f  push    rdi
0x180041010  mov     rbp, rsp
0x180041013  sub     rsp, 60h
0x180041017  mov     rsi, rdx
0x18004101a  mov     rdi, rcx
0x18004101d  mov     qword ptr [rdx], 0
0x180041024  lea     rcx, [rbp+arg_18]; this
0x180041028  call    ??0PropertyStoreHelper@wil@@QEAA@PEAUIPropertyStore@@@Z; wil::PropertyStoreHelper::PropertyStoreHelper(IPropertyStore *)
0x18004102d  nop
0x18004102e  mov     r8d, 8
0x180041034  mov     rdx, rdi
0x180041037  lea     rcx, [rbp+arg_18]
0x18004103b  call    ?InitFromItem@?$PropertyStoreHelperBase@UIPropertyStore@@@wil@@QEAAJPEAUIUnknown@@W4GETPROPERTYSTOREFLAGS@@@Z; wil::PropertyStoreHelperBase<IPropertyStore>::InitFromItem(IUnknown *,GETPROPERTYSTOREFLAGS)
0x180041040  mov     ebx, eax
0x180041042  test    eax, eax
0x180041044  jns     short loc_180041063
0x180041046  mov     rcx, [rbp+18h]; this
0x18004104a  mov     r9d, eax; char *
0x18004104d  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\priva"...
0x180041054  mov     edx, 0E1h; void *
0x180041059  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004105e  jmp     loc_1800411DE
0x180041063  mov     dword ptr [rbp+ppv], 0
0x18004106a  movups  xmm0, cs:PKEY_Home_GraphFileType
0x180041071  movaps  xmmword ptr [rbp+pvar], xmm0
0x180041075  mov     eax, cs:dword_180093D90
0x18004107b  mov     [rbp+var_30], eax
0x18004107e  lea     r8, [rbp+ppv]
0x180041082  lea     rdx, [rbp+pvar]
0x180041086  lea     rcx, [rbp+arg_18]
0x18004108a  call    ??$GetUInt32@U_tagpropertykey@@@?$PropertyStoreHelperBase@UIPropertyStore@@@wil@@QEBAJU_tagpropertykey@@PEAK@Z; wil::PropertyStoreHelperBase<IPropertyStore>::GetUInt32<_tagpropertykey>(_tagpropertykey,ulong *)
0x18004108f  test    eax, eax
0x180041091  js      loc_1800411F9
0x180041097  cmp     dword ptr [rbp+ppv], 0
0x18004109b  jz      loc_1800411F9
0x1800410a1  xor     eax, eax
0x1800410a3  mov     word ptr [rbp+pvar], ax
0x1800410a7  mov     rcx, [rbp+arg_18]
0x1800410ab  mov     rax, [rcx]
0x1800410ae  lea     r8, [rbp+pvar]
0x1800410b2  lea     rdx, PKEY_DelegateIDList
0x1800410b9  mov     rax, [rax+28h]
0x1800410bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800410c2  mov     ebx, eax
0x1800410c4  test    eax, eax
0x1800410c6  jns     short loc_1800410F0
0x1800410c8  mov     rcx, [rbp+18h]; this
0x1800410cc  mov     r9d, eax; char *
0x1800410cf  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\priva"...
0x1800410d6  mov     edx, 0EAh; void *
0x1800410db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800410e0  nop
0x1800410e1  lea     rcx, [rbp+pvar]; pvar
0x1800410e5  call    cs:__imp_PropVariantClear
0x1800410eb  jmp     loc_1800411DE
0x1800410f0  mov     [rbp+pidl], 0
0x1800410f8  lea     rax, [rbp+pidl]
0x1800410fc  mov     [rbp+var_20], rax
0x180041100  mov     [rbp+var_18], 0
0x180041108  mov     [rbp+var_10], 1
0x18004110c  lea     rdx, [rbp+var_18]
0x180041110  lea     rcx, [rbp+pvar]
0x180041114  call    PropVariantToIDList
0x180041119  mov     ebx, eax
0x18004111b  lea     rcx, [rbp+var_20]
0x18004111f  call    ??1?$out_param_t@V?$unique_ptr@U_ITEMIDLIST_ABSOLUTE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180041124  test    ebx, ebx
0x180041126  jns     short loc_18004114E
0x180041128  mov     rcx, [rbp+18h]; this
0x18004112c  mov     r9d, ebx; char *
0x18004112f  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\priva"...
0x180041136  mov     edx, 0ECh; void *
0x18004113b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041140  nop
0x180041141  xor     edx, edx
0x180041143  lea     rcx, [rbp+pidl]
0x180041147  call    ?reset@?$unique_ptr@U_ITEMIDLIST_ABSOLUTE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAU_ITEMIDLIST_ABSOLUTE@@@Z; wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(_ITEMIDLIST_ABSOLUTE *)
0x18004114c  jmp     short loc_1800410E1
0x18004114e  mov     [rbp+ppv], 0
0x180041156  lea     rcx, [rbp+ppv]
0x18004115a  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18004115f  lea     r8, [rbp+ppv]; ppv
0x180041163  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18004116a  mov     rcx, [rbp+pidl]; pidl
0x18004116e  call    cs:__imp_SHCreateItemFromIDList
0x180041174  mov     ebx, eax
0x180041176  test    eax, eax
0x180041178  jns     short loc_18004119E
0x18004117a  mov     rcx, [rbp+18h]; this
0x18004117e  mov     r9d, eax; char *
0x180041181  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\priva"...
0x180041188  mov     edx, 0EEh; void *
0x18004118d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041192  nop
0x180041193  lea     rcx, [rbp+ppv]
0x180041197  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18004119c  jmp     short loc_180041141
0x18004119e  mov     rcx, [rbp+ppv]
0x1800411a2  mov     rax, [rcx]
0x1800411a5  mov     r8, rsi
0x1800411a8  mov     edx, 80058000h
0x1800411ad  mov     rax, [rax+28h]
0x1800411b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800411b6  mov     ebx, eax
0x1800411b8  lea     rcx, [rbp+ppv]
0x1800411bc  test    eax, eax
0x1800411be  js      short loc_180041197
0x1800411c0  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x1800411c5  nop
0x1800411c6  xor     edx, edx
0x1800411c8  lea     rcx, [rbp+pidl]
0x1800411cc  call    ?reset@?$unique_ptr@U_ITEMIDLIST_ABSOLUTE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAU_ITEMIDLIST_ABSOLUTE@@@Z; wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(_ITEMIDLIST_ABSOLUTE *)
0x1800411d1  nop
0x1800411d2  lea     rcx, [rbp+pvar]; pvar
0x1800411d6  call    cs:__imp_PropVariantClear
0x1800411dc  xor     ebx, ebx
0x1800411de  lea     rcx, [rbp+arg_18]
0x1800411e2  call    ??1?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(void)
0x1800411e7  mov     eax, ebx
0x1800411e9  mov     rbx, [rsp+60h+arg_0]
0x1800411f1  add     rsp, 60h
0x1800411f5  pop     rdi
0x1800411f6  pop     rsi
0x1800411f7  pop     rbp
0x1800411f8  retn
0x1800411f9  mov     rax, [rdi]
0x1800411fc  mov     r8, rsi
0x1800411ff  mov     edx, 80058000h
0x180041204  mov     rcx, rdi
0x180041207  mov     rax, [rax+28h]
0x18004120b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041210  test    eax, eax
0x180041212  jns     short loc_1800411DC
0x180041214  mov     ebx, eax
0x180041216  jmp     short loc_1800411DE
```
