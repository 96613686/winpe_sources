# Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::~ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>(void)

- ea: `0x180007010`
- end: `0x180007038`
- name: `??1?$ComPtr@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@QEAA@XZ`
- size: `40`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `8`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a48d`
- `0x18000a4d7`
- `0x18000a530`
- `0x18000a542`
- `0x18000a5fa`
- `0x18000a60c`
- `0x18000a61e`
- `0x18000a630`

## callees

- `0x180007010`
- `0x18000b010`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::~ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>(
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
0x180007010  sub     rsp, 28h
0x180007014  mov     rax, rcx
0x180007017  mov     rcx, [rcx]
0x18000701a  test    rcx, rcx
0x18000701d  jz      short loc_180007033
0x18000701f  mov     qword ptr [rax], 0
0x180007026  mov     rax, [rcx]
0x180007029  mov     rax, [rax+10h]
0x18000702d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007032  nop
0x180007033  add     rsp, 28h
0x180007037  retn
```
