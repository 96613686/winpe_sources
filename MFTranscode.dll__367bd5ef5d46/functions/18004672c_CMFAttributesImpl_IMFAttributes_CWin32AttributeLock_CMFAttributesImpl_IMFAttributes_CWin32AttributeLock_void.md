# CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::~CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>(void)

- ea: `0x18004672c`
- end: `0x18004676c`
- name: `??1?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@UEAA@XZ`
- size: `64`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180046774`
- `0x180046840`

## callees

- `0x1800170b4`
- `0x1800352f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180046765`

## pseudocode

```c
void __fastcall CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::~CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>(
        __int64 a1)
{
  *(_QWORD *)a1 = &CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::`vftable';
  CMFAttributesImpl<IMFActivate,CMFCSLock>::_DeleteAllItems();
  operator delete(*(void **)(a1 + 48));
  *(_QWORD *)(a1 + 48) = 0;
  *(_DWORD *)(a1 + 56) = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
}

```

## disassembly

```asm
0x18004672c  push    rbx
0x18004672e  sub     rsp, 20h
0x180046732  lea     rax, ??_7?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@6B@; const CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::`vftable'
0x180046739  mov     rbx, rcx
0x18004673c  mov     [rcx], rax
0x18004673f  call    ?_DeleteAllItems@?$CMFAttributesImpl@UIMFActivate@@VCMFCSLock@@@@IEAAJXZ; CMFAttributesImpl<IMFActivate,CMFCSLock>::_DeleteAllItems(void)
0x180046744  mov     rcx, [rbx+30h]; Block
0x180046748  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18004674d  lea     rcx, [rbx+8]
0x180046751  mov     qword ptr [rbx+30h], 0
0x180046759  mov     dword ptr [rbx+38h], 0
0x180046760  add     rsp, 20h
0x180046764  pop     rbx
0x180046765  jmp     cs:__imp_DeleteCriticalSection
```
