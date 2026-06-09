# wil::last_error_context::~last_error_context(void)

- ea: `0x140001be0`
- end: `0x140001bf7`
- name: `??1last_error_context@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x140001684`
- `0x140001988`
- `0x140001a30`
- `0x140001b18`
- `0x140001c88`
- `0x1400043a4`
- `0x1400071bc`
- `0x140007210`

## callees

- `0x140001be0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140001bec`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140001bec`

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
0x140001be0  sub     rsp, 28h
0x140001be4  cmp     byte ptr [rcx], 0
0x140001be7  jnz     short loc_140001BF2
0x140001be9  mov     ecx, [rcx+4]; dwErrCode
0x140001bec  call    cs:__imp_SetLastError
0x140001bf2  add     rsp, 28h
0x140001bf6  retn
```
