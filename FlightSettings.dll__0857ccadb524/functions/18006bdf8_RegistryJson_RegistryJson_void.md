# RegistryJson::~RegistryJson(void)

- ea: `0x18006bdf8`
- end: `0x18006be58`
- name: `??1RegistryJson@@MEAA@XZ`
- size: `96`
- prototype: `void __fastcall(RegistryJson *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x18006bee0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006be0f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006be21`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006be33`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006be0f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006be21`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006be33`

## pseudocode

```c
void __fastcall RegistryJson::~RegistryJson(HSTRING *this)
{
  *this = (HSTRING)&RegistryJson::`vftable';
  WindowsDeleteString(this[5]);
  this[5] = 0;
  WindowsDeleteString(this[4]);
  this[4] = 0;
  WindowsDeleteString(this[3]);
  this[3] = 0;
  *this = (HSTRING)&RegValet::IRegistryJson::`vftable';
  *((_DWORD *)this + 3) = -1073741823;
}

```

## disassembly

```asm
0x18006bdf8  push    rbx
0x18006bdfa  sub     rsp, 20h
0x18006bdfe  lea     rax, ??_7RegistryJson@@6B@; const RegistryJson::`vftable'
0x18006be05  mov     rbx, rcx
0x18006be08  mov     [rcx], rax
0x18006be0b  mov     rcx, [rcx+28h]; string
0x18006be0f  call    cs:__imp_WindowsDeleteString
0x18006be15  mov     qword ptr [rbx+28h], 0
0x18006be1d  mov     rcx, [rbx+20h]; string
0x18006be21  call    cs:__imp_WindowsDeleteString
0x18006be27  mov     qword ptr [rbx+20h], 0
0x18006be2f  mov     rcx, [rbx+18h]; string
0x18006be33  call    cs:__imp_WindowsDeleteString
0x18006be39  mov     qword ptr [rbx+18h], 0
0x18006be41  lea     rax, ??_7IRegistryJson@RegValet@@6B@; const RegValet::IRegistryJson::`vftable'
0x18006be48  mov     [rbx], rax
0x18006be4b  mov     dword ptr [rbx+0Ch], 0C0000001h
0x18006be52  add     rsp, 20h
0x18006be56  pop     rbx
0x18006be57  retn
```
