# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::DeleteIndex(winrt::hstring)

- ea: `0x180027580`
- end: `0x18002786b`
- name: `?DeleteIndex@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UImageEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@UTextEmbeddingsGenerator@562789@UTextEmbeddingsGenerator@implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SAXUhstring@8@@Z`
- size: `747`
- prototype: `int __fastcall(volatile signed __int32 **)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001a750`

## callees

- `0x180003fb0`
- `0x180004040`
- `0x180004510`
- `0x180007740`
- `0x180007830`
- `0x180007de0`
- `0x18000ae20`
- `0x18000d230`
- `0x18000d290`
- `0x180019520`
- `0x180027580`
- `0x180027870`
- `0x18002b830`
- `0x18002dae0`
- `0x180046f70`
- `0x180067b60`
- `0x180078d00`
- `0x180078d10`
- `0x18007c660`
- `0x1801f7110`
- `0x1801f7160`
- `0x1801f7190`
- `0x1801f97e0`
- `0x180206a58`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800276df`
- `KERNEL32!CloseHandle` at `0x1800276df`

## string_xrefs

- `0x180027823`: `could not get exclusive access to the database lock file`
- `0x180027642`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\IndexStoreCommon.h`
- `0x1800277bd`: `Could not delete database file (%d) "%ls". `
- `0x180027669`: `void __cdecl winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<class asg::SemanticIndex::SemanticIndexStore,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::A`

## pseudocode

