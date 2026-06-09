# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::FormatV(ushort const *,char *)

- ea: `0x18000ae58`
- end: `0x18000afd1`
- name: `?FormatV@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGPEAD@Z`
- size: `377`
- prototype: `__int64 __fastcall(wchar_t *const *, const wchar_t *, va_list)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18000ae28`
- `0x18000bd68`

## callees

- `0x180006a80`
- `0x18000ae58`
- `0x18000b484`
- `0x18000b6ec`
- `0x18000b9a8`
- `0x18000e010`

## import_xrefs

- `msvcrt!_vscwprintf` at `0x18000ae85`
- `msvcrt!_vscwprintf` at `0x18000ae85`
- `msvcrt!vswprintf_s` at `0x18000af55`
- `msvcrt!vswprintf_s` at `0x18000af55`

## pseudocode

```c
__int64 __fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::FormatV(
        wchar_t *const *a1,
        const wchar_t *a2,
        va_list a3)
{
  int v6; // eax
  __int64 v7; // rdi
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // r8
  wchar_t *v11; // rbx
  signed __int32 v12; // eax
  bool v13; // cc
  __int64 result; // rax
  wchar_t *Format; // [rsp+48h] [rbp+10h] BYREF

  if ( !a2 )
    ATL::AtlThrowImpl(-2147024809);
  v6 = _vscwprintf(a2, a3);
  v7 = v6;
  if ( v6 == -1 )
    ATL::AtlThrowImpl(-2147024882);
  v8 = *((_QWORD *)*a1 - 3);
  if ( !v8 || (v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 32LL))(v8)) == 0 )
  {
    v9 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[4])(&ATL::g_strmgr);
    if ( !v9 )
      ATL::AtlThrowImpl(-2147467259);
  }
  Format = (wchar_t *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 24LL))(v9) + 24);
  if ( (unsigned __int64)a2 >= 0x10000 )
  {
    v10 = -1;
    do
      ++v10;
    while ( a2[v10] );
    ATL::CSimpleStringT<unsigned short,0>::SetString(&Format, a2);
  }
  else
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::LoadStringW(
      &Format,
      (unsigned __int16)a2);
  }
  if ( (int)((*((_DWORD *)*a1 - 3) - v7) | (1 - *((_DWORD *)*a1 - 2))) < 0 )
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, (unsigned int)v7);
  v11 = Format;
  vswprintf_s(*a1, (int)v7 + 1, Format, a3);
  if ( (int)v7 < 0 || (int)v7 > *((_DWORD *)*a1 - 3) )
    ATL::AtlThrowImpl(-2147024809);
  *((_DWORD *)*a1 - 4) = v7;
  (*a1)[v7] = 0;
  v12 = _InterlockedExchangeAdd((volatile signed __int32 *)v11 - 2, 0xFFFFFFFF);
  v13 = v12 <= 1;
  result = (unsigned int)(v12 - 1);
  if ( v13 )
    return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v11 - 3) + 8LL))(*((_QWORD *)v11 - 3));
  return result;
}

```

## disassembly

