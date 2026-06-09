# Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::SimpleClassFactory<CreateSystemObjectTask,0>,Microsoft::WRL::SimpleClassFactory<CreateSystemObjectTask,0>,>(Microsoft::WRL::SimpleClassFactory<CreateSystemObjectTask,0> * *)

- ea: `0x1400065e8`
- end: `0x140006678`
- name: `??$MakeAndInitialize@V?$SimpleClassFactory@VCreateSystemObjectTask@@$0A@@WRL@Microsoft@@V123@$$V@Details@WRL@Microsoft@@YAJPEAPEAV?$SimpleClassFactory@VCreateSystemObjectTask@@$0A@@12@@Z`
- size: `144`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400063c0`

## callees

- `0x1400021a8`
- `0x1400065e8`
- `0x140007208`
- `0x140007360`
- `0x14000a010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::SimpleClassFactory<CreateSystemObjectTask,0>,Microsoft::WRL::SimpleClassFactory<CreateSystemObjectTask,0>,>(
        __int64 *a1)
{
  void *v2; // rax
  unsigned int v3; // ebx
  __int64 SystemObject; // rax
  __int64 v5; // rbx
  void *v7; // [rsp+30h] [rbp+8h] BYREF

  *a1 = 0;
  v2 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v7 = v2;
  if ( v2 )
  {
    SystemObject = Microsoft::WRL::SimpleClassFactory<CreateSystemObjectTask,0>::SimpleClassFactory<CreateSystemObjectTask,0>(v2);
    v5 = SystemObject;
    v7 = 0;
    if ( SystemObject )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)SystemObject + 8LL))(SystemObject);
    *a1 = v5;
    if ( v5 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    v3 = 0;
  }
  else
  {
    v3 = -2147024882;
  }
  Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_ea734d1cec1fa7b22a66fb865ad05d37_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_ea734d1cec1fa7b22a66fb865ad05d37_>>(&v7);
  return v3;
}

```

## disassembly

```asm
0x1400065e8  mov     [rsp+arg_8], rbx
0x1400065ed  push    rdi
0x1400065ee  sub     rsp, 20h
0x1400065f2  mov     rdi, rcx
0x1400065f5  mov     qword ptr [rcx], 0
0x1400065fc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140006603  mov     ecx, 18h; unsigned __int64
0x140006608  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14000660d  mov     [rsp+28h+arg_0], rax
0x140006612  test    rax, rax
0x140006615  jnz     short loc_14000661E
0x140006617  mov     ebx, 8007000Eh
0x14000661c  jmp     short loc_140006661
0x14000661e  mov     rcx, rax
0x140006621  call    ??0?$SimpleClassFactory@VCreateSystemObjectTask@@$0A@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::SimpleClassFactory<CreateSystemObjectTask,0>::SimpleClassFactory<CreateSystemObjectTask,0>(void)
0x140006626  mov     rbx, rax
0x140006629  mov     [rsp+28h+arg_0], 0
0x140006632  test    rax, rax
0x140006635  jz      short loc_140006647
0x140006637  mov     rcx, [rax]
0x14000663a  mov     rax, [rcx+8]
0x14000663e  mov     rcx, rbx
0x140006641  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006646  nop
0x140006647  mov     [rdi], rbx
0x14000664a  test    rbx, rbx
0x14000664d  jz      short loc_14000665F
0x14000664f  mov     rax, [rbx]
0x140006652  mov     rcx, rbx
0x140006655  mov     rax, [rax+10h]
0x140006659  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000665e  nop
0x14000665f  xor     ebx, ebx
0x140006661  lea     rcx, [rsp+28h+arg_0]
0x140006666  call    ??1?$MakeAllocator@V?$CTaskWrapper@V_lambda_ea734d1cec1fa7b22a66fb865ad05d37_@@@ComTaskPool@Internal@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_ea734d1cec1fa7b22a66fb865ad05d37_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_ea734d1cec1fa7b22a66fb865ad05d37_>>(void)
0x14000666b  mov     eax, ebx
0x14000666d  mov     rbx, [rsp+28h+arg_8]
0x140006672  add     rsp, 20h
0x140006676  pop     rdi
0x140006677  retn
```
