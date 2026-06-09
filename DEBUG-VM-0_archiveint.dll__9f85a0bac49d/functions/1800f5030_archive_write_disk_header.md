# _archive_write_disk_header

- ea: `0x1800f5030`
- end: `0x1800f5503`
- name: `_archive_write_disk_header`
- size: `1235`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `reparse_path, authz_impersonation`

## callees

- `0x18000523c`
- `0x180007c80`
- `0x1800ac58c`
- `0x1800b1300`
- `0x1800b1b60`
- `0x1800b3660`
- `0x1800b36b0`
- `0x1800ed6c0`
- `0x1800f4c10`
- `0x1800f5030`
- `0x1800f5838`
- `0x1800f5acc`
- `0x1800f653c`
- `0x1800f6ea4`
- `0x1800f7330`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f51a8`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f51a8`
- `api-ms-win-crt-private-l1-1-0!_o__umask` at `0x1800f51c0`
- `api-ms-win-crt-private-l1-1-0!_o__umask` at `0x1800f51d0`
- `api-ms-win-crt-private-l1-1-0!_o__umask` at `0x1800f51c0`
- `api-ms-win-crt-private-l1-1-0!_o__umask` at `0x1800f51d0`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800f54ad`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800f54ad`

## string_xrefs

- `0x1800f5049`: `archive_write_disk_header`

## pseudocode

