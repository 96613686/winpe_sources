# CInkOverlay::FinalRelease(void)

- ea: `0x1800da308`
- end: `0x1800da509`
- name: `?FinalRelease@CInkOverlay@@QEAAXXZ`
- size: `513`
- prototype: `void __fastcall(CInkOverlay *__hidden this)`
- caller_count: `2`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1800483fc`
- `0x180048d94`

## callees

- `0x180001c20`
- `0x180002740`
- `0x1800217b0`
- `0x1800229cc`
- `0x1800365f8`
- `0x180036824`
- `0x1800a9758`
- `0x1800ae918`
- `0x1800b06d0`
- `0x1800da308`
- `0x1800e0668`
- `0x1800e3354`
- `0x18010c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800da4e8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800da4e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800da4df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800da4df`
- `USER32!SendMessageW` at `0x1800da3c1`
- `USER32!SendMessageW` at `0x1800da3c1`
- `USER32!DestroyWindow` at `0x1800da3e4`
- `USER32!DestroyWindow` at `0x1800da3e4`
- `USER32!IsWindow` at `0x1800da3d3`
- `USER32!IsWindow` at `0x1800da3d3`
- `GDI32!DeleteObject` at `0x1800da334`
- `GDI32!DeleteObject` at `0x1800da351`
- `GDI32!DeleteObject` at `0x1800da334`
- `GDI32!DeleteObject` at `0x1800da351`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CInkOverlay::FinalRelease(CInkOverlay *this)
{
  void *v2; // rcx
  void *v3; // rcx
  __int64 v4; // rcx
  HWND v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  _BYTE v10[24]; // [rsp+20h] [rbp-18h] BYREF
  __int64 v11; // [rsp+40h] [rbp+8h] BYREF

  ATL::AtlComPtrAssign((struct IUnknown **)this + 95, 0);
  v2 = (void *)*((_QWORD *)this + 140);
  if ( v2 )
  {
    DeleteObject(v2);
    *((_QWORD *)this + 140) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 141);
  if ( v3 )
  {
    DeleteObject(v3);
    *((_QWORD *)this + 141) = 0;
  }
  v4 = *((_QWORD *)this + 66);
  if ( v4 )
  {
    CTabletEventSink::SetCollector(v4, 0);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)this + 66) + 64LL) + 16LL))(*((_QWORD *)this + 66) + 64LL);
    *((_QWORD *)this + 66) = 0;
  }
  CInkOverlay::_put_Enabled(this, 0, 1);
  CInkOverlay::_FreeAllTabletContexts(this, 1);
  SendMessageW(*((HWND *)this + 7), *((_DWORD *)this + 168), 0, (LPARAM)this);
  v5 = (HWND)*((_QWORD *)this + 96);
  if ( v5 && IsWindow(v5) )
    DestroyWindow(*((HWND *)this + 96));
  CInkAutoDataLock::CInkAutoDataLock((CInkAutoDataLock *)v10, (struct _RTL_CRITICAL_SECTION *)((char *)this + 272));
  ATL::CComPtr<IInkRecognizer>::Release((char *)this + 584);
  CInkAutoDataLock::~CInkAutoDataLock((CInkAutoDataLock *)v10);
  CInkCollector::_CreateGestureObjects(this, 0);
  if ( *((_QWORD *)this + 46) )
    ATL::AtlComPtrAssign((struct IUnknown **)this + 46, 0);
  v6 = *((_QWORD *)this + 47);
  if ( v6 )
  {
    ATL::CComQIPtr<PIInkRenderer,&__s_GUID const _GUID_8d7b1448_7629_47a0_9b88_a986ef25648c>::CComQIPtr<PIInkRenderer,&__s_GUID const _GUID_8d7b1448_7629_47a0_9b88_a986ef25648c>(
      &v11,
      v6);
    if ( v11 )
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v11 + 80LL))(
        v11,
        ((unsigned __int64)this + 8) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64));
    ATL::CComPtr<IInkRecognizer>::Release((char *)this + 376);
    ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&v11);
  }
  ATL::CComPtr<IInkRecognizer>::Release((char *)this + 536);
  ATL::CComPtr<IInkRecognizer>::Release((char *)this + 544);
  v7 = *((_QWORD *)this + 77);
  if ( v7 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    *((_QWORD *)this + 77) = 0;
  }
  v8 = (void *)*((_QWORD *)this + 59);
  if ( v8 )
    WinFree(v8);
  v9 = (void *)*((_QWORD *)this + 55);
  if ( v9 )
    CloseHandle(v9);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 272));
  ATL::CComPtr<IInkRecognizer>::Release((char *)this + 256);
}

```

