# __vcrt_lock

- ea: `0x14001b4f8`
- end: `0x14001b511`
- name: `__vcrt_lock`
- size: `25`
- prototype: `void __fastcall(int)`
- caller_count: `24`
- callee_count: `0`
- tags: ``

## callers

- `0x140014968`
- `0x1400149b0`
- `0x140014b04`
- `0x140014d60`
- `0x140016fb8`
- `0x140017708`
- `0x140018498`
- `0x140018918`
- `0x140018ae0`
- `0x140018b20`
- `0x140018b8c`
- `0x140018bc8`
- `0x140019228`
- `0x140019268`
- `0x1400192a8`
- `0x1400192f0`
- `0x14001b430`
- `0x14001bdb8`
- `0x14001bff8`
- `0x14001cd74`
- `0x14001e3a8`
- `0x14001e560`
- `0x14001ee3c`
- `0x140020614`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x14001b50a`

## pseudocode

```c
void __fastcall _vcrt_lock(int a1)
{
  EnterCriticalSection((LPCRITICAL_SECTION)&qword_14003EA10[5 * a1]);
}

```

## disassembly

```asm
0x14001b4f8  movsxd  rax, ecx
0x14001b4fb  lea     rcx, [rax+rax*4]
0x14001b4ff  lea     rax, qword_14003EA10
0x14001b506  lea     rcx, [rax+rcx*8]
0x14001b50a  jmp     cs:__imp_EnterCriticalSection
```
