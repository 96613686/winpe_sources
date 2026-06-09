# Windows::Networking::UX::Internal::CategoryBase::~CategoryBase(void)

- ea: `0x180025304`
- end: `0x180025374`
- name: `??1CategoryBase@Internal@UX@Networking@Windows@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(Windows::Networking::UX::Internal::CategoryBase *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800252d4`

## callees

- `0x180002150`
- `0x180006208`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180025329`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180025329`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002533c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002534e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025360`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002533c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002534e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025360`

## pseudocode

```c
void __fastcall Windows::Networking::UX::Internal::CategoryBase::~CategoryBase(
        Windows::Networking::UX::Internal::CategoryBase *this)
{
  Microsoft::WRL::EventSource<Windows::Networking::UX::IMbConnectionProfileUpdatedEventHandler,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<Windows::Networking::UX::IMbConnectionProfileUpdatedEventHandler,Microsoft::WRL::InvokeModeOptions<-2>>((char *)this + 176);
  Microsoft::WRL::EventSource<Windows::Networking::UX::IMbConnectionProfileUpdatedEventHandler,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<Windows::Networking::UX::IMbConnectionProfileUpdatedEventHandler,Microsoft::WRL::InvokeModeOptions<-2>>((char *)this + 152);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 96);
  WindowsDeleteString(*((HSTRING *)this + 8));
  *((_QWORD *)this + 8) = 0;
  WindowsDeleteString(*((HSTRING *)this + 6));
  *((_QWORD *)this + 6) = 0;
  WindowsDeleteString(*((HSTRING *)this + 5));
  *((_QWORD *)this + 5) = 0;
}

```

## disassembly

```asm
0x180025304  push    rbx
0x180025306  sub     rsp, 20h
0x18002530a  mov     rbx, rcx
0x18002530d  add     rcx, 0B0h
0x180025314  call    ??1?$EventSource@UIMbConnectionProfileUpdatedEventHandler@UX@Networking@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::EventSource<Windows::Networking::UX::IMbConnectionProfileUpdatedEventHandler,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<Windows::Networking::UX::IMbConnectionProfileUpdatedEventHandler,Microsoft::WRL::InvokeModeOptions<-2>>(void)
0x180025319  lea     rcx, [rbx+98h]
0x180025320  call    ??1?$EventSource@UIMbConnectionProfileUpdatedEventHandler@UX@Networking@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::EventSource<Windows::Networking::UX::IMbConnectionProfileUpdatedEventHandler,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<Windows::Networking::UX::IMbConnectionProfileUpdatedEventHandler,Microsoft::WRL::InvokeModeOptions<-2>>(void)
0x180025325  lea     rcx, [rbx+70h]; lpCriticalSection
0x180025329  call    cs:__imp_DeleteCriticalSection
0x18002532f  lea     rcx, [rbx+60h]
0x180025333  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180025338  mov     rcx, [rbx+40h]; string
0x18002533c  call    cs:__imp_WindowsDeleteString
0x180025342  mov     qword ptr [rbx+40h], 0
0x18002534a  mov     rcx, [rbx+30h]; string
0x18002534e  call    cs:__imp_WindowsDeleteString
0x180025354  mov     qword ptr [rbx+30h], 0
0x18002535c  mov     rcx, [rbx+28h]; string
0x180025360  call    cs:__imp_WindowsDeleteString
0x180025366  mov     qword ptr [rbx+28h], 0
0x18002536e  add     rsp, 20h
0x180025372  pop     rbx
0x180025373  retn
```
