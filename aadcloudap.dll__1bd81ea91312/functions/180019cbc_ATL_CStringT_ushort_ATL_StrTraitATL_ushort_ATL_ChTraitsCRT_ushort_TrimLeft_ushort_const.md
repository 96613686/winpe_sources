# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::TrimLeft(ushort const *)

- ea: `0x180019cbc`
- end: `0x180019d53`
- name: `?TrimLeft@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV12@PEBG@Z`
- size: `151`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180019c98`
- `0x18004b3c8`

## callees

- `0x180006424`
- `0x180006768`
- `0x180006824`
- `0x180019cbc`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x180019d30`
- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x180019d30`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180019ce2`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180019ce2`

## pseudocode

```c
wchar_t **__fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::TrimLeft(
        wchar_t **a1,
        const wchar_t *a2)
{
  wchar_t *i; // rdi
  wchar_t *v5; // rdx
  __int64 v6; // rdi
  char *v7; // rax
  unsigned int v8; // ebx
  errno_t v9; // eax

  if ( a2 && *a2 )
  {
    for ( i = *a1; *i && wcschr(a2, *i); ++i )
      ;
    v5 = *a1;
    if ( i != *a1 )
    {
      v6 = i - v5;
      v7 = (char *)ATL::CSimpleStringT<unsigned short,0>::PrepareWrite(a1, *((unsigned int *)v5 - 4));
      v8 = *((_DWORD *)*a1 - 4) - v6;
      v9 = memmove_s(v7, 2LL * (int)(v8 + 1), &v7[2 * (int)v6], 2LL * (int)(v8 + 1));
      ATL::AtlCrtErrorCheck(v9);
      ATL::CSimpleStringT<unsigned short,0>::SetLength(a1, v8);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180019cbc  push    rbx
0x180019cbe  push    rbp
0x180019cbf  push    rsi
0x180019cc0  push    rdi
0x180019cc1  sub     rsp, 28h
0x180019cc5  xor     ebp, ebp
0x180019cc7  mov     rbx, rdx
0x180019cca  mov     rsi, rcx
0x180019ccd  test    rdx, rdx
0x180019cd0  jz      short loc_180019D47
0x180019cd2  cmp     [rdx], bp
0x180019cd5  jz      short loc_180019D47
0x180019cd7  mov     rdi, [rcx]
0x180019cda  jmp     short loc_180019CF1
0x180019cdc  movzx   edx, ax; Ch
0x180019cdf  mov     rcx, rbx; Str
0x180019ce2  call    cs:__imp_wcschr
0x180019ce8  test    rax, rax
0x180019ceb  jz      short loc_180019CF9
0x180019ced  add     rdi, 2
0x180019cf1  movzx   eax, word ptr [rdi]
0x180019cf4  test    ax, ax
0x180019cf7  jnz     short loc_180019CDC
0x180019cf9  mov     rdx, [rsi]
0x180019cfc  cmp     rdi, rdx
0x180019cff  jz      short loc_180019D47
0x180019d01  sub     rdi, rdx
0x180019d04  mov     rcx, rsi
0x180019d07  mov     edx, [rdx-10h]
0x180019d0a  sar     rdi, 1
0x180019d0d  call    ?PrepareWrite@?$CSimpleStringT@G$0A@@ATL@@AEAAPEAGH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite(int)
0x180019d12  mov     rcx, [rsi]
0x180019d15  mov     ebx, [rcx-10h]
0x180019d18  sub     ebx, edi
0x180019d1a  lea     ecx, [rbx+1]
0x180019d1d  movsxd  rdx, ecx
0x180019d20  movsxd  rcx, edi
0x180019d23  add     rdx, rdx; DestinationSize
0x180019d26  mov     r9, rdx; SourceSize
0x180019d29  lea     r8, [rax+rcx*2]; Source
0x180019d2d  mov     rcx, rax; Destination
0x180019d30  call    cs:__imp_memmove_s
0x180019d36  mov     ecx, eax; int
0x180019d38  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180019d3d  mov     edx, ebx
0x180019d3f  mov     rcx, rsi
0x180019d42  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x180019d47  mov     rax, rsi
0x180019d4a  add     rsp, 28h
0x180019d4e  pop     rdi
0x180019d4f  pop     rsi
0x180019d50  pop     rbp
0x180019d51  pop     rbx
0x180019d52  retn
```
