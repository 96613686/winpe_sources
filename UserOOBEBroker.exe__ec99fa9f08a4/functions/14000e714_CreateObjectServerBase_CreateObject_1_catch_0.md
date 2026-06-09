# _CreateObjectServerBase::CreateObject_::_1_::catch$0

- ea: `0x14000e714`
- end: `0x14000e73e`
- name: `_CreateObjectServerBase::CreateObject_::_1_::catch$0`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x14000c914`

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
0x14000e714  mov     [rsp+arg_8], rdx
0x14000e719  push    rbp
0x14000e71a  sub     rsp, 30h
0x14000e71e  mov     rbp, rdx
0x14000e721  mov     rcx, [rbp+38h]; this
0x14000e725  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x14000e72a  mov     [rbp+40h], eax
0x14000e72d  mov     rax, 0
0x14000e737  add     rsp, 30h
0x14000e73b  pop     rbp
0x14000e73c  retn
```
