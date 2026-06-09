# _dynamic_atexit_destructor_for__g_csLog__

- ea: `0x180022c60`
- end: `0x180022c89`
- name: `_dynamic_atexit_destructor_for__g_csLog__`
- size: `41`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180022c60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180022c74`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180022c74`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_csLog__()
{
  if ( dword_18002FBC8 )
  {
    DeleteCriticalSection(&g_csLog);
    dword_18002FBC8 = 0;
  }
}

```

## disassembly

```asm
0x180022c60  sub     rsp, 28h
0x180022c64  cmp     cs:dword_18002FBC8, 0
0x180022c6b  jz      short loc_180022C84
0x180022c6d  lea     rcx, ?g_csLog@@3V?$CWin32CriticalSectionT@VCEmptyType@@@@A; lpCriticalSection
0x180022c74  call    cs:__imp_DeleteCriticalSection
0x180022c7a  mov     cs:dword_18002FBC8, 0
0x180022c84  add     rsp, 28h
0x180022c88  retn
```
