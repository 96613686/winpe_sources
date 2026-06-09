# Brain::Brain(uint,bool,wchar_t const *,UusPackage const &)

- ea: `0x180038884`
- end: `0x180038d33`
- name: `??0Brain@@QEAA@I_NPEB_WAEBVUusPackage@@@Z`
- size: `1199`
- prototype: `Brain *__fastcall(Brain *this, int, __int64, const wchar_t *, const struct UusPackage *)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180037064`

## callees

- `0x1800089f4`
- `0x18000d660`
- `0x180028728`
- `0x180029158`
- `0x180029518`
- `0x1800295e8`
- `0x180029644`
- `0x1800296cc`
- `0x180033b4c`
- `0x1800345a0`
- `0x180035cb0`
- `0x180035fe0`
- `0x180038884`
- `0x180039398`
- `0x1800397cc`
- `0x18003cf20`
- `0x18003d23c`
- `0x18003dda4`
- `0x180047a30`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180038d00`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180038d00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038cf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038cf5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180038d08`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180038d08`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180038b3f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180038b3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038975`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038bbb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038975`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038bbb`

## pseudocode

```c
Brain *__fastcall Brain::Brain(Brain *this, int a2, __int64 a3, const wchar_t *a4, const struct UusPackage *a5)
{
  char *v6; // r15
  char *v7; // r12
  __int64 *v8; // rax
  __int64 *v9; // rdx
  __int64 v10; // rsi
  __int64 v11; // rcx
  char v12; // r14
  char *v13; // rax
  __int64 *v14; // r8
  __int64 v15; // rcx
  __int64 v16; // r8
  void *GuestOrNativeArchFolder; // rax
  const WCHAR *v18; // rcx
  void *v19; // rdx
  HANDLE FileW; // rbx
  unsigned int v21; // r8d
  const char *v22; // r9
  char IsFolderMatch; // al
  __int64 PreviewFolder; // rax
  bool v25; // zf
  char v26; // al
  __int64 *v27; // rax
  __int64 v28; // rbx
  unsigned int v29; // eax
  HINSTANCE ThisHandle; // rsi
  HMODULE v31; // r14
  DWORD LastError; // ebx
  const wchar_t *v34; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v35; // [rsp+48h] [rbp-B8h]
  LPVOID pv; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpFileName[4]; // [rsp+58h] [rbp-A8h] BYREF
  int v38; // [rsp+78h] [rbp-88h]
  _BYTE v39[32]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE *v40; // [rsp+A0h] [rbp-60h]
  const wchar_t *v41; // [rsp+A8h] [rbp-58h]
  _BYTE v42[32]; // [rsp+B0h] [rbp-50h] BYREF
  Brain *v43; // [rsp+D0h] [rbp-30h]
  char *v44; // [rsp+D8h] [rbp-28h]
  _BYTE v45[96]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v41 = a4;
  v38 = a2;
  v43 = this;
  *(_QWORD *)this = &Brain::`vftable';
  v6 = (char *)this + 8;
  v44 = (char *)this + 8;
  *((_QWORD *)this + 1) = &BrainSettings::`vftable';
  v7 = (char *)this + 16;
  web::json::value::value((Brain *)((char *)this + 16));
  v8 = &BrainSettings::_filenameJsonCloud;
  if ( (unsigned __int64)qword_180063A28 > 7 )
    v8 = (__int64 *)BrainSettings::_filenameJsonCloud;
  v34 = (const wchar_t *)v8;
  v35 = qword_180063A20;
  std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(lpFileName, &v34);
  pv = 0;
  v9 = &BrainSettings::_subdirOneSettingsRoot;
  if ( (unsigned __int64)qword_180063A08 > 7 )
    v9 = (__int64 *)BrainSettings::_subdirOneSettingsRoot;
  wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(
    &pv,
    v9);
  v10 = -1;
  v11 = -1;
  do
    ++v11;
  while ( *((_WORD *)pv + v11) );
  v34 = (const wchar_t *)pv;
  v35 = v11;
  std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v39, &v34);
  if ( pv )
    CoTaskMemFree(pv);
  std::filesystem::operator/(v6 + 16, v39, lpFileName);
  std::wstring::_Tidy_deallocate(v39);
  std::wstring::_Tidy_deallocate(lpFileName);
  v40 = v45;
  std::wstring::wstring(v45, BrainSettings::_oneSettingsFormatKeySettings);
  v12 = 1;
  v45[32] = 1;
  std::wstring::wstring(v42, v6 + 16);
  v13 = (char *)BrainSettings::Load((web::json::value *)&pv, (struct std::error_code *)v42);
  v14 = (__int64 *)(v6 + 8);
  if ( v6 + 8 != v13 )
  {
    v15 = *v14;
    *v14 = *(_QWORD *)v13;
    *(_QWORD *)v13 = v15;
  }
  if ( pv )
    (*(void (__fastcall **)(LPVOID, __int64))(*(_QWORD *)pv + 192LL))(pv, 1);
  v6[48] = BrainSettings::InitBool(v7, BrainSettings::_keyAllowP3);
  v6[49] = BrainSettings::InitBool(v7, BrainSettings::_keyAllowSxS);
  *((_DWORD *)this + 16) = v38;
  *(_OWORD *)((char *)this + 72) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  v16 = -1;
  do
    ++v16;
  while ( v41[v16] );
  std::wstring::_Construct<1,wchar_t const *>((char *)this + 72);
  std::wstring::wstring((char *)this + 104, (char *)a5 + 8);
  v34 = &qword_180050DC0;
  v35 = 0;
  std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v39, &v34);
  GuestOrNativeArchFolder = (void *)uus::Utility::GetGuestOrNativeArchFolder(v42);
  std::filesystem::operator/((char *)this + 136, GuestOrNativeArchFolder, v39);
  std::wstring::_Tidy_deallocate(v42);
  std::wstring::_Tidy_deallocate(v39);
  uus::Utility::GetHostArchFolder((char *)this + 168);
  std::wstring::wstring(v39, (char *)this + 104);
  v34 = (const wchar_t *)v39;
  std::wstring::wstring(lpFileName, v39);
  v18 = (const WCHAR *)lpFileName;
  if ( lpFileName[3] > (LPCWSTR)7 )
    v18 = lpFileName[0];
  FileW = CreateFileW(v18, 0x80000000, 7u, 0, 3u, 0x2000000u, 0);
  if ( FileW == (HANDLE)-1LL )
    wil::details::in1diag3::_Log_GetLastError(retaddr, v19, v21, v22);
  std::wstring::_Tidy_deallocate(lpFileName);
  std::wstring::_Tidy_deallocate(v39);
  *((_QWORD *)this + 26) = FileW;
  pv = 0;
  wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(
    &pv,
    L"%SystemRoot%\\uus");
  do
    ++v10;
  while ( *((_WORD *)pv + v10) );
  v34 = (const wchar_t *)pv;
  v35 = v10;
  std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(lpFileName, &v34);
  if ( pv )
    CoTaskMemFree(pv);
  IsFolderMatch = UusPackage::IsFolderMatch(a5, lpFileName);
  *((_BYTE *)this + 216) = IsFolderMatch;
  if ( IsFolderMatch
    || (PreviewFolder = Brain::GetPreviewFolder(v42),
        v25 = (unsigned __int8)UusPackage::IsFolderMatch(a5, PreviewFolder) == 0,
        v26 = 1,
        v25) )
  {
    v26 = 0;
  }
  *((_BYTE *)this + 217) = v26;
  if ( *((_BYTE *)this + 216) || v26 )
    v12 = 0;
  *((_BYTE *)this + 218) = v12;
  v27 = &Brain::_filenameDefaultAppManifest;
  if ( (unsigned __int64)qword_180063AA8 > 7 )
    v27 = (__int64 *)Brain::_filenameDefaultAppManifest;
  v34 = (const wchar_t *)v27;
  v35 = qword_180063AA0;
  std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(lpFileName, &v34);
  std::filesystem::operator/((char *)this + 224, (char *)this + 104, lpFileName);
  std::wstring::_Tidy_deallocate(lpFileName);
  UusVersion::GetString((char *)a5 + 48, (char *)this + 256);
  *((_QWORD *)this + 36) = *((_QWORD *)a5 + 7);
  *((_QWORD *)this + 37) = 0;
  *((_BYTE *)this + 392) = 0;
  *((_OWORD *)this + 25) = 0;
  *((_QWORD *)this + 50) = (*(__int64 (__fastcall **)(Brain *))(*(_QWORD *)this + 32LL))(this);
  v28 = *(_QWORD *)this;
  v29 = (*(__int64 (__fastcall **)(Brain *))(*(_QWORD *)this + 64LL))(this);
  *((_QWORD *)this + 51) = (*(__int64 (__fastcall **)(Brain *, _QWORD))(v28 + 72))(this, v29);
  Brain::GetInterface(this);
  ThisHandle = BrainUtils::GetThisHandle();
  v31 = (HMODULE)*((_QWORD *)this + 37);
  if ( v31 )
  {
    LastError = GetLastError();
    FreeLibrary(v31);
    SetLastError(LastError);
  }
  *((_QWORD *)this + 37) = ThisHandle;
  return this;
}

```

