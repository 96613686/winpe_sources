# Microsoft::WRL::ComPtr<IUnknown>::~ComPtr<IUnknown>(void)

- ea: `0x180001b5c`
- end: `0x180001b84`
- name: `??1?$ComPtr@UIUnknown@@@WRL@Microsoft@@QEAA@XZ`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800175fd`

## callees

- `0x180001b5c`
- `0x180018010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Microsoft::WRL::ComPtr<IUnknown>::~ComPtr<IUnknown>(_QWORD *a1)
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
0x180001b5c  sub     rsp, 28h
0x180001b60  mov     rax, rcx
0x180001b63  mov     rcx, [rcx]
0x180001b66  test    rcx, rcx
0x180001b69  jz      short loc_180001B7F
0x180001b6b  mov     qword ptr [rax], 0
0x180001b72  mov     rax, [rcx]
0x180001b75  mov     rax, [rax+10h]
0x180001b79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b7e  nop
0x180001b7f  add     rsp, 28h
0x180001b83  retn
```
