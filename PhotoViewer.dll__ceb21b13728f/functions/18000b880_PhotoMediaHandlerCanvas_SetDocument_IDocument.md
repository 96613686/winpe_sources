# PhotoMediaHandlerCanvas::SetDocument(IDocument *)

- ea: `0x18000b880`
- end: `0x18000bb3c`
- name: `?SetDocument@PhotoMediaHandlerCanvas@@UEAAJPEAVIDocument@@@Z`
- size: `700`
- prototype: `int(PhotoMediaHandlerCanvas *__hidden this, struct IDocument *)`
- caller_count: `0`
- callee_count: `17`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000b880`
- `0x18000bb44`
- `0x18000bb70`
- `0x18000bca0`
- `0x18000c1e4`
- `0x18000cb74`
- `0x18000d850`
- `0x180025a84`
- `0x18002e790`
- `0x18002efec`
- `0x18002f200`
- `0x180033a80`
- `0x180035204`
- `0x180038640`
- `0x18005d6f8`
- `0x18005dc44`
- `0x180080010`

## import_xrefs

- `USER32!IsWindow` at `0x18000bafd`
- `USER32!IsWindow` at `0x18000bafd`
- `USER32!InvalidateRect` at `0x18000bb14`
- `USER32!InvalidateRect` at `0x18000bb14`
- `USER32!UpdateWindow` at `0x18000bb21`
- `USER32!UpdateWindow` at `0x18000bb21`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18000b8a7`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18000b8da`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18000ba76`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18000b8a7`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18000b8da`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18000ba76`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall PhotoMediaHandlerCanvas::SetDocument(PhotoMediaHandlerCanvas *this, struct IDocument *a2)
{
  PhotoMediaHandlerCanvas *v4; // rbx
  struct IUnknown **v5; // r15
  struct IEngine *Engine; // rax
  int v7; // eax
  int v8; // edx
  struct IPhotoDocument **v9; // r14
  __int64 v10; // rcx
  struct IUnknown *v11; // rdx
  bool v12; // r15
  __int64 v13; // rdx
  __int64 v14; // r8
  _DWORD *v15; // rdx
  __int64 v16; // rcx
  PhotoMediaHandlerCanvas *v17; // rcx
  struct IDisplayView *v18; // rdx
  int v19; // eax
  int v20; // edx
  int v21; // edx
  BOOL v22; // ecx
  struct IUnknown *v23; // rcx
  struct IEngine *v24; // rax
  __int64 result; // rax
  _BYTE v26[72]; // [rsp+20h] [rbp-48h] BYREF
  __int64 v27; // [rsp+70h] [rbp+8h] BYREF
  struct IUnknown *v28; // [rsp+80h] [rbp+18h] BYREF
  __int64 v29; // [rsp+88h] [rbp+20h] BYREF

  try
  {
    v4 = (PhotoMediaHandlerCanvas *)((char *)this - 144);
    if ( !*((_BYTE *)this + 2380) )
      Base::Throw((Base *)0x80004005LL, (_DWORD)a2);
    v5 = (struct IUnknown **)((char *)this + 2528);
    if ( a2 != *((struct IDocument **)this + 316) )
    {
      Engine = PhotoEngine::GetEngine(this);
      v7 = (*(__int64 (__fastcall **)(struct IEngine *))(*(_QWORD *)Engine + 120LL))(Engine);
      if ( v7 < 0 )
        Base::Throw((Base *)(unsigned int)v7, v8);
      v9 = (struct IPhotoDocument **)((char *)this + 2536);
      v10 = *((_QWORD *)this + 317);
      if ( v10 )
      {
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v10 + 40LL))(
          v10,
          ((unsigned __int64)this + 16) & ((unsigned __int128)-(__int128)(unsigned __int64)v4 >> 64));
        (*(void (__fastcall **)(struct IPhotoDocument *, _QWORD))(*(_QWORD *)*v9 + 176LL))(*v9, 0);
      }
      if ( *v5 != (struct IUnknown *)a2 )
        ATL::AtlComPtrAssign(v5, (struct IUnknown *)a2);
      v11 = 0;
      v28 = 0;
      if ( a2 )
      {
        (**(void (__fastcall ***)(struct IDocument *, GUID *, struct IUnknown **))a2)(
          a2,
          &GUID_e2c10a63_113c_46f3_86dd_fae67e722f30,
          &v28);
        v11 = v28;
      }
      if ( *v9 != (struct IPhotoDocument *)v11 )
        ATL::AtlComPtrAssign((struct IUnknown **)this + 317, v11);
      v12 = *v5 != 0;
      v13 = *((_QWORD *)this + 11);
      v29 = v13;
      while ( v13 )
      {
        ATL::CComPtrBase<IEaselPhodeo>::CComPtrBase<IEaselPhodeo>(&v27, *(_QWORD *)(v13 + 16));
        if ( v4 )
          v15 = (_DWORD *)((char *)v4 + 152);
        else
          v15 = 0;
        LOBYTE(v14) = v12;
         ITweakerDisplayEventSink::`vcall'{24,{flat}}(v27, v15, v14);
        ATL::CAtlList<ATL::CComQIPtr<IEaselPhodeoEventSink,&__s_GUID const _GUID_c7061507_0070_4aad_8548_fd93e8221e42>,ATL::CComQIPtrElementTraits<IEaselPhodeoEventSink,&__s_GUID const _GUID_c7061507_0070_4aad_8548_fd93e8221e42>>::GetNext(
          v16,
          &v29);
        ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v27);
        v13 = v29;
      }
      v17 = *v9;
      if ( *v9 )
      {
        LOBYTE(v13) = 1;
        (*(void (__fastcall **)(PhotoMediaHandlerCanvas *, __int64))(*(_QWORD *)v17 + 176LL))(v17, v13);
        (*(void (__fastcall **)(struct IPhotoDocument *, _QWORD))(*(_QWORD *)*v9 + 32LL))(
          *v9,
          ((unsigned __int64)this + 16) & ((unsigned __int128)-(__int128)(unsigned __int64)v4 >> 64));
        PhotoMediaHandlerCanvas::SetIsBestFitZoom(v4, 1);
      }
      v18 = (struct IDisplayView *)*((_QWORD *)this + 314);
      if ( v18 )
      {
        PhotoMediaHandlerCanvas::UpdateViewRenderingState(v17, v18, *v9);
        PhotoMediaHandlerCanvas::UpdateDocumentGraph(v4);
        PhotoMediaHandlerCanvas::RecalculateBestFitZoom(v4);
        PhotoMediaHandlerCanvas::UpdateBackgroundColorProfile(v4);
      }
      PhotoMediaHandlerCanvas::UpdateErrorMessage(v4);
      if ( a2 )
      {
        LODWORD(v27) = 0;
        v19 = (*(__int64 (__fastcall **)(struct IDocument *, __int64 *))(*(_QWORD *)a2 + 104LL))(a2, &v27);
        if ( v19 < 0 )
          Base::Throw((Base *)(unsigned int)v19, v20);
        v22 = IsPending(v27);
      }
      else
      {
        v22 = 0;
        v21 = 0;
      }
      *((_DWORD *)this + 600) = v21;
      *((_DWORD *)v4 + 637) = v22;
      PhotoMediaHandlerCanvas::UpdateOverlay(v4);
      PhotoMediaHandlerCanvas::UpdateCursor(v4);
      v23 = v28;
      if ( v28 )
        ((void (__fastcall *)(struct IUnknown *))v28->lpVtbl->Release)(v28);
      v24 = PhotoEngine::GetEngine((PhotoEngine *)v23);
      (*(void (__fastcall **)(struct IEngine *))(*(_QWORD *)v24 + 128LL))(v24);
      if ( *v9 && IsWindow(*((HWND *)this - 17)) )
      {
        InvalidateRect(*((HWND *)this - 17), 0, 1);
        UpdateWindow(*((HWND *)this - 17));
      }
    }
    result = 0;
  }
  catch ( Base::Exception v26 )
  {
    LODWORD(v27) = Base::Exception::operator long(v26);
    Base::Exception::~Exception((Base::Exception *)v26);
    return (unsigned int)v27;
  }
  return result;
}

