# IndexCreateQueryTableKey(ushort const *,ulong,ushort const * const *)

- ea: `0x1800061c8`
- end: `0x180006318`
- name: `?IndexCreateQueryTableKey@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGKPEBQEBG@Z`
- size: `336`
- prototype: `__int64 *__fastcall(__int64 *, __int64, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180011fb0`

## callees

- `0x180004e8c`
- `0x1800050b4`
- `0x180005170`
- `0x1800061c8`
- `0x18000823c`
- `0x18000b64c`
- `0x180014010`

## import_xrefs

- `msvcrt!_wcslwr_s` at `0x180006260`
- `msvcrt!_wcslwr_s` at `0x180006260`

## pseudocode

```c
__int64 *__fastcall IndexCreateQueryTableKey(__int64 *a1, __int64 a2, unsigned int a3, __int64 a4)
{
  __int64 v8; // r8
  unsigned int i; // edi
  __int64 v10; // rdi

  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>();
  if ( a2 )
  {
    v8 = -1;
    do
      ++v8;
    while ( *(_WORD *)(a2 + 2 * v8) );
  }
  else
  {
    v8 = 0;
  }
  ATL::CSimpleStringT<unsigned short,0>::SetString(a1, a2, v8);
  for ( i = 0; i < a3; ++i )
    ATL::CSimpleStringT<unsigned short,0>::Append(a1, *(const void **)(a4 + 8LL * i));
  v10 = *(int *)(*a1 - 16);
  if ( (int)((*(_DWORD *)(*a1 - 12) - v10) | (1 - *(_DWORD *)(*a1 - 8))) < 0 )
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, (unsigned int)v10);
  _wcslwr_s((wchar_t *)*a1, (int)v10 + 1);
  if ( (int)v10 < 0 || (int)v10 > *(_DWORD *)(*a1 - 12) )
    ATL::AtlThrowImpl(-2147024809);
  *(_DWORD *)(*a1 - 16) = v10;
  *(_WORD *)(*a1 + 2 * v10) = 0;
  return a1;
}

```

## disassembly

```asm
0x1800061c8  mov     [rsp+arg_0], rcx
0x1800061cd  push    rbx
0x1800061ce  push    rsi
0x1800061cf  push    rdi
0x1800061d0  push    r12
0x1800061d2  push    r14
0x1800061d4  push    r15
0x1800061d6  sub     rsp, 38h
0x1800061da  mov     r15, r9
0x1800061dd  mov     r14d, r8d
0x1800061e0  mov     rdi, rdx
0x1800061e3  mov     rbx, rcx
0x1800061e6  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800061eb  nop
0x1800061ec  xor     r12d, r12d
0x1800061ef  test    rdi, rdi
0x1800061f2  jnz     short loc_1800061F9
0x1800061f4  mov     r8d, r12d
0x1800061f7  jmp     short loc_180006207
0x1800061f9  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800061fd  inc     r8
0x180006200  cmp     [rdi+r8*2], r12w
0x180006205  jnz     short loc_1800061FD
0x180006207  mov     rdx, rdi
0x18000620a  mov     rcx, rbx
0x18000620d  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180006212  mov     edi, r12d
0x180006215  mov     [rsp+68h+var_48], r12d
0x18000621a  mov     esi, 1
0x18000621f  cmp     edi, r14d
0x180006222  jnb     short loc_18000623A
0x180006224  mov     edx, edi
0x180006226  mov     rdx, [r15+rdx*8]
0x18000622a  mov     rcx, rbx
0x18000622d  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x180006232  add     edi, esi
0x180006234  mov     [rsp+68h+var_48], edi
0x180006238  jmp     short loc_18000621F
0x18000623a  mov     rax, [rbx]
0x18000623d  movsxd  rdi, dword ptr [rax-10h]
0x180006241  sub     esi, [rax-8]
0x180006244  mov     eax, [rax-0Ch]
0x180006247  sub     eax, edi
0x180006249  or      esi, eax
0x18000624b  jge     short loc_180006257
0x18000624d  mov     edx, edi
0x18000624f  mov     rcx, rbx
0x180006252  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x180006257  lea     eax, [rdi+1]
0x18000625a  movsxd  rdx, eax; SizeInWords
0x18000625d  mov     rcx, [rbx]; String
0x180006260  call    cs:__imp__wcslwr_s
0x180006266  test    edi, edi
0x180006268  js      loc_180006302
0x18000626e  mov     rax, [rbx]
0x180006271  cmp     edi, [rax-0Ch]
0x180006274  jg      loc_180006302
0x18000627a  mov     [rax-10h], edi
0x18000627d  mov     rcx, [rbx]
0x180006280  mov     [rcx+rdi*2], r12w
0x180006285  jmp     short loc_1800062F1
0x180006287  mov     rbx, [rsp+68h+arg_0]
0x18000628c  mov     rax, [rbx]
0x18000628f  lea     rcx, [rax-18h]
0x180006293  mov     rdi, [rcx]
0x180006296  cmp     dword ptr [rcx+8], 0
0x18000629a  jz      short loc_1800062F1
0x18000629c  cmp     dword ptr [rcx+10h], 0
0x1800062a0  jge     short loc_1800062B9
0x1800062a2  cmp     dword ptr [rax-0Ch], 0
0x1800062a6  jl      short loc_18000630D
0x1800062a8  mov     dword ptr [rax-10h], 0
0x1800062af  mov     rax, [rbx]
0x1800062b2  xor     ecx, ecx
0x1800062b4  mov     [rax], cx
0x1800062b7  jmp     short loc_1800062F1
0x1800062b9  or      eax, 0FFFFFFFFh
0x1800062bc  lock xadd [rcx+10h], eax
0x1800062c1  sub     eax, 1
0x1800062c4  jg      short loc_1800062DB
0x1800062c6  mov     rax, [rcx]
0x1800062c9  mov     rdx, [rax]
0x1800062cc  mov     rax, [rdx+8]
0x1800062d0  mov     rdx, rcx
0x1800062d3  mov     rcx, [rcx]
0x1800062d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062db  mov     rax, [rdi]
0x1800062de  mov     rcx, rdi
0x1800062e1  mov     rax, [rax+18h]
0x1800062e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062ea  add     rax, 18h
0x1800062ee  mov     [rbx], rax
0x1800062f1  mov     rax, rbx
0x1800062f4  add     rsp, 38h
0x1800062f8  pop     r15
0x1800062fa  pop     r14
0x1800062fc  pop     r12
0x1800062fe  pop     rdi
0x1800062ff  pop     rsi
0x180006300  pop     rbx
0x180006301  retn
0x180006302  mov     ecx, 80070057h; int
0x180006307  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000630d  mov     ecx, 80070057h; int
0x180006312  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
