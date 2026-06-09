# ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)

- ea: `0x180002170`
- end: `0x180002192`
- name: `??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ`
- size: `34`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800023ec`
- `0x180002ae0`
- `0x1800135d8`

## callees

- `0x180002170`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180002182`
- `KERNEL32!LeaveCriticalSection` at `0x180002182`

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
0x180002170  push    rbx
0x180002172  sub     rsp, 20h
0x180002176  cmp     byte ptr [rcx+8], 0
0x18000217a  mov     rbx, rcx
0x18000217d  jz      short loc_18000218C
0x18000217f  mov     rcx, [rcx]; lpCriticalSection
0x180002182  call    cs:__imp_LeaveCriticalSection
0x180002188  mov     byte ptr [rbx+8], 0
0x18000218c  add     rsp, 20h
0x180002190  pop     rbx
0x180002191  retn
```
