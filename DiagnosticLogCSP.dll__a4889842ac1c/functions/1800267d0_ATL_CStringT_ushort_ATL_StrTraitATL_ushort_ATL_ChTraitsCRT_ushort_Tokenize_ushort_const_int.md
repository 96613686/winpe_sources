# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Tokenize(ushort const *,int &)

- ea: `0x1800267d0`
- end: `0x18002695b`
- name: `?Tokenize@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@PEBGAEAH@Z`
- size: `395`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18001e388`
- `0x1800274b4`

## callees

- `0x180010db8`
- `0x18001dc28`
- `0x18001dccc`
- `0x1800267d0`
- `0x180037010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x180026835`
- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x180026835`
- `api-ms-win-crt-string-l1-1-0!wcsspn` at `0x180026815`
- `api-ms-win-crt-string-l1-1-0!wcsspn` at `0x180026815`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
    goto LABEL_27;
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
LABEL_27:
      ATL::AtlThrowImpl(-2147024809);
    }
  }
  *a4 = -1;
  v20 = *(_QWORD *)(*a1 - 24LL);
  if ( !v20 || (v21 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v20 + 32LL))(v20)) == 0 )
    v21 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[4])(&ATL::g_strmgr);
  if ( !v21 )
    ATL::AtlThrowImpl(-2147467259);
  *a2 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 24LL))(v21) + 24;
  return a2;
}

```

## disassembly

```asm
0x1800267d0  push    rbx
0x1800267d2  push    rbp
0x1800267d3  push    rsi
0x1800267d4  push    rdi
0x1800267d5  push    r14
0x1800267d7  push    r15
0x1800267d9  sub     rsp, 38h
0x1800267dd  mov     rsi, r9
0x1800267e0  mov     rbx, rdx
0x1800267e3  mov     rdi, rcx
0x1800267e6  cmp     dword ptr [r9], 0
0x1800267ea  jl      loc_180026950
0x1800267f0  mov     r8, [rcx]
0x1800267f3  movsxd  rax, dword ptr [r9]
0x1800267f6  lea     r14, [r8+rax*2]
0x1800267fa  movsxd  rax, dword ptr [r8-10h]
0x1800267fe  lea     rbp, [r8+rax*2]
0x180026802  cmp     r14, rbp
0x180026805  jnb     loc_1800268EB
0x18002680b  lea     rdx, Control; ";"
0x180026812  mov     rcx, r14; String
0x180026815  call    cs:__imp_wcsspn
0x18002681b  mov     r15, rax
0x18002681e  movsxd  rcx, eax
0x180026821  lea     rcx, [r14+rcx*2]; String
0x180026825  cmp     rcx, rbp
0x180026828  jnb     loc_1800268EB
0x18002682e  lea     rdx, Control; ";"
0x180026835  call    cs:__imp_wcscspn
0x18002683b  mov     edx, [rsi]
0x18002683d  add     edx, r15d
0x180026840  lea     ecx, [rax+1]
0x180026843  add     ecx, edx
0x180026845  mov     [rsi], ecx
0x180026847  xor     esi, esi
0x180026849  test    edx, edx
0x18002684b  cmovns  esi, edx
0x18002684e  xor     ecx, ecx
0x180026850  test    eax, eax
0x180026852  cmovns  ecx, eax
0x180026855  mov     eax, 7FFFFFFFh
0x18002685a  sub     eax, esi
0x18002685c  cmp     eax, ecx
0x18002685e  jl      loc_180026950
0x180026864  lea     eax, [rsi+rcx]
0x180026867  mov     r8, [rdi]
0x18002686a  mov     edx, [r8-10h]
0x18002686e  cmp     eax, edx
0x180026870  jle     short loc_180026876
0x180026872  mov     ecx, edx
0x180026874  sub     ecx, esi
0x180026876  xor     ebp, ebp
0x180026878  cmp     esi, edx
0x18002687a  cmovle  ebp, ecx
0x18002687d  test    esi, esi
0x18002687f  jnz     short loc_180026892
0x180026881  cmp     ebp, edx
0x180026883  jnz     short loc_180026892
0x180026885  mov     rdx, rdi
0x180026888  mov     rcx, rbx
0x18002688b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180026890  jmp     short loc_1800268DB
0x180026892  mov     rcx, [r8-18h]
0x180026896  test    rcx, rcx
0x180026899  jz      short loc_1800268AC
0x18002689b  mov     rax, [rcx]
0x18002689e  mov     rax, [rax+20h]
0x1800268a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800268a7  test    rax, rax
0x1800268aa  jnz     short loc_1800268C3
0x1800268ac  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800268b3  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800268ba  mov     rax, [rax+20h]
0x1800268be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800268c3  movsxd  rdx, esi
0x1800268c6  mov     rcx, [rdi]
0x1800268c9  lea     rdx, [rcx+rdx*2]
0x1800268cd  mov     r9, rax
0x1800268d0  mov     r8d, ebp
0x1800268d3  mov     rcx, rbx
0x1800268d6  call    ??0?$CSimpleStringT@G$0A@@ATL@@QEAA@PEBGHPEAUIAtlStringMgr@1@@Z; ATL::CSimpleStringT<ushort,0>::CSimpleStringT<ushort,0>(ushort const *,int,ATL::IAtlStringMgr *)
0x1800268db  mov     rax, rbx
0x1800268de  add     rsp, 38h
0x1800268e2  pop     r15
0x1800268e4  pop     r14
0x1800268e6  pop     rdi
0x1800268e7  pop     rsi
0x1800268e8  pop     rbp
0x1800268e9  pop     rbx
0x1800268ea  retn
0x1800268eb  mov     dword ptr [rsi], 0FFFFFFFFh
0x1800268f1  mov     rax, [rdi]
0x1800268f4  mov     rcx, [rax-18h]
0x1800268f8  test    rcx, rcx
0x1800268fb  jz      short loc_180026911
0x1800268fd  mov     rax, [rcx]
0x180026900  mov     rax, [rax+20h]
0x180026904  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026909  mov     rcx, rax
0x18002690c  test    rax, rax
0x18002690f  jnz     short loc_18002692B
0x180026911  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180026918  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18002691f  mov     rax, [rax+20h]
0x180026923  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026928  mov     rcx, rax
0x18002692b  test    rcx, rcx
0x18002692e  jz      short loc_180026945
0x180026930  mov     rax, [rcx]
0x180026933  mov     rax, [rax+18h]
0x180026937  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002693c  add     rax, 18h
0x180026940  mov     [rbx], rax
0x180026943  jmp     short loc_1800268DB
0x180026945  mov     ecx, 80004005h; int
0x18002694a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180026950  mov     ecx, 80070057h; int
0x180026955  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
