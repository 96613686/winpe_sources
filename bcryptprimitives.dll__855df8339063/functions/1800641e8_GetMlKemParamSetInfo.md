# GetMlKemParamSetInfo

- ea: `0x1800641e8`
- end: `0x18006427e`
- name: `GetMlKemParamSetInfo`
- size: `150`
- prototype: `__int64 __fastcall(void *Buf1, size_t Size, wchar_t ***)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18006445c`
- `0x180065260`

## callees

- `0x18000ecb0`
- `0x1800631a8`
- `0x1800641e8`

## string_xrefs

- `0x18006425d`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\kem.c`

## pseudocode

```c
__int64 __fastcall GetMlKemParamSetInfo(void *Buf1, size_t Size, wchar_t ***a3)
{
  size_t v3; // rsi
  unsigned int v6; // ebx
  wchar_t **v7; // rdi
  unsigned int v8; // ebx
  __int64 v9; // r9
  __int64 v10; // rcx

  v3 = (unsigned int)Size;
  if ( Buf1 && (_DWORD)Size )
  {
    v6 = 0;
    while ( 1 )
    {
      v7 = &(&off_180087190)[4 * v6];
      if ( (_DWORD)v3 == *((_DWORD *)v7 + 2) && !memcmp_0(Buf1, *v7, v3) )
        break;
      if ( ++v6 >= 3 )
      {
        v8 = -1073741637;
        v9 = 634;
        v10 = 3221225659LL;
        goto LABEL_10;
      }
    }
    v8 = 0;
    *a3 = v7;
  }
  else
  {
    v8 = -1073741811;
    v9 = 611;
    v10 = 3221225485LL;
LABEL_10:
    DebugTraceError(v10, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\kem.c", v9);
  }
  return v8;
}

```

## disassembly

```asm
0x1800641e8  push    rbx
0x1800641ea  push    rbp
0x1800641eb  push    rsi
0x1800641ec  push    rdi
0x1800641ed  push    r14
0x1800641ef  sub     rsp, 20h
0x1800641f3  mov     esi, edx
0x1800641f5  mov     r14, r8
0x1800641f8  mov     rbp, rcx
0x1800641fb  test    rcx, rcx
0x1800641fe  jz      short loc_18006424D
0x180064200  test    edx, edx
0x180064202  jz      short loc_18006424D
0x180064204  xor     ebx, ebx
0x180064206  mov     edi, ebx
0x180064208  lea     rcx, off_180087190; "512"
0x18006420f  shl     rdi, 5
0x180064213  add     rdi, rcx
0x180064216  cmp     esi, [rdi+8]
0x180064219  jnz     short loc_18006422D
0x18006421b  mov     rdx, [rdi]; Buf2
0x18006421e  mov     r8, rsi; Size
0x180064221  mov     rcx, rbp; Buf1
0x180064224  call    memcmp_0
0x180064229  test    eax, eax
0x18006422b  jz      short loc_180064246
0x18006422d  inc     ebx
0x18006422f  cmp     ebx, 3
0x180064232  jb      short loc_180064206
0x180064234  mov     ebx, 0C00000BBh
0x180064239  mov     r9d, 27Ah
0x18006423f  mov     ecx, 0C00000BBh
0x180064244  jmp     short loc_18006425D
0x180064246  xor     ebx, ebx
0x180064248  mov     [r14], rdi
0x18006424b  jmp     short loc_180064270
0x18006424d  mov     ebx, 0C000000Dh
0x180064252  mov     r9d, 263h
0x180064258  mov     ecx, 0C000000Dh
0x18006425d  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180064264  lea     rdx, aStatus; "Status"
0x18006426b  call    DebugTraceError
0x180064270  mov     eax, ebx
0x180064272  add     rsp, 20h
0x180064276  pop     r14
0x180064278  pop     rdi
0x180064279  pop     rsi
0x18006427a  pop     rbp
0x18006427b  pop     rbx
0x18006427c  retn
```
