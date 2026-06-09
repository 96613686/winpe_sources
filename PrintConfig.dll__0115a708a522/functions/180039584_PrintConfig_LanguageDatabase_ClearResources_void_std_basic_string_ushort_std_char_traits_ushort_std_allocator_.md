# PrintConfig::LanguageDatabase::ClearResources(void *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,bool,bool,bool)

- ea: `0x180039584`
- end: `0x180039950`
- name: `?ClearResources@LanguageDatabase@PrintConfig@@YAXPEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N22@Z`
- size: `972`
- prototype: `void __fastcall(HANDLE hPrinter, _QWORD *, __int64, char, char)`
- caller_count: `6`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x180013090`
- `0x18003a550`
- `0x1800446d8`
- `0x180047c18`
- `0x18004b124`
- `0x18004dcd8`

## callees

- `0x180003400`
- `0x180004558`
- `0x180006268`
- `0x18000e644`
- `0x18000e750`
- `0x18000fa4c`
- `0x180018f58`
- `0x180019388`
- `0x180019618`
- `0x180038bc4`
- `0x180039120`
- `0x180039584`
- `0x180039a24`
- `0x180039d64`
- `0x1801cb010`

## import_xrefs

- `KERNEL32!RemoveDirectoryW` at `0x1800397ab`
- `KERNEL32!RemoveDirectoryW` at `0x1800397ab`
- `KERNEL32!FreeLibrary` at `0x180039805`
- `KERNEL32!FreeLibrary` at `0x180039805`
- `KERNEL32!FindFirstFileW` at `0x1800396c2`
- `KERNEL32!FindFirstFileW` at `0x1800396c2`
- `KERNEL32!FindNextFileW` at `0x1800396de`
- `KERNEL32!FindNextFileW` at `0x1800396de`
- `KERNEL32!FindClose` at `0x1800397c1`
- `KERNEL32!FindClose` at `0x1800397c1`
- `WINSPOOL!DeletePrinterDataExW` at `0x180039881`
- `WINSPOOL!DeletePrinterDataExW` at `0x180039881`

## string_xrefs

- `0x180039877`: `ConfigDriverResources`
- `0x1800398b1`: `PrintConfig::LanguageDatabase::DeleteLanguage`
- `0x1800398aa`: `Failed to delete language "%ws" from language database (hr: 0x%x)`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall PrintConfig::LanguageDatabase::ClearResources(
        HANDLE hPrinter,
        _QWORD *a2,
        __int64 a3,
        char a4,
        char a5)
{
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r8
  char **v13; // r9
  const WCHAR *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r8
  BOOL NextFileW; // eax
  char **v18; // r9
  __int64 v19; // r8
  void **v20; // rax
  const WCHAR *v21; // rcx
  const WCHAR *v22; // rcx
  __int64 *v23; // rbx
  _QWORD *v24; // rdi
  const WCHAR *v25; // r8
  signed int v26; // eax
  __int64 **v27; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  int v30[2]; // [rsp+48h] [rbp-C0h] BYREF
  HMODULE hLibModule[2]; // [rsp+50h] [rbp-B8h] BYREF
  void (*v32)(void); // [rsp+60h] [rbp-A8h]
  __int64 v33; // [rsp+68h] [rbp-A0h]
  char **v34; // [rsp+70h] [rbp-98h] BYREF
  __int64 v35; // [rsp+80h] [rbp-88h]
  unsigned __int64 v36; // [rsp+88h] [rbp-80h]
  LPCWSTR lpExistingFileName[2]; // [rsp+90h] [rbp-78h] BYREF
  __int128 v38; // [rsp+A0h] [rbp-68h]
  HANDLE hFindFile; // [rsp+B0h] [rbp-58h]
  LPCWSTR lpFileName[4]; // [rsp+B8h] [rbp-50h] BYREF
  char v41; // [rsp+D8h] [rbp-30h]
  void *Src[5]; // [rsp+E0h] [rbp-28h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+108h] [rbp+0h] BYREF

  v33 = -2;
  v30[0] = 0;
  RevertToPrinterRAII::RevertToPrinterRAII((RevertToPrinterRAII *)hLibModule, v30);
  v10 = a2[2];
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v10) < 0xA )
    std::_Xlen_string();
  if ( a2[3] > 7u )
    a2 = (_QWORD *)*a2;
  std::wstring::wstring((char *)&v34, v8, v9, a2, v10, L"\\Resources", 10);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v35) < 7 )
    std::_Xlen_string();
  v13 = (char **)&v34;
  if ( v36 > 7 )
    v13 = v34;
  std::wstring::wstring((char *)lpExistingFileName, v11, v12, v13, v35, L"\\*.resx", 7);
  hFindFile = (HANDLE)-1LL;
  std::wstring::wstring((__int64)lpFileName, (__int64)lpExistingFileName);
  v41 = 1;
  while ( 1 )
  {
    std::wstring::~wstring((char **)lpExistingFileName);
    if ( v41 )
    {
      v41 = 0;
      v14 = (const WCHAR *)lpFileName;
      if ( lpFileName[3] > (LPCWSTR)7 )
        v14 = lpFileName[0];
      hFindFile = FindFirstFileW(v14, &FindFileData);
      LOBYTE(NextFileW) = hFindFile != (HANDLE)-1LL;
    }
    else
    {
      NextFileW = FindNextFileW(hFindFile, &FindFileData);
      if ( NextFileW )
        goto LABEL_14;
    }
    if ( !NextFileW )
      break;
LABEL_14:
    if ( v35 == 0x7FFFFFFFFFFFFFFELL )
      std::_Xlen_string();
    v18 = (char **)&v34;
    if ( v36 > 7 )
      v18 = v34;
    std::wstring::wstring((char *)Src, v15, v16, v18, v35, (void *)L"\\", 1);
    v20 = std::wstring::append(Src, FindFileData.cFileName, v19);
    *(_OWORD *)lpExistingFileName = 0;
    v38 = 0;
    *(_OWORD *)lpExistingFileName = *(_OWORD *)v20;
    v38 = *((_OWORD *)v20 + 1);
    v20[2] = 0;
    v20[3] = (void *)7;
    *(_WORD *)v20 = 0;
    std::wstring::~wstring((char **)Src);
    v21 = (const WCHAR *)lpExistingFileName;
    if ( *((_QWORD *)&v38 + 1) > 7u )
      v21 = lpExistingFileName[0];
    DeleteFileNowOrOnReboot(v21, 1);
  }
  v22 = (const WCHAR *)&v34;
  if ( v36 > 7 )
    v22 = (const WCHAR *)v34;
  RemoveDirectoryW(v22);
  if ( hFindFile != (HANDLE)-1LL )
    FindClose(hFindFile);
  std::wstring::~wstring((char **)lpFileName);
  std::wstring::~wstring((char **)&v34);
  if ( v32 && hLibModule[1] )
    v32();
  if ( hLibModule[0] )
    FreeLibrary(hLibModule[0]);
  if ( a4 || a5 )
  {
    PrintConfig::LanguageDatabase::GetPrinterLanguages((__int64 *)hLibModule, hPrinter, -1);
    v23 = *(__int64 **)hLibModule[0];
    while ( !*((_BYTE *)v23 + 25) )
    {
      v24 = v23 + 4;
      if ( a4 )
      {
        PrintConfig::LanguageDatabase::SetLanguageState(hPrinter, v23 + 4, 0);
      }
      else if ( a5 )
      {
        v25 = (unsigned __int64)v23[7] <= 7 ? (const WCHAR *)(v23 + 4) : (const WCHAR *)*v24;
        v26 = DeletePrinterDataExW(hPrinter, L"ConfigDriverResources", v25);
        if ( v26 )
        {
          if ( v26 > 0 )
            v26 = (unsigned __int16)v26 | 0x80070000;
          if ( (unsigned __int64)v23[7] > 7 )
            v24 = (_QWORD *)*v24;
          Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
            "PrintConfig::LanguageDatabase::DeleteLanguage",
            L"Failed to delete language \"%ws\" from language database (hr: 0x%x)",
            v24,
            (unsigned int)v26);
        }
      }
      v27 = (__int64 **)v23[2];
      if ( *((_BYTE *)v27 + 25) )
      {
        for ( i = (__int64 *)v23[1]; !*((_BYTE *)i + 25) && v23 == (__int64 *)i[2]; i = (__int64 *)i[1] )
          v23 = i;
        v23 = i;
      }
      else
      {
        v23 = (__int64 *)v23[2];
        for ( j = *v27; !*((_BYTE *)j + 25); j = (__int64 *)*j )
          v23 = j;
      }
    }
    std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>((void **)hLibModule);
  }
}

```

