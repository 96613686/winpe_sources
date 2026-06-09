# std::_Init_once_completer::~_Init_once_completer(void)

- ea: `0x180011df4`
- end: `0x180011e16`
- name: `??1_Init_once_completer@std@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(std::_Init_once_completer *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000e184`

## callees

- `0x180001f68`
- `0x180011df4`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180011e01`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180011e01`

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
0x180011df4  sub     rsp, 28h
0x180011df8  mov     edx, [rcx+8]; dwFlags
0x180011dfb  xor     r8d, r8d; lpContext
0x180011dfe  mov     rcx, [rcx]; lpInitOnce
0x180011e01  call    cs:__imp_InitOnceComplete
0x180011e07  test    eax, eax
0x180011e09  jnz     short loc_180011E11
0x180011e0b  call    __std_init_once_link_alternate_names_and_abort
0x180011e11  add     rsp, 28h
0x180011e15  retn
```
