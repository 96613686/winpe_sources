# CTreeWalker::FindMediaLibraryFolderSuggestions(void)

- ea: `0x1800442f4`
- end: `0x180044593`
- name: `?FindMediaLibraryFolderSuggestions@CTreeWalker@@AEAAXXZ`
- size: `671`
- prototype: `void __fastcall(CTreeWalker *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180040da4`

## callees

- `0x180018fb8`
- `0x18001c208`
- `0x1800386e0`
- `0x180039f8c`
- `0x18003fb50`
- `0x180043770`
- `0x180043e28`
- `0x1800442f4`
- `0x1800491f0`
- `0x1800493ac`
- `0x180049558`
- `0x180049a08`
- `0x18004ad10`
- `0x18004b3d0`
- `0x18004b3e4`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180044408`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180044408`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180044338`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180044338`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall CTreeWalker::FindMediaLibraryFolderSuggestions(const WCHAR *this)
{
  unsigned __int16 *v2; // r12
  HANDLE FileW; // rsi
  char *v4; // r14
  _QWORD *i; // rbx
  __int64 v6; // rax
  _QWORD *v7; // rax
  unsigned __int16 v8; // bx
  __int64 v9; // rdx
  _QWORD **v10; // rcx
  _QWORD *v11; // rdi
  _QWORD *v12; // rbx
  _QWORD **v13; // rcx
  _QWORD *v14; // rdi
  _QWORD *v15; // rbx
  _QWORD **v16; // rcx
  _QWORD *v17; // rdi
  _QWORD *v18; // rbx
  _QWORD *v19; // [rsp+40h] [rbp-30h] BYREF
  __int64 v20; // [rsp+48h] [rbp-28h]
  _QWORD *v21; // [rsp+50h] [rbp-20h] BYREF
  __int64 v22; // [rsp+58h] [rbp-18h]
  _QWORD *v23; // [rsp+60h] [rbp-10h] BYREF
  __int64 v24; // [rsp+68h] [rbp-8h]
  _QWORD *v25; // [rsp+B0h] [rbp+40h] BYREF
  _QWORD *v26; // [rsp+B8h] [rbp+48h] BYREF
  __int64 v27; // [rsp+C0h] [rbp+50h] BYREF
  char v28; // [rsp+C8h] [rbp+58h] BYREF

  v2 = (unsigned __int16 *)(this + 164);
  FileW = CreateFileW(this + 164, 0x100u, 3u, 0, 3u, 0x2000080u, 0);
  if ( FileW != (HANDLE)-1LL )
  {
    std::list<FoundFolderInfo>::list<FoundFolderInfo>(&v23);
    std::list<FoundFolderInfo>::list<FoundFolderInfo>(&v21);
    std::list<FoundFolderInfo>::list<FoundFolderInfo>(&v19);
    std::list<__int64>::_Unchecked_begin(this + 80, &v25);
    std::list<__int64>::_Unchecked_end(this + 80, &v26);
    v4 = (char *)(this + 32);
    for ( i = v25; i != v26; i = (_QWORD *)*i )
    {
      v27 = i[2];
      std::_Hash<std::_Umap_traits<__int64,FOLDER_USAGE,std::_Uhash_compare<__int64,std::hash<__int64>,std::equal_to<__int64>>,std::allocator<std::pair<__int64 const,FOLDER_USAGE>>,0>>::find(
        this + 32,
        &v25,
        &v27);
      v6 = std::_Hash<std::_Umap_traits<__int64,FOLDER_USAGE,std::_Uhash_compare<__int64,std::hash<__int64>,std::equal_to<__int64>>,std::allocator<std::pair<__int64 const,FOLDER_USAGE>>,0>>::end(
             this + 32,
             &v28);
      if ( (unsigned __int8)std::_List_const_iterator<std::_List_val<std::_List_simple_types<std::pair<__int64 const,FOLDER_USAGE>>>>::operator!=(
                              &v25,
                              v6) )
      {
        v7 = (_QWORD *)std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,STORAGE_USAGE>>>>::operator->(&v25);
        CTreeWalker::_GetFoldersForLibraries(
          (_DWORD)this,
          (_DWORD)FileW,
          *v7,
          (_DWORD)v7 + 8,
          (__int64)&v23,
          (__int64)&v21,
          (__int64)&v19);
      }
    }
    CloseHandle(FileW);
    v8 = *v2;
    SendDriveSpecificTelemetry(*v2, v24 + v22 + v20, (_DWORD)this + 160, (_DWORD)this + 128, (__int64)(this + 32));
    SendFolderSpecificTelemetry(v8, 1, &v23, this + 32);
    SendFolderSpecificTelemetry(v8, 3, &v21, v4);
    SendFolderSpecificTelemetry(v8, 4, &v19, v4);
    LOBYTE(v9) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_StorageServiceFolderSuggestionsWriteRegistry>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_StorageServiceFolderSuggestionsWriteRegistry>::GetImpl'::`2'::impl,
      v9);
    WriteFoldersToRegistry(v8, 0, &v23);
    WriteFoldersToRegistry(v8, 2, &v21);
    WriteFoldersToRegistry(v8, 1, &v19);
    v10 = (_QWORD **)v19;
    *(_QWORD *)v19[1] = 0;
    v11 = *v10;
    if ( *v10 )
    {
      do
      {
        v12 = (_QWORD *)*v11;
        v25 = v11 + 2;
        std::wstring::_Tidy_deallocate(v11 + 2);
        std::_Deallocate<16>(v11, (const struct std::nothrow_t *)0x40);
        v11 = v12;
      }
      while ( v12 );
    }
    std::_Deallocate<16>(v19, (const struct std::nothrow_t *)0x40);
    v13 = (_QWORD **)v21;
    *(_QWORD *)v21[1] = 0;
    v14 = *v13;
    if ( *v13 )
    {
      do
      {
        v15 = (_QWORD *)*v14;
        v25 = v14 + 2;
        std::wstring::_Tidy_deallocate(v14 + 2);
        std::_Deallocate<16>(v14, (const struct std::nothrow_t *)0x40);
        v14 = v15;
      }
      while ( v15 );
    }
    std::_Deallocate<16>(v21, (const struct std::nothrow_t *)0x40);
    v16 = (_QWORD **)v23;
    *(_QWORD *)v23[1] = 0;
    v17 = *v16;
    if ( *v16 )
    {
      do
      {
        v18 = (_QWORD *)*v17;
        v25 = v17 + 2;
        std::wstring::_Tidy_deallocate(v17 + 2);
        std::_Deallocate<16>(v17, (const struct std::nothrow_t *)0x40);
        v17 = v18;
      }
      while ( v18 );
    }
    std::_Deallocate<16>(v23, (const struct std::nothrow_t *)0x40);
  }
}

