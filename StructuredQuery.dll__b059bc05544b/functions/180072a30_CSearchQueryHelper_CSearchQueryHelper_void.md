# CSearchQueryHelper::~CSearchQueryHelper(void)

- ea: `0x180072a30`
- end: `0x180072a9e`
- name: `??1CSearchQueryHelper@@AEAA@XZ`
- size: `110`
- prototype: `void __fastcall(LPVOID *this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180072ba0`

## callees

- `0x18001b2b4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180072a47`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180072a51`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180072a5b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180072a65`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180072a6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180072a79`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180072a47`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180072a51`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180072a5b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180072a65`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180072a6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180072a79`

## pseudocode

```c
void __fastcall CSearchQueryHelper::~CSearchQueryHelper(LPVOID *this)
{
  *this = &CSearchQueryHelper::`vftable';
  CoTaskMemFree(this[6]);
  CoTaskMemFree(this[7]);
  CoTaskMemFree(this[8]);
  CoTaskMemFree(this[9]);
  CoTaskMemFree(this[10]);
  CoTaskMemFree(this[12]);
  IUnknown_SafeReleaseAndNullPtr<GrowableBuffer<tagHITRANGE>>(this + 14);
  IUnknown_SafeReleaseAndNullPtr<GrowableBuffer<tagHITRANGE>>(this + 15);
  _InterlockedDecrement(&dword_1800B134C);
}

```

## disassembly

```asm
0x180072a30  push    rbx
0x180072a32  sub     rsp, 20h
0x180072a36  mov     rbx, rcx
0x180072a39  lea     rax, ??_7CSearchQueryHelper@@6B@; const CSearchQueryHelper::`vftable'
0x180072a40  mov     [rcx], rax
0x180072a43  mov     rcx, [rcx+30h]; pv
0x180072a47  call    cs:__imp_CoTaskMemFree
0x180072a4d  mov     rcx, [rbx+38h]; pv
0x180072a51  call    cs:__imp_CoTaskMemFree
0x180072a57  mov     rcx, [rbx+40h]; pv
0x180072a5b  call    cs:__imp_CoTaskMemFree
0x180072a61  mov     rcx, [rbx+48h]; pv
0x180072a65  call    cs:__imp_CoTaskMemFree
0x180072a6b  mov     rcx, [rbx+50h]; pv
0x180072a6f  call    cs:__imp_CoTaskMemFree
0x180072a75  mov     rcx, [rbx+60h]; pv
0x180072a79  call    cs:__imp_CoTaskMemFree
0x180072a7f  lea     rcx, [rbx+70h]
0x180072a83  call    ??$IUnknown_SafeReleaseAndNullPtr@V?$GrowableBuffer@UtagHITRANGE@@@@@@YAXAEAPEAV?$GrowableBuffer@UtagHITRANGE@@@@@Z; IUnknown_SafeReleaseAndNullPtr<GrowableBuffer<tagHITRANGE>>(GrowableBuffer<tagHITRANGE> * &)
0x180072a88  lea     rcx, [rbx+78h]
0x180072a8c  call    ??$IUnknown_SafeReleaseAndNullPtr@V?$GrowableBuffer@UtagHITRANGE@@@@@@YAXAEAPEAV?$GrowableBuffer@UtagHITRANGE@@@@@Z; IUnknown_SafeReleaseAndNullPtr<GrowableBuffer<tagHITRANGE>>(GrowableBuffer<tagHITRANGE> * &)
0x180072a91  lock dec cs:dword_1800B134C
0x180072a98  add     rsp, 20h
0x180072a9c  pop     rbx
0x180072a9d  retn
```
