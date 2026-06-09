# ATL::CComObjectCached<ATL::CComClassFactory>::~CComObjectCached<ATL::CComClassFactory>(void)

- ea: `0x18001858c`
- end: `0x1800185a8`
- name: `??1?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAA@XZ`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180018740`

## import_xrefs

- `MSDART!MPDeleteCriticalSection` at `0x1800185a1`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<ATL::CComClassFactory>::~CComObjectCached<ATL::CComClassFactory>(__int64 a1)
{
  *(_DWORD *)(a1 + 8) = 1;
  *(_QWORD *)a1 = &ATL::CComObjectCached<ATL::CComClassFactory>::`vftable';
  return MPDeleteCriticalSection(a1 + 16);
}

```

## disassembly

```asm
0x18001858c  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x180018593  mov     dword ptr [rcx+8], 1
0x18001859a  mov     [rcx], rax
0x18001859d  add     rcx, 10h
0x1800185a1  jmp     cs:__imp_MPDeleteCriticalSection
```
