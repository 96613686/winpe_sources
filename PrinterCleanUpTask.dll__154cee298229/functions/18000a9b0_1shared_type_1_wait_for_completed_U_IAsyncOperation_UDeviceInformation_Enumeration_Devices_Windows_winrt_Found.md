# ??1shared_type@?1???$wait_for_completed@U?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@YA?A_PAEBU?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@2@I@Z@QEAA@XZ

- ea: `0x18000a9b0`
- end: `0x18000a9d3`
- name: `??1shared_type@?1???$wait_for_completed@U?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@YA?A_PAEBU?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@2@I@Z@QEAA@XZ`
- size: `35`
- prototype: `BOOL __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180016861`

## callees

- `0x180002c14`
- `0x18000a9b0`

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
0x18000a9b0  push    rbx
0x18000a9b2  sub     rsp, 20h
0x18000a9b6  mov     rbx, rcx
0x18000a9b9  mov     rcx, [rcx]; hObject
0x18000a9bc  test    rcx, rcx
0x18000a9bf  jz      short loc_18000A9CD
0x18000a9c1  call    WINRT_IMPL_CloseHandle
0x18000a9c6  mov     qword ptr [rbx], 0
0x18000a9cd  add     rsp, 20h
0x18000a9d1  pop     rbx
0x18000a9d2  retn
```
