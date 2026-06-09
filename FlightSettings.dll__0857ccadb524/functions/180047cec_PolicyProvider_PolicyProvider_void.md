# PolicyProvider::~PolicyProvider(void)

- ea: `0x180047cec`
- end: `0x180047d42`
- name: `??1PolicyProvider@@MEAA@XZ`
- size: `86`
- prototype: `void __fastcall(PolicyProvider *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x1800480d0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047d03`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047d15`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047d27`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047d03`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047d15`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047d27`

## pseudocode

```c
void __fastcall PolicyProvider::~PolicyProvider(HSTRING *this)
{
  *this = (HSTRING)&PolicyProvider::`vftable';
  WindowsDeleteString(this[5]);
  this[5] = 0;
  WindowsDeleteString(this[4]);
  this[4] = 0;
  WindowsDeleteString(this[2]);
  this[2] = 0;
  *((_DWORD *)this + 3) = -1073741823;
}

```

## disassembly

```asm
0x180047cec  push    rbx
0x180047cee  sub     rsp, 20h
0x180047cf2  lea     rax, ??_7PolicyProvider@@6B@; const PolicyProvider::`vftable'
0x180047cf9  mov     rbx, rcx
0x180047cfc  mov     [rcx], rax
0x180047cff  mov     rcx, [rcx+28h]; string
0x180047d03  call    cs:__imp_WindowsDeleteString
0x180047d09  mov     qword ptr [rbx+28h], 0
0x180047d11  mov     rcx, [rbx+20h]; string
0x180047d15  call    cs:__imp_WindowsDeleteString
0x180047d1b  mov     qword ptr [rbx+20h], 0
0x180047d23  mov     rcx, [rbx+10h]; string
0x180047d27  call    cs:__imp_WindowsDeleteString
0x180047d2d  mov     qword ptr [rbx+10h], 0
0x180047d35  mov     dword ptr [rbx+0Ch], 0C0000001h
0x180047d3c  add     rsp, 20h
0x180047d40  pop     rbx
0x180047d41  retn
```
