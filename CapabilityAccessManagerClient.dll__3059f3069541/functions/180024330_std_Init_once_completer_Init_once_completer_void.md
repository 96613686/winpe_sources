# std::_Init_once_completer::~_Init_once_completer(void)

- ea: `0x180024330`
- end: `0x180024352`
- name: `??1_Init_once_completer@std@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(std::_Init_once_completer *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800242c0`
- `0x180037331`

## callees

- `0x1800058a8`
- `0x180024330`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002433d`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002433d`

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
0x180024330  sub     rsp, 28h
0x180024334  mov     edx, [rcx+8]; dwFlags
0x180024337  xor     r8d, r8d; lpContext
0x18002433a  mov     rcx, [rcx]; lpInitOnce
0x18002433d  call    cs:__imp_InitOnceComplete
0x180024343  test    eax, eax
0x180024345  jz      short loc_18002434C
0x180024347  add     rsp, 28h
0x18002434b  retn
0x18002434c  call    __std_init_once_link_alternate_names_and_abort
```
