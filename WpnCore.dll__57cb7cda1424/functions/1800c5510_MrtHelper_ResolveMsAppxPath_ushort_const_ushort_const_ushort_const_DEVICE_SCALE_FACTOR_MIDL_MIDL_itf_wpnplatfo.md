# MrtHelper::ResolveMsAppxPath(ushort const *,ushort const *,ushort const *,DEVICE_SCALE_FACTOR,__MIDL___MIDL_itf_wpnplatform_0000_0028_0001,ushort * *)

- ea: `0x1800c5510`
- end: `0x1800c57b4`
- name: `?ResolveMsAppxPath@MrtHelper@@UEAAJPEBG00W4DEVICE_SCALE_FACTOR@@W4__MIDL___MIDL_itf_wpnplatform_0000_0028_0001@@PEAPEAG@Z`
- size: `676`
- prototype: `int __high(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, enum DEVICE_SCALE_FACTOR, enum __MIDL___MIDL_itf_wpnplatform_0000_0028_0001, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180004e38`
- `0x18000e5f4`
- `0x180011618`
- `0x18001ed80`
- `0x18001ef50`
- `0x18001f3ac`
- `0x180087cbc`
- `0x1800a8298`
- `0x1800c5510`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c5739`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c5739`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c5714`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c5714`
- `ext-ms-win-core-iuri-l1-1-0!CreateUri` at `0x1800c55f5`
- `ext-ms-win-core-iuri-l1-1-0!CreateUri` at `0x1800c55f5`
- `urlmon!__imp_AppXIUriToFileIUri` at `0x1800c569c`
- `urlmon!__imp_AppXIUriToFileIUri` at `0x1800c569c`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall MrtHelper::ResolveMsAppxPath(
        __int64 a1,
        const WCHAR *a2,
        CallerIdentity *a3,
        __int64 a4,
        __int64 a5,
        struct PACKAGE_INFO **a6,
        unsigned __int16 **a7)
{
  __int64 v9; // rdx
  __int64 result; // rax
  unsigned __int16 **v11; // rdi
  int PackageInfoFromPackageFullName; // ebx
  int v13; // ebx
  __int64 v14; // rax
  MrtHelper *v15; // rcx
  void *v16; // rcx
  int v17; // eax
  const char *v18; // r9
  int v19; // [rsp+20h] [rbp-88h]
  int *v20; // [rsp+20h] [rbp-88h]
  __int64 v21; // [rsp+40h] [rbp-68h] BYREF
  int v22[2]; // [rsp+48h] [rbp-60h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-58h] BYREF
  IUri *ppURI; // [rsp+58h] [rbp-50h] BYREF
  __int64 v25; // [rsp+60h] [rbp-48h] BYREF
  void *p_pv; // [rsp+68h] [rbp-40h] BYREF
  unsigned int v27[2]; // [rsp+70h] [rbp-38h] BYREF
  char v28; // [rsp+78h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]
  BSTR bstrString; // [rsp+B8h] [rbp+10h] BYREF

  if ( !a2 )
  {
    v9 = 168;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\mrthelper.cpp",
      (const char *)0x80070057LL,
      v19);
    return 2147942487LL;
  }
  v11 = a7;
  if ( !a7 )
  {
    v9 = 169;
    goto LABEL_3;
  }
  if ( !a3 )
  {
    v9 = 170;
    goto LABEL_3;
  }
  *a7 = 0;
  ppURI = 0;
  v25 = 0;
  v21 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
  LODWORD(v20) = (_DWORD)a6;
  try
  {
    MrtHelper::InitializeMRTResource();
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppURI);
    if ( CreateUri(a2, 0x4000u, 0, &ppURI) < 0 )
      goto LABEL_20;
    pv = 0;
    p_pv = &pv;
    *(_QWORD *)v27 = 0;
    v28 = 1;
    PackageInfoFromPackageFullName = CallerIdentity::GetPackageInfoFromPackageFullName(a3, 0x220070u, &bstrString, v27);
    wil::details::out_param_t<wistd::unique_ptr<PACKAGE_INFO,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<PACKAGE_INFO,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
    if ( PackageInfoFromPackageFullName < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xC0,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\mrthelper.cpp",
        (const char *)(unsigned int)PackageInfoFromPackageFullName,
        (int)v20);
    *(_QWORD *)v22 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v22);
    v20 = v22;
    v13 = AppXIUriToFileIUri(ppURI, v21, pv, 1);
    if ( v13 >= 0 )
    {
      bstrString = 0;
      v14 = **(_QWORD **)v22;
      p_pv = &bstrString;
      *(_QWORD *)v27 = 0;
      v28 = 1;
      v13 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(v14 + 56))(*(_QWORD *)v22, v27);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_pv);
      if ( v13 >= 0 )
        v13 = MrtHelper::ConvertFileUriToFilePath(v15, bstrString, v11);
      if ( bstrString )
        SysFreeString(bstrString);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v22);
    v16 = pv;
    pv = 0;
    if ( v16 )
      CoTaskMemFree(v16);
    if ( v13 < 0 )
    {
LABEL_20:
      v17 = (*(__int64 (__fastcall **)(__int64, const WCHAR *, unsigned __int16 **))(*(_QWORD *)v21 + 56LL))(
              v21,
              a2,
              v11);
      if ( v17 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xD1,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\mrthelper.cpp",
          (const char *)(unsigned int)v17,
          (int)v20);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppURI);
    result = 0;
  }
  catch ( ... )
  {
    LODWORD(bstrString) = wil::details::in1diag3::Return_CaughtException(
                            retaddr,
                            (void *)0xD5,
                            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\mrthelper.cpp",
                            v18);
    return (unsigned int)bstrString;
  }
  return result;
}

