# ATL::CComCachedTearOffObject<CImpIRowsetUpdate>::~CComCachedTearOffObject<CImpIRowsetUpdate>(void)

- ea: `0x18000a418`
- end: `0x18000a434`
- name: `??1?$CComCachedTearOffObject@VCImpIRowsetUpdate@@@ATL@@QEAA@XZ`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000a8b8`

## import_xrefs

- `MSDART!MPDeleteCriticalSection` at `0x18000a42d`

## pseudocode

```c
__int64 __fastcall ATL::CComCachedTearOffObject<CImpIRowsetUpdate>::~CComCachedTearOffObject<CImpIRowsetUpdate>(
        __int64 a1)
{
  *(_DWORD *)(a1 + 8) = 1;
  *(_QWORD *)a1 = &ATL::CComCachedTearOffObject<CImpIRowsetUpdate>::`vftable';
  return MPDeleteCriticalSection(a1 + 40);
}

```

## disassembly

```asm
0x18000a418  lea     rax, ??_7?$CComCachedTearOffObject@VCImpIRowsetUpdate@@@ATL@@6B@; const ATL::CComCachedTearOffObject<CImpIRowsetUpdate>::`vftable'
0x18000a41f  mov     dword ptr [rcx+8], 1
0x18000a426  mov     [rcx], rax
0x18000a429  add     rcx, 28h ; '('
0x18000a42d  jmp     cs:__imp_MPDeleteCriticalSection
```
