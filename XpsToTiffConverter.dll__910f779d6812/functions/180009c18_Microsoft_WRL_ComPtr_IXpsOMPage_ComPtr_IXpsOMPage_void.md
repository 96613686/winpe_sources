# Microsoft::WRL::ComPtr<IXpsOMPage>::~ComPtr<IXpsOMPage>(void)

- ea: `0x180009c18`
- end: `0x180009c40`
- name: `??1?$ComPtr@UIXpsOMPage@@@WRL@Microsoft@@QEAA@XZ`
- size: `40`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000d714`
- `0x18000d77a`
- `0x18000d7b2`

## callees

- `0x180009c18`
- `0x18000e010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Microsoft::WRL::ComPtr<IXpsOMPage>::~ComPtr<IXpsOMPage>(_QWORD *a1)
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
0x180009c18  sub     rsp, 28h
0x180009c1c  mov     rax, rcx
0x180009c1f  mov     rcx, [rcx]
0x180009c22  test    rcx, rcx
0x180009c25  jz      short loc_180009C3B
0x180009c27  mov     qword ptr [rax], 0
0x180009c2e  mov     rax, [rcx]
0x180009c31  mov     rax, [rax+10h]
0x180009c35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c3a  nop
0x180009c3b  add     rsp, 28h
0x180009c3f  retn
```
