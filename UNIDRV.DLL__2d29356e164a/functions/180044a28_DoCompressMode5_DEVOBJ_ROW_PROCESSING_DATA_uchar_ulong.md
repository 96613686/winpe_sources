# DoCompressMode5(_DEVOBJ *,_ROW_PROCESSING_DATA *,uchar *,ulong)

- ea: `0x180044a28`
- end: `0x180044b61`
- name: `?DoCompressMode5@@YAPEAEPEAU_DEVOBJ@@PEAU_ROW_PROCESSING_DATA@@PEAEK@Z`
- size: `313`
- prototype: `unsigned __int8 *(struct _DEVOBJ *, struct _ROW_PROCESSING_DATA *, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180032870`

## callees

- `0x180032eac`
- `0x180044a28`
- `0x180044b68`
- `0x18006a2a8`
- `0x18006a37c`
- `0x18006a3e0`
- `0x18006a4b0`
- `0x180074580`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180044b50`
- `KERNEL32!SetLastError` at `0x180044b50`

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
  unsigned int v10; // eax
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
    v12 = &v5[FlushRowCount(v5, a2, 0)];
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
0x180044a28  push    rbx
0x180044a2a  push    rbp
0x180044a2b  push    rsi
0x180044a2c  push    rdi
0x180044a2d  sub     rsp, 28h
0x180044a31  mov     ebx, r9d
0x180044a34  mov     rsi, r8
0x180044a37  mov     rdi, rdx
0x180044a3a  mov     rbp, rcx
0x180044a3d  test    rdx, rdx
0x180044a40  jz      loc_180044B4B
0x180044a46  test    r8, r8
0x180044a49  jz      loc_180044B4B
0x180044a4f  mov     rcx, rdx; struct _ROW_PROCESSING_DATA *
0x180044a52  mov     dword ptr [rdx+38h], 0
0x180044a59  call    ?IsEmptyRow@@YAHPEAU_ROW_PROCESSING_DATA@@@Z; IsEmptyRow(_ROW_PROCESSING_DATA *)
0x180044a5e  test    eax, eax
0x180044a60  jnz     short loc_180044A79
0x180044a62  call    ?IsRepeatRow@@YAHPEAU_ROW_PROCESSING_DATA@@@Z; IsRepeatRow(_ROW_PROCESSING_DATA *)
0x180044a67  test    eax, eax
0x180044a69  jnz     short loc_180044A79
0x180044a6b  lea     r8d, [rax+1]; int
0x180044a6f  mov     edx, ebx; unsigned int
0x180044a71  mov     rcx, rdi; struct _ROW_PROCESSING_DATA *
0x180044a74  call    ?DoCompression@@YAXPEAU_ROW_PROCESSING_DATA@@KH@Z; DoCompression(_ROW_PROCESSING_DATA *,ulong,int)
0x180044a79  cmp     dword ptr [rdi+58h], 4
0x180044a7d  jz      short loc_180044A8A
0x180044a7f  cmp     dword ptr [rdi+58h], 5
0x180044a83  mov     ecx, 3
0x180044a88  jnz     short loc_180044A8F
0x180044a8a  mov     ecx, 6
0x180044a8f  mov     eax, [rdi+38h]
0x180044a92  sub     eax, 4
0x180044a95  cmp     eax, 1
0x180044a98  jbe     short loc_180044A9D
0x180044a9a  add     ecx, [rdi+40h]
0x180044a9d  mov     eax, esi
0x180044a9f  sub     eax, [rdi+30h]
0x180044aa2  add     eax, ecx
0x180044aa4  cmp     eax, 7FFFh
0x180044aa9  jbe     short loc_180044AF4
0x180044aab  xor     r8d, r8d; int
0x180044aae  mov     rdx, rdi; struct _ROW_PROCESSING_DATA *
0x180044ab1  mov     rcx, rsi; unsigned __int8 *
0x180044ab4  call    ?FlushRowCount@@YAKPEAEPEAU_ROW_PROCESSING_DATA@@H@Z; FlushRowCount(uchar *,_ROW_PROCESSING_DATA *,int)
0x180044ab9  mov     r8d, eax
0x180044abc  mov     rcx, rbp; struct _DEVOBJ *
0x180044abf  add     r8, rsi
0x180044ac2  sub     r8d, [rdi+30h]; unsigned int
0x180044ac6  call    ?VSendMode5Block@@YAXPEAU_DEVOBJ@@PEAU_ROW_PROCESSING_DATA@@K@Z; VSendMode5Block(_DEVOBJ *,_ROW_PROCESSING_DATA *,ulong)
0x180044acb  cmp     dword ptr [rdi+38h], 5
0x180044acf  mov     rsi, [rdi+30h]
0x180044ad3  jnz     short loc_180044AE4
0x180044ad5  xor     r8d, r8d; int
0x180044ad8  mov     edx, ebx; unsigned int
0x180044ada  mov     rcx, rdi; struct _ROW_PROCESSING_DATA *
0x180044add  call    ?DoCompression@@YAXPEAU_ROW_PROCESSING_DATA@@KH@Z; DoCompression(_ROW_PROCESSING_DATA *,ulong,int)
0x180044ae2  jmp     short loc_180044AF4
0x180044ae4  cmp     dword ptr [rdi+38h], 3
0x180044ae8  jnz     short loc_180044AF4
0x180044aea  xor     edx, edx; int
0x180044aec  mov     rcx, rdi; struct _ROW_PROCESSING_DATA *
0x180044aef  call    ?SelectBestCompression@@YAXPEAU_ROW_PROCESSING_DATA@@H@Z; SelectBestCompression(_ROW_PROCESSING_DATA *,int)
0x180044af4  xor     r8d, r8d; int
0x180044af7  mov     rdx, rdi; struct _ROW_PROCESSING_DATA *
0x180044afa  mov     rcx, rsi; unsigned __int8 *
0x180044afd  call    ?FlushRowCount@@YAKPEAEPEAU_ROW_PROCESSING_DATA@@H@Z; FlushRowCount(uchar *,_ROW_PROCESSING_DATA *,int)
0x180044b02  mov     edx, eax
0x180044b04  mov     eax, [rdi+38h]
0x180044b07  add     rsi, rdx
0x180044b0a  sub     eax, 4
0x180044b0d  cmp     eax, 1
0x180044b10  jbe     short loc_180044B40
0x180044b12  mov     al, [rdi+38h]
0x180044b15  lea     rbx, [rsi+3]
0x180044b19  mov     [rsi], al
0x180044b1b  mov     rcx, rbx; void *
0x180044b1e  mov     eax, [rdi+40h]
0x180044b21  shr     eax, 8
0x180044b24  mov     [rsi+1], al
0x180044b27  mov     al, [rdi+40h]
0x180044b2a  mov     [rsi+2], al
0x180044b2d  mov     r8d, [rdi+40h]; Size
0x180044b31  mov     rdx, [rdi+28h]; Src
0x180044b35  call    memcpy_0
0x180044b3a  mov     esi, [rdi+40h]
0x180044b3d  add     rsi, rbx
0x180044b40  mov     eax, [rdi+38h]
0x180044b43  mov     [rdi+58h], eax
0x180044b46  mov     rax, rsi
0x180044b49  jmp     short loc_180044B58
0x180044b4b  mov     ecx, 0Dh; dwErrCode
0x180044b50  call    cs:__imp_SetLastError
0x180044b56  xor     eax, eax
0x180044b58  add     rsp, 28h
0x180044b5c  pop     rdi
0x180044b5d  pop     rsi
0x180044b5e  pop     rbp
0x180044b5f  pop     rbx
0x180044b60  retn
```
