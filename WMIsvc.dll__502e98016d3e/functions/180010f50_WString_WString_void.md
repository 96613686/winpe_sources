# WString::~WString(void)

- ea: `0x180010f50`
- end: `0x180010f63`
- name: `??1WString@@QEAA@XZ`
- size: `19`
- prototype: `void __fastcall(WString *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18001e739`
- `0x18001e78f`

## import_xrefs

- `wbemcomn!?DeleteString@WString@@AEAAXPEAG@Z` at `0x180010f57`
- `wbemcomn!?DeleteString@WString@@AEAAXPEAG@Z` at `0x180010f57`

## pseudocode

```c
void __fastcall WString::~WString(WString *this)
{
  WString::DeleteString(this, *(unsigned __int16 **)this);
}

```

## disassembly

```asm
0x180010f50  sub     rsp, 28h
0x180010f54  mov     rdx, [rcx]
0x180010f57  call    cs:__imp_?DeleteString@WString@@AEAAXPEAG@Z; WString::DeleteString(ushort *)
0x180010f5d  nop
0x180010f5e  add     rsp, 28h
0x180010f62  retn
```
