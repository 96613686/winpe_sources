# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)

- ea: `0x180004ee0`
- end: `0x180005048`
- name: `?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ`
- size: `360`
- prototype: `__int64(_QWORD, _QWORD, ...)`
- caller_count: `20`
- callee_count: `6`
- tags: ``

## callers

- `0x180002974`
- `0x180004864`
- `0x180005734`
- `0x180005db4`
- `0x180005f64`
- `0x1800067d0`
- `0x180008214`
- `0x180008440`
- `0x1800088e0`
- `0x180008fc0`
- `0x18001015d`
- `0x1800102e6`
- `0x1800103bb`
- `0x1800105a8`
- `0x18001067a`
- `0x180010960`
- `0x180010a50`
- `0x180010b07`
- `0x180010bd0`
- `0x180010c7c`

## callees

- `0x1800039b4`
- `0x180004684`
- `0x180004ee0`
- `0x180006530`
- `0x180007250`
- `0x180012010`

## import_xrefs

- `msvcrt!vswprintf_s` at `0x180004fd5`
- `msvcrt!vswprintf_s` at `0x180004fd5`
- `msvcrt!_vscwprintf` at `0x180004f18`
- `msvcrt!_vscwprintf` at `0x180004f18`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        __int64 *a1,
        wchar_t *a2,
        ...)
{
  int v4; // eax
  __int64 v5; // rdi
  __int64 v6; // rcx
  __int64 v7; // rcx
  wchar_t *v8; // rbx
  signed __int32 v9; // eax
  bool v10; // cc
  __int64 result; // rax
  wchar_t *Format[7]; // [rsp+20h] [rbp-38h] BYREF
  va_list va; // [rsp+70h] [rbp+18h] BYREF

  va_start(va, a2);
  Format[0] = 0;
  if ( !a2 )
    ATL::AtlThrowImpl(-2147024809);
  v4 = _vscwprintf(a2, va);
  v5 = v4;
  if ( v4 == -1 )
    ATL::AtlThrowImpl(-2147024882);
  v6 = *(_QWORD *)(*a1 - 24);
  if ( !v6 || (v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 32LL))(v6)) == 0 )
  {
    v7 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[4])(&ATL::g_strmgr);
    if ( !v7 )
      ATL::AtlThrowImpl(-2147467259);
  }
  Format[0] = (wchar_t *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 24LL))(v7) + 24);
  if ( (unsigned __int64)a2 >= 0x10000 )
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
      (int **)Format,
      (char *)a2);
  else
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::LoadStringW(
      Format,
      (unsigned __int16)a2);
  if ( (int)((*(_DWORD *)(*a1 - 12) - v5) | (1 - *(_DWORD *)(*a1 - 8))) < 0 )
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, v5);
  v8 = Format[0];
  vswprintf_s((wchar_t *const)*a1, (int)v5 + 1, Format[0], va);
  if ( (int)v5 < 0 || (int)v5 > *(_DWORD *)(*a1 - 12) )
    ATL::AtlThrowImpl(-2147024809);
  *(_DWORD *)(*a1 - 16) = v5;
  *(_WORD *)(*a1 + 2 * v5) = 0;
  v9 = _InterlockedExchangeAdd((volatile signed __int32 *)v8 - 2, 0xFFFFFFFF);
  v10 = v9 <= 1;
  result = (unsigned int)(v9 - 1);
  if ( v10 )
    return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v8 - 3) + 8LL))(*((_QWORD *)v8 - 3));
  return result;
}

