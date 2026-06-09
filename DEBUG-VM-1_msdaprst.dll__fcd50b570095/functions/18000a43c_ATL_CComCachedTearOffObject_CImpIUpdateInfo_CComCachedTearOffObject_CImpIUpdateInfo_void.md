# ATL::CComCachedTearOffObject<CImpIUpdateInfo>::~CComCachedTearOffObject<CImpIUpdateInfo>(void)

- ea: `0x18000a43c`
- end: `0x18000a458`
- name: `??1?$CComCachedTearOffObject@VCImpIUpdateInfo@@@ATL@@QEAA@XZ`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000a8e4`

## import_xrefs

- `MSDART!MPDeleteCriticalSection` at `0x18000a451`

## pseudocode

```c
__int64 __fastcall ATL::CComCachedTearOffObject<CImpIUpdateInfo>::~CComCachedTearOffObject<CImpIUpdateInfo>(__int64 a1)
{
  *(_DWORD *)(a1 + 8) = 1;
  *(_QWORD *)a1 = &ATL::CComCachedTearOffObject<CImpIUpdateInfo>::`vftable';
  return MPDeleteCriticalSection(a1 + 40);
}

```

## disassembly

```asm
0x18000a43c  lea     rax, ??_7?$CComCachedTearOffObject@VCImpIUpdateInfo@@@ATL@@6B@; const ATL::CComCachedTearOffObject<CImpIUpdateInfo>::`vftable'
0x18000a443  mov     dword ptr [rcx+8], 1
0x18000a44a  mov     [rcx], rax
0x18000a44d  add     rcx, 28h ; '('
0x18000a451  jmp     cs:__imp_MPDeleteCriticalSection
```
