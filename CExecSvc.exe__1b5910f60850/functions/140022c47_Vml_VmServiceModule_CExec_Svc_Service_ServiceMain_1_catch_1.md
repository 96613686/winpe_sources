# _Vml::VmServiceModule_CExec::Svc::Service_::ServiceMain_::_1_::catch$1

- ea: `0x140022c47`
- end: `0x140022c7d`
- name: `_Vml::VmServiceModule_CExec::Svc::Service_::ServiceMain_::_1_::catch$1`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400109d0`

## string_xrefs

- `0x140022c58`: `onecore\vm\common\vml\VmModules.h`

## pseudocode

```c
__int64 __fastcall Vml::VmServiceModule_CExec::Svc::Service_::ServiceMain_::_1_::catch_1(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 80) = wil::details::in1diag3::Log_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 56),
                           (void *)0xC61,
                           (unsigned int)"onecore\\vm\\common\\vml\\VmModules.h",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x140022c47  mov     [rsp+arg_8], rdx
0x140022c4c  push    rbp
0x140022c4d  sub     rsp, 20h
0x140022c51  mov     rbp, rdx
0x140022c54  mov     rcx, [rbp+38h]; this
0x140022c58  lea     r8, aOnecoreVmCommo; "onecore\\vm\\common\\vml\\VmModules.h"
0x140022c5f  mov     edx, 0C61h; void *
0x140022c64  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x140022c69  mov     [rbp+50h], eax
0x140022c6c  mov     rax, 0
0x140022c76  add     rsp, 20h
0x140022c7a  pop     rbp
0x140022c7b  retn
```