## disassembly

```asm
0x180039584  mov     rax, rsp
0x180039587  push    rbp
0x180039588  push    rdi
0x180039589  push    r13
0x18003958b  push    r14
0x18003958d  push    r15
0x18003958f  lea     rbp, [rax-288h]
0x180039596  sub     rsp, 360h
0x18003959d  mov     [rsp+380h+var_320], 0FFFFFFFFFFFFFFFEh
0x1800395a6  mov     [rax+18h], rbx
0x1800395aa  mov     rax, cs:__security_cookie
0x1800395b1  xor     rax, rsp
0x1800395b4  mov     [rbp+280h+var_30], rax
0x1800395bb  mov     r15b, r9b
0x1800395be  mov     rbx, rdx
0x1800395c1  mov     r14, rcx
0x1800395c4  mov     [rsp+380h+var_340], 0
0x1800395cc  lea     rdx, [rsp+380h+var_340]; int *
0x1800395d1  lea     rcx, [rsp+380h+hLibModule]; this
0x1800395d6  call    ??0RevertToPrinterRAII@@QEAA@PEAJ@Z; RevertToPrinterRAII::RevertToPrinterRAII(long *)
0x1800395db  nop
0x1800395dc  mov     rcx, [rbx+10h]
0x1800395e0  mov     rdi, 7FFFFFFFFFFFFFFEh
0x1800395ea  mov     rax, rdi
0x1800395ed  sub     rax, rcx
0x1800395f0  cmp     rax, 0Ah
0x1800395f4  jb      loc_18003994A
0x1800395fa  mov     r13d, 7
0x180039600  cmp     [rbx+18h], r13
0x180039604  jbe     short loc_180039609
0x180039606  mov     rbx, [rbx]
0x180039609  mov     qword ptr [rsp+30h], 0Ah
0x180039612  lea     rax, aResources; "\\Resources"
0x180039619  mov     [rsp+380h+var_358], rax
0x18003961e  mov     [rsp+380h+var_360], rcx
0x180039623  mov     r9, rbx
0x180039626  lea     rcx, [rsp+380h+var_318]
0x18003962b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180039630  nop
0x180039631  xor     edx, edx; Val
0x180039633  mov     r8d, 250h; Size
0x180039639  lea     rcx, [rbp+280h+FindFileData]; void *
0x18003963d  call    memset_0
0x180039642  mov     rcx, [rsp+380h+var_308]
0x180039647  mov     rax, rdi
0x18003964a  sub     rax, rcx
0x18003964d  cmp     rax, r13
0x180039650  jb      loc_18003993E
0x180039656  lea     r9, [rsp+380h+var_318]
0x18003965b  cmp     [rbp+280h+var_300], r13
0x18003965f  cmova   r9, [rsp+380h+var_318]
0x180039665  mov     [rsp+30h], r13
0x18003966a  lea     rax, aResx; "\\*.resx"
0x180039671  mov     [rsp+380h+var_358], rax
0x180039676  mov     [rsp+380h+var_360], rcx
0x18003967b  lea     rcx, [rbp+280h+lpExistingFileName]
0x18003967f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180039684  nop
0x180039685  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180039689  mov     [rbp+280h+hFindFile], rbx
0x18003968d  lea     rdx, [rbp+280h+lpExistingFileName]
0x180039691  lea     rcx, [rbp+280h+lpFileName]
0x180039695  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003969a  mov     [rbp+280h+var_2B0], 1
0x18003969e  lea     rcx, [rbp+280h+lpExistingFileName]
0x1800396a2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800396a7  lea     rdx, [rbp+280h+FindFileData]; lpFindFileData
0x1800396ab  cmp     [rbp+280h+var_2B0], 0
0x1800396af  jz      short loc_1800396DA
0x1800396b1  mov     [rbp+280h+var_2B0], 0
0x1800396b5  lea     rcx, [rbp+280h+lpFileName]
0x1800396b9  cmp     [rbp+280h+var_2B8], r13
0x1800396bd  cmova   rcx, [rbp+280h+lpFileName]; lpFileName
0x1800396c2  call    cs:__imp_FindFirstFileW
0x1800396c9  nop     dword ptr [rax+rax+00h]
0x1800396ce  mov     [rbp+280h+hFindFile], rax
0x1800396d2  cmp     rax, rbx
0x1800396d5  setnz   al
0x1800396d8  jmp     short loc_1800396EE
0x1800396da  mov     rcx, [rbp+280h+hFindFile]; hFindFile
0x1800396de  call    cs:__imp_FindNextFileW
0x1800396e5  nop     dword ptr [rax+rax+00h]
0x1800396ea  test    eax, eax
0x1800396ec  jnz     short loc_1800396F6
0x1800396ee  test    al, al
0x1800396f0  jz      loc_18003979C
0x1800396f6  mov     rcx, [rsp+380h+var_308]
0x1800396fb  mov     rax, rdi
0x1800396fe  sub     rax, rcx
0x180039701  cmp     rax, 1
0x180039705  jb      loc_180039944
0x18003970b  lea     r9, [rsp+380h+var_318]
0x180039710  cmp     [rbp+280h+var_300], r13
0x180039714  cmova   r9, [rsp+380h+var_318]
0x18003971a  mov     qword ptr [rsp+30h], 1
0x180039723  lea     rax, SubBlock; "\\"
0x18003972a  mov     [rsp+380h+var_358], rax
0x18003972f  mov     [rsp+380h+var_360], rcx
0x180039734  lea     rcx, [rbp+280h+Src]
0x180039738  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18003973d  nop
0x18003973e  lea     rdx, [rbp+280h+FindFileData.cFileName]; void *
0x180039742  lea     rcx, [rbp+280h+Src]; Src
0x180039746  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18003974b  xorps   xmm0, xmm0
0x18003974e  movups  xmmword ptr [rbp+280h+lpExistingFileName], xmm0
0x180039752  xorps   xmm1, xmm1
0x180039755  movdqu  [rbp+280h+var_2E8], xmm1
0x18003975a  movups  xmm0, xmmword ptr [rax]
0x18003975d  movups  xmmword ptr [rbp+280h+lpExistingFileName], xmm0
0x180039761  movups  xmm1, xmmword ptr [rax+10h]
0x180039765  movups  [rbp+280h+var_2E8], xmm1
0x180039769  mov     qword ptr [rax+10h], 0
0x180039771  mov     [rax+18h], r13
0x180039775  xor     ecx, ecx
0x180039777  mov     [rax], cx
0x18003977a  lea     rcx, [rbp+280h+Src]
0x18003977e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180039783  lea     rcx, [rbp+280h+lpExistingFileName]
0x180039787  cmp     qword ptr [rbp+280h+var_2E8+8], r13
0x18003978b  cmova   rcx, [rbp+280h+lpExistingFileName]; lpExistingFileName
0x180039790  mov     dl, 1; bool
0x180039792  call    ?DeleteFileNowOrOnReboot@@YAJPEBG_N@Z; DeleteFileNowOrOnReboot(ushort const *,bool)
0x180039797  jmp     loc_18003969E
0x18003979c  lea     rcx, [rsp+380h+var_318]
0x1800397a1  cmp     [rbp+280h+var_300], r13
0x1800397a5  cmova   rcx, [rsp+380h+var_318]; lpPathName
0x1800397ab  call    cs:__imp_RemoveDirectoryW
0x1800397b2  nop     dword ptr [rax+rax+00h]
0x1800397b7  nop
0x1800397b8  mov     rcx, [rbp+280h+hFindFile]; hFindFile
0x1800397bc  cmp     rcx, rbx
0x1800397bf  jz      short loc_1800397CD
0x1800397c1  call    cs:__imp_FindClose
0x1800397c8  nop     dword ptr [rax+rax+00h]
0x1800397cd  lea     rcx, [rbp+280h+lpFileName]
0x1800397d1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800397d6  nop
0x1800397d7  lea     rcx, [rsp+380h+var_318]
0x1800397dc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800397e1  nop
0x1800397e2  mov     rax, [rsp+380h+var_328]
0x1800397e7  test    rax, rax
0x1800397ea  jz      short loc_1800397FB
0x1800397ec  mov     rcx, [rsp+380h+var_330]
0x1800397f1  test    rcx, rcx
0x1800397f4  jz      short loc_1800397FB
0x1800397f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800397fb  mov     rcx, [rsp+380h+hLibModule]; hLibModule
0x180039800  test    rcx, rcx
0x180039803  jz      short loc_180039812
0x180039805  call    cs:__imp_FreeLibrary
0x18003980c  nop     dword ptr [rax+rax+00h]
0x180039811  nop
0x180039812  test    r15b, r15b
0x180039815  jnz     short loc_180039824
0x180039817  cmp     [rbp+280h+arg_20], r15b
0x18003981e  jz      loc_180039916
0x180039824  mov     r8d, ebx
0x180039827  mov     rdx, r14
0x18003982a  lea     rcx, [rsp+380h+hLibModule]
0x18003982f  call    ?GetPrinterLanguages@LanguageDatabase@PrintConfig@@YA?AV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEAXW4DriverResourcesState@@@Z; PrintConfig::LanguageDatabase::GetPrinterLanguages(void *,DriverResourcesState)
0x180039834  nop
0x180039835  mov     rbx, [rsp+380h+hLibModule]
0x18003983a  mov     rbx, [rbx]
0x18003983d  cmp     byte ptr [rbx+19h], 0
0x180039841  jnz     loc_18003990C
0x180039847  lea     rdi, [rbx+20h]
0x18003984b  test    r15b, r15b
0x18003984e  jz      short loc_180039860
0x180039850  xor     r8d, r8d
0x180039853  mov     rdx, rdi
0x180039856  mov     rcx, r14
0x180039859  call    ?SetLanguageState@LanguageDatabase@PrintConfig@@YAXPEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4DriverResourcesState@@@Z; PrintConfig::LanguageDatabase::SetLanguageState(void *,std::wstring const &,DriverResourcesState)
0x18003985e  jmp     short loc_1800398BD
0x180039860  cmp     [rbp+280h+arg_20], 0
0x180039867  jz      short loc_1800398BD
0x180039869  cmp     [rdi+18h], r13
0x18003986d  jbe     short loc_180039874
0x18003986f  mov     r8, [rdi]
0x180039872  jmp     short loc_180039877
0x180039874  mov     r8, rdi; pValueName
0x180039877  lea     rdx, aConfigdriverre; "ConfigDriverResources"
0x18003987e  mov     rcx, r14; hPrinter
0x180039881  call    cs:__imp_DeletePrinterDataExW
0x180039888  nop     dword ptr [rax+rax+00h]
0x18003988d  test    eax, eax
0x18003988f  jz      short loc_1800398BD
0x180039891  jle     short loc_18003989B
0x180039893  movzx   eax, ax
0x180039896  or      eax, 80070000h
0x18003989b  cmp     [rdi+18h], r13
0x18003989f  jbe     short loc_1800398A4
0x1800398a1  mov     rdi, [rdi]
0x1800398a4  mov     r9d, eax
0x1800398a7  mov     r8, rdi
0x1800398aa  lea     rdx, aFailedToDelete_0; "Failed to delete language \"%ws\" from "...
0x1800398b1  lea     rcx, aPrintconfigLan_0; "PrintConfig::LanguageDatabase::DeleteLa"...
0x1800398b8  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x1800398bd  mov     rcx, [rbx+10h]
0x1800398c1  cmp     byte ptr [rcx+19h], 0
0x1800398c5  jz      short loc_1800398E8
0x1800398c7  mov     rax, [rbx+8]
0x1800398cb  jmp     short loc_1800398DA
0x1800398cd  cmp     rbx, [rax+10h]
0x1800398d1  jnz     short loc_1800398E0
0x1800398d3  mov     rbx, rax
0x1800398d6  mov     rax, [rax+8]
0x1800398da  cmp     byte ptr [rax+19h], 0
0x1800398de  jz      short loc_1800398CD
0x1800398e0  mov     rbx, rax
0x1800398e3  jmp     loc_18003983D
0x1800398e8  mov     rbx, rcx
0x1800398eb  mov     rcx, [rcx]
0x1800398ee  cmp     byte ptr [rcx+19h], 0
0x1800398f2  jnz     loc_18003983D
0x1800398f8  mov     rbx, rcx
0x1800398fb  mov     rax, [rcx]
0x1800398fe  mov     rcx, rax
0x180039901  cmp     byte ptr [rax+19h], 0
0x180039905  jz      short loc_1800398F8
0x180039907  jmp     loc_18003983D
0x18003990c  lea     rcx, [rsp+380h+hLibModule]
0x180039911  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(void)
0x180039916  mov     rcx, [rbp+280h+var_30]
0x18003991d  xor     rcx, rsp; StackCookie
0x180039920  call    __security_check_cookie
0x180039925  mov     rbx, [rsp+380h+arg_10]
0x18003992d  add     rsp, 360h
0x180039934  pop     r15
0x180039936  pop     r14
0x180039938  pop     r13
0x18003993a  pop     rdi
0x18003993b  pop     rbp
0x18003993c  retn
0x18003993e  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x180039944  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x18003994a  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
