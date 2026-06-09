# MediaFrameHelpers::ConvertMFMediaBuffer(Microsoft::WRL::ComPtr<IMFMediaType> const &,Microsoft::WRL::ComPtr<IMFMediaBuffer> const &,_GUID const &,int,int,tagRECT const &)

- ea: `0x180004300`
- end: `0x180004456`
- name: `?ConvertMFMediaBuffer@MediaFrameHelpers@@SA?AV?$ComPtr@UIMFMediaBuffer@@@WRL@Microsoft@@AEBV?$ComPtr@UIMFMediaType@@@34@AEBV234@AEBU_GUID@@HHAEBUtagRECT@@@Z`
- size: `342`
- prototype: `__int64 __usercall@<rax>(IMFMediaBuffer **ppBuffer@<rcx>, DWORD dwWidth, DWORD dwHeight, struct tagRECT *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180002940`
- `0x180005d10`

## callees

- `0x1800019c0`
- `0x180004300`
- `0x180005940`
- `0x180005cd0`
- `0x180052010`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x180004342`
- `MFPlat!MFCreateMediaType` at `0x180004342`
- `MFPlat!MFCreate2DMediaBuffer` at `0x1800043f1`
- `MFPlat!MFCreate2DMediaBuffer` at `0x1800043f1`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
IMFMediaBuffer **__fastcall MediaFrameHelpers::ConvertMFMediaBuffer(
        IMFMediaBuffer **ppBuffer,
        struct IMFMediaType **a2,
        struct IMFMediaBuffer **a3,
        DWORD *a4,
        DWORD dwWidth,
        DWORD dwHeight,
        struct tagRECT *a7)
{
  unsigned int v11; // eax
  int v12; // edx
  unsigned int v13; // eax
  int v14; // edx
  unsigned int v15; // eax
  int v16; // edx
  unsigned int v17; // eax
  int v18; // edx
  unsigned int v19; // eax
  int v20; // edx
  IMFMediaType *v21; // rcx
  struct IMFDXGIDeviceManager *v23; // [rsp+30h] [rbp-20h]
  IMFMediaType *ppMFType; // [rsp+78h] [rbp+28h] BYREF

  ppMFType = 0;
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&ppMFType);
  v11 = MFCreateMediaType(&ppMFType);
  MF::ThrowIfFailed((MF *)v11, v12);
  v13 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, const GUID *))ppMFType->lpVtbl->SetGUID)(
          ppMFType,
          &MF_MT_MAJOR_TYPE,
          &MFMediaType_Video);
  MF::ThrowIfFailed((MF *)v13, v14);
  v15 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, DWORD *))ppMFType->lpVtbl->SetGUID)(
          ppMFType,
          &MF_MT_SUBTYPE,
          a4);
  MF::ThrowIfFailed((MF *)v15, v16);
  v17 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, unsigned __int64))ppMFType->lpVtbl->SetUINT64)(
          ppMFType,
          &MF_MT_FRAME_SIZE,
          dwHeight | ((unsigned __int64)dwWidth << 32));
  MF::ThrowIfFailed((MF *)v17, v18);
  *ppBuffer = 0;
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(ppBuffer);
  v19 = MFCreate2DMediaBuffer(dwWidth, dwHeight, *a4, 0, ppBuffer);
  MF::ThrowIfFailed((MF *)v19, v20);
  MediaFrameHelpers::XVPConvertMFMediaBuffer(*a3, *a2, a7, *ppBuffer, ppMFType, a7, v23);
  v21 = ppMFType;
  if ( ppMFType )
  {
    ppMFType = 0;
    ((void (__fastcall *)(IMFMediaType *))v21->lpVtbl->Release)(v21);
  }
  return ppBuffer;
}

```

## disassembly

