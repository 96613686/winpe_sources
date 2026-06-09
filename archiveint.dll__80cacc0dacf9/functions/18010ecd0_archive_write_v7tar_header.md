# archive_write_v7tar_header

- ea: `0x18010ecd0`
- end: `0x18010f02f`
- name: `archive_write_v7tar_header`
- size: `863`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `reparse_path`

## callees

- `0x180006c00`
- `0x180007c80`
- `0x18000a2d0`
- `0x18000b4d0`
- `0x18000e8d4`
- `0x180014ab4`
- `0x180014fc0`
- `0x1800b1b60`
- `0x1800b1ce0`
- `0x1800b1f40`
- `0x1800b2770`
- `0x1800ece24`
- `0x1800ecf00`
- `0x1800ed554`
- `0x1800ed5e0`
- `0x1800ed6c0`
- `0x1800ef2d4`
- `0x18010ecd0`
- `0x18010f038`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18010ee3a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18010ef69`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18010ee3a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18010ef69`

## string_xrefs

- `0x18010ed45`: `Can't record entry in tar file without pathname`

## pseudocode

```c
__int64 __fastcall archive_write_v7tar_header(__int64 a1, __int64 a2)
{
  __int64 v2; // r12
  __int64 v5; // r13
  __int64 v7; // rsi
  __int64 v8; // r15
  __int64 v9; // rdi
  _BYTE *v10; // rdi
  __int64 v11; // r15
  __int64 v12; // rdx
  __int64 v13; // rsi
  __int64 v14; // r9
  int v15; // edi
  int v16; // eax
  __int64 v17; // rax
  void *Block; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v19; // [rsp+38h] [rbp-C8h]
  __int64 v20; // [rsp+40h] [rbp-C0h]
  _BYTE v21[512]; // [rsp+50h] [rbp-B0h] BYREF

  v2 = *(_QWORD *)(a1 + 248);
  v5 = *(_QWORD *)(v2 + 16);
  if ( !v5 )
  {
    if ( !*(_DWORD *)(v2 + 32) )
    {
      *(_QWORD *)(v2 + 24) = archive_string_default_conversion_for_write();
      *(_DWORD *)(v2 + 32) = 1;
    }
    v5 = *(_QWORD *)(v2 + 24);
  }
  if ( !archive_entry_pathname(a2) )
  {
    archive_set_error(a1, -1, "Can't record entry in tar file without pathname");
    return 4294967271LL;
  }
  if ( archive_entry_hardlink(a2) || archive_entry_symlink(a2) || (*(_WORD *)(a2 + 1032) & 0xF000) != 0x8000 )
  {
    *(_DWORD *)(a2 + 160) |= 0x40u;
    *(_DWORD *)(a2 + 16) = 0;
    *(_QWORD *)(a2 + 112) = 0;
  }
  if ( (*(_WORD *)(a2 + 1032) & 0xF000) == 0x4000 )
  {
    v7 = -1;
    v8 = archive_entry_pathname_w(a2);
    if ( v8 )
    {
      v9 = -1;
      do
        ++v9;
      while ( *(_WORD *)(v8 + 2 * v9) );
      if ( *(_WORD *)(v8 + 2 * v9 - 2) != 47 )
      {
        Block = 0;
        v19 = 0;
        v20 = 0;
        if ( !archive_string_ensure(&Block, 2 * v9 + 4) )
        {
LABEL_17:
          archive_set_error(a1, 12, "Can't allocate v7tar data");
          v19 = 0;
          v20 = 0;
          free(Block);
          return 4294967266LL;
        }
        v19 = 0;
        archive_wstrncat(&Block, v8);
        archive_wstrappend_wchar(&Block, 47);
        archive_mstring_copy_wcs(a2 + 488, Block);
        v19 = 0;
        v20 = 0;
        goto LABEL_30;
      }
    }
    v10 = (_BYTE *)archive_entry_pathname(a2);
    if ( v10 )
    {
      if ( *v10 )
      {
        v11 = -1;
        do
          ++v11;
        while ( v10[v11] );
        if ( v10[v11 - 1] != 47 )
        {
          Block = 0;
          v19 = 0;
          v20 = 0;
          if ( !archive_string_ensure(&Block, v11 + 2) )
            goto LABEL_17;
          do
            ++v7;
          while ( v10[v7] );
          if ( v10[v7 - 1] != 92 )
          {
            v19 = 0;
            archive_strncat(&Block, v10, v11);
          }
          LOBYTE(v12) = 47;
          archive_strappend_char(&Block, v12);
          archive_mstring_copy_mbs(a2 + 488, Block);
          v19 = 0;
          v20 = 0;
LABEL_30:
          free(Block);
        }
      }
    }
  }
  v13 = _la_win_entry_in_posix_pathseparator(a2);
  if ( !v13 )
  {
    archive_set_error(a1, 12, "Can't allocate v7tar data");
    return 4294967266LL;
  }
  if ( a2 == v13 )
    v13 = 0;
  else
    a2 = v13;
  v15 = format_header_v7tar(a1, v21, a2, v14, v5);
  if ( v15 >= -20 )
  {
    v16 = _archive_write_filter(*(_QWORD *)(a1 + 232), v21, 512);
    if ( v16 >= -20 )
    {
      if ( v16 < v15 )
        v15 = v16;
      v17 = *(_QWORD *)(a2 + 112);
      *(_QWORD *)v2 = v17;
      *(_QWORD *)(v2 + 8) = -(int)v17 & 0x1FF;
    }
    else
    {
      v15 = v16;
    }
  }
  archive_entry_free(v13);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18010ecd0  mov     [rsp-8+arg_10], rbx
0x18010ecd5  push    rbp
0x18010ecd6  push    rsi
0x18010ecd7  push    rdi
0x18010ecd8  push    r12
0x18010ecda  push    r13
0x18010ecdc  push    r14
0x18010ecde  push    r15
0x18010ece0  lea     rbp, [rsp-160h]
0x18010ece8  sub     rsp, 260h
0x18010ecef  mov     rax, cs:__security_cookie
0x18010ecf6  xor     rax, rsp
0x18010ecf9  mov     [rbp+190h+var_40], rax
0x18010ed00  mov     r12, [rcx+0F8h]
0x18010ed07  xor     esi, esi
0x18010ed09  mov     rbx, rdx
0x18010ed0c  mov     r14, rcx
0x18010ed0f  mov     r13, [r12+10h]
0x18010ed14  test    r13, r13
0x18010ed17  jnz     short loc_18010ED38
0x18010ed19  cmp     [r12+20h], esi
0x18010ed1e  jnz     short loc_18010ED33
0x18010ed20  call    archive_string_default_conversion_for_write
0x18010ed25  mov     [r12+18h], rax
0x18010ed2a  mov     dword ptr [r12+20h], 1
0x18010ed33  mov     r13, [r12+18h]
0x18010ed38  mov     rcx, rbx
0x18010ed3b  call    archive_entry_pathname
0x18010ed40  test    rax, rax
0x18010ed43  jnz     short loc_18010ED62
0x18010ed45  lea     r8, aCanTRecordEntr; "Can't record entry in tar file without "...
0x18010ed4c  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18010ed50  mov     rcx, r14
0x18010ed53  call    archive_set_error
0x18010ed58  mov     eax, 0FFFFFFE7h
0x18010ed5d  jmp     loc_18010F005
0x18010ed62  mov     rcx, rbx
0x18010ed65  call    archive_entry_hardlink
0x18010ed6a  mov     edi, 0F000h
0x18010ed6f  test    rax, rax
0x18010ed72  jnz     short loc_18010ED95
0x18010ed74  mov     rcx, rbx
0x18010ed77  call    archive_entry_symlink
0x18010ed7c  test    rax, rax
0x18010ed7f  jnz     short loc_18010ED95
0x18010ed81  movzx   eax, word ptr [rbx+408h]
0x18010ed88  mov     ecx, 8000h
0x18010ed8d  and     ax, di
0x18010ed90  cmp     ax, cx
0x18010ed93  jz      short loc_18010EDA3
0x18010ed95  or      dword ptr [rbx+0A0h], 40h
0x18010ed9c  mov     [rbx+10h], esi
0x18010ed9f  mov     [rbx+70h], rsi
0x18010eda3  movzx   eax, word ptr [rbx+408h]
0x18010edaa  mov     ecx, 4000h
0x18010edaf  and     ax, di
0x18010edb2  cmp     cx, ax
0x18010edb5  jnz     loc_18010EF6F
0x18010edbb  mov     rcx, rbx
0x18010edbe  call    archive_entry_pathname_w
0x18010edc3  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18010edc7  mov     r15, rax
0x18010edca  xor     eax, eax
0x18010edcc  lea     ecx, [rsi+30h]
0x18010edcf  test    r15, r15
0x18010edd2  jz      loc_18010EE9A
0x18010edd8  mov     rdi, rsi
0x18010eddb  inc     rdi
0x18010edde  cmp     [r15+rdi*2], ax
0x18010ede3  jnz     short loc_18010EDDB
0x18010ede5  cmp     [r15+rdi*2-2], cx
0x18010edeb  jz      loc_18010EE9A
0x18010edf1  xor     esi, esi
0x18010edf3  lea     rdx, ds:4[rdi*2]
0x18010edfb  lea     rcx, [rsp+290h+Block]
0x18010ee00  mov     [rsp+290h+Block], rsi
0x18010ee05  mov     [rsp+290h+var_258], rsi
0x18010ee0a  mov     [rsp+290h+var_250], rsi
0x18010ee0f  call    archive_string_ensure
0x18010ee14  test    rax, rax
0x18010ee17  jnz     short loc_18010EE4A
0x18010ee19  lea     r8, aCanTAllocateV7; "Can't allocate v7tar data"
0x18010ee20  mov     rcx, r14
0x18010ee23  lea     edx, [rsi+0Ch]
0x18010ee26  call    archive_set_error
0x18010ee2b  mov     [rsp+290h+var_258], rsi
0x18010ee30  mov     [rsp+290h+var_250], rsi
0x18010ee35  mov     rcx, [rsp+290h+Block]; Block
0x18010ee3a  call    cs:__imp_free
0x18010ee40  mov     eax, 0FFFFFFE2h
0x18010ee45  jmp     loc_18010F005
0x18010ee4a  cmp     word ptr [r15+rdi*2-2], 5Ch ; '\'
0x18010ee51  jnz     short loc_18010EE56
0x18010ee53  dec     rdi
0x18010ee56  mov     r8, rdi
0x18010ee59  mov     [rsp+290h+var_258], rsi
0x18010ee5e  mov     rdx, r15
0x18010ee61  lea     rcx, [rsp+290h+Block]
0x18010ee66  call    archive_wstrncat
0x18010ee6b  mov     edx, 2Fh ; '/'
0x18010ee70  lea     rcx, [rsp+290h+Block]
0x18010ee75  call    archive_wstrappend_wchar
0x18010ee7a  mov     rdx, [rsp+290h+Block]
0x18010ee7f  lea     rcx, [rbx+1E8h]
0x18010ee86  call    archive_mstring_copy_wcs
0x18010ee8b  mov     [rsp+290h+var_258], rsi
0x18010ee90  mov     [rsp+290h+var_250], rsi
0x18010ee95  jmp     loc_18010EF64
0x18010ee9a  mov     rcx, rbx
0x18010ee9d  call    archive_entry_pathname
0x18010eea2  mov     rdi, rax
0x18010eea5  xor     eax, eax
0x18010eea7  test    rdi, rdi
0x18010eeaa  jz      loc_18010EF6F
0x18010eeb0  cmp     [rdi], al
0x18010eeb2  jz      loc_18010EF6F
0x18010eeb8  mov     r15, rsi
0x18010eebb  inc     r15
0x18010eebe  cmp     [rdi+r15], al
0x18010eec2  jnz     short loc_18010EEBB
0x18010eec4  cmp     byte ptr [r15+rdi-1], 2Fh ; '/'
0x18010eeca  jz      loc_18010EF6F
0x18010eed0  lea     rdx, [r15+2]
0x18010eed4  mov     [rsp+290h+Block], rax
0x18010eed9  lea     rcx, [rsp+290h+Block]
0x18010eede  mov     [rsp+290h+var_258], rax
0x18010eee3  mov     [rsp+290h+var_250], rax
0x18010eee8  call    archive_string_ensure
0x18010eeed  xor     ecx, ecx
0x18010eeef  test    rax, rax
0x18010eef2  jnz     short loc_18010EF17
0x18010eef4  lea     edx, [rcx+0Ch]
0x18010eef7  mov     rcx, r14
0x18010eefa  lea     r8, aCanTAllocateV7; "Can't allocate v7tar data"
0x18010ef01  call    archive_set_error
0x18010ef06  xor     eax, eax
0x18010ef08  mov     [rsp+290h+var_258], rax
0x18010ef0d  mov     [rsp+290h+var_250], rax
0x18010ef12  jmp     loc_18010EE35
0x18010ef17  inc     rsi
0x18010ef1a  cmp     [rdi+rsi], cl
0x18010ef1d  jnz     short loc_18010EF17
0x18010ef1f  cmp     byte ptr [rsi+rdi-1], 5Ch ; '\'
0x18010ef24  jz      short loc_18010EF3B
0x18010ef26  mov     [rsp+290h+var_258], rcx
0x18010ef2b  mov     r8, r15
0x18010ef2e  lea     rcx, [rsp+290h+Block]
0x18010ef33  mov     rdx, rdi
0x18010ef36  call    archive_strncat
0x18010ef3b  mov     dl, 2Fh ; '/'
0x18010ef3d  lea     rcx, [rsp+290h+Block]
0x18010ef42  call    archive_strappend_char
0x18010ef47  mov     rdx, [rsp+290h+Block]
0x18010ef4c  lea     rcx, [rbx+1E8h]
0x18010ef53  call    archive_mstring_copy_mbs
0x18010ef58  xor     eax, eax
0x18010ef5a  mov     [rsp+290h+var_258], rax
0x18010ef5f  mov     [rsp+290h+var_250], rax
0x18010ef64  mov     rcx, [rsp+290h+Block]; Block
0x18010ef69  call    cs:__imp_free
0x18010ef6f  mov     rcx, rbx
0x18010ef72  call    __la_win_entry_in_posix_pathseparator
0x18010ef77  mov     rsi, rax
0x18010ef7a  xor     eax, eax
0x18010ef7c  test    rsi, rsi
0x18010ef7f  jnz     short loc_18010EF98
0x18010ef81  lea     r8, aCanTAllocateV7; "Can't allocate v7tar data"
0x18010ef88  mov     rcx, r14
0x18010ef8b  lea     edx, [rax+0Ch]
0x18010ef8e  call    archive_set_error
0x18010ef93  jmp     loc_18010EE40
0x18010ef98  cmp     rbx, rsi
0x18010ef9b  jz      short loc_18010EFA2
0x18010ef9d  mov     rbx, rsi
0x18010efa0  jmp     short loc_18010EFA5
0x18010efa2  mov     rsi, rax
0x18010efa5  mov     r8, rbx
0x18010efa8  mov     [rsp+290h+var_270], r13
0x18010efad  lea     rdx, [rsp+290h+var_240]
0x18010efb2  mov     rcx, r14
0x18010efb5  call    format_header_v7tar
0x18010efba  mov     edi, eax
0x18010efbc  cmp     eax, 0FFFFFFECh
0x18010efbf  jl      short loc_18010EFFB
0x18010efc1  mov     rcx, [r14+0E8h]
0x18010efc8  lea     rdx, [rsp+290h+var_240]
0x18010efcd  mov     r8d, 200h
0x18010efd3  call    __archive_write_filter
0x18010efd8  cmp     eax, 0FFFFFFECh
0x18010efdb  jge     short loc_18010EFE1
0x18010efdd  mov     edi, eax
0x18010efdf  jmp     short loc_18010EFFB
0x18010efe1  cmp     eax, edi
0x18010efe3  cmovl   edi, eax
0x18010efe6  mov     rax, [rbx+70h]
0x18010efea  mov     [r12], rax
0x18010efee  neg     rax
0x18010eff1  and     eax, 1FFh
0x18010eff6  mov     [r12+8], rax
0x18010effb  mov     rcx, rsi
0x18010effe  call    archive_entry_free
0x18010f003  mov     eax, edi
0x18010f005  mov     rcx, [rbp+190h+var_40]
0x18010f00c  xor     rcx, rsp; StackCookie
0x18010f00f  call    __security_check_cookie
0x18010f014  mov     rbx, [rsp+290h+arg_10]
0x18010f01c  add     rsp, 260h
0x18010f023  pop     r15
0x18010f025  pop     r14
0x18010f027  pop     r13
0x18010f029  pop     r12
0x18010f02b  pop     rdi
0x18010f02c  pop     rsi
0x18010f02d  pop     rbp
0x18010f02e  retn
```
