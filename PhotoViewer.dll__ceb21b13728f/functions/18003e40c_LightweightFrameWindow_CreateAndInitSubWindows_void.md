# LightweightFrameWindow::CreateAndInitSubWindows(void)

- ea: `0x18003e40c`
- end: `0x18003e5cc`
- name: `?CreateAndInitSubWindows@LightweightFrameWindow@@AEAAXXZ`
- size: `448`
- prototype: `void __fastcall(LightweightFrameWindow *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18003e39c`

## callees

- `0x18000cb74`
- `0x180022410`
- `0x180032634`
- `0x18003e40c`
- `0x180067630`
- `0x180067758`
- `0x180080010`

## import_xrefs

- `dwmapi!DwmIsCompositionEnabled` at `0x18003e58e`
- `dwmapi!DwmIsCompositionEnabled` at `0x18003e58e`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003e425`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003e441`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003e461`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003e483`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003e4a3`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003e4e1`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003e515`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003e539`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003e55d`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003e59a`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003e425`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003e441`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003e461`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003e483`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003e4a3`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003e4e1`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003e515`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003e539`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003e55d`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003e59a`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall LightweightFrameWindow::CreateAndInitSubWindows(LightweightFrameWindow *this, __int64 a2)
{
  _QWORD *v3; // rbx
  int Instance; // eax
  int v5; // edx
  int v6; // eax
  int v7; // edx
  int v8; // edx
  int v9; // eax
  int v10; // edx
  int v11; // eax
  int v12; // edx
  __int64 v13; // rbx
  __int64 v14; // rdx
  int v15; // edx
  int v16; // eax
  int v17; // edx
  int v18; // eax
  int v19; // edx
  HRESULT IsCompositionEnabled; // eax
  int v21; // edx
  __int64 pfEnabled; // [rsp+40h] [rbp+20h] BYREF
  __int64 v23; // [rsp+48h] [rbp+28h] BYREF
  __int64 v24; // [rsp+50h] [rbp+30h] BYREF
  __int64 v25; // [rsp+58h] [rbp+38h]

  if ( !*((_BYTE *)this + 32) )
  {
    Base::Throw((Base *)0x80004005LL, a2);
    __debugbreak();
  }
  v3 = (_QWORD *)((char *)this + 152);
  Instance = ATL::CComCreator<ATL::CComObject<NavigationPane>>::CreateInstance(this, a2, (char *)this + 152);
  if ( Instance < 0 )
  {
    Base::Throw((Base *)(unsigned int)Instance, v5);
    __debugbreak();
  }
  v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v3 + 32LL))(*v3, *((_QWORD *)this + 6));
  if ( v6 < 0 )
  {
    Base::Throw((Base *)(unsigned int)v6, v7);
    __debugbreak();
  }
  ATL::CComQIPtr<IModularWindowUIControl,&__s_GUID const _GUID_066128bb_b234_49ed_8735_981ba9a7c488>::CComQIPtr<IModularWindowUIControl,&__s_GUID const _GUID_066128bb_b234_49ed_8735_981ba9a7c488>(
    &v24,
    *v3);
  if ( !v24 )
  {
    Base::Throw((Base *)0x80004002LL, v8);
    __debugbreak();
  }
  v9 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v24 + 24LL))(v24, *((_QWORD *)this + 39));
  if ( v9 < 0 )
  {
    Base::Throw((Base *)(unsigned int)v9, v10);
    __debugbreak();
  }
  v25 = 0;
  pfEnabled = 0;
  v11 = ATL::CComObject<PagePane>::CreateInstance(&pfEnabled);
  if ( v11 < 0 )
  {
    Base::Throw((Base *)(unsigned int)v11, v12);
    __debugbreak();
  }
  v13 = pfEnabled;
  v25 = pfEnabled;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(pfEnabled + 72) + 8LL))(pfEnabled + 72);
  if ( v13 )
    v14 = v13 + 144;
  else
    v14 = 0;
  *((_QWORD *)this + 18) = v14;
  ATL::CComQIPtr<IModularWindowUIControl,&__s_GUID const _GUID_066128bb_b234_49ed_8735_981ba9a7c488>::CComQIPtr<IModularWindowUIControl,&__s_GUID const _GUID_066128bb_b234_49ed_8735_981ba9a7c488>(
    &v23,
    v14);
  if ( !v23 )
  {
    Base::Throw((Base *)0x80004002LL, v15);
    __debugbreak();
  }
  v16 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 18) + 32LL))(
          *((_QWORD *)this + 18),
          *((_QWORD *)this + 6));
  if ( v16 < 0 )
  {
    Base::Throw((Base *)(unsigned int)v16, v17);
    __debugbreak();
  }
  v18 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v23 + 24LL))(v23, *((_QWORD *)this + 39));
  if ( v18 < 0 )
  {
    Base::Throw((Base *)(unsigned int)v18, v19);
    __debugbreak();
  }
  (*(void (__fastcall **)(char *))(*((_QWORD *)this + 5) + 32LL))((char *)this + 40);
  *((_QWORD *)this + 27) = *((_QWORD *)this + 6);
  LODWORD(pfEnabled) = 0;
  IsCompositionEnabled = DwmIsCompositionEnabled((BOOL *)&pfEnabled);
  if ( IsCompositionEnabled < 0 )
  {
    Base::Throw((Base *)(unsigned int)IsCompositionEnabled, v21);
    __debugbreak();
  }
  UIBase::TopLevelWindowCompositionHelper::UpdateDisplayCompositionState(
    (LightweightFrameWindow *)((char *)this + 208),
    (_DWORD)pfEnabled != 0);
  ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v23);
  ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v24);
}

