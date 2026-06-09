# CopyFaviconToEdge(HSTRING__ *,HSTRING__ * *)

- ea: `0x1801ec55c`
- end: `0x1801ec7a7`
- name: `?CopyFaviconToEdge@@YAJPEAUHSTRING__@@PEAPEAU1@@Z`
- size: `587`
- prototype: `int(HSTRING, HSTRING *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18021b260`

## callees

- `0x18001dac0`
- `0x18002dde0`
- `0x180087bd8`
- `0x1801d8074`
- `0x1801ec4cc`
- `0x1801ec55c`
- `0x1801ec7b0`
- `0x1801ec808`
- `0x1801f375c`
- `0x180201e50`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x1801ec677`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x1801ec70b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x1801ec677`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x1801ec70b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ec5f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ec648`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ec742`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ec756`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ec5f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ec648`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ec742`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ec756`

## string_xrefs

- `0x1801ec621`: `shellcommon\shell\inc\CopyEdgeAssetsHelper.h`
- `0x1801ec68c`: `shellcommon\shell\inc\CopyEdgeAssetsHelper.h`
- `0x1801ec720`: `shellcommon\shell\inc\CopyEdgeAssetsHelper.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=12 #try_helpers=1
__int64 __fastcall CopyFaviconToEdge(HSTRING a1, HSTRING *a2)
{
  _QWORD *v3; // rax
  __int64 v4; // r8
  HSTRING v5; // rbx
  __int64 v6; // rax
  __int64 v7; // rsi
  __int64 (__fastcall *v8)(__int64, HSTRING *); // rdi
  int v9; // eax
  HSTRING_HEADER *v10; // rax
  HRESULT v11; // eax
  int v12; // r8d
  HSTRING v13; // rbx
  HSTRING_HEADER *v14; // rax
  HRESULT v15; // eax
  int v17; // [rsp+20h] [rbp-98h]
  int v18; // [rsp+20h] [rbp-98h]
  HSTRING v19; // [rsp+30h] [rbp-88h] BYREF
  HSTRING newString; // [rsp+38h] [rbp-80h] BYREF
  HSTRING string; // [rsp+40h] [rbp-78h] BYREF
  int v22[2]; // [rsp+48h] [rbp-70h] BYREF
  HSTRING v23; // [rsp+50h] [rbp-68h] BYREF
  __int64 v24; // [rsp+58h] [rbp-60h] BYREF
  __int64 v25; // [rsp+60h] [rbp-58h] BYREF
  __int64 v26; // [rsp+68h] [rbp-50h] BYREF
  HSTRING_HEADER v27; // [rsp+70h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  v23 = a1;
  GetEdgeFaviconCache(&v25);
  v3 = (_QWORD *)wil::GetActivationFactory<Windows::Storage::IStorageFileStatics>(v22);
  ___call_and_wait_for_completion_UIStorageFileStatics_Storage_Windows__PEAUHSTRING____PEAPEAU__IAsyncOperation_PEAVStorageFile_Storage_Windows___Foundation_3___ZAEAPEAU4__wil__YA_A_PPEAUIStorageFileStatics_Storage_Windows__P8123_EAAJPEAUHSTRING____PEAPEAU__IAsyncOperation_PEAVStorageFile_Storage_Windows___Foundation_3__ZAEAPEAU4__Z(
    &v19,
    *v3,
    v4,
    &v23);
  v5 = v19;
  v19 = 0;
  v23 = v5;
  wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(v22);
  string = 0;
  v6 = wil::com_ptr_t<Windows::Storage::IStorageFile,wil::err_exception_policy>::query<Windows::Storage::IStorageItem>(
         &v23,
         v22);
  v7 = *(_QWORD *)v6;
  v8 = *(__int64 (__fastcall **)(__int64, HSTRING *))(**(_QWORD **)v6 + 88LL);
  WindowsDeleteString(string);
  string = 0;
  v9 = v8(v7, &string);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x44,
      (unsigned int)"shellcommon\\shell\\inc\\CopyEdgeAssetsHelper.h",
      (const char *)(unsigned int)v9,
      v17);
  wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(v22);
  newString = 0;
  WindowsDeleteString(0);
  newString = 0;
  v10 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v27, (const WCHAR **)off_1803DD5F0);
  v11 = WindowsConcatString(string, (HSTRING)v10[1].Reserved.Reserved1, &newString);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x48,
      (unsigned int)"shellcommon\\shell\\inc\\CopyEdgeAssetsHelper.h",
      (const char *)(unsigned int)v11,
      v17);
  LODWORD(v19) = 1;
  *(_QWORD *)v22 = newString;
  v26 = v25;
  ___call_and_wait_for_completion_UIStorageFile_Storage_Windows__PEAUIStorageFolder_23_PEAUHSTRING____W4NameCollisionOption_23_PEAPEAU__IAsyncOperation_PEAVStorageFile_Storage_Windows___Foundation_3___ZPEAU423_PEAU5_W4623__wil__YA_A_PPEAUIStorageFile_Storage_Windows__P8123_EAAJPEAUIStorageFolder_23_PEAUHSTRING____W4NameCollisionOption_23_PEAPEAU__IAsyncOperation_PEAVStorageFile_Storage_Windows___Foundation_3__Z__QEAPEAU423___QEAPEAU5___QEAW4623__Z(
    (unsigned int)&v24,
    (_DWORD)v5,
    v12,
    (unsigned int)&v26,
    (__int64)v22,
    (__int64)&v19);
  v13 = newString;
  v14 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v27, (const WCHAR **)&off_1803DD5F8);
  v15 = WindowsConcatString((HSTRING)v14[1].Reserved.Reserved1, v13, a2);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x53,
      (unsigned int)"shellcommon\\shell\\inc\\CopyEdgeAssetsHelper.h",
      (const char *)(unsigned int)v15,
      v18);
  wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v24);
  WindowsDeleteString(newString);
  newString = 0;
  WindowsDeleteString(string);
  string = 0;
  wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v23);
  wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v25);
  return 0;
}

```

