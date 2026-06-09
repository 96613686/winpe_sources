# CSecureLockAction::~CSecureLockAction(void)

- ea: `0x1800647f8`
- end: `0x1800648aa`
- name: `??1CSecureLockAction@@UEAA@XZ`
- size: `178`
- prototype: `void __fastcall(CSecureLockAction *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004f870`

## callees

- `0x18000ea44`
- `0x1800648b0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064814`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006482c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064844`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006485c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064874`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006488c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064814`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006482c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064844`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006485c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064874`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006488c`

## pseudocode

```c
void __fastcall CSecureLockAction::~CSecureLockAction(HSTRING *this)
{
  Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::UI::Logon::Controller::ILockInfo *,enum Windows::Internal::UI::Logon::Controller::LockActivity>,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::UI::Logon::Controller::ILockInfo *,enum Windows::Internal::UI::Logon::Controller::LockActivity>,Microsoft::WRL::InvokeModeOptions<-2>>(this + 32);
  WindowsDeleteString(this[30]);
  this[30] = 0;
  WindowsDeleteString(this[29]);
  this[29] = 0;
  WindowsDeleteString(this[28]);
  this[28] = 0;
  WindowsDeleteString(this[27]);
  this[27] = 0;
  WindowsDeleteString(this[26]);
  this[26] = 0;
  WindowsDeleteString(this[25]);
  this[25] = 0;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::UI::Logon::Controller::IUnlockTrigger,Windows::Internal::UI::Logon::Controller::ILockInfo,Windows::Internal::UI::Logon::Controller::ILockActivityListener,Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::UI::Logon::Controller::IUnlockTrigger,Windows::Internal::UI::Logon::Controller::ILockInfo,Windows::Internal::UI::Logon::Controller::ILockActivityListener,Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>(this);
}

```

## disassembly

```asm
0x1800647f8  push    rbx
0x1800647fa  sub     rsp, 20h
0x1800647fe  mov     rbx, rcx
0x180064801  add     rcx, 100h
0x180064808  call    ??1?$EventSource@U?$ITypedEventHandler@PEAUILockInfo@Controller@Logon@UI@Internal@Windows@@W4LockActivity@23456@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::UI::Logon::Controller::ILockInfo *,Windows::Internal::UI::Logon::Controller::LockActivity>,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::UI::Logon::Controller::ILockInfo *,Windows::Internal::UI::Logon::Controller::LockActivity>,Microsoft::WRL::InvokeModeOptions<-2>>(void)
0x18006480d  mov     rcx, [rbx+0F0h]; string
0x180064814  call    cs:__imp_WindowsDeleteString
0x18006481a  mov     qword ptr [rbx+0F0h], 0
0x180064825  mov     rcx, [rbx+0E8h]; string
0x18006482c  call    cs:__imp_WindowsDeleteString
0x180064832  mov     qword ptr [rbx+0E8h], 0
0x18006483d  mov     rcx, [rbx+0E0h]; string
0x180064844  call    cs:__imp_WindowsDeleteString
0x18006484a  mov     qword ptr [rbx+0E0h], 0
0x180064855  mov     rcx, [rbx+0D8h]; string
0x18006485c  call    cs:__imp_WindowsDeleteString
0x180064862  mov     qword ptr [rbx+0D8h], 0
0x18006486d  mov     rcx, [rbx+0D0h]; string
0x180064874  call    cs:__imp_WindowsDeleteString
0x18006487a  mov     qword ptr [rbx+0D0h], 0
0x180064885  mov     rcx, [rbx+0C8h]; string
0x18006488c  call    cs:__imp_WindowsDeleteString
0x180064892  mov     rcx, rbx
0x180064895  mov     qword ptr [rbx+0C8h], 0
0x1800648a0  add     rsp, 20h
0x1800648a4  pop     rbx
0x1800648a5  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIUnlockTrigger@Controller@Logon@UI@Internal@Windows@@UILockInfo@56789@UILockActivityListener@56789@U?$IAsyncOperation@PEAUHSTRING__@@@Foundation@9@V?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@89@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::UI::Logon::Controller::IUnlockTrigger,Windows::Internal::UI::Logon::Controller::ILockInfo,Windows::Internal::UI::Logon::Controller::ILockActivityListener,Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::UI::Logon::Controller::IUnlockTrigger,Windows::Internal::UI::Logon::Controller::ILockInfo,Windows::Internal::UI::Logon::Controller::ILockActivityListener,Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>(void)
```
