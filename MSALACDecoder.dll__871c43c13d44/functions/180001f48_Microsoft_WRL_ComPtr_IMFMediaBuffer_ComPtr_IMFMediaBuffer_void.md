# Microsoft::WRL::ComPtr<IMFMediaBuffer>::~ComPtr<IMFMediaBuffer>(void)

- ea: `0x180001f48`
- end: `0x180001f70`
- name: `??1?$ComPtr@UIMFMediaBuffer@@@WRL@Microsoft@@QEAA@XZ`
- size: `40`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a0a6`
- `0x18000a0b8`
- `0x18000a0ca`
- `0x18000a0dc`
- `0x18000a0ee`

## callees

- `0x180001f48`
- `0x18000b010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Microsoft::WRL::ComPtr<IMFMediaBuffer>::~ComPtr<IMFMediaBuffer>(_QWORD *a1)
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
0x180001f48  sub     rsp, 28h
0x180001f4c  mov     rax, rcx
0x180001f4f  mov     rcx, [rcx]
0x180001f52  test    rcx, rcx
0x180001f55  jz      short loc_180001F6B
0x180001f57  mov     qword ptr [rax], 0
0x180001f5e  mov     rax, [rcx]
0x180001f61  mov     rax, [rax+10h]
0x180001f65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f6a  nop
0x180001f6b  add     rsp, 28h
0x180001f6f  retn
```
