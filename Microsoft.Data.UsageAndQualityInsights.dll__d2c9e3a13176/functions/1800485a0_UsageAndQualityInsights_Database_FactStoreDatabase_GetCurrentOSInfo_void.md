# UsageAndQualityInsights::Database::FactStoreDatabase::GetCurrentOSInfo(void)

- ea: `0x1800485a0`
- end: `0x180048b17`
- name: `?GetCurrentOSInfo@FactStoreDatabase@Database@UsageAndQualityInsights@@AEAA?AUOsInfo@23@XZ`
- size: `1399`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180047688`

## callees

- `0x1800033d0`
- `0x18000eee0`
- `0x1800107b0`
- `0x180016648`
- `0x180016a6c`
- `0x180017b1c`
- `0x180020650`
- `0x18002adf0`
- `0x1800349f0`
- `0x180034f1c`
- `0x180041888`
- `0x1800485a0`
- `0x18004c3dc`
- `0x18004e180`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180048acb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180048acb`

## string_xrefs

- `0x180048662`: `Failed to get OS version from registry`
- `0x18004867a`: `onecore\base\usageandqualityinsights\service\lib\database\factstoredatabase.cpp`
- `0x180048704`: `onecore\base\usageandqualityinsights\service\lib\database\factstoredatabase.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
__int64 __fastcall UsageAndQualityInsights::Database::FactStoreDatabase::GetCurrentOSInfo(__int64 a1, __int64 a2)
{
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // r8
  char v6; // al
  _QWORD *v7; // rdi
  std::_Format_arg_index *v8; // r14
  __int64 v9; // r15
  _QWORD *v10; // rax
  _QWORD *v11; // rax
  char **v12; // rax
  char **v13; // rax
  char **v14; // rax
  const wchar_t *v15; // rcx
  const wchar_t *v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  const wchar_t *v21; // rcx
  __int64 v22; // rcx
  int v24; // [rsp+20h] [rbp-E0h]
  int v25; // [rsp+20h] [rbp-E0h]
  char *v26[2]; // [rsp+30h] [rbp-D0h] BYREF
  const wchar_t *v27; // [rsp+40h] [rbp-C0h] BYREF
  char *v28; // [rsp+48h] [rbp-B8h]
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  HKEY v30[2]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v31[3]; // [rsp+70h] [rbp-90h] BYREF
  char *v32[4]; // [rsp+88h] [rbp-78h] BYREF
  char v33; // [rsp+A8h] [rbp-58h]
  char *v34[4]; // [rsp+B0h] [rbp-50h] BYREF
  char v35; // [rsp+D0h] [rbp-30h]
  _QWORD v36[3]; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD v37[5]; // [rsp+F8h] [rbp-8h] BYREF
  char *Src[4]; // [rsp+120h] [rbp+20h] BYREF
  _QWORD v39[10]; // [rsp+140h] [rbp+40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  v37[3] = a2;
  UsageAndQualityInsightsTraceLogging::TraceLoggingInfo("GetCurrentOSInfo");
  wil::reg::open_unique_key(&hKey, v3, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion", 0);
  v30[0] = hKey;
  wil::reg::reg_view_details::reg_view_t<wil::err_exception_policy>::try_get_value<std::wstring>(
    v30,
    (__int64)v34,
    v4,
    L"LCUVer",
    0x10000006u);
  v30[0] = hKey;
  wil::reg::reg_view_details::reg_view_t<wil::err_exception_policy>::try_get_value<std::wstring>(
    v30,
    (__int64)v32,
    v5,
    L"BuildLabEx",
    0x10000006u);
  if ( !v33 || (v6 = 0, !v35) )
    v6 = 1;
  LOBYTE(v24) = v6;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x148,
    (unsigned int)"onecore\\base\\usageandqualityinsights\\service\\lib\\database\\factstoredatabase.cpp",
    (const char *)0x80004005LL,
    v24,
    (bool)"Failed to get OS version from registry",
    v26[0]);
  LOWORD(v26[0]) = 46;
  if ( !v33 )
    std::_Throw_bad_optional_access();
  UsageAndQualityInsights::Database::FactStoreDatabase::SplitString(v31, v32, v26);
  LOWORD(v26[0]) = 46;
  if ( !v35 )
    std::_Throw_bad_optional_access();
  UsageAndQualityInsights::Database::FactStoreDatabase::SplitString(v36, v34, v26);
  LOBYTE(v25) = (unsigned __int64)((__int64)(v31[1] - v31[0]) >> 5) < 5;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x14D,
    (unsigned int)"onecore\\base\\usageandqualityinsights\\service\\lib\\database\\factstoredatabase.cpp",
    (const char *)0x80004005LL,
    v25,
    (bool)"Unexpected format for OS version Id",
    v26[0]);
  LOWORD(v26[0]) = 45;
  UsageAndQualityInsights::Database::FactStoreDatabase::SplitString(v37, v31[0] + 128LL, v26);
  if ( !v33 )
    std::_Throw_bad_optional_access();
  v7 = (_QWORD *)v36[0];
  v8 = (std::_Format_arg_index *)v39;
  v9 = 3;
  do
  {
    std::_Format_arg_index::_Format_arg_index(v8);
    v8 = (std::_Format_arg_index *)((char *)v8 + 8);
    --v9;
  }
  while ( v9 );
  if ( v7[3] <= 7u )
    v10 = v7;
  else
    v10 = (_QWORD *)*v7;
  v39[3] = v10;
  v39[4] = v7[2];
  v39[0] = 0xC000000000000000uLL;
  if ( v7[7] <= 7u )
    v11 = v7 + 4;
  else
    v11 = (_QWORD *)v7[4];
  v39[5] = v11;
  v39[6] = v7[6];
  v39[1] = 0xC000000000000010uLL;
  v12 = v32;
  if ( v32[3] > (char *)7 )
    v12 = (char **)v32[0];
  v39[7] = v12;
  v39[8] = v32[2];
  v39[2] = 0xC000000000000020uLL;
  v30[0] = (HKEY)3;
  v30[1] = (HKEY)v39;
  v27 = L"{}.{}.{}";
  v28 = (char *)8;
  std::vformat<0>(Src);
  v13 = Src;
  if ( Src[3] > (char *)7 )
    v13 = (char **)Src[0];
  v27 = (const wchar_t *)v13;
  v28 = Src[2];
  to_utf8(a2, &v27);
  *(_OWORD *)(a2 + 32) = 0;
  *(_QWORD *)(a2 + 48) = 0;
  *(_QWORD *)(a2 + 56) = 0;
  std::string::_Construct<1,char const *>(a2 + 32, (const char *)&::Src, 0);
  if ( !v35 )
    std::_Throw_bad_optional_access();
  v14 = v34;
  if ( v34[3] > (char *)7 )
    v14 = (char **)v34[0];
  v27 = (const wchar_t *)v14;
  v28 = v34[2];
  to_utf8(a2 + 64, &v27);
  if ( *(_QWORD *)(v31[0] + 24LL) <= 7u )
    v15 = (const wchar_t *)v31[0];
  else
    v15 = *(const wchar_t **)v31[0];
  v27 = v15;
  v28 = *(char **)(v31[0] + 16LL);
  to_utf8(a2 + 96, &v27);
  *(_OWORD *)(a2 + 128) = 0;
  *(_QWORD *)(a2 + 144) = 0;
  *(_QWORD *)(a2 + 152) = 0;
  std::string::_Construct<1,char const *>(a2 + 128, (const char *)&::Src, 0);
  if ( *(_QWORD *)(v36[0] + 24LL) <= 7u )
    v16 = (const wchar_t *)v36[0];
  else
    v16 = *(const wchar_t **)v36[0];
  v27 = v16;
  v28 = *(char **)(v36[0] + 16LL);
  to_utf8(a2 + 160, &v27);
  if ( *(_QWORD *)(v36[0] + 56LL) <= 7u )
    v17 = v36[0] + 32LL;
  else
    v17 = *(_QWORD *)(v36[0] + 32LL);
  v27 = (const wchar_t *)v17;
  v28 = *(char **)(v36[0] + 48LL);
  to_utf8(a2 + 192, &v27);
  if ( *(_QWORD *)(v36[0] + 88LL) <= 7u )
    v18 = v36[0] + 64LL;
  else
    v18 = *(_QWORD *)(v36[0] + 64LL);
  v27 = (const wchar_t *)v18;
  v28 = *(char **)(v36[0] + 80LL);
  to_utf8(a2 + 224, &v27);
  if ( *(_QWORD *)(v31[0] + 120LL) <= 7u )
    v19 = v31[0] + 96LL;
  else
    v19 = *(_QWORD *)(v31[0] + 96LL);
  v27 = (const wchar_t *)v19;
  v28 = *(char **)(v31[0] + 112LL);
  to_utf8(a2 + 256, &v27);
  if ( *(_QWORD *)(v31[0] + 88LL) <= 7u )
    v20 = v31[0] + 64LL;
  else
    v20 = *(_QWORD *)(v31[0] + 64LL);
  v27 = (const wchar_t *)v20;
  v28 = *(char **)(v31[0] + 80LL);
  to_utf8(a2 + 288, &v27);
  if ( *(_QWORD *)(v37[0] + 24LL) <= 7u )
    v21 = (const wchar_t *)v37[0];
  else
    v21 = *(const wchar_t **)v37[0];
  v27 = v21;
  v28 = *(char **)(v37[0] + 16LL);
  to_utf8(a2 + 320, &v27);
  if ( *(_QWORD *)(v37[0] + 56LL) <= 7u )
    v22 = v37[0] + 32LL;
  else
    v22 = *(_QWORD *)(v37[0] + 32LL);
  v27 = (const wchar_t *)v22;
  v28 = *(char **)(v37[0] + 48LL);
  to_utf8(a2 + 352, &v27);
  *(_OWORD *)(a2 + 384) = 0;
  *(_QWORD *)(a2 + 400) = 0;
  *(_QWORD *)(a2 + 408) = 0;
  std::string::_Construct<1,char const *>(a2 + 384, (const char *)&::Src, 0);
  std::wstring::~wstring(Src);
  std::vector<std::wstring>::_Tidy(v37);
  std::vector<std::wstring>::_Tidy(v36);
  std::vector<std::wstring>::_Tidy(v31);
  if ( v33 )
    std::wstring::~wstring(v32);
  if ( v35 )
    std::wstring::~wstring(v34);
  if ( hKey )
    RegCloseKey(hKey);
  return a2;
}

```

