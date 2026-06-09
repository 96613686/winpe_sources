# FrameWindow::RefreshPage(void)

- ea: `0x180027df8`
- end: `0x180027f7c`
- name: `?RefreshPage@FrameWindow@@AEAAXXZ`
- size: `388`
- prototype: `void __fastcall(FrameWindow *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800257e0`

## callees

- `0x18000193c`
- `0x1800031a4`
- `0x180003858`
- `0x180003880`
- `0x1800039ec`
- `0x18001e894`
- `0x1800269a4`
- `0x180027df8`
- `0x180035010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180027e36`
- `OLEAUT32!__imp_SysAllocString` at `0x180027e36`
- `OLEAUT32!__imp_VariantClear` at `0x180027e20`
- `OLEAUT32!__imp_VariantClear` at `0x180027e8b`
- `OLEAUT32!__imp_VariantClear` at `0x180027e20`
- `OLEAUT32!__imp_VariantClear` at `0x180027e8b`
- `OLEAUT32!__imp_VariantCopy` at `0x180027e5f`
- `OLEAUT32!__imp_VariantCopy` at `0x180027e5f`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall FrameWindow::RefreshPage(FrameWindow *this)
{
  VARIANTARG *v2; // rbx
  HRESULT v3; // eax
  VARIANTARG **v4; // rax
  VARIANTARG *v5; // r8
  VARIANTARG *v6; // rdx
  VARIANTARG *v7; // rcx
  int *v8; // rdx
  VARIANTARG *pvargDest[2]; // [rsp+20h] [rbp-30h] BYREF
  VARIANTARG *v10; // [rsp+30h] [rbp-20h]
  VARIANTARG pvarg; // [rsp+38h] [rbp-18h] BYREF
  int *v12; // [rsp+78h] [rbp+28h] BYREF
  VARIANTARG **v13; // [rsp+80h] [rbp+30h] BYREF
  VARIANTARG ***v14; // [rsp+88h] [rbp+38h]

  *(_OWORD *)pvargDest = 0;
  v10 = 0;
  pvarg.vt = 0;
  VariantClear(&pvarg);
  pvarg.vt = 8;
  pvarg.llVal = (LONGLONG)SysAllocString(L"refreshPage");
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
  v12 = (int *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (wchar_t **)&v12,
          0) )
    ATL::CSimpleStringT<unsigned short,0>::Empty(&v12);
  FrameWindow::PostPluginMessage(this, 0, &v12, &v13);
  v8 = v12 - 6;
  if ( _InterlockedExchangeAdd(v12 - 2, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v8 + 8LL))(*(_QWORD *)v8);
  std::vector<ATL::CComVariant>::~vector<ATL::CComVariant>((__int64)pvargDest);
}

