# AppxAllUserStore::Internal::ProcessPackageFamily(AppxAllUserStore::BasicLogFile *,ushort const *,ushort const *,Common::Array<ushort,Common::ContainerOperations<ushort,ushort>,Common::NoKey,Common::ContainerOperations<Common::NoKey,ushort>,Common::ArrayOperations<ushort,Common::NoKey>> &)

- ea: `0x1800447c8`
- end: `0x180044c98`
- name: `?ProcessPackageFamily@Internal@AppxAllUserStore@@YAJPEAVBasicLogFile@2@PEBG1AEAV?$Array@GV?$ContainerOperations@GG@Common@@VNoKey@2@V?$ContainerOperations@VNoKey@Common@@G@2@V?$ArrayOperations@GVNoKey@Common@@@2@@Common@@@Z`
- size: `1232`
- prototype: `__int64 __fastcall(AppxAllUserStore::BasicLogFile *this, struct AppxAllUserStore::BasicLogFile *, unsigned __int16 *Src)`
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18004252c`
- `0x180043b10`

## callees

- `0x180004920`
- `0x180006c00`
- `0x180008550`
- `0x180017cd0`
- `0x180017f50`
- `0x180018248`
- `0x18001a6a0`
- `0x1800262ec`
- `0x180030d5c`
- `0x180031fe0`
- `0x1800414c8`
- `0x1800447c8`
- `0x18004682c`
- `0x18004c98a`
- `0x18004c9d0`

## import_xrefs

- `msvcrt!wcschr` at `0x1800448be`
- `msvcrt!wcschr` at `0x1800448be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800449eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044b45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800449eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044b45`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800449d0`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800449d0`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180044b37`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180044b37`

## string_xrefs

- `0x18004486a`: `GetSystemSisPath failed, 0x%0x.`
- `0x180044a9c`: `Found directory %ls`

## pseudocode

```c
__int64 __fastcall AppxAllUserStore::Internal::ProcessPackageFamily(
        AppxAllUserStore::BasicLogFile *this,
        struct AppxAllUserStore::BasicLogFile *a2,
        struct Common::StringBuffer *Src,
        __int64 a4)
{
  int v8; // eax
  int SystemSisPath; // eax
  unsigned int v10; // ebx
  int v11; // eax
  wchar_t *v12; // rax
  wchar_t *v13; // r14
  int appended; // eax
  __int64 v15; // rdx
  int v16; // eax
  void *v17; // rdx
  Common *v18; // rbx
  DWORD v19; // eax
  void *v20; // rdx
  signed int v21; // edi
  int v22; // eax
  bool v23; // sf
  __int64 v24; // rdx
  int v25; // eax
  int v26; // eax
  int v27; // eax
  DWORD LastError; // eax
  int v29; // eax
  bool v30; // sf
  int v32; // [rsp+20h] [rbp-E0h]
  unsigned __int16 v33[4]; // [rsp+20h] [rbp-E0h]
  char *v34; // [rsp+28h] [rbp-D8h]
  unsigned __int16 v35; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v36[2]; // [rsp+38h] [rbp-C8h] BYREF
  int v37; // [rsp+48h] [rbp-B8h]
  LPCWSTR lpFileName[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v39; // [rsp+60h] [rbp-A0h]
  Common *FirstFileW; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *Srca[2]; // [rsp+70h] [rbp-90h] BYREF
  int v42; // [rsp+80h] [rbp-80h]
  _QWORD v43[3]; // [rsp+88h] [rbp-78h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+338h] [rbp+238h]

  if ( this )
  {
    v32 = *(_DWORD *)(a4 + 16);
    v8 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"ProcessPackageFamily %ls - %ls. array size %u.", Src, a2);
    if ( v8 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x500,
        (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
        (const char *)(unsigned int)v8);
  }
  v42 = 0;
  *(_OWORD *)Srca = 0;
  SystemSisPath = AppxAllUserStore::GetSystemSisPath(a2, (Common::Deployment::Configuration *)Srca, Src);
  v10 = SystemSisPath;
  if ( SystemSisPath < 0 )
  {
    if ( this )
    {
      v11 = AppxAllUserStore::BasicLogFile::WriteMsg(
              this,
              L"GetSystemSisPath failed, 0x%0x.",
              (unsigned int)SystemSisPath);
      if ( v11 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x504,
          (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
          (const char *)(unsigned int)v11);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x504,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
      (const char *)v10,
      v32);
    goto LABEL_52;
  }
  v37 = 0;
  *(_OWORD *)v36 = 0;
  v12 = wcschr((const wchar_t *)Src, 0x5Fu);
  v13 = v12;
  if ( !v12 )
  {
    v10 = -2147024809;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x511,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
      (const char *)0x80070057LL,
      (int)"PackageFamilyName invalid: %ls.",
      (const char *)Src);
    goto LABEL_51;
  }
  appended = Common::StringBuffer::SetValue(
               (Common::StringBuffer *)v36,
               (const unsigned __int16 *)Src,
               ((char *)v12 - (char *)Src + 2) >> 1);
  v10 = appended;
  if ( appended < 0 )
  {
    v15 = 1290;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
      (const char *)(unsigned int)appended,
      v32);
LABEL_51:
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v36);
    goto LABEL_52;
  }
  v43[1] = v36;
  v43[0] = &Common::StringBufferBuilder::`vftable';
  v43[2] = v36;
  appended = Common::StringBuilder::AppendString((Common::StringBuilder *)v43, L"*_");
  v10 = appended;
  if ( appended < 0 )
  {
    v15 = 1292;
    goto LABEL_12;
  }
  appended = Common::StringBuilder::AppendString((Common::StringBuilder *)v43, v13 + 1);
  v10 = appended;
  if ( appended < 0 )
  {
    v15 = 1293;
    goto LABEL_12;
  }
  v39 = 0;
  *(_OWORD *)lpFileName = 0;
  v16 = Common::PathHelpers::CombinePaths(Srca[1], v36[1], (struct Common::StringBuffer *)lpFileName);
  v10 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x515,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
      (const char *)(unsigned int)v16,
      v32);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpFileName);
    goto LABEL_51;
  }
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = (Common *)FindFirstFileW(lpFileName[1], &FindFileData);
  v18 = FirstFileW;
  if ( FirstFileW != (Common *)-1LL )
  {
    while ( 1 )
    {
      do
      {
        if ( v18 == (Common *)-1LL )
        {
          Common::AutoHandleFreeFindFile((Common *)0xFFFFFFFFFFFFFFFFLL, v17);
          Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpFileName);
          Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v36);
          Common::StringBuffer::~StringBuffer((Common::StringBuffer *)Srca);
          return 0;
        }
        if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
        {
          if ( this )
          {
            v25 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"Found directory %ls", FindFileData.cFileName);
            if ( v25 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x526,
                (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
                (const char *)(unsigned int)v25);
          }
          LOBYTE(v35) = 0;
          v26 = AppxAllUserStore::Internal::AddPackageFullNameToMainArrayIfNeeded(
                  this,
                  a2,
                  FindFileData.cFileName,
                  (_QWORD *)a4,
                  &v35);
          if ( this )
          {
            LODWORD(v34) = v26;
            *(_DWORD *)v33 = (unsigned __int8)v35;
            v27 = AppxAllUserStore::BasicLogFile::WriteMsg(
                    this,
                    L"AddPackageFullNameToMainArrayIfNeeded %ls size %u added %u, 0x%0x.",
                    FindFileData.cFileName,
                    *(unsigned int *)(a4 + 16),
                    *(_QWORD *)v33,
                    v34);
            if ( v27 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x52C,
                (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
                (const char *)(unsigned int)v27);
          }
        }
      }
      while ( FindNextFileW(v18, &FindFileData) );
      LastError = GetLastError();
      v21 = LastError;
      if ( LastError != 18 )
        break;
      Common::AutoHandleFindFile::operator=(&FirstFileW, (Common *)0xFFFFFFFFFFFFFFFFLL);
      v18 = FirstFileW;
    }
    if ( this )
    {
      v29 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"FindNextFileW %ls got error %u.", lpFileName[1], LastError);
      if ( v29 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x534,
          (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
          (const char *)(unsigned int)v29);
    }
    v30 = v21 < 0;
    if ( v21 > 0 )
    {
      v21 = (unsigned __int16)v21 | 0x80070000;
      v30 = v21 < 0;
    }
    if ( v30 )
    {
      v24 = 1333;
      goto LABEL_47;
    }
    goto LABEL_48;
  }
  v19 = GetLastError();
  v21 = v19;
  if ( this )
  {
    v22 = AppxAllUserStore::BasicLogFile::WriteMsg(
            this,
            L"FindFirstFileW %ls got error %u, array size %u.",
            lpFileName[1],
            v19,
            *(_DWORD *)(a4 + 16));
    if ( v22 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x51D,
        (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
        (const char *)(unsigned int)v22);
  }
  if ( v21 != 18 )
  {
    v23 = v21 < 0;
    if ( v21 > 0 )
    {
      v21 = (unsigned __int16)v21 | 0x80070000;
      v23 = v21 < 0;
    }
    if ( v23 )
    {
      v24 = 1310;
LABEL_47:
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)v24,
        (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
        (const char *)(unsigned int)v21,
        (int)"%ls.",
        (const char *)lpFileName[1]);
    }
LABEL_48:
    Common::AutoHandleFreeFindFile(v18, v20);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpFileName);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v36);
    v10 = v21;
    goto LABEL_52;
  }
  Common::AutoHandleFreeFindFile((Common *)0xFFFFFFFFFFFFFFFFLL, v20);
  Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpFileName);
  Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v36);
  v10 = 0;
LABEL_52:
  Common::StringBuffer::~StringBuffer((Common::StringBuffer *)Srca);
  return v10;
}

```

