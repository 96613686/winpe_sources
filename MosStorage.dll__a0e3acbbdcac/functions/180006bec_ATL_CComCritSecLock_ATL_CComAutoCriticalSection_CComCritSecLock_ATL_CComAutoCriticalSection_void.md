# ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>(void)

- ea: `0x180006bec`
- end: `0x180006c0e`
- name: `??1?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000ed34`

## callees

- `0x180006bec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006bfe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006bfe`

## pseudocode

```c
void __fastcall ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>(
        __int64 a1)
{
  if ( *(_BYTE *)(a1 + 8) )
  {
    LeaveCriticalSection(*(LPCRITICAL_SECTION *)a1);
    *(_BYTE *)(a1 + 8) = 0;
  }
}

```

## disassembly

```asm
0x180006bec  push    rbx
0x180006bee  sub     rsp, 20h
0x180006bf2  cmp     byte ptr [rcx+8], 0
0x180006bf6  mov     rbx, rcx
0x180006bf9  jz      short loc_180006C08
0x180006bfb  mov     rcx, [rcx]; lpCriticalSection
0x180006bfe  call    cs:__imp_LeaveCriticalSection
0x180006c04  mov     byte ptr [rbx+8], 0
0x180006c08  add     rsp, 20h
0x180006c0c  pop     rbx
0x180006c0d  retn
```
