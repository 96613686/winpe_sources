# _lambda_e9a4aa2ff6130b9b99ec1f5755b266bd_::operator()

- ea: `0x1800c0cf0`
- end: `0x1800c0fe3`
- name: `_lambda_e9a4aa2ff6130b9b99ec1f5755b266bd_::operator()`
- size: `755`
- prototype: ``
- caller_count: `1`
- callee_count: `29`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800c4700`

## callees

- `0x1800049e0`
- `0x18000617a`
- `0x18000619e`
- `0x1800061aa`
- `0x18003fee0`
- `0x18003ff8c`
- `0x18007e3d0`
- `0x18008192c`
- `0x1800819a8`
- `0x180081a5c`
- `0x180087934`
- `0x180088ca4`
- `0x18008ca74`
- `0x18008e508`
- `0x18008fa58`
- `0x180092490`
- `0x180092c54`
- `0x180092d24`
- `0x180092e54`
- `0x180092f34`
- `0x1800be4e4`
- `0x1800be644`
- `0x1800c0cf0`
- `0x1800c19a0`
- `0x1800c2220`
- `0x1800c38e0`
- `0x1800c41bc`
- `0x1800c5ac8`
- `0x1800caf0c`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1800c0f3d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1800c0f3d`

## pseudocode

```c
// Hidden C++ exception states: #wind=23
void __fastcall lambda_e9a4aa2ff6130b9b99ec1f5755b266bd_::operator()(__int64 a1)
{
  __int64 v1; // rbx
  bool v2; // dl
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // r13
  __int64 v6; // rcx
  __int64 v7; // rdi
  __int64 Object; // rsi
  __int64 v9; // r15
  HSTRING v10; // r14
  __int64 FolderFromPathAsync; // r12
  __int64 v12; // r13
  __int64 v13; // rax
  __int64 v14; // r8
  __int64 v15; // rax
  Cortana::ConstraintIndex::Search::SettingsFilterCacheManager **v16; // rax
  HSTRING v17; // rsi
  HSTRING v18; // rdi
  const WCHAR *StringRawBuffer_0; // rax
  void *v20; // rdx
  const char *v21; // r9
  __int64 v22; // [rsp+20h] [rbp-168h] BYREF
  __int64 v23; // [rsp+28h] [rbp-160h] BYREF
  int v24; // [rsp+30h] [rbp-158h]
  __int64 v25; // [rsp+38h] [rbp-150h]
  __int64 v26; // [rsp+40h] [rbp-148h]
  __int64 v27; // [rsp+48h] [rbp-140h]
  __int64 v28; // [rsp+50h] [rbp-138h]
  __int64 v29; // [rsp+58h] [rbp-130h]
  HSTRING v30; // [rsp+60h] [rbp-128h]
  _BYTE v31[8]; // [rsp+68h] [rbp-120h] BYREF
  std::_Ref_count_base *v32; // [rsp+70h] [rbp-118h]
  _BYTE v33[8]; // [rsp+78h] [rbp-110h] BYREF
  std::_Ref_count_base *v34; // [rsp+80h] [rbp-108h]
  _BYTE v35[96]; // [rsp+88h] [rbp-100h] BYREF
  _BYTE v36[96]; // [rsp+E8h] [rbp-A0h] BYREF
  __int128 v37; // [rsp+148h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+0h]

  try
  {
    v1 = a1;
    v26 = a1;
    v2 = **(_BYTE **)a1
      || Cortana::ConstraintIndex::Search::SettingsFilterCacheManager::IsSettingsRebuildRequired(**(Cortana::ConstraintIndex::Search::SettingsFilterCacheManager ***)(a1 + 8));
    v3 = **(_QWORD **)(v1 + 8);
    if ( v2 )
    {
      v4 = *(_QWORD *)Cortana::ConstraintIndex::Search::SettingsFilterCacheManager::UpdateCacheOnDiskAndReadIntoMemory(
                        v3,
                        &v23);
      if ( !v4 )
        Concurrency::details::_DefaultTaskHelper::_NoCallOnDefaultTask_ErrorImpl();
    }
    else
    {
      if ( *(_QWORD *)(v3 + 88) )
      {
LABEL_12:
        v37 = 0;
        v5 = Concurrency::task_options::task_options((Concurrency::task_options *)v35);
        v7 = Windows::Storage::ApplicationData::Current::get(v6);
        v27 = v7;
        Object = Windows::Data::Json::IJsonValue::GetObject(v7);
        v28 = Object;
        v9 = __abi_winrt_cast_to(0, Object, _uuidof__AUIStorageItem_Storage_Windows__);
        v29 = v9;
        v10 = (HSTRING)Windows::Storage::IStorageItem::Path::get(v9);
        v30 = v10;
        FolderFromPathAsync = Windows::Storage::StorageFolder::GetFolderFromPathAsync(v10);
        v25 = FolderFromPathAsync;
        v12 = Concurrency::create_task<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFolder __gc *> __gc *>(
                v33,
                FolderFromPathAsync,
                v5);
        LOBYTE(v24) = 0;
        v23 = 0;
        v13 = Concurrency::task_options::task_options(v36, &v23);
        v15 = Concurrency::task_Windows::Storage::StorageFolder___::then__lambda_a0a3e839c36ac553e23b12b05f69e8f2___(
                v12,
                v31,
                v14,
                v13,
                v35,
                v23,
                v24,
                v25);
        v22 = *(_QWORD *)(v1 + 8);
        Concurrency::task_Windows::Storage::StorageFolder___::then__lambda_8bf42058bbb4f07f7e03b81c2538e7df___(
          v15,
          &v37,
          &v22);
        if ( v32 )
          std::_Ref_count_base::_Decref(v32);
        if ( v34 )
          std::_Ref_count_base::_Decref(v34);
        __abi_winrt_ptr_dtor(FolderFromPathAsync);
        WindowsDeleteString_0(v10);
        __abi_winrt_ptr_dtor(v9);
        __abi_winrt_ptr_dtor(Object);
        __abi_winrt_ptr_dtor(v7);
        if ( !(_QWORD)v37 )
          Concurrency::details::_DefaultTaskHelper::_NoCallOnDefaultTask_ErrorImpl();
        Concurrency::details::_Task_impl_base::_Wait(v37);
        v16 = *(Cortana::ConstraintIndex::Search::SettingsFilterCacheManager ***)(v1 + 8);
        if ( !*((_QWORD *)*v16 + 21) )
          Cortana::ConstraintIndex::Search::SettingsFilterCacheManager::BuildSQLiteIndex(*v16);
        v17 = (HSTRING)Cortana::ConstraintIndex::Search::IConstraintIndexOptions::CurrentConstraintIndexCabPath::get(*(_QWORD *)(*(_QWORD *)(v1 + 16) + 16LL));
        v25 = (__int64)v17;
        v18 = (HSTRING)__abi_winrt_ptrto_string_ctor(v17);
        v25 = (__int64)v18;
        WindowsDeleteString_0(v17);
        if ( WindowsIsStringEmpty_0(v18)
          || (StringRawBuffer_0 = WindowsGetStringRawBuffer_0(v18, 0), !PathFileExistsW(StringRawBuffer_0))
          || *(_QWORD *)(**(_QWORD **)(v1 + 8) + 168LL)
          && !(unsigned int)WindowsUdk::System::Profile::ISystemSettingEntryPointIndex::SynonymsAndRanksIndexState::get(*(_QWORD *)(*(_QWORD *)(v1 + 16) + 168LL)) )
        {
          Cortana::ConstraintIndex::Search::SettingsFilterCacheManager::ApplyWeightAndSynonymsToSQLiteIndex(**(Cortana::ConstraintIndex::Search::SettingsFilterCacheManager ***)(v1 + 8));
        }
        WindowsDeleteString_0(v18);
        std::shared_ptr<Concurrency::details::_Task_impl<Windows::Foundation::Collections::IVectorView<Cortana::ConstraintIndex::Search::ISettingResultItem __gc *> __gc *>>::~shared_ptr<Concurrency::details::_Task_impl<Windows::Foundation::Collections::IVectorView<Cortana::ConstraintIndex::Search::ISettingResultItem __gc *> __gc *>>(&v37);
        goto LABEL_31;
      }
      v4 = *(_QWORD *)Cortana::ConstraintIndex::Search::SettingsFilterCacheManager::ReadSettingsCacheFromDisk(v3, &v23);
      if ( !v4 )
        Concurrency::details::_DefaultTaskHelper::_NoCallOnDefaultTask_ErrorImpl();
    }
    Concurrency::details::_Task_impl_base::_Wait(v4);
    std::shared_ptr<Concurrency::details::_Task_impl<Windows::Foundation::Collections::IVectorView<Cortana::ConstraintIndex::Search::ISettingResultItem __gc *> __gc *>>::~shared_ptr<Concurrency::details::_Task_impl<Windows::Foundation::Collections::IVectorView<Cortana::ConstraintIndex::Search::ISettingResultItem __gc *> __gc *>>(&v23);
    goto LABEL_12;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0xBD,
      (unsigned int)"shellcommon\\shell\\cortana\\constraintindex\\src\\Search\\SettingsFilterCacheManager.cpp",
      v21);
    v1 = v26;
  }
LABEL_31:
  wil::details::SetEvent(**(wil::details ***)(v1 + 24), v20);
}

```

