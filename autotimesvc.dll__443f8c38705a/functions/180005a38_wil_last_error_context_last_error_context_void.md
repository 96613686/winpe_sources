# wil::last_error_context::~last_error_context(void)

- ea: `0x180005a38`
- end: `0x180005a4f`
- name: `??1last_error_context@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180008e38`
- `0x18000a9e4`
- `0x18000aa38`
- `0x18000aa8c`
- `0x18000bb08`
- `0x18000c098`
- `0x18000f258`
- `0x18000fed4`
- `0x180010ac0`

## callees

- `0x180005a38`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005a44`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005a44`

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
0x180005a38  sub     rsp, 28h
0x180005a3c  cmp     byte ptr [rcx], 0
0x180005a3f  jnz     short loc_180005A4A
0x180005a41  mov     ecx, [rcx+4]; dwErrCode
0x180005a44  call    cs:__imp_SetLastError
0x180005a4a  add     rsp, 28h
0x180005a4e  retn
```
