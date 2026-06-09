# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::RenameOldFileIfFound(std::filesystem::path)

- ea: `0x18003e920`
- end: `0x18003ed34`
- name: `?RenameOldFileIfFound@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UImageEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@UTextEmbeddingsGenerator@562789@UTextEmbeddingsGenerator@implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEAAXVpath@filesystem@std@@@Z`
- size: `1044`
- prototype: `__int64 __fastcall(__int64, WCHAR *)`
- caller_count: `2`
- callee_count: `20`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18003c3f0`
- `0x1800567e0`

## callees

- `0x180003fb0`
- `0x180004510`
- `0x180007740`
- `0x180007830`
- `0x180007de0`
- `0x18000d230`
- `0x180019520`
- `0x18003e920`
- `0x18003fda0`
- `0x180044920`
- `0x180044c80`
- `0x1800452c0`
- `0x180045320`
- `0x180045390`
- `0x1801d2a54`
- `0x1801f7110`
- `0x1801f7160`
- `0x1801f7190`
- `0x1801f97e0`
- `0x180206ec0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18003ebad`
- `KERNEL32!CloseHandle` at `0x18003ebd8`
- `KERNEL32!CloseHandle` at `0x18003ebad`
- `KERNEL32!CloseHandle` at `0x18003ebd8`

## string_xrefs

- `0x18003ec7d`: `could not get exclusive access to the database lock file`
- `0x18003ecd5`: `could not get exclusive access to the database lock file`
- `0x18003ec6e`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\IndexStoreCommon.h`
- `0x18003ecc6`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\IndexStoreCommon.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::RenameOldFileIfFound(
        __int64 a1,
        WCHAR *a2)
{
  void *v3; // rcx
  __int64 any_status; // rax
  const struct std::filesystem::path *v5; // rdx
  const struct std::filesystem::path *v6; // r9
  std::filesystem *v7; // rcx
  _QWORD *v8; // r14
  __int64 v9; // r8
  _QWORD *v10; // r15
  const WCHAR *v11; // rdx
  const WCHAR *v12; // rcx
  DWORD v13; // eax
  __int64 v14; // rcx
  std::filesystem *v15; // rax
  const struct std::filesystem::path *v16; // rdx
  __int64 v17; // rsi
  __int64 v18; // rax
  __int64 v19; // rbx
  const WCHAR *v20; // rdx
  const WCHAR *v21; // rcx
  DWORD v22; // eax
  __int64 v23; // rcx
  std::filesystem *v24; // rax
  const struct std::filesystem::path *v25; // rdx
  __int64 v26; // rsi
  __int64 v27; // rax
  __int64 v28; // rbx
  const WCHAR *v29; // rdx
  const WCHAR *v30; // rcx
  DWORD v31; // eax
  __int64 v32; // rcx
  void *v33; // rcx
  void *v34; // rcx
  unsigned int *v36; // rax
  unsigned int *v37; // rax
  _QWORD v38[2]; // [rsp+30h] [rbp-79h] BYREF
  char v39[16]; // [rsp+40h] [rbp-69h] BYREF
  _QWORD v40[3]; // [rsp+50h] [rbp-59h] BYREF
  int pExceptionObject; // [rsp+68h] [rbp-41h] BYREF
  const char *v42; // [rsp+70h] [rbp-39h]
  __int64 v43; // [rsp+78h] [rbp-31h]
  _BYTE v44[32]; // [rsp+80h] [rbp-29h] BYREF
  WCHAR *v45; // [rsp+A0h] [rbp-9h]
  __int128 v46; // [rsp+A8h] [rbp-1h] BYREF
  __int64 v47; // [rsp+B8h] [rbp+Fh]
  unsigned __int64 v48; // [rsp+C0h] [rbp+17h]
  _QWORD Src[4]; // [rsp+C8h] [rbp+1Fh] BYREF

  v45 = a2;
  std::basic_string<char16_t>::basic_string<char16_t>(Src, a2);
  v46 = 0;
  v47 = 0;
  v48 = 0;
  std::basic_string<char16_t>::_Construct<1,char16_t const *>(&v46);
  std::filesystem::path::replace_extension((std::filesystem::path *)Src, (const struct std::filesystem::path *)&v46);
  if ( v48 > 7 )
  {
    v3 = (void *)v46;
    if ( 2 * v48 + 2 >= 0x1000 )
    {
      v3 = *(void **)(v46 - 8);
      if ( (unsigned __int64)(v46 - (_QWORD)v3 - 8) > 0x1F )
        invoke_watson(0, 0, 0, 0, 0);
    }
    operator delete(v3);
  }
  any_status = std::filesystem::_Get_any_status(v39, Src);
  v40[0] = *(_QWORD *)any_status;
  v7 = (std::filesystem *)*(unsigned int *)(any_status + 8);
  *(_DWORD *)v39 = *(_DWORD *)(any_status + 8);
  *(_QWORD *)&v39[8] = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
  if ( LODWORD(v40[0]) )
  {
    if ( LODWORD(v40[0]) != 1 && !std::filesystem::exists((std::filesystem *)a2, v5) )
    {
      v38[0] = operator new(0x30u);
      std::basic_string<char16_t>::basic_string<char16_t>(&v46, a2);
      v8 = (_QWORD *)winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexLockFile::IndexLockFile(
                       v38[0],
                       &v46,
                       0);
      *(_QWORD *)v39 = v8;
      if ( v8[5] == -1 )
      {
        LODWORD(v40[0]) = 2164;
        v40[1] = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\IndexStoreCommon.h";
        v40[2] = 0;
        winrt::param::hstring::hstring(
          (winrt::param::hstring *)&v46,
          L"could not get exclusive access to the database lock file");
        v36 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)v38, -2081706721);
        winrt::hresult_error::hresult_error(&pExceptionObject, *v36, &v46, v40);
        throw (winrt::hresult_error *)&pExceptionObject;
      }
      v38[0] = operator new(0x30u);
      std::basic_string<char16_t>::basic_string<char16_t>(&v46, Src);
      LOBYTE(v9) = 1;
      v10 = (_QWORD *)winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexLockFile::IndexLockFile(
                        v38[0],
                        &v46,
                        v9);
      v40[0] = v10;
      if ( v10[5] == -1 )
      {
        pExceptionObject = 2170;
        v42 = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\IndexStoreCommon.h";
        v43 = 0;
        winrt::param::hstring::hstring(
          (winrt::param::hstring *)v44,
          L"could not get exclusive access to the database lock file");
        v37 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)v38, -2081706721);
        winrt::hresult_error::hresult_error(&v46, *v37, v44, &pExceptionObject);
        throw (winrt::hresult_error *)&v46;
      }
      v11 = a2;
      if ( *((_QWORD *)a2 + 3) > 7u )
        v11 = *(const WCHAR **)a2;
      v12 = (const WCHAR *)Src;
      if ( Src[3] > 7u )
        v12 = (const WCHAR *)Src[0];
      v13 = _std_fs_rename(v12, v11);
      if ( v13 )
        std::filesystem::_Throw_fs_error(v14, v13, Src, a2);
      v15 = (std::filesystem *)std::filesystem::path::append<char [5],0>(Src);
      if ( std::filesystem::exists(v15, v16) )
      {
        v17 = std::filesystem::path::append<char [5],0>(a2);
        v18 = std::filesystem::path::append<char [5],0>(Src);
        v19 = v18;
        v20 = (const WCHAR *)v17;
        if ( *(_QWORD *)(v17 + 24) > 7u )
          v20 = *(const WCHAR **)v17;
        v21 = (const WCHAR *)v18;
        if ( *(_QWORD *)(v18 + 24) > 7u )
          v21 = *(const WCHAR **)v18;
        v22 = _std_fs_rename(v21, v20);
        if ( v22 )
          std::filesystem::_Throw_fs_error(v23, v22, v19, v17);
      }
      v24 = (std::filesystem *)std::filesystem::path::append<char [5],0>(Src);
      if ( std::filesystem::exists(v24, v25) )
      {
        v26 = std::filesystem::path::append<char [5],0>(a2);
        v27 = std::filesystem::path::append<char [5],0>(Src);
        v28 = v27;
        v29 = (const WCHAR *)v26;
        if ( *(_QWORD *)(v26 + 24) > 7u )
          v29 = *(const WCHAR **)v26;
        v30 = (const WCHAR *)v27;
        if ( *(_QWORD *)(v27 + 24) > 7u )
          v30 = *(const WCHAR **)v27;
        v31 = _std_fs_rename(v30, v29);
        if ( v31 )
          std::filesystem::_Throw_fs_error(v32, v31, v28, v26);
      }
      v33 = (void *)v10[5];
      if ( v33 != (void *)-1LL && v33 )
        CloseHandle(v33);
      std::basic_string<char16_t>::_Tidy_deallocate(v10 + 1);
      operator delete(v10);
      v34 = (void *)v8[5];
      if ( v34 != (void *)-1LL && v34 )
        CloseHandle(v34);
      std::basic_string<char16_t>::_Tidy_deallocate(v8 + 1);
      operator delete(v8);
    }
  }
  else if ( (_DWORD)v7 )
  {
    std::filesystem::_Throw_fs_error(v7, v39, (const struct std::error_code *)Src, v6);
  }
  std::basic_string<char16_t>::_Tidy_deallocate(Src);
  return std::basic_string<char16_t>::_Tidy_deallocate(a2);
}

