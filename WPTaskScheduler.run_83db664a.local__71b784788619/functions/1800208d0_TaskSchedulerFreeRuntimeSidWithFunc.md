# TaskSchedulerFreeRuntimeSidWithFunc

- ea: `0x1800208d0`
- end: `0x1800208f8`
- name: `TaskSchedulerFreeRuntimeSidWithFunc`
- size: `40`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, service_task`

## callers

- `0x180020860`
- `0x1800209f8`

## callees

- `0x18000eea0`
- `0x1800208d0`

## pseudocode

```c
void __fastcall TaskSchedulerFreeRuntimeSidWithFunc(void **a1)
{
  void *v2; // rcx

  if ( a1 )
  {
    v2 = *a1;
    if ( v2 )
      MIDL_user_free(v2);
    MIDL_user_free(a1);
  }
}

```

## disassembly

```asm
0x1800208d0  test    rcx, rcx
0x1800208d3  jz      short locret_1800208F7
0x1800208d5  push    rbx
0x1800208d6  sub     rsp, 20h
0x1800208da  mov     rbx, rcx
0x1800208dd  mov     rcx, [rcx]; void *
0x1800208e0  test    rcx, rcx
0x1800208e3  jz      short loc_1800208EA
0x1800208e5  call    MIDL_user_free
0x1800208ea  mov     rcx, rbx; void *
0x1800208ed  call    MIDL_user_free
0x1800208f2  add     rsp, 20h
0x1800208f6  pop     rbx
0x1800208f7  retn
```
