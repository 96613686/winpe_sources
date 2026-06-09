# std::_Init_once_completer::~_Init_once_completer(void)

- ea: `0x14003260c`
- end: `0x14003262e`
- name: `??1_Init_once_completer@std@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(std::_Init_once_completer *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140033110`

## callees

- `0x140003ec8`
- `0x14003260c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x140032619`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x140032619`

## pseudocode

```c
void __fastcall std::_Init_once_completer::~_Init_once_completer(std::_Init_once_completer *this)
{
  if ( !InitOnceComplete(*(LPINIT_ONCE *)this, *((_DWORD *)this + 2), 0) )
    _std_init_once_link_alternate_names_and_abort();
}

```

## disassembly

```asm
0x14003260c  sub     rsp, 28h
0x140032610  mov     edx, [rcx+8]; dwFlags
0x140032613  xor     r8d, r8d; lpContext
0x140032616  mov     rcx, [rcx]; lpInitOnce
0x140032619  call    cs:__imp_InitOnceComplete
0x14003261f  test    eax, eax
0x140032621  jz      short loc_140032628
0x140032623  add     rsp, 28h
0x140032627  retn
0x140032628  call    __std_init_once_link_alternate_names_and_abort
```
