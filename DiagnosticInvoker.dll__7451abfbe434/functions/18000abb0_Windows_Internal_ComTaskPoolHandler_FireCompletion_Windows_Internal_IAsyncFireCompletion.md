# Windows::Internal::ComTaskPoolHandler::FireCompletion(Windows::Internal::IAsyncFireCompletion *)

- ea: `0x18000abb0`
- end: `0x18000ad4f`
- name: `?FireCompletion@ComTaskPoolHandler@Internal@Windows@@QEAAJPEAUIAsyncFireCompletion@23@@Z`
- size: `415`
- prototype: `__int64 __fastcall(Windows::Internal::ComTaskPoolHandler *__hidden this, struct Windows::Internal::IAsyncFireCompletion *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000ab70`

## callees

- `0x1800022fc`
- `0x180002d84`
- `0x18000abb0`
- `0x180011010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ac92`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ac92`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18000acb1`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18000acb1`

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
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *((_QWORD *)v7 + 2) = 0;
    if ( v7 + 16 != &v12 )
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
0x18000abb0  push    rbx
0x18000abb2  push    rbp
0x18000abb3  push    rsi
0x18000abb4  push    rdi
0x18000abb5  push    r13
0x18000abb7  push    r14
0x18000abb9  push    r15
0x18000abbb  sub     rsp, 40h
0x18000abbf  mov     rdi, rdx
0x18000abc2  mov     ecx, cs:_tls_index
0x18000abc8  mov     rax, gs:58h
0x18000abd1  mov     rbp, [rax+rcx*8]
0x18000abd5  mov     ebx, 4
0x18000abda  cmp     byte ptr [rbx+rbp], 0
0x18000abde  jnz     short loc_18000ABE5
0x18000abe0  call    __dyn_tls_on_demand_init
0x18000abe5  mov     r13d, 8
0x18000abeb  cmp     dword ptr [rbp+r13+0], 4
0x18000abf1  jle     loc_18000AD0B
0x18000abf7  xor     r15d, r15d
0x18000abfa  test    rdi, rdi
0x18000abfd  jz      short loc_18000AC0F
0x18000abff  mov     rax, [rdi]
0x18000ac02  mov     rcx, rdi
0x18000ac05  mov     rax, [rax+8]
0x18000ac09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac0e  nop
0x18000ac0f  mov     rbx, rdi
0x18000ac12  test    rdi, rdi
0x18000ac15  jz      short loc_18000AC27
0x18000ac17  mov     rax, [rdi]
0x18000ac1a  mov     rcx, rdi
0x18000ac1d  mov     rax, [rax+8]
0x18000ac21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac26  nop
0x18000ac27  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000ac2e  mov     ecx, 18h; unsigned __int64
0x18000ac33  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000ac38  mov     rsi, rax
0x18000ac3b  test    rax, rax
0x18000ac3e  jz      short loc_18000AC90
0x18000ac40  mov     dword ptr [rax+0Ch], 1
0x18000ac47  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIComPoolTask@Internal@Windows@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::`vftable'
0x18000ac4e  mov     [rsi], rax
0x18000ac51  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000ac58  test    rcx, rcx
0x18000ac5b  jz      short loc_18000AC6A
0x18000ac5d  mov     rax, [rcx]
0x18000ac60  mov     rax, [rax+8]
0x18000ac64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac69  nop
0x18000ac6a  lea     rax, [rsi+10h]
0x18000ac6e  mov     qword ptr [rax], 0
0x18000ac75  lea     rcx, [rsp+78h+var_48]
0x18000ac7a  cmp     rax, rcx
0x18000ac7d  jz      short loc_18000AC84
0x18000ac7f  mov     [rax], rdi
0x18000ac82  xor     ebx, ebx
0x18000ac84  lea     rax, ??_7?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@6B@; const Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>::`vftable'
0x18000ac8b  mov     [rsi], rax
0x18000ac8e  jmp     short loc_18000AC92
0x18000ac90  xor     esi, esi
0x18000ac92  call    cs:__imp_GetCurrentThreadId
0x18000ac98  mov     [rsp+78h+var_50], 0
0x18000aca1  mov     [rsp+78h+var_58], rsi
0x18000aca6  xor     r9d, r9d
0x18000aca9  mov     r8d, eax
0x18000acac  xor     edx, edx
0x18000acae  lea     ecx, [rdx+3]
0x18000acb1  call    cs:__imp_SHTaskPoolQueueTask
0x18000acb7  mov     r14d, eax
0x18000acba  test    rsi, rsi
0x18000acbd  jz      short loc_18000ACCF
0x18000acbf  mov     rax, [rsi]
0x18000acc2  mov     rcx, rsi
0x18000acc5  mov     rax, [rax+10h]
0x18000acc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000acce  nop
0x18000accf  shr     r14d, 1Fh
0x18000acd3  xor     r14b, 1
0x18000acd7  test    rbx, rbx
0x18000acda  jz      short loc_18000ACEC
0x18000acdc  mov     rax, [rbx]
0x18000acdf  mov     rcx, rbx
0x18000ace2  mov     rax, [rax+10h]
0x18000ace6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aceb  nop
0x18000acec  test    rdi, rdi
0x18000acef  jz      short loc_18000AD01
0x18000acf1  mov     rax, [rdi]
0x18000acf4  mov     rcx, rdi
0x18000acf7  mov     rax, [rax+10h]
0x18000acfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad00  nop
0x18000ad01  test    r14b, r14b
0x18000ad04  jnz     short loc_18000AD3D
0x18000ad06  mov     ebx, 4
0x18000ad0b  cmp     byte ptr [rbx+rbp], 0
0x18000ad0f  jnz     short loc_18000AD16
0x18000ad11  call    __dyn_tls_on_demand_init
0x18000ad16  inc     dword ptr [rbp+r13+0]
0x18000ad1b  mov     rax, [rdi]
0x18000ad1e  mov     rcx, rdi
0x18000ad21  mov     rax, [rax+18h]
0x18000ad25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad2a  mov     r15d, eax
0x18000ad2d  cmp     byte ptr [rbx+rbp], 0
0x18000ad31  jnz     short loc_18000AD38
0x18000ad33  call    __dyn_tls_on_demand_init
0x18000ad38  dec     dword ptr [rbp+r13+0]
0x18000ad3d  mov     eax, r15d
0x18000ad40  add     rsp, 40h
0x18000ad44  pop     r15
0x18000ad46  pop     r14
0x18000ad48  pop     r13
0x18000ad4a  pop     rdi
0x18000ad4b  pop     rsi
0x18000ad4c  pop     rbp
0x18000ad4d  pop     rbx
0x18000ad4e  retn
```
