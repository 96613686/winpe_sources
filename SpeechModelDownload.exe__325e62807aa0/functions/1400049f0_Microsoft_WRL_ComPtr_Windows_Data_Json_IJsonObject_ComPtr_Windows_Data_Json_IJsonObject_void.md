# Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::~ComPtr<Windows::Data::Json::IJsonObject>(void)

- ea: `0x1400049f0`
- end: `0x140004a18`
- name: `??1?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEAA@XZ`
- size: `40`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `23`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001bca0`
- `0x14001bcb2`
- `0x14001bcc4`
- `0x14001bce8`
- `0x14001bcfa`
- `0x14001bd1e`
- `0x14001bd54`
- `0x14001bd66`
- `0x14001bd78`
- `0x14001bdae`
- `0x14001bdc0`
- `0x14001bdd2`
- `0x14001bde4`
- `0x14001be10`
- `0x14001be22`
- `0x14001be69`
- `0x14001be7b`
- `0x14001be8d`
- `0x14001be9f`
- `0x14001bf9b`
- `0x14001c442`
- `0x14001c454`
- `0x14001c49c`

## callees

- `0x1400049f0`
- `0x14001d010`

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
0x1400049f0  sub     rsp, 28h
0x1400049f4  mov     rax, rcx
0x1400049f7  mov     rcx, [rcx]
0x1400049fa  test    rcx, rcx
0x1400049fd  jz      short loc_140004A13
0x1400049ff  mov     qword ptr [rax], 0
0x140004a06  mov     rax, [rcx]
0x140004a09  mov     rax, [rax+10h]
0x140004a0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004a12  nop
0x140004a13  add     rsp, 28h
0x140004a17  retn
```
