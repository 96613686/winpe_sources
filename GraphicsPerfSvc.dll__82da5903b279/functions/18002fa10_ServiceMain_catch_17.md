# ServiceMain$catch$17

- ea: `0x18002fa10`
- end: `0x18002fa4e`
- name: `ServiceMain$catch$17`
- size: `62`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000f840`

## string_xrefs

- `0x18002fa2b`: `onecoreuap\windows\directx\dxg\gpm\service\service.cpp`
- `0x18002fa24`: `Exception thrown while configuring service at startup.`

## pseudocode

```c
__int64 __fastcall ServiceMain_catch_17(__int64 a1, __int64 a2)
{
  const char *v3; // [rsp+20h] [rbp-48h]

  wil::details::in1diag3::Log_CaughtExceptionMsg(
    *(wil::details::in1diag3 **)(a2 + 360),
    (void *)0x1D7,
    (unsigned int)"onecoreuap\\windows\\directx\\dxg\\gpm\\service\\service.cpp",
    "Exception thrown while configuring service at startup.",
    v3);
  return 0;
}

```

## disassembly

```asm
0x18002fa10  mov     [rsp+arg_8], rdx
0x18002fa15  push    rbp
0x18002fa16  sub     rsp, 60h
0x18002fa1a  mov     rbp, rdx
0x18002fa1d  mov     rcx, [rbp+168h]; this
0x18002fa24  lea     r9, aExceptionThrow_0; "Exception thrown while configuring serv"...
0x18002fa2b  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\directx\\dxg\\gpm"...
0x18002fa32  mov     edx, 1D7h; void *
0x18002fa37  call    ?Log_CaughtExceptionMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Log_CaughtExceptionMsg(void *,uint,char const *,char const *,...)
0x18002fa3c  nop
0x18002fa3d  mov     rax, 0
0x18002fa47  add     rsp, 60h
0x18002fa4b  pop     rbp
0x18002fa4c  retn
```
