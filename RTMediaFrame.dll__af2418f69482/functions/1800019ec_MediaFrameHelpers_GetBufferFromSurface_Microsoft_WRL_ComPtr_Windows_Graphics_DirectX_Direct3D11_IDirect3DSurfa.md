# MediaFrameHelpers::GetBufferFromSurface(Microsoft::WRL::ComPtr<Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface> const &)

- ea: `0x1800019ec`
- end: `0x180001abc`
- name: `?GetBufferFromSurface@MediaFrameHelpers@@SA?AV?$ComPtr@UIMFMediaBuffer@@@WRL@Microsoft@@AEBV?$ComPtr@UIDirect3DSurface@Direct3D11@DirectX@Graphics@Windows@@@34@@Z`
- size: `208`
- prototype: `IMFMediaBuffer **__fastcall(IMFMediaBuffer **ppBuffer, struct IInspectable **)`
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180001ddc`
- `0x180022c1c`
- `0x1800230d0`
- `0x1800231cc`

## callees

- `0x180001938`
- `0x1800019c0`
- `0x1800019ec`
- `0x180005cd0`
- `0x180021e2c`
- `0x180052010`

## import_xrefs

- `MFPlat!MFCreateDXGISurfaceBuffer` at `0x180001a66`
- `MFPlat!MFCreateDXGISurfaceBuffer` at `0x180001a66`

## pseudocode

```c
IMFMediaBuffer **__fastcall MediaFrameHelpers::GetBufferFromSurface(
        IMFMediaBuffer **ppBuffer,
        struct IInspectable **a2)
{
  const struct _GUID *v4; // rdx
  unsigned int DXGIInterfaceFromDirect3D11Object; // eax
  int v6; // edx
  unsigned int v7; // eax
  int v8; // edx
  IUnknown *v9; // rcx
  void *v10; // rcx
  void *v12; // [rsp+68h] [rbp+28h] BYREF
  IUnknown *punkSurface; // [rsp+70h] [rbp+30h] BYREF

  v12 = 0;
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v12);
  DXGIInterfaceFromDirect3D11Object = GetDXGIInterfaceFromDirect3D11Object(*a2, v4, &v12);
  MF::ThrowIfFailed((MF *)DXGIInterfaceFromDirect3D11Object, v6);
  MF::As<ID3D11Texture2D,IDXGISurface>(&punkSurface, &v12);
  *ppBuffer = 0;
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(ppBuffer);
  v7 = MFCreateDXGISurfaceBuffer(&GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c, punkSurface, 0, 0, ppBuffer);
  MF::ThrowIfFailed((MF *)v7, v8);
  v9 = punkSurface;
  if ( punkSurface )
  {
    punkSurface = 0;
    ((void (__fastcall *)(IUnknown *))v9->lpVtbl->Release)(v9);
  }
  v10 = v12;
  if ( v12 )
  {
    v12 = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v10 + 16LL))(v10);
  }
  return ppBuffer;
}

```

## disassembly

```asm
0x1800019ec  mov     [rsp-18h+arg_0], rcx
0x1800019f1  push    rbp
0x1800019f2  push    rbx
0x1800019f3  push    rdi
0x1800019f4  mov     rbp, rsp
0x1800019f7  sub     rsp, 40h
0x1800019fb  mov     rbx, rdx
0x1800019fe  mov     rdi, rcx
0x180001a01  mov     [rbp+var_10], 0
0x180001a08  mov     [rbp+arg_8], 0
0x180001a10  lea     rcx, [rbp+arg_8]
0x180001a14  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180001a19  lea     r8, [rbp+arg_8]; void **
0x180001a1d  mov     rcx, [rbx]; struct IInspectable *
0x180001a20  call    ?GetDXGIInterfaceFromDirect3D11Object@@YAJPEAUIInspectable@@AEBU_GUID@@PEAPEAX@Z; GetDXGIInterfaceFromDirect3D11Object(IInspectable *,_GUID const &,void * *)
0x180001a25  mov     ecx, eax; this
0x180001a27  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x180001a2c  lea     rdx, [rbp+arg_8]
0x180001a30  lea     rcx, [rbp+punkSurface]
0x180001a34  call    ??$As@UID3D11Texture2D@@UIDXGISurface@@@MF@@YA?AV?$ComPtr@UID3D11Texture2D@@@WRL@Microsoft@@AEBV?$ComPtr@UIDXGISurface@@@23@@Z; MF::As<ID3D11Texture2D,IDXGISurface>(Microsoft::WRL::ComPtr<IDXGISurface> const &)
0x180001a39  nop
0x180001a3a  mov     qword ptr [rdi], 0
0x180001a41  mov     [rbp+var_10], 1
0x180001a48  mov     rcx, rdi
0x180001a4b  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180001a50  mov     [rsp+40h+ppBuffer], rdi; ppBuffer
0x180001a55  xor     r9d, r9d; fBottomUpWhenLinear
0x180001a58  xor     r8d, r8d; uSubresourceIndex
0x180001a5b  mov     rdx, [rbp+punkSurface]; punkSurface
0x180001a5f  lea     rcx, _GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c; riid
0x180001a66  call    cs:__imp_MFCreateDXGISurfaceBuffer
0x180001a6c  mov     ecx, eax; this
0x180001a6e  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x180001a73  nop
0x180001a74  mov     rcx, [rbp+punkSurface]
0x180001a78  test    rcx, rcx
0x180001a7b  jz      short loc_180001A92
0x180001a7d  mov     [rbp+punkSurface], 0
0x180001a85  mov     rax, [rcx]
0x180001a88  mov     rax, [rax+10h]
0x180001a8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a91  nop
0x180001a92  mov     rcx, [rbp+arg_8]
0x180001a96  test    rcx, rcx
0x180001a99  jz      short loc_180001AB0
0x180001a9b  mov     [rbp+arg_8], 0
0x180001aa3  mov     rax, [rcx]
0x180001aa6  mov     rax, [rax+10h]
0x180001aaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001aaf  nop
0x180001ab0  mov     rax, rdi
0x180001ab3  add     rsp, 40h
0x180001ab7  pop     rdi
0x180001ab8  pop     rbx
0x180001ab9  pop     rbp
0x180001aba  retn
```