```asm
0x18000ae58  mov     [rsp+arg_0], rbx
0x18000ae5d  mov     [rsp+arg_10], rbp
0x18000ae62  push    rsi
0x18000ae63  push    rdi
0x18000ae64  push    r14
0x18000ae66  sub     rsp, 20h
0x18000ae6a  mov     rbp, r8
0x18000ae6d  mov     rbx, rdx
0x18000ae70  mov     rsi, rcx
0x18000ae73  xor     r14d, r14d
0x18000ae76  test    rdx, rdx
0x18000ae79  jz      loc_18000AFBB
0x18000ae7f  mov     rdx, r8; ArgList
0x18000ae82  mov     rcx, rbx; Format
0x18000ae85  call    cs:__imp__vscwprintf
0x18000ae8b  movsxd  rdi, eax
0x18000ae8e  cmp     edi, 0FFFFFFFFh
0x18000ae91  jz      loc_18000AFC6
0x18000ae97  mov     rax, [rsi]
0x18000ae9a  mov     rcx, [rax-18h]
0x18000ae9e  test    rcx, rcx
0x18000aea1  jz      short loc_18000AEB7
0x18000aea3  mov     rax, [rcx]
0x18000aea6  mov     rax, [rax+20h]
0x18000aeaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aeaf  mov     rcx, rax
0x18000aeb2  test    rax, rax
0x18000aeb5  jnz     short loc_18000AEDA
0x18000aeb7  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000aebe  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000aec5  mov     rax, [rax+20h]
0x18000aec9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aece  mov     rcx, rax
0x18000aed1  test    rax, rax
0x18000aed4  jz      loc_18000AFB0
0x18000aeda  mov     rax, [rcx]
0x18000aedd  mov     rax, [rax+18h]
0x18000aee1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aee6  add     rax, 18h
0x18000aeea  mov     [rsp+38h+Format], rax
0x18000aeef  cmp     rbx, 10000h
0x18000aef6  jnb     short loc_18000AF07
0x18000aef8  movzx   edx, bx
0x18000aefb  lea     rcx, [rsp+38h+Format]
0x18000af00  call    ?LoadStringW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHI@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::LoadStringW(uint)
0x18000af05  jmp     short loc_18000AF23
0x18000af07  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000af0b  inc     r8
0x18000af0e  cmp     [rbx+r8*2], r14w
0x18000af13  jnz     short loc_18000AF0B
0x18000af15  mov     rdx, rbx
0x18000af18  lea     rcx, [rsp+38h+Format]
0x18000af1d  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18000af22  nop
0x18000af23  mov     rax, [rsi]
0x18000af26  mov     edx, 1
0x18000af2b  sub     edx, [rax-8]
0x18000af2e  mov     ecx, [rax-0Ch]
0x18000af31  sub     ecx, edi
0x18000af33  or      edx, ecx
0x18000af35  jge     short loc_18000AF41
0x18000af37  mov     edx, edi
0x18000af39  mov     rcx, rsi
0x18000af3c  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x18000af41  lea     eax, [rdi+1]
0x18000af44  movsxd  rdx, eax; BufferCount
0x18000af47  mov     r9, rbp; ArgList
0x18000af4a  mov     rbx, [rsp+38h+Format]
0x18000af4f  mov     r8, rbx; Format
0x18000af52  mov     rcx, [rsi]; Buffer
0x18000af55  call    cs:__imp_vswprintf_s
0x18000af5b  test    edi, edi
0x18000af5d  js      short loc_18000AFA5
0x18000af5f  mov     rax, [rsi]
0x18000af62  cmp     edi, [rax-0Ch]
0x18000af65  jg      short loc_18000AFA5
0x18000af67  mov     [rax-10h], edi
0x18000af6a  mov     rcx, [rsi]
0x18000af6d  mov     [rcx+rdi*2], r14w
0x18000af72  lea     rdx, [rbx-18h]
0x18000af76  or      eax, 0FFFFFFFFh
0x18000af79  lock xadd [rdx+10h], eax
0x18000af7e  sub     eax, 1
0x18000af81  jg      short loc_18000AF92
0x18000af83  mov     rcx, [rdx]
0x18000af86  mov     rax, [rcx]
0x18000af89  mov     rax, [rax+8]
0x18000af8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af92  mov     rbx, [rsp+38h+arg_0]
0x18000af97  mov     rbp, [rsp+38h+arg_10]
0x18000af9c  add     rsp, 20h
0x18000afa0  pop     r14
0x18000afa2  pop     rdi
0x18000afa3  pop     rsi
0x18000afa4  retn
0x18000afa5  mov     ecx, 80070057h; int
0x18000afaa  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000afb0  mov     ecx, 80004005h; int
0x18000afb5  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000afbb  mov     ecx, 80070057h; int
0x18000afc0  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000afc6  mov     ecx, 8007000Eh; int
0x18000afcb  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
