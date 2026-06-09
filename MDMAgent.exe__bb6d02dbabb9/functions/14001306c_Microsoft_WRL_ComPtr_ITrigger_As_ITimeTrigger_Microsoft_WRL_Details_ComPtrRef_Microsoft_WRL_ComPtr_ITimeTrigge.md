# Microsoft::WRL::ComPtr<ITrigger>::As<ITimeTrigger>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ITimeTrigger>>)

- ea: `0x14001306c`
- end: `0x1400130b6`
- name: `??$As@UITimeTrigger@@@?$ComPtr@UITrigger@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UITimeTrigger@@@WRL@Microsoft@@@Details@12@@Z`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400151d8`

## callees

- `0x140006098`
- `0x14001a010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<ITrigger>::As<ITimeTrigger>(
        __int64 (__fastcall ****a1)(_QWORD, GUID *, __int64 *),
        __int64 *a2)
{
  __int64 (__fastcall ***v3)(_QWORD, GUID *, __int64 *); // rsi
  __int64 (__fastcall *v4)(_QWORD, GUID *, __int64 *); // rdi

  v3 = *a1;
  v4 = ***a1;
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(a2);
  return v4(v3, &GUID_b45747e0_eba7_4276_9f29_85c5bb300006, a2);
}

```

## disassembly

```asm
0x14001306c  mov     [rsp+arg_0], rbx
0x140013071  mov     [rsp+arg_8], rsi
0x140013076  push    rdi
0x140013077  sub     rsp, 20h
0x14001307b  mov     rbx, rdx
0x14001307e  mov     rsi, [rcx]
0x140013081  mov     rax, [rsi]
0x140013084  mov     rdi, [rax]
0x140013087  mov     rcx, rdx
0x14001308a  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x14001308f  mov     r8, rbx
0x140013092  lea     rdx, _GUID_b45747e0_eba7_4276_9f29_85c5bb300006
0x140013099  mov     rcx, rsi
0x14001309c  mov     rax, rdi
0x14001309f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400130a4  nop
0x1400130a5  mov     rbx, [rsp+28h+arg_0]
0x1400130aa  mov     rsi, [rsp+28h+arg_8]
0x1400130af  add     rsp, 20h
0x1400130b3  pop     rdi
0x1400130b4  retn
```
