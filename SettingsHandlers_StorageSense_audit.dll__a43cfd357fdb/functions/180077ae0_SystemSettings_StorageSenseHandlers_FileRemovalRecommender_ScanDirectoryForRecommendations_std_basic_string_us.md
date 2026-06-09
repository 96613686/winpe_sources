# SystemSettings::StorageSenseHandlers::FileRemovalRecommender::ScanDirectoryForRecommendations(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180077ae0`
- end: `0x180077fe9`
- name: `?ScanDirectoryForRecommendations@FileRemovalRecommender@StorageSenseHandlers@SystemSettings@@IEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `1289`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180074070`

## callees

- `0x180006e50`
- `0x1800077ec`
- `0x180007a00`
- `0x180012374`
- `0x180014940`
- `0x180022f70`
- `0x180023578`
- `0x180023928`
- `0x180029a74`
- `0x1800352b4`
- `0x18004ef90`
- `0x18005c450`
- `0x180066cbc`
- `0x18006a8e0`
- `0x18006cd3c`
- `0x18006e670`
- `0x180073000`
- `0x180074fcc`
- `0x180077ae0`
- `0x18007a86c`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077c46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077c46`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180077c40`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180077c40`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180077c26`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180077c26`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180077b63`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180077b63`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x180077b8c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x180077b8c`

## string_xrefs

