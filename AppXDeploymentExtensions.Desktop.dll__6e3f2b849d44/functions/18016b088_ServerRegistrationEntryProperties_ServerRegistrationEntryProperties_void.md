# ServerRegistrationEntryProperties::~ServerRegistrationEntryProperties(void)

- ea: `0x18016b088`
- end: `0x18016b143`
- name: `??1ServerRegistrationEntryProperties@@QEAA@XZ`
- size: `187`
- prototype: `void __fastcall(ServerRegistrationEntryProperties *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18016afe0`

## callees

- `0x180006970`
- `0x180163550`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016b0a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016b0bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016b0e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016b0f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016b110`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016b128`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016b0a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016b0bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016b0e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016b0f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016b110`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016b128`

## pseudocode

```c
void __fastcall ServerRegistrationEntryProperties::~ServerRegistrationEntryProperties(HSTRING *this)
{
  Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(this + 22);
  WindowsDeleteString(this[21]);
  this[21] = 0;
  WindowsDeleteString(this[14]);
  this[14] = 0;
  SecurityDescriptor::Release((SecurityDescriptor *)(this + 12));
  WindowsDeleteString(this[10]);
  this[10] = 0;
  WindowsDeleteString(this[8]);
  this[8] = 0;
  WindowsDeleteString(this[4]);
  this[4] = 0;
  WindowsDeleteString(this[1]);
  this[1] = 0;
}

```

## disassembly

```asm
0x18016b088  push    rbx
0x18016b08a  sub     rsp, 20h
0x18016b08e  mov     rbx, rcx
0x18016b091  add     rcx, 0B0h
0x18016b098  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x18016b09d  mov     rcx, [rbx+0A8h]; string
0x18016b0a4  call    cs:__imp_WindowsDeleteString
0x18016b0ab  nop     dword ptr [rax+rax+00h]
0x18016b0b0  mov     qword ptr [rbx+0A8h], 0
0x18016b0bb  mov     rcx, [rbx+70h]; string
0x18016b0bf  call    cs:__imp_WindowsDeleteString
0x18016b0c6  nop     dword ptr [rax+rax+00h]
0x18016b0cb  lea     rcx, [rbx+60h]; this
0x18016b0cf  mov     qword ptr [rbx+70h], 0
0x18016b0d7  call    ?Release@SecurityDescriptor@@QEAAXXZ; SecurityDescriptor::Release(void)
0x18016b0dc  mov     rcx, [rbx+50h]; string
0x18016b0e0  call    cs:__imp_WindowsDeleteString
0x18016b0e7  nop     dword ptr [rax+rax+00h]
0x18016b0ec  mov     qword ptr [rbx+50h], 0
0x18016b0f4  mov     rcx, [rbx+40h]; string
0x18016b0f8  call    cs:__imp_WindowsDeleteString
0x18016b0ff  nop     dword ptr [rax+rax+00h]
0x18016b104  mov     qword ptr [rbx+40h], 0
0x18016b10c  mov     rcx, [rbx+20h]; string
0x18016b110  call    cs:__imp_WindowsDeleteString
0x18016b117  nop     dword ptr [rax+rax+00h]
0x18016b11c  mov     qword ptr [rbx+20h], 0
0x18016b124  mov     rcx, [rbx+8]; string
0x18016b128  call    cs:__imp_WindowsDeleteString
0x18016b12f  nop     dword ptr [rax+rax+00h]
0x18016b134  mov     qword ptr [rbx+8], 0
0x18016b13c  add     rsp, 20h
0x18016b140  pop     rbx
0x18016b141  retn
```
