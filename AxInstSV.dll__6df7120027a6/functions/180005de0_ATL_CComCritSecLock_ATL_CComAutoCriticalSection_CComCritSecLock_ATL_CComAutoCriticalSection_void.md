# ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>(void)

- ea: `0x180005de0`
- end: `0x180005e02`
- name: `??1?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(__int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180006a20`
- `0x180006c70`
- `0x180014810`

## callees

- `0x180005de0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005df2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005df2`

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
0x180005de0  push    rbx
0x180005de2  sub     rsp, 20h
0x180005de6  cmp     byte ptr [rcx+8], 0
0x180005dea  mov     rbx, rcx
0x180005ded  jz      short loc_180005DFC
0x180005def  mov     rcx, [rcx]; lpCriticalSection
0x180005df2  call    cs:__imp_LeaveCriticalSection
0x180005df8  mov     byte ptr [rbx+8], 0
0x180005dfc  add     rsp, 20h
0x180005e00  pop     rbx
0x180005e01  retn
```
