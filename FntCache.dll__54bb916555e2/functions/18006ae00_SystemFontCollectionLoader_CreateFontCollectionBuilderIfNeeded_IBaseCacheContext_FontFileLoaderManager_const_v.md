# SystemFontCollectionLoader::CreateFontCollectionBuilderIfNeeded(IBaseCacheContext *,FontFileLoaderManager const &,void *,FontSet const *,array_ref<InstalledFontFileInfo const>,bool)

- ea: `0x18006ae00`
- end: `0x18006b372`
- name: `?CreateFontCollectionBuilderIfNeeded@SystemFontCollectionLoader@@SA?AV?$ScopedPtr@VFontCollectionBuilder@@@@PEAUIBaseCacheContext@@AEBVFontFileLoaderManager@@PEAXPEBVFontSet@@V?$array_ref@$$CBUInstalledFontFileInfo@@@@_N@Z`
- size: `1394`
- prototype: `__int64 __fastcall(int, int, int, int, FontSet *, __int64, char)`
- caller_count: `1`
- callee_count: `32`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18006abdc`

## callees

- `0x180004810`
- `0x1800091a0`
- `0x18000bc70`
- `0x18000d7ec`
- `0x180013614`
- `0x180013ad0`
- `0x180028c50`
- `0x18004ff60`
- `0x18004ff84`
- `0x18004ffa8`
- `0x18006ae00`
- `0x18006b378`
- `0x18006b5f8`
- `0x18006c20c`
- `0x18006c27c`
- `0x18006c410`
- `0x1800901c4`
- `0x18009ad40`
- `0x18009d96c`
- `0x18009fe58`
- `0x1800a36b4`
- `0x1800a5114`
- `0x1800aa650`
- `0x1800aaa58`
- `0x1800b2f6c`
- `0x1800b4760`
- `0x1800b4b9c`
- `0x1800b4bd0`
- `0x1800b81a4`
- `0x1800b9148`
- `0x1800bbdd8`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18006b101`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18006b101`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18006b239`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18006b239`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
_QWORD *__fastcall SystemFontCollectionLoader::CreateFontCollectionBuilderIfNeeded(
        FontCollectionBuilder *a1,
        __int64 a2,
        __int64 a3,
        void *a4,
        FontSet *a5,
        __int64 *a6,
        char a7)
{
  struct FontSet *v7; // r13
  unsigned __int64 v8; // r12
  __int64 v9; // rsi
  unsigned __int64 v10; // r14
  unsigned int v11; // ebx
  unsigned __int64 i; // rdi
  const struct FontSetRegion::FileEntry *FileEntryByKey; // rcx
  __int64 NonStreamedFileCount; // rdi
  _QWORD *v15; // rdi
  void *v16; // rcx
  FontCollectionBuilder *v17; // r15
  struct IDWriteFontFileLoader *v18; // rbx
  unsigned __int64 v19; // rdi
  struct IAccessCheck *v20; // r9
  __int64 v21; // r14
  unsigned __int64 v22; // rax
  __int64 ObjectFromID; // rax
  HANDLE v24; // r13
  __int64 v25; // rdi
  unsigned __int64 v26; // rdi
  struct DWrite::RefString::Data *v27; // rcx
  __int64 FontProperty; // rax
  __int128 *v29; // rdx
  __int128 v31; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v32; // [rsp+50h] [rbp-B0h]
  struct DWrite::RefString::Data *v33; // [rsp+58h] [rbp-A8h] BYREF
  FontCollectionBuilder *v34; // [rsp+60h] [rbp-A0h]
  __int128 v35; // [rsp+68h] [rbp-98h] BYREF
  __int64 v36; // [rsp+78h] [rbp-88h]
  struct IDWriteFontFileLoader *v37; // [rsp+80h] [rbp-80h] BYREF
  FontSet *v38; // [rsp+88h] [rbp-78h]
  unsigned __int64 v39; // [rsp+90h] [rbp-70h]
  _QWORD *v40; // [rsp+98h] [rbp-68h]
  __int128 v41; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v42; // [rsp+B0h] [rbp-50h]
  __int64 v43[3]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v44; // [rsp+D8h] [rbp-28h]
  char v45[8]; // [rsp+E0h] [rbp-20h] BYREF
  HANDLE hToken; // [rsp+E8h] [rbp-18h]
  HANDLE v47; // [rsp+F0h] [rbp-10h]
  __int64 v48; // [rsp+F8h] [rbp-8h]
  __int64 v49; // [rsp+100h] [rbp+0h]
  struct DWrite::RefString::Data *v50; // [rsp+108h] [rbp+8h] BYREF
  unsigned __int64 v51; // [rsp+110h] [rbp+10h]
  _BYTE v52[16]; // [rsp+118h] [rbp+18h] BYREF
  char v53[24]; // [rsp+128h] [rbp+28h] BYREF
  char v54[8]; // [rsp+140h] [rbp+40h] BYREF
  __int128 v55; // [rsp+148h] [rbp+48h] BYREF
  __int64 v56; // [rsp+158h] [rbp+58h]
  unsigned __int64 v57; // [rsp+160h] [rbp+60h]

  hToken = a4;
  v44 = a3;
  v48 = a2;
  v40 = a1;
  v34 = a1;
  v7 = a5;
  v38 = a5;
  v8 = 0;
  v9 = *a6;
  v10 = -1227133513 * (unsigned int)((a6[1] - *a6) >> 3);
  v51 = v10;
  v31 = 0;
  LODWORD(v31) = 1;
  DWORD2(v31) = v10;
  *(_OWORD *)v43 = v31;
  EventLogger::LogGenericEvent(0, 0, 0x42434677656ELL, v43, 1);
  v41 = 0;
  v42 = 0;
  std::vector<FontSetRegion::FileEntry const *>::_Construct_n<>(&v41, (unsigned int)v10);
  v31 = 0u;
  std::_Tree<std::_Tset_traits<FontFeatureCoverageRegion::ScriptLanguageFeature,std::less<FontFeatureCoverageRegion::ScriptLanguageFeature>,std::allocator<FontFeatureCoverageRegion::ScriptLanguageFeature>,0>>::_Alloc_sentinel_and_proxy(&v31);
  std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(&v35);
  if ( a5 )
  {
    v11 = 0;
    if ( v10 )
    {
      for ( i = 0; i < v10; ++i )
      {
        FileEntryByKey = FontSet::FindFileEntryByKey(
                           a5,
                           *(_QWORD *)(56 * i + v9),
                           *(const void **)(56 * i + v9 + 8),
                           *(_DWORD *)(56 * i + v9 + 16) - *(_DWORD *)(56 * i + v9 + 8));
        if ( FileEntryByKey )
        {
          *(_QWORD *)(v41 + 8 * i) = FileEntryByKey;
          ++v11;
        }
      }
    }
    NonStreamedFileCount = FontSet::GetNonStreamedFileCount(a5);
    LogEvent<unsigned int,unsigned int>(0x676E69686374616DLL, v11, NonStreamedFileCount);
    if ( !a7 && v11 == (_DWORD)v10 && v11 == (_DWORD)NonStreamedFileCount )
    {
      v15 = v40;
      *v40 = 0;
      v16 = (void *)v35;
      if ( !(_QWORD)v35 )
        goto LABEL_50;
      goto LABEL_49;
    }
    if ( v11 )
      FontSetBuilder::GetMappingOfFileEntriesToFontItems(a5);
  }
  v34 = (FontCollectionBuilder *)operator new(0x70u);
  v17 = FontCollectionBuilder::FontCollectionBuilder(v34, 0, &dword_1800EC744, 0);
  v34 = v17;
  v18 = 0;
  v37 = 0;
  v19 = 0;
  v39 = 0;
  v55 = 0;
  v56 = 0;
  v57 = 0;
  std::wstring::_Construct_empty(&v55);
  v32 = 0;
  if ( a5 )
    std::wstring::reserve(&v55, 4096);
  if ( v10 )
  {
    do
    {
      if ( *(_QWORD *)(v41 + 8 * v8) )
      {
        v43[0] = v35;
        v43[1] = v35 + 4 * ((__int64)(*((_QWORD *)&v35 + 1) - v35) >> 2);
        FontSetBuilder::AddFontFile(v17, v7, (__int64)v43);
      }
      else
      {
        v21 = 56 * v8;
        v22 = *(_QWORD *)(56 * v8 + v9);
        if ( !v18 || v19 != v22 )
        {
          ObjectFromID = FontLoaderManagerBase<IDWriteFontFileLoader,3>::GetObjectFromID(
                           v44,
                           v45,
                           *(_QWORD *)(56 * v8 + v9));
          ComPtr<IDWriteFontFileLoader>::operator=(&v37, ObjectFromID);
          ComPtr<IDWriteFontFileLoader>::~ComPtr<IDWriteFontFileLoader>(v45);
          v39 = *(_QWORD *)(v21 + v9);
          v22 = v39;
          v18 = v37;
        }
        FontFileReference::FontFileReference(
          (FontFileReference *)v52,
          *(const void **)(v21 + v9 + 8),
          *(_DWORD *)(v21 + v9 + 16) - *(_DWORD *)(v21 + v9 + 8),
          v20,
          v18,
          v22,
          0);
        if ( *(_BYTE *)(v21 + v9 + 48) )
        {
          v47 = hToken;
          v24 = hToken;
          if ( hToken && !ImpersonateLoggedOnUser(hToken) )
            LogAndThrowLastError(0x6E6F737265706D49LL, 98);
        }
        else
        {
          v24 = 0;
          v47 = 0;
        }
        v25 = *((_QWORD *)v17 + 4);
        v49 = *((_QWORD *)v17 + 3);
        FontSetBuilder::AddFontFile(v17, v52, v48, *(unsigned int *)(v21 + v9 + 32), v21 + v9 + 40);
        if ( v38 )
        {
          v26 = 0x8F5C28F5C28F5C29uLL * ((v25 - v49) >> 3);
          if ( -1030792151 * (unsigned int)((__int64)(*((_QWORD *)v17 + 4) - *((_QWORD *)v17 + 3)) >> 3) > (unsigned int)v26 )
          {
            FontSetBuilder::GetFontProperty(v17, &v33, (unsigned int)v26);
            v27 = v33;
            if ( *((_DWORD *)v33 + 1)
              || (FontProperty = FontSetBuilder::GetFontProperty(v17, &v50, (unsigned int)v26),
                  DWrite::RefString::operator=(&v33, FontProperty),
                  DWrite::RefString::DecrementRef(v50),
                  v27 = v33,
                  *((_DWORD *)v33 + 1)) )
            {
              if ( v56 + (unsigned __int64)*((unsigned int *)v27 + 1) <= 0xFFF )
              {
                if ( v56 )
                {
                  std::wstring::push_back(&v55, 59);
                  v27 = v33;
                }
                std::wstring::append(&v55, (char *)v27 + 8, *((unsigned int *)v27 + 1));
                v32 = *(_DWORD *)(v21 + v9 + 32);
                v27 = v33;
              }
            }
            DWrite::RefString::DecrementRef(v27);
          }
        }
        if ( v24 )
          RevertToSelf();
        IntrusivePtr<UniversalAccessCheck>::~IntrusivePtr<UniversalAccessCheck>(v54);
        ComPtr<IDWriteFontCollectionLoader>::~ComPtr<IDWriteFontCollectionLoader>(v53);
        ComPtr<IDWriteFontFileLoader>::~ComPtr<IDWriteFontFileLoader>(v52);
        v10 = v51;
        v7 = v38;
        v19 = v39;
      }
      ++v8;
    }
    while ( v8 < v10 );
  }
  if ( v56 )
  {
    v29 = &v55;
    if ( v57 > 7 )
      v29 = (__int128 *)v55;
    DWriteTraceLogging::LogNewFonts(v32, v29);
  }
  v34 = 0;
  v15 = v40;
  *v40 = v17;
  if ( v57 > 7 )
    std::_Deallocate<16>((void *)v55, 2 * v57 + 2);
  v56 = 0;
  v57 = 7;
  LOWORD(v55) = 0;
  if ( v18 )
    (*(void (__fastcall **)(struct IDWriteFontFileLoader *))(*(_QWORD *)v18 + 16LL))(v18);
  v16 = (void *)v35;
  if ( (_QWORD)v35 )
  {
LABEL_49:
    std::_Deallocate<16>(v16, (v36 - v35) & 0xFFFFFFFFFFFFFFFCuLL);
    v36 = 0;
    v35 = 0;
  }
LABEL_50:
  std::_Tree_val<std::_Tree_simple_types<std::pair<CompactCmapRegion::Page const * const,unsigned short>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<CompactCmapRegion::Page const * const,unsigned short>,void *>>>(
    (__int64)&v31,
    (__int64)&v31,
    *(_QWORD *)(v31 + 8));
  std::_Deallocate<16>((void *)v31, 0x30u);
  if ( (_QWORD)v41 )
    std::_Deallocate<16>((void *)v41, (v42 - v41) & 0xFFFFFFFFFFFFFFF8uLL);
  return v15;
}

```

