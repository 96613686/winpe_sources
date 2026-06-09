# std::_Init_once_completer::~_Init_once_completer(void)

- ea: `0x18004ec00`
- end: `0x18004ec22`
- name: `??1_Init_once_completer@std@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(std::_Init_once_completer *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1801052c3`

## callees

- `0x180004dd8`
- `0x18004ec00`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18004ec0d`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18004ec0d`

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
0x18004ec00  sub     rsp, 28h
0x18004ec04  mov     edx, [rcx+8]; dwFlags
0x18004ec07  xor     r8d, r8d; lpContext
0x18004ec0a  mov     rcx, [rcx]; lpInitOnce
0x18004ec0d  call    cs:__imp_InitOnceComplete
0x18004ec13  test    eax, eax
0x18004ec15  jz      short loc_18004EC1C
0x18004ec17  add     rsp, 28h
0x18004ec1b  retn
0x18004ec1c  call    __std_init_once_link_alternate_names_and_abort
```
