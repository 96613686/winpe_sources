# wil::last_error_context::~last_error_context(void)

- ea: `0x140003618`
- end: `0x140003636`
- name: `??1last_error_context@wil@@QEAA@XZ`
- size: `30`
- prototype: `void __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140005d34`
- `0x140006d38`
- `0x140008294`
- `0x1400082f0`

## callees

- `0x140003618`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003624`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003624`

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
0x140003618  sub     rsp, 28h
0x14000361c  cmp     byte ptr [rcx], 0
0x14000361f  jnz     short loc_140003630
0x140003621  mov     ecx, [rcx+4]; dwErrCode
0x140003624  call    cs:__imp_SetLastError
0x14000362b  nop     dword ptr [rax+rax+00h]
0x140003630  add     rsp, 28h
0x140003634  retn
```
