# SystemSettings::WorkAccess::CAccountEnthusiastData::~CAccountEnthusiastData(void)

- ea: `0x1800456a0`
- end: `0x1800456e1`
- name: `??1CAccountEnthusiastData@WorkAccess@SystemSettings@@UEAA@XZ`
- size: `65`
- prototype: `void __fastcall(SystemSettings::WorkAccess::CAccountEnthusiastData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180045af0`

## callees

- `0x1800290b8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800456b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800456c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800456b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800456c7`

## pseudocode

```c
void __fastcall SystemSettings::WorkAccess::CAccountEnthusiastData::~CAccountEnthusiastData(HSTRING *this)
{
  *this = (HSTRING)&SystemSettings::WorkAccess::CAccountEnthusiastData::`vftable';
  WindowsDeleteString(this[1]);
  WindowsDeleteString(this[2]);
  _bstr_t::_Free((_bstr_t *)(this + 5));
}

```

## disassembly

```asm
0x1800456a0  push    rbx
0x1800456a2  sub     rsp, 20h
0x1800456a6  lea     rax, ??_7CAccountEnthusiastData@WorkAccess@SystemSettings@@6B@; const SystemSettings::WorkAccess::CAccountEnthusiastData::`vftable'
0x1800456ad  mov     rbx, rcx
0x1800456b0  mov     [rcx], rax
0x1800456b3  mov     rcx, [rcx+8]; string
0x1800456b7  call    cs:__imp_WindowsDeleteString
0x1800456be  nop     dword ptr [rax+rax+00h]
0x1800456c3  mov     rcx, [rbx+10h]; string
0x1800456c7  call    cs:__imp_WindowsDeleteString
0x1800456ce  nop     dword ptr [rax+rax+00h]
0x1800456d3  lea     rcx, [rbx+28h]; this
0x1800456d7  add     rsp, 20h
0x1800456db  pop     rbx
0x1800456dc  jmp     ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
```
