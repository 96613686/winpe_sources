# ATL::CComContainedObject<CDfsShell>::AddRef(void)

- ea: `0x180003160`
- end: `0x18000317a`
- name: `?AddRef@?$CComContainedObject@VCDfsShell@@@ATL@@UEAAKXZ`
- size: `26`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003180`

## callees

- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CDfsShell>::AddRef(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 16) + 8LL))(*(_QWORD *)(a1 + 16));
}

```

## disassembly

```asm
0x180003160  sub     rsp, 28h
0x180003164  mov     rcx, [rcx+10h]
0x180003168  mov     rax, [rcx]
0x18000316b  mov     rax, [rax+8]
0x18000316f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003174  nop
0x180003175  add     rsp, 28h
0x180003179  retn
```
