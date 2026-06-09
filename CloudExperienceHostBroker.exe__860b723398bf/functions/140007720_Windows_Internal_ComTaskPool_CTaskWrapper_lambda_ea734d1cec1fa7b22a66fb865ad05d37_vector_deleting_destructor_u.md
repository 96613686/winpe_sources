# Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_ea734d1cec1fa7b22a66fb865ad05d37_>::`vector deleting destructor'(uint)

- ea: `0x140007720`
- end: `0x140007750`
- name: `??_E?$CTaskWrapper@V_lambda_ea734d1cec1fa7b22a66fb865ad05d37_@@@ComTaskPool@Internal@Windows@@UEAAPEAXI@Z`
- size: `48`
- prototype: `void *__fastcall(void *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x14000732c`
- `0x140007720`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x14000773c`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000773c`

## pseudocode

```c
void *__fastcall Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_ea734d1cec1fa7b22a66fb865ad05d37_>::`vector deleting destructor'(
        void *a1,
        char a2)
{
  Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_ea734d1cec1fa7b22a66fb865ad05d37_>::~CTaskWrapper<_lambda_ea734d1cec1fa7b22a66fb865ad05d37_>((__int64)a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x140007720  mov     [rsp+arg_0], rbx
0x140007725  push    rdi
0x140007726  sub     rsp, 20h
0x14000772a  mov     ebx, edx
0x14000772c  mov     rdi, rcx
0x14000772f  call    ??1?$CTaskWrapper@V_lambda_ea734d1cec1fa7b22a66fb865ad05d37_@@@ComTaskPool@Internal@Windows@@UEAA@XZ; Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_ea734d1cec1fa7b22a66fb865ad05d37_>::~CTaskWrapper<_lambda_ea734d1cec1fa7b22a66fb865ad05d37_>(void)
0x140007734  test    bl, 1
0x140007737  jz      short loc_140007742
0x140007739  mov     rcx, rdi
0x14000773c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140007742  mov     rbx, [rsp+28h+arg_0]
0x140007747  mov     rax, rdi
0x14000774a  add     rsp, 20h
0x14000774e  pop     rdi
0x14000774f  retn
```
