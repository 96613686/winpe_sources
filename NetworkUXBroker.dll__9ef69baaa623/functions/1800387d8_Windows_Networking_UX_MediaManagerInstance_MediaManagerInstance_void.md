# Windows::Networking::UX::MediaManagerInstance::~MediaManagerInstance(void)

- ea: `0x1800387d8`
- end: `0x180038865`
- name: `??1MediaManagerInstance@UX@Networking@Windows@@UEAA@XZ`
- size: `141`
- prototype: `void __fastcall(Windows::Networking::UX::MediaManagerInstance *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180029e40`

## callees

- `0x18000955c`
- `0x180011a74`
- `0x18002d614`
- `0x1800387d8`
- `0x180039460`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003884d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003884d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180038832`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180038832`

## pseudocode

```c
void __fastcall Windows::Networking::UX::MediaManagerInstance::~MediaManagerInstance(
        Windows::Networking::UX::MediaManagerInstance *this)
{
  Windows::Networking::UX::UXCategoryChangedSink *v2; // rcx

  *(_QWORD *)this = &Windows::Networking::UX::MediaManagerInstance::`vftable';
  *((_QWORD *)this + 1) = &Windows::Networking::UX::MediaManagerInstance::`vftable'{for `Windows::Networking::UX::Internal::IUXCategoryChangedHandler'};
  *((_QWORD *)this + 2) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Networking::UX::Internal::IUXCategoryChangedHandler>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource>'};
  v2 = (Windows::Networking::UX::UXCategoryChangedSink *)*((_QWORD *)this + 14);
  if ( v2 )
    Windows::Networking::UX::UXCategoryChangedSink::Stop(v2);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 120);
  Microsoft::WRL::ComPtr<Windows::Networking::UX::UXCategoryChangedSink>::InternalRelease((char *)this + 112);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 104);
  WindowsDeleteString(*((HSTRING *)this + 12));
  *((_QWORD *)this + 12) = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 88);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 1);
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IMap<HSTRING__ *,unsigned char>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,unsigned char> *>>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IMap<HSTRING__ *,unsigned char>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,unsigned char> *>>(this);
}

```

## disassembly

```asm
0x1800387d8  mov     [rsp+arg_0], rbx
0x1800387dd  push    rdi
0x1800387de  sub     rsp, 20h
0x1800387e2  mov     rbx, rcx
0x1800387e5  lea     rax, ??_7MediaManagerInstance@UX@Networking@Windows@@6B@; const Windows::Networking::UX::MediaManagerInstance::`vftable'
0x1800387ec  mov     [rcx], rax
0x1800387ef  lea     rax, ??_7MediaManagerInstance@UX@Networking@Windows@@6BIUXCategoryChangedHandler@Internal@123@@; const Windows::Networking::UX::MediaManagerInstance::`vftable'{for `Windows::Networking::UX::Internal::IUXCategoryChangedHandler'}
0x1800387f6  mov     [rcx+8], rax
0x1800387fa  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIUXCategoryChangedHandler@Internal@UX@Networking@Windows@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Networking::UX::Internal::IUXCategoryChangedHandler>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource>'}
0x180038801  mov     [rcx+10h], rax
0x180038805  mov     rcx, [rcx+70h]; this
0x180038809  test    rcx, rcx
0x18003880c  jz      short loc_180038813
0x18003880e  call    ?Stop@UXCategoryChangedSink@UX@Networking@Windows@@QEAAXXZ; Windows::Networking::UX::UXCategoryChangedSink::Stop(void)
0x180038813  lea     rcx, [rbx+78h]
0x180038817  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003881c  lea     rcx, [rbx+70h]
0x180038820  call    ?InternalRelease@?$ComPtr@VUXCategoryChangedSink@UX@Networking@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Networking::UX::UXCategoryChangedSink>::InternalRelease(void)
0x180038825  lea     rcx, [rbx+68h]
0x180038829  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003882e  mov     rcx, [rbx+60h]; string
0x180038832  call    cs:__imp_WindowsDeleteString
0x180038838  mov     qword ptr [rbx+60h], 0
0x180038840  lea     rcx, [rbx+58h]
0x180038844  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180038849  lea     rcx, [rbx+28h]; lpCriticalSection
0x18003884d  call    cs:__imp_DeleteCriticalSection
0x180038853  mov     rcx, rbx
0x180038856  mov     rbx, [rsp+28h+arg_0]
0x18003885b  add     rsp, 20h
0x18003885f  pop     rdi
0x180038860  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IMap@PEAUHSTRING__@@E@Collections@Foundation@Windows@@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@E@Collections@Foundation@Windows@@@567@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IMap<HSTRING__ *,uchar>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,uchar> *>>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IMap<HSTRING__ *,uchar>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,uchar> *>>(void)
```
