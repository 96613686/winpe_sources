# Windows::Internal::ComTaskPool::QueueTask__lambda_e9a4aa2ff6130b9b99ec1f5755b266bd__&_

- ea: `0x1800bc744`
- end: `0x1800bc7da`
- name: `Windows::Internal::ComTaskPool::QueueTask__lambda_e9a4aa2ff6130b9b99ec1f5755b266bd__&_`
- size: `150`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800c0b9c`

## callees

- `0x18000525c`
- `0x1800bb854`
- `0x1800bc744`
- `0x1800bfc6c`
- `0x1800fb010`

## import_xrefs

- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x1800bc7ae`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x1800bc7ae`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::ComTaskPool::QueueTask__lambda_e9a4aa2ff6130b9b99ec1f5755b266bd____(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4)
{
  void *v7; // rax
  __int64 v8; // rbx
  unsigned int v9; // edi
  void *v11; // [rsp+30h] [rbp-28h] BYREF

  v7 = operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
  v11 = v7;
  v8 = 0;
  if ( v7 )
  {
    v8 = Windows::Internal::ComTaskPool::CTaskWrapper__lambda_e9a4aa2ff6130b9b99ec1f5755b266bd____::CTaskWrapper__lambda_e9a4aa2ff6130b9b99ec1f5755b266bd______lambda_e9a4aa2ff6130b9b99ec1f5755b266bd____(
           v7,
           a4);
    v11 = 0;
  }
  Microsoft::WRL::Details::MakeAllocator_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_e9a4aa2ff6130b9b99ec1f5755b266bd______::_MakeAllocator_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_e9a4aa2ff6130b9b99ec1f5755b266bd______(&v11);
  v9 = SHTaskPoolQueueTask(0, a2, a3, 0, v8, 0, v11);
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  return v9;
}

```

## disassembly

```asm
0x1800bc744  mov     [rsp+arg_0], rbx
0x1800bc749  push    rbp
0x1800bc74a  push    rsi
0x1800bc74b  push    rdi
0x1800bc74c  sub     rsp, 40h
0x1800bc750  mov     rdi, r9
0x1800bc753  mov     ebp, r8d
0x1800bc756  mov     esi, edx
0x1800bc758  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800bc75f  mov     ecx, 30h ; '0'; unsigned __int64
0x1800bc764  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800bc769  mov     [rsp+58h+var_28], rax
0x1800bc76e  xor     ebx, ebx
0x1800bc770  test    rax, rax
0x1800bc773  jz      short loc_1800BC78C
0x1800bc775  mov     rdx, rdi
0x1800bc778  mov     rcx, rax
0x1800bc77b  call    Windows__Internal__ComTaskPool__CTaskWrapper__lambda_e9a4aa2ff6130b9b99ec1f5755b266bd______CTaskWrapper__lambda_e9a4aa2ff6130b9b99ec1f5755b266bd______lambda_e9a4aa2ff6130b9b99ec1f5755b266bd____
0x1800bc780  mov     rbx, rax
0x1800bc783  mov     [rsp+58h+var_28], 0
0x1800bc78c  lea     rcx, [rsp+58h+var_28]
0x1800bc791  call    Microsoft__WRL__Details__MakeAllocator_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_e9a4aa2ff6130b9b99ec1f5755b266bd_________MakeAllocator_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_e9a4aa2ff6130b9b99ec1f5755b266bd______
0x1800bc796  mov     [rsp+58h+var_30], 0
0x1800bc79f  mov     [rsp+58h+var_38], rbx
0x1800bc7a4  xor     r9d, r9d
0x1800bc7a7  mov     r8d, ebp
0x1800bc7aa  mov     edx, esi
0x1800bc7ac  xor     ecx, ecx
0x1800bc7ae  call    cs:__imp_SHTaskPoolQueueTask
0x1800bc7b4  mov     edi, eax
0x1800bc7b6  test    rbx, rbx
0x1800bc7b9  jz      short loc_1800BC7CB
0x1800bc7bb  mov     rdx, [rbx]
0x1800bc7be  mov     rcx, rbx
0x1800bc7c1  mov     rax, [rdx+10h]
0x1800bc7c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc7ca  nop
0x1800bc7cb  mov     eax, edi
0x1800bc7cd  mov     rbx, [rsp+58h+arg_0]
0x1800bc7d2  add     rsp, 40h
0x1800bc7d6  pop     rdi
0x1800bc7d7  pop     rsi
0x1800bc7d8  pop     rbp
0x1800bc7d9  retn
```
