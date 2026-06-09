# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x180008318`
- end: `0x18000839e`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `134`
- prototype: `__int64 __fastcall(Microsoft::WRL::FtmBase *__hidden this)`
- caller_count: `17`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800083a4`
- `0x180008440`
- `0x18000b054`
- `0x18000c938`
- `0x18000cb44`
- `0x18000cc84`
- `0x18002978c`
- `0x18002ade8`
- `0x18002ce84`
- `0x1800a3638`
- `0x1800a4db8`
- `0x1800a4e30`
- `0x1800a4fa0`
- `0x1800a8d24`
- `0x1800abc58`
- `0x1800acea0`
- `0x180131418`

## callees

- `0x180005660`
- `0x180008318`
- `0x180142010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180008354`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180008354`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
Microsoft::WRL::FtmBase *__fastcall Microsoft::WRL::FtmBase::FtmBase(Microsoft::WRL::FtmBase *this)
{
  char *v2; // r14
  LPUNKNOWN v3; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rdi
  LPUNKNOWN ppunkMarshal; // [rsp+50h] [rbp+8h] BYREF

  *(_QWORD *)this = &Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Graphics::Imaging::Internal::HighDynamicRangeResult *,double>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Graphics::Imaging::Internal::HighDynamicRangeResult *,double>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'};
  v2 = (char *)this + 24;
  *((_QWORD *)this + 3) = 0;
  ppunkMarshal = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppunkMarshal);
  if ( CoCreateFreeThreadedMarshaler(0, &ppunkMarshal) >= 0 )
  {
    v3 = ppunkMarshal;
    QueryInterface = ppunkMarshal->lpVtbl->QueryInterface;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v2);
    ((void (__fastcall *)(LPUNKNOWN, GUID *, char *))QueryInterface)(v3, &GUID_00000003_0000_0000_c000_000000000046, v2);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppunkMarshal);
  return this;
}

```

## disassembly

```asm
0x180008318  push    rbx
0x18000831a  push    rsi
0x18000831b  push    rdi
0x18000831c  push    r14
0x18000831e  sub     rsp, 28h
0x180008322  mov     rsi, rcx
0x180008325  lea     rax, ??_7?$AsyncBaseFTM@U?$IAsyncOperationWithProgressCompletedHandler@PEAVHighDynamicRangeResult@Internal@Imaging@Graphics@Windows@@N@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@V?$AsyncBase@U?$IAsyncOperationWithProgressCompletedHandler@PEAVHighDynamicRangeResult@Internal@Imaging@Graphics@Windows@@N@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@@Details@23@VFtmBase@23@@234@@Details@WRL@Microsoft@@@; const Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Graphics::Imaging::Internal::HighDynamicRangeResult *,double>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Graphics::Imaging::Internal::HighDynamicRangeResult *,double>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'}
0x18000832c  mov     [rcx], rax
0x18000832f  lea     r14, [rcx+18h]
0x180008333  mov     qword ptr [r14], 0
0x18000833a  mov     [rsp+48h+ppunkMarshal], 0
0x180008343  lea     rcx, [rsp+48h+ppunkMarshal]
0x180008348  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000834d  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x180008352  xor     ecx, ecx; punkOuter
0x180008354  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x18000835a  test    eax, eax
0x18000835c  js      short loc_180008387
0x18000835e  mov     rbx, [rsp+48h+ppunkMarshal]
0x180008363  mov     rax, [rbx]
0x180008366  mov     rdi, [rax]
0x180008369  mov     rcx, r14
0x18000836c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180008371  mov     r8, r14
0x180008374  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x18000837b  mov     rcx, rbx
0x18000837e  mov     rax, rdi
0x180008381  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008386  nop
0x180008387  lea     rcx, [rsp+48h+ppunkMarshal]
0x18000838c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180008391  mov     rax, rsi
0x180008394  add     rsp, 28h
0x180008398  pop     r14
0x18000839a  pop     rdi
0x18000839b  pop     rsi
0x18000839c  pop     rbx
0x18000839d  retn
```
