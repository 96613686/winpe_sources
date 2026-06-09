# Microsoft::WRL::ComPtr<IEnumUnknown>::~ComPtr<IEnumUnknown>(void)

- ea: `0x180002db4`
- end: `0x180002ddc`
- name: `??1?$ComPtr@UIEnumUnknown@@@WRL@Microsoft@@QEAA@XZ`
- size: `40`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `14`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001d69a`
- `0x18001d7db`
- `0x18001d7ed`
- `0x18001d7ff`
- `0x18001d835`
- `0x18001d847`
- `0x18001d86b`
- `0x18001da87`
- `0x18001da99`
- `0x18001db3c`
- `0x18001dbbb`
- `0x18001de11`
- `0x18001de35`
- `0x18001e20b`

## callees

- `0x180002db4`
- `0x18001f010`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::ComPtr<IEnumUnknown>::~ComPtr<IEnumUnknown>(_QWORD *a1)
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
0x180002db4  sub     rsp, 28h
0x180002db8  mov     rax, rcx
0x180002dbb  mov     rcx, [rcx]
0x180002dbe  test    rcx, rcx
0x180002dc1  jz      short loc_180002DD7
0x180002dc3  mov     qword ptr [rax], 0
0x180002dca  mov     rax, [rcx]
0x180002dcd  mov     rax, [rax+10h]
0x180002dd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002dd6  nop
0x180002dd7  add     rsp, 28h
0x180002ddb  retn
```
