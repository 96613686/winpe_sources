# Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::~ComPtr<Windows::Data::Json::IJsonObject>(void)

- ea: `0x18000605c`
- end: `0x180006084`
- name: `??1?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEAA@XZ`
- size: `40`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c7c2`
- `0x18000c7e6`
- `0x18000c7f8`
- `0x18000c80a`
- `0x18000c81c`
- `0x18000c82e`
- `0x18000c840`

## callees

- `0x18000605c`
- `0x18000d010`

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
0x18000605c  sub     rsp, 28h
0x180006060  mov     rax, rcx
0x180006063  mov     rcx, [rcx]
0x180006066  test    rcx, rcx
0x180006069  jz      short loc_18000607F
0x18000606b  mov     qword ptr [rax], 0
0x180006072  mov     rax, [rcx]
0x180006075  mov     rax, [rax+10h]
0x180006079  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000607e  nop
0x18000607f  add     rsp, 28h
0x180006083  retn
```
