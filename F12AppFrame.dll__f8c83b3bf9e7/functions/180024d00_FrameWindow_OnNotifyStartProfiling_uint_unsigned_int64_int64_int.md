# FrameWindow::OnNotifyStartProfiling(uint,unsigned __int64,__int64,int &)

- ea: `0x180024d00`
- end: `0x180024f9f`
- name: `?OnNotifyStartProfiling@FrameWindow@@QEAA_JI_K_JAEAH@Z`
- size: `671`
- prototype: `__int64 __fastcall(FrameWindow *__hidden this, unsigned int, unsigned __int64, __int64, int *)`
- caller_count: `1`
- callee_count: `12`
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
- `0x180024d00`
- `0x1800269a4`
- `0x18002f710`
- `0x180035010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180024d6f`
- `OLEAUT32!__imp_SysAllocString` at `0x180024d6f`
- `OLEAUT32!__imp_VariantClear` at `0x180024d59`
- `OLEAUT32!__imp_VariantClear` at `0x180024dc4`
- `OLEAUT32!__imp_VariantClear` at `0x180024e18`
- `OLEAUT32!__imp_VariantClear` at `0x180024d59`
- `OLEAUT32!__imp_VariantClear` at `0x180024dc4`
- `OLEAUT32!__imp_VariantClear` at `0x180024e18`
- `OLEAUT32!__imp_VariantCopy` at `0x180024d98`
- `OLEAUT32!__imp_VariantCopy` at `0x180024dec`
- `OLEAUT32!__imp_VariantCopy` at `0x180024d98`
- `OLEAUT32!__imp_VariantCopy` at `0x180024dec`
- `USER32!SendMessageW` at `0x180024ef6`
- `USER32!SendMessageW` at `0x180024ef6`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall FrameWindow::OnNotifyStartProfiling(FrameWindow *this, __int64 a2, LONG a3)
{
  VARIANTARG *v5; // rdi
  HRESULT v6; // eax
  VARIANTARG *v7; // rdi
  HRESULT v8; // eax
  VARIANTARG **v9; // rax
  VARIANTARG *v10; // r8
  VARIANTARG *v11; // rdx
  VARIANTARG *v12; // rcx
  F12 *v13; // rcx
  int *v14; // rdx
  UINT v15; // eax
  _QWORD *v16; // rdx
  __int64 v17; // rbx
  VARIANTARG *pvargDest[2]; // [rsp+20h] [rbp-71h] BYREF
  VARIANTARG *v20; // [rsp+30h] [rbp-61h]
  int *v21; // [rsp+38h] [rbp-59h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-51h] BYREF
  _QWORD v23[3]; // [rsp+58h] [rbp-39h] BYREF
  _QWORD v24[7]; // [rsp+70h] [rbp-21h] BYREF
  _QWORD *v25; // [rsp+A8h] [rbp+17h]

  if ( *((int *)this + 169) < 0 || *((_BYTE *)this + 673) )
    return -1;
  *(_OWORD *)pvargDest = 0;
  v20 = 0;
  pvarg.vt = 0;
  VariantClear(&pvarg);
  pvarg.vt = 8;
  pvarg.llVal = (LONGLONG)SysAllocString(L"profilerstarted");
  if ( !pvarg.llVal )
  {
    pvarg.vt = 10;
    pvarg.lVal = -2147024882;
    ATL::AtlThrowImpl(-2147024882);
  }
  v5 = pvargDest[1];
  if ( pvargDest[1] == v20 )
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
  if ( pvargDest[1] == v20 )
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
  v23[1] = v23;
  v9 = (VARIANTARG **)operator new(0x18u);
  v10 = v20;
  v20 = 0;
  v11 = pvargDest[1];
  pvargDest[1] = 0;
  v12 = pvargDest[0];
  pvargDest[0] = 0;
  *v9 = v12;
  v9[1] = v11;
  v9[2] = v10;
  v23[0] = v9;
  v21 = (int *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (wchar_t **)&v21,
          0) )
    ATL::CSimpleStringT<unsigned short,0>::Empty(&v21);
  FrameWindow::PostPluginMessage(this, 0, &v21, v23);
  v14 = v21 - 6;
  if ( _InterlockedExchangeAdd(v21 - 2, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v14 + 8LL))(*(_QWORD *)v14);
  if ( ++*((_DWORD *)this + 169) == 1 )
  {
    v15 = F12::SiteCommandMessage(v13);
    SendMessageW(*((HWND *)this + 75), v15, 2u, 0);
    v24[0] = &std::_Func_impl_no_alloc<_lambda_9003ac4622f443cd17107ffee5f46f8b_,void,enum PluginId,std::shared_ptr<BrowserToolThread>>::`vftable';
    v25 = v24;
    FrameWindow::CallbackOnEachScriptPlugin((__int64)this, (__int64)v24);
    if ( v25 )
    {
      v16 = v24;
      LOBYTE(v16) = v25 != v24;
      (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v25 + 32LL))(v25, v16);
    }
  }
  v17 = *((int *)this + 169);
  std::vector<ATL::CComVariant>::~vector<ATL::CComVariant>((__int64)pvargDest);
  return v17;
}

```

## disassembly

```asm
0x180024d00  push    rbp
0x180024d02  push    rbx
0x180024d03  push    rsi
0x180024d04  push    rdi
0x180024d05  lea     rbp, [rsp-37h]
0x180024d0a  sub     rsp, 0C8h
0x180024d11  mov     rax, cs:__security_cookie
0x180024d18  xor     rax, rsp
0x180024d1b  mov     [rbp+4Fh+var_30], rax
0x180024d1f  mov     rsi, r8
0x180024d22  mov     rbx, rcx
0x180024d25  cmp     dword ptr [rcx+2A4h], 0
0x180024d2c  jl      loc_180024F50
0x180024d32  cmp     byte ptr [rcx+2A1h], 0
0x180024d39  jnz     loc_180024F50
0x180024d3f  xorps   xmm0, xmm0
0x180024d42  movdqu  xmmword ptr [rbp+4Fh+pvargDest], xmm0
0x180024d47  mov     [rbp+4Fh+var_B0], 0
0x180024d4f  xor     eax, eax
0x180024d51  mov     word ptr [rbp+4Fh+pvarg], ax
0x180024d55  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x180024d59  call    cs:__imp_VariantClear
0x180024d5f  mov     eax, 8
0x180024d64  mov     word ptr [rbp+4Fh+pvarg], ax
0x180024d68  lea     rcx, aProfilerstarte; "profilerstarted"
0x180024d6f  call    cs:__imp_SysAllocString
0x180024d75  mov     qword ptr [rbp+4Fh+pvarg+8], rax
0x180024d79  test    rax, rax
0x180024d7c  jz      loc_180024F7A
0x180024d82  mov     rdi, [rbp+4Fh+pvargDest+8]
0x180024d86  cmp     rdi, [rbp+4Fh+var_B0]
0x180024d8a  jz      short loc_180024DAF
0x180024d8c  xor     eax, eax
0x180024d8e  mov     [rdi], ax
0x180024d91  lea     rdx, [rbp+4Fh+pvarg]; pvargSrc
0x180024d95  mov     rcx, rdi; pvargDest
0x180024d98  call    cs:__imp_VariantCopy
0x180024d9e  mov     ecx, eax; int
0x180024da0  test    eax, eax
0x180024da2  js      loc_180024F91
0x180024da8  add     [rbp+4Fh+pvargDest+8], 18h
0x180024dad  jmp     short loc_180024DC0
0x180024daf  lea     r8, [rbp+4Fh+pvarg]
0x180024db3  mov     rdx, rdi
0x180024db6  lea     rcx, [rbp+4Fh+pvargDest]
0x180024dba  call    ??$_Emplace_reallocate@VCComVariant@ATL@@@?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@AEAAPEAVCComVariant@ATL@@QEAV23@$$QEAV23@@Z; std::vector<ATL::CComVariant>::_Emplace_reallocate<ATL::CComVariant>(ATL::CComVariant * const,ATL::CComVariant &&)
0x180024dbf  nop
0x180024dc0  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x180024dc4  call    cs:__imp_VariantClear
0x180024dca  mov     eax, 3
0x180024dcf  mov     word ptr [rbp+4Fh+pvarg], ax
0x180024dd3  mov     dword ptr [rbp+4Fh+pvarg+8], esi
0x180024dd6  mov     rdi, [rbp+4Fh+pvargDest+8]
0x180024dda  cmp     rdi, [rbp+4Fh+var_B0]
0x180024dde  jz      short loc_180024E03
0x180024de0  xor     eax, eax
0x180024de2  mov     [rdi], ax
0x180024de5  lea     rdx, [rbp+4Fh+pvarg]; pvargSrc
0x180024de9  mov     rcx, rdi; pvargDest
0x180024dec  call    cs:__imp_VariantCopy
0x180024df2  mov     ecx, eax; int
0x180024df4  test    eax, eax
0x180024df6  js      loc_180024F6C
0x180024dfc  add     [rbp+4Fh+pvargDest+8], 18h
0x180024e01  jmp     short loc_180024E14
0x180024e03  lea     r8, [rbp+4Fh+pvarg]
0x180024e07  mov     rdx, rdi
0x180024e0a  lea     rcx, [rbp+4Fh+pvargDest]
0x180024e0e  call    ??$_Emplace_reallocate@VCComVariant@ATL@@@?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@AEAAPEAVCComVariant@ATL@@QEAV23@$$QEAV23@@Z; std::vector<ATL::CComVariant>::_Emplace_reallocate<ATL::CComVariant>(ATL::CComVariant * const,ATL::CComVariant &&)
0x180024e13  nop
0x180024e14  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x180024e18  call    cs:__imp_VariantClear
0x180024e1e  lea     rax, [rbp+4Fh+var_88]
0x180024e22  mov     [rbp+4Fh+var_80], rax
0x180024e26  mov     ecx, 18h; Size
0x180024e2b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180024e30  mov     r8, [rbp+4Fh+var_B0]
0x180024e34  mov     [rbp+4Fh+var_B0], 0
0x180024e3c  mov     rdx, [rbp+4Fh+pvargDest+8]
0x180024e40  mov     [rbp+4Fh+pvargDest+8], 0
0x180024e48  mov     rcx, [rbp+4Fh+pvargDest]
0x180024e4c  mov     [rbp+4Fh+pvargDest], 0
0x180024e54  mov     [rax], rcx
0x180024e57  mov     [rax+8], rdx
0x180024e5b  mov     [rax+10h], r8
0x180024e5f  mov     [rbp+4Fh+var_88], rax
0x180024e63  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180024e6a  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180024e71  mov     rax, [rax+18h]
0x180024e75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e7a  add     rax, 18h
0x180024e7e  mov     [rbp+4Fh+var_A8], rax
0x180024e82  xor     edx, edx
0x180024e84  lea     rcx, [rbp+4Fh+var_A8]
0x180024e88  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x180024e8d  test    al, al
0x180024e8f  jnz     short loc_180024E9B
0x180024e91  lea     rcx, [rbp+4Fh+var_A8]
0x180024e95  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180024e9a  nop
0x180024e9b  lea     r9, [rbp+4Fh+var_88]
0x180024e9f  lea     r8, [rbp+4Fh+var_A8]
0x180024ea3  xor     edx, edx
0x180024ea5  mov     rcx, rbx
0x180024ea8  call    ?PostPluginMessage@FrameWindow@@AEAAXW4PluginId@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$unique_ptr@V?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@U?$default_delete@V?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@@2@@std@@@Z; FrameWindow::PostPluginMessage(PluginId,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,std::unique_ptr<std::vector<ATL::CComVariant>>)
0x180024ead  nop
0x180024eae  mov     rdx, [rbp+4Fh+var_A8]
0x180024eb2  add     rdx, 0FFFFFFFFFFFFFFE8h
0x180024eb6  or      eax, 0FFFFFFFFh
0x180024eb9  lock xadd [rdx+10h], eax
0x180024ebe  sub     eax, 1
0x180024ec1  jg      short loc_180024ED2
0x180024ec3  mov     rcx, [rdx]
0x180024ec6  mov     rax, [rcx]
0x180024ec9  mov     rax, [rax+8]
0x180024ecd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ed2  inc     dword ptr [rbx+2A4h]
0x180024ed8  cmp     dword ptr [rbx+2A4h], 1
0x180024edf  jnz     short loc_180024F3B
0x180024ee1  call    ?SiteCommandMessage@F12@@YAIXZ; F12::SiteCommandMessage(void)
0x180024ee6  xor     r9d, r9d; lParam
0x180024ee9  lea     r8d, [r9+2]; wParam
0x180024eed  mov     edx, eax; Msg
0x180024eef  mov     rcx, [rbx+258h]; hWnd
0x180024ef6  call    cs:__imp_SendMessageW
0x180024efc  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_9003ac4622f443cd17107ffee5f46f8b_@@XW4PluginId@@V?$shared_ptr@VBrowserToolThread@@@std@@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_9003ac4622f443cd17107ffee5f46f8b_,void,PluginId,std::shared_ptr<BrowserToolThread>>::`vftable'
0x180024f03  mov     [rbp+4Fh+var_70], rax
0x180024f07  lea     rax, [rbp+4Fh+var_70]
0x180024f0b  mov     [rbp+4Fh+var_38], rax
0x180024f0f  lea     rdx, [rbp+4Fh+var_70]
0x180024f13  mov     rcx, rbx
0x180024f16  call    ?CallbackOnEachScriptPlugin@FrameWindow@@AEAAXAEBV?$function@$$A6AXW4PluginId@@V?$shared_ptr@VBrowserToolThread@@@std@@@Z@std@@@Z; FrameWindow::CallbackOnEachScriptPlugin(std::function<void (PluginId,std::shared_ptr<BrowserToolThread>)> const &)
0x180024f1b  nop
0x180024f1c  mov     rcx, [rbp+4Fh+var_38]
0x180024f20  test    rcx, rcx
0x180024f23  jz      short loc_180024F3B
0x180024f25  mov     rax, [rcx]
0x180024f28  lea     rdx, [rbp+4Fh+var_70]
0x180024f2c  cmp     rcx, rdx
0x180024f2f  setnz   dl
0x180024f32  mov     rax, [rax+20h]
0x180024f36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f3b  movsxd  rbx, dword ptr [rbx+2A4h]
0x180024f42  lea     rcx, [rbp+4Fh+pvargDest]
0x180024f46  call    ??1?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@QEAA@XZ; std::vector<ATL::CComVariant>::~vector<ATL::CComVariant>(void)
0x180024f4b  mov     rax, rbx
0x180024f4e  jmp     short loc_180024F54
0x180024f50  or      rax, 0FFFFFFFFFFFFFFFFh
0x180024f54  mov     rcx, [rbp+4Fh+var_30]
0x180024f58  xor     rcx, rsp; StackCookie
0x180024f5b  call    __security_check_cookie
0x180024f60  add     rsp, 0C8h
0x180024f67  pop     rdi
0x180024f68  pop     rsi
0x180024f69  pop     rbx
0x180024f6a  pop     rbp
0x180024f6b  retn
0x180024f6c  mov     word ptr [rdi], 0Ah
0x180024f71  mov     [rdi+8], ecx
0x180024f74  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180024f7a  mov     eax, 0Ah
0x180024f7f  mov     word ptr [rbp+4Fh+pvarg], ax
0x180024f83  mov     ecx, 8007000Eh; int
0x180024f88  mov     dword ptr [rbp+4Fh+pvarg+8], ecx
0x180024f8b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180024f91  mov     word ptr [rdi], 0Ah
0x180024f96  mov     [rdi+8], ecx
0x180024f99  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
