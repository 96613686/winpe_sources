# Mso::Auditing::Unified::AuditDataCacheManager::Store(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,_GUID const &,Mso::Auditing::Unified::AuditDataCacheManager::CacheOperationTelemetry const &)

- ea: `0x1804de304`
- end: `0x1804dea13`
- name: `?Store@AuditDataCacheManager@Unified@Auditing@Mso@@SA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0AEBU_GUID@@AEBUCacheOperationTelemetry@1234@@Z`
- size: `1807`
- prototype: `__int64 __fastcall(LPCVOID lpBuffer)`
- caller_count: `2`
- callee_count: `31`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1804de1f8`
- `0x1805ad834`

## callees

- `0x180036858`
- `0x180036984`
- `0x1800396d0`
- `0x18003a6d4`
- `0x18003b330`
- `0x180055eb0`
- `0x1800615e0`
- `0x180061c9c`
- `0x180061d0c`
- `0x180061edc`
- `0x180064f70`
- `0x1800651dc`
- `0x180086af4`
- `0x1800fff6c`
- `0x180143778`
- `0x180192520`
- `0x18019918c`
- `0x1801caea8`
- `0x18025b690`
- `0x1804de304`
- `0x180587a98`
- `0x180587bc0`
- `0x1805ce9c0`
- `0x180654ed4`
- `0x180654f38`
- `0x1806741e4`
- `0x18067bbdc`
- `0x180683758`
- `0x180685edc`
- `0x1807aabc4`
- `0x1807abf30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1804de5be`
- `KERNEL32!GetLastError` at `0x1804de66f`
- `KERNEL32!GetLastError` at `0x1804de7d3`
- `KERNEL32!GetLastError` at `0x1804de83b`
- `KERNEL32!GetLastError` at `0x1804de8d3`
- `KERNEL32!GetLastError` at `0x1804de5be`
- `KERNEL32!GetLastError` at `0x1804de66f`
- `KERNEL32!GetLastError` at `0x1804de7d3`
- `KERNEL32!GetLastError` at `0x1804de83b`
- `KERNEL32!GetLastError` at `0x1804de8d3`
- `KERNEL32!DeleteFileW` at `0x1804de8cd`
- `KERNEL32!DeleteFileW` at `0x1804de8cd`
- `KERNEL32!WriteFile` at `0x1804de665`
- `KERNEL32!WriteFile` at `0x1804de8b0`
- `KERNEL32!WriteFile` at `0x1804de665`
- `KERNEL32!WriteFile` at `0x1804de8b0`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x1804de95e`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x1804de9ec`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x1804de95e`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x1804de9ec`
- `Mso20Win32Client!__imp_?ToString@OGuid@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_GUID@@_N@Z` at `0x1804de430`
- `Mso20Win32Client!__imp_?ToString@OGuid@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_GUID@@_N@Z` at `0x1804de430`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1804de468`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1804de468`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1804de380`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1804de3aa`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1804de3cd`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1804de380`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1804de3aa`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1804de3cd`
- `Mso20Win32Client!__imp_?MsoFEnsureDirectory@@YAHPEB_W@Z` at `0x1804de7c9`
- `Mso20Win32Client!__imp_?MsoFEnsureDirectory@@YAHPEB_W@Z` at `0x1804de7c9`
- `Mso20Win32Client!__imp_??0Activity@Telemetry@Mso@@QEAA@AEBUEventName@12@AEBUEventFlags@12@$$QEAVEventExportability@12@@Z` at `0x1804de375`
- `Mso20Win32Client!__imp_??0Activity@Telemetry@Mso@@QEAA@AEBUEventName@12@AEBUEventFlags@12@$$QEAVEventExportability@12@@Z` at `0x1804de375`
- `Mso20Win32Client!__imp_?Combine@Path@Mso@@YA_NPEB_WW4Enum@PathType@2@0PEA_WH@Z` at `0x1804de783`
- `Mso20Win32Client!__imp_?Combine@Path@Mso@@YA_NPEB_WW4Enum@PathType@2@0PEA_WH@Z` at `0x1804de7b4`
- `Mso20Win32Client!__imp_?Combine@Path@Mso@@YA_NPEB_WW4Enum@PathType@2@0PEA_WH@Z` at `0x1804de783`
- `Mso20Win32Client!__imp_?Combine@Path@Mso@@YA_NPEB_WW4Enum@PathType@2@0PEA_WH@Z` at `0x1804de7b4`
- `Mso20Win32Client!__imp_MsoCreateFileW` at `0x1804de59b`
- `Mso20Win32Client!__imp_MsoCreateFileW` at `0x1804de823`
- `Mso20Win32Client!__imp_MsoCreateFileW` at `0x1804de59b`
- `Mso20Win32Client!__imp_MsoCreateFileW` at `0x1804de823`
- `Mso20Win32Client!__imp_?MsoFRegSetDw@@YAHPEBU_msoreg@@K@Z` at `0x1804de910`
- `Mso20Win32Client!__imp_?MsoFRegSetDw@@YAHPEBU_msoreg@@K@Z` at `0x1804de910`
- `Mso20Win32Client!__imp_?MsoFRegValueExists@@YA_NPEBU_msoreg@@@Z` at `0x1804de8fd`
- `Mso20Win32Client!__imp_?MsoFRegValueExists@@YA_NPEBU_msoreg@@@Z` at `0x1804de8fd`

## string_xrefs

- `0x1804de359`: `CacheAuditOperation`
- `0x1804de986`: `Cache or Records empty`
- `0x1804de5d0`: `FailedToCreateFileHandle`
- `0x1804de84d`: `FailedToCreateFileHandle`
- `0x1804de439`: `.json`
- `0x1804de6db`: `FailedToUpdateCache`
- `0x1804de7e8`: `FailedToUpdateCache`
- `0x1804de489`: `FailedToGetCachePath`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall Mso::Auditing::Unified::AuditDataCacheManager::Store(
        _QWORD *lpBuffer,
        _QWORD *a2,
        __int128 *a3,
        _BYTE *a4)
{
  __int128 *v5; // rsi
  _QWORD *v6; // rbx
  __int64 v8; // rax
  struct Mso::Telemetry::IDataFieldCollection *v9; // rax
  struct Mso::Telemetry::IDataFieldCollection *v10; // rax
  __int64 v11; // r8
  __int64 v12; // r8
  struct Mso::Telemetry::IDataFieldCollection *v13; // rax
  __int64 v14; // r8
  __int64 v15; // rax
  __int64 v16; // rax
  int v17; // edx
  bool v18; // al
  std::filesystem::path *v19; // rax
  std::filesystem *v20; // rax
  struct std::error_code *v21; // r8
  __int64 v22; // rdx
  __int128 *v23; // rcx
  void *v24; // rbx
  signed int v25; // eax
  const char *v26; // r8
  __int64 v27; // rdx
  DWORD *v28; // rax
  int v29; // r8d
  signed int v30; // eax
  unsigned int v31; // ebx
  struct std::error_code *v32; // r8
  int AuditCacheDirectory; // eax
  int v34; // edx
  int AuditCacheDirectoryForScenario; // esi
  _QWORD *v36; // r8
  signed int v37; // eax
  void *FileW; // rax
  signed int LastError; // eax
  const char *v40; // r8
  DWORD v41; // r8d
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v44[16]; // [rsp+48h] [rbp-B8h] BYREF
  void *v45; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v46; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v47[32]; // [rsp+68h] [rbp-98h] BYREF
  char v48; // [rsp+88h] [rbp-78h]
  __int128 v49; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int64 v50; // [rsp+A8h] [rbp-58h]
  _QWORD v51[4]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE Src[32]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v53[8]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v54[424]; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v55[32]; // [rsp+2A0h] [rbp+1A0h] BYREF
  WCHAR FileName[264]; // [rsp+2C0h] [rbp+1C0h] BYREF

  v5 = a3;
  v6 = a2;
  LOBYTE(NumberOfBytesWritten) = 0;
  LOBYTE(a3) = 110;
  v8 = Mso::Telemetry::EventFlags::EventFlags(&v46, a2, a3);
  *(_QWORD *)&v49 = &off_180C78DD0;
  *((_QWORD *)&v49 + 1) = "CacheAuditOperation";
  Mso::Telemetry::Activity::Activity(v44, &v49, v8, &NumberOfBytesWritten);
  v9 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v44);
  v49 = *v5;
  Mso::Telemetry::IDataFieldCollection::Add<_GUID>(v9, "RecordId", &v49, 4);
  v10 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v44);
  LOBYTE(v11) = *a4;
  Mso::Telemetry::IDataFieldCollection::Add<unsigned char>(v10, "SendMode", v11);
  if ( a4[2] )
  {
    v13 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v44);
    if ( !a4[2] )
      std::_Throw_bad_optional_access();
    LOBYTE(v14) = a4[1];
    Mso::Telemetry::IDataFieldCollection::Add<unsigned char>(v13, "Operation", v14);
  }
  if ( !lpBuffer[2] || !v6[2] )
    goto LABEL_70;
  v15 = *(_QWORD *)v5 - *(_QWORD *)&GUID_NULL.Data1;
  if ( *(_QWORD *)v5 == *(_QWORD *)&GUID_NULL.Data1 )
    v15 = *((_QWORD *)v5 + 1) - *(_QWORD *)GUID_NULL.Data4;
  if ( !v15 )
  {
LABEL_70:
    BYTE1(NumberOfBytesWritten) = 0;
    BYTE4(v46) = 0;
    std::string::string(v47, "Cache or Records empty");
    v48 = 1;
    Office::System::Result::Result(
      (unsigned int)v53,
      1,
      (unsigned int)v47,
      (unsigned int)&v46,
      (__int64)&NumberOfBytesWritten);
    if ( v48 )
      Microsoft::Authentication::BrowserNativeResult::~BrowserNativeResult((Microsoft::Authentication::BrowserNativeResult *)v47);
    Mso::Telemetry::Activity::SetResult((Mso::Telemetry::Activity *)v44, 0, (const struct Office::System::Result *)v53);
    Office::System::Result::Fields::~Fields((Office::System::Result::Fields *)v54);
    goto LABEL_73;
  }
  LOBYTE(v12) = 1;
  v16 = OGuid::ToString(Src, v5, v12);
  std::operator+<wchar_t>(v51, v16, L".json");
  Mso::Collections::KeyValue<std::wstring const,_msoreg const>::~KeyValue<std::wstring const,_msoreg const>(Src);
  if ( byte_180F8E760[0] < 0 )
    v18 = Mso::AB::Optimized::ChangeGate::Evaluate((Mso::AB::Optimized::ChangeGate *)byte_180F8E760);
  else
    v18 = byte_180F8E760[0] != 0;
  if ( !v18 )
  {
    AuditCacheDirectory = Mso::Auditing::Unified::AuditDataCacheManager::GetAuditCacheDirectory(FileName, v17, 1);
    if ( AuditCacheDirectory >= 0 )
    {
      AuditCacheDirectoryForScenario = Mso::Auditing::Unified::AuditDataCacheManager::GetAuditCacheDirectoryForScenario(FileName);
      if ( AuditCacheDirectoryForScenario >= 0 )
      {
        if ( v6[3] > 7u )
          v6 = (_QWORD *)*v6;
        if ( (unsigned __int8)Mso::Path::Combine(FileName, 0, v6, FileName, 261) )
        {
          v36 = v51;
          if ( v51[3] > 7u )
            v36 = (_QWORD *)v51[0];
          if ( (unsigned __int8)Mso::Path::Combine(FileName, 0, v36, FileName, 261) )
          {
            if ( MsoFEnsureDirectory(FileName) )
            {
              FileW = (void *)MsoCreateFileW(FileName, 0x40000000, 0, 0, 2, 0, 0);
              v45 = FileW;
              if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
              {
                NumberOfBytesWritten = 0;
                v41 = 2 * *((_DWORD *)lpBuffer + 4);
                if ( lpBuffer[3] > 7u )
                  lpBuffer = (_QWORD *)*lpBuffer;
                if ( WriteFile(FileW, lpBuffer, v41, &NumberOfBytesWritten, 0) )
                {
                  std::unique_ptr<void *,Mso::Win::HandleDeleter>::~unique_ptr<void *,Mso::Win::HandleDeleter>(&v45);
                  goto LABEL_66;
                }
                std::unique_ptr<void *,Mso::Win::HandleDeleter>::reset(&v45, 0);
                DeleteFileW(FileName);
                LastError = GetLastError();
                if ( LastError > 0 )
                  LastError = (unsigned __int16)LastError | 0x80070000;
                v40 = "FailedToStoreRecord";
              }
              else
              {
                LastError = GetLastError();
                if ( LastError > 0 )
                  LastError = (unsigned __int16)LastError | 0x80070000;
                v40 = "FailedToCreateFileHandle";
              }
              Mso::Telemetry::CreateResult(v53, (unsigned int)LastError, v40, 0);
              Mso::Telemetry::Activity::SetResult(
                (Mso::Telemetry::Activity *)v44,
                0,
                (const struct Office::System::Result *)v53);
              Office::System::Result::Fields::~Fields((Office::System::Result::Fields *)v54);
              std::unique_ptr<void *,Mso::Win::HandleDeleter>::~unique_ptr<void *,Mso::Win::HandleDeleter>(&v45);
              goto LABEL_17;
            }
            v37 = GetLastError();
            if ( v37 > 0 )
              v37 = (unsigned __int16)v37 | 0x80070000;
            Mso::Telemetry::CreateResult(v53, (unsigned int)v37, "FailedToUpdateCache", 0);
LABEL_42:
            Mso::Telemetry::Activity::SetResult(
              (Mso::Telemetry::Activity *)v44,
              0,
              (const struct Office::System::Result *)v53);
            Office::System::Result::Fields::~Fields((Office::System::Result::Fields *)v54);
            goto LABEL_17;
          }
        }
      }
      v34 = AuditCacheDirectoryForScenario;
    }
    else
    {
      v34 = AuditCacheDirectory;
    }
    Office::System::Result::Result((Office::System::Result *)v53, v34);
    goto LABEL_42;
  }
  Mso::Auditing::Unified::AuditDataCacheManager::TryGetAuditCacheDirectoryForScenario(v47);
  if ( !v48 )
  {
    Mso::Telemetry::CreateResult(v53, 2147500037LL, "FailedToGetCachePath", 0);
    Mso::Telemetry::Activity::SetResult((Mso::Telemetry::Activity *)v44, 0, (const struct Office::System::Result *)v53);
    Office::System::Result::Fields::~Fields((Office::System::Result::Fields *)v54);
LABEL_16:
    std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(v47);
LABEL_17:
    Mso::Collections::KeyValue<std::wstring const,_msoreg const>::~KeyValue<std::wstring const,_msoreg const>(v51);
LABEL_73:
    Mso::Telemetry::Activity::~Activity((Mso::Telemetry::Activity *)v44);
    return 0;
  }
  std::filesystem::path::path(&v49, v6);
  std::_Optional_construct_base<std::wstring>::operator*(v47);
  std::filesystem::operator/(Src);
  Mso::Collections::KeyValue<std::wstring const,_msoreg const>::~KeyValue<std::wstring const,_msoreg const>(&v49);
  v19 = (std::filesystem::path *)std::filesystem::path::path(&v49, v51);
  std::filesystem::path::operator/=(Src, v19);
  Mso::Collections::KeyValue<std::wstring const,_msoreg const>::~KeyValue<std::wstring const,_msoreg const>(&v49);
  LODWORD(v49) = 0;
  *((_QWORD *)&v49 + 1) = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
  v20 = (std::filesystem *)std::filesystem::path::parent_path(Src, v55);
  std::filesystem::create_directories(v20, (const struct std::filesystem::path *)&v49, v21);
  Mso::Collections::KeyValue<std::wstring const,_msoreg const>::~KeyValue<std::wstring const,_msoreg const>(v55);
  v22 = (unsigned int)v49;
  if ( (_DWORD)v49 )
  {
    if ( (int)v49 > 0 )
      v22 = (unsigned __int16)v49 | 0x80070000;
    Mso::Telemetry::CreateResult(v53, v22, "FailedToUpdateCache", 0);
    Mso::Telemetry::Activity::SetResult((Mso::Telemetry::Activity *)v44, 0, (const struct Office::System::Result *)v53);
    Office::System::Result::Fields::~Fields((Office::System::Result::Fields *)v54);
    goto LABEL_26;
  }
  std::wstring::wstring(&v49, Src);
  v23 = &v49;
  if ( v50 > 7 )
    v23 = (__int128 *)v49;
  v24 = (void *)MsoCreateFileW(v23, 0x40000000, 0, 0, 2, 0, 0);
  v45 = v24;
  Mso::Collections::KeyValue<std::wstring const,_msoreg const>::~KeyValue<std::wstring const,_msoreg const>(&v49);
  if ( (((unsigned __int64)v24 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v25 = GetLastError();
    if ( v25 > 0 )
      v25 = (unsigned __int16)v25 | 0x80070000;
    v26 = "FailedToCreateFileHandle";
    v27 = (unsigned int)v25;
LABEL_25:
    Mso::Telemetry::CreateResult(v53, v27, v26, 0);
    Mso::Telemetry::Activity::SetResult((Mso::Telemetry::Activity *)v44, 0, (const struct Office::System::Result *)v53);
    Office::System::Result::Fields::~Fields((Office::System::Result::Fields *)v54);
    std::unique_ptr<void *,Mso::Win::HandleDeleter>::~unique_ptr<void *,Mso::Win::HandleDeleter>(&v45);
LABEL_26:
    Mso::Collections::KeyValue<std::wstring const,_msoreg const>::~KeyValue<std::wstring const,_msoreg const>(Src);
    goto LABEL_16;
  }
  NumberOfBytesWritten = 0;
  v46 = lpBuffer[2];
  v28 = (DWORD *)SafeInt<unsigned __int64,safeint_exception_handlers::SafeInt_InvalidParameter>::operator*<unsigned __int64>(
                   &v46,
                   &v49,
                   2);
  if ( *(_QWORD *)v28 > 0xFFFFFFFF )
    __fastfail(v29 + 3);
  if ( lpBuffer[3] > 7u )
    lpBuffer = (_QWORD *)*lpBuffer;
  if ( !WriteFile(v24, lpBuffer, *v28, &NumberOfBytesWritten, 0) )
  {
    v30 = GetLastError();
    v31 = v30;
    if ( v30 > 0 )
      v31 = (unsigned __int16)v30 | 0x80070000;
    std::unique_ptr<void *,Mso::Win::HandleDeleter>::reset(&v45, 0);
    std::filesystem::remove((std::filesystem *)Src, (const struct std::filesystem::path *)&v49, v32);
    v26 = "FailedToStoreRecord";
    v27 = v31;
    goto LABEL_25;
  }
  std::unique_ptr<void *,Mso::Win::HandleDeleter>::~unique_ptr<void *,Mso::Win::HandleDeleter>(&v45);
  Mso::Collections::KeyValue<std::wstring const,_msoreg const>::~KeyValue<std::wstring const,_msoreg const>(Src);
  std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(v47);
LABEL_66:
  if ( !MsoFRegValueExists((const struct _msoreg *)&vmsoridAuditingUnifiedLastProcessTime) )
  {
    MsoFRegSetDw((const struct _msoreg *)&vmsoridAuditingUnifiedLastProcessTime, 0);
    Mso::Auditing::Unified::UnifiedAuditLiblet::StartProcessing((Mso::Auditing::Unified::UnifiedAuditLiblet *)&Mso::Auditing::Unified::vUnifiedAuditLiblet);
  }
  Mso::Telemetry::CreateResult(v53, 0, "Success", 0);
  Mso::Telemetry::Activity::SetResult((Mso::Telemetry::Activity *)v44, 1, (const struct Office::System::Result *)v53);
  Office::System::Result::Fields::~Fields((Office::System::Result::Fields *)v54);
  Mso::Collections::KeyValue<std::wstring const,_msoreg const>::~KeyValue<std::wstring const,_msoreg const>(v51);
  Mso::Telemetry::Activity::~Activity((Mso::Telemetry::Activity *)v44);
  return 1;
}

```

