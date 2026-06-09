# make_file_entry

- ea: `0x180111734`
- end: `0x180111f4c`
- name: `make_file_entry`
- size: `2072`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `reparse_path, registry_config`

## callers

- `0x180111f54`

## callees

- `0x180006c00`
- `0x18000a2d0`
- `0x1800b1940`
- `0x1800b1a60`
- `0x1800b1bc0`
- `0x1800b20d0`
- `0x1800b2100`
- `0x1800b28d0`
- `0x1800b39f0`
- `0x1800ed038`
- `0x1800ee548`
- `0x180111620`
- `0x180111734`
- `0x18011334c`
- `0x1801133fc`
- `0x180113490`
- `0x180113564`
- `0x18011366c`
- `0x180113770`
- `0x1801137d4`
- `0x18011392c`
- `0x1801139a8`
- `0x180113a38`
- `0x180113bc0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180111bb2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180111c75`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180111bb2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180111c75`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1801119b4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1801119b4`

## string_xrefs

- `0x180111918`: `hardlink`
- `0x180111967`: `directory`
- `0x180111906`: `symlink`
- `0x180111872`: `xml_writer_start_element() failed: %d`
- `0x180111e97`: `xml_writer_start_element() failed: %d`
- `0x1801118be`: `xml_writer_write_attribute() failed: %d`
- `0x1801118fa`: `xml_writer_end_element() failed: %d`
- `0x1801118e1`: `xml_writer_write_base64() failed: %d`
- `0x180111ea3`: `xml_writer_write_attributef() failed: %d`

## pseudocode

