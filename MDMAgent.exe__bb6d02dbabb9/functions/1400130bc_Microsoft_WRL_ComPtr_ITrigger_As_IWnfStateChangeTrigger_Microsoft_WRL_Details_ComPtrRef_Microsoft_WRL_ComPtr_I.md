# Microsoft::WRL::ComPtr<ITrigger>::As<IWnfStateChangeTrigger>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IWnfStateChangeTrigger>>)

- ea: `0x1400130bc`
- end: `0x140013106`
- name: `??$As@UIWnfStateChangeTrigger@@@?$ComPtr@UITrigger@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWnfStateChangeTrigger@@@WRL@Microsoft@@@Details@12@@Z`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14001351c`

## callees

- `0x140006098`
- `0x14001a010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<ITrigger>::As<IWnfStateChangeTrigger>(
        __int64 (__fastcall ****a1)(_QWORD, GUID *, __int64 *),
        __int64 *a2)
{
  __int64 (__fastcall ***v3)(_QWORD, GUID *, __int64 *); // rsi
  __int64 (__fastcall *v4)(_QWORD, GUID *, __int64 *); // rdi

  v3 = *a1;
  v4 = ***a1;
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(a2);
  return v4(v3, &GUID_2d92bf38_0538_477b_b4d4_6c8e1dc9484f, a2);
}

```

## disassembly

```asm
0x1400130bc  mov     [rsp+arg_0], rbx
0x1400130c1  mov     [rsp+arg_8], rsi
0x1400130c6  push    rdi
0x1400130c7  sub     rsp, 20h
0x1400130cb  mov     rbx, rdx
0x1400130ce  mov     rsi, [rcx]
0x1400130d1  mov     rax, [rsi]
0x1400130d4  mov     rdi, [rax]
0x1400130d7  mov     rcx, rdx
0x1400130da  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1400130df  mov     r8, rbx
0x1400130e2  lea     rdx, _GUID_2d92bf38_0538_477b_b4d4_6c8e1dc9484f
0x1400130e9  mov     rcx, rsi
0x1400130ec  mov     rax, rdi
0x1400130ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400130f4  nop
0x1400130f5  mov     rbx, [rsp+28h+arg_0]
0x1400130fa  mov     rsi, [rsp+28h+arg_8]
0x1400130ff  add     rsp, 20h
0x140013103  pop     rdi
0x140013104  retn
```
