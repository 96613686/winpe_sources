# CSearchActivatedEventArgs::~CSearchActivatedEventArgs(void)

- ea: `0x18003adc8`
- end: `0x18003ae26`
- name: `??1CSearchActivatedEventArgs@@UEAA@XZ`
- size: `94`
- prototype: `void __fastcall(HSTRING *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003b020`

## callees

- `0x180007b3c`
- `0x18003aca8`
- `0x18003ae2c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ade4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003adfc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ade4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003adfc`

## pseudocode

```c
void __fastcall CSearchActivatedEventArgs::~CSearchActivatedEventArgs(HSTRING *this)
{
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(this + 37);
  WindowsDeleteString(this[36]);
  this[36] = 0;
  WindowsDeleteString(this[35]);
  this[35] = 0;
  CThreadRefTaker::~CThreadRefTaker((CThreadRefTaker *)(this + 33));
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,CActivatedEventArgsWithViewIdBase,Windows::ApplicationModel::Activation::ISearchActivatedEventArgsWithLinguisticDetails,Windows::ApplicationModel::Activation::ISearchActivatedEventArgs,Microsoft::WRL::CloakedIid<Windows::Foundation::Marshaling::Internal::IValueMarshalByPropertySet>>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,CActivatedEventArgsWithViewIdBase,Windows::ApplicationModel::Activation::ISearchActivatedEventArgsWithLinguisticDetails,Windows::ApplicationModel::Activation::ISearchActivatedEventArgs,Microsoft::WRL::CloakedIid<Windows::Foundation::Marshaling::Internal::IValueMarshalByPropertySet>>((CActivatedEventArgsWithViewIdBase *)this);
}

```

## disassembly

```asm
0x18003adc8  push    rbx
0x18003adca  sub     rsp, 20h
0x18003adce  mov     rbx, rcx
0x18003add1  add     rcx, 128h
0x18003add8  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18003addd  mov     rcx, [rbx+120h]; string
0x18003ade4  call    cs:__imp_WindowsDeleteString
0x18003adea  mov     qword ptr [rbx+120h], 0
0x18003adf5  mov     rcx, [rbx+118h]; string
0x18003adfc  call    cs:__imp_WindowsDeleteString
0x18003ae02  lea     rcx, [rbx+108h]; this
0x18003ae09  mov     qword ptr [rbx+118h], 0
0x18003ae14  call    ??1CThreadRefTaker@@UEAA@XZ; CThreadRefTaker::~CThreadRefTaker(void)
0x18003ae19  mov     rcx, rbx; this
0x18003ae1c  add     rsp, 20h
0x18003ae20  pop     rbx
0x18003ae21  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@VCActivatedEventArgsWithViewIdBase@@UISearchActivatedEventArgsWithLinguisticDetails@Activation@ApplicationModel@Windows@@UISearchActivatedEventArgs@678@U?$CloakedIid@UIValueMarshalByPropertySet@Internal@Marshaling@Foundation@Windows@@@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,CActivatedEventArgsWithViewIdBase,Windows::ApplicationModel::Activation::ISearchActivatedEventArgsWithLinguisticDetails,Windows::ApplicationModel::Activation::ISearchActivatedEventArgs,Microsoft::WRL::CloakedIid<Windows::Foundation::Marshaling::Internal::IValueMarshalByPropertySet>>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,CActivatedEventArgsWithViewIdBase,Windows::ApplicationModel::Activation::ISearchActivatedEventArgsWithLinguisticDetails,Windows::ApplicationModel::Activation::ISearchActivatedEventArgs,Microsoft::WRL::CloakedIid<Windows::Foundation::Marshaling::Internal::IValueMarshalByPropertySet>>(void)
```
