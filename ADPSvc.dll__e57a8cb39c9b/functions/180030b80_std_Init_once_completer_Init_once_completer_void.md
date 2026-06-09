# std::_Init_once_completer::~_Init_once_completer(void)

- ea: `0x180030b80`
- end: `0x180030ba2`
- name: `??1_Init_once_completer@std@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(std::_Init_once_completer *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800c902a`

## callees

- `0x180003748`
- `0x180030b80`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180030b8d`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180030b8d`

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
0x180030b80  sub     rsp, 28h
0x180030b84  mov     edx, [rcx+8]; dwFlags
0x180030b87  xor     r8d, r8d; lpContext
0x180030b8a  mov     rcx, [rcx]; lpInitOnce
0x180030b8d  call    cs:__imp_InitOnceComplete
0x180030b93  test    eax, eax
0x180030b95  jz      short loc_180030B9C
0x180030b97  add     rsp, 28h
0x180030b9b  retn
0x180030b9c  call    __std_init_once_link_alternate_names_and_abort
```
