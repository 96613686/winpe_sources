# Microsoft::WRL::Details::Make<MapsBrokerAsyncOperation,long (*)(_RPC_ASYNC_STATE *)>(long (*&&)(_RPC_ASYNC_STATE *))

- ea: `0x180007fc0`
- end: `0x18000804c`
- name: `??$Make@VMapsBrokerAsyncOperation@@P6AJPEAU_RPC_ASYNC_STATE@@@Z@Details@WRL@Microsoft@@YA?AV?$ComPtr@VMapsBrokerAsyncOperation@@@12@$$QEAP6AJPEAU_RPC_ASYNC_STATE@@@Z@Z`
- size: `140`
- prototype: `MapsBrokerAsyncOperation **__fastcall(MapsBrokerAsyncOperation **, int (**)(struct _RPC_ASYNC_STATE *))`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180009f30`
- `0x18000a3f0`

## callees

- `0x180002534`
- `0x180002990`
- `0x1800077bc`
- `0x180007d70`
- `0x180007fc0`

## pseudocode

```c
MapsBrokerAsyncOperation **__fastcall Microsoft::WRL::Details::Make<MapsBrokerAsyncOperation,long (*)(_RPC_ASYNC_STATE *)>(
        MapsBrokerAsyncOperation **a1,
        int (**a2)(struct _RPC_ASYNC_STATE *))
{
  MapsBrokerAsyncOperation *v4; // rax
  MapsBrokerAsyncOperation *v5; // rdi

  *a1 = 0;
  v4 = (MapsBrokerAsyncOperation *)operator new(0x98u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v4 )
  {
    v5 = MapsBrokerAsyncOperation::MapsBrokerAsyncOperation(v4, *a2);
    if ( *a1 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMapsBrokerAsyncOperation>::Release(*a1);
    *a1 = v5;
  }
  return a1;
}

```

## disassembly

```asm
0x180007fc0  mov     rax, rsp
0x180007fc3  mov     [rax+10h], rbx
0x180007fc7  mov     [rax+8], rcx
0x180007fcb  push    rdi
0x180007fcc  sub     rsp, 30h
0x180007fd0  mov     rdi, rdx
0x180007fd3  mov     rbx, rcx
0x180007fd6  mov     dword ptr [rax-18h], 0
0x180007fdd  mov     qword ptr [rcx], 0
0x180007fe4  mov     dword ptr [rax-18h], 1
0x180007feb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180007ff2  mov     ecx, 98h; unsigned __int64
0x180007ff7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180007ffc  mov     [rsp+38h+arg_10], rax
0x180008001  mov     [rsp+38h+arg_18], rax
0x180008006  test    rax, rax
0x180008009  jz      short loc_180008030
0x18000800b  mov     [rsp+38h+var_10], rax
0x180008010  mov     rdx, [rdi]; int (*)(struct _RPC_ASYNC_STATE *)
0x180008013  mov     rcx, rax; this
0x180008016  call    ??0MapsBrokerAsyncOperation@@QEAA@P6AJPEAU_RPC_ASYNC_STATE@@@Z@Z; MapsBrokerAsyncOperation::MapsBrokerAsyncOperation(long (*)(_RPC_ASYNC_STATE *))
0x18000801b  mov     rdi, rax
0x18000801e  mov     rcx, [rbx]
0x180008021  test    rcx, rcx
0x180008024  jz      short loc_18000802B
0x180008026  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIMapsBrokerAsyncOperation@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMapsBrokerAsyncOperation>::Release(void)
0x18000802b  mov     [rbx], rdi
0x18000802e  xor     eax, eax
0x180008030  test    rax, rax
0x180008033  jz      short loc_18000803D
0x180008035  mov     rcx, rax; Block
0x180008038  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000803d  mov     rax, rbx
0x180008040  mov     rbx, [rsp+38h+arg_8]
0x180008045  add     rsp, 30h
0x180008049  pop     rdi
0x18000804a  retn
```
