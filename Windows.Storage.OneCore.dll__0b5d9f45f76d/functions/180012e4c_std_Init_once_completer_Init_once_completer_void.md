# std::_Init_once_completer::~_Init_once_completer(void)

- ea: `0x180012e4c`
- end: `0x180012e6e`
- name: `??1_Init_once_completer@std@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(std::_Init_once_completer *__hidden this)`
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180012760`
- `0x1800127d4`
- `0x1800128b0`
- `0x180012980`
- `0x1800153a0`
- `0x180023d5a`
- `0x180023d6c`

## callees

- `0x1800027c8`
- `0x180012e4c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180012e59`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180012e59`

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
0x180012e4c  sub     rsp, 28h
0x180012e50  mov     edx, [rcx+8]; dwFlags
0x180012e53  xor     r8d, r8d; lpContext
0x180012e56  mov     rcx, [rcx]; lpInitOnce
0x180012e59  call    cs:__imp_InitOnceComplete
0x180012e5f  test    eax, eax
0x180012e61  jnz     short loc_180012E69
0x180012e63  call    __std_init_once_link_alternate_names_and_abort
0x180012e69  add     rsp, 28h
0x180012e6d  retn
```
