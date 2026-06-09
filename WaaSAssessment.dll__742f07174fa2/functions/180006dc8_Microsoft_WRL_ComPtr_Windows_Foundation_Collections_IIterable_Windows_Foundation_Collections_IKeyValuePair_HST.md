# Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *>>::~ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *>>(void)

- ea: `0x180006dc8`
- end: `0x180006df0`
- name: `??1?$ComPtr@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@QEAA@XZ`
- size: `40`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180019d62`
- `0x180019d74`
- `0x180019d86`
- `0x180019d98`
- `0x180019e70`

## callees

- `0x180006dc8`
- `0x18001b010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *>>::~ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *>>(
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
0x180006dc8  sub     rsp, 28h
0x180006dcc  mov     rax, rcx
0x180006dcf  mov     rcx, [rcx]
0x180006dd2  test    rcx, rcx
0x180006dd5  jz      short loc_180006DEB
0x180006dd7  mov     qword ptr [rax], 0
0x180006dde  mov     rax, [rcx]
0x180006de1  mov     rax, [rax+10h]
0x180006de5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006dea  nop
0x180006deb  add     rsp, 28h
0x180006def  retn
```
