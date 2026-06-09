# archive_read_disk_open

- ea: `0x1800bdb40`
- end: `0x1800bdc44`
- name: `archive_read_disk_open`
- size: `260`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18000523c`
- `0x180006c00`
- `0x180011d60`
- `0x1800bd08c`
- `0x1800bdb40`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800bdbd8`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800bdbd8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800bdc32`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800bdc32`

## string_xrefs

- `0x1800bdb4c`: `archive_read_disk_open`
- `0x1800bdbe3`: `Can't convert a path to a wchar_t string`

## pseudocode

```c
__int64 __fastcall archive_read_disk_open(__int64 a1, __int64 a2)
{
  unsigned int disk_open_w; // edi
  __int64 v5; // r8
  __int64 v6; // rcx
  _DWORD *v7; // rax
  __int64 v8; // rdx
  const char *v9; // r8
  void *Block[2]; // [rsp+20h] [rbp-48h] BYREF
  __int64 v12; // [rsp+30h] [rbp-38h]

  v12 = 0;
  *(_OWORD *)Block = 0;
  disk_open_w = -30;
  if ( (unsigned int)_archive_check_magic(a1, 195932357, 33, "archive_read_disk_open") != -30 )
  {
    *(_QWORD *)(a1 + 56) = 0;
    v5 = -1;
    *(_QWORD *)(a1 + 40) = 0;
    *(_DWORD *)(a1 + 36) = 0;
    Block[0] = 0;
    Block[1] = 0;
    v12 = 0;
    do
      ++v5;
    while ( *(_BYTE *)(a2 + v5) );
    if ( (unsigned int)archive_wstring_append_from_mbs_in_codepage(Block, a2, v5, 0) )
    {
      v7 = (_DWORD *)_o__errno(v6);
      v8 = 12;
      v9 = "Can't allocate memory";
      if ( *v7 != 12 )
      {
        v9 = "Can't convert a path to a wchar_t string";
        v8 = 0xFFFFFFFFLL;
      }
      archive_set_error(a1, v8, v9);
      *(_DWORD *)(a1 + 4) = 0x8000;
    }
    else
    {
      disk_open_w = archive_read_disk_open_w(a1, Block[0]);
    }
    Block[1] = 0;
    v12 = 0;
    free(Block[0]);
  }
  return disk_open_w;
}

```

## disassembly

```asm
0x1800bdb40  push    rbx
0x1800bdb42  push    rsi
0x1800bdb43  push    rdi
0x1800bdb44  push    r14
0x1800bdb46  sub     rsp, 48h
0x1800bdb4a  xor     eax, eax
0x1800bdb4c  lea     r9, aArchiveReadDis_33; "archive_read_disk_open"
0x1800bdb53  mov     rsi, rdx
0x1800bdb56  mov     [rsp+68h+var_38], rax
0x1800bdb5b  xorps   xmm0, xmm0
0x1800bdb5e  mov     edx, 0BADB0C5h
0x1800bdb63  mov     rbx, rcx
0x1800bdb66  lea     r8d, [rax+21h]
0x1800bdb6a  movups  xmmword ptr [rsp+68h+Block], xmm0
0x1800bdb6f  call    __archive_check_magic
0x1800bdb74  mov     edi, 0FFFFFFE2h
0x1800bdb79  cmp     eax, edi
0x1800bdb7b  jz      loc_1800BDC38
0x1800bdb81  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800bdb85  mov     qword ptr [rbx+38h], 0
0x1800bdb8d  mov     r8, r14
0x1800bdb90  mov     qword ptr [rbx+28h], 0
0x1800bdb98  mov     dword ptr [rbx+24h], 0
0x1800bdb9f  mov     [rsp+68h+Block], 0
0x1800bdba8  mov     [rsp+68h+Block+8], 0
0x1800bdbb1  mov     [rsp+68h+var_38], 0
0x1800bdbba  inc     r8
0x1800bdbbd  cmp     byte ptr [rsi+r8], 0
0x1800bdbc2  jnz     short loc_1800BDBBA
0x1800bdbc4  xor     r9d, r9d
0x1800bdbc7  lea     rcx, [rsp+68h+Block]
0x1800bdbcc  mov     rdx, rsi
0x1800bdbcf  call    archive_wstring_append_from_mbs_in_codepage
0x1800bdbd4  test    eax, eax
0x1800bdbd6  jz      short loc_1800BDC0C
0x1800bdbd8  call    cs:__imp__o__errno
0x1800bdbde  mov     edx, 0Ch
0x1800bdbe3  lea     rcx, aCanTConvertAPa; "Can't convert a path to a wchar_t strin"...
0x1800bdbea  lea     r8, aCanTAllocateMe_30; "Can't allocate memory"
0x1800bdbf1  cmp     [rax], edx
0x1800bdbf3  cmovnz  r8, rcx
0x1800bdbf7  cmovnz  edx, r14d
0x1800bdbfb  mov     rcx, rbx
0x1800bdbfe  call    archive_set_error
0x1800bdc03  mov     dword ptr [rbx+4], 8000h
0x1800bdc0a  jmp     short loc_1800BDC1B
0x1800bdc0c  mov     rdx, [rsp+68h+Block]
0x1800bdc11  mov     rcx, rbx
0x1800bdc14  call    _archive_read_disk_open_w
0x1800bdc19  mov     edi, eax
0x1800bdc1b  mov     rcx, [rsp+68h+Block]; Block
0x1800bdc20  mov     [rsp+68h+Block+8], 0
0x1800bdc29  mov     [rsp+68h+var_38], 0
0x1800bdc32  call    cs:__imp_free
0x1800bdc38  mov     eax, edi
0x1800bdc3a  add     rsp, 48h
0x1800bdc3e  pop     r14
0x1800bdc40  pop     rdi
0x1800bdc41  pop     rsi
0x1800bdc42  pop     rbx
0x1800bdc43  retn
```
