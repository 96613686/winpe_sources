# ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)

- ea: `0x18001855c`
- end: `0x1800185f2`
- name: `?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z`
- size: `150`
- prototype: ``
- caller_count: `12`
- callee_count: `5`
- tags: ``

## callers

- `0x180004310`
- `0x180004374`
- `0x18002053c`
- `0x180020edc`
- `0x180021144`
- `0x180021750`
- `0x1800218bc`
- `0x180021938`
- `0x1800229ec`
- `0x180023090`
- `0x180028b64`
- `0x180029e88`

## callees

- `0x18000546c`
- `0x180005c80`
- `0x180014880`
- `0x180018524`
- `0x18001855c`

## import_xrefs

- `msvcrt!memmove_s` at `0x1800185cc`
- `msvcrt!memmove_s` at `0x1800185cc`
- `msvcrt!memcpy_s` at `0x1800185d7`
- `msvcrt!memcpy_s` at `0x1800185d7`

## pseudocode

```c
__int64 __fastcall ATL::CSimpleStringT<unsigned short,0>::SetString(char **a1, _BYTE *a2, unsigned int a3)
{
  __int64 v3; // rdi
  unsigned __int64 v7; // rsi
  unsigned __int64 v8; // r14
  char *v9; // rcx
  rsize_t v10; // rdx
  rsize_t v11; // r9

  v3 = (int)a3;
  if ( !a3 )
    return ATL::CSimpleStringT<unsigned short,0>::Empty();
  if ( !a2 )
    ATL::AtlThrowImpl(-2147024809);
  v7 = (a2 - *a1) >> 1;
  v8 = *((unsigned int *)*a1 - 4);
  if ( (((*((_DWORD *)*a1 - 3) - a3) | (1 - *((_DWORD *)*a1 - 2))) & 0x80000000) != 0 )
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, a3);
  v9 = *a1;
  v10 = 2 * v3;
  v11 = 2 * v3;
  if ( v7 > v8 )
    memcpy_s(v9, v10, a2, v11);
  else
    memmove_s(v9, v10, &v9[2 * v7], v11);
  return ATL::CSimpleStringT<unsigned short,0>::SetLength(a1, (unsigned int)v3);
}

```

## disassembly

```asm
0x18001855c  push    rbx
0x18001855e  push    rbp
0x18001855f  push    rsi
0x180018560  push    rdi
0x180018561  push    r14
0x180018563  sub     rsp, 20h
0x180018567  movsxd  rdi, r8d
0x18001856a  mov     rbp, rdx
0x18001856d  mov     rbx, rcx
0x180018570  test    r8d, r8d
0x180018573  jnz     short loc_18001857C
0x180018575  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x18001857a  jmp     short loc_1800185E7
0x18001857c  test    rbp, rbp
0x18001857f  jnz     short loc_18001858C
0x180018581  mov     ecx, 80070057h; int
0x180018586  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001858c  mov     rax, [rcx]
0x18001858f  mov     rsi, rbp
0x180018592  sub     rsi, rax
0x180018595  mov     ecx, 1
0x18001859a  sar     rsi, 1
0x18001859d  sub     ecx, [rax-8]
0x1800185a0  mov     r14d, [rax-10h]
0x1800185a4  mov     eax, [rax-0Ch]
0x1800185a7  sub     eax, edi
0x1800185a9  or      ecx, eax
0x1800185ab  jge     short loc_1800185B7
0x1800185ad  mov     edx, edi
0x1800185af  mov     rcx, rbx
0x1800185b2  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x1800185b7  mov     rcx, [rbx]; Destination
0x1800185ba  mov     rdx, rdi
0x1800185bd  add     rdx, rdx; DestinationSize
0x1800185c0  mov     r9, rdx; SourceSize
0x1800185c3  cmp     rsi, r14
0x1800185c6  ja      short loc_1800185D4
0x1800185c8  lea     r8, [rcx+rsi*2]; Source
0x1800185cc  call    cs:__imp_memmove_s
0x1800185d2  jmp     short loc_1800185DD
0x1800185d4  mov     r8, rbp; Source
0x1800185d7  call    cs:__imp_memcpy_s
0x1800185dd  mov     edx, edi
0x1800185df  mov     rcx, rbx
0x1800185e2  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x1800185e7  add     rsp, 20h
0x1800185eb  pop     r14
0x1800185ed  pop     rdi
0x1800185ee  pop     rsi
0x1800185ef  pop     rbp
0x1800185f0  pop     rbx
0x1800185f1  retn
```
