# Windows::Internal::ComTaskPoolHandler::FireCompletion(Windows::Internal::IAsyncFireCompletion *)

- ea: `0x180009f50`
- end: `0x18000a0ed`
- name: `?FireCompletion@ComTaskPoolHandler@Internal@Windows@@QEAAJPEAUIAsyncFireCompletion@23@@Z`
- size: `413`
- prototype: `__int64 __fastcall(Windows::Internal::ComTaskPoolHandler *__hidden this, struct Windows::Internal::IAsyncFireCompletion *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180009f10`

## callees

- `0x180001de4`
- `0x180002234`
- `0x180009f50`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a02d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a02d`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18000a048`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18000a048`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ComTaskPoolHandler::FireCompletion(
        Windows::Internal::ComTaskPoolHandler *this,
        struct Windows::Internal::IAsyncFireCompletion *a2)
{
  __int64 v3; // rbp
  unsigned int v4; // r15d
  struct Windows::Internal::IAsyncFireCompletion *v5; // rbx
  _BYTE *v6; // rax
  _BYTE *v7; // rsi
  struct Microsoft::WRL::Details::ModuleBase *v8; // rcx
  DWORD CurrentThreadId; // eax
  int v10; // r14d
  bool v11; // r14
  char v13; // [rsp+30h] [rbp-38h] BYREF

  v3 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  if ( !*(_BYTE *)(v3 + 4) )
    _dyn_tls_on_demand_init();
  if ( *(int *)(v3 + 8) <= 4 )
    goto LABEL_28;
  v4 = 0;
  if ( a2 )
  {
    (*(void (__fastcall **)(struct Windows::Internal::IAsyncFireCompletion *))(*(_QWORD *)a2 + 8LL))(a2);
    (*(void (__fastcall **)(struct Windows::Internal::IAsyncFireCompletion *))(*(_QWORD *)a2 + 8LL))(a2);
  }
  v5 = a2;
  v6 = operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
  v7 = v6;
  if ( v6 )
  {
    v8 = Microsoft::WRL::Details::ModuleBase::module_;
    *((_DWORD *)v6 + 3) = 1;
    *(_QWORD *)v6 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::`vftable';
    if ( v8 )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)v8 + 8LL))(v8);
    *((_QWORD *)v7 + 2) = 0;
    if ( v7 + 16 != &v13 )
    {
      *((_QWORD *)v7 + 2) = a2;
      v5 = 0;
    }
    *(_QWORD *)v7 = &Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>::`vftable';
  }
  else
  {
    v7 = 0;
  }
  CurrentThreadId = GetCurrentThreadId();
  v10 = SHTaskPoolQueueTask(3, 0, CurrentThreadId, 0, v7, 0);
  if ( v7 )
    (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v7 + 16LL))(v7);
  v11 = v10 >= 0;
  if ( v5 )
    (*(void (__fastcall **)(struct Windows::Internal::IAsyncFireCompletion *))(*(_QWORD *)v5 + 16LL))(v5);
  if ( a2 )
    (*(void (__fastcall **)(struct Windows::Internal::IAsyncFireCompletion *))(*(_QWORD *)a2 + 16LL))(a2);
  if ( !v11 )
  {
LABEL_28:
    if ( !*(_BYTE *)(v3 + 4) )
      _dyn_tls_on_demand_init();
    ++*(_DWORD *)(v3 + 8);
    v4 = (*(__int64 (__fastcall **)(struct Windows::Internal::IAsyncFireCompletion *))(*(_QWORD *)a2 + 24LL))(a2);
    if ( !*(_BYTE *)(v3 + 4) )
      _dyn_tls_on_demand_init();
    --*(_DWORD *)(v3 + 8);
  }
  return v4;
}

```

## disassembly