## disassembly

```asm
0x180038884  mov     [rsp-8+arg_8], rbx
0x180038889  push    rbp
0x18003888a  push    rsi
0x18003888b  push    rdi
0x18003888c  push    r12
0x18003888e  push    r13
0x180038890  push    r14
0x180038892  push    r15
0x180038894  lea     rbp, [rsp-10h]
0x180038899  sub     rsp, 110h
0x1800388a0  mov     [rbp+40h+var_98], r9
0x1800388a4  mov     [rsp+140h+var_C8], edx
0x1800388a8  mov     rdi, rcx
0x1800388ab  mov     [rbp+40h+var_70], rcx
0x1800388af  mov     r13, [rbp+40h+arg_20]
0x1800388b3  xor     ebx, ebx
0x1800388b5  lea     rax, ??_7Brain@@6B@; const Brain::`vftable'
0x1800388bc  mov     [rcx], rax
0x1800388bf  lea     r15, [rcx+8]
0x1800388c3  mov     [rbp+40h+var_68], r15
0x1800388c7  lea     rax, ??_7BrainSettings@@6B@; const BrainSettings::`vftable'
0x1800388ce  mov     [r15], rax
0x1800388d1  lea     r12, [r15+8]
0x1800388d5  mov     rcx, r12; this
0x1800388d8  call    ??0value@json@web@@QEAA@XZ; web::json::value::value(void)
0x1800388dd  nop
0x1800388de  mov     rcx, cs:qword_180063A20
0x1800388e5  lea     rax, ?_filenameJsonCloud@BrainSettings@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const BrainSettings::_filenameJsonCloud
0x1800388ec  cmp     cs:qword_180063A28, 7
0x1800388f4  cmova   rax, cs:?_filenameJsonCloud@BrainSettings@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const BrainSettings::_filenameJsonCloud
0x1800388fc  mov     [rsp+140h+var_100], rax
0x180038901  mov     [rsp+140h+var_F8], rcx
0x180038906  lea     rdx, [rsp+140h+var_100]
0x18003890b  lea     rcx, [rsp+140h+lpFileName]
0x180038910  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x180038915  nop
0x180038916  mov     [rsp+140h+pv], rbx
0x18003891b  lea     rdx, ?_subdirOneSettingsRoot@BrainSettings@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const BrainSettings::_subdirOneSettingsRoot
0x180038922  cmp     cs:qword_180063A08, 7
0x18003892a  cmova   rdx, cs:?_subdirOneSettingsRoot@BrainSettings@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const BrainSettings::_subdirOneSettingsRoot
0x180038932  lea     rcx, [rsp+140h+pv]
0x180038937  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wchar_t const *)
0x18003893c  nop
0x18003893d  mov     rax, [rsp+140h+pv]
0x180038942  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180038946  mov     rcx, rsi
0x180038949  inc     rcx
0x18003894c  cmp     [rax+rcx*2], bx
0x180038950  jnz     short loc_180038949
0x180038952  mov     [rsp+140h+var_100], rax
0x180038957  mov     [rsp+140h+var_F8], rcx
0x18003895c  lea     rdx, [rsp+140h+var_100]
0x180038961  lea     rcx, [rbp+40h+var_C0]
0x180038965  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x18003896a  nop
0x18003896b  mov     rcx, [rsp+140h+pv]; pv
0x180038970  test    rcx, rcx
0x180038973  jz      short loc_18003897C
0x180038975  call    cs:__imp_CoTaskMemFree
0x18003897b  nop
0x18003897c  lea     r8, [rsp+140h+lpFileName]; void *
0x180038981  lea     rdx, [rbp+40h+var_C0]; void *
0x180038985  lea     rcx, [r15+10h]; Src
0x180038989  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x18003898e  nop
0x18003898f  lea     rcx, [rbp+40h+var_C0]
0x180038993  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180038998  nop
0x180038999  lea     rcx, [rsp+140h+lpFileName]
0x18003899e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800389a3  lea     rax, [rbp+40h+var_60]
0x1800389a7  mov     [rbp+40h+var_A0], rax
0x1800389ab  lea     rdx, ?_oneSettingsFormatKeySettings@BrainSettings@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const BrainSettings::_oneSettingsFormatKeySettings
0x1800389b2  lea     rcx, [rbp+40h+var_60]
0x1800389b6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800389bb  mov     r14d, 1
0x1800389c1  mov     [rbp+40h+var_40], r14b
0x1800389c5  lea     rdx, [r15+10h]
0x1800389c9  lea     rcx, [rbp+40h+var_90]
0x1800389cd  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800389d2  nop
0x1800389d3  lea     r8, [rbp+40h+var_60]
0x1800389d7  lea     rdx, [rbp+40h+var_90]; struct std::error_code *
0x1800389db  lea     rcx, [rsp+140h+pv]; this
0x1800389e0  call    ?Load@BrainSettings@@CA?AVvalue@json@web@@Vpath@filesystem@std@@V?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@7@@Z; BrainSettings::Load(std::filesystem::path,std::optional<std::wstring>)
0x1800389e5  mov     rdx, rax
0x1800389e8  lea     r8, [r15+8]
0x1800389ec  cmp     r8, rax
0x1800389ef  jz      short loc_1800389FD
0x1800389f1  mov     rcx, [r8]
0x1800389f4  mov     rax, [rax]
0x1800389f7  mov     [r8], rax
0x1800389fa  mov     [rdx], rcx
0x1800389fd  mov     rcx, [rsp+140h+pv]
0x180038a02  test    rcx, rcx
0x180038a05  jz      short loc_180038A19
0x180038a07  mov     rax, [rcx]
0x180038a0a  mov     edx, r14d
0x180038a0d  mov     rax, [rax+0C0h]
0x180038a14  call    _guard_dispatch_icall
0x180038a19  lea     rdx, ?_keyAllowP3@BrainSettings@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const BrainSettings::_keyAllowP3
0x180038a20  mov     rcx, r12
0x180038a23  call    ?InitBool@BrainSettings@@CA_NAEBVvalue@json@web@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_N@Z; BrainSettings::InitBool(web::json::value const &,std::wstring const &,bool)
0x180038a28  mov     [r15+30h], al
0x180038a2c  lea     rdx, ?_keyAllowSxS@BrainSettings@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const BrainSettings::_keyAllowSxS
0x180038a33  mov     rcx, r12
0x180038a36  call    ?InitBool@BrainSettings@@CA_NAEBVvalue@json@web@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_N@Z; BrainSettings::InitBool(web::json::value const &,std::wstring const &,bool)
0x180038a3b  mov     [r15+31h], al
0x180038a3f  mov     eax, [rsp+140h+var_C8]
0x180038a43  mov     [rdi+40h], eax
0x180038a46  lea     rcx, [rdi+48h]
0x180038a4a  xorps   xmm0, xmm0
0x180038a4d  movups  xmmword ptr [rcx], xmm0
0x180038a50  xor     r15d, r15d
0x180038a53  mov     [rcx+10h], r15
0x180038a57  mov     [rcx+18h], r15
0x180038a5b  mov     r8, rsi
0x180038a5e  mov     rax, [rbp+40h+var_98]
0x180038a62  inc     r8
0x180038a65  cmp     [rax+r8*2], r15w
0x180038a6a  jnz     short loc_180038A62
0x180038a6c  mov     rdx, rax
0x180038a6f  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180038a74  nop
0x180038a75  lea     rbx, [rdi+68h]
0x180038a79  lea     rdx, [r13+8]
0x180038a7d  mov     rcx, rbx
0x180038a80  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180038a85  nop
0x180038a86  lea     rax, qword_180050DC0
0x180038a8d  mov     [rsp+140h+var_100], rax
0x180038a92  mov     [rsp+140h+var_F8], r15
0x180038a97  lea     rdx, [rsp+140h+var_100]
0x180038a9c  lea     rcx, [rbp+40h+var_C0]
0x180038aa0  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x180038aa5  nop
0x180038aa6  mov     rdx, rbx
0x180038aa9  lea     rcx, [rbp+40h+var_90]
0x180038aad  call    ?GetGuestOrNativeArchFolder@Utility@uus@@SA?AVpath@filesystem@std@@AEBV345@@Z; uus::Utility::GetGuestOrNativeArchFolder(std::filesystem::path const &)
0x180038ab2  nop
0x180038ab3  lea     rcx, [rdi+88h]; Src
0x180038aba  lea     r8, [rbp+40h+var_C0]; void *
0x180038abe  mov     rdx, rax; void *
0x180038ac1  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x180038ac6  nop
0x180038ac7  lea     rcx, [rbp+40h+var_90]
0x180038acb  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180038ad0  nop
0x180038ad1  lea     rcx, [rbp+40h+var_C0]
0x180038ad5  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180038ada  lea     rcx, [rdi+0A8h]
0x180038ae1  mov     rdx, rbx
0x180038ae4  call    ?GetHostArchFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBVpath@filesystem@4@@Z; uus::Utility::GetHostArchFolder(std::filesystem::path const &)
0x180038ae9  nop
0x180038aea  mov     rdx, rbx
0x180038aed  lea     rcx, [rbp+40h+var_C0]
0x180038af1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180038af6  lea     rax, [rbp+40h+var_C0]
0x180038afa  mov     [rsp+140h+var_100], rax
0x180038aff  lea     rdx, [rbp+40h+var_C0]
0x180038b03  lea     rcx, [rsp+140h+lpFileName]
0x180038b08  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180038b0d  lea     rcx, [rsp+140h+lpFileName]
0x180038b12  cmp     [rsp+140h+var_D0], 7
0x180038b18  cmova   rcx, [rsp+140h+lpFileName]; lpFileName
0x180038b1e  mov     [rsp+140h+hTemplateFile], r15; hTemplateFile
0x180038b23  mov     [rsp+140h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x180038b2b  mov     [rsp+140h+dwCreationDisposition], 3; dwCreationDisposition
0x180038b33  xor     r9d, r9d; lpSecurityAttributes
0x180038b36  mov     edx, 80000000h; dwDesiredAccess
0x180038b3b  lea     r8d, [r9+7]; dwShareMode
0x180038b3f  call    cs:__imp_CreateFileW
0x180038b45  mov     rbx, rax
0x180038b48  mov     rcx, [rbp+48h]; this
0x180038b4c  cmp     rax, rsi
0x180038b4f  jnz     short loc_180038B56
0x180038b51  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180038b56  lea     rcx, [rsp+140h+lpFileName]
0x180038b5b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180038b60  nop
0x180038b61  lea     rcx, [rbp+40h+var_C0]
0x180038b65  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180038b6a  mov     [rdi+0D0h], rbx
0x180038b71  mov     [rsp+140h+pv], r15
0x180038b76  lea     rdx, aSystemrootUus; "%SystemRoot%\\uus"
0x180038b7d  lea     rcx, [rsp+140h+pv]
0x180038b82  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wchar_t const *)
0x180038b87  nop
0x180038b88  mov     rax, [rsp+140h+pv]
0x180038b8d  inc     rsi
0x180038b90  cmp     [rax+rsi*2], r15w
0x180038b95  jnz     short loc_180038B8D
0x180038b97  mov     [rsp+140h+var_100], rax
0x180038b9c  mov     [rsp+140h+var_F8], rsi
0x180038ba1  lea     rdx, [rsp+140h+var_100]
0x180038ba6  lea     rcx, [rsp+140h+lpFileName]
0x180038bab  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x180038bb0  nop
0x180038bb1  mov     rcx, [rsp+140h+pv]; pv
0x180038bb6  test    rcx, rcx
0x180038bb9  jz      short loc_180038BC1
0x180038bbb  call    cs:__imp_CoTaskMemFree
0x180038bc1  lea     rdx, [rsp+140h+lpFileName]
0x180038bc6  mov     rcx, r13
0x180038bc9  call    ?IsFolderMatch@UusPackage@@QEBA_NVpath@filesystem@std@@@Z; UusPackage::IsFolderMatch(std::filesystem::path)
0x180038bce  mov     [rdi+0D8h], al
0x180038bd4  test    al, al
0x180038bd6  jnz     short loc_180038BF3
0x180038bd8  lea     rcx, [rbp+40h+var_90]
0x180038bdc  call    ?GetPreviewFolder@Brain@@CA?AVpath@filesystem@std@@XZ; Brain::GetPreviewFolder(void)
0x180038be1  mov     rdx, rax
0x180038be4  mov     rcx, r13
0x180038be7  call    ?IsFolderMatch@UusPackage@@QEBA_NVpath@filesystem@std@@@Z; UusPackage::IsFolderMatch(std::filesystem::path)
0x180038bec  test    al, al
0x180038bee  mov     al, r14b
0x180038bf1  jnz     short loc_180038BF6
0x180038bf3  mov     al, r15b
0x180038bf6  mov     [rdi+0D9h], al
0x180038bfc  cmp     [rdi+0D8h], r15b
0x180038c03  jnz     short loc_180038C09
0x180038c05  test    al, al
0x180038c07  jz      short loc_180038C0C
0x180038c09  mov     r14b, r15b
0x180038c0c  mov     [rdi+0DAh], r14b
0x180038c13  mov     rcx, cs:qword_180063AA0
0x180038c1a  lea     rax, ?_filenameDefaultAppManifest@Brain@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const Brain::_filenameDefaultAppManifest
0x180038c21  cmp     cs:qword_180063AA8, 7
0x180038c29  cmova   rax, cs:?_filenameDefaultAppManifest@Brain@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const Brain::_filenameDefaultAppManifest
0x180038c31  mov     [rsp+140h+var_100], rax
0x180038c36  mov     [rsp+140h+var_F8], rcx
0x180038c3b  lea     rdx, [rsp+140h+var_100]
0x180038c40  lea     rcx, [rsp+140h+lpFileName]
0x180038c45  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x180038c4a  nop
0x180038c4b  lea     rdx, [rdi+68h]; void *
0x180038c4f  lea     rcx, [rdi+0E0h]; Src
0x180038c56  lea     r8, [rsp+140h+lpFileName]; void *
0x180038c5b  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x180038c60  nop
0x180038c61  lea     rcx, [rsp+140h+lpFileName]
0x180038c66  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180038c6b  lea     rdx, [rdi+100h]
0x180038c72  lea     rcx, [r13+30h]
0x180038c76  call    ?GetString@UusVersion@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; UusVersion::GetString(void)
0x180038c7b  nop
0x180038c7c  mov     rax, [r13+38h]
0x180038c80  mov     [rdi+120h], rax
0x180038c87  mov     [rdi+128h], r15
0x180038c8e  mov     [rdi+188h], r15b
0x180038c95  xorps   xmm0, xmm0
0x180038c98  movups  xmmword ptr [rdi+190h], xmm0
0x180038c9f  mov     rax, [rdi]
0x180038ca2  mov     rcx, rdi
0x180038ca5  mov     rax, [rax+20h]
0x180038ca9  call    _guard_dispatch_icall
0x180038cae  mov     [rdi+190h], rax
0x180038cb5  mov     rbx, [rdi]
0x180038cb8  mov     rcx, rdi
0x180038cbb  mov     rax, [rbx+40h]
0x180038cbf  call    _guard_dispatch_icall
0x180038cc4  mov     edx, eax
0x180038cc6  mov     rcx, rdi
0x180038cc9  mov     rax, [rbx+48h]
0x180038ccd  call    _guard_dispatch_icall
0x180038cd2  mov     [rdi+198h], rax
0x180038cd9  mov     rcx, rdi; this
0x180038cdc  call    ?GetInterface@Brain@@AEAAPEAXXZ; Brain::GetInterface(void)
0x180038ce1  call    ?GetThisHandle@BrainUtils@@SAPEAUHINSTANCE__@@XZ; BrainUtils::GetThisHandle(void)
0x180038ce6  mov     rsi, rax
0x180038ce9  mov     r14, [rdi+128h]
0x180038cf0  test    r14, r14
0x180038cf3  jz      short loc_180038D0E
0x180038cf5  call    cs:__imp_GetLastError
0x180038cfb  mov     ebx, eax
0x180038cfd  mov     rcx, r14; hLibModule
0x180038d00  call    cs:__imp_FreeLibrary
0x180038d06  mov     ecx, ebx; dwErrCode
0x180038d08  call    cs:__imp_SetLastError
0x180038d0e  mov     [rdi+128h], rsi
0x180038d15  mov     rax, rdi
0x180038d18  mov     rbx, [rsp+140h+arg_8]
0x180038d20  add     rsp, 110h
0x180038d27  pop     r15
0x180038d29  pop     r14
0x180038d2b  pop     r13
0x180038d2d  pop     r12
0x180038d2f  pop     rdi
0x180038d30  pop     rsi
0x180038d31  pop     rbp
0x180038d32  retn
```
