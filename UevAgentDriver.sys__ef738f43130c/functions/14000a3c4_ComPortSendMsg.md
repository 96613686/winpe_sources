# ComPortSendMsg

- ea: `0x14000a3c4`
- end: `0x14000a555`
- name: `ComPortSendMsg`
- size: `401`
- prototype: `__int64 __fastcall(PVOID SenderBuffer, __int64, void *, ULONG *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000aca0`

## callees

- `0x140001118`
- `0x140001168`
- `0x1400011b0`
- `0x14000a3c4`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000a446`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000a50f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000bbc4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000a446`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000a50f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000bbc4`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000a43a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000a503`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000bbb8`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000a43a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000a503`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000bbb8`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000a414`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000a4a2`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000bb56`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000a414`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000a4a2`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000bb56`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000a3ff`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000a48d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000bb41`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000a3ff`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000a48d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000bb41`
- `FLTMGR!FltSendMessage` at `0x14000a47f`
- `FLTMGR!FltSendMessage` at `0x14000a47f`
- `FLTMGR!FltCloseClientPort` at `0x14000a4de`
- `FLTMGR!FltCloseClientPort` at `0x14000bb8a`
- `FLTMGR!FltCloseClientPort` at `0x14000a4de`
- `FLTMGR!FltCloseClientPort` at `0x14000bb8a`

## string_xrefs

- `0x14000a4bf`: `UevFilter.ComPort: Closing client port\n`
- `0x14000bb6b`: `UevFilter.ComPort: Closing client port\n`
- `0x14000a3dc`: `UevFilter.ComPortSendMsg: Entry\n`
- `0x14000a51d`: `UevFilter.ComPortSendMsg: Invalid parameter specified\n`
- `0x14000a531`: `UevFilter.ComPortSendMsg: Exit, retStatus = 0x%X\n`

## pseudocode

```c
__int64 __fastcall ComPortSendMsg(PVOID SenderBuffer, __int64 a2, void *a3, ULONG *a4)
{
  unsigned int v7; // ebx

  DbgTrace(2, "UevFilter.ComPortSendMsg: Entry\n");
  if ( SenderBuffer && a3 )
  {
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite(&comPortResource, 1u);
    if ( clientPortConnected )
    {
      ++clientPortRefCount;
      ExReleaseResourceLite(&comPortResource);
      KeLeaveCriticalRegion();
      v7 = FltSendMessage(g_pFilter, &pClientPort, SenderBuffer, 8u, a3, a4, pSendMsgTimeout);
      KeEnterCriticalRegion();
      ExAcquireResourceExclusiveLite(&comPortResource, 1u);
      if ( !--clientPortRefCount )
      {
        DbgTrace(2, "UevFilter.ComPort: Closing client port\n");
        FltCloseClientPort(g_pFilter, &pClientPort);
        pClientPort = 0;
      }
    }
    else
    {
      v7 = -1073741769;
    }
    ExReleaseResourceLite(&comPortResource);
    KeLeaveCriticalRegion();
  }
  else
  {
    DbgTraceErr("UevFilter.ComPortSendMsg: Invalid parameter specified\n");
    v7 = -1073741811;
  }
  DbgTraceFrmt(2, "UevFilter.ComPortSendMsg: Exit, retStatus = 0x%X\n", v7);
  return v7;
}

