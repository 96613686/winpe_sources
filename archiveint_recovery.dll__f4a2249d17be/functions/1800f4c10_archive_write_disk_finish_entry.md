# _archive_write_disk_finish_entry

- ea: `0x1800f4c10`
- end: `0x1800f4ee1`
- name: `_archive_write_disk_finish_entry`
- size: `721`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `file_ops`

## callers

- `0x1800f49d0`
- `0x1800f5030`

## callees

- `0x18000523c`
- `0x180006c00`
- `0x180007c80`
- `0x1800149c0`
- `0x1800b1b60`
- `0x1800b1bc0`
- `0x1800b28d0`
- `0x1800b39d0`
- `0x1800f4c10`
- `0x1800f5510`
- `0x1800f57c0`
- `0x1800f65c4`
- `0x1800f6c3c`
- `0x1800f7890`
- `0x1800f7920`
- `0x1800f7a14`
- `0x1800f7c04`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f4c93`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f4e7e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f4c93`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f4e7e`
- `api-ms-win-crt-private-l1-1-0!_o__wrename` at `0x1800f4e67`
- `api-ms-win-crt-private-l1-1-0!_o__wrename` at `0x1800f4e67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f4e71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f4e71`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f4cb1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f4e32`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f4cb1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f4e32`

## string_xrefs

- `0x1800f4c1f`: `archive_write_finish_entry`
- `0x1800f4e84`: `Failed to rename temporary file`

## pseudocode

```c
__int64 __fastcall archive_write_disk_finish_entry(__int64 a1)
{
  __int64 result; // rax
  __int64 v3; // rdx
  __int64 v4; // r8
  void *v5; // rcx
  unsigned int *v6; // rax
  int v7; // esi
  __int64 v8; // rcx
  __int64 v9; // rbx
  __int64 v10; // rax
  __int64 v11; // rax
  bool v12; // zf
  __int64 v13; // rcx
  __int64 v14; // rbx
  __int64 v15; // rax
  int v16; // eax
  int v17; // ebx
  int v18; // eax
  int v19; // eax
  int v20; // eax
  void *v21; // rcx
  DWORD LastError; // eax
  unsigned int *v23; // rax

  result = _archive_check_magic(a1, 3221336261LL, 6, "archive_write_finish_entry");
  if ( (_DWORD)result != -30 )
  {
    if ( (*(_BYTE *)(a1 + 4) & 2) != 0 )
    {
      return 0;
    }
    else
    {
      *(_QWORD *)(a1 + 56) = 0;
      *(_QWORD *)(a1 + 40) = 0;
      *(_DWORD *)(a1 + 36) = 0;
      v5 = *(void **)(a1 + 432);
      if ( v5 == (void *)-1LL
        || (v3 = *(_QWORD *)(a1 + 464), v3 < 0)
        || *(_QWORD *)(a1 + 448) == v3
        || (unsigned int)la_ftruncate(v5, v3) != -1 )
      {
        v7 = 0;
        if ( (*(_DWORD *)(a1 + 416) & 0x14000001) != 0 )
        {
          v8 = *(_QWORD *)(a1 + 344);
          v9 = *(_QWORD *)(v8 + 120);
          v10 = archive_entry_uname(v8);
          v11 = archive_write_disk_uid(a1, v10, v9);
          v12 = (*(_DWORD *)(a1 + 416) & 0x14000001) == 0;
          *(_QWORD *)(a1 + 480) = v11;
          if ( !v12 )
          {
            v13 = *(_QWORD *)(a1 + 344);
            v14 = *(_QWORD *)(v13 + 88);
            v15 = archive_entry_gname(v13);
            *(_QWORD *)(a1 + 488) = archive_write_disk_gid(a1, v15, v14);
          }
        }
        if ( (*(_BYTE *)(a1 + 416) & 1) != 0 )
          v7 = set_ownership(a1);
        if ( (*(_DWORD *)(a1 + 416) & 0x34000000) != 0 )
        {
          v16 = set_mode(a1, *(unsigned __int16 *)(a1 + 476));
          if ( v16 < v7 )
            v7 = v16;
        }
        v17 = *(_DWORD *)(a1 + 416);
        if ( (v17 & 0x80u) != 0 )
        {
          if ( !(unsigned int)archive_entry_xattr_count(*(_QWORD *)(a1 + 344), v3, v4) || dword_1801547C8 )
          {
            v18 = 0;
          }
          else
          {
            dword_1801547C8 = 1;
            archive_set_error(a1, 42, "Cannot restore extended attributes on this system");
            v17 = *(_DWORD *)(a1 + 416);
            v18 = -20;
          }
          if ( v18 < v7 )
            v7 = v18;
        }
        if ( (v17 & 0x40) != 0 )
        {
          if ( *(_QWORD *)(*(_QWORD *)(a1 + 344) + 272LL) )
          {
            v19 = set_fflags_platform(*(LPCWSTR *)(a1 + 352));
            v17 = *(_DWORD *)(a1 + 416);
          }
          else
          {
            v19 = 0;
          }
          if ( v19 < v7 )
            v7 = v19;
        }
        if ( (v17 & 4) != 0 )
        {
          v20 = set_times_from_entry(a1);
          if ( v20 < v7 )
            v7 = v20;
        }
        if ( (*(_BYTE *)(a1 + 416) & 0x20) != 0 )
        {
          archive_entry_pathname_w(*(_QWORD *)(a1 + 344));
          if ( v7 > 0 )
            v7 = 0;
        }
        v21 = *(void **)(a1 + 432);
        if ( v21 != (void *)-1LL )
        {
          CloseHandle(v21);
          v12 = *(_QWORD *)(a1 + 384) == 0;
          *(_QWORD *)(a1 + 432) = -1;
          if ( !v12 )
          {
            disk_unlink(*(LPCWSTR *)(a1 + 352));
            if ( (unsigned int)_o__wrename(*(_QWORD *)(a1 + 384), *(_QWORD *)(a1 + 352)) )
            {
              LastError = GetLastError();
              _la_dosmaperr(LastError);
              v23 = (unsigned int *)_o__errno();
              archive_set_error(a1, *v23, "Failed to rename temporary file");
              v7 = -25;
              disk_unlink(*(LPCWSTR *)(a1 + 384));
            }
            *(_QWORD *)(a1 + 384) = 0;
          }
        }
        archive_entry_free(*(_QWORD *)(a1 + 344));
        result = (unsigned int)v7;
        *(_QWORD *)(a1 + 344) = 0;
        *(_DWORD *)(a1 + 4) = 2;
      }
      else
      {
        v6 = (unsigned int *)_o__errno();
        archive_set_error(a1, *v6, "File size could not be restored");
        CloseHandle(*(HANDLE *)(a1 + 432));
        result = 4294967271LL;
        *(_QWORD *)(a1 + 432) = -1;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800f4c10  mov     [rsp+arg_0], rbx
0x1800f4c15  mov     [rsp+arg_8], rsi
0x1800f4c1a  push    rdi
0x1800f4c1b  sub     rsp, 20h
0x1800f4c1f  lea     r9, aArchiveWriteFi_1; "archive_write_finish_entry"
0x1800f4c26  mov     edx, 0C001B0C5h
0x1800f4c2b  mov     r8d, 6
0x1800f4c31  mov     rdi, rcx
0x1800f4c34  call    __archive_check_magic
0x1800f4c39  cmp     eax, 0FFFFFFE2h
0x1800f4c3c  jnz     short loc_1800F4C43
0x1800f4c3e  jmp     loc_1800F4ED1
0x1800f4c43  test    byte ptr [rdi+4], 2
0x1800f4c47  jz      short loc_1800F4C50
0x1800f4c49  xor     eax, eax
0x1800f4c4b  jmp     loc_1800F4ED1
0x1800f4c50  mov     qword ptr [rdi+38h], 0
0x1800f4c58  mov     qword ptr [rdi+28h], 0
0x1800f4c60  mov     dword ptr [rdi+24h], 0
0x1800f4c67  mov     rcx, [rdi+1B0h]; hFile
0x1800f4c6e  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800f4c72  jz      short loc_1800F4CCC
0x1800f4c74  mov     rdx, [rdi+1D0h]; lDistanceToMove
0x1800f4c7b  test    rdx, rdx
0x1800f4c7e  js      short loc_1800F4CCC
0x1800f4c80  cmp     [rdi+1C0h], rdx
0x1800f4c87  jz      short loc_1800F4CCC
0x1800f4c89  call    la_ftruncate
0x1800f4c8e  cmp     eax, 0FFFFFFFFh
0x1800f4c91  jnz     short loc_1800F4CCC
0x1800f4c93  call    cs:__imp__o__errno
0x1800f4c99  lea     r8, aFileSizeCouldN; "File size could not be restored"
0x1800f4ca0  mov     rcx, rdi
0x1800f4ca3  mov     edx, [rax]
0x1800f4ca5  call    archive_set_error
0x1800f4caa  mov     rcx, [rdi+1B0h]; hObject
0x1800f4cb1  call    cs:__imp_CloseHandle
0x1800f4cb7  mov     eax, 0FFFFFFE7h
0x1800f4cbc  mov     qword ptr [rdi+1B0h], 0FFFFFFFFFFFFFFFFh
0x1800f4cc7  jmp     loc_1800F4ED1
0x1800f4ccc  xor     esi, esi
0x1800f4cce  test    dword ptr [rdi+1A0h], 14000001h
0x1800f4cd8  jz      short loc_1800F4D30
0x1800f4cda  mov     rcx, [rdi+158h]
0x1800f4ce1  mov     rbx, [rcx+78h]
0x1800f4ce5  call    archive_entry_uname
0x1800f4cea  mov     rdx, rax
0x1800f4ced  mov     r8, rbx
0x1800f4cf0  mov     rcx, rdi
0x1800f4cf3  call    archive_write_disk_uid
0x1800f4cf8  test    dword ptr [rdi+1A0h], 14000001h
0x1800f4d02  mov     [rdi+1E0h], rax
0x1800f4d09  jz      short loc_1800F4D30
0x1800f4d0b  mov     rcx, [rdi+158h]
0x1800f4d12  mov     rbx, [rcx+58h]
0x1800f4d16  call    archive_entry_gname
0x1800f4d1b  mov     rdx, rax
0x1800f4d1e  mov     r8, rbx
0x1800f4d21  mov     rcx, rdi
0x1800f4d24  call    archive_write_disk_gid
0x1800f4d29  mov     [rdi+1E8h], rax
0x1800f4d30  test    byte ptr [rdi+1A0h], 1
0x1800f4d37  jz      short loc_1800F4D43
0x1800f4d39  mov     rcx, rdi
0x1800f4d3c  call    set_ownership
0x1800f4d41  mov     esi, eax
0x1800f4d43  test    dword ptr [rdi+1A0h], 34000000h
0x1800f4d4d  jz      short loc_1800F4D63
0x1800f4d4f  movzx   edx, word ptr [rdi+1DCh]
0x1800f4d56  mov     rcx, rdi
0x1800f4d59  call    set_mode
0x1800f4d5e  cmp     eax, esi
0x1800f4d60  cmovl   esi, eax
0x1800f4d63  mov     ebx, [rdi+1A0h]
0x1800f4d69  test    bl, bl
0x1800f4d6b  jns     short loc_1800F4DB9
0x1800f4d6d  mov     rcx, [rdi+158h]
0x1800f4d74  call    archive_entry_xattr_count
0x1800f4d79  test    eax, eax
0x1800f4d7b  jz      short loc_1800F4DB1
0x1800f4d7d  cmp     cs:dword_1801547C8, 0
0x1800f4d84  jnz     short loc_1800F4DB1
0x1800f4d86  lea     r8, aCannotRestoreE; "Cannot restore extended attributes on t"...
0x1800f4d8d  mov     cs:dword_1801547C8, 1
0x1800f4d97  mov     edx, 2Ah ; '*'
0x1800f4d9c  mov     rcx, rdi
0x1800f4d9f  call    archive_set_error
0x1800f4da4  mov     ebx, [rdi+1A0h]
0x1800f4daa  mov     eax, 0FFFFFFECh
0x1800f4daf  jmp     short loc_1800F4DB3
0x1800f4db1  xor     eax, eax
0x1800f4db3  cmp     eax, esi
0x1800f4db5  jge     short loc_1800F4DB9
0x1800f4db7  mov     esi, eax
0x1800f4db9  test    bl, 40h
0x1800f4dbc  jz      short loc_1800F4DF7
0x1800f4dbe  mov     rax, [rdi+158h]
0x1800f4dc5  mov     edx, [rax+110h]
0x1800f4dcb  mov     r8d, [rax+114h]
0x1800f4dd2  test    edx, edx
0x1800f4dd4  jnz     short loc_1800F4DDF
0x1800f4dd6  test    r8d, r8d
0x1800f4dd9  jnz     short loc_1800F4DDF
0x1800f4ddb  xor     eax, eax
0x1800f4ddd  jmp     short loc_1800F4DF1
0x1800f4ddf  mov     rcx, [rdi+160h]; lpFileName
0x1800f4de6  call    set_fflags_platform
0x1800f4deb  mov     ebx, [rdi+1A0h]
0x1800f4df1  cmp     eax, esi
0x1800f4df3  jge     short loc_1800F4DF7
0x1800f4df5  mov     esi, eax
0x1800f4df7  test    bl, 4
0x1800f4dfa  jz      short loc_1800F4E09
0x1800f4dfc  mov     rcx, rdi
0x1800f4dff  call    set_times_from_entry
0x1800f4e04  cmp     eax, esi
0x1800f4e06  cmovl   esi, eax
0x1800f4e09  test    byte ptr [rdi+1A0h], 20h
0x1800f4e10  jz      short loc_1800F4E25
0x1800f4e12  mov     rcx, [rdi+158h]
0x1800f4e19  call    archive_entry_pathname_w
0x1800f4e1e  xor     eax, eax
0x1800f4e20  test    esi, esi
0x1800f4e22  cmovg   esi, eax
0x1800f4e25  mov     rcx, [rdi+1B0h]; hObject
0x1800f4e2c  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800f4e30  jz      short loc_1800F4EB1
0x1800f4e32  call    cs:__imp_CloseHandle
0x1800f4e38  cmp     qword ptr [rdi+180h], 0
0x1800f4e40  mov     qword ptr [rdi+1B0h], 0FFFFFFFFFFFFFFFFh
0x1800f4e4b  jz      short loc_1800F4EB1
0x1800f4e4d  mov     rcx, [rdi+160h]; lpFileName
0x1800f4e54  call    disk_unlink
0x1800f4e59  mov     rdx, [rdi+160h]
0x1800f4e60  mov     rcx, [rdi+180h]
0x1800f4e67  call    cs:__imp__o__wrename
0x1800f4e6d  test    eax, eax
0x1800f4e6f  jz      short loc_1800F4EA6
0x1800f4e71  call    cs:__imp_GetLastError
0x1800f4e77  mov     ecx, eax
0x1800f4e79  call    __la_dosmaperr
0x1800f4e7e  call    cs:__imp__o__errno
0x1800f4e84  lea     r8, aFailedToRename; "Failed to rename temporary file"
0x1800f4e8b  mov     rcx, rdi
0x1800f4e8e  mov     edx, [rax]
0x1800f4e90  call    archive_set_error
0x1800f4e95  mov     rcx, [rdi+180h]; lpFileName
0x1800f4e9c  mov     esi, 0FFFFFFE7h
0x1800f4ea1  call    disk_unlink
0x1800f4ea6  mov     qword ptr [rdi+180h], 0
0x1800f4eb1  mov     rcx, [rdi+158h]
0x1800f4eb8  call    archive_entry_free
0x1800f4ebd  mov     eax, esi
0x1800f4ebf  mov     qword ptr [rdi+158h], 0
0x1800f4eca  mov     dword ptr [rdi+4], 2
0x1800f4ed1  mov     rbx, [rsp+28h+arg_0]
0x1800f4ed6  mov     rsi, [rsp+28h+arg_8]
0x1800f4edb  add     rsp, 20h
0x1800f4edf  pop     rdi
0x1800f4ee0  retn
```
