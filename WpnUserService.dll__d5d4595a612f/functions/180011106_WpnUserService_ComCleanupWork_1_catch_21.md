# _WpnUserService::_ComCleanupWork_::_1_::catch$21

- ea: `0x180011106`
- end: `0x180011131`
- name: `_WpnUserService::_ComCleanupWork_::_1_::catch$21`
- size: `43`
- prototype: `__int64 __fastcall(__int64, wil::details::in1diag3 **, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180009b38`

## pseudocode

```c
__int64 __fastcall WpnUserService::_ComCleanupWork_::_1_::catch_21(
        __int64 a1,
        wil::details::in1diag3 **a2,
        unsigned int a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(a2[19], a2, a3, a4);
  return 0;
}

```

## disassembly

```asm
0x180011106  mov     [rsp+arg_8], rdx
0x18001110b  push    rbp
0x18001110c  sub     rsp, 40h
0x180011110  mov     rbp, rdx
0x180011113  mov     rcx, [rbp+98h]; this
0x18001111a  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x18001111f  nop
0x180011120  mov     rax, 0
0x18001112a  add     rsp, 40h
0x18001112e  pop     rbp
0x18001112f  retn
```
