# ConnectedStorage::Contexts::GetSpaceInfoFromDirectoryName(ushort const *,ushort *,XblGameSaveProviderInfo *)

- ea: `0x18003373c`
- end: `0x180033a43`
- name: `?GetSpaceInfoFromDirectoryName@Contexts@ConnectedStorage@@AEBA_NPEBGPEAGPEAUXblGameSaveProviderInfo@@@Z`
- size: `775`
- prototype: `bool(ConnectedStorage::Contexts *__hidden this, const unsigned __int16 *, unsigned __int16 *, struct XblGameSaveProviderInfo *)`
- caller_count: `1`
- callee_count: `26`
- tags: `service_task, broker_com_uri`

## callers

- `0x180033414`

## callees

- `0x180003c70`
- `0x18000aae4`
- `0x18000b5b8`
- `0x180010e30`
- `0x1800113bc`
- `0x1800125ec`
- `0x180012fc0`
- `0x180012ff8`
- `0x180013018`
- `0x18001c090`
- `0x18001c2a8`
- `0x18001c63c`
- `0x18001d89c`
- `0x18002a714`
- `0x18003089c`
- `0x180031360`
- `0x1800313e4`
- `0x1800335fc`
- `0x18003373c`
- `0x180033a4c`
- `0x1800510a0`
- `0x1800555f0`
- `0x18005cab4`
- `0x1800647c0`
- `0x180064ba4`
- `0x180064c00`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800338a9`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800338a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800339c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800339c1`

## string_xrefs

- `0x180033889`: `StringCchCopyW(indexPath, MAX_PATH, filename)`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
bool __fastcall ConnectedStorage::Contexts::GetSpaceInfoFromDirectoryName(
        ConnectedStorage::Contexts *this,
        const unsigned __int16 *a2,
        ConnectedStorage *a3,
        struct XblGameSaveProviderInfo *a4)
{
  char *v8; // rbx
  __int64 v9; // rcx
  _QWORD *v10; // rax
  __int64 v11; // r8
  __int64 v12; // rax
  __int64 v14; // rax
  __int64 v15; // rdx
  ConnectedStorage::ActivatingContext **v16; // rcx
  bool ProviderInfo; // al
  bool v18; // bl
  ConnectedStorage::Context **v20; // rcx
  int v21; // eax
  const unsigned __int16 *v22; // r8
  __int64 v23; // r11
  unsigned int v24; // r8d
  bool result; // al
  ConnectedStorage::ContainerIndex *v26; // [rsp+20h] [rbp-358h] BYREF
  HSTRING v27; // [rsp+28h] [rbp-350h] BYREF
  _BYTE v28[8]; // [rsp+30h] [rbp-348h] BYREF
  __int128 v29; // [rsp+38h] [rbp-340h] BYREF
  __int128 v30; // [rsp+48h] [rbp-330h] BYREF
  __int64 v31; // [rsp+58h] [rbp-320h]
  int v32; // [rsp+60h] [rbp-318h]
  char v33; // [rsp+64h] [rbp-314h]
  ConnectedStorage *v34; // [rsp+68h] [rbp-310h]
  _BYTE v35[8]; // [rsp+70h] [rbp-308h] BYREF
  __int64 v36; // [rsp+78h] [rbp-300h] BYREF
  HSTRING string; // [rsp+88h] [rbp-2F0h]
  HSTRING v38[6]; // [rsp+98h] [rbp-2E0h] BYREF
  _BYTE v39[40]; // [rsp+C8h] [rbp-2B0h] BYREF
  _DWORD v40[16]; // [rsp+F0h] [rbp-288h] BYREF
  unsigned __int16 v41[264]; // [rsp+130h] [rbp-248h] BYREF

