# CRegistryPropertyStore::~CRegistryPropertyStore(void)

- ea: `0x1800395a4`
- end: `0x1800395e5`
- name: `??1CRegistryPropertyStore@@MEAA@XZ`
- size: `65`
- prototype: `void __fastcall(CRegistryPropertyStore *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180062790`

## callees

- `0x1800395a4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800395ca`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800395ca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800395d9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800395d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800395c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800395c0`

## pseudocode

```c
void __fastcall CRegistryPropertyStore::~CRegistryPropertyStore(CRegistryPropertyStore *this)
{
  void *v2; // rcx
  HKEY v3; // rcx

  *(_QWORD *)this = &CRegistryPropertyStore::`vftable';
  v2 = (void *)*((_QWORD *)this + 8);
  if ( v2 )
    CoTaskMemFree(v2);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v3 = (HKEY)*((_QWORD *)this + 1);
  if ( v3 )
    RegCloseKey(v3);
}

```

## disassembly

```asm
0x1800395a4  push    rbx
0x1800395a6  sub     rsp, 20h
0x1800395aa  lea     rax, ??_7CRegistryPropertyStore@@6B@; const CRegistryPropertyStore::`vftable'
0x1800395b1  mov     rbx, rcx
0x1800395b4  mov     [rcx], rax
0x1800395b7  mov     rcx, [rcx+40h]; pv
0x1800395bb  test    rcx, rcx
0x1800395be  jz      short loc_1800395C6
0x1800395c0  call    cs:__imp_CoTaskMemFree
0x1800395c6  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800395ca  call    cs:__imp_DeleteCriticalSection
0x1800395d0  mov     rcx, [rbx+8]; hKey
0x1800395d4  test    rcx, rcx
0x1800395d7  jz      short loc_1800395DF
0x1800395d9  call    cs:__imp_RegCloseKey
0x1800395df  add     rsp, 20h
0x1800395e3  pop     rbx
0x1800395e4  retn
```
