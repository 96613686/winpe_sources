# ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)

- ea: `0x18000238c`
- end: `0x1800023ae`
- name: `??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ`
- size: `34`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000bbc1`

## callees

- `0x18000238c`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000239e`
- `KERNEL32!LeaveCriticalSection` at `0x18000239e`

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
0x18000238c  push    rbx
0x18000238e  sub     rsp, 20h
0x180002392  cmp     byte ptr [rcx+8], 0
0x180002396  mov     rbx, rcx
0x180002399  jz      short loc_1800023A8
0x18000239b  mov     rcx, [rcx]; lpCriticalSection
0x18000239e  call    cs:__imp_LeaveCriticalSection
0x1800023a4  mov     byte ptr [rbx+8], 0
0x1800023a8  add     rsp, 20h
0x1800023ac  pop     rbx
0x1800023ad  retn
```
