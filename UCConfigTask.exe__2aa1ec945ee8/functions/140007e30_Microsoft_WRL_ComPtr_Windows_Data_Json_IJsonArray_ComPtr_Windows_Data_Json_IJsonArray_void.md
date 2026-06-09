# Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::~ComPtr<Windows::Data::Json::IJsonArray>(void)

- ea: `0x140007e30`
- end: `0x140007e58`
- name: `??1?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEAA@XZ`
- size: `40`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140008944`
- `0x140008956`

## callees

- `0x140007e30`
- `0x140009010`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::~ComPtr<Windows::Data::Json::IJsonArray>(
        _QWORD *a1)
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
0x140007e30  sub     rsp, 28h
0x140007e34  mov     rax, rcx
0x140007e37  mov     rcx, [rcx]
0x140007e3a  test    rcx, rcx
0x140007e3d  jz      short loc_140007E53
0x140007e3f  mov     qword ptr [rax], 0
0x140007e46  mov     rax, [rcx]
0x140007e49  mov     rax, [rax+10h]
0x140007e4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007e52  nop
0x140007e53  add     rsp, 28h
0x140007e57  retn
```
