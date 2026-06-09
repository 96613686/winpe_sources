# Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::~ComPtr<Windows::Data::Json::IJsonObject>(void)

- ea: `0x180028588`
- end: `0x1800285b0`
- name: `??1?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEAA@XZ`
- size: `40`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `13`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180035f4e`
- `0x1800360f3`
- `0x180036105`
- `0x180036129`
- `0x18003613b`
- `0x18003614d`
- `0x18003615f`
- `0x180036171`
- `0x180036183`
- `0x1800361a7`
- `0x1800361b9`
- `0x1800361cb`
- `0x1800361dd`

## callees

- `0x180028588`
- `0x180037010`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::~ComPtr<Windows::Data::Json::IJsonObject>(
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
0x180028588  sub     rsp, 28h
0x18002858c  mov     rax, rcx
0x18002858f  mov     rcx, [rcx]
0x180028592  test    rcx, rcx
0x180028595  jz      short loc_1800285AB
0x180028597  mov     qword ptr [rax], 0
0x18002859e  mov     rax, [rcx]
0x1800285a1  mov     rax, [rax+10h]
0x1800285a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800285aa  nop
0x1800285ab  add     rsp, 28h
0x1800285af  retn
```
