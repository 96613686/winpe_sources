# _dynamic_atexit_destructor_for__gs_registryWatcher__

- ea: `0x18000bdf0`
- end: `0x18000be0a`
- name: `_dynamic_atexit_destructor_for__gs_registryWatcher__`
- size: `26`
- prototype: `void __fastcall(__int64, struct wil::details::registry_watcher_state *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180006e24`
- `0x18000bdf0`

## pseudocode

```c
void __fastcall dynamic_atexit_destructor_for__gs_registryWatcher__(
        __int64 a1,
        struct wil::details::registry_watcher_state *a2)
{
  if ( qword_180012C00 )
    wil::details::delete_registry_watcher_state(qword_180012C00, a2);
}

```

## disassembly

```asm
0x18000bdf0  sub     rsp, 28h
0x18000bdf4  mov     rcx, cs:qword_180012C00; this
0x18000bdfb  test    rcx, rcx
0x18000bdfe  jz      short loc_18000BE05
0x18000be00  call    ?delete_registry_watcher_state@details@wil@@YAXPEAUregistry_watcher_state@12@@Z; wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *)
0x18000be05  add     rsp, 28h
0x18000be09  retn
```
