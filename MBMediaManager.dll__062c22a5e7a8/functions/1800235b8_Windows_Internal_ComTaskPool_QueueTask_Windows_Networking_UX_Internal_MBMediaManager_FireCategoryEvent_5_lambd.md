# Windows::Internal::ComTaskPool::QueueTask__Windows::Networking::UX::Internal::MBMediaManager::_FireCategoryEvent_::_5_::_lambda_1__const__

- ea: `0x1800235b8`
- end: `0x180023657`
- name: `Windows::Internal::ComTaskPool::QueueTask__Windows::Networking::UX::Internal::MBMediaManager::_FireCategoryEvent_::_5_::_lambda_1__const__`
- size: `159`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008f00`

## callees

- `0x18000735c`
- `0x18000fde0`
- `0x1800235b8`
- `0x18002d20c`
- `0x180059010`

## import_xrefs

- `SHCORE!SHTaskPoolQueueTask` at `0x18002362f`
- `SHCORE!SHTaskPoolQueueTask` at `0x18002362f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::ComTaskPool::QueueTask__Windows::Networking::UX::Internal::MBMediaManager::_FireCategoryEvent_::_5_::_lambda_1__const__(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4)
{
  _QWORD *v6; // rax
  _QWORD *v7; // rdi
  unsigned int v8; // ebx

  v6 = operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
  v7 = v6;
  if ( v6 )
  {
    Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>(v6);
    v7[2] = *(_QWORD *)a4;
    Microsoft::WRL::ComPtr<Windows::Networking::UX::IUserInputType>::InternalAddRef(v7 + 2);
    *((_DWORD *)v7 + 6) = *(_DWORD *)(a4 + 8);
    *(_OWORD *)((char *)v7 + 28) = *(_OWORD *)(a4 + 12);
    *v7 = &off_18005CA08;
  }
  else
  {
    v7 = 0;
  }
  v8 = SHTaskPoolQueueTask(0, 2, a3, 0, v7, 0);
  if ( v7 )
    (*(void (__fastcall **)(_QWORD *))(*v7 + 16LL))(v7);
  return v8;
}

```

## disassembly

```asm
0x1800235b8  push    rbx
0x1800235ba  push    rbp
0x1800235bb  push    rsi
0x1800235bc  push    rdi
0x1800235bd  sub     rsp, 38h
0x1800235c1  mov     rsi, r9
0x1800235c4  mov     ebp, r8d
0x1800235c7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800235ce  mov     ecx, 30h ; '0'; unsigned __int64
0x1800235d3  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800235d8  mov     rdi, rax
0x1800235db  test    rax, rax
0x1800235de  jz      short loc_180023613
0x1800235e0  mov     rcx, rax
0x1800235e3  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIComPoolTask@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>(void)
0x1800235e8  mov     rax, [rsi]
0x1800235eb  mov     [rdi+10h], rax
0x1800235ef  lea     rcx, [rdi+10h]
0x1800235f3  call    ?InternalAddRef@?$ComPtr@UIUserInputType@UX@Networking@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Networking::UX::IUserInputType>::InternalAddRef(void)
0x1800235f8  mov     eax, [rsi+8]
0x1800235fb  mov     [rdi+18h], eax
0x1800235fe  movups  xmm0, xmmword ptr [rsi+0Ch]
0x180023602  movdqu  xmmword ptr [rdi+1Ch], xmm0
0x180023607  lea     rax, off_18005CA08
0x18002360e  mov     [rdi], rax
0x180023611  jmp     short loc_180023615
0x180023613  xor     edi, edi
0x180023615  mov     [rsp+58h+var_30], 0
0x18002361e  mov     [rsp+58h+var_38], rdi
0x180023623  xor     r9d, r9d
0x180023626  mov     r8d, ebp
0x180023629  lea     edx, [r9+2]
0x18002362d  xor     ecx, ecx
0x18002362f  call    cs:__imp_SHTaskPoolQueueTask
0x180023635  mov     ebx, eax
0x180023637  test    rdi, rdi
0x18002363a  jz      short loc_18002364C
0x18002363c  mov     rdx, [rdi]
0x18002363f  mov     rcx, rdi
0x180023642  mov     rax, [rdx+10h]
0x180023646  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002364b  nop
0x18002364c  mov     eax, ebx
0x18002364e  add     rsp, 38h
0x180023652  pop     rdi
0x180023653  pop     rsi
0x180023654  pop     rbp
0x180023655  pop     rbx
0x180023656  retn
```
