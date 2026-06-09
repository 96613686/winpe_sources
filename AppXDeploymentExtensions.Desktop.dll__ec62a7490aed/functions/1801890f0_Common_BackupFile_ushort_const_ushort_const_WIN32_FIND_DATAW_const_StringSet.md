# Common::BackupFile(ushort const *,ushort const *,_WIN32_FIND_DATAW const *,StringSet *)

- ea: `0x1801890f0`
- end: `0x180189414`
- name: `?BackupFile@Common@@YAJPEBG0PEBU_WIN32_FIND_DATAW@@PEAVStringSet@@@Z`
- size: `804`
- prototype: `__int64 __fastcall(Common *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const struct _WIN32_FIND_DATAW *, struct StringSet *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x18009f5cc`

## callees

- `0x18001adb4`
- `0x1800685b8`
- `0x180069eb4`
- `0x180081354`
- `0x1800991e8`
- `0x18009d9b8`
- `0x1800af1bc`
- `0x180117710`
- `0x1801890f0`
- `0x180189558`
- `0x180189600`
- `0x180189b68`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801891e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801893bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801891e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801893bd`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1801891d4`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1801891d4`
- `api-ms-win-core-file-l2-1-0!CreateHardLinkW` at `0x1801893ad`
- `api-ms-win-core-file-l2-1-0!CreateHardLinkW` at `0x1801893ad`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x1801891a5`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x1801891a5`

## string_xrefs

- `0x18018913b`: `onecore\admin\appmodel\common\mutabledirectoryhelper.cpp`
- `0x1801891be`: `onecore\admin\appmodel\common\mutabledirectoryhelper.cpp`
- `0x1801892af`: `onecore\admin\appmodel\common\mutabledirectoryhelper.cpp`
- `0x1801892f0`: `onecore\admin\appmodel\common\mutabledirectoryhelper.cpp`
- `0x180189338`: `onecore\admin\appmodel\common\mutabledirectoryhelper.cpp`
- `0x1801893fe`: `onecore\admin\appmodel\common\mutabledirectoryhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Common::BackupFile(WCHAR *this, Common *a2, struct StringSet *a3, struct _WIN32_FIND_DATAW *a4)
{
  int v8; // ecx
  const unsigned __int16 *v9; // rax
  int DirectoryTreeForFile; // ebx
  __int64 v11; // rdx
  const unsigned __int16 *v13; // r8
  const char *v14; // r9
  const unsigned __int16 *v15; // r8
  signed int v16; // eax
  const unsigned __int16 *v17; // rdx
  bool v18; // r8
  int Target; // eax
  struct StringSet *v20; // r8
  unsigned int v21; // esi
  const struct std::nothrow_t *v22; // rdx
  int v23; // eax
  const struct std::nothrow_t *v24; // rdx
  unsigned __int16 *v25; // rbx
  int v26; // eax
  const struct std::nothrow_t *v27; // rdx
  unsigned int v28; // edi
  const struct std::nothrow_t *v29; // rdx
  DWORD LastError; // eax
  const struct _WIN32_FIND_DATAW *v31; // r9
  unsigned __int16 *v32[2]; // [rsp+20h] [rbp-48h] BYREF
  int v33; // [rsp+30h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v8 = *(_DWORD *)a3 & 0x400;
  v9 = (const unsigned __int16 *)((char *)a3 + 36);
  if ( v8 && *(_DWORD *)v9 == -1610612724 )
  {
    DirectoryTreeForFile = Common::CreateDirectoryTreeForFile(a2, (StringSet *)a4, a3);
    if ( DirectoryTreeForFile < 0 )
    {
      v11 = 259;
      goto LABEL_5;
    }
    v13 = (const unsigned __int16 *)(*(_DWORD *)a3 >> 4);
    LOBYTE(v13) = (*(_DWORD *)a3 & 0x10) != 0;
    DirectoryTreeForFile = StatePaths::CopySymbolicLink(this, (const unsigned __int16 *)a2, v13);
    if ( DirectoryTreeForFile < 0 )
    {
      v11 = 264;
      goto LABEL_5;
    }
    return 0;
  }
  if ( (*(_BYTE *)a3 & 0x10) == 0 )
  {
    if ( !v8 || *(_DWORD *)v9 != -2147483624 && *(_DWORD *)v9 != -1879044072 )
    {
      DirectoryTreeForFile = Common::CreateDirectoryTreeForFile(a2, (StringSet *)a4, a3);
      if ( DirectoryTreeForFile < 0 )
      {
        v11 = 313;
        goto LABEL_5;
      }
      if ( !CreateHardLinkW((LPCWSTR)a2, this, 0) )
      {
        LastError = GetLastError();
        if ( LastError == 1142 )
        {
          DirectoryTreeForFile = Common::CopyModifiedFileOrAddOn(
                                   (Common *)this,
                                   (const unsigned __int16 *)a2,
                                   (const unsigned __int16 *)a3,
                                   v31);
          if ( DirectoryTreeForFile < 0 )
          {
            v11 = 322;
            goto LABEL_5;
          }
        }
        else if ( LastError )
        {
          return wil::details::in1diag3::Return_Win32(
                   retaddr,
                   (void *)0x146,
                   (unsigned int)"onecore\\admin\\appmodel\\common\\mutabledirectoryhelper.cpp",
                   (const char *)LastError,
                   (unsigned int)v32[0]);
        }
      }
    }
    return 0;
  }
  if ( !v8 )
  {
    DirectoryTreeForFile = Common::CreateDirectoryTreeForFile(a2, (StringSet *)a4, a3);
    if ( DirectoryTreeForFile < 0 )
    {
      v11 = 275;
      goto LABEL_5;
    }
    if ( !MoveFileW(this, (LPCWSTR)a2) )
    {
      wil::details::in1diag3::Log_GetLastError(
        retaddr,
        (void *)0x117,
        (unsigned int)"onecore\\admin\\appmodel\\common\\mutabledirectoryhelper.cpp",
        v14);
      if ( !CreateDirectoryW((LPCWSTR)a2, 0) )
      {
        v16 = GetLastError();
        DirectoryTreeForFile = v16;
        if ( v16 != 183 )
        {
          if ( v16 > 0 )
            DirectoryTreeForFile = (unsigned __int16)v16 | 0x80070000;
          if ( DirectoryTreeForFile >= 0 )
            return (unsigned int)DirectoryTreeForFile;
          v11 = 283;
LABEL_5:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v11,
            (unsigned int)"onecore\\admin\\appmodel\\common\\mutabledirectoryhelper.cpp",
            (const char *)(unsigned int)DirectoryTreeForFile,
            (int)v32[0]);
          return (unsigned int)DirectoryTreeForFile;
        }
      }
      DirectoryTreeForFile = Common::Deployment::CopyPermissions(this, (LPWSTR)a2, v15);
      if ( DirectoryTreeForFile < 0 )
      {
        v11 = 285;
        goto LABEL_5;
      }
    }
    return 0;
  }
  if ( *(_DWORD *)v9 == -1610612705 )
  {
    DirectoryTreeForFile = Common::CreateDirectoryTreeForFile(a2, (StringSet *)a4, a3);
    if ( DirectoryTreeForFile < 0 )
    {
      v11 = 291;
      goto LABEL_5;
    }
    LOBYTE(v17) = 1;
    DirectoryTreeForFile = Common::CreateTombstoneFile(a2, v17, v18);
    if ( DirectoryTreeForFile < 0 )
    {
      v11 = 294;
      goto LABEL_5;
    }
    return 0;
  }
  if ( *(_DWORD *)v9 != -1610612733 )
    return 0;
  *(_OWORD *)v32 = 0;
  v33 = 0;
  Target = Common::Deployment::MountedFolder::GetTarget(this, (struct Common::StringBuffer *)v32);
  v21 = Target;
  if ( Target < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12B,
      (unsigned int)"onecore\\admin\\appmodel\\common\\mutabledirectoryhelper.cpp",
      (const char *)(unsigned int)Target,
      (int)v32[0]);
    if ( v32[1] )
      operator delete(v32[1], v22);
    return v21;
  }
  v23 = Common::CreateDirectoryTreeForFile(a2, (StringSet *)a4, v20);
  DirectoryTreeForFile = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12C,
      (unsigned int)"onecore\\admin\\appmodel\\common\\mutabledirectoryhelper.cpp",
      (const char *)(unsigned int)v23,
      (int)v32[0]);
    if ( v32[1] )
      operator delete(v32[1], v24);
    return (unsigned int)DirectoryTreeForFile;
  }
  v25 = v32[1];
  v26 = Common::Deployment::MountedFolder::Create((LPCWSTR)a2, v32[1]);
  v28 = v26;
  if ( v26 >= 0 )
  {
    if ( v25 )
      operator delete(v25, v27);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x12D,
    (unsigned int)"onecore\\admin\\appmodel\\common\\mutabledirectoryhelper.cpp",
    (const char *)(unsigned int)v26,
    (int)v32[0]);
  if ( v25 )
    operator delete(v25, v29);
  return v28;
}

