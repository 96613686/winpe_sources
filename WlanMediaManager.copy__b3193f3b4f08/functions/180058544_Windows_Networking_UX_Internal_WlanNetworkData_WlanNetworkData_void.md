# Windows::Networking::UX::Internal::WlanNetworkData::~WlanNetworkData(void)

- ea: `0x180058544`
- end: `0x180058594`
- name: `??1WlanNetworkData@Internal@UX@Networking@Windows@@QEAA@XZ`
- size: `80`
- prototype: `void __fastcall(Windows::Networking::UX::Internal::WlanNetworkData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180059ee0`

## callees

- `0x180058544`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005856e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180058580`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005856e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180058580`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180058564`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180058564`

## pseudocode

```c
void __fastcall Windows::Networking::UX::Internal::WlanNetworkData::~WlanNetworkData(
        Windows::Networking::UX::Internal::WlanNetworkData *this)
{
  void *v2; // rcx

  v2 = (void *)*((_QWORD *)this + 25);
  *((_QWORD *)this + 25) = 0;
  if ( v2 )
    CoTaskMemFree(v2);
  WindowsDeleteString(*((HSTRING *)this + 7));
  *((_QWORD *)this + 7) = 0;
  WindowsDeleteString(*((HSTRING *)this + 4));
  *((_QWORD *)this + 4) = 0;
}

```

## disassembly

```asm
0x180058544  push    rbx
0x180058546  sub     rsp, 20h
0x18005854a  mov     rbx, rcx
0x18005854d  mov     rcx, [rcx+0C8h]; pv
0x180058554  mov     qword ptr [rbx+0C8h], 0
0x18005855f  test    rcx, rcx
0x180058562  jz      short loc_18005856A
0x180058564  call    cs:__imp_CoTaskMemFree
0x18005856a  mov     rcx, [rbx+38h]; string
0x18005856e  call    cs:__imp_WindowsDeleteString
0x180058574  mov     qword ptr [rbx+38h], 0
0x18005857c  mov     rcx, [rbx+20h]; string
0x180058580  call    cs:__imp_WindowsDeleteString
0x180058586  mov     qword ptr [rbx+20h], 0
0x18005858e  add     rsp, 20h
0x180058592  pop     rbx
0x180058593  retn
```
