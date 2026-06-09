# CInsertionString::~CInsertionString(void)

- ea: `0x140002b1c`
- end: `0x140002b38`
- name: `??1CInsertionString@@QEAA@XZ`
- size: `28`
- prototype: `void __fastcall(unsigned __int16 **this)`
- caller_count: `34`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140002b5c`
- `0x140014d84`
- `0x140014d96`
- `0x140014da8`
- `0x140014dba`
- `0x140014dcc`
- `0x140014dde`
- `0x140014df0`
- `0x140014e02`
- `0x140014e14`
- `0x140014e26`
- `0x140014e4c`
- `0x140014e5e`
- `0x140014e70`
- `0x140014e82`
- `0x140014e94`
- `0x140014ea6`
- `0x140014eb8`
- `0x140014eca`
- `0x140014edc`
- `0x140014eee`
- `0x140014f36`
- `0x140014f48`
- `0x140014f5a`
- `0x140014f6c`
- `0x140014ffc`
- `0x14001500e`
- `0x140015020`
- `0x140015032`
- `0x140015044`
- `0x140015056`
- `0x140015068`
- `0x14001507a`
- `0x140015135`

## import_xrefs

- `wbemcomn!?DeleteString@WString@@AEAAXPEAG@Z` at `0x140002b2c`
- `wbemcomn!?DeleteString@WString@@AEAAXPEAG@Z` at `0x140002b2c`

## pseudocode

```c
void __fastcall CInsertionString::~CInsertionString(unsigned __int16 **this)
{
  WString::DeleteString((WString *)(this + 1), this[1]);
}

```

## disassembly

```asm
0x140002b1c  mov     [rsp+arg_0], rcx
0x140002b21  sub     rsp, 28h
0x140002b25  add     rcx, 8
0x140002b29  mov     rdx, [rcx]
0x140002b2c  call    cs:__imp_?DeleteString@WString@@AEAAXPEAG@Z; WString::DeleteString(ushort *)
0x140002b32  nop
0x140002b33  add     rsp, 28h
0x140002b37  retn
```
