# AppxAllUserStore::Internal::AddDeletedAllUserPackagesFolderIfNeeded(AppxAllUserStore::BasicLogFile *,ushort const *,Common::Array<ushort,Common::ContainerOperations<ushort,ushort>,Common::NoKey,Common::ContainerOperations<Common::NoKey,ushort>,Common::ArrayOperations<ushort,Common::NoKey>> &)

- ea: `0x180040ba8`
- end: `0x18004118f`
- name: `?AddDeletedAllUserPackagesFolderIfNeeded@Internal@AppxAllUserStore@@YAJPEAVBasicLogFile@2@PEBGAEAV?$Array@GV?$ContainerOperations@GG@Common@@VNoKey@2@V?$ContainerOperations@VNoKey@Common@@G@2@V?$ArrayOperations@GVNoKey@Common@@@2@@Common@@@Z`
- size: `1511`
- prototype: `__int64 __fastcall(AppxAllUserStore::BasicLogFile *this, AppxAllUserStore *, HANDLE *)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18004252c`

## callees

- `0x180001f94`
- `0x180002200`
- `0x180004920`
- `0x180004b18`
- `0x18000e824`
- `0x180017cd0`
- `0x180017f50`
- `0x180018248`
- `0x18001a6a0`
- `0x18001b3f0`
- `0x18001f21c`
- `0x1800262ec`
- `0x180030d5c`
- `0x180031fe0`
- `0x18003ad58`
- `0x180040ba8`
- `0x1800468a0`
- `0x18004942c`
- `0x18004c98a`
- `0x18004c9d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040e60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040f43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040e60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040f43`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180040e3b`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180040e3b`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180040f39`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180040f39`

## string_xrefs

- `0x180040c70`: `GetSystemSisPath failed, 0x%0x.`
- `0x180040bf3`: `AddDeletedAllUserPackagesFolderIfNeeded %ws.`
- `0x180040c4a`: `GetSisDeletedAllUserPackagesPath failed, 0x%0x.`
- `0x180040cde`: `singleInstanceStoreDeleted: %ws.`
- `0x180040d35`: `DirectoryExists %ws failed, 0x%0x.`
- `0x180040d59`: `Path existence is %u.`

## pseudocode