```

## disassembly

```asm
0x180004ee0  mov     rax, rsp
0x180004ee3  mov     [rax+10h], rdx
0x180004ee7  mov     [rax+18h], r8
0x180004eeb  mov     [rax+20h], r9
0x180004eef  push    rbx
0x180004ef0  push    rbp
0x180004ef1  push    rsi
0x180004ef2  push    rdi
0x180004ef3  sub     rsp, 38h
0x180004ef7  mov     rbx, rdx
0x180004efa  mov     rsi, rcx
0x180004efd  mov     qword ptr [rax-38h], 0
0x180004f05  lea     rbp, [rax+18h]
0x180004f09  test    rdx, rdx
0x180004f0c  jz      loc_180005032
0x180004f12  mov     rdx, rbp; ArgList
0x180004f15  mov     rcx, rbx; Format
0x180004f18  call    cs:__imp__vscwprintf
0x180004f1e  movsxd  rdi, eax
0x180004f21  cmp     edi, 0FFFFFFFFh
0x180004f24  jz      loc_18000503D
0x180004f2a  mov     rax, [rsi]
0x180004f2d  mov     rcx, [rax-18h]
0x180004f31  test    rcx, rcx
0x180004f34  jz      short loc_180004F4A
0x180004f36  mov     rax, [rcx]
0x180004f39  mov     rax, [rax+20h]
0x180004f3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f42  mov     rcx, rax
0x180004f45  test    rax, rax
0x180004f48  jnz     short loc_180004F6D
0x180004f4a  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180004f51  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180004f58  mov     rax, [rax+20h]
0x180004f5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f61  mov     rcx, rax
0x180004f64  test    rax, rax
0x180004f67  jz      loc_180005027
0x180004f6d  mov     rax, [rcx]
0x180004f70  mov     rax, [rax+18h]
0x180004f74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f79  add     rax, 18h
0x180004f7d  mov     [rsp+58h+Format], rax
0x180004f82  lea     rcx, [rsp+58h+Format]
0x180004f87  cmp     rbx, 10000h
0x180004f8e  jnb     short loc_180004F9A
0x180004f90  movzx   edx, bx
0x180004f93  call    ?LoadStringW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHI@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::LoadStringW(uint)
0x180004f98  jmp     short loc_180004FA3
0x180004f9a  mov     rdx, rbx
0x180004f9d  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ushort const *)
0x180004fa2  nop
0x180004fa3  mov     rax, [rsi]
0x180004fa6  mov     edx, 1
0x180004fab  sub     edx, [rax-8]
0x180004fae  mov     ecx, [rax-0Ch]
0x180004fb1  sub     ecx, edi
0x180004fb3  or      edx, ecx
0x180004fb5  jge     short loc_180004FC1
0x180004fb7  mov     edx, edi
0x180004fb9  mov     rcx, rsi
0x180004fbc  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x180004fc1  lea     eax, [rdi+1]
0x180004fc4  movsxd  rdx, eax; BufferCount
0x180004fc7  mov     r9, rbp; ArgList
0x180004fca  mov     rbx, [rsp+58h+Format]
0x180004fcf  mov     r8, rbx; Format
0x180004fd2  mov     rcx, [rsi]; Buffer
0x180004fd5  call    cs:__imp_vswprintf_s
0x180004fdb  test    edi, edi
0x180004fdd  js      short loc_18000501C
0x180004fdf  mov     rax, [rsi]
0x180004fe2  cmp     edi, [rax-0Ch]
0x180004fe5  jg      short loc_18000501C
0x180004fe7  mov     [rax-10h], edi
0x180004fea  mov     rcx, [rsi]
0x180004fed  xor     eax, eax
0x180004fef  mov     [rcx+rdi*2], ax
0x180004ff3  lea     rdx, [rbx-18h]
0x180004ff7  or      eax, 0FFFFFFFFh
0x180004ffa  lock xadd [rdx+10h], eax
0x180004fff  sub     eax, 1
0x180005002  jg      short loc_180005013
0x180005004  mov     rcx, [rdx]
0x180005007  mov     rax, [rcx]
0x18000500a  mov     rax, [rax+8]
0x18000500e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005013  add     rsp, 38h
0x180005017  pop     rdi
0x180005018  pop     rsi
0x180005019  pop     rbp
0x18000501a  pop     rbx
0x18000501b  retn
0x18000501c  mov     ecx, 80070057h; int
0x180005021  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180005027  mov     ecx, 80004005h; int
0x18000502c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180005032  mov     ecx, 80070057h; int
0x180005037  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000503d  mov     ecx, 8007000Eh; int
0x180005042  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
