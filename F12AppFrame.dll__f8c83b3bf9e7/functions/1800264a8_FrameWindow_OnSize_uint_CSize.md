# FrameWindow::OnSize(uint,CSize)

- ea: `0x1800264a8`
- end: `0x180026703`
- name: `?OnSize@FrameWindow@@QEAAXIVCSize@@@Z`
- size: `603`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180022a0c`
- `0x1800257e0`
- `0x18002b910`

## callees

- `0x18000193c`
- `0x1800031a4`
- `0x180003858`
- `0x180003880`
- `0x1800039ec`
- `0x18001e894`
- `0x1800264a8`
- `0x1800269a4`
- `0x1800282e0`
- `0x180035010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180026553`
- `OLEAUT32!__imp_SysAllocString` at `0x180026553`
- `OLEAUT32!__imp_VariantClear` at `0x18002653d`
- `OLEAUT32!__imp_VariantClear` at `0x1800265a8`
- `OLEAUT32!__imp_VariantClear` at `0x1800265fc`
- `OLEAUT32!__imp_VariantClear` at `0x18002653d`
- `OLEAUT32!__imp_VariantClear` at `0x1800265a8`
- `OLEAUT32!__imp_VariantClear` at `0x1800265fc`
- `OLEAUT32!__imp_VariantCopy` at `0x18002657c`
- `OLEAUT32!__imp_VariantCopy` at `0x1800265d0`
- `OLEAUT32!__imp_VariantCopy` at `0x18002657c`
- `OLEAUT32!__imp_VariantCopy` at `0x1800265d0`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall FrameWindow::OnSize(__int64 a1, LONG a2, __int64 a3)
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
  VARIANTARG *pvargDest[2]; // [rsp+38h] [rbp-38h] BYREF
  VARIANTARG *v16; // [rsp+48h] [rbp-28h]
  VARIANTARG pvarg; // [rsp+50h] [rbp-20h] BYREF
  int *v18; // [rsp+90h] [rbp+20h] BYREF
  __int64 v19; // [rsp+A0h] [rbp+30h]
  VARIANTARG **v20; // [rsp+A8h] [rbp+38h] BYREF

  v19 = a3;
  (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**(_QWORD **)(a1 + 712) + 48LL))(
    *(_QWORD *)(a1 + 712),
    *(unsigned int *)(a1 + 552),
    *(unsigned __int8 *)(a1 + 435),
    *(unsigned __int8 *)(a1 + 441));
  (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**(_QWORD **)(a1 + 712) + 40LL))(
    *(_QWORD *)(a1 + 712),
    (unsigned int)a3,
    HIDWORD(v19));
  FrameWindow::Resize(a1, a3);
  if ( a2 != *(_DWORD *)(a1 + 632) )
  {
    *(_DWORD *)(a1 + 632) = a2;
    *(_OWORD *)pvargDest = 0;
    v16 = 0;
    pvarg.vt = 0;
    VariantClear(&pvarg);
    pvarg.vt = 8;
    pvarg.llVal = (LONGLONG)SysAllocString(L"windowstatechanged");
    if ( !pvarg.llVal )
    {
      pvarg.vt = 10;
      pvarg.lVal = -2147024882;
      ATL::AtlThrowImpl(-2147024882);
    }
    v6 = pvargDest[1];
    if ( pvargDest[1] == v16 )
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
    pvarg.vt = 19;
    pvarg.lVal = a2;
    v8 = pvargDest[1];
    if ( pvargDest[1] == v16 )
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
    v10 = (VARIANTARG **)operator new(0x18u);
    v11 = v16;
    v16 = 0;
    v12 = pvargDest[1];
    pvargDest[1] = 0;
    v13 = pvargDest[0];
    pvargDest[0] = 0;
    *v10 = v13;
    v10[1] = v12;
    v10[2] = v11;
    v20 = v10;
    v18 = (int *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
    if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
            (wchar_t **)&v18,
            0) )
      ATL::CSimpleStringT<unsigned short,0>::Empty(&v18);
    FrameWindow::PostPluginMessage(a1, 0, &v18, &v20);
    v14 = v18 - 6;
    if ( _InterlockedExchangeAdd(v18 - 2, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v14 + 8LL))(*(_QWORD *)v14);
    std::vector<ATL::CComVariant>::~vector<ATL::CComVariant>((__int64)pvargDest);
  }
}

```