```

## disassembly

```asm
0x180027df8  push    rbp
0x180027dfa  push    rbx
0x180027dfb  push    rdi
0x180027dfc  mov     rbp, rsp
0x180027dff  sub     rsp, 50h
0x180027e03  mov     rdi, rcx
0x180027e06  xorps   xmm0, xmm0
0x180027e09  movdqu  xmmword ptr [rbp+pvargDest], xmm0
0x180027e0e  mov     [rbp+var_20], 0
0x180027e16  xor     eax, eax
0x180027e18  mov     word ptr [rbp+pvarg], ax
0x180027e1c  lea     rcx, [rbp+pvarg]; pvarg
0x180027e20  call    cs:__imp_VariantClear
0x180027e26  mov     eax, 8
0x180027e2b  mov     word ptr [rbp+pvarg], ax
0x180027e2f  lea     rcx, aRefreshpage; "refreshPage"
0x180027e36  call    cs:__imp_SysAllocString
0x180027e3c  mov     qword ptr [rbp+pvarg+8], rax
0x180027e40  test    rax, rax
0x180027e43  jz      loc_180027F65
0x180027e49  mov     rbx, [rbp+pvargDest+8]
0x180027e4d  cmp     rbx, [rbp+var_20]
0x180027e51  jz      short loc_180027E76
0x180027e53  xor     eax, eax
0x180027e55  mov     [rbx], ax
0x180027e58  lea     rdx, [rbp+pvarg]; pvargSrc
0x180027e5c  mov     rcx, rbx; pvargDest
0x180027e5f  call    cs:__imp_VariantCopy
0x180027e65  mov     ecx, eax; int
0x180027e67  test    eax, eax
0x180027e69  js      loc_180027F57
0x180027e6f  add     [rbp+pvargDest+8], 18h
0x180027e74  jmp     short loc_180027E87
0x180027e76  lea     r8, [rbp+pvarg]
0x180027e7a  mov     rdx, rbx
0x180027e7d  lea     rcx, [rbp+pvargDest]
0x180027e81  call    ??$_Emplace_reallocate@VCComVariant@ATL@@@?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@AEAAPEAVCComVariant@ATL@@QEAV23@$$QEAV23@@Z; std::vector<ATL::CComVariant>::_Emplace_reallocate<ATL::CComVariant>(ATL::CComVariant * const,ATL::CComVariant &&)
0x180027e86  nop
0x180027e87  lea     rcx, [rbp+pvarg]; pvarg
0x180027e8b  call    cs:__imp_VariantClear
0x180027e91  lea     rax, [rbp+arg_10]
0x180027e95  mov     [rbp+arg_18], rax
0x180027e99  mov     ecx, 18h; Size
0x180027e9e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180027ea3  mov     r8, [rbp+var_20]
0x180027ea7  mov     [rbp+var_20], 0
0x180027eaf  mov     rdx, [rbp+pvargDest+8]
0x180027eb3  mov     [rbp+pvargDest+8], 0
0x180027ebb  mov     rcx, [rbp+pvargDest]
0x180027ebf  mov     [rbp+pvargDest], 0
0x180027ec7  mov     [rax], rcx
0x180027eca  mov     [rax+8], rdx
0x180027ece  mov     [rax+10h], r8
0x180027ed2  mov     [rbp+arg_10], rax
0x180027ed6  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180027edd  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180027ee4  mov     rax, [rax+18h]
0x180027ee8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027eed  add     rax, 18h
0x180027ef1  mov     [rbp+arg_8], rax
0x180027ef5  xor     edx, edx
0x180027ef7  lea     rcx, [rbp+arg_8]
0x180027efb  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x180027f00  test    al, al
0x180027f02  jnz     short loc_180027F0E
0x180027f04  lea     rcx, [rbp+arg_8]
0x180027f08  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180027f0d  nop
0x180027f0e  lea     r9, [rbp+arg_10]
0x180027f12  lea     r8, [rbp+arg_8]
0x180027f16  xor     edx, edx
0x180027f18  mov     rcx, rdi
0x180027f1b  call    ?PostPluginMessage@FrameWindow@@AEAAXW4PluginId@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$unique_ptr@V?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@U?$default_delete@V?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@@2@@std@@@Z; FrameWindow::PostPluginMessage(PluginId,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,std::unique_ptr<std::vector<ATL::CComVariant>>)
0x180027f20  nop
0x180027f21  mov     rdx, [rbp+arg_8]
0x180027f25  add     rdx, 0FFFFFFFFFFFFFFE8h
0x180027f29  or      eax, 0FFFFFFFFh
0x180027f2c  lock xadd [rdx+10h], eax
0x180027f31  sub     eax, 1
0x180027f34  jg      short loc_180027F46
0x180027f36  mov     rcx, [rdx]
0x180027f39  mov     rax, [rcx]
0x180027f3c  mov     rax, [rax+8]
0x180027f40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027f45  nop
0x180027f46  lea     rcx, [rbp+pvargDest]
0x180027f4a  call    ??1?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@QEAA@XZ; std::vector<ATL::CComVariant>::~vector<ATL::CComVariant>(void)
0x180027f4f  add     rsp, 50h
0x180027f53  pop     rdi
0x180027f54  pop     rbx
0x180027f55  pop     rbp
0x180027f56  retn
0x180027f57  mov     word ptr [rbx], 0Ah
0x180027f5c  mov     [rbx+8], ecx
0x180027f5f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180027f65  mov     eax, 0Ah
0x180027f6a  mov     word ptr [rbp+pvarg], ax
0x180027f6e  mov     ecx, 8007000Eh; int
0x180027f73  mov     dword ptr [rbp+pvarg+8], ecx
0x180027f76  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
