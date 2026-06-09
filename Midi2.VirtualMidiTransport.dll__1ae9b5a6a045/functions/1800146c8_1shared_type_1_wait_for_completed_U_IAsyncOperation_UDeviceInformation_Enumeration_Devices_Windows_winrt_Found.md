# ??1shared_type@?1???$wait_for_completed@U?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@YA?A_PAEBU?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@2@I@Z@QEAA@XZ

- ea: `0x1800146c8`
- end: `0x1800146eb`
- name: `??1shared_type@?1???$wait_for_completed@U?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@YA?A_PAEBU?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@2@I@Z@QEAA@XZ`
- size: `35`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800200e5`

## callees

- `0x180004754`
- `0x1800146c8`

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
0x1800146c8  push    rbx
0x1800146ca  sub     rsp, 20h
0x1800146ce  mov     rbx, rcx
0x1800146d1  mov     rcx, [rcx]; hObject
0x1800146d4  test    rcx, rcx
0x1800146d7  jz      short loc_1800146E5
0x1800146d9  call    WINRT_IMPL_CloseHandle
0x1800146de  mov     qword ptr [rbx], 0
0x1800146e5  add     rsp, 20h
0x1800146e9  pop     rbx
0x1800146ea  retn
```
