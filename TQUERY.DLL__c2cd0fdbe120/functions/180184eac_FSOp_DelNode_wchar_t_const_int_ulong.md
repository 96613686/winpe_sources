# FSOp::DelNode(wchar_t const *,int,ulong)

- ea: `0x180184eac`
- end: `0x1801850a9`
- name: `?DelNode@FSOp@@YAHPEB_WHK@Z`
- size: `509`
- prototype: `__int64 __fastcall(FSOp *__hidden this, const wchar_t *, int, unsigned int)`
- caller_count: `3`
- callee_count: `12`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180153d40`
- `0x180184dc0`
- `0x180184eac`

## callees

- `0x18003b678`
- `0x1800763b4`
- `0x18008f4a4`
- `0x18008facc`
- `0x18012bee4`
- `0x180142e10`
- `0x1801590dc`
- `0x180184eac`
- `0x180188d90`
- `0x180189cce`
- `0x1801f95e0`
- `0x1801f9904`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018504b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018504b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180184ee9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180184f80`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180184f9d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180184ee9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180184f80`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180184f9d`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180184f55`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180184f55`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180185024`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180185024`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180185013`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180185013`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18018503f`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18018503f`

## string_xrefs

- `0x180185064`: `"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\fsutil.cxx"`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall FSOp::DelNode(const wchar_t *this, const wchar_t *a2)
{
  unsigned int v3; // ebx
  char *FirstFileW; // rsi
  unsigned int v5; // r9d
  __int64 v6; // rcx
  DWORD v8; // [rsp+20h] [rbp-338h]
  DWORD LastError; // [rsp+20h] [rbp-338h]
  char *v10; // [rsp+30h] [rbp-328h] BYREF
  const wchar_t *v11; // [rsp+38h] [rbp-320h]
  __int64 v12; // [rsp+40h] [rbp-318h]
  _BYTE v13[8]; // [rsp+50h] [rbp-308h] BYREF
  LPCWSTR lpFileName; // [rsp+58h] [rbp-300h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+F0h] [rbp-268h] BYREF

  v11 = this;
  if ( !this || (v3 = 1, !lstrcmpW(this, &psz)) )
    v3 = 0;
  if ( v3 )
  {
    memset_0(&FindFileData, 0, sizeof(FindFileData));
    try
    {
      TLMString<64,64,32767>::TLMString<64,64,32767>(v13, this);
      AppendBackSlashIf((struct CLMString *)v13);
      CLMString::Append((CLMString *)v13, L"*.*", 0xFFFFFFFF);
      v12 = 0;
      FirstFileW = (char *)FindFirstFileW(lpFileName, &FindFileData);
      v10 = FirstFileW;
      do
      {
        if ( (unsigned __int64)(FirstFileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
          break;
        if ( lstrcmpW(FindFileData.cFileName, L".") && lstrcmpW(FindFileData.cFileName, L"..") )
        {
          CLMString::operator=(v13, this);
          AppendBackSlashIf((struct CLMString *)v13);
          CLMString::Append((CLMString *)v13, FindFileData.cFileName, 0xFFFFFFFF);
          if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
          {
            FSOp::DelNode((FSOp *)lpFileName, (const wchar_t *)1, 0, v5);
          }
          else
          {
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_55368734>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_55368734>::GetImpl'::`2'::impl) )
              SearchIndexerTelemetry::IndexerMetaFileDeleted<char const (&)[14],wchar_t (&)[260]>(
                v6,
                FindFileData.cFileName);
            DeleteFileW(lpFileName);
          }
        }
      }
      while ( FindNextFileW(FirstFileW, &FindFileData) );
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v10);
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
      TLMString<64,64,32767>::~TLMString<64,64,32767>(v13);
    }
    catch ( ... )
    {
      LODWORD(v10) = 0;
      v8 = GetLastError();
      SearchIndexerTrace::Information(
        (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\common\\\\pkmutild\\\\fsutil.cxx\"",
        (const wchar_t *)0xF6,
        (unsigned int)L"[UtilFileSystem] Error delnoding '%ls'. 0x%08x",
        v11,
        v8);
      return (unsigned int)v10;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180184eac  mov     [rsp+arg_8], rbx
0x180184eb1  mov     [rsp+arg_10], rsi
0x180184eb6  push    rdi
0x180184eb7  sub     rsp, 350h
0x180184ebe  mov     rax, cs:__security_cookie
0x180184ec5  xor     rax, rsp
0x180184ec8  mov     [rsp+358h+var_18], rax
0x180184ed0  mov     rdi, rcx
0x180184ed3  mov     [rsp+358h+var_320], rcx
0x180184ed8  test    rcx, rcx
0x180184edb  jz      short loc_180184EF3
0x180184edd  mov     ebx, 1
0x180184ee2  lea     rdx, psz; lpString2
0x180184ee9  call    cs:__imp_lstrcmpW
0x180184eef  test    eax, eax
0x180184ef1  jnz     short loc_180184EF5
0x180184ef3  xor     ebx, ebx
0x180184ef5  test    ebx, ebx
0x180184ef7  jz      loc_18018507C
0x180184efd  xor     edx, edx; Val
0x180184eff  mov     r8d, 250h; Size
0x180184f05  lea     rcx, [rsp+358h+FindFileData]; void *
0x180184f0d  call    memset_0
0x180184f12  mov     rdx, rdi
0x180184f15  lea     rcx, [rsp+358h+var_308]
0x180184f1a  call    ??0?$TLMString@$0EA@$0EA@$0HPPP@@@QEAA@PEB_W@Z; TLMString<64,64,32767>::TLMString<64,64,32767>(wchar_t const *)
0x180184f1f  nop
0x180184f20  lea     rcx, [rsp+358h+var_308]; struct CLMString *
0x180184f25  call    ?AppendBackSlashIf@@YAXAEAVCLMString@@@Z; AppendBackSlashIf(CLMString &)
0x180184f2a  or      r8d, 0FFFFFFFFh; unsigned int
0x180184f2e  lea     rdx, asc_1802EFE28; "*.*"
0x180184f35  lea     rcx, [rsp+358h+var_308]; this
0x180184f3a  call    ?Append@CLMString@@QEAAHPEB_WI@Z; CLMString::Append(wchar_t const *,uint)
0x180184f3f  mov     [rsp+358h+var_318], 0
0x180184f48  lea     rdx, [rsp+358h+FindFileData]; lpFindFileData
0x180184f50  mov     rcx, [rsp+358h+lpFileName]; lpFileName
0x180184f55  call    cs:__imp_FindFirstFileW
0x180184f5b  mov     rsi, rax
0x180184f5e  mov     [rsp+358h+var_328], rax
0x180184f63  lea     rcx, [rsi-1]
0x180184f67  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180184f6b  ja      loc_180185032
0x180184f71  lea     rdx, asc_1802EC9B0; "."
0x180184f78  lea     rcx, [rsp+358h+FindFileData.cFileName]; lpString1
0x180184f80  call    cs:__imp_lstrcmpW
0x180184f86  test    eax, eax
0x180184f88  jz      loc_180185019
0x180184f8e  lea     rdx, asc_18030F500; ".."
0x180184f95  lea     rcx, [rsp+358h+FindFileData.cFileName]; lpString1
0x180184f9d  call    cs:__imp_lstrcmpW
0x180184fa3  test    eax, eax
0x180184fa5  jz      short loc_180185019
0x180184fa7  mov     rdx, rdi
0x180184faa  lea     rcx, [rsp+358h+var_308]
0x180184faf  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x180184fb4  lea     rcx, [rsp+358h+var_308]; struct CLMString *
0x180184fb9  call    ?AppendBackSlashIf@@YAXAEAVCLMString@@@Z; AppendBackSlashIf(CLMString &)
0x180184fbe  or      r8d, 0FFFFFFFFh; unsigned int
0x180184fc2  lea     rdx, [rsp+358h+FindFileData.cFileName]; wchar_t *
0x180184fca  lea     rcx, [rsp+358h+var_308]; this
0x180184fcf  call    ?Append@CLMString@@QEAAHPEB_WI@Z; CLMString::Append(wchar_t const *,uint)
0x180184fd4  test    byte ptr [rsp+358h+FindFileData.dwFileAttributes], 10h
0x180184fdc  jz      short loc_180184FF1
0x180184fde  xor     r8d, r8d; int
0x180184fe1  lea     edx, [r8+1]; wchar_t *
0x180184fe5  mov     rcx, [rsp+358h+lpFileName]; this
0x180184fea  call    ?DelNode@FSOp@@YAHPEB_WHK@Z; FSOp::DelNode(wchar_t const *,int,ulong)
0x180184fef  jmp     short loc_180185019
0x180184ff1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_55368734@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_55368734@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55368734> `wil::Feature<__WilFeatureTraits_Feature_55368734>::GetImpl(void)'::`2'::impl
0x180184ff8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_55368734@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55368734>::__private_IsEnabled(void)
0x180184ffd  test    al, al
0x180184fff  jz      short loc_18018500E
0x180185001  lea     rdx, [rsp+358h+FindFileData.cFileName]
0x180185009  call    ??$IndexerMetaFileDeleted@AEAY0O@$$CBDAEAY0BAE@_W@SearchIndexerTelemetry@@SAXAEAY0O@$$CBDAEAY0BAE@_W@Z; SearchIndexerTelemetry::IndexerMetaFileDeleted<char const (&)[14],wchar_t (&)[260]>(char const (&)[14],wchar_t (&)[260])
0x18018500e  mov     rcx, [rsp+358h+lpFileName]; lpFileName
0x180185013  call    cs:__imp_DeleteFileW
0x180185019  lea     rdx, [rsp+358h+FindFileData]; lpFindFileData
0x180185021  mov     rcx, rsi; hFindFile
0x180185024  call    cs:__imp_FindNextFileW
0x18018502a  test    eax, eax
0x18018502c  jnz     loc_180184F63
0x180185032  lea     rcx, [rsp+358h+var_328]
0x180185037  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x18018503c  mov     rcx, rdi; lpPathName
0x18018503f  call    cs:__imp_RemoveDirectoryW
0x180185045  test    eax, eax
0x180185047  jnz     short loc_180185071
0x180185049  xor     ebx, ebx
0x18018504b  call    cs:__imp_GetLastError
0x180185051  mov     [rsp+358h+var_338], eax
0x180185055  mov     r9, rdi; wchar_t *
0x180185058  lea     r8, aUtilfilesystem_1; "[UtilFileSystem] Error delnoding '%ls'."...
0x18018505f  mov     edx, 0EEh; wchar_t *
0x180185064  lea     rcx, aOnecoreuapBase_220; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x18018506b  call    ?Information@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Information(wchar_t const *,uint,wchar_t const *,...)
0x180185070  nop
0x180185071  lea     rcx, [rsp+358h+var_308]
0x180185076  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x18018507b  nop
0x18018507c  jmp     short loc_180185082
0x18018507e  mov     ebx, dword ptr [rsp+358h+var_328]
0x180185082  mov     eax, ebx
0x180185084  mov     rcx, [rsp+358h+var_18]
0x18018508c  xor     rcx, rsp; StackCookie
0x18018508f  call    __security_check_cookie
0x180185094  lea     r11, [rsp+358h+var_8]
0x18018509c  mov     rbx, [r11+18h]
0x1801850a0  mov     rsi, [r11+20h]
0x1801850a4  mov     rsp, r11
0x1801850a7  pop     rdi
0x1801850a8  retn
```
