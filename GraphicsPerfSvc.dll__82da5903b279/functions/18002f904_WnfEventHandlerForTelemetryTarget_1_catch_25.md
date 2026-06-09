# _WnfEventHandlerForTelemetryTarget_::_1_::catch$25

- ea: `0x18002f904`
- end: `0x18002f942`
- name: `_WnfEventHandlerForTelemetryTarget_::_1_::catch$25`
- size: `62`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18000f840`

## string_xrefs

- `0x18002f91f`: `onecoreuap\windows\directx\dxg\gpm\service\service.cpp`

## pseudocode

```c
__int64 __fastcall WnfEventHandlerForTelemetryTarget_::_1_::catch_25(__int64 a1, __int64 a2)
{
  const char *v3; // [rsp+20h] [rbp-58h]

  wil::details::in1diag3::Log_CaughtExceptionMsg(
    *(wil::details::in1diag3 **)(a2 + 1256),
    (void *)0x105,
    (unsigned int)"onecoreuap\\windows\\directx\\dxg\\gpm\\service\\service.cpp",
    "Exception thrown while adding Present Consumer.",
    v3);
  return 0;
}

```

## disassembly

```asm
0x18002f904  mov     [rsp+arg_8], rdx
0x18002f909  push    rbp
0x18002f90a  sub     rsp, 70h
0x18002f90e  mov     rbp, rdx
0x18002f911  mov     rcx, [rbp+4E8h]; this
0x18002f918  lea     r9, aExceptionThrow_1; "Exception thrown while adding Present C"...
0x18002f91f  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\directx\\dxg\\gpm"...
0x18002f926  mov     edx, 105h; void *
0x18002f92b  call    ?Log_CaughtExceptionMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Log_CaughtExceptionMsg(void *,uint,char const *,char const *,...)
0x18002f930  nop
0x18002f931  mov     rax, 0
0x18002f93b  add     rsp, 70h
0x18002f93f  pop     rbp
0x18002f940  retn
```
