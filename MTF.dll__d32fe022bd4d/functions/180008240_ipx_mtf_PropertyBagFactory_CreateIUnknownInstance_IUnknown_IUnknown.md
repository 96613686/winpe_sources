# ipx::mtf::PropertyBagFactory::_CreateIUnknownInstance(IUnknown *,IUnknown * *)

- ea: `0x180008240`
- end: `0x1800082f3`
- name: `?_CreateIUnknownInstance@PropertyBagFactory@mtf@ipx@@UEAAJPEAUIUnknown@@PEAPEAU4@@Z`
- size: `179`
- prototype: `__int64 __fastcall(ipx::mtf::PropertyBagFactory *__hidden this, struct IUnknown *, struct IUnknown **)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180001fc4`
- `0x180008240`
- `0x18000cba4`
- `0x18000cbe4`
- `0x18002f010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ipx::mtf::PropertyBagFactory::_CreateIUnknownInstance(
        ipx::mtf::PropertyBagFactory *this,
        struct IUnknown *a2,
        struct IUnknown **a3)
{
  struct IUnknown *v5; // rax
  struct IUnknown *v6; // rdi

  if ( a2 )
    return 2147746064LL;
  v5 = (struct IUnknown *)operator new(0x40u);
  v6 = v5;
  if ( v5 )
  {
    LODWORD(v5[2].lpVtbl) = 0;
    v5->lpVtbl = (struct IUnknownVtbl *)&ipx::mtf::CMtfPropertyBag::`vftable'{for `IMtfPropertyBag'};
    v5[1].lpVtbl = (struct IUnknownVtbl *)&ipx::mtf::CMtfPropertyBag::`vftable'{for `_MtfIUnknownImpl_Helper<IMtfSerializable,void,void,void,void>'};
    v5[3].lpVtbl = 0;
    v5[4].lpVtbl = 0;
    v5[5].lpVtbl = 0;
    v5[4].lpVtbl = (struct IUnknownVtbl *)std::_Tree_alloc<0,std::_Tree_base_types<std::pair<_CLIENT_KEY const,RefPtr<ipx::mtf::MtfTransportClientCoreUI>>>>::_Buyheadnode();
    v6[6].lpVtbl = 0;
    v6[7].lpVtbl = 0;
    v6[6].lpVtbl = (struct IUnknownVtbl *)std::_Tree_alloc<0,std::_Tree_base_types<std::pair<unsigned short const,RefPtr<IUnknown>>>>::_Buyheadnode();
    _InterlockedIncrement(&g_cRefDll);
  }
  else
  {
    v6 = 0;
  }
  *a3 = v6;
  ((void (__fastcall *)(struct IUnknown *))v6->lpVtbl->AddRef)(v6);
  return 0;
}

```

## disassembly

```asm
0x180008240  mov     [rsp+arg_0], rbx
0x180008245  mov     [rsp+arg_10], rsi
0x18000824a  push    rdi
0x18000824b  sub     rsp, 20h
0x18000824f  mov     rsi, r8
0x180008252  test    rdx, rdx
0x180008255  jz      short loc_180008261
0x180008257  mov     eax, 80040110h
0x18000825c  jmp     loc_1800082E3
0x180008261  mov     ecx, 40h ; '@'; Size
0x180008266  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000826b  mov     rdi, rax
0x18000826e  mov     [rsp+28h+arg_8], rax
0x180008273  test    rax, rax
0x180008276  jz      short loc_1800082CD
0x180008278  mov     dword ptr [rax+10h], 0
0x18000827f  lea     rax, ??_7CMtfPropertyBag@mtf@ipx@@6BIMtfPropertyBag@@@; const ipx::mtf::CMtfPropertyBag::`vftable'{for `IMtfPropertyBag'}
0x180008286  mov     [rdi], rax
0x180008289  lea     rax, ??_7CMtfPropertyBag@mtf@ipx@@6B?$_MtfIUnknownImpl_Helper@UIMtfSerializable@@XXXX@@@; const ipx::mtf::CMtfPropertyBag::`vftable'{for `_MtfIUnknownImpl_Helper<IMtfSerializable,void,void,void,void>'}
0x180008290  mov     [rdi+8], rax
0x180008294  xor     eax, eax
0x180008296  mov     [rdi+18h], rax
0x18000829a  mov     [rdi+20h], rax
0x18000829e  mov     [rdi+28h], rax
0x1800082a2  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBU_CLIENT_KEY@@V?$RefPtr@VMtfTransportClientCoreUI@mtf@ipx@@@@@std@@V?$allocator@U?$pair@$$CBU_CLIENT_KEY@@V?$RefPtr@VMtfTransportClientCoreUI@mtf@ipx@@@@@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBU_CLIENT_KEY@@V?$RefPtr@VMtfTransportClientCoreUI@mtf@ipx@@@@@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<_CLIENT_KEY const,RefPtr<ipx::mtf::MtfTransportClientCoreUI>>>>::_Buyheadnode(void)
0x1800082a7  mov     [rdi+20h], rax
0x1800082ab  mov     qword ptr [rdi+30h], 0
0x1800082b3  mov     qword ptr [rdi+38h], 0
0x1800082bb  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBGV?$RefPtr@UIUnknown@@@@@std@@V?$allocator@U?$pair@$$CBGV?$RefPtr@UIUnknown@@@@@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBGV?$RefPtr@UIUnknown@@@@@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<ushort const,RefPtr<IUnknown>>>>::_Buyheadnode(void)
0x1800082c0  mov     [rdi+30h], rax
0x1800082c4  lock inc cs:?g_cRefDll@@3JA; long g_cRefDll
0x1800082cb  jmp     short loc_1800082CF
0x1800082cd  xor     edi, edi
0x1800082cf  mov     [rsi], rdi
0x1800082d2  mov     rax, [rdi]
0x1800082d5  mov     rcx, rdi
0x1800082d8  mov     rax, [rax+8]
0x1800082dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082e1  xor     eax, eax
0x1800082e3  mov     rbx, [rsp+28h+arg_0]
0x1800082e8  mov     rsi, [rsp+28h+arg_10]
0x1800082ed  add     rsp, 20h
0x1800082f1  pop     rdi
0x1800082f2  retn
```
