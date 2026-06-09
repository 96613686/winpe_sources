# ??1shared_type@?1???$wait_for_completed@U?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@YA?A_PAEBU?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@2@I@Z@QEAA@XZ

- ea: `0x18000d4a8`
- end: `0x18000d4cb`
- name: `??1shared_type@?1???$wait_for_completed@U?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@YA?A_PAEBU?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@2@I@Z@QEAA@XZ`
- size: `35`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001249a`

## callees

- `0x180003aec`
- `0x18000d4a8`

## pseudocode

```c
BOOL __fastcall `winrt::impl::wait_for_completed<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Devices::Enumeration::DeviceInformation>>'::`2'::shared_type::~shared_type(
        void **a1)
{
  void *v2; // rcx
  BOOL result; // eax

  v2 = *a1;
  if ( v2 )
  {
    result = WINRT_IMPL_CloseHandle(v2);
    *a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000d4a8  push    rbx
0x18000d4aa  sub     rsp, 20h
0x18000d4ae  mov     rbx, rcx
0x18000d4b1  mov     rcx, [rcx]; hObject
0x18000d4b4  test    rcx, rcx
0x18000d4b7  jz      short loc_18000D4C5
0x18000d4b9  call    WINRT_IMPL_CloseHandle
0x18000d4be  mov     qword ptr [rbx], 0
0x18000d4c5  add     rsp, 20h
0x18000d4c9  pop     rbx
0x18000d4ca  retn
```