- `0x180077c4c`: `CleanupRecommendations`
- `0x180077c7f`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\recommenderengine.cpp`
- `0x180077ce7`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\recommenderengine.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SystemSettings::StorageSenseHandlers::FileRemovalRecommender::ScanDirectoryForRecommendations(
        _QWORD *a1,
        __int64 a2)
{
  __int64 v4; // rax
  const WCHAR *v5; // rax
  HANDLE FirstFileW; // rdi
  const unsigned __int8 *ExtensionW; // rax
  unsigned __int64 v8; // rcx
  __int64 v9; // r8
  unsigned __int64 appended; // rax
  __int64 v11; // rcx
  signed int LastError; // eax
  SystemSettings::StorageSenseHandlers::FileRemovalRecommender *v13; // rcx
  int RecentFilesTimeBounds; // eax
  unsigned int v15; // ebx
  SystemSettings::StorageSenseHandlers::FileRemovalRecommender *v17; // rdx
  unsigned __int64 v18; // rbx
  unsigned __int64 v19; // r15
  SystemSettings::StorageSenseHandlers::FileRemovalRecommender *v20; // rax
  _OWORD *v21; // r8
  __int64 v22; // r9
  _DWORD *v23; // r12
  char *v24; // rax
  _OWORD *v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // rax
  char v29; // [rsp+30h] [rbp-D0h]
  struct _FILETIME v30; // [rsp+38h] [rbp-C8h] BYREF
  SystemSettings::StorageSenseHandlers::FileRemovalRecommender *v31[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v32; // [rsp+50h] [rbp-B0h]
  struct _FILETIME v33; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v34[2]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v35[24]; // [rsp+78h] [rbp-88h] BYREF
  char v36; // [rsp+90h] [rbp-70h] BYREF
  __int64 v37; // [rsp+A4h] [rbp-5Ch]
  int v38; // [rsp+ACh] [rbp-54h]
  int v39; // [rsp+B0h] [rbp-50h]
  _BYTE v40[548]; // [rsp+BCh] [rbp-44h] BYREF
  _BYTE v41[20]; // [rsp+2E0h] [rbp+1E0h] BYREF
  __int64 v42; // [rsp+2F4h] [rbp+1F4h]
  _QWORD v43[4]; // [rsp+530h] [rbp+430h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+550h] [rbp+450h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+7E8h] [rbp+6E8h]

  *(_OWORD *)v31 = 0;
  v32 = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v4 = std::operator+<unsigned short>(v43, a2, L"\\*");
  v5 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v4);
  FirstFileW = FindFirstFileW(v5, &FindFileData);
  std::wstring::_Tidy_deallocate(v43);
  do
  {
    if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
    {
      ExtensionW = (const unsigned __int8 *)PathFindExtensionW(FindFileData.cFileName);
      if ( *(_WORD *)ExtensionW )
      {
        v34[0] = ExtensionW;
        v9 = -1;
        do
          ++v9;
        while ( *(_WORD *)&ExtensionW[2 * v9] );
        v34[1] = v9;
        appended = std::_Fnv1a_append_bytes(v8, ExtensionW, 2 * v9);
        v11 = *(_QWORD *)(std::_Hash<std::_Uset_traits<std::basic_string_view<unsigned short>,std::_Uhash_compare<std::basic_string_view<unsigned short>,std::hash<std::basic_string_view<unsigned short>>,std::equal_to<std::basic_string_view<unsigned short>>>,std::allocator<std::basic_string_view<unsigned short>>,0>>::_Find_last<std::basic_string_view<unsigned short>>(
                            a1 + 21,
                            v35,
                            v34,
                            appended)
                        + 8);
        if ( !v11 )
          v11 = a1[22];
        if ( v11 == a1[22]
          && (*(unsigned __int8 (__fastcall **)(_QWORD *, _WIN32_FIND_DATAW *))(*a1 + 56LL))(a1, &FindFileData) )
        {
          std::priority_queue__WIN32_FIND_DATAW_std::vector__WIN32_FIND_DATAW_std::allocator__WIN32_FIND_DATAW_____lambda_0dcb0dbb010333414d94d8cd0edab34c___::push(
            v31,
            &FindFileData);
        }
      }
    }
  }
  while ( FindNextFileW(FirstFileW, &FindFileData) && !*((_BYTE *)a1 + 232) );
  FindClose(FirstFileW);
  LastError = GetLastError();
  if ( LastError != 18 )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    wil::details::in1diag3::Log_IfFailedMsg(
      retaddr,
      (void *)0x86,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\recommenderengine.cpp",
      (const char *)(unsigned int)LastError,
      (int)"%hs",
      "CleanupRecommendations");
  }
  v13 = v31[0];
  if ( v31[0] == v31[1] )
  {
    if ( !v31[0] )
      return 0;
LABEL_34:
    std::_Deallocate<16>(v13, 16 * ((v32 - (__int64)v13) >> 4));
    return 0;
  }
  v33 = 0;
  v30 = 0;
  RecentFilesTimeBounds = SystemSettings::StorageSenseHandlers::FileRemovalRecommender::GetRecentFilesTimeBounds(
                            v31[0],
                            &v33,
                            &v30);
  v15 = RecentFilesTimeBounds;
  if ( RecentFilesTimeBounds >= 0 )
  {
    v17 = v31[1];
    v13 = v31[0];
    v18 = 0x14C1BACF914C1BADLL * ((v31[1] - v31[0]) >> 4);
    if ( v18 > 0x14 )
      v18 = 20;
    v19 = 0;
    if ( v18 )
    {
      while ( 1 )
      {
        v20 = v13;
        v21 = v41;
        v22 = 4;
        do
        {
          *v21 = *(_OWORD *)v20;
          v21[1] = *((_OWORD *)v20 + 1);
          v21[2] = *((_OWORD *)v20 + 2);
          v21[3] = *((_OWORD *)v20 + 3);
          v21[4] = *((_OWORD *)v20 + 4);
          v21[5] = *((_OWORD *)v20 + 5);
          v21[6] = *((_OWORD *)v20 + 6);
          v21[7] = *((_OWORD *)v20 + 7);
          v21 += 8;
          v20 = (SystemSettings::StorageSenseHandlers::FileRemovalRecommender *)((char *)v20 + 128);
          --v22;
        }
        while ( v22 );
        *v21 = *(_OWORD *)v20;
        v21[1] = *((_OWORD *)v20 + 1);
        v21[2] = *((_OWORD *)v20 + 2);
        v21[3] = *((_OWORD *)v20 + 3);
        v21[4] = *((_OWORD *)v20 + 4);
        LOBYTE(v21) = v29;
        std::_Pop_heap_unchecked__WIN32_FIND_DATAW____lambda_0dcb0dbb010333414d94d8cd0edab34c___(v13, v17, v21);
        v31[1] = (SystemSettings::StorageSenseHandlers::FileRemovalRecommender *)((char *)v31[1] - 592);
        v23 = operator new(0x70u);
        v34[0] = v23;
        *(_OWORD *)v23 = 0;
        v23[2] = 1;
        v23[3] = 1;
        *(_QWORD *)v23 = &std::_Ref_count_obj2<SystemSettings::StorageSenseHandlers::UserFileRemovalRecommendation>::`vftable';
        *((_QWORD *)v23 + 3) = 0;
        *((_OWORD *)v23 + 6) = 0;
        *((_QWORD *)v23 + 2) = &SystemSettings::StorageSenseHandlers::UserFileRemovalRecommendation::`vftable';
        *((_OWORD *)v23 + 2) = 0;
        *((_QWORD *)v23 + 6) = 0;
        *((_QWORD *)v23 + 7) = 7;
        *((_WORD *)v23 + 16) = 0;
        *((_OWORD *)v23 + 4) = 0;
        *((_QWORD *)v23 + 10) = 0;
        *((_QWORD *)v23 + 11) = 7;
        *((_WORD *)v23 + 32) = 0;
        v43[0] = v23 + 4;
        v43[1] = v23;
        v24 = &v36;
        v25 = v41;
        v26 = 4;
        do
        {
          *(_OWORD *)v24 = *v25;
          *((_OWORD *)v24 + 1) = v25[1];
          *((_OWORD *)v24 + 2) = v25[2];
          *((_OWORD *)v24 + 3) = v25[3];
          *((_OWORD *)v24 + 4) = v25[4];
          *((_OWORD *)v24 + 5) = v25[5];
          *((_OWORD *)v24 + 6) = v25[6];
          *((_OWORD *)v24 + 7) = v25[7];
          v24 += 128;
          v25 += 8;
          --v26;
        }
        while ( v26 );
        *(_OWORD *)v24 = *v25;
        *((_OWORD *)v24 + 1) = v25[1];
        *((_OWORD *)v24 + 2) = v25[2];
        *((_OWORD *)v24 + 3) = v25[3];
        *((_OWORD *)v24 + 4) = v25[4];
        std::wstring::assign(v23 + 8, v40);
        std::wstring::operator=(v23 + 16, a2);
        v23[26] = v39;
        v23[27] = v38;
        *((_QWORD *)v23 + 12) = v37;
        v28 = std::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListHandlerEvent>::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListHandlerEvent>(
                v35,
                v43,
                v27);
        SystemSettings::StorageSenseHandlers::FileRemovalRecommender::CategorizeRecommendationItem(
          a1,
          v42,
          v33,
          v30,
          v28);
        std::_Ref_count_base::_Decref((std::_Ref_count_base *)v23);
        ++v19;
        v13 = v31[0];
        if ( v19 >= v18 )
          break;
        v17 = v31[1];
      }
    }
    if ( !v13 )
      return 0;
    goto LABEL_34;
  }
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    (void *)0x90,
    (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\recommenderengine.cpp",
    (const char *)(unsigned int)RecentFilesTimeBounds,
    (int)"%hs",
    "CleanupRecommendations");
  if ( v31[0] )
    std::_Deallocate<16>(v31[0], 16 * ((signed __int64)(v32 - (unsigned __int64)v31[0]) >> 4));
  return v15;
}

```

