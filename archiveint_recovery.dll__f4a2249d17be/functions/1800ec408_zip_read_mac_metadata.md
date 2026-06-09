# zip_read_mac_metadata

- ea: `0x1800ec408`
- end: `0x1800ec747`
- name: `zip_read_mac_metadata`
- size: `831`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1800e83e0`

## callees

- `0x180005914`
- `0x180005c7c`
- `0x180006c00`
- `0x18000c8c0`
- `0x18000e6c0`
- `0x180012634`
- `0x1800aba54`
- `0x1800e89d0`
- `0x1800eaa88`
- `0x1800eab00`
- `0x1800ec408`
- `0x1800eeb70`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800ec72e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800ec72e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800ec4d3`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800ec4d3`

## string_xrefs

- `0x1800ec6c3`: `Out of memory for ZIP decompression`
- `0x1800ec6af`: `ZIP decompression failed (%d)`
- `0x1800ec455`: `Unsupported ZIP compression method (%s)`

## pseudocode

```c
__int64 __fastcall zip_read_mac_metadata(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v5; // rbp
  __int64 v6; // r15
  char v7; // al
  const char *v8; // rax
  signed __int64 v10; // rcx
  __int64 v11; // r9
  char *v12; // r13
  __int64 v13; // rdx
  unsigned int v14; // ebx
  __int64 local_file_header_size; // rax
  size_t v16; // r12
  unsigned int v17; // eax
  size_t v18; // r15
  const void *v19; // rax
  size_t v20; // r14
  char v21; // cl
  int v22; // eax
  __int64 v23; // rax
  int v24; // eax
  const void *v25; // [rsp+30h] [rbp-58h]
  __int64 v26; // [rsp+38h] [rbp-50h]
  unsigned int v27; // [rsp+90h] [rbp+8h]
  char *v29; // [rsp+A0h] [rbp+18h]
  size_t v30; // [rsp+A8h] [rbp+20h] BYREF

  v5 = **(_QWORD **)(a1 + 2072);
  v6 = archive_filter_bytes(a1, 0);
  v26 = v6;
  v7 = *(_BYTE *)(a3 + 128);
  if ( v7 )
  {
    if ( v7 != 8 )
    {
      v8 = (const char *)compression_name(*(unsigned __int8 *)(a3 + 128));
      archive_set_error(a1, 42, "Unsupported ZIP compression method (%s)", v8);
      return 4294967276LL;
    }
  }
  else if ( *(_QWORD *)(a3 + 48) != *(_QWORD *)(a3 + 40) )
  {
    archive_set_error(a1, 42, "Malformed OS X metadata entry: inconsistent size");
    return 4294967266LL;
  }
  v10 = *(_QWORD *)(a3 + 48);
  if ( v10 > 10485760 )
  {
    v11 = *(_QWORD *)(a3 + 48);
LABEL_10:
    archive_set_error(a1, 42, "Mac metadata is too large: %jd > %u MiB", v11, 10);
    return 4294967276LL;
  }
  v11 = *(_QWORD *)(a3 + 40);
  if ( v11 > 10485760 )
    goto LABEL_10;
  v12 = (char *)malloc(v10);
  if ( !v12 )
  {
    archive_set_error(a1, 12, "Can't allocate memory for Mac metadata");
    return 4294967266LL;
  }
  v13 = *(_QWORD *)(a3 + 32);
  v14 = 0;
  if ( v6 >= v13 )
  {
    if ( v6 != v13 )
      _archive_read_filter_seek(*(_QWORD *)(a1 + 632), v13, 0);
  }
  else
  {
    _archive_read_filter_consume(*(_QWORD *)(a1 + 632), v13 - v6);
  }
  local_file_header_size = zip_get_local_file_header_size(a1);
  _archive_read_filter_consume(*(_QWORD *)(a1 + 632), local_file_header_size);
  v16 = *(_QWORD *)(a3 + 40);
  v17 = 0;
  v18 = *(_QWORD *)(a3 + 48);
  v27 = 0;
  v29 = v12;
  while ( !v17 && v16 )
  {
    v30 = 0;
    v19 = _archive_read_filter_ahead(*(_QWORD *)(a1 + 632), 1u, &v30);
    v25 = v19;
    if ( !v19 )
    {
      archive_set_error(a1, 42, "Truncated ZIP file header");
      v14 = -20;
      goto LABEL_44;
    }
    v20 = v30;
    v21 = *(_BYTE *)(a3 + 128);
    if ( v30 > v16 )
      v20 = v16;
    if ( v21 )
    {
      if ( v21 == 8 )
      {
        v14 = zip_deflate_init(a1, v5);
        if ( v14 )
          goto LABEL_44;
        *(_QWORD *)(v5 + 184) = v25;
        *(_QWORD *)(v5 + 200) = v29;
        *(_DWORD *)(v5 + 192) = v20;
        *(_DWORD *)(v5 + 196) = 0;
        *(_DWORD *)(v5 + 208) = v18;
        *(_DWORD *)(v5 + 212) = 0;
        v22 = inflate(v5 + 184, 0);
        if ( v22 == -4 )
        {
          archive_set_error(a1, 12, "Out of memory for ZIP decompression");
          goto LABEL_41;
        }
        if ( v22 )
        {
          if ( v22 != v14 + 1 )
          {
            archive_set_error(a1, 0xFFFFFFFFLL, "ZIP decompression failed (%d)", v22);
LABEL_41:
            v14 = -30;
            goto LABEL_44;
          }
          v27 = v14 + 1;
        }
        v23 = *(unsigned int *)(v5 + 212);
        v20 = *(unsigned int *)(v5 + 196);
        v18 -= v23;
        v29 += v23;
      }
      else
      {
        v20 = 0;
      }
    }
    else
    {
      if ( v20 > v18 )
        v20 = v18;
      memcpy_0(v29, v19, v20);
      v18 -= v20;
      v29 += v20;
      v24 = v27;
      if ( !v18 )
        v24 = 1;
      v27 = v24;
    }
    _archive_read_filter_consume(*(_QWORD *)(a1 + 632), v20);
    v17 = v27;
    v16 -= v20;
  }
  archive_entry_copy_mac_metadata(a2, v12, *(_QWORD *)(a3 + 48) - v18);
LABEL_44:
  _archive_read_filter_seek(*(_QWORD *)(a1 + 632), v26, 0);
  *(_BYTE *)(v5 + 161) = 0;
  free(v12);
  return v14;
}