## disassembly

```asm
0x1800c0cf0  mov     [rsp+arg_8], rbx
0x1800c0cf5  mov     [rsp+arg_10], rsi
0x1800c0cfa  push    rdi
0x1800c0cfb  push    r12
0x1800c0cfd  push    r13
0x1800c0cff  push    r14
0x1800c0d01  push    r15
0x1800c0d03  sub     rsp, 160h
0x1800c0d0a  mov     rax, cs:__security_cookie
0x1800c0d11  xor     rax, rsp
0x1800c0d14  mov     [rsp+188h+var_30], rax
0x1800c0d1c  mov     rbx, rcx
0x1800c0d1f  mov     [rsp+188h+var_148], rcx
0x1800c0d24  mov     rax, [rcx]
0x1800c0d27  cmp     byte ptr [rax], 0
0x1800c0d2a  jnz     short loc_1800C0D40
0x1800c0d2c  mov     rcx, [rcx+8]
0x1800c0d30  mov     rcx, [rcx]; this
0x1800c0d33  call    ?IsSettingsRebuildRequired@SettingsFilterCacheManager@Search@ConstraintIndex@Cortana@@AEAA_NXZ; Cortana::ConstraintIndex::Search::SettingsFilterCacheManager::IsSettingsRebuildRequired(void)
0x1800c0d38  test    al, al
0x1800c0d3a  jnz     short loc_1800C0D40
0x1800c0d3c  xor     dl, dl
0x1800c0d3e  jmp     short loc_1800C0D42
0x1800c0d40  mov     dl, 1
0x1800c0d42  mov     rax, [rbx+8]
0x1800c0d46  mov     rcx, [rax]
0x1800c0d49  test    dl, dl
0x1800c0d4b  jz      short loc_1800C0D6C
0x1800c0d4d  lea     rdx, [rsp+188h+var_160]
0x1800c0d52  call    ?UpdateCacheOnDiskAndReadIntoMemory@SettingsFilterCacheManager@Search@ConstraintIndex@Cortana@@AEAA?AV?$task@X@Concurrency@@XZ; Cortana::ConstraintIndex::Search::SettingsFilterCacheManager::UpdateCacheOnDiskAndReadIntoMemory(void)
0x1800c0d57  nop
0x1800c0d58  mov     rcx, [rax]
0x1800c0d5b  test    rcx, rcx
0x1800c0d5e  jz      loc_1800C0FD0
0x1800c0d64  call    ?_Wait@_Task_impl_base@details@Concurrency@@QEAA?AW4task_group_status@3@XZ; Concurrency::details::_Task_impl_base::_Wait(void)
0x1800c0d69  nop
0x1800c0d6a  jmp     short loc_1800C0D90
0x1800c0d6c  cmp     qword ptr [rcx+58h], 0
0x1800c0d71  jnz     short loc_1800C0D9A
0x1800c0d73  lea     rdx, [rsp+188h+var_160]
0x1800c0d78  call    ?ReadSettingsCacheFromDisk@SettingsFilterCacheManager@Search@ConstraintIndex@Cortana@@AEAA?AV?$task@X@Concurrency@@XZ; Cortana::ConstraintIndex::Search::SettingsFilterCacheManager::ReadSettingsCacheFromDisk(void)
0x1800c0d7d  nop
0x1800c0d7e  mov     rcx, [rax]
0x1800c0d81  test    rcx, rcx
0x1800c0d84  jz      loc_1800C0FD6
0x1800c0d8a  call    ?_Wait@_Task_impl_base@details@Concurrency@@QEAA?AW4task_group_status@3@XZ; Concurrency::details::_Task_impl_base::_Wait(void)
0x1800c0d8f  nop
0x1800c0d90  lea     rcx, [rsp+188h+var_160]
0x1800c0d95  call    ??1?$shared_ptr@U?$_Task_impl@PE$AAU?$IVectorView@PE$AAUISettingResultItem@Search@ConstraintIndex@Cortana@@@Collections@Foundation@Windows@@@details@Concurrency@@@std@@QEAA@XZ; std::shared_ptr<Concurrency::details::_Task_impl<Windows::Foundation::Collections::IVectorView<Cortana::ConstraintIndex::Search::ISettingResultItem *> *>>::~shared_ptr<Concurrency::details::_Task_impl<Windows::Foundation::Collections::IVectorView<Cortana::ConstraintIndex::Search::ISettingResultItem *> *>>(void)
0x1800c0d9a  xorps   xmm0, xmm0
0x1800c0d9d  movups  [rsp+188h+var_40], xmm0
0x1800c0da5  lea     rax, [rsp+188h+var_100]
0x1800c0dad  mov     [rsp+188h+var_168], rax
0x1800c0db2  lea     rcx, [rsp+188h+var_100]; this
0x1800c0dba  call    ??0task_options@Concurrency@@QEAA@XZ; Concurrency::task_options::task_options(void)
0x1800c0dbf  mov     r13, rax
0x1800c0dc2  call    ?get@Current@ApplicationData@Storage@Windows@@SAPE$AAV234@XZ; Windows::Storage::ApplicationData::Current::get(void)
0x1800c0dc7  mov     rdi, rax
0x1800c0dca  mov     [rsp+188h+var_140], rax
0x1800c0dcf  mov     rcx, rax
0x1800c0dd2  call    ?GetObject@IJsonValue@Json@Data@Windows@@UE$AAAPE$AAVJsonObject@234@XZ; Windows::Data::Json::IJsonValue::GetObject(void)
0x1800c0dd7  mov     rsi, rax
0x1800c0dda  mov     [rsp+188h+var_138], rax
0x1800c0ddf  lea     r8, __uuidof_?AUIStorageItem@Storage@Windows@@
0x1800c0de6  mov     rdx, rax
0x1800c0de9  xor     ecx, ecx
0x1800c0deb  call    ?__abi_winrt_cast_to@@YAPE$AAVObject@Platform@@_NPE$AAV12@AEBU_GUID@@@Z; __abi_winrt_cast_to(bool,Platform::Object *,_GUID const &)
0x1800c0df0  mov     r15, rax
0x1800c0df3  mov     [rsp+188h+var_130], rax
0x1800c0df8  mov     rcx, rax
0x1800c0dfb  call    ?get@Path@IStorageItem@Storage@Windows@@UE$AAAPE$AAVString@Platform@@XZ; Windows::Storage::IStorageItem::Path::get(void)
0x1800c0e00  mov     r14, rax
0x1800c0e03  mov     [rsp+188h+var_128], rax
0x1800c0e08  mov     rcx, rax
0x1800c0e0b  call    ?GetFolderFromPathAsync@StorageFolder@Storage@Windows@@SAPE$AAU?$IAsyncOperation@PE$AAVStorageFolder@Storage@Windows@@@Foundation@3@PE$AAVString@Platform@@@Z; Windows::Storage::StorageFolder::GetFolderFromPathAsync(Platform::String *)
0x1800c0e10  mov     r12, rax
0x1800c0e13  mov     [rsp+188h+var_150], rax
0x1800c0e18  mov     r8, r13
0x1800c0e1b  mov     rdx, rax
0x1800c0e1e  lea     rcx, [rsp+188h+var_110]
0x1800c0e23  call    ??$create_task@PE$AAU?$IAsyncOperation@PE$AAVStorageFolder@Storage@Windows@@@Foundation@Windows@@@Concurrency@@YA?AV?$task@PE$AAVStorageFolder@Storage@Windows@@@0@PE$AAU?$IAsyncOperation@PE$AAVStorageFolder@Storage@Windows@@@Foundation@Windows@@Vtask_options@0@@Z; Concurrency::create_task<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFolder *> *>(Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFolder *> *,Concurrency::task_options)
0x1800c0e28  mov     r13, rax
0x1800c0e2b  mov     byte ptr [rsp+188h+var_158], 0
0x1800c0e30  mov     [rsp+188h+var_160], 0
0x1800c0e39  lea     rdx, [rsp+188h+var_160]
0x1800c0e3e  lea     rcx, [rsp+188h+var_A0]
0x1800c0e46  call    ??0task_options@Concurrency@@QEAA@Vtask_continuation_context@1@@Z; Concurrency::task_options::task_options(Concurrency::task_continuation_context)
0x1800c0e4b  mov     r9, rax
0x1800c0e4e  lea     rdx, [rsp+188h+var_120]
0x1800c0e53  mov     rcx, r13
0x1800c0e56  call    Concurrency__task_Windows__Storage__StorageFolder_____then__lambda_a0a3e839c36ac553e23b12b05f69e8f2___
0x1800c0e5b  nop
0x1800c0e5c  mov     rcx, [rbx+8]
0x1800c0e60  mov     [rsp+188h+var_168], rcx
0x1800c0e65  lea     r8, [rsp+188h+var_168]
0x1800c0e6a  lea     rdx, [rsp+188h+var_40]
0x1800c0e72  mov     rcx, rax
0x1800c0e75  call    Concurrency__task_Windows__Storage__StorageFolder_____then__lambda_8bf42058bbb4f07f7e03b81c2538e7df___
0x1800c0e7a  nop
0x1800c0e7b  mov     rcx, [rsp+188h+var_118]; this
0x1800c0e80  test    rcx, rcx
0x1800c0e83  jz      short loc_1800C0E8B
0x1800c0e85  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c0e8a  nop
0x1800c0e8b  mov     rcx, [rsp+188h+var_108]; this
0x1800c0e93  test    rcx, rcx
0x1800c0e96  jz      short loc_1800C0E9E
0x1800c0e98  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c0e9d  nop
0x1800c0e9e  mov     rcx, r12
0x1800c0ea1  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800c0ea6  nop
0x1800c0ea7  mov     rcx, r14; string
0x1800c0eaa  call    WindowsDeleteString_0
0x1800c0eaf  nop
0x1800c0eb0  mov     rcx, r15
0x1800c0eb3  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800c0eb8  nop
0x1800c0eb9  mov     rcx, rsi
0x1800c0ebc  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800c0ec1  nop
0x1800c0ec2  mov     rcx, rdi
0x1800c0ec5  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800c0eca  mov     rcx, qword ptr [rsp+188h+var_40]
0x1800c0ed2  test    rcx, rcx
0x1800c0ed5  jz      loc_1800C0FDC
0x1800c0edb  call    ?_Wait@_Task_impl_base@details@Concurrency@@QEAA?AW4task_group_status@3@XZ; Concurrency::details::_Task_impl_base::_Wait(void)
0x1800c0ee0  mov     rax, [rbx+8]
0x1800c0ee4  mov     rcx, [rax]; this
0x1800c0ee7  cmp     qword ptr [rcx+0A8h], 0
0x1800c0eef  jnz     short loc_1800C0EF6
0x1800c0ef1  call    ?BuildSQLiteIndex@SettingsFilterCacheManager@Search@ConstraintIndex@Cortana@@QEAAXXZ; Cortana::ConstraintIndex::Search::SettingsFilterCacheManager::BuildSQLiteIndex(void)
0x1800c0ef6  mov     rcx, [rbx+10h]
0x1800c0efa  mov     rcx, [rcx+10h]
0x1800c0efe  call    ?get@CurrentConstraintIndexCabPath@IConstraintIndexOptions@Search@ConstraintIndex@Cortana@@UE$AAAPE$AAVString@Platform@@XZ; Cortana::ConstraintIndex::Search::IConstraintIndexOptions::CurrentConstraintIndexCabPath::get(void)
0x1800c0f03  mov     rsi, rax
0x1800c0f06  mov     [rsp+188h+var_150], rax
0x1800c0f0b  mov     rcx, rax
0x1800c0f0e  call    ?__abi_winrt_ptrto_string_ctor@@YAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_ctor(Platform::String const volatile *)
0x1800c0f13  mov     rdi, rax
0x1800c0f16  mov     [rsp+188h+var_150], rax
0x1800c0f1b  mov     rcx, rsi; string
0x1800c0f1e  call    WindowsDeleteString_0
0x1800c0f23  nop
0x1800c0f24  mov     rcx, rdi; string
0x1800c0f27  call    WindowsIsStringEmpty_0
0x1800c0f2c  test    eax, eax
0x1800c0f2e  jnz     short loc_1800C0F6C
0x1800c0f30  xor     edx, edx; length
0x1800c0f32  mov     rcx, rdi; string
0x1800c0f35  call    WindowsGetStringRawBuffer_0
0x1800c0f3a  mov     rcx, rax; pszPath
0x1800c0f3d  call    cs:__imp_PathFileExistsW
0x1800c0f43  test    eax, eax
0x1800c0f45  jz      short loc_1800C0F6C
0x1800c0f47  mov     rax, [rbx+8]
0x1800c0f4b  mov     rcx, [rax]
0x1800c0f4e  cmp     qword ptr [rcx+0A8h], 0
0x1800c0f56  jz      short loc_1800C0F79
0x1800c0f58  mov     rcx, [rbx+10h]
0x1800c0f5c  mov     rcx, [rcx+0A8h]
0x1800c0f63  call    ?get@SynonymsAndRanksIndexState@ISystemSettingEntryPointIndex@Profile@System@WindowsUdk@@UE$AAA?AW41345@XZ; WindowsUdk::System::Profile::ISystemSettingEntryPointIndex::SynonymsAndRanksIndexState::get(void)
0x1800c0f68  test    eax, eax
0x1800c0f6a  jnz     short loc_1800C0F79
0x1800c0f6c  mov     rcx, [rbx+8]
0x1800c0f70  mov     rcx, [rcx]; this
0x1800c0f73  call    ?ApplyWeightAndSynonymsToSQLiteIndex@SettingsFilterCacheManager@Search@ConstraintIndex@Cortana@@AEAAXXZ; Cortana::ConstraintIndex::Search::SettingsFilterCacheManager::ApplyWeightAndSynonymsToSQLiteIndex(void)
0x1800c0f78  nop
0x1800c0f79  mov     rcx, rdi; string
0x1800c0f7c  call    WindowsDeleteString_0
0x1800c0f81  nop
0x1800c0f82  lea     rcx, [rsp+188h+var_40]
0x1800c0f8a  call    ??1?$shared_ptr@U?$_Task_impl@PE$AAU?$IVectorView@PE$AAUISettingResultItem@Search@ConstraintIndex@Cortana@@@Collections@Foundation@Windows@@@details@Concurrency@@@std@@QEAA@XZ; std::shared_ptr<Concurrency::details::_Task_impl<Windows::Foundation::Collections::IVectorView<Cortana::ConstraintIndex::Search::ISettingResultItem *> *>>::~shared_ptr<Concurrency::details::_Task_impl<Windows::Foundation::Collections::IVectorView<Cortana::ConstraintIndex::Search::ISettingResultItem *> *>>(void)
0x1800c0f8f  nop
0x1800c0f90  jmp     short loc_1800C0F97
0x1800c0f92  mov     rbx, [rsp+188h+var_148]
0x1800c0f97  mov     rcx, [rbx+18h]
0x1800c0f9b  mov     rcx, [rcx]; this
0x1800c0f9e  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x1800c0fa3  mov     rcx, [rsp+188h+var_30]
0x1800c0fab  xor     rcx, rsp; StackCookie
0x1800c0fae  call    __security_check_cookie
0x1800c0fb3  lea     r11, [rsp+188h+var_28]
0x1800c0fbb  mov     rbx, [r11+38h]
0x1800c0fbf  mov     rsi, [r11+40h]
0x1800c0fc3  mov     rsp, r11
0x1800c0fc6  pop     r15
0x1800c0fc8  pop     r14
0x1800c0fca  pop     r13
0x1800c0fcc  pop     r12
0x1800c0fce  pop     rdi
0x1800c0fcf  retn
0x1800c0fd0  call    ?_NoCallOnDefaultTask_ErrorImpl@_DefaultTaskHelper@details@Concurrency@@SAXXZ; Concurrency::details::_DefaultTaskHelper::_NoCallOnDefaultTask_ErrorImpl(void)
0x1800c0fd6  call    ?_NoCallOnDefaultTask_ErrorImpl@_DefaultTaskHelper@details@Concurrency@@SAXXZ; Concurrency::details::_DefaultTaskHelper::_NoCallOnDefaultTask_ErrorImpl(void)
0x1800c0fdc  call    ?_NoCallOnDefaultTask_ErrorImpl@_DefaultTaskHelper@details@Concurrency@@SAXXZ; Concurrency::details::_DefaultTaskHelper::_NoCallOnDefaultTask_ErrorImpl(void)
```
