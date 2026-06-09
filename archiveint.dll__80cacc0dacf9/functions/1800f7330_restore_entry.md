# restore_entry

- ea: `0x1800f7330`
- end: `0x1800f7888`
- name: `restore_entry`
- size: `1368`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, reparse_path`

## callers

- `0x1800f5030`

## callees

- `0x180006c00`
- `0x1800149c0`
- `0x180014fc0`
- `0x1800b1ce0`
- `0x1800ed6c0`
- `0x1800ee614`
- `0x1800ef3f8`
- `0x1800f5e24`
- `0x1800f6098`
- `0x1800f656c`
- `0x1800f65c4`
- `0x1800f661c`
- `0x1800f6cd0`
- `0x1800f7330`
- `0x1800f7890`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f73b1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f73cc`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f7555`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f75b1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f7757`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f77a9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f77c4`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f73b1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f73cc`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f7555`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f75b1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f7757`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f77a9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f77c4`
- `api-ms-win-crt-private-l1-1-0!_o__get_osfhandle` at `0x1800f776b`
- `api-ms-win-crt-private-l1-1-0!_o__get_osfhandle` at `0x1800f776b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f74a0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f74a0`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800f742f`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800f742f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f774a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f7782`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f774a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f7782`

## string_xrefs

- `0x1800f73d2`: `Could not unlink`
- `0x1800f74df`: `Hard-link target '%s' does not exist.`
- `0x1800f755b`: `Can't remove already-existing dir`
- `0x1800f76dc`: `Refusing to overwrite archive`
- `0x1800f775d`: `Can't create temporary file`
- `0x1800f77af`: `Can't unlink directory symlink`
- `0x1800f77ca`: `Can't unlink already-existing object`
- `0x1800f7835`: `Can't create '%ls'`

## pseudocode