```asm
0x180009f50  mov     [rsp+arg_0], rbx
0x180009f55  mov     [rsp+arg_10], rbp
0x180009f5a  push    rsi
0x180009f5b  push    rdi
0x180009f5c  push    r13
0x180009f5e  push    r14
0x180009f60  push    r15
0x180009f62  sub     rsp, 40h
0x180009f66  mov     ecx, cs:_tls_index
0x180009f6c  mov     rdi, rdx
0x180009f6f  mov     rax, gs:58h
0x180009f78  mov     ebx, 4
0x180009f7d  mov     rbp, [rax+rcx*8]
0x180009f81  cmp     byte ptr [rbx+rbp], 0
0x180009f85  jnz     short loc_180009F8C
0x180009f87  call    __dyn_tls_on_demand_init
0x180009f8c  mov     r13d, 8
0x180009f92  cmp     dword ptr [rbp+r13+0], 4
0x180009f98  jle     loc_18000A09F
0x180009f9e  xor     r15d, r15d
0x180009fa1  test    rdi, rdi
0x180009fa4  jz      short loc_180009FC4
0x180009fa6  mov     rax, [rdi]
0x180009fa9  mov     rcx, rdi
0x180009fac  mov     rax, [rax+8]
0x180009fb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fb5  mov     rax, [rdi]
0x180009fb8  mov     rcx, rdi
0x180009fbb  mov     rax, [rax+8]
0x180009fbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fc4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180009fcb  mov     ecx, 18h; unsigned __int64
0x180009fd0  mov     rbx, rdi
0x180009fd3  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180009fd8  mov     rsi, rax
0x180009fdb  test    rax, rax
0x180009fde  jz      short loc_18000A02B
0x180009fe0  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180009fe7  mov     dword ptr [rax+0Ch], 1
0x180009fee  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIComPoolTask@Internal@Windows@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::`vftable'
0x180009ff5  mov     [rsi], rax
0x180009ff8  test    rcx, rcx
0x180009ffb  jz      short loc_18000A009
0x180009ffd  mov     rax, [rcx]
0x18000a000  mov     rax, [rax+8]
0x18000a004  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a009  lea     rax, [rsi+10h]
0x18000a00d  lea     rcx, [rsp+68h+var_38]
0x18000a012  mov     [rax], r15
0x18000a015  cmp     rax, rcx
0x18000a018  jz      short loc_18000A01F
0x18000a01a  mov     [rax], rdi
0x18000a01d  xor     ebx, ebx
0x18000a01f  lea     rax, ??_7?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@6B@; const Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>::`vftable'
0x18000a026  mov     [rsi], rax
0x18000a029  jmp     short loc_18000A02D
0x18000a02b  xor     esi, esi
0x18000a02d  call    cs:__imp_GetCurrentThreadId
0x18000a033  xor     edx, edx
0x18000a035  mov     [rsp+68h+var_40], r15
0x18000a03a  xor     r9d, r9d
0x18000a03d  mov     [rsp+68h+var_48], rsi
0x18000a042  mov     r8d, eax
0x18000a045  lea     ecx, [rdx+3]
0x18000a048  call    cs:__imp_SHTaskPoolQueueTask
0x18000a04e  mov     r14d, eax
0x18000a051  test    rsi, rsi
0x18000a054  jz      short loc_18000A065
0x18000a056  mov     rax, [rsi]
0x18000a059  mov     rcx, rsi
0x18000a05c  mov     rax, [rax+10h]
0x18000a060  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a065  shr     r14d, 1Fh
0x18000a069  xor     r14b, 1
0x18000a06d  test    rbx, rbx
0x18000a070  jz      short loc_18000A081
0x18000a072  mov     rax, [rbx]
0x18000a075  mov     rcx, rbx
0x18000a078  mov     rax, [rax+10h]
0x18000a07c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a081  test    rdi, rdi
0x18000a084  jz      short loc_18000A095
0x18000a086  mov     rax, [rdi]
0x18000a089  mov     rcx, rdi
0x18000a08c  mov     rax, [rax+10h]
0x18000a090  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a095  test    r14b, r14b
0x18000a098  jnz     short loc_18000A0D1
0x18000a09a  mov     ebx, 4
0x18000a09f  cmp     byte ptr [rbx+rbp], 0
0x18000a0a3  jnz     short loc_18000A0AA
0x18000a0a5  call    __dyn_tls_on_demand_init
0x18000a0aa  inc     dword ptr [rbp+r13+0]
0x18000a0af  mov     rcx, rdi
0x18000a0b2  mov     rax, [rdi]
0x18000a0b5  mov     rax, [rax+18h]
0x18000a0b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0be  cmp     byte ptr [rbx+rbp], 0
0x18000a0c2  mov     r15d, eax
0x18000a0c5  jnz     short loc_18000A0CC
0x18000a0c7  call    __dyn_tls_on_demand_init
0x18000a0cc  dec     dword ptr [rbp+r13+0]
0x18000a0d1  lea     r11, [rsp+68h+var_28]
0x18000a0d6  mov     eax, r15d
0x18000a0d9  mov     rbx, [r11+30h]
0x18000a0dd  mov     rbp, [r11+40h]
0x18000a0e1  mov     rsp, r11
0x18000a0e4  pop     r15
0x18000a0e6  pop     r14
0x18000a0e8  pop     r13
0x18000a0ea  pop     rdi
0x18000a0eb  pop     rsi
0x18000a0ec  retn
```