```

## disassembly

```asm
0x18003e920  mov     [rsp-8+arg_0], rbx
0x18003e925  mov     [rsp-8+arg_10], rsi
0x18003e92a  mov     [rsp-8+arg_18], rdi
0x18003e92f  push    rbp
0x18003e930  push    r14
0x18003e932  push    r15
0x18003e934  lea     rbp, [rsp-47h]
0x18003e939  sub     rsp, 0F0h
0x18003e940  mov     rax, cs:__security_cookie
0x18003e947  xor     rax, rsp
0x18003e94a  mov     [rbp+57h+var_18], rax
0x18003e94e  mov     rdi, rdx
0x18003e951  mov     [rbp+57h+var_60], rdx
0x18003e955  xor     esi, esi
0x18003e957  lea     rcx, [rbp+57h+Src]
0x18003e95b  call    ??0?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@QEAA@AEBV01@@Z; std::basic_string<char16_t>::basic_string<char16_t>(std::basic_string<char16_t> const &)
0x18003e960  nop
0x18003e961  xorps   xmm0, xmm0
0x18003e964  movups  [rbp+57h+var_58], xmm0
0x18003e968  mov     [rbp+57h+var_48], rsi
0x18003e96c  mov     [rbp+57h+var_40], rsi
0x18003e970  mov     r8d, 5
0x18003e976  lea     rdx, aSsdb; ".ssdb"
0x18003e97d  lea     rcx, [rbp+57h+var_58]
0x18003e981  call    ??$_Construct@$00PEB_S@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEAAXQEB_S_K@Z; std::basic_string<char16_t>::_Construct<1,char16_t const *>(char16_t const * const,unsigned __int64)
0x18003e986  nop
0x18003e987  lea     rdx, [rbp+57h+var_58]; struct std::filesystem::path *
0x18003e98b  lea     rcx, [rbp+57h+Src]; this
0x18003e98f  call    ?replace_extension@path@filesystem@std@@QEAAAEAV123@AEBV123@@Z; std::filesystem::path::replace_extension(std::filesystem::path const &)
0x18003e994  nop
0x18003e995  mov     rdx, [rbp+57h+var_40]
0x18003e999  cmp     rdx, 7
0x18003e99d  jbe     short loc_18003E9D5
0x18003e99f  lea     rdx, ds:2[rdx*2]
0x18003e9a7  mov     rcx, qword ptr [rbp+57h+var_58]
0x18003e9ab  mov     rax, rcx
0x18003e9ae  cmp     rdx, 1000h
0x18003e9b5  jb      short loc_18003E9D0
0x18003e9b7  add     rdx, 27h ; '''
0x18003e9bb  mov     rcx, [rcx-8]; Block
0x18003e9bf  sub     rax, rcx
0x18003e9c2  sub     rax, 8
0x18003e9c6  cmp     rax, 1Fh
0x18003e9ca  ja      loc_18003EC52
0x18003e9d0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003e9d5  lea     rdx, [rbp+57h+Src]
0x18003e9d9  lea     rcx, [rbp+57h+var_C0]
0x18003e9dd  call    ?_Get_any_status@filesystem@std@@YA?AU_File_status_and_error@12@AEBVpath@12@W4__std_fs_stats_flags@@@Z; std::filesystem::_Get_any_status(std::filesystem::path const &,__std_fs_stats_flags)
0x18003e9e2  movsd   xmm0, qword ptr [rax]
0x18003e9e6  movsd   [rbp+57h+var_B0], xmm0
0x18003e9eb  mov     ecx, [rax+8]; this
0x18003e9ee  mov     dword ptr [rbp+57h+var_C0], ecx
0x18003e9f1  lea     rax, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4V21@B; std::_System_error_category const `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x18003e9f8  mov     qword ptr [rbp+57h+var_C0+8], rax
0x18003e9fc  movaps  xmm0, xmmword ptr [rbp+57h+var_C0]
0x18003ea00  movdqa  xmmword ptr [rbp+57h+var_C0], xmm0
0x18003ea05  mov     eax, dword ptr [rbp+57h+var_B0]
0x18003ea08  test    eax, eax
0x18003ea0a  jz      loc_18003EC30
0x18003ea10  cmp     eax, 1
0x18003ea13  jz      loc_18003EBF5
0x18003ea19  mov     rcx, rdi; this
0x18003ea1c  call    ?exists@filesystem@std@@YA_NAEBVpath@12@@Z; std::filesystem::exists(std::filesystem::path const &)
0x18003ea21  test    al, al
0x18003ea23  jnz     loc_18003EBF5
0x18003ea29  mov     ecx, 30h ; '0'; Size
0x18003ea2e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003ea33  mov     rbx, rax
0x18003ea36  mov     [rbp+57h+var_D0], rax
0x18003ea3a  mov     rdx, rdi
0x18003ea3d  lea     rcx, [rbp+57h+var_58]
0x18003ea41  call    ??0?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@QEAA@AEBV01@@Z; std::basic_string<char16_t>::basic_string<char16_t>(std::basic_string<char16_t> const &)
0x18003ea46  xor     r8d, r8d
0x18003ea49  lea     rdx, [rbp+57h+var_58]
0x18003ea4d  mov     rcx, rbx
0x18003ea50  call    ??0IndexLockFile@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@QEAA@Vpath@filesystem@std@@_N@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexLockFile::IndexLockFile(std::filesystem::path,bool)
0x18003ea55  mov     r14, rax
0x18003ea58  mov     qword ptr [rbp+57h+var_C0], rax
0x18003ea5c  cmp     qword ptr [rax+28h], 0FFFFFFFFFFFFFFFFh
0x18003ea61  jz      loc_18003EC67
0x18003ea67  mov     ecx, 30h ; '0'; Size
0x18003ea6c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003ea71  mov     rbx, rax
0x18003ea74  mov     [rbp+57h+var_D0], rax
0x18003ea78  lea     rdx, [rbp+57h+Src]
0x18003ea7c  lea     rcx, [rbp+57h+var_58]
0x18003ea80  call    ??0?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@QEAA@AEBV01@@Z; std::basic_string<char16_t>::basic_string<char16_t>(std::basic_string<char16_t> const &)
0x18003ea85  mov     r8b, 1
0x18003ea88  lea     rdx, [rbp+57h+var_58]
0x18003ea8c  mov     rcx, rbx
0x18003ea8f  call    ??0IndexLockFile@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@QEAA@Vpath@filesystem@std@@_N@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexLockFile::IndexLockFile(std::filesystem::path,bool)
0x18003ea94  mov     r15, rax
0x18003ea97  mov     [rbp+57h+var_B0], rax
0x18003ea9b  cmp     qword ptr [rax+28h], 0FFFFFFFFFFFFFFFFh
0x18003eaa0  jz      loc_18003ECBF
0x18003eaa6  mov     rdx, rdi
0x18003eaa9  cmp     qword ptr [rdi+18h], 7
0x18003eaae  jbe     short loc_18003EAB3
0x18003eab0  mov     rdx, [rdi]
0x18003eab3  lea     rcx, [rbp+57h+Src]
0x18003eab7  cmp     [rbp+57h+var_20], 7
0x18003eabc  cmova   rcx, [rbp+57h+Src]
0x18003eac1  call    __std_fs_rename
0x18003eac6  test    eax, eax
0x18003eac8  jnz     loc_18003ED17
0x18003eace  lea     rdx, aWal; "-wal"
0x18003ead5  lea     rcx, [rbp+57h+Src]; Src
0x18003ead9  call    ??$append@$$BY04D$0A@@path@filesystem@std@@QEAAAEAV012@AEAY04$$CBD@Z; std::filesystem::path::append<char [5],0>(char const (&)[5])
0x18003eade  mov     rcx, rax; this
0x18003eae1  call    ?exists@filesystem@std@@YA_NAEBVpath@12@@Z; std::filesystem::exists(std::filesystem::path const &)
0x18003eae6  test    al, al
0x18003eae8  jz      short loc_18003EB36
0x18003eaea  lea     rdx, aWal; "-wal"
0x18003eaf1  mov     rcx, rdi; Src
0x18003eaf4  call    ??$append@$$BY04D$0A@@path@filesystem@std@@QEAAAEAV012@AEAY04$$CBD@Z; std::filesystem::path::append<char [5],0>(char const (&)[5])
0x18003eaf9  mov     rsi, rax
0x18003eafc  lea     rdx, aWal; "-wal"
0x18003eb03  lea     rcx, [rbp+57h+Src]; Src
0x18003eb07  call    ??$append@$$BY04D$0A@@path@filesystem@std@@QEAAAEAV012@AEAY04$$CBD@Z; std::filesystem::path::append<char [5],0>(char const (&)[5])
0x18003eb0c  mov     rbx, rax
0x18003eb0f  mov     rdx, rsi
0x18003eb12  cmp     qword ptr [rsi+18h], 7
0x18003eb17  jbe     short loc_18003EB1C
0x18003eb19  mov     rdx, [rsi]
0x18003eb1c  mov     rcx, rbx
0x18003eb1f  cmp     qword ptr [rax+18h], 7
0x18003eb24  jbe     short loc_18003EB29
0x18003eb26  mov     rcx, [rax]
0x18003eb29  call    __std_fs_rename
0x18003eb2e  test    eax, eax
0x18003eb30  jnz     loc_18003ED26
0x18003eb36  lea     rdx, aShm; "-shm"
0x18003eb3d  lea     rcx, [rbp+57h+Src]; Src
0x18003eb41  call    ??$append@$$BY04D$0A@@path@filesystem@std@@QEAAAEAV012@AEAY04$$CBD@Z; std::filesystem::path::append<char [5],0>(char const (&)[5])
0x18003eb46  mov     rcx, rax; this
0x18003eb49  call    ?exists@filesystem@std@@YA_NAEBVpath@12@@Z; std::filesystem::exists(std::filesystem::path const &)
0x18003eb4e  test    al, al
0x18003eb50  jz      short loc_18003EB9E
0x18003eb52  lea     rdx, aShm; "-shm"
0x18003eb59  mov     rcx, rdi; Src
0x18003eb5c  call    ??$append@$$BY04D$0A@@path@filesystem@std@@QEAAAEAV012@AEAY04$$CBD@Z; std::filesystem::path::append<char [5],0>(char const (&)[5])
0x18003eb61  mov     rsi, rax
0x18003eb64  lea     rdx, aShm; "-shm"
0x18003eb6b  lea     rcx, [rbp+57h+Src]; Src
0x18003eb6f  call    ??$append@$$BY04D$0A@@path@filesystem@std@@QEAAAEAV012@AEAY04$$CBD@Z; std::filesystem::path::append<char [5],0>(char const (&)[5])
0x18003eb74  mov     rbx, rax
0x18003eb77  mov     rdx, rsi
0x18003eb7a  cmp     qword ptr [rsi+18h], 7
0x18003eb7f  jbe     short loc_18003EB84
0x18003eb81  mov     rdx, [rsi]
0x18003eb84  mov     rcx, rbx
0x18003eb87  cmp     qword ptr [rax+18h], 7
0x18003eb8c  jbe     short loc_18003EB91
0x18003eb8e  mov     rcx, [rax]
0x18003eb91  call    __std_fs_rename
0x18003eb96  test    eax, eax
0x18003eb98  jnz     loc_18003EC36
0x18003eb9e  mov     rcx, [r15+28h]; hObject
0x18003eba2  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18003eba6  jz      short loc_18003EBB3
0x18003eba8  test    rcx, rcx
0x18003ebab  jz      short loc_18003EBB3
0x18003ebad  call    cs:__imp_CloseHandle
0x18003ebb3  lea     rcx, [r15+8]
0x18003ebb7  call    ?_Tidy_deallocate@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEAAXXZ; std::basic_string<char16_t>::_Tidy_deallocate(void)
0x18003ebbc  mov     edx, 30h ; '0'
0x18003ebc1  mov     rcx, r15; Block
0x18003ebc4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003ebc9  mov     rcx, [r14+28h]; hObject
0x18003ebcd  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18003ebd1  jz      short loc_18003EBDE
0x18003ebd3  test    rcx, rcx
0x18003ebd6  jz      short loc_18003EBDE
0x18003ebd8  call    cs:__imp_CloseHandle
0x18003ebde  lea     rcx, [r14+8]
0x18003ebe2  call    ?_Tidy_deallocate@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEAAXXZ; std::basic_string<char16_t>::_Tidy_deallocate(void)
0x18003ebe7  mov     edx, 30h ; '0'
0x18003ebec  mov     rcx, r14; Block
0x18003ebef  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003ebf4  nop
0x18003ebf5  lea     rcx, [rbp+57h+Src]
0x18003ebf9  call    ?_Tidy_deallocate@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEAAXXZ; std::basic_string<char16_t>::_Tidy_deallocate(void)
0x18003ebfe  nop
0x18003ebff  mov     rcx, rdi
0x18003ec02  call    ?_Tidy_deallocate@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEAAXXZ; std::basic_string<char16_t>::_Tidy_deallocate(void)
0x18003ec07  mov     rcx, [rbp+57h+var_18]
0x18003ec0b  xor     rcx, rsp; StackCookie
0x18003ec0e  call    __security_check_cookie
0x18003ec13  lea     r11, [rsp+100h+var_10]
0x18003ec1b  mov     rbx, [r11+20h]
0x18003ec1f  mov     rsi, [r11+30h]
0x18003ec23  mov     rdi, [r11+38h]
0x18003ec27  mov     rsp, r11
0x18003ec2a  pop     r15
0x18003ec2c  pop     r14
0x18003ec2e  pop     rbp
0x18003ec2f  retn
0x18003ec30  test    ecx, ecx
0x18003ec32  jnz     short loc_18003EC44
0x18003ec34  jmp     short loc_18003EBF5
0x18003ec36  mov     r9, rsi
0x18003ec39  mov     r8, rbx
0x18003ec3c  mov     edx, eax
0x18003ec3e  call    ?_Throw_fs_error@filesystem@std@@YAXPEBDW4__std_win_error@@AEBVpath@12@2@Z; std::filesystem::_Throw_fs_error(char const *,__std_win_error,std::filesystem::path const &,std::filesystem::path const &)
0x18003ec44  lea     r8, [rbp+57h+Src]; struct std::error_code *
0x18003ec48  lea     rdx, [rbp+57h+var_C0]; char *
0x18003ec4c  call    ?_Throw_fs_error@filesystem@std@@YAXPEBDAEBVerror_code@2@AEBVpath@12@@Z; std::filesystem::_Throw_fs_error(char const *,std::error_code const &,std::filesystem::path const &)
0x18003ec52  mov     [rsp+100h+Reserved], rsi; Reserved
0x18003ec57  xor     r9d, r9d; LineNo
0x18003ec5a  xor     r8d, r8d; FileName
0x18003ec5d  xor     edx, edx; FunctionName
0x18003ec5f  xor     ecx, ecx; Expression
0x18003ec61  call    _invoke_watson
0x18003ec67  mov     dword ptr [rbp+57h+var_B0], 874h
0x18003ec6e  lea     rax, aCW1SSrcSemanti_21; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x18003ec75  mov     [rbp+57h+var_A8], rax
0x18003ec79  mov     [rbp+57h+var_A0], rsi
0x18003ec7d  lea     rdx, aCouldNotGetExc; "could not get exclusive access to the d"...
0x18003ec84  lea     rcx, [rbp+57h+var_58]; this
0x18003ec88  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x18003ec8d  mov     edx, 83EBAD1Fh; int
0x18003ec92  lea     rcx, [rbp+57h+var_D0]; this
0x18003ec96  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x18003ec9b  lea     r9, [rbp+57h+var_B0]
0x18003ec9f  lea     r8, [rbp+57h+var_58]
0x18003eca3  mov     edx, [rax]
0x18003eca5  lea     rcx, [rbp+57h+pExceptionObject]
0x18003eca9  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x18003ecae  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x18003ecb5  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18003ecb9  call    _CxxThrowException
0x18003ecbf  mov     [rbp+57h+pExceptionObject], 87Ah
0x18003ecc6  lea     rax, aCW1SSrcSemanti_21; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x18003eccd  mov     [rbp+57h+var_90], rax
0x18003ecd1  mov     [rbp+57h+var_88], rsi
0x18003ecd5  lea     rdx, aCouldNotGetExc; "could not get exclusive access to the d"...
0x18003ecdc  lea     rcx, [rbp+57h+var_80]; this
0x18003ece0  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x18003ece5  mov     edx, 83EBAD1Fh; int
0x18003ecea  lea     rcx, [rbp+57h+var_D0]; this
0x18003ecee  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x18003ecf3  lea     r9, [rbp+57h+pExceptionObject]
0x18003ecf7  lea     r8, [rbp+57h+var_80]
0x18003ecfb  mov     edx, [rax]
0x18003ecfd  lea     rcx, [rbp+57h+var_58]
0x18003ed01  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x18003ed06  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x18003ed0d  lea     rcx, [rbp+57h+var_58]; pExceptionObject
0x18003ed11  call    _CxxThrowException
0x18003ed17  mov     r9, rdi
0x18003ed1a  lea     r8, [rbp+57h+Src]
0x18003ed1e  mov     edx, eax
0x18003ed20  call    ?_Throw_fs_error@filesystem@std@@YAXPEBDW4__std_win_error@@AEBVpath@12@2@Z; std::filesystem::_Throw_fs_error(char const *,__std_win_error,std::filesystem::path const &,std::filesystem::path const &)
0x18003ed26  mov     r9, rsi
0x18003ed29  mov     r8, rbx
0x18003ed2c  mov     edx, eax
0x18003ed2e  call    ?_Throw_fs_error@filesystem@std@@YAXPEBDW4__std_win_error@@AEBVpath@12@2@Z; std::filesystem::_Throw_fs_error(char const *,__std_win_error,std::filesystem::path const &,std::filesystem::path const &)
```
