# std::_Init_once_completer::~_Init_once_completer(void)

- ea: `0x18002fb98`
- end: `0x18002fbba`
- name: `??1_Init_once_completer@std@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(std::_Init_once_completer *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002f038`
- `0x180033d40`
- `0x180058170`

## callees

- `0x180003ca8`
- `0x18002fb98`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002fba5`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002fba5`

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
0x18002fb98  sub     rsp, 28h
0x18002fb9c  mov     edx, [rcx+8]; dwFlags
0x18002fb9f  xor     r8d, r8d; lpContext
0x18002fba2  mov     rcx, [rcx]; lpInitOnce
0x18002fba5  call    cs:__imp_InitOnceComplete
0x18002fbab  test    eax, eax
0x18002fbad  jnz     short loc_18002FBB5
0x18002fbaf  call    __std_init_once_link_alternate_names_and_abort
0x18002fbb5  add     rsp, 28h
0x18002fbb9  retn
```
