# _GetAllAppUriHandlerRegistrationsAsHostnameAndPackageFamilyName_::_1_::catch$43

- ea: `0x1400116f2`
- end: `0x140011722`
- name: `_GetAllAppUriHandlerRegistrationsAsHostnameAndPackageFamilyName_::_1_::catch$43`
- size: `48`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000d588`

## pseudocode

```c
__int64 __fastcall GetAllAppUriHandlerRegistrationsAsHostnameAndPackageFamilyName_::_1_::catch_43(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(*(wil::details::in1diag3 **)(a2 + 280), (void *)0x120, a3, a4);
  return 0;
}

```

## disassembly

```asm
0x1400116f2  mov     [rsp+arg_8], rdx
0x1400116f7  push    rbp
0x1400116f8  sub     rsp, 30h
0x1400116fc  mov     rbp, rdx
0x1400116ff  mov     rcx, [rbp+118h]; this
0x140011706  mov     edx, 120h; void *
0x14001170b  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x140011710  nop
0x140011711  mov     rax, 0
0x14001171b  add     rsp, 30h
0x14001171f  pop     rbp
0x140011720  retn
```
