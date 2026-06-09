# _dynamic_atexit_destructor_for__g_wpnUserService__

- ea: `0x1800112c0`
- end: `0x180011300`
- name: `_dynamic_atexit_destructor_for__g_wpnUserService__`
- size: `64`
- prototype: `void()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800112c0`
- `0x180012010`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_wpnUserService__()
{
  if ( !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    ((void (__fastcall *)(void *, _QWORD))*g_wpnUserService)(&g_wpnUserService, 0);
  }
}

```

## disassembly

```asm
0x1800112c0  sub     rsp, 28h
0x1800112c4  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800112cb  jnz     short loc_1800112FB
0x1800112cd  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800112d4  test    rax, rax
0x1800112d7  jz      short loc_1800112E2
0x1800112d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800112de  test    al, al
0x1800112e0  jnz     short loc_1800112FB
0x1800112e2  mov     rax, cs:?g_wpnUserService@@3V?$object_without_destructor_on_shutdown@VWpnUserService@@@wil@@A; wil::object_without_destructor_on_shutdown<WpnUserService> g_wpnUserService
0x1800112e9  xor     edx, edx
0x1800112eb  lea     rcx, ?g_wpnUserService@@3V?$object_without_destructor_on_shutdown@VWpnUserService@@@wil@@A; wil::object_without_destructor_on_shutdown<WpnUserService> g_wpnUserService
0x1800112f2  mov     rax, [rax]
0x1800112f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800112fa  nop
0x1800112fb  add     rsp, 28h
0x1800112ff  retn
```
