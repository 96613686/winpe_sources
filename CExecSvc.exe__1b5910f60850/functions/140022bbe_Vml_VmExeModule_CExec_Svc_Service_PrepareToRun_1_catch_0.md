# _Vml::VmExeModule_CExec::Svc::Service_::PrepareToRun_::_1_::catch$0

- ea: `0x140022bbe`
- end: `0x140022be4`
- name: `_Vml::VmExeModule_CExec::Svc::Service_::PrepareToRun_::_1_::catch$0`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x140002ed8`
- `0x140010240`
- `0x140022bbe`

## pseudocode

```c
void __fastcall __noreturn Vml::VmExeModule_CExec::Svc::Service_::PrepareToRun_::_1_::catch_0(__int64 a1, __int64 a2)
{
  if ( *(_BYTE *)(a2 + 56) )
    CExec::Svc::Service::CleanUpFromRunSelf(*(HANDLE **)(a2 + 48));
  throw;
}

```

## disassembly

```asm
0x140022bbe  mov     [rsp+arg_8], rdx
0x140022bc3  push    rbp
0x140022bc4  sub     rsp, 20h
0x140022bc8  mov     rbp, rdx
0x140022bcb  cmp     byte ptr [rbp+38h], 0
0x140022bcf  jz      short loc_140022BDA
0x140022bd1  mov     rcx, [rbp+30h]; this
0x140022bd5  call    ?CleanUpFromRunSelf@Service@Svc@CExec@@QEAAXXZ; CExec::Svc::Service::CleanUpFromRunSelf(void)
0x140022bda  xor     edx, edx; pThrowInfo
0x140022bdc  xor     ecx, ecx; pExceptionObject
0x140022bde  call    _CxxThrowException_0
```
