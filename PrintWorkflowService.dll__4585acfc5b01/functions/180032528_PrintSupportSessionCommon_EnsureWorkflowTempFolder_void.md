# PrintSupportSessionCommon::EnsureWorkflowTempFolder(void)

- ea: `0x180032528`
- end: `0x1800326d7`
- name: `?EnsureWorkflowTempFolder@PrintSupportSessionCommon@@IEAA?AUStorageFolder@Storage@Windows@winrt@@XZ`
- size: `431`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180033510`
- `0x180042dc8`

## callees

- `0x180003ca0`
- `0x18000495c`
- `0x1800097ec`
- `0x1800129f8`
- `0x180023664`
- `0x18002fad8`
- `0x180031168`
- `0x18003182c`
- `0x180032528`
- `0x180035b84`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18003257c`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18003257c`

## string_xrefs

- `0x180032613`: `WorkflowTemp`
- `0x1800326c2`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportsessioncommon.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PrintSupportSessionCommon::EnsureWorkflowTempFolder(__int64 a1, __int64 a2)
{
  const char *v3; // r9
  __int64 v4; // rcx
  unsigned int v5; // eax
  _BYTE *v7; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v8[8]; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v9[3]; // [rsp+40h] [rbp-C0h] BYREF
  int v10; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v11; // [rsp+60h] [rbp-A0h]
  _BYTE v12[32]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v13[4]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v14[264]; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  v9[0] = a2;
  memset_0(v14, 0, 0x208u);
  if ( !(unsigned int)GetTempPath2W(260, v14) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x1F7,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportsessioncommon.cpp",
      v3);
  winrt::param::hstring::hstring((winrt::param::hstring *)v12, v14);
  v7 = v12;
  v9[2] = &qword_180084028;
  _InterlockedIncrement64(&qword_180084028);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Storage::StorageFolder,winrt::Windows::Storage::IStorageFolderStatics> )
  {
    _lambda_0ba328cd2edd55f5ab6423f6a7e8dff9_::operator()(
      &v7,
      v8,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Storage::StorageFolder,winrt::Windows::Storage::IStorageFolderStatics>);
    _InterlockedDecrement64(&qword_180084028);
  }
  else
  {
    _InterlockedDecrement64(&qword_180084028);
    winrt::impl::factory_cache_entry<winrt::Windows::Storage::StorageFolder,winrt::Windows::Storage::IStorageFolderStatics>::call<_lambda_0ba328cd2edd55f5ab6423f6a7e8dff9_ &>(
      v4,
      v8,
      &v7);
  }
  winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Storage::StorageFolder>,winrt::Windows::Storage::StorageFolder>::get(
    v8,
    v9);
  winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow::~IWindow((winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow *)v8);
  winrt::param::hstring::hstring((winrt::param::hstring *)v13, L"WorkflowTemp");
  v7 = 0;
  v10 = 0;
  v11 = 0;
  v5 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, _BYTE **))(*(_QWORD *)v9[0] + 72LL))(v9[0], v13[0], 3, &v7);
  winrt::check_hresult(v8, v5, &v10);
  winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Storage::StorageFolder>,winrt::Windows::Storage::StorageFolder>::get(
    &v7,
    a2);
  winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow::~IWindow((winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow *)&v7);
  winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow::~IWindow((winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow *)v9);
  return a2;
}

```

## disassembly

