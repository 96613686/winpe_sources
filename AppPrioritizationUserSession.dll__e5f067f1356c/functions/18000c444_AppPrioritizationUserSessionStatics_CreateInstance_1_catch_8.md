# _AppPrioritizationUserSessionStatics::CreateInstance_::_1_::catch$8

- ea: `0x18000c444`
- end: `0x18000c473`
- name: `_AppPrioritizationUserSessionStatics::CreateInstance_::_1_::catch$8`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000a9b0`

## pseudocode

```c
__int64 __fastcall AppPrioritizationUserSessionStatics::CreateInstance_::_1_::catch_8(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 104),
                           (void *)0x30,
                           a3,
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18000c444  mov     [rsp+arg_8], rdx
0x18000c449  push    rbp
0x18000c44a  sub     rsp, 30h
0x18000c44e  mov     rbp, rdx
0x18000c451  mov     rcx, [rbp+68h]; this
0x18000c455  mov     edx, 30h ; '0'; void *
0x18000c45a  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18000c45f  mov     [rbp+30h], eax
0x18000c462  mov     rax, 0
0x18000c46c  add     rsp, 30h
0x18000c470  pop     rbp
0x18000c471  retn
```
