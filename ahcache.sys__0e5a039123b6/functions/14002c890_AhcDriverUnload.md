# AhcDriverUnload

- ea: `0x14002c890`
- end: `0x14002c980`
- name: `AhcDriverUnload`
- size: `240`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `5`
- tags: `reparse_path`

## callees

- `0x140007854`
- `0x140028f9c`
- `0x14002a764`
- `0x14002c890`
- `0x14003e364`

## import_xrefs

- `ntoskrnl!PsGetPermanentSiloContext` at `0x14002c929`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14002c929`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14002c913`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14002c913`
- `ntoskrnl!PsUnregisterSiloMonitor` at `0x14002c95d`
- `ntoskrnl!PsUnregisterSiloMonitor` at `0x14002c95d`
- `ntoskrnl!IoDeleteDevice` at `0x14002c8dd`
- `ntoskrnl!IoDeleteDevice` at `0x14002c8dd`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14002c8ee`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14002c8ee`

## string_xrefs

- `0x14002c899`: `\DosDevices\ahcache`

## pseudocode

```c
__int64 AhcDriverUnload()
{
  __int64 v0; // r10
  unsigned int v2; // ebx
  __int64 CurrentServerSilo; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-18h] BYREF
  __int64 v5; // [rsp+48h] [rbp+10h] BYREF

  DestinationString = 0;
  if ( WdmlibRtlInitUnicodeStringEx(&DestinationString, L"\\DosDevices\\ahcache") < 0 )
    return AslLogCallPrintf(1, "AhcDriverUnload", 287, "Failed to initialize dos device name");
  IoDeleteDevice(*(PDEVICE_OBJECT *)(v0 + 8));
  IoDeleteSymbolicLink(&DestinationString);
  if ( g_AhcacheSiloMonitor )
  {
    v2 = g_AhcacheSiloContextSlot;
    v5 = 0;
    CurrentServerSilo = PsGetCurrentServerSilo();
    PsGetPermanentSiloContext(CurrentServerSilo, v2, &v5);
    if ( v5 )
    {
      if ( *(_DWORD *)(v5 + 96) )
      {
        AhcShutdown();
        *(_DWORD *)(v5 + 96) = 0;
      }
    }
    PsUnregisterSiloMonitor(g_AhcacheSiloMonitor);
    g_AhcacheSiloMonitor = 0;
  }
  return AhcTraceEnd();
}

```

## disassembly

```asm
0x14002c890  push    rbx
0x14002c892  sub     rsp, 30h
0x14002c896  mov     r10, rcx
0x14002c899  lea     rdx, aDosdevicesAhca; "\\DosDevices\\ahcache"
0x14002c8a0  xorps   xmm0, xmm0
0x14002c8a3  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x14002c8a8  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x14002c8ad  call    WdmlibRtlInitUnicodeStringEx
0x14002c8b2  test    eax, eax
0x14002c8b4  jns     short loc_14002C8D9
0x14002c8b6  lea     r9, aFailedToInitia_13; "Failed to initialize dos device name"
0x14002c8bd  mov     r8d, 11Fh
0x14002c8c3  lea     rdx, aAhcdriverunloa; "AhcDriverUnload"
0x14002c8ca  mov     ecx, 1
0x14002c8cf  call    AslLogCallPrintf
0x14002c8d4  jmp     loc_14002C979
0x14002c8d9  mov     rcx, [r10+8]; DeviceObject
0x14002c8dd  call    cs:__imp_IoDeleteDevice
0x14002c8e4  nop     dword ptr [rax+rax+00h]
0x14002c8e9  lea     rcx, [rsp+38h+DestinationString]; SymbolicLinkName
0x14002c8ee  call    cs:__imp_IoDeleteSymbolicLink
0x14002c8f5  nop     dword ptr [rax+rax+00h]
0x14002c8fa  cmp     cs:g_AhcacheSiloMonitor, 0
0x14002c902  jz      short loc_14002C974
0x14002c904  mov     ebx, cs:g_AhcacheSiloContextSlot
0x14002c90a  mov     [rsp+38h+arg_8], 0
0x14002c913  call    cs:__imp_PsGetCurrentServerSilo
0x14002c91a  nop     dword ptr [rax+rax+00h]
0x14002c91f  lea     r8, [rsp+38h+arg_8]
0x14002c924  mov     edx, ebx
0x14002c926  mov     rcx, rax
0x14002c929  call    cs:__imp_PsGetPermanentSiloContext
0x14002c930  nop     dword ptr [rax+rax+00h]
0x14002c935  mov     rcx, [rsp+38h+arg_8]
0x14002c93a  test    rcx, rcx
0x14002c93d  jz      short loc_14002C956
0x14002c93f  cmp     dword ptr [rcx+60h], 0
0x14002c943  jz      short loc_14002C956
0x14002c945  call    AhcShutdown
0x14002c94a  mov     rax, [rsp+38h+arg_8]
0x14002c94f  mov     dword ptr [rax+60h], 0
0x14002c956  mov     rcx, cs:g_AhcacheSiloMonitor
0x14002c95d  call    cs:__imp_PsUnregisterSiloMonitor
0x14002c964  nop     dword ptr [rax+rax+00h]
0x14002c969  mov     cs:g_AhcacheSiloMonitor, 0
0x14002c974  call    AhcTraceEnd
0x14002c979  add     rsp, 30h
0x14002c97d  pop     rbx
0x14002c97e  retn
```
