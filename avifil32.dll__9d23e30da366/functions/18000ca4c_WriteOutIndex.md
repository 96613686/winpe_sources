# WriteOutIndex

- ea: `0x18000ca4c`
- end: `0x18000cce8`
- name: `WriteOutIndex`
- size: `668`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000b87c`

## callees

- `0x180001460`
- `0x18000ca4c`
- `0x180014468`
- `0x180014600`
- `0x180014960`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000ccb0`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000ccb0`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18000cad2`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18000cad2`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000cca7`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000ccb9`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000cca7`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000ccb9`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000cac9`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000cac9`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000ccc2`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000ccc2`

## pseudocode

```c
__int64 __fastcall WriteOutIndex(__int64 a1, int a2)
{
  _DWORD *v2; // rax
  __int64 v3; // rdi
  unsigned int v5; // ebp
  HGLOBAL v6; // rax
  char *v7; // r15
  int *v8; // r8
  int v9; // esi
  int v10; // r9d
  _DWORD *v11; // r10
  int v12; // r14d
  int v13; // edx
  __int16 v14; // r11
  unsigned int v15; // r12d
  int v16; // eax
  unsigned int v17; // ebx
  int v18; // eax
  int v19; // r13d
  int v20; // eax
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx
  HGLOBAL v24; // rax
  HGLOBAL v25; // rax
  int v27; // [rsp+24h] [rbp-94h]
  int v28; // [rsp+28h] [rbp-90h]
  int v29; // [rsp+30h] [rbp-88h]
  int v30; // [rsp+34h] [rbp-84h]
  char *v32; // [rsp+48h] [rbp-70h]
  int v33; // [rsp+50h] [rbp-68h] BYREF
  __int128 v34; // [rsp+54h] [rbp-64h]

  v2 = *(_DWORD **)(a1 + 1248);
  v34 = 0;
  v33 = 829973609;
  v3 = a1;
  LODWORD(v34) = 16 * *v2;
  if ( (unsigned int)shfileCreateChunk(*(_QWORD *)(a1 + 664), &v33, 0) )
    return 0;
  v5 = 0;
  v6 = GlobalAlloc(0x42u, 0x8000u);
  v32 = (char *)GlobalLock(v6);
  v7 = v32;
  if ( v32 )
  {
    v8 = *(int **)(v3 + 1248);
    if ( *v8 > 0 )
    {
      v9 = 2048;
      v10 = 0;
      do
      {
        if ( !v8 )
          break;
        v11 = v7;
        v12 = v10;
        if ( v10 < *v8 )
        {
          do
          {
            if ( v12 >= v10 + v9 )
              break;
            v13 = HIWORD(v8[3 * v12 + 2]);
            v14 = v8[3 * v12 + 2];
            v15 = HIWORD(v8[3 * v12 + 2]) & 0xF;
            v29 = v8[3 * v12 + 4];
            v16 = 55;
            if ( v15 <= 9 )
              v16 = 48;
            v27 = v16;
            v17 = (unsigned __int8)HIWORD(v8[3 * v12 + 2]) >> 4;
            v18 = 55;
            if ( v17 <= 9 )
              v18 = 48;
            v19 = v14 & 0x20;
            v28 = v18;
            v20 = (v19 != 0 ? 0x10 : 0) | 0x100;
            if ( (v14 & 0x80) == 0 )
              v20 = v19 != 0 ? 0x10 : 0;
            v21 = v20 | 1;
            if ( v13 != 127 )
              v21 = v20;
            v30 = v21;
            if ( v13 == 127 )
            {
              v22 = 543384946;
            }
            else
            {
              v23 = (v17 + v28) | ((v15 + v27) << 8);
              if ( (v14 & 0x60) == 0x60 )
              {
                v22 = v23 | 0x62770000;
              }
              else if ( (v14 & 0x80) != 0 )
              {
                v22 = v23 | 0x63700000;
              }
              else if ( (v8[3 * v12 + 2] & 0x8000) != 0 )
              {
                v22 = v23 | 0x78640000;
              }
              else
              {
                v22 = (v14 & 0x20) != 0 ? v23 | 0x62640000 : v23 | 0x63640000;
              }
            }
            v11[2] = v8[3 * v12++ + 3] - a2;
            v11[3] = v29;
            v11[1] = v30;
            *v11 = v22;
            v11 += 4;
          }
          while ( v12 < *v8 );
          v3 = a1;
          v5 = 0;
          v7 = v32;
        }
        v9 = v12 - v10;
        if ( v12 == v10 )
          break;
        if ( shfileWrite(*(_QWORD *)(v3 + 664), v7, 16 * v9) != 16 * v9 )
          goto LABEL_35;
        v8 = *(int **)(v3 + 1248);
        v10 = v12;
      }
      while ( v12 < *v8 );
    }
    if ( !(unsigned int)shfileAscend(*(_QWORD *)(v3 + 664), &v33) )
      v5 = 1;
LABEL_35:
    v24 = GlobalHandle(v7);
    GlobalUnlock(v24);
    v25 = GlobalHandle(v7);
    GlobalFree(v25);
  }
  return v5;
}

