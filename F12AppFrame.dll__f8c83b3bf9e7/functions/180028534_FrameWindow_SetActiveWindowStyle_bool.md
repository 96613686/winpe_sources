# FrameWindow::SetActiveWindowStyle(bool)

- ea: `0x180028534`
- end: `0x180028744`
- name: `?SetActiveWindowStyle@FrameWindow@@AEAAX_N@Z`
- size: `528`
- prototype: `void __fastcall(FrameWindow *__hidden this, bool)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800257e0`
- `0x18002b910`

## callees

- `0x18000193c`
- `0x1800031a4`
- `0x180003858`
- `0x180003880`
- `0x1800039ec`
- `0x18001e894`
- `0x1800269a4`
- `0x180028534`
- `0x180035010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18002857d`
- `OLEAUT32!__imp_SysAllocString` at `0x18002857d`
- `OLEAUT32!__imp_VariantClear` at `0x180028567`
- `OLEAUT32!__imp_VariantClear` at `0x1800285d2`
- `OLEAUT32!__imp_VariantClear` at `0x18002863d`
- `OLEAUT32!__imp_VariantClear` at `0x180028567`
- `OLEAUT32!__imp_VariantClear` at `0x1800285d2`
- `OLEAUT32!__imp_VariantClear` at `0x18002863d`
- `OLEAUT32!__imp_VariantCopy` at `0x1800285a6`
- `OLEAUT32!__imp_VariantCopy` at `0x180028611`
- `OLEAUT32!__imp_VariantCopy` at `0x1800285a6`
- `OLEAUT32!__imp_VariantCopy` at `0x180028611`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall FrameWindow::SetActiveWindowStyle(FrameWindow *this, char a2)
{
  VARIANTARG *v3; // rbx
  HRESULT v4; // eax
  VARIANTARG *v5; // rbx
  HRESULT v6; // eax
  VARIANTARG **v7; // rax
  VARIANTARG *v8; // r8
  VARIANTARG *v9; // rdx
  VARIANTARG *v10; // rcx
  int *v11; // rdx
  VARIANTARG *pvargDest[2]; // [rsp+20h] [rbp-30h] BYREF
  VARIANTARG *v13; // [rsp+30h] [rbp-20h]
  VARIANTARG pvarg; // [rsp+38h] [rbp-18h] BYREF
  int *v15; // [rsp+70h] [rbp+20h] BYREF
  VARIANTARG **v16; // [rsp+80h] [rbp+30h] BYREF
  VARIANTARG ***v17; // [rsp+88h] [rbp+38h]

  *((_BYTE *)this + 688) = a2;
  *(_OWORD *)pvargDest = 0;
  v13 = 0;
  pvarg.vt = 0;
  VariantClear(&pvarg);
  pvarg.vt = 8;
  pvarg.llVal = (LONGLONG)SysAllocString(L"windowActivation");
  if ( !pvarg.llVal )
  {
    pvarg.vt = 10;
    pvarg.lVal = -2147024882;
    ATL::AtlThrowImpl(-2147024882);
  }
  v3 = pvargDest[1];
  if ( pvargDest[1] == v13 )
  {
    std::vector<ATL::CComVariant>::_Emplace_reallocate<ATL::CComVariant>(
      (const VARIANTARG **)pvargDest,
      pvargDest[1],
      &pvarg);
  }
  else
  {
    pvargDest[1]->vt = 0;
    v4 = VariantCopy(v3, &pvarg);
    if ( v4 < 0 )
    {
      v3->vt = 10;
      v3->lVal = v4;
      ATL::AtlThrowImpl(v4);
    }
    ++pvargDest[1];
  }
  VariantClear(&pvarg);
  pvarg.vt = 11;
  if ( *((_BYTE *)this + 688) )
    pvarg.iVal = -1;
  else
    pvarg.iVal = 0;
  v5 = pvargDest[1];
  if ( pvargDest[1] == v13 )
  {
    std::vector<ATL::CComVariant>::_Emplace_reallocate<ATL::CComVariant>(
      (const VARIANTARG **)pvargDest,
      pvargDest[1],
      &pvarg);
  }
  else
  {
    pvargDest[1]->vt = 0;
    v6 = VariantCopy(v5, &pvarg);
    if ( v6 < 0 )
    {
      v5->vt = 10;
      v5->lVal = v6;
      ATL::AtlThrowImpl(v6);
    }
    ++pvargDest[1];
  }
  VariantClear(&pvarg);
  v17 = &v16;
  v7 = (VARIANTARG **)operator new(0x18u);
  v8 = v13;
  v13 = 0;
  v9 = pvargDest[1];
  pvargDest[1] = 0;
  v10 = pvargDest[0];
  pvargDest[0] = 0;
  *v7 = v10;
  v7[1] = v9;
  v7[2] = v8;
  v16 = v7;
  v15 = (int *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (wchar_t **)&v15,
          0) )
    ATL::CSimpleStringT<unsigned short,0>::Empty(&v15);
  FrameWindow::PostPluginMessage(this, 0, &v15, &v16);
  v11 = v15 - 6;
  if ( _InterlockedDecrement(v15 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v11 + 8LL))(*(_QWORD *)v11);
  std::vector<ATL::CComVariant>::~vector<ATL::CComVariant>((__int64)pvargDest);
}