```

## disassembly

```asm
0x18000b880  push    rbx
0x18000b882  push    rsi
0x18000b883  push    rdi
0x18000b884  push    r14
0x18000b886  push    r15
0x18000b888  sub     rsp, 40h
0x18000b88c  mov     rsi, rdx
0x18000b88f  mov     rdi, rcx
0x18000b892  lea     rbx, [rcx-90h]
0x18000b899  cmp     byte ptr [rbx+9DCh], 0
0x18000b8a0  jnz     short loc_18000B8AD
0x18000b8a2  mov     ecx, 80004005h
0x18000b8a7  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18000b8ad  lea     r15, [rcx+9E0h]
0x18000b8b4  cmp     rsi, [r15]
0x18000b8b7  jz      loc_18000BB28
0x18000b8bd  call    ?GetEngine@PhotoEngine@@QEAAPEAUIEngine@@XZ; PhotoEngine::GetEngine(void)
0x18000b8c2  mov     rdx, rax
0x18000b8c5  mov     rcx, [rax]
0x18000b8c8  mov     rax, [rcx+78h]
0x18000b8cc  mov     rcx, rdx
0x18000b8cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b8d4  test    eax, eax
0x18000b8d6  jns     short loc_18000B8E1
0x18000b8d8  mov     ecx, eax
0x18000b8da  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18000b8e0  nop
0x18000b8e1  lea     r14, [rdi+9E8h]
0x18000b8e8  mov     rcx, [r14]
0x18000b8eb  test    rcx, rcx
0x18000b8ee  jz      short loc_18000B920
0x18000b8f0  mov     r9, [rcx]
0x18000b8f3  mov     rax, rbx
0x18000b8f6  lea     r8, [rdi+10h]
0x18000b8fa  neg     rax
0x18000b8fd  sbb     rdx, rdx
0x18000b900  and     rdx, r8
0x18000b903  mov     rax, [r9+28h]
0x18000b907  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b90c  mov     rcx, [r14]
0x18000b90f  mov     rax, [rcx]
0x18000b912  xor     edx, edx
0x18000b914  mov     rax, [rax+0B0h]
0x18000b91b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b920  cmp     [r15], rsi
0x18000b923  jz      short loc_18000B931
0x18000b925  mov     rdx, rsi; struct IUnknown *
0x18000b928  mov     rcx, r15; struct IUnknown **
0x18000b92b  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18000b930  nop
0x18000b931  xor     edx, edx
0x18000b933  mov     [rsp+68h+arg_10], rdx
0x18000b93b  test    rsi, rsi
0x18000b93e  jz      short loc_18000B965
0x18000b940  mov     rax, [rsi]
0x18000b943  lea     r8, [rsp+68h+arg_10]
0x18000b94b  lea     rdx, _GUID_e2c10a63_113c_46f3_86dd_fae67e722f30
0x18000b952  mov     rcx, rsi
0x18000b955  mov     rax, [rax]
0x18000b958  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b95d  mov     rdx, [rsp+68h+arg_10]; struct IUnknown *
0x18000b965  cmp     [r14], rdx
0x18000b968  jz      short loc_18000B972
0x18000b96a  mov     rcx, r14; struct IUnknown **
0x18000b96d  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18000b972  cmp     qword ptr [r15], 0
0x18000b976  setnz   r15b
0x18000b97a  mov     rdx, [rdi+58h]
0x18000b97e  mov     [rsp+68h+arg_18], rdx
0x18000b986  test    rdx, rdx
0x18000b989  jz      short loc_18000B9D9
0x18000b98b  mov     rdx, [rdx+10h]
0x18000b98f  lea     rcx, [rsp+68h+arg_0]
0x18000b994  call    ??0?$CComPtrBase@VIEaselPhodeo@@@ATL@@IEAA@PEAVIEaselPhodeo@@@Z; ATL::CComPtrBase<IEaselPhodeo>::CComPtrBase<IEaselPhodeo>(IEaselPhodeo *)
0x18000b999  nop
0x18000b99a  test    rbx, rbx
0x18000b99d  jz      short loc_18000B9A8
0x18000b99f  lea     rdx, [rbx+98h]
0x18000b9a6  jmp     short loc_18000B9AA
0x18000b9a8  xor     edx, edx
0x18000b9aa  mov     r8b, r15b
0x18000b9ad  mov     rcx, [rsp+68h+arg_0]
0x18000b9b2  call    ??_9ITweakerDisplayEventSink@@$BBI@AA; [thunk]: ITweakerDisplayEventSink::`vcall'{24,{flat}}
0x18000b9b7  lea     rdx, [rsp+68h+arg_18]
0x18000b9bf  call    ?GetNext@?$CAtlList@V?$CComQIPtr@VIEaselPhodeoEventSink@@$1?_GUID_c7061507_0070_4aad_8548_fd93e8221e42@@3U__s_GUID@@B@ATL@@V?$CComQIPtrElementTraits@VIEaselPhodeoEventSink@@$1?_GUID_c7061507_0070_4aad_8548_fd93e8221e42@@3U__s_GUID@@B@2@@ATL@@QEAAAEAV?$CComQIPtr@VIEaselPhodeoEventSink@@$1?_GUID_c7061507_0070_4aad_8548_fd93e8221e42@@3U__s_GUID@@B@2@AEAPEAU__POSITION@@@Z; ATL::CAtlList<ATL::CComQIPtr<IEaselPhodeoEventSink,&__s_GUID const _GUID_c7061507_0070_4aad_8548_fd93e8221e42>,ATL::CComQIPtrElementTraits<IEaselPhodeoEventSink,&__s_GUID const _GUID_c7061507_0070_4aad_8548_fd93e8221e42>>::GetNext(__POSITION * &)
0x18000b9c4  nop
0x18000b9c5  lea     rcx, [rsp+68h+arg_0]
0x18000b9ca  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x18000b9cf  mov     rdx, [rsp+68h+arg_18]
0x18000b9d7  jmp     short loc_18000B986
0x18000b9d9  mov     rcx, [r14]
0x18000b9dc  test    rcx, rcx
0x18000b9df  jz      short loc_18000BA1B
0x18000b9e1  mov     rax, [rcx]
0x18000b9e4  mov     dl, 1
0x18000b9e6  mov     rax, [rax+0B0h]
0x18000b9ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9f2  mov     rcx, [r14]
0x18000b9f5  mov     r9, [rcx]
0x18000b9f8  mov     rax, rbx
0x18000b9fb  lea     r8, [rdi+10h]
0x18000b9ff  neg     rax
0x18000ba02  sbb     rdx, rdx
0x18000ba05  and     rdx, r8
0x18000ba08  mov     rax, [r9+20h]
0x18000ba0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba11  mov     dl, 1; bool
0x18000ba13  mov     rcx, rbx; this
0x18000ba16  call    ?SetIsBestFitZoom@PhotoMediaHandlerCanvas@@AEAAX_N@Z; PhotoMediaHandlerCanvas::SetIsBestFitZoom(bool)
0x18000ba1b  mov     rdx, [rdi+9D0h]; struct IDisplayView *
0x18000ba22  test    rdx, rdx
0x18000ba25  jz      short loc_18000BA47
0x18000ba27  mov     r8, [r14]; struct IPhotoDocument *
0x18000ba2a  call    ?UpdateViewRenderingState@PhotoMediaHandlerCanvas@@AEAAXPEAUIDisplayView@@PEAVIPhotoDocument@@@Z; PhotoMediaHandlerCanvas::UpdateViewRenderingState(IDisplayView *,IPhotoDocument *)
0x18000ba2f  mov     rcx, rbx; this
0x18000ba32  call    ?UpdateDocumentGraph@PhotoMediaHandlerCanvas@@AEAAXXZ; PhotoMediaHandlerCanvas::UpdateDocumentGraph(void)
0x18000ba37  mov     rcx, rbx; this
0x18000ba3a  call    ?RecalculateBestFitZoom@PhotoMediaHandlerCanvas@@AEAAXXZ; PhotoMediaHandlerCanvas::RecalculateBestFitZoom(void)
0x18000ba3f  mov     rcx, rbx; this
0x18000ba42  call    ?UpdateBackgroundColorProfile@PhotoMediaHandlerCanvas@@AEAAXXZ; PhotoMediaHandlerCanvas::UpdateBackgroundColorProfile(void)
0x18000ba47  mov     rcx, rbx; this
0x18000ba4a  call    ?UpdateErrorMessage@PhotoMediaHandlerCanvas@@AEAAXXZ; PhotoMediaHandlerCanvas::UpdateErrorMessage(void)
0x18000ba4f  test    rsi, rsi
0x18000ba52  jz      short loc_18000BA95
0x18000ba54  mov     dword ptr [rsp+68h+arg_0], 0
0x18000ba5c  mov     rax, [rsi]
0x18000ba5f  lea     rdx, [rsp+68h+arg_0]
0x18000ba64  mov     rcx, rsi
0x18000ba67  mov     rax, [rax+68h]
0x18000ba6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba70  test    eax, eax
0x18000ba72  jns     short loc_18000BA7C
0x18000ba74  mov     ecx, eax
0x18000ba76  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18000ba7c  xor     edx, edx
0x18000ba7e  mov     ecx, dword ptr [rsp+68h+arg_0]; int
0x18000ba82  cmp     ecx, 8000000Ah
0x18000ba88  setz    dl
0x18000ba8b  call    ?IsPending@@YA_NJ@Z; IsPending(long)
0x18000ba90  movzx   ecx, al
0x18000ba93  jmp     short loc_18000BA99
0x18000ba95  xor     ecx, ecx
0x18000ba97  xor     edx, edx
0x18000ba99  mov     eax, 960h
0x18000ba9e  mov     r8, rdi
0x18000baa1  mov     [rdi+rax], edx
0x18000baa4  mov     [rbx+9F4h], ecx
0x18000baaa  mov     rcx, rbx; this
0x18000baad  call    ?UpdateOverlay@PhotoMediaHandlerCanvas@@AEAAXXZ; PhotoMediaHandlerCanvas::UpdateOverlay(void)
0x18000bab2  mov     rcx, rbx; this
0x18000bab5  call    ?UpdateCursor@PhotoMediaHandlerCanvas@@AEAAXXZ; PhotoMediaHandlerCanvas::UpdateCursor(void)
0x18000baba  nop
0x18000babb  mov     rcx, [rsp+68h+arg_10]
0x18000bac3  test    rcx, rcx
0x18000bac6  jz      short loc_18000BAD5
0x18000bac8  mov     rax, [rcx]
0x18000bacb  mov     rax, [rax+10h]
0x18000bacf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bad4  nop
0x18000bad5  call    ?GetEngine@PhotoEngine@@QEAAPEAUIEngine@@XZ; PhotoEngine::GetEngine(void)
0x18000bada  mov     rdx, rax
0x18000badd  mov     rcx, [rax]
0x18000bae0  mov     rax, [rcx+80h]
0x18000bae7  mov     rcx, rdx
0x18000baea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000baef  nop
0x18000baf0  cmp     qword ptr [r14], 0
0x18000baf4  jz      short loc_18000BB28
0x18000baf6  mov     rcx, [rdi-88h]; hWnd
0x18000bafd  call    cs:__imp_IsWindow
0x18000bb03  test    eax, eax
0x18000bb05  jz      short loc_18000BB28
0x18000bb07  xor     edx, edx; lpRect
0x18000bb09  lea     r8d, [rdx+1]; bErase
0x18000bb0d  mov     rcx, [rdi-88h]; hWnd
0x18000bb14  call    cs:__imp_InvalidateRect
0x18000bb1a  mov     rcx, [rdi-88h]; hWnd
0x18000bb21  call    cs:__imp_UpdateWindow
0x18000bb27  nop
0x18000bb28  xor     eax, eax
0x18000bb2a  jmp     short loc_18000BB30
0x18000bb2c  mov     eax, dword ptr [rsp+68h+arg_0]
0x18000bb30  add     rsp, 40h
0x18000bb34  pop     r15
0x18000bb36  pop     r14
0x18000bb38  pop     rdi
0x18000bb39  pop     rsi
0x18000bb3a  pop     rbx
0x18000bb3b  retn
```
