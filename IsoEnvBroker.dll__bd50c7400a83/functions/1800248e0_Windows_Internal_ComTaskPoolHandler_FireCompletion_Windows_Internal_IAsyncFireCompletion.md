# Windows::Internal::ComTaskPoolHandler::FireCompletion(Windows::Internal::IAsyncFireCompletion *)

- ea: `0x1800248e0`
- end: `0x180024a7f`
- name: `?FireCompletion@ComTaskPoolHandler@Internal@Windows@@QEAAJPEAUIAsyncFireCompletion@23@@Z`
- size: `415`
- prototype: `__int64 __fastcall(Windows::Internal::ComTaskPoolHandler *__hidden this, struct Windows::Internal::IAsyncFireCompletion *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800248a0`

## callees

- `0x180002a30`
- `0x180005014`
- `0x1800248e0`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800249c2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800249c2`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x1800249e1`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x1800249e1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::ComTaskPoolHandler::FireCompletion(
        Windows::Internal::ComTaskPoolHandler *this,
        struct Windows::Internal::IAsyncFireCompletion *a2)
{
  __int64 v3; // rbp
  unsigned int v4; // r15d
  struct Windows::Internal::IAsyncFireCompletion *v5; // rbx
  _BYTE *v6; // rax
  _BYTE *v7; // rsi
  DWORD CurrentThreadId; // eax
  int v9; // r14d
  bool v10; // r14
  char v12; // [rsp+30h] [rbp-48h] BYREF

