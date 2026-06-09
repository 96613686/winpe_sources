# std::_Init_once_completer::~_Init_once_completer(void)

- ea: `0x180012dc4`
- end: `0x180012de6`
- name: `??1_Init_once_completer@std@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(std::_Init_once_completer *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800109f0`

## callees

- `0x180003bb4`
- `0x180012dc4`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180012dd1`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180012dd1`

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
0x180012dc4  sub     rsp, 28h
0x180012dc8  mov     edx, [rcx+8]; dwFlags
0x180012dcb  xor     r8d, r8d; lpContext
0x180012dce  mov     rcx, [rcx]; lpInitOnce
0x180012dd1  call    cs:__imp_InitOnceComplete
0x180012dd7  test    eax, eax
0x180012dd9  jnz     short loc_180012DE1
0x180012ddb  call    __std_init_once_link_alternate_names_and_abort
0x180012de1  add     rsp, 28h
0x180012de5  retn
```
