# ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)

- ea: `0x18000a8f4`
- end: `0x18000a916`
- name: `??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001789f`

## callees

- `0x18000a8f4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a906`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a906`

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
0x18000a8f4  push    rbx
0x18000a8f6  sub     rsp, 20h
0x18000a8fa  cmp     byte ptr [rcx+8], 0
0x18000a8fe  mov     rbx, rcx
0x18000a901  jz      short loc_18000A910
0x18000a903  mov     rcx, [rcx]; lpCriticalSection
0x18000a906  call    cs:__imp_LeaveCriticalSection
0x18000a90c  mov     byte ptr [rbx+8], 0
0x18000a910  add     rsp, 20h
0x18000a914  pop     rbx
0x18000a915  retn
```
