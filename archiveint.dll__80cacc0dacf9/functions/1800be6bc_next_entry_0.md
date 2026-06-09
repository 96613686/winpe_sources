# next_entry_0

- ea: `0x1800be6bc`
- end: `0x1800beb7f`
- name: `next_entry_0`
- size: `1219`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, reparse_path, installer_update`

## callers

- `0x1800bd240`

## callees

- `0x180006c00`
- `0x18000e0e4`
- `0x1800149c0`
- `0x1800b1ce0`
- `0x1800b4cb0`
- `0x1800b4d30`
- `0x1800b4f30`
- `0x1800bda60`
- `0x1800be020`
- `0x1800be1a4`
- `0x1800be6bc`
- `0x1800befa8`
- `0x1800bf58c`
- `0x1800bf650`
- `0x1800bf66c`
- `0x1800bf6bc`
- `0x1800bf9b8`
- `0x1800c01ec`
- `0x1800ece24`
- `0x1800ecf00`
- `0x1800ee8b0`
- `0x18011a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800be777`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800beabc`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800be777`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800beabc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800beaa1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800beaa1`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x1800bea8e`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x1800bea8e`

## string_xrefs

- `0x1800beb4d`: `%ls: Unable to continue traversing directory tree`
- `0x1800beb23`: `%ls: Couldn't visit directory`
- `0x1800beac5`: `Couldn't open %ls`

## pseudocode

