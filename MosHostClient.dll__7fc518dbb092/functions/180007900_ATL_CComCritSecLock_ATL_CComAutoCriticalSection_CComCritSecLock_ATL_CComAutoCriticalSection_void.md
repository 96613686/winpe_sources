# ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>(void)

- ea: `0x180007900`
- end: `0x180007922`
- name: `??1?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(__int64)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180011247`
- `0x180011402`
- `0x1800114f9`
- `0x180011595`
- `0x180011628`

## callees

- `0x180007900`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007912`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007912`

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
0x180007900  push    rbx
0x180007902  sub     rsp, 20h
0x180007906  cmp     byte ptr [rcx+8], 0
0x18000790a  mov     rbx, rcx
0x18000790d  jz      short loc_18000791C
0x18000790f  mov     rcx, [rcx]; lpCriticalSection
0x180007912  call    cs:__imp_LeaveCriticalSection
0x180007918  mov     byte ptr [rbx+8], 0
0x18000791c  add     rsp, 20h
0x180007920  pop     rbx
0x180007921  retn
```
