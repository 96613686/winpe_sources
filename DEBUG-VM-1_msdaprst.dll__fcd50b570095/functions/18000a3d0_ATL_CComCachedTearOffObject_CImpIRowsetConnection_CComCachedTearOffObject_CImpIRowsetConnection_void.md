# ATL::CComCachedTearOffObject<CImpIRowsetConnection>::~CComCachedTearOffObject<CImpIRowsetConnection>(void)

- ea: `0x18000a3d0`
- end: `0x18000a3ec`
- name: `??1?$CComCachedTearOffObject@VCImpIRowsetConnection@@@ATL@@QEAA@XZ`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000a860`

## import_xrefs

- `MSDART!MPDeleteCriticalSection` at `0x18000a3e5`

## pseudocode

```c
__int64 __fastcall ATL::CComCachedTearOffObject<CImpIRowsetConnection>::~CComCachedTearOffObject<CImpIRowsetConnection>(
        __int64 a1)
{
  *(_DWORD *)(a1 + 8) = 1;
  *(_QWORD *)a1 = &ATL::CComCachedTearOffObject<CImpIRowsetConnection>::`vftable';
  return MPDeleteCriticalSection(a1 + 40);
}

```

## disassembly

```asm
0x18000a3d0  lea     rax, ??_7?$CComCachedTearOffObject@VCImpIRowsetConnection@@@ATL@@6B@; const ATL::CComCachedTearOffObject<CImpIRowsetConnection>::`vftable'
0x18000a3d7  mov     dword ptr [rcx+8], 1
0x18000a3de  mov     [rcx], rax
0x18000a3e1  add     rcx, 28h ; '('
0x18000a3e5  jmp     cs:__imp_MPDeleteCriticalSection
```
