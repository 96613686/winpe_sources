# CWMIBroker::~CWMIBroker(void)

- ea: `0x140002f04`
- end: `0x140002f2a`
- name: `??1CWMIBroker@@UEAA@XZ`
- size: `38`
- prototype: `void __fastcall(unsigned __int16 **this)`
- caller_count: `5`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140002ff0`
- `0x140003320`
- `0x1400037f0`
- `0x140014f24`
- `0x1400150d4`

## import_xrefs

- `wbemcomn!?DeleteString@WString@@AEAAXPEAG@Z` at `0x140002f1e`
- `wbemcomn!?DeleteString@WString@@AEAAXPEAG@Z` at `0x140002f1e`

## pseudocode

```c
void __fastcall CWMIBroker::~CWMIBroker(unsigned __int16 **this)
{
  *this = (unsigned __int16 *)&CWMIBroker::`vftable';
  WString::DeleteString((WString *)(this + 1), this[1]);
}

```

## disassembly

```asm
0x140002f04  mov     [rsp+arg_0], rcx
0x140002f09  sub     rsp, 28h
0x140002f0d  lea     rax, ??_7CWMIBroker@@6B@; const CWMIBroker::`vftable'
0x140002f14  mov     [rcx], rax
0x140002f17  add     rcx, 8
0x140002f1b  mov     rdx, [rcx]
0x140002f1e  call    cs:__imp_?DeleteString@WString@@AEAAXPEAG@Z; WString::DeleteString(ushort *)
0x140002f24  nop
0x140002f25  add     rsp, 28h
0x140002f29  retn
```
