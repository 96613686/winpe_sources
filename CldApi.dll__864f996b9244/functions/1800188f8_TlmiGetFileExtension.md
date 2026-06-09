# TlmiGetFileExtension

- ea: `0x1800188f8`
- end: `0x1800189a5`
- name: `TlmiGetFileExtension`
- size: `173`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180017728`

## callees

- `0x1800188f8`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18001891e`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18001891e`

## pseudocode

```c
__int64 __fastcall TlmiGetFileExtension(__int64 a1, const wchar_t *a2)
{
  unsigned __int16 v4; // si
  size_t v5; // rax
  const wchar_t *v6; // rcx
  const wchar_t *v7; // rax
  __int128 v8; // xmm0
  __int16 v9; // cx

  *(_OWORD *)a1 = 0;
  if ( !a2 )
    goto LABEL_15;
  v4 = 0;
  v5 = wcsnlen(a2, 0x8000u);
  if ( a2[v5] )
    goto LABEL_15;
  v6 = &a2[v5 - 1];
  v7 = v6;
  if ( v6 >= a2 )
  {
    while ( 1 )
    {
      if ( *v7 == 92 )
      {
LABEL_8:
        if ( v4 <= 0xFu )
          goto LABEL_11;
LABEL_9:
        v8 = *(_OWORD *)L"\"$";
        goto LABEL_16;
      }
      if ( v4 > 0xFu )
        goto LABEL_9;
      if ( *v7 == 46 )
        break;
      ++v4;
      if ( --v7 < a2 )
        goto LABEL_8;
    }
    ++v7;
  }
LABEL_11:
  if ( v7 > v6 || v7 < a2 || *v7 == 92 )
  {
LABEL_15:
    v8 = *(_OWORD *)&TlmNoFileExtension;
LABEL_16:
    *(_OWORD *)a1 = v8;
  }
  else
  {
    *(_QWORD *)(a1 + 8) = v7;
    v9 = (_WORD)v6 - (_WORD)v7 + 2;
    *(_WORD *)a1 = v9;
    *(_WORD *)(a1 + 2) = v9;
  }
  return a1;
}

```

## disassembly

```asm
0x1800188f8  push    rbx
0x1800188fa  push    rbp
0x1800188fb  push    rsi
0x1800188fc  push    rdi
0x1800188fd  sub     rsp, 28h
0x180018901  xor     ebp, ebp
0x180018903  xorps   xmm0, xmm0
0x180018906  mov     rdi, rdx
0x180018909  mov     rbx, rcx
0x18001890c  movups  xmmword ptr [rcx], xmm0
0x18001890f  test    rdx, rdx
0x180018912  jz      short loc_18001898E
0x180018914  mov     edx, 8000h; MaxCount
0x180018919  mov     rcx, rdi; Source
0x18001891c  mov     esi, ebp
0x18001891e  call    cs:__imp_wcsnlen
0x180018924  cmp     [rdi+rax*2], bp
0x180018928  jnz     short loc_18001898E
0x18001892a  dec     rax
0x18001892d  lea     edx, [rbp+2]
0x180018930  lea     rcx, [rdi+rax*2]
0x180018934  mov     rax, rcx
0x180018937  cmp     rcx, rdi
0x18001893a  jb      short loc_18001896B
0x18001893c  cmp     word ptr [rax], 5Ch ; '\'
0x180018940  jz      short loc_180018959
0x180018942  cmp     si, 0Fh
0x180018946  ja      short loc_18001895F
0x180018948  cmp     word ptr [rax], 2Eh ; '.'
0x18001894c  jz      short loc_180018968
0x18001894e  inc     si
0x180018951  sub     rax, rdx
0x180018954  cmp     rax, rdi
0x180018957  jnb     short loc_18001893C
0x180018959  cmp     si, 0Fh
0x18001895d  jbe     short loc_18001896B
0x18001895f  movups  xmm0, xmmword ptr cs:TlmLongFileExtension; "\"$"
0x180018966  jmp     short loc_180018995
0x180018968  add     rax, rdx
0x18001896b  cmp     rax, rcx
0x18001896e  ja      short loc_18001898E
0x180018970  cmp     rax, rdi
0x180018973  jb      short loc_18001898E
0x180018975  cmp     word ptr [rax], 5Ch ; '\'
0x180018979  jz      short loc_18001898E
0x18001897b  sub     cx, ax
0x18001897e  mov     [rbx+8], rax
0x180018982  add     cx, dx
0x180018985  mov     [rbx], cx
0x180018988  mov     [rbx+2], cx
0x18001898c  jmp     short loc_180018999
0x18001898e  movups  xmm0, xmmword ptr cs:TlmNoFileExtension
0x180018995  movdqu  xmmword ptr [rbx], xmm0
0x180018999  mov     rax, rbx
0x18001899c  add     rsp, 28h
0x1800189a0  pop     rdi
0x1800189a1  pop     rsi
0x1800189a2  pop     rbp
0x1800189a3  pop     rbx
0x1800189a4  retn
```
