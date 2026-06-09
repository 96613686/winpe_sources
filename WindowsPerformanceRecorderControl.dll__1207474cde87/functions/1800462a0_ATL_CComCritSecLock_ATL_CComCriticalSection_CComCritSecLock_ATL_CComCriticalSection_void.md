# ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)

- ea: `0x1800462a0`
- end: `0x1800462c2`
- name: `??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(__int64)`
- caller_count: `19`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180009a84`
- `0x18001cdd0`
- `0x180024de0`
- `0x180030c64`
- `0x180046048`
- `0x180051a28`
- `0x180052a20`
- `0x180056c80`
- `0x180059ab0`
- `0x18005c140`
- `0x18005d030`
- `0x18005d750`
- `0x180072350`
- `0x180072990`
- `0x18008386f`
- `0x180085a9c`
- `0x180086e53`
- `0x180087e38`
- `0x18008a3ff`

## callees

- `0x1800462a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800462b2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800462b2`

## pseudocode

```c
void __fastcall ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(__int64 a1)
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
0x1800462a0  push    rbx
0x1800462a2  sub     rsp, 20h
0x1800462a6  cmp     byte ptr [rcx+8], 0
0x1800462aa  mov     rbx, rcx
0x1800462ad  jz      short loc_1800462BC
0x1800462af  mov     rcx, [rcx]; lpCriticalSection
0x1800462b2  call    cs:__imp_LeaveCriticalSection
0x1800462b8  mov     byte ptr [rbx+8], 0
0x1800462bc  add     rsp, 20h
0x1800462c0  pop     rbx
0x1800462c1  retn
```