```

## disassembly

```asm
0x1800442f4  push    rbp
0x1800442f6  push    rbx
0x1800442f7  push    rsi
0x1800442f8  push    rdi
0x1800442f9  push    r12
0x1800442fb  push    r14
0x1800442fd  push    r15
0x1800442ff  mov     rbp, rsp
0x180044302  sub     rsp, 70h
0x180044306  mov     rdi, rcx
0x180044309  lea     r12, [rcx+148h]
0x180044310  mov     [rsp+70h+hTemplateFile], 0; hTemplateFile
0x180044319  mov     [rsp+70h+dwFlagsAndAttributes], 2000080h; dwFlagsAndAttributes
0x180044321  mov     eax, 3
0x180044326  mov     [rsp+70h+dwCreationDisposition], eax; dwCreationDisposition
0x18004432a  xor     r9d, r9d; lpSecurityAttributes
0x18004432d  mov     r8d, eax; dwShareMode
0x180044330  mov     edx, 100h; dwDesiredAccess
0x180044335  mov     rcx, r12; lpFileName
0x180044338  call    cs:__imp_CreateFileW
0x18004433e  mov     rsi, rax
0x180044341  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180044345  jz      loc_180044584
0x18004434b  lea     rcx, [rbp+var_10]
0x18004434f  call    ??0?$list@UFoundFolderInfo@@V?$allocator@UFoundFolderInfo@@@std@@@std@@QEAA@XZ; std::list<FoundFolderInfo>::list<FoundFolderInfo>(void)
0x180044354  nop
0x180044355  lea     rcx, [rbp+var_20]
0x180044359  call    ??0?$list@UFoundFolderInfo@@V?$allocator@UFoundFolderInfo@@@std@@@std@@QEAA@XZ; std::list<FoundFolderInfo>::list<FoundFolderInfo>(void)
0x18004435e  nop
0x18004435f  lea     rcx, [rbp+var_30]
0x180044363  call    ??0?$list@UFoundFolderInfo@@V?$allocator@UFoundFolderInfo@@@std@@@std@@QEAA@XZ; std::list<FoundFolderInfo>::list<FoundFolderInfo>(void)
0x180044368  nop
0x180044369  lea     r15, [rdi+0A0h]
0x180044370  lea     rdx, [rbp+arg_0]
0x180044374  mov     rcx, r15
0x180044377  call    ?_Unchecked_begin@?$list@_JV?$allocator@_J@std@@@std@@QEAA?AV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@_J@std@@@std@@@2@XZ; std::list<__int64>::_Unchecked_begin(void)
0x18004437c  lea     rdx, [rbp+arg_8]
0x180044380  mov     rcx, r15
0x180044383  call    ?_Unchecked_end@?$list@_JV?$allocator@_J@std@@@std@@QEAA?AV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@_J@std@@@std@@@2@XZ; std::list<__int64>::_Unchecked_end(void)
0x180044388  lea     r14, [rdi+40h]
0x18004438c  mov     rbx, [rbp+arg_0]
0x180044390  cmp     rbx, [rbp+arg_8]
0x180044394  jz      short loc_180044405
0x180044396  mov     rax, [rbx+10h]
0x18004439a  mov     [rbp+arg_10], rax
0x18004439e  lea     r8, [rbp+arg_10]
0x1800443a2  lea     rdx, [rbp+arg_0]
0x1800443a6  mov     rcx, r14
0x1800443a9  call    ?find@?$_Hash@V?$_Umap_traits@_JVFOLDER_USAGE@@V?$_Uhash_compare@_JU?$hash@_J@std@@U?$equal_to@_J@2@@std@@V?$allocator@U?$pair@$$CB_JVFOLDER_USAGE@@@std@@@3@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_JVFOLDER_USAGE@@@std@@@std@@@std@@@2@AEB_J@Z; std::_Hash<std::_Umap_traits<__int64,FOLDER_USAGE,std::_Uhash_compare<__int64,std::hash<__int64>,std::equal_to<__int64>>,std::allocator<std::pair<__int64 const,FOLDER_USAGE>>,0>>::find(__int64 const &)
0x1800443ae  lea     rdx, [rbp+arg_18]
0x1800443b2  mov     rcx, r14
0x1800443b5  call    ?end@?$_Hash@V?$_Umap_traits@_JVFOLDER_USAGE@@V?$_Uhash_compare@_JU?$hash@_J@std@@U?$equal_to@_J@2@@std@@V?$allocator@U?$pair@$$CB_JVFOLDER_USAGE@@@std@@@3@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_JVFOLDER_USAGE@@@std@@@std@@@std@@@2@XZ; std::_Hash<std::_Umap_traits<__int64,FOLDER_USAGE,std::_Uhash_compare<__int64,std::hash<__int64>,std::equal_to<__int64>>,std::allocator<std::pair<__int64 const,FOLDER_USAGE>>,0>>::end(void)
0x1800443ba  mov     rdx, rax
0x1800443bd  lea     rcx, [rbp+arg_0]
0x1800443c1  call    ??9?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_JVFOLDER_USAGE@@@std@@@std@@@std@@@std@@QEBA_NAEBV01@@Z; std::_List_const_iterator<std::_List_val<std::_List_simple_types<std::pair<__int64 const,FOLDER_USAGE>>>>::operator!=(std::_List_const_iterator<std::_List_val<std::_List_simple_types<std::pair<__int64 const,FOLDER_USAGE>>>> const &)
0x1800443c6  test    al, al
0x1800443c8  jz      short loc_180044400
0x1800443ca  lea     rcx, [rbp+arg_0]
0x1800443ce  call    ??C?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHVSTORAGE_USAGE@@@std@@@std@@@std@@@std@@QEBAPEAU?$pair@$$CBHVSTORAGE_USAGE@@@1@XZ; std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,STORAGE_USAGE>>>>::operator->(void)
0x1800443d3  lea     r9, [rax+8]
0x1800443d7  lea     rcx, [rbp+var_30]
0x1800443db  mov     [rsp+70h+hTemplateFile], rcx
0x1800443e0  lea     rcx, [rbp+var_20]
0x1800443e4  mov     qword ptr [rsp+70h+dwFlagsAndAttributes], rcx
0x1800443e9  lea     rcx, [rbp+var_10]
0x1800443ed  mov     qword ptr [rsp+70h+dwCreationDisposition], rcx
0x1800443f2  mov     r8, [rax]
0x1800443f5  mov     rdx, rsi
0x1800443f8  mov     rcx, rdi
0x1800443fb  call    ?_GetFoldersForLibraries@CTreeWalker@@AEAAXPEAX_JAEAVFOLDER_USAGE@@AEAV?$list@UFoundFolderInfo@@V?$allocator@UFoundFolderInfo@@@std@@@std@@33@Z; CTreeWalker::_GetFoldersForLibraries(void *,__int64,FOLDER_USAGE &,std::list<FoundFolderInfo> &,std::list<FoundFolderInfo> &,std::list<FoundFolderInfo> &)
0x180044400  mov     rbx, [rbx]
0x180044403  jmp     short loc_180044390
0x180044405  mov     rcx, rsi; hObject
0x180044408  call    cs:__imp_CloseHandle
0x18004440e  movzx   ebx, word ptr [r12]
0x180044413  lea     r9, [rdi+80h]
0x18004441a  mov     rdx, [rbp+var_28]
0x18004441e  add     rdx, [rbp+var_18]
0x180044422  add     rdx, [rbp+var_8]
0x180044426  mov     qword ptr [rsp+70h+dwCreationDisposition], r14
0x18004442b  mov     r8, r15
0x18004442e  movzx   ecx, bx
0x180044431  call    ?SendDriveSpecificTelemetry@@YAXG_KAEAV?$list@_JV?$allocator@_J@std@@@std@@1AEAV?$unordered_map@_JVFOLDER_USAGE@@U?$hash@_J@std@@U?$equal_to@_J@3@V?$allocator@U?$pair@$$CB_JVFOLDER_USAGE@@@std@@@3@@2@@Z; SendDriveSpecificTelemetry(ushort,unsigned __int64,std::list<__int64> &,std::list<__int64> &,std::unordered_map<__int64,FOLDER_USAGE> &)
0x180044436  mov     r9, r14
0x180044439  lea     r8, [rbp+var_10]
0x18004443d  mov     edi, 1
0x180044442  mov     edx, edi
0x180044444  movzx   ecx, bx
0x180044447  call    ?SendFolderSpecificTelemetry@@YAXGW4VALID_LIBRARY_TYPE@@AEAV?$list@UFoundFolderInfo@@V?$allocator@UFoundFolderInfo@@@std@@@std@@AEAV?$unordered_map@_JVFOLDER_USAGE@@U?$hash@_J@std@@U?$equal_to@_J@3@V?$allocator@U?$pair@$$CB_JVFOLDER_USAGE@@@std@@@3@@3@@Z; SendFolderSpecificTelemetry(ushort,VALID_LIBRARY_TYPE,std::list<FoundFolderInfo> &,std::unordered_map<__int64,FOLDER_USAGE> &)
0x18004444c  mov     r9, r14
0x18004444f  lea     r8, [rbp+var_20]
0x180044453  lea     edx, [rdi+2]
0x180044456  movzx   ecx, bx
0x180044459  call    ?SendFolderSpecificTelemetry@@YAXGW4VALID_LIBRARY_TYPE@@AEAV?$list@UFoundFolderInfo@@V?$allocator@UFoundFolderInfo@@@std@@@std@@AEAV?$unordered_map@_JVFOLDER_USAGE@@U?$hash@_J@std@@U?$equal_to@_J@3@V?$allocator@U?$pair@$$CB_JVFOLDER_USAGE@@@std@@@3@@3@@Z; SendFolderSpecificTelemetry(ushort,VALID_LIBRARY_TYPE,std::list<FoundFolderInfo> &,std::unordered_map<__int64,FOLDER_USAGE> &)
0x18004445e  mov     r9, r14
0x180044461  lea     r8, [rbp+var_30]
0x180044465  lea     edx, [rdi+3]
0x180044468  movzx   ecx, bx
0x18004446b  call    ?SendFolderSpecificTelemetry@@YAXGW4VALID_LIBRARY_TYPE@@AEAV?$list@UFoundFolderInfo@@V?$allocator@UFoundFolderInfo@@@std@@@std@@AEAV?$unordered_map@_JVFOLDER_USAGE@@U?$hash@_J@std@@U?$equal_to@_J@3@V?$allocator@U?$pair@$$CB_JVFOLDER_USAGE@@@std@@@3@@3@@Z; SendFolderSpecificTelemetry(ushort,VALID_LIBRARY_TYPE,std::list<FoundFolderInfo> &,std::unordered_map<__int64,FOLDER_USAGE> &)
0x180044470  mov     dl, dil
0x180044473  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_StorageServiceFolderSuggestionsWriteRegistry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_StorageServiceFolderSuggestionsWriteRegistry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_StorageServiceFolderSuggestionsWriteRegistry> `wil::Feature<__WilFeatureTraits_Feature_StorageServiceFolderSuggestionsWriteRegistry>::GetImpl(void)'::`2'::impl
0x18004447a  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_StorageServiceFolderSuggestionsWriteRegistry@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_StorageServiceFolderSuggestionsWriteRegistry>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18004447f  lea     r8, [rbp+var_10]
0x180044483  xor     edx, edx
0x180044485  movzx   ecx, bx
0x180044488  call    ?WriteFoldersToRegistry@@YAXGW4MediaClass@TreeWalker@StorSvc@@AEAV?$list@UFoundFolderInfo@@V?$allocator@UFoundFolderInfo@@@std@@@std@@@Z; WriteFoldersToRegistry(ushort,StorSvc::TreeWalker::MediaClass,std::list<FoundFolderInfo> &)
0x18004448d  lea     r8, [rbp+var_20]
0x180044491  lea     edx, [rdi+1]
0x180044494  movzx   ecx, bx
0x180044497  call    ?WriteFoldersToRegistry@@YAXGW4MediaClass@TreeWalker@StorSvc@@AEAV?$list@UFoundFolderInfo@@V?$allocator@UFoundFolderInfo@@@std@@@std@@@Z; WriteFoldersToRegistry(ushort,StorSvc::TreeWalker::MediaClass,std::list<FoundFolderInfo> &)
0x18004449c  lea     r8, [rbp+var_30]
0x1800444a0  mov     edx, edi
0x1800444a2  movzx   ecx, bx
0x1800444a5  call    ?WriteFoldersToRegistry@@YAXGW4MediaClass@TreeWalker@StorSvc@@AEAV?$list@UFoundFolderInfo@@V?$allocator@UFoundFolderInfo@@@std@@@std@@@Z; WriteFoldersToRegistry(ushort,StorSvc::TreeWalker::MediaClass,std::list<FoundFolderInfo> &)
0x1800444aa  nop
0x1800444ab  mov     rcx, [rbp+var_30]
0x1800444af  mov     rax, [rcx+8]
0x1800444b3  mov     qword ptr [rax], 0
0x1800444ba  mov     rdi, [rcx]
0x1800444bd  mov     esi, 40h ; '@'
0x1800444c2  test    rdi, rdi
0x1800444c5  jz      short loc_1800444EA
0x1800444c7  mov     rbx, [rdi]
0x1800444ca  lea     rcx, [rdi+10h]
0x1800444ce  mov     [rbp+arg_0], rcx
0x1800444d2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800444d7  mov     rdx, rsi
0x1800444da  mov     rcx, rdi
0x1800444dd  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800444e2  mov     rdi, rbx
0x1800444e5  test    rbx, rbx
0x1800444e8  jnz     short loc_1800444C7
0x1800444ea  mov     rdx, rsi
0x1800444ed  mov     rcx, [rbp+var_30]
0x1800444f1  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800444f6  nop
0x1800444f7  mov     rcx, [rbp+var_20]
0x1800444fb  mov     rax, [rcx+8]
0x1800444ff  mov     qword ptr [rax], 0
0x180044506  mov     rdi, [rcx]
0x180044509  test    rdi, rdi
0x18004450c  jz      short loc_180044531
0x18004450e  mov     rbx, [rdi]
0x180044511  lea     rcx, [rdi+10h]
0x180044515  mov     [rbp+arg_0], rcx
0x180044519  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004451e  mov     rdx, rsi
0x180044521  mov     rcx, rdi
0x180044524  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180044529  mov     rdi, rbx
0x18004452c  test    rbx, rbx
0x18004452f  jnz     short loc_18004450E
0x180044531  mov     rdx, rsi
0x180044534  mov     rcx, [rbp+var_20]
0x180044538  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18004453d  nop
0x18004453e  mov     rcx, [rbp+var_10]
0x180044542  mov     rax, [rcx+8]
0x180044546  mov     qword ptr [rax], 0
0x18004454d  mov     rdi, [rcx]
0x180044550  test    rdi, rdi
0x180044553  jz      short loc_180044578
0x180044555  mov     rbx, [rdi]
0x180044558  lea     rcx, [rdi+10h]
0x18004455c  mov     [rbp+arg_0], rcx
0x180044560  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180044565  mov     rdx, rsi
0x180044568  mov     rcx, rdi
0x18004456b  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180044570  mov     rdi, rbx
0x180044573  test    rbx, rbx
0x180044576  jnz     short loc_180044555
0x180044578  mov     rdx, rsi
0x18004457b  mov     rcx, [rbp+var_10]
0x18004457f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180044584  add     rsp, 70h
0x180044588  pop     r15
0x18004458a  pop     r14
0x18004458c  pop     r12
0x18004458e  pop     rdi
0x18004458f  pop     rsi
0x180044590  pop     rbx
0x180044591  pop     rbp
0x180044592  retn
```
