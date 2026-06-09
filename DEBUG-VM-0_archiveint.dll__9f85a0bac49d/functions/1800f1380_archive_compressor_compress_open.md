# archive_compressor_compress_open

- ea: `0x1800f1380`
- end: `0x1800f14f5`
- name: `archive_compressor_compress_open`
- size: `373`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180006c00`
- `0x180015810`
- `0x1800f0450`
- `0x1800f1380`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800f13a9`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800f13a9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f1438`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f1438`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800f1410`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800f1410`

## string_xrefs

- `0x1800f138a`: `compress`
- `0x1800f1426`: `Can't allocate data for compression buffer`
- `0x1800f13bb`: `Can't allocate data for compression`

## pseudocode

```c
__int64 __fastcall archive_compressor_compress_open(__int64 a1)
{
  _QWORD *v2; // rax
  _DWORD *v3; // rcx
  _QWORD *v4; // rbx
  __int64 result; // rax
  size_t v6; // rdi
  int v7; // eax
  void *v8; // rax

  *(_DWORD *)(a1 + 88) = 3;
  *(_QWORD *)(a1 + 80) = "compress";
  v2 = calloc(1u, 0x65190u);
  v3 = *(_DWORD **)(a1 + 8);
  v4 = v2;
  if ( !v2 )
  {
    archive_set_error(v3, 12, "Can't allocate data for compression");
    return 4294967266LL;
  }
  v6 = 0x10000;
  if ( *v3 == -1329217314 )
  {
    v7 = archive_write_get_bytes_per_block();
    if ( (unsigned __int64)v7 <= 0x10000 )
    {
      if ( v7 )
        v6 = 0x10000 - 0x10000uLL % v7;
    }
    else
    {
      v6 = v7;
    }
  }
  v4[51760] = v6;
  v8 = malloc(v6);
  v4[51759] = v8;
  if ( !v8 )
  {
    archive_set_error(*(_QWORD *)(a1 + 8), 12, "Can't allocate data for compression buffer");
    free(v4);
    return 4294967266LL;
  }
  *(_QWORD *)(a1 + 40) = archive_compressor_compress_write;
  *(_QWORD *)(a1 + 56) = archive_compressor_compress_close;
  *(_QWORD *)(a1 + 64) = archive_compressor_compress_free;
  *((_DWORD *)v4 + 8) = 0x10000;
  *v4 = 0;
  *((_BYTE *)v4 + 414064) = 0;
  *((_DWORD *)v4 + 103515) = 0;
  v4[1] = 3;
  *(_QWORD *)((char *)v4 + 414044) = 257;
  v4[2] = 10000;
  *((_DWORD *)v4 + 6) = 9;
  *((_DWORD *)v4 + 7) = 511;
  memset_0((char *)v4 + 36, 255, 0x43624u);
  *(_BYTE *)v4[51759] = 31;
  *(_BYTE *)(v4[51759] + 1LL) = -99;
  *(_BYTE *)(v4[51759] + 2LL) = -112;
  result = 0;
  v4[51761] = 3;
  *(_QWORD *)(a1 + 72) = v4;
  return result;
}

```

## disassembly

