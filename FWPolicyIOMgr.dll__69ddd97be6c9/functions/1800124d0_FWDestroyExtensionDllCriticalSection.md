# FWDestroyExtensionDllCriticalSection

- ea: `0x1800124d0`
- end: `0x180012519`
- name: `FWDestroyExtensionDllCriticalSection`
- size: `73`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001193c`

## callees

- `0x1800124d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800124e4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180012504`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800124e4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180012504`

## pseudocode

```c
void FWDestroyExtensionDllCriticalSection()
{
  if ( dword_1800535A8 )
  {
    DeleteCriticalSection(&g_fwExtensionDllLock);
    dword_1800535A8 = 0;
  }
  if ( dword_180053568 )
  {
    DeleteCriticalSection(&g_gpLockEventCriticalSection);
    dword_180053568 = 0;
  }
}

```

## disassembly

```asm
0x1800124d0  sub     rsp, 28h
0x1800124d4  cmp     cs:dword_1800535A8, 0
0x1800124db  jz      short loc_1800124F4
0x1800124dd  lea     rcx, ?g_fwExtensionDllLock@@3UFW_CRITICAL_SECTION_@@A; lpCriticalSection
0x1800124e4  call    cs:__imp_DeleteCriticalSection
0x1800124ea  mov     cs:dword_1800535A8, 0
0x1800124f4  cmp     cs:dword_180053568, 0
0x1800124fb  jz      short loc_180012514
0x1800124fd  lea     rcx, ?g_gpLockEventCriticalSection@@3UFW_CRITICAL_SECTION_@@A; lpCriticalSection
0x180012504  call    cs:__imp_DeleteCriticalSection
0x18001250a  mov     cs:dword_180053568, 0
0x180012514  add     rsp, 28h
0x180012518  retn
```