```

## disassembly

```asm
0x18000ca4c  push    rbx
0x18000ca4e  push    rbp
0x18000ca4f  push    rsi
0x18000ca50  push    rdi
0x18000ca51  push    r12
0x18000ca53  push    r13
0x18000ca55  push    r14
0x18000ca57  push    r15
0x18000ca59  sub     rsp, 78h
0x18000ca5d  mov     rax, cs:__security_cookie
0x18000ca64  xor     rax, rsp
0x18000ca67  mov     [rsp+0B8h+var_50], rax
0x18000ca6c  mov     rax, [rcx+4E0h]
0x18000ca73  xorps   xmm0, xmm0
0x18000ca76  movdqu  [rsp+0B8h+var_64], xmm0
0x18000ca7c  mov     [rsp+0B8h+var_68], 31786469h
0x18000ca84  mov     rdi, rcx
0x18000ca87  mov     [rsp+0B8h+var_98], edx
0x18000ca8b  lea     rdx, [rsp+0B8h+var_68]
0x18000ca90  mov     r8d, [rax]
0x18000ca93  shl     r8d, 4
0x18000ca97  mov     dword ptr [rsp+0B8h+var_64], r8d
0x18000ca9c  xor     r8d, r8d
0x18000ca9f  mov     [rsp+0B8h+var_78], rcx
0x18000caa4  mov     rcx, [rcx+298h]
0x18000caab  call    shfileCreateChunk
0x18000cab0  test    eax, eax
0x18000cab2  jz      short loc_18000CABB
0x18000cab4  xor     eax, eax
0x18000cab6  jmp     loc_18000CCCA
0x18000cabb  xor     ebp, ebp
0x18000cabd  mov     edx, 8000h; dwBytes
0x18000cac2  mov     [rsp+0B8h+var_80], ebp
0x18000cac6  lea     ecx, [rbp+42h]; uFlags
0x18000cac9  call    cs:__imp_GlobalAlloc
0x18000cacf  mov     rcx, rax; hMem
0x18000cad2  call    cs:__imp_GlobalLock
0x18000cad8  mov     [rsp+0B8h+var_70], rax
0x18000cadd  mov     r15, rax
0x18000cae0  test    rax, rax
0x18000cae3  jz      loc_18000CCC8
0x18000cae9  mov     r8, [rdi+4E0h]
0x18000caf0  lea     r12d, [rbp+1]
0x18000caf4  cmp     [r8], ebp
0x18000caf7  jle     loc_18000CC8D
0x18000cafd  mov     esi, 800h
0x18000cb02  xor     r9d, r9d
0x18000cb05  test    r8, r8
0x18000cb08  jz      loc_18000CC8D
0x18000cb0e  mov     r10, r15
0x18000cb11  mov     r14d, r9d
0x18000cb14  cmp     r9d, [r8]
0x18000cb17  jge     loc_18000CC57
0x18000cb1d  mov     edi, [rsp+0B8h+var_98]
0x18000cb21  lea     ebp, [r9+rsi]
0x18000cb25  mov     r15d, 30h ; '0'
0x18000cb2b  cmp     r14d, ebp
0x18000cb2e  jge     loc_18000CC49
0x18000cb34  movsxd  rax, r14d
0x18000cb37  lea     rcx, [rax+rax*2]
0x18000cb3b  movzx   edx, word ptr [r8+rcx*4+0Ah]
0x18000cb41  movzx   r11d, word ptr [r8+rcx*4+8]
0x18000cb47  mov     r12d, edx
0x18000cb4a  mov     eax, [r8+rcx*4+0Ch]
0x18000cb4f  and     r12d, 0Fh
0x18000cb53  sub     eax, edi
0x18000cb55  mov     ebx, edx
0x18000cb57  mov     [rsp+0B8h+var_8C], eax
0x18000cb5b  cmp     r12d, 9
0x18000cb5f  mov     eax, [r8+rcx*4+10h]
0x18000cb64  mov     r13d, r11d
0x18000cb67  mov     [rsp+0B8h+var_88], eax
0x18000cb6b  mov     esi, r11d
0x18000cb6e  mov     eax, 37h ; '7'
0x18000cb73  cmovbe  eax, r15d
0x18000cb77  shr     ebx, 4
0x18000cb7a  mov     [rsp+0B8h+var_94], eax
0x18000cb7e  and     ebx, 0Fh
0x18000cb81  cmp     ebx, 9
0x18000cb84  mov     eax, 37h ; '7'
0x18000cb89  cmovbe  eax, r15d
0x18000cb8d  and     r13d, 20h
0x18000cb91  mov     [rsp+0B8h+var_90], eax
0x18000cb95  mov     eax, r13d
0x18000cb98  neg     eax
0x18000cb9a  sbb     ecx, ecx
0x18000cb9c  and     ecx, 10h
0x18000cb9f  mov     eax, ecx
0x18000cba1  bts     eax, 8
0x18000cba5  and     esi, 80h
0x18000cbab  cmovz   eax, ecx
0x18000cbae  mov     ecx, eax
0x18000cbb0  or      ecx, 1
0x18000cbb3  cmp     edx, 7Fh
0x18000cbb6  cmovnz  ecx, eax
0x18000cbb9  mov     [rsp+0B8h+var_84], ecx
0x18000cbbd  jnz     short loc_18000CBC6
0x18000cbbf  mov     ecx, 20636572h
0x18000cbc4  jmp     short loc_18000CC18
0x18000cbc6  mov     ecx, [rsp+0B8h+var_94]
0x18000cbca  mov     eax, [rsp+0B8h+var_90]
0x18000cbce  add     ecx, r12d
0x18000cbd1  add     eax, ebx
0x18000cbd3  shl     ecx, 8
0x18000cbd6  or      ecx, eax
0x18000cbd8  mov     eax, r11d
0x18000cbdb  and     eax, 60h
0x18000cbde  cmp     al, 60h ; '`'
0x18000cbe0  jnz     short loc_18000CBEA
0x18000cbe2  or      ecx, 62770000h
0x18000cbe8  jmp     short loc_18000CC18
0x18000cbea  test    esi, esi
0x18000cbec  jz      short loc_18000CBF6
0x18000cbee  or      ecx, 63700000h
0x18000cbf4  jmp     short loc_18000CC18
0x18000cbf6  bt      r11d, 0Fh
0x18000cbfb  jnb     short loc_18000CC05
0x18000cbfd  or      ecx, 78640000h
0x18000cc03  jmp     short loc_18000CC18
0x18000cc05  test    r13d, r13d
0x18000cc08  jz      short loc_18000CC12
0x18000cc0a  or      ecx, 62640000h
0x18000cc10  jmp     short loc_18000CC18
0x18000cc12  or      ecx, 63640000h
0x18000cc18  mov     eax, [rsp+0B8h+var_8C]
0x18000cc1c  mov     r12d, 1
0x18000cc22  mov     [r10+8], eax
0x18000cc26  add     r14d, r12d
0x18000cc29  mov     eax, [rsp+0B8h+var_88]
0x18000cc2d  mov     [r10+0Ch], eax
0x18000cc31  mov     eax, [rsp+0B8h+var_84]
0x18000cc35  mov     [r10+4], eax
0x18000cc39  mov     [r10], ecx
0x18000cc3c  add     r10, 10h
0x18000cc40  cmp     r14d, [r8]
0x18000cc43  jl      loc_18000CB2B
0x18000cc49  mov     rdi, [rsp+0B8h+var_78]
0x18000cc4e  mov     ebp, [rsp+0B8h+var_80]
0x18000cc52  mov     r15, [rsp+0B8h+var_70]
0x18000cc57  mov     esi, r14d
0x18000cc5a  sub     esi, r9d
0x18000cc5d  jz      short loc_18000CC8D
0x18000cc5f  mov     rcx, [rdi+298h]
0x18000cc66  mov     ebx, esi
0x18000cc68  shl     ebx, 4
0x18000cc6b  mov     rdx, r15
0x18000cc6e  mov     r8d, ebx
0x18000cc71  call    shfileWrite
0x18000cc76  cmp     eax, ebx
0x18000cc78  jnz     short loc_18000CCA4
0x18000cc7a  mov     r8, [rdi+4E0h]
0x18000cc81  mov     r9d, r14d
0x18000cc84  cmp     r14d, [r8]
0x18000cc87  jl      loc_18000CB05
0x18000cc8d  mov     rcx, [rdi+298h]
0x18000cc94  lea     rdx, [rsp+0B8h+var_68]
0x18000cc99  call    shfileAscend
0x18000cc9e  test    eax, eax
0x18000cca0  cmovz   ebp, r12d
0x18000cca4  mov     rcx, r15; pMem
0x18000cca7  call    cs:__imp_GlobalHandle
0x18000ccad  mov     rcx, rax; hMem
0x18000ccb0  call    cs:__imp_GlobalUnlock
0x18000ccb6  mov     rcx, r15; pMem
0x18000ccb9  call    cs:__imp_GlobalHandle
0x18000ccbf  mov     rcx, rax; hMem
0x18000ccc2  call    cs:__imp_GlobalFree
0x18000ccc8  mov     eax, ebp
0x18000ccca  mov     rcx, [rsp+0B8h+var_50]
0x18000cccf  xor     rcx, rsp; StackCookie
0x18000ccd2  call    __security_check_cookie
0x18000ccd7  add     rsp, 78h
0x18000ccdb  pop     r15
0x18000ccdd  pop     r14
0x18000ccdf  pop     r13
0x18000cce1  pop     r12
0x18000cce3  pop     rdi
0x18000cce4  pop     rsi
0x18000cce5  pop     rbp
0x18000cce6  pop     rbx
0x18000cce7  retn
```
