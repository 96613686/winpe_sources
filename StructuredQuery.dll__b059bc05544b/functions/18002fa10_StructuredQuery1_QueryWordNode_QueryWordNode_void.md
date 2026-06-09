# StructuredQuery1::QueryWordNode::~QueryWordNode(void)

- ea: `0x18002fa10`
- end: `0x18002fa56`
- name: `??1QueryWordNode@StructuredQuery1@@AEAA@XZ`
- size: `70`
- prototype: `void __fastcall(LPVOID *this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002f880`

## callees

- `0x18001b2b4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fa27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fa31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fa27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fa31`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall StructuredQuery1::QueryWordNode::~QueryWordNode(LPVOID *this)
{
  *this = &StructuredQuery1::QueryWordNode::`vftable';
  CoTaskMemFree(this[3]);
  CoTaskMemFree(this[4]);
  IUnknown_SafeReleaseAndNullPtr<GrowableBuffer<tagHITRANGE>>(this + 6);
  IUnknown_SafeReleaseAndNullPtr<GrowableBuffer<tagHITRANGE>>(this + 7);
  _InterlockedDecrement(&dword_1800B134C);
}

```

## disassembly

```asm
0x18002fa10  push    rbx
0x18002fa12  sub     rsp, 20h
0x18002fa16  mov     rbx, rcx
0x18002fa19  lea     rax, ??_7QueryWordNode@StructuredQuery1@@6B@; const StructuredQuery1::QueryWordNode::`vftable'
0x18002fa20  mov     [rcx], rax
0x18002fa23  mov     rcx, [rcx+18h]; pv
0x18002fa27  call    cs:__imp_CoTaskMemFree
0x18002fa2d  mov     rcx, [rbx+20h]; pv
0x18002fa31  call    cs:__imp_CoTaskMemFree
0x18002fa37  lea     rcx, [rbx+30h]
0x18002fa3b  call    ??$IUnknown_SafeReleaseAndNullPtr@V?$GrowableBuffer@UtagHITRANGE@@@@@@YAXAEAPEAV?$GrowableBuffer@UtagHITRANGE@@@@@Z; IUnknown_SafeReleaseAndNullPtr<GrowableBuffer<tagHITRANGE>>(GrowableBuffer<tagHITRANGE> * &)
0x18002fa40  lea     rcx, [rbx+38h]
0x18002fa44  call    ??$IUnknown_SafeReleaseAndNullPtr@V?$GrowableBuffer@UtagHITRANGE@@@@@@YAXAEAPEAV?$GrowableBuffer@UtagHITRANGE@@@@@Z; IUnknown_SafeReleaseAndNullPtr<GrowableBuffer<tagHITRANGE>>(GrowableBuffer<tagHITRANGE> * &)
0x18002fa49  lock dec cs:dword_1800B134C
0x18002fa50  add     rsp, 20h
0x18002fa54  pop     rbx
0x18002fa55  retn
```
