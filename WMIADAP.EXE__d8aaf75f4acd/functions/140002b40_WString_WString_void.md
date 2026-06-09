# WString::~WString(void)

- ea: `0x140002b40`
- end: `0x140002b53`
- name: `??1WString@@QEAA@XZ`
- size: `19`
- prototype: `void __fastcall(WString *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140014d6e`
- `0x1400150c2`
- `0x140015147`
- `0x1400151c5`

## import_xrefs

- `wbemcomn!?DeleteString@WString@@AEAAXPEAG@Z` at `0x140002b47`
- `wbemcomn!?DeleteString@WString@@AEAAXPEAG@Z` at `0x140002b47`

## pseudocode

```c
void __fastcall WString::~WString(WString *this)
{
  WString::DeleteString(this, *(unsigned __int16 **)this);
}

```

## disassembly

```asm
0x140002b40  sub     rsp, 28h
0x140002b44  mov     rdx, [rcx]
0x140002b47  call    cs:__imp_?DeleteString@WString@@AEAAXPEAG@Z; WString::DeleteString(ushort *)
0x140002b4d  nop
0x140002b4e  add     rsp, 28h
0x140002b52  retn
```
