# AppxAllUserStore::Internal::RemoveAllAppsFromSystemSis(AppxAllUserStore::BasicLogFile &,ushort const *)

- ea: `0x180034214`
- end: `0x1800348af`
- name: `?RemoveAllAppsFromSystemSis@Internal@AppxAllUserStore@@YAJAEAVBasicLogFile@2@PEBG@Z`
- size: `1691`
- prototype: `__int64 __fastcall(AppxAllUserStore::Internal *__hidden this, struct AppxAllUserStore::BasicLogFile *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180016878`

## callees

- `0x1800039e4`
- `0x180004920`
- `0x180008db0`
- `0x180017cd0`
- `0x180017f50`
- `0x180018248`
- `0x18001a6a0`
- `0x18001f21c`
- `0x180022188`
- `0x1800262ec`
- `0x180030d5c`
- `0x180031fe0`
- `0x180034214`
- `0x18004682c`
- `0x18004756c`
- `0x18004c98a`
- `0x18004c9d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800343b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003457e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003479e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800343b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003457e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003479e`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180034391`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180034391`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180034570`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180034570`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x180034794`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x180034794`

## string_xrefs

- `0x18003424a`: `In RemoveAllAppsFromSystemSis %ls.`
- `0x1800342b6`: `GetSystemSisPath got %ls, 0x%0x.`
- `0x1800344b2`: `Found package %ls to remove.`
- `0x180034663`: `Deleted`
- `0x180034707`: `RemoveDirectoryTree %ls returned 0x%x.`
- `0x1800347a9`: `MoveFile %ls to %ls errored with 0x%x`

## pseudocode

