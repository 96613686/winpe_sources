# CheckForServerShutdown(void)

- ea: `0x140004d10`
- end: `0x140004d57`
- name: `?CheckForServerShutdown@@YAJXZ`
- size: `71`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140004d60`
- `0x140004fe0`
- `0x140005030`

## callees

- `0x140004d10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140004d48`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140004d48`

## pseudocode

```c
__int64 CheckForServerShutdown(void)
{
  unsigned int v0; // ecx

  v0 = 1;
  if ( g_fMayExitProcess && (g_ServerRefCount <= 0 || g_fForceServerExit) )
  {
    g_fForceServerExit = 1;
    if ( g_hQuitEvent )
      SetEvent(g_hQuitEvent);
    return 0;
  }
  return v0;
}

```

## disassembly

```asm
0x140004d10  sub     rsp, 28h
0x140004d14  cmp     cs:?g_fMayExitProcess@@3_NA, 0; bool g_fMayExitProcess
0x140004d1b  mov     ecx, 1
0x140004d20  jz      short loc_140004D50
0x140004d22  mov     eax, cs:?g_ServerRefCount@@3JC; long volatile g_ServerRefCount
0x140004d28  test    eax, eax
0x140004d2a  jle     short loc_140004D36
0x140004d2c  mov     al, cs:?g_fForceServerExit@@3_NC; bool volatile g_fForceServerExit
0x140004d32  test    al, al
0x140004d34  jz      short loc_140004D50
0x140004d36  mov     cs:?g_fForceServerExit@@3_NC, cl; bool volatile g_fForceServerExit
0x140004d3c  mov     rcx, cs:?g_hQuitEvent@@3PEAXEA; hEvent
0x140004d43  test    rcx, rcx
0x140004d46  jz      short loc_140004D4E
0x140004d48  call    cs:__imp_SetEvent
0x140004d4e  xor     ecx, ecx
0x140004d50  mov     eax, ecx
0x140004d52  add     rsp, 28h
0x140004d56  retn
```
