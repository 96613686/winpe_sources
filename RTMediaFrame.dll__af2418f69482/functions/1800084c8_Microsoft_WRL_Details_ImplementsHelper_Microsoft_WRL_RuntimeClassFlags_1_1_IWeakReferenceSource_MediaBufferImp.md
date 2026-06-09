# Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,MediaBufferImpl>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,MediaBufferImpl>(void)

- ea: `0x1800084c8`
- end: `0x1800085cf`
- name: `??0?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@VMediaBufferImpl@@@Details@WRL@Microsoft@@QEAA@XZ`
- size: `263`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009e10`

## callees

- `0x1800084c8`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800085bd`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800085bd`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800084fa`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800084fa`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,MediaBufferImpl>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,MediaBufferImpl>(
        __int64 a1)
{
  __int64 *v2; // rsi
  LPUNKNOWN v3; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbp
  __int64 v5; // rcx
  LPUNKNOWN v6; // rcx
  LPUNKNOWN ppunkMarshal; // [rsp+50h] [rbp+8h] BYREF

  *(_QWORD *)(a1 + 40) = &Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geopoint *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geopoint *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'};
  v2 = (__int64 *)(a1 + 64);
  *(_QWORD *)(a1 + 64) = 0;
  ppunkMarshal = 0;
  if ( CoCreateFreeThreadedMarshaler(0, &ppunkMarshal) >= 0 )
  {
    v3 = ppunkMarshal;
    QueryInterface = ppunkMarshal->lpVtbl->QueryInterface;
    v5 = *v2;
    if ( *v2 )
    {
      *v2 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
    ((void (__fastcall *)(LPUNKNOWN, GUID *, __int64 *))QueryInterface)(
      v3,
      &GUID_00000003_0000_0000_c000_000000000046,
      v2);
  }
  v6 = ppunkMarshal;
  if ( ppunkMarshal )
  {
    ppunkMarshal = 0;
    ((void (__fastcall *)(LPUNKNOWN))v6->lpVtbl->Release)(v6);
  }
  *(_QWORD *)(a1 + 8) = &MediaBufferImpl::`vftable';
  *(_QWORD *)(a1 + 16) = &MediaBufferImpl::`vftable'{for `Windows::Foundation::IMemoryBuffer'};
  *(_QWORD *)(a1 + 24) = &MediaBufferImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IClosableBuffer>,Microsoft::WRL::CloakedIid<IClosableByteAccess>,Microsoft::WRL::FtmBase>'};
  *(_QWORD *)(a1 + 32) = &MediaBufferImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IClosableByteAccess>'};
  *(_QWORD *)(a1 + 40) = &Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geopoint *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geopoint *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'};
  *(_QWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 88) = 0;
  *(_DWORD *)(a1 + 96) = 0;
  *(_WORD *)(a1 + 100) = 0;
  *(_BYTE *)(a1 + 102) = 0;
  InitializeSRWLock((PSRWLOCK)(a1 + 104));
  return a1;
}

```

## disassembly

```asm
0x1800084c8  push    rbx
0x1800084ca  push    rbp
0x1800084cb  push    rsi
0x1800084cc  push    rdi
0x1800084cd  sub     rsp, 28h
0x1800084d1  mov     rdi, rcx
0x1800084d4  lea     rax, ??_7?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@PEAVGeopoint@Geolocation@Devices@Windows@@@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@V?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVGeopoint@Geolocation@Devices@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@@Details@23@VFtmBase@23@@234@@Details@WRL@Microsoft@@@; const Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geopoint *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geopoint *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'}
0x1800084db  mov     [rcx+28h], rax
0x1800084df  lea     rsi, [rcx+40h]
0x1800084e3  mov     qword ptr [rsi], 0
0x1800084ea  mov     [rsp+48h+ppunkMarshal], 0
0x1800084f3  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x1800084f8  xor     ecx, ecx; punkOuter
0x1800084fa  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x180008500  test    eax, eax
0x180008502  js      short loc_180008541
0x180008504  mov     rbx, [rsp+48h+ppunkMarshal]
0x180008509  mov     rax, [rbx]
0x18000850c  mov     rbp, [rax]
0x18000850f  mov     rcx, [rsi]
0x180008512  test    rcx, rcx
0x180008515  jz      short loc_18000852B
0x180008517  mov     qword ptr [rsi], 0
0x18000851e  mov     rdx, [rcx]
0x180008521  mov     rax, [rdx+10h]
0x180008525  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000852a  nop
0x18000852b  mov     r8, rsi
0x18000852e  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x180008535  mov     rcx, rbx
0x180008538  mov     rax, rbp
0x18000853b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008540  nop
0x180008541  mov     rcx, [rsp+48h+ppunkMarshal]
0x180008546  test    rcx, rcx
0x180008549  jz      short loc_180008561
0x18000854b  mov     [rsp+48h+ppunkMarshal], 0
0x180008554  mov     rax, [rcx]
0x180008557  mov     rax, [rax+10h]
0x18000855b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008560  nop
0x180008561  lea     rax, ??_7MediaBufferImpl@@6B@; const MediaBufferImpl::`vftable'
0x180008568  mov     [rdi+8], rax
0x18000856c  lea     rax, ??_7MediaBufferImpl@@6BIMemoryBuffer@Foundation@Windows@@@; const MediaBufferImpl::`vftable'{for `Windows::Foundation::IMemoryBuffer'}
0x180008573  mov     [rdi+10h], rax
0x180008577  lea     rax, ??_7MediaBufferImpl@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$CloakedIid@UIClosableBuffer@Streams@Storage@Windows@@@23@U?$CloakedIid@UIClosableByteAccess@@@23@VFtmBase@23@@Details@WRL@Microsoft@@@; const MediaBufferImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IClosableBuffer>,Microsoft::WRL::CloakedIid<IClosableByteAccess>,Microsoft::WRL::FtmBase>'}
0x18000857e  mov     [rdi+18h], rax
0x180008582  lea     rax, ??_7MediaBufferImpl@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIClosableByteAccess@@@Details@WRL@Microsoft@@@; const MediaBufferImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IClosableByteAccess>'}
0x180008589  mov     [rdi+20h], rax
0x18000858d  lea     rax, ??_7?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@PEAVGeopoint@Geolocation@Devices@Windows@@@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@V?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVGeopoint@Geolocation@Devices@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@@Details@23@VFtmBase@23@@234@@Details@WRL@Microsoft@@@; const Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geopoint *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geopoint *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'}
0x180008594  mov     [rdi+28h], rax
0x180008598  mov     qword ptr [rdi+50h], 0
0x1800085a0  mov     qword ptr [rdi+58h], 0
0x1800085a8  mov     dword ptr [rdi+60h], 0
0x1800085af  mov     word ptr [rdi+64h], 0
0x1800085b5  mov     byte ptr [rdi+66h], 0
0x1800085b9  lea     rcx, [rdi+68h]; SRWLock
0x1800085bd  call    cs:__imp_InitializeSRWLock
0x1800085c3  mov     rax, rdi
0x1800085c6  add     rsp, 28h
0x1800085ca  pop     rdi
0x1800085cb  pop     rsi
0x1800085cc  pop     rbp
0x1800085cd  pop     rbx
0x1800085ce  retn
```
