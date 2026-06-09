# Microsoft::WRL::ComPtr<ILocationManagerInternal>::~ComPtr<ILocationManagerInternal>(void)

- ea: `0x18000f4f8`
- end: `0x18000f520`
- name: `??1?$ComPtr@UILocationManagerInternal@@@WRL@Microsoft@@QEAA@XZ`
- size: `40`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180013839`

## callees

- `0x18000f4f8`
- `0x180014010`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::ComPtr<ILocationManagerInternal>::~ComPtr<ILocationManagerInternal>(_QWORD *a1)
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
0x18000f4f8  sub     rsp, 28h
0x18000f4fc  mov     rax, rcx
0x18000f4ff  mov     rcx, [rcx]
0x18000f502  test    rcx, rcx
0x18000f505  jz      short loc_18000F51B
0x18000f507  mov     qword ptr [rax], 0
0x18000f50e  mov     rax, [rcx]
0x18000f511  mov     rax, [rax+10h]
0x18000f515  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f51a  nop
0x18000f51b  add     rsp, 28h
0x18000f51f  retn
```