## disassembly

```asm
0x18006ae00  mov     [rsp-8+arg_18], rbx
0x18006ae05  push    rbp
0x18006ae06  push    rsi
0x18006ae07  push    rdi
0x18006ae08  push    r12
0x18006ae0a  push    r13
0x18006ae0c  push    r14
0x18006ae0e  push    r15
0x18006ae10  lea     rbp, [rsp-70h]
0x18006ae15  sub     rsp, 170h
0x18006ae1c  mov     rax, cs:__security_cookie
0x18006ae23  xor     rax, rsp
0x18006ae26  mov     [rbp+0A0h+var_38], rax
0x18006ae2a  mov     [rbp+0A0h+hToken], r9
0x18006ae2e  mov     [rbp+0A0h+var_C8], r8
0x18006ae32  mov     [rbp+0A0h+var_A8], rdx
0x18006ae36  mov     [rbp+0A0h+var_108], rcx
0x18006ae3a  mov     [rsp+1A0h+var_140], rcx
0x18006ae3f  mov     r13, [rbp+0A0h+arg_20]
0x18006ae46  mov     [rbp+0A0h+var_118], r13
0x18006ae4a  mov     rax, [rbp+0A0h+arg_28]
0x18006ae51  xor     r12d, r12d
0x18006ae54  mov     rsi, [rax]
0x18006ae57  mov     r14, [rax+8]
0x18006ae5b  sub     r14, rsi
0x18006ae5e  sar     r14, 3
0x18006ae62  mov     rcx, 6DB6DB6DB6DB6DB7h
0x18006ae6c  imul    r14, rcx
0x18006ae70  mov     r14d, r14d
0x18006ae73  mov     [rbp+0A0h+var_90], r14
0x18006ae77  mov     r8, 42434677656Eh
0x18006ae81  xorps   xmm0, xmm0
0x18006ae84  movups  [rsp+1A0h+var_160], xmm0
0x18006ae89  lea     r15d, [r12+1]
0x18006ae8e  mov     dword ptr [rsp+1A0h+var_160], r15d
0x18006ae93  mov     dword ptr [rsp+1A0h+var_160+8], r14d
0x18006ae98  movaps  xmm0, [rsp+1A0h+var_160]
0x18006ae9d  movdqa  xmmword ptr [rbp+0A0h+var_E0], xmm0
0x18006aea2  mov     edx, r12d
0x18006aea5  mov     [rsp+1A0h+var_180], r15
0x18006aeaa  lea     r9, [rbp+0A0h+var_E0]
0x18006aeae  xor     ecx, ecx
0x18006aeb0  call    ?LogGenericEvent@EventLogger@@SAXIVEventTag@@0PEBU__MIDL___MIDL_itf_serverinterface_0000_0000_0002@@_K@Z; EventLogger::LogGenericEvent(uint,EventTag,EventTag,__MIDL___MIDL_itf_serverinterface_0000_0000_0002 const *,unsigned __int64)
0x18006aeb5  xorps   xmm0, xmm0
0x18006aeb8  movdqu  [rbp+0A0h+var_100], xmm0
0x18006aebd  mov     [rbp+0A0h+var_F0], r12
0x18006aec1  mov     edx, r14d
0x18006aec4  lea     rcx, [rbp+0A0h+var_100]
0x18006aec8  call    ??$_Construct_n@$$V@?$vector@PEBUFileEntry@FontSetRegion@@V?$allocator@PEBUFileEntry@FontSetRegion@@@std@@@std@@AEAAX_K@Z; std::vector<FontSetRegion::FileEntry const *>::_Construct_n<>(unsigned __int64)
0x18006aecd  nop
0x18006aece  mov     qword ptr [rsp+1A0h+var_160], r12
0x18006aed3  mov     qword ptr [rsp+1A0h+var_160+8], r12
0x18006aed8  lea     rcx, [rsp+1A0h+var_160]
0x18006aedd  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tset_traits@UScriptLanguageFeature@FontFeatureCoverageRegion@@U?$less@UScriptLanguageFeature@FontFeatureCoverageRegion@@@std@@V?$allocator@UScriptLanguageFeature@FontFeatureCoverageRegion@@@4@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tset_traits<FontFeatureCoverageRegion::ScriptLanguageFeature,std::less<FontFeatureCoverageRegion::ScriptLanguageFeature>,std::allocator<FontFeatureCoverageRegion::ScriptLanguageFeature>,0>>::_Alloc_sentinel_and_proxy(void)
0x18006aee2  nop
0x18006aee3  lea     rcx, [rsp+1A0h+var_138]; void *
0x18006aee8  call    ??0?$vector@V?$KeyValuePair@HVOpenTypeName@@@@V?$allocator@V?$KeyValuePair@HVOpenTypeName@@@@@std@@@std@@QEAA@XZ; std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(void)
0x18006aeed  nop
0x18006aeee  test    r13, r13
0x18006aef1  jz      loc_18006AFB2
0x18006aef7  mov     ebx, r12d
0x18006aefa  test    r14, r14
0x18006aefd  jz      short loc_18006AF3C
0x18006aeff  mov     edi, r12d
0x18006af02  imul    rdx, rdi, 38h ; '8'
0x18006af06  mov     r9d, [rdx+rsi+10h]
0x18006af0b  sub     r9d, [rdx+rsi+8]; unsigned int
0x18006af10  mov     r8, [rdx+rsi+8]; void *
0x18006af15  mov     rdx, [rdx+rsi]; unsigned __int64
0x18006af19  mov     rcx, r13; this
0x18006af1c  call    ?FindFileEntryByKey@FontSet@@QEBAPEBUFileEntry@FontSetRegion@@_KPEBXI@Z; FontSet::FindFileEntryByKey(unsigned __int64,void const *,uint)
0x18006af21  mov     rcx, rax
0x18006af24  test    rax, rax
0x18006af27  jz      short loc_18006AF34
0x18006af29  mov     rax, qword ptr [rbp+0A0h+var_100]
0x18006af2d  mov     [rax+rdi*8], rcx
0x18006af31  add     ebx, r15d
0x18006af34  add     rdi, r15
0x18006af37  cmp     rdi, r14
0x18006af3a  jb      short loc_18006AF02
0x18006af3c  mov     rcx, r13; this
0x18006af3f  call    ?GetNonStreamedFileCount@FontSet@@QEBAIXZ; FontSet::GetNonStreamedFileCount(void)
0x18006af44  mov     edi, eax
0x18006af46  mov     rcx, 676E69686374616Dh
0x18006af50  mov     r8d, eax
0x18006af53  mov     edx, ebx
0x18006af55  call    ??$LogEvent@II@@YAXVEventTag@@II@Z; LogEvent<uint,uint>(EventTag,uint,uint)
0x18006af5a  cmp     [rbp+0A0h+arg_30], r12b
0x18006af61  jnz     short loc_18006AF9C
0x18006af63  cmp     ebx, r14d
0x18006af66  jnz     short loc_18006AF9C
0x18006af68  cmp     ebx, edi
0x18006af6a  jnz     short loc_18006AF9C
0x18006af6c  mov     rdi, [rbp+0A0h+var_108]
0x18006af70  mov     [rdi], r12
0x18006af73  mov     rcx, qword ptr [rsp+1A0h+var_138]
0x18006af78  test    rcx, rcx
0x18006af7b  jz      loc_18006B307
0x18006af81  mov     rdx, [rsp+1A0h+var_128]
0x18006af86  sub     rdx, rcx
0x18006af89  and     rdx, 0FFFFFFFFFFFFFFFCh
0x18006af8d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18006af92  mov     [rsp+1A0h+var_128], r12
0x18006af97  jmp     loc_18006B2FE
0x18006af9c  test    ebx, ebx
0x18006af9e  jz      short loc_18006AFB2
0x18006afa0  lea     r8, [rsp+1A0h+var_138]
0x18006afa5  lea     rdx, [rsp+1A0h+var_160]
0x18006afaa  mov     rcx, r13; this
0x18006afad  call    ?GetMappingOfFileEntriesToFontItems@FontSetBuilder@@SAXAEBVFontSet@@AEAV?$map@PEBUFileEntry@FontSetRegion@@IU?$less@PEBUFileEntry@FontSetRegion@@@std@@V?$allocator@U?$pair@QEBUFileEntry@FontSetRegion@@I@std@@@4@@std@@AEAV?$vector@IV?$allocator@I@std@@@4@@Z; FontSetBuilder::GetMappingOfFileEntriesToFontItems(FontSet const &,std::map<FontSetRegion::FileEntry const *,uint> &,std::vector<uint> &)
0x18006afb2  mov     ecx, 70h ; 'p'; Size
0x18006afb7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006afbc  mov     [rsp+1A0h+var_140], rax
0x18006afc1  xor     r9d, r9d; unsigned int
0x18006afc4  lea     r8, dword_1800EC744; void *
0x18006afcb  xor     edx, edx; unsigned __int64
0x18006afcd  mov     rcx, rax; this
0x18006afd0  call    ??0FontCollectionBuilder@@QEAA@_KPEBXI@Z; FontCollectionBuilder::FontCollectionBuilder(unsigned __int64,void const *,uint)
0x18006afd5  mov     r15, rax
0x18006afd8  mov     [rsp+1A0h+var_140], rax
0x18006afdd  mov     rbx, r12
0x18006afe0  mov     [rbp+0A0h+var_120], rbx
0x18006afe4  mov     rdi, r12
0x18006afe7  mov     [rbp+0A0h+var_110], r12
0x18006afeb  xorps   xmm0, xmm0
0x18006afee  movups  [rbp+0A0h+var_58], xmm0
0x18006aff2  mov     [rbp+0A0h+var_48], r12
0x18006aff6  mov     [rbp+0A0h+var_40], r12
0x18006affa  lea     rcx, [rbp+0A0h+var_58]
0x18006affe  call    ?_Construct_empty@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x18006b003  nop
0x18006b004  mov     [rsp+1A0h+var_150], r12d
0x18006b009  test    r13, r13
0x18006b00c  jz      short loc_18006B01C
0x18006b00e  mov     edx, 1000h
0x18006b013  lea     rcx, [rbp+0A0h+var_58]
0x18006b017  call    ?reserve@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K@Z; std::wstring::reserve(unsigned __int64)
0x18006b01c  test    r14, r14
0x18006b01f  jz      loc_18006B273
0x18006b025  mov     rax, qword ptr [rbp+0A0h+var_100]
0x18006b029  mov     r8, [rax+r12*8]
0x18006b02d  test    r8, r8
0x18006b030  jz      short loc_18006B06D
0x18006b032  mov     rcx, qword ptr [rsp+1A0h+var_138]
0x18006b037  mov     [rbp+0A0h+var_E0], rcx
0x18006b03b  mov     rax, qword ptr [rsp+1A0h+var_138+8]
0x18006b040  sub     rax, rcx
0x18006b043  sar     rax, 2
0x18006b047  lea     rax, [rcx+rax*4]
0x18006b04b  mov     [rbp+0A0h+var_E0+8], rax
0x18006b04f  lea     rax, [rbp+0A0h+var_E0]
0x18006b053  mov     [rsp+1A0h+var_180], rax; __int64
0x18006b058  lea     r9, [rsp+1A0h+var_160]
0x18006b05d  mov     rdx, r13; struct FontSet *
0x18006b060  mov     rcx, r15; this
0x18006b063  call    ?AddFontFile@FontSetBuilder@@QEAAXAEBVFontSet@@PEBUFileEntry@FontSetRegion@@AEBV?$map@PEBUFileEntry@FontSetRegion@@IU?$less@PEBUFileEntry@FontSetRegion@@@std@@V?$allocator@U?$pair@QEBUFileEntry@FontSetRegion@@I@std@@@4@@std@@V?$array_ref@$$CBI@@@Z; FontSetBuilder::AddFontFile(FontSet const &,FontSetRegion::FileEntry const *,std::map<FontSetRegion::FileEntry const *,uint> const &,array_ref<uint const>)
0x18006b068  jmp     loc_18006B267
0x18006b06d  imul    r14, r12, 38h ; '8'
0x18006b071  mov     rax, [r14+rsi]
0x18006b075  test    rbx, rbx
0x18006b078  jz      short loc_18006B07F
0x18006b07a  cmp     rdi, rax
0x18006b07d  jz      short loc_18006B0B3
0x18006b07f  mov     r8, rax
0x18006b082  lea     rdx, [rbp+0A0h+var_C0]
0x18006b086  mov     rcx, [rbp+0A0h+var_C8]
0x18006b08a  call    ?GetObjectFromID@?$FontLoaderManagerBase@UIDWriteFontFileLoader@@$02@@QEBA?AV?$ComPtr@UIDWriteFontFileLoader@@@@_K@Z; FontLoaderManagerBase<IDWriteFontFileLoader,3>::GetObjectFromID(unsigned __int64)
0x18006b08f  mov     rdx, rax
0x18006b092  lea     rcx, [rbp+0A0h+var_120]
0x18006b096  call    ??4?$ComPtr@UIDWriteFontFileLoader@@@@QEAAAEAV0@$$QEAV0@@Z; ComPtr<IDWriteFontFileLoader>::operator=(ComPtr<IDWriteFontFileLoader> &&)
0x18006b09b  lea     rcx, [rbp+0A0h+var_C0]
0x18006b09f  call    ??1?$ComPtr@UIDWriteFontFileLoader@@@@QEAA@XZ; ComPtr<IDWriteFontFileLoader>::~ComPtr<IDWriteFontFileLoader>(void)
0x18006b0a4  mov     rdi, [r14+rsi]
0x18006b0a8  mov     [rbp+0A0h+var_110], rdi
0x18006b0ac  mov     rax, rdi
0x18006b0af  mov     rbx, [rbp+0A0h+var_120]
0x18006b0b3  mov     r8d, [r14+rsi+10h]
0x18006b0b8  sub     r8d, [r14+rsi+8]; unsigned int
0x18006b0bd  xor     edi, edi
0x18006b0bf  mov     [rsp+1A0h+var_170], rdi; struct IDWriteFontFileStream *
0x18006b0c4  mov     [rsp+1A0h+var_178], rax; unsigned __int64
0x18006b0c9  mov     [rsp+1A0h+var_180], rbx; struct IDWriteFontFileLoader *
0x18006b0ce  mov     rdx, [r14+rsi+8]; void *
0x18006b0d3  lea     rcx, [rbp+0A0h+var_88]; this
0x18006b0d7  call    ??0FontFileReference@@QEAA@PEBXIPEAVIAccessCheck@@PEAUIDWriteFontFileLoader@@_KPEAUIDWriteFontFileStream@@@Z; FontFileReference::FontFileReference(void const *,uint,IAccessCheck *,IDWriteFontFileLoader *,unsigned __int64,IDWriteFontFileStream *)
0x18006b0dc  nop
0x18006b0dd  cmp     [r14+rsi+30h], dil
0x18006b0e2  jz      short loc_18006B117
0x18006b0e4  mov     rax, [rbp+0A0h+hToken]
0x18006b0e8  mov     [rbp+0A0h+var_B0], rax
0x18006b0ec  mov     r13, rax
0x18006b0ef  test    rax, rax
0x18006b0f2  jz      short loc_18006B11E
0x18006b0f4  mov     rdi, 6E6F737265706D49h
0x18006b0fe  mov     rcx, rax; hToken
0x18006b101  call    cs:__imp_ImpersonateLoggedOnUser
0x18006b107  test    eax, eax
0x18006b109  jnz     short loc_18006B11E
0x18006b10b  lea     edx, [rax+62h]
0x18006b10e  mov     rcx, rdi
0x18006b111  call    ?LogAndThrowLastError@@YAXVEventTag@@I@Z; LogAndThrowLastError(EventTag,uint)
0x18006b117  mov     r13, rdi
0x18006b11a  mov     [rbp+0A0h+var_B0], rdi
0x18006b11e  mov     rdi, [r15+20h]
0x18006b122  mov     rax, [r15+18h]
0x18006b126  mov     [rbp+0A0h+var_A0], rax
0x18006b12a  lea     rax, [rsi+28h]
0x18006b12e  add     rax, r14
0x18006b131  mov     [rsp+1A0h+var_180], rax
0x18006b136  mov     r9d, [r14+rsi+20h]
0x18006b13b  mov     r8, [rbp+0A0h+var_A8]
0x18006b13f  lea     rdx, [rbp+0A0h+var_88]
0x18006b143  mov     rcx, r15
0x18006b146  call    ?AddFontFile@FontSetBuilder@@QEAAJAEBVFontFileReference@@PEAUIBaseCacheContext@@W4DWRITE_FONT_SOURCE_TYPE@@AEBVRefString@DWrite@@@Z; FontSetBuilder::AddFontFile(FontFileReference const &,IBaseCacheContext *,DWRITE_FONT_SOURCE_TYPE,DWrite::RefString const &)
0x18006b14b  cmp     [rbp+0A0h+var_118], 0
0x18006b150  jz      loc_18006B234
0x18006b156  sub     rdi, [rbp+0A0h+var_A0]
0x18006b15a  sar     rdi, 3
0x18006b15e  mov     rcx, 8F5C28F5C28F5C29h
0x18006b168  imul    rdi, rcx
0x18006b16c  mov     rax, [r15+20h]
0x18006b170  sub     rax, [r15+18h]
0x18006b174  sar     rax, 3
0x18006b178  imul    rax, rcx
0x18006b17c  cmp     eax, edi
0x18006b17e  jbe     loc_18006B234
0x18006b184  lea     rax, aEnUs; "en-us"
0x18006b18b  mov     [rsp+1A0h+var_180], rax
0x18006b190  mov     r8d, edi
0x18006b193  lea     rdx, [rsp+1A0h+var_148]
0x18006b198  mov     rcx, r15
0x18006b19b  call    ?GetFontProperty@FontSetBuilder@@QEAA?AVRefString@DWrite@@IW4DWRITE_FONT_PROPERTY_ID@@PEB_W@Z; FontSetBuilder::GetFontProperty(uint,DWRITE_FONT_PROPERTY_ID,wchar_t const *)
0x18006b1a0  nop
0x18006b1a1  mov     rcx, [rsp+1A0h+var_148]
0x18006b1a6  cmp     dword ptr [rcx+4], 0
0x18006b1aa  jnz     short loc_18006B1E5
0x18006b1ac  mov     [rsp+1A0h+var_180], 0
0x18006b1b5  mov     r8d, edi
0x18006b1b8  lea     rdx, [rbp+0A0h+var_98]
0x18006b1bc  mov     rcx, r15
0x18006b1bf  call    ?GetFontProperty@FontSetBuilder@@QEAA?AVRefString@DWrite@@IW4DWRITE_FONT_PROPERTY_ID@@PEB_W@Z; FontSetBuilder::GetFontProperty(uint,DWRITE_FONT_PROPERTY_ID,wchar_t const *)
0x18006b1c4  mov     rdx, rax
0x18006b1c7  lea     rcx, [rsp+1A0h+var_148]
0x18006b1cc  call    ??4RefString@DWrite@@QEAAAEAV01@AEBV01@@Z; DWrite::RefString::operator=(DWrite::RefString const &)
0x18006b1d1  mov     rcx, [rbp+0A0h+var_98]; struct DWrite::RefString::Data *
0x18006b1d5  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x18006b1da  mov     rcx, [rsp+1A0h+var_148]
0x18006b1df  cmp     dword ptr [rcx+4], 0
0x18006b1e3  jz      short loc_18006B22E
0x18006b1e5  mov     eax, [rcx+4]
0x18006b1e8  mov     rdx, [rbp+0A0h+var_48]
0x18006b1ec  add     rax, rdx
0x18006b1ef  cmp     rax, 0FFFh
0x18006b1f5  ja      short loc_18006B22E
0x18006b1f7  test    rdx, rdx
0x18006b1fa  jz      short loc_18006B20F
0x18006b1fc  mov     edx, 3Bh ; ';'
0x18006b201  lea     rcx, [rbp+0A0h+var_58]
0x18006b205  call    ?push_back@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_W@Z; std::wstring::push_back(wchar_t)
0x18006b20a  mov     rcx, [rsp+1A0h+var_148]
0x18006b20f  mov     r8d, [rcx+4]
0x18006b213  lea     rdx, [rcx+8]
0x18006b217  lea     rcx, [rbp+0A0h+var_58]
0x18006b21b  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x18006b220  mov     eax, [r14+rsi+20h]
0x18006b225  mov     [rsp+1A0h+var_150], eax
0x18006b229  mov     rcx, [rsp+1A0h+var_148]; struct DWrite::RefString::Data *
0x18006b22e  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x18006b233  nop
0x18006b234  test    r13, r13
0x18006b237  jz      short loc_18006B240
0x18006b239  call    cs:__imp_RevertToSelf
0x18006b23f  nop
0x18006b240  lea     rcx, [rbp+0A0h+var_60]
0x18006b244  call    ??1?$IntrusivePtr@VUniversalAccessCheck@@@@QEAA@XZ; IntrusivePtr<UniversalAccessCheck>::~IntrusivePtr<UniversalAccessCheck>(void)
0x18006b249  lea     rcx, [rbp+0A0h+var_78]
0x18006b24d  call    ??1?$ComPtr@UIDWriteFontCollectionLoader@@@@QEAA@XZ; ComPtr<IDWriteFontCollectionLoader>::~ComPtr<IDWriteFontCollectionLoader>(void)
0x18006b252  lea     rcx, [rbp+0A0h+var_88]
0x18006b256  call    ??1?$ComPtr@UIDWriteFontFileLoader@@@@QEAA@XZ; ComPtr<IDWriteFontFileLoader>::~ComPtr<IDWriteFontFileLoader>(void)
0x18006b25b  mov     r14, [rbp+0A0h+var_90]
0x18006b25f  mov     r13, [rbp+0A0h+var_118]
0x18006b263  mov     rdi, [rbp+0A0h+var_110]
0x18006b267  inc     r12
0x18006b26a  cmp     r12, r14
0x18006b26d  jb      loc_18006B025
0x18006b273  xor     esi, esi
0x18006b275  cmp     [rbp+0A0h+var_48], rsi
0x18006b279  jz      short loc_18006B292
0x18006b27b  lea     rdx, [rbp+0A0h+var_58]
0x18006b27f  cmp     [rbp+0A0h+var_40], 7
0x18006b284  cmova   rdx, qword ptr [rbp+0A0h+var_58]
0x18006b289  mov     ecx, [rsp+1A0h+var_150]
0x18006b28d  call    ?LogNewFonts@DWriteTraceLogging@@YAXW4DWRITE_FONT_SOURCE_TYPE@@PEB_W@Z; DWriteTraceLogging::LogNewFonts(DWRITE_FONT_SOURCE_TYPE,wchar_t const *)
0x18006b292  mov     [rsp+1A0h+var_140], rsi
0x18006b297  mov     rdi, [rbp+0A0h+var_108]
0x18006b29b  mov     [rdi], r15
0x18006b29e  mov     rdx, [rbp+0A0h+var_40]
0x18006b2a2  cmp     rdx, 7
0x18006b2a6  jbe     short loc_18006B2B9
0x18006b2a8  lea     rdx, ds:2[rdx*2]
  ... truncated ...
```
