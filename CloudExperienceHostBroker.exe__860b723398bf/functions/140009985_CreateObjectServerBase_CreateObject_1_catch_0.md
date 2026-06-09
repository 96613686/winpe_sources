# _CreateObjectServerBase::CreateObject_::_1_::catch$0

- ea: `0x140009985`
- end: `0x1400099af`
- name: `_CreateObjectServerBase::CreateObject_::_1_::catch$0`
- size: `42`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140008924`

## pseudocode

```c
__int64 __fastcall CreateObjectServerBase::CreateObject_::_1_::catch_0(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 64) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 56),
                           (void *)a2,
                           a3,
                           a4);
  return 0;
}

```

## disassembly

```asm
0x140009985  mov     [rsp+arg_8], rdx
0x14000998a  push    rbp
0x14000998b  sub     rsp, 30h
0x14000998f  mov     rbp, rdx
0x140009992  mov     rcx, [rbp+38h]; this
0x140009996  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x14000999b  mov     [rbp+40h], eax
0x14000999e  mov     rax, 0
0x1400099a8  add     rsp, 30h
0x1400099ac  pop     rbp
0x1400099ad  retn
```
