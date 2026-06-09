# IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ITaskService>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ITaskService>>)

- ea: `0x1400022c8`
- end: `0x1400022f6`
- name: `??$IID_PPV_ARGS_Helper@V?$ComPtr@UITaskService@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UITaskService@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z`
- size: `46`
- prototype: `__int64 *__fastcall(__int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400045f0`
- `0x140009de4`

## callees

- `0x1400022c8`
- `0x140010010`

## pseudocode

```c
__int64 *__fastcall IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ITaskService>>(__int64 *a1)
{
  __int64 v2; // rcx

  v2 = *a1;
  if ( v2 )
  {
    *a1 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  return a1;
}

```

## disassembly

```asm
0x1400022c8  push    rbx
0x1400022ca  sub     rsp, 20h
0x1400022ce  mov     rbx, rcx
0x1400022d1  mov     rcx, [rcx]
0x1400022d4  test    rcx, rcx
0x1400022d7  jz      short loc_1400022ED
0x1400022d9  mov     qword ptr [rbx], 0
0x1400022e0  mov     rax, [rcx]
0x1400022e3  mov     rax, [rax+10h]
0x1400022e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400022ec  nop
0x1400022ed  mov     rax, rbx
0x1400022f0  add     rsp, 20h
0x1400022f4  pop     rbx
0x1400022f5  retn
```
