# CBroadcastConfigManager::NotifyBroadcastConfigChange(void)

- ea: `0x180064090`
- end: `0x1800640d8`
- name: `?NotifyBroadcastConfigChange@CBroadcastConfigManager@@QEAAJXZ`
- size: `72`
- prototype: `__int64 __fastcall(CBroadcastConfigManager *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180036650`
- `0x1800385ac`
- `0x1800648f4`

## callees

- `0x180051420`
- `0x180064090`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800640a6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800640a6`

## string_xrefs

- `0x1800640c2`: `CBroadcastConfigManager::NotifyBroadcastConfigChange`
- `0x1800640b0`: `NotifyBroadcastConfigChange called with m_hNotifyEvent == NULL.`

## pseudocode

```c
__int64 __fastcall CBroadcastConfigManager::NotifyBroadcastConfigChange(CBroadcastConfigManager *this)
{
  void *v2; // rcx

  v2 = (void *)*((_QWORD *)this + 2);
  if ( v2 && *((_DWORD *)this + 2) )
  {
    SetEvent(v2);
    return 0;
  }
  else
  {
    LogSmsRouterError(
      "CBroadcastConfigManager::NotifyBroadcastConfigChange",
      0x9Au,
      -2147024875,
      "NotifyBroadcastConfigChange called with m_hNotifyEvent == NULL.");
    return 2147942421LL;
  }
}

```

## disassembly

```asm
0x180064090  sub     rsp, 28h
0x180064094  mov     rax, rcx
0x180064097  mov     rcx, [rcx+10h]; hEvent
0x18006409b  test    rcx, rcx
0x18006409e  jz      short loc_1800640B0
0x1800640a0  cmp     dword ptr [rax+8], 0
0x1800640a4  jz      short loc_1800640B0
0x1800640a6  call    cs:__imp_SetEvent
0x1800640ac  xor     eax, eax
0x1800640ae  jmp     short loc_1800640D3
0x1800640b0  lea     r9, aNotifybroadcas; "NotifyBroadcastConfigChange called with"...
0x1800640b7  mov     edx, 9Ah; unsigned int
0x1800640bc  mov     r8d, 80070015h; int
0x1800640c2  lea     rcx, aCbroadcastconf_2; "CBroadcastConfigManager::NotifyBroadcas"...
0x1800640c9  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x1800640ce  mov     eax, 80070015h
0x1800640d3  add     rsp, 28h
0x1800640d7  retn
```
