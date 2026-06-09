# wil::last_error_context::~last_error_context(void)

- ea: `0x140005460`
- end: `0x140005477`
- name: `??1last_error_context@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140007884`
- `0x1400078d8`
- `0x14000ca7c`
- `0x14000d884`

## callees

- `0x140005460`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000546c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000546c`

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
0x140005460  sub     rsp, 28h
0x140005464  cmp     byte ptr [rcx], 0
0x140005467  jnz     short loc_140005472
0x140005469  mov     ecx, [rcx+4]; dwErrCode
0x14000546c  call    cs:__imp_SetLastError
0x140005472  add     rsp, 28h
0x140005476  retn
```
