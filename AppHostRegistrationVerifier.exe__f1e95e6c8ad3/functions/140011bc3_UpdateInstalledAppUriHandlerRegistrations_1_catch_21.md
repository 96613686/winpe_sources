# _UpdateInstalledAppUriHandlerRegistrations_::_1_::catch$21

- ea: `0x140011bc3`
- end: `0x140011bf3`
- name: `_UpdateInstalledAppUriHandlerRegistrations_::_1_::catch$21`
- size: `48`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x14000d588`

## pseudocode

```c
__int64 __fastcall UpdateInstalledAppUriHandlerRegistrations_::_1_::catch_21(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(*(wil::details::in1diag3 **)(a2 + 904), (void *)0x1AB, a3, a4);
  return 0;
}

```

## disassembly

```asm
0x140011bc3  mov     [rsp+arg_8], rdx
0x140011bc8  push    rbp
0x140011bc9  sub     rsp, 30h
0x140011bcd  mov     rbp, rdx
0x140011bd0  mov     rcx, [rbp+388h]; this
0x140011bd7  mov     edx, 1ABh; void *
0x140011bdc  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x140011be1  nop
0x140011be2  mov     rax, 0
0x140011bec  add     rsp, 30h
0x140011bf0  pop     rbp
0x140011bf1  retn
```
