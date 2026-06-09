# CInkPicture::FinalRelease(void)

- ea: `0x1800e8538`
- end: `0x1800e8750`
- name: `?FinalRelease@CInkPicture@@QEAAXXZ`
- size: `536`
- prototype: `void __fastcall(CInkPicture *__hidden this)`
- caller_count: `2`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180048438`
- `0x180048e1c`

## callees

- `0x180001c20`
- `0x180002740`
- `0x1800217b0`
- `0x1800229cc`
- `0x1800365f8`
- `0x180036824`
- `0x1800a9758`
- `0x1800ae918`
- `0x1800e8538`
- `0x1800eef24`
- `0x1800f0988`
- `0x1800f4624`
- `0x18010c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800e872f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800e872f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e8726`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e8726`
- `USER32!SendMessageW` at `0x1800e85f4`
- `USER32!SendMessageW` at `0x1800e85f4`
- `USER32!DestroyWindow` at `0x1800e8617`
- `USER32!DestroyWindow` at `0x1800e8617`
- `USER32!IsWindow` at `0x1800e8606`
- `USER32!IsWindow` at `0x1800e8606`
- `GDI32!DeleteObject` at `0x1800e8564`
- `GDI32!DeleteObject` at `0x1800e8581`
- `GDI32!DeleteObject` at `0x1800e8564`
- `GDI32!DeleteObject` at `0x1800e8581`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CInkPicture::FinalRelease(CInkPicture *this)
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

  ATL::AtlComPtrAssign((struct IUnknown **)this + 123, 0);
  v2 = (void *)*((_QWORD *)this + 167);
  if ( v2 )
  {
    DeleteObject(v2);
    *((_QWORD *)this + 167) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 168);
  if ( v3 )
  {
    DeleteObject(v3);
    *((_QWORD *)this + 168) = 0;
  }
  v4 = *((_QWORD *)this + 94);
  if ( v4 )
  {
    CTabletEventSink::SetCollector(v4, 0);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)this + 94) + 64LL) + 16LL))(*((_QWORD *)this + 94) + 64LL);
    *((_QWORD *)this + 94) = 0;
  }
  CInkPicture::_put_Enabled(this, 0, 1);
  CInkPicture::_FreeAllTabletContexts(this, 1);
  SendMessageW(*((HWND *)this + 21), *((_DWORD *)this + 224), 0, (LPARAM)this);
  v5 = (HWND)*((_QWORD *)this + 124);
  if ( v5 && IsWindow(v5) )
    DestroyWindow(*((HWND *)this + 124));
  CInkAutoDataLock::CInkAutoDataLock((CInkAutoDataLock *)v10, (struct _RTL_CRITICAL_SECTION *)((char *)this + 496));
  ATL::CComPtr<IInkRecognizer>::Release((char *)this + 808);
  CInkAutoDataLock::~CInkAutoDataLock((CInkAutoDataLock *)v10);
  CInkPicture::_CreateGestureObjects(this, 0);
  if ( *((_QWORD *)this + 74) )
    ATL::AtlComPtrAssign((struct IUnknown **)this + 74, 0);
  v6 = *((_QWORD *)this + 75);
  if ( v6 )
  {
    ATL::CComQIPtr<PIInkRenderer,&__s_GUID const _GUID_8d7b1448_7629_47a0_9b88_a986ef25648c>::CComQIPtr<PIInkRenderer,&__s_GUID const _GUID_8d7b1448_7629_47a0_9b88_a986ef25648c>(
      &v11,
      v6);
    if ( v11 )
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v11 + 80LL))(
        v11,
        ((unsigned __int64)this + 8) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64));
    ATL::CComPtr<IInkRecognizer>::Release((char *)this + 600);
    ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&v11);
  }
  ATL::CComPtr<IInkRecognizer>::Release((char *)this + 760);
  ATL::CComPtr<IInkRecognizer>::Release((char *)this + 768);
  v7 = *((_QWORD *)this + 105);
  if ( v7 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    *((_QWORD *)this + 105) = 0;
  }
  v8 = (void *)*((_QWORD *)this + 87);
  if ( v8 )
    WinFree(v8);
  if ( *((_QWORD *)this + 171) )
    ATL::AtlComPtrAssign((struct IUnknown **)this + 171, 0);
  v9 = (void *)*((_QWORD *)this + 83);
  if ( v9 )
    CloseHandle(v9);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 496));
  ATL::CComPtr<IInkRecognizer>::Release((char *)this + 480);
}

