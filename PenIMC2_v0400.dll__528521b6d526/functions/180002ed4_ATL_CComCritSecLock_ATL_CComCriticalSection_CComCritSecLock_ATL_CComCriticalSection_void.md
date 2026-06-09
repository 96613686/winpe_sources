# ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)

- ea: `0x180002ed4`
- end: `0x180002ef6`
- name: `??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ`
- size: `34`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000e50e`

## callees

- `0x180002ed4`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180002ee6`
- `KERNEL32!LeaveCriticalSection` at `0x180002ee6`

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
0x180002ed4  push    rbx
0x180002ed6  sub     rsp, 20h
0x180002eda  cmp     byte ptr [rcx+8], 0
0x180002ede  mov     rbx, rcx
0x180002ee1  jz      short loc_180002EF0
0x180002ee3  mov     rcx, [rcx]; lpCriticalSection
0x180002ee6  call    cs:__imp_LeaveCriticalSection
0x180002eec  mov     byte ptr [rbx+8], 0
0x180002ef0  add     rsp, 20h
0x180002ef4  pop     rbx
0x180002ef5  retn
```
