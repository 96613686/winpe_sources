# Microsoft::WRL::ComPtr<IPopupWindowFactory>::~ComPtr<IPopupWindowFactory>(void)

- ea: `0x1400031c4`
- end: `0x1400031ec`
- name: `??1?$ComPtr@UIPopupWindowFactory@@@WRL@Microsoft@@QEAA@XZ`
- size: `40`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400093f1`
- `0x140009403`
- `0x140009481`
- `0x1400098de`
- `0x1400098f0`
- `0x140009902`

## callees

- `0x1400031c4`
- `0x14000a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Microsoft::WRL::ComPtr<IPopupWindowFactory>::~ComPtr<IPopupWindowFactory>(_QWORD *a1)
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
0x1400031c4  sub     rsp, 28h
0x1400031c8  mov     rax, rcx
0x1400031cb  mov     rcx, [rcx]
0x1400031ce  test    rcx, rcx
0x1400031d1  jz      short loc_1400031E7
0x1400031d3  mov     qword ptr [rax], 0
0x1400031da  mov     rax, [rcx]
0x1400031dd  mov     rax, [rax+10h]
0x1400031e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400031e6  nop
0x1400031e7  add     rsp, 28h
0x1400031eb  retn
```
