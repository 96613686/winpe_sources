# wil::last_error_context::~last_error_context(void)

- ea: `0x18000dadc`
- end: `0x18000daf3`
- name: `??1last_error_context@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d0e8`
- `0x18000d884`
- `0x18000d92c`
- `0x18000da14`
- `0x18000db84`
- `0x180010be4`
- `0x18001439c`
- `0x1800143f0`

## callees

- `0x18000dadc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dae8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dae8`

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
0x18000dadc  sub     rsp, 28h
0x18000dae0  cmp     byte ptr [rcx], 0
0x18000dae3  jnz     short loc_18000DAEE
0x18000dae5  mov     ecx, [rcx+4]; dwErrCode
0x18000dae8  call    cs:__imp_SetLastError
0x18000daee  add     rsp, 28h
0x18000daf2  retn
```
