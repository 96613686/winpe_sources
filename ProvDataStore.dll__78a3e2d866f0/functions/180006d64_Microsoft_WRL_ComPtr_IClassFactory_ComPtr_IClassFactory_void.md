# Microsoft::WRL::ComPtr<IClassFactory>::~ComPtr<IClassFactory>(void)

- ea: `0x180006d64`
- end: `0x180006d8c`
- name: `??1?$ComPtr@UIClassFactory@@@WRL@Microsoft@@QEAA@XZ`
- size: `40`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `8`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180011735`
- `0x180011747`
- `0x18001186d`
- `0x180011a5b`
- `0x180011aec`
- `0x180011bdd`
- `0x180011c01`
- `0x180011dcb`

## callees

- `0x180006d64`
- `0x180012010`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::ComPtr<IClassFactory>::~ComPtr<IClassFactory>(_QWORD *a1)
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
0x180006d64  sub     rsp, 28h
0x180006d68  mov     rax, rcx
0x180006d6b  mov     rcx, [rcx]
0x180006d6e  test    rcx, rcx
0x180006d71  jz      short loc_180006D87
0x180006d73  mov     qword ptr [rax], 0
0x180006d7a  mov     rax, [rcx]
0x180006d7d  mov     rax, [rax+10h]
0x180006d81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d86  nop
0x180006d87  add     rsp, 28h
0x180006d8b  retn
```
