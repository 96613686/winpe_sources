# _dynamic_atexit_destructor_for__s_CallerId__

- ea: `0x180045850`
- end: `0x180045871`
- name: `_dynamic_atexit_destructor_for__s_CallerId__`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004585b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004585b`

## pseudocode

```c
HRESULT dynamic_atexit_destructor_for__s_CallerId__()
{
  HRESULT result; // eax

  result = WindowsDeleteString(string);
  string = 0;
  return result;
}

```

## disassembly

```asm
0x180045850  sub     rsp, 28h
0x180045854  mov     rcx, cs:string; string
0x18004585b  call    cs:__imp_WindowsDeleteString
0x180045861  mov     cs:string, 0
0x18004586c  add     rsp, 28h
0x180045870  retn
```