```c
__int64 __fastcall AppxAllUserStore::Internal::AddDeletedAllUserPackagesFolderIfNeeded(
        AppxAllUserStore::BasicLogFile *this,
        AppxAllUserStore *a2,
        HANDLE *a3)
{
  int v6; // eax
  signed int SystemSisPath; // ebx
  bool *v8; // r8
  unsigned int v9; // esi
  int v10; // eax
  unsigned __int64 v11; // r9
  __int64 v12; // rdx
  int appended; // eax
  int v14; // eax
  int v15; // eax
  char v16; // bl
  int v17; // eax
  const struct _tlgProvider_t *v18; // rax
  __int64 v19; // r8
  __int64 v20; // r9
  int v21; // eax
  Common *FirstFileW; // rax
  Common *v23; // rbx
  DWORD LastError; // eax
  void *v25; // rdx
  int v26; // eax
  bool v27; // sf
  DWORD v28; // eax
  void *v29; // rdx
  signed int v30; // esi
  int v31; // eax
  bool v32; // sf
  const struct _tlgProvider_t *v33; // rax
  __int64 v34; // r8
  __int64 v35; // r9
  int v36; // eax
  int v37; // eax
  int v38; // eax
  __int64 v39; // rcx
  const struct _tlgProvider_t *v40; // rax
  __int64 v41; // r8
  __int64 v42; // r9
  int v43; // eax
  int v45[2]; // [rsp+20h] [rbp-E0h]
  unsigned __int16 v46; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE hFindFile; // [rsp+38h] [rbp-C8h] BYREF
  int v48[2]; // [rsp+40h] [rbp-C0h] BYREF
  Common *v49[2]; // [rsp+48h] [rbp-B8h] BYREF
  int v50; // [rsp+58h] [rbp-A8h]
  LPCWSTR lpFileName[2]; // [rsp+60h] [rbp-A0h] BYREF
  int v52; // [rsp+70h] [rbp-90h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+318h] [rbp+218h]

  if ( this )
  {
    v6 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"AddDeletedAllUserPackagesFolderIfNeeded %ws.", a2);
    if ( v6 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x22B,
        (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
        (const char *)(unsigned int)v6);
  }
  v50 = 0;
  *(_OWORD *)v49 = 0;
  if ( a2 )
  {
    SystemSisPath = AppxAllUserStore::GetSystemSisPath(
                      a2,
                      (Common::Deployment::Configuration *)v49,
                      (struct Common::StringBuffer *)a3);
    if ( SystemSisPath < 0 )
    {
      v9 = 569;
      if ( !this )
        goto LABEL_13;
      v10 = AppxAllUserStore::BasicLogFile::WriteMsg(
              this,
              L"GetSystemSisPath failed, 0x%0x.",
              (unsigned int)SystemSisPath);
LABEL_11:
      if ( v10 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)v9,
          (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
          (const char *)(unsigned int)v10);
      goto LABEL_13;
    }
    appended = Common::PathHelpers::AppendPathSegment(
                 (struct Common::StringBuffer *)v49,
                 (const struct Common::COMMON_STRING *)&qword_18004E760);
    SystemSisPath = appended;
    if ( appended < 0 )
    {
      v11 = (unsigned int)appended;
      v12 = 570;
      goto LABEL_14;
    }
LABEL_17:
    if ( this )
    {
      v14 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"singleInstanceStoreDeleted: %ws.", v49[1]);
      if ( v14 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x23D,
          (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
          (const char *)(unsigned int)v14);
    }
    LOBYTE(v46) = 0;
    v15 = Common::DirectoryExists(v49[1], &v46, v8);
    SystemSisPath = v15;
    if ( v15 < 0 )
    {
      v9 = 579;
      if ( !this )
        goto LABEL_13;
      v10 = AppxAllUserStore::BasicLogFile::WriteMsg(
              this,
              L"DirectoryExists %ws failed, 0x%0x.",
              v49[1],
              (unsigned int)v15);
      goto LABEL_11;
    }
    v16 = v46;
    if ( this )
    {
      v17 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"Path existence is %u.", (unsigned __int8)v46);
      if ( v17 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x245,
          (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
          (const char *)(unsigned int)v17);
    }
    if ( !v16 )
    {
      v18 = AppxAllUserStoreTelemetry::Provider();
      if ( *(_DWORD *)v18 > 5u )
      {
        hFindFile = a3[2];
        *(_QWORD *)v48 = a2;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
          (__int64)v18,
          (__int64)byte_18005D569,
          v19,
          v20,
          (const unsigned __int16 **)v48,
          (__int64)&hFindFile);
      }
      goto LABEL_77;
    }
    v52 = 0;
    *(_OWORD *)lpFileName = 0;
    v21 = Common::PathHelpers::CombinePaths(
            (const struct Common::COMMON_STRING *)v49,
            L"*",
            (struct Common::StringBuffer *)lpFileName);
    SystemSisPath = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x254,
        (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
        (const char *)(unsigned int)v21,
        v45[0]);
LABEL_31:
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpFileName);
      goto LABEL_78;
    }
    memset_0(&FindFileData, 0, sizeof(FindFileData));
    hFindFile = 0;
    FirstFileW = (Common *)FindFirstFileW(lpFileName[1], &FindFileData);
    Common::AutoHandleFindFile::operator=((Common **)&hFindFile, FirstFileW);
    v23 = (Common *)hFindFile;
    if ( hFindFile == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      SystemSisPath = LastError;
      if ( this )
      {
        v26 = AppxAllUserStore::BasicLogFile::WriteMsg(
                this,
                L"FindFirstFileW %ws got error %u, array size %u.",
                lpFileName[1],
                LastError,
                *((_DWORD *)a3 + 4));
        if ( v26 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x25D,
            (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
            (const char *)(unsigned int)v26);
      }
      if ( SystemSisPath != 18 )
      {
        v27 = SystemSisPath < 0;
        if ( SystemSisPath > 0 )
        {
          SystemSisPath = (unsigned __int16)SystemSisPath | 0x80070000;
          v27 = SystemSisPath < 0;
        }
        if ( v27 )
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0x25E,
            (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
            (const char *)(unsigned int)SystemSisPath,
            (int)"%ws.",
            (const char *)lpFileName[1]);
        Common::AutoHandleFreeFindFile((Common *)0xFFFFFFFFFFFFFFFFLL, v25);
        goto LABEL_31;
      }
LABEL_75:
      v39 = -1;
    }
    else
    {
      while ( FindFileData.cFileName[0] == 46
           && (!FindFileData.cFileName[1] || FindFileData.cFileName[1] == 46 && !FindFileData.cFileName[2])
           || (FindFileData.dwFileAttributes & 0x10) == 0 )
      {
        if ( !FindNextFileW(v23, &FindFileData) )
        {
          v28 = GetLastError();
          v30 = v28;
          if ( this )
          {
            v31 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"FindNextFileW %ws got error %u.", lpFileName[1], v28);
            if ( v31 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x27D,
                (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
                (const char *)(unsigned int)v31);
          }
          if ( v30 != 18 )
          {
            v32 = v30 < 0;
            if ( v30 > 0 )
            {
              v30 = (unsigned __int16)v30 | 0x80070000;
              v32 = v30 < 0;
            }
            if ( v32 )
              wil::details::in1diag3::Return_HrMsg(
                retaddr,
                (void *)0x27E,
                (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
                (const char *)(unsigned int)v30,
                (int)"%ws.",
                (const char *)lpFileName[1]);
LABEL_65:
            Common::AutoHandleFreeFindFile(v23, v29);
            Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpFileName);
            SystemSisPath = v30;
            goto LABEL_78;
          }
          Common::AutoHandleFindFile::operator=((Common **)&hFindFile, (Common *)0xFFFFFFFFFFFFFFFFLL);
          v23 = (Common *)hFindFile;
        }
        if ( v23 == (Common *)-1LL )
        {
          v40 = AppxAllUserStoreTelemetry::Provider();
          if ( *(_DWORD *)v40 > 5u )
          {
            *(_QWORD *)v48 = a3[2];
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
              (__int64)v40,
              (__int64)&word_18005D4EE,
              v41,
              v42,
              (__int64)v48);
          }
          if ( this )
          {
            v43 = AppxAllUserStore::BasicLogFile::WriteMsg(
                    this,
                    L"No item found, array size is %u.",
                    *((unsigned int *)a3 + 4));
            if ( v43 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x288,
                (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
                (const char *)(unsigned int)v43);
          }
          goto LABEL_75;
        }
      }
      v33 = AppxAllUserStoreTelemetry::Provider();
      if ( *(_DWORD *)v33 > 5u )
      {
        *(_QWORD *)v48 = FindFileData.cFileName;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (__int64)v33,
          (unsigned __int8 *)&word_18005D536,
          v34,
          v35,
          (const unsigned __int16 **)v48);
      }
      v36 = Common::Array<unsigned short,Common::ContainerOperations<unsigned short,unsigned short>,Common::NoKey,Common::ContainerOperations<Common::NoKey,unsigned short>,Common::ArrayOperations<unsigned short,Common::NoKey>>::Add(
              a3,
              (__int64)v49[1]);
      v30 = v36;
      if ( v36 < 0 )
      {
        if ( this )
        {
          v37 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"Add %ws failed, 0x%0x.", v49[1], (unsigned int)v36);
          if ( v37 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x26D,
              (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
              (const char *)(unsigned int)v37);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x26D,
          (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
          (const char *)(unsigned int)v30,
          v45[0]);
        goto LABEL_65;
      }
      if ( this )
      {
        v45[0] = *((_DWORD *)a3 + 4);
        v38 = AppxAllUserStore::BasicLogFile::WriteMsg(
                this,
                L"Added %ws found under %ws, array size %u.",
                FindFileData.cFileName,
                v49[1],
                *(_QWORD *)v45);
        if ( v38 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x270,
            (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
            (const char *)(unsigned int)v38);
      }
      v49[1] = 0;
      v39 = (__int64)v23;
      LODWORD(v49[0]) = 0;
      v50 = 0;
    }
    Common::AutoHandleFreeFindFile((Common *)v39, v25);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpFileName);
LABEL_77:
    SystemSisPath = 0;
    goto LABEL_78;
  }
  SystemSisPath = Common::Deployment::Configuration::GetSisDeletedAllUserPackagesPath(
                    (Common::Deployment::Configuration *)v49,
                    a2);
  if ( SystemSisPath >= 0 )
    goto LABEL_17;
  v9 = 563;
  if ( this )
  {
    v10 = AppxAllUserStore::BasicLogFile::WriteMsg(
            this,
            L"GetSisDeletedAllUserPackagesPath failed, 0x%0x.",
            (unsigned int)SystemSisPath);
    goto LABEL_11;
  }
LABEL_13:
  v11 = (unsigned int)SystemSisPath;
  v12 = v9;
LABEL_14:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v12,
    (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
    (const char *)v11,
    v45[0]);
LABEL_78:
  Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v49);
  return (unsigned int)SystemSisPath;
}

```

