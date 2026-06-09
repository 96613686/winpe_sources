# AppUriHandlerRegistrationInfo::~AppUriHandlerRegistrationInfo(void)

- ea: `0x14000a254`
- end: `0x14000a285`
- name: `??1AppUriHandlerRegistrationInfo@@QEAA@XZ`
- size: `49`
- prototype: `void __fastcall(HSTRING *this)`
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140009294`
- `0x14000b114`
- `0x140011698`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000a261`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000a272`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000a261`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000a272`

## pseudocode

```c
void __fastcall AppUriHandlerRegistrationInfo::~AppUriHandlerRegistrationInfo(HSTRING *this)
{
  WindowsDeleteString(this[1]);
  this[1] = 0;
  WindowsDeleteString(*this);
  *this = 0;
}

```

## disassembly

```asm
0x14000a254  push    rbx
0x14000a256  sub     rsp, 20h
0x14000a25a  mov     rbx, rcx
0x14000a25d  mov     rcx, [rcx+8]; string
0x14000a261  call    cs:__imp_WindowsDeleteString
0x14000a267  mov     qword ptr [rbx+8], 0
0x14000a26f  mov     rcx, [rbx]; string
0x14000a272  call    cs:__imp_WindowsDeleteString
0x14000a278  mov     qword ptr [rbx], 0
0x14000a27f  add     rsp, 20h
0x14000a283  pop     rbx
0x14000a284  retn
```
