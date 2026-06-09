# Microsoft::WRL::ComPtr<IMMDevice>::~ComPtr<IMMDevice>(void)

- ea: `0x18000dbb8`
- end: `0x18000dbe1`
- name: `??1?$ComPtr@UIMMDevice@@@WRL@Microsoft@@QEAA@XZ`
- size: `41`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000dc0c`
- `0x18000dd84`
- `0x18000eb3c`
- `0x1800107f8`
- `0x18001082e`
- `0x180010840`
- `0x180010852`
- `0x18001089a`

## callees

- `0x18000dbb8`
- `0x180011010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Microsoft::WRL::ComPtr<IMMDevice>::~ComPtr<IMMDevice>(_QWORD *a1)
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
0x18000dbb8  sub     rsp, 28h
0x18000dbbc  mov     rax, rcx
0x18000dbbf  mov     rcx, [rcx]
0x18000dbc2  test    rcx, rcx
0x18000dbc5  jz      short loc_18000DBDB
0x18000dbc7  mov     qword ptr [rax], 0
0x18000dbce  mov     rax, [rcx]
0x18000dbd1  mov     rax, [rax+10h]
0x18000dbd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbda  nop
0x18000dbdb  add     rsp, 28h
0x18000dbdf  retn
```
