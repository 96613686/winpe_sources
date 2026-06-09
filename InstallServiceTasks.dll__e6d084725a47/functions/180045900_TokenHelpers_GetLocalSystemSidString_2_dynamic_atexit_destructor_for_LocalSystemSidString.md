# _TokenHelpers::GetLocalSystemSidString_::_2_::_dynamic_atexit_destructor_for__LocalSystemSidString__

- ea: `0x180045900`
- end: `0x180045921`
- name: `_TokenHelpers::GetLocalSystemSidString_::_2_::_dynamic_atexit_destructor_for__LocalSystemSidString__`
- size: `33`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004590b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004590b`

## pseudocode

```c
void __fastcall TokenHelpers::GetLocalSystemSidString_::_2_::_dynamic_atexit_destructor_for__LocalSystemSidString__()
{
  WindowsDeleteString(qword_1800840B8);
  qword_1800840B8 = 0;
}

```

## disassembly

```asm
0x180045900  sub     rsp, 28h
0x180045904  mov     rcx, cs:qword_1800840B8; string
0x18004590b  call    cs:__imp_WindowsDeleteString
0x180045911  mov     cs:qword_1800840B8, 0
0x18004591c  add     rsp, 28h
0x180045920  retn
```
