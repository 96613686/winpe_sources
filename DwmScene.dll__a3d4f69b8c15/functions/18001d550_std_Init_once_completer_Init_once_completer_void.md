# std::_Init_once_completer::~_Init_once_completer(void)

- ea: `0x18001d550`
- end: `0x18001d572`
- name: `??1_Init_once_completer@std@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(std::_Init_once_completer *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001cf70`
- `0x1800d2453`

## callees

- `0x18000d888`
- `0x18001d550`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001d55d`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001d55d`

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
0x18001d550  sub     rsp, 28h
0x18001d554  mov     edx, [rcx+8]; dwFlags
0x18001d557  xor     r8d, r8d; lpContext
0x18001d55a  mov     rcx, [rcx]; lpInitOnce
0x18001d55d  call    cs:__imp_InitOnceComplete
0x18001d563  test    eax, eax
0x18001d565  jnz     short loc_18001D56D
0x18001d567  call    __std_init_once_link_alternate_names_and_abort
0x18001d56d  add     rsp, 28h
0x18001d571  retn
```
