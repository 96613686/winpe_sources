# FrameWindow::~FrameWindow(void)

- ea: `0x180020090`
- end: `0x18002033b`
- name: `??1FrameWindow@@UEAA@XZ`
- size: `683`
- prototype: `void __fastcall(FrameWindow *__hidden this)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callers

- `0x180016710`
- `0x180020830`
- `0x180033586`

## callees

- `0x180001900`
- `0x18001eb60`
- `0x18001fc5c`
- `0x18001fdfc`
- `0x180020020`
- `0x180020090`
- `0x18002d4c4`
- `0x180035010`

## import_xrefs

- `GDI32!DeleteObject` at `0x180020273`
- `GDI32!DeleteObject` at `0x180020294`
- `GDI32!DeleteObject` at `0x1800202b5`
- `GDI32!DeleteObject` at `0x180020273`
- `GDI32!DeleteObject` at `0x180020294`
- `GDI32!DeleteObject` at `0x1800202b5`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall FrameWindow::~FrameWindow(FrameWindow *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  volatile signed __int32 *v5; // rdx
  volatile signed __int32 *v6; // rdx
  volatile signed __int32 *v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // rcx
  AtlThunkData_t *v10; // rcx
  void *v11; // rcx
  void *v12; // rcx
  void *v13; // rcx
  volatile signed __int32 *v14; // rbx
  AtlThunkData_t *v15; // rcx
  AtlThunkData_t *v16; // rcx

  *(_QWORD *)this = &FrameWindow::`vftable'{for `WTL::CFrameWindowImpl<FrameWindow,ATL::CWindow,ATL::CWinTraits<0,262144>>'};
  *((_QWORD *)this + 13) = &FrameWindow::`vftable'{for `WTL::CMessageFilter'};
  (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 89) + 56LL))(
    *((_QWORD *)this + 89),
    *((unsigned int *)this + 138),
    *((unsigned __int8 *)this + 432));
  (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 89) + 48LL))(
    *((_QWORD *)this + 89),
    *((unsigned int *)this + 138),
    *((unsigned __int8 *)this + 435),
    *((unsigned __int8 *)this + 441));
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 89) + 64LL))(*((_QWORD *)this + 89));
  v2 = *((_QWORD *)this + 71);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 32LL))(v2);
  v3 = *((_QWORD *)this + 90);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  v4 = *((_QWORD *)this + 89);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  v5 = (volatile signed __int32 *)(*((_QWORD *)this + 78) - 24LL);
  if ( _InterlockedDecrement(v5 + 4) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v5 + 8LL))(*(_QWORD *)v5);
  v6 = (volatile signed __int32 *)(*((_QWORD *)this + 77) - 24LL);
  if ( _InterlockedDecrement(v6 + 4) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v6 + 8LL))(*(_QWORD *)v6);
  v7 = (volatile signed __int32 *)(*((_QWORD *)this + 76) - 24LL);
  if ( _InterlockedDecrement(v7 + 4) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v7 + 8LL))(*(_QWORD *)v7);
  v8 = *((_QWORD *)this + 72);
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  v9 = *((_QWORD *)this + 71);
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  std::deque<enum PluginId>::~deque<enum PluginId>((__int64)this + 504);
  std::vector<enum PluginId>::~vector<enum PluginId>((char **)this + 60);
  std::_Tree<std::_Tmap_traits<enum PluginId,std::vector<std::shared_ptr<PluginPendingMessage>>,std::less<enum PluginId>,std::allocator<std::pair<enum PluginId const,std::vector<std::shared_ptr<PluginPendingMessage>>>>,0>>::~_Tree<std::_Tmap_traits<enum PluginId,std::vector<std::shared_ptr<PluginPendingMessage>>,std::less<enum PluginId>,std::allocator<std::pair<enum PluginId const,std::vector<std::shared_ptr<PluginPendingMessage>>>>,0>>((void **)this + 58);
  std::_Tree_val<std::_Tree_simple_types<std::pair<enum PluginId const,std::shared_ptr<BrowserToolThreadInfo>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<enum PluginId const,std::shared_ptr<BrowserToolThreadInfo>>,void *>>>(
    (__int64)this + 448,
    (__int64)this + 448,
    *(_QWORD *)(*((_QWORD *)this + 56) + 8LL));
  operator delete(*((void **)this + 56));
  v10 = (AtlThunkData_t *)*((_QWORD *)this + 40);
  if ( v10 )
    AtlThunk_FreeData(v10);
  v11 = (void *)*((_QWORD *)this + 34);
  if ( v11 && DeleteObject(v11) )
    *((_QWORD *)this + 34) = 0;
  v12 = (void *)*((_QWORD *)this + 33);
  if ( v12 && DeleteObject(v12) )
    *((_QWORD *)this + 33) = 0;
  v13 = (void *)*((_QWORD *)this + 32);
  if ( v13 && DeleteObject(v13) )
    *((_QWORD *)this + 32) = 0;
  v14 = (volatile signed __int32 *)*((_QWORD *)this + 31);
  if ( v14 )
  {
    if ( !_InterlockedDecrement(v14 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
      if ( !_InterlockedDecrement(v14 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
    }
  }
  v15 = (AtlThunkData_t *)*((_QWORD *)this + 23);
  if ( v15 )
    AtlThunk_FreeData(v15);
  v16 = (AtlThunkData_t *)*((_QWORD *)this + 5);
  if ( v16 )
    AtlThunk_FreeData(v16);
}

```

## disassembly

```asm
0x180020090  mov     [rsp+arg_0], rbx
0x180020095  mov     [rsp+arg_8], rbp
0x18002009a  push    rdi
0x18002009b  sub     rsp, 30h
0x18002009f  mov     rdi, rcx
0x1800200a2  lea     rax, ??_7FrameWindow@@6B?$CFrameWindowImpl@VFrameWindow@@VCWindow@ATL@@V?$CWinTraits@$0A@$0EAAAA@@3@@WTL@@@; const FrameWindow::`vftable'{for `WTL::CFrameWindowImpl<FrameWindow,ATL::CWindow,ATL::CWinTraits<0,262144>>'}
0x1800200a9  mov     [rcx], rax
0x1800200ac  lea     rax, ??_7FrameWindow@@6BCMessageFilter@WTL@@@; const FrameWindow::`vftable'{for `WTL::CMessageFilter'}
0x1800200b3  mov     [rcx+68h], rax
0x1800200b7  mov     rcx, [rcx+2C8h]
0x1800200be  mov     rax, [rcx]
0x1800200c1  movzx   r8d, byte ptr [rdi+1B0h]
0x1800200c9  mov     edx, [rdi+228h]
0x1800200cf  mov     rax, [rax+38h]
0x1800200d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800200d8  mov     rcx, [rdi+2C8h]
0x1800200df  mov     rax, [rcx]
0x1800200e2  movzx   r9d, byte ptr [rdi+1B9h]
0x1800200ea  movzx   r8d, byte ptr [rdi+1B3h]
0x1800200f2  mov     edx, [rdi+228h]
0x1800200f8  mov     rax, [rax+30h]
0x1800200fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020101  mov     rcx, [rdi+2C8h]
0x180020108  mov     rax, [rcx]
0x18002010b  mov     rax, [rax+40h]
0x18002010f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020114  mov     rcx, [rdi+238h]
0x18002011b  test    rcx, rcx
0x18002011e  jz      short loc_18002012D
0x180020120  mov     rax, [rcx]
0x180020123  mov     rax, [rax+20h]
0x180020127  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002012c  nop
0x18002012d  mov     rcx, [rdi+2D0h]
0x180020134  test    rcx, rcx
0x180020137  jz      short loc_180020146
0x180020139  mov     rax, [rcx]
0x18002013c  mov     rax, [rax+10h]
0x180020140  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020145  nop
0x180020146  mov     rcx, [rdi+2C8h]
0x18002014d  test    rcx, rcx
0x180020150  jz      short loc_18002015F
0x180020152  mov     rax, [rcx]
0x180020155  mov     rax, [rax+10h]
0x180020159  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002015e  nop
0x18002015f  mov     rdx, [rdi+270h]
0x180020166  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18002016a  or      ebp, 0FFFFFFFFh
0x18002016d  mov     eax, ebp
0x18002016f  lock xadd [rdx+10h], eax
0x180020174  add     eax, ebp
0x180020176  test    eax, eax
0x180020178  jg      short loc_180020189
0x18002017a  mov     rcx, [rdx]
0x18002017d  mov     rax, [rcx]
0x180020180  mov     rax, [rax+8]
0x180020184  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020189  mov     rdx, [rdi+268h]
0x180020190  add     rdx, 0FFFFFFFFFFFFFFE8h
0x180020194  mov     eax, ebp
0x180020196  lock xadd [rdx+10h], eax
0x18002019b  add     eax, ebp
0x18002019d  test    eax, eax
0x18002019f  jg      short loc_1800201B0
0x1800201a1  mov     rcx, [rdx]
0x1800201a4  mov     rax, [rcx]
0x1800201a7  mov     rax, [rax+8]
0x1800201ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800201b0  mov     rdx, [rdi+260h]
0x1800201b7  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1800201bb  mov     eax, ebp
0x1800201bd  lock xadd [rdx+10h], eax
0x1800201c2  add     eax, ebp
0x1800201c4  test    eax, eax
0x1800201c6  jg      short loc_1800201D8
0x1800201c8  mov     rcx, [rdx]
0x1800201cb  mov     rax, [rcx]
0x1800201ce  mov     rax, [rax+8]
0x1800201d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800201d7  nop
0x1800201d8  mov     rcx, [rdi+240h]
0x1800201df  test    rcx, rcx
0x1800201e2  jz      short loc_1800201F1
0x1800201e4  mov     rax, [rcx]
0x1800201e7  mov     rax, [rax+10h]
0x1800201eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800201f0  nop
0x1800201f1  mov     rcx, [rdi+238h]
0x1800201f8  test    rcx, rcx
0x1800201fb  jz      short loc_18002020A
0x1800201fd  mov     rax, [rcx]
0x180020200  mov     rax, [rax+10h]
0x180020204  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020209  nop
0x18002020a  lea     rcx, [rdi+1F8h]
0x180020211  call    ??1?$deque@W4PluginId@@V?$allocator@W4PluginId@@@std@@@std@@QEAA@XZ; std::deque<PluginId>::~deque<PluginId>(void)
0x180020216  lea     rcx, [rdi+1E0h]
0x18002021d  call    ??1?$vector@W4PluginId@@V?$allocator@W4PluginId@@@std@@@std@@QEAA@XZ; std::vector<PluginId>::~vector<PluginId>(void)
0x180020222  lea     rcx, [rdi+1D0h]
0x180020229  call    ??1?$_Tree@V?$_Tmap_traits@W4PluginId@@V?$vector@V?$shared_ptr@UPluginPendingMessage@@@std@@V?$allocator@V?$shared_ptr@UPluginPendingMessage@@@std@@@2@@std@@U?$less@W4PluginId@@@3@V?$allocator@U?$pair@$$CBW4PluginId@@V?$vector@V?$shared_ptr@UPluginPendingMessage@@@std@@V?$allocator@V?$shared_ptr@UPluginPendingMessage@@@std@@@2@@std@@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<PluginId,std::vector<std::shared_ptr<PluginPendingMessage>>,std::less<PluginId>,std::allocator<std::pair<PluginId const,std::vector<std::shared_ptr<PluginPendingMessage>>>>,0>>::~_Tree<std::_Tmap_traits<PluginId,std::vector<std::shared_ptr<PluginPendingMessage>>,std::less<PluginId>,std::allocator<std::pair<PluginId const,std::vector<std::shared_ptr<PluginPendingMessage>>>>,0>>(void)
0x18002022e  lea     rbx, [rdi+1C0h]
0x180020235  mov     r8, [rbx]
0x180020238  mov     r8, [r8+8]
0x18002023c  mov     rdx, rbx
0x18002023f  mov     rcx, rbx
0x180020242  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBW4PluginId@@V?$shared_ptr@UBrowserToolThreadInfo@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4PluginId@@V?$shared_ptr@UBrowserToolThreadInfo@@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBW4PluginId@@V?$shared_ptr@UBrowserToolThreadInfo@@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBW4PluginId@@V?$shared_ptr@UBrowserToolThreadInfo@@@std@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<PluginId const,std::shared_ptr<BrowserToolThreadInfo>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<PluginId const,std::shared_ptr<BrowserToolThreadInfo>>,void *>>>(std::allocator<std::_Tree_node<std::pair<PluginId const,std::shared_ptr<BrowserToolThreadInfo>>,void *>> &,std::_Tree_node<std::pair<PluginId const,std::shared_ptr<BrowserToolThreadInfo>>,void *> *)
0x180020247  mov     edx, 38h ; '8'
0x18002024c  mov     rcx, [rbx]; Block
0x18002024f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180020254  nop
0x180020255  mov     rcx, [rdi+140h]; Thunk
0x18002025c  test    rcx, rcx
0x18002025f  jz      short loc_180020267
0x180020261  call    AtlThunk_FreeData
0x180020266  nop
0x180020267  mov     rcx, [rdi+110h]; ho
0x18002026e  test    rcx, rcx
0x180020271  jz      short loc_180020288
0x180020273  call    cs:__imp_DeleteObject
0x180020279  test    eax, eax
0x18002027b  jz      short loc_180020288
0x18002027d  mov     qword ptr [rdi+110h], 0
0x180020288  mov     rcx, [rdi+108h]; ho
0x18002028f  test    rcx, rcx
0x180020292  jz      short loc_1800202A9
0x180020294  call    cs:__imp_DeleteObject
0x18002029a  test    eax, eax
0x18002029c  jz      short loc_1800202A9
0x18002029e  mov     qword ptr [rdi+108h], 0
0x1800202a9  mov     rcx, [rdi+100h]; ho
0x1800202b0  test    rcx, rcx
0x1800202b3  jz      short loc_1800202CA
0x1800202b5  call    cs:__imp_DeleteObject
0x1800202bb  test    eax, eax
0x1800202bd  jz      short loc_1800202CA
0x1800202bf  mov     qword ptr [rdi+100h], 0
0x1800202ca  mov     rbx, [rdi+0F8h]
0x1800202d1  test    rbx, rbx
0x1800202d4  jz      short loc_18002030A
0x1800202d6  mov     eax, ebp
0x1800202d8  lock xadd [rbx+8], eax
0x1800202dd  add     eax, ebp
0x1800202df  jnz     short loc_18002030A
0x1800202e1  mov     rax, [rbx]
0x1800202e4  mov     rcx, rbx
0x1800202e7  mov     rax, [rax]
0x1800202ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800202ef  mov     eax, ebp
0x1800202f1  lock xadd [rbx+0Ch], eax
0x1800202f6  add     eax, ebp
0x1800202f8  jnz     short loc_18002030A
0x1800202fa  mov     rax, [rbx]
0x1800202fd  mov     rcx, rbx
0x180020300  mov     rax, [rax+8]
0x180020304  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020309  nop
0x18002030a  mov     rcx, [rdi+0B8h]; Thunk
0x180020311  test    rcx, rcx
0x180020314  jz      short loc_18002031C
0x180020316  call    AtlThunk_FreeData
0x18002031b  nop
0x18002031c  mov     rcx, [rdi+28h]; Thunk
0x180020320  test    rcx, rcx
0x180020323  jz      short loc_18002032B
0x180020325  call    AtlThunk_FreeData
0x18002032a  nop
0x18002032b  mov     rbx, [rsp+38h+arg_0]
0x180020330  mov     rbp, [rsp+38h+arg_8]
0x180020335  add     rsp, 30h
0x180020339  pop     rdi
0x18002033a  retn
```
