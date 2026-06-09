# _MaxUserPolicyEngine::RunPolicyEvaluation_::_1_::catch$5

- ea: `0x1800251bd`
- end: `0x1800251f6`
- name: `_MaxUserPolicyEngine::RunPolicyEvaluation_::_1_::catch$5`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000c210`

## string_xrefs

- `0x1800251d1`: `shellcommon\shell\sharedpc\accountmanager\lib\policy\maxuserpolicyengine.cpp`

## pseudocode

```c
__int64 __fastcall MaxUserPolicyEngine::RunPolicyEvaluation_::_1_::catch_5(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 32) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 488),
                           (void *)0x47,
                           (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\policy\\maxuserpolicyengine.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x1800251bd  mov     [rsp+arg_8], rdx
0x1800251c2  push    rbp
0x1800251c3  sub     rsp, 20h
0x1800251c7  mov     rbp, rdx
0x1800251ca  mov     rcx, [rbp+1E8h]; this
0x1800251d1  lea     r8, aShellcommonShe_19; "shellcommon\\shell\\sharedpc\\accountma"...
0x1800251d8  mov     edx, 47h ; 'G'; void *
0x1800251dd  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800251e2  mov     [rbp+20h], eax
0x1800251e5  mov     rax, 0
0x1800251ef  add     rsp, 20h
0x1800251f3  pop     rbp
0x1800251f4  retn
```
