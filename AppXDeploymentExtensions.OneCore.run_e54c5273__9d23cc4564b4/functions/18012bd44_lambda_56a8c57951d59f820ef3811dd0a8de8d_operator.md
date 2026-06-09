# _lambda_56a8c57951d59f820ef3811dd0a8de8d_::operator()

- ea: `0x18012bd44`
- end: `0x18012c0ed`
- name: `_lambda_56a8c57951d59f820ef3811dd0a8de8d_::operator()`
- size: `937`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18012cea0`

## callees

- `0x180012964`
- `0x18001c4fc`
- `0x1800a8f80`
- `0x1800aa988`
- `0x1800ac484`
- `0x1800ac630`
- `0x1800dc344`
- `0x18012bd44`
- `0x18012d01c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012bd62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012bf1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012bf92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012bd62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012bf1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012bf92`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18012bf55`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18012bf55`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18012bf6c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18012bf6c`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18012bfc1`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18012bfc1`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18012bd58`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18012bd58`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18012bdf9`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18012bdf9`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18012bf0c`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18012bf88`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18012bf0c`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18012bf88`

## string_xrefs

- `0x18012bd83`: `CreateDirectory`
- `0x18012c00f`: `Remove %ws %ws %ws`
- `0x18012c0de`: `CreateFullFileName %ws %ws from`
- `0x18012c0a3`: `CreateFullFileName %ws %ws to`
- `0x18012c069`: `MoveFileEx %ws src %ws dest %ws file %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall lambda_56a8c57951d59f820ef3811dd0a8de8d_::operator()(__int64 a1)
{
  signed int LastError; // eax
  signed int LastErrorMsg; // ebx
  const char *v4; // rax
  __int64 v5; // rdx
  HANDLE FirstFileW; // rbx
  void *v8; // rdx
  struct Common::StringBuffer *v9; // r9
  int FullFileName; // esi
  struct Common::StringBuffer *v11; // r9
  _BYTE *v12; // rax
  signed int v13; // eax
  int v14; // ebp
  signed int v15; // eax
  void *v16; // rdx
  char *v17; // [rsp+28h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  if ( !CreateDirectoryW(**(LPCWSTR **)a1, 0) )
  {
    LastError = GetLastError();
    LastErrorMsg = LastError;
    if ( LastError > 0 )
      LastErrorMsg = (unsigned __int16)LastError | 0x80070000;
    if ( LastErrorMsg != -2147024713 && LastErrorMsg < 0 )
    {
      v4 = "CreateDirectory";
      v5 = 591;
LABEL_7:
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)v5,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\applydata\\applydata.cpp",
        (const char *)(unsigned int)LastErrorMsg,
        (int)v4,
        v17);
      return (unsigned int)LastErrorMsg;
    }
  }
  LastErrorMsg = StringCchPrintfW(**(wchar_t ***)(a1 + 8), 0x104u, L"%s%s", **(_QWORD **)(a1 + 16), L"\\*");
  if ( LastErrorMsg < 0 )
  {
    v4 = "StringCchPrintf";
    v5 = 596;
    goto LABEL_7;
  }
  FirstFileW = FindFirstFileW(**(LPCWSTR **)(a1 + 8), *(LPWIN32_FIND_DATAW *)(a1 + 24));
  if ( FirstFileW == (HANDLE)-1LL )
  {
    LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                     retaddr,
                     (void *)0x257,
                     (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\applydata\\applydata.cpp",
                     "FindFirstFile %ws",
                     **(const char ***)(a1 + 8));
    Common::AutoHandleFreeFindFile((Common *)0xFFFFFFFFFFFFFFFFLL, v8);
    return (unsigned int)LastErrorMsg;
  }
  while ( 1 )
  {
    if ( !OSIntegration::DEH::ApplyData::ExtensionHandler::ShouldMoveForDeletion(
            *(OSIntegration::DEH::ApplyData::ExtensionHandler **)(a1 + 32),
            (const unsigned __int16 *)(*(_QWORD *)(a1 + 24) + 44LL)) )
      goto LABEL_33;
    FullFileName = DirectoryPaths::CreateFullFileName(
                     **(DirectoryPaths ***)(a1 + 16),
                     (const unsigned __int16 *)(*(_QWORD *)(a1 + 24) + 44LL),
                     *(const unsigned __int16 **)(a1 + 40),
                     v9);
    if ( FullFileName < 0 )
      break;
    FullFileName = DirectoryPaths::CreateFullFileName(
                     **(DirectoryPaths ***)a1,
                     (const unsigned __int16 *)(*(_QWORD *)(a1 + 24) + 44LL),
                     *(const unsigned __int16 **)(a1 + 48),
                     v11);
    v12 = *(_BYTE **)(a1 + 24);
    if ( FullFileName < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x261,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\applydata\\applydata.cpp",
        (const char *)(unsigned int)FullFileName,
        (int)"CreateFullFileName %ws %ws to",
        **(const char ***)(a1 + 8),
        v12 + 44);
      goto LABEL_35;
    }
    if ( (*v12 & 0x10) != 0 )
    {
      FullFileName = Common::Deployment::MountedFolder::Remove(*(LPCWSTR *)(*(_QWORD *)(a1 + 48) + 8LL), 0);
      if ( FullFileName == -2147024809 )
        FullFileName = RemoveDirectoryTree(*(unsigned __int16 **)(*(_QWORD *)(a1 + 48) + 8LL), 0);
      if ( (unsigned int)(FullFileName + 2147024894) > 1 && FullFileName < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x271,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\applydata\\applydata.cpp",
          (const char *)(unsigned int)FullFileName,
          (int)"Remove %ws %ws %ws",
          **(const char ***)(a1 + 8),
          *(_QWORD *)(*(_QWORD *)(a1 + 48) + 8LL),
          *(_QWORD *)(a1 + 24) + 44LL);
        goto LABEL_35;
      }
    }
    if ( !MoveFileExW(*(LPCWSTR *)(*(_QWORD *)(a1 + 40) + 8LL), *(LPCWSTR *)(*(_QWORD *)(a1 + 48) + 8LL), 9u) )
    {
      v13 = GetLastError();
      FullFileName = v13;
      if ( v13 > 0 )
        FullFileName = (unsigned __int16)v13 | 0x80070000;
      if ( FullFileName == -2147024891 )
      {
        if ( CompareStringOrdinal((LPCWCH)(*(_QWORD *)(a1 + 24) + 44LL), -1, L"AC", -1, 1) != 2 )
          goto LABEL_37;
        v14 = 1;
        while ( 1 )
        {
          Sleep(0x1F4u);
          if ( MoveFileExW(*(LPCWSTR *)(*(_QWORD *)(a1 + 40) + 8LL), *(LPCWSTR *)(*(_QWORD *)(a1 + 48) + 8LL), 9u) )
            break;
          v15 = GetLastError();
          FullFileName = v15;
          if ( v15 > 0 )
            FullFileName = (unsigned __int16)v15 | 0x80070000;
          if ( FullFileName == -2147024891 && (unsigned int)++v14 < 0x28 )
            continue;
          goto LABEL_32;
        }
      }
      else
      {
LABEL_32:
        if ( FullFileName < 0 )
        {
LABEL_37:
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0x28F,
            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\applydata\\applydata.cpp",
            (const char *)(unsigned int)FullFileName,
            (int)"MoveFileEx %ws src %ws dest %ws file %ws",
            **(const char ***)(a1 + 8),
            *(_QWORD *)(*(_QWORD *)(a1 + 40) + 8LL),
            *(_QWORD *)(*(_QWORD *)(a1 + 48) + 8LL),
            *(_QWORD *)(a1 + 24) + 44LL);
          goto LABEL_35;
        }
      }
    }
LABEL_33:
    if ( !FindNextFileW(FirstFileW, *(LPWIN32_FIND_DATAW *)(a1 + 24)) )
    {
      FullFileName = 0;
      goto LABEL_35;
    }
  }
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    (void *)0x25F,
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\applydata\\applydata.cpp",
    (const char *)(unsigned int)FullFileName,
    (int)"CreateFullFileName %ws %ws from",
    **(const char ***)(a1 + 8),
    *(_QWORD *)(a1 + 24) + 44LL);
LABEL_35:
  Common::AutoHandleFreeFindFile((Common *)FirstFileW, v16);
  return (unsigned int)FullFileName;
}

```

