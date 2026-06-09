# std::_Temporary_owner<IPxlatInterfaceMgr>::~_Temporary_owner<IPxlatInterfaceMgr>(void)

- ea: `0x18000b590`
- end: `0x18000b5b9`
- name: `??1?$_Temporary_owner@VIPxlatInterfaceMgr@@@std@@QEAA@XZ`
- size: `41`
- prototype: `void __fastcall(IPxlatInterfaceMgr **)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180018325`

## callees

- `0x180002110`
- `0x18000b590`
- `0x18000f41c`

## pseudocode

```c
void __fastcall std::_Temporary_owner<IPxlatInterfaceMgr>::~_Temporary_owner<IPxlatInterfaceMgr>(
        IPxlatInterfaceMgr **a1)
{
  IPxlatInterfaceMgr *v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    IPxlatInterfaceMgr::~IPxlatInterfaceMgr(*a1);
    operator delete(v1, 0xA0u);
  }
}

```

## disassembly

```asm
0x18000b590  push    rbx
0x18000b592  sub     rsp, 20h
0x18000b596  mov     rbx, [rcx]
0x18000b599  test    rbx, rbx
0x18000b59c  jz      short loc_18000B5B3
0x18000b59e  mov     rcx, rbx; this
0x18000b5a1  call    ??1IPxlatInterfaceMgr@@QEAA@XZ; IPxlatInterfaceMgr::~IPxlatInterfaceMgr(void)
0x18000b5a6  mov     edx, 0A0h; unsigned __int64
0x18000b5ab  mov     rcx, rbx; void *
0x18000b5ae  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000b5b3  add     rsp, 20h
0x18000b5b7  pop     rbx
0x18000b5b8  retn
```
