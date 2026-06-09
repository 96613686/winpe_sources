# Microsoft::WRL::ComPtr<ITrigger>::As<ITimeTrigger>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ITimeTrigger>>)

- ea: `0x140012754`
- end: `0x14001279d`
- name: `??$As@UITimeTrigger@@@?$ComPtr@UITrigger@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UITimeTrigger@@@WRL@Microsoft@@@Details@12@@Z`
- size: `73`
- prototype: `__int64 __fastcall(__int64 (__fastcall ****)(_QWORD, GUID *, __int64), __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14001464c`

## callees

- `0x140005e94`
- `0x140019010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<ITrigger>::As<ITimeTrigger>(
        __int64 (__fastcall ****a1)(_QWORD, GUID *, __int64),
        __int64 a2)
{
  __int64 (__fastcall ***v3)(_QWORD, GUID *, __int64); // rsi
  __int64 (__fastcall *v4)(_QWORD, GUID *, __int64); // rdi

  v3 = *a1;
  v4 = ***a1;
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(a2);
  return v4(v3, &GUID_b45747e0_eba7_4276_9f29_85c5bb300006, a2);
}

```

## disassembly

```asm
0x140012754  mov     [rsp+arg_0], rbx
0x140012759  mov     [rsp+arg_8], rsi
0x14001275e  push    rdi
0x14001275f  sub     rsp, 20h
0x140012763  mov     rbx, rdx
0x140012766  mov     rsi, [rcx]
0x140012769  mov     rax, [rsi]
0x14001276c  mov     rdi, [rax]
0x14001276f  mov     rcx, rdx
0x140012772  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x140012777  mov     r8, rbx
0x14001277a  lea     rdx, _GUID_b45747e0_eba7_4276_9f29_85c5bb300006
0x140012781  mov     rcx, rsi
0x140012784  mov     rax, rdi
0x140012787  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001278c  nop
0x14001278d  mov     rbx, [rsp+28h+arg_0]
0x140012792  mov     rsi, [rsp+28h+arg_8]
0x140012797  add     rsp, 20h
0x14001279b  pop     rdi
0x14001279c  retn
```
