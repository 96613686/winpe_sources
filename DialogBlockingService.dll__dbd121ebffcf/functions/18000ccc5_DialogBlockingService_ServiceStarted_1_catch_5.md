# _DialogBlockingService::ServiceStarted_::_1_::catch$5

- ea: `0x18000ccc5`
- end: `0x18000ccef`
- name: `_DialogBlockingService::ServiceStarted_::_1_::catch$5`
- size: `42`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1800067c4`

## pseudocode

```c
__int64 __fastcall DialogBlockingService::ServiceStarted_::_1_::catch_5(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 56) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 40),
                           (void *)a2,
                           a3,
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18000ccc5  mov     [rsp+arg_8], rdx
0x18000ccca  push    rbp
0x18000cccb  sub     rsp, 20h
0x18000cccf  mov     rbp, rdx
0x18000ccd2  mov     rcx, [rbp+28h]; this
0x18000ccd6  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18000ccdb  mov     [rbp+38h], eax
0x18000ccde  mov     rax, 0
0x18000cce8  add     rsp, 20h
0x18000ccec  pop     rbp
0x18000cced  retn
```
