# CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::~CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>(void)

- ea: `0x18006bdd0`
- end: `0x18006be15`
- name: `??1?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@UEAA@XZ`
- size: `69`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18006be5c`
- `0x18006bf40`
- `0x18006bf80`

## callees

- `0x18004cf10`
- `0x180070758`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006be09`

## pseudocode

```c
void __fastcall CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::~CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>(
        __int64 a1)
{
  *(_QWORD *)a1 = &CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::`vftable';
  CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::_DeleteAllItems();
  operator delete(*(void **)(a1 + 48));
  *(_QWORD *)(a1 + 48) = 0;
  *(_DWORD *)(a1 + 56) = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
}

```

## disassembly

```asm
0x18006bdd0  push    rbx
0x18006bdd2  sub     rsp, 20h
0x18006bdd6  lea     rax, ??_7?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@6B@; const CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::`vftable'
0x18006bddd  mov     rbx, rcx
0x18006bde0  mov     [rcx], rax
0x18006bde3  call    ?_DeleteAllItems@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@IEAAJXZ; CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::_DeleteAllItems(void)
0x18006bde8  mov     rcx, [rbx+30h]; Block
0x18006bdec  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18006bdf1  lea     rcx, [rbx+8]
0x18006bdf5  mov     qword ptr [rbx+30h], 0
0x18006bdfd  mov     dword ptr [rbx+38h], 0
0x18006be04  add     rsp, 20h
0x18006be08  pop     rbx
0x18006be09  jmp     cs:__imp_DeleteCriticalSection
```
