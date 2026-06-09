# ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)

- ea: `0x180014204`
- end: `0x18001422d`
- name: `??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ`
- size: `41`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000d540`
- `0x1800155f8`
- `0x180015978`
- `0x1800177b4`
- `0x1800314b0`

## callees

- `0x180014204`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014216`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014216`

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
0x180014204  push    rbx
0x180014206  sub     rsp, 20h
0x18001420a  cmp     byte ptr [rcx+8], 0
0x18001420e  mov     rbx, rcx
0x180014211  jz      short loc_180014226
0x180014213  mov     rcx, [rcx]; lpCriticalSection
0x180014216  call    cs:__imp_LeaveCriticalSection
0x18001421d  nop     dword ptr [rax+rax+00h]
0x180014222  mov     byte ptr [rbx+8], 0
0x180014226  add     rsp, 20h
0x18001422a  pop     rbx
0x18001422b  retn
```
