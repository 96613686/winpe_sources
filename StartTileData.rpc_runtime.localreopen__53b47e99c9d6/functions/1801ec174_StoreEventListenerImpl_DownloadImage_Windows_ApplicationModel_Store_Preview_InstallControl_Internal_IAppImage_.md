# StoreEventListenerImpl::DownloadImage(Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppImage *,WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier *,uint,uint,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1801ec174`
- end: `0x1801ec372`
- name: `?DownloadImage@StoreEventListenerImpl@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUIAppImage@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@PEAUIUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@IIAEBV23@@Z`
- size: `510`
- prototype: `__int64 __fastcall(HSTRING, __int64, __int64, __int64, unsigned int, int, _QWORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180187298`

## callees

- `0x18000ce94`
- `0x18001dac0`
- `0x1800756e4`
- `0x1800c158c`
- `0x1800c18c4`
- `0x18015cfa4`
- `0x1801ec174`
- `0x18022cc70`
- `0x18023f0b0`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ec1e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ec244`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ec331`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ec343`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ec1e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ec244`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ec331`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ec343`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801ec2c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801ec2c5`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1801ec2d8`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1801ec2d8`

## string_xrefs

- `0x1801ec1c9`: `shellcommon\shell\tiles\curatedtilecollections\storeeventlistener\lib\storeeventlistenerimpl.cpp`
- `0x1801ec221`: `shellcommon\shell\tiles\curatedtilecollections\storeeventlistener\lib\storeeventlistenerimpl.cpp`
- `0x1801ec2ad`: `shellcommon\shell\tiles\curatedtilecollections\storeeventlistener\lib\storeeventlistenerimpl.cpp`
- `0x1801ec2e6`: `shellcommon\shell\tiles\curatedtilecollections\storeeventlistener\lib\storeeventlistenerimpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=37
__int64 __fastcall StoreEventListenerImpl::DownloadImage(
        HSTRING a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        int a6,
        _QWORD *a7)
{
  __int64 (__fastcall *v10)(__int64, __int64 *); // rbx
  int v11; // eax
  __int64 v12; // rbx
  int v13; // eax
  void (__fastcall *v14)(__int64, HSTRING *); // rbx
  _QWORD *v15; // r8
  int v16; // eax
  const WCHAR *StringRawBuffer; // rax
  LPCWSTR v18; // rbx
  const char *v19; // r9
  int v21; // [rsp+20h] [rbp-40h]
  int v22; // [rsp+20h] [rbp-40h]
  __int64 v23; // [rsp+38h] [rbp-28h] BYREF
  LPCWSTR lpNewFileName[4]; // [rsp+40h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  HSTRING string; // [rsp+80h] [rbp+20h] BYREF
  HSTRING v27; // [rsp+90h] [rbp+30h] BYREF

  string = a1;
  v23 = 0;
  v10 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a3 + 96LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
  v11 = v10(a3, &v23);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x15B,
      (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\storeeventlistener\\lib\\storeeventlistenerimpl.cpp",
      (const char *)(unsigned int)v11,
      v21);
  string = 0;
  WindowsDeleteString(0);
  string = 0;
  v12 = v23;
  v13 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Foundation::IAsyncOperation<HSTRING__ *>>(v23);
  if ( v13 >= 0 )
    v13 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v12 + 64LL))(v12, &string);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x15E,
      (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\storeeventlistener\\lib\\storeeventlistenerimpl.cpp",
      (const char *)(unsigned int)v13,
      v21);
  v27 = 0;
  v14 = *(void (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a4 + 56LL);
  WindowsDeleteString(0);
  v27 = 0;
  v14(a4, &v27);
  memset(lpNewFileName, 0, 24);
  v15 = a7;
  if ( a7[3] > 7u )
    v15 = (_QWORD *)*a7;
  v16 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
          lpNewFileName,
          L"%s\\%03dX%03d.png",
          v15,
          a5,
          a6);
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x168,
      (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\storeeventlistener\\lib\\storeeventlistenerimpl.cpp",
      (const char *)(unsigned int)v16,
      v22);
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v18 = lpNewFileName[0];
  if ( !CopyFileW(StringRawBuffer, lpNewFileName[0], 0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x16A,
      (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\storeeventlistener\\lib\\storeeventlistenerimpl.cpp",
      v19);
  if ( (Microsoft_Windows_ShellCommon_StartLayoutPopulationEnableBits & 1) != 0 )
    McTemplateU0z_EventWriteTransfer(
      &Microsoft_Windows_StartLayoutPopulation_Provider_Context,
      ImageAssetDownloaded,
      v18);
  std::wstring::wstring(a2, v18);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(lpNewFileName);
  WindowsDeleteString(v27);
  v27 = 0;
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
  return a2;
}

```

## disassembly

```asm
0x1801ec174  mov     [rsp-18h+arg_8], rbx
0x1801ec179  mov     [rsp-18h+arg_18], rsi
0x1801ec17e  mov     [rsp-18h+string], rcx
0x1801ec183  push    rbp
0x1801ec184  push    rdi
0x1801ec185  push    r14
0x1801ec187  mov     rbp, rsp
0x1801ec18a  sub     rsp, 60h
0x1801ec18e  mov     r14, r9
0x1801ec191  mov     rdi, r8
0x1801ec194  mov     rsi, rdx
0x1801ec197  mov     [rbp+var_28], 0
0x1801ec19f  mov     rax, [r8]
0x1801ec1a2  mov     rbx, [rax+60h]
0x1801ec1a6  lea     rcx, [rbp+var_28]
0x1801ec1aa  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801ec1af  lea     rdx, [rbp+var_28]
0x1801ec1b3  mov     rcx, rdi
0x1801ec1b6  mov     rax, rbx
0x1801ec1b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ec1be  mov     rcx, [rbp+18h]; this
0x1801ec1c2  test    eax, eax
0x1801ec1c4  jns     short loc_1801EC1DB
0x1801ec1c6  mov     r9d, eax; char *
0x1801ec1c9  lea     r8, aShellcommonShe_106; "shellcommon\\shell\\tiles\\curatedtilec"...
0x1801ec1d0  mov     edx, 15Bh; void *
0x1801ec1d5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801ec1db  mov     [rbp+string], 0
0x1801ec1e3  xor     ecx, ecx; string
0x1801ec1e5  call    cs:__imp_WindowsDeleteString
0x1801ec1eb  mov     [rbp+string], 0
0x1801ec1f3  mov     rbx, [rbp+var_28]
0x1801ec1f7  mov     rcx, rbx
0x1801ec1fa  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperation@PEAUHSTRING__@@@23@@@YAJPEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Foundation::IAsyncOperation<HSTRING__ *>>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,void *)
0x1801ec1ff  test    eax, eax
0x1801ec201  js      short loc_1801EC216
0x1801ec203  mov     rax, [rbx]
0x1801ec206  lea     rdx, [rbp+string]
0x1801ec20a  mov     rcx, rbx
0x1801ec20d  mov     rax, [rax+40h]
0x1801ec211  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ec216  mov     rcx, [rbp+18h]; this
0x1801ec21a  test    eax, eax
0x1801ec21c  jns     short loc_1801EC233
0x1801ec21e  mov     r9d, eax; char *
0x1801ec221  lea     r8, aShellcommonShe_106; "shellcommon\\shell\\tiles\\curatedtilec"...
0x1801ec228  mov     edx, 15Eh; void *
0x1801ec22d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801ec233  mov     [rbp+arg_10], 0
0x1801ec23b  mov     rax, [r14]
0x1801ec23e  mov     rbx, [rax+38h]
0x1801ec242  xor     ecx, ecx; string
0x1801ec244  call    cs:__imp_WindowsDeleteString
0x1801ec24a  mov     [rbp+arg_10], 0
0x1801ec252  lea     rdx, [rbp+arg_10]
0x1801ec256  mov     rcx, r14
0x1801ec259  mov     rax, rbx
0x1801ec25c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ec261  mov     [rbp+lpNewFileName], 0
0x1801ec269  mov     [rbp+var_18], 0
0x1801ec271  mov     [rbp+var_10], 0
0x1801ec279  mov     r8, [rbp+arg_30]
0x1801ec27d  cmp     qword ptr [r8+18h], 7
0x1801ec282  jbe     short loc_1801EC287
0x1801ec284  mov     r8, [r8]
0x1801ec287  mov     eax, [rbp+arg_28]
0x1801ec28a  mov     [rsp+60h+var_40], eax; int
0x1801ec28e  mov     r9d, [rbp+arg_20]
0x1801ec292  lea     rdx, aS03dx03dPng; "%s\\%03dX%03d.png"
0x1801ec299  lea     rcx, [rbp+lpNewFileName]
0x1801ec29d  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1801ec2a2  mov     rcx, [rbp+18h]; this
0x1801ec2a6  test    eax, eax
0x1801ec2a8  jns     short loc_1801EC2BF
0x1801ec2aa  mov     r9d, eax; char *
0x1801ec2ad  lea     r8, aShellcommonShe_106; "shellcommon\\shell\\tiles\\curatedtilec"...
0x1801ec2b4  mov     edx, 168h; void *
0x1801ec2b9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801ec2bf  xor     edx, edx; length
0x1801ec2c1  mov     rcx, [rbp+string]; string
0x1801ec2c5  call    cs:__imp_WindowsGetStringRawBuffer
0x1801ec2cb  xor     r8d, r8d; bFailIfExists
0x1801ec2ce  mov     rbx, [rbp+lpNewFileName]
0x1801ec2d2  mov     rdx, rbx; lpNewFileName
0x1801ec2d5  mov     rcx, rax; lpExistingFileName
0x1801ec2d8  call    cs:__imp_CopyFileW
0x1801ec2de  mov     rcx, [rbp+18h]; this
0x1801ec2e2  test    eax, eax
0x1801ec2e4  jnz     short loc_1801EC2F8
0x1801ec2e6  lea     r8, aShellcommonShe_106; "shellcommon\\shell\\tiles\\curatedtilec"...
0x1801ec2ed  mov     edx, 16Ah; void *
0x1801ec2f2  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1801ec2f8  test    cs:Microsoft_Windows_ShellCommon_StartLayoutPopulationEnableBits, 1
0x1801ec2ff  jz      short loc_1801EC317
0x1801ec301  mov     r8, rbx
0x1801ec304  lea     rdx, ImageAssetDownloaded
0x1801ec30b  lea     rcx, Microsoft_Windows_StartLayoutPopulation_Provider_Context
0x1801ec312  call    McTemplateU0z_EventWriteTransfer
0x1801ec317  mov     rdx, rbx
0x1801ec31a  mov     rcx, rsi
0x1801ec31d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1801ec322  nop
0x1801ec323  lea     rcx, [rbp+lpNewFileName]
0x1801ec327  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801ec32c  nop
0x1801ec32d  mov     rcx, [rbp+arg_10]; string
0x1801ec331  call    cs:__imp_WindowsDeleteString
0x1801ec337  mov     [rbp+arg_10], 0
0x1801ec33f  mov     rcx, [rbp+string]; string
0x1801ec343  call    cs:__imp_WindowsDeleteString
0x1801ec349  mov     [rbp+string], 0
0x1801ec351  lea     rcx, [rbp+var_28]
0x1801ec355  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801ec35a  mov     rax, rsi
0x1801ec35d  lea     r11, [rsp+60h+var_s0]
0x1801ec362  mov     rbx, [r11+28h]
0x1801ec366  mov     rsi, [r11+38h]
0x1801ec36a  mov     rsp, r11
0x1801ec36d  pop     r14
0x1801ec36f  pop     rdi
0x1801ec370  pop     rbp
0x1801ec371  retn
```
