# CDBFolder::TranslateIDs(long *,_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_ABSOLUTE * *,_ITEMIDLIST_ABSOLUTE * *,long *,_ITEMIDLIST_ABSOLUTE * *,_ITEMIDLIST_ABSOLUTE * *)

- ea: `0x180065100`
- end: `0x180065343`
- name: `?TranslateIDs@CDBFolder@@UEAAJPEAJPEBU_ITEMIDLIST_ABSOLUTE@@1PEAPEAU2@2022@Z`
- size: `579`
- prototype: `int(CDBFolder *__hidden this, int *, const struct _ITEMIDLIST_ABSOLUTE *, const struct _ITEMIDLIST_ABSOLUTE *, struct _ITEMIDLIST_ABSOLUTE **, struct _ITEMIDLIST_ABSOLUTE **, int *, struct _ITEMIDLIST_ABSOLUTE **, struct _ITEMIDLIST_ABSOLUTE **)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180007c70`
- `0x180014498`
- `0x18004fe14`
- `0x1800515d8`
- `0x180063a68`
- `0x180063f24`
- `0x180064790`
- `0x180065100`
- `0x180082b24`
- `0x1800830e0`
- `0x180087f54`
- `0x1800ea010`

## import_xrefs

- `Windows.Storage!SHCreateItemFromIDList` at `0x180065156`
- `Windows.Storage!SHCreateItemFromIDList` at `0x180065156`
- `Windows.Storage!ILCombine` at `0x1800652ec`
- `Windows.Storage!ILCombine` at `0x1800652ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800652d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180065302`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800652d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180065302`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180065206`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180065317`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180065206`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180065317`
- `PROPSYS!PropVariantToStringAlloc` at `0x180065237`
- `PROPSYS!PropVariantToStringAlloc` at `0x180065237`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CDBFolder::TranslateIDs(
        LPCITEMIDLIST *this,
        int *a2,
        const ITEMIDLIST *a3,
        const struct _ITEMIDLIST_ABSOLUTE *a4,
        struct _ITEMIDLIST_ABSOLUTE **a5,
        struct _ITEMIDLIST_ABSOLUTE **a6,
        int *a7,
        struct _ITEMIDLIST_ABSOLUTE **a8,
        struct _ITEMIDLIST_ABSOLUTE **a9)
{
  HRESULT v11; // eax
  struct IBindCtx *v12; // rdx
  int v13; // ebx
  int v14; // eax
  int v15; // eax
  void *v16; // rcx
  void *v17; // rcx
  int v19; // [rsp+20h] [rbp-61h]
  int v20; // [rsp+20h] [rbp-61h]
  PWSTR ppszOut; // [rsp+40h] [rbp-41h] BYREF
  LPBC ppbc; // [rsp+48h] [rbp-39h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-31h] BYREF
  void *ppv; // [rsp+58h] [rbp-29h] BYREF
  PROPVARIANT pvar[3]; // [rsp+60h] [rbp-21h] BYREF
  LPVOID *p_pv; // [rsp+78h] [rbp-9h] BYREF
  struct _ITEMIDLIST_RELATIVE *v27; // [rsp+80h] [rbp-1h] BYREF
  char v28; // [rsp+88h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+37h]

  AssertAnyEnabled<wil::Feature<__WilFeatureTraits_Feature_Servicing_FileExplorerDehydratedThumbnailsChangeNotificationsFix>,wil::Feature<__WilFeatureTraits_Feature_FI45690266>>(
    this,
    a2,
    a3,
    a4);
  *a5 = 0;
  *a6 = 0;
  *a7 = 0;
  *a8 = 0;
  *a9 = 0;
  ppv = 0;
  v11 = SHCreateItemFromIDList(a3, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, &ppv);
  v13 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x23FA,
      (unsigned int)"onecoreuap\\shell\\windows.storage.search\\dbfolder.cpp",
      (const char *)(unsigned int)v11,
      v19);
    goto LABEL_20;
  }
  wil::ShellBindContextHelper::ShellBindContextHelper(&ppbc, v12);
  v14 = wil::ShellBindContextHelper::InitFromItemParsingBindContext(
          (wil::ShellBindContextHelper *)&ppbc,
          (struct IShellItem *)ppv);
  v13 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x23FD,
      (unsigned int)"onecoreuap\\shell\\windows.storage.search\\dbfolder.cpp",
      (const char *)(unsigned int)v14,
      v19);
LABEL_5:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppbc);
    goto LABEL_20;
  }
  LOWORD(pvar[0]) = 0;
  v15 = (*(__int64 (__fastcall **)(void *, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)ppv + 104LL))(
          ppv,
          &PKEY_FileName,
          pvar);
  v13 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2400,
      (unsigned int)"onecoreuap\\shell\\windows.storage.search\\dbfolder.cpp",
      (const char *)(unsigned int)v15,
      v19);
LABEL_8:
    PropVariantClear(pvar);
    goto LABEL_5;
  }
  ppszOut = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &ppszOut,
    0);
  ppszOut = 0;
  if ( !LOWORD(pvar[0]) )
  {
    v13 = -2147023728;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2402,
      (unsigned int)"onecoreuap\\shell\\windows.storage.search\\dbfolder.cpp",
      (const char *)(unsigned int)v13,
      v19);
LABEL_13:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&ppszOut);
    goto LABEL_8;
  }
  v13 = PropVariantToStringAlloc(pvar, &ppszOut);
  if ( v13 < 0 )
    goto LABEL_12;
  pv = 0;
  p_pv = &pv;
  v27 = 0;
  v28 = 1;
  v13 = CDBFolder::ParseDisplayName((CDBFolder *)(this - 24), 0, ppbc, ppszOut, 0, &v27, 0);
  wil::details::out_param_t<wistd::unique_ptr<_ITEMIDLIST_RELATIVE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMIDLIST_RELATIVE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2405,
      (unsigned int)"onecoreuap\\shell\\windows.storage.search\\dbfolder.cpp",
      (const char *)(unsigned int)v13,
      v20);
    v16 = pv;
    pv = 0;
    if ( v16 )
      CoTaskMemFree(v16);
    goto LABEL_13;
  }
  *a5 = (struct _ITEMIDLIST_ABSOLUTE *)ILCombine(this[4], (LPCITEMIDLIST)pv);
  v17 = pv;
  pv = 0;
  if ( v17 )
    CoTaskMemFree(v17);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&ppszOut);
  PropVariantClear(pvar);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppbc);
  v13 = 0;
LABEL_20:
  wil::com_ptr_t<IInitializeSortColumnArray,wil::err_exception_policy>::~com_ptr_t<IInitializeSortColumnArray,wil::err_exception_policy>(&ppv);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180065100  push    rbp
0x180065102  push    rbx
0x180065103  push    rsi
0x180065104  push    rdi
0x180065105  push    r14
0x180065107  lea     rbp, [rsp-0Fh]
0x18006510c  sub     rsp, 90h
0x180065113  mov     rbx, r8
0x180065116  mov     rdi, rcx
0x180065119  call    ??$AssertAnyEnabled@V?$Feature@U__WilFeatureTraits_Feature_Servicing_FileExplorerDehydratedThumbnailsChangeNotificationsFix@@@wil@@V?$Feature@U__WilFeatureTraits_Feature_FI45690266@@@2@@@YAXXZ; AssertAnyEnabled<wil::Feature<__WilFeatureTraits_Feature_Servicing_FileExplorerDehydratedThumbnailsChangeNotificationsFix>,wil::Feature<__WilFeatureTraits_Feature_FI45690266>>(void)
0x18006511e  xor     r14d, r14d
0x180065121  mov     rsi, [rbp+2Fh+arg_20]
0x180065125  mov     [rsi], r14
0x180065128  mov     rax, [rbp+2Fh+arg_28]
0x18006512c  mov     [rax], r14
0x18006512f  mov     rax, [rbp+2Fh+arg_30]
0x180065133  mov     [rax], r14d
0x180065136  mov     rax, [rbp+2Fh+arg_38]
0x18006513a  mov     [rax], r14
0x18006513d  mov     rax, [rbp+2Fh+arg_40]
0x180065141  mov     [rax], r14
0x180065144  mov     [rbp+2Fh+ppv], r14
0x180065148  lea     r8, [rbp+2Fh+ppv]; ppv
0x18006514c  lea     rdx, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93; riid
0x180065153  mov     rcx, rbx; pidl
0x180065156  call    cs:__imp_SHCreateItemFromIDList
0x18006515c  mov     ebx, eax
0x18006515e  test    eax, eax
0x180065160  jns     short loc_18006517F
0x180065162  mov     rcx, [rbp+37h]; this
0x180065166  mov     r9d, eax; char *
0x180065169  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\windows.storage.sear"...
0x180065170  mov     edx, 23FAh; void *
0x180065175  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006517a  jmp     loc_18006532A
0x18006517f  lea     rcx, [rbp+2Fh+ppbc]; ppbc
0x180065183  call    ??0ShellBindContextHelper@wil@@QEAA@PEAUIBindCtx@@@Z; wil::ShellBindContextHelper::ShellBindContextHelper(IBindCtx *)
0x180065188  nop
0x180065189  mov     rdx, [rbp+2Fh+ppv]; struct IShellItem *
0x18006518d  lea     rcx, [rbp+2Fh+ppbc]; this
0x180065191  call    ?InitFromItemParsingBindContext@ShellBindContextHelper@wil@@QEAAJPEAUIShellItem@@@Z; wil::ShellBindContextHelper::InitFromItemParsingBindContext(IShellItem *)
0x180065196  mov     ebx, eax
0x180065198  test    eax, eax
0x18006519a  jns     short loc_1800651C3
0x18006519c  mov     rcx, [rbp+37h]; this
0x1800651a0  mov     r9d, eax; char *
0x1800651a3  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\windows.storage.sear"...
0x1800651aa  mov     edx, 23FDh; void *
0x1800651af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800651b4  nop
0x1800651b5  lea     rcx, [rbp+2Fh+ppbc]
0x1800651b9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800651be  jmp     loc_18006532A
0x1800651c3  mov     word ptr [rbp+2Fh+pvar], r14w
0x1800651c8  mov     rcx, [rbp+2Fh+ppv]
0x1800651cc  mov     rax, [rcx]
0x1800651cf  lea     r8, [rbp+2Fh+pvar]
0x1800651d3  lea     rdx, PKEY_FileName
0x1800651da  mov     rax, [rax+68h]
0x1800651de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800651e3  mov     ebx, eax
0x1800651e5  test    eax, eax
0x1800651e7  jns     short loc_18006520E
0x1800651e9  mov     rcx, [rbp+37h]; this
0x1800651ed  mov     r9d, eax; char *
0x1800651f0  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\windows.storage.sear"...
0x1800651f7  mov     edx, 2400h; void *
0x1800651fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180065201  nop
0x180065202  lea     rcx, [rbp+2Fh+pvar]; pvar
0x180065206  call    cs:__imp_PropVariantClear
0x18006520c  jmp     short loc_1800651B5
0x18006520e  mov     [rbp+2Fh+ppszOut], r14
0x180065212  xor     edx, edx
0x180065214  lea     rcx, [rbp+2Fh+ppszOut]
0x180065218  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18006521d  mov     [rbp+2Fh+ppszOut], r14
0x180065221  cmp     word ptr [rbp+2Fh+pvar], r14w
0x180065226  jnz     short loc_18006522F
0x180065228  mov     ebx, 80070490h
0x18006522d  jmp     short loc_180065243
0x18006522f  lea     rdx, [rbp+2Fh+ppszOut]; ppszOut
0x180065233  lea     rcx, [rbp+2Fh+pvar]; propvar
0x180065237  call    cs:__imp_PropVariantToStringAlloc
0x18006523d  mov     ebx, eax
0x18006523f  test    eax, eax
0x180065241  jns     short loc_180065267
0x180065243  mov     rcx, [rbp+37h]; this
0x180065247  mov     r9d, ebx; char *
0x18006524a  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\windows.storage.sear"...
0x180065251  mov     edx, 2402h; void *
0x180065256  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006525b  nop
0x18006525c  lea     rcx, [rbp+2Fh+ppszOut]
0x180065260  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180065265  jmp     short loc_180065202
0x180065267  mov     [rbp+2Fh+pv], r14
0x18006526b  lea     rax, [rbp+2Fh+pv]
0x18006526f  mov     [rbp+2Fh+var_38], rax
0x180065273  mov     [rbp+2Fh+var_30], r14
0x180065277  mov     [rbp+2Fh+var_28], 1
0x18006527b  lea     rcx, [rdi-0C0h]; this
0x180065282  mov     [rsp+0B0h+var_80], r14; unsigned int *
0x180065287  lea     rax, [rbp+2Fh+var_30]
0x18006528b  mov     [rsp+0B0h+var_88], rax; struct _ITEMIDLIST_RELATIVE **
0x180065290  mov     [rsp+0B0h+var_90], r14; int
0x180065295  mov     r9, [rbp+2Fh+ppszOut]; unsigned __int16 *
0x180065299  mov     r8, [rbp+2Fh+ppbc]; struct IBindCtx *
0x18006529d  xor     edx, edx; HWND
0x18006529f  call    ?ParseDisplayName@CDBFolder@@UEAAJPEAUHWND__@@PEAUIBindCtx@@PEAGPEAKPEAPEAU_ITEMIDLIST_RELATIVE@@3@Z; CDBFolder::ParseDisplayName(HWND__ *,IBindCtx *,ushort *,ulong *,_ITEMIDLIST_RELATIVE * *,ulong *)
0x1800652a4  mov     ebx, eax
0x1800652a6  lea     rcx, [rbp+2Fh+var_38]
0x1800652aa  call    ??1?$out_param_t@V?$unique_ptr@U_ITEMIDLIST_RELATIVE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_ITEMIDLIST_RELATIVE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMIDLIST_RELATIVE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1800652af  test    ebx, ebx
0x1800652b1  jns     short loc_1800652E4
0x1800652b3  mov     rcx, [rbp+37h]; this
0x1800652b7  mov     r9d, ebx; char *
0x1800652ba  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\windows.storage.sear"...
0x1800652c1  mov     edx, 2405h; void *
0x1800652c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800652cb  nop
0x1800652cc  mov     rcx, [rbp+2Fh+pv]; pv
0x1800652d0  mov     [rbp+2Fh+pv], r14
0x1800652d4  test    rcx, rcx
0x1800652d7  jz      short loc_18006525C
0x1800652d9  call    cs:__imp_CoTaskMemFree
0x1800652df  jmp     loc_18006525C
0x1800652e4  mov     rdx, [rbp+2Fh+pv]; pidl2
0x1800652e8  mov     rcx, [rdi+20h]; pidl1
0x1800652ec  call    cs:__imp_ILCombine
0x1800652f2  mov     [rsi], rax
0x1800652f5  mov     rcx, [rbp+2Fh+pv]; pv
0x1800652f9  mov     [rbp+2Fh+pv], r14
0x1800652fd  test    rcx, rcx
0x180065300  jz      short loc_180065309
0x180065302  call    cs:__imp_CoTaskMemFree
0x180065308  nop
0x180065309  lea     rcx, [rbp+2Fh+ppszOut]
0x18006530d  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180065312  nop
0x180065313  lea     rcx, [rbp+2Fh+pvar]; pvar
0x180065317  call    cs:__imp_PropVariantClear
0x18006531d  nop
0x18006531e  lea     rcx, [rbp+2Fh+ppbc]
0x180065322  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180065327  mov     ebx, r14d
0x18006532a  lea     rcx, [rbp+2Fh+ppv]
0x18006532e  call    ??1?$com_ptr_t@UIInitializeSortColumnArray@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IInitializeSortColumnArray,wil::err_exception_policy>::~com_ptr_t<IInitializeSortColumnArray,wil::err_exception_policy>(void)
0x180065333  mov     eax, ebx
0x180065335  add     rsp, 90h
0x18006533c  pop     r14
0x18006533e  pop     rdi
0x18006533f  pop     rsi
0x180065340  pop     rbx
0x180065341  pop     rbp
0x180065342  retn
```
