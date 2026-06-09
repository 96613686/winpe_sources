# DoCompressMode5(_DEVOBJ *,_ROW_PROCESSING_DATA *,uchar *,ulong)

- ea: `0x180045d04`
- end: `0x180045e44`
- name: `?DoCompressMode5@@YAPEAEPEAU_DEVOBJ@@PEAU_ROW_PROCESSING_DATA@@PEAEK@Z`
- size: `320`
- prototype: `unsigned __int8 *__fastcall(struct _DEVOBJ *, struct _ROW_PROCESSING_DATA *, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180033198`

## callees

- `0x180033830`
- `0x180045d04`
- `0x180045e4c`
- `0x18006bbc0`
- `0x18006bc98`
- `0x18006bcfc`
- `0x18006bdf8`
- `0x180076660`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180045e2c`
- `KERNEL32!SetLastError` at `0x180045e2c`

## pseudocode

```c
unsigned __int8 *__fastcall DoCompressMode5(
        struct _DEVOBJ *a1,
        struct _ROW_PROCESSING_DATA *a2,
        unsigned __int8 *a3,
        unsigned int a4)
{
  unsigned __int8 *v5; // rsi
  struct _ROW_PROCESSING_DATA *v8; // rcx
  int v9; // ecx
  int v10; // eax
  struct _ROW_PROCESSING_DATA *v11; // rdx
  unsigned __int8 *v12; // rsi

  v5 = a3;
  if ( a2 && a3 )
  {
    *((_DWORD *)a2 + 14) = 0;
    if ( !(unsigned int)IsEmptyRow(a2) && !(unsigned int)IsRepeatRow(v8) )
      DoCompression(a2, a4, 1);
    if ( *((_DWORD *)a2 + 22) == 4 || (v9 = 3, *((_DWORD *)a2 + 22) == 5) )
      v9 = 6;
    if ( (unsigned int)(*((_DWORD *)a2 + 14) - 4) > 1 )
      v9 += *((_DWORD *)a2 + 16);
    if ( (unsigned int)(v9 + (_DWORD)v5 - *((_DWORD *)a2 + 12)) > 0x7FFF )
    {
      v10 = FlushRowCount(v5, a2, 0);
      VSendMode5Block(a1, v11, (_DWORD)v5 + v10 - *((_DWORD *)a2 + 12));
      v5 = (unsigned __int8 *)*((_QWORD *)a2 + 6);
      if ( *((_DWORD *)a2 + 14) == 5 )
      {
        DoCompression(a2, a4, 0);
      }
      else if ( *((_DWORD *)a2 + 14) == 3 )
      {
        SelectBestCompression(a2, 0);
      }
    }
    v12 = &v5[(unsigned int)FlushRowCount(v5, a2, 0)];
    if ( (unsigned int)(*((_DWORD *)a2 + 14) - 4) > 1 )
    {
      *v12 = *((_BYTE *)a2 + 56);
      v12[1] = BYTE1(*((_DWORD *)a2 + 16));
      v12[2] = *((_BYTE *)a2 + 64);
      memcpy_0(v12 + 3, *((const void **)a2 + 5), *((unsigned int *)a2 + 16));
      v12 += *((unsigned int *)a2 + 16) + 3;
    }
    *((_DWORD *)a2 + 22) = *((_DWORD *)a2 + 14);
    return v12;
  }
  else
  {
    SetLastError(0xDu);
    return 0;
  }
}

