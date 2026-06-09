# ATL::CComContainedObject<CMidi2UmpProtocolDownscalerTransform>::AddRef(void)

- ea: `0x1800051d0`
- end: `0x1800051ea`
- name: `?AddRef@?$CComContainedObject@VCMidi2UmpProtocolDownscalerTransform@@@ATL@@UEAAKXZ`
- size: `26`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180013010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CMidi2UmpProtocolDownscalerTransform>::AddRef(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 8LL))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x1800051d0  sub     rsp, 28h
0x1800051d4  mov     rcx, [rcx+8]
0x1800051d8  mov     rax, [rcx]
0x1800051db  mov     rax, [rax+8]
0x1800051df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051e4  nop
0x1800051e5  add     rsp, 28h
0x1800051e9  retn
```
