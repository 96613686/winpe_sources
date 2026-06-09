# wil::last_error_context::~last_error_context(void)

- ea: `0x140004d00`
- end: `0x140004d1e`
- name: `??1last_error_context@wil@@QEAA@XZ`
- size: `30`
- prototype: `void __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x140007e3c`
- `0x140007e98`
- `0x140007eec`
- `0x140008e44`
- `0x140008ec8`
- `0x14000b888`
- `0x140011cd0`
- `0x140011d78`
- `0x140011dd4`

## callees

- `0x140004d00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004d0c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004d0c`

## pseudocode

```c
void __fastcall wil::last_error_context::~last_error_context(wil::last_error_context *this)
{
  if ( !*(_BYTE *)this )
    SetLastError(*((_DWORD *)this + 1));
}

```

## disassembly

```asm
0x140004d00  sub     rsp, 28h
0x140004d04  cmp     byte ptr [rcx], 0
0x140004d07  jnz     short loc_140004D18
0x140004d09  mov     ecx, [rcx+4]; dwErrCode
0x140004d0c  call    cs:__imp_SetLastError
0x140004d13  nop     dword ptr [rax+rax+00h]
0x140004d18  add     rsp, 28h
0x140004d1c  retn
```