```c
__int64 __fastcall make_file_entry(__int64 a1, __int64 a2, __int64 a3)
{
  char *v3; // r9
  __int64 v4; // r13
  char v6; // al
  char *i; // rcx
  __int64 v10; // rax
  const char *v11; // r12
  __int16 v12; // cx
  const char *v13; // rbx
  int started; // eax
  const char *v15; // r8
  __int64 result; // rax
  __int64 v17; // r8
  __int64 v18; // r8
  int v19; // eax
  int v20; // ebx
  __int16 v21; // r15
  __int64 v22; // rdx
  int v23; // eax
  int v24; // eax
  __int64 v25; // r8
  int v26; // eax
  unsigned int v27; // r15d
  const char *v28; // rax
  const char *v29; // rax
  __int64 v30; // r9
  __int64 v31; // r9
  __int64 v32; // r9
  __int64 v33; // rax
  __int64 v34; // rbx
  __int64 j; // rbx
  __int64 v36; // rcx
  int v37; // eax
  int v38; // eax
  __int64 v39; // rcx
  void *Block[2]; // [rsp+30h] [rbp-20h] BYREF
  __int64 v41; // [rsp+40h] [rbp-10h]
  __int64 v42; // [rsp+90h] [rbp+40h] BYREF
  __int64 v43; // [rsp+A0h] [rbp+50h] BYREF
  char v44; // [rsp+A8h] [rbp+58h] BYREF

  v3 = *(char **)(a3 + 136);
  v4 = *(_QWORD *)(a1 + 248);
  v41 = 0;
  v43 = 0;
  *(_OWORD *)Block = 0;
  v6 = *v3;
  v42 = 0;
  for ( i = v3; ; v6 = *i )
  {
    if ( !v6 )
    {
      if ( (int)xmlwrite_string(a1, a2, "name", v3) < 0 )
        return 4294967266LL;
      goto LABEL_9;
    }
    ++i;
    if ( (unsigned int)v6 >= 0x80 )
      break;
LABEL_6:
    ;
  }
  if ( (v6 & 0xFC) == 0xC0 && (*i & 0xC0) == 0x80 )
  {
    ++i;
    goto LABEL_6;
  }
  started = xml_writer_start_element(a2, "name");
  if ( started < 0 )
    goto LABEL_18;
  started = xml_writer_write_attribute(a2, "enctype", "base64");
  if ( started < 0 )
  {
    v15 = "xml_writer_write_attribute() failed: %d";
    goto LABEL_19;
  }
  started = xml_writer_write_base64(a2, *(_QWORD *)(a3 + 136), v17, *(int *)(a3 + 144));
  if ( started < 0 )
  {
    v15 = "xml_writer_write_base64() failed: %d";
    goto LABEL_19;
  }
  started = xml_writer_end_element(a2);
  if ( started < 0 )
  {
LABEL_27:
    v15 = "xml_writer_end_element() failed: %d";
    goto LABEL_19;
  }
LABEL_9:
  v10 = *(_QWORD *)(a3 + 32);
  Block[0] = 0;
  Block[1] = 0;
  v41 = 0;
  v11 = 0;
  v12 = *(_WORD *)(v10 + 1032) & 0xF000;
  switch ( v12 )
  {
    case 4096:
      v13 = "fifo";
      break;
    case 8192:
      v13 = "character special";
      break;
    case 16384:
      v13 = "directory";
      break;
    case 24576:
      v13 = "block special";
      break;
    case -32768:
      goto LABEL_29;
    case -24576:
      v13 = "symlink";
      break;
    case -16384:
      v13 = "socket";
      break;
    default:
LABEL_29:
      v18 = *(_QWORD *)(a3 + 80);
      if ( v18 )
      {
        v13 = "hardlink";
        v11 = "link";
        if ( v18 == a3 )
          archive_strncat(Block, "original", 8);
        else
          archive_string_sprintf(Block, "%d", *(_DWORD *)(v18 + 24));
      }
      else
      {
        v13 = "file";
      }
      break;
  }
  v19 = xmlwrite_string_attr(a1, a2, (unsigned int)"type", (_DWORD)v13, (__int64)v11, (__int64)Block[0]);
  Block[1] = 0;
  v20 = v19;
  v41 = 0;
  free(Block[0]);
  Block[0] = 0;
  if ( v20 < 0 )
    return 4294967266LL;
  if ( (*(_BYTE *)(a3 + 360) & 1) != 0 )
    return 0;
  v21 = *(_WORD *)(*(_QWORD *)(a3 + 32) + 1032LL) & 0xF000;
  if ( ((v21 - 0x2000) & 0xBFFF) != 0 )
  {
    if ( v21 != -24576
      || (int)xmlwrite_string_attr(
                a1,
                a2,
                (unsigned int)"link",
                *(_QWORD *)(a3 + 160),
                (__int64)"type",
                (__int64)"broken") >= 0 )
    {
      goto LABEL_49;
    }
    return 4294967266LL;
  }
  started = xml_writer_start_element(a2, "device");
  if ( started < 0 )
  {
LABEL_18:
    v15 = "xml_writer_start_element() failed: %d";
LABEL_19:
    archive_set_error(a1, 0xFFFFFFFFLL, v15, (unsigned int)started);
    return 4294967266LL;
  }
  v23 = archive_entry_rdevmajor(*(_QWORD *)(a3 + 32), v22);
  if ( (int)xmlwrite_fstring(a1, a2, "major", "%d", v23) < 0 )
    return 4294967266LL;
  v24 = archive_entry_rdevminor(*(_QWORD *)(a3 + 32));
  if ( (int)xmlwrite_fstring(a1, a2, "minor", "%d", v24) < 0 )
    return 4294967266LL;
  started = xml_writer_end_element(a2);
  if ( started < 0 )
    goto LABEL_27;
LABEL_49:
  if ( (int)xmlwrite_fstring(a1, a2, "inode", "%jd", *(_QWORD *)(*(_QWORD *)(a3 + 32) + 96LL)) < 0 )
    return 4294967266LL;
  if ( (unsigned int)archive_entry_dev(*(_QWORD *)(a3 + 32)) )
  {
    v26 = archive_entry_dev(*(_QWORD *)(a3 + 32));
    if ( (int)xmlwrite_fstring(a1, a2, "deviceno", "%d", v26) < 0 )
      return 4294967266LL;
  }
  if ( (int)xmlwrite_mode(a1, a2, v25, *(unsigned __int16 *)(*(_QWORD *)(a3 + 32) + 1032LL)) < 0
    || (int)xmlwrite_fstring(a1, a2, "uid", "%jd", *(_QWORD *)(*(_QWORD *)(a3 + 32) + 120LL)) < 0 )
  {
    return 4294967266LL;
  }
  v27 = 0;
  if ( (unsigned int)archive_mstring_get_mbs_l(
                       **(_QWORD **)(a3 + 32),
                       (unsigned int)*(_QWORD *)(a3 + 32) + 592,
                       (unsigned int)&v43,
                       (unsigned int)&v42,
                       *(_QWORD *)(v4 + 344)) )
  {
    if ( *(_DWORD *)_o__errno() == 12 )
    {
      archive_set_error(a1, 12, "Can't allocate memory for Uname");
      return 4294967266LL;
    }
    v28 = (const char *)archive_entry_uname(*(_QWORD *)(a3 + 32));
    archive_set_error(a1, 42, "Can't translate uname '%s' to UTF-8", v28);
    v27 = -20;
  }
  if ( v42 && (int)xmlwrite_string(a1, a2, "user", v43) < 0
    || (int)xmlwrite_fstring(a1, a2, "gid", "%jd", *(_QWORD *)(*(_QWORD *)(a3 + 32) + 88LL)) < 0 )
  {
    return 4294967266LL;
  }
  if ( (unsigned int)archive_mstring_get_mbs_l(
                       **(_QWORD **)(a3 + 32),
                       (unsigned int)*(_QWORD *)(a3 + 32) + 280,
                       (unsigned int)&v43,
                       (unsigned int)&v42,
                       *(_QWORD *)(v4 + 344)) )
  {
    if ( *(_DWORD *)_o__errno() == 12 )
    {
      archive_set_error(a1, 12, "Can't allocate memory for Gname");
      return 4294967266LL;
    }
    v29 = (const char *)archive_entry_gname(*(_QWORD *)(a3 + 32));
    archive_set_error(a1, 42, "Can't translate gname '%s' to UTF-8", v29);
    v27 = -20;
  }
  if ( v42 && (int)xmlwrite_string(a1, a2, "group", v43) < 0 )
    return 4294967266LL;
  v30 = *(_QWORD *)(a3 + 32);
  if ( (*(_BYTE *)(v30 + 160) & 8) != 0
    && (int)xmlwrite_time(a1, a2, (unsigned int)"ctime", *(_QWORD *)(v30 + 40), 1) < 0 )
  {
    return 4294967266LL;
  }
  v31 = *(_QWORD *)(a3 + 32);
  if ( (*(_BYTE *)(v31 + 160) & 0x10) != 0
    && (int)xmlwrite_time(a1, a2, (unsigned int)"mtime", *(_QWORD *)(v31 + 56), 1) < 0 )
  {
    return 4294967266LL;
  }
  v32 = *(_QWORD *)(a3 + 32);
  if ( (*(_BYTE *)(v32 + 160) & 4) != 0
    && (int)xmlwrite_time(a1, a2, (unsigned int)"atime", *(_QWORD *)(v32 + 24), 1) < 0 )
  {
    return 4294967266LL;
  }
  v33 = archive_entry_fflags_text(*(_QWORD *)(a3 + 32));
  v34 = v33;
  if ( !v33
    || (result = make_fflags_entry(a1, a2, "flags", v33), (int)result >= 0)
    && (result = make_fflags_entry(a1, a2, "ext2", v34), (int)result >= 0) )
  {
    *(_QWORD *)(*(_QWORD *)(a3 + 32) + 1096LL) = *(_QWORD *)(*(_QWORD *)(a3 + 32) + 1088LL);
    for ( j = *(_QWORD *)(a3 + 192); j; j = *(_QWORD *)(j + 8) )
    {
      v36 = *(_QWORD *)(a3 + 32);
      v42 = 0;
      archive_entry_xattr_next(v36, &v42, &v44, &v43);
      started = xml_writer_start_element(a2, "ea");
      if ( started < 0 )
        goto LABEL_18;
      v37 = xml_writer_write_attributef(a2, "id", "%d", *(_DWORD *)j);
      if ( v37 < 0 )
      {
        archive_set_error(a1, 0xFFFFFFFFLL, "xml_writer_write_attributef() failed: %d", (unsigned int)v37);
        return 4294967266LL;
      }
      if ( (int)xmlwrite_heap(a1, a2, j) < 0 || (int)xmlwrite_string(a1, a2, "name", v42) < 0 )
        return 4294967266LL;
      started = xml_writer_end_element(a2);
      if ( started < 0 )
        goto LABEL_27;
    }
    if ( *(_QWORD *)(a3 + 232) )
    {
      v38 = xml_writer_start_element(a2, "data");
      v39 = a1;
      if ( v38 < 0 )
      {
LABEL_87:
        archive_set_error(v39, 0xFFFFFFFFLL, "xml_writer_start_element() failed: %d", (unsigned int)v38);
        return 4294967266LL;
      }
      if ( (int)xmlwrite_heap(a1, a2, a3 + 208) < 0 )
        return 4294967266LL;
      started = xml_writer_end_element(a2);
      if ( started < 0 )
        goto LABEL_27;
    }
    if ( *(_QWORD *)(a3 + 344) )
    {
      v38 = xml_writer_start_element(a2, "content");
      v39 = a1;
      if ( v38 < 0 )
        goto LABEL_87;
      if ( (int)xmlwrite_string(a1, a2, "interpreter", *(_QWORD *)(a3 + 336)) < 0
        || (int)xmlwrite_string(a1, a2, "type", "script") < 0 )
      {
        return 4294967266LL;
      }
      started = xml_writer_end_element(a2);
      if ( started < 0 )
        goto LABEL_27;
    }
    return v27;
  }
  return result;
}

```

