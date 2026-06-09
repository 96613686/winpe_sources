# CMFAttributesImpl<IMFActivate,CMFCSLock>::~CMFAttributesImpl<IMFActivate,CMFCSLock>(void)

- ea: `0x1800313b8`
- end: `0x1800313f8`
- name: `??1?$CMFAttributesImpl@UIMFActivate@@VCMFCSLock@@@@UEAA@XZ`
- size: `64`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180031400`
- `0x180031500`
- `0x180046228`

## callees

- `0x180017068`
- `0x1800352f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800313f1`

## pseudocode

```c
void __fastcall CMFAttributesImpl<IMFActivate,CMFCSLock>::~CMFAttributesImpl<IMFActivate,CMFCSLock>(__int64 a1)
{
  *(_QWORD *)a1 = &CMFAttributesImpl<IMFActivate,CMFCSLock>::`vftable';
  CMFAttributesImpl<IMFActivate,CMFCSLock>::_DeleteAllItems();
  operator delete(*(void **)(a1 + 48));
  *(_QWORD *)(a1 + 48) = 0;
  *(_DWORD *)(a1 + 56) = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
}

```

## disassembly

```asm
0x1800313b8  push    rbx
0x1800313ba  sub     rsp, 20h
0x1800313be  lea     rax, ??_7?$CMFAttributesImpl@UIMFActivate@@VCMFCSLock@@@@6B@; const CMFAttributesImpl<IMFActivate,CMFCSLock>::`vftable'
0x1800313c5  mov     rbx, rcx
0x1800313c8  mov     [rcx], rax
0x1800313cb  call    ?_DeleteAllItems@?$CMFAttributesImpl@UIMFActivate@@VCMFCSLock@@@@IEAAJXZ; CMFAttributesImpl<IMFActivate,CMFCSLock>::_DeleteAllItems(void)
0x1800313d0  mov     rcx, [rbx+30h]; Block
0x1800313d4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800313d9  lea     rcx, [rbx+8]
0x1800313dd  mov     qword ptr [rbx+30h], 0
0x1800313e5  mov     dword ptr [rbx+38h], 0
0x1800313ec  add     rsp, 20h
0x1800313f0  pop     rbx
0x1800313f1  jmp     cs:__imp_DeleteCriticalSection
```
