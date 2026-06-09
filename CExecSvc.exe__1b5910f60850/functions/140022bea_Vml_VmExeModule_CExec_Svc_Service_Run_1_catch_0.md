# _Vml::VmExeModule_CExec::Svc::Service_::Run_::_1_::catch$0

- ea: `0x140022bea`
- end: `0x140022c11`
- name: `_Vml::VmExeModule_CExec::Svc::Service_::Run_::_1_::catch$0`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x140002ed8`
- `0x1400138a4`
- `0x140022bea`

## pseudocode

```c
void __fastcall __noreturn Vml::VmExeModule_CExec::Svc::Service_::Run_::_1_::catch_0(__int64 a1, __int64 a2)
{
  if ( *(_BYTE *)(a2 + 32) )
    Vml::VmServiceModule<CExec::Svc::Service>::CleanUpFromRun(*(_QWORD *)(a2 + 40));
  throw;
}

```

## disassembly

```asm
0x140022bea  mov     [rsp+arg_8], rdx
0x140022bef  push    rbp
0x140022bf0  sub     rsp, 20h
0x140022bf4  mov     rbp, rdx
0x140022bf7  mov     al, [rbp+20h]
0x140022bfa  test    al, al
0x140022bfc  jz      short loc_140022C07
0x140022bfe  mov     rcx, [rbp+28h]
0x140022c02  call    ?CleanUpFromRun@?$VmServiceModule@VService@Svc@CExec@@@Vml@@QEAAXXZ; Vml::VmServiceModule<CExec::Svc::Service>::CleanUpFromRun(void)
0x140022c07  xor     edx, edx; pThrowInfo
0x140022c09  xor     ecx, ecx; pExceptionObject
0x140022c0b  call    _CxxThrowException_0
```
