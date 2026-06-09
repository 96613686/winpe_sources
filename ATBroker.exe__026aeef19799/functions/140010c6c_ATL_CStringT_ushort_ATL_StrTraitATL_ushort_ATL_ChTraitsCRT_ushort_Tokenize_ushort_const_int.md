# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Tokenize(ushort const *,int &)

- ea: `0x140010c6c`
- end: `0x140010e3e`
- name: `?Tokenize@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@PEBGAEAH@Z`
- size: `466`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14000d1b8`

## callees

- `0x140004890`
- `0x140006c00`
- `0x14000cb50`
- `0x14000f5dc`
- `0x140010c6c`
- `0x140017010`

## import_xrefs

- `msvcrt!wcscspn` at `0x140010ce0`
- `msvcrt!wcscspn` at `0x140010ce0`
- `msvcrt!wcsspn` at `0x140010cc4`
- `msvcrt!wcsspn` at `0x140010cc4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 *__fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Tokenize(
        __int64 *a1,
        __int64 *a2,
        const wchar_t *a3,
        int *a4)
{
  __int64 v8; // rax
  __int64 v9; // rcx
  const wchar_t *v10; // r15
  unsigned __int64 v11; // rbp
  int v12; // r12d
  const wchar_t *v13; // rcx
  unsigned int v14; // eax
  __int64 v15; // r8
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  _WORD *v19; // rdi
  __int64 v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rcx

  v8 = *a4;
  if ( (int)v8 < 0 )
    ATL::AtlThrowImpl(-2147024809);
  if ( a3 && *a3 )
  {
    v9 = *a1;
    v10 = (const wchar_t *)(v9 + 2 * v8);
    v11 = v9 + 2LL * *(int *)(v9 - 16);
    if ( (unsigned __int64)v10 < v11 )
    {
      v12 = wcsspn(v10, a3);
      v13 = &v10[v12];
      if ( (unsigned __int64)v13 < v11 )
      {
        v14 = wcscspn(v13, a3);
        v15 = (unsigned int)(v12 + *a4);
        *a4 = v15 + v14 + 1;
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Mid(
          a1,
          a2,
          v15,
          v14);
        return a2;
      }
    }
  }
  else
  {
    v16 = *a1;
    if ( (int)v8 < *(_DWORD *)(v16 - 16) )
    {
      v17 = *(_QWORD *)(v16 - 24);
      if ( !v17 || (v18 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 32LL))(v17)) == 0 )
      {
        v18 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[4])(&ATL::g_strmgr);
        if ( !v18 )
          ATL::AtlThrowImpl(-2147467259);
      }
      v19 = (_WORD *)(*a1 + 2LL * *a4);
      *a2 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v18 + 24LL))(v18) + 24;
      if ( v19 )
      {
        if ( (unsigned __int64)v19 < 0x10000 )
        {
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::LoadStringW(
            a2,
            (unsigned __int16)v19);
          return a2;
        }
        v20 = -1;
        do
          ++v20;
        while ( v19[v20] );
      }
      else
      {
        LODWORD(v20) = 0;
      }
      ATL::CSimpleStringT<unsigned short,0>::SetString(a2, v19, v20);
      return a2;
    }
  }
  *a4 = -1;
  v21 = *(_QWORD *)(*a1 - 24);
  if ( !v21 || (v22 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 32LL))(v21)) == 0 )
    v22 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[4])(&ATL::g_strmgr);
  if ( !v22 )
    ATL::AtlThrowImpl(-2147467259);
  *a2 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v22 + 24LL))(v22) + 24;
  return a2;
}

