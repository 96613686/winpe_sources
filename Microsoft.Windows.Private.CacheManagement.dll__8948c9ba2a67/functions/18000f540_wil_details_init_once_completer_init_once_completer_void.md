# wil::details::init_once_completer::~init_once_completer(void)

- ea: `0x18000f540`
- end: `0x18000f550`
- name: `??1init_once_completer@details@wil@@QEAA@XZ`
- size: `16`
- prototype: `void __fastcall(wil::details::init_once_completer *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18001da60`

## import_xrefs

- `KERNEL32!InitOnceComplete` at `0x18000f549`

## pseudocode

```c
void __fastcall wil::details::init_once_completer::~init_once_completer(wil::details::init_once_completer *this)
{
  InitOnceComplete(*(LPINIT_ONCE *)this, *((_DWORD *)this + 2), 0);
}

```

## disassembly

```asm
0x18000f540  mov     edx, [rcx+8]
0x18000f543  xor     r8d, r8d
0x18000f546  mov     rcx, [rcx]
0x18000f549  jmp     cs:__imp_InitOnceComplete
```
