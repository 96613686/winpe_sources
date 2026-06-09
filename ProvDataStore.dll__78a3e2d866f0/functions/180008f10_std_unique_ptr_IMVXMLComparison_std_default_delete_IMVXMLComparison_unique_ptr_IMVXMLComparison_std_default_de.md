# std::unique_ptr<IMVXMLComparison,std::default_delete<IMVXMLComparison>>::~unique_ptr<IMVXMLComparison,std::default_delete<IMVXMLComparison>>(void)

- ea: `0x180008f10`
- end: `0x180008f31`
- name: `??1?$unique_ptr@VIMVXMLComparison@@U?$default_delete@VIMVXMLComparison@@@std@@@std@@QEAA@XZ`
- size: `33`
- prototype: `__int64 __fastcall(__int64 (__fastcall ****)(_QWORD, __int64))`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800117eb`
- `0x180011c73`

## callees

- `0x180008f10`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall std::unique_ptr<IMVXMLComparison>::~unique_ptr<IMVXMLComparison>(
        __int64 (__fastcall ****a1)(_QWORD, __int64))
{
  __int64 (__fastcall ***v1)(_QWORD, __int64); // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (**v1)(v1, 1);
  return result;
}

```

## disassembly

```asm
0x180008f10  sub     rsp, 28h
0x180008f14  mov     rcx, [rcx]
0x180008f17  test    rcx, rcx
0x180008f1a  jz      short loc_180008F2C
0x180008f1c  mov     rax, [rcx]
0x180008f1f  mov     edx, 1
0x180008f24  mov     rax, [rax]
0x180008f27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f2c  add     rsp, 28h
0x180008f30  retn
```
