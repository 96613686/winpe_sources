# IkeStartReceivingPackets

- ea: `0x180071c0c`
- end: `0x180071c8d`
- name: `IkeStartReceivingPackets`
- size: `129`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180054bf4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180071c28`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180071c46`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180071c64`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180071c28`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180071c46`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180071c64`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180071c86`

## pseudocode

```c
void IkeStartReceivingPackets()
{
  SetThreadpoolWait((PTP_WAIT)gIkeExtGlobals[82].DebugInfo, gIkeExtGlobals[72].LockSemaphore, 0);
  SetThreadpoolWait(*(PTP_WAIT *)&gIkeExtGlobals[82].LockCount, (HANDLE)gIkeExtGlobals[72].SpinCount, 0);
  SetThreadpoolWait((PTP_WAIT)gIkeExtGlobals[82].OwningThread, gIkeExtGlobals[73].DebugInfo, 0);
  SetThreadpoolWait((PTP_WAIT)gIkeExtGlobals[82].LockSemaphore, *(HANDLE *)&gIkeExtGlobals[73].LockCount, 0);
}

```

## disassembly

```asm
0x180071c0c  sub     rsp, 28h
0x180071c10  mov     rcx, cs:gIkeExtGlobals
0x180071c17  xor     r8d, r8d; pftTimeout
0x180071c1a  mov     rdx, [rcx+0B58h]; h
0x180071c21  mov     rcx, [rcx+0CD0h]; pwa
0x180071c28  call    cs:__imp_SetThreadpoolWait
0x180071c2e  mov     rcx, cs:gIkeExtGlobals
0x180071c35  xor     r8d, r8d; pftTimeout
0x180071c38  mov     rdx, [rcx+0B60h]; h
0x180071c3f  mov     rcx, [rcx+0CD8h]; pwa
0x180071c46  call    cs:__imp_SetThreadpoolWait
0x180071c4c  mov     rcx, cs:gIkeExtGlobals
0x180071c53  xor     r8d, r8d; pftTimeout
0x180071c56  mov     rdx, [rcx+0B68h]; h
0x180071c5d  mov     rcx, [rcx+0CE0h]; pwa
0x180071c64  call    cs:__imp_SetThreadpoolWait
0x180071c6a  mov     rcx, cs:gIkeExtGlobals
0x180071c71  xor     r8d, r8d
0x180071c74  mov     rdx, [rcx+0B70h]
0x180071c7b  mov     rcx, [rcx+0CE8h]
0x180071c82  add     rsp, 28h
0x180071c86  jmp     cs:__imp_SetThreadpoolWait
```
