# _lambda_ea734d1cec1fa7b22a66fb865ad05d37_::_lambda_ea734d1cec1fa7b22a66fb865ad05d37_(CreateObjectServerTaskBase *,Microsoft::WRL::ComPtr<ITaskHandler> const &,Microsoft::WRL::ComPtr<ITaskHandlerStatus> const &)

- ea: `0x140007158`
- end: `0x1400071a1`
- name: `??0_lambda_ea734d1cec1fa7b22a66fb865ad05d37_@@QEAA@PEAVCreateObjectServerTaskBase@@AEBV?$ComPtr@UITaskHandler@@@WRL@Microsoft@@AEBV?$ComPtr@UITaskHandlerStatus@@@34@@Z`
- size: `73`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, _QWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140008a10`

## callees

- `0x140007158`
- `0x140007fec`
- `0x14000a010`

## pseudocode

```c
_QWORD *__fastcall _lambda_ea734d1cec1fa7b22a66fb865ad05d37_::_lambda_ea734d1cec1fa7b22a66fb865ad05d37_(
        _QWORD *a1,
        __int64 a2,
        _QWORD *a3,
        __int64 *a4)
{
  _QWORD *v6; // rcx
  __int64 v7; // rcx

  *a1 = a2;
  v6 = a1 + 1;
  *v6 = *a3;
  Microsoft::WRL::ComPtr<ITaskHandler>::InternalAddRef(v6);
  v7 = *a4;
  a1[2] = *a4;
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
  return a1;
}

```

## disassembly

```asm
0x140007158  mov     [rsp+arg_0], rbx
0x14000715d  push    rdi
0x14000715e  sub     rsp, 20h
0x140007162  mov     rbx, r9
0x140007165  mov     rdi, rcx
0x140007168  mov     [rcx], rdx
0x14000716b  add     rcx, 8
0x14000716f  mov     rax, [r8]
0x140007172  mov     [rcx], rax
0x140007175  call    ?InternalAddRef@?$ComPtr@UITaskHandler@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<ITaskHandler>::InternalAddRef(void)
0x14000717a  mov     rcx, [rbx]
0x14000717d  mov     [rdi+10h], rcx
0x140007181  test    rcx, rcx
0x140007184  jz      short loc_140007193
0x140007186  mov     rax, [rcx]
0x140007189  mov     rax, [rax+8]
0x14000718d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007192  nop
0x140007193  mov     rax, rdi
0x140007196  mov     rbx, [rsp+28h+arg_0]
0x14000719b  add     rsp, 20h
0x14000719f  pop     rdi
0x1400071a0  retn
```
