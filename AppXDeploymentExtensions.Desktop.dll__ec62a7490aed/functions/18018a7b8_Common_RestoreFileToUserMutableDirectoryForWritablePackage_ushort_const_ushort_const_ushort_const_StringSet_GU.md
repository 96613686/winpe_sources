# Common::RestoreFileToUserMutableDirectoryForWritablePackage(ushort const *,ushort const *,ushort const *,StringSet &,_GUID const &,ulong,bool,_WIN32_FIND_DATAW const *,StringSet *)

- ea: `0x18018a7b8`
- end: `0x18018ab08`
- name: `?RestoreFileToUserMutableDirectoryForWritablePackage@Common@@YAJPEBG00AEAVStringSet@@AEBU_GUID@@K_NPEBU_WIN32_FIND_DATAW@@PEAV2@@Z`
- size: `848`
- prototype: `__int64 __fastcall(Common *__hidden this, const unsigned __int16 *, PCWSTR pszPathIn, struct _GUID *, struct StringSet *, const struct _GUID *, char, unsigned __int16 *, const struct _WIN32_FIND_DATAW *, struct StringSet *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x18018ab10`

## callees

- `0x18000a398`
- `0x18001adb4`
- `0x1800685b8`
- `0x180069eb4`
- `0x18009d9b8`
- `0x1800af1bc`
- `0x180124adc`
- `0x1801731cc`
- `0x180189558`
- `0x180189724`
- `0x180189b68`
- `0x18018a648`
- `0x18018a7b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018aa35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018aaa9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018aa35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018aaa9`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18018aa25`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18018aa25`
- `api-ms-win-core-file-l2-1-0!CreateHardLinkW` at `0x18018aa95`
- `api-ms-win-core-file-l2-1-0!CreateHardLinkW` at `0x18018aa95`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x18018a9e3`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x18018a9e3`

## string_xrefs

