# ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)

- ea: `0x140003418`
- end: `0x14000343a`
- name: `??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(__int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140004e94`
- `0x1400069fc`
- `0x140015dce`

## callees

- `0x140003418`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x14000342a`
- `KERNEL32!LeaveCriticalSection` at `0x14000342a`

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
0x140003418  push    rbx
0x14000341a  sub     rsp, 20h
0x14000341e  cmp     byte ptr [rcx+8], 0
0x140003422  mov     rbx, rcx
0x140003425  jz      short loc_140003434
0x140003427  mov     rcx, [rcx]; lpCriticalSection
0x14000342a  call    cs:__imp_LeaveCriticalSection
0x140003430  mov     byte ptr [rbx+8], 0
0x140003434  add     rsp, 20h
0x140003438  pop     rbx
0x140003439  retn
```
