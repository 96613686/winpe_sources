# std::_Init_once_completer::~_Init_once_completer(void)

- ea: `0x18001b8ac`
- end: `0x18001b8ce`
- name: `??1_Init_once_completer@std@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(std::_Init_once_completer *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001a8cc`

## callees

- `0x1800041a4`
- `0x18001b8ac`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001b8b9`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001b8b9`

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
0x18001b8ac  sub     rsp, 28h
0x18001b8b0  mov     edx, [rcx+8]; dwFlags
0x18001b8b3  xor     r8d, r8d; lpContext
0x18001b8b6  mov     rcx, [rcx]; lpInitOnce
0x18001b8b9  call    cs:__imp_InitOnceComplete
0x18001b8bf  test    eax, eax
0x18001b8c1  jnz     short loc_18001B8C9
0x18001b8c3  call    __std_init_once_link_alternate_names_and_abort
0x18001b8c9  add     rsp, 28h
0x18001b8cd  retn
```
