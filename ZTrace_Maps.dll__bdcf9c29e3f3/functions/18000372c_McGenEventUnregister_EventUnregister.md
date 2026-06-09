# McGenEventUnregister_EventUnregister

- ea: `0x18000372c`
- end: `0x180003756`
- name: `McGenEventUnregister_EventUnregister`
- size: `42`
- prototype: `ULONG()`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002420`
- `0x180002490`

## callees

- `0x18000372c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180003740`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180003740`

## pseudocode

```c
ULONG McGenEventUnregister_EventUnregister()
{
  ULONG result; // eax

  if ( !MICROSOFT_WINDOWS_ZTRACEMAPS_Context )
    return 0;
  result = EventUnregister(MICROSOFT_WINDOWS_ZTRACEMAPS_Context);
  MICROSOFT_WINDOWS_ZTRACEMAPS_Context = 0;
  return result;
}

```

## disassembly

```asm
0x18000372c  sub     rsp, 28h
0x180003730  mov     rcx, cs:MICROSOFT_WINDOWS_ZTRACEMAPS_Context; RegHandle
0x180003737  test    rcx, rcx
0x18000373a  jnz     short loc_180003740
0x18000373c  xor     eax, eax
0x18000373e  jmp     short loc_180003751
0x180003740  call    cs:__imp_EventUnregister
0x180003746  mov     cs:MICROSOFT_WINDOWS_ZTRACEMAPS_Context, 0
0x180003751  add     rsp, 28h
0x180003755  retn
```
