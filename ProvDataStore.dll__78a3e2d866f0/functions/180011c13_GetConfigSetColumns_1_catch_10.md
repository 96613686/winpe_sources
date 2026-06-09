# _GetConfigSetColumns_::_1_::catch$10

- ea: `0x180011c13`
- end: `0x180011c37`
- name: `_GetConfigSetColumns_::_1_::catch$10`
- size: `36`
- prototype: `__int64 __fastcall(wil *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000f2b0`

## pseudocode

```c
__int64 __fastcall GetConfigSetColumns_::_1_::catch_10(wil *a1)
{
  wil::ResultFromCaughtException(a1);
  return 0;
}

```

## disassembly

```asm
0x180011c13  mov     [rsp+arg_8], rdx
0x180011c18  push    rbp
0x180011c19  sub     rsp, 30h
0x180011c1d  mov     rbp, rdx
0x180011c20  call    ?ResultFromCaughtException@wil@@YAJXZ; wil::ResultFromCaughtException(void)
0x180011c25  nop
0x180011c26  mov     rax, 0
0x180011c30  add     rsp, 30h
0x180011c34  pop     rbp
0x180011c35  retn
```
