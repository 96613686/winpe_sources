# FrameWindow::OnNotifyStopProfiling(uint,unsigned __int64,__int64,int &)

- ea: `0x180024fa8`
- end: `0x180025226`
- name: `?OnNotifyStopProfiling@FrameWindow@@QEAA_JI_K_JAEAH@Z`
- size: `638`
- prototype: `__int64 __fastcall(FrameWindow *__hidden this, unsigned int, unsigned __int64, __int64, int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002b910`

## callees

- `0x180001800`
- `0x18000193c`
- `0x1800031a4`
- `0x180003858`
- `0x180003880`
- `0x1800039ec`
- `0x18001e894`
- `0x180020bac`
- `0x180024fa8`
- `0x1800269a4`
- `0x180035010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180025017`
- `OLEAUT32!__imp_SysAllocString` at `0x180025017`
- `OLEAUT32!__imp_VariantClear` at `0x180025001`
- `OLEAUT32!__imp_VariantClear` at `0x18002506c`
- `OLEAUT32!__imp_VariantClear` at `0x1800250c0`
- `OLEAUT32!__imp_VariantClear` at `0x180025001`
- `OLEAUT32!__imp_VariantClear` at `0x18002506c`
- `OLEAUT32!__imp_VariantClear` at `0x1800250c0`
- `OLEAUT32!__imp_VariantCopy` at `0x180025040`
- `OLEAUT32!__imp_VariantCopy` at `0x180025094`
- `OLEAUT32!__imp_VariantCopy` at `0x180025040`
- `OLEAUT32!__imp_VariantCopy` at `0x180025094`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall FrameWindow::OnNotifyStopProfiling(FrameWindow *this, __int64 a2, LONG a3)
{
  VARIANTARG *v5; // rdi
  HRESULT v6; // eax
  VARIANTARG *v7; // rdi
  HRESULT v8; // eax
  VARIANTARG **v9; // rax
  VARIANTARG *v10; // r8
  VARIANTARG *v11; // rdx
  VARIANTARG *v12; // rcx
  int *v13; // rdx
  _QWORD *v15; // rdx
  __int64 v16; // rbx
  VARIANTARG *pvargDest[2]; // [rsp+20h] [rbp-71h] BYREF
  VARIANTARG *v19; // [rsp+30h] [rbp-61h]
  int *v20; // [rsp+38h] [rbp-59h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-51h] BYREF
  _QWORD v22[3]; // [rsp+58h] [rbp-39h] BYREF
  _QWORD v23[7]; // [rsp+70h] [rbp-21h] BYREF
  _QWORD *v24; // [rsp+A8h] [rbp+17h]

  if ( *((int *)this + 169) <= 0 || *((_BYTE *)this + 673) )
    return -1;
  *(_OWORD *)pvargDest = 0;
  v19 = 0;
  pvarg.vt = 0;
  VariantClear(&pvarg);
  pvarg.vt = 8;
  pvarg.llVal = (LONGLONG)SysAllocString(L"profilerstopped");
  if ( !pvarg.llVal )
  {
    pvarg.vt = 10;
    pvarg.lVal = -2147024882;
    ATL::AtlThrowImpl(-2147024882);
  }
  v5 = pvargDest[1];
  if ( pvargDest[1] == v19 )
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
  pvarg.vt = 3;
  pvarg.lVal = a3;
  v7 = pvargDest[1];
  if ( pvargDest[1] == v19 )
  {
    std::vector<ATL::CComVariant>::_Emplace_reallocate<ATL::CComVariant>(
      (const VARIANTARG **)pvargDest,
      pvargDest[1],
      &pvarg);
  }
  else
  {
    pvargDest[1]->vt = 0;
    v8 = VariantCopy(v7, &pvarg);
    if ( v8 < 0 )
    {
      v7->vt = 10;
      v7->lVal = v8;
      ATL::AtlThrowImpl(v8);
    }
    ++pvargDest[1];
  }
  VariantClear(&pvarg);
  v22[1] = v22;
  v9 = (VARIANTARG **)operator new(0x18u);
  v10 = v19;
  v19 = 0;
  v11 = pvargDest[1];
  pvargDest[1] = 0;
  v12 = pvargDest[0];
  pvargDest[0] = 0;
  *v9 = v12;
  v9[1] = v11;
  v9[2] = v10;
  v22[0] = v9;
  v20 = (int *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (wchar_t **)&v20,
          0) )
    ATL::CSimpleStringT<unsigned short,0>::Empty(&v20);
  FrameWindow::PostPluginMessage(this, 0, &v20, v22);
  v13 = v20 - 6;
  if ( _InterlockedExchangeAdd(v20 - 2, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v13 + 8LL))(*(_QWORD *)v13);
  if ( (*((_DWORD *)this + 169))-- == 1 )
  {
    v23[0] = &std::_Func_impl_no_alloc<_lambda_d7989139b408ab19cc6d3076c44446be_,void,enum PluginId,std::shared_ptr<BrowserToolThread>>::`vftable';
    v24 = v23;
    FrameWindow::CallbackOnEachScriptPlugin((__int64)this, (__int64)v23);
    if ( v24 )
    {
      v15 = v23;
      LOBYTE(v15) = v24 != v23;
      (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v24 + 32LL))(v24, v15);
    }
  }
  v16 = *((int *)this + 169);
  std::vector<ATL::CComVariant>::~vector<ATL::CComVariant>((__int64)pvargDest);
  return v16;
}

```

## disassembly

```asm
0x180024fa8  push    rbp
0x180024faa  push    rbx
0x180024fab  push    rsi
0x180024fac  push    rdi
0x180024fad  lea     rbp, [rsp-37h]
0x180024fb2  sub     rsp, 0C8h
0x180024fb9  mov     rax, cs:__security_cookie
0x180024fc0  xor     rax, rsp
0x180024fc3  mov     [rbp+4Fh+var_30], rax
0x180024fc7  mov     rsi, r8
0x180024fca  mov     rbx, rcx
0x180024fcd  cmp     dword ptr [rcx+2A4h], 0
0x180024fd4  jle     loc_1800251D7
0x180024fda  cmp     byte ptr [rcx+2A1h], 0
0x180024fe1  jnz     loc_1800251D7
0x180024fe7  xorps   xmm0, xmm0
0x180024fea  movdqu  xmmword ptr [rbp+4Fh+pvargDest], xmm0
0x180024fef  mov     [rbp+4Fh+var_B0], 0
0x180024ff7  xor     eax, eax
0x180024ff9  mov     word ptr [rbp+4Fh+pvarg], ax
0x180024ffd  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x180025001  call    cs:__imp_VariantClear
0x180025007  mov     eax, 8
0x18002500c  mov     word ptr [rbp+4Fh+pvarg], ax
0x180025010  lea     rcx, aProfilerstoppe; "profilerstopped"
0x180025017  call    cs:__imp_SysAllocString
0x18002501d  mov     qword ptr [rbp+4Fh+pvarg+8], rax
0x180025021  test    rax, rax
0x180025024  jz      loc_180025201
0x18002502a  mov     rdi, [rbp+4Fh+pvargDest+8]
0x18002502e  cmp     rdi, [rbp+4Fh+var_B0]
0x180025032  jz      short loc_180025057
0x180025034  xor     eax, eax
0x180025036  mov     [rdi], ax
0x180025039  lea     rdx, [rbp+4Fh+pvarg]; pvargSrc
0x18002503d  mov     rcx, rdi; pvargDest
0x180025040  call    cs:__imp_VariantCopy
0x180025046  mov     ecx, eax; int
0x180025048  test    eax, eax
0x18002504a  js      loc_180025218
0x180025050  add     [rbp+4Fh+pvargDest+8], 18h
0x180025055  jmp     short loc_180025068
0x180025057  lea     r8, [rbp+4Fh+pvarg]
0x18002505b  mov     rdx, rdi
0x18002505e  lea     rcx, [rbp+4Fh+pvargDest]
0x180025062  call    ??$_Emplace_reallocate@VCComVariant@ATL@@@?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@AEAAPEAVCComVariant@ATL@@QEAV23@$$QEAV23@@Z; std::vector<ATL::CComVariant>::_Emplace_reallocate<ATL::CComVariant>(ATL::CComVariant * const,ATL::CComVariant &&)
0x180025067  nop
0x180025068  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x18002506c  call    cs:__imp_VariantClear
0x180025072  mov     eax, 3
0x180025077  mov     word ptr [rbp+4Fh+pvarg], ax
0x18002507b  mov     dword ptr [rbp+4Fh+pvarg+8], esi
0x18002507e  mov     rdi, [rbp+4Fh+pvargDest+8]
0x180025082  cmp     rdi, [rbp+4Fh+var_B0]
0x180025086  jz      short loc_1800250AB
0x180025088  xor     eax, eax
0x18002508a  mov     [rdi], ax
0x18002508d  lea     rdx, [rbp+4Fh+pvarg]; pvargSrc
0x180025091  mov     rcx, rdi; pvargDest
0x180025094  call    cs:__imp_VariantCopy
0x18002509a  mov     ecx, eax; int
0x18002509c  test    eax, eax
0x18002509e  js      loc_1800251F3
0x1800250a4  add     [rbp+4Fh+pvargDest+8], 18h
0x1800250a9  jmp     short loc_1800250BC
0x1800250ab  lea     r8, [rbp+4Fh+pvarg]
0x1800250af  mov     rdx, rdi
0x1800250b2  lea     rcx, [rbp+4Fh+pvargDest]
0x1800250b6  call    ??$_Emplace_reallocate@VCComVariant@ATL@@@?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@AEAAPEAVCComVariant@ATL@@QEAV23@$$QEAV23@@Z; std::vector<ATL::CComVariant>::_Emplace_reallocate<ATL::CComVariant>(ATL::CComVariant * const,ATL::CComVariant &&)
0x1800250bb  nop
0x1800250bc  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x1800250c0  call    cs:__imp_VariantClear
0x1800250c6  lea     rax, [rbp+4Fh+var_88]
0x1800250ca  mov     [rbp+4Fh+var_80], rax
0x1800250ce  mov     ecx, 18h; Size
0x1800250d3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800250d8  mov     r8, [rbp+4Fh+var_B0]
0x1800250dc  mov     [rbp+4Fh+var_B0], 0
0x1800250e4  mov     rdx, [rbp+4Fh+pvargDest+8]
0x1800250e8  mov     [rbp+4Fh+pvargDest+8], 0
0x1800250f0  mov     rcx, [rbp+4Fh+pvargDest]
0x1800250f4  mov     [rbp+4Fh+pvargDest], 0
0x1800250fc  mov     [rax], rcx
0x1800250ff  mov     [rax+8], rdx
0x180025103  mov     [rax+10h], r8
0x180025107  mov     [rbp+4Fh+var_88], rax
0x18002510b  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180025112  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180025119  mov     rax, [rax+18h]
0x18002511d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025122  add     rax, 18h
0x180025126  mov     [rbp+4Fh+var_A8], rax
0x18002512a  xor     edx, edx
0x18002512c  lea     rcx, [rbp+4Fh+var_A8]
0x180025130  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x180025135  test    al, al
0x180025137  jnz     short loc_180025143
0x180025139  lea     rcx, [rbp+4Fh+var_A8]
0x18002513d  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180025142  nop
0x180025143  lea     r9, [rbp+4Fh+var_88]
0x180025147  lea     r8, [rbp+4Fh+var_A8]
0x18002514b  xor     edx, edx
0x18002514d  mov     rcx, rbx
0x180025150  call    ?PostPluginMessage@FrameWindow@@AEAAXW4PluginId@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$unique_ptr@V?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@U?$default_delete@V?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@@2@@std@@@Z; FrameWindow::PostPluginMessage(PluginId,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,std::unique_ptr<std::vector<ATL::CComVariant>>)
0x180025155  nop
0x180025156  mov     rdx, [rbp+4Fh+var_A8]
0x18002515a  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18002515e  or      eax, 0FFFFFFFFh
0x180025161  lock xadd [rdx+10h], eax
0x180025166  sub     eax, 1
0x180025169  jg      short loc_18002517A
0x18002516b  mov     rcx, [rdx]
0x18002516e  mov     rax, [rcx]
0x180025171  mov     rax, [rax+8]
0x180025175  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002517a  sub     dword ptr [rbx+2A4h], 1
0x180025181  jnz     short loc_1800251C2
0x180025183  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_d7989139b408ab19cc6d3076c44446be_@@XW4PluginId@@V?$shared_ptr@VBrowserToolThread@@@std@@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_d7989139b408ab19cc6d3076c44446be_,void,PluginId,std::shared_ptr<BrowserToolThread>>::`vftable'
0x18002518a  mov     [rbp+4Fh+var_70], rax
0x18002518e  lea     rax, [rbp+4Fh+var_70]
0x180025192  mov     [rbp+4Fh+var_38], rax
0x180025196  lea     rdx, [rbp+4Fh+var_70]
0x18002519a  mov     rcx, rbx
0x18002519d  call    ?CallbackOnEachScriptPlugin@FrameWindow@@AEAAXAEBV?$function@$$A6AXW4PluginId@@V?$shared_ptr@VBrowserToolThread@@@std@@@Z@std@@@Z; FrameWindow::CallbackOnEachScriptPlugin(std::function<void (PluginId,std::shared_ptr<BrowserToolThread>)> const &)
0x1800251a2  nop
0x1800251a3  mov     rcx, [rbp+4Fh+var_38]
0x1800251a7  test    rcx, rcx
0x1800251aa  jz      short loc_1800251C2
0x1800251ac  mov     rax, [rcx]
0x1800251af  lea     rdx, [rbp+4Fh+var_70]
0x1800251b3  cmp     rcx, rdx
0x1800251b6  setnz   dl
0x1800251b9  mov     rax, [rax+20h]
0x1800251bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800251c2  movsxd  rbx, dword ptr [rbx+2A4h]
0x1800251c9  lea     rcx, [rbp+4Fh+pvargDest]
0x1800251cd  call    ??1?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@QEAA@XZ; std::vector<ATL::CComVariant>::~vector<ATL::CComVariant>(void)
0x1800251d2  mov     rax, rbx
0x1800251d5  jmp     short loc_1800251DB
0x1800251d7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800251db  mov     rcx, [rbp+4Fh+var_30]
0x1800251df  xor     rcx, rsp; StackCookie
0x1800251e2  call    __security_check_cookie
0x1800251e7  add     rsp, 0C8h
0x1800251ee  pop     rdi
0x1800251ef  pop     rsi
0x1800251f0  pop     rbx
0x1800251f1  pop     rbp
0x1800251f2  retn
0x1800251f3  mov     word ptr [rdi], 0Ah
0x1800251f8  mov     [rdi+8], ecx
0x1800251fb  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180025201  mov     eax, 0Ah
0x180025206  mov     word ptr [rbp+4Fh+pvarg], ax
0x18002520a  mov     ecx, 8007000Eh; int
0x18002520f  mov     dword ptr [rbp+4Fh+pvarg+8], ecx
0x180025212  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180025218  mov     word ptr [rdi], 0Ah
0x18002521d  mov     [rdi+8], ecx
0x180025220  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
