# AppxAllUserStore::Internal::EnumerateDeletedAllUserPackages(AppxAllUserStore::BasicLogFile &,Common::StringBuffer &,Common::Array<ushort,Common::ContainerOperations<ushort,ushort>,Common::NoKey,Common::ContainerOperations<Common::NoKey,ushort>,Common::ArrayOperations<ushort,Common::NoKey>> &)

- ea: `0x180032248`
- end: `0x180032544`
- name: `?EnumerateDeletedAllUserPackages@Internal@AppxAllUserStore@@YAJAEAVBasicLogFile@2@AEAVStringBuffer@Common@@AEAV?$Array@GV?$ContainerOperations@GG@Common@@VNoKey@2@V?$ContainerOperations@VNoKey@Common@@G@2@V?$ArrayOperations@GVNoKey@Common@@@2@@5@@Z`
- size: `764`
- prototype: `__int64 __fastcall(AppxAllUserStore::BasicLogFile *this, __int64, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180033dcc`

## callees

- `0x180004920`
- `0x180008db0`
- `0x180017cd0`
- `0x180017f50`
- `0x18001a6a0`
- `0x18001f21c`
- `0x180030d5c`
- `0x180031fe0`
- `0x180032248`
- `0x18004c98a`
- `0x18004c9d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800322f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032487`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800322f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032487`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800322d6`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800322d6`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180032479`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180032479`

## string_xrefs

- `0x180032285`: `In EnumerateDeletedAllUserPackages %ls.`
- `0x180032344`: `Nothing under the DeleteAllUsersPackage folder.`

## pseudocode

```c
__int64 __fastcall AppxAllUserStore::Internal::EnumerateDeletedAllUserPackages(
        AppxAllUserStore::BasicLogFile *this,
        __int64 a2,
        __int64 a3)
{
  int v6; // eax
  const WCHAR *v7; // rcx
  HANDLE FirstFileW; // rax
  HANDLE v9; // rbx
  signed int LastError; // eax
  void *v11; // rdx
  unsigned int v12; // ebx
  int v13; // eax
  int v15; // eax
  signed int v16; // edi
  const char *v17; // rsi
  signed int v18; // eax
  void *v19; // rdx
  int v20; // [rsp+20h] [rbp-E0h]
  HANDLE hFindFile; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v22; // [rsp+38h] [rbp-C8h] BYREF
  int v23; // [rsp+48h] [rbp-B8h]
  _WIN32_FIND_DATAW FindFileData; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+1E8h]

  v6 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"In EnumerateDeletedAllUserPackages %ls.", *(_QWORD *)(a2 + 8));
  if ( v6 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x81C,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
      (const char *)(unsigned int)v6,
      v20);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v7 = *(const WCHAR **)(a2 + 8);
  hFindFile = 0;
  FirstFileW = FindFirstFileW(v7, &FindFileData);
  Common::AutoHandleFindFile::operator=(&hFindFile, FirstFileW);
  v9 = hFindFile;
  if ( hFindFile == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v12 = LastError;
    if ( LastError == 18 )
    {
      v13 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"Nothing under the DeleteAllUsersPackage folder.");
      if ( v13 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x826,
          (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
          (const char *)(unsigned int)v13,
          v20);
LABEL_11:
      v12 = 0;
    }
    else
    {
      if ( LastError > 0 )
        v12 = (unsigned __int16)LastError | 0x80070000;
      if ( (v12 & 0x80000000) != 0 )
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x825,
          (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
          (const char *)v12,
          (int)"Searching %ls.",
          *(const char **)(a2 + 8));
    }
    Common::AutoHandleFreeFindFile((Common *)0xFFFFFFFFFFFFFFFFLL, v11);
    return v12;
  }
  while ( 1 )
  {
    if ( (FindFileData.cFileName[0] != 46
       || FindFileData.cFileName[1] && (FindFileData.cFileName[1] != 46 || FindFileData.cFileName[2]))
      && (FindFileData.dwFileAttributes & 0x10) != 0 )
    {
      v15 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"Found package %ls.", FindFileData.cFileName);
      if ( v15 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x830,
          (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
          (const char *)(unsigned int)v15,
          v20);
      v23 = 0;
      v22 = 0;
      v16 = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)&v22, FindFileData.cFileName);
      if ( v16 < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x834,
          (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
          (const char *)(unsigned int)v16,
          (int)"Folder %ls.",
          (const char *)FindFileData.cFileName);
        goto LABEL_29;
      }
      v17 = (const char *)*((_QWORD *)&v22 + 1);
      v16 = Common::Array<unsigned short,Common::ContainerOperations<unsigned short,unsigned short>,Common::NoKey,Common::ContainerOperations<Common::NoKey,unsigned short>,Common::ArrayOperations<unsigned short,Common::NoKey>>::Add(
              a3,
              *((_QWORD *)&v22 + 1));
      if ( v16 < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x837,
          (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
          (const char *)(unsigned int)v16,
          (int)"Folder %ls.",
          v17);
LABEL_29:
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v22);
        goto LABEL_34;
      }
      *((_QWORD *)&v22 + 1) = 0;
      LODWORD(v22) = 0;
      v23 = 0;
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v22);
    }
    if ( !FindNextFileW(v9, &FindFileData) )
      break;
