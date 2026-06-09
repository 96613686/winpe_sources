# header_common

- ea: `0x1800dfbe4`
- end: `0x1800e0106`
- name: `header_common`
- size: `1314`
- prototype: ``
- caller_count: `3`
- callee_count: `15`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x1800e023c`
- `0x1800e04d4`
- `0x1800e0b90`

## callees

- `0x180006c00`
- `0x18000a2d0`
- `0x18000ce38`
- `0x18000e920`
- `0x1800144b0`
- `0x1800b0a20`
- `0x1800b0a70`
- `0x1800b1ce0`
- `0x1800b1db0`
- `0x1800b24b0`
- `0x1800b24d0`
- `0x1800b2770`
- `0x1800b2840`
- `0x1800deeb0`
- `0x1800dfbe4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800dff1b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800dffd6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800dffed`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800dff1b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800dffd6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800dffed`

## string_xrefs

- `0x1800dfef4`: `Linkname`
- `0x1800dffb3`: `Linkname`

## pseudocode

```c
__int64 __fastcall header_common(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int16 v8; // ax
  int v9; // esi
  __int16 v10; // r15
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rax
  char v16; // al
  __int64 v17; // rax
  char v19; // al
  __int64 v20; // rax
  int v21; // eax
  unsigned int v22; // r15d
  __int16 v23; // ax
  _WORD *v24; // rsi
  _BYTE *v25; // rax
  _WORD *v26; // rsi
  _BYTE *v27; // rax
  __int64 v28; // rax
  int v29; // eax
  __int16 v30; // ax
  void *Block; // [rsp+20h] [rbp-28h] BYREF
  __int64 v32; // [rsp+28h] [rbp-20h]
  __int64 v33; // [rsp+30h] [rbp-18h]

  v8 = tar_atol(a4 + 100, 8);
  *(_DWORD *)(a3 + 160) |= 0x400u;
  v9 = *(_DWORD *)(a3 + 160);
  v10 = v8 ^ (*(_WORD *)(a3 + 1032) ^ v8) & 0xFFF;
  *(_DWORD *)(a3 + 16) = 0;
  *(_WORD *)(a3 + 1032) = v10;
  if ( (v9 & 0x200) == 0 )
  {
    v9 |= 0x200u;
    *(_WORD *)(a3 + 1032) = v10 ^ (v10 ^ tar_atol(a4 + 100, 8)) & 0xFFF;
    *(_DWORD *)(a3 + 160) = v9;
  }
  if ( (v9 & 0x800) == 0 )
  {
    v11 = tar_atol(a4 + 108, 8);
    v12 = 0;
    if ( v11 >= 0 )
      v12 = v11;
    v9 |= 0x800u;
    *(_DWORD *)(a3 + 160) = v9;
    *(_QWORD *)(a3 + 120) = v12;
  }
  if ( (v9 & 0x1000) == 0 )
  {
    v13 = tar_atol(a4 + 116, 8);
    v14 = 0;
    if ( v13 >= 0 )
      v14 = v13;
    v9 |= 0x1000u;
    *(_DWORD *)(a3 + 160) = v9;
    *(_QWORD *)(a3 + 88) = v14;
  }
  if ( (v9 & 0x10) == 0 )
  {
    v15 = tar_atol(a4 + 136, 12);
    archive_entry_set_mtime(a3, v15, 0);
  }
  v16 = *(_BYTE *)(a2 + 266);
  if ( (v16 & 2) != 0 )
  {
    v17 = *(_QWORD *)(a2 + 192);
  }
  else if ( (v16 & 4) == 0 || *(_DWORD *)(a2 + 256) )
  {
    if ( (v16 & 8) != 0 )
    {
      v17 = *(_QWORD *)(a2 + 208);
    }
    else if ( (v16 & 1) != 0 )
    {
      v17 = *(_QWORD *)(a2 + 216);
    }
    else
    {
      v17 = tar_atol(a4 + 124, 12);
    }
  }
  else
  {
    v17 = *(_QWORD *)(a2 + 200);
  }
  *(_QWORD *)(a2 + 184) = v17;
  if ( v17 < 0 )
  {
    archive_set_error(a1, 0xFFFFFFFFLL, "Tar entry has negative file size");
    return 4294967266LL;
  }
  if ( v17 > 0xFFFFFFFFFFFFFFFLL )
  {
LABEL_27:
    archive_set_error(a1, 0xFFFFFFFFLL, "Tar entry size overflow");
    return 4294967266LL;
  }
  *(_DWORD *)(a3 + 160) |= 0x40u;
  *(_DWORD *)(a3 + 16) = 0;
  *(_QWORD *)(a3 + 112) = v17;
  v19 = *(_BYTE *)(a2 + 266);
  if ( (v19 & 4) != 0 && *(_DWORD *)(a2 + 256) == 1 )
  {
    v20 = *(_QWORD *)(a2 + 200);
  }
  else if ( (v19 & 1) != 0 )
  {
    v20 = *(_QWORD *)(a2 + 216);
  }
  else
  {
    v20 = tar_atol(a4 + 124, 12);
  }
  *(_QWORD *)(a2 + 152) = v20;
  if ( v20 < 0 )
  {
    *(_QWORD *)(a2 + 152) = 0;
    archive_set_error(a1, 0xFFFFFFFFLL, "Tar entry has negative size");
    return 4294967266LL;
  }
  if ( v20 > 0xFFFFFFFFFFFFFFFLL )
  {
    *(_QWORD *)(a2 + 152) = 0;
    goto LABEL_27;
  }
  v21 = *(char *)(a4 + 156);
  v22 = 0;
  *(_BYTE *)(a2 + 265) = *(_BYTE *)(a4 + 156);
  if ( (char)v21 > 53 )
  {
    switch ( v21 )
    {
      case '6':
        *(_WORD *)(a3 + 1032) &= 0xFFFu;
        v23 = 4096;
        goto LABEL_78;
      case 'D':
        *(_WORD *)(a3 + 1032) &= 0xFFFu;
        v30 = 0x4000;
        goto LABEL_76;
      case 'M':
        return v22;
    }
LABEL_74:
    *(_WORD *)(a3 + 1032) &= 0xFFFu;
    v30 = 0x8000;
LABEL_76:
    *(_WORD *)(a3 + 1032) |= v30;
    *(_DWORD *)(a3 + 160) |= 0x400u;
    *(_DWORD *)(a3 + 16) = 0;
    return v22;
  }
  if ( (_BYTE)v21 == 53 )
  {
    *(_WORD *)(a3 + 1032) &= 0xFFFu;
    v23 = 0x4000;
    goto LABEL_78;
  }
  if ( v21 == 48 )
    goto LABEL_74;
  if ( v21 != 49 )
  {
    if ( v21 != 50 )
    {
      if ( v21 == 51 )
      {
        *(_WORD *)(a3 + 1032) &= 0xFFFu;
        v23 = 0x2000;
        goto LABEL_78;
      }
      if ( v21 == 52 )
      {
        *(_WORD *)(a3 + 1032) &= 0xFFFu;
        v23 = 24576;
LABEL_78:
        *(_WORD *)(a3 + 1032) |= v23;
        *(_DWORD *)(a3 + 160) |= 0x440u;
LABEL_79:
        *(_DWORD *)(a3 + 16) = 0;
        *(_QWORD *)(a3 + 112) = 0;
        *(_QWORD *)(a2 + 152) = 0;
        return v22;
      }
      goto LABEL_74;
    }
    archive_entry_set_link_to_symlink(a3);
    v24 = (_WORD *)archive_entry_symlink_w(a3);
    v25 = (_BYTE *)archive_entry_symlink(a3);
    if ( v25 && *v25 || v24 && *v24 )
    {
LABEL_54:
      *(_WORD *)(a3 + 1032) &= 0xFFFu;
      v23 = -24576;
      goto LABEL_78;
    }
    Block = 0;
    v33 = 0;
    v32 = 0;
    archive_strncat(&Block, a4 + 157, 100);
    if ( !(unsigned int)archive_entry_copy_symlink_l(a3, Block, v32, *(_QWORD *)(a2 + 304))
      || (v22 = set_conversion_failed_error(a1, *(_QWORD *)(a2 + 304), "Linkname"), v22 != -30) )
    {
      v32 = 0;
      v33 = 0;
      free(Block);
      goto LABEL_54;
    }
LABEL_61:
    v32 = 0;
    v33 = 0;
    free(Block);
    return 4294967266LL;
  }
  archive_entry_set_link_to_hardlink(a3);
  v26 = (_WORD *)archive_entry_hardlink_w(a3);
  v27 = (_BYTE *)archive_entry_hardlink(a3);
  if ( (!v27 || !*v27) && (!v26 || !*v26) )
  {
    Block = 0;
    v33 = 0;
    v32 = 0;
    archive_strncat(&Block, a4 + 157, 100);
    if ( (unsigned int)archive_entry_copy_hardlink_l(a3, Block, v32, *(_QWORD *)(a2 + 304)) )
    {
      v22 = set_conversion_failed_error(a1, *(_QWORD *)(a2 + 304), "Linkname");
      if ( v22 == -30 )
        goto LABEL_61;
    }
    v32 = 0;
    v33 = 0;
    free(Block);
  }
  v28 = *(_QWORD *)(a3 + 112);
  if ( v28 > 0 )
  {
    *(_DWORD *)(a3 + 16) = 0;
    *(_WORD *)(a3 + 1032) &= 0xFFFu;
    *(_WORD *)(a3 + 1032) |= 0x8000u;
    *(_DWORD *)(a3 + 160) |= 0x400u;
    goto LABEL_66;
  }
  if ( v28 )
  {
LABEL_66:
    v29 = *(_DWORD *)(a1 + 16);
    if ( v29 == 196610 || ((v29 - 196608) & 0xFFFFFFFB) != 0 && (int)archive_read_format_tar_bid(a1, 50) <= 50 )
      return v22;
    *(_DWORD *)(a3 + 160) |= 0x40u;
    goto LABEL_79;
  }
  return v22;
}

```

