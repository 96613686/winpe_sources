# SmartPtr<IBackgroundCopyJobHttpOptions>::~SmartPtr<IBackgroundCopyJobHttpOptions>(void)

- ea: `0x18001afdc`
- end: `0x18001afef`
- name: `??1?$SmartPtr@UIBackgroundCopyJobHttpOptions@@@@UEAA@XZ`
- size: `19`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180020b99`
- `0x180020c11`
- `0x180020c23`
- `0x180020c6b`

## callees

- `0x18001afb4`

## pseudocode

```c
__int64 __fastcall SmartPtr<IBackgroundCopyJobHttpOptions>::~SmartPtr<IBackgroundCopyJobHttpOptions>(_QWORD *a1)
{
  *a1 = &SmartPtr<IBITSDownloadMonitor>::`vftable';
  return ATL::CComPtr<IBackgroundCopyCallback>::~CComPtr<IBackgroundCopyCallback>(a1 + 1);
}

```

## disassembly

```asm
0x18001afdc  lea     rax, ??_7?$SmartPtr@UIBITSDownloadMonitor@@@@6B@
0x18001afe3  mov     [rcx], rax
0x18001afe6  add     rcx, 8
0x18001afea  jmp     ??1?$CComPtr@UIBackgroundCopyCallback@@@ATL@@QEAA@XZ
```
