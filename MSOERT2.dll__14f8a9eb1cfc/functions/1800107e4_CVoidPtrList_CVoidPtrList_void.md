# CVoidPtrList::~CVoidPtrList(void)

- ea: `0x1800107e4`
- end: `0x18001080c`
- name: `??1CVoidPtrList@@QEAA@XZ`
- size: `40`
- prototype: `void __fastcall(CVoidPtrList *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180010ba0`

## callees

- `0x180010910`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180010805`

## pseudocode

```c
void __fastcall CVoidPtrList::~CVoidPtrList(CVoidPtrList *this)
{
  *(_QWORD *)this = &CVoidPtrList::`vftable';
  CVoidPtrList::ClearList(this);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
}

```

## disassembly

```asm
0x1800107e4  push    rbx
0x1800107e6  sub     rsp, 20h
0x1800107ea  lea     rax, ??_7CVoidPtrList@@6B@; const CVoidPtrList::`vftable'
0x1800107f1  mov     rbx, rcx
0x1800107f4  mov     [rcx], rax
0x1800107f7  call    ?ClearList@CVoidPtrList@@UEAAJXZ; CVoidPtrList::ClearList(void)
0x1800107fc  lea     rcx, [rbx+40h]
0x180010800  add     rsp, 20h
0x180010804  pop     rbx
0x180010805  jmp     cs:__imp_DeleteCriticalSection
```
