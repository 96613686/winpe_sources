# FSOp::DelNode(wchar_t const *,int,ulong)

- ea: `0x180117204`
- end: `0x180117408`
- name: `?DelNode@FSOp@@YAHPEB_WHK@Z`
- size: `516`
- prototype: `__int64 __fastcall(const wchar_t *this, const wchar_t *)`
- caller_count: `9`
- callee_count: `12`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800e3668`
- `0x1800e419c`
- `0x1800fa9f0`
- `0x18010f910`
- `0x180116cd4`
- `0x180116eec`
- `0x180117204`
- `0x180159174`
- `0x18017bd70`

## callees

- `0x1800269b0`
- `0x180026a18`
- `0x18002751c`
- `0x180056610`
- `0x18005edc4`
- `0x18006028c`
- `0x180117204`
- `0x1801244c0`
- `0x18012540e`
- `0x180143e5c`
- `0x1801481a0`
- `0x180148ccc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801173aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801173aa`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180117241`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1801172d8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1801172f5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180117241`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1801172d8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1801172f5`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180117383`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180117383`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180117372`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180117372`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1801172ad`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1801172ad`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18011739e`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18011739e`

## string_xrefs

- `0x1801173c3`: `"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\fsutil.cxx"`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FSOp::DelNode(const wchar_t *this, const wchar_t *a2)
{
  unsigned int v3; // ebx
  char *FirstFileW; // rsi
  unsigned int v5; // r9d
  DWORD v7; // [rsp+20h] [rbp-338h]
  DWORD LastError; // [rsp+20h] [rbp-338h]
  char *v9; // [rsp+30h] [rbp-328h] BYREF
  const wchar_t *v10; // [rsp+38h] [rbp-320h]
  __int64 v11; // [rsp+40h] [rbp-318h]
  _BYTE v12[8]; // [rsp+50h] [rbp-308h] BYREF
  LPCWSTR lpFileName; // [rsp+58h] [rbp-300h]
  _WIN32_FIND_DATAW FindFileData; // [rsp+F0h] [rbp-268h] BYREF

  v10 = this;
  if ( !this || (v3 = 1, !lstrcmpW(this, (LPCWSTR)&cchOriginalDestLength)) )
    v3 = 0;
  if ( v3 )
  {
    memset_0(&FindFileData, 0, sizeof(FindFileData));
    try
    {
      TLMString<64,64,32767>::TLMString<64,64,32767>(v12, this);
      AppendBackSlashIf((struct CLMString *)v12);
      CLMString::Append((CLMString *)v12, L"*.*", 0xFFFFFFFF);
      v11 = 0;
      FirstFileW = (char *)FindFirstFileW(lpFileName, &FindFileData);
      v9 = FirstFileW;
      do
      {
        if ( (unsigned __int64)(FirstFileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
          break;
        if ( lstrcmpW(FindFileData.cFileName, L".") && lstrcmpW(FindFileData.cFileName, L"..") )
        {
          CLMString::operator=(v12, this);
          AppendBackSlashIf((struct CLMString *)v12);
          CLMString::Append((CLMString *)v12, FindFileData.cFileName, 0xFFFFFFFF);
          if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
          {
            FSOp::DelNode((FSOp *)lpFileName, (const wchar_t *)1, 0, v5);
          }
          else
          {
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_55368734>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_55368734>::GetImpl'::`2'::impl) )
              SearchIndexerTelemetry::IndexerMetaFileDeleted<char const (&)[14],wchar_t (&)[260]>(
                "FSOp::DelNode",
                FindFileData.cFileName);
            DeleteFileW(lpFileName);
          }
        }
      }
      while ( FindNextFileW(FirstFileW, &FindFileData) );
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v9);
      if ( !RemoveDirectoryW(this) )
      {
        v3 = 0;
        LastError = GetLastError();
        SearchIndexerTrace::Information(
          (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\common\\\\pkmutild\\\\fsutil.cxx\"",
          (const wchar_t *)0xEE,
          (unsigned int)L"[UtilFileSystem] Error delnoding '%ls'. 0x%08x",
          this,
          LastError);
      }
      TLMString<64,64,32767>::~TLMString<64,64,32767>(v12);
    }
    catch ( ... )
    {
      LODWORD(v9) = 0;
      v7 = GetLastError();
      SearchIndexerTrace::Information(
        (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\common\\\\pkmutild\\\\fsutil.cxx\"",
        (const wchar_t *)0xF6,
        (unsigned int)L"[UtilFileSystem] Error delnoding '%ls'. 0x%08x",
        v10,
        v7);
      return (unsigned int)v9;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180117204  mov     [rsp+arg_8], rbx
0x180117209  mov     [rsp+arg_10], rsi
0x18011720e  push    rdi
0x18011720f  sub     rsp, 350h
0x180117216  mov     rax, cs:__security_cookie
0x18011721d  xor     rax, rsp
0x180117220  mov     [rsp+358h+var_18], rax
0x180117228  mov     rdi, rcx
0x18011722b  mov     [rsp+358h+var_320], rcx
0x180117230  test    rcx, rcx
0x180117233  jz      short loc_18011724B
0x180117235  mov     ebx, 1
0x18011723a  lea     rdx, cchOriginalDestLength; lpString2
0x180117241  call    cs:__imp_lstrcmpW
0x180117247  test    eax, eax
0x180117249  jnz     short loc_18011724D
0x18011724b  xor     ebx, ebx
0x18011724d  test    ebx, ebx
0x18011724f  jz      loc_1801173DB
0x180117255  xor     edx, edx; Val
0x180117257  mov     r8d, 250h; Size
0x18011725d  lea     rcx, [rsp+358h+FindFileData]; void *
0x180117265  call    memset_0
0x18011726a  mov     rdx, rdi
0x18011726d  lea     rcx, [rsp+358h+var_308]
0x180117272  call    ??0?$TLMString@$0EA@$0EA@$0HPPP@@@QEAA@PEB_W@Z; TLMString<64,64,32767>::TLMString<64,64,32767>(wchar_t const *)
0x180117277  nop
0x180117278  lea     rcx, [rsp+358h+var_308]; struct CLMString *
0x18011727d  call    ?AppendBackSlashIf@@YAXAEAVCLMString@@@Z; AppendBackSlashIf(CLMString &)
0x180117282  or      r8d, 0FFFFFFFFh; unsigned int
0x180117286  lea     rdx, asc_180272188; "*.*"
0x18011728d  lea     rcx, [rsp+358h+var_308]; this
0x180117292  call    ?Append@CLMString@@QEAAHPEB_WI@Z; CLMString::Append(wchar_t const *,uint)
0x180117297  mov     [rsp+358h+var_318], 0
0x1801172a0  lea     rdx, [rsp+358h+FindFileData]; lpFindFileData
0x1801172a8  mov     rcx, [rsp+358h+lpFileName]; lpFileName
0x1801172ad  call    cs:__imp_FindFirstFileW
0x1801172b3  mov     rsi, rax
0x1801172b6  mov     [rsp+358h+var_328], rax
0x1801172bb  lea     rcx, [rsi-1]
0x1801172bf  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1801172c3  ja      loc_180117391
0x1801172c9  lea     rdx, Src; "."
0x1801172d0  lea     rcx, [rsp+358h+FindFileData.cFileName]; lpString1
0x1801172d8  call    cs:__imp_lstrcmpW
0x1801172de  test    eax, eax
0x1801172e0  jz      loc_180117378
0x1801172e6  lea     rdx, asc_180273264; ".."
0x1801172ed  lea     rcx, [rsp+358h+FindFileData.cFileName]; lpString1
0x1801172f5  call    cs:__imp_lstrcmpW
0x1801172fb  test    eax, eax
0x1801172fd  jz      short loc_180117378
0x1801172ff  mov     rdx, rdi
0x180117302  lea     rcx, [rsp+358h+var_308]
0x180117307  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x18011730c  lea     rcx, [rsp+358h+var_308]; struct CLMString *
0x180117311  call    ?AppendBackSlashIf@@YAXAEAVCLMString@@@Z; AppendBackSlashIf(CLMString &)
0x180117316  or      r8d, 0FFFFFFFFh; unsigned int
0x18011731a  lea     rdx, [rsp+358h+FindFileData.cFileName]; wchar_t *
0x180117322  lea     rcx, [rsp+358h+var_308]; this
0x180117327  call    ?Append@CLMString@@QEAAHPEB_WI@Z; CLMString::Append(wchar_t const *,uint)
0x18011732c  test    byte ptr [rsp+358h+FindFileData.dwFileAttributes], 10h
0x180117334  jz      short loc_180117349
0x180117336  xor     r8d, r8d; int
0x180117339  lea     edx, [r8+1]; wchar_t *
0x18011733d  mov     rcx, [rsp+358h+lpFileName]; this
0x180117342  call    ?DelNode@FSOp@@YAHPEB_WHK@Z; FSOp::DelNode(wchar_t const *,int,ulong)
0x180117347  jmp     short loc_180117378
0x180117349  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_55368734@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_55368734@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55368734> `wil::Feature<__WilFeatureTraits_Feature_55368734>::GetImpl(void)'::`2'::impl
0x180117350  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_55368734@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55368734>::__private_IsEnabled(void)
0x180117355  test    al, al
0x180117357  jz      short loc_18011736D
0x180117359  lea     rdx, [rsp+358h+FindFileData.cFileName]
0x180117361  lea     rcx, aFsopDelnode; "FSOp::DelNode"
0x180117368  call    ??$IndexerMetaFileDeleted@AEAY0O@$$CBDAEAY0BAE@_W@SearchIndexerTelemetry@@SAXAEAY0O@$$CBDAEAY0BAE@_W@Z; SearchIndexerTelemetry::IndexerMetaFileDeleted<char const (&)[14],wchar_t (&)[260]>(char const (&)[14],wchar_t (&)[260])
0x18011736d  mov     rcx, [rsp+358h+lpFileName]; lpFileName
0x180117372  call    cs:__imp_DeleteFileW
0x180117378  lea     rdx, [rsp+358h+FindFileData]; lpFindFileData
0x180117380  mov     rcx, rsi; hFindFile
0x180117383  call    cs:__imp_FindNextFileW
0x180117389  test    eax, eax
0x18011738b  jnz     loc_1801172BB
0x180117391  lea     rcx, [rsp+358h+var_328]
0x180117396  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x18011739b  mov     rcx, rdi; lpPathName
0x18011739e  call    cs:__imp_RemoveDirectoryW
0x1801173a4  test    eax, eax
0x1801173a6  jnz     short loc_1801173D0
0x1801173a8  xor     ebx, ebx
0x1801173aa  call    cs:__imp_GetLastError
0x1801173b0  mov     [rsp+358h+var_338], eax
0x1801173b4  mov     r9, rdi; wchar_t *
0x1801173b7  lea     r8, aUtilfilesystem_3; "[UtilFileSystem] Error delnoding '%ls'."...
0x1801173be  mov     edx, 0EEh; wchar_t *
0x1801173c3  lea     rcx, aOnecoreuapBase_174; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x1801173ca  call    ?Information@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Information(wchar_t const *,uint,wchar_t const *,...)
0x1801173cf  nop
0x1801173d0  lea     rcx, [rsp+358h+var_308]
0x1801173d5  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x1801173da  nop
0x1801173db  jmp     short loc_1801173E1
0x1801173dd  mov     ebx, dword ptr [rsp+358h+var_328]
0x1801173e1  mov     eax, ebx
0x1801173e3  mov     rcx, [rsp+358h+var_18]
0x1801173eb  xor     rcx, rsp; StackCookie
0x1801173ee  call    __security_check_cookie
0x1801173f3  lea     r11, [rsp+358h+var_8]
0x1801173fb  mov     rbx, [r11+18h]
0x1801173ff  mov     rsi, [r11+20h]
0x180117403  mov     rsp, r11
0x180117406  pop     rdi
0x180117407  retn
```