```asm
0x180004300  mov     [rsp-18h+arg_10], rbx
0x180004305  mov     [rsp-18h+arg_18], rsi
0x18000430a  mov     [rsp-18h+arg_0], rcx
0x18000430f  push    rbp
0x180004310  push    rdi
0x180004311  push    r14
0x180004313  mov     rbp, rsp
0x180004316  sub     rsp, 50h
0x18000431a  mov     rbx, r9
0x18000431d  mov     rsi, r8
0x180004320  mov     rdi, rdx
0x180004323  mov     r14, rcx
0x180004326  mov     [rbp+var_10], 0
0x18000432d  mov     [rbp+ppMFType], 0
0x180004335  lea     rcx, [rbp+ppMFType]
0x180004339  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x18000433e  lea     rcx, [rbp+ppMFType]; ppMFType
0x180004342  call    cs:__imp_MFCreateMediaType
0x180004348  mov     ecx, eax; this
0x18000434a  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x18000434f  mov     rcx, [rbp+ppMFType]
0x180004353  mov     rax, [rcx]
0x180004356  lea     r8, MFMediaType_Video
0x18000435d  lea     rdx, MF_MT_MAJOR_TYPE
0x180004364  mov     rax, [rax+0C0h]
0x18000436b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004370  mov     ecx, eax; this
0x180004372  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x180004377  mov     rcx, [rbp+ppMFType]
0x18000437b  mov     rax, [rcx]
0x18000437e  mov     r8, rbx
0x180004381  lea     rdx, MF_MT_SUBTYPE
0x180004388  mov     rax, [rax+0C0h]
0x18000438f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004394  mov     ecx, eax; this
0x180004396  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x18000439b  mov     rcx, [rbp+ppMFType]
0x18000439f  mov     r9, [rcx]
0x1800043a2  mov     r8d, [rbp+dwWidth]
0x1800043a6  shl     r8, 20h
0x1800043aa  mov     eax, [rbp+dwHeight]
0x1800043ad  or      r8, rax
0x1800043b0  lea     rdx, MF_MT_FRAME_SIZE
0x1800043b7  mov     rax, [r9+0B0h]
0x1800043be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043c3  mov     ecx, eax; this
0x1800043c5  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x1800043ca  mov     qword ptr [r14], 0
0x1800043d1  mov     [rbp+var_10], 1
0x1800043d8  mov     rcx, r14
0x1800043db  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x1800043e0  mov     [rsp+50h+ppBuffer], r14; ppBuffer
0x1800043e5  xor     r9d, r9d; fBottomUp
0x1800043e8  mov     r8d, [rbx]; dwFourCC
0x1800043eb  mov     edx, [rbp+dwHeight]; dwHeight
0x1800043ee  mov     ecx, [rbp+dwWidth]; dwWidth
0x1800043f1  call    cs:__imp_MFCreate2DMediaBuffer
0x1800043f7  mov     ecx, eax; this
0x1800043f9  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x1800043fe  mov     r8, [rbp+arg_30]; struct tagRECT *
0x180004402  mov     [rsp+50h+var_28], r8; struct tagRECT *
0x180004407  mov     rax, [rbp+ppMFType]
0x18000440b  mov     [rsp+50h+ppBuffer], rax; struct IMFMediaType *
0x180004410  mov     r9, [r14]; struct IMFMediaBuffer *
0x180004413  mov     rdx, [rdi]; struct IMFMediaType *
0x180004416  mov     rcx, [rsi]; struct IMFMediaBuffer *
0x180004419  call    ?XVPConvertMFMediaBuffer@MediaFrameHelpers@@SAXPEAUIMFMediaBuffer@@PEAUIMFMediaType@@AEBUtagRECT@@012PEAUIMFDXGIDeviceManager@@@Z; MediaFrameHelpers::XVPConvertMFMediaBuffer(IMFMediaBuffer *,IMFMediaType *,tagRECT const &,IMFMediaBuffer *,IMFMediaType *,tagRECT const &,IMFDXGIDeviceManager *)
0x18000441e  nop
0x18000441f  mov     rcx, [rbp+ppMFType]
0x180004423  test    rcx, rcx
0x180004426  jz      short loc_18000443D
0x180004428  mov     [rbp+ppMFType], 0
0x180004430  mov     rax, [rcx]
0x180004433  mov     rax, [rax+10h]
0x180004437  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000443c  nop
0x18000443d  mov     rax, r14
0x180004440  lea     r11, [rsp+50h+var_s0]
0x180004445  mov     rbx, [r11+30h]
0x180004449  mov     rsi, [r11+38h]
0x18000444d  mov     rsp, r11
0x180004450  pop     r14
0x180004452  pop     rdi
0x180004453  pop     rbp
0x180004454  retn
```