```c
int __fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::DeleteIndex(
        volatile signed __int32 **a1)
{
  const wchar_t *v2; // rdx
  __int64 v3; // r8
  __int64 v4; // r8
  _QWORD *v5; // r14
  __int64 i; // rcx
  std::error_code *v7; // rbx
  int v8; // edx
  void *v9; // rcx
  int result; // eax
  volatile signed __int32 *v11; // rbx
  int v12; // esi
  HANDLE ProcessHeap; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  unsigned int *v16; // rax
  unsigned int *v17; // rax
  int v18; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE *v19; // [rsp+28h] [rbp-D8h] BYREF
  __int128 v20; // [rsp+30h] [rbp-D0h] BYREF
  _DWORD v21[2]; // [rsp+40h] [rbp-C0h] BYREF
  const char *v22; // [rsp+48h] [rbp-B8h]
  const char *v23; // [rsp+50h] [rbp-B0h]
  __int128 pExceptionObject; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v25; // [rsp+68h] [rbp-98h]
  __int64 v26; // [rsp+70h] [rbp-90h]
  int v27; // [rsp+78h] [rbp-88h] BYREF
  const char *v28; // [rsp+80h] [rbp-80h]
  __int64 v29; // [rsp+88h] [rbp-78h]
  __int64 v30; // [rsp+98h] [rbp-68h] BYREF
  __int64 v31; // [rsp+A0h] [rbp-60h]
  volatile signed __int32 **v32; // [rsp+B0h] [rbp-50h]
  _QWORD *v33; // [rsp+B8h] [rbp-48h]
  _BYTE v34[32]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v35[32]; // [rsp+E0h] [rbp-20h] BYREF
  char v36[32]; // [rsp+100h] [rbp+0h] BYREF
  char v37[32]; // [rsp+120h] [rbp+20h] BYREF

  v32 = a1;
  if ( *a1 )
    v2 = (const wchar_t *)*((_QWORD *)*a1 + 2);
  else
    v2 = &String;
  v3 = -1;
  do
    ++v3;
  while ( v2[v3] );
  pExceptionObject = 0;
  v25 = 0;
  v26 = 0;
  std::basic_string<char16_t>::_Construct<1,char16_t const *>(&pExceptionObject);
  winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::AppendDbExtensionIfRequired(
    v35,
    &pExceptionObject);
  *(_QWORD *)&v20 = operator new(0x30u);
  std::basic_string<char16_t>::basic_string<char16_t>(&v27, v35);
  LOBYTE(v4) = 1;
  v5 = (_QWORD *)winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexLockFile::IndexLockFile(
                   v20,
                   &v27,
                   v4);
  v33 = v5;
  v22 = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\IndexStoreCommon.h";
  if ( v5[5] == -1 )
  {
    v21[0] = 63;
    v23 = 0;
    winrt::param::hstring::hstring(
      (winrt::param::hstring *)&pExceptionObject,
      L"could not get exclusive access to the database lock file");
    v17 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)&v18, -2081706721);
    winrt::hresult_error::hresult_error(&v27, *v17, &pExceptionObject, v21);
    throw (winrt::hresult_error *)&v27;
  }
  v21[0] = 66;
  v21[1] = 28;
  v23 = "void __cdecl winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<cla"
        "ss asg::SemanticIndex::SemanticIndexStore,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::"
        "ImageEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::I"
        "mageEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGene"
        "rator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenera"
        "tor>::DeleteIndex(struct winrt::hstring)";
  v19 = v35;
  ___SemanticIndexCall_V_lambda_1___1__DeleteIndex___IndexStoreCommon_VSemanticIndexStore_SemanticIndex_asg__UImageEmbeddingsGenerator_Compatibility_AiFabric_2Asg_Microsoft_winrt__U4implementation_562789_UTextEmbeddingsGenerator_562789_UTextEmbeddingsGenerator_implementation_562789__implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__SAXUhstring_winrt___Z__implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__YA_A_P__QEAV_lambda_1___1__DeleteIndex___IndexStoreCommon_VSemanticIndexStore_SemanticIndex_asg__UImageEmbeddingsGenerator_Compatibility_AiFabric_2Asg_Microsoft_winrt__U4implementation_562789_UTextEmbeddingsGenerator_562789_UTextEmbeddingsGenerator_implementation_562789__0123456_SAXUhstring_6__Z_AEBUsource_location_std___Z(
    &v30,
    &v19,
    v21);
  for ( i = v30; i != v31; i += 48 )
  {
    v7 = (std::error_code *)(i + 32);
    v8 = *(_DWORD *)(i + 32);
    if ( v8 && (*(_QWORD *)(*(_QWORD *)(i + 40) + 8LL) != qword_18033C360 || v8 != 2) )
    {
      v27 = 76;
      v28 = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\IndexStoreCommon.h";
      v29 = 0;
      v20 = *(_OWORD *)std::basic_string<char8_t>::operator std::u8string_view(i, v21, v31, qword_18033C360);
      v14 = asg::utf8ToWide(v36, &v20);
      *(_QWORD *)&v20 = std::basic_string<char16_t>::c_str(v14);
      v18 = std::error_code::value(v7);
      v15 = asg::wformat<int,wchar_t *>(v37, L"Could not delete database file (%d) \"%ls\". ", &v18, &v20);
      winrt::param::hstring::hstring(v34, v15);
      v16 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)&v19, -2081706721);
      winrt::hresult_error::hresult_error(&pExceptionObject, *v16, v34, &v27);
      throw (winrt::hresult_error *)&pExceptionObject;
    }
  }
  v9 = (void *)v5[5];
  if ( v9 != (void *)-1LL && v9 )
    CloseHandle(v9);
  std::basic_string<char16_t>::_Tidy_deallocate(v5 + 1);
  operator delete(v5);
  std::vector<asg::SemanticIndex::DatabaseFileDeletionAttempt>::~vector<asg::SemanticIndex::DatabaseFileDeletionAttempt>(&v30);
  result = std::basic_string<char16_t>::_Tidy_deallocate(v35);
  v11 = *a1;
  if ( *a1 )
  {
    v12 = _InterlockedDecrement(v11 + 6);
    if ( v12 )
    {
      if ( v12 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      result = WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v11);
    }
    *a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180027580  mov     [rsp-8+arg_8], rbx
0x180027585  mov     [rsp-8+arg_10], rsi
0x18002758a  push    rbp
0x18002758b  push    rdi
0x18002758c  push    r12
0x18002758e  push    r14
0x180027590  push    r15
0x180027592  lea     rbp, [rsp-50h]
0x180027597  sub     rsp, 150h
0x18002759e  mov     rax, cs:__security_cookie
0x1800275a5  xor     rax, rsp
0x1800275a8  mov     [rbp+70h+var_30], rax
0x1800275ac  mov     rdi, rcx
0x1800275af  mov     [rbp+70h+var_C0], rcx
0x1800275b3  xor     r12d, r12d
0x1800275b6  mov     rdx, [rcx]
0x1800275b9  test    rdx, rdx
0x1800275bc  jz      short loc_1800275C4
0x1800275be  mov     rdx, [rdx+10h]
0x1800275c2  jmp     short loc_1800275CB
0x1800275c4  lea     rdx, String
0x1800275cb  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x1800275d2  mov     r8, rsi
0x1800275d5  inc     r8
0x1800275d8  cmp     word ptr [rdx+r8*2], 0
0x1800275de  jnz     short loc_1800275D5
0x1800275e0  xorps   xmm0, xmm0
0x1800275e3  movups  [rsp+170h+pExceptionObject], xmm0
0x1800275e8  mov     [rsp+170h+var_108], r12
0x1800275ed  mov     [rsp+170h+var_100], r12
0x1800275f2  lea     rcx, [rsp+170h+pExceptionObject]
0x1800275f7  call    ??$_Construct@$00PEB_S@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEAAXQEB_S_K@Z; std::basic_string<char16_t>::_Construct<1,char16_t const *>(char16_t const * const,unsigned __int64)
0x1800275fc  lea     rdx, [rsp+170h+pExceptionObject]
0x180027601  lea     rcx, [rbp+70h+var_90]
0x180027605  call    ?AppendDbExtensionIfRequired@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@YA?AVpath@filesystem@std@@V89std@@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::AppendDbExtensionIfRequired(std::filesystem::path)
0x18002760a  nop
0x18002760b  mov     ecx, 30h ; '0'; Size
0x180027610  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180027615  mov     rbx, rax
0x180027618  mov     qword ptr [rsp+170h+var_140], rax
0x18002761d  lea     rdx, [rbp+70h+var_90]
0x180027621  lea     rcx, [rsp+170h+var_F8]
0x180027626  call    ??0?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@QEAA@AEBV01@@Z; std::basic_string<char16_t>::basic_string<char16_t>(std::basic_string<char16_t> const &)
0x18002762b  mov     r8b, 1
0x18002762e  lea     rdx, [rsp+170h+var_F8]
0x180027633  mov     rcx, rbx
0x180027636  call    ??0IndexLockFile@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@QEAA@Vpath@filesystem@std@@_N@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexLockFile::IndexLockFile(std::filesystem::path,bool)
0x18002763b  mov     r14, rax
0x18002763e  mov     [rbp+70h+var_B8], rax
0x180027642  lea     r15, aCW1SSrcSemanti_21; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x180027649  mov     [rsp+170h+var_128], r15
0x18002764e  cmp     qword ptr [rax+28h], 0FFFFFFFFFFFFFFFFh
0x180027653  jz      loc_180027816
0x180027659  mov     [rsp+170h+var_130], 42h ; 'B'
0x180027661  mov     [rsp+170h+var_12C], 1Ch
0x180027669  lea     rax, aVoidCdeclWinrt; "void __cdecl winrt::Microsoft::Asg::Sem"...
0x180027670  mov     [rsp+170h+var_120], rax
0x180027675  lea     rax, [rbp+70h+var_90]
0x180027679  mov     [rsp+170h+var_148], rax
0x18002767e  lea     r8, [rsp+170h+var_130]
0x180027683  lea     rdx, [rsp+170h+var_148]
0x180027688  lea     rcx, [rbp+70h+var_D8]
0x18002768c  call    ??$SemanticIndexCall@V_lambda_1_@?1??DeleteIndex@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UImageEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@UTextEmbeddingsGenerator@562789@UTextEmbeddingsGenerator@implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SAXUhstring@winrt@@@Z@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@YA?A_P$$QEAV_lambda_1_@?1??DeleteIndex@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UImageEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@UTextEmbeddingsGenerator@562789@UTextEmbeddingsGenerator@implementation@562789@@0123456@SAXUhstring@6@@Z@AEBUsource_location@std@@@Z
0x180027691  nop
0x180027692  mov     rcx, [rbp+70h+var_D8]
0x180027696  mov     r8, [rbp+70h+var_D0]
0x18002769a  cmp     rcx, r8
0x18002769d  jz      short loc_1800276D0
0x18002769f  mov     r9, cs:qword_18033C360
0x1800276a6  lea     rbx, [rcx+20h]
0x1800276aa  mov     edx, [rbx]
0x1800276ac  test    edx, edx
0x1800276ae  jz      short loc_1800276C7
0x1800276b0  mov     rax, [rcx+28h]
0x1800276b4  cmp     [rax+8], r9
0x1800276b8  jnz     loc_180027769
0x1800276be  cmp     edx, 2
0x1800276c1  jnz     loc_180027769
0x1800276c7  add     rcx, 30h ; '0'
0x1800276cb  cmp     rcx, r8
0x1800276ce  jnz     short loc_1800276A6
0x1800276d0  mov     rcx, [r14+28h]; hObject
0x1800276d4  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800276d8  jz      short loc_1800276E5
0x1800276da  test    rcx, rcx
0x1800276dd  jz      short loc_1800276E5
0x1800276df  call    cs:__imp_CloseHandle
0x1800276e5  lea     rcx, [r14+8]
0x1800276e9  call    ?_Tidy_deallocate@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEAAXXZ; std::basic_string<char16_t>::_Tidy_deallocate(void)
0x1800276ee  mov     edx, 30h ; '0'
0x1800276f3  mov     rcx, r14; Block
0x1800276f6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800276fb  nop
0x1800276fc  lea     rcx, [rbp+70h+var_D8]
0x180027700  call    ??1?$vector@UDatabaseFileDeletionAttempt@SemanticIndex@asg@@V?$allocator@UDatabaseFileDeletionAttempt@SemanticIndex@asg@@@std@@@std@@QEAA@XZ; std::vector<asg::SemanticIndex::DatabaseFileDeletionAttempt>::~vector<asg::SemanticIndex::DatabaseFileDeletionAttempt>(void)
0x180027705  nop
0x180027706  lea     rcx, [rbp+70h+var_90]
0x18002770a  call    ?_Tidy_deallocate@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEAAXXZ; std::basic_string<char16_t>::_Tidy_deallocate(void)
0x18002770f  nop
0x180027710  mov     rbx, [rdi]
0x180027713  test    rbx, rbx
0x180027716  jz      short loc_180027737
0x180027718  lock xadd [rbx+18h], esi
0x18002771d  sub     esi, 1
0x180027720  jnz     short loc_18002775F
0x180027722  call    WINRT_IMPL_GetProcessHeap
0x180027727  mov     rcx, rax; hHeap
0x18002772a  mov     r8, rbx; lpMem
0x18002772d  xor     edx, edx; dwFlags
0x18002772f  call    WINRT_IMPL_HeapFree
0x180027734  mov     [rdi], r12
0x180027737  mov     rcx, [rbp+70h+var_30]
0x18002773b  xor     rcx, rsp; StackCookie
0x18002773e  call    __security_check_cookie
0x180027743  lea     r11, [rsp+170h+var_20]
0x18002774b  mov     rbx, [r11+38h]
0x18002774f  mov     rsi, [r11+40h]
0x180027753  mov     rsp, r11
0x180027756  pop     r15
0x180027758  pop     r14
0x18002775a  pop     r12
0x18002775c  pop     rdi
0x18002775d  pop     rbp
0x18002775e  retn
0x18002775f  test    esi, esi
0x180027761  js      loc_180027810
0x180027767  jmp     short loc_180027734
0x180027769  mov     [rsp+170h+var_F8], 4Ch ; 'L'
0x180027771  mov     [rbp+70h+var_F0], r15
0x180027775  mov     [rbp+70h+var_E8], r12
0x180027779  lea     rdx, [rsp+170h+var_130]
0x18002777e  call    ??B?$basic_string@_QU?$char_traits@_Q@std@@V?$allocator@_Q@2@@std@@QEBA?AV?$basic_string_view@_QU?$char_traits@_Q@std@@@1@XZ; std::basic_string<char8_t>::operator std::u8string_view(void)
0x180027783  movups  xmm0, xmmword ptr [rax]
0x180027786  movaps  [rsp+170h+var_140], xmm0
0x18002778b  lea     rdx, [rsp+170h+var_140]
0x180027790  lea     rcx, [rbp+70h+var_70]
0x180027794  call    ?utf8ToWide@asg@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_QU?$char_traits@_Q@std@@@3@@Z; asg::utf8ToWide(std::u8string_view)
0x180027799  nop
0x18002779a  mov     rcx, rax
0x18002779d  call    ?c_str@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@QEBAPEB_SXZ; std::basic_string<char16_t>::c_str(void)
0x1800277a2  mov     qword ptr [rsp+170h+var_140], rax
0x1800277a7  mov     rcx, rbx; this
0x1800277aa  call    ?value@error_code@std@@QEBAHXZ; std::error_code::value(void)
0x1800277af  mov     [rsp+170h+var_150], eax
0x1800277b3  lea     r9, [rsp+170h+var_140]
0x1800277b8  lea     r8, [rsp+170h+var_150]
0x1800277bd  lea     rdx, aCouldNotDelete; "Could not delete database file (%d) \"%"...
0x1800277c4  lea     rcx, [rbp+70h+var_50]
0x1800277c8  call    ??$wformat@HPEA_W@asg@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W$$QEAH$$QEAPEA_W@Z; asg::wformat<int,wchar_t *>(wchar_t const *,int &&,wchar_t * &&)
0x1800277cd  nop
0x1800277ce  mov     rdx, rax
0x1800277d1  lea     rcx, [rbp+70h+var_B0]
0x1800277d5  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; winrt::param::hstring::hstring(std::wstring const &)
0x1800277da  mov     edx, 83EBAD1Fh; int
0x1800277df  lea     rcx, [rsp+170h+var_148]; this
0x1800277e4  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x1800277e9  lea     r9, [rsp+170h+var_F8]
0x1800277ee  lea     r8, [rbp+70h+var_B0]
0x1800277f2  mov     edx, [rax]
0x1800277f4  lea     rcx, [rsp+170h+pExceptionObject]
0x1800277f9  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x1800277fe  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x180027805  lea     rcx, [rsp+170h+pExceptionObject]; pExceptionObject
0x18002780a  call    _CxxThrowException
0x180027810  call    abort
0x180027816  mov     [rsp+170h+var_130], 3Fh ; '?'
0x18002781e  mov     [rsp+170h+var_120], r12
0x180027823  lea     rdx, aCouldNotGetExc; "could not get exclusive access to the d"...
0x18002782a  lea     rcx, [rsp+170h+pExceptionObject]; this
0x18002782f  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x180027834  mov     edx, 83EBAD1Fh; int
0x180027839  lea     rcx, [rsp+170h+var_150]; this
0x18002783e  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x180027843  lea     r9, [rsp+170h+var_130]
0x180027848  lea     r8, [rsp+170h+pExceptionObject]
0x18002784d  mov     edx, [rax]
0x18002784f  lea     rcx, [rsp+170h+var_F8]
0x180027854  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x180027859  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x180027860  lea     rcx, [rsp+170h+var_F8]; pExceptionObject
0x180027865  call    _CxxThrowException
```
