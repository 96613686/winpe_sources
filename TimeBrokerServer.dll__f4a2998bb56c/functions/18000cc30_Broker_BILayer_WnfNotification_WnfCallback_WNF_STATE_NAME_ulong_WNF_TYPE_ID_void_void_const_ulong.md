# Broker::BILayer::WnfNotification::WnfCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)

- ea: `0x18000cc30`
- end: `0x18000cc90`
- name: `?WnfCallback@WnfNotification@BILayer@Broker@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z`
- size: `96`
- prototype: `__int64 __fastcall(struct _WNF_STATE_NAME, __int64, struct _WNF_TYPE_ID *, _DWORD *, const void *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000cc30`
- `0x18001164c`
- `0x18001c010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18000cc89`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18000cc89`

## pseudocode

```c
__int64 __fastcall Broker::BILayer::WnfNotification::WnfCallback(
        struct _WNF_STATE_NAME a1,
        __int64 a2,
        struct _WNF_TYPE_ID *a3,
        _DWORD *a4,
        const void *a5,
        unsigned int a6)
{
  __int64 v7; // rcx
  __int64 v9; // [rsp+48h] [rbp+20h] BYREF

  if ( a1.Data[0] != *a4 || (a1 = (struct _WNF_STATE_NAME)a1.Data[1], a1.Data[0] != a4[1]) )
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))MicrosoftTelemetryAssertTriggeredNoArgs)(a1, a2, a3);
  v7 = *((_QWORD *)a4 + 9);
  v9 = a6;
  if ( !v7 )
  {
    std::_Xbad_function_call();
    JUMPOUT(0x18000CC8FLL);
  }
  (*(void (__fastcall **)(__int64, __int64 *, const void **))(*(_QWORD *)v7 + 16LL))(v7, &v9, &a5);
  return 0;
}

```

## disassembly

```asm
0x18000cc30  push    rbx
0x18000cc32  sub     rsp, 20h
0x18000cc36  mov     rbx, r9
0x18000cc39  cmp     ecx, [r9]
0x18000cc3c  jnz     short loc_18000CC82
0x18000cc3e  shr     rcx, 20h
0x18000cc42  cmp     ecx, [r9+4]
0x18000cc46  jnz     short loc_18000CC82
0x18000cc48  mov     rax, [rsp+28h+arg_20]
0x18000cc4d  mov     rcx, [rbx+48h]
0x18000cc51  mov     [rsp+28h+arg_20], rax
0x18000cc56  mov     eax, [rsp+28h+arg_28]
0x18000cc5a  mov     [rsp+28h+arg_18], rax
0x18000cc5f  test    rcx, rcx
0x18000cc62  jz      short loc_18000CC89
0x18000cc64  mov     rax, [rcx]
0x18000cc67  lea     r8, [rsp+28h+arg_20]
0x18000cc6c  lea     rdx, [rsp+28h+arg_18]
0x18000cc71  mov     rax, [rax+10h]
0x18000cc75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc7a  xor     eax, eax
0x18000cc7c  add     rsp, 20h
0x18000cc80  pop     rbx
0x18000cc81  retn
0x18000cc82  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000cc87  jmp     short loc_18000CC48
0x18000cc89  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
```
