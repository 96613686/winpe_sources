# FrameWindow::OnPostJsonMessage(uint,unsigned __int64,__int64,int &)

- ea: `0x1800256c0`
- end: `0x1800257d9`
- name: `?OnPostJsonMessage@FrameWindow@@QEAA_JI_K_JAEAH@Z`
- size: `281`
- prototype: `__int64 __fastcall(FrameWindow *this, __int64, unsigned int, void *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x18002b910`

## callees

- `0x180001800`
- `0x180001900`
- `0x180020528`
- `0x180020bac`
- `0x180022f44`
- `0x1800256c0`
- `0x1800269a4`
- `0x180035010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FrameWindow::OnPostJsonMessage(FrameWindow *this, __int64 a2, unsigned int a3, void *a4)
{
  _DWORD *v5; // r11
  _QWORD *v6; // rdx
  void *v7; // rbx
  volatile signed __int32 *v8; // rdx
  unsigned int v10; // [rsp+20h] [rbp-21h] BYREF
  void *Block; // [rsp+28h] [rbp-19h] BYREF
  __int64 v12; // [rsp+30h] [rbp-11h] BYREF
  _QWORD v13[7]; // [rsp+40h] [rbp-1h] BYREF
  _QWORD *v14; // [rsp+78h] [rbp+37h]

  v10 = a3;
  Block = a4;
  if ( (unsigned __int8)FrameWindow::IsPluginLoaded(this, a3) )
  {
    *(_BYTE *)(*(_QWORD *)std::map<enum PluginId,std::shared_ptr<BrowserToolThreadInfo>>::operator[](
                            (char *)this + 448,
                            &v10)
             + 24LL) = 1;
    v5 = Block;
  }
  if ( *v5 == -1 )
  {
    v13[0] = &std::_Func_impl_no_alloc<_lambda_45b4ba228d180e3cbcd12fab182c287e_,void,enum PluginId,std::shared_ptr<BrowserToolThread>>::`vftable';
    v13[1] = &Block;
    v14 = v13;
    FrameWindow::CallbackOnEachScriptPlugin(this, v13);
    if ( v14 )
    {
      v6 = v13;
      LOBYTE(v6) = v14 != v13;
      (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v14 + 32LL))(v14, v6);
    }
  }
  else
  {
    v12 = 0;
    FrameWindow::PostPluginMessage(this, (unsigned int)*v5, v5 + 2, &v12);
  }
  v7 = Block;
  if ( Block )
  {
    v8 = (volatile signed __int32 *)(*((_QWORD *)Block + 1) - 24LL);
    if ( _InterlockedExchangeAdd(v8 + 4, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v8 + 8LL))(*(_QWORD *)v8);
    operator delete(v7);
  }
  return 0;
}

