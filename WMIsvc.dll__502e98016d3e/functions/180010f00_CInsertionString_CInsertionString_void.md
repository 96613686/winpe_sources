# CInsertionString::~CInsertionString(void)

- ea: `0x180010f00`
- end: `0x180010f1c`
- name: `??1CInsertionString@@QEAA@XZ`
- size: `28`
- prototype: `void __fastcall(CInsertionString *__hidden this)`
- caller_count: `21`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18001da4d`
- `0x18001da5f`
- `0x18001da71`
- `0x18001da83`
- `0x18001da95`
- `0x18001daa7`
- `0x18001dab9`
- `0x18001dacb`
- `0x18001dadd`
- `0x18001daef`
- `0x18001ddcb`
- `0x18001dddd`
- `0x18001ddef`
- `0x18001de01`
- `0x18001de13`
- `0x18001de25`
- `0x18001de37`
- `0x18001de49`
- `0x18001de5b`
- `0x18001de6d`
- `0x18001e8f4`

## import_xrefs

- `wbemcomn!?DeleteString@WString@@AEAAXPEAG@Z` at `0x180010f10`
- `wbemcomn!?DeleteString@WString@@AEAAXPEAG@Z` at `0x180010f10`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CInsertionString::~CInsertionString(unsigned __int16 **this)
{
  WString::DeleteString((WString *)(this + 1), this[1]);
}

```

## disassembly

```asm
0x180010f00  mov     [rsp+arg_0], rcx
0x180010f05  sub     rsp, 28h
0x180010f09  add     rcx, 8
0x180010f0d  mov     rdx, [rcx]
0x180010f10  call    cs:__imp_?DeleteString@WString@@AEAAXPEAG@Z; WString::DeleteString(ushort *)
0x180010f16  nop
0x180010f17  add     rsp, 28h
0x180010f1b  retn
```
