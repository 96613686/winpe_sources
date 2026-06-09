# Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>::~ComPtr<Windows::Foundation::IUriRuntimeClass>(void)

- ea: `0x14000ea54`
- end: `0x14000ea7c`
- name: `??1?$ComPtr@UIUriRuntimeClass@Foundation@Windows@@@WRL@Microsoft@@QEAA@XZ`
- size: `40`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `8`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140011147`
- `0x140011159`
- `0x14001116b`
- `0x14001117d`
- `0x1400112e1`
- `0x1400112f3`
- `0x140011305`
- `0x140011317`

## callees

- `0x14000ea54`
- `0x140012010`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>::~ComPtr<Windows::Foundation::IUriRuntimeClass>(
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
0x14000ea54  sub     rsp, 28h
0x14000ea58  mov     rax, rcx
0x14000ea5b  mov     rcx, [rcx]
0x14000ea5e  test    rcx, rcx
0x14000ea61  jz      short loc_14000EA77
0x14000ea63  mov     qword ptr [rax], 0
0x14000ea6a  mov     rax, [rcx]
0x14000ea6d  mov     rax, [rax+10h]
0x14000ea71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ea76  nop
0x14000ea77  add     rsp, 28h
0x14000ea7b  retn
```