## disassembly

```asm
0x180040ba8  mov     [rsp-8+arg_18], rbx
0x180040bad  push    rbp
0x180040bae  push    rsi
0x180040baf  push    rdi
0x180040bb0  push    r12
0x180040bb2  push    r13
0x180040bb4  push    r14
0x180040bb6  push    r15
0x180040bb8  lea     rbp, [rsp-1E0h]
0x180040bc0  sub     rsp, 2E0h
0x180040bc7  mov     rax, cs:__security_cookie
0x180040bce  xor     rax, rsp
0x180040bd1  mov     [rbp+210h+var_40], rax
0x180040bd8  xor     r15d, r15d
0x180040bdb  lea     r12, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\appxalluserst"...
0x180040be2  mov     r14, r8
0x180040be5  mov     rsi, rdx
0x180040be8  mov     rdi, rcx
0x180040beb  test    rcx, rcx
0x180040bee  jz      short loc_180040C1A
0x180040bf0  mov     r8, rdx
0x180040bf3  lea     rdx, aAdddeletedallu_0; "AddDeletedAllUserPackagesFolderIfNeeded"...
0x180040bfa  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180040bff  test    eax, eax
0x180040c01  jns     short loc_180040C1A
0x180040c03  mov     rcx, [rbp+218h]; this
0x180040c0a  mov     r9d, eax; char *
0x180040c0d  mov     r8, r12; unsigned int
0x180040c10  mov     edx, 22Bh; void *
0x180040c15  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180040c1a  mov     [rsp+310h+var_2B8], r15d
0x180040c1f  xorps   xmm0, xmm0
0x180040c22  movups  xmmword ptr [rsp+310h+var_2C8], xmm0
0x180040c27  test    rsi, rsi
0x180040c2a  jnz     short loc_180040C53
0x180040c2c  lea     rcx, [rsp+310h+var_2C8]; this
0x180040c31  call    ?GetSisDeletedAllUserPackagesPath@Configuration@Deployment@Common@@YAJPEAVStringBuffer@3@@Z; Common::Deployment::Configuration::GetSisDeletedAllUserPackagesPath(Common::StringBuffer *)
0x180040c36  mov     ebx, eax
0x180040c38  test    eax, eax
0x180040c3a  jns     loc_180040CD4
0x180040c40  mov     esi, 233h
0x180040c45  test    rdi, rdi
0x180040c48  jz      short loc_180040C9A
0x180040c4a  lea     rdx, aGetsisdeleteda; "GetSisDeletedAllUserPackagesPath failed"...
0x180040c51  jmp     short loc_180040C77
0x180040c53  lea     rdx, [rsp+310h+var_2C8]; Common::Deployment::Configuration *
0x180040c58  mov     rcx, rsi; this
0x180040c5b  call    ?GetSystemSisPath@AppxAllUserStore@@YAJPEBGAEAVStringBuffer@Common@@@Z; AppxAllUserStore::GetSystemSisPath(ushort const *,Common::StringBuffer &)
0x180040c60  mov     ebx, eax
0x180040c62  test    eax, eax
0x180040c64  jns     short loc_180040CB3
0x180040c66  mov     esi, 239h
0x180040c6b  test    rdi, rdi
0x180040c6e  jz      short loc_180040C9A
0x180040c70  lea     rdx, aGetsystemsispa_0; "GetSystemSisPath failed, 0x%0x."
0x180040c77  mov     r8d, ebx
0x180040c7a  mov     rcx, rdi; this
0x180040c7d  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180040c82  test    eax, eax
0x180040c84  jns     short loc_180040C9A
0x180040c86  mov     rcx, [rbp+218h]; this
0x180040c8d  mov     r9d, eax; char *
0x180040c90  mov     r8, r12; unsigned int
0x180040c93  mov     edx, esi; void *
0x180040c95  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180040c9a  mov     r9d, ebx; char *
0x180040c9d  mov     edx, esi; void *
0x180040c9f  mov     rcx, [rbp+218h]; this
0x180040ca6  mov     r8, r12; unsigned int
0x180040ca9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040cae  jmp     loc_180041159
0x180040cb3  lea     rdx, qword_18004E760; struct Common::COMMON_STRING *
0x180040cba  lea     rcx, [rsp+310h+var_2C8]; struct Common::StringBuffer *
0x180040cbf  call    ?AppendPathSegment@PathHelpers@Common@@SAJPEAVStringBuffer@2@PEBUCOMMON_STRING@2@@Z; Common::PathHelpers::AppendPathSegment(Common::StringBuffer *,Common::COMMON_STRING const *)
0x180040cc4  mov     ebx, eax
0x180040cc6  test    eax, eax
0x180040cc8  jns     short loc_180040CD4
0x180040cca  mov     r9d, eax
0x180040ccd  mov     edx, 23Ah
0x180040cd2  jmp     short loc_180040C9F
0x180040cd4  test    rdi, rdi
0x180040cd7  jz      short loc_180040D08
0x180040cd9  mov     r8, [rsp+310h+var_2C8+8]
0x180040cde  lea     rdx, aSingleinstance; "singleInstanceStoreDeleted: %ws."
0x180040ce5  mov     rcx, rdi; this
0x180040ce8  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180040ced  test    eax, eax
0x180040cef  jns     short loc_180040D08
0x180040cf1  mov     rcx, [rbp+218h]; this
0x180040cf8  mov     r9d, eax; char *
0x180040cfb  mov     r8, r12; unsigned int
0x180040cfe  mov     edx, 23Dh; void *
0x180040d03  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180040d08  mov     rcx, [rsp+310h+var_2C8+8]; this
0x180040d0d  lea     rdx, [rsp+310h+var_2E0]; unsigned __int16 *
0x180040d12  mov     byte ptr [rsp+310h+var_2E0], r15b
0x180040d17  call    ?DirectoryExists@Common@@YAJPEBGPEA_N@Z; Common::DirectoryExists(ushort const *,bool *)
0x180040d1c  mov     ebx, eax
0x180040d1e  test    eax, eax
0x180040d20  jns     short loc_180040D4C
0x180040d22  mov     esi, 243h
0x180040d27  test    rdi, rdi
0x180040d2a  jz      loc_180040C9A
0x180040d30  mov     r8, [rsp+310h+var_2C8+8]
0x180040d35  lea     rdx, aDirectoryexist_0; "DirectoryExists %ws failed, 0x%0x."
0x180040d3c  mov     r9d, eax
0x180040d3f  mov     rcx, rdi; this
0x180040d42  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180040d47  jmp     loc_180040C82
0x180040d4c  movzx   ebx, byte ptr [rsp+310h+var_2E0]
0x180040d51  test    rdi, rdi
0x180040d54  jz      short loc_180040D83
0x180040d56  mov     r8d, ebx
0x180040d59  lea     rdx, aPathExistenceI; "Path existence is %u."
0x180040d60  mov     rcx, rdi; this
0x180040d63  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180040d68  test    eax, eax
0x180040d6a  jns     short loc_180040D83
0x180040d6c  mov     rcx, [rbp+218h]; this
0x180040d73  mov     r9d, eax; char *
0x180040d76  mov     r8, r12; unsigned int
0x180040d79  mov     edx, 245h; void *
0x180040d7e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180040d83  test    bl, bl
0x180040d85  jnz     short loc_180040DCD
0x180040d87  call    ?Provider@AppxAllUserStoreTelemetry@@SAPEBU_tlgProvider_t@@XZ; AppxAllUserStoreTelemetry::Provider(void)
0x180040d8c  mov     ecx, [rax]
0x180040d8e  cmp     ecx, 5
0x180040d91  jbe     loc_180041156
0x180040d97  mov     rcx, [r14+10h]
0x180040d9b  lea     rdx, byte_18005D569
0x180040da2  mov     [rsp+310h+hFindFile], rcx
0x180040da7  lea     rcx, [rsp+310h+hFindFile]
0x180040dac  mov     [rsp+310h+var_2E8], rcx
0x180040db1  lea     rcx, [rsp+310h+var_2D0]
0x180040db6  mov     qword ptr [rsp+310h+var_2F0], rcx
0x180040dbb  mov     rcx, rax
0x180040dbe  mov     qword ptr [rsp+310h+var_2D0], rsi
0x180040dc3  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x180040dc8  jmp     loc_180041156
0x180040dcd  xorps   xmm0, xmm0
0x180040dd0  mov     [rsp+310h+var_2A0], r15d
0x180040dd5  lea     r8, [rsp+310h+lpFileName]; struct Common::StringBuffer *
0x180040dda  lea     rdx, asc_180053710; "*"
0x180040de1  lea     rcx, [rsp+310h+var_2C8]; struct Common::COMMON_STRING *
0x180040de6  movups  xmmword ptr [rsp+310h+lpFileName], xmm0
0x180040deb  call    ?CombinePaths@PathHelpers@Common@@SAJPEBUCOMMON_STRING@2@PEBGPEAVStringBuffer@2@@Z; Common::PathHelpers::CombinePaths(Common::COMMON_STRING const *,ushort const *,Common::StringBuffer *)
0x180040df0  mov     ebx, eax
0x180040df2  test    eax, eax
0x180040df4  jns     short loc_180040E1C
0x180040df6  mov     rcx, [rbp+218h]; this
0x180040dfd  mov     r9d, eax; char *
0x180040e00  mov     r8, r12; unsigned int
0x180040e03  mov     edx, 254h; void *
0x180040e08  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040e0d  lea     rcx, [rsp+310h+lpFileName]; this
0x180040e12  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180040e17  jmp     loc_180041159
0x180040e1c  xor     edx, edx; Val
0x180040e1e  lea     rcx, [rbp+210h+FindFileData]; void *
0x180040e22  mov     r8d, 250h; Size
0x180040e28  call    memset_0
0x180040e2d  mov     rcx, [rsp+310h+lpFileName+8]; lpFileName
0x180040e32  lea     rdx, [rbp+210h+FindFileData]; lpFindFileData
0x180040e36  mov     [rsp+310h+hFindFile], r15
0x180040e3b  call    cs:__imp_FindFirstFileW
0x180040e41  mov     rdx, rax
0x180040e44  lea     rcx, [rsp+310h+hFindFile]
0x180040e49  call    ??4AutoHandleFindFile@Common@@QEAAPEAXPEAX@Z; Common::AutoHandleFindFile::operator=(void *)
0x180040e4e  mov     rbx, [rsp+310h+hFindFile]
0x180040e53  or      r13, 0FFFFFFFFFFFFFFFFh
0x180040e57  cmp     rbx, r13
0x180040e5a  jnz     loc_180040F04
0x180040e60  call    cs:__imp_GetLastError
0x180040e66  mov     ebx, eax
0x180040e68  test    rdi, rdi
0x180040e6b  jz      short loc_180040EA7
0x180040e6d  mov     ecx, [r14+10h]
0x180040e71  lea     rdx, aFindfirstfilew; "FindFirstFileW %ws got error %u, array "...
0x180040e78  mov     r8, [rsp+310h+lpFileName+8]
0x180040e7d  mov     r9d, eax
0x180040e80  mov     [rsp+310h+var_2F0], ecx; int
0x180040e84  mov     rcx, rdi; this
0x180040e87  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180040e8c  test    eax, eax
0x180040e8e  jns     short loc_180040EA7
0x180040e90  mov     rcx, [rbp+218h]; this
0x180040e97  mov     r9d, eax; char *
0x180040e9a  mov     r8, r12; unsigned int
0x180040e9d  mov     edx, 25Dh; void *
0x180040ea2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180040ea7  cmp     ebx, 12h
0x180040eaa  jz      loc_180041144
0x180040eb0  test    ebx, ebx
0x180040eb2  jle     short loc_180040EBF
0x180040eb4  movzx   ebx, bx
0x180040eb7  or      ebx, 80070000h
0x180040ebd  test    ebx, ebx
0x180040ebf  jns     short loc_180040EEE
0x180040ec1  mov     rax, [rsp+310h+lpFileName+8]
0x180040ec6  mov     r9d, ebx; char *
0x180040ec9  mov     rcx, [rbp+218h]; this
0x180040ed0  mov     r8, r12; unsigned int
0x180040ed3  mov     [rsp+310h+var_2E8], rax; char *
0x180040ed8  mov     edx, 25Eh; void *
0x180040edd  lea     rax, aWs; "%ws."
0x180040ee4  mov     qword ptr [rsp+310h+var_2F0], rax; int
0x180040ee9  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180040eee  mov     rcx, r13; this
0x180040ef1  call    ?AutoHandleFreeFindFile@Common@@YAXPEAX@Z; Common::AutoHandleFreeFindFile(void *)
0x180040ef6  jmp     loc_180040E0D
0x180040efb  cmp     rbx, r13
0x180040efe  jz      loc_1800410E3
0x180040f04  cmp     [rbp+210h+FindFileData.cFileName], 2Eh ; '.'
0x180040f09  movzx   eax, [rbp+210h+FindFileData.cFileName+2]
0x180040f0d  jnz     short loc_180040F28
0x180040f0f  test    ax, ax
0x180040f12  jz      short loc_180040F32
0x180040f14  cmp     [rbp+210h+FindFileData.cFileName], 2Eh ; '.'
0x180040f19  jnz     short loc_180040F28
0x180040f1b  cmp     ax, 2Eh ; '.'
0x180040f1f  jnz     short loc_180040F28
0x180040f21  cmp     [rbp+210h+FindFileData.cFileName+4], r15w
0x180040f26  jz      short loc_180040F32
0x180040f28  test    byte ptr [rbp+210h+FindFileData.dwFileAttributes], 10h
0x180040f2c  jnz     loc_180040FE5
0x180040f32  lea     rdx, [rbp+210h+FindFileData]; lpFindFileData
0x180040f36  mov     rcx, rbx; hFindFile
0x180040f39  call    cs:__imp_FindNextFileW
0x180040f3f  test    eax, eax
0x180040f41  jnz     short loc_180040EFB
0x180040f43  call    cs:__imp_GetLastError
0x180040f49  mov     esi, eax
0x180040f4b  test    rdi, rdi
0x180040f4e  jz      short loc_180040F82
0x180040f50  mov     r8, [rsp+310h+lpFileName+8]
0x180040f55  lea     rdx, aFindnextfilewW; "FindNextFileW %ws got error %u."
0x180040f5c  mov     r9d, eax
0x180040f5f  mov     rcx, rdi; this
0x180040f62  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180040f67  test    eax, eax
0x180040f69  jns     short loc_180040F82
0x180040f6b  mov     rcx, [rbp+218h]; this
0x180040f72  mov     r9d, eax; char *
0x180040f75  mov     r8, r12; unsigned int
0x180040f78  mov     edx, 27Dh; void *
0x180040f7d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180040f82  cmp     esi, 12h
0x180040f85  jnz     short loc_180040F9E
0x180040f87  mov     rdx, r13
0x180040f8a  lea     rcx, [rsp+310h+hFindFile]
0x180040f8f  call    ??4AutoHandleFindFile@Common@@QEAAPEAXPEAX@Z; Common::AutoHandleFindFile::operator=(void *)
0x180040f94  mov     rbx, [rsp+310h+hFindFile]
0x180040f99  jmp     loc_180040EFB
0x180040f9e  test    esi, esi
0x180040fa0  jle     short loc_180040FAD
0x180040fa2  movzx   esi, si
0x180040fa5  or      esi, 80070000h
0x180040fab  test    esi, esi
0x180040fad  jns     loc_180041076
0x180040fb3  mov     rax, [rsp+310h+lpFileName+8]
0x180040fb8  mov     r9d, esi; char *
0x180040fbb  mov     rcx, [rbp+218h]; this
0x180040fc2  mov     r8, r12; unsigned int
0x180040fc5  mov     [rsp+310h+var_2E8], rax; char *
0x180040fca  mov     edx, 27Eh; void *
0x180040fcf  lea     rax, aWs; "%ws."
0x180040fd6  mov     qword ptr [rsp+310h+var_2F0], rax; int
0x180040fdb  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180040fe0  jmp     loc_180041076
0x180040fe5  call    ?Provider@AppxAllUserStoreTelemetry@@SAPEBU_tlgProvider_t@@XZ; AppxAllUserStoreTelemetry::Provider(void)
0x180040fea  mov     ecx, [rax]
0x180040fec  cmp     ecx, 5
0x180040fef  jbe     short loc_180041013
0x180040ff1  lea     rcx, [rbp+210h+FindFileData.cFileName]
0x180040ff5  mov     qword ptr [rsp+310h+var_2D0], rcx
0x180040ffa  lea     rdx, word_18005D536
0x180041001  lea     rcx, [rsp+310h+var_2D0]
0x180041006  mov     qword ptr [rsp+310h+var_2F0], rcx; int
0x18004100b  mov     rcx, rax
0x18004100e  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180041013  mov     rdx, [rsp+310h+var_2C8+8]
0x180041018  mov     rcx, r14
0x18004101b  call    ?Add@?$Array@GV?$ContainerOperations@GG@Common@@VNoKey@2@V?$ContainerOperations@VNoKey@Common@@G@2@V?$ArrayOperations@GVNoKey@Common@@@2@@Common@@QEAAJPEAG@Z; Common::Array<ushort,Common::ContainerOperations<ushort,ushort>,Common::NoKey,Common::ContainerOperations<Common::NoKey,ushort>,Common::ArrayOperations<ushort,Common::NoKey>>::Add(ushort *)
0x180041020  mov     esi, eax
0x180041022  test    eax, eax
0x180041024  jns     short loc_18004108F
0x180041026  mov     r14d, 26Dh
0x18004102c  test    rdi, rdi
0x18004102f  jz      short loc_180041061
0x180041031  mov     r8, [rsp+310h+var_2C8+8]
0x180041036  lea     rdx, aAddWsFailed0x0; "Add %ws failed, 0x%0x."
0x18004103d  mov     r9d, eax
0x180041040  mov     rcx, rdi; this
0x180041043  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180041048  test    eax, eax
0x18004104a  jns     short loc_180041061
0x18004104c  mov     rcx, [rbp+218h]; this
0x180041053  mov     r9d, eax; char *
0x180041056  mov     r8, r12; unsigned int
  ... truncated ...
```
