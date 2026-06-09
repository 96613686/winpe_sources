# Accommodation::Accommodation(ushort const *)

- ea: `0x140011204`
- end: `0x1400113a9`
- name: `??0Accommodation@@AEAA@PEBG@Z`
- size: `421`
- prototype: `Accommodation *__fastcall(Accommodation *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400116c4`

## callees

- `0x140004890`
- `0x140007560`
- `0x14000cb50`
- `0x140011204`
- `0x140017010`

## import_xrefs

- `msvcrt!_wcslwr_s` at `0x14001136b`
- `msvcrt!_wcslwr_s` at `0x14001136b`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
Accommodation *__fastcall Accommodation::Accommodation(Accommodation *this, const unsigned __int16 *a2)
{
  __int64 v4; // r8
  __int64 v5; // rdi

  *(_QWORD *)this = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *((_QWORD *)this + 1) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *((_QWORD *)this + 2) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *((_QWORD *)this + 3) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *((_QWORD *)this + 4) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *((_QWORD *)this + 5) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *((_QWORD *)this + 6) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *((_QWORD *)this + 7) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *((_QWORD *)this + 9) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *(_WORD *)((char *)this + 85) = 0;
  if ( a2 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a2[v4] );
  }
  else
  {
    LODWORD(v4) = 0;
  }
  ATL::CSimpleStringT<unsigned short,0>::SetString((__int64 *)this, a2, v4);
  v5 = *(int *)(*(_QWORD *)this - 16LL);
  if ( (int)((*(_DWORD *)(*(_QWORD *)this - 12LL) - v5) | (1 - *(_DWORD *)(*(_QWORD *)this - 8LL))) < 0 )
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(this, (unsigned int)v5);
  _wcslwr_s(*(wchar_t **)this, (int)v5 + 1);
  if ( (int)v5 < 0 || (int)v5 > *(_DWORD *)(*(_QWORD *)this - 12LL) )
    ATL::AtlThrowImpl(-2147024809);
  *(_DWORD *)(*(_QWORD *)this - 16LL) = v5;
  *(_WORD *)(*(_QWORD *)this + 2 * v5) = 0;
  *((_BYTE *)this + 84) = 0;
  return this;
}

```

## disassembly

```asm
0x140011204  mov     [rsp+arg_8], rbx
0x140011209  mov     [rsp+arg_10], rsi
0x14001120e  mov     [rsp+arg_0], rcx
0x140011213  push    rdi
0x140011214  sub     rsp, 20h
0x140011218  mov     rdi, rdx
0x14001121b  mov     rbx, rcx
0x14001121e  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140011225  lea     rsi, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14001122c  mov     rcx, rsi
0x14001122f  mov     rax, [rax+18h]
0x140011233  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011238  add     rax, 18h
0x14001123c  mov     [rbx], rax
0x14001123f  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140011246  mov     rcx, rsi
0x140011249  mov     rax, [rax+18h]
0x14001124d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011252  add     rax, 18h
0x140011256  mov     [rbx+8], rax
0x14001125a  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140011261  mov     rcx, rsi
0x140011264  mov     rax, [rax+18h]
0x140011268  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001126d  add     rax, 18h
0x140011271  mov     [rbx+10h], rax
0x140011275  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14001127c  mov     rcx, rsi
0x14001127f  mov     rax, [rax+18h]
0x140011283  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011288  add     rax, 18h
0x14001128c  mov     [rbx+18h], rax
0x140011290  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140011297  mov     rcx, rsi
0x14001129a  mov     rax, [rax+18h]
0x14001129e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400112a3  add     rax, 18h
0x1400112a7  mov     [rbx+20h], rax
0x1400112ab  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400112b2  mov     rcx, rsi
0x1400112b5  mov     rax, [rax+18h]
0x1400112b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400112be  add     rax, 18h
0x1400112c2  mov     [rbx+28h], rax
0x1400112c6  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400112cd  mov     rcx, rsi
0x1400112d0  mov     rax, [rax+18h]
0x1400112d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400112d9  add     rax, 18h
0x1400112dd  mov     [rbx+30h], rax
0x1400112e1  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400112e8  mov     rcx, rsi
0x1400112eb  mov     rax, [rax+18h]
0x1400112ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400112f4  add     rax, 18h
0x1400112f8  mov     [rbx+38h], rax
0x1400112fc  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140011303  mov     rcx, rsi
0x140011306  mov     rax, [rax+18h]
0x14001130a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001130f  add     rax, 18h
0x140011313  mov     [rbx+48h], rax
0x140011317  xor     esi, esi
0x140011319  mov     [rbx+55h], si
0x14001131d  test    rdi, rdi
0x140011320  jnz     short loc_140011327
0x140011322  mov     r8d, esi
0x140011325  jmp     short loc_140011335
0x140011327  or      r8, 0FFFFFFFFFFFFFFFFh
0x14001132b  inc     r8
0x14001132e  cmp     [rdi+r8*2], si
0x140011333  jnz     short loc_14001132B
0x140011335  mov     rdx, rdi
0x140011338  mov     rcx, rbx
0x14001133b  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x140011340  mov     rax, [rbx]
0x140011343  movsxd  rdi, dword ptr [rax-10h]
0x140011347  mov     ecx, 1
0x14001134c  sub     ecx, [rax-8]
0x14001134f  mov     eax, [rax-0Ch]
0x140011352  sub     eax, edi
0x140011354  or      ecx, eax
0x140011356  jge     short loc_140011362
0x140011358  mov     edx, edi
0x14001135a  mov     rcx, rbx
0x14001135d  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x140011362  lea     eax, [rdi+1]
0x140011365  movsxd  rdx, eax; SizeInWords
0x140011368  mov     rcx, [rbx]; String
0x14001136b  call    cs:__imp__wcslwr_s
0x140011371  test    edi, edi
0x140011373  js      short loc_14001139E
0x140011375  mov     rax, [rbx]
0x140011378  cmp     edi, [rax-0Ch]
0x14001137b  jg      short loc_14001139E
0x14001137d  mov     [rax-10h], edi
0x140011380  mov     rcx, [rbx]
0x140011383  mov     [rcx+rdi*2], si
0x140011387  mov     [rbx+54h], sil
0x14001138b  mov     rax, rbx
0x14001138e  mov     rbx, [rsp+28h+arg_8]
0x140011393  mov     rsi, [rsp+28h+arg_10]
0x140011398  add     rsp, 20h
0x14001139c  pop     rdi
0x14001139d  retn
0x14001139e  mov     ecx, 80070057h; int
0x1400113a3  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
