# Common::RestoreFileToMutableDirectory(ushort const *,ushort const *,ushort const *,StringSet &,_GUID const &,bool,bool,_WIN32_FIND_DATAW const *,StringSet *)

- ea: `0x18008cf20`
- end: `0x18008d415`
- name: `?RestoreFileToMutableDirectory@Common@@YAJPEBG00AEAVStringSet@@AEBU_GUID@@_N3PEBU_WIN32_FIND_DATAW@@PEAV2@@Z`
- size: `1269`
- prototype: `__int64 __fastcall(Common *__hidden this, const unsigned __int16 *, const unsigned __int16 *Src, const unsigned __int16 *, struct StringSet *, const struct _GUID *, bool, bool, const struct _WIN32_FIND_DATAW *, struct StringSet *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x18018ace0`

## callees

- `0x18000a398`
- `0x18001adb4`
- `0x1800685b8`
- `0x180069eb4`
- `0x180081354`
- `0x18008cf20`
- `0x1800991e8`
- `0x18009d9b8`
- `0x1800af1bc`
- `0x180124adc`
- `0x1801731cc`
- `0x180189558`
- `0x180189724`
- `0x180189b68`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d2ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d392`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d2ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d392`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18008d29d`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18008d29d`
- `api-ms-win-core-file-l2-1-0!CreateHardLinkW` at `0x18008d37e`
- `api-ms-win-core-file-l2-1-0!CreateHardLinkW` at `0x18008d37e`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x18008d25c`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x18008d25c`

## string_xrefs

