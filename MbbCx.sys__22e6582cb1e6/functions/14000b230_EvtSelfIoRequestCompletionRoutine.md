# EvtSelfIoRequestCompletionRoutine

- ea: `0x14000b230`
- end: `0x14000b2a2`
- name: `EvtSelfIoRequestCompletionRoutine`
- size: `114`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140009104`
- `0x14000b230`
- `0x140047e90`

## pseudocode

```c
__int64 __fastcall EvtSelfIoRequestCompletionRoutine(__int64 a1, __int64 a2, __int64 a3)
{
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qd(
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      8,
      68,
      (__int64)WPP_87eee639879b3392f87380bbab0baecf_Traceguids,
      a1,
      *(_DWORD *)(a3 + 8));
  return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01031 + 1664))(WdfDriverGlobals, a1);
}

```

## disassembly

```asm
0x14000b230  push    rbx
0x14000b232  sub     rsp, 40h
0x14000b236  mov     rbx, rcx
0x14000b239  lea     rax, WPP_RECORDER_INITIALIZED
0x14000b240  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000b247  jz      short loc_14000B27E
0x14000b249  mov     eax, [r8+8]
0x14000b24d  mov     r9d, 44h ; 'D'
0x14000b253  mov     [rsp+48h+var_18], eax
0x14000b257  mov     dl, 4
0x14000b259  mov     [rsp+48h+var_20], rcx
0x14000b25e  lea     rax, WPP_87eee639879b3392f87380bbab0baecf_Traceguids
0x14000b265  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b26c  lea     r8d, [r9-3Ch]
0x14000b270  mov     [rsp+48h+var_28], rax
0x14000b275  mov     rcx, [rcx+40h]
0x14000b279  call    WPP_RECORDER_SF_qd
0x14000b27e  mov     rax, cs:WdfFunctions_01031
0x14000b285  mov     rdx, rbx
0x14000b288  mov     rcx, cs:WdfDriverGlobals
0x14000b28f  mov     rax, [rax+680h]
0x14000b296  call    _guard_dispatch_icall
0x14000b29b  add     rsp, 40h
0x14000b29f  pop     rbx
0x14000b2a0  retn
```