## disassembly

```asm
0x1800da308  mov     [rsp+arg_8], rbx
0x1800da30d  mov     [rsp+arg_10], rsi
0x1800da312  push    rdi
0x1800da313  sub     rsp, 30h
0x1800da317  mov     rbx, rcx
0x1800da31a  add     rcx, 2F8h; struct IUnknown **
0x1800da321  xor     edx, edx; struct IUnknown *
0x1800da323  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800da328  mov     rcx, [rbx+460h]; ho
0x1800da32f  test    rcx, rcx
0x1800da332  jz      short loc_1800DA345
0x1800da334  call    cs:__imp_DeleteObject
0x1800da33a  mov     qword ptr [rbx+460h], 0
0x1800da345  mov     rcx, [rbx+468h]; ho
0x1800da34c  test    rcx, rcx
0x1800da34f  jz      short loc_1800DA362
0x1800da351  call    cs:__imp_DeleteObject
0x1800da357  mov     qword ptr [rbx+468h], 0
0x1800da362  mov     rcx, [rbx+210h]
0x1800da369  test    rcx, rcx
0x1800da36c  jz      short loc_1800DA397
0x1800da36e  xor     edx, edx
0x1800da370  call    ?SetCollector@CTabletEventSink@@QEAAXPEAV?$CComObject@VCInkCollector@@@ATL@@@Z; CTabletEventSink::SetCollector(ATL::CComObject<CInkCollector> *)
0x1800da375  mov     rcx, [rbx+210h]
0x1800da37c  add     rcx, 40h ; '@'
0x1800da380  mov     rax, [rcx]
0x1800da383  mov     rax, [rax+10h]
0x1800da387  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da38c  mov     qword ptr [rbx+210h], 0
0x1800da397  xor     edx, edx; __int16
0x1800da399  lea     edi, [rdx+1]
0x1800da39c  mov     r8d, edi; int
0x1800da39f  mov     rcx, rbx; this
0x1800da3a2  call    ?_put_Enabled@CInkOverlay@@AEAAJFH@Z; CInkOverlay::_put_Enabled(short,int)
0x1800da3a7  mov     edx, edi; int
0x1800da3a9  mov     rcx, rbx; this
0x1800da3ac  call    ?_FreeAllTabletContexts@CInkOverlay@@AEAAJH@Z; CInkOverlay::_FreeAllTabletContexts(int)
0x1800da3b1  mov     r9, rbx; lParam
0x1800da3b4  xor     r8d, r8d; wParam
0x1800da3b7  mov     edx, [rbx+2A0h]; Msg
0x1800da3bd  mov     rcx, [rbx+38h]; hWnd
0x1800da3c1  call    cs:__imp_SendMessageW
0x1800da3c7  mov     rcx, [rbx+300h]; hWnd
0x1800da3ce  test    rcx, rcx
0x1800da3d1  jz      short loc_1800DA3EA
0x1800da3d3  call    cs:__imp_IsWindow
0x1800da3d9  test    eax, eax
0x1800da3db  jz      short loc_1800DA3EA
0x1800da3dd  mov     rcx, [rbx+300h]; hWnd
0x1800da3e4  call    cs:__imp_DestroyWindow
0x1800da3ea  lea     rsi, [rbx+110h]
0x1800da3f1  mov     rdx, rsi; struct _RTL_CRITICAL_SECTION *
0x1800da3f4  lea     rcx, [rsp+38h+var_18]; this
0x1800da3f9  call    ??0CInkAutoDataLock@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInkAutoDataLock::CInkAutoDataLock(_RTL_CRITICAL_SECTION *)
0x1800da3fe  nop
0x1800da3ff  lea     rcx, [rbx+248h]
0x1800da406  call    ?Release@?$CComPtr@UIInkRecognizer@@@ATL@@QEAAXXZ; ATL::CComPtr<IInkRecognizer>::Release(void)
0x1800da40b  nop
0x1800da40c  lea     rcx, [rsp+38h+var_18]; this
0x1800da411  call    ??1CInkAutoDataLock@@QEAA@XZ; CInkAutoDataLock::~CInkAutoDataLock(void)
0x1800da416  xor     edx, edx; bool
0x1800da418  mov     rcx, rbx; this
0x1800da41b  call    ?_CreateGestureObjects@CInkCollector@@AEAAJ_N@Z; CInkCollector::_CreateGestureObjects(bool)
0x1800da420  lea     rcx, [rbx+170h]; struct IUnknown **
0x1800da427  cmp     qword ptr [rcx], 0
0x1800da42b  jz      short loc_1800DA434
0x1800da42d  xor     edx, edx; struct IUnknown *
0x1800da42f  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800da434  lea     rdi, [rbx+178h]
0x1800da43b  mov     rdx, [rdi]
0x1800da43e  test    rdx, rdx
0x1800da441  jz      short loc_1800DA487
0x1800da443  lea     rcx, [rsp+38h+arg_0]
0x1800da448  call    ??0?$CComQIPtr@UPIInkRenderer@@$1?_GUID_8d7b1448_7629_47a0_9b88_a986ef25648c@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<PIInkRenderer,&__s_GUID const _GUID_8d7b1448_7629_47a0_9b88_a986ef25648c>::CComQIPtr<PIInkRenderer,&__s_GUID const _GUID_8d7b1448_7629_47a0_9b88_a986ef25648c>(IUnknown *)
0x1800da44d  nop
0x1800da44e  mov     rcx, [rsp+38h+arg_0]
0x1800da453  test    rcx, rcx
0x1800da456  jz      short loc_1800DA474
0x1800da458  mov     r9, [rcx]
0x1800da45b  mov     rax, rbx
0x1800da45e  lea     r8, [rbx+8]
0x1800da462  neg     rax
0x1800da465  sbb     rdx, rdx
0x1800da468  and     rdx, r8
0x1800da46b  mov     rax, [r9+50h]
0x1800da46f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da474  mov     rcx, rdi
0x1800da477  call    ?Release@?$CComPtr@UIInkRecognizer@@@ATL@@QEAAXXZ; ATL::CComPtr<IInkRecognizer>::Release(void)
0x1800da47c  nop
0x1800da47d  lea     rcx, [rsp+38h+arg_0]; void *
0x1800da482  call    ??1?$CComPtr@UITablet2@@@ATL@@QEAA@XZ; ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(void)
0x1800da487  lea     rcx, [rbx+218h]
0x1800da48e  call    ?Release@?$CComPtr@UIInkRecognizer@@@ATL@@QEAAXXZ; ATL::CComPtr<IInkRecognizer>::Release(void)
0x1800da493  lea     rcx, [rbx+220h]
0x1800da49a  call    ?Release@?$CComPtr@UIInkRecognizer@@@ATL@@QEAAXXZ; ATL::CComPtr<IInkRecognizer>::Release(void)
0x1800da49f  mov     rcx, [rbx+268h]
0x1800da4a6  test    rcx, rcx
0x1800da4a9  jz      short loc_1800DA4C2
0x1800da4ab  mov     rax, [rcx]
0x1800da4ae  mov     rax, [rax+10h]
0x1800da4b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da4b7  mov     qword ptr [rbx+268h], 0
0x1800da4c2  mov     rcx, [rbx+1D8h]; void *
0x1800da4c9  test    rcx, rcx
0x1800da4cc  jz      short loc_1800DA4D3
0x1800da4ce  call    ?WinFree@@YAXPEAX@Z; WinFree(void *)
0x1800da4d3  mov     rcx, [rbx+1B8h]; hObject
0x1800da4da  test    rcx, rcx
0x1800da4dd  jz      short loc_1800DA4E5
0x1800da4df  call    cs:__imp_CloseHandle
0x1800da4e5  mov     rcx, rsi; lpCriticalSection
0x1800da4e8  call    cs:__imp_DeleteCriticalSection
0x1800da4ee  lea     rcx, [rbx+100h]
0x1800da4f5  mov     rbx, [rsp+38h+arg_8]
0x1800da4fa  mov     rsi, [rsp+38h+arg_10]
0x1800da4ff  add     rsp, 30h
0x1800da503  pop     rdi
0x1800da504  jmp     ?Release@?$CComPtr@UIInkRecognizer@@@ATL@@QEAAXXZ; ATL::CComPtr<IInkRecognizer>::Release(void)
```
