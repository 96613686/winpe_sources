# ColorCorrectImageWithWIC(IWICImagingFactory *,IWICBitmapFrameDecode *,IWICBitmapSource *,IWICBitmapSource * *)

- ea: `0x18000d87c`
- end: `0x18000d985`
- name: `?ColorCorrectImageWithWIC@@YAJPEAUIWICImagingFactory@@PEAUIWICBitmapFrameDecode@@PEAUIWICBitmapSource@@PEAPEAU3@@Z`
- size: `265`
- prototype: `__int64 __fastcall(struct IWICImagingFactory *, struct IWICBitmapFrameDecode *, struct IWICColorTransform *, struct IWICBitmapSource **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000ae9c`

## callees

- `0x18000d848`
- `0x18000d87c`
- `0x18000d98c`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000d8e2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000d8e2`

## pseudocode

```c
__int64 __fastcall ColorCorrectImageWithWIC(
        struct IWICImagingFactory *a1,
        struct IWICBitmapFrameDecode *a2,
        struct IWICColorTransform *a3,
        struct IWICBitmapSource **a4)
{
  LPVOID *ppv; // rax
  HRESULT Instance; // edi
  struct IWICColorTransform *v10; // rcx
  __int64 (__fastcall **lpVtbl)(struct IWICColorTransform *, GUID *, struct IWICBitmapSource **); // rax
  HRESULT v12; // eax
  struct IWICColorTransform *v13; // rcx
  struct IWICImagingFactory *v14; // rcx
  struct IWICColorTransform *v16; // [rsp+50h] [rbp+8h] BYREF
  struct IWICImagingFactory *v17; // [rsp+68h] [rbp+20h] BYREF

  *a4 = 0;
  v17 = a1;
  if ( a1 && (((void (__fastcall *)(struct IWICImagingFactory *))a1->lpVtbl->AddRef)(a1), v17)
    || (ppv = (LPVOID *)IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IWICImagingFactory>>(&v17),
        Instance = CoCreateInstance(&CLSID_WICImagingFactory2, 0, 1u, &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70, ppv),
        Instance >= 0) )
  {
    v16 = 0;
    if ( (int)_GetsRGBTransformer(a2, (struct IWICBitmapSource *)a3, a1, &v16) < 0 )
    {
      lpVtbl = (__int64 (__fastcall **)(struct IWICColorTransform *, GUID *, struct IWICBitmapSource **))a3->lpVtbl;
      v10 = a3;
    }
    else
    {
      v10 = v16;
      lpVtbl = (__int64 (__fastcall **)(struct IWICColorTransform *, GUID *, struct IWICBitmapSource **))v16->lpVtbl;
    }
    v12 = (*lpVtbl)(v10, &GUID_00000120_a8f2_4877_ba0a_fd2b6645fb94, a4);
    v13 = v16;
    Instance = v12;
    if ( v16 )
    {
      v16 = 0;
      ((void (__fastcall *)(struct IWICColorTransform *))v13->lpVtbl->Release)(v13);
    }
  }
  v14 = v17;
  if ( v17 )
  {
    v17 = 0;
    ((void (__fastcall *)(struct IWICImagingFactory *))v14->lpVtbl->Release)(v14);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18000d87c  mov     [rsp+arg_8], rbx
0x18000d881  mov     [rsp+arg_10], rbp
0x18000d886  push    rsi
0x18000d887  push    rdi
0x18000d888  push    r14
0x18000d88a  sub     rsp, 30h
0x18000d88e  mov     qword ptr [r9], 0
0x18000d895  mov     r14, r9
0x18000d898  mov     [rsp+48h+arg_18], rcx
0x18000d89d  mov     rsi, r8
0x18000d8a0  mov     rbp, rdx
0x18000d8a3  mov     rbx, rcx
0x18000d8a6  test    rcx, rcx
0x18000d8a9  jz      short loc_18000D8BF
0x18000d8ab  mov     rax, [rcx]
0x18000d8ae  mov     rax, [rax+8]
0x18000d8b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8b7  cmp     [rsp+48h+arg_18], 0
0x18000d8bd  jnz     short loc_18000D8EE
0x18000d8bf  lea     rcx, [rsp+48h+arg_18]
0x18000d8c4  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIWICImagingFactory@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIWICImagingFactory@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IWICImagingFactory>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IWICImagingFactory>>)
0x18000d8c9  xor     edx, edx; pUnkOuter
0x18000d8cb  mov     [rsp+48h+ppv], rax; ppv
0x18000d8d0  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x18000d8d7  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x18000d8de  lea     r8d, [rdx+1]; dwClsContext
0x18000d8e2  call    cs:__imp_CoCreateInstance
0x18000d8e8  mov     edi, eax
0x18000d8ea  test    eax, eax
0x18000d8ec  js      short loc_18000D951
0x18000d8ee  lea     r9, [rsp+48h+arg_0]; struct IWICColorTransform **
0x18000d8f3  mov     [rsp+48h+arg_0], 0
0x18000d8fc  mov     r8, rbx; struct IWICImagingFactory *
0x18000d8ff  mov     rdx, rsi; struct IWICBitmapSource *
0x18000d902  mov     rcx, rbp; struct IWICBitmapFrameDecode *
0x18000d905  call    ?_GetsRGBTransformer@@YAJPEAUIWICBitmapFrameDecode@@PEAUIWICBitmapSource@@PEAUIWICImagingFactory@@PEAPEAUIWICColorTransform@@@Z; _GetsRGBTransformer(IWICBitmapFrameDecode *,IWICBitmapSource *,IWICImagingFactory *,IWICColorTransform * *)
0x18000d90a  lea     rdx, _GUID_00000120_a8f2_4877_ba0a_fd2b6645fb94
0x18000d911  mov     r8, r14
0x18000d914  test    eax, eax
0x18000d916  js      short loc_18000D922
0x18000d918  mov     rcx, [rsp+48h+arg_0]
0x18000d91d  mov     rax, [rcx]
0x18000d920  jmp     short loc_18000D928
0x18000d922  mov     rax, [rsi]
0x18000d925  mov     rcx, rsi
0x18000d928  mov     rax, [rax]
0x18000d92b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d930  mov     rcx, [rsp+48h+arg_0]
0x18000d935  mov     edi, eax
0x18000d937  test    rcx, rcx
0x18000d93a  jz      short loc_18000D951
0x18000d93c  mov     [rsp+48h+arg_0], 0
0x18000d945  mov     rax, [rcx]
0x18000d948  mov     rax, [rax+10h]
0x18000d94c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d951  mov     rcx, [rsp+48h+arg_18]
0x18000d956  test    rcx, rcx
0x18000d959  jz      short loc_18000D970
0x18000d95b  mov     [rsp+48h+arg_18], 0
0x18000d964  mov     rax, [rcx]
0x18000d967  mov     rax, [rax+10h]
0x18000d96b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d970  mov     rbx, [rsp+48h+arg_8]
0x18000d975  mov     eax, edi
0x18000d977  mov     rbp, [rsp+48h+arg_10]
0x18000d97c  add     rsp, 30h
0x18000d980  pop     r14
0x18000d982  pop     rdi
0x18000d983  pop     rsi
0x18000d984  retn
```
