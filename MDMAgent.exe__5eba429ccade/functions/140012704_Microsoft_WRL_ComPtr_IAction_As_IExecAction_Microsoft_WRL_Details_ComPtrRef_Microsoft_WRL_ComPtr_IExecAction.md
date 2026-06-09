# Microsoft::WRL::ComPtr<IAction>::As<IExecAction>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IExecAction>>)

- ea: `0x140012704`
- end: `0x14001274d`
- name: `??$As@UIExecAction@@@?$ComPtr@UIAction@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIExecAction@@@WRL@Microsoft@@@Details@12@@Z`
- size: `73`
- prototype: `__int64 __fastcall(__int64 (__fastcall ****)(_QWORD, GUID *, __int64), __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140012bd0`
- `0x14001464c`

## callees

- `0x140005e94`
- `0x140019010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<IAction>::As<IExecAction>(
        __int64 (__fastcall ****a1)(_QWORD, GUID *, __int64),
        __int64 a2)
{
  __int64 (__fastcall ***v3)(_QWORD, GUID *, __int64); // rsi
  __int64 (__fastcall *v4)(_QWORD, GUID *, __int64); // rdi

  v3 = *a1;
  v4 = ***a1;
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(a2);
  return v4(v3, &GUID_4c3d624d_fd6b_49a3_b9b7_09cb3cd3f047, a2);
}

```

## disassembly

```asm
0x140012704  mov     [rsp+arg_0], rbx
0x140012709  mov     [rsp+arg_8], rsi
0x14001270e  push    rdi
0x14001270f  sub     rsp, 20h
0x140012713  mov     rbx, rdx
0x140012716  mov     rsi, [rcx]
0x140012719  mov     rax, [rsi]
0x14001271c  mov     rdi, [rax]
0x14001271f  mov     rcx, rdx
0x140012722  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x140012727  mov     r8, rbx
0x14001272a  lea     rdx, _GUID_4c3d624d_fd6b_49a3_b9b7_09cb3cd3f047
0x140012731  mov     rcx, rsi
0x140012734  mov     rax, rdi
0x140012737  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001273c  nop
0x14001273d  mov     rbx, [rsp+28h+arg_0]
0x140012742  mov     rsi, [rsp+28h+arg_8]
0x140012747  add     rsp, 20h
0x14001274b  pop     rdi
0x14001274c  retn
```