```

## disassembly

```asm
0x1801890f0  push    rbx
0x1801890f2  push    rsi
0x1801890f3  push    rdi
0x1801890f4  push    r14
0x1801890f6  sub     rsp, 48h
0x1801890fa  mov     rbx, r9
0x1801890fd  mov     r14, r8
0x180189100  mov     rdi, rdx
0x180189103  mov     rsi, rcx
0x180189106  mov     ecx, [r8]
0x180189109  and     ecx, 400h
0x18018910f  lea     rax, [r8+24h]
0x180189113  jz      short loc_180189175
0x180189115  cmp     dword ptr [rax], 0A000000Ch
0x18018911b  jnz     short loc_180189175
0x18018911d  mov     rdx, rbx; StringSet *
0x180189120  mov     rcx, rdi; this
0x180189123  call    ?CreateDirectoryTreeForFile@Common@@YAJPEBGPEAVStringSet@@@Z; Common::CreateDirectoryTreeForFile(ushort const *,StringSet *)
0x180189128  mov     ebx, eax
0x18018912a  test    eax, eax
0x18018912c  jns     short loc_18018914E
0x18018912e  mov     edx, 103h; void *
0x180189133  mov     rcx, [rsp+68h]; this
0x180189138  mov     r9d, ebx; char *
0x18018913b  lea     r8, aOnecoreAdminAp_117; "onecore\\admin\\appmodel\\common\\mutab"...
0x180189142  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180189147  mov     eax, ebx
0x180189149  jmp     loc_18018936A
0x18018914e  mov     r8d, [r14]
0x180189151  shr     r8d, 4
0x180189155  and     r8b, 1; unsigned __int16 *
0x180189159  mov     rdx, rdi; unsigned __int16 *
0x18018915c  mov     rcx, rsi; this
0x18018915f  call    ?CopySymbolicLink@StatePaths@@YAJPEBG0_N@Z; StatePaths::CopySymbolicLink(ushort const *,ushort const *,bool)
0x180189164  mov     ebx, eax
0x180189166  test    eax, eax
0x180189168  jns     loc_180189368
0x18018916e  mov     edx, 108h
0x180189173  jmp     short loc_180189133
0x180189175  test    byte ptr [r8], 10h
0x180189179  jz      loc_180189375
0x18018917f  test    ecx, ecx
0x180189181  jnz     loc_180189237
0x180189187  mov     rdx, rbx; StringSet *
0x18018918a  mov     rcx, rdi; this
0x18018918d  call    ?CreateDirectoryTreeForFile@Common@@YAJPEBGPEAVStringSet@@@Z; Common::CreateDirectoryTreeForFile(ushort const *,StringSet *)
0x180189192  mov     ebx, eax
0x180189194  test    eax, eax
0x180189196  jns     short loc_18018919F
0x180189198  mov     edx, 113h
0x18018919d  jmp     short loc_180189133
0x18018919f  mov     rdx, rdi; lpNewFileName
0x1801891a2  mov     rcx, rsi; lpExistingFileName
0x1801891a5  call    cs:__imp_MoveFileW
0x1801891ac  nop     dword ptr [rax+rax+00h]
0x1801891b1  test    eax, eax
0x1801891b3  jnz     loc_180189368
0x1801891b9  mov     rcx, [rsp+68h]; this
0x1801891be  lea     r8, aOnecoreAdminAp_117; "onecore\\admin\\appmodel\\common\\mutab"...
0x1801891c5  mov     edx, 117h; void *
0x1801891ca  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x1801891cf  xor     edx, edx; lpSecurityAttributes
0x1801891d1  mov     rcx, rdi; lpPathName
0x1801891d4  call    cs:__imp_CreateDirectoryW
0x1801891db  nop     dword ptr [rax+rax+00h]
0x1801891e0  test    eax, eax
0x1801891e2  jnz     short loc_180189218
0x1801891e4  call    cs:__imp_GetLastError
0x1801891eb  nop     dword ptr [rax+rax+00h]
0x1801891f0  mov     ebx, eax
0x1801891f2  cmp     eax, 0B7h
0x1801891f7  jz      short loc_180189218
0x1801891f9  test    eax, eax
0x1801891fb  jle     short loc_180189206
0x1801891fd  movzx   ebx, ax
0x180189200  or      ebx, 80070000h
0x180189206  test    ebx, ebx
0x180189208  jns     loc_180189147
0x18018920e  mov     edx, 11Bh
0x180189213  jmp     loc_180189133
0x180189218  mov     rdx, rdi; LPWSTR
0x18018921b  mov     rcx, rsi; pObjectName
0x18018921e  call    ?CopyPermissions@Deployment@Common@@YAJPEBG0@Z; Common::Deployment::CopyPermissions(ushort const *,ushort const *)
0x180189223  mov     ebx, eax
0x180189225  test    eax, eax
0x180189227  jns     loc_180189368
0x18018922d  mov     edx, 11Dh
0x180189232  jmp     loc_180189133
0x180189237  mov     ecx, [rax]
0x180189239  cmp     ecx, 0A000001Fh
0x18018923f  jnz     short loc_18018927A
0x180189241  mov     rdx, rbx; StringSet *
0x180189244  mov     rcx, rdi; this
0x180189247  call    ?CreateDirectoryTreeForFile@Common@@YAJPEBGPEAVStringSet@@@Z; Common::CreateDirectoryTreeForFile(ushort const *,StringSet *)
0x18018924c  mov     ebx, eax
0x18018924e  test    eax, eax
0x180189250  jns     short loc_18018925C
0x180189252  mov     edx, 123h
0x180189257  jmp     loc_180189133
0x18018925c  mov     dl, 1; unsigned __int16 *
0x18018925e  mov     rcx, rdi; this
0x180189261  call    ?CreateTombstoneFile@Common@@YAJPEBG_N@Z; Common::CreateTombstoneFile(ushort const *,bool)
0x180189266  mov     ebx, eax
0x180189268  test    eax, eax
0x18018926a  jns     loc_180189368
0x180189270  mov     edx, 126h
0x180189275  jmp     loc_180189133
0x18018927a  cmp     ecx, 0A0000003h
0x180189280  jnz     loc_180189368
0x180189286  xor     eax, eax
0x180189288  xorps   xmm0, xmm0
0x18018928b  movups  xmmword ptr [rsp+68h+var_48], xmm0; int
0x180189290  mov     [rsp+68h+var_38], eax
0x180189294  lea     rdx, [rsp+68h+var_48]; struct Common::StringBuffer *
0x180189299  mov     rcx, rsi; unsigned __int16 *
0x18018929c  call    ?GetTarget@MountedFolder@Deployment@Common@@SAJPEBGPEAVStringBuffer@3@@Z; Common::Deployment::MountedFolder::GetTarget(ushort const *,Common::StringBuffer *)
0x1801892a1  mov     esi, eax
0x1801892a3  test    eax, eax
0x1801892a5  jns     short loc_1801892D7
0x1801892a7  mov     rcx, [rsp+68h]; this
0x1801892ac  mov     r9d, eax; char *
0x1801892af  lea     r8, aOnecoreAdminAp_117; "onecore\\admin\\appmodel\\common\\mutab"...
0x1801892b6  mov     edx, 12Bh; void *
0x1801892bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801892c0  nop
0x1801892c1  mov     rcx, [rsp+68h+var_48+8]; void *
0x1801892c6  test    rcx, rcx
0x1801892c9  jz      short loc_1801892D0
0x1801892cb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801892d0  mov     eax, esi
0x1801892d2  jmp     loc_18018936A
0x1801892d7  mov     rdx, rbx; StringSet *
0x1801892da  mov     rcx, rdi; this
0x1801892dd  call    ?CreateDirectoryTreeForFile@Common@@YAJPEBGPEAVStringSet@@@Z; Common::CreateDirectoryTreeForFile(ushort const *,StringSet *)
0x1801892e2  mov     ebx, eax
0x1801892e4  test    eax, eax
0x1801892e6  jns     short loc_18018931A
0x1801892e8  mov     rcx, [rsp+68h]; this
0x1801892ed  mov     r9d, eax; char *
0x1801892f0  lea     r8, aOnecoreAdminAp_117; "onecore\\admin\\appmodel\\common\\mutab"...
0x1801892f7  mov     edx, 12Ch; void *
0x1801892fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180189301  nop
0x180189302  mov     rcx, [rsp+68h+var_48+8]; void *
0x180189307  test    rcx, rcx
0x18018930a  jz      loc_180189147
0x180189310  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180189315  jmp     loc_180189147
0x18018931a  mov     rbx, [rsp+68h+var_48+8]
0x18018931f  mov     rdx, rbx; unsigned __int16 *
0x180189322  mov     rcx, rdi; lpFileName
0x180189325  call    ?Create@MountedFolder@Deployment@Common@@SAJPEBG0@Z; Common::Deployment::MountedFolder::Create(ushort const *,ushort const *)
0x18018932a  mov     edi, eax
0x18018932c  test    eax, eax
0x18018932e  jns     short loc_18018935B
0x180189330  mov     rcx, [rsp+68h]; this
0x180189335  mov     r9d, eax; char *
0x180189338  lea     r8, aOnecoreAdminAp_117; "onecore\\admin\\appmodel\\common\\mutab"...
0x18018933f  mov     edx, 12Dh; void *
0x180189344  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180189349  nop
0x18018934a  test    rbx, rbx
0x18018934d  jz      short loc_180189357
0x18018934f  mov     rcx, rbx; void *
0x180189352  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180189357  mov     eax, edi
0x180189359  jmp     short loc_18018936A
0x18018935b  test    rbx, rbx
0x18018935e  jz      short loc_180189368
0x180189360  mov     rcx, rbx; void *
0x180189363  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180189368  xor     eax, eax
0x18018936a  add     rsp, 48h
0x18018936e  pop     r14
0x180189370  pop     rdi
0x180189371  pop     rsi
0x180189372  pop     rbx
0x180189373  retn
0x180189375  test    ecx, ecx
0x180189377  jz      short loc_180189389
0x180189379  cmp     dword ptr [rax], 80000018h
0x18018937f  jz      short loc_180189368
0x180189381  cmp     dword ptr [rax], 90001018h
0x180189387  jz      short loc_180189368
0x180189389  mov     rdx, rbx; StringSet *
0x18018938c  mov     rcx, rdi; this
0x18018938f  call    ?CreateDirectoryTreeForFile@Common@@YAJPEBGPEAVStringSet@@@Z; Common::CreateDirectoryTreeForFile(ushort const *,StringSet *)
0x180189394  mov     ebx, eax
0x180189396  test    eax, eax
0x180189398  jns     short loc_1801893A4
0x18018939a  mov     edx, 139h
0x18018939f  jmp     loc_180189133
0x1801893a4  xor     r8d, r8d; lpSecurityAttributes
0x1801893a7  mov     rdx, rsi; lpExistingFileName
0x1801893aa  mov     rcx, rdi; lpFileName
0x1801893ad  call    cs:__imp_CreateHardLinkW
0x1801893b4  nop     dword ptr [rax+rax+00h]
0x1801893b9  test    eax, eax
0x1801893bb  jnz     short loc_180189368
0x1801893bd  call    cs:__imp_GetLastError
0x1801893c4  nop     dword ptr [rax+rax+00h]
0x1801893c9  cmp     eax, 476h
0x1801893ce  jnz     short loc_1801893EE
0x1801893d0  mov     r8, r14; unsigned __int16 *
0x1801893d3  mov     rdx, rdi; unsigned __int16 *
0x1801893d6  mov     rcx, rsi; this
0x1801893d9  call    ?CopyModifiedFileOrAddOn@Common@@YAJPEBG0PEBU_WIN32_FIND_DATAW@@@Z; Common::CopyModifiedFileOrAddOn(ushort const *,ushort const *,_WIN32_FIND_DATAW const *)
0x1801893de  mov     ebx, eax
0x1801893e0  test    eax, eax
0x1801893e2  jns     short loc_180189368
0x1801893e4  mov     edx, 142h
0x1801893e9  jmp     loc_180189133
0x1801893ee  test    eax, eax
0x1801893f0  jz      loc_180189368
0x1801893f6  mov     rcx, [rsp+68h]; this
0x1801893fb  mov     r9d, eax; char *
0x1801893fe  lea     r8, aOnecoreAdminAp_117; "onecore\\admin\\appmodel\\common\\mutab"...
0x180189405  mov     edx, 146h; void *
0x18018940a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18018940f  jmp     loc_18018936A
```