```

## disassembly

```asm
0x1800c5510  push    rbx
0x1800c5512  push    rsi
0x1800c5513  push    rdi
0x1800c5514  push    r14
0x1800c5516  sub     rsp, 88h
0x1800c551d  mov     r14, r9
0x1800c5520  mov     rbx, r8
0x1800c5523  mov     rsi, rdx
0x1800c5526  test    rdx, rdx
0x1800c5529  jnz     short loc_1800C5553
0x1800c552b  mov     edx, 0A8h; void *
0x1800c5530  mov     ebx, 80070057h
0x1800c5535  mov     rcx, [rsp+0A8h]; this
0x1800c553d  mov     r9d, ebx; char *
0x1800c5540  lea     r8, aOnecoreuapBase_131; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800c5547  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c554c  mov     eax, ebx
0x1800c554e  jmp     loc_1800C57A7
0x1800c5553  mov     rdi, [rsp+0A8h+arg_30]
0x1800c555b  test    rdi, rdi
0x1800c555e  jnz     short loc_1800C5567
0x1800c5560  mov     edx, 0A9h
0x1800c5565  jmp     short loc_1800C5530
0x1800c5567  test    rbx, rbx
0x1800c556a  jnz     short loc_1800C5573
0x1800c556c  mov     edx, 0AAh
0x1800c5571  jmp     short loc_1800C5530
0x1800c5573  mov     qword ptr [rdi], 0
0x1800c557a  mov     [rsp+0A8h+ppURI], 0
0x1800c5583  mov     [rsp+0A8h+var_48], 0
0x1800c558c  mov     [rsp+0A8h+var_68], 0
0x1800c5595  lea     rcx, [rsp+0A8h+var_68]
0x1800c559a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c559f  lea     rcx, [rsp+0A8h+var_48]
0x1800c55a4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c55a9  lea     rax, [rsp+0A8h+var_68]
0x1800c55ae  mov     [rsp+0A8h+var_78], rax
0x1800c55b3  lea     rax, [rsp+0A8h+var_48]
0x1800c55b8  mov     [rsp+0A8h+var_80], rax
0x1800c55bd  mov     eax, dword ptr [rsp+0A8h+arg_28]
0x1800c55c4  mov     dword ptr [rsp+0A8h+var_88], eax; int
0x1800c55c8  mov     r9d, [rsp+0A8h+arg_20]
0x1800c55d0  mov     r8, rbx
0x1800c55d3  mov     rdx, r14
0x1800c55d6  call    ?InitializeMRTResource@MrtHelper@@AEAAXPEBG0W4DEVICE_SCALE_FACTOR@@W4__MIDL___MIDL_itf_wpnplatform_0000_0028_0001@@PEAPEAUIMrtResourceManager@@PEAPEAUIResourceMap@@@Z; MrtHelper::InitializeMRTResource(ushort const *,ushort const *,DEVICE_SCALE_FACTOR,__MIDL___MIDL_itf_wpnplatform_0000_0028_0001,IMrtResourceManager * *,IResourceMap * *)
0x1800c55db  lea     rcx, [rsp+0A8h+ppURI]
0x1800c55e0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c55e5  lea     r9, [rsp+0A8h+ppURI]; ppURI
0x1800c55ea  xor     r8d, r8d; dwReserved
0x1800c55ed  mov     edx, 4000h; dwFlags
0x1800c55f2  mov     rcx, rsi; pwzURI
0x1800c55f5  call    cs:__imp_CreateUri
0x1800c55fb  test    eax, eax
0x1800c55fd  js      loc_1800C5743
0x1800c5603  mov     [rsp+0A8h+pv], 0
0x1800c560c  lea     rax, [rsp+0A8h+pv]
0x1800c5611  mov     [rsp+0A8h+var_40], rax
0x1800c5616  mov     qword ptr [rsp+0A8h+var_38], 0
0x1800c561f  mov     [rsp+0A8h+var_30], 1
0x1800c5624  lea     r9, [rsp+0A8h+var_38]; unsigned int *
0x1800c5629  lea     r8, [rsp+0A8h+bstrString]; unsigned int
0x1800c5631  mov     edx, 220070h; flags
0x1800c5636  mov     rcx, rbx; this
0x1800c5639  call    ?GetPackageInfoFromPackageFullName@CallerIdentity@@YAJPEBGIPEAIPEAPEAUPACKAGE_INFO@@@Z; CallerIdentity::GetPackageInfoFromPackageFullName(ushort const *,uint,uint *,PACKAGE_INFO * *)
0x1800c563e  mov     ebx, eax
0x1800c5640  lea     rcx, [rsp+0A8h+var_40]
0x1800c5645  call    ??1?$out_param_t@V?$unique_ptr@UPACKAGE_INFO@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<PACKAGE_INFO,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<PACKAGE_INFO,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1800c564a  mov     rcx, [rsp+0A8h]; this
0x1800c5652  test    ebx, ebx
0x1800c5654  jns     short loc_1800C566A
0x1800c5656  mov     r9d, ebx; char *
0x1800c5659  lea     r8, aOnecoreuapBase_131; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800c5660  mov     edx, 0C0h; void *
0x1800c5665  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800c566a  mov     qword ptr [rsp+0A8h+var_60], 0
0x1800c5673  lea     rcx, [rsp+0A8h+var_60]
0x1800c5678  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c567d  lea     rax, [rsp+0A8h+var_60]
0x1800c5682  mov     [rsp+0A8h+var_88], rax; int
0x1800c5687  mov     r9d, 1
0x1800c568d  mov     r8, [rsp+0A8h+pv]
0x1800c5692  mov     rdx, [rsp+0A8h+var_68]
0x1800c5697  mov     rcx, [rsp+0A8h+ppURI]
0x1800c569c  call    cs:__imp_AppXIUriToFileIUri
0x1800c56a2  mov     ebx, eax
0x1800c56a4  test    eax, eax
0x1800c56a6  js      short loc_1800C571B
0x1800c56a8  mov     [rsp+0A8h+bstrString], 0
0x1800c56b4  mov     rcx, qword ptr [rsp+0A8h+var_60]
0x1800c56b9  mov     rax, [rcx]
0x1800c56bc  lea     rdx, [rsp+0A8h+bstrString]
0x1800c56c4  mov     [rsp+0A8h+var_40], rdx
0x1800c56c9  mov     qword ptr [rsp+0A8h+var_38], 0
0x1800c56d2  mov     [rsp+0A8h+var_30], 1
0x1800c56d7  lea     rdx, [rsp+0A8h+var_38]
0x1800c56dc  mov     rax, [rax+38h]
0x1800c56e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c56e5  mov     ebx, eax
0x1800c56e7  lea     rcx, [rsp+0A8h+var_40]
0x1800c56ec  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x1800c56f1  test    ebx, ebx
0x1800c56f3  js      short loc_1800C5707
0x1800c56f5  mov     r8, rdi; unsigned __int16 **
0x1800c56f8  mov     rdx, [rsp+0A8h+bstrString]; unsigned __int16 *
0x1800c5700  call    ?ConvertFileUriToFilePath@MrtHelper@@AEAAJPEBGPEAPEAG@Z; MrtHelper::ConvertFileUriToFilePath(ushort const *,ushort * *)
0x1800c5705  mov     ebx, eax
0x1800c5707  mov     rcx, [rsp+0A8h+bstrString]; bstrString
0x1800c570f  test    rcx, rcx
0x1800c5712  jz      short loc_1800C571B
0x1800c5714  call    cs:__imp_SysFreeString
0x1800c571a  nop
0x1800c571b  lea     rcx, [rsp+0A8h+var_60]
0x1800c5720  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c5725  nop
0x1800c5726  mov     rcx, [rsp+0A8h+pv]; pv
0x1800c572b  mov     [rsp+0A8h+pv], 0
0x1800c5734  test    rcx, rcx
0x1800c5737  jz      short loc_1800C573F
0x1800c5739  call    cs:__imp_CoTaskMemFree
0x1800c573f  test    ebx, ebx
0x1800c5741  jns     short loc_1800C577B
0x1800c5743  mov     rcx, [rsp+0A8h+var_68]
0x1800c5748  mov     rax, [rcx]
0x1800c574b  mov     r8, rdi
0x1800c574e  mov     rdx, rsi
0x1800c5751  mov     rax, [rax+38h]
0x1800c5755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c575a  mov     rcx, [rsp+0A8h]; this
0x1800c5762  test    eax, eax
0x1800c5764  jns     short loc_1800C577B
0x1800c5766  mov     r9d, eax; char *
0x1800c5769  lea     r8, aOnecoreuapBase_131; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800c5770  mov     edx, 0D1h; void *
0x1800c5775  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800c577b  lea     rcx, [rsp+0A8h+var_68]
0x1800c5780  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c5785  nop
0x1800c5786  lea     rcx, [rsp+0A8h+var_48]
0x1800c578b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c5790  nop
0x1800c5791  lea     rcx, [rsp+0A8h+ppURI]
0x1800c5796  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c579b  nop
0x1800c579c  xor     eax, eax
0x1800c579e  jmp     short loc_1800C57A7
0x1800c57a0  mov     eax, dword ptr [rsp+0A8h+bstrString]
0x1800c57a7  add     rsp, 88h
0x1800c57ae  pop     r14
0x1800c57b0  pop     rdi
0x1800c57b1  pop     rsi
0x1800c57b2  pop     rbx
0x1800c57b3  retn
```
