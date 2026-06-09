# ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)

- ea: `0x180009ea0`
- end: `0x180009ec2`
- name: `??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000e6f5`

## callees

- `0x180009ea0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009eb2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009eb2`

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
0x180009ea0  push    rbx
0x180009ea2  sub     rsp, 20h
0x180009ea6  cmp     byte ptr [rcx+8], 0
0x180009eaa  mov     rbx, rcx
0x180009ead  jz      short loc_180009EBC
0x180009eaf  mov     rcx, [rcx]; lpCriticalSection
0x180009eb2  call    cs:__imp_LeaveCriticalSection
0x180009eb8  mov     byte ptr [rbx+8], 0
0x180009ebc  add     rsp, 20h
0x180009ec0  pop     rbx
0x180009ec1  retn
```
