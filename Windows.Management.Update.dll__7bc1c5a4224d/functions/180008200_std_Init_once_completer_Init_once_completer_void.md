# std::_Init_once_completer::~_Init_once_completer(void)

- ea: `0x180008200`
- end: `0x180008222`
- name: `??1_Init_once_completer@std@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(std::_Init_once_completer *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180027a00`

## callees

- `0x180008200`
- `0x180008698`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000820d`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000820d`

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
0x180008200  sub     rsp, 28h
0x180008204  mov     edx, [rcx+8]; dwFlags
0x180008207  xor     r8d, r8d; lpContext
0x18000820a  mov     rcx, [rcx]; lpInitOnce
0x18000820d  call    cs:__imp_InitOnceComplete
0x180008213  test    eax, eax
0x180008215  jz      short loc_18000821C
0x180008217  add     rsp, 28h
0x18000821b  retn
0x18000821c  call    __std_init_once_link_alternate_names_and_abort
```
