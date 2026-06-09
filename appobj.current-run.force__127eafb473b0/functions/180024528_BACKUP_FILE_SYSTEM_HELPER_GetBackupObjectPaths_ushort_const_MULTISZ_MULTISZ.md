# BACKUP_FILE_SYSTEM_HELPER::GetBackupObjectPaths(ushort const *,MULTISZ *,MULTISZ *)

- ea: `0x180024528`
- end: `0x18002484d`
- name: `?GetBackupObjectPaths@BACKUP_FILE_SYSTEM_HELPER@@SAJPEBGPEAVMULTISZ@@1@Z`
- size: `805`
- prototype: `static int(const unsigned __int16 *, struct MULTISZ *, struct MULTISZ *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x180023740`

## callees

- `0x180001fb0`
- `0x1800024e0`
- `0x180002640`
- `0x180002e90`
- `0x1800243c8`
- `0x180024528`
- `0x180032c08`
- `0x180033bc4`
- `0x180034cbe`
- `0x180034d00`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800246a9`
- `msvcrt!_wcsicmp` at `0x1800246c2`
- `msvcrt!_wcsicmp` at `0x1800246a9`
- `msvcrt!_wcsicmp` at `0x1800246c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002466c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800247bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002466c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800247bb`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18002481d`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18002481d`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18002465d`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18002465d`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180024772`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180024772`

## string_xrefs

- `0x18002459e`: `%windir%\system32\inetsrv\backup`

## pseudocode

```c
__int64 __fastcall BACKUP_FILE_SYSTEM_HELPER::GetBackupObjectPaths(
        const unsigned __int16 *a1,
        struct MULTISZ *a2,
        struct MULTISZ *a3)
{
  __int64 FirstFileW; // rdi
  signed int PathCanonicalizationProof; // ebx
  unsigned int i; // r14d
  const WCHAR *v9; // rcx
  signed int LastError; // eax
  signed int v11; // eax
  LPCWSTR lpSrc[2]; // [rsp+20h] [rbp-E0h]
  _QWORD v14[4]; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR lpFileName; // [rsp+50h] [rbp-B0h]
  int v16; // [rsp+58h] [rbp-A8h]
  __int16 v17; // [rsp+5Ch] [rbp-A4h]
  int v18; // [rsp+60h] [rbp-A0h]
  _QWORD v19[4]; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v20; // [rsp+88h] [rbp-78h]
  int v21; // [rsp+90h] [rbp-70h]
  __int16 v22; // [rsp+94h] [rbp-6Ch]
  int v23; // [rsp+98h] [rbp-68h]
  _QWORD v24[4]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *Src; // [rsp+C0h] [rbp-40h]
  int v26; // [rsp+C8h] [rbp-38h]
  __int16 v27; // [rsp+CCh] [rbp-34h]
  int v28; // [rsp+D0h] [rbp-30h]
  _WIN32_FIND_DATAW FindFileData; // [rsp+E0h] [rbp-20h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  if ( !a2 || **((_WORD **)a2 + 4) || !a3 || **((_WORD **)a3 + 4) )
    return (unsigned int)-2147024809;
  lpSrc[1] = a1;
  lpSrc[0] = L"%windir%\\system32\\inetsrv\\backup";
  FirstFileW = -1;
  PathCanonicalizationProof = 0;
  for ( i = 0; ; ++i )
  {
    if ( i >= 2 )
    {
      if ( *((_DWORD *)a2 + 13) != *((_DWORD *)a3 + 13) )
        PathCanonicalizationProof = -2147024809;
LABEL_33:
      if ( FirstFileW != -1 )
        goto LABEL_34;
      return (unsigned int)PathCanonicalizationProof;
    }
    v20 = (unsigned __int16 *)v19;
    v19[0] = 0;
    v21 = 32;
    v9 = lpSrc[i];
    v22 = 256;
    v23 = 0;
    v14[0] = 0;
    lpFileName = (LPCWSTR)v14;
    v16 = 32;
    v17 = 256;
    v18 = 0;
    PathCanonicalizationProof = BACKUP_FILE_SYSTEM_HELPER::ExpandEnvironmentStringsSTRU(v9, (struct STRU *)v19);
    if ( PathCanonicalizationProof < 0
      || (PathCanonicalizationProof = MakePathCanonicalizationProof(v20, (struct STRU *)v14),
          PathCanonicalizationProof < 0)
      || (PathCanonicalizationProof = STRU::Append((STRU *)v14, L"\\*"), PathCanonicalizationProof < 0) )
    {
      BUFFER::~BUFFER((BUFFER *)v14);
      BUFFER::~BUFFER((BUFFER *)v19);
      goto LABEL_33;
    }
    FirstFileW = (__int64)FindFirstFileW(lpFileName, &FindFileData);
    if ( FirstFileW != -1 )
      break;
    LastError = GetLastError();
    if ( (unsigned int)(LastError - 2) > 1 )
    {
      if ( LastError > 0 )
        PathCanonicalizationProof = (unsigned __int16)LastError | 0x80070000;
      else
        PathCanonicalizationProof = LastError;
      BUFFER::~BUFFER((BUFFER *)v14);
      BUFFER::~BUFFER((BUFFER *)v19);
      return (unsigned int)PathCanonicalizationProof;
    }
LABEL_24:
    BUFFER::~BUFFER((BUFFER *)v14);
    BUFFER::~BUFFER((BUFFER *)v19);
  }
  while ( 1 )
  {
    if ( (FindFileData.dwFileAttributes & 0x410) != 0x10
      || !_wcsicmp(FindFileData.cFileName, L".")
      || !_wcsicmp(FindFileData.cFileName, L"..") )
    {
      goto LABEL_23;
    }
    Src = (unsigned __int16 *)v24;
    v24[0] = 0;
    v26 = 32;
    v27 = 256;
    v28 = 0;
    PathCanonicalizationProof = STRU::Copy((STRU *)v24, v20);
    if ( PathCanonicalizationProof < 0 )
      goto LABEL_29;
    PathCanonicalizationProof = STRU::Append((STRU *)v24, L"\\");
    if ( PathCanonicalizationProof < 0 )
      goto LABEL_29;
    PathCanonicalizationProof = STRU::Append((STRU *)v24, FindFileData.cFileName);
    if ( PathCanonicalizationProof < 0 )
      goto LABEL_29;
    if ( !(unsigned int)MULTISZ::AuxAppend(a2, Src, (unsigned int)(2 * v28), 1)
      || !(unsigned int)MULTISZ::Append(a3, FindFileData.cFileName) )
    {
      break;
    }
    BUFFER::~BUFFER((BUFFER *)v24);
LABEL_23:
    if ( !FindNextFileW((HANDLE)FirstFileW, &FindFileData) )
      goto LABEL_24;
  }
  v11 = GetLastError();
  PathCanonicalizationProof = v11;
  if ( v11 > 0 )
    PathCanonicalizationProof = (unsigned __int16)v11 | 0x80070000;
LABEL_29:
  BUFFER::~BUFFER((BUFFER *)v24);
  BUFFER::~BUFFER((BUFFER *)v14);
  BUFFER::~BUFFER((BUFFER *)v19);
LABEL_34:
  FindClose((HANDLE)FirstFileW);
  return (unsigned int)PathCanonicalizationProof;
}

