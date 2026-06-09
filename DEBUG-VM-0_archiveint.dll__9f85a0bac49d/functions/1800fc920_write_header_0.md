# write_header_0

- ea: `0x1800fc920`
- end: `0x1800fcd04`
- name: `write_header_0`
- size: `996`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `reparse_path`

## callers

- `0x1800fc630`
- `0x1800fc6b0`

## callees

- `0x180006c00`
- `0x18000e8d4`
- `0x180014fc0`
- `0x180015810`
- `0x1800b0b0c`
- `0x1800b1940`
- `0x1800b1b60`
- `0x1800b1f40`
- `0x1800b2070`
- `0x1800b2770`
- `0x1800ed038`
- `0x1800ed464`
- `0x1800ef2d4`
- `0x1800fc0f0`
- `0x1800fc134`
- `0x1800fc8a4`
- `0x1800fc920`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800fc9d3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800fcbb4`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800fc9d3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800fcbb4`

## string_xrefs

- `0x1800fc9de`: `Can't allocate memory for Pathname`
- `0x1800fcbbf`: `Can't allocate memory for Linkname`
- `0x1800fca15`: `Can't translate pathname '%s' to %s`
- `0x1800fcbe6`: `Can't translate linkname '%s' to %s`

## pseudocode

```c
__int64 __fastcall write_header_0(__int64 a1, __int64 a2)
{
  _QWORD *v2; // r13
  __int64 sconv; // r15
  __int64 v6; // rax
  __int64 v7; // r12
  unsigned int v9; // ebx
  const char *v10; // r8
  const char *v11; // rbx
  const char *v12; // rax
  unsigned int v13; // eax
  int v14; // eax
  int v15; // r13d
  unsigned int v16; // r11d
  unsigned int v17; // r11d
  unsigned int v18; // r11d
  unsigned int v19; // r11d
  __int64 v20; // rcx
  const char *v21; // rbx
  const char *v22; // rax
  _BYTE *v23; // r14
  __int64 v24; // r15
  __int64 v25; // rcx
  int v26; // eax
  int v27; // edx
  __int64 v28; // [rsp+30h] [rbp-59h] BYREF
  _BYTE *v29; // [rsp+38h] [rbp-51h] BYREF
  __int64 v30; // [rsp+40h] [rbp-49h] BYREF
  _QWORD *v31; // [rsp+48h] [rbp-41h]
  _BYTE v32[6]; // [rsp+50h] [rbp-39h] BYREF
  _BYTE v33[6]; // [rsp+56h] [rbp-33h] BYREF
  _BYTE v34[6]; // [rsp+5Ch] [rbp-2Dh] BYREF
  _BYTE v35[6]; // [rsp+62h] [rbp-27h] BYREF
  _BYTE v36[6]; // [rsp+68h] [rbp-21h] BYREF
  _BYTE v37[6]; // [rsp+6Eh] [rbp-1Bh] BYREF
  _BYTE v38[6]; // [rsp+74h] [rbp-15h] BYREF
  _BYTE v39[6]; // [rsp+7Ah] [rbp-Fh] BYREF
  _BYTE v40[11]; // [rsp+80h] [rbp-9h] BYREF
  _BYTE v41[6]; // [rsp+8Bh] [rbp+2h] BYREF
  _BYTE v42[15]; // [rsp+91h] [rbp+8h] BYREF

  v2 = *(_QWORD **)(a1 + 248);
  v29 = 0;
  v30 = 0;
  v28 = 0;
  v31 = v2;
  sconv = get_sconv();
  v6 = _la_win_entry_in_posix_pathseparator(a2);
  v7 = v6;
  if ( !v6 )
  {
    archive_set_error(a1, 12, "Can't allocate ustar data");
    return 4294967266LL;
  }
  v9 = 0;
  if ( a2 == v6 )
    v7 = 0;
  else
    a2 = v6;
  if ( (unsigned int)archive_mstring_get_mbs_l(
                       *(_QWORD *)a2,
                       (int)a2 + 488,
                       (unsigned int)&v30,
                       (unsigned int)&v28,
                       sconv) )
  {
    if ( *(_DWORD *)_o__errno() == 12 )
    {
      v10 = "Can't allocate memory for Pathname";
LABEL_9:
      archive_set_error(a1, 12, v10);
      goto LABEL_10;
    }
    v11 = (const char *)archive_string_conversion_charset_name(sconv);
    v12 = (const char *)archive_entry_pathname(a2);
    archive_set_error(a1, 42, "Can't translate pathname '%s' to %s", v12, v11);
    v9 = -20;
  }
  memset_0(v32, 0, 0x4Cu);
  format_octal_0(29127, v32, 6);
  v13 = archive_entry_dev(a2);
  format_octal_0(v13, v33, 6);
  v14 = synthesize_ino_value(v2, a2);
  if ( v14 < 0 )
  {
    v10 = "No memory for ino translation table";
    goto LABEL_9;
  }
  if ( v14 > 0x3FFFFLL )
  {
    archive_set_error(a1, 34, "Too many files for this cpio format");
    goto LABEL_10;
  }
  v15 = v28 + 1;
  format_octal_0(v14 & 0x3FFFFLL, v34, 6);
  format_octal_0(*(unsigned __int16 *)(a2 + 1032), v35, v16);
  format_octal_0(*(_QWORD *)(a2 + 120), v36, v17);
  format_octal_0(*(_QWORD *)(a2 + 88), v37, v18);
  format_octal_0(*(unsigned int *)(a2 + 104), v38, v19);
  if ( (((*(_WORD *)(a2 + 1032) & 0xF000) - 0x2000) & 0xBFFF) != 0 )
    v20 = 0;
  else
    v20 = (unsigned int)archive_entry_rdev(a2);
  format_octal_0(v20, v39, 6);
  format_octal_0(*(_QWORD *)(a2 + 56), v40, 11);
  format_octal_0(v15, v41, 6);
  if ( (*(_WORD *)(a2 + 1032) & 0xF000) != 0x8000 )
  {
    *(_DWORD *)(a2 + 160) |= 0x40u;
    *(_DWORD *)(a2 + 16) = 0;
    *(_QWORD *)(a2 + 112) = 0;
  }
  if ( (unsigned int)archive_entry_symlink_l(a2, &v29, &v28, sconv) )
  {
    if ( *(_DWORD *)_o__errno() == 12 )
    {
      v10 = "Can't allocate memory for Linkname";
      goto LABEL_9;
    }
    v21 = (const char *)archive_string_conversion_charset_name(sconv);
    v22 = (const char *)archive_entry_symlink(a2);
    archive_set_error(a1, 42, "Can't translate linkname '%s' to %s", v22, v21);
    v9 = -20;
  }
  v23 = v29;
  v24 = -1;
  if ( v28 && v29 && *v29 )
  {
    v25 = -1;
    do
      ++v25;
    while ( v29[v25] );
  }
  else
  {
    v25 = *(_QWORD *)(a2 + 112);
  }
  if ( (unsigned int)format_octal_0(v25, v42, 11) )
  {
    archive_set_error(a1, 34, "File is too large for cpio format.");
    v9 = -25;
    goto LABEL_42;
  }
  if ( !(unsigned int)_archive_write_filter(*(_QWORD *)(a1 + 232), v32, 76)
    && !(unsigned int)_archive_write_filter(*(_QWORD *)(a1 + 232), v30, v15) )
  {
    *v31 = *(_QWORD *)(a2 + 112);
    if ( v23 && *v23 )
    {
      do
        ++v24;
      while ( v23[v24] );
      v26 = _archive_write_filter(*(_QWORD *)(a1 + 232), v23, v24);
      v27 = v9;
      if ( v26 )
        v27 = -30;
      v9 = v27;
    }
    goto LABEL_42;
  }
LABEL_10:
  v9 = -30;
LABEL_42:
  archive_entry_free(v7);
  return v9;
}

```

