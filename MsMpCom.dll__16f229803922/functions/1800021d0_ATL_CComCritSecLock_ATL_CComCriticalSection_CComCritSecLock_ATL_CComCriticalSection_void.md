# ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)

- ea: `0x1800021d0`
- end: `0x1800021f2`
- name: `??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ`
- size: `34`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000990d`

## callees

- `0x1800021d0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800021e2`
- `KERNEL32!LeaveCriticalSection` at `0x1800021e2`

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
0x1800021d0  push    rbx
0x1800021d2  sub     rsp, 20h
0x1800021d6  cmp     byte ptr [rcx+8], 0
0x1800021da  mov     rbx, rcx
0x1800021dd  jz      short loc_1800021EC
0x1800021df  mov     rcx, [rcx]; lpCriticalSection
0x1800021e2  call    cs:__imp_LeaveCriticalSection
0x1800021e8  mov     byte ptr [rbx+8], 0
0x1800021ec  add     rsp, 20h
0x1800021f0  pop     rbx
0x1800021f1  retn
```