## disassembly

```asm
0x18012bd44  push    rbx
0x18012bd46  push    rbp
0x18012bd47  push    rsi
0x18012bd48  push    rdi
0x18012bd49  sub     rsp, 58h
0x18012bd4d  mov     rdi, rcx
0x18012bd50  mov     rcx, [rcx]
0x18012bd53  xor     edx, edx; lpSecurityAttributes
0x18012bd55  mov     rcx, [rcx]; lpPathName
0x18012bd58  call    cs:__imp_CreateDirectoryW
0x18012bd5e  test    eax, eax
0x18012bd60  jnz     short loc_18012BDAF
0x18012bd62  call    cs:__imp_GetLastError
0x18012bd68  mov     ebx, eax
0x18012bd6a  test    eax, eax
0x18012bd6c  jle     short loc_18012BD77
0x18012bd6e  movzx   ebx, ax
0x18012bd71  or      ebx, 80070000h
0x18012bd77  cmp     ebx, 800700B7h
0x18012bd7d  jz      short loc_18012BDAF
0x18012bd7f  test    ebx, ebx
0x18012bd81  jns     short loc_18012BDAF
0x18012bd83  lea     rax, aCreatedirector_5; "CreateDirectory"
0x18012bd8a  mov     edx, 24Fh; void *
0x18012bd8f  lea     r8, aOnecoreAdminAp_22; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18012bd96  mov     r9d, ebx; char *
0x18012bd99  mov     qword ptr [rsp+78h+bIgnoreCase], rax; int
0x18012bd9e  mov     rcx, [rsp+78h]; this
0x18012bda3  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18012bda8  mov     eax, ebx
0x18012bdaa  jmp     loc_18012BFDB
0x18012bdaf  mov     r9, [rdi+10h]
0x18012bdb3  mov     rcx, [rdi+8]
0x18012bdb7  lea     rax, asc_180244A20; "\\*"
0x18012bdbe  mov     qword ptr [rsp+78h+bIgnoreCase], rax
0x18012bdc3  mov     r9, [r9]
0x18012bdc6  lea     r8, aSS_0; "%s%s"
0x18012bdcd  mov     edx, 104h; unsigned __int64
0x18012bdd2  mov     rcx, [rcx]; Buffer
0x18012bdd5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18012bdda  mov     ebx, eax
0x18012bddc  test    eax, eax
0x18012bdde  jns     short loc_18012BDEE
0x18012bde0  lea     rax, aStringcchprint_33; "StringCchPrintf"
0x18012bde7  mov     edx, 254h
0x18012bdec  jmp     short loc_18012BD8F
0x18012bdee  mov     rcx, [rdi+8]
0x18012bdf2  mov     rdx, [rdi+18h]; lpFindFileData
0x18012bdf6  mov     rcx, [rcx]; lpFileName
0x18012bdf9  call    cs:__imp_FindFirstFileW
0x18012bdff  mov     rbx, rax
0x18012be02  mov     [rsp+78h+arg_0], rax
0x18012be0a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18012be0e  jnz     short loc_18012BE49
0x18012be10  mov     rax, [rdi+8]
0x18012be14  mov     rcx, [rsp+78h]; this
0x18012be19  mov     rax, [rax]
0x18012be1c  mov     qword ptr [rsp+78h+bIgnoreCase], rax; char *
0x18012be21  lea     r9, aFindfirstfileW; "FindFirstFile %ws"
0x18012be28  lea     r8, aOnecoreAdminAp_22; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18012be2f  mov     edx, 257h; void *
0x18012be34  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x18012be39  mov     ebx, eax
0x18012be3b  or      rcx, 0FFFFFFFFFFFFFFFFh; this
0x18012be3f  call    ?AutoHandleFreeFindFile@Common@@YAXPEAX@Z; Common::AutoHandleFreeFindFile(void *)
0x18012be44  jmp     loc_18012BDA8
0x18012be49  mov     rdx, [rdi+18h]
0x18012be4d  add     rdx, 2Ch ; ','; unsigned __int16 *
0x18012be51  mov     rcx, [rdi+20h]; this
0x18012be55  call    ?ShouldMoveForDeletion@ExtensionHandler@ApplyData@DEH@OSIntegration@@AEAA_NPEBG@Z; OSIntegration::DEH::ApplyData::ExtensionHandler::ShouldMoveForDeletion(ushort const *)
0x18012be5a  test    al, al
0x18012be5c  jz      loc_18012BFBA
0x18012be62  mov     rdx, [rdi+18h]
0x18012be66  add     rdx, 2Ch ; ','; unsigned __int16 *
0x18012be6a  mov     rcx, [rdi+10h]
0x18012be6e  mov     r8, [rdi+28h]; unsigned __int16 *
0x18012be72  mov     rcx, [rcx]; this
0x18012be75  call    ?CreateFullFileName@DirectoryPaths@@YAJPEBG0PEAVStringBuffer@Common@@@Z; DirectoryPaths::CreateFullFileName(ushort const *,ushort const *,Common::StringBuffer *)
0x18012be7a  mov     esi, eax
0x18012be7c  mov     rdx, [rdi+18h]
0x18012be80  add     rdx, 2Ch ; ','; unsigned __int16 *
0x18012be84  test    eax, eax
0x18012be86  js      loc_18012C0CD
0x18012be8c  mov     rcx, [rdi]
0x18012be8f  mov     r8, [rdi+30h]; unsigned __int16 *
0x18012be93  mov     rcx, [rcx]; this
0x18012be96  call    ?CreateFullFileName@DirectoryPaths@@YAJPEBG0PEAVStringBuffer@Common@@@Z; DirectoryPaths::CreateFullFileName(ushort const *,ushort const *,Common::StringBuffer *)
0x18012be9b  mov     esi, eax
0x18012be9d  mov     rax, [rdi+18h]
0x18012bea1  test    esi, esi
0x18012bea3  js      loc_18012C08E
0x18012bea9  test    byte ptr [rax], 10h
0x18012beac  jz      short loc_18012BEF6
0x18012beae  mov     rcx, [rdi+30h]
0x18012beb2  xor     edx, edx; unsigned __int16 *
0x18012beb4  mov     rcx, [rcx+8]; lpPathName
0x18012beb8  call    ?Remove@MountedFolder@Deployment@Common@@SAJPEBG0@Z; Common::Deployment::MountedFolder::Remove(ushort const *,ushort const *)
0x18012bebd  mov     esi, eax
0x18012bebf  cmp     eax, 80070057h
0x18012bec4  jnz     short loc_18012BEE3
0x18012bec6  mov     rcx, [rdi+30h]
0x18012beca  mov     qword ptr [rsp+78h+bIgnoreCase], 0; __int64
0x18012bed3  xor     r9d, r9d
0x18012bed6  xor     edx, edx
0x18012bed8  mov     rcx, [rcx+8]; unsigned __int16 *
0x18012bedc  call    RemoveDirectoryTree
0x18012bee1  mov     esi, eax
0x18012bee3  lea     eax, [rsi+7FF8FFFEh]
0x18012bee9  cmp     eax, 1
0x18012beec  jbe     short loc_18012BEF6
0x18012beee  test    esi, esi
0x18012bef0  js      loc_18012BFE4
0x18012bef6  mov     rdx, [rdi+30h]
0x18012befa  mov     rcx, [rdi+28h]
0x18012befe  mov     r8d, 9; dwFlags
0x18012bf04  mov     rdx, [rdx+8]; lpNewFileName
0x18012bf08  mov     rcx, [rcx+8]; lpExistingFileName
0x18012bf0c  call    cs:__imp_MoveFileExW
0x18012bf12  test    eax, eax
0x18012bf14  jnz     loc_18012BFBA
0x18012bf1a  call    cs:__imp_GetLastError
0x18012bf20  mov     esi, eax
0x18012bf22  test    eax, eax
0x18012bf24  jle     short loc_18012BF2F
0x18012bf26  movzx   esi, ax
0x18012bf29  or      esi, 80070000h
0x18012bf2f  cmp     esi, 80070005h
0x18012bf35  jnz     short loc_18012BFB6
0x18012bf37  mov     rcx, [rdi+18h]
0x18012bf3b  add     rcx, 2Ch ; ','; lpString1
0x18012bf3f  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x18012bf47  or      r9d, 0FFFFFFFFh; cchCount2
0x18012bf4b  lea     r8, aAc_1; "AC"
0x18012bf52  or      edx, r9d; cchCount1
0x18012bf55  call    cs:__imp_CompareStringOrdinal
0x18012bf5b  cmp     eax, 2
0x18012bf5e  jnz     loc_18012C031
0x18012bf64  lea     ebp, [rax-1]
0x18012bf67  mov     ecx, 1F4h; dwMilliseconds
0x18012bf6c  call    cs:__imp_Sleep
0x18012bf72  mov     rdx, [rdi+30h]
0x18012bf76  mov     rcx, [rdi+28h]
0x18012bf7a  mov     r8d, 9; dwFlags
0x18012bf80  mov     rdx, [rdx+8]; lpNewFileName
0x18012bf84  mov     rcx, [rcx+8]; lpExistingFileName
0x18012bf88  call    cs:__imp_MoveFileExW
0x18012bf8e  test    eax, eax
0x18012bf90  jnz     short loc_18012BFBA
0x18012bf92  call    cs:__imp_GetLastError
0x18012bf98  mov     esi, eax
0x18012bf9a  test    eax, eax
0x18012bf9c  jle     short loc_18012BFA7
0x18012bf9e  movzx   esi, ax
0x18012bfa1  or      esi, 80070000h
0x18012bfa7  cmp     esi, 80070005h
0x18012bfad  jnz     short loc_18012BFB6
0x18012bfaf  inc     ebp
0x18012bfb1  cmp     ebp, 28h ; '('
0x18012bfb4  jb      short loc_18012BF67
0x18012bfb6  test    esi, esi
0x18012bfb8  js      short loc_18012C031
0x18012bfba  mov     rdx, [rdi+18h]; lpFindFileData
0x18012bfbe  mov     rcx, rbx; hFindFile
0x18012bfc1  call    cs:__imp_FindNextFileW
0x18012bfc7  test    eax, eax
0x18012bfc9  jnz     loc_18012BE49
0x18012bfcf  xor     esi, esi
0x18012bfd1  mov     rcx, rbx; this
0x18012bfd4  call    ?AutoHandleFreeFindFile@Common@@YAXPEAX@Z; Common::AutoHandleFreeFindFile(void *)
0x18012bfd9  mov     eax, esi
0x18012bfdb  add     rsp, 58h
0x18012bfdf  pop     rdi
0x18012bfe0  pop     rsi
0x18012bfe1  pop     rbp
0x18012bfe2  pop     rbx
0x18012bfe3  retn
0x18012bfe4  mov     rdx, [rdi+18h]
0x18012bfe8  add     rdx, 2Ch ; ','
0x18012bfec  mov     rax, [rdi+30h]
0x18012bff0  mov     r8, [rdi+8]
0x18012bff4  mov     rcx, [rsp+78h]; this
0x18012bff9  mov     [rsp+78h+var_40], rdx
0x18012bffe  mov     rax, [rax+8]
0x18012c002  mov     [rsp+78h+var_48], rax
0x18012c007  mov     rax, [r8]
0x18012c00a  mov     [rsp+78h+var_50], rax; char *
0x18012c00f  lea     rax, aRemoveWsWsWs; "Remove %ws %ws %ws"
0x18012c016  mov     qword ptr [rsp+78h+bIgnoreCase], rax; int
0x18012c01b  mov     r9d, esi; char *
0x18012c01e  lea     r8, aOnecoreAdminAp_22; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18012c025  mov     edx, 271h; void *
0x18012c02a  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18012c02f  jmp     short loc_18012BFD1
0x18012c031  mov     rdx, [rdi+18h]
0x18012c035  add     rdx, 2Ch ; ','
0x18012c039  mov     rax, [rdi+30h]
0x18012c03d  mov     r8, [rdi+28h]
0x18012c041  mov     r9, [rdi+8]
0x18012c045  mov     rcx, [rsp+78h]; this
0x18012c04a  mov     [rsp+78h+var_38], rdx
0x18012c04f  mov     rax, [rax+8]
0x18012c053  mov     [rsp+78h+var_40], rax
0x18012c058  mov     rax, [r8+8]
0x18012c05c  mov     [rsp+78h+var_48], rax
0x18012c061  mov     rax, [r9]
0x18012c064  mov     [rsp+78h+var_50], rax; char *
0x18012c069  lea     rax, aMovefileexWsSr; "MoveFileEx %ws src %ws dest %ws file %w"...
0x18012c070  mov     qword ptr [rsp+78h+bIgnoreCase], rax; int
0x18012c075  mov     r9d, esi; char *
0x18012c078  lea     r8, aOnecoreAdminAp_22; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18012c07f  mov     edx, 28Fh; void *
0x18012c084  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18012c089  jmp     loc_18012BFD1
0x18012c08e  add     rax, 2Ch ; ','
0x18012c092  mov     rdx, [rdi+8]
0x18012c096  mov     [rsp+78h+var_48], rax
0x18012c09b  mov     rax, [rdx]
0x18012c09e  mov     [rsp+78h+var_50], rax; char *
0x18012c0a3  lea     rax, aCreatefullfile_2; "CreateFullFileName %ws %ws to"
0x18012c0aa  mov     edx, 261h; void *
0x18012c0af  lea     r8, aOnecoreAdminAp_22; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18012c0b6  mov     r9d, esi; char *
0x18012c0b9  mov     qword ptr [rsp+78h+bIgnoreCase], rax; int
0x18012c0be  mov     rcx, [rsp+78h]; this
0x18012c0c3  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18012c0c8  jmp     loc_18012BFD1
0x18012c0cd  mov     rax, [rdi+8]
0x18012c0d1  mov     [rsp+78h+var_48], rdx
0x18012c0d6  mov     rax, [rax]
0x18012c0d9  mov     [rsp+78h+var_50], rax
0x18012c0de  lea     rax, aCreatefullfile; "CreateFullFileName %ws %ws from"
0x18012c0e5  mov     edx, 25Fh
0x18012c0ea  jmp     short loc_18012C0AF
```