```

## disassembly

```asm
0x1800256c0  mov     [rsp-8+arg_8], rbx
0x1800256c5  push    rbp
0x1800256c6  lea     rbp, [rsp-4Fh]
0x1800256cb  sub     rsp, 90h
0x1800256d2  mov     rax, cs:__security_cookie
0x1800256d9  xor     rax, rsp
0x1800256dc  mov     [rbp+4Fh+var_10], rax
0x1800256e0  mov     r11, r9
0x1800256e3  mov     rbx, rcx
0x1800256e6  mov     [rbp+4Fh+var_70], r8d
0x1800256ea  mov     [rbp+4Fh+Block], r9
0x1800256ee  mov     edx, r8d
0x1800256f1  call    ?IsPluginLoaded@FrameWindow@@AEBA_NW4PluginId@@@Z; FrameWindow::IsPluginLoaded(PluginId)
0x1800256f6  test    al, al
0x1800256f8  jz      short loc_180025715
0x1800256fa  lea     rcx, [rbx+1C0h]
0x180025701  lea     rdx, [rbp+4Fh+var_70]
0x180025705  call    ??A?$map@W4PluginId@@V?$shared_ptr@UBrowserToolThreadInfo@@@std@@U?$less@W4PluginId@@@3@V?$allocator@U?$pair@$$CBW4PluginId@@V?$shared_ptr@UBrowserToolThreadInfo@@@std@@@std@@@3@@std@@QEAAAEAV?$shared_ptr@UBrowserToolThreadInfo@@@1@AEBW4PluginId@@@Z; std::map<PluginId,std::shared_ptr<BrowserToolThreadInfo>>::operator[](PluginId const &)
0x18002570a  mov     rcx, [rax]
0x18002570d  mov     byte ptr [rcx+18h], 1
0x180025711  mov     r11, [rbp+4Fh+Block]
0x180025715  cmp     dword ptr [r11], 0FFFFFFFFh
0x180025719  jnz     short loc_180025764
0x18002571b  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_45b4ba228d180e3cbcd12fab182c287e_@@XW4PluginId@@V?$shared_ptr@VBrowserToolThread@@@std@@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_45b4ba228d180e3cbcd12fab182c287e_,void,PluginId,std::shared_ptr<BrowserToolThread>>::`vftable'
0x180025722  mov     [rbp+4Fh+var_50], rax
0x180025726  lea     rax, [rbp+4Fh+Block]
0x18002572a  mov     [rbp+4Fh+var_48], rax
0x18002572e  lea     rax, [rbp+4Fh+var_50]
0x180025732  mov     [rbp+4Fh+var_18], rax
0x180025736  lea     rdx, [rbp+4Fh+var_50]
0x18002573a  mov     rcx, rbx
0x18002573d  call    ?CallbackOnEachScriptPlugin@FrameWindow@@AEAAXAEBV?$function@$$A6AXW4PluginId@@V?$shared_ptr@VBrowserToolThread@@@std@@@Z@std@@@Z; FrameWindow::CallbackOnEachScriptPlugin(std::function<void (PluginId,std::shared_ptr<BrowserToolThread>)> const &)
0x180025742  nop
0x180025743  mov     rcx, [rbp+4Fh+var_18]
0x180025747  test    rcx, rcx
0x18002574a  jz      short loc_180025780
0x18002574c  mov     rax, [rcx]
0x18002574f  lea     rdx, [rbp+4Fh+var_50]
0x180025753  cmp     rcx, rdx
0x180025756  setnz   dl
0x180025759  mov     rax, [rax+20h]
0x18002575d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025762  jmp     short loc_180025780
0x180025764  mov     [rbp+4Fh+var_60], 0
0x18002576c  lea     r8, [r11+8]
0x180025770  lea     r9, [rbp+4Fh+var_60]
0x180025774  mov     edx, [r11]
0x180025777  mov     rcx, rbx
0x18002577a  call    ?PostPluginMessage@FrameWindow@@AEAAXW4PluginId@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$unique_ptr@V?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@U?$default_delete@V?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@@2@@std@@@Z; FrameWindow::PostPluginMessage(PluginId,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,std::unique_ptr<std::vector<ATL::CComVariant>>)
0x18002577f  nop
0x180025780  mov     rbx, [rbp+4Fh+Block]
0x180025784  test    rbx, rbx
0x180025787  jz      short loc_1800257BA
0x180025789  mov     rdx, [rbx+8]
0x18002578d  add     rdx, 0FFFFFFFFFFFFFFE8h
0x180025791  or      eax, 0FFFFFFFFh
0x180025794  lock xadd [rdx+10h], eax
0x180025799  sub     eax, 1
0x18002579c  jg      short loc_1800257AD
0x18002579e  mov     rcx, [rdx]
0x1800257a1  mov     rax, [rcx]
0x1800257a4  mov     rax, [rax+8]
0x1800257a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800257ad  mov     edx, 10h
0x1800257b2  mov     rcx, rbx; Block
0x1800257b5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800257ba  xor     eax, eax
0x1800257bc  mov     rcx, [rbp+4Fh+var_10]
0x1800257c0  xor     rcx, rsp; StackCookie
0x1800257c3  call    __security_check_cookie
0x1800257c8  mov     rbx, [rsp+90h+arg_8]
0x1800257d0  add     rsp, 90h
0x1800257d7  pop     rbp
0x1800257d8  retn
```
