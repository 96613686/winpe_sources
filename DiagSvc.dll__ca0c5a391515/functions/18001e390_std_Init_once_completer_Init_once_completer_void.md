# std::_Init_once_completer::~_Init_once_completer(void)

- ea: `0x18001e390`
- end: `0x18001e3b2`
- name: `??1_Init_once_completer@std@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(std::_Init_once_completer *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001d318`

## callees

- `0x180004e30`
- `0x18001e390`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001e39d`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001e39d`

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
0x18001e390  sub     rsp, 28h
0x18001e394  mov     edx, [rcx+8]; dwFlags
0x18001e397  xor     r8d, r8d; lpContext
0x18001e39a  mov     rcx, [rcx]; lpInitOnce
0x18001e39d  call    cs:__imp_InitOnceComplete
0x18001e3a3  test    eax, eax
0x18001e3a5  jnz     short loc_18001E3AD
0x18001e3a7  call    __std_init_once_link_alternate_names_and_abort
0x18001e3ad  add     rsp, 28h
0x18001e3b1  retn
```
