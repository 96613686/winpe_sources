# Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_ea734d1cec1fa7b22a66fb865ad05d37_>::~CTaskWrapper<_lambda_ea734d1cec1fa7b22a66fb865ad05d37_>(void)

- ea: `0x14000732c`
- end: `0x14000734b`
- name: `??1?$CTaskWrapper@V_lambda_ea734d1cec1fa7b22a66fb865ad05d37_@@@ComTaskPool@Internal@Windows@@UEAA@XZ`
- size: `31`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x140007720`

## callees

- `0x1400072ec`

## pseudocode

```c
void __fastcall Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_ea734d1cec1fa7b22a66fb865ad05d37_>::~CTaskWrapper<_lambda_ea734d1cec1fa7b22a66fb865ad05d37_>(
        __int64 a1)
{
  _lambda_ea734d1cec1fa7b22a66fb865ad05d37_::~_lambda_ea734d1cec1fa7b22a66fb865ad05d37_((_lambda_ea734d1cec1fa7b22a66fb865ad05d37_ *)(a1 + 16));
  *(_DWORD *)(a1 + 12) = -1073741823;
}

```

## disassembly

```asm
0x14000732c  push    rbx
0x14000732e  sub     rsp, 20h
0x140007332  mov     rbx, rcx
0x140007335  add     rcx, 10h; this
0x140007339  call    ??1_lambda_ea734d1cec1fa7b22a66fb865ad05d37_@@QEAA@XZ; _lambda_ea734d1cec1fa7b22a66fb865ad05d37_::~_lambda_ea734d1cec1fa7b22a66fb865ad05d37_(void)
0x14000733e  mov     dword ptr [rbx+0Ch], 0C0000001h
0x140007345  add     rsp, 20h
0x140007349  pop     rbx
0x14000734a  retn
```
