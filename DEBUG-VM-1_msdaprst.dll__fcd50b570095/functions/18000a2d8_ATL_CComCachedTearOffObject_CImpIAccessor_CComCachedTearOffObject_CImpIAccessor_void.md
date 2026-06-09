# ATL::CComCachedTearOffObject<CImpIAccessor>::~CComCachedTearOffObject<CImpIAccessor>(void)

- ea: `0x18000a2d8`
- end: `0x18000a2f4`
- name: `??1?$CComCachedTearOffObject@VCImpIAccessor@@@ATL@@QEAA@XZ`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000a72c`

## import_xrefs

- `MSDART!MPDeleteCriticalSection` at `0x18000a2ed`

## pseudocode

```c
__int64 __fastcall ATL::CComCachedTearOffObject<CImpIAccessor>::~CComCachedTearOffObject<CImpIAccessor>(__int64 a1)
{
  *(_DWORD *)(a1 + 8) = 1;
  *(_QWORD *)a1 = &ATL::CComCachedTearOffObject<CImpIAccessor>::`vftable';
  return MPDeleteCriticalSection(a1 + 40);
}

```

## disassembly

```asm
0x18000a2d8  lea     rax, ??_7?$CComCachedTearOffObject@VCImpIAccessor@@@ATL@@6B@; const ATL::CComCachedTearOffObject<CImpIAccessor>::`vftable'
0x18000a2df  mov     dword ptr [rcx+8], 1
0x18000a2e6  mov     [rcx], rax
0x18000a2e9  add     rcx, 28h ; '('
0x18000a2ed  jmp     cs:__imp_MPDeleteCriticalSection
```