  v3 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  if ( !*(_BYTE *)(v3 + 4) )
    _dyn_tls_on_demand_init();
  if ( *(int *)(v3 + 8) <= 4 )
    goto LABEL_30;
  v4 = 0;
  if ( a2 )
    (*(void (__fastcall **)(struct Windows::Internal::IAsyncFireCompletion *))(*(_QWORD *)a2 + 8LL))(a2);
  v5 = a2;
  if ( a2 )
    (*(void (__fastcall **)(struct Windows::Internal::IAsyncFireCompletion *))(*(_QWORD *)a2 + 8LL))(a2);
  v6 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v7 = v6;
  if ( v6 )
  {
    *((_DWORD *)v6 + 3) = 1;
    *(_QWORD *)v6 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *((_QWORD *)v7 + 2) = 0;
    if ( v7 + 16 != &v12 )
    {
      *((_QWORD *)v7 + 2) = a2;
      v5 = 0;
    }
    *(_QWORD *)v7 = Z::CTaskWrapper<`Windows::Internal::ComTaskPoolHandler::_FireCompletion'::`5'::_lambda_1_,long near * const volatile,Windows::Internal::IAsyncFireCompletion *>::`vftable';
  }
  else
  {
    v7 = 0;
  }
  CurrentThreadId = GetCurrentThreadId();
  v9 = SHTaskPoolQueueTask(3, 0, CurrentThreadId, 0, v7, 0);
  if ( v7 )
    (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v7 + 16LL))(v7);
  v10 = v9 >= 0;
  if ( v5 )
    (*(void (__fastcall **)(struct Windows::Internal::IAsyncFireCompletion *))(*(_QWORD *)v5 + 16LL))(v5);
  if ( a2 )
    (*(void (__fastcall **)(struct Windows::Internal::IAsyncFireCompletion *))(*(_QWORD *)a2 + 16LL))(a2);
  if ( !v10 )
  {
LABEL_30:
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
0x1800248e0  push    rbx
0x1800248e2  push    rbp
0x1800248e3  push    rsi
0x1800248e4  push    rdi
0x1800248e5  push    r13
0x1800248e7  push    r14
0x1800248e9  push    r15
0x1800248eb  sub     rsp, 40h
0x1800248ef  mov     rdi, rdx
0x1800248f2  mov     ecx, cs:_tls_index
0x1800248f8  mov     rax, gs:58h
0x180024901  mov     rbp, [rax+rcx*8]
0x180024905  mov     ebx, 4
0x18002490a  cmp     byte ptr [rbx+rbp], 0
0x18002490e  jnz     short loc_180024915
0x180024910  call    __dyn_tls_on_demand_init
0x180024915  mov     r13d, 8
0x18002491b  cmp     dword ptr [rbp+r13+0], 4
0x180024921  jle     loc_180024A3B
0x180024927  xor     r15d, r15d
0x18002492a  test    rdi, rdi
0x18002492d  jz      short loc_18002493F
0x18002492f  mov     rax, [rdi]
0x180024932  mov     rcx, rdi
0x180024935  mov     rax, [rax+8]
0x180024939  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002493e  nop
0x18002493f  mov     rbx, rdi
0x180024942  test    rdi, rdi
0x180024945  jz      short loc_180024957
0x180024947  mov     rax, [rdi]
0x18002494a  mov     rcx, rdi
0x18002494d  mov     rax, [rax+8]
0x180024951  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024956  nop
0x180024957  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002495e  mov     ecx, 18h; unsigned __int64
0x180024963  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180024968  mov     rsi, rax
0x18002496b  test    rax, rax
0x18002496e  jz      short loc_1800249C0
0x180024970  mov     dword ptr [rax+0Ch], 1
0x180024977  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIComPoolTask@Internal@Windows@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::`vftable'
0x18002497e  mov     [rsi], rax
0x180024981  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180024988  test    rcx, rcx
0x18002498b  jz      short loc_18002499A
0x18002498d  mov     rax, [rcx]
0x180024990  mov     rax, [rax+8]
0x180024994  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024999  nop
0x18002499a  lea     rax, [rsi+10h]
0x18002499e  mov     qword ptr [rax], 0
0x1800249a5  lea     rcx, [rsp+78h+var_48]
0x1800249aa  cmp     rax, rcx
0x1800249ad  jz      short loc_1800249B4
0x1800249af  mov     [rax], rdi
0x1800249b2  xor     ebx, ebx
0x1800249b4  lea     rax, ??_7?$CTaskWrapper@V_lambda_1_@?4??_FireCompletion@ComTaskPoolHandler@Internal@Windows@@SAJPEAUIAsyncFireCompletion@45@@Z@@ComTaskPool@Internal@Windows@@6B@; const Windows::Internal::ComTaskPool::CTaskWrapper<`Windows::Internal::ComTaskPoolHandler::_FireCompletion(Windows::Internal::IAsyncFireCompletion *)'::`5'::_lambda_1_>::`vftable'
0x1800249bb  mov     [rsi], rax
0x1800249be  jmp     short loc_1800249C2
0x1800249c0  xor     esi, esi
0x1800249c2  call    cs:__imp_GetCurrentThreadId
0x1800249c8  mov     [rsp+78h+var_50], 0
0x1800249d1  mov     [rsp+78h+var_58], rsi
0x1800249d6  xor     r9d, r9d
0x1800249d9  mov     r8d, eax
0x1800249dc  xor     edx, edx
0x1800249de  lea     ecx, [rdx+3]
0x1800249e1  call    cs:__imp_SHTaskPoolQueueTask
0x1800249e7  mov     r14d, eax
0x1800249ea  test    rsi, rsi
0x1800249ed  jz      short loc_1800249FF
0x1800249ef  mov     rax, [rsi]
0x1800249f2  mov     rcx, rsi
0x1800249f5  mov     rax, [rax+10h]
0x1800249f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800249fe  nop
0x1800249ff  shr     r14d, 1Fh
0x180024a03  xor     r14b, 1
0x180024a07  test    rbx, rbx
0x180024a0a  jz      short loc_180024A1C
0x180024a0c  mov     rax, [rbx]
0x180024a0f  mov     rcx, rbx
0x180024a12  mov     rax, [rax+10h]
0x180024a16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024a1b  nop
0x180024a1c  test    rdi, rdi
0x180024a1f  jz      short loc_180024A31
0x180024a21  mov     rax, [rdi]
0x180024a24  mov     rcx, rdi
0x180024a27  mov     rax, [rax+10h]
0x180024a2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024a30  nop
0x180024a31  test    r14b, r14b
0x180024a34  jnz     short loc_180024A6D
0x180024a36  mov     ebx, 4
0x180024a3b  cmp     byte ptr [rbx+rbp], 0
0x180024a3f  jnz     short loc_180024A46
0x180024a41  call    __dyn_tls_on_demand_init
0x180024a46  inc     dword ptr [rbp+r13+0]
0x180024a4b  mov     rax, [rdi]
0x180024a4e  mov     rcx, rdi
0x180024a51  mov     rax, [rax+18h]
0x180024a55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024a5a  mov     r15d, eax
0x180024a5d  cmp     byte ptr [rbx+rbp], 0
0x180024a61  jnz     short loc_180024A68
0x180024a63  call    __dyn_tls_on_demand_init
0x180024a68  dec     dword ptr [rbp+r13+0]
0x180024a6d  mov     eax, r15d
0x180024a70  add     rsp, 40h
0x180024a74  pop     r15
0x180024a76  pop     r14
0x180024a78  pop     r13
0x180024a7a  pop     rdi
0x180024a7b  pop     rsi
0x180024a7c  pop     rbp
0x180024a7d  pop     rbx
0x180024a7e  retn
```
