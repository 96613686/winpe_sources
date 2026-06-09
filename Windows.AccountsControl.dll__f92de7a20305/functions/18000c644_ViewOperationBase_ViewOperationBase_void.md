# ViewOperationBase::~ViewOperationBase(void)

- ea: `0x18000c644`
- end: `0x18000c765`
- name: `??1ViewOperationBase@@UEAA@XZ`
- size: `289`
- prototype: `void __fastcall(ViewOperationBase *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000bfb0`
- `0x18000d560`
- `0x180049054`

## callees

- `0x18000be1c`
- `0x18000c618`
- `0x18000c644`
- `0x180011ffc`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000c751`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000c751`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c6ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c706`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c71b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c72d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c73f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c6ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c706`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c71b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c72d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c73f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ViewOperationBase::~ViewOperationBase(ViewOperationBase *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx

  *(_QWORD *)this = &ViewOperationBase::`vftable'{for `Windows::Internal::UI::ApplicationSettings::IViewOperation'};
  *((_QWORD *)this + 1) = &CActivatedEventArgsBase::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 568);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 560);
  v2 = *((_QWORD *)this + 69);
  if ( v2 )
  {
    *((_QWORD *)this + 69) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  v3 = *((_QWORD *)this + 68);
  if ( v3 )
  {
    *((_QWORD *)this + 68) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  WindowsDeleteString(*((HSTRING *)this + 67));
  *((_QWORD *)this + 67) = 0;
  SyncPartnershipApiTelemetry::ViewOperationActivity::~ViewOperationActivity((ViewOperationBase *)((char *)this + 184));
  Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::UI::ApplicationSettings::IViewOperation *,int>,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::UI::ApplicationSettings::IViewOperation *,int>,Microsoft::WRL::InvokeModeOptions<-2>>((char *)this + 160);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 136);
  WindowsDeleteString(*((HSTRING *)this + 16));
  *((_QWORD *)this + 16) = 0;
  WindowsDeleteString(*((HSTRING *)this + 15));
  *((_QWORD *)this + 15) = 0;
  WindowsDeleteString(*((HSTRING *)this + 13));
  *((_QWORD *)this + 13) = 0;
  WindowsDeleteString(*((HSTRING *)this + 12));
  *((_QWORD *)this + 12) = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 32);
}

```

## disassembly

```asm
0x18000c644  push    rbx
0x18000c646  sub     rsp, 20h
0x18000c64a  mov     rbx, rcx
0x18000c64d  lea     rax, ??_7ViewOperationBase@@6BIViewOperation@ApplicationSettings@UI@Internal@Windows@@@; const ViewOperationBase::`vftable'{for `Windows::Internal::UI::ApplicationSettings::IViewOperation'}
0x18000c654  mov     [rcx], rax
0x18000c657  lea     rax, ??_7CActivatedEventArgsBase@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const CActivatedEventArgsBase::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000c65e  mov     [rcx+8], rax
0x18000c662  add     rcx, 238h
0x18000c669  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000c66e  lea     rcx, [rbx+230h]
0x18000c675  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000c67a  nop
0x18000c67b  mov     rcx, [rbx+228h]
0x18000c682  test    rcx, rcx
0x18000c685  jz      short loc_18000C69F
0x18000c687  mov     qword ptr [rbx+228h], 0
0x18000c692  mov     rax, [rcx]
0x18000c695  mov     rax, [rax+10h]
0x18000c699  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c69e  nop
0x18000c69f  mov     rcx, [rbx+220h]
0x18000c6a6  test    rcx, rcx
0x18000c6a9  jz      short loc_18000C6C3
0x18000c6ab  mov     qword ptr [rbx+220h], 0
0x18000c6b6  mov     rax, [rcx]
0x18000c6b9  mov     rax, [rax+10h]
0x18000c6bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c6c2  nop
0x18000c6c3  mov     rcx, [rbx+218h]; string
0x18000c6ca  call    cs:__imp_WindowsDeleteString
0x18000c6d0  mov     qword ptr [rbx+218h], 0
0x18000c6db  lea     rcx, [rbx+0B8h]; this
0x18000c6e2  call    ??1ViewOperationActivity@SyncPartnershipApiTelemetry@@QEAA@XZ; SyncPartnershipApiTelemetry::ViewOperationActivity::~ViewOperationActivity(void)
0x18000c6e7  lea     rcx, [rbx+0A0h]
0x18000c6ee  call    ??1?$EventSource@U?$ITypedEventHandler@PEAUIViewOperation@ApplicationSettings@UI@Internal@Windows@@H@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::UI::ApplicationSettings::IViewOperation *,int>,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::UI::ApplicationSettings::IViewOperation *,int>,Microsoft::WRL::InvokeModeOptions<-2>>(void)
0x18000c6f3  lea     rcx, [rbx+88h]
0x18000c6fa  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000c6ff  mov     rcx, [rbx+80h]; string
0x18000c706  call    cs:__imp_WindowsDeleteString
0x18000c70c  mov     qword ptr [rbx+80h], 0
0x18000c717  mov     rcx, [rbx+78h]; string
0x18000c71b  call    cs:__imp_WindowsDeleteString
0x18000c721  mov     qword ptr [rbx+78h], 0
0x18000c729  mov     rcx, [rbx+68h]; string
0x18000c72d  call    cs:__imp_WindowsDeleteString
0x18000c733  mov     qword ptr [rbx+68h], 0
0x18000c73b  mov     rcx, [rbx+60h]; string
0x18000c73f  call    cs:__imp_WindowsDeleteString
0x18000c745  mov     qword ptr [rbx+60h], 0
0x18000c74d  lea     rcx, [rbx+30h]; lpCriticalSection
0x18000c751  call    cs:__imp_DeleteCriticalSection
0x18000c757  lea     rcx, [rbx+20h]
0x18000c75b  add     rsp, 20h
0x18000c75f  pop     rbx
0x18000c760  jmp     ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
```
