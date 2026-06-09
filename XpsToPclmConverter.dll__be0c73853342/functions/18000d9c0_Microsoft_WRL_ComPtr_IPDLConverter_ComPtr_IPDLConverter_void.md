# Microsoft::WRL::ComPtr<IPDLConverter>::~ComPtr<IPDLConverter>(void)

- ea: `0x18000d9c0`
- end: `0x18000d9e8`
- name: `??1?$ComPtr@UIPDLConverter@@@WRL@Microsoft@@QEAA@XZ`
- size: `40`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001d3aa`
- `0x18001d696`
- `0x18001e0e0`
- `0x18001e0f2`
- `0x18001e158`

## callees

- `0x18000d9c0`
- `0x18001f010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Microsoft::WRL::ComPtr<IPDLConverter>::~ComPtr<IPDLConverter>(_QWORD *a1)
{
  _QWORD *result; // rax
  __int64 v2; // rcx

  result = a1;
  v2 = *a1;
  if ( v2 )
  {
    *result = 0;
    return (_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  return result;
}

```

## disassembly

```asm
0x18000d9c0  sub     rsp, 28h
0x18000d9c4  mov     rax, rcx
0x18000d9c7  mov     rcx, [rcx]
0x18000d9ca  test    rcx, rcx
0x18000d9cd  jz      short loc_18000D9E3
0x18000d9cf  mov     qword ptr [rax], 0
0x18000d9d6  mov     rax, [rcx]
0x18000d9d9  mov     rax, [rax+10h]
0x18000d9dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d9e2  nop
0x18000d9e3  add     rsp, 28h
0x18000d9e7  retn
```
