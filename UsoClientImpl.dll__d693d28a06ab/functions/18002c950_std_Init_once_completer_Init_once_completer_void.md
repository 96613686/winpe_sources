# std::_Init_once_completer::~_Init_once_completer(void)

- ea: `0x18002c950`
- end: `0x18002c972`
- name: `??1_Init_once_completer@std@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(std::_Init_once_completer *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18005fc1e`

## callees

- `0x18002c950`
- `0x180037fa0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002c95d`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002c95d`

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
0x18002c950  sub     rsp, 28h
0x18002c954  mov     edx, [rcx+8]; dwFlags
0x18002c957  xor     r8d, r8d; lpContext
0x18002c95a  mov     rcx, [rcx]; lpInitOnce
0x18002c95d  call    cs:__imp_InitOnceComplete
0x18002c963  test    eax, eax
0x18002c965  jz      short loc_18002C96C
0x18002c967  add     rsp, 28h
0x18002c96b  retn
0x18002c96c  call    __std_init_once_link_alternate_names_and_abort
```
