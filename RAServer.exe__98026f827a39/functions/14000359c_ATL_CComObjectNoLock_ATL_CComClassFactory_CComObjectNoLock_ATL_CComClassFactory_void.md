# ATL::CComObjectNoLock<ATL::CComClassFactory>::~CComObjectNoLock<ATL::CComClassFactory>(void)

- ea: `0x14000359c`
- end: `0x1400035b6`
- name: `??1?$CComObjectNoLock@VCComClassFactory@ATL@@@ATL@@QEAA@XZ`
- size: `26`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140003f28`

## callees

- `0x1400039e0`

## pseudocode

```c
void __fastcall ATL::CComObjectNoLock<ATL::CComClassFactory>::~CComObjectNoLock<ATL::CComClassFactory>(__int64 a1)
{
  *(_DWORD *)(a1 + 8) = -1073741823;
  *(_QWORD *)a1 = &ATL::CComClassFactory::`vftable';
  ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection((ATL::CComSafeDeleteCriticalSection *)(a1 + 16));
}

```

## disassembly

```asm
0x14000359c  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x1400035a3  mov     dword ptr [rcx+8], 0C0000001h
0x1400035aa  mov     [rcx], rax
0x1400035ad  add     rcx, 10h; this
0x1400035b1  jmp     ??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)
```