```c
__int64 __fastcall next_entry_0(__int64 a1, __int64 a2, __int64 a3)
{
  int v6; // eax
  __int64 v7; // rcx
  int matched; // ebp
  __int64 v9; // rbx
  unsigned int *v10; // rdi
  const char *v11; // rax
  __int64 result; // rax
  char v13; // al
  _BYTE *v14; // r14
  _BYTE *v15; // r15
  int is_dir; // ebp
  __int64 v17; // r12
  int v18; // eax
  __int64 v19; // r8
  __int64 v20; // rdx
  __int64 v21; // rcx
  int v22; // eax
  __int64 disk_uname; // rax
  __int64 disk_gname; // rax
  __int64 v25; // rcx
  int v26; // eax
  void (__fastcall *v27)(__int64, _QWORD, __int64); // rax
  __int64 v28; // rax
  _QWORD *i; // rcx
  int v30; // ebp
  unsigned int (__fastcall *v31)(__int64, _QWORD, __int64); // rax
  int v32; // eax
  int v33; // eax
  __int64 v34; // rcx
  __int64 File2; // rax
  DWORD LastError; // eax
  __int64 v37; // rbx
  unsigned int *v38; // rax
  const char *v39; // r8
  _OWORD v40[6]; // [rsp+30h] [rbp-68h] BYREF

  *(_DWORD *)(a2 + 820) = 0;
  do
  {
    v6 = tree_next(a2);
    switch ( v6 )
    {
      case -2:
        archive_set_error(
          a1,
          *(unsigned int *)(a2 + 632),
          "%ls: Unable to continue traversing directory tree",
          *(const wchar_t **)(a2 + 672));
LABEL_66:
        result = 4294967266LL;
        *(_DWORD *)(a1 + 4) = 0x8000;
        return result;
      case -1:
        v39 = "%ls: Couldn't visit directory";
        goto LABEL_63;
      case 0:
        return 1;
    }
  }
  while ( v6 != 1 );
  if ( (*(_BYTE *)(a2 + 624) & 0x20) != 0 )
    goto LABEL_9;
  if ( (unsigned int)tree_current_file_information(a2, a2 + 716, 1) )
  {
    *(_DWORD *)(a2 + 624) |= 0x20u;
LABEL_9:
    if ( a2 != -716 )
    {
      archive_mstring_copy_wcs(a3 + 488, *(_QWORD *)(a2 + 672));
      v7 = *(_QWORD *)(a1 + 264);
      if ( v7 )
      {
        matched = archive_match_path_excluded(v7, a3);
        if ( matched < 0 )
          goto LABEL_12;
        if ( matched )
          goto LABEL_34;
      }
      v13 = *(_BYTE *)(a2 + 881);
      if ( v13 == 72 )
      {
        *(_BYTE *)(a2 + 881) = 80;
      }
      else if ( v13 != 76 )
      {
        v14 = (_BYTE *)(a1 + 152);
        v15 = (_BYTE *)(a1 + 153);
        goto LABEL_18;
      }
      v14 = (_BYTE *)(a1 + 152);
      is_dir = tree_current_is_dir(a2);
      v15 = (_BYTE *)(a1 + 153);
      *(_BYTE *)(a1 + 152) = 76;
      *(_BYTE *)(a1 + 153) = 1;
      v28 = tree_current_stat();
      v17 = v28;
      if ( v28 )
      {
        for ( i = *(_QWORD **)(*(_QWORD *)(a2 + 8) + 16LL); i; i = (_QWORD *)i[2] )
        {
          if ( i[11] == *(_DWORD *)(v28 + 28)
            && i[12] == *(unsigned int *)(v28 + 48) + ((unsigned __int64)*(unsigned __int16 *)(v28 + 44) << 32) )
          {
            goto LABEL_18;
          }
        }
      }
      else
      {
LABEL_18:
        is_dir = tree_current_is_physical_dir(a2);
        *v14 = 80;
        *v15 = 0;
        v17 = a2 + 716;
      }
      if ( !(unsigned int)update_current_filesystem(a1, *(unsigned int *)(v17 + 28)) )
      {
        v18 = *(_DWORD *)(a2 + 904);
        if ( v18 == -1 )
        {
          v18 = *(_DWORD *)(a2 + 908);
          *(_DWORD *)(a2 + 904) = v18;
        }
        if ( (*(_BYTE *)(a1 + 192) & 8) != 0 && v18 != *(_DWORD *)(a2 + 908) )
          return 4294967286LL;
        v19 = *(_QWORD *)(a2 + 616);
        v20 = *(_QWORD *)(a2 + 672);
        *(_DWORD *)(a2 + 820) = is_dir;
        entry_copy_bhfi(a3, v20, v19, v17);
        *(_QWORD *)(a2 + 832) = *(_QWORD *)(v17 + 20);
        *(_QWORD *)(a2 + 840) = *(_QWORD *)(v17 + 12);
        *(_WORD *)(a2 + 848) = *(_WORD *)(a3 + 1032) & 0xF000;
        v21 = *(_QWORD *)(a1 + 264);
        if ( !v21 )
          goto LABEL_27;
        v22 = archive_match_time_excluded(v21, a3);
        matched = v22;
        if ( v22 < 0 )
          goto LABEL_12;
        if ( !v22 )
        {
LABEL_27:
          disk_uname = archive_read_disk_uname(a1, *(_QWORD *)(a3 + 120));
          if ( disk_uname )
            archive_mstring_copy_mbs(a3 + 592, disk_uname);
          disk_gname = archive_read_disk_gname(a1, *(_QWORD *)(a3 + 88));
          if ( disk_gname )
            archive_mstring_copy_mbs(a3 + 280, disk_gname);
          v25 = *(_QWORD *)(a1 + 264);
          if ( !v25 )
            goto LABEL_43;
          v26 = archive_match_owner_excluded(v25, a3);
          matched = v26;
          if ( v26 >= 0 )
          {
            if ( v26 )
              goto LABEL_34;
LABEL_43:
            if ( (*(_BYTE *)(a1 + 192) & 0x40) == 0 )
            {
              v30 = *(_DWORD *)v17 & 7;
              if ( v30 )
              {
                archive_mstring_clean(a3 + 168);
                *(_DWORD *)(a3 + 272) = v30;
                *(_DWORD *)(a3 + 276) = 0;
              }
            }
            v31 = *(unsigned int (__fastcall **)(__int64, _QWORD, __int64))(a1 + 248);
            if ( v31 && !v31(a1, *(_QWORD *)(a1 + 256), a3) )
              return 4294967286LL;
            archive_mstring_copy_wcs(a3 + 696, *(_QWORD *)(a2 + 640));
            matched = 0;
            if ( (*(_WORD *)(a3 + 1032) & 0xF000) == 0x8000 && *(__int64 *)(a3 + 112) > 0 )
            {
              v32 = *(_DWORD *)(a2 + 1628);
              if ( *(_DWORD *)(a2 + 1624) )
                v33 = v32 != 0 ? 1644167168 : 570425344;
              else
                v33 = v32 != 0 ? 1241513984 : 167772160;
              v34 = *(_QWORD *)(a2 + 640);
              memset(v40, 0, 32);
              DWORD2(v40[0]) = v33;
              LODWORD(v40[0]) = 32;
              File2 = CreateFile2(v34, 0x80000000LL, 7, 3, v40);
              *(_QWORD *)(a2 + 920) = File2;
              if ( File2 == -1 )
              {
                LastError = GetLastError();
                _la_dosmaperr(LastError);
                v37 = *(_QWORD *)(*(_QWORD *)(a1 + 160) + 672LL);
                v38 = (unsigned int *)_o__errno();
                archive_set_error(a1, *v38, "Couldn't open %ls", v37);
                return 4294967271LL;
              }
              if ( *(char *)(a1 + 192) >= 0 && !archive_entry_hardlink(a3) && (*(_DWORD *)v17 & 0x200) != 0 )
                return (unsigned int)setup_sparse_from_disk(a1, a3, *(_QWORD *)(a2 + 920));
            }
            return (unsigned int)matched;
          }
LABEL_12:
          v9 = *(_QWORD *)(a1 + 264);
          v10 = (unsigned int *)_o__errno();
          v11 = (const char *)archive_error_string(v9);
          archive_set_error(a1, *v10, "Failed : %s", v11);
          return (unsigned int)matched;
        }
LABEL_34:
        v27 = *(void (__fastcall **)(__int64, _QWORD, __int64))(a1 + 272);
        if ( v27 )
          v27(a1, *(_QWORD *)(a1 + 280), a3);
        return 4294967286LL;
      }
      goto LABEL_66;
    }
  }
  v39 = "%ls: Cannot stat";
LABEL_63:
  archive_set_error(a1, *(unsigned int *)(a2 + 632), v39, *(_QWORD *)(a2 + 672));
  return 4294967271LL;
}

```

