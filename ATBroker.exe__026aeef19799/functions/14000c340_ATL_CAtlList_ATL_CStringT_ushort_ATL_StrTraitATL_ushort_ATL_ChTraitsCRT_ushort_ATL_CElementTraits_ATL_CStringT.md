# ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::AddTail(ushort const *)

- ea: `0x14000c340`
- end: `0x14000c41a`
- name: `?AddTail@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAPEAU__POSITION@@PEBG@Z`
- size: `218`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x14000cfd0`
- `0x14000d1b8`
- `0x14000e538`
- `0x140010244`

## callees

- `0x140004890`
- `0x14000c19c`
- `0x14000c340`

## import_xrefs

- `msvcrt!malloc` at `0x14000c388`
- `msvcrt!malloc` at `0x14000c388`

## pseudocode

```c
__int64 *__fastcall ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::AddTail(
        __int64 a1,
        const void *a2)
{
  __int64 *v2; // rdi
  __int64 v4; // r14
  unsigned __int64 v6; // rbx
  __int64 v7; // rcx
  _QWORD *v8; // rax
  int v9; // ebx
  __int64 *i; // rcx
  __int64 v11; // rbx
  __int64 **v12; // rax

  v2 = *(__int64 **)(a1 + 32);
  v4 = *(_QWORD *)(a1 + 8);
  if ( v2 )
    goto LABEL_9;
  v6 = *(unsigned int *)(a1 + 40);
  if ( (_DWORD)v6 )
  {
    if ( 0xFFFFFFFFFFFFFFFFuLL / v6 < 0x18 )
      goto LABEL_13;
    v7 = 24 * v6;
  }
  else
  {
    v7 = 0;
  }
  v8 = malloc(v7 + 8);
  if ( !v8 )
LABEL_13:
    ATL::AtlThrowImpl(-2147024882);
  v9 = v6 - 1;
  *v8 = *(_QWORD *)(a1 + 24);
  *(_QWORD *)(a1 + 24) = v8;
  for ( i = &v8[2 * v9 + 1 + (unsigned int)v9]; v9 >= 0; --v9 )
  {
    v2 = i;
    *i = *(_QWORD *)(a1 + 32);
    *(_QWORD *)(a1 + 32) = i;
    i -= 3;
  }
LABEL_9:
  v11 = *v2;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v2 + 2,
    a2);
  *(_QWORD *)(a1 + 32) = v11;
  v2[1] = v4;
  *v2 = 0;
  ++*(_QWORD *)(a1 + 16);
  v12 = *(__int64 ***)(a1 + 8);
  if ( v12 )
    *v12 = v2;
  else
    *(_QWORD *)a1 = v2;
  *(_QWORD *)(a1 + 8) = v2;
  return v2;
}

```

## disassembly

```asm
0x14000c340  push    rbx
0x14000c342  push    rbp
0x14000c343  push    rsi
0x14000c344  push    rdi
0x14000c345  push    r14
0x14000c347  sub     rsp, 20h
0x14000c34b  mov     rdi, [rcx+20h]
0x14000c34f  mov     rbp, rdx
0x14000c352  mov     r14, [rcx+8]
0x14000c356  mov     rsi, rcx
0x14000c359  test    rdi, rdi
0x14000c35c  jnz     short loc_14000C3CA
0x14000c35e  mov     ebx, [rcx+28h]
0x14000c361  test    ebx, ebx
0x14000c363  jnz     short loc_14000C369
0x14000c365  xor     ecx, ecx
0x14000c367  jmp     short loc_14000C384
0x14000c369  xor     edx, edx
0x14000c36b  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000c36f  div     rbx
0x14000c372  cmp     rax, 18h
0x14000c376  jb      loc_14000C40F
0x14000c37c  lea     rcx, [rbx+rbx*2]
0x14000c380  shl     rcx, 3
0x14000c384  add     rcx, 8; Size
0x14000c388  call    cs:__imp_malloc
0x14000c38e  test    rax, rax
0x14000c391  jz      short loc_14000C40F
0x14000c393  mov     rcx, [rsi+18h]
0x14000c397  sub     ebx, 1
0x14000c39a  mov     [rax], rcx
0x14000c39d  mov     [rsi+18h], rax
0x14000c3a1  lea     rcx, ds:1[rbx*2]
0x14000c3a9  lea     rcx, [rcx+rbx]
0x14000c3ad  lea     rcx, [rax+rcx*8]
0x14000c3b1  js      short loc_14000C3CA
0x14000c3b3  mov     rax, [rsi+20h]
0x14000c3b7  mov     rdi, rcx
0x14000c3ba  mov     [rcx], rax
0x14000c3bd  mov     [rsi+20h], rcx
0x14000c3c1  sub     rcx, 18h
0x14000c3c5  sub     ebx, 1
0x14000c3c8  jns     short loc_14000C3B3
0x14000c3ca  mov     rbx, [rdi]
0x14000c3cd  lea     rcx, [rdi+10h]
0x14000c3d1  mov     rdx, rbp
0x14000c3d4  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14000c3d9  mov     [rsi+20h], rbx
0x14000c3dd  mov     [rdi+8], r14
0x14000c3e1  mov     qword ptr [rdi], 0
0x14000c3e8  inc     qword ptr [rsi+10h]
0x14000c3ec  mov     rax, [rsi+8]
0x14000c3f0  test    rax, rax
0x14000c3f3  jz      short loc_14000C3FA
0x14000c3f5  mov     [rax], rdi
0x14000c3f8  jmp     short loc_14000C3FD
0x14000c3fa  mov     [rsi], rdi
0x14000c3fd  mov     [rsi+8], rdi
0x14000c401  mov     rax, rdi
0x14000c404  add     rsp, 20h
0x14000c408  pop     r14
0x14000c40a  pop     rdi
0x14000c40b  pop     rsi
0x14000c40c  pop     rbp
0x14000c40d  pop     rbx
0x14000c40e  retn
0x14000c40f  mov     ecx, 8007000Eh; int
0x14000c414  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