```asm
0x1800f1380  push    rbx
0x1800f1382  push    rsi
0x1800f1383  push    rdi
0x1800f1384  push    r14
0x1800f1386  sub     rsp, 28h
0x1800f138a  lea     rax, aCompress_0; "compress"
0x1800f1391  mov     dword ptr [rcx+58h], 3
0x1800f1398  mov     [rcx+50h], rax
0x1800f139c  mov     rsi, rcx
0x1800f139f  mov     ecx, 1; Count
0x1800f13a4  mov     edx, 65190h; Size
0x1800f13a9  call    cs:__imp_calloc
0x1800f13af  mov     rcx, [rsi+8]
0x1800f13b3  mov     rbx, rax
0x1800f13b6  test    rax, rax
0x1800f13b9  jnz     short loc_1800F13D4
0x1800f13bb  lea     r8, aCanTAllocateDa_2; "Can't allocate data for compression"
0x1800f13c2  lea     edx, [rax+0Ch]
0x1800f13c5  call    archive_set_error
0x1800f13ca  mov     eax, 0FFFFFFE2h
0x1800f13cf  jmp     loc_1800F14EB
0x1800f13d4  cmp     dword ptr [rcx], 0B0C5C0DEh
0x1800f13da  mov     r14d, 10000h
0x1800f13e0  mov     edi, r14d
0x1800f13e3  jnz     short loc_1800F1406
0x1800f13e5  call    archive_write_get_bytes_per_block
0x1800f13ea  movsxd  rcx, eax
0x1800f13ed  cmp     rcx, r14
0x1800f13f0  jbe     short loc_1800F13F7
0x1800f13f2  mov     rdi, rcx
0x1800f13f5  jmp     short loc_1800F1406
0x1800f13f7  test    eax, eax
0x1800f13f9  jz      short loc_1800F1406
0x1800f13fb  xor     edx, edx
0x1800f13fd  mov     rax, r14
0x1800f1400  div     rcx
0x1800f1403  sub     rdi, rdx
0x1800f1406  mov     rcx, rdi; Size
0x1800f1409  mov     [rbx+65180h], rdi
0x1800f1410  call    cs:__imp_malloc
0x1800f1416  mov     [rbx+65178h], rax
0x1800f141d  test    rax, rax
0x1800f1420  jnz     short loc_1800F1440
0x1800f1422  mov     rcx, [rsi+8]
0x1800f1426  lea     r8, aCanTAllocateDa_3; "Can't allocate data for compression buf"...
0x1800f142d  lea     edx, [rax+0Ch]
0x1800f1430  call    archive_set_error
0x1800f1435  mov     rcx, rbx; Block
0x1800f1438  call    cs:__imp_free
0x1800f143e  jmp     short loc_1800F13CA
0x1800f1440  lea     rax, archive_compressor_compress_write
0x1800f1447  mov     edx, 0FFh; Val
0x1800f144c  mov     [rsi+28h], rax
0x1800f1450  lea     rcx, [rbx+24h]; void *
0x1800f1454  lea     rax, archive_compressor_compress_close
0x1800f145b  mov     r8d, 43624h; Size
0x1800f1461  mov     [rsi+38h], rax
0x1800f1465  lea     rax, archive_compressor_compress_free
0x1800f146c  mov     [rsi+40h], rax
0x1800f1470  mov     [rbx+20h], r14d
0x1800f1474  mov     qword ptr [rbx], 0
0x1800f147b  mov     byte ptr [rbx+65170h], 0
0x1800f1482  mov     dword ptr [rbx+6516Ch], 0
0x1800f148c  mov     qword ptr [rbx+8], 3
0x1800f1494  mov     qword ptr [rbx+6515Ch], 101h
0x1800f149f  mov     qword ptr [rbx+10h], 2710h
0x1800f14a7  mov     dword ptr [rbx+18h], 9
0x1800f14ae  mov     dword ptr [rbx+1Ch], 1FFh
0x1800f14b5  call    memset_0
0x1800f14ba  mov     rax, [rbx+65178h]
0x1800f14c1  mov     byte ptr [rax], 1Fh
0x1800f14c4  mov     rax, [rbx+65178h]
0x1800f14cb  mov     byte ptr [rax+1], 9Dh
0x1800f14cf  mov     rax, [rbx+65178h]
0x1800f14d6  mov     byte ptr [rax+2], 90h
0x1800f14da  xor     eax, eax
0x1800f14dc  mov     qword ptr [rbx+65188h], 3
0x1800f14e7  mov     [rsi+48h], rbx
0x1800f14eb  add     rsp, 28h
0x1800f14ef  pop     r14
0x1800f14f1  pop     rdi
0x1800f14f2  pop     rsi
0x1800f14f3  pop     rbx
0x1800f14f4  retn
```
