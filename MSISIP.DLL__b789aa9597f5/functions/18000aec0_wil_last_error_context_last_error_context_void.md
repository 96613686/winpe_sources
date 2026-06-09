# wil::last_error_context::~last_error_context(void)

- ea: `0x18000aec0`
- end: `0x18000aed7`
- name: `??1last_error_context@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180006370`
- `0x1800069b4`
- `0x180006fac`
- `0x180007334`
- `0x180007cb8`
- `0x1800097c0`
- `0x18000afa0`
- `0x18000cc9c`
- `0x18000cd40`

## callees

- `0x18000aec0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000aecc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000aecc`

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
0x18000aec0  sub     rsp, 28h
0x18000aec4  cmp     byte ptr [rcx], 0
0x18000aec7  jnz     short loc_18000AED2
0x18000aec9  mov     ecx, [rcx+4]; dwErrCode
0x18000aecc  call    cs:__imp_SetLastError
0x18000aed2  add     rsp, 28h
0x18000aed6  retn
```
