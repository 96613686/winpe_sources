# std::_Init_once_completer::~_Init_once_completer(void)

- ea: `0x18000bff4`
- end: `0x18000c016`
- name: `??1_Init_once_completer@std@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(std::_Init_once_completer *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180011703`

## callees

- `0x180002168`
- `0x18000bff4`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000c001`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000c001`

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
0x18000bff4  sub     rsp, 28h
0x18000bff8  mov     edx, [rcx+8]; dwFlags
0x18000bffb  xor     r8d, r8d; lpContext
0x18000bffe  mov     rcx, [rcx]; lpInitOnce
0x18000c001  call    cs:__imp_InitOnceComplete
0x18000c007  test    eax, eax
0x18000c009  jz      short loc_18000C010
0x18000c00b  add     rsp, 28h
0x18000c00f  retn
0x18000c010  call    __std_init_once_link_alternate_names_and_abort
```
