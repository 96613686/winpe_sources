# ATL::CComCachedTearOffObject<CImpIConvertType>::~CComCachedTearOffObject<CImpIConvertType>(void)

- ea: `0x18000a38c`
- end: `0x18000a3a8`
- name: `??1?$CComCachedTearOffObject@VCImpIConvertType@@@ATL@@QEAA@XZ`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000a808`

## import_xrefs

- `MSDART!MPDeleteCriticalSection` at `0x18000a3a1`

## pseudocode

```c
__int64 __fastcall ATL::CComCachedTearOffObject<CImpIConvertType>::~CComCachedTearOffObject<CImpIConvertType>(
        __int64 a1)
{
  *(_DWORD *)(a1 + 8) = 1;
  *(_QWORD *)a1 = &ATL::CComCachedTearOffObject<CImpIConvertType>::`vftable';
  return MPDeleteCriticalSection(a1 + 40);
}

```

## disassembly

```asm
0x18000a38c  lea     rax, ??_7?$CComCachedTearOffObject@VCImpIConvertType@@@ATL@@6B@; const ATL::CComCachedTearOffObject<CImpIConvertType>::`vftable'
0x18000a393  mov     dword ptr [rcx+8], 1
0x18000a39a  mov     [rcx], rax
0x18000a39d  add     rcx, 28h ; '('
0x18000a3a1  jmp     cs:__imp_MPDeleteCriticalSection
```