## disassembly

```asm
0x1800dfbe4  push    rbp
0x1800dfbe6  push    rbx
0x1800dfbe7  push    rsi
0x1800dfbe8  push    rdi
0x1800dfbe9  push    r12
0x1800dfbeb  push    r13
0x1800dfbed  push    r14
0x1800dfbef  push    r15
0x1800dfbf1  mov     rbp, rsp
0x1800dfbf4  sub     rsp, 48h
0x1800dfbf8  mov     rdi, rdx
0x1800dfbfb  mov     r14, rcx
0x1800dfbfe  mov     edx, 8
0x1800dfc03  lea     rcx, [r9+64h]
0x1800dfc07  mov     r13, r9
0x1800dfc0a  mov     rbx, r8
0x1800dfc0d  call    tar_atol
0x1800dfc12  bts     dword ptr [rbx+0A0h], 0Ah
0x1800dfc1a  movzx   r15d, ax
0x1800dfc1e  xor     r15w, [rbx+408h]
0x1800dfc26  mov     ecx, 0FFFh
0x1800dfc2b  mov     esi, [rbx+0A0h]
0x1800dfc31  and     r15w, cx
0x1800dfc35  xor     r15w, ax
0x1800dfc39  mov     dword ptr [rbx+10h], 0
0x1800dfc40  mov     [rbx+408h], r15w
0x1800dfc48  bt      esi, 9
0x1800dfc4c  jb      short loc_1800DFC7D
0x1800dfc4e  mov     edx, 8
0x1800dfc53  lea     rcx, [r13+64h]
0x1800dfc57  call    tar_atol
0x1800dfc5c  xor     ax, r15w
0x1800dfc60  mov     ecx, 0FFFh
0x1800dfc65  and     ax, cx
0x1800dfc68  xor     ax, r15w
0x1800dfc6c  bts     esi, 9
0x1800dfc70  mov     [rbx+408h], ax
0x1800dfc77  mov     [rbx+0A0h], esi
0x1800dfc7d  mov     r15d, 800h
0x1800dfc83  test    r15d, esi
0x1800dfc86  jnz     short loc_1800DFCB2
0x1800dfc88  lea     rcx, [r13+6Ch]
0x1800dfc8c  mov     edx, 8
0x1800dfc91  call    tar_atol
0x1800dfc96  xor     r12d, r12d
0x1800dfc99  test    rax, rax
0x1800dfc9c  mov     ecx, r12d
0x1800dfc9f  cmovns  rcx, rax
0x1800dfca3  or      esi, r15d
0x1800dfca6  mov     [rbx+0A0h], esi
0x1800dfcac  mov     [rbx+78h], rcx
0x1800dfcb0  jmp     short loc_1800DFCB5
0x1800dfcb2  xor     r12d, r12d
0x1800dfcb5  mov     r15d, 1000h
0x1800dfcbb  test    r15d, esi
0x1800dfcbe  jnz     short loc_1800DFCE5
0x1800dfcc0  lea     rcx, [r13+74h]
0x1800dfcc4  mov     edx, 8
0x1800dfcc9  call    tar_atol
0x1800dfcce  test    rax, rax
0x1800dfcd1  mov     rcx, r12
0x1800dfcd4  cmovns  rcx, rax
0x1800dfcd8  or      esi, r15d
0x1800dfcdb  mov     [rbx+0A0h], esi
0x1800dfce1  mov     [rbx+58h], rcx
0x1800dfce5  mov     r15d, 0Ch
0x1800dfceb  test    sil, 10h
0x1800dfcef  jnz     short loc_1800DFD0E
0x1800dfcf1  lea     rcx, [r13+88h]
0x1800dfcf8  mov     edx, r15d
0x1800dfcfb  call    tar_atol
0x1800dfd00  mov     rdx, rax
0x1800dfd03  xor     r8d, r8d
0x1800dfd06  mov     rcx, rbx
0x1800dfd09  call    archive_entry_set_mtime
0x1800dfd0e  mov     al, [rdi+10Ah]
0x1800dfd14  test    al, 2
0x1800dfd16  jz      short loc_1800DFD21
0x1800dfd18  mov     rax, [rdi+0C0h]
0x1800dfd1f  jmp     short loc_1800DFD5D
0x1800dfd21  test    al, 4
0x1800dfd23  jz      short loc_1800DFD37
0x1800dfd25  cmp     [rdi+100h], r12d
0x1800dfd2c  jnz     short loc_1800DFD37
0x1800dfd2e  mov     rax, [rdi+0C8h]
0x1800dfd35  jmp     short loc_1800DFD5D
0x1800dfd37  test    al, 8
0x1800dfd39  jz      short loc_1800DFD44
0x1800dfd3b  mov     rax, [rdi+0D0h]
0x1800dfd42  jmp     short loc_1800DFD5D
0x1800dfd44  test    al, 1
0x1800dfd46  jz      short loc_1800DFD51
0x1800dfd48  mov     rax, [rdi+0D8h]
0x1800dfd4f  jmp     short loc_1800DFD5D
0x1800dfd51  lea     rcx, [r13+7Ch]
0x1800dfd55  mov     rdx, r15
0x1800dfd58  call    tar_atol
0x1800dfd5d  mov     [rdi+0B8h], rax
0x1800dfd64  test    rax, rax
0x1800dfd67  jns     short loc_1800DFD85
0x1800dfd69  lea     r8, aTarEntryHasNeg; "Tar entry has negative file size"
0x1800dfd70  or      edx, 0FFFFFFFFh
0x1800dfd73  mov     rcx, r14
0x1800dfd76  call    archive_set_error
0x1800dfd7b  mov     eax, 0FFFFFFE2h
0x1800dfd80  jmp     loc_1800E00F5
0x1800dfd85  mov     rsi, 0FFFFFFFFFFFFFFFh
0x1800dfd8f  cmp     rax, rsi
0x1800dfd92  jle     short loc_1800DFD9D
0x1800dfd94  lea     r8, aTarEntrySizeOv; "Tar entry size overflow"
0x1800dfd9b  jmp     short loc_1800DFD70
0x1800dfd9d  or      dword ptr [rbx+0A0h], 40h
0x1800dfda4  mov     [rbx+10h], r12d
0x1800dfda8  mov     [rbx+70h], rax
0x1800dfdac  mov     al, [rdi+10Ah]
0x1800dfdb2  test    al, 4
0x1800dfdb4  jz      short loc_1800DFDC8
0x1800dfdb6  cmp     dword ptr [rdi+100h], 1
0x1800dfdbd  jnz     short loc_1800DFDC8
0x1800dfdbf  mov     rax, [rdi+0C8h]
0x1800dfdc6  jmp     short loc_1800DFDE1
0x1800dfdc8  test    al, 1
0x1800dfdca  jz      short loc_1800DFDD5
0x1800dfdcc  mov     rax, [rdi+0D8h]
0x1800dfdd3  jmp     short loc_1800DFDE1
0x1800dfdd5  lea     rcx, [r13+7Ch]
0x1800dfdd9  mov     rdx, r15
0x1800dfddc  call    tar_atol
0x1800dfde1  mov     [rdi+98h], rax
0x1800dfde8  test    rax, rax
0x1800dfdeb  jns     short loc_1800DFE00
0x1800dfded  mov     [rdi+98h], r12
0x1800dfdf4  lea     r8, aTarEntryHasNeg_0; "Tar entry has negative size"
0x1800dfdfb  jmp     loc_1800DFD70
0x1800dfe00  cmp     rax, rsi
0x1800dfe03  jle     short loc_1800DFE0E
0x1800dfe05  mov     [rdi+98h], r12
0x1800dfe0c  jmp     short loc_1800DFD94
0x1800dfe0e  movsx   eax, byte ptr [r13+9Ch]
0x1800dfe16  mov     r15d, r12d
0x1800dfe19  mov     [rdi+109h], al
0x1800dfe1f  cmp     al, 35h ; '5'
0x1800dfe21  jg      loc_1800E0077
0x1800dfe27  jz      loc_1800E0064
0x1800dfe2d  mov     ecx, eax
0x1800dfe2f  sub     ecx, 30h ; '0'
0x1800dfe32  jz      loc_1800E0088
0x1800dfe38  sub     ecx, 1
0x1800dfe3b  jz      loc_1800DFF37
0x1800dfe41  sub     ecx, 1
0x1800dfe44  jz      short loc_1800DFE80
0x1800dfe46  sub     ecx, 1
0x1800dfe49  jz      short loc_1800DFE6A
0x1800dfe4b  cmp     ecx, 1
0x1800dfe4e  jnz     loc_1800E0088
0x1800dfe54  mov     eax, 0FFFh
0x1800dfe59  and     [rbx+408h], ax
0x1800dfe60  mov     eax, 6000h
0x1800dfe65  jmp     loc_1800E00D2
0x1800dfe6a  mov     eax, 0FFFh
0x1800dfe6f  and     [rbx+408h], ax
0x1800dfe76  mov     eax, 2000h
0x1800dfe7b  jmp     loc_1800E00D2
0x1800dfe80  mov     rcx, rbx
0x1800dfe83  call    archive_entry_set_link_to_symlink
0x1800dfe88  mov     rcx, rbx
0x1800dfe8b  call    archive_entry_symlink_w
0x1800dfe90  mov     rcx, rbx
0x1800dfe93  mov     rsi, rax
0x1800dfe96  call    archive_entry_symlink
0x1800dfe9b  test    rax, rax
0x1800dfe9e  jz      short loc_1800DFEA5
0x1800dfea0  cmp     [rax], r12b
0x1800dfea3  jnz     short loc_1800DFF21
0x1800dfea5  test    rsi, rsi
0x1800dfea8  jz      short loc_1800DFEB0
0x1800dfeaa  cmp     [rsi], r12w
0x1800dfeae  jnz     short loc_1800DFF21
0x1800dfeb0  lea     rdx, [r13+9Dh]
0x1800dfeb7  mov     [rbp+Block], r12
0x1800dfebb  mov     r8d, 64h ; 'd'
0x1800dfec1  mov     [rbp+var_18], r12
0x1800dfec5  lea     rcx, [rbp+Block]
0x1800dfec9  mov     [rbp+var_20], r12
0x1800dfecd  call    archive_strncat
0x1800dfed2  mov     r9, [rdi+130h]
0x1800dfed9  mov     rcx, rbx
0x1800dfedc  mov     r8, [rbp+var_20]
0x1800dfee0  mov     rdx, [rbp+Block]
0x1800dfee4  call    _archive_entry_copy_symlink_l
0x1800dfee9  test    eax, eax
0x1800dfeeb  jz      short loc_1800DFF0F
0x1800dfeed  mov     rdx, [rdi+130h]
0x1800dfef4  lea     r8, aLinkname; "Linkname"
0x1800dfefb  mov     rcx, r14
0x1800dfefe  call    set_conversion_failed_error
0x1800dff03  mov     r15d, eax
0x1800dff06  cmp     eax, 0FFFFFFE2h
0x1800dff09  jz      loc_1800DFFCA
0x1800dff0f  mov     rcx, [rbp+Block]; Block
0x1800dff13  mov     [rbp+var_20], r12
0x1800dff17  mov     [rbp+var_18], r12
0x1800dff1b  call    cs:__imp_free
0x1800dff21  mov     eax, 0FFFh
0x1800dff26  and     [rbx+408h], ax
0x1800dff2d  mov     eax, 0A000h
0x1800dff32  jmp     loc_1800E00D2
0x1800dff37  mov     rcx, rbx
0x1800dff3a  call    archive_entry_set_link_to_hardlink
0x1800dff3f  mov     rcx, rbx
0x1800dff42  call    archive_entry_hardlink_w
0x1800dff47  mov     rcx, rbx
0x1800dff4a  mov     rsi, rax
0x1800dff4d  call    archive_entry_hardlink
0x1800dff52  test    rax, rax
0x1800dff55  jz      short loc_1800DFF60
0x1800dff57  cmp     [rax], r12b
0x1800dff5a  jnz     loc_1800DFFF3
0x1800dff60  test    rsi, rsi
0x1800dff63  jz      short loc_1800DFF6F
0x1800dff65  cmp     [rsi], r12w
0x1800dff69  jnz     loc_1800DFFF3
0x1800dff6f  lea     rdx, [r13+9Dh]
0x1800dff76  mov     [rbp+Block], r12
0x1800dff7a  mov     r8d, 64h ; 'd'
0x1800dff80  mov     [rbp+var_18], r12
0x1800dff84  lea     rcx, [rbp+Block]
0x1800dff88  mov     [rbp+var_20], r12
0x1800dff8c  call    archive_strncat
0x1800dff91  mov     r9, [rdi+130h]
0x1800dff98  mov     rcx, rbx
0x1800dff9b  mov     r8, [rbp+var_20]
0x1800dff9f  mov     rdx, [rbp+Block]
0x1800dffa3  call    _archive_entry_copy_hardlink_l
0x1800dffa8  test    eax, eax
0x1800dffaa  jz      short loc_1800DFFE1
0x1800dffac  mov     rdx, [rdi+130h]
0x1800dffb3  lea     r8, aLinkname; "Linkname"
0x1800dffba  mov     rcx, r14
0x1800dffbd  call    set_conversion_failed_error
0x1800dffc2  mov     r15d, eax
0x1800dffc5  cmp     eax, 0FFFFFFE2h
0x1800dffc8  jnz     short loc_1800DFFE1
0x1800dffca  mov     rcx, [rbp+Block]; Block
0x1800dffce  mov     [rbp+var_20], r12
0x1800dffd2  mov     [rbp+var_18], r12
0x1800dffd6  call    cs:__imp_free
0x1800dffdc  jmp     loc_1800DFD7B
0x1800dffe1  mov     rcx, [rbp+Block]; Block
0x1800dffe5  mov     [rbp+var_20], r12
0x1800dffe9  mov     [rbp+var_18], r12
0x1800dffed  call    cs:__imp_free
0x1800dfff3  mov     rax, [rbx+70h]
0x1800dfff7  test    rax, rax
0x1800dfffa  jle     short loc_1800E0024
0x1800dfffc  mov     eax, 0FFFh
0x1800e0001  mov     [rbx+10h], r12d
0x1800e0005  and     [rbx+408h], ax
0x1800e000c  mov     eax, 8000h
0x1800e0011  or      [rbx+408h], ax
0x1800e0018  or      dword ptr [rbx+0A0h], 400h
0x1800e0022  jmp     short loc_1800E002A
0x1800e0024  jz      loc_1800E00F2
0x1800e002a  mov     eax, [r14+10h]
0x1800e002e  cmp     eax, 30002h
0x1800e0033  jz      loc_1800E00F2
0x1800e0039  add     eax, 0FFFD0000h
0x1800e003e  test    eax, 0FFFFFFFBh
0x1800e0043  jz      short loc_1800E005B
0x1800e0045  mov     edx, 32h ; '2'
0x1800e004a  mov     rcx, r14
0x1800e004d  call    archive_read_format_tar_bid
0x1800e0052  cmp     eax, 32h ; '2'
0x1800e0055  jle     loc_1800E00F2
0x1800e005b  or      dword ptr [rbx+0A0h], 40h
0x1800e0062  jmp     short loc_1800E00E3
0x1800e0064  mov     eax, 0FFFh
0x1800e0069  and     [rbx+408h], ax
0x1800e0070  mov     eax, 4000h
0x1800e0075  jmp     short loc_1800E00D2
0x1800e0077  mov     ecx, eax
0x1800e0079  sub     ecx, 36h ; '6'
0x1800e007c  jz      short loc_1800E00C1
0x1800e007e  sub     ecx, 0Eh
0x1800e0081  jz      short loc_1800E009B
0x1800e0083  sub     ecx, 9
0x1800e0086  jz      short loc_1800E00F2
0x1800e0088  mov     eax, 0FFFh
0x1800e008d  and     [rbx+408h], ax
0x1800e0094  mov     eax, 8000h
0x1800e0099  jmp     short loc_1800E00AC
0x1800e009b  mov     eax, 0FFFh
0x1800e00a0  and     [rbx+408h], ax
0x1800e00a7  mov     eax, 4000h
0x1800e00ac  or      [rbx+408h], ax
0x1800e00b3  bts     dword ptr [rbx+0A0h], 0Ah
0x1800e00bb  mov     [rbx+10h], r12d
0x1800e00bf  jmp     short loc_1800E00F2
0x1800e00c1  mov     eax, 0FFFh
0x1800e00c6  and     [rbx+408h], ax
  ... truncated ...
```
