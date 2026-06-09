# AppxAllUserStore::Internal::ProcessAllFrameworksInSIS(AppxAllUserStore::BasicLogFile *,ushort const *,Common::Array<ushort,Common::ContainerOperations<ushort,ushort>,Common::NoKey,Common::ContainerOperations<Common::NoKey,ushort>,Common::ArrayOperations<ushort,Common::NoKey>> &)

- ea: `0x180043740`
- end: `0x180043b09`
- name: `?ProcessAllFrameworksInSIS@Internal@AppxAllUserStore@@YAJPEAVBasicLogFile@2@PEBGAEAV?$Array@GV?$ContainerOperations@GG@Common@@VNoKey@2@V?$ContainerOperations@VNoKey@Common@@G@2@V?$ArrayOperations@GVNoKey@Common@@@2@@Common@@@Z`
- size: `969`
- prototype: `__int64 __fastcall(AppxAllUserStore::BasicLogFile *this, struct AppxAllUserStore::BasicLogFile *, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18004252c`

## callees

- `0x180004920`
- `0x180017cd0`
- `0x180017f50`
- `0x180018248`
- `0x18001a6a0`
- `0x1800262ec`
- `0x180030d5c`
- `0x180031fe0`
- `0x180041a94`
- `0x180043740`
- `0x1800468a0`
- `0x18004c98a`
- `0x18004c9d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800438b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800439fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800438b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800439fa`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180043893`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180043893`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800439ec`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800439ec`

## string_xrefs

- `0x1800437e3`: `GetSystemSisPath failed, 0x%0x.`
- `0x18004399e`: `Found directory %ws`

## pseudocode

