# ATL::CComObject<CRASrv>::`vector deleting destructor'(uint)

- ea: `0x140003e60`
- end: `0x140003e90`
- name: `??_E?$CComObject@VCRASrv@@@ATL@@UEAAPEAXI@Z`
- size: `48`
- prototype: `void *__fastcall(void *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1400034c0`
- `0x140003e60`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140003e7c`
- `msvcrt!??3@YAXPEAX@Z` at `0x140003e7c`

## pseudocode

```c
void *__fastcall ATL::CComObject<CRASrv>::`vector deleting destructor'(void *a1, char a2)
{
  ATL::CComObject<CRASrv>::~CComObject<CRASrv>((__int64)a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x140003e60  mov     [rsp+arg_0], rbx
0x140003e65  push    rdi
0x140003e66  sub     rsp, 20h
0x140003e6a  mov     ebx, edx
0x140003e6c  mov     rdi, rcx
0x140003e6f  call    ??1?$CComObject@VCRASrv@@@ATL@@UEAA@XZ; ATL::CComObject<CRASrv>::~CComObject<CRASrv>(void)
0x140003e74  test    bl, 1
0x140003e77  jz      short loc_140003E82
0x140003e79  mov     rcx, rdi
0x140003e7c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140003e82  mov     rbx, [rsp+28h+arg_0]
0x140003e87  mov     rax, rdi
0x140003e8a  add     rsp, 20h
0x140003e8e  pop     rdi
0x140003e8f  retn
```
