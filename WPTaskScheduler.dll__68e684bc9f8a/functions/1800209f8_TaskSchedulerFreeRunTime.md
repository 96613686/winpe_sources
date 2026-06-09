# TaskSchedulerFreeRunTime

- ea: `0x1800209f8`
- end: `0x180020a25`
- name: `TaskSchedulerFreeRunTime`
- size: `45`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180017e48`
- `0x18001efc8`
- `0x18001f3ec`
- `0x18001f65c`

## callees

- `0x18000eea0`
- `0x180020860`
- `0x1800208d0`
- `0x1800209f8`

## pseudocode

```c
void __fastcall TaskSchedulerFreeRunTime(void **a1)
{
  if ( a1 )
  {
    TaskSchedulerFreeRuntimeSidWithFunc(a1[2]);
    TaskSchedulerFreeRuntimeAppContainerSecInfoWithFunc(a1[3]);
    MIDL_user_free(a1);
  }
}

```

## disassembly

```asm
0x1800209f8  test    rcx, rcx
0x1800209fb  jz      short locret_180020A24
0x1800209fd  push    rbx
0x1800209fe  sub     rsp, 20h
0x180020a02  mov     rbx, rcx
0x180020a05  mov     rcx, [rcx+10h]; void *
0x180020a09  call    TaskSchedulerFreeRuntimeSidWithFunc
0x180020a0e  mov     rcx, [rbx+18h]; void *
0x180020a12  call    TaskSchedulerFreeRuntimeAppContainerSecInfoWithFunc
0x180020a17  mov     rcx, rbx; void *
0x180020a1a  call    MIDL_user_free
0x180020a1f  add     rsp, 20h
0x180020a23  pop     rbx
0x180020a24  retn
```