```c
__int64 __fastcall AppxAllUserStore::Internal::ProcessAllFrameworksInSIS(
        AppxAllUserStore::BasicLogFile *this,
        struct AppxAllUserStore::BasicLogFile *a2,
        unsigned int *a3)
{
  int v6; // eax
  int SystemSisPath; // eax
  signed int v8; // edi
  int v9; // eax
  int v10; // eax
  Common *FirstFileW; // rax
  HANDLE v12; // rbx
  DWORD LastError; // eax
  void *v14; // rdx
  signed int v15; // ebx
  int v16; // eax
  bool v17; // sf
  int v18; // eax
  int IsStoreSignedFramework; // eax
  DWORD v20; // eax
  void *v21; // rdx
  int v22; // eax
  bool v23; // sf
  int v25; // [rsp+20h] [rbp-E0h]
  int v26; // [rsp+20h] [rbp-E0h]
  HANDLE hFindFile; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+38h] [rbp-C8h] BYREF
  int v29; // [rsp+48h] [rbp-B8h]
  __int128 v30; // [rsp+50h] [rbp-B0h] BYREF
  int v31; // [rsp+60h] [rbp-A0h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+308h] [rbp+208h]

  if ( this )
  {
    v6 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"ProcessAllFrameworksInSIS %ws. array size %u.", a2, a3[4]);
    if ( v6 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x37F,
        (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
        (const char *)(unsigned int)v6);
  }
  v31 = 0;
  v30 = 0;
  SystemSisPath = AppxAllUserStore::GetSystemSisPath(
                    a2,
                    (Common::Deployment::Configuration *)&v30,
                    (struct Common::StringBuffer *)a3);
  v8 = SystemSisPath;
  if ( SystemSisPath < 0 )
  {
    if ( this )
    {
      v9 = AppxAllUserStore::BasicLogFile::WriteMsg(
             this,
             L"GetSystemSisPath failed, 0x%0x.",
             (unsigned int)SystemSisPath);
      if ( v9 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x383,
          (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
          (const char *)(unsigned int)v9);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x383,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
      (const char *)(unsigned int)v8,
      v25);
    goto LABEL_45;
  }
  v29 = 0;
  *(_OWORD *)lpFileName = 0;
  v10 = Common::PathHelpers::CombinePaths(
          (const unsigned __int16 **)&v30,
          L"*",
          (struct Common::StringBuffer *)lpFileName);
  v8 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x386,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
      (const char *)(unsigned int)v10,
      v25);
    goto LABEL_11;
  }
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  hFindFile = 0;
  FirstFileW = (Common *)FindFirstFileW(lpFileName[1], &FindFileData);
  Common::AutoHandleFindFile::operator=((Common **)&hFindFile, FirstFileW);
  v12 = hFindFile;
  if ( hFindFile == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v15 = LastError;
    if ( this )
    {
      v16 = AppxAllUserStore::BasicLogFile::WriteMsg(
              this,
              L"FindFirstFileW %ws got error %u, array size %u.",
              lpFileName[1],
              LastError,
              a3[4]);
      if ( v16 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x38F,
          (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
          (const char *)(unsigned int)v16);
    }
    if ( v15 == 18 )
    {
LABEL_44:
      Common::AutoHandleFreeFindFile((Common *)0xFFFFFFFFFFFFFFFFLL, v14);
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpFileName);
      v8 = 0;
    }
    else
    {
      v17 = v15 < 0;
      if ( v15 > 0 )
      {
        v15 = (unsigned __int16)v15 | 0x80070000;
        v17 = v15 < 0;
      }
      if ( v17 )
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x390,
          (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
          (const char *)(unsigned int)v15,
          (int)"%ws.",
          (const char *)lpFileName[1]);
      Common::AutoHandleFreeFindFile((Common *)0xFFFFFFFFFFFFFFFFLL, v14);
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpFileName);
      v8 = v15;
    }
    goto LABEL_45;
  }
  while ( 1 )
  {
    if ( (FindFileData.cFileName[0] != 46
       || FindFileData.cFileName[1] && (FindFileData.cFileName[1] != 46 || FindFileData.cFileName[2]))
      && (FindFileData.dwFileAttributes & 0x10) != 0 )
    {
      if ( this )
      {
        v18 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"Found directory %ws", FindFileData.cFileName);
        if ( v18 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x399,
            (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
            (const char *)(unsigned int)v18);
      }
      IsStoreSignedFramework = AppxAllUserStore::Internal::AddPackageToArrayIfIsStoreSignedFramework(
                                 this,
                                 a2,
                                 (const struct Common::COMMON_STRING *)&v30,
                                 FindFileData.cFileName,
                                 (__int64)a3);
      v8 = IsStoreSignedFramework;
      if ( IsStoreSignedFramework < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x39A,
          (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
          (const char *)(unsigned int)IsStoreSignedFramework,
          v26);
        goto LABEL_36;
      }
    }
    if ( !FindNextFileW(v12, &FindFileData) )
      break;
LABEL_22:
    if ( v12 == (HANDLE)-1LL )
      goto LABEL_44;
  }
  v20 = GetLastError();
  v8 = v20;
  if ( v20 == 18 )
  {
    Common::AutoHandleFindFile::operator=((Common **)&hFindFile, (Common *)0xFFFFFFFFFFFFFFFFLL);
    v12 = hFindFile;
    goto LABEL_22;
  }
  if ( this )
  {
    v22 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"FindNextFileW %ws got error %u.", lpFileName[1], v20);
    if ( v22 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x3A2,
        (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
        (const char *)(unsigned int)v22);
  }
  v23 = v8 < 0;
  if ( v8 > 0 )
  {
    v8 = (unsigned __int16)v8 | 0x80070000;
    v23 = v8 < 0;
  }
  if ( v23 )
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x3A3,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
      (const char *)(unsigned int)v8,
      (int)"%ws.",
      (const char *)lpFileName[1]);
LABEL_36:
  Common::AutoHandleFreeFindFile((Common *)v12, v21);
LABEL_11:
  Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpFileName);
LABEL_45:
  Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v30);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180043740  mov     [rsp-8+arg_18], rbx
0x180043745  push    rbp
0x180043746  push    rsi
0x180043747  push    rdi
0x180043748  push    r12
0x18004374a  push    r13
0x18004374c  push    r14
0x18004374e  push    r15
0x180043750  lea     rbp, [rsp-1D0h]
0x180043758  sub     rsp, 2D0h
0x18004375f  mov     rax, cs:__security_cookie
0x180043766  xor     rax, rsp
0x180043769  mov     [rbp+200h+var_40], rax
0x180043770  xor     r12d, r12d
0x180043773  lea     r13, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\appxalluserst"...
0x18004377a  mov     r15, r8
0x18004377d  mov     r14, rdx
0x180043780  mov     rsi, rcx
0x180043783  test    rcx, rcx
0x180043786  jz      short loc_1800437B6
0x180043788  mov     r9d, [r8+10h]
0x18004378c  mov     r8, rdx
0x18004378f  lea     rdx, aProcessallfram_0; "ProcessAllFrameworksInSIS %ws. array si"...
0x180043796  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x18004379b  test    eax, eax
0x18004379d  jns     short loc_1800437B6
0x18004379f  mov     rcx, [rbp+208h]; this
0x1800437a6  mov     r9d, eax; char *
0x1800437a9  mov     r8, r13; unsigned int
0x1800437ac  mov     edx, 37Fh; void *
0x1800437b1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800437b6  xorps   xmm0, xmm0
0x1800437b9  mov     [rsp+300h+var_2A0], r12d
0x1800437be  lea     rdx, [rsp+300h+var_2B0]; Common::Deployment::Configuration *
0x1800437c3  mov     rcx, r14; this
0x1800437c6  movups  [rsp+300h+var_2B0], xmm0
0x1800437cb  call    ?GetSystemSisPath@AppxAllUserStore@@YAJPEBGAEAVStringBuffer@Common@@@Z; AppxAllUserStore::GetSystemSisPath(ushort const *,Common::StringBuffer &)
0x1800437d0  mov     edi, eax
0x1800437d2  test    eax, eax
0x1800437d4  jns     short loc_180043823
0x1800437d6  mov     ebx, 383h
0x1800437db  test    rsi, rsi
0x1800437de  jz      short loc_18004380A
0x1800437e0  mov     r8d, eax
0x1800437e3  lea     rdx, aGetsystemsispa_0; "GetSystemSisPath failed, 0x%0x."
0x1800437ea  mov     rcx, rsi; this
0x1800437ed  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x1800437f2  test    eax, eax
0x1800437f4  jns     short loc_18004380A
0x1800437f6  mov     rcx, [rbp+208h]; this
0x1800437fd  mov     r9d, eax; char *
0x180043800  mov     r8, r13; unsigned int
0x180043803  mov     edx, ebx; void *
0x180043805  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004380a  mov     rcx, [rbp+208h]; this
0x180043811  mov     r9d, edi; char *
0x180043814  mov     r8, r13; unsigned int
0x180043817  mov     edx, ebx; void *
0x180043819  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004381e  jmp     loc_180043AD3
0x180043823  xorps   xmm0, xmm0
0x180043826  mov     [rsp+300h+var_2B8], r12d
0x18004382b  lea     r8, [rsp+300h+lpFileName]; struct Common::StringBuffer *
0x180043830  lea     rdx, asc_180053710; "*"
0x180043837  lea     rcx, [rsp+300h+var_2B0]; struct Common::COMMON_STRING *
0x18004383c  movups  xmmword ptr [rsp+300h+lpFileName], xmm0
0x180043841  call    ?CombinePaths@PathHelpers@Common@@SAJPEBUCOMMON_STRING@2@PEBGPEAVStringBuffer@2@@Z; Common::PathHelpers::CombinePaths(Common::COMMON_STRING const *,ushort const *,Common::StringBuffer *)
0x180043846  mov     edi, eax
0x180043848  test    eax, eax
0x18004384a  jns     short loc_180043872
0x18004384c  mov     rcx, [rbp+208h]; this
0x180043853  mov     r9d, eax; char *
0x180043856  mov     r8, r13; unsigned int
0x180043859  mov     edx, 386h; void *
0x18004385e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043863  lea     rcx, [rsp+300h+lpFileName]; this
0x180043868  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18004386d  jmp     loc_180043AD3
0x180043872  xor     edx, edx; Val
0x180043874  lea     rcx, [rsp+300h+FindFileData]; void *
0x180043879  mov     r8d, 250h; Size
0x18004387f  call    memset_0
0x180043884  mov     rcx, [rsp+300h+lpFileName+8]; lpFileName
0x180043889  lea     rdx, [rsp+300h+FindFileData]; lpFindFileData
0x18004388e  mov     [rsp+300h+hFindFile], r12
0x180043893  call    cs:__imp_FindFirstFileW
0x180043899  mov     rdx, rax
0x18004389c  lea     rcx, [rsp+300h+hFindFile]
0x1800438a1  call    ??4AutoHandleFindFile@Common@@QEAAPEAXPEAX@Z; Common::AutoHandleFindFile::operator=(void *)
0x1800438a6  mov     rbx, [rsp+300h+hFindFile]
0x1800438ab  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800438af  jnz     loc_180043967
0x1800438b5  call    cs:__imp_GetLastError
0x1800438bb  mov     ebx, eax
0x1800438bd  test    rsi, rsi
0x1800438c0  jz      short loc_1800438FC
0x1800438c2  mov     ecx, [r15+10h]
0x1800438c6  lea     rdx, aFindfirstfilew; "FindFirstFileW %ws got error %u, array "...
0x1800438cd  mov     r8, [rsp+300h+lpFileName+8]
0x1800438d2  mov     r9d, eax
0x1800438d5  mov     dword ptr [rsp+300h+var_2E0], ecx; int
0x1800438d9  mov     rcx, rsi; this
0x1800438dc  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x1800438e1  test    eax, eax
0x1800438e3  jns     short loc_1800438FC
0x1800438e5  mov     rcx, [rbp+208h]; this
0x1800438ec  mov     r9d, eax; char *
0x1800438ef  mov     r8, r13; unsigned int
0x1800438f2  mov     edx, 38Fh; void *
0x1800438f7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800438fc  cmp     ebx, 12h
0x1800438ff  jz      loc_180043ABD
0x180043905  test    ebx, ebx
0x180043907  jle     short loc_180043914
0x180043909  movzx   ebx, bx
0x18004390c  or      ebx, 80070000h
0x180043912  test    ebx, ebx
0x180043914  jns     short loc_180043943
0x180043916  mov     rax, [rsp+300h+lpFileName+8]
0x18004391b  mov     r9d, ebx; char *
0x18004391e  mov     rcx, [rbp+208h]; this
0x180043925  mov     r8, r13; unsigned int
0x180043928  mov     [rsp+300h+var_2D8], rax; char *
0x18004392d  mov     edx, 390h; void *
0x180043932  lea     rax, aWs; "%ws."
0x180043939  mov     [rsp+300h+var_2E0], rax; int
0x18004393e  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180043943  or      rcx, 0FFFFFFFFFFFFFFFFh; this
0x180043947  call    ?AutoHandleFreeFindFile@Common@@YAXPEAX@Z; Common::AutoHandleFreeFindFile(void *)
0x18004394c  lea     rcx, [rsp+300h+lpFileName]; this
0x180043951  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180043956  mov     edi, ebx
0x180043958  jmp     loc_180043AD3
0x18004395d  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180043961  jz      loc_180043ABD
0x180043967  cmp     [rbp+200h+FindFileData.cFileName], 2Eh ; '.'
0x18004396c  movzx   eax, [rbp+200h+FindFileData.cFileName+2]
0x180043970  jnz     short loc_18004398B
0x180043972  test    ax, ax
0x180043975  jz      short loc_1800439E4
0x180043977  cmp     [rbp+200h+FindFileData.cFileName], 2Eh ; '.'
0x18004397c  jnz     short loc_18004398B
0x18004397e  cmp     ax, 2Eh ; '.'
0x180043982  jnz     short loc_18004398B
0x180043984  cmp     [rbp+200h+FindFileData.cFileName+4], r12w
0x180043989  jz      short loc_1800439E4
0x18004398b  test    byte ptr [rsp+300h+FindFileData.dwFileAttributes], 10h
0x180043990  jz      short loc_1800439E4
0x180043992  test    rsi, rsi
0x180043995  jz      short loc_1800439C5
0x180043997  lea     r8, [rbp+200h+FindFileData.cFileName]
0x18004399b  mov     rcx, rsi; this
0x18004399e  lea     rdx, aFoundDirectory_0; "Found directory %ws"
0x1800439a5  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x1800439aa  test    eax, eax
0x1800439ac  jns     short loc_1800439C5
0x1800439ae  mov     rcx, [rbp+208h]; this
0x1800439b5  mov     r9d, eax; char *
0x1800439b8  mov     r8, r13; unsigned int
0x1800439bb  mov     edx, 399h; void *
0x1800439c0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800439c5  lea     r9, [rbp+200h+FindFileData.cFileName]
0x1800439c9  mov     [rsp+300h+var_2E0], r15; int
0x1800439ce  lea     r8, [rsp+300h+var_2B0]
0x1800439d3  mov     rdx, r14; struct AppxAllUserStore::BasicLogFile *
0x1800439d6  mov     rcx, rsi; this
0x1800439d9  call    ?AddPackageToArrayIfIsStoreSignedFramework@Internal@AppxAllUserStore@@YAJPEAVBasicLogFile@2@PEBGAEAVStringBuffer@Common@@1AEAV?$Array@GV?$ContainerOperations@GG@Common@@VNoKey@2@V?$ContainerOperations@VNoKey@Common@@G@2@V?$ArrayOperations@GVNoKey@Common@@@2@@5@@Z; AppxAllUserStore::Internal::AddPackageToArrayIfIsStoreSignedFramework(AppxAllUserStore::BasicLogFile *,ushort const *,Common::StringBuffer &,ushort const *,Common::Array<ushort,Common::ContainerOperations<ushort,ushort>,Common::NoKey,Common::ContainerOperations<Common::NoKey,ushort>,Common::ArrayOperations<ushort,Common::NoKey>> &)
0x1800439de  mov     edi, eax
0x1800439e0  test    eax, eax
0x1800439e2  js      short loc_180043A1F
0x1800439e4  lea     rdx, [rsp+300h+FindFileData]; lpFindFileData
0x1800439e9  mov     rcx, rbx; hFindFile
0x1800439ec  call    cs:__imp_FindNextFileW
0x1800439f2  test    eax, eax
0x1800439f4  jnz     loc_18004395D
0x1800439fa  call    cs:__imp_GetLastError
0x180043a00  mov     edi, eax
0x180043a02  cmp     eax, 12h
0x180043a05  jnz     short loc_180043A43
0x180043a07  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180043a0b  lea     rcx, [rsp+300h+hFindFile]
0x180043a10  call    ??4AutoHandleFindFile@Common@@QEAAPEAXPEAX@Z; Common::AutoHandleFindFile::operator=(void *)
0x180043a15  mov     rbx, [rsp+300h+hFindFile]
0x180043a1a  jmp     loc_18004395D
0x180043a1f  mov     rcx, [rbp+208h]; this
0x180043a26  mov     r9d, eax; char *
0x180043a29  mov     r8, r13; unsigned int
0x180043a2c  mov     edx, 39Ah; void *
0x180043a31  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043a36  mov     rcx, rbx; this
0x180043a39  call    ?AutoHandleFreeFindFile@Common@@YAXPEAX@Z; Common::AutoHandleFreeFindFile(void *)
0x180043a3e  jmp     loc_180043863
0x180043a43  test    rsi, rsi
0x180043a46  jz      short loc_180043A7A
0x180043a48  mov     r8, [rsp+300h+lpFileName+8]
0x180043a4d  lea     rdx, aFindnextfilewW; "FindNextFileW %ws got error %u."
0x180043a54  mov     r9d, edi
0x180043a57  mov     rcx, rsi; this
0x180043a5a  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180043a5f  test    eax, eax
0x180043a61  jns     short loc_180043A7A
0x180043a63  mov     rcx, [rbp+208h]; this
0x180043a6a  mov     r9d, eax; char *
0x180043a6d  mov     r8, r13; unsigned int
0x180043a70  mov     edx, 3A2h; void *
0x180043a75  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180043a7a  test    edi, edi
0x180043a7c  jle     short loc_180043A89
0x180043a7e  movzx   edi, di
0x180043a81  or      edi, 80070000h
0x180043a87  test    edi, edi
0x180043a89  jns     short loc_180043A36
0x180043a8b  mov     rax, [rsp+300h+lpFileName+8]
0x180043a90  mov     r9d, edi; char *
0x180043a93  mov     rcx, [rbp+208h]; this
0x180043a9a  mov     r8, r13; unsigned int
0x180043a9d  mov     [rsp+300h+var_2D8], rax; char *
0x180043aa2  mov     edx, 3A3h; void *
0x180043aa7  lea     rax, aWs; "%ws."
0x180043aae  mov     [rsp+300h+var_2E0], rax; int
0x180043ab3  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180043ab8  jmp     loc_180043A36
0x180043abd  or      rcx, 0FFFFFFFFFFFFFFFFh; this
0x180043ac1  call    ?AutoHandleFreeFindFile@Common@@YAXPEAX@Z; Common::AutoHandleFreeFindFile(void *)
0x180043ac6  lea     rcx, [rsp+300h+lpFileName]; this
0x180043acb  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180043ad0  mov     edi, r12d
0x180043ad3  lea     rcx, [rsp+300h+var_2B0]; this
0x180043ad8  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180043add  mov     eax, edi
0x180043adf  mov     rcx, [rbp+200h+var_40]
0x180043ae6  xor     rcx, rsp; StackCookie
0x180043ae9  call    __security_check_cookie
0x180043aee  mov     rbx, [rsp+300h+arg_18]
0x180043af6  add     rsp, 2D0h
0x180043afd  pop     r15
0x180043aff  pop     r14
0x180043b01  pop     r13
0x180043b03  pop     r12
0x180043b05  pop     rdi
0x180043b06  pop     rsi
0x180043b07  pop     rbp
0x180043b08  retn
```