```

## disassembly

```asm
0x180024528  push    rbp
0x18002452a  push    rbx
0x18002452b  push    rsi
0x18002452c  push    rdi
0x18002452d  push    r12
0x18002452f  push    r14
0x180024531  push    r15
0x180024533  lea     rbp, [rsp-240h]
0x18002453b  sub     rsp, 340h
0x180024542  mov     rax, cs:__security_cookie
0x180024549  xor     rax, rsp
0x18002454c  mov     [rbp+270h+var_40], rax
0x180024553  mov     rsi, r8
0x180024556  mov     r15, rdx
0x180024559  mov     r14, rcx
0x18002455c  xor     edx, edx; Val
0x18002455e  mov     r8d, 250h; Size
0x180024564  lea     rcx, [rbp+270h+FindFileData]; void *
0x180024568  call    memset_0
0x18002456d  xor     r12d, r12d
0x180024570  test    r15, r15
0x180024573  jz      loc_180024825
0x180024579  mov     rax, [r15+20h]
0x18002457d  cmp     [rax], r12w
0x180024581  jnz     loc_180024825
0x180024587  test    rsi, rsi
0x18002458a  jz      loc_180024825
0x180024590  mov     rax, [rsi+20h]
0x180024594  cmp     [rax], r12w
0x180024598  jnz     loc_180024825
0x18002459e  lea     rax, Src; "%windir%\\system32\\inetsrv\\backup"
0x1800245a5  mov     [rsp+370h+var_348], r14
0x1800245aa  mov     [rsp+370h+lpSrc], rax
0x1800245af  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800245b3  mov     ebx, r12d
0x1800245b6  mov     r14d, r12d
0x1800245b9  cmp     r14d, 2
0x1800245bd  jnb     loc_180024805
0x1800245c3  lea     rax, [rsp+370h+var_308]
0x1800245c8  mov     ecx, r14d
0x1800245cb  mov     [rbp+270h+var_2E8], rax
0x1800245cf  lea     rdx, [rsp+370h+var_308]; this
0x1800245d4  lea     rax, [rsp+370h+var_340]
0x1800245d9  mov     [rsp+370h+var_308], r12
0x1800245de  mov     [rbp+270h+var_2E0], 20h ; ' '
0x1800245e5  mov     rcx, [rsp+rcx*8+370h+lpSrc]; lpSrc
0x1800245ea  mov     [rbp+270h+var_2DC], 100h
0x1800245f0  mov     [rbp+270h+var_2D8], r12d
0x1800245f4  mov     [rsp+370h+var_340], r12
0x1800245f9  mov     [rsp+370h+lpFileName], rax
0x1800245fe  mov     [rsp+370h+var_318], 20h ; ' '
0x180024606  mov     [rsp+370h+var_314], 100h
0x18002460d  mov     [rsp+370h+var_310], r12d
0x180024612  call    ?ExpandEnvironmentStringsSTRU@BACKUP_FILE_SYSTEM_HELPER@@CAJPEBGPEAVSTRU@@@Z; BACKUP_FILE_SYSTEM_HELPER::ExpandEnvironmentStringsSTRU(ushort const *,STRU *)
0x180024617  mov     ebx, eax
0x180024619  test    eax, eax
0x18002461b  js      loc_1800247EF
0x180024621  mov     rcx, [rbp+270h+var_2E8]; unsigned __int16 *
0x180024625  lea     rdx, [rsp+370h+var_340]; this
0x18002462a  call    ?MakePathCanonicalizationProof@@YAJPEBGPEAVSTRU@@@Z; MakePathCanonicalizationProof(ushort const *,STRU *)
0x18002462f  lea     rcx, [rsp+370h+var_340]; this
0x180024634  mov     ebx, eax
0x180024636  test    eax, eax
0x180024638  js      loc_1800247F4
0x18002463e  lea     rdx, asc_18004D864; "\\*"
0x180024645  call    ?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18002464a  mov     ebx, eax
0x18002464c  test    eax, eax
0x18002464e  js      loc_1800247EF
0x180024654  mov     rcx, [rsp+370h+lpFileName]; lpFileName
0x180024659  lea     rdx, [rbp+270h+FindFileData]; lpFindFileData
0x18002465d  call    cs:__imp_FindFirstFileW
0x180024663  mov     rdi, rax
0x180024666  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002466a  jnz     short loc_18002468D
0x18002466c  call    cs:__imp_GetLastError
0x180024672  lea     ecx, [rax-2]
0x180024675  cmp     ecx, 1
0x180024678  jbe     loc_180024780
0x18002467e  test    eax, eax
0x180024680  jg      loc_18002479C
0x180024686  mov     ebx, eax
0x180024688  jmp     loc_1800247A5
0x18002468d  mov     eax, [rbp+270h+FindFileData.dwFileAttributes]
0x180024690  and     eax, 410h
0x180024695  cmp     eax, 10h
0x180024698  jnz     loc_18002476B
0x18002469e  lea     rdx, asc_180039808; "."
0x1800246a5  lea     rcx, [rbp+270h+FindFileData.cFileName]; String1
0x1800246a9  call    cs:__imp__wcsicmp
0x1800246af  test    eax, eax
0x1800246b1  jz      loc_18002476B
0x1800246b7  lea     rdx, asc_18004D86C; ".."
0x1800246be  lea     rcx, [rbp+270h+FindFileData.cFileName]; String1
0x1800246c2  call    cs:__imp__wcsicmp
0x1800246c8  test    eax, eax
0x1800246ca  jz      loc_18002476B
0x1800246d0  mov     rdx, [rbp+270h+var_2E8]; unsigned __int16 *
0x1800246d4  lea     rax, [rbp+270h+var_2D0]
0x1800246d8  lea     rcx, [rbp+270h+var_2D0]; this
0x1800246dc  mov     [rbp+270h+Src], rax
0x1800246e0  mov     [rbp+270h+var_2D0], r12
0x1800246e4  mov     [rbp+270h+var_2A8], 20h ; ' '
0x1800246eb  mov     [rbp+270h+var_2A4], 100h
0x1800246f1  mov     [rbp+270h+var_2A0], r12d
0x1800246f5  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800246fa  mov     ebx, eax
0x1800246fc  test    eax, eax
0x1800246fe  js      loc_1800247D0
0x180024704  lea     rdx, asc_180039420; "\\"
0x18002470b  lea     rcx, [rbp+270h+var_2D0]; this
0x18002470f  call    ?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180024714  mov     ebx, eax
0x180024716  test    eax, eax
0x180024718  js      loc_1800247D0
0x18002471e  lea     rdx, [rbp+270h+FindFileData.cFileName]; unsigned __int16 *
0x180024722  lea     rcx, [rbp+270h+var_2D0]; this
0x180024726  call    ?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18002472b  mov     ebx, eax
0x18002472d  test    eax, eax
0x18002472f  js      loc_1800247D0
0x180024735  mov     r8d, [rbp+270h+var_2A0]
0x180024739  mov     r9d, 1; int
0x18002473f  mov     rdx, [rbp+270h+Src]; Src
0x180024743  add     r8d, r8d; Size
0x180024746  mov     rcx, r15; this
0x180024749  call    ?AuxAppend@MULTISZ@@AEAAHPEBGIH@Z; MULTISZ::AuxAppend(ushort const *,uint,int)
0x18002474e  test    eax, eax
0x180024750  jz      short loc_1800247BB
0x180024752  lea     rdx, [rbp+270h+FindFileData.cFileName]; unsigned __int16 *
0x180024756  mov     rcx, rsi; this
0x180024759  call    ?Append@MULTISZ@@QEAAHPEBG@Z; MULTISZ::Append(ushort const *)
0x18002475e  test    eax, eax
0x180024760  jz      short loc_1800247BB
0x180024762  lea     rcx, [rbp+270h+var_2D0]; this
0x180024766  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18002476b  lea     rdx, [rbp+270h+FindFileData]; lpFindFileData
0x18002476f  mov     rcx, rdi; hFindFile
0x180024772  call    cs:__imp_FindNextFileW
0x180024778  test    eax, eax
0x18002477a  jnz     loc_18002468D
0x180024780  lea     rcx, [rsp+370h+var_340]; this
0x180024785  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18002478a  lea     rcx, [rsp+370h+var_308]; this
0x18002478f  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180024794  inc     r14d
0x180024797  jmp     loc_1800245B9
0x18002479c  movzx   ebx, ax
0x18002479f  or      ebx, 80070000h
0x1800247a5  lea     rcx, [rsp+370h+var_340]; this
0x1800247aa  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800247af  lea     rcx, [rsp+370h+var_308]; this
0x1800247b4  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800247b9  jmp     short loc_18002482A
0x1800247bb  call    cs:__imp_GetLastError
0x1800247c1  mov     ebx, eax
0x1800247c3  test    eax, eax
0x1800247c5  jle     short loc_1800247D0
0x1800247c7  movzx   ebx, ax
0x1800247ca  or      ebx, 80070000h
0x1800247d0  lea     rcx, [rbp+270h+var_2D0]; this
0x1800247d4  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800247d9  lea     rcx, [rsp+370h+var_340]; this
0x1800247de  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800247e3  lea     rcx, [rsp+370h+var_308]; this
0x1800247e8  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800247ed  jmp     short loc_18002481A
0x1800247ef  lea     rcx, [rsp+370h+var_340]; this
0x1800247f4  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800247f9  lea     rcx, [rsp+370h+var_308]; this
0x1800247fe  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180024803  jmp     short loc_180024814
0x180024805  mov     eax, [rsi+34h]
0x180024808  mov     ecx, 80070057h
0x18002480d  cmp     [r15+34h], eax
0x180024811  cmovnz  ebx, ecx
0x180024814  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180024818  jz      short loc_18002482A
0x18002481a  mov     rcx, rdi; hFindFile
0x18002481d  call    cs:__imp_FindClose
0x180024823  jmp     short loc_18002482A
0x180024825  mov     ebx, 80070057h
0x18002482a  mov     eax, ebx
0x18002482c  mov     rcx, [rbp+270h+var_40]
0x180024833  xor     rcx, rsp; StackCookie
0x180024836  call    __security_check_cookie
0x18002483b  add     rsp, 340h
0x180024842  pop     r15
0x180024844  pop     r14
0x180024846  pop     r12
0x180024848  pop     rdi
0x180024849  pop     rsi
0x18002484a  pop     rbx
0x18002484b  pop     rbp
0x18002484c  retn
```
