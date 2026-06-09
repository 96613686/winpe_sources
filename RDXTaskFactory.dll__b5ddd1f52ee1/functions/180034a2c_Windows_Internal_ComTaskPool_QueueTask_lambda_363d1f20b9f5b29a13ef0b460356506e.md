# Windows::Internal::ComTaskPool::QueueTask__lambda_363d1f20b9f5b29a13ef0b460356506e___

- ea: `0x180034a2c`
- end: `0x180034ac7`
- name: `Windows::Internal::ComTaskPool::QueueTask__lambda_363d1f20b9f5b29a13ef0b460356506e___`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180039e10`

## callees

- `0x18000534c`
- `0x180012448`
- `0x180022a54`
- `0x180034a2c`
- `0x180050010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180034a7f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180034a7f`
- `SHCORE!SHTaskPoolQueueTask` at `0x180034a9d`
- `SHCORE!SHTaskPoolQueueTask` at `0x180034a9d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::ComTaskPool::QueueTask__lambda_363d1f20b9f5b29a13ef0b460356506e___(
        __int64 a1,
        _QWORD *a2)
{
  _QWORD *v2; // rax
  _QWORD *v3; // rbx
  _QWORD *v4; // rdi
  DWORD CurrentThreadId; // eax
  unsigned int v6; // ebx
  _QWORD *v8; // [rsp+48h] [rbp+10h] BYREF

  v8 = a2;
  v2 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v3 = v2;
  v8 = v2;
  v4 = 0;
  if ( v2 )
  {
    Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>(v2);
    *v3 = off_1800539D0;
    v8 = 0;
    v4 = v3;
  }
  Microsoft::WRL::Details::MakeAllocator_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_d9eb9fdc385074818c94944c7f345152_____::_MakeAllocator_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_d9eb9fdc385074818c94944c7f345152_____(&v8);
  CurrentThreadId = GetCurrentThreadId();
  v6 = SHTaskPoolQueueTask(0, 0, CurrentThreadId);
  if ( v4 )
    (*(void (__fastcall **)(_QWORD *))(*v4 + 16LL))(v4);
  return v6;
}

```

## disassembly

```asm
0x180034a2c  mov     [rsp+arg_0], rbx
0x180034a31  mov     [rsp+arg_8], rdx
0x180034a36  push    rdi
0x180034a37  sub     rsp, 30h
0x180034a3b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180034a42  mov     ecx, 18h; unsigned __int64
0x180034a47  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180034a4c  mov     rbx, rax
0x180034a4f  mov     [rsp+38h+arg_8], rax
0x180034a54  xor     edi, edi
0x180034a56  test    rax, rax
0x180034a59  jz      short loc_180034A75
0x180034a5b  mov     rcx, rax
0x180034a5e  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIComPoolTask@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>(void)
0x180034a63  lea     rax, off_1800539D0
0x180034a6a  mov     [rbx], rax
0x180034a6d  mov     [rsp+38h+arg_8], rdi
0x180034a72  mov     rdi, rbx
0x180034a75  lea     rcx, [rsp+38h+arg_8]
0x180034a7a  call    Microsoft__WRL__Details__MakeAllocator_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_d9eb9fdc385074818c94944c7f345152________MakeAllocator_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_d9eb9fdc385074818c94944c7f345152_____
0x180034a7f  call    cs:__imp_GetCurrentThreadId
0x180034a85  mov     [rsp+38h+var_10], 0
0x180034a8e  mov     [rsp+38h+var_18], rdi
0x180034a93  xor     r9d, r9d
0x180034a96  mov     r8d, eax
0x180034a99  xor     edx, edx
0x180034a9b  xor     ecx, ecx
0x180034a9d  call    cs:__imp_SHTaskPoolQueueTask
0x180034aa3  mov     ebx, eax
0x180034aa5  test    rdi, rdi
0x180034aa8  jz      short loc_180034ABA
0x180034aaa  mov     rdx, [rdi]
0x180034aad  mov     rcx, rdi
0x180034ab0  mov     rax, [rdx+10h]
0x180034ab4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034ab9  nop
0x180034aba  mov     eax, ebx
0x180034abc  mov     rbx, [rsp+38h+arg_0]
0x180034ac1  add     rsp, 30h
0x180034ac5  pop     rdi
0x180034ac6  retn
```
