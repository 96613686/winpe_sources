# Microsoft::WRL::ComPtr<IEnumUnknown>::~ComPtr<IEnumUnknown>(void)

- ea: `0x180002db8`
- end: `0x180002de1`
- name: `??1?$ComPtr@UIEnumUnknown@@@WRL@Microsoft@@QEAA@XZ`
- size: `41`
- prototype: ``
- caller_count: `14`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001dd7a`
- `0x18001debb`
- `0x18001decd`
- `0x18001dedf`
- `0x18001df15`
- `0x18001df27`
- `0x18001df4b`
- `0x18001e167`
- `0x18001e179`
- `0x18001e21c`
- `0x18001e29b`
- `0x18001e4f1`
- `0x18001e515`
- `0x18001e8eb`

## callees

- `0x180002db8`
- `0x18001f010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180002db8  sub     rsp, 28h
0x180002dbc  mov     rax, rcx
0x180002dbf  mov     rcx, [rcx]
0x180002dc2  test    rcx, rcx
0x180002dc5  jz      short loc_180002DDB
0x180002dc7  mov     qword ptr [rax], 0
0x180002dce  mov     rax, [rcx]
0x180002dd1  mov     rax, [rax+10h]
0x180002dd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002dda  nop
0x180002ddb  add     rsp, 28h
0x180002ddf  retn
```
