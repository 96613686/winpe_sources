# std::_Init_once_completer::~_Init_once_completer(void)

- ea: `0x180008740`
- end: `0x180008762`
- name: `??1_Init_once_completer@std@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(std::_Init_once_completer *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180028f60`

## callees

- `0x180008740`
- `0x180008c38`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000874d`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000874d`

## pseudocode

```c
void __fastcall std::_Init_once_completer::~_Init_once_completer(std::_Init_once_completer *this)
{
  __int64 v1; // rdx
  __int64 v2; // rcx

  if ( !InitOnceComplete(*(LPINIT_ONCE *)this, *((_DWORD *)this + 2), 0) )
    _std_init_once_link_alternate_names_and_abort(v2, v1);
}

```

## disassembly

```asm
0x180008740  sub     rsp, 28h
0x180008744  mov     edx, [rcx+8]; dwFlags
0x180008747  xor     r8d, r8d; lpContext
0x18000874a  mov     rcx, [rcx]; lpInitOnce
0x18000874d  call    cs:__imp_InitOnceComplete
0x180008753  test    eax, eax
0x180008755  jz      short loc_18000875C
0x180008757  add     rsp, 28h
0x18000875b  retn
0x18000875c  call    __std_init_once_link_alternate_names_and_abort
```