LABEL_13:
    if ( v9 == (HANDLE)-1LL )
      goto LABEL_11;
  }
  v18 = GetLastError();
  v16 = v18;
  if ( v18 == 18 )
  {
    Common::AutoHandleFindFile::operator=(&hFindFile, -1);
    v9 = hFindFile;
    goto LABEL_13;
  }
  if ( v18 > 0 )
    v16 = (unsigned __int16)v18 | 0x80070000;
  if ( v16 < 0 )
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x840,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
      (const char *)(unsigned int)v16,
      (int)"Searching %ls.",
      *(const char **)(a2 + 8));
LABEL_34:
  Common::AutoHandleFreeFindFile((Common *)v9, v19);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x180032248  mov     [rsp-8+arg_18], rbx
0x18003224d  push    rbp
0x18003224e  push    rsi
0x18003224f  push    rdi
0x180032250  push    r12
0x180032252  push    r13
0x180032254  push    r14
0x180032256  push    r15
0x180032258  lea     rbp, [rsp-1B0h]
0x180032260  sub     rsp, 2B0h
0x180032267  mov     rax, cs:__security_cookie
0x18003226e  xor     rax, rsp
0x180032271  mov     [rbp+1E0h+var_40], rax
0x180032278  mov     r12, r8
0x18003227b  mov     r15, rdx
0x18003227e  mov     r8, [rdx+8]
0x180032282  mov     r14, rcx
0x180032285  lea     rdx, aInEnumeratedel; "In EnumerateDeletedAllUserPackages %ls."
0x18003228c  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180032291  xor     r13d, r13d
0x180032294  lea     rsi, aOnecoreAdminAp_10; "onecore\\admin\\appmodel\\appxalluserst"...
0x18003229b  test    eax, eax
0x18003229d  jns     short loc_1800322B6
0x18003229f  mov     rcx, [rbp+1E8h]; this
0x1800322a6  mov     r9d, eax; char *
0x1800322a9  mov     r8, rsi; unsigned int
0x1800322ac  mov     edx, 81Ch; void *
0x1800322b1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800322b6  xor     edx, edx; Val
0x1800322b8  lea     rcx, [rsp+2E0h+FindFileData]; void *
0x1800322bd  mov     r8d, 250h; Size
0x1800322c3  call    memset_0
0x1800322c8  mov     rcx, [r15+8]; lpFileName
0x1800322cc  lea     rdx, [rsp+2E0h+FindFileData]; lpFindFileData
0x1800322d1  mov     [rsp+2E0h+hFindFile], r13
0x1800322d6  call    cs:__imp_FindFirstFileW
0x1800322dc  mov     rdx, rax
0x1800322df  lea     rcx, [rsp+2E0h+hFindFile]
0x1800322e4  call    ??4AutoHandleFindFile@Common@@QEAAPEAXPEAX@Z; Common::AutoHandleFindFile::operator=(void *)
0x1800322e9  mov     rbx, [rsp+2E0h+hFindFile]
0x1800322ee  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800322f2  jnz     loc_1800323AC
0x1800322f8  call    cs:__imp_GetLastError
0x1800322fe  mov     ebx, eax
0x180032300  cmp     eax, 12h
0x180032303  jz      short loc_180032344
0x180032305  test    eax, eax
0x180032307  jle     short loc_180032312
0x180032309  movzx   ebx, ax
0x18003230c  or      ebx, 80070000h
0x180032312  test    ebx, ebx
0x180032314  jns     short loc_180032371
0x180032316  mov     rax, [r15+8]
0x18003231a  mov     r9d, ebx; char *
0x18003231d  mov     rcx, [rbp+1E8h]; this
0x180032324  mov     r8, rsi; unsigned int
0x180032327  mov     [rsp+2E0h+var_2B8], rax; char *
0x18003232c  mov     edx, 825h; void *
0x180032331  lea     rax, aSearchingLs; "Searching %ls."
0x180032338  mov     qword ptr [rsp+2E0h+var_2C0], rax; int
0x18003233d  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180032342  jmp     short loc_180032371
0x180032344  lea     rdx, aNothingUnderTh; "Nothing under the DeleteAllUsersPackage"...
0x18003234b  mov     rcx, r14; this
0x18003234e  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180032353  test    eax, eax
0x180032355  jns     short loc_18003236E
0x180032357  mov     rcx, [rbp+1E8h]; this
0x18003235e  mov     r9d, eax; char *
0x180032361  mov     r8, rsi; unsigned int
0x180032364  mov     edx, 826h; void *
0x180032369  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003236e  mov     ebx, r13d
0x180032371  or      rcx, 0FFFFFFFFFFFFFFFFh; this
0x180032375  call    ?AutoHandleFreeFindFile@Common@@YAXPEAX@Z; Common::AutoHandleFreeFindFile(void *)
0x18003237a  mov     eax, ebx
0x18003237c  mov     rcx, [rbp+1E0h+var_40]
0x180032383  xor     rcx, rsp; StackCookie
0x180032386  call    __security_check_cookie
0x18003238b  mov     rbx, [rsp+2E0h+arg_18]
0x180032393  add     rsp, 2B0h
0x18003239a  pop     r15
0x18003239c  pop     r14
0x18003239e  pop     r13
0x1800323a0  pop     r12
0x1800323a2  pop     rdi
0x1800323a3  pop     rsi
0x1800323a4  pop     rbp
0x1800323a5  retn
0x1800323a6  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800323aa  jz      short loc_18003236E
0x1800323ac  cmp     [rsp+2E0h+FindFileData.cFileName], 2Eh ; '.'
0x1800323b2  movzx   eax, [rsp+2E0h+FindFileData.cFileName+2]
0x1800323b7  jnz     short loc_1800323DB
0x1800323b9  test    ax, ax
0x1800323bc  jz      loc_180032471
0x1800323c2  cmp     [rsp+2E0h+FindFileData.cFileName], 2Eh ; '.'
0x1800323c8  jnz     short loc_1800323DB
0x1800323ca  cmp     ax, 2Eh ; '.'
0x1800323ce  jnz     short loc_1800323DB
0x1800323d0  cmp     [rbp+1E0h+FindFileData.cFileName+4], r13w
0x1800323d5  jz      loc_180032471
0x1800323db  test    byte ptr [rsp+2E0h+FindFileData.dwFileAttributes], 10h
0x1800323e0  jz      loc_180032471
0x1800323e6  lea     r8, [rsp+2E0h+FindFileData.cFileName]
0x1800323eb  mov     rcx, r14; this
0x1800323ee  lea     rdx, aFoundPackageLs; "Found package %ls."
0x1800323f5  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x1800323fa  test    eax, eax
0x1800323fc  jns     short loc_180032415
0x1800323fe  mov     rcx, [rbp+1E8h]; this
0x180032405  mov     r9d, eax; char *
0x180032408  mov     r8, rsi; unsigned int
0x18003240b  mov     edx, 830h; void *
0x180032410  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180032415  xorps   xmm0, xmm0
0x180032418  mov     [rsp+2E0h+var_298], r13d
0x18003241d  lea     rdx, [rsp+2E0h+FindFileData.cFileName]; Src
0x180032422  lea     rcx, [rsp+2E0h+var_2A8]; this
0x180032427  movups  [rsp+2E0h+var_2A8], xmm0
0x18003242c  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x180032431  mov     edi, eax
0x180032433  test    eax, eax
0x180032435  js      loc_1800324BF
0x18003243b  mov     rsi, qword ptr [rsp+2E0h+var_2A8+8]
0x180032440  mov     rcx, r12
0x180032443  mov     rdx, rsi
0x180032446  call    ?Add@?$Array@GV?$ContainerOperations@GG@Common@@VNoKey@2@V?$ContainerOperations@VNoKey@Common@@G@2@V?$ArrayOperations@GVNoKey@Common@@@2@@Common@@QEAAJPEAG@Z; Common::Array<ushort,Common::ContainerOperations<ushort,ushort>,Common::NoKey,Common::ContainerOperations<Common::NoKey,ushort>,Common::ArrayOperations<ushort,Common::NoKey>>::Add(ushort *)
0x18003244b  mov     edi, eax
0x18003244d  test    eax, eax
0x18003244f  js      short loc_1800324AC
0x180032451  lea     rcx, [rsp+2E0h+var_2A8]; this
0x180032456  mov     qword ptr [rsp+2E0h+var_2A8+8], r13
0x18003245b  mov     dword ptr [rsp+2E0h+var_2A8], r13d
0x180032460  mov     [rsp+2E0h+var_298], r13d
0x180032465  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18003246a  lea     rsi, aOnecoreAdminAp_10; "onecore\\admin\\appmodel\\appxalluserst"...
0x180032471  lea     rdx, [rsp+2E0h+FindFileData]; lpFindFileData
0x180032476  mov     rcx, rbx; hFindFile
0x180032479  call    cs:__imp_FindNextFileW
0x18003247f  test    eax, eax
0x180032481  jnz     loc_1800323A6
0x180032487  call    cs:__imp_GetLastError
0x18003248d  mov     edi, eax
0x18003248f  cmp     eax, 12h
0x180032492  jnz     short loc_1800324F8
0x180032494  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180032498  lea     rcx, [rsp+2E0h+hFindFile]
0x18003249d  call    ??4AutoHandleFindFile@Common@@QEAAPEAXPEAX@Z; Common::AutoHandleFindFile::operator=(void *)
0x1800324a2  mov     rbx, [rsp+2E0h+hFindFile]
0x1800324a7  jmp     loc_1800323A6
0x1800324ac  mov     [rsp+2E0h+var_2B8], rsi
0x1800324b1  lea     r8, aOnecoreAdminAp_10; "onecore\\admin\\appmodel\\appxalluserst"...
0x1800324b8  mov     edx, 837h
0x1800324bd  jmp     short loc_1800324D1
0x1800324bf  lea     rax, [rsp+2E0h+FindFileData.cFileName]
0x1800324c4  mov     r8, rsi; unsigned int
0x1800324c7  mov     [rsp+2E0h+var_2B8], rax; char *
0x1800324cc  mov     edx, 834h; void *
0x1800324d1  mov     rcx, [rbp+1E8h]; this
0x1800324d8  lea     rax, aFolderLs; "Folder %ls."
0x1800324df  mov     r9d, edi; char *
0x1800324e2  mov     qword ptr [rsp+2E0h+var_2C0], rax; int
0x1800324e7  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800324ec  lea     rcx, [rsp+2E0h+var_2A8]; this
0x1800324f1  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x1800324f6  jmp     short loc_180032535
0x1800324f8  test    eax, eax
0x1800324fa  jle     short loc_180032505
0x1800324fc  movzx   edi, ax
0x1800324ff  or      edi, 80070000h
0x180032505  test    edi, edi
0x180032507  jns     short loc_180032535
0x180032509  mov     rax, [r15+8]
0x18003250d  mov     r9d, edi; char *
0x180032510  mov     rcx, [rbp+1E8h]; this
0x180032517  mov     r8, rsi; unsigned int
0x18003251a  mov     [rsp+2E0h+var_2B8], rax; char *
0x18003251f  mov     edx, 840h; void *
0x180032524  lea     rax, aSearchingLs; "Searching %ls."
0x18003252b  mov     qword ptr [rsp+2E0h+var_2C0], rax; int
0x180032530  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180032535  mov     rcx, rbx; this
0x180032538  call    ?AutoHandleFreeFindFile@Common@@YAXPEAX@Z; Common::AutoHandleFreeFindFile(void *)
0x18003253d  mov     eax, edi
0x18003253f  jmp     loc_18003237C
```
