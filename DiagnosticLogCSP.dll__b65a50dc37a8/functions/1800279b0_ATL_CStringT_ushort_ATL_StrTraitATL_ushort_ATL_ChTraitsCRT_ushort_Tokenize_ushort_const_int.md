# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Tokenize(ushort const *,int &)

- ea: `0x1800279b0`
- end: `0x180027b48`
- name: `?Tokenize@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@PEBGAEAH@Z`
- size: `408`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18001f32c`
- `0x180028664`

## callees

- `0x180011648`
- `0x18001ebc0`
- `0x18001ec68`
- `0x1800279b0`
- `0x180039010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x180027a1b`
- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x180027a1b`
- `api-ms-win-crt-string-l1-1-0!wcsspn` at `0x1800279f5`
- `api-ms-win-crt-string-l1-1-0!wcsspn` at `0x1800279f5`

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
0x1800279b0  push    rbx
0x1800279b2  push    rbp
0x1800279b3  push    rsi
0x1800279b4  push    rdi
0x1800279b5  push    r14
0x1800279b7  push    r15
0x1800279b9  sub     rsp, 38h
0x1800279bd  mov     rsi, r9
0x1800279c0  mov     rbx, rdx
0x1800279c3  mov     rdi, rcx
0x1800279c6  cmp     dword ptr [r9], 0
0x1800279ca  jl      loc_180027B3D
0x1800279d0  mov     r8, [rcx]
0x1800279d3  movsxd  rax, dword ptr [r9]
0x1800279d6  lea     r14, [r8+rax*2]
0x1800279da  movsxd  rax, dword ptr [r8-10h]
0x1800279de  lea     rbp, [r8+rax*2]
0x1800279e2  cmp     r14, rbp
0x1800279e5  jnb     loc_180027AD8
0x1800279eb  lea     rdx, Control; ";"
0x1800279f2  mov     rcx, r14; String
0x1800279f5  call    cs:__imp_wcsspn
0x1800279fc  nop     dword ptr [rax+rax+00h]
0x180027a01  mov     r15, rax
0x180027a04  movsxd  rcx, eax
0x180027a07  lea     rcx, [r14+rcx*2]; String
0x180027a0b  cmp     rcx, rbp
0x180027a0e  jnb     loc_180027AD8
0x180027a14  lea     rdx, Control; ";"
0x180027a1b  call    cs:__imp_wcscspn
0x180027a22  nop     dword ptr [rax+rax+00h]
0x180027a27  mov     edx, [rsi]
0x180027a29  add     edx, r15d
0x180027a2c  lea     ecx, [rax+1]
0x180027a2f  add     ecx, edx
0x180027a31  mov     [rsi], ecx
0x180027a33  xor     esi, esi
0x180027a35  test    edx, edx
0x180027a37  cmovns  esi, edx
0x180027a3a  xor     ecx, ecx
0x180027a3c  test    eax, eax
0x180027a3e  cmovns  ecx, eax
0x180027a41  mov     eax, 7FFFFFFFh
0x180027a46  sub     eax, esi
0x180027a48  cmp     eax, ecx
0x180027a4a  jl      loc_180027B3D
0x180027a50  lea     eax, [rsi+rcx]
0x180027a53  mov     r8, [rdi]
0x180027a56  mov     edx, [r8-10h]
0x180027a5a  cmp     eax, edx
0x180027a5c  jle     short loc_180027A62
0x180027a5e  mov     ecx, edx
0x180027a60  sub     ecx, esi
0x180027a62  xor     ebp, ebp
0x180027a64  cmp     esi, edx
0x180027a66  cmovle  ebp, ecx
0x180027a69  test    esi, esi
0x180027a6b  jnz     short loc_180027A7E
0x180027a6d  cmp     ebp, edx
0x180027a6f  jnz     short loc_180027A7E
0x180027a71  mov     rdx, rdi
0x180027a74  mov     rcx, rbx
0x180027a77  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180027a7c  jmp     short loc_180027AC7
0x180027a7e  mov     rcx, [r8-18h]
0x180027a82  test    rcx, rcx
0x180027a85  jz      short loc_180027A98
0x180027a87  mov     rax, [rcx]
0x180027a8a  mov     rax, [rax+20h]
0x180027a8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027a93  test    rax, rax
0x180027a96  jnz     short loc_180027AAF
0x180027a98  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180027a9f  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180027aa6  mov     rax, [rax+20h]
0x180027aaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027aaf  movsxd  rdx, esi
0x180027ab2  mov     rcx, [rdi]
0x180027ab5  lea     rdx, [rcx+rdx*2]
0x180027ab9  mov     r9, rax
0x180027abc  mov     r8d, ebp
0x180027abf  mov     rcx, rbx
0x180027ac2  call    ??0?$CSimpleStringT@G$0A@@ATL@@QEAA@PEBGHPEAUIAtlStringMgr@1@@Z; ATL::CSimpleStringT<ushort,0>::CSimpleStringT<ushort,0>(ushort const *,int,ATL::IAtlStringMgr *)
0x180027ac7  mov     rax, rbx
0x180027aca  add     rsp, 38h
0x180027ace  pop     r15
0x180027ad0  pop     r14
0x180027ad2  pop     rdi
0x180027ad3  pop     rsi
0x180027ad4  pop     rbp
0x180027ad5  pop     rbx
0x180027ad6  retn
0x180027ad8  mov     dword ptr [rsi], 0FFFFFFFFh
0x180027ade  mov     rax, [rdi]
0x180027ae1  mov     rcx, [rax-18h]
0x180027ae5  test    rcx, rcx
0x180027ae8  jz      short loc_180027AFE
0x180027aea  mov     rax, [rcx]
0x180027aed  mov     rax, [rax+20h]
0x180027af1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027af6  mov     rcx, rax
0x180027af9  test    rax, rax
0x180027afc  jnz     short loc_180027B18
0x180027afe  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180027b05  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180027b0c  mov     rax, [rax+20h]
0x180027b10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027b15  mov     rcx, rax
0x180027b18  test    rcx, rcx
0x180027b1b  jz      short loc_180027B32
0x180027b1d  mov     rax, [rcx]
0x180027b20  mov     rax, [rax+18h]
0x180027b24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027b29  add     rax, 18h
0x180027b2d  mov     [rbx], rax
0x180027b30  jmp     short loc_180027AC7
0x180027b32  mov     ecx, 80004005h; int
0x180027b37  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180027b3d  mov     ecx, 80070057h; int
0x180027b42  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
