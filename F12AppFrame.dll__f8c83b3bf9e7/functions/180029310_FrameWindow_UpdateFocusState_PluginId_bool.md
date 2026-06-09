# FrameWindow::UpdateFocusState(PluginId,bool)

- ea: `0x180029310`
- end: `0x18002951a`
- name: `?UpdateFocusState@FrameWindow@@AEAAXW4PluginId@@_N@Z`
- size: `522`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180023220`
- `0x180028834`

## callees

- `0x18000193c`
- `0x1800031a4`
- `0x180003858`
- `0x180003880`
- `0x1800039ec`
- `0x18001e894`
- `0x1800269a4`
- `0x180029310`
- `0x180035010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180029358`
- `OLEAUT32!__imp_SysAllocString` at `0x180029358`
- `OLEAUT32!__imp_VariantClear` at `0x180029342`
- `OLEAUT32!__imp_VariantClear` at `0x1800293ad`
- `OLEAUT32!__imp_VariantClear` at `0x180029414`
- `OLEAUT32!__imp_VariantClear` at `0x180029342`
- `OLEAUT32!__imp_VariantClear` at `0x1800293ad`
- `OLEAUT32!__imp_VariantClear` at `0x180029414`
- `OLEAUT32!__imp_VariantCopy` at `0x180029381`
- `OLEAUT32!__imp_VariantCopy` at `0x1800293e8`
- `OLEAUT32!__imp_VariantCopy` at `0x180029381`
- `OLEAUT32!__imp_VariantCopy` at `0x1800293e8`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall FrameWindow::UpdateFocusState(__int64 a1, unsigned int a2, char a3)
{
  VARIANTARG *v6; // rbx
  HRESULT v7; // eax
  VARIANTARG *v8; // rbx
  HRESULT v9; // eax
  VARIANTARG **v10; // rax
  VARIANTARG *v11; // r8
  VARIANTARG *v12; // rdx
  VARIANTARG *v13; // rcx
  int *v14; // rdx
  _QWORD v15[2]; // [rsp+20h] [rbp-48h] BYREF
  VARIANTARG *pvargDest[2]; // [rsp+30h] [rbp-38h] BYREF
  VARIANTARG *v17; // [rsp+40h] [rbp-28h]
  VARIANTARG pvarg; // [rsp+48h] [rbp-20h] BYREF
  int *v19; // [rsp+B8h] [rbp+50h] BYREF

  *(_OWORD *)pvargDest = 0;
  v17 = 0;
  pvarg.vt = 0;
  VariantClear(&pvarg);
  pvarg.vt = 8;
  pvarg.llVal = (LONGLONG)SysAllocString(L"showfocus");
  if ( !pvarg.llVal )
  {
    pvarg.vt = 10;
    pvarg.lVal = -2147024882;
    ATL::AtlThrowImpl(-2147024882);
  }
  v6 = pvargDest[1];
  if ( pvargDest[1] == v17 )
  {
    std::vector<ATL::CComVariant>::_Emplace_reallocate<ATL::CComVariant>(
      (const VARIANTARG **)pvargDest,
      pvargDest[1],
      &pvarg);
  }
  else
  {
    pvargDest[1]->vt = 0;
    v7 = VariantCopy(v6, &pvarg);
    if ( v7 < 0 )
    {
      v6->vt = 10;
      v6->lVal = v7;
      ATL::AtlThrowImpl(v7);
    }
    ++pvargDest[1];
  }
  VariantClear(&pvarg);
  pvarg.vt = 11;
  if ( a3 )
    pvarg.iVal = -1;
  else
    pvarg.iVal = 0;
  v8 = pvargDest[1];
  if ( pvargDest[1] == v17 )
  {
    std::vector<ATL::CComVariant>::_Emplace_reallocate<ATL::CComVariant>(
      (const VARIANTARG **)pvargDest,
      pvargDest[1],
      &pvarg);
  }
  else
  {
    pvargDest[1]->vt = 0;
    v9 = VariantCopy(v8, &pvarg);
    if ( v9 < 0 )
    {
      v8->vt = 10;
      v8->lVal = v9;
      ATL::AtlThrowImpl(v9);
    }
    ++pvargDest[1];
  }
  VariantClear(&pvarg);
  v15[1] = v15;
  v10 = (VARIANTARG **)operator new(0x18u);
  v11 = v17;
  v17 = 0;
  v12 = pvargDest[1];
  pvargDest[1] = 0;
  v13 = pvargDest[0];
  pvargDest[0] = 0;
  *v10 = v13;
  v10[1] = v12;
  v10[2] = v11;
  v15[0] = v10;
  v19 = (int *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (wchar_t **)&v19,
          0) )
    ATL::CSimpleStringT<unsigned short,0>::Empty(&v19);
  FrameWindow::PostPluginMessage(a1, a2, &v19, v15);
  v14 = v19 - 6;
  if ( _InterlockedDecrement(v19 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v14 + 8LL))(*(_QWORD *)v14);
  std::vector<ATL::CComVariant>::~vector<ATL::CComVariant>((__int64)pvargDest);
}

```

