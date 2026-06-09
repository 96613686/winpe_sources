# MdmTaskRequestImpl::~MdmTaskRequestImpl(void)

- ea: `0x18000ab88`
- end: `0x18000abad`
- name: `??1MdmTaskRequestImpl@@QEAA@XZ`
- size: `37`
- prototype: `void __fastcall(MdmTaskRequestImpl *this, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `file_ops, service_task`

## callers

- `0x180003a20`
- `0x180004520`
- `0x180004c70`
- `0x18000745c`
- `0x180009b24`

## callees

- `0x180001544`
- `0x18000ab88`

## pseudocode

```c
void __fastcall MdmTaskRequestImpl::~MdmTaskRequestImpl(MdmTaskRequestImpl *this, unsigned __int64 a2)
{
  void *v3; // rcx

  v3 = (void *)*((_QWORD *)this + 2);
  if ( v3 )
  {
    operator delete(v3, a2);
    *((_QWORD *)this + 2) = 0;
  }
}

```

## disassembly

```asm
0x18000ab88  push    rbx
0x18000ab8a  sub     rsp, 20h
0x18000ab8e  mov     rbx, rcx
0x18000ab91  mov     rcx, [rcx+10h]; void *
0x18000ab95  test    rcx, rcx
0x18000ab98  jz      short loc_18000ABA7
0x18000ab9a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ab9f  mov     qword ptr [rbx+10h], 0
0x18000aba7  add     rsp, 20h
0x18000abab  pop     rbx
0x18000abac  retn
```