```c
__int64 __fastcall archive_write_disk_header(__int64 a1, __int64 a2)
{
  __int64 v4; // rcx
  __int64 v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rbp
  __int64 v9; // rax
  unsigned __int16 *v10; // rdx
  __int64 result; // rax
  __int64 v12; // rcx
  unsigned __int16 v13; // ax
  int v14; // r8d
  __int16 v15; // cx
  int v16; // edx
  int v17; // r15d
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  __int16 v22; // cx
  _QWORD *v23; // r8
  __int64 v24; // rdx
  int v25; // eax
  __int64 v26; // rax
  int v27; // ecx
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rbp
  int v32; // r14d
  int i; // ebx
  void *v34; // rcx
  __int64 BytesReturned; // [rsp+70h] [rbp+8h] BYREF
  __int64 v36; // [rsp+80h] [rbp+18h] BYREF

  if ( (unsigned int)_archive_check_magic(a1, 3221336261LL, 6, "archive_write_disk_header") == -30 )
    return 4294967266LL;
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 40) = 0;
  *(_DWORD *)(a1 + 36) = 0;
  if ( (*(_BYTE *)(a1 + 4) & 4) != 0 && (unsigned int)archive_write_disk_finish_entry(a1) == -30 )
    return 4294967266LL;
  v4 = *(_QWORD *)(a1 + 344);
  *(_QWORD *)(a1 + 336) = 0;
  *(_QWORD *)(a1 + 160) = 0;
  *(_DWORD *)(a1 + 420) = 0;
  archive_entry_free(v4);
  *(_QWORD *)(a1 + 344) = 0;
  v5 = archive_entry_clone(a2);
  *(_QWORD *)(a1 + 480) = *(_QWORD *)(a1 + 168);
  *(_QWORD *)(a1 + 344) = v5;
  *(_QWORD *)(a1 + 432) = -1;
  *(_QWORD *)(a1 + 448) = 0;
  *(_QWORD *)(a1 + 440) = 0;
  *(_DWORD *)(a1 + 472) = -1;
  *(_WORD *)(a1 + 476) = *(_WORD *)(v5 + 1032);
  if ( (*(_BYTE *)(v5 + 160) & 0x40) != 0 )
    v6 = *(_QWORD *)(v5 + 112);
  else
    v6 = -1;
  *(_QWORD *)(a1 + 464) = v6;
  *(_QWORD *)(a1 + 368) = 0;
  if ( archive_entry_pathname_w(v5) )
  {
    v7 = archive_entry_pathname_w(*(_QWORD *)(a1 + 344));
    v8 = -1;
    do
      ++v8;
    while ( *(_WORD *)(v7 + 2 * v8) );
  }
  v9 = archive_entry_pathname_w(*(_QWORD *)(a1 + 344));
  archive_wstrncat(a1 + 360, v9);
  v10 = *(unsigned __int16 **)(a1 + 360);
  *(_QWORD *)(a1 + 352) = v10;
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 40) = 0;
  *(_DWORD *)(a1 + 36) = 0;
  result = cleanup_pathname(a1, v10);
  if ( !(_DWORD)result )
  {
    if ( (int)permissive_name_w((_QWORD *)a1) >= 0 )
    {
      v13 = _o__umask(0);
      *(_WORD *)(a1 + 144) = v13;
      _o__umask(v13);
      v14 = *(_DWORD *)(a1 + 424);
      v15 = *(_WORD *)(a1 + 476);
      *(_DWORD *)(a1 + 416) = 0x20000000;
      if ( (v14 & 2) != 0 )
      {
        v16 = 1610612736;
        *(_DWORD *)(a1 + 416) = 1610612736;
        if ( (v15 & 0x400) != 0 )
        {
          v16 = 1711276032;
          *(_DWORD *)(a1 + 416) = 1711276032;
        }
        if ( (v15 & 0x800) != 0 )
        {
          v16 |= 0x18000000u;
          *(_DWORD *)(a1 + 416) = v16;
        }
      }
      else
      {
        v16 = 0x20000000;
        *(_WORD *)(a1 + 476) = v15 & ~*(_WORD *)(a1 + 144) & 0xF1FF;
      }
      if ( (v14 & 4) != 0 )
      {
        v16 |= 4u;
        *(_DWORD *)(a1 + 416) = v16;
      }
      if ( (v14 & 0x20) != 0 )
      {
        if ( (*(_WORD *)(*(_QWORD *)(a1 + 344) + 1032LL) & 0xF000) == 0x4000 )
        {
          *(_DWORD *)(a1 + 420) |= 0x20u;
        }
        else
        {
          v16 |= 0x20u;
          *(_DWORD *)(a1 + 416) = v16;
        }
      }
      if ( (v14 & 0x80u) != 0 )
      {
        v16 |= 0x80u;
        *(_DWORD *)(a1 + 416) = v16;
      }
      if ( (v14 & 0x40) != 0 )
        *(_DWORD *)(a1 + 416) = v16 | 0x40;
      if ( (v14 & 0x100) == 0 || (result = check_symlinks(a1), !(_DWORD)result) )
      {
        v17 = restore_entry(a1);
        if ( (*(_DWORD *)(a1 + 420) & 0x34000000) != 0 )
        {
          v18 = archive_entry_pathname_w(a2);
          v19 = current_fixup(a1, v18);
          *(_DWORD *)(v19 + 124) |= 0x20000000u;
          *(_WORD *)(v19 + 64) = *(_WORD *)(a1 + 476);
        }
        if ( (*(_BYTE *)(a1 + 420) & 4) != 0 && (*(_BYTE *)(a2 + 160) & 0x14) != 0 )
        {
          v20 = archive_entry_pathname_w(a2);
          v21 = current_fixup(a1, v20);
          v22 = *(_WORD *)(a1 + 476);
          v23 = (_QWORD *)(a1 + 200);
          v24 = v21;
          *(_DWORD *)(v21 + 124) |= 4u;
          *(_WORD *)(v21 + 64) = v22;
          if ( (*(_BYTE *)(a2 + 160) & 4) != 0 )
          {
            *(_QWORD *)(v21 + 72) = *(_QWORD *)(a2 + 24);
            v25 = *(_DWORD *)(a2 + 32);
          }
          else
          {
            *(_QWORD *)(v21 + 72) = *v23;
            v25 = 0;
          }
          *(_DWORD *)(v24 + 104) = v25;
          if ( (*(_BYTE *)(a2 + 160) & 0x10) != 0 )
          {
            v26 = *(_QWORD *)(a2 + 56);
            *(_QWORD *)(v24 + 88) = v26;
            v27 = *(_DWORD *)(a2 + 64);
          }
          else
          {
            v26 = *v23;
            v27 = 0;
            *(_QWORD *)(v24 + 88) = *v23;
          }
          *(_DWORD *)(v24 + 112) = v27;
          if ( (*(_BYTE *)(a2 + 160) & 0x20) != 0 )
          {
            *(_QWORD *)(v24 + 80) = *(_QWORD *)(a2 + 72);
            *(_DWORD *)(v24 + 108) = *(_DWORD *)(a2 + 80);
          }
          else
          {
            *(_QWORD *)(v24 + 80) = v26;
            *(_DWORD *)(v24 + 108) = v27;
          }
        }
        if ( (*(_BYTE *)(a1 + 420) & 0x20) != 0 )
        {
          v28 = archive_entry_pathname_w(a2);
          v29 = current_fixup(a1, v28);
          archive_acl_copy(v29 + 8, a2 + 1032);
        }
        if ( (*(_BYTE *)(a1 + 420) & 0x40) != 0 )
        {
          v30 = archive_entry_pathname_w(a2);
          *(_DWORD *)(current_fixup(a1, v30) + 120) = *(_DWORD *)(a2 + 272);
        }
        if ( *(_QWORD *)(a1 + 432) != -1 && (int)archive_entry_sparse_count(a2) > 0 )
        {
          *(_QWORD *)(a2 + 1120) = *(_QWORD *)(a2 + 1104);
          v31 = 0;
          BytesReturned = 0;
          v36 = 0;
          v32 = archive_entry_sparse_count(a2);
          for ( i = 0; i < v32; ++i )
          {
            archive_entry_sparse_next(a2, &BytesReturned, &v36);
            if ( BytesReturned - v31 >= 4096 )
            {
              v34 = *(void **)(a1 + 432);
              LODWORD(BytesReturned) = 0;
              DeviceIoControl(v34, 0x900C4u, 0, 0, 0, 0, (LPDWORD)&BytesReturned, 0);
              break;
            }
            v31 = BytesReturned + v36;
          }
        }
        if ( v17 >= -20 )
          *(_DWORD *)(a1 + 4) = 4;
        if ( *(_QWORD *)(a1 + 432) == -1 )
        {
          *(_DWORD *)(a2 + 160) |= 0x40u;
          *(_DWORD *)(a2 + 16) = 0;
          *(_QWORD *)(a2 + 112) = 0;
          *(_QWORD *)(a1 + 464) = 0;
        }
        return (unsigned int)v17;
      }
    }
    else
    {
      *(_DWORD *)_o__errno(v12) = 22;
      return 4294967271LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800f5030  mov     [rsp+arg_8], rbx
0x1800f5035  mov     [rsp+arg_18], rbp
0x1800f503a  push    rsi
0x1800f503b  push    rdi
0x1800f503c  push    r12
0x1800f503e  push    r14
0x1800f5040  push    r15
0x1800f5042  sub     rsp, 40h
0x1800f5046  mov     rsi, rdx
0x1800f5049  lea     r9, aArchiveWriteDi_8; "archive_write_disk_header"
0x1800f5050  mov     edx, 0C001B0C5h
0x1800f5055  mov     r8d, 6
0x1800f505b  mov     rdi, rcx
0x1800f505e  call    __archive_check_magic
0x1800f5063  cmp     eax, 0FFFFFFE2h
0x1800f5066  jz      loc_1800F54E5
0x1800f506c  xor     r12d, r12d
0x1800f506f  mov     [rdi+38h], r12
0x1800f5073  mov     [rdi+28h], r12
0x1800f5077  mov     [rdi+24h], r12d
0x1800f507b  test    byte ptr [rdi+4], 4
0x1800f507f  jz      short loc_1800F5092
0x1800f5081  mov     rcx, rdi
0x1800f5084  call    _archive_write_disk_finish_entry
0x1800f5089  cmp     eax, 0FFFFFFE2h
0x1800f508c  jz      loc_1800F54E5
0x1800f5092  mov     rcx, [rdi+158h]
0x1800f5099  mov     [rdi+150h], r12
0x1800f50a0  mov     [rdi+0A0h], r12
0x1800f50a7  mov     [rdi+1A4h], r12d
0x1800f50ae  call    archive_entry_free
0x1800f50b3  mov     rcx, rsi
0x1800f50b6  mov     [rdi+158h], r12
0x1800f50bd  call    archive_entry_clone
0x1800f50c2  mov     rcx, [rdi+0A8h]
0x1800f50c9  mov     [rdi+1E0h], rcx
0x1800f50d0  mov     [rdi+158h], rax
0x1800f50d7  mov     qword ptr [rdi+1B0h], 0FFFFFFFFFFFFFFFFh
0x1800f50e2  mov     [rdi+1C0h], r12
0x1800f50e9  mov     [rdi+1B8h], r12
0x1800f50f0  mov     dword ptr [rdi+1D8h], 0FFFFFFFFh
0x1800f50fa  movzx   ecx, word ptr [rax+408h]
0x1800f5101  mov     [rdi+1DCh], cx
0x1800f5108  test    byte ptr [rax+0A0h], 40h
0x1800f510f  jz      short loc_1800F5117
0x1800f5111  mov     rcx, [rax+70h]
0x1800f5115  jmp     short loc_1800F511B
0x1800f5117  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800f511b  mov     [rdi+1D0h], rcx
0x1800f5122  mov     rcx, rax
0x1800f5125  mov     [rdi+170h], r12
0x1800f512c  call    archive_entry_pathname_w
0x1800f5131  test    rax, rax
0x1800f5134  jnz     short loc_1800F513B
0x1800f5136  mov     rbp, r12
0x1800f5139  jmp     short loc_1800F5155
0x1800f513b  mov     rcx, [rdi+158h]
0x1800f5142  call    archive_entry_pathname_w
0x1800f5147  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1800f514b  inc     rbp
0x1800f514e  cmp     [rax+rbp*2], r12w
0x1800f5153  jnz     short loc_1800F514B
0x1800f5155  mov     rcx, [rdi+158h]
0x1800f515c  lea     rbx, [rdi+168h]
0x1800f5163  call    archive_entry_pathname_w
0x1800f5168  mov     rdx, rax
0x1800f516b  mov     r8, rbp
0x1800f516e  mov     rcx, rbx
0x1800f5171  call    archive_wstrncat
0x1800f5176  mov     rdx, [rbx]
0x1800f5179  mov     rcx, rdi
0x1800f517c  mov     [rdi+160h], rdx
0x1800f5183  mov     [rdi+38h], r12
0x1800f5187  mov     [rdi+28h], r12
0x1800f518b  mov     [rdi+24h], r12d
0x1800f518f  call    cleanup_pathname
0x1800f5194  test    eax, eax
0x1800f5196  jnz     loc_1800F54EA
0x1800f519c  mov     rcx, rdi
0x1800f519f  call    permissive_name_w
0x1800f51a4  test    eax, eax
0x1800f51a6  jns     short loc_1800F51BE
0x1800f51a8  call    cs:__imp__o__errno
0x1800f51ae  mov     dword ptr [rax], 16h
0x1800f51b4  mov     eax, 0FFFFFFE7h
0x1800f51b9  jmp     loc_1800F54EA
0x1800f51be  xor     ecx, ecx
0x1800f51c0  call    cs:__imp__o__umask
0x1800f51c6  movzx   ecx, ax
0x1800f51c9  mov     [rdi+90h], ax
0x1800f51d0  call    cs:__imp__o__umask
0x1800f51d6  mov     r8d, [rdi+1A8h]
0x1800f51dd  mov     ebx, 20000000h
0x1800f51e2  movzx   ecx, word ptr [rdi+1DCh]
0x1800f51e9  mov     [rdi+1A0h], ebx
0x1800f51ef  test    r8b, 2
0x1800f51f3  jz      short loc_1800F5227
0x1800f51f5  bt      cx, 0Ah
0x1800f51fa  mov     edx, 60000000h
0x1800f51ff  mov     [rdi+1A0h], edx
0x1800f5205  jnb     short loc_1800F5212
0x1800f5207  mov     edx, 66000000h
0x1800f520c  mov     [rdi+1A0h], edx
0x1800f5212  bt      cx, 0Bh
0x1800f5217  jnb     short loc_1800F5245
0x1800f5219  or      edx, 18000000h
0x1800f521f  mov     [rdi+1A0h], edx
0x1800f5225  jmp     short loc_1800F5245
0x1800f5227  movzx   eax, word ptr [rdi+90h]
0x1800f522e  mov     edx, ebx
0x1800f5230  not     ax
0x1800f5233  and     ax, cx
0x1800f5236  mov     ecx, 0F1FFh
0x1800f523b  and     ax, cx
0x1800f523e  mov     [rdi+1DCh], ax
0x1800f5245  test    r8b, 4
0x1800f5249  jz      short loc_1800F5254
0x1800f524b  or      edx, 4
0x1800f524e  mov     [rdi+1A0h], edx
0x1800f5254  test    r8b, 20h
0x1800f5258  jz      short loc_1800F528C
0x1800f525a  mov     rax, [rdi+158h]
0x1800f5261  movzx   ecx, word ptr [rax+408h]
0x1800f5268  mov     eax, 0F000h
0x1800f526d  and     cx, ax
0x1800f5270  mov     eax, 4000h
0x1800f5275  cmp     cx, ax
0x1800f5278  jnz     short loc_1800F5283
0x1800f527a  or      dword ptr [rdi+1A4h], 20h
0x1800f5281  jmp     short loc_1800F528C
0x1800f5283  or      edx, 20h
0x1800f5286  mov     [rdi+1A0h], edx
0x1800f528c  test    r8b, r8b
0x1800f528f  jns     short loc_1800F529B
0x1800f5291  bts     edx, 7
0x1800f5295  mov     [rdi+1A0h], edx
0x1800f529b  test    r8b, 40h
0x1800f529f  jz      short loc_1800F52AA
0x1800f52a1  or      edx, 40h
0x1800f52a4  mov     [rdi+1A0h], edx
0x1800f52aa  bt      r8d, 8
0x1800f52af  jnb     short loc_1800F52C1
0x1800f52b1  mov     rcx, rdi
0x1800f52b4  call    check_symlinks
0x1800f52b9  test    eax, eax
0x1800f52bb  jnz     loc_1800F54EA
0x1800f52c1  mov     rcx, rdi
0x1800f52c4  call    restore_entry
0x1800f52c9  test    dword ptr [rdi+1A4h], 34000000h
0x1800f52d3  mov     r15d, eax
0x1800f52d6  jz      short loc_1800F52F9
0x1800f52d8  mov     rcx, rsi
0x1800f52db  call    archive_entry_pathname_w
0x1800f52e0  mov     rdx, rax
0x1800f52e3  mov     rcx, rdi
0x1800f52e6  call    current_fixup
0x1800f52eb  or      [rax+7Ch], ebx
0x1800f52ee  movzx   ecx, word ptr [rdi+1DCh]
0x1800f52f5  mov     [rax+40h], cx
0x1800f52f9  test    byte ptr [rdi+1A4h], 4
0x1800f5300  jz      loc_1800F53A5
0x1800f5306  test    byte ptr [rsi+0A0h], 14h
0x1800f530d  jz      loc_1800F53A5
0x1800f5313  mov     rcx, rsi
0x1800f5316  call    archive_entry_pathname_w
0x1800f531b  mov     rdx, rax
0x1800f531e  mov     rcx, rdi
0x1800f5321  call    current_fixup
0x1800f5326  movzx   ecx, word ptr [rdi+1DCh]
0x1800f532d  lea     r8, [rdi+0C8h]
0x1800f5334  mov     rdx, rax
0x1800f5337  or      dword ptr [rax+7Ch], 4
0x1800f533b  mov     [rax+40h], cx
0x1800f533f  test    byte ptr [rsi+0A0h], 4
0x1800f5346  jz      short loc_1800F5355
0x1800f5348  mov     rcx, [rsi+18h]
0x1800f534c  mov     [rax+48h], rcx
0x1800f5350  mov     eax, [rsi+20h]
0x1800f5353  jmp     short loc_1800F535F
0x1800f5355  mov     rax, [r8]
0x1800f5358  mov     [rdx+48h], rax
0x1800f535c  mov     eax, r12d
0x1800f535f  mov     [rdx+68h], eax
0x1800f5362  test    byte ptr [rsi+0A0h], 10h
0x1800f5369  jz      short loc_1800F5378
0x1800f536b  mov     rax, [rsi+38h]
0x1800f536f  mov     [rdx+58h], rax
0x1800f5373  mov     ecx, [rsi+40h]
0x1800f5376  jmp     short loc_1800F5382
0x1800f5378  mov     rax, [r8]
0x1800f537b  mov     ecx, r12d
0x1800f537e  mov     [rdx+58h], rax
0x1800f5382  mov     [rdx+70h], ecx
0x1800f5385  test    byte ptr [rsi+0A0h], 20h
0x1800f538c  jz      short loc_1800F539E
0x1800f538e  mov     rax, [rsi+48h]
0x1800f5392  mov     [rdx+50h], rax
0x1800f5396  mov     eax, [rsi+50h]
0x1800f5399  mov     [rdx+6Ch], eax
0x1800f539c  jmp     short loc_1800F53A5
0x1800f539e  mov     [rdx+50h], rax
0x1800f53a2  mov     [rdx+6Ch], ecx
0x1800f53a5  test    byte ptr [rdi+1A4h], 20h
0x1800f53ac  jz      short loc_1800F53D1
0x1800f53ae  mov     rcx, rsi
0x1800f53b1  call    archive_entry_pathname_w
0x1800f53b6  mov     rdx, rax
0x1800f53b9  mov     rcx, rdi
0x1800f53bc  call    current_fixup
0x1800f53c1  lea     rdx, [rsi+408h]
0x1800f53c8  lea     rcx, [rax+8]
0x1800f53cc  call    archive_acl_copy
0x1800f53d1  test    byte ptr [rdi+1A4h], 40h
0x1800f53d8  jz      short loc_1800F53F6
0x1800f53da  mov     rcx, rsi
0x1800f53dd  call    archive_entry_pathname_w
0x1800f53e2  mov     rdx, rax
0x1800f53e5  mov     rcx, rdi
0x1800f53e8  call    current_fixup
0x1800f53ed  mov     ecx, [rsi+110h]
0x1800f53f3  mov     [rax+78h], ecx
0x1800f53f6  cmp     qword ptr [rdi+1B0h], 0FFFFFFFFFFFFFFFFh
0x1800f53fe  jz      loc_1800F54B3
0x1800f5404  mov     rcx, rsi
0x1800f5407  call    archive_entry_sparse_count
0x1800f540c  test    eax, eax
0x1800f540e  jle     loc_1800F54B3
0x1800f5414  mov     rax, [rsi+450h]
0x1800f541b  mov     rcx, rsi
0x1800f541e  mov     [rsi+460h], rax
0x1800f5425  mov     rbp, r12
0x1800f5428  mov     [rsp+68h+BytesReturned], r12
0x1800f542d  mov     [rsp+68h+arg_10], r12
0x1800f5435  call    archive_entry_sparse_count
0x1800f543a  mov     r14d, eax
0x1800f543d  mov     ebx, r12d
0x1800f5440  cmp     ebx, r14d
0x1800f5443  jge     short loc_1800F54B3
0x1800f5445  lea     r8, [rsp+68h+arg_10]
0x1800f544d  mov     rcx, rsi
0x1800f5450  lea     rdx, [rsp+68h+BytesReturned]
0x1800f5455  call    archive_entry_sparse_next
0x1800f545a  mov     rdx, [rsp+68h+BytesReturned]
0x1800f545f  mov     rcx, rdx
0x1800f5462  sub     rcx, rbp
0x1800f5465  cmp     rcx, 1000h
0x1800f546c  jge     short loc_1800F547D
0x1800f546e  mov     rbp, [rsp+68h+arg_10]
0x1800f5476  add     rbp, rdx
0x1800f5479  inc     ebx
0x1800f547b  jmp     short loc_1800F5440
0x1800f547d  mov     rcx, [rdi+1B0h]; hDevice
0x1800f5484  lea     rax, [rsp+68h+BytesReturned]
0x1800f5489  mov     [rsp+68h+lpOverlapped], r12; lpOverlapped
0x1800f548e  xor     r9d, r9d; nInBufferSize
0x1800f5491  mov     [rsp+68h+lpBytesReturned], rax; lpBytesReturned
0x1800f5496  xor     r8d, r8d; lpInBuffer
0x1800f5499  mov     [rsp+68h+nOutBufferSize], r12d; nOutBufferSize
0x1800f549e  mov     edx, 900C4h; dwIoControlCode
0x1800f54a3  mov     [rsp+68h+lpOutBuffer], r12; lpOutBuffer
0x1800f54a8  mov     dword ptr [rsp+68h+BytesReturned], r12d
0x1800f54ad  call    cs:__imp_DeviceIoControl
0x1800f54b3  cmp     r15d, 0FFFFFFECh
0x1800f54b7  jl      short loc_1800F54C0
0x1800f54b9  mov     dword ptr [rdi+4], 4
0x1800f54c0  cmp     qword ptr [rdi+1B0h], 0FFFFFFFFFFFFFFFFh
0x1800f54c8  jnz     short loc_1800F54E0
0x1800f54ca  or      dword ptr [rsi+0A0h], 40h
0x1800f54d1  mov     [rsi+10h], r12d
0x1800f54d5  mov     [rsi+70h], r12
0x1800f54d9  mov     [rdi+1D0h], r12
0x1800f54e0  mov     eax, r15d
0x1800f54e3  jmp     short loc_1800F54EA
0x1800f54e5  mov     eax, 0FFFFFFE2h
0x1800f54ea  lea     r11, [rsp+68h+var_28]
0x1800f54ef  mov     rbx, [r11+38h]
0x1800f54f3  mov     rbp, [r11+48h]
0x1800f54f7  mov     rsp, r11
0x1800f54fa  pop     r15
0x1800f54fc  pop     r14
0x1800f54fe  pop     r12
0x1800f5500  pop     rdi
0x1800f5501  pop     rsi
0x1800f5502  retn
```
