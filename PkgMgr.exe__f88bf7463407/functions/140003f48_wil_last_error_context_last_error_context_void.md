# wil::last_error_context::~last_error_context(void)

- ea: `0x140003f48`
- end: `0x140003f5f`
- name: `??1last_error_context@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x1400063c8`
- `0x14000641c`
- `0x14000e29c`
- `0x14000e318`
- `0x14000ebdc`
- `0x140010870`
- `0x140010918`

## callees

- `0x140003f48`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003f54`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003f54`

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
0x140003f48  sub     rsp, 28h
0x140003f4c  cmp     byte ptr [rcx], 0
0x140003f4f  jnz     short loc_140003F5A
0x140003f51  mov     ecx, [rcx+4]; dwErrCode
0x140003f54  call    cs:__imp_SetLastError
0x140003f5a  add     rsp, 28h
0x140003f5e  retn
```