- `0x18008cf6f`: `onecore\admin\appmodel\common\mutabledirectoryhelper.cpp`
- `0x18008d02c`: `onecore\admin\appmodel\common\mutabledirectoryhelper.cpp`
- `0x18008d12a`: `onecore\admin\appmodel\common\mutabledirectoryhelper.cpp`
- `0x18008d19f`: `onecore\admin\appmodel\common\mutabledirectoryhelper.cpp`
- `0x18008d27e`: `onecore\admin\appmodel\common\mutabledirectoryhelper.cpp`
- `0x18008d3d8`: `onecore\admin\appmodel\common\mutabledirectoryhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Common::RestoreFileToMutableDirectory(
        Common *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *Src,
        const struct _GUID *a4,
        struct StringSet *a5,
        const struct _GUID *a6,
        bool a7,
        unsigned __int16 *a8,
        struct _WIN32_FIND_DATAW *a9)
{
  int TombstoneFile; // ebx
  __int64 v14; // rdx
  const struct std::nothrow_t *v15; // rdx
  const struct std::nothrow_t *v17; // rdx
  int v18; // eax
  int DirectoryTreeForFileWithReparsePoints; // edi
  __int64 v20; // rdx
  const struct std::nothrow_t *v21; // rdx
  const unsigned __int16 *v22; // r8
  const unsigned __int16 *v23; // rdx
  bool v24; // r8
  __int64 v25; // rdx
  unsigned __int16 *v26; // rbx
  int v27; // eax
  const char *v28; // r9
  char v29; // bl
  char v30; // al
  const unsigned __int16 *v31; // r8
  signed int LastError; // eax
  const struct _WIN32_FIND_DATAW *v33; // r9
  DWORD v34; // eax
  const struct _WIN32_FIND_DATAW *v35; // r9
  unsigned int v36; // [rsp+20h] [rbp-61h]
  LPCWSTR lpNewFileName[2]; // [rsp+30h] [rbp-51h] BYREF
  int v38; // [rsp+40h] [rbp-41h]
  LPCWSTR lpExistingFileName[2]; // [rsp+48h] [rbp-39h] BYREF
  int v40; // [rsp+58h] [rbp-29h]
  unsigned __int16 *v41[2]; // [rsp+60h] [rbp-21h] BYREF
  int v42; // [rsp+70h] [rbp-11h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+37h]

  *(_OWORD *)lpNewFileName = 0;
  v38 = 0;
  *(_OWORD *)lpExistingFileName = 0;
  v40 = 0;
  TombstoneFile = Common::PathHelpers::CombinePaths(a2, Src, (struct Common::StringBuffer *)lpNewFileName);
  if ( TombstoneFile < 0 )
  {
    v14 = 135;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\admin\\appmodel\\common\\mutabledirectoryhelper.cpp",
      (const char *)(unsigned int)TombstoneFile,
      v36);
LABEL_4:
    if ( lpExistingFileName[1] )
      operator delete((void *)lpExistingFileName[1], v15);
    if ( lpNewFileName[1] )
      operator delete((void *)lpNewFileName[1], v15);
    return (unsigned int)TombstoneFile;
  }
  TombstoneFile = Common::PathHelpers::CombinePaths(
                    (const unsigned __int16 *)this,
                    Src,
                    (struct Common::StringBuffer *)lpExistingFileName);
  if ( TombstoneFile < 0 )
  {
    v14 = 136;
    goto LABEL_3;
  }
  if ( !(_BYTE)a6 && !a7 && Common::GenericMap<unsigned short const *,unsigned short const *>::Find(a4, Src) )
    goto LABEL_45;
  v18 = *(_DWORD *)a8 & 0x400;
  if ( v18 && *((_DWORD *)a8 + 9) == -1610612724 )
  {
    DirectoryTreeForFileWithReparsePoints = Common::CreateDirectoryTreeForFileWithReparsePoints(
                                              this,
                                              a2,
                                              Src,
                                              (const unsigned __int16 *)a5,
                                              a4,
                                              (struct StringSet *)a9,
                                              (struct StringSet *)lpNewFileName[0]);
    if ( DirectoryTreeForFileWithReparsePoints < 0 )
    {
      v20 = 153;
LABEL_18:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v20,
        (unsigned int)"onecore\\admin\\appmodel\\common\\mutabledirectoryhelper.cpp",
        (const char *)(unsigned int)DirectoryTreeForFileWithReparsePoints,
        v36);
LABEL_19:
      if ( lpExistingFileName[1] )
        operator delete((void *)lpExistingFileName[1], v21);
      if ( lpNewFileName[1] )
        operator delete((void *)lpNewFileName[1], v21);
      return (unsigned int)DirectoryTreeForFileWithReparsePoints;
    }
    v22 = (const unsigned __int16 *)(*(_DWORD *)a8 >> 4);
    LOBYTE(v22) = (*(_DWORD *)a8 & 0x10) != 0;
    TombstoneFile = StatePaths::CopySymbolicLink(lpExistingFileName[1], lpNewFileName[1], v22);
    if ( TombstoneFile < 0 )
    {
      v14 = 157;
      goto LABEL_3;
    }
  }
  else if ( (*(_BYTE *)a8 & 0x10) != 0 )
  {
    if ( v18 )
    {
      if ( *((_DWORD *)a8 + 9) == -1610612705 )
      {
        TombstoneFile = Common::CreateDirectoryTreeForFileWithReparsePoints(
                          this,
                          a2,
                          Src,
                          (const unsigned __int16 *)a5,
                          a4,
                          (struct StringSet *)a9,
                          (struct StringSet *)lpNewFileName[0]);
        if ( TombstoneFile < 0 )
        {
          v14 = 164;
          goto LABEL_3;
        }
        LOBYTE(v23) = 1;
        TombstoneFile = Common::CreateTombstoneFile((Common *)lpNewFileName[1], v23, v24);
        if ( TombstoneFile < 0 )
        {
          v14 = 165;
          goto LABEL_3;
        }
        goto LABEL_45;
      }
      if ( *((_DWORD *)a8 + 9) == -1610612733 )
      {
        *(_OWORD *)v41 = 0;
        v42 = 0;
        TombstoneFile = Common::Deployment::MountedFolder::GetTarget(
                          lpExistingFileName[1],
                          (struct Common::StringBuffer *)v41);
        if ( TombstoneFile >= 0 )
        {
          TombstoneFile = Common::CreateDirectoryTreeForFileWithReparsePoints(
                            this,
                            a2,
                            Src,
                            (const unsigned __int16 *)a5,
                            a4,
                            (struct StringSet *)a9,
                            (struct StringSet *)lpNewFileName[0]);
          if ( TombstoneFile >= 0 )
          {
            v26 = v41[1];
            v27 = Common::Deployment::MountedFolder::Create(lpNewFileName[1], v41[1]);
            DirectoryTreeForFileWithReparsePoints = v27;
            if ( v27 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xAC,
                (unsigned int)"onecore\\admin\\appmodel\\common\\mutabledirectoryhelper.cpp",
                (const char *)(unsigned int)v27,
                v36);
              if ( v26 )
                operator delete(v26, v21);
              goto LABEL_19;
            }
            if ( v26 )
              operator delete(v26, v17);
            goto LABEL_45;
          }
          v25 = 171;
        }
        else
        {
          v25 = 170;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v25,
          (unsigned int)"onecore\\admin\\appmodel\\common\\mutabledirectoryhelper.cpp",
          (const char *)(unsigned int)TombstoneFile,
          v36);
        if ( v41[1] )
          operator delete(v41[1], v15);
        goto LABEL_4;
      }
    }
    if ( !Common::GenericMap<unsigned short const *,unsigned short const *>::Find(a4, Src) )
    {
      DirectoryTreeForFileWithReparsePoints = Common::CreateDirectoryTreeForFileWithReparsePoints(
                                                this,
                                                a2,
                                                Src,
                                                (const unsigned __int16 *)a5,
                                                a4,
                                                (struct StringSet *)a9,
                                                (struct StringSet *)lpNewFileName[0]);
      if ( DirectoryTreeForFileWithReparsePoints < 0 )
      {
        v20 = 184;
        goto LABEL_18;
      }
      if ( a7 || (*(_DWORD *)a8 & 0x400) != 0 )
        goto LABEL_89;
      if ( MoveFileW(lpExistingFileName[1], lpNewFileName[1]) )
      {
        v29 = 1;
        v30 = 0;
      }
      else
      {
        v29 = 0;
        v30 = 1;
      }
      if ( v30 )
        wil::details::in1diag3::_Log_GetLastError(
          retaddr,
          (void *)0xC0,
          (unsigned int)"onecore\\admin\\appmodel\\common\\mutabledirectoryhelper.cpp",
          v28);
      if ( !v29 )
      {
LABEL_89:
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
            v14 = 201;
            goto LABEL_3;
          }
        }
        TombstoneFile = Common::Deployment::CopyPermissions(lpExistingFileName[1], (LPWSTR)lpNewFileName[1], v31);
        if ( TombstoneFile < 0 )
        {
          v14 = 203;
          goto LABEL_3;
        }
      }
    }
  }
  else if ( (!v18 || *((_DWORD *)a8 + 9) != -2147483624 && *((_DWORD *)a8 + 9) != -1879044072)
         && ((_BYTE)a6 || a7 || !v18 || *((_DWORD *)a8 + 9) != -1610612705) )
  {
    DirectoryTreeForFileWithReparsePoints = Common::CreateDirectoryTreeForFileWithReparsePoints(
                                              this,
                                              a2,
                                              Src,
                                              (const unsigned __int16 *)a5,
                                              a4,
                                              (struct StringSet *)a9,
                                              (struct StringSet *)lpNewFileName[0]);
    if ( DirectoryTreeForFileWithReparsePoints < 0 )
    {
      v20 = 226;
      goto LABEL_18;
    }
    if ( a7 )
    {
      TombstoneFile = Common::CopyModifiedFileOrAddOn((Common *)lpExistingFileName[1], lpNewFileName[1], a8, v33);
      if ( TombstoneFile < 0 )
      {
        v14 = 246;
        goto LABEL_3;
      }
    }
    else if ( !CreateHardLinkW(lpNewFileName[1], lpExistingFileName[1], 0) )
    {
      v34 = GetLastError();
      if ( v34 == 1142 )
      {
        TombstoneFile = Common::CopyModifiedFileOrAddOn((Common *)lpExistingFileName[1], lpNewFileName[1], a8, v35);
        if ( TombstoneFile < 0 )
        {
          v14 = 236;
          goto LABEL_3;
        }
      }
      else if ( v34 )
      {
        TombstoneFile = wil::details::in1diag3::Return_Win32(
                          retaddr,
                          (void *)0xF0,
                          (unsigned int)"onecore\\admin\\appmodel\\common\\mutabledirectoryhelper.cpp",
                          (const char *)v34,
                          v36);
        goto LABEL_4;
      }
    }
  }
LABEL_45:
  if ( lpExistingFileName[1] )
    operator delete((void *)lpExistingFileName[1], v17);
  if ( lpNewFileName[1] )
    operator delete((void *)lpNewFileName[1], v17);
  return 0;
}

```

