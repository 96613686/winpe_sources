# ATL::CComContainedObject<CALACDecMFT>::Release(void)

- ea: `0x1800068b0`
- end: `0x1800068cd`
- name: `?Release@?$CComContainedObject@VCALACDecMFT@@@ATL@@UEAAKXZ`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000b010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CALACDecMFT>::Release(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 152) + 16LL))(*(_QWORD *)(a1 + 152));
}

```

## disassembly

```asm
0x1800068b0  sub     rsp, 28h
0x1800068b4  mov     rcx, [rcx+98h]
0x1800068bb  mov     rax, [rcx]
0x1800068be  mov     rax, [rax+10h]
0x1800068c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068c7  nop
0x1800068c8  add     rsp, 28h
0x1800068cc  retn
```
