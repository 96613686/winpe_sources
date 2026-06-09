# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Tokenize(ushort const *,int &)

- ea: `0x18001578c`
- end: `0x180015917`
- name: `?Tokenize@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@PEBGAEAH@Z`
- size: `395`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18000d770`
- `0x1800166b4`

## callees

- `0x180003bb8`
- `0x18000cf40`
- `0x18000cfe4`
- `0x18001578c`
- `0x18002a010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x1800157f1`
- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x1800157f1`
- `api-ms-win-crt-string-l1-1-0!wcsspn` at `0x1800157d1`
- `api-ms-win-crt-string-l1-1-0!wcsspn` at `0x1800157d1`

## pseudocode

```c
_QWORD *__fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Tokenize(
        _QWORD *a1,
        _QWORD *a2,
        __int64 a3,
        int *a4)
{
  unsigned __int64 v7; // r14
  unsigned __int64 v8; // rbp
  int v9; // r15d
  const wchar_t *v10; // rcx
  int v11; // eax
  int v12; // edx
  int v13; // esi
  int v14; // ecx
  int v15; // edx
  unsigned int v16; // ebp
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 v20; // rcx
  __int64 v21; // rcx

  if ( *a4 < 0 )
    goto LABEL_26;
  v7 = *a1 + 2LL * *a4;
  v8 = *a1 + 2LL * *(int *)(*a1 - 16LL);
  if ( v7 < v8 )
  {
    v9 = wcsspn((const wchar_t *)(*a1 + 2LL * *a4), L";");
    v10 = (const wchar_t *)(v7 + 2LL * v9);
    if ( (unsigned __int64)v10 < v8 )
    {
      v11 = wcscspn(v10, L";");
      v12 = v9 + *a4;
      *a4 = v12 + v11 + 1;
      v13 = 0;
      if ( v12 >= 0 )
        v13 = v12;
      v14 = 0;
      if ( v11 >= 0 )
        v14 = v11;
      if ( 0x7FFFFFFF - v13 >= v14 )
      {
        v15 = *(_DWORD *)(*a1 - 16LL);
        if ( v13 + v14 > v15 )
          v14 = v15 - v13;
        v16 = 0;
        if ( v13 <= v15 )
          v16 = v14;
        if ( v13 || v16 != v15 )
        {
          v17 = *(_QWORD *)(*a1 - 24LL);
          if ( !v17 || (v18 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 32LL))(v17)) == 0 )
            v18 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[4])(&ATL::g_strmgr);
          ATL::CSimpleStringT<unsigned short,0>::CSimpleStringT<unsigned short,0>(a2, *a1 + 2LL * v13, v16, v18);
        }
        else
        {
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            a2,
            a1);
        }
        return a2;
      }
LABEL_26:
      ATL::AtlThrowImpl(-2147024809);
    }
  }
  *a4 = -1;
  v20 = *(_QWORD *)(*a1 - 24LL);
  if ( !v20 || (v21 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v20 + 32LL))(v20)) == 0 )
  {
    v21 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[4])(&ATL::g_strmgr);
    if ( !v21 )
      ATL::AtlThrowImpl(-2147467259);
  }
  *a2 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 24LL))(v21) + 24;
  return a2;
}

```

## disassembly

