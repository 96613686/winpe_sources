# Microsoft::WRL::ComPtr<ITrigger>::As<IWnfStateChangeTrigger>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IWnfStateChangeTrigger>>)

- ea: `0x1400127a4`
- end: `0x1400127ed`
- name: `??$As@UIWnfStateChangeTrigger@@@?$ComPtr@UITrigger@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWnfStateChangeTrigger@@@WRL@Microsoft@@@Details@12@@Z`
- size: `73`
- prototype: `__int64 __fastcall(__int64 (__fastcall ****)(_QWORD, GUID *, __int64), __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140012bd0`

## callees

- `0x140005e94`
- `0x140019010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<ITrigger>::As<IWnfStateChangeTrigger>(
        __int64 (__fastcall ****a1)(_QWORD, GUID *, __int64),
        __int64 a2)
{
  __int64 (__fastcall ***v3)(_QWORD, GUID *, __int64); // rsi
  __int64 (__fastcall *v4)(_QWORD, GUID *, __int64); // rdi

  v3 = *a1;
  v4 = ***a1;
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(a2);
  return v4(v3, &GUID_2d92bf38_0538_477b_b4d4_6c8e1dc9484f, a2);
}

```

## disassembly

```asm
0x1400127a4  mov     [rsp+arg_0], rbx
0x1400127a9  mov     [rsp+arg_8], rsi
0x1400127ae  push    rdi
0x1400127af  sub     rsp, 20h
0x1400127b3  mov     rbx, rdx
0x1400127b6  mov     rsi, [rcx]
0x1400127b9  mov     rax, [rsi]
0x1400127bc  mov     rdi, [rax]
0x1400127bf  mov     rcx, rdx
0x1400127c2  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1400127c7  mov     r8, rbx
0x1400127ca  lea     rdx, _GUID_2d92bf38_0538_477b_b4d4_6c8e1dc9484f
0x1400127d1  mov     rcx, rsi
0x1400127d4  mov     rax, rdi
0x1400127d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400127dc  nop
0x1400127dd  mov     rbx, [rsp+28h+arg_0]
0x1400127e2  mov     rsi, [rsp+28h+arg_8]
0x1400127e7  add     rsp, 20h
0x1400127eb  pop     rdi
0x1400127ec  retn
```