```

## disassembly

```asm
0x1800ec408  mov     [rsp+arg_8], rdx
0x1800ec40d  push    rbx
0x1800ec40e  push    rbp
0x1800ec40f  push    rsi
0x1800ec410  push    rdi
0x1800ec411  push    r12
0x1800ec413  push    r13
0x1800ec415  push    r14
0x1800ec417  push    r15
0x1800ec419  sub     rsp, 48h
0x1800ec41d  mov     rax, [rcx+818h]
0x1800ec424  xor     edx, edx
0x1800ec426  mov     rsi, r8
0x1800ec429  mov     rdi, rcx
0x1800ec42c  mov     rbp, [rax]
0x1800ec42f  call    archive_filter_bytes
0x1800ec434  mov     r15, rax
0x1800ec437  mov     [rsp+88h+var_50], rax
0x1800ec43c  movzx   eax, byte ptr [rsi+80h]
0x1800ec443  test    al, al
0x1800ec445  jz      short loc_1800EC473
0x1800ec447  cmp     al, 8
0x1800ec449  jz      short loc_1800EC49B
0x1800ec44b  mov     ecx, eax
0x1800ec44d  call    compression_name
0x1800ec452  mov     r9, rax
0x1800ec455  lea     r8, aUnsupportedZip_0; "Unsupported ZIP compression method (%s)"
0x1800ec45c  mov     edx, 2Ah ; '*'
0x1800ec461  mov     rcx, rdi
0x1800ec464  call    archive_set_error
0x1800ec469  mov     eax, 0FFFFFFECh
0x1800ec46e  jmp     loc_1800EC736
0x1800ec473  mov     rax, [rsi+28h]
0x1800ec477  cmp     [rsi+30h], rax
0x1800ec47b  jz      short loc_1800EC49B
0x1800ec47d  lea     r8, aMalformedOsXMe; "Malformed OS X metadata entry: inconsis"...
0x1800ec484  mov     edx, 2Ah ; '*'
0x1800ec489  mov     rcx, rdi
0x1800ec48c  call    archive_set_error
0x1800ec491  mov     eax, 0FFFFFFE2h
0x1800ec496  jmp     loc_1800EC736
0x1800ec49b  mov     rcx, [rsi+30h]; Size
0x1800ec49f  mov     eax, 0A00000h
0x1800ec4a4  cmp     rcx, rax
0x1800ec4a7  jle     short loc_1800EC4CA
0x1800ec4a9  mov     r9, rcx
0x1800ec4ac  lea     r8, aMacMetadataIsT; "Mac metadata is too large: %jd > %u MiB"
0x1800ec4b3  mov     [rsp+88h+var_68], 0Ah
0x1800ec4bb  mov     edx, 2Ah ; '*'
0x1800ec4c0  mov     rcx, rdi
0x1800ec4c3  call    archive_set_error
0x1800ec4c8  jmp     short loc_1800EC469
0x1800ec4ca  mov     r9, [rsi+28h]
0x1800ec4ce  cmp     r9, rax
0x1800ec4d1  jg      short loc_1800EC4AC
0x1800ec4d3  call    cs:__imp_malloc
0x1800ec4d9  mov     r13, rax
0x1800ec4dc  test    rax, rax
0x1800ec4df  jnz     short loc_1800EC4ED
0x1800ec4e1  lea     r8, aCanTAllocateMe_8; "Can't allocate memory for Mac metadata"
0x1800ec4e8  lea     edx, [rax+0Ch]
0x1800ec4eb  jmp     short loc_1800EC489
0x1800ec4ed  mov     rdx, [rsi+20h]
0x1800ec4f1  xor     ebx, ebx
0x1800ec4f3  cmp     r15, rdx
0x1800ec4f6  jge     short loc_1800EC509
0x1800ec4f8  mov     rcx, [rdi+278h]
0x1800ec4ff  sub     rdx, r15
0x1800ec502  call    __archive_read_filter_consume
0x1800ec507  jmp     short loc_1800EC51A
0x1800ec509  jz      short loc_1800EC51A
0x1800ec50b  mov     rcx, [rdi+278h]
0x1800ec512  xor     r8d, r8d
0x1800ec515  call    __archive_read_filter_seek
0x1800ec51a  mov     rcx, rdi
0x1800ec51d  call    zip_get_local_file_header_size
0x1800ec522  mov     rcx, [rdi+278h]
0x1800ec529  mov     rdx, rax
0x1800ec52c  call    __archive_read_filter_consume
0x1800ec531  mov     r12, [rsi+28h]
0x1800ec535  xor     eax, eax
0x1800ec537  mov     r15, [rsi+30h]
0x1800ec53b  mov     [rsp+88h+arg_0], eax
0x1800ec542  mov     [rsp+88h+arg_10], r13
0x1800ec54a  mov     ecx, 1
0x1800ec54f  test    eax, eax
0x1800ec551  jnz     loc_1800EC6F9
0x1800ec557  test    r12, r12
0x1800ec55a  jz      loc_1800EC6F9
0x1800ec560  mov     edx, ecx
0x1800ec562  mov     [rsp+88h+arg_18], 0
0x1800ec56e  mov     rcx, [rdi+278h]
0x1800ec575  lea     r8, [rsp+88h+arg_18]
0x1800ec57d  call    __archive_read_filter_ahead
0x1800ec582  mov     [rsp+88h+var_58], rax
0x1800ec587  test    rax, rax
0x1800ec58a  jz      loc_1800EC6DE
0x1800ec590  mov     r14, [rsp+88h+arg_18]
0x1800ec598  mov     cl, [rsi+80h]
0x1800ec59e  cmp     r14, r12
0x1800ec5a1  cmova   r14, r12
0x1800ec5a5  test    cl, cl
0x1800ec5a7  jz      loc_1800EC647
0x1800ec5ad  cmp     cl, 8
0x1800ec5b0  jz      short loc_1800EC5BA
0x1800ec5b2  xor     r14d, r14d
0x1800ec5b5  jmp     loc_1800EC68E
0x1800ec5ba  mov     rdx, rbp
0x1800ec5bd  mov     rcx, rdi
0x1800ec5c0  call    zip_deflate_init
0x1800ec5c5  mov     ebx, eax
0x1800ec5c7  test    eax, eax
0x1800ec5c9  jnz     loc_1800EC710
0x1800ec5cf  mov     rax, [rsp+88h+var_58]
0x1800ec5d4  lea     rcx, [rbp+0B8h]
0x1800ec5db  mov     [rcx], rax
0x1800ec5de  xor     edx, edx
0x1800ec5e0  mov     rax, [rsp+88h+arg_10]
0x1800ec5e8  mov     [rbp+0C8h], rax
0x1800ec5ef  mov     [rbp+0C0h], r14d
0x1800ec5f6  mov     [rbp+0C4h], ebx
0x1800ec5fc  mov     [rbp+0D0h], r15d
0x1800ec603  mov     [rbp+0D4h], ebx
0x1800ec609  call    inflate
0x1800ec60e  cmp     eax, 0FFFFFFFCh
0x1800ec611  jz      loc_1800EC6C3
0x1800ec617  test    eax, eax
0x1800ec619  jz      short loc_1800EC62D
0x1800ec61b  lea     ecx, [rbx+1]
0x1800ec61e  cmp     eax, ecx
0x1800ec620  jnz     loc_1800EC6AC
0x1800ec626  mov     [rsp+88h+arg_0], ecx
0x1800ec62d  mov     eax, [rbp+0D4h]
0x1800ec633  mov     r14d, [rbp+0C4h]
0x1800ec63a  sub     r15, rax
0x1800ec63d  add     [rsp+88h+arg_10], rax
0x1800ec645  jmp     short loc_1800EC68E
0x1800ec647  mov     rcx, [rsp+88h+arg_10]; void *
0x1800ec64f  cmp     r14, r15
0x1800ec652  mov     rdx, rax; Src
0x1800ec655  cmova   r14, r15
0x1800ec659  mov     r8, r14; Size
0x1800ec65c  call    memcpy_0
0x1800ec661  mov     rax, [rsp+88h+arg_10]
0x1800ec669  sub     r15, r14
0x1800ec66c  mov     ecx, 1
0x1800ec671  lea     rax, [r14+rax]
0x1800ec675  mov     [rsp+88h+arg_10], rax
0x1800ec67d  mov     eax, [rsp+88h+arg_0]
0x1800ec684  cmovz   eax, ecx
0x1800ec687  mov     [rsp+88h+arg_0], eax
0x1800ec68e  mov     rcx, [rdi+278h]
0x1800ec695  mov     rdx, r14
0x1800ec698  call    __archive_read_filter_consume
0x1800ec69d  mov     eax, [rsp+88h+arg_0]
0x1800ec6a4  sub     r12, r14
0x1800ec6a7  jmp     loc_1800EC54A
0x1800ec6ac  mov     r9d, eax
0x1800ec6af  lea     r8, aZipDecompressi; "ZIP decompression failed (%d)"
0x1800ec6b6  or      edx, 0FFFFFFFFh
0x1800ec6b9  mov     rcx, rdi
0x1800ec6bc  call    archive_set_error
0x1800ec6c1  jmp     short loc_1800EC6D7
0x1800ec6c3  lea     r8, aOutOfMemoryFor_0; "Out of memory for ZIP decompression"
0x1800ec6ca  mov     edx, 0Ch
0x1800ec6cf  mov     rcx, rdi
0x1800ec6d2  call    archive_set_error
0x1800ec6d7  mov     ebx, 0FFFFFFE2h
0x1800ec6dc  jmp     short loc_1800EC710
0x1800ec6de  lea     r8, aTruncatedZipFi_1; "Truncated ZIP file header"
0x1800ec6e5  mov     edx, 2Ah ; '*'
0x1800ec6ea  mov     rcx, rdi
0x1800ec6ed  call    archive_set_error
0x1800ec6f2  mov     ebx, 0FFFFFFECh
0x1800ec6f7  jmp     short loc_1800EC710
0x1800ec6f9  mov     r8, [rsi+30h]
0x1800ec6fd  mov     rdx, r13
0x1800ec700  mov     rcx, [rsp+88h+arg_8]
0x1800ec708  sub     r8, r15
0x1800ec70b  call    archive_entry_copy_mac_metadata
0x1800ec710  mov     rdx, [rsp+88h+var_50]
0x1800ec715  xor     r8d, r8d
0x1800ec718  mov     rcx, [rdi+278h]
0x1800ec71f  call    __archive_read_filter_seek
0x1800ec724  mov     rcx, r13; Block
0x1800ec727  mov     byte ptr [rbp+0A1h], 0
0x1800ec72e  call    cs:__imp_free
0x1800ec734  mov     eax, ebx
0x1800ec736  add     rsp, 48h
0x1800ec73a  pop     r15
0x1800ec73c  pop     r14
0x1800ec73e  pop     r13
0x1800ec740  pop     r12
0x1800ec742  pop     rdi
0x1800ec743  pop     rsi
0x1800ec744  pop     rbp
0x1800ec745  pop     rbx
0x1800ec746  retn
```
