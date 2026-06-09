# ATL::CComCachedTearOffObject<CImpIColumnsUpdateInfo>::~CComCachedTearOffObject<CImpIColumnsUpdateInfo>(void)

- ea: `0x18000a368`
- end: `0x18000a384`
- name: `??1?$CComCachedTearOffObject@VCImpIColumnsUpdateInfo@@@ATL@@QEAA@XZ`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000a7dc`

## import_xrefs

- `MSDART!MPDeleteCriticalSection` at `0x18000a37d`

## pseudocode

```c
__int64 __fastcall ATL::CComCachedTearOffObject<CImpIColumnsUpdateInfo>::~CComCachedTearOffObject<CImpIColumnsUpdateInfo>(
        __int64 a1)
{
  *(_DWORD *)(a1 + 8) = 1;
  *(_QWORD *)a1 = &ATL::CComCachedTearOffObject<CImpIColumnsUpdateInfo>::`vftable';
  return MPDeleteCriticalSection(a1 + 40);
}

```

## disassembly

```asm
0x18000a368  lea     rax, ??_7?$CComCachedTearOffObject@VCImpIColumnsUpdateInfo@@@ATL@@6B@; const ATL::CComCachedTearOffObject<CImpIColumnsUpdateInfo>::`vftable'
0x18000a36f  mov     dword ptr [rcx+8], 1
0x18000a376  mov     [rcx], rax
0x18000a379  add     rcx, 28h ; '('
0x18000a37d  jmp     cs:__imp_MPDeleteCriticalSection
```
