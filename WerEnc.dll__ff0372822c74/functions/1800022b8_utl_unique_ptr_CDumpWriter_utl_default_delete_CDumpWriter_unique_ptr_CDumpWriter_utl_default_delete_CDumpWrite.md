# utl::unique_ptr<CDumpWriter,utl::default_delete<CDumpWriter>>::~unique_ptr<CDumpWriter,utl::default_delete<CDumpWriter>>(void)

- ea: `0x1800022b8`
- end: `0x1800022e1`
- name: `??1?$unique_ptr@VCDumpWriter@@U?$default_delete@VCDumpWriter@@@utl@@@utl@@QEAA@XZ`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180002d92`

## callees

- `0x180001424`
- `0x1800022b8`
- `0x1800022e8`

## pseudocode

```c
void __fastcall utl::unique_ptr<CDumpWriter,utl::default_delete<CDumpWriter>>::~unique_ptr<CDumpWriter,utl::default_delete<CDumpWriter>>(
        CDumpWriter **a1)
{
  CDumpWriter *v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    CDumpWriter::~CDumpWriter(*a1);
    operator delete(v1);
  }
}

```

## disassembly

```asm
0x1800022b8  push    rbx
0x1800022ba  sub     rsp, 20h
0x1800022be  mov     rbx, [rcx]
0x1800022c1  test    rbx, rbx
0x1800022c4  jz      short loc_1800022DB
0x1800022c6  mov     rcx, rbx; this
0x1800022c9  call    ??1CDumpWriter@@QEAA@XZ; CDumpWriter::~CDumpWriter(void)
0x1800022ce  mov     edx, 70h ; 'p'; unsigned __int64
0x1800022d3  mov     rcx, rbx; void *
0x1800022d6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800022db  add     rsp, 20h
0x1800022df  pop     rbx
0x1800022e0  retn
```
