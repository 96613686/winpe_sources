# _lambda_8d16998f3a7765ec946ee0f4259e66ba_::operator()

- ea: `0x1800cdcc0`
- end: `0x1800ce368`
- name: `_lambda_8d16998f3a7765ec946ee0f4259e66ba_::operator()`
- size: `1704`
- prototype: ``
- caller_count: `1`
- callee_count: `36`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800d0550`

## callees

- `0x1800049e0`
- `0x18000616e`
- `0x18000617a`
- `0x180006192`
- `0x18000619e`
- `0x18003fd04`
- `0x18003feb4`
- `0x18003fee0`
- `0x18003ff00`
- `0x18003ff8c`
- `0x18007e3d0`
- `0x18008192c`
- `0x1800819a8`
- `0x180081a5c`
- `0x180086d3c`
- `0x18008ca74`
- `0x180092490`
- `0x180092c54`
- `0x180092e54`
- `0x1800942dc`
- `0x1800999d0`
- `0x1800a9dcc`
- `0x1800cc084`
- `0x1800cc32c`
- `0x1800cc460`
- `0x1800cc700`
- `0x1800cc8d8`
- `0x1800cd050`
- `0x1800cd084`
- `0x1800cd418`
- `0x1800cdcc0`
- `0x1800ce69c`
- `0x1800ce8e0`
- `0x1800cfa0c`
- `0x1800d6dc0`
- `0x1800d6fe0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsPromoteStringBuffer` at `0x1800cdfb6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPromoteStringBuffer` at `0x1800cdfb6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x1800cdefc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x1800cdefc`

## string_xrefs

- `0x1800ce2df`: `shellcommon\shell\cortana\constraintindex\src\Search\SettingsJsonGenerator.cpp`
- `0x1800ce2ff`: `shellcommon\shell\cortana\constraintindex\src\Search\SettingsJsonGenerator.cpp`
- `0x1800ce317`: `shellcommon\shell\cortana\constraintindex\src\Search\SettingsJsonGenerator.cpp`
- `0x1800ce32c`: `shellcommon\shell\cortana\constraintindex\src\Search\SettingsJsonGenerator.cpp`
- `0x1800ce341`: `shellcommon\shell\cortana\constraintindex\src\Search\SettingsJsonGenerator.cpp`
- `0x1800ce356`: `shellcommon\shell\cortana\constraintindex\src\Search\SettingsJsonGenerator.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=34
__int64 __fastcall lambda_8d16998f3a7765ec946ee0f4259e66ba_::operator()(_QWORD *a1, __int64 a2)
{
  __int64 v2; // r14
  _QWORD *v3; // r12
  HRESULT v4; // eax
  Cortana::ConstraintIndex::Search *v5; // rcx
  HSTRING v6; // rcx
  HSTRING AllSettingsInJsonFormat; // rbx
  HSTRING v8; // rdi
  WCHAR *v9; // rbx
  HSTRING v10; // r15
  __int64 StringLen; // r14
  PCWSTR StringRawBuffer_0; // rax
  PCWSTR v13; // r13
  unsigned __int64 v14; // rdi
  __int64 traits_2_0_unsigned_short; // rax
  __int64 v16; // rdx
  __int64 v17; // rax
  __int64 v18; // rsi
  char v19; // al
  __int64 v20; // rbx
  const wchar_t *v21; // r12
  __int64 v22; // rax
  char v23; // al
  int v24; // ebx
  HRESULT v25; // eax
  unsigned __int64 v26; // rbx
  int v27; // eax
  int v28; // eax
  HRESULT v29; // eax
  __int64 v30; // rbx
  __int64 v31; // rcx
  __int64 v32; // r15
  HSTRING Object; // r13
  __int64 v34; // rdi
  __int64 v35; // rbx
  __int64 v36; // rdi
  __int64 v37; // rbx
  __int64 v38; // rdi
  __int64 v39; // rbx
  __int64 v40; // rdi
  __int64 v41; // rbx
  __int64 ModernSettingsInJsonFormat; // [rsp+28h] [rbp-D8h]
  __int64 FolderAsync; // [rsp+28h] [rbp-D8h]
  __int64 v47; // [rsp+40h] [rbp-C0h] BYREF
  char v48; // [rsp+48h] [rbp-B8h]
  __int64 v49; // [rsp+50h] [rbp-B0h] BYREF
  char v50; // [rsp+58h] [rbp-A8h]
  __int64 v51; // [rsp+60h] [rbp-A0h] BYREF
  char v52; // [rsp+68h] [rbp-98h]
  __int64 v53; // [rsp+70h] [rbp-90h] BYREF
  char v54; // [rsp+78h] [rbp-88h]
  HSTRING_HEADER hstringHeader; // [rsp+80h] [rbp-80h] BYREF
  __int64 v56; // [rsp+98h] [rbp-68h]
  _BYTE v57[16]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v58[16]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v59[8]; // [rsp+C0h] [rbp-40h] BYREF
  std::_Ref_count_base *v60; // [rsp+C8h] [rbp-38h]
  _BYTE v61[96]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v62[96]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v63[96]; // [rsp+190h] [rbp+90h] BYREF
  _BYTE v64[96]; // [rsp+1F0h] [rbp+F0h] BYREF
  _BYTE v65[96]; // [rsp+250h] [rbp+150h] BYREF
  __int64 v66; // [rsp+2B0h] [rbp+1B0h] BYREF
  _QWORD v67[43]; // [rsp+2B8h] [rbp+1B8h] BYREF
  __int64 v68; // [rsp+410h] [rbp+310h] BYREF
  _QWORD v69[43]; // [rsp+418h] [rbp+318h] BYREF
  _QWORD v70[44]; // [rsp+570h] [rbp+470h] BYREF
  _QWORD v71[42]; // [rsp+6D0h] [rbp+5D0h] BYREF
  HSTRING v72; // [rsp+820h] [rbp+720h] BYREF
  WCHAR *charBuffer; // [rsp+828h] [rbp+728h] BYREF
  HSTRING string; // [rsp+830h] [rbp+730h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+878h] [rbp+778h]

  v2 = a2;
  v3 = a1;
  v56 = a2;
  string = 0;
  v4 = WindowsCreateStringReference_0(&LocaleName, 0, &hstringHeader, &string);
  if ( v4 < 0 )
    __abi_WinRTraiseException(v4);
  v72 = (HSTRING)__abi_winrt_ptrto_string_ctor(string);
  if ( Cortana::ConstraintIndex::Search::IsCShellSettingsApp(v5) )
  {
    ModernSettingsInJsonFormat = Windows::Cortana::SearchFolders::GetModernSettingsInJsonFormat();
    __abi_winrt_ptrto_string_assign(&v72, ModernSettingsInJsonFormat);
    v6 = (HSTRING)ModernSettingsInJsonFormat;
    goto LABEL_25;
  }
  AllSettingsInJsonFormat = (HSTRING)Windows::Cortana::DesktopItem::GetAllSettingsInJsonFormat();
  string = AllSettingsInJsonFormat;
  __abi_winrt_ptrto_string_assign(&v72, AllSettingsInJsonFormat);
  WindowsDeleteString_0(AllSettingsInJsonFormat);
  v8 = (HSTRING)__abi_winrt_cast_to(
                  0,
                  *(_QWORD *)(*v3 + 48LL),
                  _uuidof__AUISettingsSearchDatabase2_DataModel_SystemSettings__);
  string = v8;
  v9 = (WCHAR *)WindowsUdk::System::Profile::ISystemSettingEntryPoint::Id::get(v8);
  charBuffer = v9;
  v10 = (HSTRING)__abi_winrt_ptrto_string_ctor(v9);
  WindowsDeleteString_0((HSTRING)v9);
  __abi_winrt_ptr_dtor(v8);
  if ( v10 )
  {
    StringLen = _Platform_WindowsGetStringLen(v10);
    StringRawBuffer_0 = WindowsGetStringRawBuffer_0(v10, 0);
    v13 = StringRawBuffer_0;
    v14 = -1;
    if ( !StringLen
      || (traits_2_0_unsigned_short = anonymous_namespace_::_Finding::_Find_impl__anonymous_namespace_::_Finding::_Find_traits_2_0_unsigned_short_(
                                        StringRawBuffer_0,
                                        &StringRawBuffer_0[StringLen],
                                        91),
          traits_2_0_unsigned_short == v16) )
    {
      v18 = 0;
    }
    else
    {
      v17 = (traits_2_0_unsigned_short - (__int64)v13) >> 1;
      v18 = v17 + 1;
      if ( v17 == -2 )
      {
        v19 = 1;
        goto LABEL_11;
      }
    }
    v19 = 0;
LABEL_11:
    if ( v19 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x48,
        (unsigned int)"shellcommon\\shell\\cortana\\constraintindex\\src\\Search\\SettingsJsonGenerator.cpp",
        (const char *)0x80070057LL,
        (int)v10);
    v20 = _Platform_WindowsGetStringLen(v72);
    v21 = WindowsGetStringRawBuffer_0(v72, 0);
    if ( v20 )
    {
      v22 = anonymous_namespace_::_Finding::_Find_last_impl__anonymous_namespace_::_Finding::_Find_traits_2_0_unsigned_short_(
              v21,
              &v21[v20]);
      if ( (const wchar_t *)v22 == &v21[v20] )
      {
        v14 = -1;
      }
      else
      {
        v14 = (v22 - (__int64)v21) >> 1;
        if ( v14 != -1 )
        {
          v23 = 0;
LABEL_18:
          if ( v23 )
            wil::details::in1diag3::_Throw_Hr(
              retaddr,
              (void *)0x4C,
              (unsigned int)"shellcommon\\shell\\cortana\\constraintindex\\src\\Search\\SettingsJsonGenerator.cpp",
              (const char *)0x80070057LL,
              (int)v10);
          v24 = StringLen + v14 - v18;
          charBuffer = 0;
          string = 0;
          v25 = WindowsPreallocateStringBuffer(v24 + 1, &charBuffer, (HSTRING_BUFFER *)&string);
          if ( v25 < 0 )
            wil::details::in1diag3::_Throw_Hr(
              retaddr,
              (void *)0x53,
              (unsigned int)"shellcommon\\shell\\cortana\\constraintindex\\src\\Search\\SettingsJsonGenerator.cpp",
              (const char *)(unsigned int)v25,
              (int)v10);
          hstringHeader.Reserved.Reserved1 = &charBuffer;
          *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = &string;
          hstringHeader.Reserved.Reserved2[16] = 1;
          v26 = (unsigned int)(v24 + 2);
          v27 = StringCchCopyNW(charBuffer, v26, v21, v14);
          if ( v27 < 0 )
            wil::details::in1diag3::_Throw_Hr(
              retaddr,
              (void *)0x60,
              (unsigned int)"shellcommon\\shell\\cortana\\constraintindex\\src\\Search\\SettingsJsonGenerator.cpp",
              (const char *)(unsigned int)v27,
              (int)v10);
          charBuffer[v14] = 44;
          v28 = StringCchCopyNW(&charBuffer[v14 + 1], v26 - (v14 + 1), &v13[v18], (unsigned int)(StringLen - v18));
          if ( v28 < 0 )
            wil::details::in1diag3::_Throw_Hr(
              retaddr,
              (void *)0x65,
              (unsigned int)"shellcommon\\shell\\cortana\\constraintindex\\src\\Search\\SettingsJsonGenerator.cpp",
              (const char *)(unsigned int)v28,
              (int)v10);
          __abi_winrt_ptrto_string_assign(&v72, 0);
          v29 = WindowsPromoteStringBuffer((HSTRING_BUFFER)string, &v72);
          if ( v29 < 0 )
            wil::details::in1diag3::_Throw_Hr(
              retaddr,
              (void *)0x68,
              (unsigned int)"shellcommon\\shell\\cortana\\constraintindex\\src\\Search\\SettingsJsonGenerator.cpp",
              (const char *)(unsigned int)v29,
              (int)v10);
          v2 = a2;
          v3 = a1;
          goto LABEL_24;
        }
      }
    }
    v23 = 1;
    goto LABEL_18;
  }
LABEL_24:
  v6 = v10;
LABEL_25:
  WindowsDeleteString_0(v6);
  v30 = Concurrency::task_options::task_options((Concurrency::task_options *)v61);
  v32 = Windows::Storage::ApplicationData::Current::get(v31);
  Object = (HSTRING)Windows::Data::Json::IJsonValue::GetObject(v32);
  string = Object;
  FolderAsync = Windows::Storage::IStorageFolder::CreateFolderAsync(Object, qword_18013EE28, 3);
  v34 = Concurrency::create_task<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFolder __gc *> __gc *>(
          &hstringHeader,
          FolderAsync,
          v30);
  v48 = 0;
  v47 = 0;
  v35 = Concurrency::task_options::task_options(v62, &v47);
  wil::ActivityBase<CortanaSearchTelemetryLogging,1,70368744177664,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CortanaSearchTelemetryLogging,1,70368744177664,4,0,_TlgReflectorTag_Param0IsProviderType>(
    v71,
    v3 + 1);
  v71[0] = &ConstraintIndexTelemetry::SettingsJsonGenerator_UpdateSettingsCacheOnDiskAsync::`vftable';
  v36 = Concurrency::task_Windows::Storage::StorageFolder___::then__lambda_80f771bdc2cad1641d2aace83692679e___(
          v34,
          v59,
          v71,
          v35,
          v61);
  v50 = 0;
  v49 = 0;
  v37 = Concurrency::task_options::task_options(v63, &v49);
  wil::ActivityBase<CortanaSearchTelemetryLogging,1,70368744177664,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CortanaSearchTelemetryLogging,1,70368744177664,4,0,_TlgReflectorTag_Param0IsProviderType>(
    v70,
    v3 + 1);
  v70[0] = &ConstraintIndexTelemetry::SettingsJsonGenerator_UpdateSettingsCacheOnDiskAsync::`vftable';
  v70[42] = __abi_winrt_ptrto_string_ctor(v72);
  v38 = Concurrency::task_Windows::Storage::StorageFile___::then__lambda_6fa97f730ee460c7c90d0ec3d6d68255___(
          v36,
          v58,
          v70,
          v37,
          v63);
  v52 = 0;
  v51 = 0;
  v39 = Concurrency::task_options::task_options(v64, &v51);
  v68 = __abi_winrt_ptr_ctor(*v3);
  wil::ActivityBase<CortanaSearchTelemetryLogging,1,70368744177664,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CortanaSearchTelemetryLogging,1,70368744177664,4,0,_TlgReflectorTag_Param0IsProviderType>(
    v69,
    v3 + 1);
  v69[0] = &ConstraintIndexTelemetry::SettingsJsonGenerator_UpdateSettingsCacheOnDiskAsync::`vftable';
  v69[42] = __abi_winrt_ptrto_string_ctor(v72);
  v40 = Concurrency::task_void_::then__lambda_721501eea695c4aea33978392a3615f5___(v38, v57, &v68, v39, v64);
  v54 = 0;
  v53 = 0;
  v41 = Concurrency::task_options::task_options(v65, &v53);
  v66 = __abi_winrt_ptr_ctor(*v3);
  wil::ActivityBase<CortanaSearchTelemetryLogging,1,70368744177664,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CortanaSearchTelemetryLogging,1,70368744177664,4,0,_TlgReflectorTag_Param0IsProviderType>(
    v67,
    v3 + 1);
  v67[0] = &ConstraintIndexTelemetry::SettingsJsonGenerator_UpdateSettingsCacheOnDiskAsync::`vftable';
  v67[42] = __abi_winrt_ptrto_string_ctor(v72);
  Concurrency::task_void_::then__lambda_29ac248f55211da4406ef09dc0edc4e5___(v40, v2, &v66, v41, v65);
  lambda_721501eea695c4aea33978392a3615f5_::__lambda_721501eea695c4aea33978392a3615f5_(&v66);
  std::shared_ptr<Concurrency::details::_Task_impl<Windows::Foundation::Collections::IVectorView<Cortana::ConstraintIndex::Search::ISettingResultItem __gc *> __gc *>>::~shared_ptr<Concurrency::details::_Task_impl<Windows::Foundation::Collections::IVectorView<Cortana::ConstraintIndex::Search::ISettingResultItem __gc *> __gc *>>(v57);
  lambda_721501eea695c4aea33978392a3615f5_::__lambda_721501eea695c4aea33978392a3615f5_(&v68);
  std::shared_ptr<Concurrency::details::_Task_impl<Windows::Foundation::Collections::IVectorView<Cortana::ConstraintIndex::Search::ISettingResultItem __gc *> __gc *>>::~shared_ptr<Concurrency::details::_Task_impl<Windows::Foundation::Collections::IVectorView<Cortana::ConstraintIndex::Search::ISettingResultItem __gc *> __gc *>>(v58);
  lambda_6fa97f730ee460c7c90d0ec3d6d68255_::__lambda_6fa97f730ee460c7c90d0ec3d6d68255_((ConstraintIndexTelemetry::SettingsJsonGenerator_UpdateSettingsCacheOnDiskAsync *)v70);
  if ( v60 )
    std::_Ref_count_base::_Decref(v60);
  ConstraintIndexTelemetry::SettingsJsonGenerator_UpdateSettingsCacheOnDiskAsync::~SettingsJsonGenerator_UpdateSettingsCacheOnDiskAsync((ConstraintIndexTelemetry::SettingsJsonGenerator_UpdateSettingsCacheOnDiskAsync *)v71);
  if ( *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] )
    std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&hstringHeader.Reserved.Reserved2[8]);
  __abi_winrt_ptr_dtor(FolderAsync);
  __abi_winrt_ptr_dtor(Object);
  __abi_winrt_ptr_dtor(v32);
  WindowsDeleteString_0(v72);
  return v2;
}

