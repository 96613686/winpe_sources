# ATL::CComObjectNoLock<ATL::CComClassFactory>::`scalar deleting destructor'(uint)

- ea: `0x140003f28`
- end: `0x140003f48`
- name: `??_G?$CComObjectNoLock@VCComClassFactory@ATL@@@ATL@@QEAAPEAXI@Z`
- size: `32`
- prototype: `void *__fastcall(void *)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140005b70`
- `0x140009ff0`

## callees

- `0x14000359c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140003f39`
- `msvcrt!??3@YAXPEAX@Z` at `0x140003f39`

## pseudocode

```c
void *__fastcall ATL::CComObjectNoLock<ATL::CComClassFactory>::`scalar deleting destructor'(void *a1)
{
  ATL::CComObjectNoLock<ATL::CComClassFactory>::~CComObjectNoLock<ATL::CComClassFactory>((__int64)a1);
  operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x140003f28  push    rbx
0x140003f2a  sub     rsp, 20h
0x140003f2e  mov     rbx, rcx
0x140003f31  call    ??1?$CComObjectNoLock@VCComClassFactory@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectNoLock<ATL::CComClassFactory>::~CComObjectNoLock<ATL::CComClassFactory>(void)
0x140003f36  mov     rcx, rbx
0x140003f39  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140003f3f  mov     rax, rbx
0x140003f42  add     rsp, 20h
0x140003f46  pop     rbx
0x140003f47  retn
```