```asm
0x18001578c  push    rbx
0x18001578e  push    rbp
0x18001578f  push    rsi
0x180015790  push    rdi
0x180015791  push    r14
0x180015793  push    r15
0x180015795  sub     rsp, 28h
0x180015799  cmp     dword ptr [r9], 0
0x18001579d  mov     rsi, r9
0x1800157a0  mov     rdi, rdx
0x1800157a3  mov     rbx, rcx
0x1800157a6  jl      loc_18001590C
0x1800157ac  mov     r8, [rcx]
0x1800157af  movsxd  rax, dword ptr [r9]
0x1800157b2  lea     r14, [r8+rax*2]
0x1800157b6  movsxd  rax, dword ptr [r8-10h]
0x1800157ba  lea     rbp, [r8+rax*2]
0x1800157be  cmp     r14, rbp
0x1800157c1  jnb     loc_1800158A7
0x1800157c7  lea     rdx, Control; ";"
0x1800157ce  mov     rcx, r14; String
0x1800157d1  call    cs:__imp_wcsspn
0x1800157d7  movsxd  rcx, eax
0x1800157da  mov     r15, rax
0x1800157dd  lea     rcx, [r14+rcx*2]; String
0x1800157e1  cmp     rcx, rbp
0x1800157e4  jnb     loc_1800158A7
0x1800157ea  lea     rdx, Control; ";"
0x1800157f1  call    cs:__imp_wcscspn
0x1800157f7  mov     edx, [rsi]
0x1800157f9  add     edx, r15d
0x1800157fc  lea     ecx, [rax+1]
0x1800157ff  add     ecx, edx
0x180015801  mov     [rsi], ecx
0x180015803  xor     esi, esi
0x180015805  test    edx, edx
0x180015807  cmovns  esi, edx
0x18001580a  xor     ecx, ecx
0x18001580c  test    eax, eax
0x18001580e  cmovns  ecx, eax
0x180015811  mov     eax, 7FFFFFFFh
0x180015816  sub     eax, esi
0x180015818  cmp     eax, ecx
0x18001581a  jl      loc_18001590C
0x180015820  mov     r8, [rbx]
0x180015823  lea     eax, [rsi+rcx]
0x180015826  mov     edx, [r8-10h]
0x18001582a  cmp     eax, edx
0x18001582c  jle     short loc_180015832
0x18001582e  mov     ecx, edx
0x180015830  sub     ecx, esi
0x180015832  xor     ebp, ebp
0x180015834  cmp     esi, edx
0x180015836  cmovle  ebp, ecx
0x180015839  test    esi, esi
0x18001583b  jnz     short loc_18001584E
0x18001583d  cmp     ebp, edx
0x18001583f  jnz     short loc_18001584E
0x180015841  mov     rdx, rbx
0x180015844  mov     rcx, rdi
0x180015847  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18001584c  jmp     short loc_180015897
0x18001584e  mov     rcx, [r8-18h]
0x180015852  test    rcx, rcx
0x180015855  jz      short loc_180015868
0x180015857  mov     rax, [rcx]
0x18001585a  mov     rax, [rax+20h]
0x18001585e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015863  test    rax, rax
0x180015866  jnz     short loc_18001587F
0x180015868  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001586f  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180015876  mov     rax, [rax+20h]
0x18001587a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001587f  mov     rcx, [rbx]
0x180015882  mov     r9, rax
0x180015885  movsxd  rdx, esi
0x180015888  mov     r8d, ebp
0x18001588b  lea     rdx, [rcx+rdx*2]
0x18001588f  mov     rcx, rdi
0x180015892  call    ??0?$CSimpleStringT@G$0A@@ATL@@QEAA@PEBGHPEAUIAtlStringMgr@1@@Z; ATL::CSimpleStringT<ushort,0>::CSimpleStringT<ushort,0>(ushort const *,int,ATL::IAtlStringMgr *)
0x180015897  mov     rax, rdi
0x18001589a  add     rsp, 28h
0x18001589e  pop     r15
0x1800158a0  pop     r14
0x1800158a2  pop     rdi
0x1800158a3  pop     rsi
0x1800158a4  pop     rbp
0x1800158a5  pop     rbx
0x1800158a6  retn
0x1800158a7  mov     dword ptr [rsi], 0FFFFFFFFh
0x1800158ad  mov     rax, [rbx]
0x1800158b0  mov     rcx, [rax-18h]
0x1800158b4  test    rcx, rcx
0x1800158b7  jz      short loc_1800158CD
0x1800158b9  mov     rax, [rcx]
0x1800158bc  mov     rax, [rax+20h]
0x1800158c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800158c5  mov     rcx, rax
0x1800158c8  test    rax, rax
0x1800158cb  jnz     short loc_1800158EC
0x1800158cd  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800158d4  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800158db  mov     rax, [rax+20h]
0x1800158df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800158e4  mov     rcx, rax
0x1800158e7  test    rax, rax
0x1800158ea  jz      short loc_180015901
0x1800158ec  mov     rax, [rcx]
0x1800158ef  mov     rax, [rax+18h]
0x1800158f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800158f8  add     rax, 18h
0x1800158fc  mov     [rdi], rax
0x1800158ff  jmp     short loc_180015897
0x180015901  mov     ecx, 80004005h; int
0x180015906  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001590c  mov     ecx, 80070057h; int
0x180015911  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