```

## disassembly

```asm
0x14000a3c4  mov     [rsp+arg_0], rbx
0x14000a3c9  mov     [rsp+arg_10], rsi
0x14000a3ce  push    rdi
0x14000a3cf  sub     rsp, 40h
0x14000a3d3  mov     rsi, r9
0x14000a3d6  mov     rbx, r8
0x14000a3d9  mov     rdi, rcx
0x14000a3dc  lea     rdx, aUevfilterCompo_5; "UevFilter.ComPortSendMsg: Entry\n"
0x14000a3e3  mov     ecx, 2
0x14000a3e8  call    DbgTrace
0x14000a3ed  test    rdi, rdi
0x14000a3f0  jz      loc_14000A51D
0x14000a3f6  test    rbx, rbx
0x14000a3f9  jz      loc_14000A51D
0x14000a3ff  call    cs:__imp_KeEnterCriticalRegion
0x14000a406  nop     dword ptr [rax+rax+00h]
0x14000a40b  mov     dl, 1; Wait
0x14000a40d  lea     rcx, comPortResource; Resource
0x14000a414  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14000a41b  nop     dword ptr [rax+rax+00h]
0x14000a420  cmp     cs:clientPortConnected, 0
0x14000a427  jz      loc_14000A4F7
0x14000a42d  inc     cs:clientPortRefCount
0x14000a433  lea     rcx, comPortResource; Resource
0x14000a43a  call    cs:__imp_ExReleaseResourceLite
0x14000a441  nop     dword ptr [rax+rax+00h]
0x14000a446  call    cs:__imp_KeLeaveCriticalRegion
0x14000a44d  nop     dword ptr [rax+rax+00h]
0x14000a452  mov     rax, cs:pSendMsgTimeout
0x14000a459  mov     [rsp+48h+Timeout], rax; Timeout
0x14000a45e  mov     [rsp+48h+ReplyLength], rsi; ReplyLength
0x14000a463  mov     [rsp+48h+ReplyBuffer], rbx; ReplyBuffer
0x14000a468  mov     r9d, 8; SenderBufferLength
0x14000a46e  mov     r8, rdi; SenderBuffer
0x14000a471  lea     rdx, pClientPort; ClientPort
0x14000a478  mov     rcx, cs:g_pFilter; Filter
0x14000a47f  call    cs:__imp_FltSendMessage
0x14000a486  nop     dword ptr [rax+rax+00h]
0x14000a48b  mov     ebx, eax
0x14000a48d  call    cs:__imp_KeEnterCriticalRegion
0x14000a494  nop     dword ptr [rax+rax+00h]
0x14000a499  mov     dl, 1; Wait
0x14000a49b  lea     rcx, comPortResource; Resource
0x14000a4a2  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14000a4a9  nop     dword ptr [rax+rax+00h]
0x14000a4ae  mov     ecx, cs:clientPortRefCount
0x14000a4b4  add     ecx, 0FFFFFFFFh
0x14000a4b7  mov     cs:clientPortRefCount, ecx
0x14000a4bd  jnz     short loc_14000A4FC
0x14000a4bf  lea     rdx, aUevfilterCompo_6; "UevFilter.ComPort: Closing client port"...
0x14000a4c6  mov     ecx, 2
0x14000a4cb  call    DbgTrace
0x14000a4d0  lea     rdx, pClientPort; ClientPort
0x14000a4d7  mov     rcx, cs:g_pFilter; Filter
0x14000a4de  call    cs:__imp_FltCloseClientPort
0x14000a4e5  nop     dword ptr [rax+rax+00h]
0x14000a4ea  mov     cs:pClientPort, 0
0x14000a4f5  jmp     short loc_14000A4FC
0x14000a4f7  mov     ebx, 0C0000037h
0x14000a4fc  lea     rcx, comPortResource; Resource
0x14000a503  call    cs:__imp_ExReleaseResourceLite
0x14000a50a  nop     dword ptr [rax+rax+00h]
0x14000a50f  call    cs:__imp_KeLeaveCriticalRegion
0x14000a516  nop     dword ptr [rax+rax+00h]
0x14000a51b  jmp     short loc_14000A52E
0x14000a51d  lea     rcx, aUevfilterCompo_10; "UevFilter.ComPortSendMsg: Invalid param"...
0x14000a524  call    DbgTraceErr
0x14000a529  mov     ebx, 0C000000Dh
0x14000a52e  mov     r8d, ebx
0x14000a531  lea     rdx, aUevfilterCompo_3; "UevFilter.ComPortSendMsg: Exit, retStat"...
0x14000a538  mov     ecx, 2
0x14000a53d  call    DbgTraceFrmt
0x14000a542  mov     eax, ebx
0x14000a544  mov     rbx, [rsp+48h+arg_0]
0x14000a549  mov     rsi, [rsp+48h+arg_10]
0x14000a54e  add     rsp, 40h
0x14000a552  pop     rdi
0x14000a553  retn
0x14000bb38  push    rbp
0x14000bb3a  sub     rsp, 40h
0x14000bb3e  mov     rbp, rdx
0x14000bb41  call    cs:__imp_KeEnterCriticalRegion
0x14000bb48  nop     dword ptr [rax+rax+00h]
0x14000bb4d  mov     dl, 1; Wait
0x14000bb4f  lea     rcx, comPortResource; Resource
0x14000bb56  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14000bb5d  nop     dword ptr [rax+rax+00h]
0x14000bb62  add     cs:clientPortRefCount, 0FFFFFFFFh
0x14000bb69  jnz     short loc_14000BBA1
0x14000bb6b  lea     rdx, aUevfilterCompo_6; "UevFilter.ComPort: Closing client port"...
0x14000bb72  mov     ecx, 2
0x14000bb77  call    DbgTrace
0x14000bb7c  lea     rdx, pClientPort; ClientPort
0x14000bb83  mov     rcx, cs:g_pFilter; Filter
0x14000bb8a  call    cs:__imp_FltCloseClientPort
0x14000bb91  nop     dword ptr [rax+rax+00h]
0x14000bb96  mov     cs:pClientPort, 0
0x14000bba1  add     rsp, 40h
0x14000bba5  pop     rbp
0x14000bba6  retn
0x14000bba8  push    rbp
0x14000bbaa  sub     rsp, 40h
0x14000bbae  mov     rbp, rdx
0x14000bbb1  lea     rcx, comPortResource; Resource
0x14000bbb8  call    cs:__imp_ExReleaseResourceLite
0x14000bbbf  nop     dword ptr [rax+rax+00h]
0x14000bbc4  call    cs:__imp_KeLeaveCriticalRegion
0x14000bbcb  nop     dword ptr [rax+rax+00h]
0x14000bbd0  nop
0x14000bbd1  add     rsp, 40h
0x14000bbd5  pop     rbp
0x14000bbd6  retn
```