- `0x18018a803`: `onecore\admin\appmodel\common\mutabledirectoryhelper.cpp`
- `0x18018a93b`: `onecore\admin\appmodel\common\mutabledirectoryhelper.cpp`
- `0x18018aa05`: `onecore\admin\appmodel\common\mutabledirectoryhelper.cpp`
- `0x18018aaef`: `onecore\admin\appmodel\common\mutabledirectoryhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Common::RestoreFileToUserMutableDirectoryForWritablePackage(
        Common *this,
        const unsigned __int16 *a2,
        PCWSTR pszPathIn,
        struct _GUID *a4,
        struct StringSet *a5,
        const struct _GUID *a6,
        char a7,
        unsigned __int16 *a8,
        struct _WIN32_FIND_DATAW *a9)
{
  int TombstoneFile; // ebx
  __int64 v14; // rdx
  const struct std::nothrow_t *v15; // rdx
  const unsigned __int16 *v17; // rdx
  char v18; // bl
  bool IsFileModifiedInSilo; // al
  int DirectoryTreeForFileWithReparsePoints; // eax
  const unsigned __int16 *v21; // r8
  unsigned int v22; // esi
  const struct std::nothrow_t *v23; // rdx
  const char *v24; // r9
  char v25; // di
  const unsigned __int16 *v26; // r8
  signed int LastError; // eax
  DWORD v28; // eax
  const struct _WIN32_FIND_DATAW *v29; // r9
  unsigned int v30; // [rsp+20h] [rbp-40h]
  LPCWSTR lpNewFileName[2]; // [rsp+30h] [rbp-30h] BYREF
  int v32; // [rsp+40h] [rbp-20h]
  LPCWSTR lpExistingFileName[2]; // [rsp+48h] [rbp-18h] BYREF
  int v34; // [rsp+58h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]

  *(_OWORD *)lpNewFileName = 0;
  v32 = 0;
  *(_OWORD *)lpExistingFileName = 0;
  v34 = 0;
  TombstoneFile = Common::PathHelpers::CombinePaths(a2, pszPathIn, (struct Common::StringBuffer *)lpNewFileName);
  if ( TombstoneFile < 0 )
  {
    v14 = 498;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\admin\\appmodel\\common\\mutabledirectoryhelper.cpp",
      (const char *)(unsigned int)TombstoneFile,
      v30);
LABEL_4:
    if ( lpExistingFileName[1] )
      operator delete((void *)lpExistingFileName[1], v15);
    if ( lpNewFileName[1] )
      operator delete((void *)lpNewFileName[1], v15);
    return (unsigned int)TombstoneFile;
  }
  TombstoneFile = Common::PathHelpers::CombinePaths(
                    (const unsigned __int16 *)this,
                    pszPathIn,
                    (struct Common::StringBuffer *)lpExistingFileName);
  if ( TombstoneFile < 0 )
  {
    v14 = 499;
    goto LABEL_3;
  }
  if ( (*(_DWORD *)a8 & 0x400) != 0 && (*((_DWORD *)a8 + 9) == -2147483624 || *((_DWORD *)a8 + 9) == -1879044072) )
    goto LABEL_21;
  v18 = 1;
  if ( a7 )
    IsFileModifiedInSilo = 1;
  else
    IsFileModifiedInSilo = Common::IsFileModifiedInSilo((Common *)lpExistingFileName[1], v17);
  if ( (*(_DWORD *)a8 & 0x400) != 0 && *((_DWORD *)a8 + 9) == -1610612705 )
  {
    if ( ((unsigned __int8)a6 & 2) != 0
      || !Common::GenericMap<unsigned short const *,unsigned short const *>::Find(a4, pszPathIn) )
    {
      goto LABEL_21;
    }
  }
  else if ( IsFileModifiedInSilo )
  {
    if ( Common::GenericMap<unsigned short const *,unsigned short const *>::Find(a4, pszPathIn)
      && ((unsigned __int8)a6 & 1) != 0
      || ((unsigned __int8)a6 & 4) != 0 )
    {
      goto LABEL_21;
    }
  }
  else if ( Common::GenericMap<unsigned short const *,unsigned short const *>::Find(a4, pszPathIn) )
  {
LABEL_21:
    if ( lpExistingFileName[1] )
      operator delete((void *)lpExistingFileName[1], (const struct std::nothrow_t *)v17);
    if ( lpNewFileName[1] )
      operator delete((void *)lpNewFileName[1], (const struct std::nothrow_t *)v17);
    return 0;
  }
  DirectoryTreeForFileWithReparsePoints = Common::CreateDirectoryTreeForFileWithReparsePoints(
                                            this,
                                            a2,
                                            pszPathIn,
                                            (const unsigned __int16 *)a5,
                                            a4,
                                            (struct StringSet *)a9);
  v22 = DirectoryTreeForFileWithReparsePoints;
  if ( DirectoryTreeForFileWithReparsePoints >= 0 )
  {
    if ( (*(_BYTE *)a8 & 0x10) != 0 )
    {
      if ( (*(_DWORD *)a8 & 0x400) != 0 )
      {
        if ( *((_DWORD *)a8 + 9) == -1610612705 )
        {
          LOBYTE(v17) = 1;
          TombstoneFile = Common::CreateTombstoneFile((Common *)lpNewFileName[1], v17, (bool)v21);
          if ( TombstoneFile < 0 )
          {
            v14 = 550;
            goto LABEL_3;
          }
        }
        else if ( *((_DWORD *)a8 + 9) == -1610612724 )
        {
          LOBYTE(v21) = 1;
          TombstoneFile = StatePaths::CopySymbolicLink(lpExistingFileName[1], lpNewFileName[1], v21);
          if ( TombstoneFile < 0 )
          {
            v14 = 555;
            goto LABEL_3;
          }
        }
      }
      else
      {
        if ( MoveFileW(lpExistingFileName[1], lpNewFileName[1]) )
        {
          v25 = 1;
          v18 = 0;
        }
        else
        {
          v25 = 0;
        }
        if ( v18 )
          wil::details::in1diag3::_Log_GetLastError(
            retaddr,
            (void *)0x233,
            (unsigned int)"onecore\\admin\\appmodel\\common\\mutabledirectoryhelper.cpp",
            v24);
        if ( !v25 )
        {
          if ( !CreateDirectoryW(lpNewFileName[1], 0) )
          {
            LastError = GetLastError();
            TombstoneFile = LastError;
            if ( LastError != 183 )
            {
              if ( LastError > 0 )
                TombstoneFile = (unsigned __int16)LastError | 0x80070000;
              if ( TombstoneFile >= 0 )
                goto LABEL_4;
              v14 = 571;
              goto LABEL_3;
            }
          }
          TombstoneFile = Common::Deployment::CopyPermissions(lpExistingFileName[1], (LPWSTR)lpNewFileName[1], v26);
          if ( TombstoneFile < 0 )
          {
            v14 = 573;
            goto LABEL_3;
          }
        }
      }
    }
    else if ( !CreateHardLinkW(lpNewFileName[1], lpExistingFileName[1], 0) )
    {
      v28 = GetLastError();
      if ( v28 == 1142 )
      {
        TombstoneFile = Common::CopyModifiedFileOrAddOn((Common *)lpExistingFileName[1], lpNewFileName[1], a8, v29);
        if ( TombstoneFile < 0 )
        {
          v14 = 584;
          goto LABEL_3;
        }
      }
      else if ( v28 )
      {
        TombstoneFile = wil::details::in1diag3::Return_Win32(
                          retaddr,
                          (void *)0x24C,
                          (unsigned int)"onecore\\admin\\appmodel\\common\\mutabledirectoryhelper.cpp",
                          (const char *)v28,
                          v30);
        goto LABEL_4;
      }
    }
    goto LABEL_21;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x21F,
    (unsigned int)"onecore\\admin\\appmodel\\common\\mutabledirectoryhelper.cpp",
    (const char *)(unsigned int)DirectoryTreeForFileWithReparsePoints,
    v30);
  if ( lpExistingFileName[1] )
    operator delete((void *)lpExistingFileName[1], v23);
  if ( lpNewFileName[1] )
    operator delete((void *)lpNewFileName[1], v23);
  return v22;
}

```

