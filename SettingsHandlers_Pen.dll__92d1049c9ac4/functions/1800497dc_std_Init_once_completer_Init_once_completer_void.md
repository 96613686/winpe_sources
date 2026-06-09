# std::_Init_once_completer::~_Init_once_completer(void)

- ea: `0x1800497dc`
- end: `0x1800497fe`
- name: `??1_Init_once_completer@std@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(std::_Init_once_completer *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180046c4c`

## callees

- `0x1800040f8`
- `0x1800497dc`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800497e9`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800497e9`

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
0x1800497dc  sub     rsp, 28h
0x1800497e0  mov     edx, [rcx+8]; dwFlags
0x1800497e3  xor     r8d, r8d; lpContext
0x1800497e6  mov     rcx, [rcx]; lpInitOnce
0x1800497e9  call    cs:__imp_InitOnceComplete
0x1800497ef  test    eax, eax
0x1800497f1  jnz     short loc_1800497F9
0x1800497f3  call    __std_init_once_link_alternate_names_and_abort
0x1800497f9  add     rsp, 28h
0x1800497fd  retn
```
