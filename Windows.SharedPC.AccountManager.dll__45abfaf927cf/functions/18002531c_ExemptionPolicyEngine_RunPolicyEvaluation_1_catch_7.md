# _ExemptionPolicyEngine::RunPolicyEvaluation_::_1_::catch$7

- ea: `0x18002531c`
- end: `0x180025353`
- name: `_ExemptionPolicyEngine::RunPolicyEvaluation_::_1_::catch$7`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000fbe8`

## string_xrefs

- `0x180025330`: `shellcommon\shell\sharedpc\accountmanager\lib\policy\exemptionpolicyengine.cpp`

## pseudocode

```c
__int64 __fastcall ExemptionPolicyEngine::RunPolicyEvaluation_::_1_::catch_7(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 488),
    (void *)0x18,
    (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\policy\\exemptionpolicyengine.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x18002531c  mov     [rsp+arg_8], rdx
0x180025321  push    rbp
0x180025322  sub     rsp, 20h
0x180025326  mov     rbp, rdx
0x180025329  mov     rcx, [rbp+1E8h]; this
0x180025330  lea     r8, aShellcommonShe_14; "shellcommon\\shell\\sharedpc\\accountma"...
0x180025337  mov     edx, 18h; void *
0x18002533c  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x180025341  nop
0x180025342  mov     rax, 0
0x18002534c  add     rsp, 20h
0x180025350  pop     rbp
0x180025351  retn
```
