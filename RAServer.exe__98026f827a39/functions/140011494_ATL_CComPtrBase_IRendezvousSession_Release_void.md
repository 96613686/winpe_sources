# ATL::CComPtrBase<IRendezvousSession>::Release(void)

- ea: `0x140011494`
- end: `0x1400114bc`
- name: `?Release@?$CComPtrBase@UIRendezvousSession@@@ATL@@QEAAXXZ`
- size: `40`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400114c4`

## callees

- `0x140011494`
- `0x140017010`

## pseudocode

```c
_QWORD *__fastcall ATL::CComPtrBase<IRendezvousSession>::Release(_QWORD *a1)
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
0x140011494  sub     rsp, 28h
0x140011498  mov     rax, rcx
0x14001149b  mov     rcx, [rcx]
0x14001149e  test    rcx, rcx
0x1400114a1  jz      short loc_1400114B7
0x1400114a3  mov     qword ptr [rax], 0
0x1400114aa  mov     rax, [rcx]
0x1400114ad  mov     rax, [rax+10h]
0x1400114b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400114b6  nop
0x1400114b7  add     rsp, 28h
0x1400114bb  retn
```
