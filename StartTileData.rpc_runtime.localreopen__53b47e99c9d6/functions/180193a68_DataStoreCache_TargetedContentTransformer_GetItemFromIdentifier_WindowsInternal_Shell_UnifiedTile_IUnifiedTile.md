# DataStoreCache::TargetedContentTransformer::GetItemFromIdentifier(WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier *)

- ea: `0x180193a68`
- end: `0x180193c7f`
- name: `?GetItemFromIdentifier@TargetedContentTransformer@DataStoreCache@@AEAA?AV?$com_ptr_t@UITargetedContentItem@TargetedContent@Services@Windows@@Uerr_exception_policy@wil@@@wil@@PEAUIUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@@Z`
- size: `535`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801f3348`

## callees

- `0x18001ac50`
- `0x18001dac0`
- `0x18002dde0`
- `0x180193a68`
- `0x180193c88`
- `0x1801fecd4`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180193a94`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180193b03`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180193b86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180193c27`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180193c48`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180193c62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180193a94`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180193b03`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180193b86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180193c27`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180193c48`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180193c62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180193b12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180193b12`

## string_xrefs

- `0x180193ab8`: `shellcommon\shell\datastorecache\transformers\targetedcontenttransformer\lib\targetedcontenttransformer.cpp`
- `0x180193b51`: `shellcommon\shell\datastorecache\transformers\targetedcontenttransformer\lib\targetedcontenttransformer.cpp`
- `0x180193bba`: `shellcommon\shell\datastorecache\transformers\targetedcontenttransformer\lib\targetedcontenttransformer.cpp`
- `0x180193bf3`: `shellcommon\shell\datastorecache\transformers\targetedcontenttransformer\lib\targetedcontenttransformer.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
_QWORD *__fastcall DataStoreCache::TargetedContentTransformer::GetItemFromIdentifier(
        __int64 a1,
        _QWORD *a2,
        __int64 a3)
{
  __int64 (__fastcall *v6)(__int64, HSTRING *); // rbx
  int v7; // eax
  HSTRING v8; // rbx
  PCWSTR StringRawBuffer; // rax
  __int64 v10; // rcx
  int v11; // eax
  HSTRING v12; // rdi
  __int64 (__fastcall *v13)(__int64, HSTRING, __int64 **); // rax
  int v14; // eax
  __int64 v15; // rax
  int v16; // eax
  __int64 v17; // rax
  int v19; // [rsp+20h] [rbp-50h]
  HSTRING string; // [rsp+38h] [rbp-38h] BYREF
  __int64 *v21; // [rsp+40h] [rbp-30h] BYREF
  __int64 v22; // [rsp+48h] [rbp-28h] BYREF
  HSTRING v23; // [rsp+50h] [rbp-20h]
  HSTRING v24; // [rsp+58h] [rbp-18h]
  __int64 v25; // [rsp+60h] [rbp-10h] BYREF
  std::_Ref_count_base *v26; // [rsp+68h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  int v28; // [rsp+B0h] [rbp+40h] BYREF
  __int64 v29; // [rsp+B8h] [rbp+48h] BYREF

  string = 0;
  v6 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a3 + 56LL);
  WindowsDeleteString(0);
  string = 0;
  v7 = v6(a3, &string);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x8FC,
      (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\targetedcontenttransformer\\lib\\targetedcontenttransformer.cpp",
      (const char *)(unsigned int)v7,
      v19);
  (*(void (__fastcall **)(__int64, __int64 *, __int128 *, HSTRING))(*(_QWORD *)(a1 + 8) + 24LL))(
    a1 + 8,
    &v25,
    &TileData,
    string);
  v23 = 0;
  v8 = (HSTRING)DataStoreCache::DataStorePropertyBag::GetProperty<HSTRING__ *>(
                  v25,
                  &DataStoreCache::TargetedContentProperties::ContentId);
  WindowsDeleteString(0);
  v23 = v8;
  StringRawBuffer = WindowsGetStringRawBuffer(v8, 0);
  DataStoreCache::TargetedContentTransformer::GetSubscriptionContainer(v10, &v22, StringRawBuffer);
  if ( !v22 )
    goto LABEL_12;
  v28 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v22 + 64LL))(v22, &v28);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x906,
      (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\targetedcontenttransformer\\lib\\targetedcontenttransformer.cpp",
      (const char *)(unsigned int)v11,
      v19);
  if ( v28 == 2 )
  {
    v24 = 0;
    v12 = (HSTRING)DataStoreCache::DataStorePropertyBag::GetProperty<HSTRING__ *>(
                     v25,
                     &DataStoreCache::TargetedContentProperties::ItemPath);
    WindowsDeleteString(0);
    v24 = v12;
    v21 = 0;
    v13 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 **))(*(_QWORD *)v22 + 80LL);
    v21 = 0;
    v14 = v13(v22, v12, &v21);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x90F,
        (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\targetedcontenttransformer\\lib\\targetedcontenttransformer.cpp",
        (const char *)(unsigned int)v14,
        v19);
    v29 = 0;
    v15 = *v21;
    v29 = 0;
    v16 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v15 + 64))(v21, &v29);
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x911,
        (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\targetedcontenttransformer\\lib\\targetedcontenttransformer.cpp",
        (const char *)(unsigned int)v16,
        v19);
    v17 = v29;
    v29 = 0;
    *a2 = v17;
    wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v29);
    wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v21);
    WindowsDeleteString(v12);
    wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v22);
  }
  else
  {
LABEL_12:
    wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v22);
    *a2 = 0;
  }
  WindowsDeleteString(v8);
  if ( v26 )
    std::_Ref_count_base::_Decref(v26);
  WindowsDeleteString(string);
  return a2;
}

```