## disassembly

```asm
0x1801ec55c  mov     [rsp+arg_10], rbx
0x1801ec561  push    rsi
0x1801ec562  push    rdi
0x1801ec563  push    r14
0x1801ec565  sub     rsp, 0A0h
0x1801ec56c  mov     rax, cs:__security_cookie
0x1801ec573  xor     rax, rsp
0x1801ec576  mov     [rsp+0B8h+var_28], rax
0x1801ec57e  mov     r14, rdx
0x1801ec581  mov     [rsp+0B8h+var_68], rcx
0x1801ec586  lea     rcx, [rsp+0B8h+var_58]
0x1801ec58b  call    ?GetEdgeFaviconCache@@YA?AV?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@XZ; GetEdgeFaviconCache(void)
0x1801ec590  nop
0x1801ec591  lea     rcx, [rsp+0B8h+var_70]
0x1801ec596  call    ??$GetActivationFactory@UIStorageFileStatics@Storage@Windows@@@wil@@YA?AV?$com_ptr_t@UIStorageFileStatics@Storage@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::GetActivationFactory<Windows::Storage::IStorageFileStatics>(ushort const *)
0x1801ec59b  nop
0x1801ec59c  lea     r9, [rsp+0B8h+var_68]
0x1801ec5a1  mov     rdx, [rax]
0x1801ec5a4  lea     rcx, [rsp+0B8h+var_88]
0x1801ec5a9  call    ??$call_and_wait_for_completion@UIStorageFileStatics@Storage@Windows@@PEAUHSTRING__@@PEAPEAU?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@Foundation@3@$$ZAEAPEAU4@@wil@@YA?A_PPEAUIStorageFileStatics@Storage@Windows@@P8123@EAAJPEAUHSTRING__@@PEAPEAU?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@Foundation@3@@ZAEAPEAU4@@Z
0x1801ec5ae  mov     rbx, [rsp+0B8h+var_88]
0x1801ec5b3  mov     [rsp+0B8h+var_88], 0
0x1801ec5bc  mov     [rsp+0B8h+var_68], rbx
0x1801ec5c1  lea     rcx, [rsp+0B8h+var_70]; void *
0x1801ec5c6  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x1801ec5cb  mov     [rsp+0B8h+string], 0
0x1801ec5d4  lea     rdx, [rsp+0B8h+var_70]
0x1801ec5d9  lea     rcx, [rsp+0B8h+var_68]
0x1801ec5de  call    ??$query@UIStorageItem@Storage@Windows@@@?$com_ptr_t@UIStorageFile@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIStorageItem@Storage@Windows@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<Windows::Storage::IStorageFile,wil::err_exception_policy>::query<Windows::Storage::IStorageItem>(void)
0x1801ec5e3  nop
0x1801ec5e4  mov     rsi, [rax]
0x1801ec5e7  mov     rax, [rsi]
0x1801ec5ea  mov     rdi, [rax+58h]
0x1801ec5ee  mov     rcx, [rsp+0B8h+string]; string
0x1801ec5f3  call    cs:__imp_WindowsDeleteString
0x1801ec5f9  mov     [rsp+0B8h+string], 0
0x1801ec602  lea     rdx, [rsp+0B8h+string]
0x1801ec607  mov     rcx, rsi
0x1801ec60a  mov     rax, rdi
0x1801ec60d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ec612  mov     rcx, [rsp+0B8h]; this
0x1801ec61a  test    eax, eax
0x1801ec61c  jns     short loc_1801EC633
0x1801ec61e  mov     r9d, eax; char *
0x1801ec621  lea     r8, aShellcommonShe_74; "shellcommon\\shell\\inc\\CopyEdgeAssets"...
0x1801ec628  mov     edx, 44h ; 'D'; void *
0x1801ec62d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801ec633  lea     rcx, [rsp+0B8h+var_70]; void *
0x1801ec638  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x1801ec63d  mov     [rsp+0B8h+newString], 0
0x1801ec646  xor     ecx, ecx; string
0x1801ec648  call    cs:__imp_WindowsDeleteString
0x1801ec64e  mov     [rsp+0B8h+newString], 0
0x1801ec657  lea     rdx, off_1803DD5F0; ".png"
0x1801ec65e  lea     rcx, [rsp+0B8h+var_48]
0x1801ec663  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1801ec668  nop
0x1801ec669  lea     r8, [rsp+0B8h+newString]; newString
0x1801ec66e  mov     rdx, [rax+18h]; string2
0x1801ec672  mov     rcx, [rsp+0B8h+string]; string1
0x1801ec677  call    cs:__imp_WindowsConcatString
0x1801ec67d  mov     rcx, [rsp+0B8h]; this
0x1801ec685  test    eax, eax
0x1801ec687  jns     short loc_1801EC69E
0x1801ec689  mov     r9d, eax; char *
0x1801ec68c  lea     r8, aShellcommonShe_74; "shellcommon\\shell\\inc\\CopyEdgeAssets"...
0x1801ec693  mov     edx, 48h ; 'H'; void *
0x1801ec698  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801ec69e  mov     dword ptr [rsp+0B8h+var_88], 1
0x1801ec6a6  mov     rax, [rsp+0B8h+newString]
0x1801ec6ab  mov     qword ptr [rsp+0B8h+var_70], rax
0x1801ec6b0  mov     rax, [rsp+0B8h+var_58]
0x1801ec6b5  mov     [rsp+0B8h+var_50], rax
0x1801ec6ba  lea     rax, [rsp+0B8h+var_88]
0x1801ec6bf  mov     [rsp+0B8h+var_90], rax
0x1801ec6c4  lea     rax, [rsp+0B8h+var_70]
0x1801ec6c9  mov     qword ptr [rsp+0B8h+var_98], rax; int
0x1801ec6ce  lea     r9, [rsp+0B8h+var_50]
0x1801ec6d3  mov     rdx, rbx
0x1801ec6d6  lea     rcx, [rsp+0B8h+var_60]
0x1801ec6db  call    ??$call_and_wait_for_completion@UIStorageFile@Storage@Windows@@PEAUIStorageFolder@23@PEAUHSTRING__@@W4NameCollisionOption@23@PEAPEAU?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@Foundation@3@$$ZPEAU423@PEAU5@W4623@@wil@@YA?A_PPEAUIStorageFile@Storage@Windows@@P8123@EAAJPEAUIStorageFolder@23@PEAUHSTRING__@@W4NameCollisionOption@23@PEAPEAU?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@Foundation@3@@Z$$QEAPEAU423@$$QEAPEAU5@$$QEAW4623@@Z
0x1801ec6e0  mov     rax, [rsp+0B8h+var_60]
0x1801ec6e5  mov     [rsp+0B8h+var_60], rax
0x1801ec6ea  mov     rbx, [rsp+0B8h+newString]
0x1801ec6ef  lea     rdx, off_1803DD5F8; "ms-appdata:///local/Favicons/Provided/"
0x1801ec6f6  lea     rcx, [rsp+0B8h+var_48]
0x1801ec6fb  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1801ec700  nop
0x1801ec701  mov     r8, r14; newString
0x1801ec704  mov     rdx, rbx; string2
0x1801ec707  mov     rcx, [rax+18h]; string1
0x1801ec70b  call    cs:__imp_WindowsConcatString
0x1801ec711  mov     rcx, [rsp+0B8h]; this
0x1801ec719  test    eax, eax
0x1801ec71b  jns     short loc_1801EC732
0x1801ec71d  mov     r9d, eax; char *
0x1801ec720  lea     r8, aShellcommonShe_74; "shellcommon\\shell\\inc\\CopyEdgeAssets"...
0x1801ec727  mov     edx, 53h ; 'S'; void *
0x1801ec72c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801ec732  lea     rcx, [rsp+0B8h+var_60]; void *
0x1801ec737  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x1801ec73c  nop
0x1801ec73d  mov     rcx, [rsp+0B8h+newString]; string
0x1801ec742  call    cs:__imp_WindowsDeleteString
0x1801ec748  mov     [rsp+0B8h+newString], 0
0x1801ec751  mov     rcx, [rsp+0B8h+string]; string
0x1801ec756  call    cs:__imp_WindowsDeleteString
0x1801ec75c  mov     [rsp+0B8h+string], 0
0x1801ec765  lea     rcx, [rsp+0B8h+var_68]; void *
0x1801ec76a  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x1801ec76f  nop
0x1801ec770  lea     rcx, [rsp+0B8h+var_58]; void *
0x1801ec775  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x1801ec77a  xor     eax, eax
0x1801ec77c  jmp     short loc_1801EC782
0x1801ec77e  mov     eax, dword ptr [rsp+0B8h+var_88]
0x1801ec782  mov     rcx, [rsp+0B8h+var_28]
0x1801ec78a  xor     rcx, rsp; StackCookie
0x1801ec78d  call    __security_check_cookie
0x1801ec792  mov     rbx, [rsp+0B8h+arg_10]
0x1801ec79a  add     rsp, 0A0h
0x1801ec7a1  pop     r14
0x1801ec7a3  pop     rdi
0x1801ec7a4  pop     rsi
0x1801ec7a5  retn
```
