# PrintConfig::LanguageDatabase::ClearResources(void *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,bool,bool,bool)

- ea: `0x180038054`
- end: `0x1800383fb`
- name: `?ClearResources@LanguageDatabase@PrintConfig@@YAXPEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N22@Z`
- size: `935`
- prototype: `__int64 __usercall@<rax>(HANDLE hPrinter@<rcx>, char)`
- caller_count: `6`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x18001290c`
- `0x180038fb4`
- `0x180042dac`
- `0x180045f4c`
- `0x180049274`
- `0x18004bce4`

## callees

- `0x1800032e0`
- `0x180004418`
- `0x1800060ec`
- `0x18000e23c`
- `0x18000e348`
- `0x18000f590`
- `0x1800183f8`
- `0x180018818`
- `0x180018a28`
- `0x1800376f4`
- `0x180037c28`
- `0x180038054`
- `0x1800384d0`
- `0x1800387e4`
- `0x1801c3010`

## import_xrefs

- `KERNEL32!RemoveDirectoryW` at `0x18003826f`
- `KERNEL32!RemoveDirectoryW` at `0x18003826f`
- `KERNEL32!FreeLibrary` at `0x1800382bd`
- `KERNEL32!FreeLibrary` at `0x1800382bd`
- `KERNEL32!FindFirstFileW` at `0x180038192`
- `KERNEL32!FindFirstFileW` at `0x180038192`
- `KERNEL32!FindNextFileW` at `0x1800381a8`
- `KERNEL32!FindNextFileW` at `0x1800381a8`
- `KERNEL32!FindClose` at `0x18003827f`
- `KERNEL32!FindClose` at `0x18003827f`
- `WINSPOOL!DeletePrinterDataExW` at `0x180038333`
- `WINSPOOL!DeletePrinterDataExW` at `0x180038333`

## string_xrefs

- `0x180038329`: `ConfigDriverResources`
- `0x180038356`: `Failed to delete language "%ws" from language database (hr: 0x%x)`
- `0x18003835d`: `PrintConfig::LanguageDatabase::DeleteLanguage`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
int __fastcall PrintConfig::LanguageDatabase::ClearResources(HANDLE hPrinter, _QWORD *a2, __int64 a3, char a4, char a5)
{
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r8
  _QWORD *v13; // r9
  const WCHAR *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r8
  BOOL NextFileW; // eax
  _QWORD *v18; // r9
  __int64 v19; // rax
  const WCHAR *v20; // rcx
  const WCHAR *v21; // rcx
  int result; // eax
  __int64 *v23; // rbx
  _QWORD *v24; // rdi
  const WCHAR *v25; // r8
  signed int v26; // eax
  __int64 **v27; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  int v30[2]; // [rsp+48h] [rbp-C0h] BYREF
  HMODULE hLibModule[2]; // [rsp+50h] [rbp-B8h] BYREF
  __int64 (*v32)(void); // [rsp+60h] [rbp-A8h]
  __int64 v33; // [rsp+68h] [rbp-A0h]
  _QWORD *v34; // [rsp+70h] [rbp-98h] BYREF
  __int64 v35; // [rsp+80h] [rbp-88h]
  unsigned __int64 v36; // [rsp+88h] [rbp-80h]
  LPCWSTR lpExistingFileName[2]; // [rsp+90h] [rbp-78h] BYREF
  __int128 v38; // [rsp+A0h] [rbp-68h]
  HANDLE hFindFile; // [rsp+B0h] [rbp-58h]
  LPCWSTR lpFileName[4]; // [rsp+B8h] [rbp-50h] BYREF
  char v41; // [rsp+D8h] [rbp-30h]
  _BYTE Src[40]; // [rsp+E0h] [rbp-28h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+108h] [rbp+0h] BYREF

  v33 = -2;
  v30[0] = 0;
  RevertToPrinterRAII::RevertToPrinterRAII((RevertToPrinterRAII *)hLibModule, v30);
  v10 = a2[2];
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v10) < 0xA )
    std::_Xlen_string();
  if ( a2[3] > 7u )
    a2 = (_QWORD *)*a2;
  std::wstring::wstring(&v34, v8, v9, a2, v10, L"\\Resources", 10);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v35) < 7 )
    std::_Xlen_string();
  v13 = &v34;
  if ( v36 > 7 )
    v13 = v34;
  std::wstring::wstring(lpExistingFileName, v11, v12, v13, v35, L"\\*.resx", 7);
  hFindFile = (HANDLE)-1LL;
  std::wstring::wstring((__int64)lpFileName, (__int64)lpExistingFileName);
  v41 = 1;
  while ( 1 )
  {
    std::wstring::~wstring(lpExistingFileName);
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
    v18 = &v34;
    if ( v36 > 7 )
      v18 = v34;
    std::wstring::wstring(Src, v15, v16, v18, v35, L"\\", 1);
    v19 = std::wstring::append(Src, FindFileData.cFileName);
    *(_OWORD *)lpExistingFileName = 0;
    v38 = 0;
    *(_OWORD *)lpExistingFileName = *(_OWORD *)v19;
    v38 = *(_OWORD *)(v19 + 16);
    *(_QWORD *)(v19 + 16) = 0;
    *(_QWORD *)(v19 + 24) = 7;
    *(_WORD *)v19 = 0;
    std::wstring::~wstring(Src);
    v20 = (const WCHAR *)lpExistingFileName;
    if ( *((_QWORD *)&v38 + 1) > 7u )
      v20 = lpExistingFileName[0];
    DeleteFileNowOrOnReboot(v20, 1);
  }
  v21 = (const WCHAR *)&v34;
  if ( v36 > 7 )
    v21 = (const WCHAR *)v34;
  RemoveDirectoryW(v21);
  if ( hFindFile != (HANDLE)-1LL )
    FindClose(hFindFile);
  std::wstring::~wstring(lpFileName);
  std::wstring::~wstring(&v34);
  result = (int)v32;
  if ( v32 && hLibModule[1] )
    result = v32();
  if ( hLibModule[0] )
    result = FreeLibrary(hLibModule[0]);
  if ( a4 || a5 )
  {
    PrintConfig::LanguageDatabase::GetPrinterLanguages(hLibModule, hPrinter, 0xFFFFFFFFLL);
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
    return std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(hLibModule);
  }
  return result;
}

```