```c
__int64 __fastcall restore_entry(__int64 a1)
{
  int v2; // ecx
  unsigned int *v3; // rax
  unsigned int filesystem_object; // eax
  unsigned int v6; // ebx
  const wchar_t *v7; // rsi
  wchar_t *v8; // rax
  wchar_t *v9; // rbx
  wchar_t *v10; // rax
  wchar_t *v11; // rsi
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 v14; // rax
  unsigned int *v15; // rax
  const WCHAR *v16; // rdx
  unsigned int *v17; // rax
  __int16 v18; // si
  DWORD v19; // r14d
  DWORD nFileIndexLow; // eax
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  int v23; // r11d
  __int64 v24; // r10
  int v25; // eax
  DWORD LastError; // eax
  unsigned int *v27; // rax
  intptr_t osfhandle; // rax
  DWORD v29; // eax
  const WCHAR *v30; // rcx
  unsigned int *v31; // rax
  unsigned int *v32; // rax
  __int16 v33; // cx
  int v34; // eax
  _WORD v35[2]; // [rsp+30h] [rbp-49h] BYREF
  int v36; // [rsp+34h] [rbp-45h] BYREF
  __int64 v37; // [rsp+38h] [rbp-41h]
  __int64 v38; // [rsp+40h] [rbp-39h] BYREF
  struct _BY_HANDLE_FILE_INFORMATION v39; // [rsp+48h] [rbp-31h] BYREF

  v2 = *(_DWORD *)(a1 + 424);
  if ( (v2 & 0x10) == 0 || (*(_WORD *)(a1 + 476) & 0xF000) == 0x4000 )
    goto LABEL_11;
  if ( (v2 & 0x20000) != 0 )
    set_fflags_platform(*(LPCWSTR *)(a1 + 352));
  if ( (unsigned int)disk_unlink(*(LPCWSTR *)(a1 + 352)) )
  {
    if ( *(_DWORD *)_o__errno() == 2 )
      goto LABEL_11;
    if ( (unsigned int)disk_rmdir(*(LPCWSTR *)(a1 + 352)) )
    {
      v3 = (unsigned int *)_o__errno();
      archive_set_error(a1, *v3, "Could not unlink");
      return 4294967271LL;
    }
  }
  *(_QWORD *)(a1 + 336) = 0;
LABEL_11:
  filesystem_object = create_filesystem_object(a1);
  v6 = filesystem_object;
  if ( filesystem_object == 20 || filesystem_object == 2 )
  {
    if ( (*(_DWORD *)(a1 + 424) & 0x400) == 0 )
    {
      v7 = *(const wchar_t **)(a1 + 352);
      v8 = wcsrchr(v7, 0x5Cu);
      v9 = v8;
      if ( v8 )
      {
        *v8 = 0;
        create_dir(a1, v7);
        *v9 = 92;
      }
      v10 = _la_win_permissive_name_w(*(LPCWSTR *)(a1 + 352));
      v11 = v10;
      if ( !v10 )
      {
        v6 = 22;
LABEL_72:
        archive_set_error(a1, v6, "Can't create '%ls'", *(_QWORD *)(a1 + 352));
        return 4294967271LL;
      }
      *(_QWORD *)(a1 + 368) = 0;
      v12 = -1;
      do
        ++v12;
      while ( v10[v12] );
      archive_wstrncat(a1 + 360, v10);
      *(_QWORD *)(a1 + 352) = *(_QWORD *)(a1 + 360);
      free(v11);
      v6 = create_filesystem_object(a1);
    }
    if ( v6 == 2 )
    {
      if ( archive_entry_hardlink(*(_QWORD *)(a1 + 344)) )
      {
        v13 = archive_entry_hardlink(*(_QWORD *)(a1 + 344));
        archive_set_error(a1, 2, "Hard-link target '%s' does not exist.", v13);
        return 4294967271LL;
      }
      goto LABEL_72;
    }
  }
  if ( ((v6 - 17) & 0xFFFFFFFB) == 0 )
  {
    if ( (*(_BYTE *)(a1 + 424) & 8) != 0 )
    {
      if ( (*(_WORD *)(a1 + 476) & 0xF000) == 0x4000 )
        *(_DWORD *)(a1 + 416) = 0;
      v14 = *(_QWORD *)(a1 + 344);
      *(_DWORD *)(v14 + 160) &= ~0x40u;
      *(_DWORD *)(v14 + 16) = 0;
      *(_QWORD *)(v14 + 112) = 0;
      return 0;
    }
    if ( v6 == 21 )
    {
      if ( (unsigned int)disk_rmdir(*(LPCWSTR *)(a1 + 352)) )
      {
LABEL_32:
        v15 = (unsigned int *)_o__errno();
        archive_set_error(a1, *v15, "Can't remove already-existing dir");
        return 4294967271LL;
      }
      goto LABEL_65;
    }
  }
  if ( v6 != 17 )
    goto LABEL_71;
  v16 = *(const WCHAR **)(a1 + 352);
  LOWORD(v36) = 0;
  v35[0] = 0;
  memset(&v39, 0, sizeof(v39));
  if ( (unsigned int)file_information(a1, v16, &v39, v35, 1) )
  {
    v17 = (unsigned int *)_o__errno();
    archive_set_error(a1, *v17, "Can't stat existing object");
    return 4294967271LL;
  }
  v18 = v35[0];
  if ( (v35[0] & 0xF000) != 0xA000 )
  {
    v19 = 0;
    goto LABEL_40;
  }
  v19 = (v39.dwFileAttributes >> 4) & 1;
  if ( (unsigned int)file_information(
                       a1,
                       *(const WCHAR **)(a1 + 352),
                       (struct _BY_HANDLE_FILE_INFORMATION *)(a1 + 280),
                       &v36,
                       0) )
  {
LABEL_40:
    nFileIndexLow = v39.nFileIndexLow;
    v21 = *(_OWORD *)&v39.ftLastAccessTime.dwHighDateTime;
    *(_OWORD *)(a1 + 280) = *(_OWORD *)&v39.dwFileAttributes;
    v22 = *(_OWORD *)&v39.nFileSizeHigh;
    *(_OWORD *)(a1 + 296) = v21;
    *(_OWORD *)(a1 + 312) = v22;
    *(_DWORD *)(a1 + 328) = nFileIndexLow;
    goto LABEL_41;
  }
  v18 = v36;
LABEL_41:
  v23 = *(_DWORD *)(a1 + 424);
  if ( (v23 & 0x800) == 0
    || (v18 & 0xF000) == 0x4000
    || (v37 = *(_QWORD *)(a1 + 300), v38 = 0, v36 = 0, ntfs_to_unix(v37, &v38, &v36), v38 < *(_QWORD *)(v24 + 56))
    || v38 <= *(_QWORD *)(v24 + 56) && v36 < *(_DWORD *)(v24 + 64) )
  {
    if ( *(_DWORD *)(a1 + 176)
      && *(_DWORD *)(a1 + 308) == *(_QWORD *)(a1 + 184)
      && (*(unsigned int *)(a1 + 328) | ((unsigned __int64)*(unsigned __int16 *)(a1 + 324) << 32)) == *(_QWORD *)(a1 + 192) )
    {
      archive_set_error(a1, 0, "Refusing to overwrite archive");
      return 4294967271LL;
    }
    if ( (v18 & 0xF000) == 0x4000 )
    {
      v33 = *(_WORD *)(a1 + 476);
      if ( (v33 & 0xF000) != 0x4000 )
      {
        if ( (v23 & 0x20000) != 0 )
          set_fflags_platform(*(LPCWSTR *)(a1 + 352));
        if ( (unsigned int)disk_rmdir(*(LPCWSTR *)(a1 + 352)) )
          goto LABEL_32;
        goto LABEL_70;
      }
      if ( v33 != v18 )
      {
        v34 = *(_DWORD *)(a1 + 416);
        if ( (v34 & 0x40000000) != 0 )
          *(_DWORD *)(a1 + 420) |= v34 & 0x34000000;
      }
    }
    else
    {
      if ( (v23 & 0x20000) != 0 )
        set_fflags_platform(*(LPCWSTR *)(a1 + 352));
      if ( (*(_DWORD *)(a1 + 424) & 0x40000) == 0 || (*(_WORD *)(a1 + 476) & 0xF000) != 0x8000 )
      {
        v30 = *(const WCHAR **)(a1 + 352);
        if ( v19 )
        {
          if ( (unsigned int)disk_rmdir(v30) )
          {
            v31 = (unsigned int *)_o__errno();
            archive_set_error(a1, *v31, "Can't unlink directory symlink");
            return 4294967271LL;
          }
        }
        else if ( (unsigned int)disk_unlink(v30) )
        {
          v32 = (unsigned int *)_o__errno();
          archive_set_error(a1, *v32, "Can't unlink already-existing object");
          return 4294967271LL;
        }
LABEL_65:
        *(_QWORD *)(a1 + 336) = 0;
LABEL_70:
        v6 = create_filesystem_object(a1);
LABEL_71:
        if ( v6 )
          goto LABEL_72;
        goto LABEL_76;
      }
      v25 = la_mktemp(a1);
      if ( v25 == -1 )
      {
        LastError = GetLastError();
        _la_dosmaperr(LastError);
        v27 = (unsigned int *)_o__errno();
        archive_set_error(a1, *v27, "Can't create temporary file");
        return 4294967271LL;
      }
      osfhandle = _get_osfhandle(v25);
      *(_QWORD *)(a1 + 432) = osfhandle;
      if ( osfhandle == -1 )
      {
        v29 = GetLastError();
        _la_dosmaperr(v29);
        return 4294967271LL;
      }
    }
LABEL_76:
    *(_QWORD *)(a1 + 336) = 0;
    return 0;
  }
  *(_DWORD *)(v24 + 160) &= ~0x40u;
  *(_DWORD *)(v24 + 16) = 0;
  *(_QWORD *)(v24 + 112) = 0;
  return 0;
}

```