  v34 = a3;
  *(_OWORD *)a4 = 0;
  *((_OWORD *)a4 + 1) = 0;
  *((_OWORD *)a4 + 2) = 0;
  *((_QWORD *)a4 + 6) = 0;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  v33 = 1;
  if ( !ConnectedStorage::ContextDesc::TryGetContextDescFromDirectoryName(
          (unsigned __int16 *)a3,
          (HSTRING *)&v29,
          (const unsigned __int16 *)a3)
    || v33 )
  {
    v18 = 0;
    goto LABEL_16;
  }
  ConnectedStorage::ContextDesc::ContextDesc(v38, (const struct ConnectedStorage::ContextDesc *)&v29);
  v8 = (char *)this + 224;
  std::vector<ConnectedStorage::ContextDesc>::begin(v8, v35);
  v10 = (_QWORD *)std::list<ConnectedStorage::NtmTransferWrapper>::begin(v9, &v27);
  std::find_if_std::_Tree_iterator_std::_Tree_val_std::_Tree_simple_types_std::pair_ConnectedStorage::ContextDesc_const__ConnectedStorage::Contexts::ContextEntry_________lambda_435db05b6977f8137ff5da8c15516fe1___(
    &v26,
    *v10,
    v11,
    v38);
  v12 = std::vector<ConnectedStorage::ContextDesc>::begin(v8, &v27);
  if ( (unsigned __int8)std::_List_const_iterator<std::_List_val<std::_List_simple_types<ConnectedStorage::NtmTransferWrapper>>>::operator!=(
                          &v26,
                          v12) )
  {
    v14 = std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ConnectedStorage::ContextDesc const,ConnectedStorage::Contexts::ContextEntry>>>>::operator->(&v26);
    if ( (unsigned __int8)std::shared_ptr<ConnectedStorage::WebService>::operator bool(v14 + 64) )
    {
      ProviderInfo = ConnectedStorage::ActivatingContext::GetProviderInfo(*v16, a4);
LABEL_6:
      v18 = ProviderInfo;
LABEL_16:
      ConnectedStorage::ContextDesc::~ContextDesc((HSTRING *)&v29);
      return v18;
    }
    if ( (unsigned __int8)std::shared_ptr<ConnectedStorage::WebService>::operator bool(v15 + 80) )
    {
      ProviderInfo = ConnectedStorage::Context::GetProviderInfo(*v20, a4);
      goto LABEL_6;
    }
  }
  try
  {
    v21 = StringCchCopyW(v41, 0x104u, (const unsigned __int16 *)a3);
    if ( v21 < 0 )
      ConnectedStorage::ReportErrorAndThrow(
        (ConnectedStorage *)(unsigned int)v21,
        (int)L"StringCchCopyW(indexPath, MAX_PATH, filename)",
        v22);
    _o_wcscat_s(v41, v23, L"\\containers.index");
    std::wstring::wstring((__int64)v38, (__int64)v41);
    std::wstring::wstring((__int64)v39, (__int64)a2);
    ConnectedStorage::ContainerIndex::Load((_lambda_249230bd792972bce8c42ec595a35649_ *)&v26);
    std::wstring::_Tidy_deallocate(v39);
    std::wstring::_Tidy_deallocate(v38);
    if ( ConnectedStorage::ContainerIndex::GetTotalBytes(v26) )
    {
      ConnectedStorage::ContainerIndex::GetMetaData(v26, &v27);
      ConnectedStorage::ContainerIndex::GetSyncMetaData(v26, &v36);
      ConnectedStorage::SimpleHStringWrapper::DuplicateTo((ConnectedStorage::SimpleHStringWrapper *)&v30, (HSTRING *)a4);
      ConnectedStorage::SimpleHStringWrapper::DuplicateTo(
        (ConnectedStorage::SimpleHStringWrapper *)((char *)&v30 + 8),
        (HSTRING *)a4 + 1);
      ConnectedStorage::SimpleHStringWrapper::DuplicateTo(
        (ConnectedStorage::SimpleHStringWrapper *)&v27,
        (HSTRING *)a4 + 2);
      ConnectedStorage::SimpleHStringWrapper::DuplicateTo(
        (ConnectedStorage::SimpleHStringWrapper *)v28,
        (HSTRING *)a4 + 3);
      *((_QWORD *)a4 + 4) = v36;
      *((_QWORD *)a4 + 5) = ConnectedStorage::ContainerIndex::GetTotalBytes(v26);
      *((_BYTE *)a4 + 48) = ConnectedStorage::ContainerIndex::IsFullyUploaded(v26);
      *((_BYTE *)a4 + 49) = 0;
      WindowsDeleteString(string);
      string = 0;
      ConnectedStorage::ContainerIndexMetaData::~ContainerIndexMetaData(&v27);
      std::unique_ptr<ConnectedStorage::ContainerIndex>::~unique_ptr<ConnectedStorage::ContainerIndex>(&v26);
      ConnectedStorage::ContextDesc::~ContextDesc((HSTRING *)&v29);
      result = 1;
    }
    else
    {
      std::unique_ptr<ConnectedStorage::ContainerIndex>::~unique_ptr<ConnectedStorage::ContainerIndex>(&v26);
      ConnectedStorage::ContextDesc::~ContextDesc((HSTRING *)&v29);
      result = 0;
    }
  }
  catch ( ConnectedStorage::ComError v40 )
  {
    LODWORD(v26) = v40[6];
    ConnectedStorage::ComError::~ComError((ConnectedStorage::ComError *)v40);
    goto LABEL_14;
  }
  catch ( std::bad_alloc )
  {
    LODWORD(v26) = -2147024882;
    goto LABEL_14;
  }
  catch ( ... )
  {
    LODWORD(v26) = -2147467259;
LABEL_14:
    ConnectedStorage::EventWriteEnumerationFailedToLoadIndex(v34, (const unsigned __int16 *const)(unsigned int)v26, v24);
    ConnectedStorage::ContextDesc::~ContextDesc((HSTRING *)&v29);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18003373c  push    rbx
0x18003373e  push    rsi
0x18003373f  push    rdi
0x180033740  push    r14
0x180033742  sub     rsp, 358h
0x180033749  mov     rax, cs:__security_cookie
0x180033750  xor     rax, rsp
0x180033753  mov     [rsp+378h+var_38], rax
0x18003375b  mov     rdi, r9
0x18003375e  mov     rsi, r8
0x180033761  mov     r14, rdx
0x180033764  mov     rbx, rcx
0x180033767  mov     [rsp+378h+var_310], r8
0x18003376c  xorps   xmm0, xmm0
0x18003376f  xor     eax, eax
0x180033771  movups  xmmword ptr [r9], xmm0
0x180033775  movups  xmmword ptr [r9+10h], xmm0
0x18003377a  movups  xmmword ptr [r9+20h], xmm0
0x18003377f  mov     [r9+30h], rax
0x180033783  movdqu  [rsp+378h+var_340], xmm0
0x180033789  xorps   xmm1, xmm1
0x18003378c  movdqu  [rsp+378h+var_330], xmm1
0x180033792  mov     [rsp+378h+var_320], rax
0x180033797  mov     [rsp+378h+var_318], eax
0x18003379b  mov     [rsp+378h+var_314], 1
0x1800337a0  lea     rdx, [rsp+378h+var_340]; struct ConnectedStorage::ContextDesc *
0x1800337a5  mov     rcx, r8; unsigned __int16 *
0x1800337a8  call    ?TryGetContextDescFromDirectoryName@ContextDesc@ConnectedStorage@@SA_NPEAGPEAV12@@Z; ConnectedStorage::ContextDesc::TryGetContextDescFromDirectoryName(ushort *,ConnectedStorage::ContextDesc *)
0x1800337ad  test    al, al
0x1800337af  jz      loc_180033A18
0x1800337b5  cmp     [rsp+378h+var_314], 0
0x1800337ba  jnz     loc_180033A18
0x1800337c0  lea     rdx, [rsp+378h+var_340]; struct ConnectedStorage::ContextDesc *
0x1800337c5  lea     rcx, [rsp+378h+var_2E0]; this
0x1800337cd  call    ??0ContextDesc@ConnectedStorage@@QEAA@AEBV01@@Z; ConnectedStorage::ContextDesc::ContextDesc(ConnectedStorage::ContextDesc const &)
0x1800337d2  add     rbx, 0E0h
0x1800337d9  lea     rdx, [rsp+378h+var_308]
0x1800337de  mov     rcx, rbx
0x1800337e1  call    ?begin@?$vector@VContextDesc@ConnectedStorage@@V?$allocator@VContextDesc@ConnectedStorage@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@VContextDesc@ConnectedStorage@@@std@@@std@@@2@XZ; std::vector<ConnectedStorage::ContextDesc>::begin(void)
0x1800337e6  mov     r8, [rax]
0x1800337e9  lea     rdx, [rsp+378h+var_350]
0x1800337ee  call    ?begin@?$list@VNtmTransferWrapper@ConnectedStorage@@V?$allocator@VNtmTransferWrapper@ConnectedStorage@@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@VNtmTransferWrapper@ConnectedStorage@@@std@@@std@@@2@XZ; std::list<ConnectedStorage::NtmTransferWrapper>::begin(void)
0x1800337f3  lea     r9, [rsp+378h+var_2E0]
0x1800337fb  mov     rdx, [rax]
0x1800337fe  lea     rcx, [rsp+378h+var_358]
0x180033803  call    std__find_if_std___Tree_iterator_std___Tree_val_std___Tree_simple_types_std__pair_ConnectedStorage__ContextDesc_const__ConnectedStorage__Contexts__ContextEntry_________lambda_435db05b6977f8137ff5da8c15516fe1___
0x180033808  lea     rdx, [rsp+378h+var_350]
0x18003380d  mov     rcx, rbx
0x180033810  call    ?begin@?$vector@VContextDesc@ConnectedStorage@@V?$allocator@VContextDesc@ConnectedStorage@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@VContextDesc@ConnectedStorage@@@std@@@std@@@2@XZ; std::vector<ConnectedStorage::ContextDesc>::begin(void)
0x180033815  mov     rdx, rax
0x180033818  lea     rcx, [rsp+378h+var_358]
0x18003381d  call    ??9?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@VNtmTransferWrapper@ConnectedStorage@@@std@@@std@@@std@@QEBA_NAEBV01@@Z; std::_List_const_iterator<std::_List_val<std::_List_simple_types<ConnectedStorage::NtmTransferWrapper>>>::operator!=(std::_List_const_iterator<std::_List_val<std::_List_simple_types<ConnectedStorage::NtmTransferWrapper>>> const &)
0x180033822  test    al, al
0x180033824  jz      short loc_18003386C
0x180033826  lea     rcx, [rsp+378h+var_358]
0x18003382b  call    ??C?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVContextDesc@ConnectedStorage@@UContextEntry@Contexts@2@@std@@@std@@@std@@@std@@QEBAPEAU?$pair@$$CBVContextDesc@ConnectedStorage@@UContextEntry@Contexts@2@@1@XZ; std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ConnectedStorage::ContextDesc const,ConnectedStorage::Contexts::ContextEntry>>>>::operator->(void)
0x180033830  mov     rdx, rax
0x180033833  lea     rcx, [rax+40h]
0x180033837  call    ??B?$shared_ptr@VWebService@ConnectedStorage@@@std@@QEBA_NXZ; std::shared_ptr<ConnectedStorage::WebService>::operator bool(void)
0x18003383c  test    al, al
0x18003383e  jz      short loc_180033852
0x180033840  mov     rdx, rdi; struct XblGameSaveProviderInfo *
0x180033843  mov     rcx, [rcx]; this
0x180033846  call    ?GetProviderInfo@ActivatingContext@ConnectedStorage@@QEBA_NPEAUXblGameSaveProviderInfo@@@Z; ConnectedStorage::ActivatingContext::GetProviderInfo(XblGameSaveProviderInfo *)
0x18003384b  mov     bl, al
0x18003384d  jmp     loc_180033A1A
0x180033852  lea     rcx, [rdx+50h]
0x180033856  call    ??B?$shared_ptr@VWebService@ConnectedStorage@@@std@@QEBA_NXZ; std::shared_ptr<ConnectedStorage::WebService>::operator bool(void)
0x18003385b  test    al, al
0x18003385d  jz      short loc_18003386C
0x18003385f  mov     rdx, rdi; struct XblGameSaveProviderInfo *
0x180033862  mov     rcx, [rcx]; this
0x180033865  call    ?GetProviderInfo@Context@ConnectedStorage@@QEBA_NPEAUXblGameSaveProviderInfo@@@Z; ConnectedStorage::Context::GetProviderInfo(XblGameSaveProviderInfo *)
0x18003386a  jmp     short loc_18003384B
0x18003386c  mov     r8, rsi; unsigned __int16 *
0x18003386f  mov     r11d, 104h
0x180033875  mov     edx, r11d; unsigned __int64
0x180033878  lea     rcx, [rsp+378h+var_248]; unsigned __int16 *
0x180033880  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180033885  test    eax, eax
0x180033887  jns     short loc_180033897
0x180033889  lea     rdx, aStringcchcopyw_0; "StringCchCopyW(indexPath, MAX_PATH, fil"...
0x180033890  mov     ecx, eax; this
0x180033892  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x180033897  lea     r8, aContainersInde; "\\containers.index"
0x18003389e  mov     rdx, r11
0x1800338a1  lea     rcx, [rsp+378h+var_248]
0x1800338a9  call    cs:__imp__o_wcscat_s
0x1800338af  lea     rdx, [rsp+378h+var_248]
0x1800338b7  lea     rcx, [rsp+378h+var_2E0]
0x1800338bf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800338c4  nop
0x1800338c5  mov     rdx, r14
0x1800338c8  lea     rcx, [rsp+378h+var_2B0]
0x1800338d0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800338d5  nop
0x1800338d6  xor     r9d, r9d
0x1800338d9  lea     r8, [rsp+378h+var_2E0]
0x1800338e1  lea     rdx, [rsp+378h+var_2B0]
0x1800338e9  lea     rcx, [rsp+378h+var_358]; this
0x1800338ee  call    ?Load@ContainerIndex@ConnectedStorage@@SA?AV?$unique_ptr@VContainerIndex@ConnectedStorage@@U?$default_delete@VContainerIndex@ConnectedStorage@@@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@0W4ContainerSyncTrackingFlag@2@@Z; ConnectedStorage::ContainerIndex::Load(std::wstring const &,std::wstring const &,ConnectedStorage::ContainerSyncTrackingFlag)
0x1800338f3  nop
0x1800338f4  lea     rcx, [rsp+378h+var_2B0]
0x1800338fc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180033901  nop
0x180033902  lea     rcx, [rsp+378h+var_2E0]
0x18003390a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003390f  mov     rcx, [rsp+378h+var_358]; this
0x180033914  call    ?GetTotalBytes@ContainerIndex@ConnectedStorage@@QEBA_KXZ; ConnectedStorage::ContainerIndex::GetTotalBytes(void)
0x180033919  test    rax, rax
0x18003391c  jnz     short loc_18003393A
0x18003391e  lea     rcx, [rsp+378h+var_358]
0x180033923  call    ??1?$unique_ptr@VContainerIndex@ConnectedStorage@@U?$default_delete@VContainerIndex@ConnectedStorage@@@std@@@std@@QEAA@XZ; std::unique_ptr<ConnectedStorage::ContainerIndex>::~unique_ptr<ConnectedStorage::ContainerIndex>(void)
0x180033928  nop
0x180033929  lea     rcx, [rsp+378h+var_340]; this
0x18003392e  call    ??1ContextDesc@ConnectedStorage@@QEAA@XZ; ConnectedStorage::ContextDesc::~ContextDesc(void)
0x180033933  xor     al, al
0x180033935  jmp     loc_180033A26
0x18003393a  lea     rdx, [rsp+378h+var_350]
0x18003393f  mov     rcx, [rsp+378h+var_358]
0x180033944  call    ?GetMetaData@ContainerIndex@ConnectedStorage@@QEBA?AUContainerIndexMetaData@2@XZ; ConnectedStorage::ContainerIndex::GetMetaData(void)
0x180033949  nop
0x18003394a  lea     rdx, [rsp+378h+var_300]
0x18003394f  mov     rcx, [rsp+378h+var_358]
0x180033954  call    ?GetSyncMetaData@ContainerIndex@ConnectedStorage@@QEBA?AUContainerIndexSyncMetaData@2@XZ; ConnectedStorage::ContainerIndex::GetSyncMetaData(void)
0x180033959  nop
0x18003395a  mov     rdx, rdi; HSTRING *
0x18003395d  lea     rcx, [rsp+378h+var_330]; this
0x180033962  call    ?DuplicateTo@SimpleHStringWrapper@ConnectedStorage@@QEBAXPEAPEAUHSTRING__@@@Z; ConnectedStorage::SimpleHStringWrapper::DuplicateTo(HSTRING__ * *)
0x180033967  lea     rdx, [rdi+8]; HSTRING *
0x18003396b  lea     rcx, [rsp+378h+var_330+8]; this
0x180033970  call    ?DuplicateTo@SimpleHStringWrapper@ConnectedStorage@@QEBAXPEAPEAUHSTRING__@@@Z; ConnectedStorage::SimpleHStringWrapper::DuplicateTo(HSTRING__ * *)
0x180033975  lea     rdx, [rdi+10h]; HSTRING *
0x180033979  lea     rcx, [rsp+378h+var_350]; this
0x18003397e  call    ?DuplicateTo@SimpleHStringWrapper@ConnectedStorage@@QEBAXPEAPEAUHSTRING__@@@Z; ConnectedStorage::SimpleHStringWrapper::DuplicateTo(HSTRING__ * *)
0x180033983  lea     rdx, [rdi+18h]; HSTRING *
0x180033987  lea     rcx, [rsp+378h+var_348]; this
0x18003398c  call    ?DuplicateTo@SimpleHStringWrapper@ConnectedStorage@@QEBAXPEAPEAUHSTRING__@@@Z; ConnectedStorage::SimpleHStringWrapper::DuplicateTo(HSTRING__ * *)
0x180033991  mov     rax, [rsp+378h+var_300]
0x180033996  mov     [rdi+20h], rax
0x18003399a  mov     rcx, [rsp+378h+var_358]; this
0x18003399f  call    ?GetTotalBytes@ContainerIndex@ConnectedStorage@@QEBA_KXZ; ConnectedStorage::ContainerIndex::GetTotalBytes(void)
0x1800339a4  mov     [rdi+28h], rax
0x1800339a8  mov     rcx, [rsp+378h+var_358]; this
0x1800339ad  call    ?IsFullyUploaded@ContainerIndex@ConnectedStorage@@QEBA_NXZ; ConnectedStorage::ContainerIndex::IsFullyUploaded(void)
0x1800339b2  mov     [rdi+30h], al
0x1800339b5  mov     byte ptr [rdi+31h], 0
0x1800339b9  mov     rcx, [rsp+378h+string]; string
0x1800339c1  call    cs:__imp_WindowsDeleteString
0x1800339c7  mov     [rsp+378h+string], 0
0x1800339d3  lea     rcx, [rsp+378h+var_350]; this
0x1800339d8  call    ??1ContainerIndexMetaData@ConnectedStorage@@QEAA@XZ; ConnectedStorage::ContainerIndexMetaData::~ContainerIndexMetaData(void)
0x1800339dd  nop
0x1800339de  lea     rcx, [rsp+378h+var_358]
0x1800339e3  call    ??1?$unique_ptr@VContainerIndex@ConnectedStorage@@U?$default_delete@VContainerIndex@ConnectedStorage@@@std@@@std@@QEAA@XZ; std::unique_ptr<ConnectedStorage::ContainerIndex>::~unique_ptr<ConnectedStorage::ContainerIndex>(void)
0x1800339e8  nop
0x1800339e9  lea     rcx, [rsp+378h+var_340]; this
0x1800339ee  call    ??1ContextDesc@ConnectedStorage@@QEAA@XZ; ConnectedStorage::ContextDesc::~ContextDesc(void)
0x1800339f3  mov     al, 1
0x1800339f5  jmp     short loc_180033A26
0x1800339f7  jmp     short loc_1800339FB
0x1800339f9  jmp     short $+2
0x1800339fb  mov     edx, dword ptr [rsp+378h+var_358]; unsigned __int16 *
0x1800339ff  mov     rcx, [rsp+378h+var_310]; this
0x180033a04  call    ?EventWriteEnumerationFailedToLoadIndex@ConnectedStorage@@YAXQEBGI@Z; ConnectedStorage::EventWriteEnumerationFailedToLoadIndex(ushort const * const,uint)
0x180033a09  nop
0x180033a0a  lea     rcx, [rsp+378h+var_340]; this
0x180033a0f  call    ??1ContextDesc@ConnectedStorage@@QEAA@XZ; ConnectedStorage::ContextDesc::~ContextDesc(void)
0x180033a14  xor     al, al
0x180033a16  jmp     short loc_180033A26
0x180033a18  xor     bl, bl
0x180033a1a  lea     rcx, [rsp+378h+var_340]; this
0x180033a1f  call    ??1ContextDesc@ConnectedStorage@@QEAA@XZ; ConnectedStorage::ContextDesc::~ContextDesc(void)
0x180033a24  mov     al, bl
0x180033a26  mov     rcx, [rsp+378h+var_38]
0x180033a2e  xor     rcx, rsp; StackCookie
0x180033a31  call    __security_check_cookie
0x180033a36  add     rsp, 358h
0x180033a3d  pop     r14
0x180033a3f  pop     rdi
0x180033a40  pop     rsi
0x180033a41  pop     rbx
0x180033a42  retn
```