## disassembly

```asm
0x180077ae0  mov     [rsp-8+arg_10], rbx
0x180077ae5  push    rbp
0x180077ae6  push    rsi
0x180077ae7  push    rdi
0x180077ae8  push    r12
0x180077aea  push    r13
0x180077aec  push    r14
0x180077aee  push    r15
0x180077af0  lea     rbp, [rsp-6B0h]
0x180077af8  sub     rsp, 7B0h
0x180077aff  mov     rax, cs:__security_cookie
0x180077b06  xor     rax, rsp
0x180077b09  mov     [rbp+6E0h+var_40], rax
0x180077b10  mov     r13, rdx
0x180077b13  mov     rsi, rcx
0x180077b16  xor     r14d, r14d
0x180077b19  xorps   xmm0, xmm0
0x180077b1c  movdqu  xmmword ptr [rsp+7E0h+var_7A0], xmm0
0x180077b22  mov     [rsp+7E0h+var_790], r14
0x180077b27  xor     edx, edx; Val
0x180077b29  mov     r8d, 250h; Size
0x180077b2f  lea     rcx, [rbp+6E0h+FindFileData]; void *
0x180077b36  call    memset_0
0x180077b3b  lea     r8, asc_18010F654; "\\*"
0x180077b42  mov     rdx, r13
0x180077b45  lea     rcx, [rbp+6E0h+var_2B0]
0x180077b4c  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x180077b51  mov     rcx, rax
0x180077b54  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180077b59  lea     rdx, [rbp+6E0h+FindFileData]; lpFindFileData
0x180077b60  mov     rcx, rax; lpFileName
0x180077b63  call    cs:__imp_FindFirstFileW
0x180077b69  mov     rdi, rax
0x180077b6c  lea     rcx, [rbp+6E0h+var_2B0]
0x180077b73  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180077b78  test    byte ptr [rbp+6E0h+FindFileData.dwFileAttributes], 10h
0x180077b7f  jnz     loc_180077C1C
0x180077b85  lea     rcx, [rbp+6E0h+FindFileData.cFileName]; pszPath
0x180077b8c  call    cs:__imp_PathFindExtensionW
0x180077b92  cmp     [rax], r14w
0x180077b96  jz      loc_180077C1C
0x180077b9c  lea     rbx, [rsi+0A8h]
0x180077ba3  mov     [rsp+7E0h+var_778], rax
0x180077ba8  or      r8, 0FFFFFFFFFFFFFFFFh
0x180077bac  inc     r8
0x180077baf  cmp     [rax+r8*2], r14w
0x180077bb4  jnz     short loc_180077BAC
0x180077bb6  mov     [rsp+7E0h+var_770], r8
0x180077bbb  add     r8, r8; unsigned __int64
0x180077bbe  mov     rdx, rax; unsigned __int8 *
0x180077bc1  call    ?_Fnv1a_append_bytes@std@@YA_K_KQEBE_K@Z; std::_Fnv1a_append_bytes(unsigned __int64,uchar const * const,unsigned __int64)
0x180077bc6  mov     r9, rax
0x180077bc9  lea     r8, [rsp+7E0h+var_778]
0x180077bce  lea     rdx, [rsp+7E0h+var_768]
0x180077bd3  mov     rcx, rbx
0x180077bd6  call    ??$_Find_last@V?$basic_string_view@GU?$char_traits@G@std@@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string_view@GU?$char_traits@G@std@@@std@@V?$_Uhash_compare@V?$basic_string_view@GU?$char_traits@G@std@@@std@@U?$hash@V?$basic_string_view@GU?$char_traits@G@std@@@std@@@2@U?$equal_to@V?$basic_string_view@GU?$char_traits@G@std@@@std@@@2@@2@V?$allocator@V?$basic_string_view@GU?$char_traits@G@std@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@V?$basic_string_view@GU?$char_traits@G@std@@@std@@PEAX@std@@@1@AEBV?$basic_string_view@GU?$char_traits@G@std@@@1@_K@Z; std::_Hash<std::_Uset_traits<std::basic_string_view<ushort>,std::_Uhash_compare<std::basic_string_view<ushort>,std::hash<std::basic_string_view<ushort>>,std::equal_to<std::basic_string_view<ushort>>>,std::allocator<std::basic_string_view<ushort>>,0>>::_Find_last<std::basic_string_view<ushort>>(std::basic_string_view<ushort> const &,unsigned __int64)
0x180077bdb  mov     rcx, [rax+8]
0x180077bdf  test    rcx, rcx
0x180077be2  jnz     short loc_180077BE8
0x180077be4  mov     rcx, [rbx+8]
0x180077be8  cmp     rcx, [rsi+0B0h]
0x180077bef  jnz     short loc_180077C1C
0x180077bf1  mov     rax, [rsi]
0x180077bf4  lea     rdx, [rbp+6E0h+FindFileData]
0x180077bfb  mov     rcx, rsi
0x180077bfe  mov     rax, [rax+38h]
0x180077c02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077c07  test    al, al
0x180077c09  jz      short loc_180077C1C
0x180077c0b  lea     rdx, [rbp+6E0h+FindFileData]
0x180077c12  lea     rcx, [rsp+7E0h+var_7A0]
0x180077c17  call    std__priority_queue__WIN32_FIND_DATAW_std__vector__WIN32_FIND_DATAW_std__allocator__WIN32_FIND_DATAW_____lambda_0dcb0dbb010333414d94d8cd0edab34c_____push
0x180077c1c  lea     rdx, [rbp+6E0h+FindFileData]; lpFindFileData
0x180077c23  mov     rcx, rdi; hFindFile
0x180077c26  call    cs:__imp_FindNextFileW
0x180077c2c  test    eax, eax
0x180077c2e  jz      short loc_180077C3D
0x180077c30  cmp     [rsi+0E8h], r14b
0x180077c37  jz      loc_180077B78
0x180077c3d  mov     rcx, rdi; hFindFile
0x180077c40  call    cs:__imp_FindClose
0x180077c46  call    cs:__imp_GetLastError
0x180077c4c  lea     rdi, aCleanuprecomme; "CleanupRecommendations"
0x180077c53  lea     r15, aHs; "%hs"
0x180077c5a  cmp     eax, 12h
0x180077c5d  jz      short loc_180077C90
0x180077c5f  test    eax, eax
0x180077c61  jle     short loc_180077C6B
0x180077c63  movzx   eax, ax
0x180077c66  or      eax, 80070000h
0x180077c6b  mov     rcx, [rbp+6E8h]; this
0x180077c72  mov     [rsp+7E0h+var_7B8], rdi; char *
0x180077c77  mov     qword ptr [rsp+7E0h+var_7C0], r15; int
0x180077c7c  mov     r9d, eax; char *
0x180077c7f  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\coresettinghandlers"...
0x180077c86  mov     edx, 86h; void *
0x180077c8b  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180077c90  mov     rcx, [rsp+7E0h+var_7A0]; this
0x180077c95  cmp     rcx, [rsp+7E0h+var_7A0+8]
0x180077c9a  jnz     short loc_180077CB4
0x180077c9c  test    rcx, rcx
0x180077c9f  jz      loc_180077FBD
0x180077ca5  mov     rdi, 14C1BACF914C1BADh
0x180077caf  jmp     loc_180077FA1
0x180077cb4  mov     qword ptr [rsp+7E0h+var_780.dwLowDateTime], r14
0x180077cb9  mov     qword ptr [rsp+7E0h+var_7A8.dwLowDateTime], r14
0x180077cbe  lea     r8, [rsp+7E0h+var_7A8]; struct _FILETIME *
0x180077cc3  lea     rdx, [rsp+7E0h+var_780]; struct _FILETIME *
0x180077cc8  call    ?GetRecentFilesTimeBounds@FileRemovalRecommender@StorageSenseHandlers@SystemSettings@@IEAAJPEAU_FILETIME@@0@Z; SystemSettings::StorageSenseHandlers::FileRemovalRecommender::GetRecentFilesTimeBounds(_FILETIME *,_FILETIME *)
0x180077ccd  mov     ebx, eax
0x180077ccf  test    eax, eax
0x180077cd1  jns     short loc_180077D30
0x180077cd3  mov     rcx, [rbp+6E8h]; this
0x180077cda  mov     [rsp+7E0h+var_7B8], rdi; char *
0x180077cdf  mov     qword ptr [rsp+7E0h+var_7C0], r15; int
0x180077ce4  mov     r9d, eax; char *
0x180077ce7  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\coresettinghandlers"...
0x180077cee  mov     edx, 90h; void *
0x180077cf3  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180077cf8  nop
0x180077cf9  mov     rcx, [rsp+7E0h+var_7A0]
0x180077cfe  test    rcx, rcx
0x180077d01  jz      short loc_180077D29
0x180077d03  mov     rax, [rsp+7E0h+var_790]
0x180077d08  sub     rax, rcx
0x180077d0b  sar     rax, 4
0x180077d0f  mov     rdi, 14C1BACF914C1BADh
0x180077d19  imul    rax, rdi
0x180077d1d  imul    rdx, rax, 250h
0x180077d24  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180077d29  mov     eax, ebx
0x180077d2b  jmp     loc_180077FBF
0x180077d30  mov     rdx, [rsp+7E0h+var_7A0+8]
0x180077d35  mov     rbx, rdx
0x180077d38  mov     rcx, [rsp+7E0h+var_7A0]
0x180077d3d  sub     rbx, rcx
0x180077d40  sar     rbx, 4
0x180077d44  mov     rdi, 14C1BACF914C1BADh
0x180077d4e  imul    rbx, rdi
0x180077d52  mov     eax, 14h
0x180077d57  cmp     rbx, rax
0x180077d5a  cmova   rbx, rax
0x180077d5e  mov     r15, r14
0x180077d61  test    rbx, rbx
0x180077d64  jz      loc_180077F9C
0x180077d6a  mov     rax, rcx
0x180077d6d  lea     r8, [rbp+6E0h+var_500]
0x180077d74  mov     r9d, 4
0x180077d7a  movups  xmm0, xmmword ptr [rax]
0x180077d7d  movups  xmmword ptr [r8], xmm0
0x180077d81  movups  xmm1, xmmword ptr [rax+10h]
0x180077d85  movups  xmmword ptr [r8+10h], xmm1
0x180077d8a  movups  xmm0, xmmword ptr [rax+20h]
0x180077d8e  movups  xmmword ptr [r8+20h], xmm0
0x180077d93  movups  xmm1, xmmword ptr [rax+30h]
0x180077d97  movups  xmmword ptr [r8+30h], xmm1
0x180077d9c  movups  xmm0, xmmword ptr [rax+40h]
0x180077da0  movups  xmmword ptr [r8+40h], xmm0
0x180077da5  movups  xmm1, xmmword ptr [rax+50h]
0x180077da9  movups  xmmword ptr [r8+50h], xmm1
0x180077dae  movups  xmm0, xmmword ptr [rax+60h]
0x180077db2  movups  xmmword ptr [r8+60h], xmm0
0x180077db7  movups  xmm1, xmmword ptr [rax+70h]
0x180077dbb  movups  xmmword ptr [r8+70h], xmm1
0x180077dc0  lea     r8, [r8+80h]
0x180077dc7  lea     rax, [rax+80h]
0x180077dce  sub     r9, 1
0x180077dd2  jnz     short loc_180077D7A
0x180077dd4  movups  xmm0, xmmword ptr [rax]
0x180077dd7  movups  xmmword ptr [r8], xmm0
0x180077ddb  movups  xmm1, xmmword ptr [rax+10h]
0x180077ddf  movups  xmmword ptr [r8+10h], xmm1
0x180077de4  movups  xmm0, xmmword ptr [rax+20h]
0x180077de8  movups  xmmword ptr [r8+20h], xmm0
0x180077ded  movups  xmm1, xmmword ptr [rax+30h]
0x180077df1  movups  xmmword ptr [r8+30h], xmm1
0x180077df6  movups  xmm0, xmmword ptr [rax+40h]
0x180077dfa  movups  xmmword ptr [r8+40h], xmm0
0x180077dff  mov     r8b, [rsp+7E0h+var_7B0]
0x180077e04  call    std___Pop_heap_unchecked__WIN32_FIND_DATAW____lambda_0dcb0dbb010333414d94d8cd0edab34c___
0x180077e09  sub     [rsp+7E0h+var_7A0+8], 250h
0x180077e12  mov     ecx, 70h ; 'p'; Size
0x180077e17  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180077e1c  mov     r12, rax
0x180077e1f  mov     [rsp+7E0h+var_778], rax
0x180077e24  xorps   xmm0, xmm0
0x180077e27  movups  xmmword ptr [rax], xmm0
0x180077e2a  mov     dword ptr [rax+8], 1
0x180077e31  mov     dword ptr [rax+0Ch], 1
0x180077e38  lea     rax, ??_7?$_Ref_count_obj2@UUserFileRemovalRecommendation@StorageSenseHandlers@SystemSettings@@@std@@6B@; const std::_Ref_count_obj2<SystemSettings::StorageSenseHandlers::UserFileRemovalRecommendation>::`vftable'
0x180077e3f  mov     [r12], rax
0x180077e43  lea     r14, [r12+10h]
0x180077e48  xor     eax, eax
0x180077e4a  mov     [r14+8], rax
0x180077e4e  movups  xmmword ptr [r14+50h], xmm0
0x180077e53  lea     rax, ??_7UserFileRemovalRecommendation@StorageSenseHandlers@SystemSettings@@6B@; const SystemSettings::StorageSenseHandlers::UserFileRemovalRecommendation::`vftable'
0x180077e5a  mov     [r14], rax
0x180077e5d  movups  xmmword ptr [r14+10h], xmm0
0x180077e62  mov     qword ptr [r14+20h], 0
0x180077e6a  mov     ecx, 7
0x180077e6f  mov     [r14+28h], rcx
0x180077e73  xor     eax, eax
0x180077e75  mov     [r14+10h], ax
0x180077e7a  movups  xmmword ptr [r14+30h], xmm0
0x180077e7f  mov     [r14+40h], rax
0x180077e83  mov     [r14+48h], rcx
0x180077e87  mov     [r14+30h], ax
0x180077e8c  mov     [rbp+6E0h+var_2B0], r14
0x180077e93  mov     [rbp+6E0h+var_2A8], r12
0x180077e9a  lea     rax, [rbp+6E0h+var_750]
0x180077e9e  lea     rcx, [rbp+6E0h+var_500]
0x180077ea5  mov     edx, 4
0x180077eaa  lea     r8d, [rdx+7Ch]
0x180077eae  movups  xmm0, xmmword ptr [rcx]
0x180077eb1  movups  xmmword ptr [rax], xmm0
0x180077eb4  movups  xmm1, xmmword ptr [rcx+10h]
0x180077eb8  movups  xmmword ptr [rax+10h], xmm1
0x180077ebc  movups  xmm0, xmmword ptr [rcx+20h]
0x180077ec0  movups  xmmword ptr [rax+20h], xmm0
0x180077ec4  movups  xmm1, xmmword ptr [rcx+30h]
0x180077ec8  movups  xmmword ptr [rax+30h], xmm1
0x180077ecc  movups  xmm0, xmmword ptr [rcx+40h]
0x180077ed0  movups  xmmword ptr [rax+40h], xmm0
0x180077ed4  movups  xmm1, xmmword ptr [rcx+50h]
0x180077ed8  movups  xmmword ptr [rax+50h], xmm1
0x180077edc  movups  xmm0, xmmword ptr [rcx+60h]
0x180077ee0  movups  xmmword ptr [rax+60h], xmm0
0x180077ee4  movups  xmm1, xmmword ptr [rcx+70h]
0x180077ee8  movups  xmmword ptr [rax+70h], xmm1
0x180077eec  add     rax, r8
0x180077eef  add     rcx, r8
0x180077ef2  sub     rdx, 1
0x180077ef6  jnz     short loc_180077EAE
0x180077ef8  movups  xmm0, xmmword ptr [rcx]
0x180077efb  movups  xmmword ptr [rax], xmm0
0x180077efe  movups  xmm1, xmmword ptr [rcx+10h]
0x180077f02  movups  xmmword ptr [rax+10h], xmm1
0x180077f06  movups  xmm0, xmmword ptr [rcx+20h]
0x180077f0a  movups  xmmword ptr [rax+20h], xmm0
0x180077f0e  movups  xmm1, xmmword ptr [rcx+30h]
0x180077f12  movups  xmmword ptr [rax+30h], xmm1
0x180077f16  movups  xmm0, xmmword ptr [rcx+40h]
0x180077f1a  movups  xmmword ptr [rax+40h], xmm0
0x180077f1e  lea     rcx, [r14+10h]
0x180077f22  lea     rdx, [rbp+6E0h+var_724]
0x180077f26  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180077f2b  lea     rcx, [r14+30h]
0x180077f2f  mov     rdx, r13
0x180077f32  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180077f37  mov     eax, [rbp+6E0h+var_730]
0x180077f3a  mov     [r14+58h], eax
0x180077f3e  mov     eax, [rbp+6E0h+var_734]
0x180077f41  mov     [r14+5Ch], eax
0x180077f45  mov     rax, [rbp+6E0h+var_73C]
0x180077f49  mov     [r14+50h], rax
0x180077f4d  lea     rdx, [rbp+6E0h+var_2B0]
0x180077f54  lea     rcx, [rsp+7E0h+var_768]
0x180077f59  call    ??$?0UCleanupListOperationProgress@StorageSenseHandlers@SystemSettings@@$0A@@?$shared_ptr@UCleanupListHandlerEvent@StorageSenseHandlers@SystemSettings@@@std@@QEAA@AEBV?$shared_ptr@UCleanupListOperationProgress@StorageSenseHandlers@SystemSettings@@@1@@Z; std::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListHandlerEvent>::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListHandlerEvent>(std::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListOperationProgress> const &)
0x180077f5e  mov     qword ptr [rsp+7E0h+var_7C0], rax
0x180077f63  mov     r9, qword ptr [rsp+7E0h+var_7A8.dwLowDateTime]
0x180077f68  mov     r8, qword ptr [rsp+7E0h+var_780.dwLowDateTime]
0x180077f6d  mov     rdx, [rbp+6E0h+var_4EC]
0x180077f74  mov     rcx, rsi
0x180077f77  call    ?CategorizeRecommendationItem@FileRemovalRecommender@StorageSenseHandlers@SystemSettings@@IEAAXU_FILETIME@@00V?$shared_ptr@UUserFileRemovalRecommendation@StorageSenseHandlers@SystemSettings@@@std@@@Z; SystemSettings::StorageSenseHandlers::FileRemovalRecommender::CategorizeRecommendationItem(_FILETIME,_FILETIME,_FILETIME,std::shared_ptr<SystemSettings::StorageSenseHandlers::UserFileRemovalRecommendation>)
0x180077f7c  nop
0x180077f7d  mov     rcx, r12; this
0x180077f80  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180077f85  inc     r15
0x180077f88  mov     rcx, [rsp+7E0h+var_7A0]
0x180077f8d  cmp     r15, rbx
0x180077f90  jnb     short loc_180077F9C
0x180077f92  mov     rdx, [rsp+7E0h+var_7A0+8]
0x180077f97  jmp     loc_180077D6A
0x180077f9c  test    rcx, rcx
0x180077f9f  jz      short loc_180077FBD
0x180077fa1  mov     rax, [rsp+7E0h+var_790]
0x180077fa6  sub     rax, rcx
0x180077fa9  sar     rax, 4
0x180077fad  imul    rax, rdi
0x180077fb1  imul    rdx, rax, 250h
0x180077fb8  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180077fbd  xor     eax, eax
0x180077fbf  mov     rcx, [rbp+6E0h+var_40]
0x180077fc6  xor     rcx, rsp; StackCookie
0x180077fc9  call    __security_check_cookie
0x180077fce  mov     rbx, [rsp+7E0h+arg_10]
0x180077fd6  add     rsp, 7B0h
0x180077fdd  pop     r15
0x180077fdf  pop     r14
0x180077fe1  pop     r13
0x180077fe3  pop     r12
0x180077fe5  pop     rdi
0x180077fe6  pop     rsi
0x180077fe7  pop     rbp
0x180077fe8  retn
```
