# Microsoft::WRL::ComPtr<IWICBitmapFrameEncode>::~ComPtr<IWICBitmapFrameEncode>(void)

- ea: `0x18000f068`
- end: `0x18000f090`
- name: `??1?$ComPtr@UIWICBitmapFrameEncode@@@WRL@Microsoft@@QEAA@XZ`
- size: `40`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002a800`
- `0x18002a812`
- `0x18002a824`
- `0x18002a836`
- `0x18002aadc`
- `0x18002aaee`
- `0x18002ab00`

## callees

- `0x18000f068`
- `0x18002d010`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::ComPtr<IWICBitmapFrameEncode>::~ComPtr<IWICBitmapFrameEncode>(_QWORD *a1)
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
0x18000f068  sub     rsp, 28h
0x18000f06c  mov     rax, rcx
0x18000f06f  mov     rcx, [rcx]
0x18000f072  test    rcx, rcx
0x18000f075  jz      short loc_18000F08B
0x18000f077  mov     qword ptr [rax], 0
0x18000f07e  mov     rax, [rcx]
0x18000f081  mov     rax, [rax+10h]
0x18000f085  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f08a  nop
0x18000f08b  add     rsp, 28h
0x18000f08f  retn
```
