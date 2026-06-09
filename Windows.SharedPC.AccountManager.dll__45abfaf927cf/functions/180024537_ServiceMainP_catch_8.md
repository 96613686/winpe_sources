# ServiceMainP$catch$8

- ea: `0x180024537`
- end: `0x180024581`
- name: `ServiceMainP$catch$8`
- size: `74`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000fbe8`
- `0x18000fffc`
- `0x1800112ac`

## string_xrefs

- `0x18002454b`: `shellcommon\shell\sharedpc\accountmanager\lib\service\service.cpp`

## pseudocode

```c
__int64 __fastcall ServiceMainP_catch_8(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  wil *v4; // rcx
  int v5; // eax

  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 840),
    (void *)0xFD,
    (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\service\\service.cpp",
    a4);
  v5 = wil::ResultFromCaughtException(v4);
  ServiceState::StopServiceWithExitCode((ServiceState *)&g_serviceState, v5);
  return 0;
}

```

## disassembly

```asm
0x180024537  mov     [rsp+arg_8], rdx
0x18002453c  push    rbp
0x18002453d  sub     rsp, 40h
0x180024541  mov     rbp, rdx
0x180024544  mov     rcx, [rbp+348h]; this
0x18002454b  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\sharedpc\\accountma"...
0x180024552  mov     edx, 0FDh; void *
0x180024557  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x18002455c  call    ?ResultFromCaughtException@wil@@YAJXZ; wil::ResultFromCaughtException(void)
0x180024561  mov     edx, eax; int
0x180024563  lea     rcx, ?g_serviceState@@3VServiceState@@A; this
0x18002456a  call    ?StopServiceWithExitCode@ServiceState@@QEAAXJ@Z; ServiceState::StopServiceWithExitCode(long)
0x18002456f  nop
0x180024570  mov     rax, 0
0x18002457a  add     rsp, 40h
0x18002457e  pop     rbp
0x18002457f  retn
```