## disassembly

```asm
0x1800447c8  push    rbp
0x1800447ca  push    rbx
0x1800447cb  push    rsi
0x1800447cc  push    rdi
0x1800447cd  push    r12
0x1800447cf  push    r14
0x1800447d1  push    r15
0x1800447d3  lea     rbp, [rsp-200h]
0x1800447db  sub     rsp, 300h
0x1800447e2  mov     rax, cs:__security_cookie
0x1800447e9  xor     rax, rsp
0x1800447ec  mov     [rbp+230h+var_40], rax
0x1800447f3  lea     r14, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\appxalluserst"...
0x1800447fa  mov     r15, r9
0x1800447fd  mov     rdi, r8
0x180044800  mov     r12, rdx
0x180044803  mov     rsi, rcx
0x180044806  test    rcx, rcx
0x180044809  jz      short loc_18004483D
0x18004480b  mov     eax, [r9+10h]
0x18004480f  mov     r9, rdx
0x180044812  lea     rdx, aProcesspackage; "ProcessPackageFamily %ls - %ls. array s"...
0x180044819  mov     dword ptr [rsp+330h+var_310], eax; int
0x18004481d  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180044822  test    eax, eax
0x180044824  jns     short loc_18004483D
0x180044826  mov     rcx, [rbp+238h]; this
0x18004482d  mov     r9d, eax; char *
0x180044830  mov     r8, r14; unsigned int
0x180044833  mov     edx, 500h; void *
0x180044838  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004483d  xor     eax, eax
0x18004483f  lea     rdx, [rsp+330h+Src]; Common::Deployment::Configuration *
0x180044844  xorps   xmm0, xmm0
0x180044847  mov     [rbp+230h+var_2B0], eax
0x18004484a  mov     rcx, r12; this
0x18004484d  movups  xmmword ptr [rsp+330h+Src], xmm0
0x180044852  call    ?GetSystemSisPath@AppxAllUserStore@@YAJPEBGAEAVStringBuffer@Common@@@Z; AppxAllUserStore::GetSystemSisPath(ushort const *,Common::StringBuffer &)
0x180044857  mov     ebx, eax
0x180044859  test    eax, eax
0x18004485b  jns     short loc_1800448AA
0x18004485d  mov     edi, 504h
0x180044862  test    rsi, rsi
0x180044865  jz      short loc_180044891
0x180044867  mov     r8d, eax
0x18004486a  lea     rdx, aGetsystemsispa_0; "GetSystemSisPath failed, 0x%0x."
0x180044871  mov     rcx, rsi; this
0x180044874  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180044879  test    eax, eax
0x18004487b  jns     short loc_180044891
0x18004487d  mov     rcx, [rbp+238h]; this
0x180044884  mov     r9d, eax; char *
0x180044887  mov     r8, r14; unsigned int
0x18004488a  mov     edx, edi; void *
0x18004488c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180044891  mov     rcx, [rbp+238h]; this
0x180044898  mov     r9d, ebx; char *
0x18004489b  mov     r8, r14; unsigned int
0x18004489e  mov     edx, edi; void *
0x1800448a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800448a5  jmp     loc_180044C6B
0x1800448aa  xor     eax, eax
0x1800448ac  xorps   xmm0, xmm0
0x1800448af  mov     rcx, rdi; Str
0x1800448b2  mov     [rsp+330h+var_2E8], eax
0x1800448b6  movups  xmmword ptr [rsp+330h+var_2F8], xmm0
0x1800448bb  lea     edx, [rax+5Fh]; Ch
0x1800448be  call    cs:__imp_wcschr
0x1800448c4  mov     r14, rax
0x1800448c7  test    rax, rax
0x1800448ca  jz      loc_180044C30
0x1800448d0  mov     r8, rax
0x1800448d3  lea     rcx, [rsp+330h+var_2F8]; this
0x1800448d8  sub     r8, rdi
0x1800448db  mov     rdx, rdi; Src
0x1800448de  add     r8, 2
0x1800448e2  sar     r8, 1; unsigned int
0x1800448e5  call    ?SetValue@StringBuffer@Common@@QEAAJPEBGK@Z; Common::StringBuffer::SetValue(ushort const *,ulong)
0x1800448ea  mov     ebx, eax
0x1800448ec  test    eax, eax
0x1800448ee  jns     short loc_180044910
0x1800448f0  mov     edx, 50Ah; void *
0x1800448f5  mov     rcx, [rbp+238h]; this
0x1800448fc  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\appxalluserst"...
0x180044903  mov     r9d, eax; char *
0x180044906  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004490b  jmp     loc_180044C61
0x180044910  lea     rax, [rsp+330h+var_2F8]
0x180044915  mov     [rbp+230h+var_2A0], rax
0x180044919  lea     rdx, asc_180057490; "*_"
0x180044920  lea     rax, ??_7StringBufferBuilder@Common@@6B@; const Common::StringBufferBuilder::`vftable'
0x180044927  mov     [rbp+230h+var_2A8], rax
0x18004492b  lea     rcx, [rbp+230h+var_2A8]; this
0x18004492f  lea     rax, [rsp+330h+var_2F8]
0x180044934  mov     [rbp+230h+var_298], rax
0x180044938  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x18004493d  mov     ebx, eax
0x18004493f  test    eax, eax
0x180044941  jns     short loc_18004494A
0x180044943  mov     edx, 50Ch
0x180044948  jmp     short loc_1800448F5
0x18004494a  lea     rdx, [r14+2]; unsigned __int16 *
0x18004494e  lea     rcx, [rbp+230h+var_2A8]; this
0x180044952  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x180044957  mov     ebx, eax
0x180044959  test    eax, eax
0x18004495b  jns     short loc_180044964
0x18004495d  mov     edx, 50Dh
0x180044962  jmp     short loc_1800448F5
0x180044964  mov     rdx, [rsp+330h+var_2F8+8]; unsigned __int16 *
0x180044969  lea     r8, [rsp+330h+lpFileName]; this
0x18004496e  mov     rcx, [rsp+330h+Src+8]; Src
0x180044973  xor     eax, eax
0x180044975  xorps   xmm0, xmm0
0x180044978  mov     [rsp+330h+var_2D0], eax
0x18004497c  movups  xmmword ptr [rsp+330h+lpFileName], xmm0
0x180044981  call    ?CombinePaths@PathHelpers@Common@@SAJPEBG0PEAVStringBuffer@2@@Z; Common::PathHelpers::CombinePaths(ushort const *,ushort const *,Common::StringBuffer *)
0x180044986  mov     ebx, eax
0x180044988  test    eax, eax
0x18004498a  jns     short loc_1800449B6
0x18004498c  mov     rcx, [rbp+238h]; this
0x180044993  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\appxalluserst"...
0x18004499a  mov     r9d, eax; char *
0x18004499d  mov     edx, 515h; void *
0x1800449a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800449a7  lea     rcx, [rsp+330h+lpFileName]; this
0x1800449ac  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x1800449b1  jmp     loc_180044C61
0x1800449b6  xor     edx, edx; Val
0x1800449b8  lea     rcx, [rbp+230h+FindFileData]; void *
0x1800449bc  mov     r8d, 250h; Size
0x1800449c2  call    memset_0
0x1800449c7  mov     rcx, [rsp+330h+lpFileName+8]; lpFileName
0x1800449cc  lea     rdx, [rbp+230h+FindFileData]; lpFindFileData
0x1800449d0  call    cs:__imp_FindFirstFileW
0x1800449d6  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800449da  mov     [rsp+330h+var_2C8], rax
0x1800449df  mov     rbx, rax
0x1800449e2  cmp     rax, r14
0x1800449e5  jnz     loc_180044A7D
0x1800449eb  call    cs:__imp_GetLastError
0x1800449f1  mov     edi, eax
0x1800449f3  test    rsi, rsi
0x1800449f6  jz      short loc_180044A36
0x1800449f8  mov     ecx, [r15+10h]
0x1800449fc  lea     rdx, aFindfirstfilew_0; "FindFirstFileW %ls got error %u, array "...
0x180044a03  mov     r8, [rsp+330h+lpFileName+8]
0x180044a08  mov     r9d, eax
0x180044a0b  mov     dword ptr [rsp+330h+var_310], ecx; int
0x180044a0f  mov     rcx, rsi; this
0x180044a12  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180044a17  test    eax, eax
0x180044a19  jns     short loc_180044A36
0x180044a1b  mov     rcx, [rbp+238h]; this
0x180044a22  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\appxalluserst"...
0x180044a29  mov     r9d, eax; char *
0x180044a2c  mov     edx, 51Dh; void *
0x180044a31  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180044a36  cmp     edi, 12h
0x180044a39  jz      short loc_180044A5A
0x180044a3b  test    edi, edi
0x180044a3d  jle     short loc_180044A4A
0x180044a3f  movzx   edi, di
0x180044a42  or      edi, 80070000h
0x180044a48  test    edi, edi
0x180044a4a  jns     loc_180044BE6
0x180044a50  mov     edx, 51Eh
0x180044a55  jmp     loc_180044BBA
0x180044a5a  mov     rcx, rbx; this
0x180044a5d  call    ?AutoHandleFreeFindFile@Common@@YAXPEAX@Z; Common::AutoHandleFreeFindFile(void *)
0x180044a62  lea     rcx, [rsp+330h+lpFileName]; this
0x180044a67  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180044a6c  lea     rcx, [rsp+330h+var_2F8]; this
0x180044a71  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180044a76  xor     ebx, ebx
0x180044a78  jmp     loc_180044C6B
0x180044a7d  cmp     rbx, r14
0x180044a80  jz      loc_180044C06
0x180044a86  test    byte ptr [rbp+230h+FindFileData.dwFileAttributes], 10h
0x180044a8a  jz      loc_180044B30
0x180044a90  test    rsi, rsi
0x180044a93  jz      short loc_180044AC7
0x180044a95  lea     r8, [rbp+230h+FindFileData.cFileName]
0x180044a99  mov     rcx, rsi; this
0x180044a9c  lea     rdx, aFoundDirectory; "Found directory %ls"
0x180044aa3  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180044aa8  test    eax, eax
0x180044aaa  jns     short loc_180044AC7
0x180044aac  mov     rcx, [rbp+238h]; this
0x180044ab3  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\appxalluserst"...
0x180044aba  mov     r9d, eax; char *
0x180044abd  mov     edx, 526h; void *
0x180044ac2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180044ac7  lea     rax, [rsp+330h+var_300]
0x180044acc  mov     byte ptr [rsp+330h+var_300], 0
0x180044ad1  mov     r9, r15
0x180044ad4  mov     qword ptr [rsp+330h+var_310], rax; unsigned __int16
0x180044ad9  lea     r8, [rbp+230h+FindFileData.cFileName]; unsigned __int16 *
0x180044add  mov     rdx, r12; struct AppxAllUserStore::BasicLogFile *
0x180044ae0  mov     rcx, rsi; this
0x180044ae3  call    ?AddPackageFullNameToMainArrayIfNeeded@Internal@AppxAllUserStore@@YAJPEAVBasicLogFile@2@PEBG1AEAV?$Array@GV?$ContainerOperations@GG@Common@@VNoKey@2@V?$ContainerOperations@VNoKey@Common@@G@2@V?$ArrayOperations@GVNoKey@Common@@@2@@Common@@AEA_N@Z; AppxAllUserStore::Internal::AddPackageFullNameToMainArrayIfNeeded(AppxAllUserStore::BasicLogFile *,ushort const *,ushort const *,Common::Array<ushort,Common::ContainerOperations<ushort,ushort>,Common::NoKey,Common::ContainerOperations<Common::NoKey,ushort>,Common::ArrayOperations<ushort,Common::NoKey>> &,bool &)
0x180044ae8  test    rsi, rsi
0x180044aeb  jz      short loc_180044B30
0x180044aed  movzx   ecx, byte ptr [rsp+330h+var_300]
0x180044af2  lea     r8, [rbp+230h+FindFileData.cFileName]
0x180044af6  mov     r9d, [r15+10h]
0x180044afa  lea     rdx, aAddpackagefull; "AddPackageFullNameToMainArrayIfNeeded %"...
0x180044b01  mov     dword ptr [rsp+330h+var_308], eax
0x180044b05  mov     dword ptr [rsp+330h+var_310], ecx; int
0x180044b09  mov     rcx, rsi; this
0x180044b0c  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180044b11  test    eax, eax
0x180044b13  jns     short loc_180044B30
0x180044b15  mov     rcx, [rbp+238h]; this
0x180044b1c  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\appxalluserst"...
0x180044b23  mov     r9d, eax; char *
0x180044b26  mov     edx, 52Ch; void *
0x180044b2b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180044b30  lea     rdx, [rbp+230h+FindFileData]; lpFindFileData
0x180044b34  mov     rcx, rbx; hFindFile
0x180044b37  call    cs:__imp_FindNextFileW
0x180044b3d  test    eax, eax
0x180044b3f  jnz     loc_180044A7D
0x180044b45  call    cs:__imp_GetLastError
0x180044b4b  mov     edi, eax
0x180044b4d  cmp     eax, 12h
0x180044b50  jnz     short loc_180044B69
0x180044b52  mov     rdx, r14
0x180044b55  lea     rcx, [rsp+330h+var_2C8]
0x180044b5a  call    ??4AutoHandleFindFile@Common@@QEAAPEAXPEAX@Z; Common::AutoHandleFindFile::operator=(void *)
0x180044b5f  mov     rbx, [rsp+330h+var_2C8]
0x180044b64  jmp     loc_180044A7D
0x180044b69  test    rsi, rsi
0x180044b6c  jz      short loc_180044BA4
0x180044b6e  mov     r8, [rsp+330h+lpFileName+8]
0x180044b73  lea     rdx, aFindnextfilewL; "FindNextFileW %ls got error %u."
0x180044b7a  mov     r9d, edi
0x180044b7d  mov     rcx, rsi; this
0x180044b80  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180044b85  test    eax, eax
0x180044b87  jns     short loc_180044BA4
0x180044b89  mov     rcx, [rbp+238h]; this
0x180044b90  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\appxalluserst"...
0x180044b97  mov     r9d, eax; char *
0x180044b9a  mov     edx, 534h; void *
0x180044b9f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180044ba4  test    edi, edi
0x180044ba6  jle     short loc_180044BB3
0x180044ba8  movzx   edi, di
0x180044bab  or      edi, 80070000h
0x180044bb1  test    edi, edi
0x180044bb3  jns     short loc_180044BE6
0x180044bb5  mov     edx, 535h; void *
0x180044bba  mov     rax, [rsp+330h+lpFileName+8]
0x180044bbf  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\appxalluserst"...
0x180044bc6  mov     rcx, [rbp+238h]; this
0x180044bcd  mov     r9d, edi; char *
0x180044bd0  mov     [rsp+330h+var_308], rax; char *
0x180044bd5  lea     rax, aLs; "%ls."
0x180044bdc  mov     qword ptr [rsp+330h+var_310], rax; int
0x180044be1  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180044be6  mov     rcx, rbx; this
0x180044be9  call    ?AutoHandleFreeFindFile@Common@@YAXPEAX@Z; Common::AutoHandleFreeFindFile(void *)
0x180044bee  lea     rcx, [rsp+330h+lpFileName]; this
0x180044bf3  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180044bf8  lea     rcx, [rsp+330h+var_2F8]; this
0x180044bfd  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180044c02  mov     ebx, edi
0x180044c04  jmp     short loc_180044C6B
0x180044c06  mov     rcx, r14; this
0x180044c09  call    ?AutoHandleFreeFindFile@Common@@YAXPEAX@Z; Common::AutoHandleFreeFindFile(void *)
0x180044c0e  lea     rcx, [rsp+330h+lpFileName]; this
0x180044c13  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180044c18  lea     rcx, [rsp+330h+var_2F8]; this
0x180044c1d  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180044c22  lea     rcx, [rsp+330h+Src]; this
0x180044c27  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180044c2c  xor     eax, eax
0x180044c2e  jmp     short loc_180044C77
0x180044c30  mov     rcx, [rbp+238h]; this
0x180044c37  lea     rax, aPackagefamilyn_0; "PackageFamilyName invalid: %ls."
0x180044c3e  mov     ebx, 80070057h
0x180044c43  mov     [rsp+330h+var_308], rdi; char *
0x180044c48  mov     r9d, ebx; char *
0x180044c4b  mov     qword ptr [rsp+330h+var_310], rax; int
0x180044c50  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\appxalluserst"...
0x180044c57  mov     edx, 511h; void *
0x180044c5c  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180044c61  lea     rcx, [rsp+330h+var_2F8]; this
0x180044c66  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180044c6b  lea     rcx, [rsp+330h+Src]; this
0x180044c70  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180044c75  mov     eax, ebx
0x180044c77  mov     rcx, [rbp+230h+var_40]
0x180044c7e  xor     rcx, rsp; StackCookie
0x180044c81  call    __security_check_cookie
0x180044c86  add     rsp, 300h
0x180044c8d  pop     r15
0x180044c8f  pop     r14
0x180044c91  pop     r12
  ... truncated ...
```
