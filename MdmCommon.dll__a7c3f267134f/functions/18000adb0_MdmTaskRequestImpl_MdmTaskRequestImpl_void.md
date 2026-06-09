# MdmTaskRequestImpl::~MdmTaskRequestImpl(void)

- ea: `0x18000adb0`
- end: `0x18000add6`
- name: `??1MdmTaskRequestImpl@@QEAA@XZ`
- size: `38`
- prototype: `void __fastcall(MdmTaskRequestImpl *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: `file_ops, service_task`

## callers

- `0x180003a30`
- `0x180004550`
- `0x180004ca0`
- `0x1800074e4`
- `0x180009d18`

## callees

- `0x180001544`
- `0x18000adb0`

## pseudocode

```c
void __fastcall MdmTaskRequestImpl::~MdmTaskRequestImpl(MdmTaskRequestImpl *this)
{
  void *v2; // rcx

  v2 = (void *)*((_QWORD *)this + 2);
  if ( v2 )
  {
    operator delete(v2);
    *((_QWORD *)this + 2) = 0;
  }
}

```

## disassembly

```asm
0x18000adb0  push    rbx
0x18000adb2  sub     rsp, 20h
0x18000adb6  mov     rbx, rcx
0x18000adb9  mov     rcx, [rcx+10h]; void *
0x18000adbd  test    rcx, rcx
0x18000adc0  jz      short loc_18000ADCF
0x18000adc2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000adc7  mov     qword ptr [rbx+10h], 0
0x18000adcf  add     rsp, 20h
0x18000add3  pop     rbx
0x18000add4  retn
```
