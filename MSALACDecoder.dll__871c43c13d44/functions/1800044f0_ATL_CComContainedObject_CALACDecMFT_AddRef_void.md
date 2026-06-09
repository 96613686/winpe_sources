# ATL::CComContainedObject<CALACDecMFT>::AddRef(void)

- ea: `0x1800044f0`
- end: `0x18000450d`
- name: `?AddRef@?$CComContainedObject@VCALACDecMFT@@@ATL@@UEAAKXZ`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000b010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CALACDecMFT>::AddRef(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 152) + 8LL))(*(_QWORD *)(a1 + 152));
}

```

## disassembly

```asm
0x1800044f0  sub     rsp, 28h
0x1800044f4  mov     rcx, [rcx+98h]
0x1800044fb  mov     rax, [rcx]
0x1800044fe  mov     rax, [rax+8]
0x180004502  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004507  nop
0x180004508  add     rsp, 28h
0x18000450c  retn
```