```

## disassembly

```asm
0x140010c6c  mov     [rsp+arg_8], rdx
0x140010c71  push    rbx
0x140010c72  push    rbp
0x140010c73  push    rsi
0x140010c74  push    rdi
0x140010c75  push    r12
0x140010c77  push    r13
0x140010c79  push    r14
0x140010c7b  push    r15
0x140010c7d  sub     rsp, 38h
0x140010c81  mov     r14, r9
0x140010c84  mov     rdi, r8
0x140010c87  mov     rbx, rdx
0x140010c8a  mov     rsi, rcx
0x140010c8d  xor     r13d, r13d
0x140010c90  movsxd  rax, dword ptr [r9]
0x140010c93  test    eax, eax
0x140010c95  js      loc_140010E28
0x140010c9b  test    r8, r8
0x140010c9e  jz      short loc_140010D08
0x140010ca0  cmp     [r8], r13w
0x140010ca4  jz      short loc_140010D08
0x140010ca6  mov     rcx, [rcx]
0x140010ca9  lea     r15, [rcx+rax*2]
0x140010cad  movsxd  rax, dword ptr [rcx-10h]
0x140010cb1  lea     rbp, [rcx+rax*2]
0x140010cb5  cmp     r15, rbp
0x140010cb8  jnb     loc_140010DB0
0x140010cbe  mov     rdx, r8; Control
0x140010cc1  mov     rcx, r15; String
0x140010cc4  call    cs:__imp_wcsspn
0x140010cca  mov     r12, rax
0x140010ccd  movsxd  rcx, eax
0x140010cd0  lea     rcx, [r15+rcx*2]; String
0x140010cd4  cmp     rcx, rbp
0x140010cd7  jnb     loc_140010DB0
0x140010cdd  mov     rdx, rdi; Control
0x140010ce0  call    cs:__imp_wcscspn
0x140010ce6  mov     r8d, [r14]
0x140010ce9  add     r8d, r12d
0x140010cec  lea     ecx, [rax+1]
0x140010cef  add     ecx, r8d
0x140010cf2  mov     [r14], ecx
0x140010cf5  mov     r9d, eax
0x140010cf8  mov     rdx, rbx
0x140010cfb  mov     rcx, rsi
0x140010cfe  call    ?Mid@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@HH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Mid(int,int)
0x140010d03  jmp     loc_140010E09
0x140010d08  mov     rcx, [rcx]
0x140010d0b  cmp     eax, [rcx-10h]
0x140010d0e  jge     loc_140010DB0
0x140010d14  mov     rcx, [rcx-18h]
0x140010d18  test    rcx, rcx
0x140010d1b  jz      short loc_140010D31
0x140010d1d  mov     rax, [rcx]
0x140010d20  mov     rax, [rax+20h]
0x140010d24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010d29  mov     rcx, rax
0x140010d2c  test    rax, rax
0x140010d2f  jnz     short loc_140010D54
0x140010d31  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140010d38  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140010d3f  mov     rax, [rax+20h]
0x140010d43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010d48  mov     rcx, rax
0x140010d4b  test    rax, rax
0x140010d4e  jz      loc_140010E33
0x140010d54  movsxd  rdx, dword ptr [r14]
0x140010d57  mov     rax, [rsi]
0x140010d5a  lea     rdi, [rax+rdx*2]
0x140010d5e  mov     rax, [rcx]
0x140010d61  mov     rax, [rax+18h]
0x140010d65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010d6a  add     rax, 18h
0x140010d6e  mov     [rbx], rax
0x140010d71  test    rdi, rdi
0x140010d74  jz      short loc_140010D9C
0x140010d76  cmp     rdi, 10000h
0x140010d7d  jnb     short loc_140010D8C
0x140010d7f  movzx   edx, di
0x140010d82  mov     rcx, rbx
0x140010d85  call    ?LoadStringW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHI@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::LoadStringW(uint)
0x140010d8a  jmp     short loc_140010DAE
0x140010d8c  or      rax, 0FFFFFFFFFFFFFFFFh
0x140010d90  inc     rax
0x140010d93  cmp     [rdi+rax*2], r13w
0x140010d98  jnz     short loc_140010D90
0x140010d9a  jmp     short loc_140010D9F
0x140010d9c  mov     eax, r13d
0x140010d9f  mov     r8d, eax
0x140010da2  mov     rdx, rdi
0x140010da5  mov     rcx, rbx
0x140010da8  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x140010dad  nop
0x140010dae  jmp     short loc_140010E09
0x140010db0  mov     dword ptr [r14], 0FFFFFFFFh
0x140010db7  mov     rax, [rsi]
0x140010dba  mov     rcx, [rax-18h]
0x140010dbe  test    rcx, rcx
0x140010dc1  jz      short loc_140010DD7
0x140010dc3  mov     rax, [rcx]
0x140010dc6  mov     rax, [rax+20h]
0x140010dca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010dcf  mov     rcx, rax
0x140010dd2  test    rax, rax
0x140010dd5  jnz     short loc_140010DF1
0x140010dd7  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140010dde  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140010de5  mov     rax, [rax+20h]
0x140010de9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010dee  mov     rcx, rax
0x140010df1  test    rcx, rcx
0x140010df4  jz      short loc_140010E1D
0x140010df6  mov     rax, [rcx]
0x140010df9  mov     rax, [rax+18h]
0x140010dfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010e02  add     rax, 18h
0x140010e06  mov     [rbx], rax
0x140010e09  mov     rax, rbx
0x140010e0c  add     rsp, 38h
0x140010e10  pop     r15
0x140010e12  pop     r14
0x140010e14  pop     r13
0x140010e16  pop     r12
0x140010e18  pop     rdi
0x140010e19  pop     rsi
0x140010e1a  pop     rbp
0x140010e1b  pop     rbx
0x140010e1c  retn
0x140010e1d  mov     ecx, 80004005h; int
0x140010e22  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140010e28  mov     ecx, 80070057h; int
0x140010e2d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140010e33  mov     ecx, 80004005h; int
0x140010e38  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
