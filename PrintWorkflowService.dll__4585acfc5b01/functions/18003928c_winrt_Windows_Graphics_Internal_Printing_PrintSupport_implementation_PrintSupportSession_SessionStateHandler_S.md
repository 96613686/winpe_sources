# winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession::SessionStateHandler::~SessionStateHandler(void)

- ea: `0x18003928c`
- end: `0x1800392bd`
- name: `??1SessionStateHandler@PrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@QEAA@XZ`
- size: `49`
- prototype: `void __fastcall(winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession::SessionStateHandler *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800394bc`

## callees

- `0x1800097ec`
- `0x1800147dc`
- `0x18003928c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800392a2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800392a2`

## pseudocode

```c
void __fastcall winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession::SessionStateHandler::~SessionStateHandler(
        winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession::SessionStateHandler *this)
{
  winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow::~IWindow((winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession::SessionStateHandler *)((char *)this + 64));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  if ( *((_QWORD *)this + 2) )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((char *)this + 16);
}

```

## disassembly

```asm
0x18003928c  push    rbx
0x18003928e  sub     rsp, 20h
0x180039292  mov     rbx, rcx
0x180039295  add     rcx, 40h ; '@'; this
0x180039299  call    ??1IWindow@WindowManagement@ApplicationModel@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow::~IWindow(void)
0x18003929e  lea     rcx, [rbx+18h]; lpCriticalSection
0x1800392a2  call    cs:__imp_DeleteCriticalSection
0x1800392a8  lea     rcx, [rbx+10h]
0x1800392ac  cmp     qword ptr [rcx], 0
0x1800392b0  jz      short loc_1800392B7
0x1800392b2  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800392b7  add     rsp, 20h
0x1800392bb  pop     rbx
0x1800392bc  retn
```
