# archive_write_ustar_header

- ea: `0x18010e7b0`
- end: `0x18010eb05`
- name: `archive_write_ustar_header`
- size: `853`
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
- `0x18010df74`
- `0x18010e7b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18010e920`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18010ea35`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18010e920`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18010ea35`

## string_xrefs

- `0x18010e827`: `Can't record entry in tar file without pathname`

## pseudocode

```c
__int64 __fastcall archive_write_ustar_header(__int64 a1, __int64 a2)
{
  __int64 v2; // r12
  __int64 v5; // r13
  __int64 v7; // rsi
  __int64 v8; // rdi
  _BYTE *v9; // rdi
  __int64 v10; // rsi
  __int64 v11; // rdx
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rsi
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
  if ( !archive_entry_pathname_w(a2) )
  {
    archive_set_error(a1, 0xFFFFFFFFLL, "Can't record entry in tar file without pathname");
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
    v7 = archive_entry_pathname_w(a2);
    if ( v7 )
    {
      v8 = -1;
      do
        ++v8;
      while ( *(_WORD *)(v7 + 2 * v8) );
      if ( *(_WORD *)(v7 + 2 * v8 - 2) != 47 )
      {
        Block = 0;
        v19 = 0;
        v20 = 0;
        if ( !archive_string_ensure(&Block, 2 * v8 + 4) )
        {
LABEL_17:
          archive_set_error(a1, 12, "Can't allocate ustar data");
          v19 = 0;
          v20 = 0;
          free(Block);
          return 4294967266LL;
        }
        if ( *(_WORD *)(v7 + 2 * v8 - 2) == 92 )
          --v8;
        v19 = 0;
        archive_wstrncat(&Block, v7, v8);
        archive_wstrappend_wchar(&Block, 47);
        archive_mstring_copy_wcs(a2 + 488, Block);
        goto LABEL_33;
      }
    }
    v9 = (_BYTE *)archive_entry_pathname(a2);
    if ( v9 )
    {
      if ( *v9 )
      {
        v10 = -1;
        do
          ++v10;
        while ( v9[v10] );
        if ( v9[v10 - 1] != 47 )
        {
          Block = 0;
          v19 = 0;
          v20 = 0;
          if ( !archive_string_ensure(&Block, v10 + 2) )
            goto LABEL_17;
          v12 = -1;
          do
            ++v12;
          while ( v9[v12] );
          if ( v9[v12 - 1] != 92 )
          {
            v19 = 0;
            archive_strncat(&Block, v9, v10);
          }
          LOBYTE(v11) = 47;
          archive_strappend_char(&Block, v11);
          archive_mstring_copy_mbs(a2 + 488, Block);
LABEL_33:
          v19 = 0;
          v20 = 0;
          free(Block);
        }
      }
    }
  }
  v13 = _la_win_entry_in_posix_pathseparator(a2);
  v14 = v13;
  if ( !v13 )
  {
    archive_set_error(a1, 12, "Can't allocate ustar data");
    return 4294967266LL;
  }
  if ( a2 == v13 )
    v14 = 0;
  else
    a2 = v13;
  v15 = _archive_write_format_header_ustar(a1, v21, a2, -1, 1, v5);
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
  archive_entry_free(v14);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18010e7b0  mov     [rsp-8+arg_10], rbx
0x18010e7b5  mov     [rsp-8+arg_18], rsi
0x18010e7ba  push    rbp
0x18010e7bb  push    rdi
0x18010e7bc  push    r12
0x18010e7be  push    r13
0x18010e7c0  push    r14
0x18010e7c2  lea     rbp, [rsp-160h]
0x18010e7ca  sub     rsp, 260h
0x18010e7d1  mov     rax, cs:__security_cookie
0x18010e7d8  xor     rax, rsp
0x18010e7db  mov     [rbp+180h+var_30], rax
0x18010e7e2  mov     r12, [rcx+0F8h]
0x18010e7e9  xor     esi, esi
0x18010e7eb  mov     rbx, rdx
0x18010e7ee  mov     r14, rcx
0x18010e7f1  mov     r13, [r12+10h]
0x18010e7f6  test    r13, r13
0x18010e7f9  jnz     short loc_18010E81A
0x18010e7fb  cmp     [r12+20h], esi
0x18010e800  jnz     short loc_18010E815
0x18010e802  call    archive_string_default_conversion_for_write
0x18010e807  mov     [r12+18h], rax
0x18010e80c  mov     dword ptr [r12+20h], 1
0x18010e815  mov     r13, [r12+18h]
0x18010e81a  mov     rcx, rbx
0x18010e81d  call    archive_entry_pathname_w
0x18010e822  test    rax, rax
0x18010e825  jnz     short loc_18010E843
0x18010e827  lea     r8, aCanTRecordEntr; "Can't record entry in tar file without "...
0x18010e82e  or      edx, 0FFFFFFFFh
0x18010e831  mov     rcx, r14
0x18010e834  call    archive_set_error
0x18010e839  mov     eax, 0FFFFFFE7h
0x18010e83e  jmp     loc_18010EADA
0x18010e843  mov     rcx, rbx
0x18010e846  call    archive_entry_hardlink
0x18010e84b  mov     edi, 0F000h
0x18010e850  test    rax, rax
0x18010e853  jnz     short loc_18010E876
0x18010e855  mov     rcx, rbx
0x18010e858  call    archive_entry_symlink
0x18010e85d  test    rax, rax
0x18010e860  jnz     short loc_18010E876
0x18010e862  movzx   eax, word ptr [rbx+408h]
0x18010e869  mov     ecx, 8000h
0x18010e86e  and     ax, di
0x18010e871  cmp     ax, cx
0x18010e874  jz      short loc_18010E884
0x18010e876  or      dword ptr [rbx+0A0h], 40h
0x18010e87d  mov     [rbx+10h], esi
0x18010e880  mov     [rbx+70h], rsi
0x18010e884  movzx   eax, word ptr [rbx+408h]
0x18010e88b  mov     ecx, 4000h
0x18010e890  and     ax, di
0x18010e893  cmp     cx, ax
0x18010e896  jnz     loc_18010EA3B
0x18010e89c  mov     rcx, rbx
0x18010e89f  call    archive_entry_pathname_w
0x18010e8a4  mov     rsi, rax
0x18010e8a7  mov     ecx, 2Fh ; '/'
0x18010e8ac  xor     eax, eax
0x18010e8ae  test    rsi, rsi
0x18010e8b1  jz      loc_18010E979
0x18010e8b7  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18010e8bb  inc     rdi
0x18010e8be  cmp     [rsi+rdi*2], ax
0x18010e8c2  jnz     short loc_18010E8BB
0x18010e8c4  cmp     [rsi+rdi*2-2], cx
0x18010e8c9  jz      loc_18010E979
0x18010e8cf  lea     rdx, ds:4[rdi*2]
0x18010e8d7  mov     [rsp+280h+Block], rax
0x18010e8dc  lea     rcx, [rsp+280h+Block]
0x18010e8e1  mov     [rsp+280h+var_248], rax
0x18010e8e6  mov     [rsp+280h+var_240], rax
0x18010e8eb  call    archive_string_ensure
0x18010e8f0  test    rax, rax
0x18010e8f3  jnz     short loc_18010E930
0x18010e8f5  lea     r8, aCanTAllocateUs; "Can't allocate ustar data"
0x18010e8fc  mov     edx, 0Ch
0x18010e901  mov     rcx, r14
0x18010e904  call    archive_set_error
0x18010e909  mov     rcx, [rsp+280h+Block]; Block
0x18010e90e  mov     [rsp+280h+var_248], 0
0x18010e917  mov     [rsp+280h+var_240], 0
0x18010e920  call    cs:__imp_free
0x18010e926  mov     eax, 0FFFFFFE2h
0x18010e92b  jmp     loc_18010EADA
0x18010e930  cmp     word ptr [rsi+rdi*2-2], 5Ch ; '\'
0x18010e936  jnz     short loc_18010E93B
0x18010e938  dec     rdi
0x18010e93b  mov     r8, rdi
0x18010e93e  mov     [rsp+280h+var_248], 0
0x18010e947  mov     rdx, rsi
0x18010e94a  lea     rcx, [rsp+280h+Block]
0x18010e94f  call    archive_wstrncat
0x18010e954  mov     edx, 2Fh ; '/'
0x18010e959  lea     rcx, [rsp+280h+Block]
0x18010e95e  call    archive_wstrappend_wchar
0x18010e963  mov     rdx, [rsp+280h+Block]
0x18010e968  lea     rcx, [rbx+1E8h]
0x18010e96f  call    archive_mstring_copy_wcs
0x18010e974  jmp     loc_18010EA1E
0x18010e979  mov     rcx, rbx
0x18010e97c  call    archive_entry_pathname
0x18010e981  mov     rdi, rax
0x18010e984  xor     eax, eax
0x18010e986  test    rdi, rdi
0x18010e989  jz      loc_18010EA3B
0x18010e98f  cmp     [rdi], al
0x18010e991  jz      loc_18010EA3B
0x18010e997  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18010e99b  inc     rsi
0x18010e99e  cmp     [rdi+rsi], al
0x18010e9a1  jnz     short loc_18010E99B
0x18010e9a3  cmp     byte ptr [rsi+rdi-1], 2Fh ; '/'
0x18010e9a8  jz      loc_18010EA3B
0x18010e9ae  lea     rdx, [rsi+2]
0x18010e9b2  mov     [rsp+280h+Block], rax
0x18010e9b7  lea     rcx, [rsp+280h+Block]
0x18010e9bc  mov     [rsp+280h+var_248], rax
0x18010e9c1  mov     [rsp+280h+var_240], rax
0x18010e9c6  call    archive_string_ensure
0x18010e9cb  test    rax, rax
0x18010e9ce  jz      loc_18010E8F5
0x18010e9d4  or      rax, 0FFFFFFFFFFFFFFFFh
0x18010e9d8  inc     rax
0x18010e9db  cmp     byte ptr [rdi+rax], 0
0x18010e9df  jnz     short loc_18010E9D8
0x18010e9e1  cmp     byte ptr [rax+rdi-1], 5Ch ; '\'
0x18010e9e6  jz      short loc_18010EA01
0x18010e9e8  mov     r8, rsi
0x18010e9eb  mov     [rsp+280h+var_248], 0
0x18010e9f4  mov     rdx, rdi
0x18010e9f7  lea     rcx, [rsp+280h+Block]
0x18010e9fc  call    archive_strncat
0x18010ea01  mov     dl, 2Fh ; '/'
0x18010ea03  lea     rcx, [rsp+280h+Block]
0x18010ea08  call    archive_strappend_char
0x18010ea0d  mov     rdx, [rsp+280h+Block]
0x18010ea12  lea     rcx, [rbx+1E8h]
0x18010ea19  call    archive_mstring_copy_mbs
0x18010ea1e  mov     rcx, [rsp+280h+Block]; Block
0x18010ea23  mov     [rsp+280h+var_248], 0
0x18010ea2c  mov     [rsp+280h+var_240], 0
0x18010ea35  call    cs:__imp_free
0x18010ea3b  mov     rcx, rbx
0x18010ea3e  call    __la_win_entry_in_posix_pathseparator
0x18010ea43  mov     rsi, rax
0x18010ea46  test    rax, rax
0x18010ea49  jnz     short loc_18010EA62
0x18010ea4b  lea     r8, aCanTAllocateUs; "Can't allocate ustar data"
0x18010ea52  mov     rcx, r14
0x18010ea55  lea     edx, [rax+0Ch]
0x18010ea58  call    archive_set_error
0x18010ea5d  jmp     loc_18010E926
0x18010ea62  cmp     rbx, rax
0x18010ea65  jz      short loc_18010EA6C
0x18010ea67  mov     rbx, rax
0x18010ea6a  jmp     short loc_18010EA6E
0x18010ea6c  xor     esi, esi
0x18010ea6e  mov     [rsp+280h+var_258], r13
0x18010ea73  lea     rdx, [rsp+280h+var_230]
0x18010ea78  or      r9d, 0FFFFFFFFh
0x18010ea7c  mov     [rsp+280h+var_260], 1
0x18010ea84  mov     r8, rbx
0x18010ea87  mov     rcx, r14
0x18010ea8a  call    __archive_write_format_header_ustar
0x18010ea8f  mov     edi, eax
0x18010ea91  cmp     eax, 0FFFFFFECh
0x18010ea94  jl      short loc_18010EAD0
0x18010ea96  mov     rcx, [r14+0E8h]
0x18010ea9d  lea     rdx, [rsp+280h+var_230]
0x18010eaa2  mov     r8d, 200h
0x18010eaa8  call    __archive_write_filter
0x18010eaad  cmp     eax, 0FFFFFFECh
0x18010eab0  jge     short loc_18010EAB6
0x18010eab2  mov     edi, eax
0x18010eab4  jmp     short loc_18010EAD0
0x18010eab6  cmp     eax, edi
0x18010eab8  cmovl   edi, eax
0x18010eabb  mov     rax, [rbx+70h]
0x18010eabf  mov     [r12], rax
0x18010eac3  neg     rax
0x18010eac6  and     eax, 1FFh
0x18010eacb  mov     [r12+8], rax
0x18010ead0  mov     rcx, rsi
0x18010ead3  call    archive_entry_free
0x18010ead8  mov     eax, edi
0x18010eada  mov     rcx, [rbp+180h+var_30]
0x18010eae1  xor     rcx, rsp; StackCookie
0x18010eae4  call    __security_check_cookie
0x18010eae9  lea     r11, [rsp+280h+var_20]
0x18010eaf1  mov     rbx, [r11+40h]
0x18010eaf5  mov     rsi, [r11+48h]
0x18010eaf9  mov     rsp, r11
0x18010eafc  pop     r14
0x18010eafe  pop     r13
0x18010eb00  pop     r12
0x18010eb02  pop     rdi
0x18010eb03  pop     rbp
0x18010eb04  retn
```
