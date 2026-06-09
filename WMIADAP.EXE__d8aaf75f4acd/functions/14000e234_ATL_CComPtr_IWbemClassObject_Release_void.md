# ATL::CComPtr<IWbemClassObject>::Release(void)

- ea: `0x14000e234`
- end: `0x14000e25b`
- name: `?Release@?$CComPtr@UIWbemClassObject@@@ATL@@QEAAXXZ`
- size: `39`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000e04c`
- `0x140015bd9`

## callees

- `0x14000e234`
- `0x140017010`

## pseudocode

```c
_QWORD *__fastcall ATL::CComPtr<IWbemClassObject>::Release(_QWORD *a1)
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
0x14000e234  sub     rsp, 28h
0x14000e238  mov     rax, rcx
0x14000e23b  mov     rcx, [rcx]
0x14000e23e  test    rcx, rcx
0x14000e241  jz      short loc_14000E256
0x14000e243  mov     qword ptr [rax], 0
0x14000e24a  mov     rax, [rcx]
0x14000e24d  mov     rax, [rax+10h]
0x14000e251  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e256  add     rsp, 28h
0x14000e25a  retn
```
