# RegistryRegRow::~RegistryRegRow(void)

- ea: `0x18003a52c`
- end: `0x18003a610`
- name: `??1RegistryRegRow@@UEAA@XZ`
- size: `228`
- prototype: `void __fastcall(RegistryRegRow *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003a670`

## callees

- `0x18001ee98`
- `0x18002c15c`
- `0x18002c234`
- `0x18003a52c`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a543`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a595`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a59f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a5a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a5d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a5e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a543`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a595`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a59f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a5a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a5d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a5e2`

## pseudocode

```c
void __fastcall RegistryRegRow::~RegistryRegRow(LPVOID *this)
{
  LPVOID v2; // rcx
  void *v3; // rcx

  *this = &RegistryRegRow::`vftable';
  CoTaskMemFree(this[14]);
  v2 = this[7];
  if ( v2 )
  {
    (*(void (__fastcall **)(LPVOID, LPVOID *))(*(_QWORD *)v2 + 56LL))(v2, this);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)this[7] + 16LL))(this[7]);
    this[7] = 0;
  }
  RegistryRegRow::ClearMaps((RegistryRegRow *)this);
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixNonAtomicAccessInRegistryRegRow>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FixNonAtomicAccessInRegistryRegRow>::GetImpl'::`2'::impl) )
    CoTaskMemFree(this[9]);
  CoTaskMemFree(this[13]);
  CoTaskMemFree(this[15]);
  this[13] = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixNonAtomicAccessInRegistryRegRow>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FixNonAtomicAccessInRegistryRegRow>::GetImpl'::`2'::impl) )
    this[9] = 0;
  CoTaskMemFree(this[2]);
  v3 = this[10];
  if ( v3 )
  {
    CoTaskMemFree(v3);
    this[10] = 0;
    this[11] = 0;
  }
  *this = &RegRow::`vftable';
  UTSemReadWriteES::~UTSemReadWriteES((UTSemReadWriteES *)(this + 3));
}

```

## disassembly

```asm
0x18003a52c  push    rbx
0x18003a52e  sub     rsp, 20h
0x18003a532  lea     rax, ??_7RegistryRegRow@@6B@; const RegistryRegRow::`vftable'
0x18003a539  mov     rbx, rcx
0x18003a53c  mov     [rcx], rax
0x18003a53f  mov     rcx, [rcx+70h]; pv
0x18003a543  call    cs:__imp_CoTaskMemFree
0x18003a549  mov     rcx, [rbx+38h]
0x18003a54d  test    rcx, rcx
0x18003a550  jz      short loc_18003A579
0x18003a552  mov     rax, [rcx]
0x18003a555  mov     rdx, rbx
0x18003a558  mov     rax, [rax+38h]
0x18003a55c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a561  mov     rcx, [rbx+38h]
0x18003a565  mov     rax, [rcx]
0x18003a568  mov     rax, [rax+10h]
0x18003a56c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a571  mov     qword ptr [rbx+38h], 0
0x18003a579  mov     rcx, rbx; this
0x18003a57c  call    ?ClearMaps@RegistryRegRow@@AEAAXXZ; RegistryRegRow::ClearMaps(void)
0x18003a581  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FixNonAtomicAccessInRegistryRegRow@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FixNonAtomicAccessInRegistryRegRow@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixNonAtomicAccessInRegistryRegRow> `wil::Feature<__WilFeatureTraits_Feature_FixNonAtomicAccessInRegistryRegRow>::GetImpl(void)'::`2'::impl
0x18003a588  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FixNonAtomicAccessInRegistryRegRow@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixNonAtomicAccessInRegistryRegRow>::__private_IsEnabled(void)
0x18003a58d  test    al, al
0x18003a58f  jnz     short loc_18003A59B
0x18003a591  mov     rcx, [rbx+48h]; pv
0x18003a595  call    cs:__imp_CoTaskMemFree
0x18003a59b  mov     rcx, [rbx+68h]; pv
0x18003a59f  call    cs:__imp_CoTaskMemFree
0x18003a5a5  mov     rcx, [rbx+78h]; pv
0x18003a5a9  call    cs:__imp_CoTaskMemFree
0x18003a5af  mov     qword ptr [rbx+68h], 0
0x18003a5b7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FixNonAtomicAccessInRegistryRegRow@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FixNonAtomicAccessInRegistryRegRow@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixNonAtomicAccessInRegistryRegRow> `wil::Feature<__WilFeatureTraits_Feature_FixNonAtomicAccessInRegistryRegRow>::GetImpl(void)'::`2'::impl
0x18003a5be  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FixNonAtomicAccessInRegistryRegRow@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixNonAtomicAccessInRegistryRegRow>::__private_IsEnabled(void)
0x18003a5c3  test    al, al
0x18003a5c5  jnz     short loc_18003A5CF
0x18003a5c7  mov     qword ptr [rbx+48h], 0
0x18003a5cf  mov     rcx, [rbx+10h]; pv
0x18003a5d3  call    cs:__imp_CoTaskMemFree
0x18003a5d9  mov     rcx, [rbx+50h]; pv
0x18003a5dd  test    rcx, rcx
0x18003a5e0  jz      short loc_18003A5F8
0x18003a5e2  call    cs:__imp_CoTaskMemFree
0x18003a5e8  mov     qword ptr [rbx+50h], 0
0x18003a5f0  mov     qword ptr [rbx+58h], 0
0x18003a5f8  lea     rax, ??_7RegRow@@6B@; const RegRow::`vftable'
0x18003a5ff  lea     rcx, [rbx+18h]; this
0x18003a603  mov     [rbx], rax
0x18003a606  add     rsp, 20h
0x18003a60a  pop     rbx
0x18003a60b  jmp     ??1UTSemReadWriteES@@QEAA@XZ; UTSemReadWriteES::~UTSemReadWriteES(void)
```