## disassembly

```asm
0x1800f7330  push    rbp
0x1800f7332  push    rbx
0x1800f7333  push    rsi
0x1800f7334  push    rdi
0x1800f7335  push    r12
0x1800f7337  push    r13
0x1800f7339  push    r14
0x1800f733b  push    r15
0x1800f733d  lea     rbp, [rsp-1Fh]
0x1800f7342  sub     rsp, 98h
0x1800f7349  mov     rax, cs:__security_cookie
0x1800f7350  xor     rax, rsp
0x1800f7353  mov     [rbp+57h+var_50], rax
0x1800f7357  xor     r15d, r15d
0x1800f735a  mov     rdi, rcx
0x1800f735d  mov     ecx, [rcx+1A8h]
0x1800f7363  mov     r12d, 0F000h
0x1800f7369  mov     r13d, 4000h
0x1800f736f  lea     r14d, [r15+2]
0x1800f7373  test    cl, 10h
0x1800f7376  jz      short loc_1800F73F4
0x1800f7378  movzx   eax, word ptr [rdi+1DCh]
0x1800f737f  and     ax, r12w
0x1800f7383  cmp     ax, r13w
0x1800f7387  jz      short loc_1800F73F4
0x1800f7389  bt      ecx, 11h
0x1800f738d  jnb     short loc_1800F73A1
0x1800f738f  mov     rcx, [rdi+160h]; lpFileName
0x1800f7396  lea     r8d, [r15+1]
0x1800f739a  xor     edx, edx
0x1800f739c  call    set_fflags_platform
0x1800f73a1  mov     rcx, [rdi+160h]; lpFileName
0x1800f73a8  call    disk_unlink
0x1800f73ad  test    eax, eax
0x1800f73af  jz      short loc_1800F73ED
0x1800f73b1  call    cs:__imp__o__errno
0x1800f73b7  cmp     [rax], r14d
0x1800f73ba  jz      short loc_1800F73F4
0x1800f73bc  mov     rcx, [rdi+160h]; lpFileName
0x1800f73c3  call    disk_rmdir
0x1800f73c8  test    eax, eax
0x1800f73ca  jz      short loc_1800F73ED
0x1800f73cc  call    cs:__imp__o__errno
0x1800f73d2  lea     r8, aCouldNotUnlink; "Could not unlink"
0x1800f73d9  mov     edx, [rax]
0x1800f73db  mov     rcx, rdi
0x1800f73de  call    archive_set_error
0x1800f73e3  mov     eax, 0FFFFFFE7h
0x1800f73e8  jmp     loc_1800F7868
0x1800f73ed  mov     [rdi+150h], r15
0x1800f73f4  mov     rcx, rdi
0x1800f73f7  call    create_filesystem_object
0x1800f73fc  mov     ebx, eax
0x1800f73fe  cmp     eax, 14h
0x1800f7401  jz      short loc_1800F740C
0x1800f7403  cmp     eax, r14d
0x1800f7406  jnz     loc_1800F74F6
0x1800f740c  test    dword ptr [rdi+1A8h], 400h
0x1800f7416  jnz     loc_1800F74B6
0x1800f741c  mov     rsi, [rdi+160h]
0x1800f7423  mov     r13d, 5Ch ; '\'
0x1800f7429  mov     edx, r13d; Ch
0x1800f742c  mov     rcx, rsi; Str
0x1800f742f  call    cs:__imp_wcsrchr
0x1800f7435  mov     rbx, rax
0x1800f7438  test    rax, rax
0x1800f743b  jz      short loc_1800F7450
0x1800f743d  mov     rdx, rsi
0x1800f7440  mov     [rax], r15w
0x1800f7444  mov     rcx, rdi
0x1800f7447  call    create_dir
0x1800f744c  mov     [rbx], r13w
0x1800f7450  mov     rcx, [rdi+160h]; lpFileName
0x1800f7457  call    __la_win_permissive_name_w
0x1800f745c  mov     rsi, rax
0x1800f745f  test    rax, rax
0x1800f7462  jnz     short loc_1800F746C
0x1800f7464  lea     ebx, [rax+16h]
0x1800f7467  jmp     loc_1800F782E
0x1800f746c  mov     [rdi+170h], r15
0x1800f7473  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800f7477  inc     r8
0x1800f747a  cmp     [rax+r8*2], r15w
0x1800f747f  jnz     short loc_1800F7477
0x1800f7481  lea     rbx, [rdi+168h]
0x1800f7488  mov     rdx, rsi
0x1800f748b  mov     rcx, rbx
0x1800f748e  call    archive_wstrncat
0x1800f7493  mov     rax, [rbx]
0x1800f7496  mov     rcx, rsi; Block
0x1800f7499  mov     [rdi+160h], rax
0x1800f74a0  call    cs:__imp_free
0x1800f74a6  mov     rcx, rdi
0x1800f74a9  call    create_filesystem_object
0x1800f74ae  mov     ebx, eax
0x1800f74b0  mov     r13d, 4000h
0x1800f74b6  cmp     ebx, r14d
0x1800f74b9  jnz     short loc_1800F74F6
0x1800f74bb  mov     rcx, [rdi+158h]
0x1800f74c2  call    archive_entry_hardlink
0x1800f74c7  test    rax, rax
0x1800f74ca  jz      loc_1800F782E
0x1800f74d0  mov     rcx, [rdi+158h]
0x1800f74d7  call    archive_entry_hardlink
0x1800f74dc  mov     r9, rax
0x1800f74df  lea     r8, aHardLinkTarget; "Hard-link target '%s' does not exist."
0x1800f74e6  mov     edx, r14d
0x1800f74e9  mov     rcx, rdi
0x1800f74ec  call    archive_set_error
0x1800f74f1  jmp     loc_1800F73E3
0x1800f74f6  lea     eax, [rbx-11h]
0x1800f74f9  test    eax, 0FFFFFFFBh
0x1800f74fe  jnz     short loc_1800F7567
0x1800f7500  test    byte ptr [rdi+1A8h], 8
0x1800f7507  jz      short loc_1800F753C
0x1800f7509  movzx   eax, word ptr [rdi+1DCh]
0x1800f7510  and     ax, r12w
0x1800f7514  cmp     ax, r13w
0x1800f7518  jnz     short loc_1800F7521
0x1800f751a  mov     [rdi+1A0h], r15d
0x1800f7521  mov     rax, [rdi+158h]
0x1800f7528  and     dword ptr [rax+0A0h], 0FFFFFFBFh
0x1800f752f  mov     [rax+10h], r15d
0x1800f7533  mov     [rax+70h], r15
0x1800f7537  jmp     loc_1800F7866
0x1800f753c  cmp     ebx, 15h
0x1800f753f  jnz     short loc_1800F7567
0x1800f7541  mov     rcx, [rdi+160h]; lpFileName
0x1800f7548  call    disk_rmdir
0x1800f754d  test    eax, eax
0x1800f754f  jz      loc_1800F77D6
0x1800f7555  call    cs:__imp__o__errno
0x1800f755b  lea     r8, aCanTRemoveAlre; "Can't remove already-existing dir"
0x1800f7562  jmp     loc_1800F73D9
0x1800f7567  cmp     ebx, 11h
0x1800f756a  jnz     loc_1800F782A
0x1800f7570  mov     rdx, [rdi+160h]
0x1800f7577  lea     r9, [rbp+57h+var_A0]
0x1800f757b  xorps   xmm0, xmm0
0x1800f757e  mov     word ptr [rbp+57h+var_9C], r15w
0x1800f7583  xor     eax, eax
0x1800f7585  mov     [rbp+57h+var_A0], r15w
0x1800f758a  lea     r8, [rbp+57h+var_88]
0x1800f758e  mov     [rbp+57h+var_58], eax
0x1800f7591  mov     rcx, rdi
0x1800f7594  mov     [rsp+0D0h+var_B0], 1
0x1800f759c  movups  [rbp+57h+var_88], xmm0
0x1800f75a0  movups  [rbp+57h+var_78], xmm0
0x1800f75a4  movups  [rbp+57h+var_68], xmm0
0x1800f75a8  call    file_information
0x1800f75ad  test    eax, eax
0x1800f75af  jz      short loc_1800F75C3
0x1800f75b1  call    cs:__imp__o__errno
0x1800f75b7  lea     r8, aCanTStatExisti; "Can't stat existing object"
0x1800f75be  jmp     loc_1800F73D9
0x1800f75c3  movzx   esi, [rbp+57h+var_A0]
0x1800f75c7  lea     rbx, [rdi+118h]
0x1800f75ce  movzx   eax, si
0x1800f75d1  mov     ecx, 0A000h
0x1800f75d6  and     ax, r12w
0x1800f75da  cmp     ax, cx
0x1800f75dd  jnz     short loc_1800F7610
0x1800f75df  mov     r14d, dword ptr [rbp+57h+var_88]
0x1800f75e3  lea     r9, [rbp+57h+var_9C]
0x1800f75e7  mov     rdx, [rdi+160h]
0x1800f75ee  mov     r8, rbx
0x1800f75f1  shr     r14d, 4
0x1800f75f5  mov     rcx, rdi
0x1800f75f8  and     r14d, 1
0x1800f75fc  mov     [rsp+0D0h+var_B0], r15d
0x1800f7601  call    file_information
0x1800f7606  test    eax, eax
0x1800f7608  jnz     short loc_1800F7613
0x1800f760a  movzx   esi, word ptr [rbp+57h+var_9C]
0x1800f760e  jmp     short loc_1800F7630
0x1800f7610  mov     r14d, r15d
0x1800f7613  movups  xmm0, [rbp+57h+var_88]
0x1800f7617  mov     eax, [rbp+57h+var_58]
0x1800f761a  movups  xmm1, [rbp+57h+var_78]
0x1800f761e  movups  xmmword ptr [rbx], xmm0
0x1800f7621  movups  xmm0, [rbp+57h+var_68]
0x1800f7625  movups  xmmword ptr [rbx+10h], xmm1
0x1800f7629  movups  xmmword ptr [rbx+20h], xmm0
0x1800f762d  mov     [rbx+30h], eax
0x1800f7630  mov     r11d, [rdi+1A8h]
0x1800f7637  bt      r11d, 0Bh
0x1800f763c  jnb     short loc_1800F76A7
0x1800f763e  movzx   eax, si
0x1800f7641  and     ax, r12w
0x1800f7645  cmp     ax, r13w
0x1800f7649  jz      short loc_1800F76A7
0x1800f764b  mov     eax, [rdi+130h]
0x1800f7651  lea     r8, [rbp+57h+var_9C]
0x1800f7655  mov     r10, [rdi+158h]
0x1800f765c  lea     rdx, [rbp+57h+var_90]
0x1800f7660  mov     dword ptr [rbp+57h+var_98+4], eax
0x1800f7663  mov     eax, [rdi+12Ch]
0x1800f7669  mov     dword ptr [rbp+57h+var_98], eax
0x1800f766c  mov     rcx, [rbp+57h+var_98]
0x1800f7670  mov     [rbp+57h+var_90], r15
0x1800f7674  mov     [rbp+57h+var_9C], r15d
0x1800f7678  call    ntfs_to_unix
0x1800f767d  mov     rax, [rbp+57h+var_90]
0x1800f7681  cmp     rax, [r10+38h]
0x1800f7685  jl      short loc_1800F76A7
0x1800f7687  jg      short loc_1800F7692
0x1800f7689  mov     eax, [r10+40h]
0x1800f768d  cmp     [rbp+57h+var_9C], eax
0x1800f7690  jl      short loc_1800F76A7
0x1800f7692  and     dword ptr [r10+0A0h], 0FFFFFFBFh
0x1800f769a  mov     [r10+10h], r15d
0x1800f769e  mov     [r10+70h], r15
0x1800f76a2  jmp     loc_1800F7866
0x1800f76a7  cmp     [rdi+0B0h], r15d
0x1800f76ae  jz      short loc_1800F76F2
0x1800f76b0  mov     eax, [rdi+134h]
0x1800f76b6  cmp     rax, [rdi+0B8h]
0x1800f76bd  jnz     short loc_1800F76F2
0x1800f76bf  movzx   ecx, word ptr [rdi+144h]
0x1800f76c6  mov     eax, [rdi+148h]
0x1800f76cc  shl     rcx, 20h
0x1800f76d0  or      rcx, rax
0x1800f76d3  cmp     rcx, [rdi+0C0h]
0x1800f76da  jnz     short loc_1800F76F2
0x1800f76dc  lea     r8, aRefusingToOver; "Refusing to overwrite archive"
0x1800f76e3  xor     edx, edx
0x1800f76e5  mov     rcx, rdi
0x1800f76e8  call    archive_set_error
0x1800f76ed  jmp     loc_1800F73E3
0x1800f76f2  movzx   eax, si
0x1800f76f5  and     ax, r12w
0x1800f76f9  cmp     ax, r13w
0x1800f76fd  jz      loc_1800F77DF
0x1800f7703  bt      r11d, 11h
0x1800f7708  jnb     short loc_1800F771C
0x1800f770a  mov     rcx, [rdi+160h]; lpFileName
0x1800f7711  xor     edx, edx
0x1800f7713  lea     r8d, [rdx+1]
0x1800f7717  call    set_fflags_platform
0x1800f771c  test    dword ptr [rdi+1A8h], 40000h
0x1800f7726  jz      short loc_1800F7794
0x1800f7728  movzx   eax, word ptr [rdi+1DCh]
0x1800f772f  mov     ecx, 8000h
0x1800f7734  and     ax, r12w
0x1800f7738  cmp     ax, cx
0x1800f773b  jnz     short loc_1800F7794
0x1800f773d  mov     rcx, rdi
0x1800f7740  call    la_mktemp
0x1800f7745  cmp     eax, 0FFFFFFFFh
0x1800f7748  jnz     short loc_1800F7769
0x1800f774a  call    cs:__imp_GetLastError
0x1800f7750  mov     ecx, eax
0x1800f7752  call    __la_dosmaperr
0x1800f7757  call    cs:__imp__o__errno
0x1800f775d  lea     r8, aCanTCreateTemp; "Can't create temporary file"
0x1800f7764  jmp     loc_1800F73D9
0x1800f7769  mov     ecx, eax; FileHandle
0x1800f776b  call    cs:__imp__get_osfhandle
0x1800f7771  mov     [rdi+1B0h], rax
0x1800f7778  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800f777c  jnz     loc_1800F785F
0x1800f7782  call    cs:__imp_GetLastError
0x1800f7788  mov     ecx, eax
0x1800f778a  call    __la_dosmaperr
0x1800f778f  jmp     loc_1800F73E3
0x1800f7794  mov     rcx, [rdi+160h]; lpFileName
0x1800f779b  test    r14d, r14d
0x1800f779e  jz      short loc_1800F77BB
0x1800f77a0  call    disk_rmdir
0x1800f77a5  test    eax, eax
0x1800f77a7  jz      short loc_1800F77D6
0x1800f77a9  call    cs:__imp__o__errno
0x1800f77af  lea     r8, aCanTUnlinkDire; "Can't unlink directory symlink"
0x1800f77b6  jmp     loc_1800F73D9
0x1800f77bb  call    disk_unlink
0x1800f77c0  test    eax, eax
0x1800f77c2  jz      short loc_1800F77D6
0x1800f77c4  call    cs:__imp__o__errno
0x1800f77ca  lea     r8, aCanTUnlinkAlre; "Can't unlink already-existing object"
0x1800f77d1  jmp     loc_1800F73D9
0x1800f77d6  mov     [rdi+150h], r15
0x1800f77dd  jmp     short loc_1800F7820
0x1800f77df  movzx   ecx, word ptr [rdi+1DCh]
0x1800f77e6  movzx   eax, cx
0x1800f77e9  and     ax, r12w
0x1800f77ed  cmp     ax, r13w
0x1800f77f1  jz      short loc_1800F7843
0x1800f77f3  bt      r11d, 11h
0x1800f77f8  jnb     short loc_1800F780C
0x1800f77fa  mov     rcx, [rdi+160h]; lpFileName
0x1800f7801  xor     edx, edx
0x1800f7803  lea     r8d, [rdx+1]
0x1800f7807  call    set_fflags_platform
0x1800f780c  mov     rcx, [rdi+160h]; lpFileName
0x1800f7813  call    disk_rmdir
0x1800f7818  test    eax, eax
0x1800f781a  jnz     loc_1800F7555
0x1800f7820  mov     rcx, rdi
0x1800f7823  call    create_filesystem_object
0x1800f7828  mov     ebx, eax
  ... truncated ...
```
