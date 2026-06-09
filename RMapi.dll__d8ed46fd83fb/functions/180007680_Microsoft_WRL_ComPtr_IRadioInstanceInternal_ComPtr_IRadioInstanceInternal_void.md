# Microsoft::WRL::ComPtr<IRadioInstanceInternal>::~ComPtr<IRadioInstanceInternal>(void)

- ea: `0x180007680`
- end: `0x1800076a8`
- name: `??1?$ComPtr@UIRadioInstanceInternal@@@WRL@Microsoft@@QEAA@XZ`
- size: `40`
- prototype: ``
- caller_count: `22`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800251b0`
- `0x180025280`
- `0x1800253d0`
- `0x18002565f`
- `0x180025671`
- `0x1800257cc`
- `0x180025802`
- `0x180025a88`
- `0x180025ad8`
- `0x180025b30`
- `0x180025cfd`
- `0x180025d6f`
- `0x1800262e3`
- `0x18002640e`
- `0x180026420`
- `0x180026444`
- `0x180026468`
- `0x18002656a`
- `0x1800267b5`
- `0x1800267d9`
- `0x180026a2f`
- `0x180026bd9`

## callees

- `0x180007680`
- `0x180028010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Microsoft::WRL::ComPtr<IRadioInstanceInternal>::~ComPtr<IRadioInstanceInternal>(_QWORD *a1)
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
0x180007680  sub     rsp, 28h
0x180007684  mov     rax, rcx
0x180007687  mov     rcx, [rcx]
0x18000768a  test    rcx, rcx
0x18000768d  jz      short loc_1800076A3
0x18000768f  mov     qword ptr [rax], 0
0x180007696  mov     rax, [rcx]
0x180007699  mov     rax, [rax+10h]
0x18000769d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076a2  nop
0x1800076a3  add     rsp, 28h
0x1800076a7  retn
```
