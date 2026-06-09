# ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>(void)

- ea: `0x18000e6a0`
- end: `0x18000e6c2`
- name: `??1?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(__int64)`
- caller_count: `10`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000ea5c`
- `0x18000ec18`
- `0x18000ec6c`
- `0x18000ed40`
- `0x180010780`
- `0x18001b690`
- `0x18001cc50`
- `0x180023698`
- `0x180023716`
- `0x180023def`

## callees

- `0x18000e6a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e6b2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e6b2`

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
0x18000e6a0  push    rbx
0x18000e6a2  sub     rsp, 20h
0x18000e6a6  cmp     byte ptr [rcx+8], 0
0x18000e6aa  mov     rbx, rcx
0x18000e6ad  jz      short loc_18000E6BC
0x18000e6af  mov     rcx, [rcx]; lpCriticalSection
0x18000e6b2  call    cs:__imp_LeaveCriticalSection
0x18000e6b8  mov     byte ptr [rbx+8], 0
0x18000e6bc  add     rsp, 20h
0x18000e6c0  pop     rbx
0x18000e6c1  retn
```