```c
__int64 __fastcall AppxAllUserStore::Internal::RemoveAllAppsFromSystemSis(
        AppxAllUserStore::Internal *this,
        struct AppxAllUserStore::BasicLogFile *a2,
        const unsigned __int16 *a3)
{
  int v5; // eax
  struct Common::StringBuffer *v6; // r8
  int SystemSisPath; // eax
  unsigned int v8; // ebx
  int v9; // eax
  int v10; // eax
  HANDLE FirstFileW; // rax
  struct Common::StringBuffer *v12; // r8
  Common *v13; // rbx
  signed int LastError; // eax
  void *v15; // rdx
  int v16; // eax
  void *v17; // rdx
  int v18; // eax
  signed int v19; // edi
  const char *v20; // rsi
  int v21; // eax
  signed int v22; // eax
  void *v23; // rdx
  int v24; // eax
  unsigned __int64 v25; // rsi
  unsigned __int64 v26; // rbx
  __int64 v27; // r12
  const unsigned __int16 *v28; // rdx
  int v29; // eax
  int v30; // edx
  int v31; // r8d
  unsigned int v32; // r14d
  __int64 v33; // r14
  int v34; // eax
  const unsigned __int16 *v35; // rdx
  int v36; // eax
  int v37; // eax
  void *v39; // rdx
  DWORD v40; // [rsp+20h] [rbp-E0h]
  LPCWSTR lpExistingFileName[2]; // [rsp+30h] [rbp-D0h] BYREF
  int v42; // [rsp+40h] [rbp-C0h]
  LPCWSTR lpFileName[2]; // [rsp+48h] [rbp-B8h] BYREF
  int v44; // [rsp+58h] [rbp-A8h]
  HANDLE hFindFile; // [rsp+60h] [rbp-A0h] BYREF
  LPCWSTR lpNewFileName[2]; // [rsp+68h] [rbp-98h] BYREF
  int v47; // [rsp+78h] [rbp-88h]
  _QWORD v48[2]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int64 v49; // [rsp+90h] [rbp-70h]
  char v50; // [rsp+98h] [rbp-68h]
  unsigned __int16 *Src[2]; // [rsp+A0h] [rbp-60h] BYREF
  int v52; // [rsp+B0h] [rbp-50h]
  unsigned __int16 *v53[2]; // [rsp+B8h] [rbp-48h] BYREF
  int v54; // [rsp+C8h] [rbp-38h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+D0h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+368h] [rbp+268h]

  v5 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"In RemoveAllAppsFromSystemSis %ls.", a2);
  if ( v5 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x918,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
      (const char *)(unsigned int)v5,
      v40);
  v52 = 0;
  *(_OWORD *)Src = 0;
  SystemSisPath = AppxAllUserStore::GetSystemSisPath(a2, (Common::Deployment::Configuration *)Src, v6);
  v8 = SystemSisPath;
  if ( SystemSisPath < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x91B,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
      (const char *)(unsigned int)SystemSisPath,
      v40);
  v9 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"GetSystemSisPath got %ls, 0x%0x.", Src[1], v8);
  if ( v9 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x91C,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
      (const char *)(unsigned int)v9,
      v40);
  if ( (v8 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x91D,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
      (const char *)v8,
      (int)"system root %ls.",
      (const char *)a2);
    goto LABEL_69;
  }
  v44 = 0;
  *(_OWORD *)lpFileName = 0;
  v10 = Common::PathHelpers::CombinePaths(Src[1], L"*", (struct Common::StringBuffer *)lpFileName);
  v8 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x920,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
      (const char *)(unsigned int)v10,
      v40);
LABEL_11:
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpFileName);
    goto LABEL_69;
  }
  v48[0] = 0;
  v48[1] = 0;
  v49 = 0;
  v50 = 1;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  hFindFile = 0;
  FirstFileW = FindFirstFileW(lpFileName[1], &FindFileData);
  Common::AutoHandleFindFile::operator=(&hFindFile, FirstFileW);
  v13 = (Common *)hFindFile;
  if ( hFindFile == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError != 18 )
    {
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      if ( (v8 & 0x80000000) != 0 )
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x92B,
          (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
          (const char *)v8,
          (int)"Searching %ls.",
          (const char *)lpFileName[1]);
      goto LABEL_18;
    }
    v16 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"Nothing under the system Sis root folder.");
    if ( v16 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x92C,
        (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
        (const char *)(unsigned int)v16,
        v40);
LABEL_68:
    Common::AutoHandleFreeFindFile((Common *)0xFFFFFFFFFFFFFFFFLL, v17);
    Common::Array<AppxAllUserStore::_SharedPackageContainerInfo,Common::ContainerOperations<AppxAllUserStore::_SharedPackageContainerInfo,AppxAllUserStore::_SharedPackageContainerInfo>,Common::NoKey,Common::ContainerOperations<Common::NoKey,AppxAllUserStore::_SharedPackageContainerInfo>,Common::ArrayOperations<AppxAllUserStore::_SharedPackageContainerInfo,Common::NoKey>>::~Array<AppxAllUserStore::_SharedPackageContainerInfo,Common::ContainerOperations<AppxAllUserStore::_SharedPackageContainerInfo,AppxAllUserStore::_SharedPackageContainerInfo>,Common::NoKey,Common::ContainerOperations<Common::NoKey,AppxAllUserStore::_SharedPackageContainerInfo>,Common::ArrayOperations<AppxAllUserStore::_SharedPackageContainerInfo,Common::NoKey>>(v48);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpFileName);
    v8 = 0;
    goto LABEL_69;
  }
  do
  {
    if ( (FindFileData.cFileName[0] != 46
       || FindFileData.cFileName[1] && (FindFileData.cFileName[1] != 46 || FindFileData.cFileName[2]))
      && (FindFileData.dwFileAttributes & 0x10) != 0 )
    {
      v47 = 0;
      *(_OWORD *)lpNewFileName = 0;
      if ( (int)Common::Deployment::GetPackageFamilyNameFromFullName(
                  FindFileData.cFileName,
                  (Common::StringBuffer *)lpNewFileName,
                  v12) < 0 )
      {
        v21 = AppxAllUserStore::BasicLogFile::WriteMsg(
                this,
                L"Ignoring package %ls because could not convert to family name",
                FindFileData.cFileName);
        if ( v21 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x946,
            (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
            (const char *)(unsigned int)v21,
            v40);
      }
      else
      {
        v18 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"Found package %ls to remove.", FindFileData.cFileName);
        if ( v18 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x93A,
            (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
            (const char *)(unsigned int)v18,
            v40);
        v42 = 0;
        *(_OWORD *)lpExistingFileName = 0;
        v19 = Common::StringBuffer::SetValueFromString(
                (Common::StringBuffer *)lpExistingFileName,
                FindFileData.cFileName);
        if ( v19 < 0 )
        {
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0x93E,
            (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
            (const char *)(unsigned int)v19,
            (int)"Folder %ls.",
            (const char *)FindFileData.cFileName);
LABEL_42:
          Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpExistingFileName);
          Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpNewFileName);
LABEL_43:
          Common::AutoHandleFreeFindFile(v13, v23);
          Common::Array<AppxAllUserStore::_SharedPackageContainerInfo,Common::ContainerOperations<AppxAllUserStore::_SharedPackageContainerInfo,AppxAllUserStore::_SharedPackageContainerInfo>,Common::NoKey,Common::ContainerOperations<Common::NoKey,AppxAllUserStore::_SharedPackageContainerInfo>,Common::ArrayOperations<AppxAllUserStore::_SharedPackageContainerInfo,Common::NoKey>>::~Array<AppxAllUserStore::_SharedPackageContainerInfo,Common::ContainerOperations<AppxAllUserStore::_SharedPackageContainerInfo,AppxAllUserStore::_SharedPackageContainerInfo>,Common::NoKey,Common::ContainerOperations<Common::NoKey,AppxAllUserStore::_SharedPackageContainerInfo>,Common::ArrayOperations<AppxAllUserStore::_SharedPackageContainerInfo,Common::NoKey>>(v48);
          Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpFileName);
          v8 = v19;
          goto LABEL_69;
        }
        v20 = (const char *)lpExistingFileName[1];
        v19 = Common::Array<unsigned short,Common::ContainerOperations<unsigned short,unsigned short>,Common::NoKey,Common::ContainerOperations<Common::NoKey,unsigned short>,Common::ArrayOperations<unsigned short,Common::NoKey>>::Add(
                v48,
                lpExistingFileName[1]);
        if ( v19 < 0 )
        {
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0x941,
            (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
            (const char *)(unsigned int)v19,
            (int)"Folder %ls.",
            v20);
          goto LABEL_42;
        }
        lpExistingFileName[1] = 0;
        LODWORD(lpExistingFileName[0]) = 0;
        v42 = 0;
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpExistingFileName);
      }
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpNewFileName);
    }
    if ( !FindNextFileW(v13, &FindFileData) )
    {
      v22 = GetLastError();
      v19 = v22;
      if ( v22 != 18 )
      {
        if ( v22 > 0 )
          v19 = (unsigned __int16)v22 | 0x80070000;
        if ( v19 < 0 )
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0x94F,
            (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
            (const char *)(unsigned int)v19,
            (int)"Searching %ls.",
            (const char *)lpFileName[1]);
        goto LABEL_43;
      }
      Common::AutoHandleFindFile::operator=(&hFindFile, -1);
      v13 = (Common *)hFindFile;
    }
  }
  while ( v13 != (Common *)-1LL );
  v54 = 0;
  *(_OWORD *)v53 = 0;
  v24 = Common::PathHelpers::CombinePaths(Src[1], L"Deleted", (struct Common::StringBuffer *)v53);
  v8 = v24;
  if ( v24 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x955,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
      (const char *)(unsigned int)v24,
      v40);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v53);
LABEL_18:
    Common::AutoHandleFreeFindFile((Common *)0xFFFFFFFFFFFFFFFFLL, v15);
    Common::Array<AppxAllUserStore::_SharedPackageContainerInfo,Common::ContainerOperations<AppxAllUserStore::_SharedPackageContainerInfo,AppxAllUserStore::_SharedPackageContainerInfo>,Common::NoKey,Common::ContainerOperations<Common::NoKey,AppxAllUserStore::_SharedPackageContainerInfo>,Common::ArrayOperations<AppxAllUserStore::_SharedPackageContainerInfo,Common::NoKey>>::~Array<AppxAllUserStore::_SharedPackageContainerInfo,Common::ContainerOperations<AppxAllUserStore::_SharedPackageContainerInfo,AppxAllUserStore::_SharedPackageContainerInfo>,Common::NoKey,Common::ContainerOperations<Common::NoKey,AppxAllUserStore::_SharedPackageContainerInfo>,Common::ArrayOperations<AppxAllUserStore::_SharedPackageContainerInfo,Common::NoKey>>(v48);
    goto LABEL_11;
  }
  v25 = v49;
  v26 = 0;
  if ( !v49 )
  {
LABEL_67:
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v53);
    goto LABEL_68;
  }
  v27 = v48[0];
  while ( 1 )
  {
    v42 = 0;
    v28 = 0;
    *(_OWORD *)lpExistingFileName = 0;
    if ( v26 < v25 )
      v28 = *(const unsigned __int16 **)(8 * v26 + v27);
    v29 = Common::PathHelpers::CombinePaths(Src[1], v28, (struct Common::StringBuffer *)lpExistingFileName);
    v32 = v29;
    if ( v29 < 0 )
      break;
    v33 = (unsigned int)RemoveDirectoryTree(
                          lpExistingFileName[1],
                          v30,
                          v31,
                          (unsigned int)&AppxAllUserStore::Internal::LogRemoveDirectoryTreeError,
                          (__int64)this);
    v34 = AppxAllUserStore::BasicLogFile::WriteMsg(
            this,
            L"RemoveDirectoryTree %ls returned 0x%x.",
            lpExistingFileName[1],
            v33);
    if ( v34 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x95E,
        (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
        (const char *)(unsigned int)v34,
        v40);
    if ( (_DWORD)v33 )
    {
      v47 = 0;
      v35 = 0;
      *(_OWORD *)lpNewFileName = 0;
      if ( v26 < v25 )
        v35 = *(const unsigned __int16 **)(v27 + 8 * v26);
      v36 = Common::PathHelpers::CombinePaths(v53[1], v35, (struct Common::StringBuffer *)lpNewFileName);
      if ( v36 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x963,
          (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
          (const char *)(unsigned int)v36,
          v40);
      if ( !MoveFileW(lpExistingFileName[1], lpNewFileName[1]) )
      {
        v40 = GetLastError();
        v37 = AppxAllUserStore::BasicLogFile::WriteMsg(
                this,
                L"MoveFile %ls to %ls errored with 0x%x",
                lpExistingFileName[1],
                lpNewFileName[1]);
        if ( v37 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x969,
            (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
            (const char *)(unsigned int)v37,
            v40);
      }
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpNewFileName);
    }
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpExistingFileName);
    if ( ++v26 >= v25 )
      goto LABEL_67;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x95A,
    (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
    (const char *)(unsigned int)v29,
    v40);
  Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpExistingFileName);
  Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v53);
  Common::AutoHandleFreeFindFile((Common *)0xFFFFFFFFFFFFFFFFLL, v39);
  Common::Array<AppxAllUserStore::_SharedPackageContainerInfo,Common::ContainerOperations<AppxAllUserStore::_SharedPackageContainerInfo,AppxAllUserStore::_SharedPackageContainerInfo>,Common::NoKey,Common::ContainerOperations<Common::NoKey,AppxAllUserStore::_SharedPackageContainerInfo>,Common::ArrayOperations<AppxAllUserStore::_SharedPackageContainerInfo,Common::NoKey>>::~Array<AppxAllUserStore::_SharedPackageContainerInfo,Common::ContainerOperations<AppxAllUserStore::_SharedPackageContainerInfo,AppxAllUserStore::_SharedPackageContainerInfo>,Common::NoKey,Common::ContainerOperations<Common::NoKey,AppxAllUserStore::_SharedPackageContainerInfo>,Common::ArrayOperations<AppxAllUserStore::_SharedPackageContainerInfo,Common::NoKey>>(v48);
  Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpFileName);
  v8 = v32;
LABEL_69:
  Common::StringBuffer::~StringBuffer((Common::StringBuffer *)Src);
  return v8;
}

```

