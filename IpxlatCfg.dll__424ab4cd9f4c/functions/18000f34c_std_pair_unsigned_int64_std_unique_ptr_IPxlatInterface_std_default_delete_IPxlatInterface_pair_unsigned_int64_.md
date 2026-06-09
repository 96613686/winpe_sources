# std::pair<unsigned __int64,std::unique_ptr<IPxlatInterface,std::default_delete<IPxlatInterface>>>::~pair<unsigned __int64,std::unique_ptr<IPxlatInterface,std::default_delete<IPxlatInterface>>>(void)

- ea: `0x18000f34c`
- end: `0x18000f376`
- name: `??1?$pair@_KV?$unique_ptr@VIPxlatInterface@@U?$default_delete@VIPxlatInterface@@@std@@@std@@@std@@QEAA@XZ`
- size: `42`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18001876a`

## callees

- `0x180002110`
- `0x18000f34c`
- `0x1800132ac`

## pseudocode

```c
void __fastcall std::pair<unsigned __int64,std::unique_ptr<IPxlatInterface>>::~pair<unsigned __int64,std::unique_ptr<IPxlatInterface>>(
        __int64 a1)
{
  void *v1; // rbx

  v1 = *(void **)(a1 + 8);
  if ( v1 )
  {
    IPxlatInterface::~IPxlatInterface(*(IPxlatInterface **)(a1 + 8));
    operator delete(v1, 0xE8u);
  }
}

```

## disassembly

```asm
0x18000f34c  push    rbx
0x18000f34e  sub     rsp, 20h
0x18000f352  mov     rbx, [rcx+8]
0x18000f356  test    rbx, rbx
0x18000f359  jz      short loc_18000F370
0x18000f35b  mov     rcx, rbx; this
0x18000f35e  call    ??1IPxlatInterface@@QEAA@XZ; IPxlatInterface::~IPxlatInterface(void)
0x18000f363  mov     edx, 0E8h; unsigned __int64
0x18000f368  mov     rcx, rbx; void *
0x18000f36b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000f370  add     rsp, 20h
0x18000f374  pop     rbx
0x18000f375  retn
```