## disassembly

```asm
0x18008cf20  push    rbp
0x18008cf22  push    rbx
0x18008cf23  push    rdi
0x18008cf24  push    r13
0x18008cf26  push    r14
0x18008cf28  push    r15
0x18008cf2a  lea     rbp, [rsp-7]
0x18008cf2f  sub     rsp, 88h
0x18008cf36  mov     r14, r9
0x18008cf39  mov     rdi, r8
0x18008cf3c  mov     r13, rdx
0x18008cf3f  mov     r15, rcx
0x18008cf42  xor     eax, eax
0x18008cf44  xorps   xmm0, xmm0
0x18008cf47  movups  xmmword ptr [rbp+2Fh+lpNewFileName], xmm0
0x18008cf4b  mov     [rbp+2Fh+var_70], eax
0x18008cf4e  movups  xmmword ptr [rbp+2Fh+lpExistingFileName], xmm0
0x18008cf52  mov     [rbp+2Fh+var_58], eax
0x18008cf55  lea     r8, [rbp+2Fh+lpNewFileName]; this
0x18008cf59  mov     rdx, rdi; Src
0x18008cf5c  mov     rcx, r13; unsigned __int16 *
0x18008cf5f  call    ?CombinePaths@PathHelpers@Common@@SAJPEBG0PEAVStringBuffer@2@@Z; Common::PathHelpers::CombinePaths(ushort const *,ushort const *,Common::StringBuffer *)
0x18008cf64  mov     ebx, eax
0x18008cf66  test    eax, eax
0x18008cf68  jns     short loc_18008CFA7
0x18008cf6a  mov     edx, 87h; void *
0x18008cf6f  lea     r8, aOnecoreAdminAp_117; "onecore\\admin\\appmodel\\common\\mutab"...
0x18008cf76  mov     r9d, ebx; char *
0x18008cf79  mov     rcx, [rbp+37h]; this
0x18008cf7d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008cf82  nop
0x18008cf83  mov     rcx, [rbp+2Fh+lpExistingFileName+8]; void *
0x18008cf87  test    rcx, rcx
0x18008cf8a  jz      short loc_18008CF92
0x18008cf8c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18008cf91  nop
0x18008cf92  mov     rcx, [rbp+2Fh+lpNewFileName+8]; void *
0x18008cf96  test    rcx, rcx
0x18008cf99  jz      short loc_18008CFA0
0x18008cf9b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18008cfa0  mov     eax, ebx
0x18008cfa2  jmp     loc_18008D1F4
0x18008cfa7  lea     r8, [rbp+2Fh+lpExistingFileName]; this
0x18008cfab  mov     rdx, rdi; Src
0x18008cfae  mov     rcx, r15; unsigned __int16 *
0x18008cfb1  call    ?CombinePaths@PathHelpers@Common@@SAJPEBG0PEAVStringBuffer@2@@Z; Common::PathHelpers::CombinePaths(ushort const *,ushort const *,Common::StringBuffer *)
0x18008cfb6  mov     ebx, eax
0x18008cfb8  test    eax, eax
0x18008cfba  jns     short loc_18008CFC3
0x18008cfbc  mov     edx, 88h
0x18008cfc1  jmp     short loc_18008CF6F
0x18008cfc3  cmp     byte ptr [rbp+2Fh+arg_28], 0
0x18008cfc7  jnz     short loc_18008CFE3
0x18008cfc9  cmp     [rbp+2Fh+arg_30], 0
0x18008cfcd  jnz     short loc_18008CFE3
0x18008cfcf  mov     rdx, rdi
0x18008cfd2  mov     rcx, r14
0x18008cfd5  call    ?Find@?$GenericMap@PEBGPEBG@Common@@QEAAPEBGPEBG@Z; Common::GenericMap<ushort const *,ushort const *>::Find(ushort const *)
0x18008cfda  test    rax, rax
0x18008cfdd  jnz     loc_18008D1D5
0x18008cfe3  mov     rbx, [rbp+2Fh+arg_38]
0x18008cfe7  mov     eax, [rbx]
0x18008cfe9  and     eax, 400h
0x18008cfee  jz      loc_18008D090
0x18008cff4  cmp     dword ptr [rbx+24h], 0A000000Ch
0x18008cffb  jnz     loc_18008D090
0x18008d001  mov     rax, [rbp+2Fh+arg_40]
0x18008d005  mov     [rsp+0B0h+var_88], rax; struct StringSet *
0x18008d00a  mov     [rsp+0B0h+var_90], r14; int
0x18008d00f  mov     r9, [rbp+2Fh+arg_20]; unsigned __int16 *
0x18008d013  mov     r8, rdi; pszPathIn
0x18008d016  mov     rdx, r13; unsigned __int16 *
0x18008d019  mov     rcx, r15; this
0x18008d01c  call    ?CreateDirectoryTreeForFileWithReparsePoints@Common@@YAJPEBG00AEBU_GUID@@AEAVStringSet@@PEAV3@@Z; Common::CreateDirectoryTreeForFileWithReparsePoints(ushort const *,ushort const *,ushort const *,_GUID const &,StringSet &,StringSet *)
0x18008d021  mov     edi, eax
0x18008d023  test    eax, eax
0x18008d025  jns     short loc_18008D064
0x18008d027  mov     edx, 99h; void *
0x18008d02c  lea     r8, aOnecoreAdminAp_117; "onecore\\admin\\appmodel\\common\\mutab"...
0x18008d033  mov     r9d, edi; char *
0x18008d036  mov     rcx, [rbp+37h]; this
0x18008d03a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008d03f  nop
0x18008d040  mov     rcx, [rbp+2Fh+lpExistingFileName+8]; void *
0x18008d044  test    rcx, rcx
0x18008d047  jz      short loc_18008D04F
0x18008d049  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18008d04e  nop
0x18008d04f  mov     rcx, [rbp+2Fh+lpNewFileName+8]; void *
0x18008d053  test    rcx, rcx
0x18008d056  jz      short loc_18008D05D
0x18008d058  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18008d05d  mov     eax, edi
0x18008d05f  jmp     loc_18008D1F4
0x18008d064  mov     r8d, [rbx]
0x18008d067  shr     r8d, 4
0x18008d06b  and     r8b, 1; unsigned __int16 *
0x18008d06f  mov     rdx, [rbp+2Fh+lpNewFileName+8]; unsigned __int16 *
0x18008d073  mov     rcx, [rbp+2Fh+lpExistingFileName+8]; this
0x18008d077  call    ?CopySymbolicLink@StatePaths@@YAJPEBG0_N@Z; StatePaths::CopySymbolicLink(ushort const *,ushort const *,bool)
0x18008d07c  mov     ebx, eax
0x18008d07e  test    eax, eax
0x18008d080  jns     loc_18008D1D5
0x18008d086  mov     edx, 9Dh
0x18008d08b  jmp     loc_18008CF6F
0x18008d090  test    byte ptr [rbx], 10h
0x18008d093  jz      loc_18008D302
0x18008d099  test    eax, eax
0x18008d09b  jz      loc_18008D206
0x18008d0a1  cmp     dword ptr [rbx+24h], 0A000001Fh
0x18008d0a8  jnz     short loc_18008D0F9
0x18008d0aa  mov     rax, [rbp+2Fh+arg_40]
0x18008d0ae  mov     [rsp+0B0h+var_88], rax; struct StringSet *
0x18008d0b3  mov     [rsp+0B0h+var_90], r14; struct _GUID *
0x18008d0b8  mov     r9, [rbp+2Fh+arg_20]; unsigned __int16 *
0x18008d0bc  mov     r8, rdi; pszPathIn
0x18008d0bf  mov     rdx, r13; unsigned __int16 *
0x18008d0c2  mov     rcx, r15; this
0x18008d0c5  call    ?CreateDirectoryTreeForFileWithReparsePoints@Common@@YAJPEBG00AEBU_GUID@@AEAVStringSet@@PEAV3@@Z; Common::CreateDirectoryTreeForFileWithReparsePoints(ushort const *,ushort const *,ushort const *,_GUID const &,StringSet &,StringSet *)
0x18008d0ca  mov     ebx, eax
0x18008d0cc  test    eax, eax
0x18008d0ce  jns     short loc_18008D0DA
0x18008d0d0  mov     edx, 0A4h
0x18008d0d5  jmp     loc_18008CF6F
0x18008d0da  mov     dl, 1; unsigned __int16 *
0x18008d0dc  mov     rcx, [rbp+2Fh+lpNewFileName+8]; this
0x18008d0e0  call    ?CreateTombstoneFile@Common@@YAJPEBG_N@Z; Common::CreateTombstoneFile(ushort const *,bool)
0x18008d0e5  mov     ebx, eax
0x18008d0e7  test    eax, eax
0x18008d0e9  jns     loc_18008D1D5
0x18008d0ef  mov     edx, 0A5h
0x18008d0f4  jmp     loc_18008CF6F
0x18008d0f9  cmp     dword ptr [rbx+24h], 0A0000003h
0x18008d100  jnz     loc_18008D206
0x18008d106  xor     eax, eax
0x18008d108  xorps   xmm0, xmm0
0x18008d10b  movups  xmmword ptr [rbp+2Fh+var_50], xmm0
0x18008d10f  mov     [rbp+2Fh+var_40], eax
0x18008d112  lea     rdx, [rbp+2Fh+var_50]; struct Common::StringBuffer *
0x18008d116  mov     rcx, [rbp+2Fh+lpExistingFileName+8]; unsigned __int16 *
0x18008d11a  call    ?GetTarget@MountedFolder@Deployment@Common@@SAJPEBGPEAVStringBuffer@3@@Z; Common::Deployment::MountedFolder::GetTarget(ushort const *,Common::StringBuffer *)
0x18008d11f  mov     ebx, eax
0x18008d121  test    eax, eax
0x18008d123  jns     short loc_18008D155
0x18008d125  mov     edx, 0AAh; void *
0x18008d12a  lea     r8, aOnecoreAdminAp_117; "onecore\\admin\\appmodel\\common\\mutab"...
0x18008d131  mov     r9d, ebx; char *
0x18008d134  mov     rcx, [rbp+37h]; this
0x18008d138  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008d13d  nop
0x18008d13e  mov     rcx, [rbp+2Fh+var_50+8]; void *
0x18008d142  test    rcx, rcx
0x18008d145  jz      loc_18008CF83
0x18008d14b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18008d150  jmp     loc_18008CF83
0x18008d155  mov     rax, [rbp+2Fh+arg_40]
0x18008d159  mov     [rsp+0B0h+var_88], rax; struct StringSet *
0x18008d15e  mov     [rsp+0B0h+var_90], r14; int
0x18008d163  mov     r9, [rbp+2Fh+arg_20]; unsigned __int16 *
0x18008d167  mov     r8, rdi; pszPathIn
0x18008d16a  mov     rdx, r13; unsigned __int16 *
0x18008d16d  mov     rcx, r15; this
0x18008d170  call    ?CreateDirectoryTreeForFileWithReparsePoints@Common@@YAJPEBG00AEBU_GUID@@AEAVStringSet@@PEAV3@@Z; Common::CreateDirectoryTreeForFileWithReparsePoints(ushort const *,ushort const *,ushort const *,_GUID const &,StringSet &,StringSet *)
0x18008d175  mov     ebx, eax
0x18008d177  test    eax, eax
0x18008d179  jns     short loc_18008D182
0x18008d17b  mov     edx, 0ABh
0x18008d180  jmp     short loc_18008D12A
0x18008d182  mov     rbx, [rbp+2Fh+var_50+8]
0x18008d186  mov     rdx, rbx; unsigned __int16 *
0x18008d189  mov     rcx, [rbp+2Fh+lpNewFileName+8]; lpFileName
0x18008d18d  call    ?Create@MountedFolder@Deployment@Common@@SAJPEBG0@Z; Common::Deployment::MountedFolder::Create(ushort const *,ushort const *)
0x18008d192  mov     edi, eax
0x18008d194  test    eax, eax
0x18008d196  jns     short loc_18008D1C7
0x18008d198  mov     rcx, [rbp+37h]; this
0x18008d19c  mov     r9d, eax; char *
0x18008d19f  lea     r8, aOnecoreAdminAp_117; "onecore\\admin\\appmodel\\common\\mutab"...
0x18008d1a6  mov     edx, 0ACh; void *
0x18008d1ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008d1b0  nop
0x18008d1b1  test    rbx, rbx
0x18008d1b4  jz      loc_18008D040
0x18008d1ba  mov     rcx, rbx; void *
0x18008d1bd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18008d1c2  jmp     loc_18008D040
0x18008d1c7  test    rbx, rbx
0x18008d1ca  jz      short loc_18008D1D5
0x18008d1cc  mov     rcx, rbx; void *
0x18008d1cf  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18008d1d4  nop
0x18008d1d5  mov     rcx, [rbp+2Fh+lpExistingFileName+8]; void *
0x18008d1d9  test    rcx, rcx
0x18008d1dc  jz      short loc_18008D1E4
0x18008d1de  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18008d1e3  nop
0x18008d1e4  mov     rcx, [rbp+2Fh+lpNewFileName+8]; void *
0x18008d1e8  test    rcx, rcx
0x18008d1eb  jz      short loc_18008D1F2
0x18008d1ed  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18008d1f2  xor     eax, eax
0x18008d1f4  add     rsp, 88h
0x18008d1fb  pop     r15
0x18008d1fd  pop     r14
0x18008d1ff  pop     r13
0x18008d201  pop     rdi
0x18008d202  pop     rbx
0x18008d203  pop     rbp
0x18008d204  retn
0x18008d206  mov     rdx, rdi
0x18008d209  mov     rcx, r14
0x18008d20c  call    ?Find@?$GenericMap@PEBGPEBG@Common@@QEAAPEBGPEBG@Z; Common::GenericMap<ushort const *,ushort const *>::Find(ushort const *)
0x18008d211  test    rax, rax
0x18008d214  jnz     short loc_18008D1D5
0x18008d216  mov     rax, [rbp+2Fh+arg_40]
0x18008d21a  mov     [rsp+0B0h+var_88], rax; struct StringSet *
0x18008d21f  mov     [rsp+0B0h+var_90], r14; struct _GUID *
0x18008d224  mov     r9, [rbp+2Fh+arg_20]; unsigned __int16 *
0x18008d228  mov     r8, rdi; pszPathIn
0x18008d22b  mov     rdx, r13; unsigned __int16 *
0x18008d22e  mov     rcx, r15; this
0x18008d231  call    ?CreateDirectoryTreeForFileWithReparsePoints@Common@@YAJPEBG00AEBU_GUID@@AEAVStringSet@@PEAV3@@Z; Common::CreateDirectoryTreeForFileWithReparsePoints(ushort const *,ushort const *,ushort const *,_GUID const &,StringSet &,StringSet *)
0x18008d236  mov     edi, eax
0x18008d238  test    eax, eax
0x18008d23a  jns     short loc_18008D246
0x18008d23c  mov     edx, 0B8h
0x18008d241  jmp     loc_18008D02C
0x18008d246  cmp     [rbp+2Fh+arg_30], 0
0x18008d24a  jnz     short loc_18008D297
0x18008d24c  test    dword ptr [rbx], 400h
0x18008d252  jnz     short loc_18008D297
0x18008d254  mov     rdx, [rbp+2Fh+lpNewFileName+8]; lpNewFileName
0x18008d258  mov     rcx, [rbp+2Fh+lpExistingFileName+8]; lpExistingFileName
0x18008d25c  call    cs:__imp_MoveFileW
0x18008d263  nop     dword ptr [rax+rax+00h]
0x18008d268  test    eax, eax
0x18008d26a  jz      short loc_18008D272
0x18008d26c  mov     bl, 1
0x18008d26e  xor     al, al
0x18008d270  jmp     short loc_18008D276
0x18008d272  xor     bl, bl
0x18008d274  mov     al, 1
0x18008d276  mov     rcx, [rbp+37h]; this
0x18008d27a  test    al, al
0x18008d27c  jz      short loc_18008D28F
0x18008d27e  lea     r8, aOnecoreAdminAp_117; "onecore\\admin\\appmodel\\common\\mutab"...
0x18008d285  mov     edx, 0C0h; void *
0x18008d28a  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18008d28f  test    bl, bl
0x18008d291  jnz     loc_18008D1D5
0x18008d297  xor     edx, edx; lpSecurityAttributes
0x18008d299  mov     rcx, [rbp+2Fh+lpNewFileName+8]; lpPathName
0x18008d29d  call    cs:__imp_CreateDirectoryW
0x18008d2a4  nop     dword ptr [rax+rax+00h]
0x18008d2a9  test    eax, eax
0x18008d2ab  jnz     short loc_18008D2E1
0x18008d2ad  call    cs:__imp_GetLastError
0x18008d2b4  nop     dword ptr [rax+rax+00h]
0x18008d2b9  mov     ebx, eax
0x18008d2bb  cmp     eax, 0B7h
0x18008d2c0  jz      short loc_18008D2E1
0x18008d2c2  test    eax, eax
0x18008d2c4  jle     short loc_18008D2CF
0x18008d2c6  movzx   ebx, ax
0x18008d2c9  or      ebx, 80070000h
0x18008d2cf  test    ebx, ebx
0x18008d2d1  jns     loc_18008CF83
0x18008d2d7  mov     edx, 0C9h
0x18008d2dc  jmp     loc_18008CF6F
0x18008d2e1  mov     rdx, [rbp+2Fh+lpNewFileName+8]; LPWSTR
0x18008d2e5  mov     rcx, [rbp+2Fh+lpExistingFileName+8]; pObjectName
0x18008d2e9  call    ?CopyPermissions@Deployment@Common@@YAJPEBG0@Z; Common::Deployment::CopyPermissions(ushort const *,ushort const *)
0x18008d2ee  mov     ebx, eax
0x18008d2f0  test    eax, eax
0x18008d2f2  jns     loc_18008D1D5
0x18008d2f8  mov     edx, 0CBh
0x18008d2fd  jmp     loc_18008CF6F
0x18008d302  test    eax, eax
0x18008d304  jz      short loc_18008D320
0x18008d306  cmp     dword ptr [rbx+24h], 80000018h
0x18008d30d  jz      loc_18008D1D5
0x18008d313  cmp     dword ptr [rbx+24h], 90001018h
0x18008d31a  jz      loc_18008D1D5
0x18008d320  cmp     byte ptr [rbp+2Fh+arg_28], 0
0x18008d324  jnz     short loc_18008D33D
0x18008d326  cmp     [rbp+2Fh+arg_30], 0
0x18008d32a  jnz     short loc_18008D33D
0x18008d32c  test    eax, eax
0x18008d32e  jz      short loc_18008D33D
0x18008d330  cmp     dword ptr [rbx+24h], 0A000001Fh
0x18008d337  jz      loc_18008D1D5
0x18008d33d  mov     rax, [rbp+2Fh+arg_40]
0x18008d341  mov     [rsp+0B0h+var_88], rax; struct StringSet *
0x18008d346  mov     [rsp+0B0h+var_90], r14; unsigned int
0x18008d34b  mov     r9, [rbp+2Fh+arg_20]; unsigned __int16 *
0x18008d34f  mov     r8, rdi; pszPathIn
0x18008d352  mov     rdx, r13; unsigned __int16 *
0x18008d355  mov     rcx, r15; this
0x18008d358  call    ?CreateDirectoryTreeForFileWithReparsePoints@Common@@YAJPEBG00AEBU_GUID@@AEAVStringSet@@PEAV3@@Z; Common::CreateDirectoryTreeForFileWithReparsePoints(ushort const *,ushort const *,ushort const *,_GUID const &,StringSet &,StringSet *)
0x18008d35d  mov     edi, eax
  ... truncated ...
```
