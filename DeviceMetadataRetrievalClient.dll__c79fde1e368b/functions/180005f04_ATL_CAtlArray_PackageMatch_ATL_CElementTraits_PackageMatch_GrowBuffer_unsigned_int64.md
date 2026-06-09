# ATL::CAtlArray<PackageMatch,ATL::CElementTraits<PackageMatch>>::GrowBuffer(unsigned __int64)

- ea: `0x180005f04`
- end: `0x180005ffe`
- name: `?GrowBuffer@?$CAtlArray@UPackageMatch@@V?$CElementTraits@UPackageMatch@@@ATL@@@ATL@@AEAA_N_K@Z`
- size: `250`
- prototype: `char __fastcall(__int64, size_t)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005a38`

## callees

- `0x180005170`
- `0x180005f04`

## import_xrefs

- `msvcrt!memmove_s` at `0x180005f9d`
- `msvcrt!memmove_s` at `0x180005f9d`
- `msvcrt!calloc` at `0x180005f3f`
- `msvcrt!calloc` at `0x180005f7a`
- `msvcrt!calloc` at `0x180005f3f`
- `msvcrt!calloc` at `0x180005f7a`
- `msvcrt!free` at `0x180005fbe`
- `msvcrt!free` at `0x180005fbe`

## pseudocode

```c
char __fastcall ATL::CAtlArray<PackageMatch,ATL::CElementTraits<PackageMatch>>::GrowBuffer(__int64 a1, size_t a2)
{
  size_t v4; // rdx
  size_t v5; // rcx
  void *v6; // rax
  void *v7; // rax
  void *v8; // rsi
  errno_t v10; // eax

  v4 = *(_QWORD *)(a1 + 16);
  if ( a2 <= v4 )
    return 1;
  v5 = *(int *)(a1 + 24);
  if ( *(_QWORD *)a1 )
  {
    if ( !v5 )
    {
      v5 = v4 >> 1;
      if ( a2 - v4 > v4 >> 1 )
        v5 = a2 - v4;
    }
    if ( a2 < v4 + v5 )
      a2 = v4 + v5;
    v7 = calloc(a2, 0x40u);
    v8 = v7;
    if ( v7 )
    {
      v10 = memmove_s(v7, *(_QWORD *)(a1 + 8) << 6, *(const void *const *)a1, *(_QWORD *)(a1 + 8) << 6);
      if ( v10 )
      {
        if ( v10 == 12 )
          ATL::AtlThrowImpl(-2147024882);
        if ( v10 == 22 || v10 == 34 )
          ATL::AtlThrowImpl(-2147024809);
        if ( v10 != 80 )
          ATL::AtlThrowImpl(-2147467259);
      }
      free(*(void **)a1);
      *(_QWORD *)a1 = v8;
      goto LABEL_20;
    }
    return 0;
  }
  if ( v5 > a2 )
    a2 = v5;
  v6 = calloc(a2, 0x40u);
  *(_QWORD *)a1 = v6;
  if ( !v6 )
    return 0;
LABEL_20:
  *(_QWORD *)(a1 + 16) = a2;
  return 1;
}

```

## disassembly

```asm
0x180005f04  mov     [rsp+arg_0], rbx
0x180005f09  mov     [rsp+arg_8], rsi
0x180005f0e  push    rdi
0x180005f0f  sub     rsp, 20h
0x180005f13  mov     rdi, rdx
0x180005f16  mov     rbx, rcx
0x180005f19  mov     rdx, [rcx+10h]
0x180005f1d  cmp     rdi, rdx
0x180005f20  jbe     loc_180005FCB
0x180005f26  cmp     qword ptr [rbx], 0
0x180005f2a  movsxd  rcx, dword ptr [rcx+18h]
0x180005f2e  jnz     short loc_180005F4F
0x180005f30  cmp     rcx, rdi
0x180005f33  mov     edx, 40h ; '@'; Size
0x180005f38  cmova   rdi, rcx
0x180005f3c  mov     rcx, rdi; Count
0x180005f3f  call    cs:__imp_calloc
0x180005f45  mov     [rbx], rax
0x180005f48  test    rax, rax
0x180005f4b  jz      short loc_180005F88
0x180005f4d  jmp     short loc_180005FC7
0x180005f4f  test    rcx, rcx
0x180005f52  jnz     short loc_180005F67
0x180005f54  mov     rcx, rdx
0x180005f57  mov     rax, rdi
0x180005f5a  shr     rcx, 1
0x180005f5d  sub     rax, rdx
0x180005f60  cmp     rax, rcx
0x180005f63  cmova   rcx, rax
0x180005f67  lea     rax, [rdx+rcx]
0x180005f6b  mov     edx, 40h ; '@'; Size
0x180005f70  cmp     rdi, rax
0x180005f73  cmovb   rdi, rax
0x180005f77  mov     rcx, rdi; Count
0x180005f7a  call    cs:__imp_calloc
0x180005f80  mov     rsi, rax
0x180005f83  test    rax, rax
0x180005f86  jnz     short loc_180005F8C
0x180005f88  xor     al, al
0x180005f8a  jmp     short loc_180005FCD
0x180005f8c  mov     rdx, [rbx+8]
0x180005f90  mov     rcx, rsi; Destination
0x180005f93  mov     r8, [rbx]; Source
0x180005f96  shl     rdx, 6; DestinationSize
0x180005f9a  mov     r9, rdx; SourceSize
0x180005f9d  call    cs:__imp_memmove_s
0x180005fa3  test    eax, eax
0x180005fa5  jz      short loc_180005FBB
0x180005fa7  cmp     eax, 0Ch
0x180005faa  jz      short loc_180005FF3
0x180005fac  cmp     eax, 16h
0x180005faf  jz      short loc_180005FE8
0x180005fb1  cmp     eax, 22h ; '"'
0x180005fb4  jz      short loc_180005FE8
0x180005fb6  cmp     eax, 50h ; 'P'
0x180005fb9  jnz     short loc_180005FDD
0x180005fbb  mov     rcx, [rbx]; Block
0x180005fbe  call    cs:__imp_free
0x180005fc4  mov     [rbx], rsi
0x180005fc7  mov     [rbx+10h], rdi
0x180005fcb  mov     al, 1
0x180005fcd  mov     rbx, [rsp+28h+arg_0]
0x180005fd2  mov     rsi, [rsp+28h+arg_8]
0x180005fd7  add     rsp, 20h
0x180005fdb  pop     rdi
0x180005fdc  retn
0x180005fdd  mov     ecx, 80004005h; int
0x180005fe2  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180005fe8  mov     ecx, 80070057h; int
0x180005fed  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180005ff3  mov     ecx, 8007000Eh; int
0x180005ff8  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
