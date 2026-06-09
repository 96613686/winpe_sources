# SystemSettings::DataModel::TokenBrokerSingleton::~TokenBrokerSingleton(void)

- ea: `0x18001acbc`
- end: `0x18001ad50`
- name: `??1TokenBrokerSingleton@DataModel@SystemSettings@@UEAA@XZ`
- size: `148`
- prototype: `void __fastcall(SystemSettings::DataModel::TokenBrokerSingleton *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001bac0`
- `0x1800512e0`

## callees

- `0x1800076ac`
- `0x18001a828`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ace4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ad02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ad20`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ace4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ad02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ad20`

## pseudocode

```c
void __fastcall SystemSettings::DataModel::TokenBrokerSingleton::~TokenBrokerSingleton(HSTRING *this)
{
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(this + 38);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(this + 35);
  WindowsDeleteString(this[34]);
  this[34] = 0;
  WindowsDeleteString(this[33]);
  this[33] = 0;
  WindowsDeleteString(this[32]);
  this[32] = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(this + 31);
  SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::CorpDeviceNotification>::~CSingletonHelper<SystemSettings::DataModel::CorpDeviceNotification>(this);
}

```

## disassembly

```asm
0x18001acbc  push    rbx
0x18001acbe  sub     rsp, 20h
0x18001acc2  mov     rbx, rcx
0x18001acc5  add     rcx, 130h
0x18001accc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001acd1  lea     rcx, [rbx+118h]
0x18001acd8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001acdd  mov     rcx, [rbx+110h]; string
0x18001ace4  call    cs:__imp_WindowsDeleteString
0x18001aceb  nop     dword ptr [rax+rax+00h]
0x18001acf0  mov     qword ptr [rbx+110h], 0
0x18001acfb  mov     rcx, [rbx+108h]; string
0x18001ad02  call    cs:__imp_WindowsDeleteString
0x18001ad09  nop     dword ptr [rax+rax+00h]
0x18001ad0e  mov     qword ptr [rbx+108h], 0
0x18001ad19  mov     rcx, [rbx+100h]; string
0x18001ad20  call    cs:__imp_WindowsDeleteString
0x18001ad27  nop     dword ptr [rax+rax+00h]
0x18001ad2c  lea     rcx, [rbx+0F8h]
0x18001ad33  mov     qword ptr [rbx+100h], 0
0x18001ad3e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001ad43  mov     rcx, rbx
0x18001ad46  add     rsp, 20h
0x18001ad4a  pop     rbx
0x18001ad4b  jmp     ??1?$CSingletonHelper@UCorpDeviceNotification@DataModel@SystemSettings@@@DataModel@SystemSettings@@UEAA@XZ; SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::CorpDeviceNotification>::~CSingletonHelper<SystemSettings::DataModel::CorpDeviceNotification>(void)
```
