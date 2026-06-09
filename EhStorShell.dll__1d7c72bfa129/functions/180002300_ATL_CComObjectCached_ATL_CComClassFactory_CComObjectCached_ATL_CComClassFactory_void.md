# ATL::CComObjectCached<ATL::CComClassFactory>::~CComObjectCached<ATL::CComClassFactory>(void)

- ea: `0x180002300`
- end: `0x18000231a`
- name: `??1?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAA@XZ`
- size: `26`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001eb0`
- `0x1800021c0`

## callees

- `0x18000238c`

## pseudocode

```c
void __fastcall ATL::CComObjectCached<ATL::CComClassFactory>::~CComObjectCached<ATL::CComClassFactory>(__int64 a1)
{
  *(_DWORD *)(a1 + 8) = -1073741823;
  *(_QWORD *)a1 = &ATL::CComClassFactory::`vftable';
  ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection((ATL::CComSafeDeleteCriticalSection *)(a1 + 16));
}

```

## disassembly

```asm
0x180002300  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180002307  mov     dword ptr [rcx+8], 0C0000001h
0x18000230e  mov     [rcx], rax
0x180002311  add     rcx, 10h; this
0x180002315  jmp     ??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)
```