## disassembly

```asm
0x18018a7b8  push    rbp
0x18018a7ba  push    rbx
0x18018a7bb  push    rsi
0x18018a7bc  push    rdi
0x18018a7bd  push    r12
0x18018a7bf  push    r14
0x18018a7c1  push    r15
0x18018a7c3  mov     rbp, rsp
0x18018a7c6  sub     rsp, 60h
0x18018a7ca  mov     r14, r9
0x18018a7cd  mov     rsi, r8
0x18018a7d0  mov     r12, rdx
0x18018a7d3  mov     r15, rcx
0x18018a7d6  xor     eax, eax
0x18018a7d8  xorps   xmm0, xmm0
0x18018a7db  movups  xmmword ptr [rbp+lpNewFileName], xmm0
0x18018a7df  mov     [rbp+var_20], eax
0x18018a7e2  movups  xmmword ptr [rbp+lpExistingFileName], xmm0
0x18018a7e6  mov     [rbp+var_8], eax
0x18018a7e9  lea     r8, [rbp+lpNewFileName]; this
0x18018a7ed  mov     rdx, rsi; Src
0x18018a7f0  mov     rcx, r12; unsigned __int16 *
0x18018a7f3  call    ?CombinePaths@PathHelpers@Common@@SAJPEBG0PEAVStringBuffer@2@@Z; Common::PathHelpers::CombinePaths(ushort const *,ushort const *,Common::StringBuffer *)
0x18018a7f8  mov     ebx, eax
0x18018a7fa  test    eax, eax
0x18018a7fc  jns     short loc_18018A83B
0x18018a7fe  mov     edx, 1F2h; void *
0x18018a803  lea     r8, aOnecoreAdminAp_117; "onecore\\admin\\appmodel\\common\\mutab"...
0x18018a80a  mov     r9d, ebx; char *
0x18018a80d  mov     rcx, [rbp+38h]; this
0x18018a811  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018a816  nop
0x18018a817  mov     rcx, [rbp+lpExistingFileName+8]; void *
0x18018a81b  test    rcx, rcx
0x18018a81e  jz      short loc_18018A826
0x18018a820  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18018a825  nop
0x18018a826  mov     rcx, [rbp+lpNewFileName+8]; void *
0x18018a82a  test    rcx, rcx
0x18018a82d  jz      short loc_18018A834
0x18018a82f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18018a834  mov     eax, ebx
0x18018a836  jmp     loc_18018A8D0
0x18018a83b  lea     r8, [rbp+lpExistingFileName]; this
0x18018a83f  mov     rdx, rsi; Src
0x18018a842  mov     rcx, r15; unsigned __int16 *
0x18018a845  call    ?CombinePaths@PathHelpers@Common@@SAJPEBG0PEAVStringBuffer@2@@Z; Common::PathHelpers::CombinePaths(ushort const *,ushort const *,Common::StringBuffer *)
0x18018a84a  mov     ebx, eax
0x18018a84c  test    eax, eax
0x18018a84e  jns     short loc_18018A857
0x18018a850  mov     edx, 1F3h
0x18018a855  jmp     short loc_18018A803
0x18018a857  mov     rdi, [rbp+arg_38]
0x18018a85b  test    dword ptr [rdi], 400h
0x18018a861  jz      short loc_18018A875
0x18018a863  cmp     dword ptr [rdi+24h], 80000018h
0x18018a86a  jz      short loc_18018A8B1
0x18018a86c  cmp     dword ptr [rdi+24h], 90001018h
0x18018a873  jz      short loc_18018A8B1
0x18018a875  mov     bl, 1
0x18018a877  cmp     [rbp+arg_30], 0
0x18018a87b  jz      short loc_18018A881
0x18018a87d  mov     al, bl
0x18018a87f  jmp     short loc_18018A88A
0x18018a881  mov     rcx, [rbp+lpExistingFileName+8]; this
0x18018a885  call    ?IsFileModifiedInSilo@Common@@YA_NPEBG@Z; Common::IsFileModifiedInSilo(ushort const *)
0x18018a88a  test    dword ptr [rdi], 400h
0x18018a890  jz      short loc_18018A8E0
0x18018a892  cmp     dword ptr [rdi+24h], 0A000001Fh
0x18018a899  jnz     short loc_18018A8E0
0x18018a89b  test    byte ptr [rbp+arg_28], 2
0x18018a89f  jnz     short loc_18018A8B1
0x18018a8a1  mov     rdx, rsi
0x18018a8a4  mov     rcx, r14
0x18018a8a7  call    ?Find@?$GenericMap@PEBGPEBG@Common@@QEAAPEBGPEBG@Z; Common::GenericMap<ushort const *,ushort const *>::Find(ushort const *)
0x18018a8ac  test    rax, rax
0x18018a8af  jnz     short loc_18018A90B
0x18018a8b1  mov     rcx, [rbp+lpExistingFileName+8]; void *
0x18018a8b5  test    rcx, rcx
0x18018a8b8  jz      short loc_18018A8C0
0x18018a8ba  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18018a8bf  nop
0x18018a8c0  mov     rcx, [rbp+lpNewFileName+8]; void *
0x18018a8c4  test    rcx, rcx
0x18018a8c7  jz      short loc_18018A8CE
0x18018a8c9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18018a8ce  xor     eax, eax
0x18018a8d0  add     rsp, 60h
0x18018a8d4  pop     r15
0x18018a8d6  pop     r14
0x18018a8d8  pop     r12
0x18018a8da  pop     rdi
0x18018a8db  pop     rsi
0x18018a8dc  pop     rbx
0x18018a8dd  pop     rbp
0x18018a8de  retn
0x18018a8e0  mov     rdx, rsi
0x18018a8e3  mov     rcx, r14
0x18018a8e6  test    al, al
0x18018a8e8  jz      short loc_18018A901
0x18018a8ea  call    ?Find@?$GenericMap@PEBGPEBG@Common@@QEAAPEBGPEBG@Z; Common::GenericMap<ushort const *,ushort const *>::Find(ushort const *)
0x18018a8ef  test    rax, rax
0x18018a8f2  jz      short loc_18018A8F9
0x18018a8f4  test    byte ptr [rbp+arg_28], bl
0x18018a8f7  jnz     short loc_18018A8B1
0x18018a8f9  test    byte ptr [rbp+arg_28], 4
0x18018a8fd  jz      short loc_18018A90B
0x18018a8ff  jmp     short loc_18018A8B1
0x18018a901  call    ?Find@?$GenericMap@PEBGPEBG@Common@@QEAAPEBGPEBG@Z; Common::GenericMap<ushort const *,ushort const *>::Find(ushort const *)
0x18018a906  test    rax, rax
0x18018a909  jnz     short loc_18018A8B1
0x18018a90b  mov     rax, [rbp+arg_40]
0x18018a912  mov     [rsp+60h+var_38], rax; struct StringSet *
0x18018a917  mov     [rsp+60h+var_40], r14; unsigned int
0x18018a91c  mov     r9, [rbp+arg_20]; unsigned __int16 *
0x18018a920  mov     r8, rsi; pszPathIn
0x18018a923  mov     rdx, r12; unsigned __int16 *
0x18018a926  mov     rcx, r15; this
0x18018a929  call    ?CreateDirectoryTreeForFileWithReparsePoints@Common@@YAJPEBG00AEBU_GUID@@AEAVStringSet@@PEAV3@@Z; Common::CreateDirectoryTreeForFileWithReparsePoints(ushort const *,ushort const *,ushort const *,_GUID const &,StringSet &,StringSet *)
0x18018a92e  mov     esi, eax
0x18018a930  test    eax, eax
0x18018a932  jns     short loc_18018A971
0x18018a934  mov     rcx, [rbp+38h]; this
0x18018a938  mov     r9d, eax; char *
0x18018a93b  lea     r8, aOnecoreAdminAp_117; "onecore\\admin\\appmodel\\common\\mutab"...
0x18018a942  mov     edx, 21Fh; void *
0x18018a947  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018a94c  nop
0x18018a94d  mov     rcx, [rbp+lpExistingFileName+8]; void *
0x18018a951  test    rcx, rcx
0x18018a954  jz      short loc_18018A95C
0x18018a956  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18018a95b  nop
0x18018a95c  mov     rcx, [rbp+lpNewFileName+8]; void *
0x18018a960  test    rcx, rcx
0x18018a963  jz      short loc_18018A96A
0x18018a965  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18018a96a  mov     eax, esi
0x18018a96c  jmp     loc_18018A8D0
0x18018a971  test    byte ptr [rdi], 10h
0x18018a974  jz      loc_18018AA8A
0x18018a97a  test    dword ptr [rdi], 400h
0x18018a980  jz      short loc_18018A9DB
0x18018a982  cmp     dword ptr [rdi+24h], 0A000001Fh
0x18018a989  jnz     short loc_18018A9AA
0x18018a98b  mov     dl, bl; unsigned __int16 *
0x18018a98d  mov     rcx, [rbp+lpNewFileName+8]; this
0x18018a991  call    ?CreateTombstoneFile@Common@@YAJPEBG_N@Z; Common::CreateTombstoneFile(ushort const *,bool)
0x18018a996  mov     ebx, eax
0x18018a998  test    eax, eax
0x18018a99a  jns     loc_18018A8B1
0x18018a9a0  mov     edx, 226h
0x18018a9a5  jmp     loc_18018A803
0x18018a9aa  cmp     dword ptr [rdi+24h], 0A000000Ch
0x18018a9b1  jnz     loc_18018A8B1
0x18018a9b7  mov     r8b, bl; unsigned __int16 *
0x18018a9ba  mov     rdx, [rbp+lpNewFileName+8]; unsigned __int16 *
0x18018a9be  mov     rcx, [rbp+lpExistingFileName+8]; this
0x18018a9c2  call    ?CopySymbolicLink@StatePaths@@YAJPEBG0_N@Z; StatePaths::CopySymbolicLink(ushort const *,ushort const *,bool)
0x18018a9c7  mov     ebx, eax
0x18018a9c9  test    eax, eax
0x18018a9cb  jns     loc_18018A8B1
0x18018a9d1  mov     edx, 22Bh
0x18018a9d6  jmp     loc_18018A803
0x18018a9db  mov     rdx, [rbp+lpNewFileName+8]; lpNewFileName
0x18018a9df  mov     rcx, [rbp+lpExistingFileName+8]; lpExistingFileName
0x18018a9e3  call    cs:__imp_MoveFileW
0x18018a9ea  nop     dword ptr [rax+rax+00h]
0x18018a9ef  test    eax, eax
0x18018a9f1  jz      short loc_18018A9FA
0x18018a9f3  mov     dil, bl
0x18018a9f6  xor     bl, bl
0x18018a9f8  jmp     short loc_18018A9FD
0x18018a9fa  xor     dil, dil
0x18018a9fd  mov     rcx, [rbp+38h]; this
0x18018aa01  test    bl, bl
0x18018aa03  jz      short loc_18018AA16
0x18018aa05  lea     r8, aOnecoreAdminAp_117; "onecore\\admin\\appmodel\\common\\mutab"...
0x18018aa0c  mov     edx, 233h; void *
0x18018aa11  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18018aa16  test    dil, dil
0x18018aa19  jnz     loc_18018A8B1
0x18018aa1f  xor     edx, edx; lpSecurityAttributes
0x18018aa21  mov     rcx, [rbp+lpNewFileName+8]; lpPathName
0x18018aa25  call    cs:__imp_CreateDirectoryW
0x18018aa2c  nop     dword ptr [rax+rax+00h]
0x18018aa31  test    eax, eax
0x18018aa33  jnz     short loc_18018AA69
0x18018aa35  call    cs:__imp_GetLastError
0x18018aa3c  nop     dword ptr [rax+rax+00h]
0x18018aa41  mov     ebx, eax
0x18018aa43  cmp     eax, 0B7h
0x18018aa48  jz      short loc_18018AA69
0x18018aa4a  test    eax, eax
0x18018aa4c  jle     short loc_18018AA57
0x18018aa4e  movzx   ebx, ax
0x18018aa51  or      ebx, 80070000h
0x18018aa57  test    ebx, ebx
0x18018aa59  jns     loc_18018A817
0x18018aa5f  mov     edx, 23Bh
0x18018aa64  jmp     loc_18018A803
0x18018aa69  mov     rdx, [rbp+lpNewFileName+8]; LPWSTR
0x18018aa6d  mov     rcx, [rbp+lpExistingFileName+8]; pObjectName
0x18018aa71  call    ?CopyPermissions@Deployment@Common@@YAJPEBG0@Z; Common::Deployment::CopyPermissions(ushort const *,ushort const *)
0x18018aa76  mov     ebx, eax
0x18018aa78  test    eax, eax
0x18018aa7a  jns     loc_18018A8B1
0x18018aa80  mov     edx, 23Dh
0x18018aa85  jmp     loc_18018A803
0x18018aa8a  xor     r8d, r8d; lpSecurityAttributes
0x18018aa8d  mov     rdx, [rbp+lpExistingFileName+8]; lpExistingFileName
0x18018aa91  mov     rcx, [rbp+lpNewFileName+8]; lpFileName
0x18018aa95  call    cs:__imp_CreateHardLinkW
0x18018aa9c  nop     dword ptr [rax+rax+00h]
0x18018aaa1  test    eax, eax
0x18018aaa3  jnz     loc_18018A8B1
0x18018aaa9  call    cs:__imp_GetLastError
0x18018aab0  nop     dword ptr [rax+rax+00h]
0x18018aab5  cmp     eax, 476h
0x18018aaba  jnz     short loc_18018AAE0
0x18018aabc  mov     r8, rdi; unsigned __int16 *
0x18018aabf  mov     rdx, [rbp+lpNewFileName+8]; unsigned __int16 *
0x18018aac3  mov     rcx, [rbp+lpExistingFileName+8]; this
0x18018aac7  call    ?CopyModifiedFileOrAddOn@Common@@YAJPEBG0PEBU_WIN32_FIND_DATAW@@@Z; Common::CopyModifiedFileOrAddOn(ushort const *,ushort const *,_WIN32_FIND_DATAW const *)
0x18018aacc  mov     ebx, eax
0x18018aace  test    eax, eax
0x18018aad0  jns     loc_18018A8B1
0x18018aad6  mov     edx, 248h
0x18018aadb  jmp     loc_18018A803
0x18018aae0  test    eax, eax
0x18018aae2  jz      loc_18018A8B1
0x18018aae8  mov     rcx, [rbp+38h]; this
0x18018aaec  mov     r9d, eax; char *
0x18018aaef  lea     r8, aOnecoreAdminAp_117; "onecore\\admin\\appmodel\\common\\mutab"...
0x18018aaf6  mov     edx, 24Ch; void *
0x18018aafb  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18018ab00  mov     ebx, eax
0x18018ab02  jmp     loc_18018A817
```
