# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::LoadStringW(HINSTANCE__ *,uint)

- ea: `0x18000b590`
- end: `0x18000b6e4`
- name: `?LoadStringW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEAUHINSTANCE__@@I@Z`
- size: `340`
- prototype: `__int64 __fastcall(void *const *, HMODULE, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b3e4`
- `0x18000b484`

## callees

- `0x180006a80`
- `0x18000b590`
- `0x18000b6ec`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000b671`
- `msvcrt!memcpy_s` at `0x18000b671`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18000b609`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18000b609`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18000b5df`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18000b5df`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18000b5c4`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18000b5c4`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x18000b5f1`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x18000b5f1`

## pseudocode

```c
__int64 __fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::LoadStringW(
        void *const *a1,
        HMODULE a2,
        unsigned int a3)
{
  char v3; // di
  HRSRC Resource; // rax
  HRSRC v7; // r14
  HGLOBAL v8; // rax
  unsigned __int16 *v9; // rbx
  unsigned __int16 *v10; // rcx
  int v11; // edi
  __int64 v12; // rdi
  errno_t v13; // eax

  v3 = a3;
  Resource = FindResourceExW(a2, (LPCWSTR)6, (LPCWSTR)(unsigned __int16)((a3 >> 4) + 1), 0);
  v7 = Resource;
  if ( !Resource )
    return 0;
  v8 = LoadResource(a2, Resource);
  if ( !v8 )
    return 0;
  v9 = (unsigned __int16 *)LockResource(v8);
  if ( !v9 )
    return 0;
  v10 = (unsigned __int16 *)((char *)v9 + SizeofResource(a2, v7));
  v11 = v3 & 0xF;
  if ( v11 )
  {
    while ( v9 < v10 )
    {
      v9 += *v9 + 1;
      if ( !--v11 )
        goto LABEL_7;
    }
    return 0;
  }
LABEL_7:
  if ( v9 >= v10 || !*v9 )
    return 0;
  v12 = *v9;
  if ( (int)((*((_DWORD *)*a1 - 3) - v12) | (1 - *((_DWORD *)*a1 - 2))) < 0 )
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, *v9);
  v13 = memcpy_s(*a1, 2 * v12, v9 + 1, 2LL * *v9);
  if ( v13 )
  {
    if ( v13 == 12 )
      ATL::AtlThrowImpl(-2147024882);
    if ( v13 == 22 || v13 == 34 )
      ATL::AtlThrowImpl(-2147024809);
    if ( v13 != 80 )
      ATL::AtlThrowImpl(-2147467259);
  }
  if ( (int)v12 > *((_DWORD *)*a1 - 3) )
    ATL::AtlThrowImpl(-2147024809);
  *((_DWORD *)*a1 - 4) = v12;
  *((_WORD *)*a1 + v12) = 0;
  return 1;
}

