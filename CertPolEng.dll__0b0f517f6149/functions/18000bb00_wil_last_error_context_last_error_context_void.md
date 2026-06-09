# wil::last_error_context::~last_error_context(void)

- ea: `0x18000bb00`
- end: `0x18000bb17`
- name: `??1last_error_context@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a978`
- `0x18000b4d0`
- `0x18000b8bc`
- `0x18000b9b0`
- `0x18000ba78`
- `0x18000bb44`
- `0x1800129f4`
- `0x180012a98`
- `0x180017554`
- `0x180018a84`

## callees

- `0x18000bb00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bb0c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bb0c`

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
0x18000bb00  sub     rsp, 28h
0x18000bb04  cmp     byte ptr [rcx], 0
0x18000bb07  jnz     short loc_18000BB12
0x18000bb09  mov     ecx, [rcx+4]; dwErrCode
0x18000bb0c  call    cs:__imp_SetLastError
0x18000bb12  add     rsp, 28h
0x18000bb16  retn
```