```

## disassembly

```asm
0x1800e8538  mov     [rsp+arg_8], rbx
0x1800e853d  mov     [rsp+arg_10], rsi
0x1800e8542  push    rdi
0x1800e8543  sub     rsp, 30h
0x1800e8547  mov     rbx, rcx
0x1800e854a  add     rcx, 3D8h; struct IUnknown **
0x1800e8551  xor     edx, edx; struct IUnknown *
0x1800e8553  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800e8558  mov     rcx, [rbx+538h]; ho
0x1800e855f  test    rcx, rcx
0x1800e8562  jz      short loc_1800E8575
0x1800e8564  call    cs:__imp_DeleteObject
0x1800e856a  mov     qword ptr [rbx+538h], 0
0x1800e8575  mov     rcx, [rbx+540h]; ho
0x1800e857c  test    rcx, rcx
0x1800e857f  jz      short loc_1800E8592
0x1800e8581  call    cs:__imp_DeleteObject
0x1800e8587  mov     qword ptr [rbx+540h], 0
0x1800e8592  mov     rcx, [rbx+2F0h]
0x1800e8599  test    rcx, rcx
0x1800e859c  jz      short loc_1800E85C7
0x1800e859e  xor     edx, edx
0x1800e85a0  call    ?SetCollector@CTabletEventSink@@QEAAXPEAV?$CComObject@VCInkCollector@@@ATL@@@Z; CTabletEventSink::SetCollector(ATL::CComObject<CInkCollector> *)
0x1800e85a5  mov     rcx, [rbx+2F0h]
0x1800e85ac  add     rcx, 40h ; '@'
0x1800e85b0  mov     rax, [rcx]
0x1800e85b3  mov     rax, [rax+10h]
0x1800e85b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e85bc  mov     qword ptr [rbx+2F0h], 0
0x1800e85c7  xor     edx, edx; __int16
0x1800e85c9  lea     edi, [rdx+1]
0x1800e85cc  mov     r8d, edi; int
0x1800e85cf  mov     rcx, rbx; this
0x1800e85d2  call    ?_put_Enabled@CInkPicture@@AEAAJFH@Z; CInkPicture::_put_Enabled(short,int)
0x1800e85d7  mov     edx, edi; int
0x1800e85d9  mov     rcx, rbx; this
0x1800e85dc  call    ?_FreeAllTabletContexts@CInkPicture@@AEAAJH@Z; CInkPicture::_FreeAllTabletContexts(int)
0x1800e85e1  mov     r9, rbx; lParam
0x1800e85e4  xor     r8d, r8d; wParam
0x1800e85e7  mov     edx, [rbx+380h]; Msg
0x1800e85ed  mov     rcx, [rbx+0A8h]; hWnd
0x1800e85f4  call    cs:__imp_SendMessageW
0x1800e85fa  mov     rcx, [rbx+3E0h]; hWnd
0x1800e8601  test    rcx, rcx
0x1800e8604  jz      short loc_1800E861D
0x1800e8606  call    cs:__imp_IsWindow
0x1800e860c  test    eax, eax
0x1800e860e  jz      short loc_1800E861D
0x1800e8610  mov     rcx, [rbx+3E0h]; hWnd
0x1800e8617  call    cs:__imp_DestroyWindow
0x1800e861d  lea     rsi, [rbx+1F0h]
0x1800e8624  mov     rdx, rsi; struct _RTL_CRITICAL_SECTION *
0x1800e8627  lea     rcx, [rsp+38h+var_18]; this
0x1800e862c  call    ??0CInkAutoDataLock@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInkAutoDataLock::CInkAutoDataLock(_RTL_CRITICAL_SECTION *)
0x1800e8631  nop
0x1800e8632  lea     rcx, [rbx+328h]
0x1800e8639  call    ?Release@?$CComPtr@UIInkRecognizer@@@ATL@@QEAAXXZ; ATL::CComPtr<IInkRecognizer>::Release(void)
0x1800e863e  nop
0x1800e863f  lea     rcx, [rsp+38h+var_18]; this
0x1800e8644  call    ??1CInkAutoDataLock@@QEAA@XZ; CInkAutoDataLock::~CInkAutoDataLock(void)
0x1800e8649  xor     edx, edx; bool
0x1800e864b  mov     rcx, rbx; this
0x1800e864e  call    ?_CreateGestureObjects@CInkPicture@@AEAAJ_N@Z; CInkPicture::_CreateGestureObjects(bool)
0x1800e8653  lea     rcx, [rbx+250h]; struct IUnknown **
0x1800e865a  cmp     qword ptr [rcx], 0
0x1800e865e  jz      short loc_1800E8667
0x1800e8660  xor     edx, edx; struct IUnknown *
0x1800e8662  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800e8667  lea     rdi, [rbx+258h]
0x1800e866e  mov     rdx, [rdi]
0x1800e8671  test    rdx, rdx
0x1800e8674  jz      short loc_1800E86BA
0x1800e8676  lea     rcx, [rsp+38h+arg_0]
0x1800e867b  call    ??0?$CComQIPtr@UPIInkRenderer@@$1?_GUID_8d7b1448_7629_47a0_9b88_a986ef25648c@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<PIInkRenderer,&__s_GUID const _GUID_8d7b1448_7629_47a0_9b88_a986ef25648c>::CComQIPtr<PIInkRenderer,&__s_GUID const _GUID_8d7b1448_7629_47a0_9b88_a986ef25648c>(IUnknown *)
0x1800e8680  nop
0x1800e8681  mov     rcx, [rsp+38h+arg_0]
0x1800e8686  test    rcx, rcx
0x1800e8689  jz      short loc_1800E86A7
0x1800e868b  mov     r9, [rcx]
0x1800e868e  mov     rax, rbx
0x1800e8691  lea     r8, [rbx+8]
0x1800e8695  neg     rax
0x1800e8698  sbb     rdx, rdx
0x1800e869b  and     rdx, r8
0x1800e869e  mov     rax, [r9+50h]
0x1800e86a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e86a7  mov     rcx, rdi
0x1800e86aa  call    ?Release@?$CComPtr@UIInkRecognizer@@@ATL@@QEAAXXZ; ATL::CComPtr<IInkRecognizer>::Release(void)
0x1800e86af  nop
0x1800e86b0  lea     rcx, [rsp+38h+arg_0]; void *
0x1800e86b5  call    ??1?$CComPtr@UITablet2@@@ATL@@QEAA@XZ; ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(void)
0x1800e86ba  lea     rcx, [rbx+2F8h]
0x1800e86c1  call    ?Release@?$CComPtr@UIInkRecognizer@@@ATL@@QEAAXXZ; ATL::CComPtr<IInkRecognizer>::Release(void)
0x1800e86c6  lea     rcx, [rbx+300h]
0x1800e86cd  call    ?Release@?$CComPtr@UIInkRecognizer@@@ATL@@QEAAXXZ; ATL::CComPtr<IInkRecognizer>::Release(void)
0x1800e86d2  mov     rcx, [rbx+348h]
0x1800e86d9  test    rcx, rcx
0x1800e86dc  jz      short loc_1800E86F5
0x1800e86de  mov     rax, [rcx]
0x1800e86e1  mov     rax, [rax+10h]
0x1800e86e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e86ea  mov     qword ptr [rbx+348h], 0
0x1800e86f5  mov     rcx, [rbx+2B8h]; void *
0x1800e86fc  test    rcx, rcx
0x1800e86ff  jz      short loc_1800E8706
0x1800e8701  call    ?WinFree@@YAXPEAX@Z; WinFree(void *)
0x1800e8706  lea     rcx, [rbx+558h]; struct IUnknown **
0x1800e870d  cmp     qword ptr [rcx], 0
0x1800e8711  jz      short loc_1800E871A
0x1800e8713  xor     edx, edx; struct IUnknown *
0x1800e8715  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800e871a  mov     rcx, [rbx+298h]; hObject
0x1800e8721  test    rcx, rcx
0x1800e8724  jz      short loc_1800E872C
0x1800e8726  call    cs:__imp_CloseHandle
0x1800e872c  mov     rcx, rsi; lpCriticalSection
0x1800e872f  call    cs:__imp_DeleteCriticalSection
0x1800e8735  lea     rcx, [rbx+1E0h]
0x1800e873c  mov     rbx, [rsp+38h+arg_8]
0x1800e8741  mov     rsi, [rsp+38h+arg_10]
0x1800e8746  add     rsp, 30h
0x1800e874a  pop     rdi
0x1800e874b  jmp     ?Release@?$CComPtr@UIInkRecognizer@@@ATL@@QEAAXXZ; ATL::CComPtr<IInkRecognizer>::Release(void)
```
