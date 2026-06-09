# TaskSchedulerFreeRuntimeAppContainerSecInfoWithFunc

- ea: `0x180020860`
- end: `0x1800208c9`
- name: `TaskSchedulerFreeRuntimeAppContainerSecInfoWithFunc`
- size: `105`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800209f8`

## callees

- `0x18000eea0`
- `0x180020860`
- `0x1800208d0`

## pseudocode

```c
void __fastcall TaskSchedulerFreeRuntimeAppContainerSecInfoWithFunc(void **a1)
{
  void ***v2; // rsi
  void **v3; // rdi
  int v4; // eax

  if ( a1 )
  {
    TaskSchedulerFreeRuntimeSidWithFunc(*a1);
    v2 = (void ***)a1[1];
    if ( *((_DWORD *)a1 + 4) )
    {
      do
      {
        v3 = *v2;
        if ( *v2 )
          TaskSchedulerFreeRuntimeSidWithFunc(*v3);
        MIDL_user_free(v3);
        ++v2;
        v4 = *((_DWORD *)a1 + 4) - 1;
        *((_DWORD *)a1 + 4) = v4;
      }
      while ( v4 );
    }
    MIDL_user_free(a1);
  }
}

```

## disassembly

```asm
0x180020860  test    rcx, rcx
0x180020863  jz      short locret_1800208C8
0x180020865  mov     [rsp+arg_0], rbx
0x18002086a  mov     [rsp+arg_8], rsi
0x18002086f  push    rdi
0x180020870  sub     rsp, 20h
0x180020874  mov     rbx, rcx
0x180020877  mov     rcx, [rcx]; void *
0x18002087a  call    TaskSchedulerFreeRuntimeSidWithFunc
0x18002087f  cmp     dword ptr [rbx+10h], 0
0x180020883  mov     rsi, [rbx+8]
0x180020887  jbe     short loc_1800208B1
0x180020889  mov     rdi, [rsi]
0x18002088c  test    rdi, rdi
0x18002088f  jz      short loc_180020899
0x180020891  mov     rcx, [rdi]; void *
0x180020894  call    TaskSchedulerFreeRuntimeSidWithFunc
0x180020899  mov     rcx, rdi; void *
0x18002089c  call    MIDL_user_free
0x1800208a1  mov     eax, [rbx+10h]
0x1800208a4  add     rsi, 8
0x1800208a8  dec     eax
0x1800208aa  mov     [rbx+10h], eax
0x1800208ad  test    eax, eax
0x1800208af  jnz     short loc_180020889
0x1800208b1  mov     rcx, rbx; void *
0x1800208b4  call    MIDL_user_free
0x1800208b9  mov     rbx, [rsp+28h+arg_0]
0x1800208be  mov     rsi, [rsp+28h+arg_8]
0x1800208c3  add     rsp, 20h
0x1800208c7  pop     rdi
0x1800208c8  retn
```
