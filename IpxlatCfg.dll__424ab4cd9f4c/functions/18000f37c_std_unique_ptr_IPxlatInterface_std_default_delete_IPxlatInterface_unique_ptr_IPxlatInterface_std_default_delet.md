# std::unique_ptr<IPxlatInterface,std::default_delete<IPxlatInterface>>::~unique_ptr<IPxlatInterface,std::default_delete<IPxlatInterface>>(void)

- ea: `0x18000f37c`
- end: `0x18000f3a5`
- name: `??1?$unique_ptr@VIPxlatInterface@@U?$default_delete@VIPxlatInterface@@@std@@@std@@QEAA@XZ`
- size: `41`
- prototype: `void __fastcall(IPxlatInterface **)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180018723`
- `0x180018758`

## callees

- `0x180002110`
- `0x18000f37c`
- `0x1800132ac`

## pseudocode

```c
void __fastcall std::unique_ptr<IPxlatInterface>::~unique_ptr<IPxlatInterface>(IPxlatInterface **a1)
{
  IPxlatInterface *v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    IPxlatInterface::~IPxlatInterface(*a1);
    operator delete(v1, 0xE8u);
  }
}

```

## disassembly

```asm
0x18000f37c  push    rbx
0x18000f37e  sub     rsp, 20h
0x18000f382  mov     rbx, [rcx]
0x18000f385  test    rbx, rbx
0x18000f388  jz      short loc_18000F39F
0x18000f38a  mov     rcx, rbx; this
0x18000f38d  call    ??1IPxlatInterface@@QEAA@XZ; IPxlatInterface::~IPxlatInterface(void)
0x18000f392  mov     edx, 0E8h; unsigned __int64
0x18000f397  mov     rcx, rbx; void *
0x18000f39a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000f39f  add     rsp, 20h
0x18000f3a3  pop     rbx
0x18000f3a4  retn
```