## disassembly

```asm
0x180029310  push    rbp
0x180029312  push    rbx
0x180029313  push    rsi
0x180029314  push    rdi
0x180029315  push    r12
0x180029317  push    r14
0x180029319  mov     rbp, rsp
0x18002931c  sub     rsp, 68h
0x180029320  mov     dil, r8b
0x180029323  mov     esi, edx
0x180029325  mov     r14, rcx
0x180029328  xorps   xmm0, xmm0
0x18002932b  movdqu  xmmword ptr [rbp+pvargDest], xmm0
0x180029330  mov     [rbp+var_28], 0
0x180029338  xor     eax, eax
0x18002933a  mov     word ptr [rbp+pvarg], ax
0x18002933e  lea     rcx, [rbp+pvarg]; pvarg
0x180029342  call    cs:__imp_VariantClear
0x180029348  mov     eax, 8
0x18002934d  mov     word ptr [rbp+pvarg], ax
0x180029351  lea     rcx, aShowfocus; "showfocus"
0x180029358  call    cs:__imp_SysAllocString
0x18002935e  mov     qword ptr [rbp+pvarg+8], rax
0x180029362  test    rax, rax
0x180029365  jz      loc_1800294F5
0x18002936b  mov     rbx, [rbp+pvargDest+8]
0x18002936f  cmp     rbx, [rbp+var_28]
0x180029373  jz      short loc_180029398
0x180029375  xor     eax, eax
0x180029377  mov     [rbx], ax
0x18002937a  lea     rdx, [rbp+pvarg]; pvargSrc
0x18002937e  mov     rcx, rbx; pvargDest
0x180029381  call    cs:__imp_VariantCopy
0x180029387  mov     ecx, eax; int
0x180029389  test    eax, eax
0x18002938b  js      loc_18002950C
0x180029391  add     [rbp+pvargDest+8], 18h
0x180029396  jmp     short loc_1800293A9
0x180029398  lea     r8, [rbp+pvarg]
0x18002939c  mov     rdx, rbx
0x18002939f  lea     rcx, [rbp+pvargDest]
0x1800293a3  call    ??$_Emplace_reallocate@VCComVariant@ATL@@@?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@AEAAPEAVCComVariant@ATL@@QEAV23@$$QEAV23@@Z; std::vector<ATL::CComVariant>::_Emplace_reallocate<ATL::CComVariant>(ATL::CComVariant * const,ATL::CComVariant &&)
0x1800293a8  nop
0x1800293a9  lea     rcx, [rbp+pvarg]; pvarg
0x1800293ad  call    cs:__imp_VariantClear
0x1800293b3  mov     eax, 0Bh
0x1800293b8  mov     word ptr [rbp+pvarg], ax
0x1800293bc  or      r12d, 0FFFFFFFFh
0x1800293c0  test    dil, dil
0x1800293c3  jz      short loc_1800293CC
0x1800293c5  mov     word ptr [rbp+pvarg+8], r12w
0x1800293ca  jmp     short loc_1800293D2
0x1800293cc  xor     eax, eax
0x1800293ce  mov     word ptr [rbp+pvarg+8], ax
0x1800293d2  mov     rbx, [rbp+pvargDest+8]
0x1800293d6  cmp     rbx, [rbp+var_28]
0x1800293da  jz      short loc_1800293FF
0x1800293dc  xor     eax, eax
0x1800293de  mov     [rbx], ax
0x1800293e1  lea     rdx, [rbp+pvarg]; pvargSrc
0x1800293e5  mov     rcx, rbx; pvargDest
0x1800293e8  call    cs:__imp_VariantCopy
0x1800293ee  mov     ecx, eax; int
0x1800293f0  test    eax, eax
0x1800293f2  js      loc_1800294E7
0x1800293f8  add     [rbp+pvargDest+8], 18h
0x1800293fd  jmp     short loc_180029410
0x1800293ff  lea     r8, [rbp+pvarg]
0x180029403  mov     rdx, rbx
0x180029406  lea     rcx, [rbp+pvargDest]
0x18002940a  call    ??$_Emplace_reallocate@VCComVariant@ATL@@@?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@AEAAPEAVCComVariant@ATL@@QEAV23@$$QEAV23@@Z; std::vector<ATL::CComVariant>::_Emplace_reallocate<ATL::CComVariant>(ATL::CComVariant * const,ATL::CComVariant &&)
0x18002940f  nop
0x180029410  lea     rcx, [rbp+pvarg]; pvarg
0x180029414  call    cs:__imp_VariantClear
0x18002941a  lea     rax, [rbp+var_48]
0x18002941e  mov     [rbp+var_40], rax
0x180029422  mov     ecx, 18h; Size
0x180029427  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002942c  mov     r8, [rbp+var_28]
0x180029430  mov     [rbp+var_28], 0
0x180029438  mov     rdx, [rbp+pvargDest+8]
0x18002943c  mov     [rbp+pvargDest+8], 0
0x180029444  mov     rcx, [rbp+pvargDest]
0x180029448  mov     [rbp+pvargDest], 0
0x180029450  mov     [rax], rcx
0x180029453  mov     [rax+8], rdx
0x180029457  mov     [rax+10h], r8
0x18002945b  mov     [rbp+var_48], rax
0x18002945f  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180029466  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18002946d  mov     rax, [rax+18h]
0x180029471  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029476  add     rax, 18h
0x18002947a  mov     [rbp+arg_18], rax
0x18002947e  xor     edx, edx
0x180029480  lea     rcx, [rbp+arg_18]
0x180029484  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x180029489  test    al, al
0x18002948b  jnz     short loc_180029497
0x18002948d  lea     rcx, [rbp+arg_18]
0x180029491  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180029496  nop
0x180029497  lea     r9, [rbp+var_48]
0x18002949b  lea     r8, [rbp+arg_18]
0x18002949f  mov     edx, esi
0x1800294a1  mov     rcx, r14
0x1800294a4  call    ?PostPluginMessage@FrameWindow@@AEAAXW4PluginId@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$unique_ptr@V?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@U?$default_delete@V?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@@2@@std@@@Z; FrameWindow::PostPluginMessage(PluginId,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,std::unique_ptr<std::vector<ATL::CComVariant>>)
0x1800294a9  nop
0x1800294aa  mov     rdx, [rbp+arg_18]
0x1800294ae  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1800294b2  mov     eax, r12d
0x1800294b5  lock xadd [rdx+10h], eax
0x1800294ba  add     eax, r12d
0x1800294bd  test    eax, eax
0x1800294bf  jg      short loc_1800294D1
0x1800294c1  mov     rcx, [rdx]
0x1800294c4  mov     rax, [rcx]
0x1800294c7  mov     rax, [rax+8]
0x1800294cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800294d0  nop
0x1800294d1  lea     rcx, [rbp+pvargDest]
0x1800294d5  call    ??1?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@QEAA@XZ; std::vector<ATL::CComVariant>::~vector<ATL::CComVariant>(void)
0x1800294da  add     rsp, 68h
0x1800294de  pop     r14
0x1800294e0  pop     r12
0x1800294e2  pop     rdi
0x1800294e3  pop     rsi
0x1800294e4  pop     rbx
0x1800294e5  pop     rbp
0x1800294e6  retn
0x1800294e7  mov     word ptr [rbx], 0Ah
0x1800294ec  mov     [rbx+8], ecx
0x1800294ef  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800294f5  mov     eax, 0Ah
0x1800294fa  mov     word ptr [rbp+pvarg], ax
0x1800294fe  mov     ecx, 8007000Eh; int
0x180029503  mov     dword ptr [rbp+pvarg+8], ecx
0x180029506  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002950c  mov     word ptr [rbx], 0Ah
0x180029511  mov     [rbx+8], ecx
0x180029514  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
