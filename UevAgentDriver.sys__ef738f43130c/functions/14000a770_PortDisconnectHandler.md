# PortDisconnectHandler

- ea: `0x14000a770`
- end: `0x14000a843`
- name: `PortDisconnectHandler`
- size: `211`
- prototype: `void __fastcall(PFLT_PORT ConnectionCookie)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140001118`
- `0x14000a770`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000a81f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000bc26`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000a81f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000bc26`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000a813`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000bc1a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000a813`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000bc1a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000a7a0`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000a7a0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000a78b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000a78b`
- `FLTMGR!FltCloseClientPort` at `0x14000a7f5`
- `FLTMGR!FltCloseClientPort` at `0x14000a7f5`

## string_xrefs

- `0x14000a7d6`: `UevFilter.ComPort: Closing client port\n`

## pseudocode

```c
void __fastcall PortDisconnectHandler(PFLT_PORT ConnectionCookie)
{
  DbgTrace(2, "UevFilter.PortDisconnectHandler: Entry\n");
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite(&comPortResource, 1u);
  if ( clientPortConnected )
  {
    if ( pClientPort == ConnectionCookie )
    {
      clientPortConnected = 0;
      if ( !--clientPortRefCount )
      {
        DbgTrace(2, "UevFilter.ComPort: Closing client port\n");
        FltCloseClientPort(g_pFilter, &pClientPort);
        pClientPort = 0;
      }
    }
  }
  ExReleaseResourceLite(&comPortResource);
  KeLeaveCriticalRegion();
  DbgTrace(2, "UevFilter.PortDisconnectHandler: Exit\n");
}

```

## disassembly

```asm
0x14000a770  push    rbx
0x14000a772  sub     rsp, 20h
0x14000a776  mov     rbx, rcx
0x14000a779  lea     rdx, aUevfilterPortd; "UevFilter.PortDisconnectHandler: Entry"...
0x14000a780  mov     ecx, 2
0x14000a785  call    DbgTrace
0x14000a78a  nop
0x14000a78b  call    cs:__imp_KeEnterCriticalRegion
0x14000a792  nop     dword ptr [rax+rax+00h]
0x14000a797  mov     dl, 1; Wait
0x14000a799  lea     rcx, comPortResource; Resource
0x14000a7a0  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14000a7a7  nop     dword ptr [rax+rax+00h]
0x14000a7ac  cmp     cs:clientPortConnected, 0
0x14000a7b3  jz      short loc_14000A80C
0x14000a7b5  cmp     cs:pClientPort, rbx
0x14000a7bc  jnz     short loc_14000A80C
0x14000a7be  mov     cs:clientPortConnected, 0
0x14000a7c5  mov     eax, cs:clientPortRefCount
0x14000a7cb  add     eax, 0FFFFFFFFh
0x14000a7ce  mov     cs:clientPortRefCount, eax
0x14000a7d4  jnz     short loc_14000A80C
0x14000a7d6  lea     rdx, aUevfilterCompo_6; "UevFilter.ComPort: Closing client port"...
0x14000a7dd  mov     ecx, 2
0x14000a7e2  call    DbgTrace
0x14000a7e7  lea     rdx, pClientPort; ClientPort
0x14000a7ee  mov     rcx, cs:g_pFilter; Filter
0x14000a7f5  call    cs:__imp_FltCloseClientPort
0x14000a7fc  nop     dword ptr [rax+rax+00h]
0x14000a801  mov     cs:pClientPort, 0
0x14000a80c  lea     rcx, comPortResource; Resource
0x14000a813  call    cs:__imp_ExReleaseResourceLite
0x14000a81a  nop     dword ptr [rax+rax+00h]
0x14000a81f  call    cs:__imp_KeLeaveCriticalRegion
0x14000a826  nop     dword ptr [rax+rax+00h]
0x14000a82b  lea     rdx, aUevfilterPortd_0; "UevFilter.PortDisconnectHandler: Exit\n"
0x14000a832  mov     ecx, 2
0x14000a837  call    DbgTrace
0x14000a83c  add     rsp, 20h
0x14000a840  pop     rbx
0x14000a841  retn
0x14000bc0a  push    rbp
0x14000bc0c  sub     rsp, 20h
0x14000bc10  mov     rbp, rdx
0x14000bc13  lea     rcx, comPortResource; Resource
0x14000bc1a  call    cs:__imp_ExReleaseResourceLite
0x14000bc21  nop     dword ptr [rax+rax+00h]
0x14000bc26  call    cs:__imp_KeLeaveCriticalRegion
0x14000bc2d  nop     dword ptr [rax+rax+00h]
0x14000bc32  nop
0x14000bc33  add     rsp, 20h
0x14000bc37  pop     rbp
0x14000bc38  retn
```
