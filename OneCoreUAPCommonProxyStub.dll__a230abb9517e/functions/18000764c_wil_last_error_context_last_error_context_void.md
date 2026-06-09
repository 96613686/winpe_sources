# wil::last_error_context::~last_error_context(void)

- ea: `0x18000764c`
- end: `0x180007663`
- name: `??1last_error_context@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180008c1c`
- `0x180009e40`
- `0x180009e94`

## callees

- `0x18000764c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007658`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007658`

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
0x18000764c  sub     rsp, 28h
0x180007650  cmp     byte ptr [rcx], 0
0x180007653  jnz     short loc_18000765E
0x180007655  mov     ecx, [rcx+4]; dwErrCode
0x180007658  call    cs:__imp_SetLastError
0x18000765e  add     rsp, 28h
0x180007662  retn
```
