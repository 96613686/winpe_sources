# FrameWindow::DismissPopupWindow(void)

- ea: `0x180022204`
- end: `0x18002239b`
- name: `?DismissPopupWindow@FrameWindow@@AEAAXXZ`
- size: `407`
- prototype: `void __fastcall(FrameWindow *__hidden this)`
- caller_count: `5`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800257e0`
- `0x180028a60`
- `0x180028d38`
- `0x1800298b4`
- `0x18002b910`

## callees

- `0x18000193c`
- `0x1800031a4`
- `0x180003858`
- `0x180003880`
- `0x1800039ec`
- `0x18001e894`
- `0x180022204`
- `0x180022b8c`
- `0x1800269a4`
- `0x180035010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18002224e`
- `OLEAUT32!__imp_SysAllocString` at `0x18002224e`
- `OLEAUT32!__imp_VariantClear` at `0x180022236`
- `OLEAUT32!__imp_VariantClear` at `0x1800222a3`
- `OLEAUT32!__imp_VariantClear` at `0x180022236`
- `OLEAUT32!__imp_VariantClear` at `0x1800222a3`
- `OLEAUT32!__imp_VariantCopy` at `0x180022277`
- `OLEAUT32!__imp_VariantCopy` at `0x180022277`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall FrameWindow::DismissPopupWindow(FrameWindow *this)
{
  VARIANTARG *v2; // rbx
  HRESULT v3; // eax
  VARIANTARG **v4; // rax
  VARIANTARG *v5; // r8
  VARIANTARG *v6; // rdx
  VARIANTARG *v7; // rcx
  wchar_t *v8; // rdx
  VARIANTARG *pvargDest[2]; // [rsp+20h] [rbp-30h] BYREF
  VARIANTARG *v10; // [rsp+30h] [rbp-20h]
  VARIANTARG pvarg; // [rsp+38h] [rbp-18h] BYREF
  wchar_t *v12; // [rsp+78h] [rbp+28h] BYREF
  VARIANTARG **v13; // [rsp+80h] [rbp+30h] BYREF
  VARIANTARG ***v14; // [rsp+88h] [rbp+38h]

  FrameWindow::HidePopupWindow(this);
  *(_OWORD *)pvargDest = 0;
  v10 = 0;
  pvarg.vt = 0;
  VariantClear(&pvarg);
  pvarg.vt = 8;
  pvarg.llVal = (LONGLONG)SysAllocString(L"hidePopup");
  if ( !pvarg.llVal )
  {
    pvarg.vt = 10;
    pvarg.lVal = -2147024882;
    ATL::AtlThrowImpl(-2147024882);
  }
  v2 = pvargDest[1];
  if ( pvargDest[1] == v10 )
  {
    std::vector<ATL::CComVariant>::_Emplace_reallocate<ATL::CComVariant>(
      (const VARIANTARG **)pvargDest,
      pvargDest[1],
      &pvarg);
  }
  else
  {
    pvargDest[1]->vt = 0;
    v3 = VariantCopy(v2, &pvarg);
    if ( v3 < 0 )
    {
      v2->vt = 10;
      v2->lVal = v3;
      ATL::AtlThrowImpl(v3);
    }
    ++pvargDest[1];
  }
  VariantClear(&pvarg);
  v14 = &v13;
  v4 = (VARIANTARG **)operator new(0x18u);
  v5 = v10;
  v10 = 0;
  v6 = pvargDest[1];
  pvargDest[1] = 0;
  v7 = pvargDest[0];
  pvargDest[0] = 0;
  *v4 = v7;
  v4[1] = v6;
  v4[2] = v5;
  v13 = v4;
  v12 = (wchar_t *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          &v12,
          0) )
    ATL::CSimpleStringT<unsigned short,0>::Empty(&v12);
  FrameWindow::PostPluginMessage(this, 8, &v12, &v13);
  v8 = v12 - 12;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v12 - 2, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v8 + 8LL))(*(_QWORD *)v8);
  std::vector<ATL::CComVariant>::~vector<ATL::CComVariant>((__int64)pvargDest);
}

```

## disassembly

