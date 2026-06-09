# CRegistryChangeListener::~CRegistryChangeListener(void)

- ea: `0x1800090dc`
- end: `0x18000913e`
- name: `??1CRegistryChangeListener@@AEAA@XZ`
- size: `98`
- prototype: `void __fastcall(CRegistryChangeListener *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180009320`

## callees

- `0x1800090dc`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009103`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009103`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000912b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000912b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009112`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009112`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180009121`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180009121`

## pseudocode

```c
void __fastcall CRegistryChangeListener::~CRegistryChangeListener(CRegistryChangeListener *this)
{
  void *v2; // rcx
  HKEY v3; // rcx
  struct _TP_WORK *v4; // rcx

  *(_QWORD *)this = &CRegistryChangeListener::`vftable'{for `IOleCommandTarget'};
  *((_QWORD *)this + 1) = &CRegistryChangeListener::`vftable'{for `IRegistryChangeListener'};
  v2 = (void *)*((_QWORD *)this + 3);
  if ( v2 )
    CloseHandle(v2);
  v3 = (HKEY)*((_QWORD *)this + 4);
  if ( v3 )
    RegCloseKey(v3);
  v4 = (struct _TP_WORK *)*((_QWORD *)this + 8);
  if ( v4 )
    CloseThreadpoolWork(v4);
  CoTaskMemFree(*((LPVOID *)this + 10));
  _InterlockedDecrement((volatile signed __int32 *)&g_cLocks);
}

```

## disassembly

```asm
0x1800090dc  push    rbx
0x1800090de  sub     rsp, 20h
0x1800090e2  lea     rax, ??_7CRegistryChangeListener@@6BIOleCommandTarget@@@; const CRegistryChangeListener::`vftable'{for `IOleCommandTarget'}
0x1800090e9  mov     rbx, rcx
0x1800090ec  mov     [rcx], rax
0x1800090ef  lea     rax, ??_7CRegistryChangeListener@@6BIRegistryChangeListener@@@; const CRegistryChangeListener::`vftable'{for `IRegistryChangeListener'}
0x1800090f6  mov     [rcx+8], rax
0x1800090fa  mov     rcx, [rcx+18h]; hObject
0x1800090fe  test    rcx, rcx
0x180009101  jz      short loc_180009109
0x180009103  call    cs:__imp_CloseHandle
0x180009109  mov     rcx, [rbx+20h]; hKey
0x18000910d  test    rcx, rcx
0x180009110  jz      short loc_180009118
0x180009112  call    cs:__imp_RegCloseKey
0x180009118  mov     rcx, [rbx+40h]; pwk
0x18000911c  test    rcx, rcx
0x18000911f  jz      short loc_180009127
0x180009121  call    cs:__imp_CloseThreadpoolWork
0x180009127  mov     rcx, [rbx+50h]; pv
0x18000912b  call    cs:__imp_CoTaskMemFree
0x180009131  lock dec cs:?g_cLocks@@3KA; ulong g_cLocks
0x180009138  add     rsp, 20h
0x18000913c  pop     rbx
0x18000913d  retn
```
