# Util::RecursiveScanFolder

- ea: `0x18003107c`
- end: `0x180031558`
- name: `Util::RecursiveScanFolder`
- size: `1244`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003107c`
- `0x180031560`

## callees

- `0x18000d030`
- `0x18000ddb0`
- `0x180012734`
- `0x180012ce0`
- `0x18001c130`
- `0x18001c208`
- `0x18001f634`
- `0x18002dcf4`
- `0x18002e45c`
- `0x18002e4f0`
- `0x18003107c`
- `0x180032040`
- `0x180034018`
- `0x1800345bc`
- `0x18003aef8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800314eb`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800314eb`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x180031161`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x180031161`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800314fc`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800314fc`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18003124d`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180031363`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18003124d`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180031363`
- `cldapi!CfGetPlaceholderStateFromFindData` at `0x1800311f6`
- `cldapi!CfGetPlaceholderStateFromFindData` at `0x1800311f6`

## string_xrefs

- `0x18003112b`: `onecore\drivers\storage\storsvc\service\storagepolicy.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Util::RecursiveScanFolder(
        int a1,
        __int64 a2,
        unsigned int a3,
        _QWORD *a4,
        __int64 a5,
        _BYTE *a6,
        __int64 a7)
{
  unsigned int v7; // edi
  __int64 v8; // rsi
  int v10; // eax
  unsigned int v11; // ebx
  HANDLE FirstFile; // r13
  int v14; // r12d
  int v15; // r15d
  int v16; // edx
  int v17; // edx
  DWORD dwFileAttributes; // edx
  char Data; // bl
  LONG v20; // eax
  unsigned int v21; // r8d
  FILETIME *p_ftLastWriteTime; // rcx
  _QWORD *v23; // r8
  _QWORD *i; // rdx
  __int64 v25; // rax
  _QWORD *v26; // rdx
  char *v27; // r10
  int v28; // ecx
  int v29; // r9d
  __int64 v30; // rbx
  __int64 v31; // rax
  unsigned int v32; // r8d
  FILETIME *p_ftLastAccessTime; // rsi
  _QWORD *v34; // rax
  std::_Ref_count_base *v35; // rbx
  std::_Ref_count_base *v36; // rdx
  std::_Ref_count_base *v37; // rcx
  std::_Ref_count_base *v38; // rcx
  _QWORD *v39; // rax
  std::_Ref_count_base *v40; // rdx
  std::_Ref_count_base *v41; // rcx
  __int64 v42; // rax
  int lpSearchFilter; // [rsp+20h] [rbp-E0h]
  char v44[8]; // [rsp+40h] [rbp-C0h] BYREF
  std::_Ref_count_base *v45[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v46; // [rsp+58h] [rbp-A8h]
  unsigned int v47; // [rsp+60h] [rbp-A0h]
  __int64 v48; // [rsp+68h] [rbp-98h]
  unsigned __int64 v49; // [rsp+70h] [rbp-90h]
  _QWORD *v50; // [rsp+78h] [rbp-88h]
  __int128 v51; // [rsp+80h] [rbp-80h]
  __int128 v52; // [rsp+90h] [rbp-70h]
  int v53[2]; // [rsp+A0h] [rbp-60h]
  _BYTE *v54; // [rsp+A8h] [rbp-58h]
  _BYTE *v55; // [rsp+B0h] [rbp-50h]
  char v56[8]; // [rsp+B8h] [rbp-48h] BYREF
  std::_Ref_count_base *v57; // [rsp+C0h] [rbp-40h]
  char v58[8]; // [rsp+C8h] [rbp-38h] BYREF
  std::_Ref_count_base *v59; // [rsp+D0h] [rbp-30h]
  _BYTE v60[32]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v61[40]; // [rsp+F8h] [rbp-8h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+120h] [rbp+20h] BYREF
  WCHAR FileName[264]; // [rsp+370h] [rbp+270h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+5D8h] [rbp+4D8h]

  v50 = a4;
  v7 = a3;
  v47 = a3;
  v8 = a2;
  v46 = a2;
  *(_QWORD *)v53 = a5;
  v54 = a6;
  v48 = a7;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  *(_OWORD *)v45 = 0;
  *a6 = 0;
  v10 = StringCchPrintfW(FileName, 0x104u, L"%s\\*.*", v8);
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x687,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagepolicy.cpp",
      (const char *)(unsigned int)v10,
      lpSearchFilter);
    return v11;
  }
  FirstFile = FindFirstFileExW(FileName, FindExInfoBasic, &FindFileData, FindExSearchNameMatch, 0, 2u);
  if ( FirstFile == (HANDLE)-1LL )
    return (unsigned int)-2147023728;
  v14 = 0;
  v15 = 0;
  while ( 1 )
  {
    v16 = FindFileData.cFileName[0] - 46;
    if ( FindFileData.cFileName[0] == 46 )
      v16 = FindFileData.cFileName[1];
    if ( !v16 )
      goto LABEL_53;
    v17 = FindFileData.cFileName[0] - 46;
    if ( FindFileData.cFileName[0] == 46 )
    {
      v17 = FindFileData.cFileName[1] - 46;
      if ( FindFileData.cFileName[1] == 46 )
        v17 = FindFileData.cFileName[2];
    }
    if ( !v17 )
      goto LABEL_53;
    ++v14;
    dwFileAttributes = FindFileData.dwFileAttributes;
    if ( (FindFileData.dwFileAttributes & 6) != 0 )
      goto LABEL_53;
    Data = 0;
    if ( a1 == 1 )
    {
      if ( (FindFileData.dwFileAttributes & 0x400) == 0 )
        goto LABEL_53;
      Data = CfGetPlaceholderStateFromFindData(&FindFileData);
      if ( (Data & 1) == 0 )
        goto LABEL_53;
      dwFileAttributes = FindFileData.dwFileAttributes;
    }
    if ( (dwFileAttributes & 0x10) == 0 )
      break;
    if ( StringCchPrintfW(FileName, 0x104u, L"%s\\%s", v8, FindFileData.cFileName) < 0 )
    {
      dwFileAttributes = FindFileData.dwFileAttributes;
      break;
    }
    if ( a1 == 5 )
    {
      v20 = CompareFileTime(&FindFileData.ftLastAccessTime, &FindFileData.ftLastWriteTime);
      p_ftLastWriteTime = &FindFileData.ftLastWriteTime;
      if ( v20 == 1 )
        p_ftLastWriteTime = &FindFileData.ftLastAccessTime;
      if ( (unsigned int)RecursiveUtil::CompareTimeThreshold(p_ftLastWriteTime, (struct _FILETIME *)v7, v21) != -1 )
        goto LABEL_53;
      v23 = *(_QWORD **)(v48 + 8);
      for ( i = (_QWORD *)*v23; i != v23; i = (_QWORD *)*v26 )
      {
        v25 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(i + 2);
        v27 = (char *)FileName - v25;
        do
        {
          v28 = *(unsigned __int16 *)&v27[v25];
          v29 = *(unsigned __int16 *)v25 - v28;
          if ( v29 )
            break;
          v25 += 2;
        }
        while ( v28 );
        if ( !v29 )
          goto LABEL_53;
      }
    }
    v44[0] = 0;
    v30 = *(_QWORD *)v53;
    Util::RecursiveScanFolder(a1, (unsigned int)FileName, v7, (_DWORD)v50, *(__int64 *)v53, (__int64)v44, v48);
    if ( v44[0] )
    {
      ++v15;
      v31 = std::wstring::wstring((__int64)v61, (__int64)FileName);
      std::vector<std::wstring>::push_back(v30, v31);
      std::wstring::_Tidy_deallocate(v61);
    }
LABEL_53:
    if ( !FindNextFileW(FirstFile, &FindFileData) )
    {
      FindClose(FirstFile);
      if ( v14 == v15 )
        *v54 = 1;
      if ( v45[1] )
        std::_Ref_count_base::_Decref(v45[1]);
      return 0;
    }
  }
  v49 = __PAIR64__(FindFileData.nFileSizeHigh, FindFileData.nFileSizeLow);
  if ( a1 == 1 && ((Data & 0x28) != 8 || (dwFileAttributes & 0x80000) != 0) )
    goto LABEL_53;
  p_ftLastAccessTime = &FindFileData.ftLastWriteTime;
  if ( CompareFileTime(&FindFileData.ftLastAccessTime, &FindFileData.ftLastWriteTime) == 1 )
    p_ftLastAccessTime = &FindFileData.ftLastAccessTime;
  if ( (unsigned int)RecursiveUtil::CompareTimeThreshold(p_ftLastAccessTime, (struct _FILETIME *)v7, v32) != -1
    || StringCchPrintfW(FileName, 0x104u, L"%s\\%s", v46, FindFileData.cFileName) < 0 )
  {
LABEL_52:
    v8 = v46;
    goto LABEL_53;
  }
  if ( a1 == 1 )
  {
    v39 = (_QWORD *)std::make_shared<CloudFilePolicy,>(v58);
    v52 = 0;
    *(_QWORD *)&v52 = *v39;
    v35 = (std::_Ref_count_base *)v52;
    v40 = (std::_Ref_count_base *)v39[1];
    *v39 = 0;
    v39[1] = 0;
    v52 = *(_OWORD *)v45;
    v45[0] = v35;
    v41 = v45[1];
    v45[1] = v40;
    if ( *((_QWORD *)&v52 + 1) )
      std::_Ref_count_base::_Decref(v41);
    v38 = v59;
    goto LABEL_49;
  }
  if ( a1 == 5 )
  {
    v34 = (_QWORD *)std::make_shared<DownloadsFolderPolicy,>(v56);
    v51 = 0;
    *(_QWORD *)&v51 = *v34;
    v35 = (std::_Ref_count_base *)v51;
    v36 = (std::_Ref_count_base *)v34[1];
    *v34 = 0;
    v34[1] = 0;
    v51 = *(_OWORD *)v45;
    v45[0] = v35;
    v37 = v45[1];
    v45[1] = v36;
    if ( *((_QWORD *)&v51 + 1) )
      std::_Ref_count_base::_Decref(v37);
    v38 = v57;
LABEL_49:
    if ( v38 )
      std::_Ref_count_base::_Decref(v38);
    *((_QWORD *)v35 + 6) = v49;
    v55 = v60;
    v42 = std::wstring::wstring((__int64)v60, (__int64)FileName);
    CCleanupPolicy::SetTarget(v35, v42);
    *((FILETIME *)v35 + 7) = *p_ftLastAccessTime;
    std::list<std::shared_ptr<CCleanupPolicy>>::_Emplace<std::shared_ptr<CCleanupPolicy> const &>(v50, *v50, v45);
    ++v15;
    v7 = v47;
    goto LABEL_52;
  }
  if ( v45[1] )
    std::_Ref_count_base::_Decref(v45[1]);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18003107c  push    rbp
0x18003107e  push    rbx
0x18003107f  push    rsi
0x180031080  push    rdi
0x180031081  push    r12
0x180031083  push    r13
0x180031085  push    r14
0x180031087  push    r15
0x180031089  lea     rbp, [rsp-498h]
0x180031091  sub     rsp, 598h
0x180031098  mov     rax, cs:__security_cookie
0x18003109f  xor     rax, rsp
0x1800310a2  mov     [rbp+4D0h+var_50], rax
0x1800310a9  mov     [rsp+5D0h+var_558], r9
0x1800310ae  mov     edi, r8d
0x1800310b1  mov     [rsp+5D0h+var_570], r8d
0x1800310b6  mov     rsi, rdx
0x1800310b9  mov     [rsp+5D0h+var_578], rdx
0x1800310be  mov     r14d, ecx
0x1800310c1  mov     rax, [rbp+4D0h+arg_20]
0x1800310c8  mov     qword ptr [rbp+4D0h+var_530], rax
0x1800310cc  mov     rbx, [rbp+4D0h+arg_28]
0x1800310d3  mov     [rbp+4D0h+var_528], rbx
0x1800310d7  mov     rax, [rbp+4D0h+arg_30]
0x1800310de  mov     [rsp+5D0h+var_568], rax
0x1800310e3  xor     edx, edx; Val
0x1800310e5  mov     r8d, 250h; Size
0x1800310eb  lea     rcx, [rbp+4D0h+FindFileData]; void *
0x1800310ef  call    memset_0
0x1800310f4  xorps   xmm0, xmm0
0x1800310f7  movdqu  xmmword ptr [rsp+5D0h+var_588], xmm0
0x1800310fd  mov     byte ptr [rbx], 0
0x180031100  mov     r9, rsi
0x180031103  lea     r8, aS; "%s\\*.*"
0x18003110a  mov     edx, 104h; unsigned __int64
0x18003110f  lea     rcx, [rbp+4D0h+FileName]; unsigned __int16 *
0x180031116  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003111b  mov     ebx, eax
0x18003111d  test    eax, eax
0x18003111f  jns     short loc_18003113E
0x180031121  mov     rcx, [rbp+4D8h]; this
0x180031128  mov     r9d, eax; char *
0x18003112b  lea     r8, aOnecoreDrivers_25; "onecore\\drivers\\storage\\storsvc\\ser"...
0x180031132  mov     edx, 687h; void *
0x180031137  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003113c  jmp     short loc_180031175
0x18003113e  mov     [rsp+5D0h+dwAdditionalFlags], 2; dwAdditionalFlags
0x180031146  mov     [rsp+5D0h+lpSearchFilter], 0; lpSearchFilter
0x18003114f  xor     r9d, r9d; fSearchOp
0x180031152  lea     r8, [rbp+4D0h+FindFileData]; lpFindFileData
0x180031156  lea     edx, [r9+1]; fInfoLevelId
0x18003115a  lea     rcx, [rbp+4D0h+FileName]; lpFileName
0x180031161  call    cs:__imp_FindFirstFileExW
0x180031167  mov     r13, rax
0x18003116a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003116e  jnz     short loc_18003117C
0x180031170  mov     ebx, 80070490h
0x180031175  mov     eax, ebx
0x180031177  jmp     loc_18003151F
0x18003117c  xor     r12d, r12d
0x18003117f  xor     r15d, r15d
0x180031182  mov     ecx, 2Eh ; '.'
0x180031187  movzx   edx, [rbp+4D0h+var_484]
0x18003118b  movzx   eax, cx
0x18003118e  sub     edx, eax
0x180031190  jnz     short loc_1800311A0
0x180031192  movzx   edx, [rbp+4D0h+var_482]
0x180031196  xor     eax, eax
0x180031198  movzx   ecx, ax
0x18003119b  sub     edx, ecx
0x18003119d  lea     ecx, [rax+2Eh]
0x1800311a0  test    edx, edx
0x1800311a2  jz      loc_1800314E4
0x1800311a8  movzx   edx, [rbp+4D0h+var_484]
0x1800311ac  movzx   eax, cx
0x1800311af  sub     edx, eax
0x1800311b1  jnz     short loc_1800311C9
0x1800311b3  movzx   edx, [rbp+4D0h+var_482]
0x1800311b7  movzx   eax, cx
0x1800311ba  sub     edx, eax
0x1800311bc  jnz     short loc_1800311C9
0x1800311be  movzx   edx, [rbp+4D0h+var_480]
0x1800311c2  xor     eax, eax
0x1800311c4  movzx   ecx, ax
0x1800311c7  sub     edx, ecx
0x1800311c9  test    edx, edx
0x1800311cb  jz      loc_1800314E4
0x1800311d1  inc     r12d
0x1800311d4  mov     edx, [rbp+4D0h+FindFileData]
0x1800311d7  test    dl, 6
0x1800311da  jnz     loc_1800314E4
0x1800311e0  xor     ebx, ebx
0x1800311e2  cmp     r14d, 1
0x1800311e6  jnz     short loc_18003120A
0x1800311e8  bt      edx, 0Ah
0x1800311ec  jnb     loc_1800314E4
0x1800311f2  lea     rcx, [rbp+4D0h+FindFileData]
0x1800311f6  call    cs:__imp_CfGetPlaceholderStateFromFindData
0x1800311fc  mov     ebx, eax
0x1800311fe  test    r14b, al
0x180031201  jz      loc_1800314E4
0x180031207  mov     edx, [rbp+4D0h+FindFileData]
0x18003120a  test    dl, 10h
0x18003120d  jz      loc_18003132F
0x180031213  lea     rax, [rbp+4D0h+var_484]
0x180031217  mov     [rsp+5D0h+lpSearchFilter], rax
0x18003121c  mov     r9, rsi
0x18003121f  lea     r8, aSS; "%s\\%s"
0x180031226  mov     edx, 104h; unsigned __int64
0x18003122b  lea     rcx, [rbp+4D0h+FileName]; unsigned __int16 *
0x180031232  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180031237  test    eax, eax
0x180031239  js      loc_18003132C
0x18003123f  cmp     r14d, 5
0x180031243  jnz     short loc_1800312BA
0x180031245  lea     rdx, [rbp+4D0h+FileTime2]; lpFileTime2
0x180031249  lea     rcx, [rbp+4D0h+FileTime1]; lpFileTime1
0x18003124d  call    cs:__imp_CompareFileTime
0x180031253  lea     rcx, [rbp+4D0h+FileTime2]
0x180031257  lea     rdx, [rbp+4D0h+FileTime1]
0x18003125b  cmp     eax, 1
0x18003125e  cmovz   rcx, rdx; lpFileTime1
0x180031262  mov     edx, edi; this
0x180031264  call    ?CompareTimeThreshold@RecursiveUtil@@YAJPEAU_FILETIME@@K@Z; RecursiveUtil::CompareTimeThreshold(_FILETIME *,ulong)
0x180031269  cmp     eax, 0FFFFFFFFh
0x18003126c  jnz     loc_1800314E4
0x180031272  mov     rax, [rsp+5D0h+var_568]
0x180031277  mov     r8, [rax+8]
0x18003127b  mov     rdx, [r8]
0x18003127e  cmp     rdx, r8
0x180031281  jz      short loc_1800312BA
0x180031283  lea     rcx, [rdx+10h]
0x180031287  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003128c  lea     r10, [rbp+4D0h+FileName]
0x180031293  sub     r10, rax
0x180031296  movzx   r9d, word ptr [rax]
0x18003129a  movzx   ecx, word ptr [rax+r10]
0x18003129f  sub     r9d, ecx
0x1800312a2  jnz     short loc_1800312AC
0x1800312a4  add     rax, 2
0x1800312a8  test    ecx, ecx
0x1800312aa  jnz     short loc_180031296
0x1800312ac  test    r9d, r9d
0x1800312af  jz      loc_1800314E4
0x1800312b5  mov     rdx, [rdx]
0x1800312b8  jmp     short loc_18003127E
0x1800312ba  mov     [rsp+5D0h+var_590], 0
0x1800312bf  mov     rax, [rsp+5D0h+var_568]
0x1800312c4  mov     [rsp+5D0h+var_5A0], rax
0x1800312c9  lea     rax, [rsp+5D0h+var_590]
0x1800312ce  mov     qword ptr [rsp+5D0h+dwAdditionalFlags], rax
0x1800312d3  mov     rbx, qword ptr [rbp+4D0h+var_530]
0x1800312d7  mov     [rsp+5D0h+lpSearchFilter], rbx; int
0x1800312dc  mov     r9, [rsp+5D0h+var_558]
0x1800312e1  mov     r8d, edi
0x1800312e4  lea     rdx, [rbp+4D0h+FileName]
0x1800312eb  mov     ecx, r14d
0x1800312ee  call    Util__RecursiveScanFolder
0x1800312f3  cmp     [rsp+5D0h+var_590], 0
0x1800312f8  jz      loc_1800314E4
0x1800312fe  inc     r15d
0x180031301  lea     rdx, [rbp+4D0h+FileName]
0x180031308  lea     rcx, [rbp+4D0h+var_4D8]
0x18003130c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180031311  nop
0x180031312  mov     rdx, rax
0x180031315  mov     rcx, rbx
0x180031318  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x18003131d  nop
0x18003131e  lea     rcx, [rbp+4D0h+var_4D8]
0x180031322  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180031327  jmp     loc_1800314E4
0x18003132c  mov     edx, [rbp+4D0h+FindFileData]
0x18003132f  mov     eax, [rbp+4D0h+var_490]
0x180031332  mov     dword ptr [rsp+5D0h+var_560], eax
0x180031336  mov     eax, [rbp+4D0h+var_494]
0x180031339  mov     dword ptr [rsp+5D0h+var_560+4], eax
0x18003133d  cmp     r14d, 1
0x180031341  jnz     short loc_18003135B
0x180031343  and     bl, 28h
0x180031346  cmp     bl, 8
0x180031349  setz    cl
0x18003134c  bt      edx, 13h
0x180031350  setnb   al
0x180031353  test    al, cl
0x180031355  jz      loc_1800314E4
0x18003135b  lea     rdx, [rbp+4D0h+FileTime2]; lpFileTime2
0x18003135f  lea     rcx, [rbp+4D0h+FileTime1]; lpFileTime1
0x180031363  call    cs:__imp_CompareFileTime
0x180031369  lea     rsi, [rbp+4D0h+FileTime2]
0x18003136d  lea     rcx, [rbp+4D0h+FileTime1]
0x180031371  cmp     eax, 1
0x180031374  cmovz   rsi, rcx
0x180031378  mov     edx, edi; this
0x18003137a  mov     rcx, rsi; lpFileTime1
0x18003137d  call    ?CompareTimeThreshold@RecursiveUtil@@YAJPEAU_FILETIME@@K@Z; RecursiveUtil::CompareTimeThreshold(_FILETIME *,ulong)
0x180031382  cmp     eax, 0FFFFFFFFh
0x180031385  jnz     loc_1800314DF
0x18003138b  lea     rax, [rbp+4D0h+var_484]
0x18003138f  mov     [rsp+5D0h+lpSearchFilter], rax
0x180031394  mov     r9, [rsp+5D0h+var_578]
0x180031399  lea     r8, aSS; "%s\\%s"
0x1800313a0  mov     edx, 104h; unsigned __int64
0x1800313a5  lea     rcx, [rbp+4D0h+FileName]; unsigned __int16 *
0x1800313ac  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800313b1  test    eax, eax
0x1800313b3  js      loc_1800314DF
0x1800313b9  mov     ecx, r14d
0x1800313bc  sub     ecx, 1
0x1800313bf  jz      short loc_180031427
0x1800313c1  cmp     ecx, 4
0x1800313c4  jnz     loc_180031542
0x1800313ca  lea     rcx, [rbp+4D0h+var_518]
0x1800313ce  call    ??$make_shared@VDownloadsFolderPolicy@@$$V@std@@YA?AV?$shared_ptr@VDownloadsFolderPolicy@@@0@XZ; std::make_shared<DownloadsFolderPolicy,>(void)
0x1800313d3  nop
0x1800313d4  xorps   xmm0, xmm0
0x1800313d7  movdqu  [rbp+4D0h+var_550], xmm0
0x1800313dc  mov     rbx, [rax]
0x1800313df  mov     qword ptr [rbp+4D0h+var_550], rbx
0x1800313e3  mov     rdx, [rax+8]
0x1800313e7  mov     qword ptr [rbp+4D0h+var_550+8], rdx
0x1800313eb  mov     qword ptr [rax], 0
0x1800313f2  mov     qword ptr [rax+8], 0
0x1800313fa  mov     rax, [rsp+5D0h+var_588]
0x1800313ff  mov     qword ptr [rbp+4D0h+var_550], rax
0x180031403  mov     [rsp+5D0h+var_588], rbx
0x180031408  mov     rcx, [rsp+5D0h+var_588+8]; this
0x18003140d  mov     qword ptr [rbp+4D0h+var_550+8], rcx
0x180031411  mov     [rsp+5D0h+var_588+8], rdx
0x180031416  test    rcx, rcx
0x180031419  jz      short loc_180031421
0x18003141b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180031420  nop
0x180031421  mov     rcx, [rbp+4D0h+var_510]
0x180031425  jmp     short loc_180031482
0x180031427  lea     rcx, [rbp+4D0h+var_508]
0x18003142b  call    ??$make_shared@VCloudFilePolicy@@$$V@std@@YA?AV?$shared_ptr@VCloudFilePolicy@@@0@XZ; std::make_shared<CloudFilePolicy,>(void)
0x180031430  nop
0x180031431  xorps   xmm0, xmm0
0x180031434  movdqu  [rbp+4D0h+var_540], xmm0
0x180031439  mov     rbx, [rax]
0x18003143c  mov     qword ptr [rbp+4D0h+var_540], rbx
0x180031440  mov     rdx, [rax+8]
0x180031444  mov     qword ptr [rbp+4D0h+var_540+8], rdx
0x180031448  mov     qword ptr [rax], 0
0x18003144f  mov     qword ptr [rax+8], 0
0x180031457  mov     rax, [rsp+5D0h+var_588]
0x18003145c  mov     qword ptr [rbp+4D0h+var_540], rax
0x180031460  mov     [rsp+5D0h+var_588], rbx
0x180031465  mov     rcx, [rsp+5D0h+var_588+8]; this
0x18003146a  mov     qword ptr [rbp+4D0h+var_540+8], rcx
0x18003146e  mov     [rsp+5D0h+var_588+8], rdx
0x180031473  test    rcx, rcx
0x180031476  jz      short loc_18003147E
0x180031478  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003147d  nop
0x18003147e  mov     rcx, [rbp+4D0h+var_500]; this
0x180031482  test    rcx, rcx
0x180031485  jz      short loc_18003148C
0x180031487  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003148c  mov     rdi, rbx
0x18003148f  mov     rax, [rsp+5D0h+var_560]
0x180031494  mov     [rbx+30h], rax
0x180031498  lea     rax, [rbp+4D0h+var_4F8]
0x18003149c  mov     [rbp+4D0h+var_520], rax
0x1800314a0  lea     rdx, [rbp+4D0h+FileName]
0x1800314a7  lea     rcx, [rbp+4D0h+var_4F8]
0x1800314ab  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800314b0  nop
0x1800314b1  mov     rdx, rax
0x1800314b4  mov     rcx, rbx
0x1800314b7  call    ?SetTarget@CCleanupPolicy@@QEAAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CCleanupPolicy::SetTarget(std::wstring)
0x1800314bc  mov     rax, [rsi]
0x1800314bf  mov     [rbx+38h], rax
0x1800314c3  lea     r8, [rsp+5D0h+var_588]
0x1800314c8  mov     rax, [rsp+5D0h+var_558]
0x1800314cd  mov     rdx, [rax]
0x1800314d0  mov     rcx, rax
0x1800314d3  call    ??$_Emplace@AEBV?$shared_ptr@VCCleanupPolicy@@@std@@@?$list@V?$shared_ptr@VCCleanupPolicy@@@std@@V?$allocator@V?$shared_ptr@VCCleanupPolicy@@@std@@@2@@std@@QEAAPEAU?$_List_node@V?$shared_ptr@VCCleanupPolicy@@@std@@PEAX@1@QEAU21@AEBV?$shared_ptr@VCCleanupPolicy@@@1@@Z; std::list<std::shared_ptr<CCleanupPolicy>>::_Emplace<std::shared_ptr<CCleanupPolicy> const &>(std::_List_node<std::shared_ptr<CCleanupPolicy>,void *> * const,std::shared_ptr<CCleanupPolicy> const &)
0x1800314d8  inc     r15d
0x1800314db  mov     edi, [rsp+5D0h+var_570]
0x1800314df  mov     rsi, [rsp+5D0h+var_578]
0x1800314e4  lea     rdx, [rbp+4D0h+FindFileData]; lpFindFileData
0x1800314e8  mov     rcx, r13; hFindFile
0x1800314eb  call    cs:__imp_FindNextFileW
0x1800314f1  test    eax, eax
0x1800314f3  jnz     loc_180031182
0x1800314f9  mov     rcx, r13; hFindFile
0x1800314fc  call    cs:__imp_FindClose
0x180031502  cmp     r12d, r15d
0x180031505  jnz     short loc_18003150E
0x180031507  mov     rax, [rbp+4D0h+var_528]
0x18003150b  mov     byte ptr [rax], 1
0x18003150e  mov     rcx, [rsp+5D0h+var_588+8]; this
0x180031513  test    rcx, rcx
0x180031516  jz      short loc_18003151D
0x180031518  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003151d  xor     eax, eax
0x18003151f  mov     rcx, [rbp+4D0h+var_50]
0x180031526  xor     rcx, rsp; StackCookie
  ... truncated ...
```
