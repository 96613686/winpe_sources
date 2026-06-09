# _CopyINetFwRule_::_1_::catch$85

- ea: `0x18002bf18`
- end: `0x18002bf54`
- name: `_CopyINetFwRule_::_1_::catch$85`
- size: `60`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18002917c`

## string_xrefs

- `0x18002bf2c`: `shellcommon\shell\networkux\firewallux\lib\utils.cpp`

## pseudocode

```c
__int64 __fastcall CopyINetFwRule_::_1_::catch_85(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 320) = wil::details::in1diag3::Return_CaughtException(
                            *(wil::details::in1diag3 **)(a2 + 312),
                            (void *)0x23A,
                            (unsigned int)"shellcommon\\shell\\networkux\\firewallux\\lib\\utils.cpp",
                            a4);
  return 0;
}

```

## disassembly

```asm
0x18002bf18  mov     [rsp+arg_8], rdx
0x18002bf1d  push    rbp
0x18002bf1e  sub     rsp, 20h
0x18002bf22  mov     rbp, rdx
0x18002bf25  mov     rcx, [rbp+138h]; this
0x18002bf2c  lea     r8, aShellcommonShe_0; "shellcommon\\shell\\networkux\\firewall"...
0x18002bf33  mov     edx, 23Ah; void *
0x18002bf38  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18002bf3d  mov     [rbp+140h], eax
0x18002bf43  mov     rax, 0
0x18002bf4d  add     rsp, 20h
0x18002bf51  pop     rbp
0x18002bf52  retn
```
