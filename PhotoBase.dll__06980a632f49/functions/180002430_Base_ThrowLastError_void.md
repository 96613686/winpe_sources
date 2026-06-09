# Base::ThrowLastError(void)

- ea: `0x180002430`
- end: `0x180002449`
- name: `?ThrowLastError@Base@@YAXXZ`
- size: `25`
- prototype: `void __fastcall __noreturn(Base *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180003cd0`
- `0x180004c6c`
- `0x180004dd8`
- `0x180004f94`
- `0x18000558c`
- `0x180006880`
- `0x1800069e4`

## callees

- `0x18000247c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180002434`
- `KERNEL32!GetLastError` at `0x180002434`

## pseudocode

```c
void __fastcall __noreturn Base::ThrowLastError(Base *this)
{
  unsigned __int16 LastError; // ax
  int v2; // edx

  LastError = GetLastError();
  BasePrivate::ThrowImpl((BasePrivate *)(LastError | 0x80070000), v2);
}

```

## disassembly

```asm
0x180002430  sub     rsp, 28h; void ATL::BaseAtlThrowLastError(void)
0x180002434  call    cs:__imp_GetLastError
0x18000243a  movzx   ecx, ax
0x18000243d  or      ecx, 80070000h; this
0x180002443  call    ?ThrowImpl@BasePrivate@@YAXJ@Z; BasePrivate::ThrowImpl(long)
```
