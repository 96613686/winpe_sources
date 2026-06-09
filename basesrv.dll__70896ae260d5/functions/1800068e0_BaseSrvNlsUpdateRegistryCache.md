# BaseSrvNlsUpdateRegistryCache

- ea: `0x1800068e0`
- end: `0x180006994`
- name: `BaseSrvNlsUpdateRegistryCache`
- size: `180`
- prototype: `void __fastcall(PVOID ApcContext, PIO_STATUS_BLOCK IoStatusBlock, ULONG Reserved)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x1800068e0`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x1800068eb`
- `ntdll!RtlEnterCriticalSection` at `0x1800068eb`
- `ntdll!RtlLeaveCriticalSection` at `0x180006955`
- `ntdll!RtlLeaveCriticalSection` at `0x180006986`
- `ntdll!RtlLeaveCriticalSection` at `0x180006955`
- `ntdll!RtlLeaveCriticalSection` at `0x180006986`
- `ntdll!NtNotifyChangeKey` at `0x180006942`
- `ntdll!NtNotifyChangeKey` at `0x180006942`

## pseudocode

```c
void __fastcall BaseSrvNlsUpdateRegistryCache(PVOID ApcContext, PIO_STATUS_BLOCK IoStatusBlock, ULONG Reserved)
{
  RtlEnterCriticalSection(&NlsCacheCriticalSection);
  if ( hCPanelIntlKeyRead == (HANDLE)-1LL )
  {
    RtlLeaveCriticalSection(&NlsCacheCriticalSection);
  }
  else
  {
    NtNotifyChangeKey(
      hCPanelIntlKeyRead,
      0,
      BaseSrvNlsUpdateRegistryCache,
      0,
      &::IoStatusBlock,
      5u,
      0,
      NlsChangeBuffer,
      4u,
      1u);
    RtlLeaveCriticalSection(&NlsCacheCriticalSection);
    bCacheDirty = 1;
    _InterlockedIncrement((volatile signed __int32 *)pNlsRegUserInfo + 414);
  }
}

```

## disassembly

```asm
0x1800068e0  sub     rsp, 58h
0x1800068e4  lea     rcx, NlsCacheCriticalSection; CriticalSection
0x1800068eb  call    cs:__imp_RtlEnterCriticalSection
0x1800068f2  nop     dword ptr [rax+rax+00h]
0x1800068f7  mov     rcx, cs:hCPanelIntlKeyRead; KeyHandle
0x1800068fe  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180006902  jz      short loc_18000697F
0x180006904  mov     [rsp+58h+WatchSubtree], 1; WatchSubtree
0x180006909  lea     rax, NlsChangeBuffer
0x180006910  mov     [rsp+58h+Length], 4; Length
0x180006918  lea     r8, BaseSrvNlsUpdateRegistryCache; ApcRoutine
0x18000691f  mov     [rsp+58h+ChangeBuffer], rax; ChangeBuffer
0x180006924  xor     r9d, r9d; ApcContext
0x180006927  mov     [rsp+58h+Asynchroneous], 0; Asynchroneous
0x18000692c  lea     rax, IoStatusBlock
0x180006933  mov     [rsp+58h+CompletionFilter], 5; CompletionFilter
0x18000693b  xor     edx, edx; Event
0x18000693d  mov     [rsp+58h+IoStatusBlock], rax; IoStatusBlock
0x180006942  call    cs:__imp_NtNotifyChangeKey
0x180006949  nop     dword ptr [rax+rax+00h]
0x18000694e  lea     rcx, NlsCacheCriticalSection; CriticalSection
0x180006955  call    cs:__imp_RtlLeaveCriticalSection
0x18000695c  nop     dword ptr [rax+rax+00h]
0x180006961  mov     rax, cs:pNlsRegUserInfo
0x180006968  mov     cs:bCacheDirty, 1
0x180006972  lock inc dword ptr [rax+678h]
0x180006979  add     rsp, 58h
0x18000697d  retn
0x18000697f  lea     rcx, NlsCacheCriticalSection; CriticalSection
0x180006986  call    cs:__imp_RtlLeaveCriticalSection
0x18000698d  nop     dword ptr [rax+rax+00h]
0x180006992  jmp     short loc_180006979
```
