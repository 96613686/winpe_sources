# ATL::CComCachedTearOffObject<CImpIColumnsInfo>::~CComCachedTearOffObject<CImpIColumnsInfo>(void)

- ea: `0x18000a320`
- end: `0x18000a33c`
- name: `??1?$CComCachedTearOffObject@VCImpIColumnsInfo@@@ATL@@QEAA@XZ`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000a784`

## import_xrefs

- `MSDART!MPDeleteCriticalSection` at `0x18000a335`

## pseudocode

```c
__int64 __fastcall ATL::CComCachedTearOffObject<CImpIColumnsInfo>::~CComCachedTearOffObject<CImpIColumnsInfo>(
        __int64 a1)
{
  *(_DWORD *)(a1 + 8) = 1;
  *(_QWORD *)a1 = &ATL::CComCachedTearOffObject<CImpIColumnsInfo>::`vftable';
  return MPDeleteCriticalSection(a1 + 40);
}

```

## disassembly

```asm
0x18000a320  lea     rax, ??_7?$CComCachedTearOffObject@VCImpIColumnsInfo@@@ATL@@6B@; const ATL::CComCachedTearOffObject<CImpIColumnsInfo>::`vftable'
0x18000a327  mov     dword ptr [rcx+8], 1
0x18000a32e  mov     [rcx], rax
0x18000a331  add     rcx, 28h ; '('
0x18000a335  jmp     cs:__imp_MPDeleteCriticalSection
```
