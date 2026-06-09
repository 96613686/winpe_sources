# ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>(void)

- ea: `0x180009d80`
- end: `0x180009d9d`
- name: `??1?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ`
- size: `29`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180034268`

## callees

- `0x180009d80`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180009d92`
- `KERNEL32!DeleteCriticalSection` at `0x180009d92`

## pseudocode

```c
void __fastcall ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>(
        __int64 a1)
{
  __int64 v1; // rcx

  v1 = a1 + 8;
  if ( *(_BYTE *)(v1 + 40) )
  {
    *(_BYTE *)(v1 + 40) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)v1);
  }
}

```

## disassembly

```asm
0x180009d80  sub     rsp, 28h
0x180009d84  add     rcx, 8; lpCriticalSection
0x180009d88  cmp     byte ptr [rcx+28h], 0
0x180009d8c  jz      short loc_180009D98
0x180009d8e  mov     byte ptr [rcx+28h], 0
0x180009d92  call    cs:__imp_DeleteCriticalSection
0x180009d98  add     rsp, 28h
0x180009d9c  retn
```