```

## disassembly

```asm
0x1800cdcc0  mov     [rsp-8+arg_10], rbx
0x1800cdcc5  push    rbp
0x1800cdcc6  push    rsi
0x1800cdcc7  push    rdi
0x1800cdcc8  push    r12
0x1800cdcca  push    r13
0x1800cdccc  push    r14
0x1800cdcce  push    r15
0x1800cdcd0  lea     rbp, [rsp-740h]
0x1800cdcd8  sub     rsp, 840h
0x1800cdcdf  mov     rax, cs:__security_cookie
0x1800cdce6  xor     rax, rsp
0x1800cdce9  mov     [rbp+770h+var_38], rax
0x1800cdcf0  mov     r14, rdx
0x1800cdcf3  mov     [rsp+870h+var_838], rdx
0x1800cdcf8  mov     r12, rcx
0x1800cdcfb  mov     [rsp+870h+var_848], rcx
0x1800cdd00  mov     [rbp+770h+var_7D8], rdx
0x1800cdd04  mov     [rsp+870h+var_840], 0
0x1800cdd0c  mov     [rbp+770h+string], 0
0x1800cdd17  lea     r9, [rbp+770h+string]; string
0x1800cdd1e  lea     r8, [rbp+770h+hstringHeader]; hstringHeader
0x1800cdd22  xor     edx, edx; length
0x1800cdd24  lea     rcx, LocaleName; sourceString
0x1800cdd2b  call    WindowsCreateStringReference_0
0x1800cdd30  test    eax, eax
0x1800cdd32  js      loc_1800CE2F1
0x1800cdd38  mov     rcx, [rbp+770h+string]
0x1800cdd3f  call    ?__abi_winrt_ptrto_string_ctor@@YAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_ctor(Platform::String const volatile *)
0x1800cdd44  mov     [rbp+770h+var_50], rax
0x1800cdd4b  call    ?IsCShellSettingsApp@Search@ConstraintIndex@Cortana@@YA_NXZ; Cortana::ConstraintIndex::Search::IsCShellSettingsApp(void)
0x1800cdd50  test    al, al
0x1800cdd52  jz      short loc_1800CDD79
0x1800cdd54  call    ?GetModernSettingsInJsonFormat@SearchFolders@Cortana@Windows@@SAPE$AAVString@Platform@@XZ; Windows::Cortana::SearchFolders::GetModernSettingsInJsonFormat(void)
0x1800cdd59  mov     rbx, rax
0x1800cdd5c  mov     [rsp+870h+var_848], rax
0x1800cdd61  mov     rdx, rax
0x1800cdd64  lea     rcx, [rbp+770h+var_50]
0x1800cdd6b  call    ?__abi_winrt_ptrto_string_assign@@YAPEAXPEAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_assign(void * *,Platform::String const volatile *)
0x1800cdd70  nop
0x1800cdd71  mov     rcx, rbx
0x1800cdd74  jmp     loc_1800CDFD8
0x1800cdd79  call    ?GetAllSettingsInJsonFormat@DesktopItem@Cortana@Windows@@SAPE$AAVString@Platform@@XZ; Windows::Cortana::DesktopItem::GetAllSettingsInJsonFormat(void)
0x1800cdd7e  mov     rbx, rax
0x1800cdd81  mov     [rbp+770h+string], rax
0x1800cdd88  mov     rdx, rax
0x1800cdd8b  lea     rcx, [rbp+770h+var_50]
0x1800cdd92  call    ?__abi_winrt_ptrto_string_assign@@YAPEAXPEAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_assign(void * *,Platform::String const volatile *)
0x1800cdd97  nop
0x1800cdd98  mov     rcx, rbx; string
0x1800cdd9b  call    WindowsDeleteString_0
0x1800cdda0  mov     rdx, [r12]
0x1800cdda4  lea     r8, __uuidof_?AUISettingsSearchDatabase2@DataModel@SystemSettings@@
0x1800cddab  mov     rdx, [rdx+30h]
0x1800cddaf  xor     ecx, ecx
0x1800cddb1  call    ?__abi_winrt_cast_to@@YAPE$AAVObject@Platform@@_NPE$AAV12@AEBU_GUID@@@Z; __abi_winrt_cast_to(bool,Platform::Object *,_GUID const &)
0x1800cddb6  mov     rdi, rax
0x1800cddb9  mov     [rbp+770h+string], rax
0x1800cddc0  mov     rcx, rax
0x1800cddc3  call    ?get@Id@ISystemSettingEntryPoint@Profile@System@WindowsUdk@@UE$AAAPE$AAVString@Platform@@XZ; WindowsUdk::System::Profile::ISystemSettingEntryPoint::Id::get(void)
0x1800cddc8  mov     rbx, rax
0x1800cddcb  mov     [rbp+770h+charBuffer], rax
0x1800cddd2  mov     rcx, rax
0x1800cddd5  call    ?__abi_winrt_ptrto_string_ctor@@YAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_ctor(Platform::String const volatile *)
0x1800cddda  mov     r15, rax
0x1800cdddd  mov     qword ptr [rsp+870h+var_850], rax; int
0x1800cdde2  mov     rcx, rbx; string
0x1800cdde5  call    WindowsDeleteString_0
0x1800cddea  nop
0x1800cddeb  mov     rcx, rdi
0x1800cddee  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800cddf3  nop
0x1800cddf4  test    r15, r15
0x1800cddf7  jz      loc_1800CDFD5
0x1800cddfd  mov     rcx, r15; string
0x1800cde00  call    __Platform_WindowsGetStringLen
0x1800cde05  mov     r14d, eax
0x1800cde08  xor     edx, edx; length
0x1800cde0a  mov     rcx, r15; string
0x1800cde0d  call    WindowsGetStringRawBuffer_0
0x1800cde12  mov     r13, rax
0x1800cde15  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800cde19  test    r14, r14
0x1800cde1c  jz      short loc_1800CDE4D
0x1800cde1e  lea     rdx, ds:0[r14*2]
0x1800cde26  add     rdx, rax
0x1800cde29  lea     r8d, [rdi+5Ch]
0x1800cde2d  mov     rcx, rax
0x1800cde30  call    _anonymous_namespace____Finding___Find_impl__anonymous_namespace____Finding___Find_traits_2_0_unsigned_short_
0x1800cde35  cmp     rax, rdx
0x1800cde38  jz      short loc_1800CDE4D
0x1800cde3a  sub     rax, r13
0x1800cde3d  sar     rax, 1
0x1800cde40  lea     rsi, [rax+1]
0x1800cde44  cmp     rsi, rdi
0x1800cde47  jnz     short loc_1800CDE4F
0x1800cde49  mov     al, 1
0x1800cde4b  jmp     short loc_1800CDE51
0x1800cde4d  xor     esi, esi
0x1800cde4f  xor     al, al
0x1800cde51  mov     rcx, [rbp+778h]; this
0x1800cde58  test    al, al
0x1800cde5a  jnz     loc_1800CE2F9
0x1800cde60  mov     rcx, [rbp+770h+var_50]; string
0x1800cde67  call    __Platform_WindowsGetStringLen
0x1800cde6c  mov     ebx, eax
0x1800cde6e  xor     edx, edx; length
0x1800cde70  mov     rcx, [rbp+770h+var_50]; string
0x1800cde77  call    WindowsGetStringRawBuffer_0
0x1800cde7c  mov     r12, rax
0x1800cde7f  test    rbx, rbx
0x1800cde82  jz      short loc_1800CDEBD
0x1800cde84  lea     rax, [rbx-1]
0x1800cde88  cmp     rax, rdi
0x1800cde8b  cmovnb  rax, rdi
0x1800cde8f  inc     rax
0x1800cde92  lea     rbx, [r12+rax*2]
0x1800cde96  mov     rdx, rbx
0x1800cde99  mov     rcx, r12
0x1800cde9c  call    _anonymous_namespace____Finding___Find_last_impl__anonymous_namespace____Finding___Find_traits_2_0_unsigned_short_
0x1800cdea1  mov     rdi, rax
0x1800cdea4  cmp     rax, rbx
0x1800cdea7  jz      short loc_1800CDEB9
0x1800cdea9  sub     rdi, r12
0x1800cdeac  sar     rdi, 1
0x1800cdeaf  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800cdeb3  jz      short loc_1800CDEBD
0x1800cdeb5  xor     al, al
0x1800cdeb7  jmp     short loc_1800CDEBF
0x1800cdeb9  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800cdebd  mov     al, 1
0x1800cdebf  mov     rcx, [rbp+778h]; this
0x1800cdec6  test    al, al
0x1800cdec8  jnz     loc_1800CE311
0x1800cdece  mov     ebx, edi
0x1800cded0  sub     ebx, esi
0x1800cded2  add     ebx, r14d
0x1800cded5  mov     [rbp+770h+charBuffer], 0
0x1800cdee0  mov     [rbp+770h+string], 0
0x1800cdeeb  lea     r8, [rbp+770h+string]; bufferHandle
0x1800cdef2  lea     rdx, [rbp+770h+charBuffer]; charBuffer
0x1800cdef9  lea     ecx, [rbx+1]; length
0x1800cdefc  call    cs:__imp_WindowsPreallocateStringBuffer
0x1800cdf02  mov     rcx, [rbp+778h]; this
0x1800cdf09  test    eax, eax
0x1800cdf0b  js      loc_1800CE329
0x1800cdf11  lea     rax, [rbp+770h+charBuffer]
0x1800cdf18  mov     qword ptr [rbp+770h+hstringHeader.Reserved], rax
0x1800cdf1c  lea     rax, [rbp+770h+string]
0x1800cdf23  mov     qword ptr [rbp+770h+hstringHeader.Reserved+8], rax
0x1800cdf27  mov     byte ptr [rbp+770h+hstringHeader.Reserved+10h], 1
0x1800cdf2b  lea     eax, [rbx+2]
0x1800cdf2e  mov     ebx, eax
0x1800cdf30  mov     r9, rdi; unsigned __int64
0x1800cdf33  mov     r8, r12; wchar_t *
0x1800cdf36  mov     edx, eax; unsigned __int64
0x1800cdf38  mov     rcx, [rbp+770h+charBuffer]; wchar_t *
0x1800cdf3f  call    ?StringCchCopyNW@@YAJPEA_W_KPEB_W1@Z; StringCchCopyNW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64)
0x1800cdf44  mov     rcx, [rbp+778h]; this
0x1800cdf4b  test    eax, eax
0x1800cdf4d  js      loc_1800CE33E
0x1800cdf53  mov     rax, [rbp+770h+charBuffer]
0x1800cdf5a  mov     word ptr [rax+rdi*2], 2Ch ; ','
0x1800cdf60  lea     rcx, [rdi+1]
0x1800cdf64  sub     r14d, esi
0x1800cdf67  mov     r9d, r14d; unsigned __int64
0x1800cdf6a  lea     r8, ds:0[rsi*2]
0x1800cdf72  add     r8, r13; wchar_t *
0x1800cdf75  sub     rbx, rcx
0x1800cdf78  mov     rax, [rbp+770h+charBuffer]
0x1800cdf7f  lea     rcx, [rax+rcx*2]; wchar_t *
0x1800cdf83  mov     rdx, rbx; unsigned __int64
0x1800cdf86  call    ?StringCchCopyNW@@YAJPEA_W_KPEB_W1@Z; StringCchCopyNW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64)
0x1800cdf8b  mov     rcx, [rbp+778h]; this
0x1800cdf92  test    eax, eax
0x1800cdf94  js      loc_1800CE353
0x1800cdf9a  xor     edx, edx
0x1800cdf9c  lea     rcx, [rbp+770h+var_50]
0x1800cdfa3  call    ?__abi_winrt_ptrto_string_assign@@YAPEAXPEAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_assign(void * *,Platform::String const volatile *)
0x1800cdfa8  lea     rdx, [rbp+770h+var_50]; string
0x1800cdfaf  mov     rcx, [rbp+770h+string]; bufferHandle
0x1800cdfb6  call    cs:__imp_WindowsPromoteStringBuffer
0x1800cdfbc  mov     rcx, [rbp+778h]; this
0x1800cdfc3  test    eax, eax
0x1800cdfc5  js      loc_1800CE2DC
0x1800cdfcb  mov     r14, [rsp+870h+var_838]
0x1800cdfd0  mov     r12, [rsp+870h+var_848]
0x1800cdfd5  mov     rcx, r15; string
0x1800cdfd8  call    WindowsDeleteString_0
0x1800cdfdd  lea     rax, [rbp+770h+var_7A0]
0x1800cdfe1  mov     qword ptr [rsp+870h+var_850], rax
0x1800cdfe6  lea     rcx, [rbp+770h+var_7A0]; this
0x1800cdfea  call    ??0task_options@Concurrency@@QEAA@XZ; Concurrency::task_options::task_options(void)
0x1800cdfef  mov     rbx, rax
0x1800cdff2  call    ?get@Current@ApplicationData@Storage@Windows@@SAPE$AAV234@XZ; Windows::Storage::ApplicationData::Current::get(void)
0x1800cdff7  mov     r15, rax
0x1800cdffa  mov     [rsp+870h+var_838], rax
0x1800cdfff  mov     rcx, rax
0x1800ce002  call    ?GetObject@IJsonValue@Json@Data@Windows@@UE$AAAPE$AAVJsonObject@234@XZ; Windows::Data::Json::IJsonValue::GetObject(void)
0x1800ce007  mov     r13, rax
0x1800ce00a  mov     [rbp+770h+string], rax
0x1800ce011  mov     r8d, 3
0x1800ce017  mov     rdx, cs:qword_18013EE28
0x1800ce01e  mov     rcx, rax
0x1800ce021  call    ?CreateFolderAsync@IStorageFolder@Storage@Windows@@UE$AAAPE$AAU?$IAsyncOperation@PE$AAVStorageFolder@Storage@Windows@@@Foundation@3@PE$AAVString@Platform@@W4CreationCollisionOption@23@@Z; Windows::Storage::IStorageFolder::CreateFolderAsync(Platform::String *,Windows::Storage::CreationCollisionOption)
0x1800ce026  mov     [rsp+870h+var_848], rax
0x1800ce02b  mov     r8, rbx
0x1800ce02e  mov     rdx, rax
0x1800ce031  lea     rcx, [rbp+770h+hstringHeader]
0x1800ce035  call    ??$create_task@PE$AAU?$IAsyncOperation@PE$AAVStorageFolder@Storage@Windows@@@Foundation@Windows@@@Concurrency@@YA?AV?$task@PE$AAVStorageFolder@Storage@Windows@@@0@PE$AAU?$IAsyncOperation@PE$AAVStorageFolder@Storage@Windows@@@Foundation@Windows@@Vtask_options@0@@Z; Concurrency::create_task<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFolder *> *>(Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFolder *> *,Concurrency::task_options)
0x1800ce03a  mov     rdi, rax
0x1800ce03d  mov     [rsp+870h+var_828], 0
0x1800ce042  mov     [rsp+870h+var_830], 0
0x1800ce04b  lea     rdx, [rsp+870h+var_830]
0x1800ce050  lea     rcx, [rbp+770h+var_740]
0x1800ce054  call    ??0task_options@Concurrency@@QEAA@Vtask_continuation_context@1@@Z; Concurrency::task_options::task_options(Concurrency::task_continuation_context)
0x1800ce059  mov     rbx, rax
0x1800ce05c  lea     rsi, [r12+8]
0x1800ce061  mov     rdx, rsi
0x1800ce064  lea     rcx, [rbp+770h+var_1A0]
0x1800ce06b  call    ??0?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$0EAAAAAAAAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@AEBV01@@Z; wil::ActivityBase<CortanaSearchTelemetryLogging,1,70368744177664,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CortanaSearchTelemetryLogging,1,70368744177664,4,0,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<CortanaSearchTelemetryLogging,1,70368744177664,4,0,_TlgReflectorTag_Param0IsProviderType> const &)
0x1800ce070  lea     rax, ??_7SettingsJsonGenerator_UpdateSettingsCacheOnDiskAsync@ConstraintIndexTelemetry@@6B@; const ConstraintIndexTelemetry::SettingsJsonGenerator_UpdateSettingsCacheOnDiskAsync::`vftable'
0x1800ce077  mov     [rbp+770h+var_1A0], rax
0x1800ce07e  mov     r9, rbx
0x1800ce081  lea     r8, [rbp+770h+var_1A0]
0x1800ce088  lea     rdx, [rbp+770h+var_7B0]
0x1800ce08c  mov     rcx, rdi
0x1800ce08f  call    Concurrency__task_Windows__Storage__StorageFolder_____then__lambda_80f771bdc2cad1641d2aace83692679e___
0x1800ce094  mov     rdi, rax
0x1800ce097  lea     rax, [rbp+770h+var_6E0]
0x1800ce09e  mov     qword ptr [rsp+870h+var_850], rax
0x1800ce0a3  mov     [rsp+870h+var_818], 0
0x1800ce0a8  mov     [rsp+870h+var_820], 0
0x1800ce0b1  lea     rdx, [rsp+870h+var_820]
0x1800ce0b6  lea     rcx, [rbp+770h+var_6E0]
0x1800ce0bd  call    ??0task_options@Concurrency@@QEAA@Vtask_continuation_context@1@@Z; Concurrency::task_options::task_options(Concurrency::task_continuation_context)
0x1800ce0c2  mov     rbx, rax
0x1800ce0c5  mov     rdx, rsi
0x1800ce0c8  lea     rcx, [rbp+770h+var_300]
0x1800ce0cf  call    ??0?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$0EAAAAAAAAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@AEBV01@@Z; wil::ActivityBase<CortanaSearchTelemetryLogging,1,70368744177664,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CortanaSearchTelemetryLogging,1,70368744177664,4,0,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<CortanaSearchTelemetryLogging,1,70368744177664,4,0,_TlgReflectorTag_Param0IsProviderType> const &)
0x1800ce0d4  lea     rax, ??_7SettingsJsonGenerator_UpdateSettingsCacheOnDiskAsync@ConstraintIndexTelemetry@@6B@; const ConstraintIndexTelemetry::SettingsJsonGenerator_UpdateSettingsCacheOnDiskAsync::`vftable'
0x1800ce0db  mov     [rbp+770h+var_300], rax
0x1800ce0e2  mov     rcx, [rbp+770h+var_50]
0x1800ce0e9  call    ?__abi_winrt_ptrto_string_ctor@@YAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_ctor(Platform::String const volatile *)
0x1800ce0ee  mov     [rbp+770h+var_1B0], rax
0x1800ce0f5  mov     r9, rbx
0x1800ce0f8  lea     r8, [rbp+770h+var_300]
0x1800ce0ff  lea     rdx, [rbp+770h+var_7C0]
0x1800ce103  mov     rcx, rdi
0x1800ce106  call    Concurrency__task_Windows__Storage__StorageFile_____then__lambda_6fa97f730ee460c7c90d0ec3d6d68255___
0x1800ce10b  mov     rdi, rax
0x1800ce10e  lea     rax, [rbp+770h+var_680]
0x1800ce115  mov     qword ptr [rsp+870h+var_850], rax
0x1800ce11a  mov     [rsp+870h+var_808], 0
0x1800ce11f  mov     [rsp+870h+var_810], 0
0x1800ce128  lea     rdx, [rsp+870h+var_810]
0x1800ce12d  lea     rcx, [rbp+770h+var_680]
0x1800ce134  call    ??0task_options@Concurrency@@QEAA@Vtask_continuation_context@1@@Z; Concurrency::task_options::task_options(Concurrency::task_continuation_context)
0x1800ce139  mov     rbx, rax
0x1800ce13c  mov     rcx, [r12]
0x1800ce140  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x1800ce145  mov     [rbp+770h+var_460], rax
0x1800ce14c  mov     rdx, rsi
0x1800ce14f  lea     rcx, [rbp+770h+var_458]
0x1800ce156  call    ??0?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$0EAAAAAAAAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@AEBV01@@Z; wil::ActivityBase<CortanaSearchTelemetryLogging,1,70368744177664,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CortanaSearchTelemetryLogging,1,70368744177664,4,0,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<CortanaSearchTelemetryLogging,1,70368744177664,4,0,_TlgReflectorTag_Param0IsProviderType> const &)
0x1800ce15b  lea     rax, ??_7SettingsJsonGenerator_UpdateSettingsCacheOnDiskAsync@ConstraintIndexTelemetry@@6B@; const ConstraintIndexTelemetry::SettingsJsonGenerator_UpdateSettingsCacheOnDiskAsync::`vftable'
0x1800ce162  mov     [rbp+770h+var_458], rax
0x1800ce169  mov     rcx, [rbp+770h+var_50]
0x1800ce170  call    ?__abi_winrt_ptrto_string_ctor@@YAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_ctor(Platform::String const volatile *)
0x1800ce175  mov     [rbp+770h+var_308], rax
0x1800ce17c  mov     r9, rbx
0x1800ce17f  lea     r8, [rbp+770h+var_460]
0x1800ce186  lea     rdx, [rbp+770h+var_7D0]
0x1800ce18a  mov     rcx, rdi
0x1800ce18d  call    Concurrency__task_void___then__lambda_721501eea695c4aea33978392a3615f5___
0x1800ce192  mov     rdi, rax
0x1800ce195  lea     rax, [rbp+770h+var_620]
0x1800ce19c  mov     qword ptr [rsp+870h+var_850], rax
0x1800ce1a1  mov     [rsp+870h+var_7F8], 0
0x1800ce1a6  mov     [rsp+870h+var_800], 0
0x1800ce1af  lea     rdx, [rsp+870h+var_800]
0x1800ce1b4  lea     rcx, [rbp+770h+var_620]
0x1800ce1bb  call    ??0task_options@Concurrency@@QEAA@Vtask_continuation_context@1@@Z; Concurrency::task_options::task_options(Concurrency::task_continuation_context)
0x1800ce1c0  mov     rbx, rax
0x1800ce1c3  mov     rcx, [r12]
0x1800ce1c7  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x1800ce1cc  mov     [rbp+770h+var_5C0], rax
0x1800ce1d3  mov     rdx, rsi
0x1800ce1d6  lea     rcx, [rbp+770h+var_5B8]
0x1800ce1dd  call    ??0?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$0EAAAAAAAAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@AEBV01@@Z; wil::ActivityBase<CortanaSearchTelemetryLogging,1,70368744177664,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CortanaSearchTelemetryLogging,1,70368744177664,4,0,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<CortanaSearchTelemetryLogging,1,70368744177664,4,0,_TlgReflectorTag_Param0IsProviderType> const &)
0x1800ce1e2  lea     rax, ??_7SettingsJsonGenerator_UpdateSettingsCacheOnDiskAsync@ConstraintIndexTelemetry@@6B@; const ConstraintIndexTelemetry::SettingsJsonGenerator_UpdateSettingsCacheOnDiskAsync::`vftable'
0x1800ce1e9  mov     [rbp+770h+var_5B8], rax
0x1800ce1f0  mov     rcx, [rbp+770h+var_50]
0x1800ce1f7  call    ?__abi_winrt_ptrto_string_ctor@@YAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_ctor(Platform::String const volatile *)
0x1800ce1fc  mov     [rbp+770h+var_468], rax
0x1800ce203  mov     r9, rbx
0x1800ce206  lea     r8, [rbp+770h+var_5C0]
0x1800ce20d  mov     rdx, r14
0x1800ce210  mov     rcx, rdi
0x1800ce213  call    Concurrency__task_void___then__lambda_29ac248f55211da4406ef09dc0edc4e5___
  ... truncated ...
```