```asm
0x180032528  mov     [rsp-8+arg_0], rbx
0x18003252d  mov     [rsp-8+arg_10], rdi
0x180032532  push    rbp
0x180032533  lea     rbp, [rsp-1D0h]
0x18003253b  sub     rsp, 2D0h
0x180032542  mov     rax, cs:__security_cookie
0x180032549  xor     rax, rsp
0x18003254c  mov     [rbp+1D0h+var_10], rax
0x180032553  mov     rbx, rdx
0x180032556  mov     [rsp+2D0h+var_290], rdx
0x18003255b  xor     edx, edx; Val
0x18003255d  mov     r8d, 208h; Size
0x180032563  lea     rcx, [rbp+1D0h+var_220]; void *
0x180032567  call    memset_0
0x18003256c  mov     rdi, [rbp+1D8h]
0x180032573  lea     rdx, [rbp+1D0h+var_220]
0x180032577  mov     ecx, 104h
0x18003257c  call    cs:__imp_GetTempPath2W
0x180032582  test    eax, eax
0x180032584  jz      loc_1800326C2
0x18003258a  lea     rdx, [rbp+1D0h+var_220]; unsigned __int16 *
0x18003258e  lea     rcx, [rsp+2D0h+var_260]; this
0x180032593  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180032598  lea     rax, [rsp+2D0h+var_260]
0x18003259d  mov     [rsp+2D0h+var_2A0], rax
0x1800325a2  lea     rax, qword_180084028
0x1800325a9  mov     [rsp+2D0h+var_280], rax
0x1800325ae  lock inc cs:qword_180084028
0x1800325b6  cmp     cs:??$factory_cache_entry_v@UStorageFolder@Storage@Windows@winrt@@UIStorageFolderStatics@234@@impl@winrt@@3U?$factory_cache_entry@UStorageFolder@Storage@Windows@winrt@@UIStorageFolderStatics@234@@12@A, 0; factory_cache_entry<winrt::Windows::Storage::StorageFolder,winrt::Windows::Storage::IStorageFolderStatics>::winrt::factory_cache_entry<winrt::Windows::Storage::StorageFolder,winrt::Windows::Storage::IStorageFolderStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Storage::StorageFolder,winrt::Windows::Storage::IStorageFolderStatics>
0x1800325be  jz      short loc_1800325E1
0x1800325c0  lea     r8, ??$factory_cache_entry_v@UStorageFolder@Storage@Windows@winrt@@UIStorageFolderStatics@234@@impl@winrt@@3U?$factory_cache_entry@UStorageFolder@Storage@Windows@winrt@@UIStorageFolderStatics@234@@12@A; factory_cache_entry<winrt::Windows::Storage::StorageFolder,winrt::Windows::Storage::IStorageFolderStatics>::winrt::factory_cache_entry<winrt::Windows::Storage::StorageFolder,winrt::Windows::Storage::IStorageFolderStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Storage::StorageFolder,winrt::Windows::Storage::IStorageFolderStatics>
0x1800325c7  lea     rdx, [rsp+2D0h+var_298]
0x1800325cc  lea     rcx, [rsp+2D0h+var_2A0]
0x1800325d1  call    ??R_lambda_0ba328cd2edd55f5ab6423f6a7e8dff9_@@QEBA@AEBUIStorageFolderStatics@Storage@Windows@winrt@@@Z; _lambda_0ba328cd2edd55f5ab6423f6a7e8dff9_::operator()(winrt::Windows::Storage::IStorageFolderStatics const &)
0x1800325d6  nop
0x1800325d7  lock dec cs:qword_180084028
0x1800325df  jmp     short loc_1800325F9
0x1800325e1  lock dec cs:qword_180084028
0x1800325e9  lea     r8, [rsp+2D0h+var_2A0]
0x1800325ee  lea     rdx, [rsp+2D0h+var_298]
0x1800325f3  call    ??$call@AEAV_lambda_0ba328cd2edd55f5ab6423f6a7e8dff9_@@@?$factory_cache_entry@UStorageFolder@Storage@Windows@winrt@@UIStorageFolderStatics@234@@impl@winrt@@QEAA?A_PAEAV_lambda_0ba328cd2edd55f5ab6423f6a7e8dff9_@@@Z
0x1800325f8  nop
0x1800325f9  lea     rdx, [rsp+2D0h+var_290]
0x1800325fe  lea     rcx, [rsp+2D0h+var_298]
0x180032603  call    ?get@?$consume_Windows_Foundation_IAsyncOperation@U?$IAsyncOperation@UStorageFolder@Storage@Windows@winrt@@@Foundation@Windows@winrt@@UStorageFolder@Storage@34@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Storage::StorageFolder>,winrt::Windows::Storage::StorageFolder>::get(void)
0x180032608  nop
0x180032609  lea     rcx, [rsp+2D0h+var_298]; this
0x18003260e  call    ??1IWindow@WindowManagement@ApplicationModel@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow::~IWindow(void)
0x180032613  lea     rdx, aWorkflowtemp; "WorkflowTemp"
0x18003261a  lea     rcx, [rbp+1D0h+var_240]; this
0x18003261e  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180032623  mov     [rsp+2D0h+var_2A0], 0
0x18003262c  mov     rcx, [rsp+2D0h+var_290]
0x180032631  mov     [rsp+2D0h+var_278], 0
0x180032639  xorps   xmm0, xmm0
0x18003263c  movdqu  [rsp+2D0h+var_270], xmm0
0x180032642  mov     rax, [rcx]
0x180032645  lea     r9, [rsp+2D0h+var_2A0]
0x18003264a  mov     r8d, 3
0x180032650  mov     rdx, [rbp+1D0h+var_240]
0x180032654  mov     rax, [rax+48h]
0x180032658  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003265d  lea     r8, [rsp+2D0h+var_278]
0x180032662  mov     edx, eax
0x180032664  lea     rcx, [rsp+2D0h+var_298]
0x180032669  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18003266e  mov     rcx, [rsp+2D0h+var_2A0]
0x180032673  mov     [rsp+2D0h+var_2A0], rcx
0x180032678  mov     rdx, rbx
0x18003267b  lea     rcx, [rsp+2D0h+var_2A0]
0x180032680  call    ?get@?$consume_Windows_Foundation_IAsyncOperation@U?$IAsyncOperation@UStorageFolder@Storage@Windows@winrt@@@Foundation@Windows@winrt@@UStorageFolder@Storage@34@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Storage::StorageFolder>,winrt::Windows::Storage::StorageFolder>::get(void)
0x180032685  nop
0x180032686  lea     rcx, [rsp+2D0h+var_2A0]; this
0x18003268b  call    ??1IWindow@WindowManagement@ApplicationModel@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow::~IWindow(void)
0x180032690  nop
0x180032691  lea     rcx, [rsp+2D0h+var_290]; this
0x180032696  call    ??1IWindow@WindowManagement@ApplicationModel@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow::~IWindow(void)
0x18003269b  mov     rax, rbx
0x18003269e  mov     rcx, [rbp+1D0h+var_10]
0x1800326a5  xor     rcx, rsp; StackCookie
0x1800326a8  call    __security_check_cookie
0x1800326ad  lea     r11, [rsp+2D0h+var_s0]
0x1800326b5  mov     rbx, [r11+10h]
0x1800326b9  mov     rdi, [r11+20h]
0x1800326bd  mov     rsp, r11
0x1800326c0  pop     rbp
0x1800326c1  retn
0x1800326c2  lea     r8, aOnecoreuapPrin_26; "onecoreuap\\printscan\\print\\workflow"...
0x1800326c9  mov     edx, 1F7h; void *
0x1800326ce  mov     rcx, rdi; this
0x1800326d1  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
