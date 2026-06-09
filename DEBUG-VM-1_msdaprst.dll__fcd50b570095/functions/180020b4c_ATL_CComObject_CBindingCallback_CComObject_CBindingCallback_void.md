# ATL::CComObject<CBindingCallback>::~CComObject<CBindingCallback>(void)

- ea: `0x180020b4c`
- end: `0x180020b79`
- name: `??1?$CComObject@VCBindingCallback@@@ATL@@QEAA@XZ`
- size: `45`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180020ce8`

## import_xrefs

- `MSDART!MPDeleteCriticalSection` at `0x180020b72`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CBindingCallback>::~CComObject<CBindingCallback>(__int64 a1)
{
  *(_DWORD *)(a1 + 8) = 1;
  *(_QWORD *)a1 = &ATL::CComObject<CBindingCallback>::`vftable';
  _InterlockedDecrement(&dword_1800454E8);
  *(_QWORD *)a1 = &CBindingCallback::`vftable';
  return MPDeleteCriticalSection(a1 + 16);
}

```

## disassembly

```asm
0x180020b4c  mov     dword ptr [rcx+8], 1
0x180020b53  lea     rax, ??_7?$CComObject@VCBindingCallback@@@ATL@@6B@; const ATL::CComObject<CBindingCallback>::`vftable'
0x180020b5a  mov     [rcx], rax
0x180020b5d  lea     rax, ??_7CBindingCallback@@6B@; const CBindingCallback::`vftable'
0x180020b64  lock dec cs:dword_1800454E8
0x180020b6b  mov     [rcx], rax
0x180020b6e  add     rcx, 10h
0x180020b72  jmp     cs:__imp_MPDeleteCriticalSection
```
