# D2D1RenderTarget::StartRecording(tagRECT *,ushort const *)

- ea: `0x18003ca80`
- end: `0x18003cb2d`
- name: `?StartRecording@D2D1RenderTarget@@UEAAJPEAUtagRECT@@PEBG@Z`
- size: `173`
- prototype: `__int64 __fastcall(D2D1RenderTarget *__hidden this, struct tagRECT *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003b4f0`

## callees

- `0x18003c434`
- `0x18003ca80`

## import_xrefs

- `d2d1!__imp_D2D1CreateFactory` at `0x18003cae8`
- `d2d1!__imp_D2D1CreateFactory` at `0x18003cae8`
- `DWrite!DWriteCreateFactory` at `0x18003caff`
- `DWrite!DWriteCreateFactory` at `0x18003caff`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003cace`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003cace`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18003ca9c`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18003ca9c`

## pseudocode

```c
HRESULT __fastcall D2D1RenderTarget::StartRecording(
        D2D1RenderTarget *this,
        struct tagRECT *a2,
        const unsigned __int16 *a3)
{
  HRESULT result; // eax

  result = CoInitializeEx(0, 0);
  if ( (unsigned int)result <= 1 )
  {
    *((_QWORD *)this + 10) = a3;
    *((_QWORD *)this + 11) = a2;
    result = CoCreateInstance(&CLSID_WICImagingFactory2, 0, 1u, &IID_IWICImagingFactory, (LPVOID *)this + 5);
    if ( result >= 0 )
    {
      result = D2D1CreateFactory(
                 D2D1_FACTORY_TYPE_SINGLE_THREADED,
                 &GUID_06152247_6f50_465a_9245_118bfd3b6007,
                 0,
                 (void **)this + 6);
      if ( result >= 0 )
      {
        result = DWriteCreateFactory(0, &GUID_b859ee5a_d838_4b5b_a2e8_1adc7d93db48, (char *)this + 56);
        if ( result >= 0 )
          return D2D1RenderTarget::CreateRenderTarget(
                   (__int64)this,
                   (struct IUnknown **)this + 2,
                   (struct IUnknown **)this + 13,
                   (struct IUnknown **)this + 14);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18003ca80  mov     [rsp+arg_0], rbx
0x18003ca85  mov     [rsp+arg_8], rsi
0x18003ca8a  push    rdi
0x18003ca8b  sub     rsp, 30h
0x18003ca8f  mov     rsi, rdx
0x18003ca92  mov     rbx, rcx
0x18003ca95  xor     edx, edx; dwCoInit
0x18003ca97  xor     ecx, ecx; pvReserved
0x18003ca99  mov     rdi, r8
0x18003ca9c  call    cs:__imp_CoInitializeEx
0x18003caa2  mov     r8d, 1; dwClsContext
0x18003caa8  cmp     eax, r8d
0x18003caab  ja      short loc_18003CB1D
0x18003caad  lea     rax, [rbx+28h]
0x18003cab1  mov     [rbx+50h], rdi
0x18003cab5  lea     r9, IID_IWICImagingFactory; riid
0x18003cabc  mov     [rsp+38h+ppv], rax; ppv
0x18003cac1  xor     edx, edx; pUnkOuter
0x18003cac3  mov     [rbx+58h], rsi
0x18003cac7  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x18003cace  call    cs:__imp_CoCreateInstance
0x18003cad4  test    eax, eax
0x18003cad6  js      short loc_18003CB1D
0x18003cad8  lea     r9, [rbx+30h]; ppIFactory
0x18003cadc  xor     r8d, r8d; pFactoryOptions
0x18003cadf  lea     rdx, _GUID_06152247_6f50_465a_9245_118bfd3b6007; riid
0x18003cae6  xor     ecx, ecx; factoryType
0x18003cae8  call    cs:__imp_D2D1CreateFactory
0x18003caee  test    eax, eax
0x18003caf0  js      short loc_18003CB1D
0x18003caf2  lea     r8, [rbx+38h]
0x18003caf6  xor     ecx, ecx
0x18003caf8  lea     rdx, _GUID_b859ee5a_d838_4b5b_a2e8_1adc7d93db48
0x18003caff  call    cs:__imp_DWriteCreateFactory
0x18003cb05  test    eax, eax
0x18003cb07  js      short loc_18003CB1D
0x18003cb09  lea     r9, [rbx+70h]
0x18003cb0d  mov     rcx, rbx
0x18003cb10  lea     r8, [rbx+68h]
0x18003cb14  lea     rdx, [rbx+10h]
0x18003cb18  call    ?CreateRenderTarget@D2D1RenderTarget@@AEAAJAEAV?$CComPtr@UID2D1RenderTarget@@@ATL@@AEAV?$CComPtr@UID2D1Bitmap1@@@3@AEAV?$CComPtr@UID2D1DeviceContext@@@3@@Z; D2D1RenderTarget::CreateRenderTarget(ATL::CComPtr<ID2D1RenderTarget> &,ATL::CComPtr<ID2D1Bitmap1> &,ATL::CComPtr<ID2D1DeviceContext> &)
0x18003cb1d  mov     rbx, [rsp+38h+arg_0]
0x18003cb22  mov     rsi, [rsp+38h+arg_8]
0x18003cb27  add     rsp, 30h
0x18003cb2b  pop     rdi
0x18003cb2c  retn
```