## disassembly

```asm
0x1800264a8  mov     [rsp-18h+arg_8], rbx
0x1800264ad  mov     [rsp-18h+arg_10], r8
0x1800264b2  push    rbp
0x1800264b3  push    rsi
0x1800264b4  push    rdi
0x1800264b5  mov     rbp, rsp
0x1800264b8  sub     rsp, 70h
0x1800264bc  mov     rbx, r8
0x1800264bf  mov     esi, edx
0x1800264c1  mov     rdi, rcx
0x1800264c4  mov     rcx, [rcx+2C8h]
0x1800264cb  mov     rax, [rcx]
0x1800264ce  movzx   r9d, byte ptr [rdi+1B9h]
0x1800264d6  movzx   r8d, byte ptr [rdi+1B3h]
0x1800264de  mov     edx, [rdi+228h]
0x1800264e4  mov     rax, [rax+30h]
0x1800264e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800264ed  mov     rcx, [rdi+2C8h]
0x1800264f4  mov     rax, [rcx]
0x1800264f7  mov     r8d, dword ptr [rbp+arg_10+4]
0x1800264fb  mov     edx, ebx
0x1800264fd  mov     rax, [rax+28h]
0x180026501  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026506  mov     rdx, rbx
0x180026509  mov     rcx, rdi
0x18002650c  call    ?Resize@FrameWindow@@AEAAXVCSize@@@Z; FrameWindow::Resize(CSize)
0x180026511  cmp     esi, [rdi+278h]
0x180026517  jz      loc_1800266C0
0x18002651d  mov     [rdi+278h], esi
0x180026523  xorps   xmm0, xmm0
0x180026526  movdqu  xmmword ptr [rbp+pvargDest], xmm0
0x18002652b  mov     [rbp+var_28], 0
0x180026533  xor     eax, eax
0x180026535  mov     word ptr [rbp+pvarg], ax
0x180026539  lea     rcx, [rbp+pvarg]; pvarg
0x18002653d  call    cs:__imp_VariantClear
0x180026543  mov     eax, 8
0x180026548  mov     word ptr [rbp+pvarg], ax
0x18002654c  lea     rcx, aWindowstatecha; "windowstatechanged"
0x180026553  call    cs:__imp_SysAllocString
0x180026559  mov     qword ptr [rbp+pvarg+8], rax
0x18002655d  test    rax, rax
0x180026560  jz      loc_1800266DE
0x180026566  mov     rbx, [rbp+pvargDest+8]
0x18002656a  cmp     rbx, [rbp+var_28]
0x18002656e  jz      short loc_180026593
0x180026570  xor     eax, eax
0x180026572  mov     [rbx], ax
0x180026575  lea     rdx, [rbp+pvarg]; pvargSrc
0x180026579  mov     rcx, rbx; pvargDest
0x18002657c  call    cs:__imp_VariantCopy
0x180026582  mov     ecx, eax; int
0x180026584  test    eax, eax
0x180026586  js      loc_1800266F5
0x18002658c  add     [rbp+pvargDest+8], 18h
0x180026591  jmp     short loc_1800265A4
0x180026593  lea     r8, [rbp+pvarg]
0x180026597  mov     rdx, rbx
0x18002659a  lea     rcx, [rbp+pvargDest]
0x18002659e  call    ??$_Emplace_reallocate@VCComVariant@ATL@@@?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@AEAAPEAVCComVariant@ATL@@QEAV23@$$QEAV23@@Z; std::vector<ATL::CComVariant>::_Emplace_reallocate<ATL::CComVariant>(ATL::CComVariant * const,ATL::CComVariant &&)
0x1800265a3  nop
0x1800265a4  lea     rcx, [rbp+pvarg]; pvarg
0x1800265a8  call    cs:__imp_VariantClear
0x1800265ae  mov     eax, 13h
0x1800265b3  mov     word ptr [rbp+pvarg], ax
0x1800265b7  mov     dword ptr [rbp+pvarg+8], esi
0x1800265ba  mov     rbx, [rbp+pvargDest+8]
0x1800265be  cmp     rbx, [rbp+var_28]
0x1800265c2  jz      short loc_1800265E7
0x1800265c4  xor     eax, eax
0x1800265c6  mov     [rbx], ax
0x1800265c9  lea     rdx, [rbp+pvarg]; pvargSrc
0x1800265cd  mov     rcx, rbx; pvargDest
0x1800265d0  call    cs:__imp_VariantCopy
0x1800265d6  mov     ecx, eax; int
0x1800265d8  test    eax, eax
0x1800265da  js      loc_1800266D0
0x1800265e0  add     [rbp+pvargDest+8], 18h
0x1800265e5  jmp     short loc_1800265F8
0x1800265e7  lea     r8, [rbp+pvarg]
0x1800265eb  mov     rdx, rbx
0x1800265ee  lea     rcx, [rbp+pvargDest]
0x1800265f2  call    ??$_Emplace_reallocate@VCComVariant@ATL@@@?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@AEAAPEAVCComVariant@ATL@@QEAV23@$$QEAV23@@Z; std::vector<ATL::CComVariant>::_Emplace_reallocate<ATL::CComVariant>(ATL::CComVariant * const,ATL::CComVariant &&)
0x1800265f7  nop
0x1800265f8  lea     rcx, [rbp+pvarg]; pvarg
0x1800265fc  call    cs:__imp_VariantClear
0x180026602  lea     rax, [rbp+arg_18]
0x180026606  mov     [rbp+var_40], rax
0x18002660a  mov     ecx, 18h; Size
0x18002660f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180026614  mov     r8, [rbp+var_28]
0x180026618  mov     [rbp+var_28], 0
0x180026620  mov     rdx, [rbp+pvargDest+8]
0x180026624  mov     [rbp+pvargDest+8], 0
0x18002662c  mov     rcx, [rbp+pvargDest]
0x180026630  mov     [rbp+pvargDest], 0
0x180026638  mov     [rax], rcx
0x18002663b  mov     [rax+8], rdx
0x18002663f  mov     [rax+10h], r8
0x180026643  mov     [rbp+arg_18], rax
0x180026647  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18002664e  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180026655  mov     rax, [rax+18h]
0x180026659  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002665e  add     rax, 18h
0x180026662  mov     [rbp+arg_0], rax
0x180026666  xor     edx, edx
0x180026668  lea     rcx, [rbp+arg_0]
0x18002666c  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x180026671  test    al, al
0x180026673  jnz     short loc_18002667F
0x180026675  lea     rcx, [rbp+arg_0]
0x180026679  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x18002667e  nop
0x18002667f  lea     r9, [rbp+arg_18]
0x180026683  lea     r8, [rbp+arg_0]
0x180026687  xor     edx, edx
0x180026689  mov     rcx, rdi
0x18002668c  call    ?PostPluginMessage@FrameWindow@@AEAAXW4PluginId@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$unique_ptr@V?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@U?$default_delete@V?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@@2@@std@@@Z; FrameWindow::PostPluginMessage(PluginId,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,std::unique_ptr<std::vector<ATL::CComVariant>>)
0x180026691  nop
0x180026692  mov     rdx, [rbp+arg_0]
0x180026696  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18002669a  or      eax, 0FFFFFFFFh
0x18002669d  lock xadd [rdx+10h], eax
0x1800266a2  sub     eax, 1
0x1800266a5  jg      short loc_1800266B7
0x1800266a7  mov     rcx, [rdx]
0x1800266aa  mov     rax, [rcx]
0x1800266ad  mov     rax, [rax+8]
0x1800266b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800266b6  nop
0x1800266b7  lea     rcx, [rbp+pvargDest]
0x1800266bb  call    ??1?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@QEAA@XZ; std::vector<ATL::CComVariant>::~vector<ATL::CComVariant>(void)
0x1800266c0  mov     rbx, [rsp+70h+arg_8]
0x1800266c8  add     rsp, 70h
0x1800266cc  pop     rdi
0x1800266cd  pop     rsi
0x1800266ce  pop     rbp
0x1800266cf  retn
0x1800266d0  mov     word ptr [rbx], 0Ah
0x1800266d5  mov     [rbx+8], ecx
0x1800266d8  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800266de  mov     eax, 0Ah
0x1800266e3  mov     word ptr [rbp+pvarg], ax
0x1800266e7  mov     ecx, 8007000Eh; int
0x1800266ec  mov     dword ptr [rbp+pvarg+8], ecx
0x1800266ef  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800266f5  mov     word ptr [rbx], 0Ah
0x1800266fa  mov     [rbx+8], ecx
0x1800266fd  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