```asm
0x180022204  mov     [rsp-18h+arg_0], rbx
0x180022209  push    rbp
0x18002220a  push    rdi
0x18002220b  push    r14
0x18002220d  mov     rbp, rsp
0x180022210  sub     rsp, 50h
0x180022214  mov     rdi, rcx
0x180022217  call    ?HidePopupWindow@FrameWindow@@AEAAXXZ; FrameWindow::HidePopupWindow(void)
0x18002221c  xorps   xmm0, xmm0
0x18002221f  movdqu  xmmword ptr [rbp+pvargDest], xmm0
0x180022224  mov     [rbp+var_20], 0
0x18002222c  xor     eax, eax
0x18002222e  mov     word ptr [rbp+pvarg], ax
0x180022232  lea     rcx, [rbp+pvarg]; pvarg
0x180022236  call    cs:__imp_VariantClear
0x18002223c  mov     r14d, 8
0x180022242  mov     word ptr [rbp+pvarg], r14w
0x180022247  lea     rcx, psz; "hidePopup"
0x18002224e  call    cs:__imp_SysAllocString
0x180022254  mov     qword ptr [rbp+pvarg+8], rax
0x180022258  test    rax, rax
0x18002225b  jz      loc_180022384
0x180022261  mov     rbx, [rbp+pvargDest+8]
0x180022265  cmp     rbx, [rbp+var_20]
0x180022269  jz      short loc_18002228E
0x18002226b  xor     eax, eax
0x18002226d  mov     [rbx], ax
0x180022270  lea     rdx, [rbp+pvarg]; pvargSrc
0x180022274  mov     rcx, rbx; pvargDest
0x180022277  call    cs:__imp_VariantCopy
0x18002227d  mov     ecx, eax; int
0x18002227f  test    eax, eax
0x180022281  js      loc_180022376
0x180022287  add     [rbp+pvargDest+8], 18h
0x18002228c  jmp     short loc_18002229F
0x18002228e  lea     r8, [rbp+pvarg]
0x180022292  mov     rdx, rbx
0x180022295  lea     rcx, [rbp+pvargDest]
0x180022299  call    ??$_Emplace_reallocate@VCComVariant@ATL@@@?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@AEAAPEAVCComVariant@ATL@@QEAV23@$$QEAV23@@Z; std::vector<ATL::CComVariant>::_Emplace_reallocate<ATL::CComVariant>(ATL::CComVariant * const,ATL::CComVariant &&)
0x18002229e  nop
0x18002229f  lea     rcx, [rbp+pvarg]; pvarg
0x1800222a3  call    cs:__imp_VariantClear
0x1800222a9  lea     rax, [rbp+arg_10]
0x1800222ad  mov     [rbp+arg_18], rax
0x1800222b1  mov     ecx, 18h; Size
0x1800222b6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800222bb  mov     r8, [rbp+var_20]
0x1800222bf  mov     [rbp+var_20], 0
0x1800222c7  mov     rdx, [rbp+pvargDest+8]
0x1800222cb  mov     [rbp+pvargDest+8], 0
0x1800222d3  mov     rcx, [rbp+pvargDest]
0x1800222d7  mov     [rbp+pvargDest], 0
0x1800222df  mov     [rax], rcx
0x1800222e2  mov     [rax+8], rdx
0x1800222e6  mov     [rax+10h], r8
0x1800222ea  mov     [rbp+arg_10], rax
0x1800222ee  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800222f5  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800222fc  mov     rax, [rax+18h]
0x180022300  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022305  add     rax, 18h
0x180022309  mov     [rbp+arg_8], rax
0x18002230d  xor     edx, edx
0x18002230f  lea     rcx, [rbp+arg_8]
0x180022313  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x180022318  test    al, al
0x18002231a  jnz     short loc_180022326
0x18002231c  lea     rcx, [rbp+arg_8]
0x180022320  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180022325  nop
0x180022326  lea     r9, [rbp+arg_10]
0x18002232a  lea     r8, [rbp+arg_8]
0x18002232e  mov     edx, r14d
0x180022331  mov     rcx, rdi
0x180022334  call    ?PostPluginMessage@FrameWindow@@AEAAXW4PluginId@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$unique_ptr@V?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@U?$default_delete@V?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@@2@@std@@@Z; FrameWindow::PostPluginMessage(PluginId,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,std::unique_ptr<std::vector<ATL::CComVariant>>)
0x180022339  nop
0x18002233a  mov     rdx, [rbp+arg_8]
0x18002233e  add     rdx, 0FFFFFFFFFFFFFFE8h
0x180022342  or      eax, 0FFFFFFFFh
0x180022345  lock xadd [rdx+10h], eax
0x18002234a  sub     eax, 1
0x18002234d  jg      short loc_18002235F
0x18002234f  mov     rcx, [rdx]
0x180022352  mov     rax, [rcx]
0x180022355  mov     rax, [rax+8]
0x180022359  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002235e  nop
0x18002235f  lea     rcx, [rbp+pvargDest]
0x180022363  call    ??1?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@QEAA@XZ; std::vector<ATL::CComVariant>::~vector<ATL::CComVariant>(void)
0x180022368  mov     rbx, [rsp+50h+arg_0]
0x18002236d  add     rsp, 50h
0x180022371  pop     r14
0x180022373  pop     rdi
0x180022374  pop     rbp
0x180022375  retn
0x180022376  mov     word ptr [rbx], 0Ah
0x18002237b  mov     [rbx+8], ecx
0x18002237e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180022384  mov     eax, 0Ah
0x180022389  mov     word ptr [rbp+pvarg], ax
0x18002238d  mov     ecx, 8007000Eh; int
0x180022392  mov     dword ptr [rbp+pvarg+8], ecx
0x180022395  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
