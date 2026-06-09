# StructuredQuery1::LeafCondition::`scalar deleting destructor'(uint)

- ea: `0x180036fc0`
- end: `0x1800370f0`
- name: `??_GLeafCondition@StructuredQuery1@@EEAAPEAXI@Z`
- size: `304`
- prototype: `StructuredQuery1::LeafCondition *__fastcall(StructuredQuery1::LeafCondition *this, char)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x180036fc0`
- `0x18003716c`
- `0x18005db14`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180037071`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180037071`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036ffd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037007`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036ffd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037007`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180036ff3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180036ff3`

## pseudocode

```c
StructuredQuery1::LeafCondition *__fastcall StructuredQuery1::LeafCondition::`scalar deleting destructor'(
        StructuredQuery1::LeafCondition *this,
        char a2)
{
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  StructuredQuery1::AttributeList *v7; // rcx
  __int64 v8; // rcx

  *(_QWORD *)this = &StructuredQuery1::LeafCondition::`vftable'{for `ICondition2'};
  *((_QWORD *)this + 1) = &StructuredQuery1::NegationCondition::`vftable'{for `IConditionAttributeContainer'};
  *((_QWORD *)this + 2) = &StructuredQuery1::LeafCondition::`vftable'{for `IPersistXML'};
  PropVariantClear((PROPVARIANT *)this + 9);
  CoTaskMemFree(*((LPVOID *)this + 12));
  CoTaskMemFree(*((LPVOID *)this + 13));
  v4 = *((_QWORD *)this + 14);
  if ( v4 )
  {
    *((_QWORD *)this + 14) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  v5 = *((_QWORD *)this + 15);
  if ( v5 )
  {
    *((_QWORD *)this + 15) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
  v6 = *((_QWORD *)this + 16);
  if ( v6 )
  {
    *((_QWORD *)this + 16) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  *(_QWORD *)this = &StructuredQuery1::BaseCondition::`vftable'{for `ICondition2'};
  *((_QWORD *)this + 1) = &StructuredQuery1::NegationCondition::`vftable'{for `IConditionAttributeContainer'};
  *((_QWORD *)this + 2) = &StructuredQuery1::BaseCondition::`vftable'{for `IPersistXML'};
  v7 = (StructuredQuery1::AttributeList *)*((_QWORD *)this + 5);
  if ( v7 )
    StructuredQuery1::AttributeList::`scalar deleting destructor'(v7);
  v8 = *((_QWORD *)this + 4);
  if ( v8 )
  {
    *((_QWORD *)this + 4) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
  _InterlockedDecrement(&dword_1800B134C);
  if ( (a2 & 1) != 0 )
    operator delete(this, (const struct std::nothrow_t *)0xB0);
  return this;
}

```

## disassembly

```asm
0x180036fc0  mov     [rsp+arg_0], rbx
0x180036fc5  push    rdi
0x180036fc6  sub     rsp, 20h
0x180036fca  mov     edi, edx
0x180036fcc  mov     rbx, rcx
0x180036fcf  lea     rax, ??_7LeafCondition@StructuredQuery1@@6BICondition2@@@; const StructuredQuery1::LeafCondition::`vftable'{for `ICondition2'}
0x180036fd6  mov     [rcx], rax
0x180036fd9  lea     rax, ??_7NegationCondition@StructuredQuery1@@6BIConditionAttributeContainer@@@; const StructuredQuery1::NegationCondition::`vftable'{for `IConditionAttributeContainer'}
0x180036fe0  mov     [rcx+8], rax
0x180036fe4  lea     rax, ??_7LeafCondition@StructuredQuery1@@6BIPersistXML@@@; const StructuredQuery1::LeafCondition::`vftable'{for `IPersistXML'}
0x180036feb  mov     [rcx+10h], rax
0x180036fef  add     rcx, 48h ; 'H'; pvar
0x180036ff3  call    cs:__imp_PropVariantClear
0x180036ff9  mov     rcx, [rbx+60h]; pv
0x180036ffd  call    cs:__imp_CoTaskMemFree
0x180037003  mov     rcx, [rbx+68h]; pv
0x180037007  call    cs:__imp_CoTaskMemFree
0x18003700d  mov     rcx, [rbx+70h]
0x180037011  test    rcx, rcx
0x180037014  jz      short loc_18003702A
0x180037016  mov     qword ptr [rbx+70h], 0
0x18003701e  mov     rax, [rcx]
0x180037021  mov     rax, [rax+10h]
0x180037025  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003702a  mov     rcx, [rbx+78h]
0x18003702e  test    rcx, rcx
0x180037031  jz      short loc_180037047
0x180037033  mov     qword ptr [rbx+78h], 0
0x18003703b  mov     rax, [rcx]
0x18003703e  mov     rax, [rax+10h]
0x180037042  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037047  mov     rcx, [rbx+80h]
0x18003704e  test    rcx, rcx
0x180037051  jz      short loc_18003706A
0x180037053  mov     qword ptr [rbx+80h], 0
0x18003705e  mov     rax, [rcx]
0x180037061  mov     rax, [rax+10h]
0x180037065  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003706a  lea     rcx, [rbx+88h]; lpCriticalSection
0x180037071  call    cs:__imp_DeleteCriticalSection
0x180037077  nop
0x180037078  lea     rax, ??_7BaseCondition@StructuredQuery1@@6BICondition2@@@; const StructuredQuery1::BaseCondition::`vftable'{for `ICondition2'}
0x18003707f  mov     [rbx], rax
0x180037082  lea     rax, ??_7NegationCondition@StructuredQuery1@@6BIConditionAttributeContainer@@@; const StructuredQuery1::NegationCondition::`vftable'{for `IConditionAttributeContainer'}
0x180037089  mov     [rbx+8], rax
0x18003708d  lea     rax, ??_7BaseCondition@StructuredQuery1@@6BIPersistXML@@@; const StructuredQuery1::BaseCondition::`vftable'{for `IPersistXML'}
0x180037094  mov     [rbx+10h], rax
0x180037098  mov     rcx, [rbx+28h]; this
0x18003709c  test    rcx, rcx
0x18003709f  jnz     short loc_1800370D2
0x1800370a1  mov     rcx, [rbx+20h]
0x1800370a5  test    rcx, rcx
0x1800370a8  jnz     short loc_1800370D9
0x1800370aa  lock dec cs:dword_1800B134C
0x1800370b1  test    dil, 1
0x1800370b5  jz      short loc_1800370C4
0x1800370b7  mov     edx, 0B0h; struct std::nothrow_t *
0x1800370bc  mov     rcx, rbx; void *
0x1800370bf  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800370c4  mov     rax, rbx
0x1800370c7  mov     rbx, [rsp+28h+arg_0]
0x1800370cc  add     rsp, 20h
0x1800370d0  pop     rdi
0x1800370d1  retn
0x1800370d2  call    ??_GAttributeList@StructuredQuery1@@QEAAPEAXI@Z; StructuredQuery1::AttributeList::`scalar deleting destructor'(uint)
0x1800370d7  jmp     short loc_1800370A1
0x1800370d9  mov     qword ptr [rbx+20h], 0
0x1800370e1  mov     rax, [rcx]
0x1800370e4  mov     rax, [rax+10h]
0x1800370e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800370ed  jmp     short loc_1800370AA
```
