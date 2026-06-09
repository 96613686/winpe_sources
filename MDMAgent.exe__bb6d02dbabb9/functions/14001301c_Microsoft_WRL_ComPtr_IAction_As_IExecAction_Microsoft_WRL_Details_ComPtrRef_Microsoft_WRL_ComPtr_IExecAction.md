# Microsoft::WRL::ComPtr<IAction>::As<IExecAction>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IExecAction>>)

- ea: `0x14001301c`
- end: `0x140013066`
- name: `??$As@UIExecAction@@@?$ComPtr@UIAction@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIExecAction@@@WRL@Microsoft@@@Details@12@@Z`
- size: `74`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14001351c`
- `0x1400151d8`

## callees

- `0x140006098`
- `0x14001a010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<IAction>::As<IExecAction>(
        __int64 (__fastcall ****a1)(_QWORD, GUID *, __int64 *),
        __int64 *a2)
{
  __int64 (__fastcall ***v3)(_QWORD, GUID *, __int64 *); // rsi
  __int64 (__fastcall *v4)(_QWORD, GUID *, __int64 *); // rdi

  v3 = *a1;
  v4 = ***a1;
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(a2);
  return v4(v3, &GUID_4c3d624d_fd6b_49a3_b9b7_09cb3cd3f047, a2);
}

```

## disassembly

```asm
0x14001301c  mov     [rsp+arg_0], rbx
0x140013021  mov     [rsp+arg_8], rsi
0x140013026  push    rdi
0x140013027  sub     rsp, 20h
0x14001302b  mov     rbx, rdx
0x14001302e  mov     rsi, [rcx]
0x140013031  mov     rax, [rsi]
0x140013034  mov     rdi, [rax]
0x140013037  mov     rcx, rdx
0x14001303a  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x14001303f  mov     r8, rbx
0x140013042  lea     rdx, _GUID_4c3d624d_fd6b_49a3_b9b7_09cb3cd3f047
0x140013049  mov     rcx, rsi
0x14001304c  mov     rax, rdi
0x14001304f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013054  nop
0x140013055  mov     rbx, [rsp+28h+arg_0]
0x14001305a  mov     rsi, [rsp+28h+arg_8]
0x14001305f  add     rsp, 20h
0x140013063  pop     rdi
0x140013064  retn
```
