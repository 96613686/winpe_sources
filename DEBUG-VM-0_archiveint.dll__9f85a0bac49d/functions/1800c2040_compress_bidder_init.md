# compress_bidder_init

- ea: `0x1800c2040`
- end: `0x1800c219f`
- name: `compress_bidder_init`
- size: `351`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180006c00`
- `0x1800c2040`
- `0x1800c2280`
- `0x1800c2370`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800c2069`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800c2069`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800c2167`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800c2170`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800c2167`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800c2170`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800c2077`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800c2077`

## string_xrefs

- `0x1800c204a`: `compress (.Z)`
- `0x1800c217a`: `Can't allocate data for %s decompression`
- `0x1800c20e1`: `Invalid compressed data`

## pseudocode

```c
__int64 __fastcall compress_bidder_init(__int64 a1)
{
  char *v2; // rbx
  void *v3; // rax
  char v4; // dl
  unsigned int v5; // ecx
  int v6; // edx
  int v7; // edx

  *(_DWORD *)(a1 + 56) = 3;
  *(_QWORD *)(a1 + 48) = "compress (.Z)";
  v2 = (char *)calloc(1u, 0x3FF80u);
  v3 = malloc(0x10000u);
  if ( !v2 || !v3 )
  {
    free(v3);
    free(v2);
    archive_set_error(*(_QWORD *)(a1 + 24), 12, "Can't allocate data for %s decompression", *(const char **)(a1 + 48));
    return 4294967266LL;
  }
  *(_QWORD *)(a1 + 40) = v2;
  *((_QWORD *)v2 + 6) = v3;
  *((_QWORD *)v2 + 5) = 0x10000;
  *(_QWORD *)(a1 + 32) = off_18011DB08;
  getbits(a1, 8);
  getbits(a1, 8);
  v4 = getbits(a1, 8);
  v5 = v4 & 0x1F;
  if ( v5 > 0x10 )
  {
    archive_set_error(*(_QWORD *)(a1 + 24), 0xFFFFFFFFLL, "Invalid compressed data");
    return 4294967266LL;
  }
  *((_DWORD *)v2 + 17) = v5;
  *((_DWORD *)v2 + 16) = 1 << v5;
  v6 = v4 & 0x80;
  *((_DWORD *)v2 + 14) = v6;
  *((_QWORD *)v2 + 24588) = v2 + 196712;
  *((_DWORD *)v2 + 22) = 256;
  if ( v6 )
    *((_DWORD *)v2 + 22) = 257;
  *((_DWORD *)v2 + 19) = 9;
  v7 = 255;
  *((_DWORD *)v2 + 18) = 511;
  *((_DWORD *)v2 + 20) = -1;
  do
  {
    *(_WORD *)&v2[2 * v7 + 65628] = 0;
    v2[v7 + 92] = v7;
    --v7;
  }
  while ( v7 >= 0 );
  next_code(a1);
  return 0;
}

```

## disassembly

```asm
0x1800c2040  mov     [rsp+arg_0], rbx
0x1800c2045  push    rdi
0x1800c2046  sub     rsp, 20h
0x1800c204a  lea     rax, aCompressZ; "compress (.Z)"
0x1800c2051  mov     dword ptr [rcx+38h], 3
0x1800c2058  mov     [rcx+30h], rax
0x1800c205c  mov     rdi, rcx
0x1800c205f  mov     ecx, 1; Count
0x1800c2064  mov     edx, 3FF80h; Size
0x1800c2069  call    cs:__imp_calloc
0x1800c206f  mov     ecx, 10000h; Size
0x1800c2074  mov     rbx, rax
0x1800c2077  call    cs:__imp_malloc
0x1800c207d  test    rbx, rbx
0x1800c2080  jz      loc_1800C2164
0x1800c2086  test    rax, rax
0x1800c2089  jz      loc_1800C2164
0x1800c208f  mov     [rdi+28h], rbx
0x1800c2093  mov     edx, 8
0x1800c2098  mov     [rbx+30h], rax
0x1800c209c  mov     rcx, rdi
0x1800c209f  lea     rax, off_18011DB08
0x1800c20a6  mov     qword ptr [rbx+28h], 10000h
0x1800c20ae  mov     [rdi+20h], rax
0x1800c20b2  call    getbits
0x1800c20b7  mov     edx, 8
0x1800c20bc  mov     rcx, rdi
0x1800c20bf  call    getbits
0x1800c20c4  mov     edx, 8
0x1800c20c9  mov     rcx, rdi
0x1800c20cc  call    getbits
0x1800c20d1  mov     ecx, eax
0x1800c20d3  mov     edx, eax
0x1800c20d5  and     ecx, 1Fh
0x1800c20d8  cmp     ecx, 10h
0x1800c20db  jbe     short loc_1800C20F5
0x1800c20dd  mov     rcx, [rdi+18h]
0x1800c20e1  lea     r8, aInvalidCompres; "Invalid compressed data"
0x1800c20e8  or      edx, 0FFFFFFFFh
0x1800c20eb  call    archive_set_error
0x1800c20f0  jmp     loc_1800C218F
0x1800c20f5  mov     eax, 1
0x1800c20fa  mov     [rbx+44h], ecx
0x1800c20fd  shl     eax, cl
0x1800c20ff  mov     [rbx+40h], eax
0x1800c2102  and     edx, 80h
0x1800c2108  lea     rax, [rbx+30068h]
0x1800c210f  mov     [rbx+38h], edx
0x1800c2112  mov     [rbx+30060h], rax
0x1800c2119  mov     dword ptr [rbx+58h], 100h
0x1800c2120  jz      short loc_1800C2129
0x1800c2122  mov     dword ptr [rbx+58h], 101h
0x1800c2129  mov     dword ptr [rbx+4Ch], 9
0x1800c2130  mov     edx, 0FFh
0x1800c2135  mov     dword ptr [rbx+48h], 1FFh
0x1800c213c  mov     dword ptr [rbx+50h], 0FFFFFFFFh
0x1800c2143  mov     ecx, edx
0x1800c2145  xor     eax, eax
0x1800c2147  mov     [rbx+rcx*2+1005Ch], ax
0x1800c214f  mov     [rbx+rcx+5Ch], dl
0x1800c2153  sub     edx, 1
0x1800c2156  jns     short loc_1800C2143
0x1800c2158  mov     rcx, rdi
0x1800c215b  call    next_code
0x1800c2160  xor     eax, eax
0x1800c2162  jmp     short loc_1800C2194
0x1800c2164  mov     rcx, rax; Block
0x1800c2167  call    cs:__imp_free
0x1800c216d  mov     rcx, rbx; Block
0x1800c2170  call    cs:__imp_free
0x1800c2176  mov     r9, [rdi+30h]
0x1800c217a  lea     r8, aCanTAllocateDa_7; "Can't allocate data for %s decompressio"...
0x1800c2181  mov     rcx, [rdi+18h]
0x1800c2185  mov     edx, 0Ch
0x1800c218a  call    archive_set_error
0x1800c218f  mov     eax, 0FFFFFFE2h
0x1800c2194  mov     rbx, [rsp+28h+arg_0]
0x1800c2199  add     rsp, 20h
0x1800c219d  pop     rdi
0x1800c219e  retn
```
