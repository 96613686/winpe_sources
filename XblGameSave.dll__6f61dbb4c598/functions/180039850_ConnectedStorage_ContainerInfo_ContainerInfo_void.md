# ConnectedStorage::ContainerInfo::~ContainerInfo(void)

- ea: `0x180039850`
- end: `0x180039893`
- name: `??1ContainerInfo@ConnectedStorage@@QEAA@XZ`
- size: `67`
- prototype: `void __fastcall(ConnectedStorage::ContainerInfo *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180038454`
- `0x18003a9d0`
- `0x18005b89c`
- `0x18006a720`
- `0x1800888a8`
- `0x18008bc0e`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003985d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003986f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039880`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003985d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003986f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039880`

## pseudocode

```c
void __fastcall ConnectedStorage::ContainerInfo::~ContainerInfo(HSTRING *this)
{
  WindowsDeleteString(this[2]);
  this[2] = 0;
  WindowsDeleteString(this[1]);
  this[1] = 0;
  WindowsDeleteString(*this);
  *this = 0;
}

```

## disassembly

```asm
0x180039850  push    rbx
0x180039852  sub     rsp, 20h
0x180039856  mov     rbx, rcx
0x180039859  mov     rcx, [rcx+10h]; string
0x18003985d  call    cs:__imp_WindowsDeleteString
0x180039863  mov     qword ptr [rbx+10h], 0
0x18003986b  mov     rcx, [rbx+8]; string
0x18003986f  call    cs:__imp_WindowsDeleteString
0x180039875  mov     qword ptr [rbx+8], 0
0x18003987d  mov     rcx, [rbx]; string
0x180039880  call    cs:__imp_WindowsDeleteString
0x180039886  mov     qword ptr [rbx], 0
0x18003988d  add     rsp, 20h
0x180039891  pop     rbx
0x180039892  retn
```
