# ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>(void)

- ea: `0x14000319c`
- end: `0x1400031be`
- name: `??1?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@XZ`
- size: `34`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140009884`

## callees

- `0x14000319c`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1400031ae`
- `KERNEL32!LeaveCriticalSection` at `0x1400031ae`

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
0x14000319c  push    rbx
0x14000319e  sub     rsp, 20h
0x1400031a2  cmp     byte ptr [rcx+8], 0
0x1400031a6  mov     rbx, rcx
0x1400031a9  jz      short loc_1400031B8
0x1400031ab  mov     rcx, [rcx]; lpCriticalSection
0x1400031ae  call    cs:__imp_LeaveCriticalSection
0x1400031b4  mov     byte ptr [rbx+8], 0
0x1400031b8  add     rsp, 20h
0x1400031bc  pop     rbx
0x1400031bd  retn
```