## disassembly

```asm
0x180034214  mov     [rsp-8+arg_10], rbx
0x180034219  push    rbp
0x18003421a  push    rsi
0x18003421b  push    rdi
0x18003421c  push    r12
0x18003421e  push    r13
0x180034220  push    r14
0x180034222  push    r15
0x180034224  lea     rbp, [rsp-230h]
0x18003422c  sub     rsp, 330h
0x180034233  mov     rax, cs:__security_cookie
0x18003423a  xor     rax, rsp
0x18003423d  mov     [rbp+260h+var_40], rax
0x180034244  mov     rdi, rdx
0x180034247  mov     r8, rdx
0x18003424a  lea     rdx, aInRemoveallapp_0; "In RemoveAllAppsFromSystemSis %ls."
0x180034251  mov     r15, rcx
0x180034254  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180034259  xor     r13d, r13d
0x18003425c  lea     r14, aOnecoreAdminAp_10; "onecore\\admin\\appmodel\\appxalluserst"...
0x180034263  test    eax, eax
0x180034265  jns     short loc_18003427E
0x180034267  mov     rcx, [rbp+268h]; this
0x18003426e  mov     r9d, eax; char *
0x180034271  mov     r8, r14; unsigned int
0x180034274  mov     edx, 918h; void *
0x180034279  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003427e  xorps   xmm0, xmm0
0x180034281  mov     [rbp+260h+var_2B0], r13d
0x180034285  lea     rdx, [rbp+260h+Src]; Common::Deployment::Configuration *
0x180034289  mov     rcx, rdi; this
0x18003428c  movups  xmmword ptr [rbp+260h+Src], xmm0
0x180034290  call    ?GetSystemSisPath@AppxAllUserStore@@YAJPEBGAEAVStringBuffer@Common@@@Z; AppxAllUserStore::GetSystemSisPath(ushort const *,Common::StringBuffer &)
0x180034295  mov     ebx, eax
0x180034297  test    eax, eax
0x180034299  jns     short loc_1800342B2
0x18003429b  mov     rcx, [rbp+268h]; this
0x1800342a2  mov     r9d, eax; char *
0x1800342a5  mov     r8, r14; unsigned int
0x1800342a8  mov     edx, 91Bh; void *
0x1800342ad  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800342b2  mov     r8, [rbp+260h+Src+8]
0x1800342b6  lea     rdx, aGetsystemsispa; "GetSystemSisPath got %ls, 0x%0x."
0x1800342bd  mov     r9d, ebx
0x1800342c0  mov     rcx, r15; this
0x1800342c3  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x1800342c8  test    eax, eax
0x1800342ca  jns     short loc_1800342E3
0x1800342cc  mov     rcx, [rbp+268h]; this
0x1800342d3  mov     r9d, eax; char *
0x1800342d6  mov     r8, r14; unsigned int
0x1800342d9  mov     edx, 91Ch; void *
0x1800342de  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800342e3  test    ebx, ebx
0x1800342e5  jns     short loc_180034314
0x1800342e7  mov     rcx, [rbp+268h]; this
0x1800342ee  lea     rax, aSystemRootLs; "system root %ls."
0x1800342f5  mov     [rsp+360h+var_338], rdi; char *
0x1800342fa  mov     r9d, ebx; char *
0x1800342fd  mov     r8, r14; unsigned int
0x180034300  mov     qword ptr [rsp+360h+var_340], rax; int
0x180034305  mov     edx, 91Dh; void *
0x18003430a  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003430f  jmp     loc_180034828
0x180034314  mov     rcx, [rbp+260h+Src+8]; Src
0x180034318  lea     r8, [rsp+360h+lpFileName]; this
0x18003431d  xorps   xmm0, xmm0
0x180034320  mov     [rsp+360h+var_308], r13d
0x180034325  lea     rdx, asc_180053710; "*"
0x18003432c  movups  xmmword ptr [rsp+360h+lpFileName], xmm0
0x180034331  call    ?CombinePaths@PathHelpers@Common@@SAJPEBG0PEAVStringBuffer@2@@Z; Common::PathHelpers::CombinePaths(ushort const *,ushort const *,Common::StringBuffer *)
0x180034336  mov     ebx, eax
0x180034338  test    eax, eax
0x18003433a  jns     short loc_180034362
0x18003433c  mov     rcx, [rbp+268h]; this
0x180034343  mov     r9d, eax; char *
0x180034346  mov     r8, r14; unsigned int
0x180034349  mov     edx, 920h; void *
0x18003434e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034353  lea     rcx, [rsp+360h+lpFileName]; this
0x180034358  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18003435d  jmp     loc_180034828
0x180034362  xor     edx, edx; Val
0x180034364  mov     [rbp+260h+var_2E0], r13
0x180034368  mov     r8d, 250h; Size
0x18003436e  mov     [rbp+260h+var_2D8], r13
0x180034372  lea     rcx, [rbp+260h+FindFileData]; void *
0x180034376  mov     [rbp+260h+var_2D0], r13
0x18003437a  mov     [rbp+260h+var_2C8], 1
0x18003437e  call    memset_0
0x180034383  mov     rcx, [rsp+360h+lpFileName+8]; lpFileName
0x180034388  lea     rdx, [rbp+260h+FindFileData]; lpFindFileData
0x18003438c  mov     [rsp+360h+hFindFile], r13
0x180034391  call    cs:__imp_FindFirstFileW
0x180034397  mov     rdx, rax
0x18003439a  lea     rcx, [rsp+360h+hFindFile]
0x18003439f  call    ??4AutoHandleFindFile@Common@@QEAAPEAXPEAX@Z; Common::AutoHandleFindFile::operator=(void *)
0x1800343a4  mov     rbx, [rsp+360h+hFindFile]
0x1800343a9  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800343ad  cmp     rbx, rsi
0x1800343b0  jnz     loc_180034452
0x1800343b6  call    cs:__imp_GetLastError
0x1800343bc  mov     ebx, eax
0x1800343be  cmp     eax, 12h
0x1800343c1  jz      short loc_180034417
0x1800343c3  test    eax, eax
0x1800343c5  jle     short loc_1800343D0
0x1800343c7  movzx   ebx, ax
0x1800343ca  or      ebx, 80070000h
0x1800343d0  test    ebx, ebx
0x1800343d2  jns     short loc_180034401
0x1800343d4  mov     rax, [rsp+360h+lpFileName+8]
0x1800343d9  mov     r9d, ebx; char *
0x1800343dc  mov     rcx, [rbp+268h]; this
0x1800343e3  mov     r8, r14; unsigned int
0x1800343e6  mov     [rsp+360h+var_338], rax; char *
0x1800343eb  mov     edx, 92Bh; void *
0x1800343f0  lea     rax, aSearchingLs; "Searching %ls."
0x1800343f7  mov     qword ptr [rsp+360h+var_340], rax; int
0x1800343fc  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180034401  mov     rcx, rsi; this
0x180034404  call    ?AutoHandleFreeFindFile@Common@@YAXPEAX@Z; Common::AutoHandleFreeFindFile(void *)
0x180034409  lea     rcx, [rbp+260h+var_2E0]
0x18003440d  call    ??1?$Array@U_SharedPackageContainerInfo@AppxAllUserStore@@V?$ContainerOperations@U_SharedPackageContainerInfo@AppxAllUserStore@@U12@@Common@@VNoKey@4@V?$ContainerOperations@VNoKey@Common@@U_SharedPackageContainerInfo@AppxAllUserStore@@@4@V?$ArrayOperations@U_SharedPackageContainerInfo@AppxAllUserStore@@VNoKey@Common@@@4@@Common@@QEAA@XZ; Common::Array<AppxAllUserStore::_SharedPackageContainerInfo,Common::ContainerOperations<AppxAllUserStore::_SharedPackageContainerInfo,AppxAllUserStore::_SharedPackageContainerInfo>,Common::NoKey,Common::ContainerOperations<Common::NoKey,AppxAllUserStore::_SharedPackageContainerInfo>,Common::ArrayOperations<AppxAllUserStore::_SharedPackageContainerInfo,Common::NoKey>>::~Array<AppxAllUserStore::_SharedPackageContainerInfo,Common::ContainerOperations<AppxAllUserStore::_SharedPackageContainerInfo,AppxAllUserStore::_SharedPackageContainerInfo>,Common::NoKey,Common::ContainerOperations<Common::NoKey,AppxAllUserStore::_SharedPackageContainerInfo>,Common::ArrayOperations<AppxAllUserStore::_SharedPackageContainerInfo,Common::NoKey>>(void)
0x180034412  jmp     loc_180034353
0x180034417  lea     rdx, aNothingUnderTh_0; "Nothing under the system Sis root folde"...
0x18003441e  mov     rcx, r15; this
0x180034421  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180034426  test    eax, eax
0x180034428  jns     short loc_180034441
0x18003442a  mov     rcx, [rbp+268h]; this
0x180034431  mov     r9d, eax; char *
0x180034434  mov     r8, r14; unsigned int
0x180034437  mov     edx, 92Ch; void *
0x18003443c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180034441  mov     rcx, rsi
0x180034444  jmp     loc_18003480D
0x180034449  cmp     rbx, rsi
0x18003444c  jz      loc_180034654
0x180034452  cmp     [rbp+260h+FindFileData.cFileName], 2Eh ; '.'
0x180034457  movzx   eax, [rbp+260h+FindFileData.cFileName+2]
0x18003445b  jnz     short loc_18003447E
0x18003445d  test    ax, ax
0x180034460  jz      loc_180034569
0x180034466  cmp     [rbp+260h+FindFileData.cFileName], 2Eh ; '.'
0x18003446b  jnz     short loc_18003447E
0x18003446d  cmp     ax, 2Eh ; '.'
0x180034471  jnz     short loc_18003447E
0x180034473  cmp     [rbp+260h+FindFileData.cFileName+4], r13w
0x180034478  jz      loc_180034569
0x18003447e  test    byte ptr [rbp+260h+FindFileData.dwFileAttributes], 10h
0x180034482  jz      loc_180034569
0x180034488  xorps   xmm0, xmm0
0x18003448b  mov     [rsp+360h+var_2E8], r13d
0x180034490  lea     rdx, [rsp+360h+lpNewFileName]; this
0x180034495  lea     rcx, [rbp+260h+FindFileData.cFileName]; lpString1
0x180034499  movups  xmmword ptr [rsp+360h+lpNewFileName], xmm0
0x18003449e  call    ?GetPackageFamilyNameFromFullName@Deployment@Common@@YAJPEBGPEAVStringBuffer@2@@Z; Common::Deployment::GetPackageFamilyNameFromFullName(ushort const *,Common::StringBuffer *)
0x1800344a3  lea     r8, [rbp+260h+FindFileData.cFileName]
0x1800344a7  mov     rcx, r15; this
0x1800344aa  test    eax, eax
0x1800344ac  js      loc_180034538
0x1800344b2  lea     rdx, aFoundPackageLs_0; "Found package %ls to remove."
0x1800344b9  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x1800344be  test    eax, eax
0x1800344c0  jns     short loc_1800344D9
0x1800344c2  mov     rcx, [rbp+268h]; this
0x1800344c9  mov     r9d, eax; char *
0x1800344cc  mov     r8, r14; unsigned int
0x1800344cf  mov     edx, 93Ah; void *
0x1800344d4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800344d9  xorps   xmm0, xmm0
0x1800344dc  mov     [rsp+360h+var_320], r13d
0x1800344e1  lea     rdx, [rbp+260h+FindFileData.cFileName]; Src
0x1800344e5  lea     rcx, [rsp+360h+lpExistingFileName]; this
0x1800344ea  movups  xmmword ptr [rsp+360h+lpExistingFileName], xmm0
0x1800344ef  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x1800344f4  mov     edi, eax
0x1800344f6  test    eax, eax
0x1800344f8  js      loc_1800345B2
0x1800344fe  mov     rsi, [rsp+360h+lpExistingFileName+8]
0x180034503  lea     rcx, [rbp+260h+var_2E0]
0x180034507  mov     rdx, rsi
0x18003450a  call    ?Add@?$Array@GV?$ContainerOperations@GG@Common@@VNoKey@2@V?$ContainerOperations@VNoKey@Common@@G@2@V?$ArrayOperations@GVNoKey@Common@@@2@@Common@@QEAAJPEAG@Z; Common::Array<ushort,Common::ContainerOperations<ushort,ushort>,Common::NoKey,Common::ContainerOperations<Common::NoKey,ushort>,Common::ArrayOperations<ushort,Common::NoKey>>::Add(ushort *)
0x18003450f  mov     edi, eax
0x180034511  test    eax, eax
0x180034513  js      loc_1800345A6
0x180034519  lea     rcx, [rsp+360h+lpExistingFileName]; this
0x18003451e  mov     [rsp+360h+lpExistingFileName+8], r13
0x180034523  mov     dword ptr [rsp+360h+lpExistingFileName], r13d
0x180034528  mov     [rsp+360h+var_320], r13d
0x18003452d  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180034532  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180034536  jmp     short loc_18003455F
0x180034538  lea     rdx, aIgnoringPackag; "Ignoring package %ls because could not "...
0x18003453f  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180034544  test    eax, eax
0x180034546  jns     short loc_18003455F
0x180034548  mov     rcx, [rbp+268h]; this
0x18003454f  mov     r9d, eax; char *
0x180034552  mov     r8, r14; unsigned int
0x180034555  mov     edx, 946h; void *
0x18003455a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003455f  lea     rcx, [rsp+360h+lpNewFileName]; this
0x180034564  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180034569  lea     rdx, [rbp+260h+FindFileData]; lpFindFileData
0x18003456d  mov     rcx, rbx; hFindFile
0x180034570  call    cs:__imp_FindNextFileW
0x180034576  test    eax, eax
0x180034578  jnz     loc_180034449
0x18003457e  call    cs:__imp_GetLastError
0x180034584  mov     edi, eax
0x180034586  cmp     eax, 12h
0x180034589  jnz     loc_180034614
0x18003458f  mov     rdx, rsi
0x180034592  lea     rcx, [rsp+360h+hFindFile]
0x180034597  call    ??4AutoHandleFindFile@Common@@QEAAPEAXPEAX@Z; Common::AutoHandleFindFile::operator=(void *)
0x18003459c  mov     rbx, [rsp+360h+hFindFile]
0x1800345a1  jmp     loc_180034449
0x1800345a6  mov     [rsp+360h+var_338], rsi
0x1800345ab  mov     edx, 941h
0x1800345b0  jmp     short loc_1800345C0
0x1800345b2  lea     rax, [rbp+260h+FindFileData.cFileName]
0x1800345b6  mov     edx, 93Eh; void *
0x1800345bb  mov     [rsp+360h+var_338], rax; char *
0x1800345c0  mov     rcx, [rbp+268h]; this
0x1800345c7  lea     rax, aFolderLs; "Folder %ls."
0x1800345ce  mov     r8, r14; unsigned int
0x1800345d1  mov     qword ptr [rsp+360h+var_340], rax; int
0x1800345d6  mov     r9d, edi; char *
0x1800345d9  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800345de  lea     rcx, [rsp+360h+lpExistingFileName]; this
0x1800345e3  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x1800345e8  lea     rcx, [rsp+360h+lpNewFileName]; this
0x1800345ed  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x1800345f2  mov     rcx, rbx; this
0x1800345f5  call    ?AutoHandleFreeFindFile@Common@@YAXPEAX@Z; Common::AutoHandleFreeFindFile(void *)
0x1800345fa  lea     rcx, [rbp+260h+var_2E0]
0x1800345fe  call    ??1?$Array@U_SharedPackageContainerInfo@AppxAllUserStore@@V?$ContainerOperations@U_SharedPackageContainerInfo@AppxAllUserStore@@U12@@Common@@VNoKey@4@V?$ContainerOperations@VNoKey@Common@@U_SharedPackageContainerInfo@AppxAllUserStore@@@4@V?$ArrayOperations@U_SharedPackageContainerInfo@AppxAllUserStore@@VNoKey@Common@@@4@@Common@@QEAA@XZ; Common::Array<AppxAllUserStore::_SharedPackageContainerInfo,Common::ContainerOperations<AppxAllUserStore::_SharedPackageContainerInfo,AppxAllUserStore::_SharedPackageContainerInfo>,Common::NoKey,Common::ContainerOperations<Common::NoKey,AppxAllUserStore::_SharedPackageContainerInfo>,Common::ArrayOperations<AppxAllUserStore::_SharedPackageContainerInfo,Common::NoKey>>::~Array<AppxAllUserStore::_SharedPackageContainerInfo,Common::ContainerOperations<AppxAllUserStore::_SharedPackageContainerInfo,AppxAllUserStore::_SharedPackageContainerInfo>,Common::NoKey,Common::ContainerOperations<Common::NoKey,AppxAllUserStore::_SharedPackageContainerInfo>,Common::ArrayOperations<AppxAllUserStore::_SharedPackageContainerInfo,Common::NoKey>>(void)
0x180034603  lea     rcx, [rsp+360h+lpFileName]; this
0x180034608  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18003460d  mov     ebx, edi
0x18003460f  jmp     loc_180034828
0x180034614  test    eax, eax
0x180034616  jle     short loc_180034621
0x180034618  movzx   edi, ax
0x18003461b  or      edi, 80070000h
0x180034621  test    edi, edi
0x180034623  jns     short loc_1800345F2
0x180034625  mov     rax, [rsp+360h+lpFileName+8]
0x18003462a  mov     r9d, edi; char *
0x18003462d  mov     rcx, [rbp+268h]; this
0x180034634  mov     r8, r14; unsigned int
0x180034637  mov     [rsp+360h+var_338], rax; char *
0x18003463c  mov     edx, 94Fh; void *
0x180034641  lea     rax, aSearchingLs; "Searching %ls."
0x180034648  mov     qword ptr [rsp+360h+var_340], rax; int
0x18003464d  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180034652  jmp     short loc_1800345F2
0x180034654  mov     rcx, [rbp+260h+Src+8]; Src
0x180034658  lea     r8, [rbp+260h+var_2A8]; this
0x18003465c  xorps   xmm0, xmm0
0x18003465f  mov     [rbp+260h+var_298], r13d
0x180034663  lea     rdx, aDeleted; "Deleted"
0x18003466a  movups  xmmword ptr [rbp+260h+var_2A8], xmm0
0x18003466e  call    ?CombinePaths@PathHelpers@Common@@SAJPEBG0PEAVStringBuffer@2@@Z; Common::PathHelpers::CombinePaths(ushort const *,ushort const *,Common::StringBuffer *)
0x180034673  mov     ebx, eax
0x180034675  test    eax, eax
0x180034677  jns     short loc_18003469E
0x180034679  mov     rcx, [rbp+268h]; this
0x180034680  mov     r9d, eax; char *
0x180034683  mov     r8, r14; unsigned int
0x180034686  mov     edx, 955h; void *
0x18003468b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034690  lea     rcx, [rbp+260h+var_2A8]; this
0x180034694  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180034699  jmp     loc_180034401
0x18003469e  mov     rsi, [rbp+260h+var_2D0]
0x1800346a2  mov     rbx, r13
0x1800346a5  test    rsi, rsi
0x1800346a8  jz      loc_180034800
0x1800346ae  mov     r12, [rbp+260h+var_2E0]
0x1800346b2  mov     [rsp+360h+var_320], r13d
0x1800346b7  xorps   xmm0, xmm0
0x1800346ba  lea     rdi, ds:0[rbx*8]
0x1800346c2  mov     rdx, r13
0x1800346c5  movups  xmmword ptr [rsp+360h+lpExistingFileName], xmm0
0x1800346ca  cmp     rbx, rsi
0x1800346cd  jnb     short loc_1800346D3
0x1800346cf  mov     rdx, [rdi+r12]; unsigned __int16 *
0x1800346d3  mov     rcx, [rbp+260h+Src+8]; Src
0x1800346d7  lea     r8, [rsp+360h+lpExistingFileName]; this
0x1800346dc  call    ?CombinePaths@PathHelpers@Common@@SAJPEBG0PEAVStringBuffer@2@@Z; Common::PathHelpers::CombinePaths(ushort const *,ushort const *,Common::StringBuffer *)
0x1800346e1  mov     r14d, eax
0x1800346e4  test    eax, eax
0x1800346e6  js      loc_18003485D
0x1800346ec  mov     rcx, [rsp+360h+lpExistingFileName+8]
0x1800346f1  lea     r9, ?LogRemoveDirectoryTreeError@Internal@AppxAllUserStore@@YAJPEBGW4ActionType@@JPEAX@Z; AppxAllUserStore::Internal::LogRemoveDirectoryTreeError(ushort const *,ActionType,long,void *)
0x1800346f8  mov     qword ptr [rsp+360h+var_340], r15; int
0x1800346fd  call    RemoveDirectoryTree
  ... truncated ...
```