```

## disassembly

```asm
0x180045d04  push    rbx
0x180045d06  push    rbp
0x180045d07  push    rsi
0x180045d08  push    rdi
0x180045d09  sub     rsp, 28h
0x180045d0d  mov     ebx, r9d
0x180045d10  mov     rsi, r8
0x180045d13  mov     rdi, rdx
0x180045d16  mov     rbp, rcx
0x180045d19  test    rdx, rdx
0x180045d1c  jz      loc_180045E27
0x180045d22  test    r8, r8
0x180045d25  jz      loc_180045E27
0x180045d2b  mov     rcx, rdx; struct _ROW_PROCESSING_DATA *
0x180045d2e  mov     dword ptr [rdx+38h], 0
0x180045d35  call    ?IsEmptyRow@@YAHPEAU_ROW_PROCESSING_DATA@@@Z; IsEmptyRow(_ROW_PROCESSING_DATA *)
0x180045d3a  test    eax, eax
0x180045d3c  jnz     short loc_180045D55
0x180045d3e  call    ?IsRepeatRow@@YAHPEAU_ROW_PROCESSING_DATA@@@Z; IsRepeatRow(_ROW_PROCESSING_DATA *)
0x180045d43  test    eax, eax
0x180045d45  jnz     short loc_180045D55
0x180045d47  lea     r8d, [rax+1]; int
0x180045d4b  mov     edx, ebx; unsigned int
0x180045d4d  mov     rcx, rdi; struct _ROW_PROCESSING_DATA *
0x180045d50  call    ?DoCompression@@YAXPEAU_ROW_PROCESSING_DATA@@KH@Z; DoCompression(_ROW_PROCESSING_DATA *,ulong,int)
0x180045d55  cmp     dword ptr [rdi+58h], 4
0x180045d59  jz      short loc_180045D66
0x180045d5b  cmp     dword ptr [rdi+58h], 5
0x180045d5f  mov     ecx, 3
0x180045d64  jnz     short loc_180045D6B
0x180045d66  mov     ecx, 6
0x180045d6b  mov     eax, [rdi+38h]
0x180045d6e  sub     eax, 4
0x180045d71  cmp     eax, 1
0x180045d74  jbe     short loc_180045D79
0x180045d76  add     ecx, [rdi+40h]
0x180045d79  mov     eax, esi
0x180045d7b  sub     eax, [rdi+30h]
0x180045d7e  add     eax, ecx
0x180045d80  cmp     eax, 7FFFh
0x180045d85  jbe     short loc_180045DD0
0x180045d87  xor     r8d, r8d; int
0x180045d8a  mov     rdx, rdi; struct _ROW_PROCESSING_DATA *
0x180045d8d  mov     rcx, rsi; unsigned __int8 *
0x180045d90  call    ?FlushRowCount@@YAKPEAEPEAU_ROW_PROCESSING_DATA@@H@Z; FlushRowCount(uchar *,_ROW_PROCESSING_DATA *,int)
0x180045d95  mov     r8d, eax
0x180045d98  mov     rcx, rbp; struct _DEVOBJ *
0x180045d9b  add     r8, rsi
0x180045d9e  sub     r8d, [rdi+30h]; unsigned int
0x180045da2  call    ?VSendMode5Block@@YAXPEAU_DEVOBJ@@PEAU_ROW_PROCESSING_DATA@@K@Z; VSendMode5Block(_DEVOBJ *,_ROW_PROCESSING_DATA *,ulong)
0x180045da7  cmp     dword ptr [rdi+38h], 5
0x180045dab  mov     rsi, [rdi+30h]
0x180045daf  jnz     short loc_180045DC0
0x180045db1  xor     r8d, r8d; int
0x180045db4  mov     edx, ebx; unsigned int
0x180045db6  mov     rcx, rdi; struct _ROW_PROCESSING_DATA *
0x180045db9  call    ?DoCompression@@YAXPEAU_ROW_PROCESSING_DATA@@KH@Z; DoCompression(_ROW_PROCESSING_DATA *,ulong,int)
0x180045dbe  jmp     short loc_180045DD0
0x180045dc0  cmp     dword ptr [rdi+38h], 3
0x180045dc4  jnz     short loc_180045DD0
0x180045dc6  xor     edx, edx; int
0x180045dc8  mov     rcx, rdi; struct _ROW_PROCESSING_DATA *
0x180045dcb  call    ?SelectBestCompression@@YAXPEAU_ROW_PROCESSING_DATA@@H@Z; SelectBestCompression(_ROW_PROCESSING_DATA *,int)
0x180045dd0  xor     r8d, r8d; int
0x180045dd3  mov     rdx, rdi; struct _ROW_PROCESSING_DATA *
0x180045dd6  mov     rcx, rsi; unsigned __int8 *
0x180045dd9  call    ?FlushRowCount@@YAKPEAEPEAU_ROW_PROCESSING_DATA@@H@Z; FlushRowCount(uchar *,_ROW_PROCESSING_DATA *,int)
0x180045dde  mov     edx, eax
0x180045de0  mov     eax, [rdi+38h]
0x180045de3  add     rsi, rdx
0x180045de6  sub     eax, 4
0x180045de9  cmp     eax, 1
0x180045dec  jbe     short loc_180045E1C
0x180045dee  mov     al, [rdi+38h]
0x180045df1  lea     rbx, [rsi+3]
0x180045df5  mov     [rsi], al
0x180045df7  mov     rcx, rbx; void *
0x180045dfa  mov     eax, [rdi+40h]
0x180045dfd  shr     eax, 8
0x180045e00  mov     [rsi+1], al
0x180045e03  mov     al, [rdi+40h]
0x180045e06  mov     [rsi+2], al
0x180045e09  mov     r8d, [rdi+40h]; Size
0x180045e0d  mov     rdx, [rdi+28h]; Src
0x180045e11  call    memcpy_0
0x180045e16  mov     esi, [rdi+40h]
0x180045e19  add     rsi, rbx
0x180045e1c  mov     eax, [rdi+38h]
0x180045e1f  mov     [rdi+58h], eax
0x180045e22  mov     rax, rsi
0x180045e25  jmp     short loc_180045E3A
0x180045e27  mov     ecx, 0Dh; dwErrCode
0x180045e2c  call    cs:__imp_SetLastError
0x180045e33  nop     dword ptr [rax+rax+00h]
0x180045e38  xor     eax, eax
0x180045e3a  add     rsp, 28h
0x180045e3e  pop     rdi
0x180045e3f  pop     rsi
0x180045e40  pop     rbp
0x180045e41  pop     rbx
0x180045e42  retn
```
