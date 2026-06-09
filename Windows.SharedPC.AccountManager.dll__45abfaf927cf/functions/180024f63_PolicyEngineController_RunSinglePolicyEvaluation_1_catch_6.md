# _PolicyEngineController::RunSinglePolicyEvaluation_::_1_::catch$6

- ea: `0x180024f63`
- end: `0x180024f9c`
- name: `_PolicyEngineController::RunSinglePolicyEvaluation_::_1_::catch$6`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000c210`

## string_xrefs

- `0x180024f77`: `shellcommon\shell\sharedpc\accountmanager\lib\policy\policyenginecontroller.cpp`

## pseudocode

```c
__int64 __fastcall PolicyEngineController::RunSinglePolicyEvaluation_::_1_::catch_6(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 456),
                           (void *)0x52,
                           (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\policy\\policyenginecontroller.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180024f63  mov     [rsp+arg_8], rdx
0x180024f68  push    rbp
0x180024f69  sub     rsp, 30h
0x180024f6d  mov     rbp, rdx
0x180024f70  mov     rcx, [rbp+1C8h]; this
0x180024f77  lea     r8, aShellcommonShe_3; "shellcommon\\shell\\sharedpc\\accountma"...
0x180024f7e  mov     edx, 52h ; 'R'; void *
0x180024f83  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180024f88  mov     [rbp+30h], eax
0x180024f8b  mov     rax, 0
0x180024f95  add     rsp, 30h
0x180024f99  pop     rbp
0x180024f9a  retn
```
