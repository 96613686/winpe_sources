# FrameWindow::SetViewSourceUrlFromSite(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x180028978`
- end: `0x180028a59`
- name: `?SetViewSourceUrlFromSite@FrameWindow@@AEAAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `225`
- prototype: `__int64 __fastcall(FrameWindow *this, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180023598`

## callees

- `0x18000193c`
- `0x180002d44`
- `0x180003338`
- `0x180020bac`
- `0x180025cac`
- `0x180028978`
- `0x180035010`

## pseudocode

```c
__int64 __fastcall FrameWindow::SetViewSourceUrlFromSite(FrameWindow *this, __int64 a2)
{
  _QWORD *v4; // rbx
  _BYTE *v5; // rdx
  _QWORD *v6; // rdx
  int *v8; // [rsp+20h] [rbp-58h]
  _BYTE v9[56]; // [rsp+30h] [rbp-48h] BYREF
  _BYTE *v10; // [rsp+68h] [rbp-10h]
  __int64 v11; // [rsp+80h] [rbp+8h] BYREF
  _QWORD *v12; // [rsp+90h] [rbp+18h]

  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
    (char *)this + 616,
    a2);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v11,
    a2);
  v4 = operator new(0x10u);
  v12 = v4;
  *v4 = &std::_Func_impl_no_alloc<_lambda_354993ef8de0f281d5c7dac2ccdc8414_,void,enum PluginId,std::shared_ptr<BrowserToolThread>>::`vftable';
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v4 + 1,
    &v11);
  v10 = v4;
  FrameWindow::CallbackOnEachScriptPlugin(this, v9);
  if ( v10 )
  {
    v5 = v9;
    LOBYTE(v5) = v10 != v9;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v10 + 32LL))(v10, v5);
  }
  v6 = (_QWORD *)(v11 - 24);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v11 - 24 + 16), 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v6 + 8LL))(*v6);
  return FrameWindow::OnSelectTabById(this, (unsigned int)v6, 3u, 0, v8);
}

```

## disassembly

```asm
0x180028978  mov     [rsp+arg_8], rbx
0x18002897d  push    rdi
0x18002897e  sub     rsp, 70h
0x180028982  mov     rbx, rdx
0x180028985  mov     rdi, rcx
0x180028988  add     rcx, 268h
0x18002898f  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180028994  mov     rdx, rbx
0x180028997  lea     rcx, [rsp+78h+arg_0]
0x18002899f  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1800289a4  nop
0x1800289a5  mov     [rsp+78h+var_10], 0
0x1800289ae  mov     ecx, 10h; Size
0x1800289b3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800289b8  mov     rbx, rax
0x1800289bb  mov     [rsp+78h+arg_10], rax
0x1800289c3  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_354993ef8de0f281d5c7dac2ccdc8414_@@XW4PluginId@@V?$shared_ptr@VBrowserToolThread@@@std@@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_354993ef8de0f281d5c7dac2ccdc8414_,void,PluginId,std::shared_ptr<BrowserToolThread>>::`vftable'
0x1800289ca  mov     [rbx], rax
0x1800289cd  lea     rcx, [rbx+8]
0x1800289d1  lea     rdx, [rsp+78h+arg_0]
0x1800289d9  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1800289de  nop
0x1800289df  mov     [rsp+78h+var_10], rbx
0x1800289e4  lea     rdx, [rsp+78h+var_48]
0x1800289e9  mov     rcx, rdi
0x1800289ec  call    ?CallbackOnEachScriptPlugin@FrameWindow@@AEAAXAEBV?$function@$$A6AXW4PluginId@@V?$shared_ptr@VBrowserToolThread@@@std@@@Z@std@@@Z; FrameWindow::CallbackOnEachScriptPlugin(std::function<void (PluginId,std::shared_ptr<BrowserToolThread>)> const &)
0x1800289f1  nop
0x1800289f2  mov     rcx, [rsp+78h+var_10]
0x1800289f7  test    rcx, rcx
0x1800289fa  jz      short loc_180028A14
0x1800289fc  mov     rax, [rcx]
0x1800289ff  lea     rdx, [rsp+78h+var_48]
0x180028a04  cmp     rcx, rdx
0x180028a07  setnz   dl
0x180028a0a  mov     rax, [rax+20h]
0x180028a0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028a13  nop
0x180028a14  mov     rdx, [rsp+78h+arg_0]
0x180028a1c  add     rdx, 0FFFFFFFFFFFFFFE8h
0x180028a20  or      eax, 0FFFFFFFFh
0x180028a23  lock xadd [rdx+10h], eax
0x180028a28  sub     eax, 1
0x180028a2b  jg      short loc_180028A3C
0x180028a2d  mov     rcx, [rdx]
0x180028a30  mov     rax, [rcx]
0x180028a33  mov     rax, [rax+8]
0x180028a37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028a3c  xor     r9d, r9d; __int64
0x180028a3f  lea     r8d, [r9+3]; unsigned __int64
0x180028a43  mov     rcx, rdi; this
0x180028a46  call    ?OnSelectTabById@FrameWindow@@QEAA_JI_K_JAEAH@Z; FrameWindow::OnSelectTabById(uint,unsigned __int64,__int64,int &)
0x180028a4b  mov     rbx, [rsp+78h+arg_8]
0x180028a53  add     rsp, 70h
0x180028a57  pop     rdi
0x180028a58  retn
```
