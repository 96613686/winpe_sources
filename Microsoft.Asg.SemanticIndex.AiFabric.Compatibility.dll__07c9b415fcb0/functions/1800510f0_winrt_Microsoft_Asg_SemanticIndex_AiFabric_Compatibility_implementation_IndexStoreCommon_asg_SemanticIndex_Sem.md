# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::DeleteIndex(winrt::hstring)

- ea: `0x1800510f0`
- end: `0x1800513db`
- name: `?DeleteIndex@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UTextEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@U4562789@U4implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SAXUhstring@8@@Z`
- size: `747`
- prototype: `int __fastcall(volatile signed __int32 **)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180049ef0`

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
- `0x180027870`
- `0x18002b830`
- `0x18002dae0`
- `0x180046f70`
- `0x1800510f0`
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

- `KERNEL32!CloseHandle` at `0x18005124f`
- `KERNEL32!CloseHandle` at `0x18005124f`

## string_xrefs

- `0x180051393`: `could not get exclusive access to the database lock file`
- `0x1800511b2`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\IndexStoreCommon.h`
- `0x18005132d`: `Could not delete database file (%d) "%ls". `
- `0x1800511d9`: `void __cdecl winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<class asg::SemanticIndex::SemanticIndexStore,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiF`

## pseudocode

```c
int __fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::DeleteIndex(
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
        "TextEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::Te"
        "xtEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenera"
        "tor,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerato"
        "r>::DeleteIndex(struct winrt::hstring)";
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
0x1800510f0  mov     [rsp-8+arg_8], rbx
0x1800510f5  mov     [rsp-8+arg_10], rsi
0x1800510fa  push    rbp
0x1800510fb  push    rdi
0x1800510fc  push    r12
0x1800510fe  push    r14
0x180051100  push    r15
0x180051102  lea     rbp, [rsp-50h]
0x180051107  sub     rsp, 150h
0x18005110e  mov     rax, cs:__security_cookie
0x180051115  xor     rax, rsp
0x180051118  mov     [rbp+70h+var_30], rax
0x18005111c  mov     rdi, rcx
0x18005111f  mov     [rbp+70h+var_C0], rcx
0x180051123  xor     r12d, r12d
0x180051126  mov     rdx, [rcx]
0x180051129  test    rdx, rdx
0x18005112c  jz      short loc_180051134
0x18005112e  mov     rdx, [rdx+10h]
0x180051132  jmp     short loc_18005113B
0x180051134  lea     rdx, String
0x18005113b  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180051142  mov     r8, rsi
0x180051145  inc     r8
0x180051148  cmp     word ptr [rdx+r8*2], 0
0x18005114e  jnz     short loc_180051145
0x180051150  xorps   xmm0, xmm0
0x180051153  movups  [rsp+170h+pExceptionObject], xmm0
0x180051158  mov     [rsp+170h+var_108], r12
0x18005115d  mov     [rsp+170h+var_100], r12
0x180051162  lea     rcx, [rsp+170h+pExceptionObject]
0x180051167  call    ??$_Construct@$00PEB_S@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEAAXQEB_S_K@Z; std::basic_string<char16_t>::_Construct<1,char16_t const *>(char16_t const * const,unsigned __int64)
0x18005116c  lea     rdx, [rsp+170h+pExceptionObject]
0x180051171  lea     rcx, [rbp+70h+var_90]
0x180051175  call    ?AppendDbExtensionIfRequired@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@YA?AVpath@filesystem@std@@V89std@@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::AppendDbExtensionIfRequired(std::filesystem::path)
0x18005117a  nop
0x18005117b  mov     ecx, 30h ; '0'; Size
0x180051180  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180051185  mov     rbx, rax
0x180051188  mov     qword ptr [rsp+170h+var_140], rax
0x18005118d  lea     rdx, [rbp+70h+var_90]
0x180051191  lea     rcx, [rsp+170h+var_F8]
0x180051196  call    ??0?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@QEAA@AEBV01@@Z; std::basic_string<char16_t>::basic_string<char16_t>(std::basic_string<char16_t> const &)
0x18005119b  mov     r8b, 1
0x18005119e  lea     rdx, [rsp+170h+var_F8]
0x1800511a3  mov     rcx, rbx
0x1800511a6  call    ??0IndexLockFile@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@QEAA@Vpath@filesystem@std@@_N@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexLockFile::IndexLockFile(std::filesystem::path,bool)
0x1800511ab  mov     r14, rax
0x1800511ae  mov     [rbp+70h+var_B8], rax
0x1800511b2  lea     r15, aCW1SSrcSemanti_21; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x1800511b9  mov     [rsp+170h+var_128], r15
0x1800511be  cmp     qword ptr [rax+28h], 0FFFFFFFFFFFFFFFFh
0x1800511c3  jz      loc_180051386
0x1800511c9  mov     [rsp+170h+var_130], 42h ; 'B'
0x1800511d1  mov     [rsp+170h+var_12C], 1Ch
0x1800511d9  lea     rax, aVoidCdeclWinrt_13; "void __cdecl winrt::Microsoft::Asg::Sem"...
0x1800511e0  mov     [rsp+170h+var_120], rax
0x1800511e5  lea     rax, [rbp+70h+var_90]
0x1800511e9  mov     [rsp+170h+var_148], rax
0x1800511ee  lea     r8, [rsp+170h+var_130]
0x1800511f3  lea     rdx, [rsp+170h+var_148]
0x1800511f8  lea     rcx, [rbp+70h+var_D8]
0x1800511fc  call    ??$SemanticIndexCall@V_lambda_1_@?1??DeleteIndex@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UImageEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@UTextEmbeddingsGenerator@562789@UTextEmbeddingsGenerator@implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SAXUhstring@winrt@@@Z@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@YA?A_P$$QEAV_lambda_1_@?1??DeleteIndex@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UImageEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@UTextEmbeddingsGenerator@562789@UTextEmbeddingsGenerator@implementation@562789@@0123456@SAXUhstring@6@@Z@AEBUsource_location@std@@@Z
0x180051201  nop
0x180051202  mov     rcx, [rbp+70h+var_D8]
0x180051206  mov     r8, [rbp+70h+var_D0]
0x18005120a  cmp     rcx, r8
0x18005120d  jz      short loc_180051240
0x18005120f  mov     r9, cs:qword_18033C360
0x180051216  lea     rbx, [rcx+20h]
0x18005121a  mov     edx, [rbx]
0x18005121c  test    edx, edx
0x18005121e  jz      short loc_180051237
0x180051220  mov     rax, [rcx+28h]
0x180051224  cmp     [rax+8], r9
0x180051228  jnz     loc_1800512D9
0x18005122e  cmp     edx, 2
0x180051231  jnz     loc_1800512D9
0x180051237  add     rcx, 30h ; '0'
0x18005123b  cmp     rcx, r8
0x18005123e  jnz     short loc_180051216
0x180051240  mov     rcx, [r14+28h]; hObject
0x180051244  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180051248  jz      short loc_180051255
0x18005124a  test    rcx, rcx
0x18005124d  jz      short loc_180051255
0x18005124f  call    cs:__imp_CloseHandle
0x180051255  lea     rcx, [r14+8]
0x180051259  call    ?_Tidy_deallocate@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEAAXXZ; std::basic_string<char16_t>::_Tidy_deallocate(void)
0x18005125e  mov     edx, 30h ; '0'
0x180051263  mov     rcx, r14; Block
0x180051266  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005126b  nop
0x18005126c  lea     rcx, [rbp+70h+var_D8]
0x180051270  call    ??1?$vector@UDatabaseFileDeletionAttempt@SemanticIndex@asg@@V?$allocator@UDatabaseFileDeletionAttempt@SemanticIndex@asg@@@std@@@std@@QEAA@XZ; std::vector<asg::SemanticIndex::DatabaseFileDeletionAttempt>::~vector<asg::SemanticIndex::DatabaseFileDeletionAttempt>(void)
0x180051275  nop
0x180051276  lea     rcx, [rbp+70h+var_90]
0x18005127a  call    ?_Tidy_deallocate@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEAAXXZ; std::basic_string<char16_t>::_Tidy_deallocate(void)
0x18005127f  nop
0x180051280  mov     rbx, [rdi]
0x180051283  test    rbx, rbx
0x180051286  jz      short loc_1800512A7
0x180051288  lock xadd [rbx+18h], esi
0x18005128d  sub     esi, 1
0x180051290  jnz     short loc_1800512CF
0x180051292  call    WINRT_IMPL_GetProcessHeap
0x180051297  mov     rcx, rax; hHeap
0x18005129a  mov     r8, rbx; lpMem
0x18005129d  xor     edx, edx; dwFlags
0x18005129f  call    WINRT_IMPL_HeapFree
0x1800512a4  mov     [rdi], r12
0x1800512a7  mov     rcx, [rbp+70h+var_30]
0x1800512ab  xor     rcx, rsp; StackCookie
0x1800512ae  call    __security_check_cookie
0x1800512b3  lea     r11, [rsp+170h+var_20]
0x1800512bb  mov     rbx, [r11+38h]
0x1800512bf  mov     rsi, [r11+40h]
0x1800512c3  mov     rsp, r11
0x1800512c6  pop     r15
0x1800512c8  pop     r14
0x1800512ca  pop     r12
0x1800512cc  pop     rdi
0x1800512cd  pop     rbp
0x1800512ce  retn
0x1800512cf  test    esi, esi
0x1800512d1  js      loc_180051380
0x1800512d7  jmp     short loc_1800512A4
0x1800512d9  mov     [rsp+170h+var_F8], 4Ch ; 'L'
0x1800512e1  mov     [rbp+70h+var_F0], r15
0x1800512e5  mov     [rbp+70h+var_E8], r12
0x1800512e9  lea     rdx, [rsp+170h+var_130]
0x1800512ee  call    ??B?$basic_string@_QU?$char_traits@_Q@std@@V?$allocator@_Q@2@@std@@QEBA?AV?$basic_string_view@_QU?$char_traits@_Q@std@@@1@XZ; std::basic_string<char8_t>::operator std::u8string_view(void)
0x1800512f3  movups  xmm0, xmmword ptr [rax]
0x1800512f6  movaps  [rsp+170h+var_140], xmm0
0x1800512fb  lea     rdx, [rsp+170h+var_140]
0x180051300  lea     rcx, [rbp+70h+var_70]
0x180051304  call    ?utf8ToWide@asg@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_QU?$char_traits@_Q@std@@@3@@Z; asg::utf8ToWide(std::u8string_view)
0x180051309  nop
0x18005130a  mov     rcx, rax
0x18005130d  call    ?c_str@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@QEBAPEB_SXZ; std::basic_string<char16_t>::c_str(void)
0x180051312  mov     qword ptr [rsp+170h+var_140], rax
0x180051317  mov     rcx, rbx; this
0x18005131a  call    ?value@error_code@std@@QEBAHXZ; std::error_code::value(void)
0x18005131f  mov     [rsp+170h+var_150], eax
0x180051323  lea     r9, [rsp+170h+var_140]
0x180051328  lea     r8, [rsp+170h+var_150]
0x18005132d  lea     rdx, aCouldNotDelete; "Could not delete database file (%d) \"%"...
0x180051334  lea     rcx, [rbp+70h+var_50]
0x180051338  call    ??$wformat@HPEA_W@asg@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W$$QEAH$$QEAPEA_W@Z; asg::wformat<int,wchar_t *>(wchar_t const *,int &&,wchar_t * &&)
0x18005133d  nop
0x18005133e  mov     rdx, rax
0x180051341  lea     rcx, [rbp+70h+var_B0]
0x180051345  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; winrt::param::hstring::hstring(std::wstring const &)
0x18005134a  mov     edx, 83EBAD1Fh; int
0x18005134f  lea     rcx, [rsp+170h+var_148]; this
0x180051354  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x180051359  lea     r9, [rsp+170h+var_F8]
0x18005135e  lea     r8, [rbp+70h+var_B0]
0x180051362  mov     edx, [rax]
0x180051364  lea     rcx, [rsp+170h+pExceptionObject]
0x180051369  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x18005136e  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x180051375  lea     rcx, [rsp+170h+pExceptionObject]; pExceptionObject
0x18005137a  call    _CxxThrowException
0x180051380  call    abort
0x180051386  mov     [rsp+170h+var_130], 3Fh ; '?'
0x18005138e  mov     [rsp+170h+var_120], r12
0x180051393  lea     rdx, aCouldNotGetExc; "could not get exclusive access to the d"...
0x18005139a  lea     rcx, [rsp+170h+pExceptionObject]; this
0x18005139f  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x1800513a4  mov     edx, 83EBAD1Fh; int
0x1800513a9  lea     rcx, [rsp+170h+var_150]; this
0x1800513ae  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x1800513b3  lea     r9, [rsp+170h+var_130]
0x1800513b8  lea     r8, [rsp+170h+pExceptionObject]
0x1800513bd  mov     edx, [rax]
0x1800513bf  lea     rcx, [rsp+170h+var_F8]
0x1800513c4  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x1800513c9  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x1800513d0  lea     rcx, [rsp+170h+var_F8]; pExceptionObject
0x1800513d5  call    _CxxThrowException
```
