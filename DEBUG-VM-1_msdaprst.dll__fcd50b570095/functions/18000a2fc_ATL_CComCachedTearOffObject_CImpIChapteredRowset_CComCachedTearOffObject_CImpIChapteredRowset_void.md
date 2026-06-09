# ATL::CComCachedTearOffObject<CImpIChapteredRowset>::~CComCachedTearOffObject<CImpIChapteredRowset>(void)

- ea: `0x18000a2fc`
- end: `0x18000a318`
- name: `??1?$CComCachedTearOffObject@VCImpIChapteredRowset@@@ATL@@QEAA@XZ`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000a758`

## import_xrefs

- `MSDART!MPDeleteCriticalSection` at `0x18000a311`

## pseudocode

```c
__int64 __fastcall ATL::CComCachedTearOffObject<CImpIChapteredRowset>::~CComCachedTearOffObject<CImpIChapteredRowset>(
        __int64 a1)
{
  *(_DWORD *)(a1 + 8) = 1;
  *(_QWORD *)a1 = &ATL::CComCachedTearOffObject<CImpIChapteredRowset>::`vftable';
  return MPDeleteCriticalSection(a1 + 40);
}

```

## disassembly

```asm
0x18000a2fc  lea     rax, ??_7?$CComCachedTearOffObject@VCImpIChapteredRowset@@@ATL@@6B@; const ATL::CComCachedTearOffObject<CImpIChapteredRowset>::`vftable'
0x18000a303  mov     dword ptr [rcx+8], 1
0x18000a30a  mov     [rcx], rax
0x18000a30d  add     rcx, 28h ; '('
0x18000a311  jmp     cs:__imp_MPDeleteCriticalSection
```