## disassembly

```asm
0x1800fc920  mov     [rsp-8+arg_10], rbx
0x1800fc925  push    rbp
0x1800fc926  push    rsi
0x1800fc927  push    rdi
0x1800fc928  push    r12
0x1800fc92a  push    r13
0x1800fc92c  push    r14
0x1800fc92e  push    r15
0x1800fc930  lea     rbp, [rsp-27h]
0x1800fc935  sub     rsp, 0B0h
0x1800fc93c  mov     rax, cs:__security_cookie
0x1800fc943  xor     rax, rsp
0x1800fc946  mov     [rbp+57h+var_40], rax
0x1800fc94a  mov     r13, [rcx+0F8h]
0x1800fc951  xor     r14d, r14d
0x1800fc954  mov     [rbp+57h+var_A8], r14
0x1800fc958  mov     rdi, rdx
0x1800fc95b  mov     [rbp+57h+var_A0], r14
0x1800fc95f  mov     rsi, rcx
0x1800fc962  mov     [rbp+57h+var_B0], r14
0x1800fc966  mov     [rbp+57h+var_98], r13
0x1800fc96a  call    get_sconv
0x1800fc96f  mov     rcx, rdi
0x1800fc972  mov     r15, rax
0x1800fc975  call    __la_win_entry_in_posix_pathseparator
0x1800fc97a  mov     r12, rax
0x1800fc97d  test    rax, rax
0x1800fc980  jnz     short loc_1800FC99D
0x1800fc982  lea     r8, aCanTAllocateUs; "Can't allocate ustar data"
0x1800fc989  mov     rcx, rsi
0x1800fc98c  lea     edx, [rax+0Ch]
0x1800fc98f  call    archive_set_error
0x1800fc994  lea     eax, [r14-1Eh]
0x1800fc998  jmp     loc_1800FCCDD
0x1800fc99d  mov     ebx, r14d
0x1800fc9a0  cmp     rdi, rax
0x1800fc9a3  jz      short loc_1800FC9AA
0x1800fc9a5  mov     rdi, rax
0x1800fc9a8  jmp     short loc_1800FC9AD
0x1800fc9aa  mov     r12, r14
0x1800fc9ad  mov     rcx, [rdi]
0x1800fc9b0  lea     rdx, [rdi+1E8h]
0x1800fc9b7  lea     r9, [rbp+57h+var_B0]
0x1800fc9bb  mov     [rsp+0E0h+var_C0], r15
0x1800fc9c0  lea     r8, [rbp+57h+var_A0]
0x1800fc9c4  call    archive_mstring_get_mbs_l
0x1800fc9c9  mov     r14d, 0Ch
0x1800fc9cf  test    eax, eax
0x1800fc9d1  jz      short loc_1800FCA2E
0x1800fc9d3  call    cs:__imp__o__errno
0x1800fc9d9  cmp     [rax], r14d
0x1800fc9dc  jnz     short loc_1800FC9FA
0x1800fc9de  lea     r8, aCanTAllocateMe_24; "Can't allocate memory for Pathname"
0x1800fc9e5  mov     edx, r14d
0x1800fc9e8  mov     rcx, rsi
0x1800fc9eb  call    archive_set_error
0x1800fc9f0  mov     ebx, 0FFFFFFE2h
0x1800fc9f5  jmp     loc_1800FCCD3
0x1800fc9fa  mov     rcx, r15
0x1800fc9fd  call    archive_string_conversion_charset_name
0x1800fca02  mov     rcx, rdi
0x1800fca05  mov     rbx, rax
0x1800fca08  call    archive_entry_pathname
0x1800fca0d  mov     r9, rax
0x1800fca10  mov     [rsp+0E0h+var_C0], rbx
0x1800fca15  lea     r8, aCanTTranslateP; "Can't translate pathname '%s' to %s"
0x1800fca1c  mov     edx, 2Ah ; '*'
0x1800fca21  mov     rcx, rsi
0x1800fca24  call    archive_set_error
0x1800fca29  mov     ebx, 0FFFFFFECh
0x1800fca2e  xor     edx, edx; Val
0x1800fca30  lea     rcx, [rbp+57h+var_90]; void *
0x1800fca34  lea     r8d, [rdx+4Ch]; Size
0x1800fca38  call    memset_0
0x1800fca3d  mov     r8d, 6
0x1800fca43  lea     rdx, [rbp+57h+var_90]
0x1800fca47  mov     ecx, 71C7h
0x1800fca4c  call    format_octal_0
0x1800fca51  mov     rcx, rdi
0x1800fca54  call    archive_entry_dev
0x1800fca59  mov     ecx, eax
0x1800fca5b  lea     rdx, [rbp+57h+var_8A]
0x1800fca5f  mov     r8d, 6
0x1800fca65  call    format_octal_0
0x1800fca6a  mov     rdx, rdi
0x1800fca6d  mov     rcx, r13
0x1800fca70  call    synthesize_ino_value
0x1800fca75  movsxd  rcx, eax
0x1800fca78  test    eax, eax
0x1800fca7a  jns     short loc_1800FCA88
0x1800fca7c  lea     r8, aNoMemoryForIno; "No memory for ino translation table"
0x1800fca83  jmp     loc_1800FC9E5
0x1800fca88  mov     edx, 3FFFFh
0x1800fca8d  cmp     rcx, rdx
0x1800fca90  jle     short loc_1800FCAA3
0x1800fca92  lea     r8, aTooManyFilesFo; "Too many files for this cpio format"
0x1800fca99  mov     edx, 22h ; '"'
0x1800fca9e  jmp     loc_1800FC9E8
0x1800fcaa3  mov     r13d, dword ptr [rbp+57h+var_B0]
0x1800fcaa7  and     rcx, rdx
0x1800fcaaa  mov     r11d, 6
0x1800fcab0  lea     rdx, [rbp+57h+var_84]
0x1800fcab4  mov     r8d, r11d
0x1800fcab7  inc     r13d
0x1800fcaba  call    format_octal_0
0x1800fcabf  movzx   ecx, word ptr [rdi+408h]
0x1800fcac6  lea     rdx, [rbp+57h+var_7E]
0x1800fcaca  mov     r8d, r11d
0x1800fcacd  call    format_octal_0
0x1800fcad2  mov     rcx, [rdi+78h]
0x1800fcad6  lea     rdx, [rbp+57h+var_78]
0x1800fcada  mov     r8d, r11d
0x1800fcadd  call    format_octal_0
0x1800fcae2  mov     rcx, [rdi+58h]
0x1800fcae6  lea     rdx, [rbp+57h+var_72]
0x1800fcaea  mov     r8d, r11d
0x1800fcaed  call    format_octal_0
0x1800fcaf2  mov     ecx, [rdi+68h]
0x1800fcaf5  lea     rdx, [rbp+57h+var_6C]
0x1800fcaf9  mov     r8d, r11d
0x1800fcafc  call    format_octal_0
0x1800fcb01  movzx   r11d, word ptr [rdi+408h]
0x1800fcb09  mov     eax, 0F000h
0x1800fcb0e  and     r11w, ax
0x1800fcb12  mov     eax, 2000h
0x1800fcb17  sub     r11w, ax
0x1800fcb1b  mov     eax, 0BFFFh
0x1800fcb20  test    ax, r11w
0x1800fcb24  jz      short loc_1800FCB2A
0x1800fcb26  xor     ecx, ecx
0x1800fcb28  jmp     short loc_1800FCB34
0x1800fcb2a  mov     rcx, rdi
0x1800fcb2d  call    archive_entry_rdev
0x1800fcb32  mov     ecx, eax
0x1800fcb34  mov     r8d, 6
0x1800fcb3a  lea     rdx, [rbp+57h+var_66]
0x1800fcb3e  call    format_octal_0
0x1800fcb43  mov     rcx, [rdi+38h]
0x1800fcb47  lea     rdx, [rbp+57h+var_60]
0x1800fcb4b  mov     r8d, 0Bh
0x1800fcb51  call    format_octal_0
0x1800fcb56  movsxd  r13, r13d
0x1800fcb59  lea     rdx, [rbp+57h+var_55]
0x1800fcb5d  mov     rcx, r13
0x1800fcb60  mov     r8d, 6
0x1800fcb66  call    format_octal_0
0x1800fcb6b  movzx   r11d, word ptr [rdi+408h]
0x1800fcb73  mov     eax, 0F000h
0x1800fcb78  and     r11w, ax
0x1800fcb7c  mov     eax, 8000h
0x1800fcb81  cmp     r11w, ax
0x1800fcb85  jz      short loc_1800FCB9D
0x1800fcb87  or      dword ptr [rdi+0A0h], 40h
0x1800fcb8e  mov     dword ptr [rdi+10h], 0
0x1800fcb95  mov     qword ptr [rdi+70h], 0
0x1800fcb9d  mov     r9, r15
0x1800fcba0  lea     r8, [rbp+57h+var_B0]
0x1800fcba4  lea     rdx, [rbp+57h+var_A8]
0x1800fcba8  mov     rcx, rdi
0x1800fcbab  call    _archive_entry_symlink_l
0x1800fcbb0  test    eax, eax
0x1800fcbb2  jz      short loc_1800FCBFF
0x1800fcbb4  call    cs:__imp__o__errno
0x1800fcbba  cmp     [rax], r14d
0x1800fcbbd  jnz     short loc_1800FCBCB
0x1800fcbbf  lea     r8, aCanTAllocateMe_15; "Can't allocate memory for Linkname"
0x1800fcbc6  jmp     loc_1800FC9E5
0x1800fcbcb  mov     rcx, r15
0x1800fcbce  call    archive_string_conversion_charset_name
0x1800fcbd3  mov     rcx, rdi
0x1800fcbd6  mov     rbx, rax
0x1800fcbd9  call    archive_entry_symlink
0x1800fcbde  mov     r9, rax
0x1800fcbe1  mov     [rsp+0E0h+var_C0], rbx
0x1800fcbe6  lea     r8, aCanTTranslateL; "Can't translate linkname '%s' to %s"
0x1800fcbed  mov     edx, 2Ah ; '*'
0x1800fcbf2  mov     rcx, rsi
0x1800fcbf5  call    archive_set_error
0x1800fcbfa  mov     ebx, 0FFFFFFECh
0x1800fcbff  mov     r14, [rbp+57h+var_A8]
0x1800fcc03  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800fcc07  cmp     [rbp+57h+var_B0], 0
0x1800fcc0c  jbe     short loc_1800FCC28
0x1800fcc0e  test    r14, r14
0x1800fcc11  jz      short loc_1800FCC28
0x1800fcc13  cmp     byte ptr [r14], 0
0x1800fcc17  jz      short loc_1800FCC28
0x1800fcc19  mov     rcx, r15
0x1800fcc1c  inc     rcx
0x1800fcc1f  cmp     byte ptr [r14+rcx], 0
0x1800fcc24  jnz     short loc_1800FCC1C
0x1800fcc26  jmp     short loc_1800FCC2C
0x1800fcc28  mov     rcx, [rdi+70h]
0x1800fcc2c  mov     r8d, 0Bh
0x1800fcc32  lea     rdx, [rbp+57h+var_4F]
0x1800fcc36  call    format_octal_0
0x1800fcc3b  test    eax, eax
0x1800fcc3d  jz      short loc_1800FCC5A
0x1800fcc3f  lea     r8, aFileIsTooLarge_0; "File is too large for cpio format."
0x1800fcc46  mov     edx, 22h ; '"'
0x1800fcc4b  mov     rcx, rsi
0x1800fcc4e  call    archive_set_error
0x1800fcc53  mov     ebx, 0FFFFFFE7h
0x1800fcc58  jmp     short loc_1800FCCD3
0x1800fcc5a  mov     rcx, [rsi+0E8h]
0x1800fcc61  lea     rdx, [rbp+57h+var_90]
0x1800fcc65  mov     r8d, 4Ch ; 'L'
0x1800fcc6b  call    __archive_write_filter
0x1800fcc70  test    eax, eax
0x1800fcc72  jnz     loc_1800FC9F0
0x1800fcc78  mov     rdx, [rbp+57h+var_A0]
0x1800fcc7c  mov     r8, r13
0x1800fcc7f  mov     rcx, [rsi+0E8h]
0x1800fcc86  call    __archive_write_filter
0x1800fcc8b  test    eax, eax
0x1800fcc8d  jnz     loc_1800FC9F0
0x1800fcc93  mov     rcx, [rbp+57h+var_98]
0x1800fcc97  mov     rax, [rdi+70h]
0x1800fcc9b  mov     [rcx], rax
0x1800fcc9e  test    r14, r14
0x1800fcca1  jz      short loc_1800FCCD3
0x1800fcca3  cmp     byte ptr [r14], 0
0x1800fcca7  jz      short loc_1800FCCD3
0x1800fcca9  inc     r15
0x1800fccac  cmp     byte ptr [r14+r15], 0
0x1800fccb1  jnz     short loc_1800FCCA9
0x1800fccb3  mov     rcx, [rsi+0E8h]
0x1800fccba  mov     r8, r15
0x1800fccbd  mov     rdx, r14
0x1800fccc0  call    __archive_write_filter
0x1800fccc5  mov     edx, ebx
0x1800fccc7  test    eax, eax
0x1800fccc9  mov     ebx, 0FFFFFFE2h
0x1800fccce  cmovnz  edx, ebx
0x1800fccd1  mov     ebx, edx
0x1800fccd3  mov     rcx, r12
0x1800fccd6  call    archive_entry_free
0x1800fccdb  mov     eax, ebx
0x1800fccdd  mov     rcx, [rbp+57h+var_40]
0x1800fcce1  xor     rcx, rsp; StackCookie
0x1800fcce4  call    __security_check_cookie
0x1800fcce9  mov     rbx, [rsp+0E0h+arg_10]
0x1800fccf1  add     rsp, 0B0h
0x1800fccf8  pop     r15
0x1800fccfa  pop     r14
0x1800fccfc  pop     r13
0x1800fccfe  pop     r12
0x1800fcd00  pop     rdi
0x1800fcd01  pop     rsi
0x1800fcd02  pop     rbp
0x1800fcd03  retn
```