## disassembly

```asm
0x1800be6bc  push    rbx
0x1800be6be  push    rbp
0x1800be6bf  push    rsi
0x1800be6c0  push    rdi
0x1800be6c1  push    r12
0x1800be6c3  push    r13
0x1800be6c5  push    r14
0x1800be6c7  push    r15
0x1800be6c9  sub     rsp, 58h
0x1800be6cd  mov     rdi, r8
0x1800be6d0  mov     dword ptr [rdx+334h], 0
0x1800be6da  mov     rbx, rdx
0x1800be6dd  mov     rsi, rcx
0x1800be6e0  mov     r12d, 1
0x1800be6e6  mov     rcx, rbx
0x1800be6e9  call    tree_next
0x1800be6ee  cmp     eax, 0FFFFFFFEh
0x1800be6f1  jz      loc_1800BEB46
0x1800be6f7  cmp     eax, 0FFFFFFFFh
0x1800be6fa  jz      loc_1800BEB23
0x1800be700  test    eax, eax
0x1800be702  jz      loc_1800BEB1E
0x1800be708  cmp     eax, r12d
0x1800be70b  jnz     short loc_1800BE6E6
0x1800be70d  test    byte ptr [rbx+270h], 20h
0x1800be714  lea     r13, [rbx+2CCh]
0x1800be71b  jnz     short loc_1800BE73A
0x1800be71d  mov     r8d, r12d
0x1800be720  mov     rdx, r13
0x1800be723  mov     rcx, rbx
0x1800be726  call    tree_current_file_information
0x1800be72b  test    eax, eax
0x1800be72d  jz      loc_1800BEB15
0x1800be733  or      dword ptr [rbx+270h], 20h
0x1800be73a  test    r13, r13
0x1800be73d  jz      loc_1800BEB15
0x1800be743  mov     rdx, [rbx+2A0h]
0x1800be74a  lea     rcx, [rdi+1E8h]
0x1800be751  call    archive_mstring_copy_wcs
0x1800be756  mov     rcx, [rsi+108h]
0x1800be75d  test    rcx, rcx
0x1800be760  jz      short loc_1800BE7AB
0x1800be762  mov     rdx, rdi
0x1800be765  call    archive_match_path_excluded
0x1800be76a  mov     ebp, eax
0x1800be76c  test    eax, eax
0x1800be76e  jns     short loc_1800BE7A3
0x1800be770  mov     rbx, [rsi+108h]
0x1800be777  call    cs:__imp__o__errno
0x1800be77d  mov     rcx, rbx
0x1800be780  mov     rdi, rax
0x1800be783  call    archive_error_string
0x1800be788  mov     edx, [rdi]
0x1800be78a  lea     r8, aFailedS; "Failed : %s"
0x1800be791  mov     r9, rax
0x1800be794  mov     rcx, rsi
0x1800be797  call    archive_set_error
0x1800be79c  mov     eax, ebp
0x1800be79e  jmp     loc_1800BEB6E
0x1800be7a3  test    ebp, ebp
0x1800be7a5  jnz     loc_1800BE900
0x1800be7ab  mov     al, [rbx+371h]
0x1800be7b1  cmp     al, 48h ; 'H'
0x1800be7b3  jz      loc_1800BE927
0x1800be7b9  cmp     al, 4Ch ; 'L'
0x1800be7bb  jz      loc_1800BE92E
0x1800be7c1  lea     r14, [rsi+98h]
0x1800be7c8  lea     r15, [rsi+99h]
0x1800be7cf  mov     rcx, rbx
0x1800be7d2  call    tree_current_is_physical_dir
0x1800be7d7  mov     ebp, eax
0x1800be7d9  mov     byte ptr [r14], 50h ; 'P'
0x1800be7dd  mov     byte ptr [r15], 0
0x1800be7e1  mov     r12, r13
0x1800be7e4  mov     edx, [r12+1Ch]
0x1800be7e9  mov     rcx, rsi
0x1800be7ec  call    update_current_filesystem
0x1800be7f1  test    eax, eax
0x1800be7f3  jnz     loc_1800BEB62
0x1800be7f9  mov     eax, [rbx+388h]
0x1800be7ff  cmp     eax, 0FFFFFFFFh
0x1800be802  jnz     short loc_1800BE810
0x1800be804  mov     eax, [rbx+38Ch]
0x1800be80a  mov     [rbx+388h], eax
0x1800be810  test    byte ptr [rsi+0C0h], 8
0x1800be817  jz      short loc_1800BE825
0x1800be819  cmp     eax, [rbx+38Ch]
0x1800be81f  jnz     loc_1800BE9E7
0x1800be825  mov     r8, [rbx+268h]
0x1800be82c  mov     r9, r12
0x1800be82f  mov     rdx, [rbx+2A0h]
0x1800be836  mov     rcx, rdi
0x1800be839  mov     [rbx+334h], ebp
0x1800be83f  call    entry_copy_bhfi
0x1800be844  mov     rax, [r12+14h]
0x1800be849  mov     r14d, 0F000h
0x1800be84f  mov     [rbx+340h], rax
0x1800be856  mov     rax, [r12+0Ch]
0x1800be85b  mov     [rbx+348h], rax
0x1800be862  movzx   eax, word ptr [rdi+408h]
0x1800be869  and     ax, r14w
0x1800be86d  mov     [rbx+350h], ax
0x1800be874  mov     rcx, [rsi+108h]
0x1800be87b  test    rcx, rcx
0x1800be87e  jz      short loc_1800BE896
0x1800be880  mov     rdx, rdi
0x1800be883  call    archive_match_time_excluded
0x1800be888  mov     ebp, eax
0x1800be88a  test    eax, eax
0x1800be88c  js      loc_1800BE770
0x1800be892  test    eax, eax
0x1800be894  jnz     short loc_1800BE900
0x1800be896  mov     rdx, [rdi+78h]
0x1800be89a  mov     rcx, rsi
0x1800be89d  call    archive_read_disk_uname
0x1800be8a2  test    rax, rax
0x1800be8a5  jz      short loc_1800BE8B6
0x1800be8a7  lea     rcx, [rdi+250h]
0x1800be8ae  mov     rdx, rax
0x1800be8b1  call    archive_mstring_copy_mbs
0x1800be8b6  mov     rdx, [rdi+58h]
0x1800be8ba  mov     rcx, rsi
0x1800be8bd  call    archive_read_disk_gname
0x1800be8c2  test    rax, rax
0x1800be8c5  jz      short loc_1800BE8D6
0x1800be8c7  lea     rcx, [rdi+118h]
0x1800be8ce  mov     rdx, rax
0x1800be8d1  call    archive_mstring_copy_mbs
0x1800be8d6  mov     rcx, [rsi+108h]
0x1800be8dd  test    rcx, rcx
0x1800be8e0  jz      loc_1800BE997
0x1800be8e6  mov     rdx, rdi
0x1800be8e9  call    archive_match_owner_excluded
0x1800be8ee  mov     ebp, eax
0x1800be8f0  test    eax, eax
0x1800be8f2  js      loc_1800BE770
0x1800be8f8  test    eax, eax
0x1800be8fa  jz      loc_1800BE997
0x1800be900  mov     rax, [rsi+110h]
0x1800be907  test    rax, rax
0x1800be90a  jz      loc_1800BE9E7
0x1800be910  mov     rdx, [rsi+118h]
0x1800be917  mov     r8, rdi
0x1800be91a  mov     rcx, rsi
0x1800be91d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be922  jmp     loc_1800BE9E7
0x1800be927  mov     byte ptr [rbx+371h], 50h ; 'P'
0x1800be92e  mov     rcx, rbx
0x1800be931  call    tree_current_is_dir
0x1800be936  lea     r14, [rsi+98h]
0x1800be93d  mov     ebp, eax
0x1800be93f  lea     r15, [rsi+99h]
0x1800be946  mov     byte ptr [r14], 4Ch ; 'L'
0x1800be94a  mov     [r15], r12b
0x1800be94d  call    tree_current_stat
0x1800be952  mov     r12, rax
0x1800be955  test    rax, rax
0x1800be958  jz      loc_1800BE7CF
0x1800be95e  movzx   edx, word ptr [rax+2Ch]
0x1800be962  mov     r8d, [rax+1Ch]
0x1800be966  mov     eax, [rax+30h]
0x1800be969  shl     rdx, 20h
0x1800be96d  add     rdx, rax
0x1800be970  mov     rax, [rbx+8]
0x1800be974  mov     rcx, [rax+10h]
0x1800be978  test    rcx, rcx
0x1800be97b  jz      loc_1800BE7E4
0x1800be981  cmp     [rcx+58h], r8
0x1800be985  jnz     short loc_1800BE991
0x1800be987  cmp     [rcx+60h], rdx
0x1800be98b  jz      loc_1800BE7CF
0x1800be991  mov     rcx, [rcx+10h]
0x1800be995  jmp     short loc_1800BE978
0x1800be997  test    byte ptr [rsi+0C0h], 40h
0x1800be99e  jnz     short loc_1800BE9C5
0x1800be9a0  mov     ebp, [r12]
0x1800be9a4  and     ebp, 7
0x1800be9a7  jz      short loc_1800BE9C5
0x1800be9a9  lea     rcx, [rdi+0A8h]
0x1800be9b0  call    archive_mstring_clean
0x1800be9b5  mov     [rdi+110h], ebp
0x1800be9bb  mov     dword ptr [rdi+114h], 0
0x1800be9c5  mov     rax, [rsi+0F8h]
0x1800be9cc  test    rax, rax
0x1800be9cf  jz      short loc_1800BE9F1
0x1800be9d1  mov     rdx, [rsi+100h]
0x1800be9d8  mov     r8, rdi
0x1800be9db  mov     rcx, rsi
0x1800be9de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be9e3  test    eax, eax
0x1800be9e5  jnz     short loc_1800BE9F1
0x1800be9e7  mov     eax, 0FFFFFFF6h
0x1800be9ec  jmp     loc_1800BEB6E
0x1800be9f1  mov     rdx, [rbx+280h]
0x1800be9f8  lea     rcx, [rdi+2B8h]
0x1800be9ff  call    archive_mstring_copy_wcs
0x1800bea04  movzx   eax, word ptr [rdi+408h]
0x1800bea0b  xor     ebp, ebp
0x1800bea0d  and     ax, r14w
0x1800bea11  mov     ecx, 8000h
0x1800bea16  cmp     ax, cx
0x1800bea19  jnz     loc_1800BE79C
0x1800bea1f  cmp     [rdi+70h], rbp
0x1800bea23  jle     loc_1800BE79C
0x1800bea29  mov     eax, [rbx+65Ch]
0x1800bea2f  cmp     [rbx+658h], ebp
0x1800bea35  jz      short loc_1800BEA47
0x1800bea37  neg     eax
0x1800bea39  sbb     eax, eax
0x1800bea3b  and     eax, 40000000h
0x1800bea40  add     eax, 22000000h
0x1800bea45  jmp     short loc_1800BEA55
0x1800bea47  neg     eax
0x1800bea49  sbb     eax, eax
0x1800bea4b  and     eax, 40000000h
0x1800bea50  add     eax, 0A000000h
0x1800bea55  mov     rcx, [rbx+280h]
0x1800bea5c  xorps   xmm0, xmm0
0x1800bea5f  movups  [rsp+98h+var_68], xmm0
0x1800bea64  mov     r9d, 3
0x1800bea6a  mov     dword ptr [rsp+98h+var_68+8], eax
0x1800bea6e  lea     rax, [rsp+98h+var_68]
0x1800bea73  mov     dword ptr [rsp+98h+var_68], 20h ; ' '
0x1800bea7b  mov     edx, 80000000h
0x1800bea80  mov     [rsp+98h+var_78], rax
0x1800bea85  movups  [rsp+98h+var_58], xmm0
0x1800bea8a  lea     r8d, [r9+4]
0x1800bea8e  call    cs:__imp_CreateFile2
0x1800bea94  mov     [rbx+398h], rax
0x1800bea9b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800bea9f  jnz     short loc_1800BEAD0
0x1800beaa1  call    cs:__imp_GetLastError
0x1800beaa7  mov     ecx, eax
0x1800beaa9  call    __la_dosmaperr
0x1800beaae  mov     rax, [rsi+0A0h]
0x1800beab5  mov     rbx, [rax+2A0h]
0x1800beabc  call    cs:__imp__o__errno
0x1800beac2  mov     r9, rbx
0x1800beac5  lea     r8, aCouldnTOpenLs; "Couldn't open %ls"
0x1800beacc  mov     edx, [rax]
0x1800beace  jmp     short loc_1800BEB37
0x1800bead0  test    byte ptr [rsi+0C0h], 80h
0x1800bead7  jnz     loc_1800BE79C
0x1800beadd  mov     rcx, rdi
0x1800beae0  call    archive_entry_hardlink
0x1800beae5  test    rax, rax
0x1800beae8  jnz     loc_1800BE79C
0x1800beaee  test    dword ptr [r12], 200h
0x1800beaf6  jz      loc_1800BE79C
0x1800beafc  mov     r8, [rbx+398h]
0x1800beb03  mov     rdx, rdi
0x1800beb06  mov     rcx, rsi
0x1800beb09  call    setup_sparse_from_disk
0x1800beb0e  mov     ebp, eax
0x1800beb10  jmp     loc_1800BE79C
0x1800beb15  lea     r8, aLsCannotStat; "%ls: Cannot stat"
0x1800beb1c  jmp     short loc_1800BEB2A
0x1800beb1e  mov     eax, r12d
0x1800beb21  jmp     short loc_1800BEB6E
0x1800beb23  lea     r8, aLsCouldnTVisit; "%ls: Couldn't visit directory"
0x1800beb2a  mov     r9, [rbx+2A0h]
0x1800beb31  mov     edx, [rbx+278h]
0x1800beb37  mov     rcx, rsi
0x1800beb3a  call    archive_set_error
0x1800beb3f  mov     eax, 0FFFFFFE7h
0x1800beb44  jmp     short loc_1800BEB6E
0x1800beb46  mov     r9, [rbx+2A0h]
0x1800beb4d  lea     r8, aLsUnableToCont; "%ls: Unable to continue traversing dire"...
0x1800beb54  mov     edx, [rbx+278h]
0x1800beb5a  mov     rcx, rsi
0x1800beb5d  call    archive_set_error
0x1800beb62  mov     eax, 0FFFFFFE2h
0x1800beb67  mov     dword ptr [rsi+4], 8000h
0x1800beb6e  add     rsp, 58h
0x1800beb72  pop     r15
0x1800beb74  pop     r14
0x1800beb76  pop     r13
0x1800beb78  pop     r12
0x1800beb7a  pop     rdi
0x1800beb7b  pop     rsi
0x1800beb7c  pop     rbp
0x1800beb7d  pop     rbx
0x1800beb7e  retn
```
