# Microsoft::WRL::ComPtr<ICommandHandler>::~ComPtr<ICommandHandler>(void)

- ea: `0x180005ab4`
- end: `0x180005adc`
- name: `??1?$ComPtr@UICommandHandler@@@WRL@Microsoft@@QEAA@XZ`
- size: `40`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `17`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180028d19`
- `0x180028d61`
- `0x1800291e1`
- `0x1800292f1`
- `0x18002934b`
- `0x1800293a5`
- `0x1800293b7`
- `0x18002947e`
- `0x180029490`
- `0x1800294b4`
- `0x1800294c6`
- `0x1800295af`
- `0x180029a90`
- `0x180029be6`
- `0x180029bf8`
- `0x180029c65`
- `0x180029cf9`

## callees

- `0x180005ab4`
- `0x18002a010`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::ComPtr<ICommandHandler>::~ComPtr<ICommandHandler>(_QWORD *a1)
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
0x180005ab4  sub     rsp, 28h
0x180005ab8  mov     rax, rcx
0x180005abb  mov     rcx, [rcx]
0x180005abe  test    rcx, rcx
0x180005ac1  jz      short loc_180005AD7
0x180005ac3  mov     qword ptr [rax], 0
0x180005aca  mov     rax, [rcx]
0x180005acd  mov     rax, [rax+10h]
0x180005ad1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ad6  nop
0x180005ad7  add     rsp, 28h
0x180005adb  retn
```
