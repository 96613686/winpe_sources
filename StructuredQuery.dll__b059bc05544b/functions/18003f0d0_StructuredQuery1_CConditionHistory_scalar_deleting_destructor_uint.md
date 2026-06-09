# StructuredQuery1::CConditionHistory::`scalar deleting destructor'(uint)

- ea: `0x18003f0d0`
- end: `0x18003f152`
- name: `??_GCConditionHistory@StructuredQuery1@@AEAAPEAXI@Z`
- size: `130`
- prototype: `StructuredQuery1::CConditionHistory *__fastcall(StructuredQuery1::CConditionHistory *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18003f0a0`

## callees

- `0x18003f0d0`
- `0x18005db14`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003f135`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003f135`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f0fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f107`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f0fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f107`

## pseudocode

```c
StructuredQuery1::CConditionHistory *__fastcall StructuredQuery1::CConditionHistory::`scalar deleting destructor'(
        StructuredQuery1::CConditionHistory *this)
{
  __int64 v2; // rcx

  *(_QWORD *)this = &StructuredQuery1::CConditionHistory::`vftable'{for `IConditionHistory'};
  *((_QWORD *)this + 1) = &StructuredQuery1::CConditionHistory::`vftable'{for `IConditionAttribute'};
  *((_QWORD *)this + 2) = &StructuredQuery1::CConditionHistory::`vftable'{for `IPersistXML'};
  CoTaskMemFree(*((LPVOID *)this + 4));
  CoTaskMemFree(*((LPVOID *)this + 5));
  v2 = *((_QWORD *)this + 8);
  if ( v2 )
  {
    *((_QWORD *)this + 8) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  _InterlockedDecrement(&dword_1800B134C);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  operator delete(this, (const struct std::nothrow_t *)0x70);
  return this;
}

```

## disassembly

```asm
0x18003f0d0  push    rbx
0x18003f0d2  sub     rsp, 20h
0x18003f0d6  mov     rbx, rcx
0x18003f0d9  lea     rax, ??_7CConditionHistory@StructuredQuery1@@6BIConditionHistory@@@; const StructuredQuery1::CConditionHistory::`vftable'{for `IConditionHistory'}
0x18003f0e0  mov     [rcx], rax
0x18003f0e3  lea     rax, ??_7CConditionHistory@StructuredQuery1@@6BIConditionAttribute@@@; const StructuredQuery1::CConditionHistory::`vftable'{for `IConditionAttribute'}
0x18003f0ea  mov     [rcx+8], rax
0x18003f0ee  lea     rax, ??_7CConditionHistory@StructuredQuery1@@6BIPersistXML@@@; const StructuredQuery1::CConditionHistory::`vftable'{for `IPersistXML'}
0x18003f0f5  mov     [rcx+10h], rax
0x18003f0f9  mov     rcx, [rcx+20h]; pv
0x18003f0fd  call    cs:__imp_CoTaskMemFree
0x18003f103  mov     rcx, [rbx+28h]; pv
0x18003f107  call    cs:__imp_CoTaskMemFree
0x18003f10d  mov     rcx, [rbx+40h]
0x18003f111  test    rcx, rcx
0x18003f114  jz      short loc_18003F12A
0x18003f116  mov     qword ptr [rbx+40h], 0
0x18003f11e  mov     rax, [rcx]
0x18003f121  mov     rax, [rax+10h]
0x18003f125  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f12a  lock dec cs:dword_1800B134C
0x18003f131  lea     rcx, [rbx+48h]; lpCriticalSection
0x18003f135  call    cs:__imp_DeleteCriticalSection
0x18003f13b  nop
0x18003f13c  mov     edx, 70h ; 'p'; struct std::nothrow_t *
0x18003f141  mov     rcx, rbx; void *
0x18003f144  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003f149  mov     rax, rbx
0x18003f14c  add     rsp, 20h
0x18003f150  pop     rbx
0x18003f151  retn
```
