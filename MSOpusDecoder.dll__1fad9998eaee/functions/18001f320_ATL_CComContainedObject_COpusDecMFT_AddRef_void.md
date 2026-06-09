# ATL::CComContainedObject<COpusDecMFT>::AddRef(void)

- ea: `0x18001f320`
- end: `0x18001f33d`
- name: `?AddRef@?$CComContainedObject@VCOpusDecMFT@@@ATL@@UEAAKXZ`
- size: `29`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001f350`

## callees

- `0x180024010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<COpusDecMFT>::AddRef(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 160) + 8LL))(*(_QWORD *)(a1 + 160));
}

```

## disassembly

```asm
0x18001f320  sub     rsp, 28h
0x18001f324  mov     rcx, [rcx+0A0h]
0x18001f32b  mov     rax, [rcx]
0x18001f32e  mov     rax, [rax+8]
0x18001f332  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f337  nop
0x18001f338  add     rsp, 28h
0x18001f33c  retn
```