```

## disassembly

```asm
0x18003e40c  push    rbp
0x18003e40e  push    rbx
0x18003e40f  push    rdi
0x18003e410  mov     rbp, rsp
0x18003e413  sub     rsp, 20h
0x18003e417  mov     rdi, rcx
0x18003e41a  cmp     byte ptr [rcx+20h], 0
0x18003e41e  jnz     short loc_18003E42C
0x18003e420  mov     ecx, 80004005h
0x18003e425  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18003e42b  int     3; Trap to Debugger
0x18003e42c  lea     rbx, [rcx+98h]
0x18003e433  mov     r8, rbx
0x18003e436  call    ?CreateInstance@?$CComCreator@V?$CComObject@VNavigationPane@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<NavigationPane>>::CreateInstance(void *,_GUID const &,void * *)
0x18003e43b  test    eax, eax
0x18003e43d  jns     short loc_18003E448
0x18003e43f  mov     ecx, eax
0x18003e441  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18003e447  int     3; Trap to Debugger
0x18003e448  mov     rcx, [rbx]
0x18003e44b  mov     rax, [rcx]
0x18003e44e  mov     rdx, [rdi+30h]
0x18003e452  mov     rax, [rax+20h]
0x18003e456  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e45b  test    eax, eax
0x18003e45d  jns     short loc_18003E468
0x18003e45f  mov     ecx, eax
0x18003e461  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18003e467  int     3; Trap to Debugger
0x18003e468  mov     rdx, [rbx]
0x18003e46b  lea     rcx, [rbp+arg_10]
0x18003e46f  call    ??0?$CComQIPtr@UIModularWindowUIControl@@$1?_GUID_066128bb_b234_49ed_8735_981ba9a7c488@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<IModularWindowUIControl,&__s_GUID const _GUID_066128bb_b234_49ed_8735_981ba9a7c488>::CComQIPtr<IModularWindowUIControl,&__s_GUID const _GUID_066128bb_b234_49ed_8735_981ba9a7c488>(IUnknown *)
0x18003e474  nop
0x18003e475  mov     rcx, [rbp+arg_10]
0x18003e479  test    rcx, rcx
0x18003e47c  jnz     short loc_18003E48A
0x18003e47e  mov     ecx, 80004002h
0x18003e483  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18003e489  int     3; Trap to Debugger
0x18003e48a  mov     rax, [rcx]
0x18003e48d  mov     rdx, [rdi+138h]
0x18003e494  mov     rax, [rax+18h]
0x18003e498  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e49d  test    eax, eax
0x18003e49f  jns     short loc_18003E4AA
0x18003e4a1  mov     ecx, eax
0x18003e4a3  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18003e4a9  int     3; Trap to Debugger
0x18003e4aa  xor     ebx, ebx
0x18003e4ac  mov     [rbp+arg_18], rbx
0x18003e4b0  mov     [rbp+pfEnabled], rbx
0x18003e4b4  lea     rcx, [rbp+pfEnabled]
0x18003e4b8  call    ?CreateInstance@?$CComObject@VPagePane@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<PagePane>::CreateInstance(ATL::CComObject<PagePane> * *)
0x18003e4bd  test    eax, eax
0x18003e4bf  js      short loc_18003E4DF
0x18003e4c1  mov     rbx, [rbp+pfEnabled]
0x18003e4c5  mov     [rbp+arg_18], rbx
0x18003e4c9  lea     rcx, [rbx+48h]
0x18003e4cd  mov     rax, [rcx]
0x18003e4d0  mov     rax, [rax+8]
0x18003e4d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e4d9  xor     eax, eax
0x18003e4db  test    eax, eax
0x18003e4dd  jns     short loc_18003E4E8
0x18003e4df  mov     ecx, eax
0x18003e4e1  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18003e4e7  int     3; Trap to Debugger
0x18003e4e8  test    rbx, rbx
0x18003e4eb  jz      short loc_18003E4F6
0x18003e4ed  lea     rdx, [rbx+90h]
0x18003e4f4  jmp     short loc_18003E4F8
0x18003e4f6  xor     edx, edx
0x18003e4f8  mov     [rdi+90h], rdx
0x18003e4ff  lea     rcx, [rbp+arg_8]
0x18003e503  call    ??0?$CComQIPtr@UIModularWindowUIControl@@$1?_GUID_066128bb_b234_49ed_8735_981ba9a7c488@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<IModularWindowUIControl,&__s_GUID const _GUID_066128bb_b234_49ed_8735_981ba9a7c488>::CComQIPtr<IModularWindowUIControl,&__s_GUID const _GUID_066128bb_b234_49ed_8735_981ba9a7c488>(IUnknown *)
0x18003e508  nop
0x18003e509  cmp     [rbp+arg_8], 0
0x18003e50e  jnz     short loc_18003E51C
0x18003e510  mov     ecx, 80004002h
0x18003e515  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18003e51b  int     3; Trap to Debugger
0x18003e51c  mov     rcx, [rdi+90h]
0x18003e523  mov     rax, [rcx]
0x18003e526  mov     rdx, [rdi+30h]
0x18003e52a  mov     rax, [rax+20h]
0x18003e52e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e533  test    eax, eax
0x18003e535  jns     short loc_18003E540
0x18003e537  mov     ecx, eax
0x18003e539  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18003e53f  int     3; Trap to Debugger
0x18003e540  mov     rcx, [rbp+arg_8]
0x18003e544  mov     rax, [rcx]
0x18003e547  mov     rdx, [rdi+138h]
0x18003e54e  mov     rax, [rax+18h]
0x18003e552  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e557  test    eax, eax
0x18003e559  jns     short loc_18003E564
0x18003e55b  mov     ecx, eax
0x18003e55d  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18003e563  int     3; Trap to Debugger
0x18003e564  lea     rcx, [rdi+28h]
0x18003e568  mov     rax, [rcx]
0x18003e56b  mov     rax, [rax+20h]
0x18003e56f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e574  lea     rbx, [rdi+0D0h]
0x18003e57b  mov     rax, [rdi+30h]
0x18003e57f  mov     [rbx+8], rax
0x18003e583  mov     dword ptr [rbp+pfEnabled], 0
0x18003e58a  lea     rcx, [rbp+pfEnabled]; pfEnabled
0x18003e58e  call    cs:__imp_DwmIsCompositionEnabled
0x18003e594  test    eax, eax
0x18003e596  jns     short loc_18003E5A1
0x18003e598  mov     ecx, eax
0x18003e59a  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18003e5a0  int     3; Trap to Debugger
0x18003e5a1  cmp     dword ptr [rbp+pfEnabled], 0
0x18003e5a5  setnz   dl; bool
0x18003e5a8  mov     rcx, rbx; this
0x18003e5ab  call    ?UpdateDisplayCompositionState@TopLevelWindowCompositionHelper@UIBase@@AEAAX_N@Z; UIBase::TopLevelWindowCompositionHelper::UpdateDisplayCompositionState(bool)
0x18003e5b0  nop
0x18003e5b1  lea     rcx, [rbp+arg_8]
0x18003e5b5  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x18003e5ba  nop
0x18003e5bb  lea     rcx, [rbp+arg_10]
0x18003e5bf  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x18003e5c4  add     rsp, 20h
0x18003e5c8  pop     rdi
0x18003e5c9  pop     rbx
0x18003e5ca  pop     rbp
0x18003e5cb  retn
```