## disassembly

```asm
0x180038054  mov     rax, rsp
0x180038057  push    rbp
0x180038058  push    rdi
0x180038059  push    r13
0x18003805b  push    r14
0x18003805d  push    r15
0x18003805f  lea     rbp, [rax-288h]
0x180038066  sub     rsp, 360h
0x18003806d  mov     [rsp+380h+var_320], 0FFFFFFFFFFFFFFFEh
0x180038076  mov     [rax+18h], rbx
0x18003807a  mov     rax, cs:__security_cookie
0x180038081  xor     rax, rsp
0x180038084  mov     [rbp+280h+var_30], rax
0x18003808b  mov     r15b, r9b
0x18003808e  mov     rbx, rdx
0x180038091  mov     r14, rcx
0x180038094  mov     [rsp+380h+var_340], 0
0x18003809c  lea     rdx, [rsp+380h+var_340]; int *
0x1800380a1  lea     rcx, [rsp+380h+hLibModule]; this
0x1800380a6  call    ??0RevertToPrinterRAII@@QEAA@PEAJ@Z; RevertToPrinterRAII::RevertToPrinterRAII(long *)
0x1800380ab  nop
0x1800380ac  mov     rcx, [rbx+10h]
0x1800380b0  mov     rdi, 7FFFFFFFFFFFFFFEh
0x1800380ba  mov     rax, rdi
0x1800380bd  sub     rax, rcx
0x1800380c0  cmp     rax, 0Ah
0x1800380c4  jb      loc_1800383F5
0x1800380ca  mov     r13d, 7
0x1800380d0  cmp     [rbx+18h], r13
0x1800380d4  jbe     short loc_1800380D9
0x1800380d6  mov     rbx, [rbx]
0x1800380d9  mov     qword ptr [rsp+30h], 0Ah
0x1800380e2  lea     rax, aResources; "\\Resources"
0x1800380e9  mov     [rsp+380h+var_358], rax
0x1800380ee  mov     [rsp+380h+var_360], rcx
0x1800380f3  mov     r9, rbx
0x1800380f6  lea     rcx, [rsp+380h+var_318]
0x1800380fb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180038100  nop
0x180038101  xor     edx, edx; Val
0x180038103  mov     r8d, 250h; Size
0x180038109  lea     rcx, [rbp+280h+FindFileData]; void *
0x18003810d  call    memset_0
0x180038112  mov     rcx, [rsp+380h+var_308]
0x180038117  mov     rax, rdi
0x18003811a  sub     rax, rcx
0x18003811d  cmp     rax, r13
0x180038120  jb      loc_1800383E9
0x180038126  lea     r9, [rsp+380h+var_318]
0x18003812b  cmp     [rbp+280h+var_300], r13
0x18003812f  cmova   r9, [rsp+380h+var_318]
0x180038135  mov     [rsp+30h], r13
0x18003813a  lea     rax, aResx; "\\*.resx"
0x180038141  mov     [rsp+380h+var_358], rax
0x180038146  mov     [rsp+380h+var_360], rcx
0x18003814b  lea     rcx, [rbp+280h+lpExistingFileName]
0x18003814f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180038154  nop
0x180038155  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180038159  mov     [rbp+280h+hFindFile], rbx
0x18003815d  lea     rdx, [rbp+280h+lpExistingFileName]
0x180038161  lea     rcx, [rbp+280h+lpFileName]
0x180038165  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003816a  mov     [rbp+280h+var_2B0], 1
0x18003816e  lea     rcx, [rbp+280h+lpExistingFileName]
0x180038172  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180038177  lea     rdx, [rbp+280h+FindFileData]; lpFindFileData
0x18003817b  cmp     [rbp+280h+var_2B0], 0
0x18003817f  jz      short loc_1800381A4
0x180038181  mov     [rbp+280h+var_2B0], 0
0x180038185  lea     rcx, [rbp+280h+lpFileName]
0x180038189  cmp     [rbp+280h+var_2B8], r13
0x18003818d  cmova   rcx, [rbp+280h+lpFileName]; lpFileName
0x180038192  call    cs:__imp_FindFirstFileW
0x180038198  mov     [rbp+280h+hFindFile], rax
0x18003819c  cmp     rax, rbx
0x18003819f  setnz   al
0x1800381a2  jmp     short loc_1800381B2
0x1800381a4  mov     rcx, [rbp+280h+hFindFile]; hFindFile
0x1800381a8  call    cs:__imp_FindNextFileW
0x1800381ae  test    eax, eax
0x1800381b0  jnz     short loc_1800381BA
0x1800381b2  test    al, al
0x1800381b4  jz      loc_180038260
0x1800381ba  mov     rcx, [rsp+380h+var_308]
0x1800381bf  mov     rax, rdi
0x1800381c2  sub     rax, rcx
0x1800381c5  cmp     rax, 1
0x1800381c9  jb      loc_1800383EF
0x1800381cf  lea     r9, [rsp+380h+var_318]
0x1800381d4  cmp     [rbp+280h+var_300], r13
0x1800381d8  cmova   r9, [rsp+380h+var_318]
0x1800381de  mov     qword ptr [rsp+30h], 1
0x1800381e7  lea     rax, SubBlock; "\\"
0x1800381ee  mov     [rsp+380h+var_358], rax
0x1800381f3  mov     [rsp+380h+var_360], rcx
0x1800381f8  lea     rcx, [rbp+280h+Src]
0x1800381fc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180038201  nop
0x180038202  lea     rdx, [rbp+280h+FindFileData.cFileName]; void *
0x180038206  lea     rcx, [rbp+280h+Src]; Src
0x18003820a  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18003820f  xorps   xmm0, xmm0
0x180038212  movups  xmmword ptr [rbp+280h+lpExistingFileName], xmm0
0x180038216  xorps   xmm1, xmm1
0x180038219  movdqu  [rbp+280h+var_2E8], xmm1
0x18003821e  movups  xmm0, xmmword ptr [rax]
0x180038221  movups  xmmword ptr [rbp+280h+lpExistingFileName], xmm0
0x180038225  movups  xmm1, xmmword ptr [rax+10h]
0x180038229  movups  [rbp+280h+var_2E8], xmm1
0x18003822d  mov     qword ptr [rax+10h], 0
0x180038235  mov     [rax+18h], r13
0x180038239  xor     ecx, ecx
0x18003823b  mov     [rax], cx
0x18003823e  lea     rcx, [rbp+280h+Src]
0x180038242  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180038247  lea     rcx, [rbp+280h+lpExistingFileName]
0x18003824b  cmp     qword ptr [rbp+280h+var_2E8+8], r13
0x18003824f  cmova   rcx, [rbp+280h+lpExistingFileName]; lpExistingFileName
0x180038254  mov     dl, 1; bool
0x180038256  call    ?DeleteFileNowOrOnReboot@@YAJPEBG_N@Z; DeleteFileNowOrOnReboot(ushort const *,bool)
0x18003825b  jmp     loc_18003816E
0x180038260  lea     rcx, [rsp+380h+var_318]
0x180038265  cmp     [rbp+280h+var_300], r13
0x180038269  cmova   rcx, [rsp+380h+var_318]; lpPathName
0x18003826f  call    cs:__imp_RemoveDirectoryW
0x180038275  nop
0x180038276  mov     rcx, [rbp+280h+hFindFile]; hFindFile
0x18003827a  cmp     rcx, rbx
0x18003827d  jz      short loc_180038285
0x18003827f  call    cs:__imp_FindClose
0x180038285  lea     rcx, [rbp+280h+lpFileName]
0x180038289  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003828e  nop
0x18003828f  lea     rcx, [rsp+380h+var_318]
0x180038294  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180038299  nop
0x18003829a  mov     rax, [rsp+380h+var_328]
0x18003829f  test    rax, rax
0x1800382a2  jz      short loc_1800382B3
0x1800382a4  mov     rcx, [rsp+380h+var_330]
0x1800382a9  test    rcx, rcx
0x1800382ac  jz      short loc_1800382B3
0x1800382ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800382b3  mov     rcx, [rsp+380h+hLibModule]; hLibModule
0x1800382b8  test    rcx, rcx
0x1800382bb  jz      short loc_1800382C4
0x1800382bd  call    cs:__imp_FreeLibrary
0x1800382c3  nop
0x1800382c4  test    r15b, r15b
0x1800382c7  jnz     short loc_1800382D6
0x1800382c9  cmp     [rbp+280h+arg_20], r15b
0x1800382d0  jz      loc_1800383C2
0x1800382d6  mov     r8d, ebx
0x1800382d9  mov     rdx, r14
0x1800382dc  lea     rcx, [rsp+380h+hLibModule]
0x1800382e1  call    ?GetPrinterLanguages@LanguageDatabase@PrintConfig@@YA?AV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEAXW4DriverResourcesState@@@Z; PrintConfig::LanguageDatabase::GetPrinterLanguages(void *,DriverResourcesState)
0x1800382e6  nop
0x1800382e7  mov     rbx, [rsp+380h+hLibModule]
0x1800382ec  mov     rbx, [rbx]
0x1800382ef  cmp     byte ptr [rbx+19h], 0
0x1800382f3  jnz     loc_1800383B8
0x1800382f9  lea     rdi, [rbx+20h]
0x1800382fd  test    r15b, r15b
0x180038300  jz      short loc_180038312
0x180038302  xor     r8d, r8d
0x180038305  mov     rdx, rdi
0x180038308  mov     rcx, r14
0x18003830b  call    ?SetLanguageState@LanguageDatabase@PrintConfig@@YAXPEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4DriverResourcesState@@@Z; PrintConfig::LanguageDatabase::SetLanguageState(void *,std::wstring const &,DriverResourcesState)
0x180038310  jmp     short loc_180038369
0x180038312  cmp     [rbp+280h+arg_20], 0
0x180038319  jz      short loc_180038369
0x18003831b  cmp     [rdi+18h], r13
0x18003831f  jbe     short loc_180038326
0x180038321  mov     r8, [rdi]
0x180038324  jmp     short loc_180038329
0x180038326  mov     r8, rdi; pValueName
0x180038329  lea     rdx, aConfigdriverre; "ConfigDriverResources"
0x180038330  mov     rcx, r14; hPrinter
0x180038333  call    cs:__imp_DeletePrinterDataExW
0x180038339  test    eax, eax
0x18003833b  jz      short loc_180038369
0x18003833d  jle     short loc_180038347
0x18003833f  movzx   eax, ax
0x180038342  or      eax, 80070000h
0x180038347  cmp     [rdi+18h], r13
0x18003834b  jbe     short loc_180038350
0x18003834d  mov     rdi, [rdi]
0x180038350  mov     r9d, eax
0x180038353  mov     r8, rdi
0x180038356  lea     rdx, aFailedToDelete_0; "Failed to delete language \"%ws\" from "...
0x18003835d  lea     rcx, aPrintconfigLan_0; "PrintConfig::LanguageDatabase::DeleteLa"...
0x180038364  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180038369  mov     rcx, [rbx+10h]
0x18003836d  cmp     byte ptr [rcx+19h], 0
0x180038371  jz      short loc_180038394
0x180038373  mov     rax, [rbx+8]
0x180038377  jmp     short loc_180038386
0x180038379  cmp     rbx, [rax+10h]
0x18003837d  jnz     short loc_18003838C
0x18003837f  mov     rbx, rax
0x180038382  mov     rax, [rax+8]
0x180038386  cmp     byte ptr [rax+19h], 0
0x18003838a  jz      short loc_180038379
0x18003838c  mov     rbx, rax
0x18003838f  jmp     loc_1800382EF
0x180038394  mov     rbx, rcx
0x180038397  mov     rcx, [rcx]
0x18003839a  cmp     byte ptr [rcx+19h], 0
0x18003839e  jnz     loc_1800382EF
0x1800383a4  mov     rbx, rcx
0x1800383a7  mov     rax, [rcx]
0x1800383aa  mov     rcx, rax
0x1800383ad  cmp     byte ptr [rax+19h], 0
0x1800383b1  jz      short loc_1800383A4
0x1800383b3  jmp     loc_1800382EF
0x1800383b8  lea     rcx, [rsp+380h+hLibModule]
0x1800383bd  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(void)
0x1800383c2  mov     rcx, [rbp+280h+var_30]
0x1800383c9  xor     rcx, rsp; StackCookie
0x1800383cc  call    __security_check_cookie
0x1800383d1  mov     rbx, [rsp+380h+arg_10]
0x1800383d9  add     rsp, 360h
0x1800383e0  pop     r15
0x1800383e2  pop     r14
0x1800383e4  pop     r13
0x1800383e6  pop     rdi
0x1800383e7  pop     rbp
0x1800383e8  retn
0x1800383e9  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x1800383ef  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x1800383f5  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