```

## disassembly

```asm
0x18000b590  push    rbx
0x18000b592  push    rbp
0x18000b593  push    rsi
0x18000b594  push    rdi
0x18000b595  push    r12
0x18000b597  push    r14
0x18000b599  push    r15
0x18000b59b  sub     rsp, 20h
0x18000b59f  mov     edi, r8d
0x18000b5a2  mov     rbp, rdx
0x18000b5a5  mov     rsi, rcx
0x18000b5a8  xor     r9d, r9d; wLanguage
0x18000b5ab  mov     eax, r8d
0x18000b5ae  shr     eax, 4
0x18000b5b1  lea     r12d, [r9+1]
0x18000b5b5  add     ax, r12w
0x18000b5b9  movzx   r8d, ax; lpName
0x18000b5bd  lea     edx, [r9+6]; lpType
0x18000b5c1  mov     rcx, rbp; hModule
0x18000b5c4  call    cs:__imp_FindResourceExW
0x18000b5ca  mov     r14, rax
0x18000b5cd  xor     r15d, r15d
0x18000b5d0  test    rax, rax
0x18000b5d3  jz      loc_18000B6A7
0x18000b5d9  mov     rdx, rax; hResInfo
0x18000b5dc  mov     rcx, rbp; hModule
0x18000b5df  call    cs:__imp_LoadResource
0x18000b5e5  test    rax, rax
0x18000b5e8  jz      loc_18000B6A7
0x18000b5ee  mov     rcx, rax; hResData
0x18000b5f1  call    cs:__imp_LockResource
0x18000b5f7  mov     rbx, rax
0x18000b5fa  test    rax, rax
0x18000b5fd  jz      loc_18000B6A7
0x18000b603  mov     rdx, r14; hResInfo
0x18000b606  mov     rcx, rbp; hModule
0x18000b609  call    cs:__imp_SizeofResource
0x18000b60f  mov     ecx, eax
0x18000b611  add     rcx, rbx
0x18000b614  and     edi, 0Fh
0x18000b617  jbe     short loc_18000B632
0x18000b619  cmp     rbx, rcx
0x18000b61c  jnb     loc_18000B6A7
0x18000b622  movzx   eax, word ptr [rbx]
0x18000b625  lea     rbx, [rbx+rax*2]
0x18000b629  add     rbx, 2
0x18000b62d  add     edi, 0FFFFFFFFh
0x18000b630  jnz     short loc_18000B619
0x18000b632  cmp     rbx, rcx
0x18000b635  jnb     short loc_18000B6A7
0x18000b637  cmp     [rbx], r15w
0x18000b63b  jz      short loc_18000B6A7
0x18000b63d  movzx   edi, word ptr [rbx]
0x18000b640  mov     rax, [rsi]
0x18000b643  mov     edx, r12d
0x18000b646  sub     edx, [rax-8]
0x18000b649  mov     ecx, [rax-0Ch]
0x18000b64c  sub     ecx, edi
0x18000b64e  or      edx, ecx
0x18000b650  jge     short loc_18000B65C
0x18000b652  mov     edx, edi
0x18000b654  mov     rcx, rsi
0x18000b657  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x18000b65c  lea     r8, [rbx+2]; Source
0x18000b660  lea     r14, [rdi+rdi]
0x18000b664  movzx   r9d, word ptr [rbx]
0x18000b668  add     r9, r9; SourceSize
0x18000b66b  mov     rdx, r14; DestinationSize
0x18000b66e  mov     rcx, [rsi]; Destination
0x18000b671  call    cs:__imp_memcpy_s
0x18000b677  test    eax, eax
0x18000b679  jz      short loc_18000B68F
0x18000b67b  cmp     eax, 0Ch
0x18000b67e  jz      short loc_18000B6D9
0x18000b680  cmp     eax, 16h
0x18000b683  jz      short loc_18000B6CE
0x18000b685  cmp     eax, 22h ; '"'
0x18000b688  jz      short loc_18000B6CE
0x18000b68a  cmp     eax, 50h ; 'P'
0x18000b68d  jnz     short loc_18000B6C3
0x18000b68f  mov     rcx, [rsi]
0x18000b692  cmp     edi, [rcx-0Ch]
0x18000b695  jg      short loc_18000B6B8
0x18000b697  mov     [rcx-10h], edi
0x18000b69a  mov     rdx, [rsi]
0x18000b69d  mov     [r14+rdx], r15w
0x18000b6a2  mov     eax, r12d
0x18000b6a5  jmp     short loc_18000B6A9
0x18000b6a7  xor     eax, eax
0x18000b6a9  add     rsp, 20h
0x18000b6ad  pop     r15
0x18000b6af  pop     r14
0x18000b6b1  pop     r12
0x18000b6b3  pop     rdi
0x18000b6b4  pop     rsi
0x18000b6b5  pop     rbp
0x18000b6b6  pop     rbx
0x18000b6b7  retn
0x18000b6b8  mov     ecx, 80070057h; int
0x18000b6bd  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000b6c3  mov     ecx, 80004005h; int
0x18000b6c8  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000b6ce  mov     ecx, 80070057h; int
0x18000b6d3  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000b6d9  mov     ecx, 8007000Eh; int
0x18000b6de  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