## disassembly

```asm
0x1804de304  push    rbp
0x1804de306  push    rbx
0x1804de307  push    rsi
0x1804de308  push    rdi
0x1804de309  push    r14
0x1804de30b  push    r15
0x1804de30d  lea     rbp, [rsp-3E8h]
0x1804de315  sub     rsp, 4E8h
0x1804de31c  mov     rax, cs:__security_cookie
0x1804de323  xor     rax, rsp
0x1804de326  mov     [rbp+410h+var_40], rax
0x1804de32d  mov     r14, r9
0x1804de330  mov     rsi, r8
0x1804de333  mov     rbx, rdx
0x1804de336  mov     rdi, rcx
0x1804de339  xor     r15d, r15d
0x1804de33c  mov     byte ptr [rsp+510h+NumberOfBytesWritten], r15b
0x1804de341  mov     r8b, 6Eh ; 'n'
0x1804de344  lea     rcx, [rsp+510h+var_4B0]
0x1804de349  call    ??0EventFlags@Telemetry@Mso@@QEAA@W4DataCategories@12@W4DiagnosticLevel@12@@Z; Mso::Telemetry::EventFlags::EventFlags(Mso::Telemetry::DataCategories,Mso::Telemetry::DiagnosticLevel)
0x1804de34e  lea     rcx, off_180C78DD0
0x1804de355  mov     qword ptr [rbp+410h+var_480], rcx
0x1804de359  lea     rcx, aCacheauditoper; "CacheAuditOperation"
0x1804de360  mov     qword ptr [rbp+410h+var_480+8], rcx
0x1804de364  lea     r9, [rsp+510h+NumberOfBytesWritten]
0x1804de369  mov     r8, rax
0x1804de36c  lea     rdx, [rbp+410h+var_480]
0x1804de370  lea     rcx, [rsp+510h+var_4C8]
0x1804de375  call    cs:__imp_??0Activity@Telemetry@Mso@@QEAA@AEBUEventName@12@AEBUEventFlags@12@$$QEAVEventExportability@12@@Z; Mso::Telemetry::Activity::Activity(Mso::Telemetry::EventName const &,Mso::Telemetry::EventFlags const &,Mso::Telemetry::EventExportability &&)
0x1804de37b  lea     rcx, [rsp+510h+var_4C8]
0x1804de380  call    cs:__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ; Mso::Telemetry::Activity::DataFields(void)
0x1804de386  movups  xmm0, xmmword ptr [rsi]
0x1804de389  movdqu  [rbp+410h+var_480], xmm0
0x1804de38e  lea     r9d, [r15+4]
0x1804de392  lea     r8, [rbp+410h+var_480]
0x1804de396  lea     rdx, aRecordid; "RecordId"
0x1804de39d  mov     rcx, rax
0x1804de3a0  call    ??$Add@U_GUID@@@IDataFieldCollection@Telemetry@Mso@@QEAAXPEBDU_GUID@@W4DataClassifications@Logging@2@@Z; Mso::Telemetry::IDataFieldCollection::Add<_GUID>(char const *,_GUID,Mso::Logging::DataClassifications)
0x1804de3a5  lea     rcx, [rsp+510h+var_4C8]
0x1804de3aa  call    cs:__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ; Mso::Telemetry::Activity::DataFields(void)
0x1804de3b0  mov     r8b, [r14]
0x1804de3b3  lea     rdx, aSendmode; "SendMode"
0x1804de3ba  mov     rcx, rax
0x1804de3bd  call    ??$Add@E@IDataFieldCollection@Telemetry@Mso@@QEAAXPEBDEW4DataClassifications@Logging@2@@Z; Mso::Telemetry::IDataFieldCollection::Add<uchar>(char const *,uchar,Mso::Logging::DataClassifications)
0x1804de3c2  cmp     [r14+2], r15b
0x1804de3c6  jz      short loc_1804DE3F2
0x1804de3c8  lea     rcx, [rsp+510h+var_4C8]
0x1804de3cd  call    cs:__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ; Mso::Telemetry::Activity::DataFields(void)
0x1804de3d3  cmp     [r14+2], r15b
0x1804de3d7  jnz     short loc_1804DE3DF
0x1804de3d9  call    ?_Throw_bad_optional_access@std@@YAXXZ; std::_Throw_bad_optional_access(void)
0x1804de3df  mov     r8b, [r14+1]
0x1804de3e3  lea     rdx, aOperation; "Operation"
0x1804de3ea  mov     rcx, rax
0x1804de3ed  call    ??$Add@E@IDataFieldCollection@Telemetry@Mso@@QEAAXPEBDEW4DataClassifications@Logging@2@@Z; Mso::Telemetry::IDataFieldCollection::Add<uchar>(char const *,uchar,Mso::Logging::DataClassifications)
0x1804de3f2  cmp     [rdi+10h], r15
0x1804de3f6  jz      loc_1804DE972
0x1804de3fc  cmp     [rbx+10h], r15
0x1804de400  jz      loc_1804DE972
0x1804de406  mov     rax, [rsi]
0x1804de409  sub     rax, qword ptr cs:GUID_NULL.Data1
0x1804de410  jnz     short loc_1804DE41D
0x1804de412  mov     rax, [rsi+8]
0x1804de416  sub     rax, qword ptr cs:GUID_NULL.Data4
0x1804de41d  test    rax, rax
0x1804de420  jz      loc_1804DE972
0x1804de426  mov     r8b, 1
0x1804de429  mov     rdx, rsi
0x1804de42c  lea     rcx, [rbp+410h+Src]
0x1804de430  call    cs:__imp_?ToString@OGuid@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_GUID@@_N@Z; OGuid::ToString(_GUID const &,bool)
0x1804de436  mov     rdx, rax
0x1804de439  lea     r8, aJson_2; ".json"
0x1804de440  lea     rcx, [rbp+410h+var_460]
0x1804de444  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x1804de449  lea     rcx, [rbp+410h+Src]; void *
0x1804de44d  call    ??1?$KeyValue@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$CBU_msoreg@@@Collections@Mso@@QEAA@XZ; Mso::Collections::KeyValue<std::wstring const,_msoreg const>::~KeyValue<std::wstring const,_msoreg const>(void)
0x1804de452  mov     al, cs:byte_180F8E760
0x1804de458  test    al, al
0x1804de45a  js      short loc_1804DE461
0x1804de45c  setnz   al
0x1804de45f  jmp     short loc_1804DE46E
0x1804de461  lea     rcx, byte_180F8E760
0x1804de468  call    cs:__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ; Mso::AB::Optimized::ChangeGate::Evaluate(void)
0x1804de46e  test    al, al
0x1804de470  jz      loc_1804DE709
0x1804de476  lea     rcx, [rsp+510h+var_4A8]
0x1804de47b  call    ?TryGetAuditCacheDirectoryForScenario@AuditDataCacheManager@Unified@Auditing@Mso@@CA?AV?$optional@Vpath@filesystem@std@@@std@@W4Scenario@234@@Z; Mso::Auditing::Unified::AuditDataCacheManager::TryGetAuditCacheDirectoryForScenario(Mso::Auditing::Unified::Scenario)
0x1804de480  cmp     [rbp+410h+var_488], r15b
0x1804de484  jnz     short loc_1804DE4CF
0x1804de486  xor     r9d, r9d
0x1804de489  lea     r8, aFailedtogetcac_0; "FailedToGetCachePath"
0x1804de490  mov     edx, 80004005h
0x1804de495  lea     rcx, [rbp+410h+var_420]
0x1804de499  call    ?CreateResult@Telemetry@Mso@@YA?AVResult@System@Office@@HPEBDI@Z; Mso::Telemetry::CreateResult(int,char const *,uint)
0x1804de49e  lea     r8, [rbp+410h+var_420]; struct Office::System::Result *
0x1804de4a2  xor     edx, edx; bool
0x1804de4a4  lea     rcx, [rsp+510h+var_4C8]; this
0x1804de4a9  call    ?SetResult@Activity@Telemetry@Mso@@QEAAX_NAEBVResult@System@Office@@@Z; Mso::Telemetry::Activity::SetResult(bool,Office::System::Result const &)
0x1804de4ae  lea     rcx, [rbp+410h+var_418]; this
0x1804de4b2  call    ??1Fields@Result@System@Office@@QEAA@XZ; Office::System::Result::Fields::~Fields(void)
0x1804de4b7  lea     rcx, [rsp+510h+var_4A8]
0x1804de4bc  call    ??1?$_Optional_destruct_base@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(void)
0x1804de4c1  lea     rcx, [rbp+410h+var_460]; void *
0x1804de4c5  call    ??1?$KeyValue@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$CBU_msoreg@@@Collections@Mso@@QEAA@XZ; Mso::Collections::KeyValue<std::wstring const,_msoreg const>::~KeyValue<std::wstring const,_msoreg const>(void)
0x1804de4ca  jmp     loc_1804DE9E7
0x1804de4cf  mov     rdx, rbx
0x1804de4d2  lea     rcx, [rbp+410h+var_480]
0x1804de4d6  call    ??$?0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$0A@@path@filesystem@std@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@W4format@012@@Z; std::filesystem::path::path(std::wstring const &,std::filesystem::path::format)
0x1804de4db  lea     rcx, [rsp+510h+var_4A8]
0x1804de4e0  call    ??D?$_Optional_construct_base@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEGBAAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@XZ; std::_Optional_construct_base<std::wstring>::operator*(void)
0x1804de4e5  mov     rdx, rax
0x1804de4e8  lea     r8, [rbp+410h+var_480]
0x1804de4ec  lea     rcx, [rbp+410h+Src]; Src
0x1804de4f0  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x1804de4f5  lea     rcx, [rbp+410h+var_480]; void *
0x1804de4f9  call    ??1?$KeyValue@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$CBU_msoreg@@@Collections@Mso@@QEAA@XZ; Mso::Collections::KeyValue<std::wstring const,_msoreg const>::~KeyValue<std::wstring const,_msoreg const>(void)
0x1804de4fe  lea     rdx, [rbp+410h+var_460]
0x1804de502  lea     rcx, [rbp+410h+var_480]
0x1804de506  call    ??$?0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$0A@@path@filesystem@std@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@W4format@012@@Z; std::filesystem::path::path(std::wstring const &,std::filesystem::path::format)
0x1804de50b  mov     rdx, rax; this
0x1804de50e  lea     rcx, [rbp+410h+Src]; Src
0x1804de512  call    ??_0path@filesystem@std@@QEAAAEAV012@AEBV012@@Z; std::filesystem::path::operator/=(std::filesystem::path const &)
0x1804de517  lea     rcx, [rbp+410h+var_480]; void *
0x1804de51b  call    ??1?$KeyValue@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$CBU_msoreg@@@Collections@Mso@@QEAA@XZ; Mso::Collections::KeyValue<std::wstring const,_msoreg const>::~KeyValue<std::wstring const,_msoreg const>(void)
0x1804de520  mov     dword ptr [rbp+410h+var_480], r15d
0x1804de524  lea     rax, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4V21@B; std::_System_error_category const `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x1804de52b  mov     qword ptr [rbp+410h+var_480+8], rax
0x1804de52f  lea     rdx, [rbp+410h+var_270]
0x1804de536  lea     rcx, [rbp+410h+Src]
0x1804de53a  call    ?parent_path@path@filesystem@std@@QEBA?AV123@XZ; std::filesystem::path::parent_path(void)
0x1804de53f  mov     rcx, rax; this
0x1804de542  lea     rdx, [rbp+410h+var_480]; struct std::filesystem::path *
0x1804de546  call    ?create_directories@filesystem@std@@YA_NAEBVpath@12@AEAVerror_code@2@@Z; std::filesystem::create_directories(std::filesystem::path const &,std::error_code &)
0x1804de54b  lea     rcx, [rbp+410h+var_270]; void *
0x1804de552  call    ??1?$KeyValue@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$CBU_msoreg@@@Collections@Mso@@QEAA@XZ; Mso::Collections::KeyValue<std::wstring const,_msoreg const>::~KeyValue<std::wstring const,_msoreg const>(void)
0x1804de557  mov     edx, dword ptr [rbp+410h+var_480]
0x1804de55a  test    edx, edx
0x1804de55c  jnz     loc_1804DE6CD
0x1804de562  lea     rdx, [rbp+410h+Src]
0x1804de566  lea     rcx, [rbp+410h+var_480]
0x1804de56a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1804de56f  nop
0x1804de570  lea     rcx, [rbp+410h+var_480]
0x1804de574  cmp     [rbp+410h+var_468], 7
0x1804de579  cmova   rcx, qword ptr [rbp+410h+var_480]
0x1804de57e  mov     [rsp+510h+var_4E0], r15
0x1804de583  mov     [rsp+510h+var_4E8], r15d
0x1804de588  mov     dword ptr [rsp+510h+lpOverlapped], 2
0x1804de590  xor     r9d, r9d
0x1804de593  xor     r8d, r8d
0x1804de596  mov     edx, 40000000h
0x1804de59b  call    cs:__imp_MsoCreateFileW
0x1804de5a1  mov     rbx, rax
0x1804de5a4  mov     [rsp+510h+var_4B8], rax
0x1804de5a9  lea     rcx, [rbp+410h+var_480]; void *
0x1804de5ad  call    ??1?$KeyValue@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$CBU_msoreg@@@Collections@Mso@@QEAA@XZ; Mso::Collections::KeyValue<std::wstring const,_msoreg const>::~KeyValue<std::wstring const,_msoreg const>(void)
0x1804de5b2  lea     rax, [rbx+1]
0x1804de5b6  test    rax, 0FFFFFFFFFFFFFFFEh
0x1804de5bc  jnz     short loc_1804DE616
0x1804de5be  call    cs:__imp_GetLastError
0x1804de5c4  test    eax, eax
0x1804de5c6  jle     short loc_1804DE5D0
0x1804de5c8  movzx   eax, ax
0x1804de5cb  or      eax, 80070000h
0x1804de5d0  lea     r8, aFailedtocreate_0; "FailedToCreateFileHandle"
0x1804de5d7  mov     edx, eax
0x1804de5d9  xor     r9d, r9d
0x1804de5dc  lea     rcx, [rbp+410h+var_420]
0x1804de5e0  call    ?CreateResult@Telemetry@Mso@@YA?AVResult@System@Office@@HPEBDI@Z; Mso::Telemetry::CreateResult(int,char const *,uint)
0x1804de5e5  lea     r8, [rbp+410h+var_420]; struct Office::System::Result *
0x1804de5e9  xor     edx, edx; bool
0x1804de5eb  lea     rcx, [rsp+510h+var_4C8]; this
0x1804de5f0  call    ?SetResult@Activity@Telemetry@Mso@@QEAAX_NAEBVResult@System@Office@@@Z; Mso::Telemetry::Activity::SetResult(bool,Office::System::Result const &)
0x1804de5f5  lea     rcx, [rbp+410h+var_418]; this
0x1804de5f9  call    ??1Fields@Result@System@Office@@QEAA@XZ; Office::System::Result::Fields::~Fields(void)
0x1804de5fe  lea     rcx, [rsp+510h+var_4B8]
0x1804de603  call    ??1?$unique_ptr@PEAXUHandleDeleter@Win@Mso@@@std@@QEAA@XZ; std::unique_ptr<void *,Mso::Win::HandleDeleter>::~unique_ptr<void *,Mso::Win::HandleDeleter>(void)
0x1804de608  lea     rcx, [rbp+410h+Src]; void *
0x1804de60c  call    ??1?$KeyValue@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$CBU_msoreg@@@Collections@Mso@@QEAA@XZ; Mso::Collections::KeyValue<std::wstring const,_msoreg const>::~KeyValue<std::wstring const,_msoreg const>(void)
0x1804de611  jmp     loc_1804DE4B7
0x1804de616  mov     [rsp+510h+NumberOfBytesWritten], r15d
0x1804de61b  mov     rax, [rdi+10h]
0x1804de61f  mov     [rsp+510h+var_4B0], rax
0x1804de624  mov     r8d, 2
0x1804de62a  lea     rdx, [rbp+410h+var_480]
0x1804de62e  lea     rcx, [rsp+510h+var_4B0]
0x1804de633  call    ??$?D_K@?$SafeInt@_KVSafeInt_InvalidParameter@safeint_exception_handlers@@@@QEBA?AV0@_K@Z; SafeInt<unsigned __int64,safeint_exception_handlers::SafeInt_InvalidParameter>::operator*<unsigned __int64>(unsigned __int64)
0x1804de638  mov     ecx, 0FFFFFFFFh
0x1804de63d  cmp     [rax], rcx
0x1804de640  jbe     short loc_1804DE648
0x1804de642  lea     ecx, [r8+3]
0x1804de646  int     29h; Win8: RtlFailFast(ecx)
0x1804de648  cmp     qword ptr [rdi+18h], 7
0x1804de64d  jbe     short loc_1804DE652
0x1804de64f  mov     rdi, [rdi]
0x1804de652  mov     [rsp+510h+lpOverlapped], r15; lpOverlapped
0x1804de657  lea     r9, [rsp+510h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1804de65c  mov     r8d, [rax]; nNumberOfBytesToWrite
0x1804de65f  mov     rdx, rdi; lpBuffer
0x1804de662  mov     rcx, rbx; hFile
0x1804de665  call    cs:__imp_WriteFile
0x1804de66b  test    eax, eax
0x1804de66d  jnz     short loc_1804DE6AB
0x1804de66f  call    cs:__imp_GetLastError
0x1804de675  mov     ebx, eax
0x1804de677  test    eax, eax
0x1804de679  jle     short loc_1804DE684
0x1804de67b  movzx   ebx, ax
0x1804de67e  or      ebx, 80070000h
0x1804de684  xor     edx, edx
0x1804de686  lea     rcx, [rsp+510h+var_4B8]
0x1804de68b  call    ?reset@?$unique_ptr@PEAXUHandleDeleter@Win@Mso@@@std@@QEAAXPEAX@Z; std::unique_ptr<void *,Mso::Win::HandleDeleter>::reset(void *)
0x1804de690  lea     rdx, [rbp+410h+var_480]; struct std::filesystem::path *
0x1804de694  lea     rcx, [rbp+410h+Src]; this
0x1804de698  call    ?remove@filesystem@std@@YA_NAEBVpath@12@AEAVerror_code@2@@Z; std::filesystem::remove(std::filesystem::path const &,std::error_code &)
0x1804de69d  lea     r8, aFailedtostorer; "FailedToStoreRecord"
0x1804de6a4  mov     edx, ebx
0x1804de6a6  jmp     loc_1804DE5D9
0x1804de6ab  lea     rcx, [rsp+510h+var_4B8]
0x1804de6b0  call    ??1?$unique_ptr@PEAXUHandleDeleter@Win@Mso@@@std@@QEAA@XZ; std::unique_ptr<void *,Mso::Win::HandleDeleter>::~unique_ptr<void *,Mso::Win::HandleDeleter>(void)
0x1804de6b5  lea     rcx, [rbp+410h+Src]; void *
0x1804de6b9  call    ??1?$KeyValue@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$CBU_msoreg@@@Collections@Mso@@QEAA@XZ; Mso::Collections::KeyValue<std::wstring const,_msoreg const>::~KeyValue<std::wstring const,_msoreg const>(void)
0x1804de6be  lea     rcx, [rsp+510h+var_4A8]
0x1804de6c3  call    ??1?$_Optional_destruct_base@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(void)
0x1804de6c8  jmp     loc_1804DE8F6
0x1804de6cd  jle     short loc_1804DE6D8
0x1804de6cf  movzx   edx, dx
0x1804de6d2  or      edx, 80070000h
0x1804de6d8  xor     r9d, r9d
0x1804de6db  lea     r8, aFailedtoupdate; "FailedToUpdateCache"
0x1804de6e2  lea     rcx, [rbp+410h+var_420]
0x1804de6e6  call    ?CreateResult@Telemetry@Mso@@YA?AVResult@System@Office@@HPEBDI@Z; Mso::Telemetry::CreateResult(int,char const *,uint)
0x1804de6eb  lea     r8, [rbp+410h+var_420]; struct Office::System::Result *
0x1804de6ef  xor     edx, edx; bool
0x1804de6f1  lea     rcx, [rsp+510h+var_4C8]; this
0x1804de6f6  call    ?SetResult@Activity@Telemetry@Mso@@QEAAX_NAEBVResult@System@Office@@@Z; Mso::Telemetry::Activity::SetResult(bool,Office::System::Result const &)
0x1804de6fb  lea     rcx, [rbp+410h+var_418]; this
0x1804de6ff  call    ??1Fields@Result@System@Office@@QEAA@XZ; Office::System::Result::Fields::~Fields(void)
0x1804de704  jmp     loc_1804DE608
0x1804de709  mov     r8b, 1; bool
0x1804de70c  lea     rcx, [rbp+410h+FileName]; wchar_t *
0x1804de713  call    ?GetAuditCacheDirectory@AuditDataCacheManager@Unified@Auditing@Mso@@CAJPEA_WH_N@Z; Mso::Auditing::Unified::AuditDataCacheManager::GetAuditCacheDirectory(wchar_t *,int,bool)
0x1804de718  test    eax, eax
0x1804de71a  jns     short loc_1804DE745
0x1804de71c  mov     edx, eax; int
0x1804de71e  lea     rcx, [rbp+410h+var_420]; this
0x1804de722  call    ??0Result@System@Office@@QEAA@H@Z; Office::System::Result::Result(int)
0x1804de727  lea     r8, [rbp+410h+var_420]; struct Office::System::Result *
0x1804de72b  xor     edx, edx; bool
0x1804de72d  lea     rcx, [rsp+510h+var_4C8]; this
0x1804de732  call    ?SetResult@Activity@Telemetry@Mso@@QEAAX_NAEBVResult@System@Office@@@Z; Mso::Telemetry::Activity::SetResult(bool,Office::System::Result const &)
0x1804de737  lea     rcx, [rbp+410h+var_418]; this
0x1804de73b  call    ??1Fields@Result@System@Office@@QEAA@XZ; Office::System::Result::Fields::~Fields(void)
0x1804de740  jmp     loc_1804DE4C1
0x1804de745  lea     rcx, [rbp+410h+FileName]
0x1804de74c  call    ?GetAuditCacheDirectoryForScenario@AuditDataCacheManager@Unified@Auditing@Mso@@CAJPEA_WHW4Scenario@234@_N@Z; Mso::Auditing::Unified::AuditDataCacheManager::GetAuditCacheDirectoryForScenario(wchar_t *,int,Mso::Auditing::Unified::Scenario,bool)
0x1804de751  mov     esi, eax
0x1804de753  test    eax, eax
0x1804de755  js      loc_1804DE96B
0x1804de75b  cmp     qword ptr [rbx+18h], 7
0x1804de760  jbe     short loc_1804DE765
0x1804de762  mov     rbx, [rbx]
0x1804de765  mov     r14d, 105h
0x1804de76b  mov     dword ptr [rsp+510h+lpOverlapped], r14d
0x1804de770  lea     r9, [rbp+410h+FileName]
0x1804de777  mov     r8, rbx
0x1804de77a  xor     edx, edx
0x1804de77c  lea     rcx, [rbp+410h+FileName]
0x1804de783  call    cs:__imp_?Combine@Path@Mso@@YA_NPEB_WW4Enum@PathType@2@0PEA_WH@Z; Mso::Path::Combine(wchar_t const *,Mso::PathType::Enum,wchar_t const *,wchar_t *,int)
0x1804de789  test    al, al
0x1804de78b  jz      loc_1804DE96B
0x1804de791  lea     r8, [rbp+410h+var_460]
0x1804de795  cmp     [rbp+410h+var_448], 7
0x1804de79a  cmova   r8, [rbp+410h+var_460]
0x1804de79f  mov     dword ptr [rsp+510h+lpOverlapped], r14d
0x1804de7a4  lea     r9, [rbp+410h+FileName]
0x1804de7ab  xor     edx, edx
0x1804de7ad  lea     rcx, [rbp+410h+FileName]
0x1804de7b4  call    cs:__imp_?Combine@Path@Mso@@YA_NPEB_WW4Enum@PathType@2@0PEA_WH@Z; Mso::Path::Combine(wchar_t const *,Mso::PathType::Enum,wchar_t const *,wchar_t *,int)
0x1804de7ba  test    al, al
0x1804de7bc  jz      loc_1804DE96B
0x1804de7c2  lea     rcx, [rbp+410h+FileName]
0x1804de7c9  call    cs:__imp_?MsoFEnsureDirectory@@YAHPEB_W@Z; MsoFEnsureDirectory(wchar_t const *)
0x1804de7cf  test    eax, eax
0x1804de7d1  jnz     short loc_1804DE7FF
0x1804de7d3  call    cs:__imp_GetLastError
0x1804de7d9  test    eax, eax
0x1804de7db  jle     short loc_1804DE7E5
0x1804de7dd  movzx   eax, ax
0x1804de7e0  or      eax, 80070000h
0x1804de7e5  xor     r9d, r9d
0x1804de7e8  lea     r8, aFailedtoupdate; "FailedToUpdateCache"
0x1804de7ef  mov     edx, eax
0x1804de7f1  lea     rcx, [rbp+410h+var_420]
0x1804de7f5  call    ?CreateResult@Telemetry@Mso@@YA?AVResult@System@Office@@HPEBDI@Z; Mso::Telemetry::CreateResult(int,char const *,uint)
0x1804de7fa  jmp     loc_1804DE727
0x1804de7ff  mov     [rsp+510h+var_4E0], r15
0x1804de804  mov     [rsp+510h+var_4E8], r15d
0x1804de809  mov     dword ptr [rsp+510h+lpOverlapped], 2
0x1804de811  xor     r9d, r9d
  ... truncated ...
```
