# ATL::CComContainedObject<COpusDecMFT>::Release(void)

- ea: `0x180021c40`
- end: `0x180021c5d`
- name: `?Release@?$CComContainedObject@VCOpusDecMFT@@@ATL@@UEAAKXZ`
- size: `29`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180021c70`

## callees

- `0x180024010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<COpusDecMFT>::Release(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 160) + 16LL))(*(_QWORD *)(a1 + 160));
}

```

## disassembly

```asm
0x180021c40  sub     rsp, 28h
0x180021c44  mov     rcx, [rcx+0A0h]
0x180021c4b  mov     rax, [rcx]
0x180021c4e  mov     rax, [rax+10h]
0x180021c52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021c57  nop
0x180021c58  add     rsp, 28h
0x180021c5c  retn
```
