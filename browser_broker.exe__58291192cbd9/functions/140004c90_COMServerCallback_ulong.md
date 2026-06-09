# COMServerCallback(ulong)

- ea: `0x140004c90`
- end: `0x140004d09`
- name: `?COMServerCallback@@YAJK@Z`
- size: `121`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140004c90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140004cb8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140004cb8`

## pseudocode

```c
__int64 __fastcall COMServerCallback(int a1)
{
  unsigned int v1; // ebx
  int v2; // ecx

  v1 = -2147467259;
  v2 = a1 - 1;
  if ( v2 )
  {
    if ( v2 == 1 )
    {
      g_fMayExitProcess = 1;
      g_fForceServerExit = 1;
      SetEvent(g_hQuitEvent);
    }
  }
  else
  {
    v1 = 1;
    if ( !g_fForceServerExit && (g_fMultiUse || g_ServerRefCount > 0 || g_fNothingYetAllocated) )
    {
      g_fNothingYetAllocated = 0;
      _InterlockedIncrement(&g_ServerRefCount);
      return 0;
    }
  }
  return v1;
}

```

## disassembly

```asm
0x140004c90  push    rbx
0x140004c92  sub     rsp, 20h
0x140004c96  mov     ebx, 80004005h
0x140004c9b  sub     ecx, 1
0x140004c9e  jz      short loc_140004CC0
0x140004ca0  cmp     ecx, 1
0x140004ca3  jnz     short loc_140004D01
0x140004ca5  mov     cs:?g_fMayExitProcess@@3_NA, cl; bool g_fMayExitProcess
0x140004cab  mov     cs:?g_fForceServerExit@@3_NC, cl; bool volatile g_fForceServerExit
0x140004cb1  mov     rcx, cs:?g_hQuitEvent@@3PEAXEA; hEvent
0x140004cb8  call    cs:__imp_SetEvent
0x140004cbe  jmp     short loc_140004D01
0x140004cc0  mov     al, cs:?g_fForceServerExit@@3_NC; bool volatile g_fForceServerExit
0x140004cc6  mov     ebx, 1
0x140004ccb  test    al, al
0x140004ccd  jnz     short loc_140004D01
0x140004ccf  cmp     cs:?g_fMultiUse@@3_NA, al; bool g_fMultiUse
0x140004cd5  jnz     short loc_140004CEB
0x140004cd7  mov     eax, cs:?g_ServerRefCount@@3JC; long volatile g_ServerRefCount
0x140004cdd  test    eax, eax
0x140004cdf  jg      short loc_140004CEB
0x140004ce1  mov     al, cs:?g_fNothingYetAllocated@@3_NC; bool volatile g_fNothingYetAllocated
0x140004ce7  test    al, al
0x140004ce9  jz      short loc_140004D01
0x140004ceb  mov     cs:?g_fNothingYetAllocated@@3_NC, 0; bool volatile g_fNothingYetAllocated
0x140004cf2  lock inc cs:?g_ServerRefCount@@3JC; long volatile g_ServerRefCount
0x140004cf9  mov     eax, cs:?g_ServerRefCount@@3JC; long volatile g_ServerRefCount
0x140004cff  xor     ebx, ebx
0x140004d01  mov     eax, ebx
0x140004d03  add     rsp, 20h
0x140004d07  pop     rbx
0x140004d08  retn
```
