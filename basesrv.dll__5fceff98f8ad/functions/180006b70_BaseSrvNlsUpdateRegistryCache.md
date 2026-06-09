# BaseSrvNlsUpdateRegistryCache

- ea: `0x180006b70`
- end: `0x180006c24`
- name: `BaseSrvNlsUpdateRegistryCache`
- size: `180`
- prototype: `void __stdcall(PVOID ApcContext, PIO_STATUS_BLOCK IoStatusBlock, ULONG Reserved)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x180006b70`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x180006b7b`
- `ntdll!RtlEnterCriticalSection` at `0x180006b7b`
- `ntdll!RtlLeaveCriticalSection` at `0x180006be5`
- `ntdll!RtlLeaveCriticalSection` at `0x180006c16`
- `ntdll!RtlLeaveCriticalSection` at `0x180006be5`
- `ntdll!RtlLeaveCriticalSection` at `0x180006c16`
- `ntdll!NtNotifyChangeKey` at `0x180006bd2`
- `ntdll!NtNotifyChangeKey` at `0x180006bd2`

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
0x180006b70  sub     rsp, 58h
0x180006b74  lea     rcx, NlsCacheCriticalSection; CriticalSection
0x180006b7b  call    cs:__imp_RtlEnterCriticalSection
0x180006b82  nop     dword ptr [rax+rax+00h]
0x180006b87  mov     rcx, cs:hCPanelIntlKeyRead; KeyHandle
0x180006b8e  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180006b92  jz      short loc_180006C0F
0x180006b94  mov     [rsp+58h+WatchSubtree], 1; WatchSubtree
0x180006b99  lea     rax, NlsChangeBuffer
0x180006ba0  mov     [rsp+58h+Length], 4; Length
0x180006ba8  lea     r8, BaseSrvNlsUpdateRegistryCache; ApcRoutine
0x180006baf  mov     [rsp+58h+ChangeBuffer], rax; ChangeBuffer
0x180006bb4  xor     r9d, r9d; ApcContext
0x180006bb7  mov     [rsp+58h+Asynchroneous], 0; Asynchroneous
0x180006bbc  lea     rax, IoStatusBlock
0x180006bc3  mov     [rsp+58h+CompletionFilter], 5; CompletionFilter
0x180006bcb  xor     edx, edx; Event
0x180006bcd  mov     [rsp+58h+IoStatusBlock], rax; IoStatusBlock
0x180006bd2  call    cs:__imp_NtNotifyChangeKey
0x180006bd9  nop     dword ptr [rax+rax+00h]
0x180006bde  lea     rcx, NlsCacheCriticalSection; CriticalSection
0x180006be5  call    cs:__imp_RtlLeaveCriticalSection
0x180006bec  nop     dword ptr [rax+rax+00h]
0x180006bf1  mov     rax, cs:pNlsRegUserInfo
0x180006bf8  mov     cs:bCacheDirty, 1
0x180006c02  lock inc dword ptr [rax+678h]
0x180006c09  add     rsp, 58h
0x180006c0d  retn
0x180006c0f  lea     rcx, NlsCacheCriticalSection; CriticalSection
0x180006c16  call    cs:__imp_RtlLeaveCriticalSection
0x180006c1d  nop     dword ptr [rax+rax+00h]
0x180006c22  jmp     short loc_180006C09
```
