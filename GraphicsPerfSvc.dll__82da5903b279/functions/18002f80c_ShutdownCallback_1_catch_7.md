# _ShutdownCallback_::_1_::catch$7

- ea: `0x18002f80c`
- end: `0x18002f84a`
- name: `_ShutdownCallback_::_1_::catch$7`
- size: `62`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18000f840`

## string_xrefs

- `0x18002f827`: `onecoreuap\windows\directx\dxg\gpm\service\service.cpp`

## pseudocode

```c
__int64 __fastcall ShutdownCallback_::_1_::catch_7(__int64 a1, __int64 a2)
{
  const char *v3; // [rsp+20h] [rbp-28h]

  wil::details::in1diag3::Log_CaughtExceptionMsg(
    *(wil::details::in1diag3 **)(a2 + 328),
    (void *)0x152,
    (unsigned int)"onecoreuap\\windows\\directx\\dxg\\gpm\\service\\service.cpp",
    "Exception thrown while shutting down MLSD",
    v3);
  return 0;
}

```

## disassembly

```asm
0x18002f80c  mov     [rsp+arg_8], rdx
0x18002f811  push    rbp
0x18002f812  sub     rsp, 40h
0x18002f816  mov     rbp, rdx
0x18002f819  mov     rcx, [rbp+148h]; this
0x18002f820  lea     r9, aExceptionThrow; "Exception thrown while shutting down ML"...
0x18002f827  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\directx\\dxg\\gpm"...
0x18002f82e  mov     edx, 152h; void *
0x18002f833  call    ?Log_CaughtExceptionMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Log_CaughtExceptionMsg(void *,uint,char const *,char const *,...)
0x18002f838  nop
0x18002f839  mov     rax, 0
0x18002f843  add     rsp, 40h
0x18002f847  pop     rbp
0x18002f848  retn
```