## disassembly

```asm
0x180111734  mov     [rsp-38h+arg_8], rbx
0x180111739  push    rbp
0x18011173a  push    rsi
0x18011173b  push    rdi
0x18011173c  push    r12
0x18011173e  push    r13
0x180111740  push    r14
0x180111742  push    r15
0x180111744  mov     rbp, rsp
0x180111747  sub     rsp, 50h
0x18011174b  mov     r9, [r8+88h]
0x180111752  xor     eax, eax
0x180111754  mov     r13, [rcx+0F8h]
0x18011175b  xor     ebx, ebx
0x18011175d  xorps   xmm0, xmm0
0x180111760  mov     [rbp+var_10], rax
0x180111764  mov     rdi, rcx
0x180111767  mov     [rbp+arg_10], rbx
0x18011176b  movups  xmmword ptr [rbp+Block], xmm0
0x18011176f  mov     al, [r9]
0x180111772  mov     r14, r8
0x180111775  mov     rsi, rdx
0x180111778  mov     [rbp+arg_0], rbx
0x18011177c  mov     rcx, r9
0x18011177f  jmp     short loc_1801117AC
0x180111781  movsx   eax, al
0x180111784  inc     rcx
0x180111787  cmp     eax, 80h
0x18011178c  jb      short loc_1801117AA
0x18011178e  and     eax, 0FCh
0x180111793  cmp     al, 0C0h
0x180111795  jnz     loc_18011185F
0x18011179b  mov     al, [rcx]
0x18011179d  and     al, 0C0h
0x18011179f  cmp     al, 80h
0x1801117a1  jnz     loc_18011185F
0x1801117a7  inc     rcx
0x1801117aa  mov     al, [rcx]
0x1801117ac  test    al, al
0x1801117ae  jnz     short loc_180111781
0x1801117b0  lea     r8, aName; "name"
0x1801117b7  mov     rcx, rdi
0x1801117ba  call    xmlwrite_string
0x1801117bf  test    eax, eax
0x1801117c1  js      loc_180111887
0x1801117c7  mov     rax, [r14+20h]
0x1801117cb  mov     r15d, 0F000h
0x1801117d1  mov     ecx, r15d
0x1801117d4  mov     [rbp+Block], rbx
0x1801117d8  mov     [rbp+Block+8], rbx
0x1801117dc  mov     edx, 1000h
0x1801117e1  mov     [rbp+var_10], rbx
0x1801117e5  mov     r12, rbx
0x1801117e8  and     cx, [rax+408h]
0x1801117ef  mov     r8d, 0A000h
0x1801117f5  movzx   eax, cx
0x1801117f8  mov     r9d, 2000h
0x1801117fe  cmp     cx, dx
0x180111801  jz      loc_180111979
0x180111807  cmp     cx, r9w
0x18011180b  jz      loc_180111970
0x180111811  mov     edx, 4000h
0x180111816  cmp     cx, dx
0x180111819  jz      loc_180111967
0x18011181f  mov     edx, 6000h
0x180111824  cmp     cx, dx
0x180111827  jz      loc_18011195E
0x18011182d  mov     edx, 8000h
0x180111832  cmp     cx, dx
0x180111835  jz      loc_18011190F
0x18011183b  cmp     cx, r8w
0x18011183f  jz      loc_180111906
0x180111845  mov     ecx, 0C000h
0x18011184a  cmp     ax, cx
0x18011184d  jnz     loc_18011190F
0x180111853  lea     rbx, aSocket; "socket"
0x18011185a  jmp     loc_180111980
0x18011185f  lea     rdx, aName; "name"
0x180111866  mov     rcx, rsi
0x180111869  call    xml_writer_start_element
0x18011186e  test    eax, eax
0x180111870  jns     short loc_1801118A4
0x180111872  lea     r8, aXmlWriterStart_0; "xml_writer_start_element() failed: %d"
0x180111879  mov     rcx, rdi
0x18011187c  mov     r9d, eax
0x18011187f  or      edx, 0FFFFFFFFh
0x180111882  call    archive_set_error
0x180111887  mov     eax, 0FFFFFFE2h
0x18011188c  mov     rbx, [rsp+50h+arg_8]
0x180111894  add     rsp, 50h
0x180111898  pop     r15
0x18011189a  pop     r14
0x18011189c  pop     r13
0x18011189e  pop     r12
0x1801118a0  pop     rdi
0x1801118a1  pop     rsi
0x1801118a2  pop     rbp
0x1801118a3  retn
0x1801118a4  lea     r8, aBase64; "base64"
0x1801118ab  mov     rcx, rsi
0x1801118ae  lea     rdx, aEnctype; "enctype"
0x1801118b5  call    xml_writer_write_attribute
0x1801118ba  test    eax, eax
0x1801118bc  jns     short loc_1801118C7
0x1801118be  lea     r8, aXmlWriterWrite; "xml_writer_write_attribute() failed: %d"
0x1801118c5  jmp     short loc_180111879
0x1801118c7  movsxd  r9, dword ptr [r14+90h]
0x1801118ce  mov     rcx, rsi
0x1801118d1  mov     rdx, [r14+88h]
0x1801118d8  call    xml_writer_write_base64
0x1801118dd  test    eax, eax
0x1801118df  jns     short loc_1801118EA
0x1801118e1  lea     r8, aXmlWriterWrite_2; "xml_writer_write_base64() failed: %d"
0x1801118e8  jmp     short loc_180111879
0x1801118ea  mov     rcx, rsi
0x1801118ed  call    xml_writer_end_element
0x1801118f2  test    eax, eax
0x1801118f4  jns     loc_1801117C7
0x1801118fa  lea     r8, aXmlWriterEndEl; "xml_writer_end_element() failed: %d"
0x180111901  jmp     loc_180111879
0x180111906  lea     rbx, aSymlink; "symlink"
0x18011190d  jmp     short loc_180111980
0x18011190f  mov     r8, [r14+50h]
0x180111913  test    r8, r8
0x180111916  jz      short loc_180111955
0x180111918  lea     rbx, aHardlink; "hardlink"
0x18011191f  lea     r12, aLink_0; "link"
0x180111926  lea     rcx, [rbp+Block]
0x18011192a  cmp     r8, r14
0x18011192d  jnz     short loc_180111943
0x18011192f  mov     r8d, 8
0x180111935  lea     rdx, aOriginal; "original"
0x18011193c  call    archive_strncat
0x180111941  jmp     short loc_180111980
0x180111943  mov     r8d, [r8+18h]
0x180111947  lea     rdx, aD_2; "%d"
0x18011194e  call    archive_string_sprintf
0x180111953  jmp     short loc_180111980
0x180111955  lea     rbx, Buf2; "file"
0x18011195c  jmp     short loc_180111980
0x18011195e  lea     rbx, aBlockSpecial; "block special"
0x180111965  jmp     short loc_180111980
0x180111967  lea     rbx, aDirectory; "directory"
0x18011196e  jmp     short loc_180111980
0x180111970  lea     rbx, aCharacterSpeci; "character special"
0x180111977  jmp     short loc_180111980
0x180111979  lea     rbx, aFifo; "fifo"
0x180111980  mov     rax, [rbp+Block]
0x180111984  lea     r8, aType; "type"
0x18011198b  mov     [rsp+50h+var_28], rax
0x180111990  mov     r9, rbx
0x180111993  mov     rdx, rsi
0x180111996  mov     [rsp+50h+var_30], r12
0x18011199b  mov     rcx, rdi
0x18011199e  call    xmlwrite_string_attr
0x1801119a3  mov     rcx, [rbp+Block]; Block
0x1801119a7  xor     r12d, r12d
0x1801119aa  mov     [rbp+Block+8], r12
0x1801119ae  mov     ebx, eax
0x1801119b0  mov     [rbp+var_10], r12
0x1801119b4  call    cs:__imp_free
0x1801119ba  mov     [rbp+Block], r12
0x1801119be  test    ebx, ebx
0x1801119c0  js      loc_180111887
0x1801119c6  test    byte ptr [r14+168h], 1
0x1801119ce  jz      short loc_1801119D7
0x1801119d0  xor     eax, eax
0x1801119d2  jmp     loc_18011188C
0x1801119d7  mov     rax, [r14+20h]
0x1801119db  mov     ecx, 2000h
0x1801119e0  and     r15w, [rax+408h]
0x1801119e8  movzx   eax, r15w
0x1801119ec  sub     ax, cx
0x1801119ef  mov     ecx, 0BFFFh
0x1801119f4  test    cx, ax
0x1801119f7  jz      short loc_180111A46
0x1801119f9  mov     eax, 0A000h
0x1801119fe  cmp     r15w, ax
0x180111a02  jnz     loc_180111AC9
0x180111a08  mov     r9, [r14+0A0h]
0x180111a0f  lea     rax, aBroken; "broken"
0x180111a16  mov     [rsp+50h+var_28], rax
0x180111a1b  lea     r8, aLink_0; "link"
0x180111a22  lea     rax, aType; "type"
0x180111a29  mov     rdx, rsi
0x180111a2c  mov     rcx, rdi
0x180111a2f  mov     [rsp+50h+var_30], rax
0x180111a34  call    xmlwrite_string_attr
0x180111a39  test    eax, eax
0x180111a3b  js      loc_180111887
0x180111a41  jmp     loc_180111AC9
0x180111a46  lea     rdx, aDevice; "device"
0x180111a4d  mov     rcx, rsi
0x180111a50  call    xml_writer_start_element
0x180111a55  test    eax, eax
0x180111a57  js      loc_180111872
0x180111a5d  mov     rcx, [r14+20h]
0x180111a61  call    archive_entry_rdevmajor
0x180111a66  lea     r9, aD_2; "%d"
0x180111a6d  mov     dword ptr [rsp+50h+var_30], eax
0x180111a71  lea     r8, aMajor; "major"
0x180111a78  mov     rdx, rsi
0x180111a7b  mov     rcx, rdi
0x180111a7e  call    xmlwrite_fstring
0x180111a83  test    eax, eax
0x180111a85  js      loc_180111887
0x180111a8b  mov     rcx, [r14+20h]
0x180111a8f  call    archive_entry_rdevminor
0x180111a94  lea     r9, aD_2; "%d"
0x180111a9b  mov     dword ptr [rsp+50h+var_30], eax
0x180111a9f  lea     r8, aMinor; "minor"
0x180111aa6  mov     rdx, rsi
0x180111aa9  mov     rcx, rdi
0x180111aac  call    xmlwrite_fstring
0x180111ab1  test    eax, eax
0x180111ab3  js      loc_180111887
0x180111ab9  mov     rcx, rsi
0x180111abc  call    xml_writer_end_element
0x180111ac1  test    eax, eax
0x180111ac3  js      loc_1801118FA
0x180111ac9  mov     rax, [r14+20h]
0x180111acd  lea     r9, aJd; "%jd"
0x180111ad4  lea     r8, aInode; "inode"
0x180111adb  mov     rdx, rsi
0x180111ade  mov     rcx, [rax+60h]
0x180111ae2  mov     [rsp+50h+var_30], rcx
0x180111ae7  mov     rcx, rdi
0x180111aea  call    xmlwrite_fstring
0x180111aef  test    eax, eax
0x180111af1  js      loc_180111887
0x180111af7  mov     rcx, [r14+20h]
0x180111afb  call    archive_entry_dev
0x180111b00  test    eax, eax
0x180111b02  jz      short loc_180111B32
0x180111b04  mov     rcx, [r14+20h]
0x180111b08  call    archive_entry_dev
0x180111b0d  lea     r9, aD_2; "%d"
0x180111b14  mov     dword ptr [rsp+50h+var_30], eax
0x180111b18  lea     r8, aDeviceno; "deviceno"
0x180111b1f  mov     rdx, rsi
0x180111b22  mov     rcx, rdi
0x180111b25  call    xmlwrite_fstring
0x180111b2a  test    eax, eax
0x180111b2c  js      loc_180111887
0x180111b32  mov     r9, [r14+20h]
0x180111b36  mov     rdx, rsi
0x180111b39  mov     rcx, rdi
0x180111b3c  movzx   r9d, word ptr [r9+408h]
0x180111b44  call    xmlwrite_mode
0x180111b49  test    eax, eax
0x180111b4b  js      loc_180111887
0x180111b51  mov     rax, [r14+20h]
0x180111b55  lea     r9, aJd; "%jd"
0x180111b5c  lea     r8, aUid; "uid"
0x180111b63  mov     rdx, rsi
0x180111b66  mov     rcx, [rax+78h]
0x180111b6a  mov     [rsp+50h+var_30], rcx
0x180111b6f  mov     rcx, rdi
0x180111b72  call    xmlwrite_fstring
0x180111b77  test    eax, eax
0x180111b79  js      loc_180111887
0x180111b7f  mov     rcx, [r14+20h]
0x180111b83  lea     r9, [rbp+arg_0]
0x180111b87  mov     rax, [r13+158h]
0x180111b8e  lea     r8, [rbp+arg_10]
0x180111b92  mov     r15d, r12d
0x180111b95  mov     [rsp+50h+var_30], rax
0x180111b9a  lea     rdx, [rcx+250h]
0x180111ba1  mov     rcx, [rcx]
0x180111ba4  call    archive_mstring_get_mbs_l
0x180111ba9  mov     ebx, 0Ch
0x180111bae  test    eax, eax
0x180111bb0  jz      short loc_180111BF8
0x180111bb2  call    cs:__imp__o__errno
0x180111bb8  cmp     [rax], ebx
0x180111bba  jnz     short loc_180111BD2
0x180111bbc  lea     r8, aCanTAllocateMe_22; "Can't allocate memory for Uname"
0x180111bc3  mov     edx, ebx
0x180111bc5  mov     rcx, rdi
0x180111bc8  call    archive_set_error
0x180111bcd  jmp     loc_180111887
0x180111bd2  mov     rcx, [r14+20h]
0x180111bd6  call    archive_entry_uname
0x180111bdb  mov     r9, rax
0x180111bde  lea     r8, aCanTTranslateU_0; "Can't translate uname '%s' to UTF-8"
0x180111be5  mov     edx, 2Ah ; '*'
0x180111bea  mov     rcx, rdi
0x180111bed  call    archive_set_error
0x180111bf2  mov     r15d, 0FFFFFFECh
0x180111bf8  cmp     [rbp+arg_0], r12
0x180111bfc  jbe     short loc_180111C1C
0x180111bfe  mov     r9, [rbp+arg_10]
0x180111c02  lea     r8, aUser_0; "user"
0x180111c09  mov     rdx, rsi
0x180111c0c  mov     rcx, rdi
0x180111c0f  call    xmlwrite_string
0x180111c14  test    eax, eax
0x180111c16  js      loc_180111887
0x180111c1c  mov     rax, [r14+20h]
0x180111c20  lea     r9, aJd; "%jd"
  ... truncated ...
```