## disassembly

```asm
0x1800485a0  mov     [rsp-8+arg_0], rbx
0x1800485a5  mov     [rsp-8+arg_10], rsi
0x1800485aa  push    rbp
0x1800485ab  push    rdi
0x1800485ac  push    r12
0x1800485ae  push    r14
0x1800485b0  push    r15
0x1800485b2  lea     rbp, [rsp-0A0h]
0x1800485ba  sub     rsp, 1A0h
0x1800485c1  mov     rax, cs:__security_cookie
0x1800485c8  xor     rax, rsp
0x1800485cb  mov     [rbp+0C0h+var_30], rax
0x1800485d2  mov     rbx, rdx
0x1800485d5  mov     [rbp+0C0h+var_B0], rdx
0x1800485d9  xor     r12d, r12d
0x1800485dc  lea     rcx, aGetcurrentosin; "GetCurrentOSInfo"
0x1800485e3  call    ?TraceLoggingInfo@UsageAndQualityInsightsTraceLogging@@SAXPEBDZZ; UsageAndQualityInsightsTraceLogging::TraceLoggingInfo(char const *,...)
0x1800485e8  xor     r9d, r9d
0x1800485eb  lea     r8, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800485f2  lea     rcx, [rsp+1C0h+hKey]; int
0x1800485f7  call    ?open_unique_key@reg@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@PEAUHKEY__@@PEB_WW4key_access@12@@Z; wil::reg::open_unique_key(HKEY__ *,wchar_t const *,wil::reg::key_access)
0x1800485fc  nop
0x1800485fd  mov     rax, [rsp+1C0h+hKey]
0x180048602  mov     [rsp+1C0h+var_160], rax
0x180048607  mov     edi, 10000006h
0x18004860c  mov     [rsp+1C0h+var_1A0], edi
0x180048610  lea     r9, aLcuver; "LCUVer"
0x180048617  lea     rdx, [rbp+0C0h+var_110]
0x18004861b  lea     rcx, [rsp+1C0h+var_160]
0x180048620  call    ??$try_get_value@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$reg_view_t@Uerr_exception_policy@wil@@@reg_view_details@reg@wil@@QEBA?AV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@PEB_W0K@Z; wil::reg::reg_view_details::reg_view_t<wil::err_exception_policy>::try_get_value<std::wstring>(wchar_t const *,wchar_t const *,ulong)
0x180048625  nop
0x180048626  mov     rax, [rsp+1C0h+hKey]
0x18004862b  mov     [rsp+1C0h+var_160], rax
0x180048630  mov     [rsp+1C0h+var_1A0], edi
0x180048634  lea     r9, aBuildlabex; "BuildLabEx"
0x18004863b  lea     rdx, [rbp+0C0h+var_138]
0x18004863f  lea     rcx, [rsp+1C0h+var_160]
0x180048644  call    ??$try_get_value@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$reg_view_t@Uerr_exception_policy@wil@@@reg_view_details@reg@wil@@QEBA?AV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@PEB_W0K@Z; wil::reg::reg_view_details::reg_view_t<wil::err_exception_policy>::try_get_value<std::wstring>(wchar_t const *,wchar_t const *,ulong)
0x180048649  nop
0x18004864a  cmp     [rbp+0C0h+var_118], r12b
0x18004864e  jz      short loc_180048659
0x180048650  cmp     [rbp+0C0h+var_F0], r12b
0x180048654  mov     al, r12b
0x180048657  jnz     short loc_18004865B
0x180048659  mov     al, 1
0x18004865b  mov     rcx, [rbp+0C8h]; this
0x180048662  lea     rdx, aFailedToGetOsV; "Failed to get OS version from registry"
0x180048669  mov     qword ptr [rsp+1C0h+var_198], rdx; bool
0x18004866e  mov     byte ptr [rsp+1C0h+var_1A0], al; int
0x180048672  mov     esi, 80004005h
0x180048677  mov     r9d, esi; char *
0x18004867a  lea     r8, aOnecoreBaseUsa_3; "onecore\\base\\usageandqualityinsights"...
0x180048681  mov     edx, 148h; void *
0x180048686  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18004868b  mov     edi, 2Eh ; '.'
0x180048690  mov     word ptr [rsp+1C0h+var_190], di
0x180048695  cmp     [rbp+0C0h+var_118], r12b
0x180048699  jz      loc_180048B05
0x18004869f  lea     r8, [rsp+1C0h+var_190]
0x1800486a4  lea     rdx, [rbp+0C0h+var_138]
0x1800486a8  lea     rcx, [rsp+1C0h+var_150]
0x1800486ad  call    ?SplitString@FactStoreDatabase@Database@UsageAndQualityInsights@@CA?AV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@AEB_W@Z; UsageAndQualityInsights::Database::FactStoreDatabase::SplitString(std::wstring const &,wchar_t const &)
0x1800486b2  nop
0x1800486b3  mov     word ptr [rsp+1C0h+var_190], di; char *
0x1800486b8  cmp     [rbp+0C0h+var_F0], r12b
0x1800486bc  jz      loc_180048B0B
0x1800486c2  lea     r8, [rsp+1C0h+var_190]
0x1800486c7  lea     rdx, [rbp+0C0h+var_110]
0x1800486cb  lea     rcx, [rbp+0C0h+var_E0]
0x1800486cf  call    ?SplitString@FactStoreDatabase@Database@UsageAndQualityInsights@@CA?AV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@AEB_W@Z; UsageAndQualityInsights::Database::FactStoreDatabase::SplitString(std::wstring const &,wchar_t const &)
0x1800486d4  nop
0x1800486d5  mov     rax, [rsp+1C0h+var_148]
0x1800486da  sub     rax, [rsp+1C0h+var_150]
0x1800486df  sar     rax, 5
0x1800486e3  cmp     rax, 5
0x1800486e7  setb    al
0x1800486ea  mov     rcx, [rbp+0C8h]; this
0x1800486f1  lea     rdx, aUnexpectedForm; "Unexpected format for OS version Id"
0x1800486f8  mov     qword ptr [rsp+1C0h+var_198], rdx; bool
0x1800486fd  mov     byte ptr [rsp+1C0h+var_1A0], al; int
0x180048701  mov     r9d, esi; char *
0x180048704  lea     r8, aOnecoreBaseUsa_3; "onecore\\base\\usageandqualityinsights"...
0x18004870b  mov     edx, 14Dh; void *
0x180048710  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180048715  lea     eax, [rdi-1]
0x180048718  mov     word ptr [rsp+1C0h+var_190], ax
0x18004871d  mov     rdx, [rsp+1C0h+var_150]
0x180048722  sub     rdx, 0FFFFFFFFFFFFFF80h
0x180048726  lea     r8, [rsp+1C0h+var_190]
0x18004872b  lea     rcx, [rbp+0C0h+var_C8]
0x18004872f  call    ?SplitString@FactStoreDatabase@Database@UsageAndQualityInsights@@CA?AV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@AEB_W@Z; UsageAndQualityInsights::Database::FactStoreDatabase::SplitString(std::wstring const &,wchar_t const &)
0x180048734  nop
0x180048735  cmp     [rbp+0C0h+var_118], r12b
0x180048739  jz      loc_180048B11
0x18004873f  mov     rdi, [rbp+0C0h+var_E0]
0x180048743  lea     r14, [rbp+0C0h+var_80]
0x180048747  mov     r15d, 3
0x18004874d  mov     rcx, r14; this
0x180048750  call    ??0_Format_arg_index@std@@QEAA@XZ; std::_Format_arg_index::_Format_arg_index(void)
0x180048755  add     r14, 8
0x180048759  sub     r15, 1
0x18004875d  jnz     short loc_18004874D
0x18004875f  lea     r14d, [r15+7]
0x180048763  cmp     [rdi+18h], r14
0x180048767  jbe     short loc_18004876E
0x180048769  mov     rax, [rdi]
0x18004876c  jmp     short loc_180048771
0x18004876e  mov     rax, rdi
0x180048771  mov     [rbp+0C0h+var_68], rax
0x180048775  mov     rax, [rdi+10h]
0x180048779  mov     [rbp+0C0h+var_60], rax
0x18004877d  mov     rax, 0C000000000000000h
0x180048787  mov     [rbp+0C0h+var_80], rax
0x18004878b  cmp     [rdi+38h], r14
0x18004878f  jbe     short loc_180048797
0x180048791  mov     rax, [rdi+20h]
0x180048795  jmp     short loc_18004879B
0x180048797  lea     rax, [rdi+20h]
0x18004879b  mov     [rbp+0C0h+var_58], rax
0x18004879f  mov     rax, [rdi+30h]
0x1800487a3  mov     [rbp+0C0h+var_50], rax
0x1800487a7  mov     rax, 0C000000000000010h
0x1800487b1  mov     [rbp+0C0h+var_78], rax
0x1800487b5  lea     rax, [rbp+0C0h+var_138]
0x1800487b9  cmp     [rbp+0C0h+var_120], r14
0x1800487bd  cmova   rax, [rbp+0C0h+var_138]
0x1800487c2  mov     [rbp+0C0h+var_48], rax
0x1800487c6  mov     rax, [rbp+0C0h+var_128]
0x1800487ca  mov     [rbp+0C0h+var_40], rax
0x1800487d1  mov     rax, 0C000000000000020h
0x1800487db  mov     [rbp+0C0h+var_70], rax
0x1800487df  mov     [rsp+1C0h+var_160], 3
0x1800487e8  lea     rax, [rbp+0C0h+var_80]
0x1800487ec  mov     [rsp+1C0h+var_158], rax
0x1800487f1  lea     rax, asc_180133530; "{}.{}.{}"
0x1800487f8  mov     [rsp+1C0h+var_180], rax
0x1800487fd  mov     [rsp+1C0h+var_178], 8
0x180048806  lea     r8, [rsp+1C0h+var_160]
0x18004880b  lea     rdx, [rsp+1C0h+var_180]
0x180048810  lea     rcx, [rbp+0C0h+Src]; Src
0x180048814  call    ??$vformat@$0A@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@V?$basic_string_view@_WU?$char_traits@_W@std@@@0@V?$basic_format_args@V?$basic_format_context@V?$back_insert_iterator@V?$_Fmt_buffer@_W@std@@@std@@_W@std@@@0@@Z; std::vformat<0>(std::wstring_view,std::basic_format_args<std::basic_format_context<std::back_insert_iterator<std::_Fmt_buffer<wchar_t>>,wchar_t>>)
0x180048819  nop
0x18004881a  lea     rax, [rbp+0C0h+Src]
0x18004881e  cmp     [rbp+0C0h+var_88], r14
0x180048822  cmova   rax, [rbp+0C0h+Src]
0x180048827  mov     [rsp+1C0h+var_180], rax
0x18004882c  mov     rax, [rbp+0C0h+var_90]
0x180048830  mov     [rsp+1C0h+var_178], rax
0x180048835  lea     rdx, [rsp+1C0h+var_180]
0x18004883a  mov     rcx, rbx
0x18004883d  call    ?to_utf8@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@2@@Z; to_utf8(std::wstring_view)
0x180048842  nop
0x180048843  lea     rcx, [rbx+20h]
0x180048847  xorps   xmm0, xmm0
0x18004884a  movups  xmmword ptr [rcx], xmm0
0x18004884d  mov     [rcx+10h], r12
0x180048851  mov     [rcx+18h], r12
0x180048855  xor     r8d, r8d
0x180048858  lea     rdi, Src
0x18004885f  mov     rdx, rdi
0x180048862  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180048867  nop
0x180048868  cmp     [rbp+0C0h+var_F0], r12b
0x18004886c  jz      loc_180048AFF
0x180048872  lea     rax, [rbp+0C0h+var_110]
0x180048876  cmp     [rbp+0C0h+var_F8], r14
0x18004887a  cmova   rax, [rbp+0C0h+var_110]
0x18004887f  mov     [rsp+1C0h+var_180], rax
0x180048884  mov     rax, [rbp+0C0h+var_100]
0x180048888  mov     [rsp+1C0h+var_178], rax
0x18004888d  lea     rcx, [rbx+40h]
0x180048891  lea     rdx, [rsp+1C0h+var_180]
0x180048896  call    ?to_utf8@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@2@@Z; to_utf8(std::wstring_view)
0x18004889b  nop
0x18004889c  mov     rax, [rsp+1C0h+var_150]
0x1800488a1  cmp     [rax+18h], r14
0x1800488a5  jbe     short loc_1800488AC
0x1800488a7  mov     rcx, [rax]
0x1800488aa  jmp     short loc_1800488AF
0x1800488ac  mov     rcx, rax
0x1800488af  mov     [rsp+1C0h+var_180], rcx
0x1800488b4  mov     rax, [rax+10h]
0x1800488b8  mov     [rsp+1C0h+var_178], rax
0x1800488bd  lea     rcx, [rbx+60h]
0x1800488c1  lea     rdx, [rsp+1C0h+var_180]
0x1800488c6  call    ?to_utf8@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@2@@Z; to_utf8(std::wstring_view)
0x1800488cb  nop
0x1800488cc  lea     rcx, [rbx+80h]
0x1800488d3  xorps   xmm0, xmm0
0x1800488d6  movups  xmmword ptr [rcx], xmm0
0x1800488d9  mov     [rcx+10h], r12
0x1800488dd  mov     [rcx+18h], r12
0x1800488e1  xor     r8d, r8d
0x1800488e4  mov     rdx, rdi
0x1800488e7  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800488ec  nop
0x1800488ed  mov     rax, [rbp+0C0h+var_E0]
0x1800488f1  cmp     [rax+18h], r14
0x1800488f5  jbe     short loc_1800488FC
0x1800488f7  mov     rcx, [rax]
0x1800488fa  jmp     short loc_1800488FF
0x1800488fc  mov     rcx, rax
0x1800488ff  mov     [rsp+1C0h+var_180], rcx
0x180048904  mov     rax, [rax+10h]
0x180048908  mov     [rsp+1C0h+var_178], rax
0x18004890d  lea     rcx, [rbx+0A0h]
0x180048914  lea     rdx, [rsp+1C0h+var_180]
0x180048919  call    ?to_utf8@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@2@@Z; to_utf8(std::wstring_view)
0x18004891e  nop
0x18004891f  mov     rax, [rbp+0C0h+var_E0]
0x180048923  cmp     [rax+38h], r14
0x180048927  jbe     short loc_18004892F
0x180048929  mov     rcx, [rax+20h]
0x18004892d  jmp     short loc_180048933
0x18004892f  lea     rcx, [rax+20h]
0x180048933  mov     [rsp+1C0h+var_180], rcx
0x180048938  mov     rax, [rax+30h]
0x18004893c  mov     [rsp+1C0h+var_178], rax
0x180048941  lea     rcx, [rbx+0C0h]
0x180048948  lea     rdx, [rsp+1C0h+var_180]
0x18004894d  call    ?to_utf8@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@2@@Z; to_utf8(std::wstring_view)
0x180048952  nop
0x180048953  mov     rax, [rbp+0C0h+var_E0]
0x180048957  cmp     [rax+58h], r14
0x18004895b  jbe     short loc_180048963
0x18004895d  mov     rcx, [rax+40h]
0x180048961  jmp     short loc_180048967
0x180048963  lea     rcx, [rax+40h]
0x180048967  mov     [rsp+1C0h+var_180], rcx
0x18004896c  mov     rax, [rax+50h]
0x180048970  mov     [rsp+1C0h+var_178], rax
0x180048975  lea     rcx, [rbx+0E0h]
0x18004897c  lea     rdx, [rsp+1C0h+var_180]
0x180048981  call    ?to_utf8@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@2@@Z; to_utf8(std::wstring_view)
0x180048986  nop
0x180048987  mov     rax, [rsp+1C0h+var_150]
0x18004898c  cmp     [rax+78h], r14
0x180048990  jbe     short loc_180048998
0x180048992  mov     rcx, [rax+60h]
0x180048996  jmp     short loc_18004899C
0x180048998  lea     rcx, [rax+60h]
0x18004899c  mov     [rsp+1C0h+var_180], rcx
0x1800489a1  mov     rax, [rax+70h]
0x1800489a5  mov     [rsp+1C0h+var_178], rax
0x1800489aa  lea     rcx, [rbx+100h]
0x1800489b1  lea     rdx, [rsp+1C0h+var_180]
0x1800489b6  call    ?to_utf8@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@2@@Z; to_utf8(std::wstring_view)
0x1800489bb  nop
0x1800489bc  mov     rax, [rsp+1C0h+var_150]
0x1800489c1  cmp     [rax+58h], r14
0x1800489c5  jbe     short loc_1800489CD
0x1800489c7  mov     rcx, [rax+40h]
0x1800489cb  jmp     short loc_1800489D1
0x1800489cd  lea     rcx, [rax+40h]
0x1800489d1  mov     [rsp+1C0h+var_180], rcx
0x1800489d6  mov     rax, [rax+50h]
0x1800489da  mov     [rsp+1C0h+var_178], rax
0x1800489df  lea     rcx, [rbx+120h]
0x1800489e6  lea     rdx, [rsp+1C0h+var_180]
0x1800489eb  call    ?to_utf8@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@2@@Z; to_utf8(std::wstring_view)
0x1800489f0  nop
0x1800489f1  mov     rax, [rbp+0C0h+var_C8]
0x1800489f5  cmp     [rax+18h], r14
0x1800489f9  jbe     short loc_180048A00
0x1800489fb  mov     rcx, [rax]
0x1800489fe  jmp     short loc_180048A03
0x180048a00  mov     rcx, rax
0x180048a03  mov     [rsp+1C0h+var_180], rcx
0x180048a08  mov     rax, [rax+10h]
0x180048a0c  mov     [rsp+1C0h+var_178], rax
0x180048a11  lea     rcx, [rbx+140h]
0x180048a18  lea     rdx, [rsp+1C0h+var_180]
0x180048a1d  call    ?to_utf8@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@2@@Z; to_utf8(std::wstring_view)
0x180048a22  nop
0x180048a23  mov     rax, [rbp+0C0h+var_C8]
0x180048a27  cmp     [rax+38h], r14
0x180048a2b  jbe     short loc_180048A33
0x180048a2d  mov     rcx, [rax+20h]
0x180048a31  jmp     short loc_180048A37
0x180048a33  lea     rcx, [rax+20h]
0x180048a37  mov     [rsp+1C0h+var_180], rcx
0x180048a3c  mov     rax, [rax+30h]
0x180048a40  mov     [rsp+1C0h+var_178], rax
0x180048a45  lea     rcx, [rbx+160h]
0x180048a4c  lea     rdx, [rsp+1C0h+var_180]
0x180048a51  call    ?to_utf8@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@2@@Z; to_utf8(std::wstring_view)
0x180048a56  nop
0x180048a57  lea     rcx, [rbx+180h]
0x180048a5e  xorps   xmm0, xmm0
0x180048a61  movups  xmmword ptr [rcx], xmm0
0x180048a64  mov     [rcx+10h], r12
0x180048a68  mov     [rcx+18h], r12
0x180048a6c  xor     r8d, r8d
0x180048a6f  mov     rdx, rdi
0x180048a72  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180048a77  nop
0x180048a78  lea     rcx, [rbp+0C0h+Src]; void *
0x180048a7c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180048a81  nop
0x180048a82  lea     rcx, [rbp+0C0h+var_C8]
  ... truncated ...
```