```

## disassembly

```asm
0x180028534  mov     [rsp-18h+arg_8], rbx
0x180028539  push    rbp
0x18002853a  push    rdi
0x18002853b  push    r14
0x18002853d  mov     rbp, rsp
0x180028540  sub     rsp, 50h
0x180028544  mov     rdi, rcx
0x180028547  mov     [rcx+2B0h], dl
0x18002854d  xorps   xmm0, xmm0
0x180028550  movdqu  xmmword ptr [rbp+pvargDest], xmm0
0x180028555  mov     [rbp+var_20], 0
0x18002855d  xor     eax, eax
0x18002855f  mov     word ptr [rbp+pvarg], ax
0x180028563  lea     rcx, [rbp+pvarg]; pvarg
0x180028567  call    cs:__imp_VariantClear
0x18002856d  mov     eax, 8
0x180028572  mov     word ptr [rbp+pvarg], ax
0x180028576  lea     rcx, aWindowactivati; "windowActivation"
0x18002857d  call    cs:__imp_SysAllocString
0x180028583  mov     qword ptr [rbp+pvarg+8], rax
0x180028587  test    rax, rax
0x18002858a  jz      loc_18002871F
0x180028590  mov     rbx, [rbp+pvargDest+8]
0x180028594  cmp     rbx, [rbp+var_20]
0x180028598  jz      short loc_1800285BD
0x18002859a  xor     eax, eax
0x18002859c  mov     [rbx], ax
0x18002859f  lea     rdx, [rbp+pvarg]; pvargSrc
0x1800285a3  mov     rcx, rbx; pvargDest
0x1800285a6  call    cs:__imp_VariantCopy
0x1800285ac  mov     ecx, eax; int
0x1800285ae  test    eax, eax
0x1800285b0  js      loc_180028736
0x1800285b6  add     [rbp+pvargDest+8], 18h
0x1800285bb  jmp     short loc_1800285CE
0x1800285bd  lea     r8, [rbp+pvarg]
0x1800285c1  mov     rdx, rbx
0x1800285c4  lea     rcx, [rbp+pvargDest]
0x1800285c8  call    ??$_Emplace_reallocate@VCComVariant@ATL@@@?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@AEAAPEAVCComVariant@ATL@@QEAV23@$$QEAV23@@Z; std::vector<ATL::CComVariant>::_Emplace_reallocate<ATL::CComVariant>(ATL::CComVariant * const,ATL::CComVariant &&)
0x1800285cd  nop
0x1800285ce  lea     rcx, [rbp+pvarg]; pvarg
0x1800285d2  call    cs:__imp_VariantClear
0x1800285d8  mov     eax, 0Bh
0x1800285dd  mov     word ptr [rbp+pvarg], ax
0x1800285e1  or      r14d, 0FFFFFFFFh
0x1800285e5  cmp     byte ptr [rdi+2B0h], 0
0x1800285ec  jz      short loc_1800285F5
0x1800285ee  mov     word ptr [rbp+pvarg+8], r14w
0x1800285f3  jmp     short loc_1800285FB
0x1800285f5  xor     eax, eax
0x1800285f7  mov     word ptr [rbp+pvarg+8], ax
0x1800285fb  mov     rbx, [rbp+pvargDest+8]
0x1800285ff  cmp     rbx, [rbp+var_20]
0x180028603  jz      short loc_180028628
0x180028605  xor     eax, eax
0x180028607  mov     [rbx], ax
0x18002860a  lea     rdx, [rbp+pvarg]; pvargSrc
0x18002860e  mov     rcx, rbx; pvargDest
0x180028611  call    cs:__imp_VariantCopy
0x180028617  mov     ecx, eax; int
0x180028619  test    eax, eax
0x18002861b  js      loc_180028711
0x180028621  add     [rbp+pvargDest+8], 18h
0x180028626  jmp     short loc_180028639
0x180028628  lea     r8, [rbp+pvarg]
0x18002862c  mov     rdx, rbx
0x18002862f  lea     rcx, [rbp+pvargDest]
0x180028633  call    ??$_Emplace_reallocate@VCComVariant@ATL@@@?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@AEAAPEAVCComVariant@ATL@@QEAV23@$$QEAV23@@Z; std::vector<ATL::CComVariant>::_Emplace_reallocate<ATL::CComVariant>(ATL::CComVariant * const,ATL::CComVariant &&)
0x180028638  nop
0x180028639  lea     rcx, [rbp+pvarg]; pvarg
0x18002863d  call    cs:__imp_VariantClear
0x180028643  lea     rax, [rbp+arg_10]
0x180028647  mov     [rbp+arg_18], rax
0x18002864b  mov     ecx, 18h; Size
0x180028650  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180028655  mov     r8, [rbp+var_20]
0x180028659  mov     [rbp+var_20], 0
0x180028661  mov     rdx, [rbp+pvargDest+8]
0x180028665  mov     [rbp+pvargDest+8], 0
0x18002866d  mov     rcx, [rbp+pvargDest]
0x180028671  mov     [rbp+pvargDest], 0
0x180028679  mov     [rax], rcx
0x18002867c  mov     [rax+8], rdx
0x180028680  mov     [rax+10h], r8
0x180028684  mov     [rbp+arg_10], rax
0x180028688  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18002868f  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180028696  mov     rax, [rax+18h]
0x18002869a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002869f  add     rax, 18h
0x1800286a3  mov     [rbp+arg_0], rax
0x1800286a7  xor     edx, edx
0x1800286a9  lea     rcx, [rbp+arg_0]
0x1800286ad  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x1800286b2  test    al, al
0x1800286b4  jnz     short loc_1800286C0
0x1800286b6  lea     rcx, [rbp+arg_0]
0x1800286ba  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x1800286bf  nop
0x1800286c0  lea     r9, [rbp+arg_10]
0x1800286c4  lea     r8, [rbp+arg_0]
0x1800286c8  xor     edx, edx
0x1800286ca  mov     rcx, rdi
0x1800286cd  call    ?PostPluginMessage@FrameWindow@@AEAAXW4PluginId@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$unique_ptr@V?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@U?$default_delete@V?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@@2@@std@@@Z; FrameWindow::PostPluginMessage(PluginId,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,std::unique_ptr<std::vector<ATL::CComVariant>>)
0x1800286d2  nop
0x1800286d3  mov     rdx, [rbp+arg_0]
0x1800286d7  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1800286db  mov     eax, r14d
0x1800286de  lock xadd [rdx+10h], eax
0x1800286e3  add     eax, r14d
0x1800286e6  test    eax, eax
0x1800286e8  jg      short loc_1800286FA
0x1800286ea  mov     rcx, [rdx]
0x1800286ed  mov     rax, [rcx]
0x1800286f0  mov     rax, [rax+8]
0x1800286f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800286f9  nop
0x1800286fa  lea     rcx, [rbp+pvargDest]
0x1800286fe  call    ??1?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@QEAA@XZ; std::vector<ATL::CComVariant>::~vector<ATL::CComVariant>(void)
0x180028703  mov     rbx, [rsp+50h+arg_8]
0x180028708  add     rsp, 50h
0x18002870c  pop     r14
0x18002870e  pop     rdi
0x18002870f  pop     rbp
0x180028710  retn
0x180028711  mov     word ptr [rbx], 0Ah
0x180028716  mov     [rbx+8], ecx
0x180028719  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002871f  mov     eax, 0Ah
0x180028724  mov     word ptr [rbp+pvarg], ax
0x180028728  mov     ecx, 8007000Eh; int
0x18002872d  mov     dword ptr [rbp+pvarg+8], ecx
0x180028730  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180028736  mov     word ptr [rbx], 0Ah
0x18002873b  mov     [rbx+8], ecx
0x18002873e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
