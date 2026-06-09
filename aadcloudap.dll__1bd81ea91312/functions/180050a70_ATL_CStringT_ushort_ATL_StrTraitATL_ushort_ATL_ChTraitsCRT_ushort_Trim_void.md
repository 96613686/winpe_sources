# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Trim(void)

- ea: `0x180050a70`
- end: `0x180050b3b`
- name: `?Trim@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV12@XZ`
- size: `203`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x180050008`
- `0x180050170`
- `0x180053f88`
- `0x1800666f8`
- `0x18006ffc4`
- `0x18007b398`
- `0x180080930`

## callees

- `0x180006424`
- `0x180006768`
- `0x180006824`
- `0x180019dd4`
- `0x180050a70`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x180050b18`
- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x180050b18`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x180050a8e`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x180050ad7`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x180050a8e`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x180050ad7`

## pseudocode

```c
unsigned __int16 **__fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Trim(
        unsigned __int16 **a1)
{
  unsigned __int16 *v1; // rsi
  unsigned __int16 v3; // ax
  unsigned __int16 *v4; // rbx
  unsigned __int16 *v5; // rax
  unsigned __int16 *i; // rsi
  unsigned __int16 *v7; // rdx
  __int64 v8; // rsi
  char *v9; // rax
  unsigned int v10; // ebx
  errno_t v11; // eax

  v1 = *a1;
  v3 = **a1;
  if ( v3 )
  {
    v4 = 0;
    do
    {
      if ( (unsigned int)_o_iswspace(v3) )
      {
        v5 = v1;
        if ( v4 )
          v5 = v4;
        v4 = v5;
      }
      else
      {
        v4 = 0;
      }
      v3 = *++v1;
    }
    while ( *v1 );
    if ( v4 )
      ATL::CSimpleStringT<unsigned short,0>::Truncate(a1, (unsigned int)(v4 - *a1));
  }
  for ( i = *a1; (unsigned int)_o_iswspace(*i); ++i )
    ;
  v7 = *a1;
  if ( i != *a1 )
  {
    v8 = i - v7;
    v9 = (char *)ATL::CSimpleStringT<unsigned short,0>::PrepareWrite(a1, *((unsigned int *)v7 - 4));
    v10 = *((_DWORD *)*a1 - 4) - v8;
    v11 = memmove_s(v9, 2LL * (int)(v10 + 1), &v9[2 * (int)v8], 2LL * (int)(v10 + 1));
    ATL::AtlCrtErrorCheck(v11);
    ATL::CSimpleStringT<unsigned short,0>::SetLength(a1, v10);
  }
  return a1;
}

```

## disassembly

```asm
0x180050a70  push    rbx
0x180050a72  push    rbp
0x180050a73  push    rsi
0x180050a74  push    rdi
0x180050a75  sub     rsp, 28h
0x180050a79  mov     rsi, [rcx]
0x180050a7c  xor     ebp, ebp
0x180050a7e  mov     rdi, rcx
0x180050a81  movzx   eax, word ptr [rsi]
0x180050a84  test    ax, ax
0x180050a87  jz      short loc_180050ACB
0x180050a89  mov     ebx, ebp
0x180050a8b  movzx   ecx, ax
0x180050a8e  call    cs:__imp__o_iswspace
0x180050a94  test    eax, eax
0x180050a96  jz      short loc_180050AA7
0x180050a98  test    rbx, rbx
0x180050a9b  mov     rax, rsi
0x180050a9e  cmovnz  rax, rbx
0x180050aa2  mov     rbx, rax
0x180050aa5  jmp     short loc_180050AAA
0x180050aa7  mov     rbx, rbp
0x180050aaa  add     rsi, 2
0x180050aae  movzx   eax, word ptr [rsi]
0x180050ab1  test    ax, ax
0x180050ab4  jnz     short loc_180050A8B
0x180050ab6  test    rbx, rbx
0x180050ab9  jz      short loc_180050ACB
0x180050abb  sub     rbx, [rdi]
0x180050abe  mov     rcx, rdi
0x180050ac1  sar     rbx, 1
0x180050ac4  mov     edx, ebx
0x180050ac6  call    ?Truncate@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Truncate(int)
0x180050acb  mov     rsi, [rdi]
0x180050ace  jmp     short loc_180050AD4
0x180050ad0  add     rsi, 2
0x180050ad4  movzx   ecx, word ptr [rsi]
0x180050ad7  call    cs:__imp__o_iswspace
0x180050add  test    eax, eax
0x180050adf  jnz     short loc_180050AD0
0x180050ae1  mov     rdx, [rdi]
0x180050ae4  cmp     rsi, rdx
0x180050ae7  jz      short loc_180050B2F
0x180050ae9  sub     rsi, rdx
0x180050aec  mov     rcx, rdi
0x180050aef  mov     edx, [rdx-10h]
0x180050af2  sar     rsi, 1
0x180050af5  call    ?PrepareWrite@?$CSimpleStringT@G$0A@@ATL@@AEAAPEAGH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite(int)
0x180050afa  mov     rcx, [rdi]
0x180050afd  mov     ebx, [rcx-10h]
0x180050b00  sub     ebx, esi
0x180050b02  lea     ecx, [rbx+1]
0x180050b05  movsxd  rdx, ecx
0x180050b08  movsxd  rcx, esi
0x180050b0b  add     rdx, rdx; DestinationSize
0x180050b0e  mov     r9, rdx; SourceSize
0x180050b11  lea     r8, [rax+rcx*2]; Source
0x180050b15  mov     rcx, rax; Destination
0x180050b18  call    cs:__imp_memmove_s
0x180050b1e  mov     ecx, eax; int
0x180050b20  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180050b25  mov     edx, ebx
0x180050b27  mov     rcx, rdi
0x180050b2a  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x180050b2f  mov     rax, rdi
0x180050b32  add     rsp, 28h
0x180050b36  pop     rdi
0x180050b37  pop     rsi
0x180050b38  pop     rbp
0x180050b39  pop     rbx
0x180050b3a  retn
```