## disassembly

```asm
0x180193a68  mov     [rsp-28h+arg_0], rbx
0x180193a6d  push    rbp
0x180193a6e  push    rsi
0x180193a6f  push    rdi
0x180193a70  push    r14
0x180193a72  push    r15
0x180193a74  mov     rbp, rsp
0x180193a77  sub     rsp, 70h
0x180193a7b  mov     rdi, r8
0x180193a7e  mov     rsi, rdx
0x180193a81  mov     r14, rcx
0x180193a84  xor     r15d, r15d
0x180193a87  mov     [rbp+string], r15
0x180193a8b  mov     rax, [r8]
0x180193a8e  mov     rbx, [rax+38h]
0x180193a92  xor     ecx, ecx; string
0x180193a94  call    cs:__imp_WindowsDeleteString
0x180193a9a  mov     [rbp+string], r15
0x180193a9e  lea     rdx, [rbp+string]
0x180193aa2  mov     rcx, rdi
0x180193aa5  mov     rax, rbx
0x180193aa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180193aad  mov     rcx, [rbp+28h]; this
0x180193ab1  test    eax, eax
0x180193ab3  jns     short loc_180193ACA
0x180193ab5  mov     r9d, eax; char *
0x180193ab8  lea     r8, aShellcommonShe_103; "shellcommon\\shell\\datastorecache\\tra"...
0x180193abf  mov     edx, 8FCh; void *
0x180193ac4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180193aca  lea     rcx, [r14+8]
0x180193ace  mov     rax, [rcx]
0x180193ad1  mov     r9, [rbp+string]
0x180193ad5  lea     r8, TileData
0x180193adc  lea     rdx, [rbp+var_10]
0x180193ae0  mov     rax, [rax+18h]
0x180193ae4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180193ae9  nop
0x180193aea  mov     [rbp+var_20], r15
0x180193aee  lea     rdx, ?ContentId@TargetedContentProperties@DataStoreCache@@3U?$DataStoreProperty@PEAUHSTRING__@@@2@B; DataStoreCache::DataStoreProperty<HSTRING__ *> const DataStoreCache::TargetedContentProperties::ContentId
0x180193af5  mov     rcx, [rbp+var_10]
0x180193af9  call    ??$GetProperty@PEAUHSTRING__@@@DataStorePropertyBag@DataStoreCache@@QEBAQEAUHSTRING__@@AEBU?$DataStoreProperty@PEAUHSTRING__@@@1@@Z; DataStoreCache::DataStorePropertyBag::GetProperty<HSTRING__ *>(DataStoreCache::DataStoreProperty<HSTRING__ *> const &)
0x180193afe  mov     rbx, rax
0x180193b01  xor     ecx, ecx; string
0x180193b03  call    cs:__imp_WindowsDeleteString
0x180193b09  mov     [rbp+var_20], rbx
0x180193b0d  xor     edx, edx; length
0x180193b0f  mov     rcx, rbx; string
0x180193b12  call    cs:__imp_WindowsGetStringRawBuffer
0x180193b18  mov     r8, rax
0x180193b1b  lea     rdx, [rbp+var_28]
0x180193b1f  call    ?GetSubscriptionContainer@TargetedContentTransformer@DataStoreCache@@AEBA?AV?$com_ptr_t@UITargetedContentContainer@TargetedContent@Services@Windows@@Uerr_exception_policy@wil@@@wil@@PEBG@Z; DataStoreCache::TargetedContentTransformer::GetSubscriptionContainer(ushort const *)
0x180193b24  nop
0x180193b25  mov     rcx, [rbp+var_28]
0x180193b29  test    rcx, rcx
0x180193b2c  jz      loc_180193C39
0x180193b32  mov     [rbp+arg_10], r15d
0x180193b36  mov     rax, [rcx]
0x180193b39  lea     rdx, [rbp+arg_10]
0x180193b3d  mov     rax, [rax+40h]
0x180193b41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180193b46  mov     rcx, [rbp+28h]; this
0x180193b4a  test    eax, eax
0x180193b4c  jns     short loc_180193B63
0x180193b4e  mov     r9d, eax; char *
0x180193b51  lea     r8, aShellcommonShe_103; "shellcommon\\shell\\datastorecache\\tra"...
0x180193b58  mov     edx, 906h; void *
0x180193b5d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180193b63  cmp     [rbp+arg_10], 2
0x180193b67  jnz     loc_180193C39
0x180193b6d  mov     [rbp+var_18], r15
0x180193b71  lea     rdx, ?ItemPath@TargetedContentProperties@DataStoreCache@@3U?$DataStoreProperty@PEAUHSTRING__@@@2@B; DataStoreCache::DataStoreProperty<HSTRING__ *> const DataStoreCache::TargetedContentProperties::ItemPath
0x180193b78  mov     rcx, [rbp+var_10]
0x180193b7c  call    ??$GetProperty@PEAUHSTRING__@@@DataStorePropertyBag@DataStoreCache@@QEBAQEAUHSTRING__@@AEBU?$DataStoreProperty@PEAUHSTRING__@@@1@@Z; DataStoreCache::DataStorePropertyBag::GetProperty<HSTRING__ *>(DataStoreCache::DataStoreProperty<HSTRING__ *> const &)
0x180193b81  mov     rdi, rax
0x180193b84  xor     ecx, ecx; string
0x180193b86  call    cs:__imp_WindowsDeleteString
0x180193b8c  mov     [rbp+var_18], rdi
0x180193b90  mov     [rbp+var_30], r15
0x180193b94  mov     rcx, [rbp+var_28]
0x180193b98  mov     rdx, [rcx]
0x180193b9b  mov     rax, [rdx+50h]
0x180193b9f  mov     [rbp+var_30], r15
0x180193ba3  lea     r8, [rbp+var_30]
0x180193ba7  mov     rdx, rdi
0x180193baa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180193baf  mov     rcx, [rbp+28h]; this
0x180193bb3  test    eax, eax
0x180193bb5  jns     short loc_180193BCC
0x180193bb7  mov     r9d, eax; char *
0x180193bba  lea     r8, aShellcommonShe_103; "shellcommon\\shell\\datastorecache\\tra"...
0x180193bc1  mov     edx, 90Fh; void *
0x180193bc6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180193bcc  mov     [rbp+arg_18], r15
0x180193bd0  mov     rcx, [rbp+var_30]
0x180193bd4  mov     rax, [rcx]
0x180193bd7  mov     [rbp+arg_18], r15
0x180193bdb  lea     rdx, [rbp+arg_18]
0x180193bdf  mov     rax, [rax+40h]
0x180193be3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180193be8  mov     rcx, [rbp+28h]; this
0x180193bec  test    eax, eax
0x180193bee  jns     short loc_180193C05
0x180193bf0  mov     r9d, eax; char *
0x180193bf3  lea     r8, aShellcommonShe_103; "shellcommon\\shell\\datastorecache\\tra"...
0x180193bfa  mov     edx, 911h; void *
0x180193bff  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180193c05  mov     rax, [rbp+arg_18]
0x180193c09  mov     [rbp+arg_18], r15
0x180193c0d  mov     [rsi], rax
0x180193c10  lea     rcx, [rbp+arg_18]; void *
0x180193c14  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x180193c19  nop
0x180193c1a  lea     rcx, [rbp+var_30]; void *
0x180193c1e  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x180193c23  nop
0x180193c24  mov     rcx, rdi; string
0x180193c27  call    cs:__imp_WindowsDeleteString
0x180193c2d  nop
0x180193c2e  lea     rcx, [rbp+var_28]; void *
0x180193c32  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x180193c37  jmp     short loc_180193C45
0x180193c39  lea     rcx, [rbp+var_28]; void *
0x180193c3d  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x180193c42  mov     [rsi], r15
0x180193c45  mov     rcx, rbx; string
0x180193c48  call    cs:__imp_WindowsDeleteString
0x180193c4e  nop
0x180193c4f  mov     rcx, [rbp+var_8]; this
0x180193c53  test    rcx, rcx
0x180193c56  jz      short loc_180193C5E
0x180193c58  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180193c5d  nop
0x180193c5e  mov     rcx, [rbp+string]; string
0x180193c62  call    cs:__imp_WindowsDeleteString
0x180193c68  mov     rax, rsi
0x180193c6b  mov     rbx, [rsp+70h+arg_0]
0x180193c73  add     rsp, 70h
0x180193c77  pop     r15
0x180193c79  pop     r14
0x180193c7b  pop     rdi
0x180193c7c  pop     rsi
0x180193c7d  pop     rbp
0x180193c7e  retn
```
