# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x1800149a0`
- end: `0x180014a3c`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `156`
- prototype: `__int64 __fastcall(Microsoft::WRL::FtmBase *__hidden this)`
- caller_count: `69`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180014878`
- `0x180020744`
- `0x180028a5c`
- `0x18004a870`
- `0x18004c504`
- `0x18004cc14`
- `0x18004d164`
- `0x18004d8c4`
- `0x180058ff0`
- `0x18005a30c`
- `0x18005a770`
- `0x1800609dc`
- `0x180072f8c`
- `0x1800730cc`
- `0x18007320c`
- `0x180073bf4`
- `0x180073ca4`
- `0x180079ff4`
- `0x18007a018`
- `0x18007a160`
- `0x18007b23c`
- `0x18007ba84`
- `0x18007bb48`
- `0x18007bc0c`
- `0x18007bcd0`
- `0x18007ff14`
- `0x18007ffe8`
- `0x1800800bc`
- `0x180080184`
- `0x1800802b8`
- `0x1800803ec`
- `0x18008078c`
- `0x180081490`
- `0x180081554`
- `0x180081618`
- `0x180081afc`
- `0x180081f00`
- `0x180081fcc`
- `0x180082090`
- `0x180096dbc`
- `0x180096ed4`
- `0x180096f74`
- `0x180097014`
- `0x1800970b4`
- `0x180097154`
- `0x18009721c`
- `0x18009989c`
- `0x180099ba4`
- `0x18009b23c`
- `0x18009c304`

## callees

- `0x18000fa5c`
- `0x1800149a0`
- `0x1800dc010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800149dc`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800149dc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
Microsoft::WRL::FtmBase *__fastcall Microsoft::WRL::FtmBase::FtmBase(Microsoft::WRL::FtmBase *this)
{
  char *v2; // r14
  LPUNKNOWN v3; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rdi
  LPUNKNOWN v5; // rcx
  LPUNKNOWN ppunkMarshal; // [rsp+50h] [rbp+8h] BYREF

  *(_QWORD *)this = &Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const CopyFilesAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const CopyFilesAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'};
  v2 = (char *)this + 24;
  *((_QWORD *)this + 3) = 0;
  ppunkMarshal = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppunkMarshal);
  if ( CoCreateFreeThreadedMarshaler(0, &ppunkMarshal) >= 0 )
  {
    v3 = ppunkMarshal;
    QueryInterface = ppunkMarshal->lpVtbl->QueryInterface;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v2);
    ((void (__fastcall *)(LPUNKNOWN, GUID *, char *))QueryInterface)(v3, &GUID_00000003_0000_0000_c000_000000000046, v2);
  }
  v5 = ppunkMarshal;
  if ( ppunkMarshal )
  {
    ppunkMarshal = 0;
    ((void (__fastcall *)(LPUNKNOWN))v5->lpVtbl->Release)(v5);
  }
  return this;
}

```

## disassembly

```asm
0x1800149a0  push    rbx
0x1800149a2  push    rsi
0x1800149a3  push    rdi
0x1800149a4  push    r14
0x1800149a6  sub     rsp, 28h
0x1800149aa  mov     rsi, rcx
0x1800149ad  lea     rax, ??_7?$AsyncBaseFTM@UIAsyncActionCompletedHandler@Foundation@Windows@@$00U?$AsyncCausalityOptions@$1?CopyFilesAsyncActionName@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@V?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?CopyFilesAsyncActionName@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@@Details@23@VFtmBase@23@@234@@Details@WRL@Microsoft@@@; const Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const CopyFilesAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const CopyFilesAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'}
0x1800149b4  mov     [rcx], rax
0x1800149b7  lea     r14, [rcx+18h]
0x1800149bb  mov     qword ptr [r14], 0
0x1800149c2  mov     [rsp+48h+ppunkMarshal], 0
0x1800149cb  lea     rcx, [rsp+48h+ppunkMarshal]
0x1800149d0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800149d5  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x1800149da  xor     ecx, ecx; punkOuter
0x1800149dc  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x1800149e2  test    eax, eax
0x1800149e4  js      short loc_180014A0F
0x1800149e6  mov     rbx, [rsp+48h+ppunkMarshal]
0x1800149eb  mov     rax, [rbx]
0x1800149ee  mov     rdi, [rax]
0x1800149f1  mov     rcx, r14
0x1800149f4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800149f9  mov     r8, r14
0x1800149fc  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x180014a03  mov     rcx, rbx
0x180014a06  mov     rax, rdi
0x180014a09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a0e  nop
0x180014a0f  mov     rcx, [rsp+48h+ppunkMarshal]
0x180014a14  test    rcx, rcx
0x180014a17  jz      short loc_180014A2F
0x180014a19  mov     [rsp+48h+ppunkMarshal], 0
0x180014a22  mov     rax, [rcx]
0x180014a25  mov     rax, [rax+10h]
0x180014a29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a2e  nop
0x180014a2f  mov     rax, rsi
0x180014a32  add     rsp, 28h
0x180014a36  pop     r14
0x180014a38  pop     rdi
0x180014a39  pop     rsi
0x180014a3a  pop     rbx
0x180014a3b  retn
```
