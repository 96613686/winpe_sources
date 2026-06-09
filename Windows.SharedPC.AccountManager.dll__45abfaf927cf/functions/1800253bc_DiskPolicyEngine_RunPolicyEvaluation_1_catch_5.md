# _DiskPolicyEngine::RunPolicyEvaluation_::_1_::catch$5

- ea: `0x1800253bc`
- end: `0x1800253f5`
- name: `_DiskPolicyEngine::RunPolicyEvaluation_::_1_::catch$5`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000c210`

## string_xrefs

- `0x1800253d0`: `shellcommon\shell\sharedpc\accountmanager\lib\policy\diskpolicyengine.cpp`

## pseudocode

```c
__int64 __fastcall DiskPolicyEngine::RunPolicyEvaluation_::_1_::catch_5(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 64) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 600),
                           (void *)0x64,
                           (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\policy\\diskpolicyengine.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x1800253bc  mov     [rsp+arg_8], rdx
0x1800253c1  push    rbp
0x1800253c2  sub     rsp, 40h
0x1800253c6  mov     rbp, rdx
0x1800253c9  mov     rcx, [rbp+258h]; this
0x1800253d0  lea     r8, aShellcommonShe_17; "shellcommon\\shell\\sharedpc\\accountma"...
0x1800253d7  mov     edx, 64h ; 'd'; void *
0x1800253dc  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800253e1  mov     [rbp+40h], eax
0x1800253e4  mov     rax, 0
0x1800253ee  add     rsp, 40h
0x1800253f2  pop     rbp
0x1800253f3  retn
```
