# NotificationMetadata::~NotificationMetadata(void)

- ea: `0x180064bbc`
- end: `0x180064c74`
- name: `??1NotificationMetadata@@QEAA@XZ`
- size: `184`
- prototype: `void __fastcall(NotificationMetadata *__hidden this)`
- caller_count: `6`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800668c4`
- `0x1801b370c`
- `0x1801b37a4`
- `0x1801fd975`
- `0x18021022f`
- `0x180210253`

## callees

- `0x1800101f4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064bc9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064bdb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064bed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064bff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064c11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064c23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064c35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064c47`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064c59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064bc9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064bdb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064bed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064bff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064c11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064c23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064c35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064c47`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064c59`

## pseudocode

```c
void __fastcall NotificationMetadata::~NotificationMetadata(HSTRING *this)
{
  WindowsDeleteString(this[10]);
  this[10] = 0;
  WindowsDeleteString(this[9]);
  this[9] = 0;
  WindowsDeleteString(this[8]);
  this[8] = 0;
  WindowsDeleteString(this[7]);
  this[7] = 0;
  WindowsDeleteString(this[6]);
  this[6] = 0;
  WindowsDeleteString(this[5]);
  this[5] = 0;
  WindowsDeleteString(this[4]);
  this[4] = 0;
  WindowsDeleteString(this[3]);
  this[3] = 0;
  WindowsDeleteString(this[2]);
  this[2] = 0;
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(this);
}

```

## disassembly

```asm
0x180064bbc  push    rbx
0x180064bbe  sub     rsp, 20h
0x180064bc2  mov     rbx, rcx
0x180064bc5  mov     rcx, [rcx+50h]; string
0x180064bc9  call    cs:__imp_WindowsDeleteString
0x180064bcf  mov     qword ptr [rbx+50h], 0
0x180064bd7  mov     rcx, [rbx+48h]; string
0x180064bdb  call    cs:__imp_WindowsDeleteString
0x180064be1  mov     qword ptr [rbx+48h], 0
0x180064be9  mov     rcx, [rbx+40h]; string
0x180064bed  call    cs:__imp_WindowsDeleteString
0x180064bf3  mov     qword ptr [rbx+40h], 0
0x180064bfb  mov     rcx, [rbx+38h]; string
0x180064bff  call    cs:__imp_WindowsDeleteString
0x180064c05  mov     qword ptr [rbx+38h], 0
0x180064c0d  mov     rcx, [rbx+30h]; string
0x180064c11  call    cs:__imp_WindowsDeleteString
0x180064c17  mov     qword ptr [rbx+30h], 0
0x180064c1f  mov     rcx, [rbx+28h]; string
0x180064c23  call    cs:__imp_WindowsDeleteString
0x180064c29  mov     qword ptr [rbx+28h], 0
0x180064c31  mov     rcx, [rbx+20h]; string
0x180064c35  call    cs:__imp_WindowsDeleteString
0x180064c3b  mov     qword ptr [rbx+20h], 0
0x180064c43  mov     rcx, [rbx+18h]; string
0x180064c47  call    cs:__imp_WindowsDeleteString
0x180064c4d  mov     qword ptr [rbx+18h], 0
0x180064c55  mov     rcx, [rbx+10h]; string
0x180064c59  call    cs:__imp_WindowsDeleteString
0x180064c5f  mov     rcx, rbx
0x180064c62  mov     qword ptr [rbx+10h], 0
0x180064c6a  add     rsp, 20h
0x180064c6e  pop     rbx
0x180064c6f  jmp     ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
```
