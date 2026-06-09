# Concurrency::details::_AsyncTaskGeneratorThunk__lambda_012995b310defc0ef83a366488a71671___::[Concurrency::details::_AsyncInfoBase_Concurrency::details::_AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency::details::_TaskTypeTraits_void_0__0_0__1_]::_OnStart

- ea: `0x14001c760`
- end: `0x14001c9b6`
- name: `Concurrency::details::_AsyncTaskGeneratorThunk__lambda_012995b310defc0ef83a366488a71671___::[Concurrency::details::_AsyncInfoBase_Concurrency::details::_AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency::details::_TaskTypeTraits_void_0__0_0__1_]::_OnStart`
- size: `598`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x14001c9c0`

## callees

- `0x1400129fc`
- `0x140013af4`
- `0x14001508c`
- `0x140015e84`
- `0x14001c760`
- `0x14001c9d0`
- `0x140023fa8`
- `0x140035010`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall Concurrency::details::_AsyncTaskGeneratorThunk__lambda_012995b310defc0ef83a366488a71671___::_Concurrency::details::_AsyncInfoBase_Concurrency::details::_AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency::details::_TaskTypeTraits_void_0__0_0__1__::_OnStart(
        _QWORD *a1)
{
  volatile signed __int32 *v2; // rax
  volatile signed __int32 *v3; // rdx
  __int64 ambient_scheduler; // rax
  volatile signed __int32 *v5; // rcx
  volatile signed __int32 *v6; // rax
  volatile signed __int32 *v7; // rcx
  volatile signed __int32 *v8; // rcx
  volatile signed __int32 *v9; // rcx
  volatile signed __int32 *v10; // rcx
  __int64 v11; // rax
  volatile signed __int32 *v12; // rbx
  volatile signed __int32 *v13; // rbx
  volatile signed __int32 *v15; // [rsp+20h] [rbp-59h] BYREF
  __int64 v16; // [rsp+28h] [rbp-51h] BYREF
  volatile signed __int32 *v17; // [rsp+30h] [rbp-49h]
  char v18[16]; // [rsp+38h] [rbp-41h] BYREF
  _BYTE v19[24]; // [rsp+48h] [rbp-31h] BYREF
  volatile signed __int32 *v20; // [rsp+60h] [rbp-19h]
  __int64 v21; // [rsp+68h] [rbp-11h]
  __int16 v22; // [rsp+70h] [rbp-9h]
  volatile signed __int32 **v23; // [rsp+78h] [rbp-1h]
  volatile signed __int32 **v24; // [rsp+80h] [rbp+7h]
  volatile signed __int32 **v25; // [rsp+88h] [rbp+Fh]
  volatile signed __int32 **v26; // [rsp+90h] [rbp+17h]
  _BYTE v27[56]; // [rsp+98h] [rbp+1Fh] BYREF
  volatile signed __int32 *v28; // [rsp+E8h] [rbp+6Fh] BYREF
  volatile signed __int32 *v29; // [rsp+F0h] [rbp+77h] BYREF
  volatile signed __int32 *v30; // [rsp+F8h] [rbp+7Fh] BYREF

  v2 = (volatile signed __int32 *)a1[18];
  v3 = v2 + 2;
  if ( v2 )
    _InterlockedIncrement(v3);
  v15 = v2;
  v23 = &v15;
  if ( v2 )
    _InterlockedIncrement(v3);
  v30 = v2;
  v24 = &v30;
  if ( v2 )
    _InterlockedIncrement(v3);
  v29 = v2;
  v25 = &v29;
  v28 = v2;
  if ( v2 == (volatile signed __int32 *)2 )
  {
    v28 = 0;
  }
  else if ( v2 )
  {
    _InterlockedIncrement(v2 + 2);
  }
  v26 = &v28;
  ambient_scheduler = pplx::get_ambient_scheduler(v18);
  Concurrency::scheduler_ptr::scheduler_ptr(v19, ambient_scheduler);
  v5 = v28;
  v6 = v28;
  if ( v28 )
  {
    _InterlockedIncrement(v28 + 2);
    v5 = v28;
  }
  v20 = v6;
  v21 = 1;
  v22 = 1;
  if ( v5 && _InterlockedExchangeAdd(v5 + 2, 0xFFFFFFFF) == 1 )
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 8LL))(v5);
  v28 = 0;
  lambda_012995b310defc0ef83a366488a71671_::_lambda_012995b310defc0ef83a366488a71671_(v27, a1 + 27);
  Concurrency::task_void_::task_void___lambda_b491893a6046e26d34a6ad5978ce944a___(&v16, v27, v19);
  Concurrency::task_options::~task_options((Concurrency::task_options *)v19);
  v7 = v29;
  if ( v29 && _InterlockedExchangeAdd(v29 + 2, 0xFFFFFFFF) == 1 )
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
  v8 = v30;
  if ( v30 && _InterlockedExchangeAdd(v30 + 2, 0xFFFFFFFF) == 1 )
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
  v9 = v15;
  if ( v15 && _InterlockedExchangeAdd(v15 + 2, 0xFFFFFFFF) == 1 )
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
  if ( a1 + 16 != &v16 )
  {
    v10 = v17;
    v17 = 0;
    v11 = v16;
    v16 = 0;
    v12 = (volatile signed __int32 *)a1[17];
    a1[17] = v10;
    a1[16] = v11;
    if ( v12 )
    {
      if ( !_InterlockedDecrement(v12 + 2) )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
        if ( !_InterlockedDecrement(v12 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
      }
    }
  }
  v13 = v17;
  if ( v17 )
  {
    if ( !_InterlockedDecrement(v17 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
      if ( !_InterlockedDecrement(v13 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
    }
  }
  return Concurrency::details::_AsyncTaskThunkBase_Concurrency::details::_AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency::details::_TaskTypeTraits_void_0__0_0__void_::_Concurrency::details::_AsyncInfoBase_Concurrency::details::_AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency::details::_TaskTypeTraits_void_0__0_0__1__::_OnStart(a1 + 2);
}

```

## disassembly

```asm
0x14001c760  push    rbp
0x14001c762  push    rbx
0x14001c763  push    rdi
0x14001c764  push    r14
0x14001c766  lea     rbp, [rsp-3Fh]
0x14001c76b  sub     rsp, 0B8h
0x14001c772  mov     rdi, rcx
0x14001c775  mov     [rbp+57h+arg_0], 0
0x14001c77c  mov     rax, [rcx+90h]
0x14001c783  lea     rdx, [rax+8]
0x14001c787  test    rax, rax
0x14001c78a  jz      short loc_14001C78F
0x14001c78c  lock inc dword ptr [rdx]
0x14001c78f  mov     [rbp+57h+var_B0], rax
0x14001c793  lea     rcx, [rbp+57h+var_B0]
0x14001c797  mov     [rbp+57h+var_58], rcx
0x14001c79b  test    rax, rax
0x14001c79e  jz      short loc_14001C7A3
0x14001c7a0  lock inc dword ptr [rdx]
0x14001c7a3  mov     [rbp+57h+arg_18], rax
0x14001c7a7  lea     rcx, [rbp+57h+arg_18]
0x14001c7ab  mov     [rbp+57h+var_50], rcx
0x14001c7af  test    rax, rax
0x14001c7b2  jz      short loc_14001C7B7
0x14001c7b4  lock inc dword ptr [rdx]
0x14001c7b7  mov     [rbp+57h+arg_10], rax
0x14001c7bb  lea     rcx, [rbp+57h+arg_10]
0x14001c7bf  mov     [rbp+57h+var_48], rcx
0x14001c7c3  mov     [rbp+57h+arg_8], rax
0x14001c7c7  cmp     rax, 2
0x14001c7cb  jnz     short loc_14001C7D7
0x14001c7cd  mov     [rbp+57h+arg_8], 0
0x14001c7d5  jmp     short loc_14001C7E0
0x14001c7d7  test    rax, rax
0x14001c7da  jz      short loc_14001C7E0
0x14001c7dc  lock inc dword ptr [rax+8]
0x14001c7e0  lea     rax, [rbp+57h+arg_8]
0x14001c7e4  mov     [rbp+57h+var_40], rax
0x14001c7e8  lea     rcx, [rbp+57h+var_98]
0x14001c7ec  call    ?get_ambient_scheduler@pplx@@YA?AV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ; pplx::get_ambient_scheduler(void)
0x14001c7f1  mov     rdx, rax
0x14001c7f4  lea     rcx, [rbp+57h+var_88]
0x14001c7f8  call    ??0scheduler_ptr@Concurrency@@QEAA@V?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@@Z; Concurrency::scheduler_ptr::scheduler_ptr(std::shared_ptr<Concurrency::scheduler_interface>)
0x14001c7fd  mov     rcx, [rbp+57h+arg_8]
0x14001c801  mov     rax, rcx
0x14001c804  test    rcx, rcx
0x14001c807  jz      short loc_14001C811
0x14001c809  lock inc dword ptr [rcx+8]
0x14001c80d  mov     rcx, [rbp+57h+arg_8]
0x14001c811  mov     [rbp+57h+var_70], rax
0x14001c815  mov     ebx, 1
0x14001c81a  mov     [rbp+57h+var_68], rbx
0x14001c81e  mov     [rbp+57h+var_60], bx
0x14001c822  or      r14d, 0FFFFFFFFh
0x14001c826  test    rcx, rcx
0x14001c829  jz      short loc_14001C843
0x14001c82b  mov     eax, r14d
0x14001c82e  lock xadd [rcx+8], eax
0x14001c833  cmp     eax, ebx
0x14001c835  jnz     short loc_14001C843
0x14001c837  mov     rax, [rcx]
0x14001c83a  mov     rax, [rax+8]
0x14001c83e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c843  mov     [rbp+57h+arg_8], 0
0x14001c84b  lea     rdx, [rdi+0D8h]
0x14001c852  lea     rcx, [rbp+57h+var_38]
0x14001c856  call    _lambda_012995b310defc0ef83a366488a71671____lambda_012995b310defc0ef83a366488a71671_
0x14001c85b  lea     r8, [rbp+57h+var_88]
0x14001c85f  lea     rdx, [rbp+57h+var_38]
0x14001c863  lea     rcx, [rbp+57h+var_A8]
0x14001c867  call    Concurrency__task_void___task_void___lambda_b491893a6046e26d34a6ad5978ce944a___
0x14001c86c  mov     [rbp+57h+arg_0], 4
0x14001c873  lea     rcx, [rbp+57h+var_88]; this
0x14001c877  call    ??1task_options@Concurrency@@QEAA@XZ; Concurrency::task_options::~task_options(void)
0x14001c87c  nop
0x14001c87d  mov     rcx, [rbp+57h+arg_10]
0x14001c881  test    rcx, rcx
0x14001c884  jz      short loc_14001C8A0
0x14001c886  mov     eax, r14d
0x14001c889  lock xadd [rcx+8], eax
0x14001c88e  cmp     eax, 1
0x14001c891  jnz     short loc_14001C8A0
0x14001c893  mov     rax, [rcx]
0x14001c896  mov     rax, [rax+8]
0x14001c89a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c89f  nop
0x14001c8a0  mov     [rbp+57h+arg_0], 2
0x14001c8a7  mov     rcx, [rbp+57h+arg_18]
0x14001c8ab  test    rcx, rcx
0x14001c8ae  jz      short loc_14001C8CA
0x14001c8b0  mov     eax, r14d
0x14001c8b3  lock xadd [rcx+8], eax
0x14001c8b8  cmp     eax, 1
0x14001c8bb  jnz     short loc_14001C8CA
0x14001c8bd  mov     rax, [rcx]
0x14001c8c0  mov     rax, [rax+8]
0x14001c8c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c8c9  nop
0x14001c8ca  mov     [rbp+57h+arg_0], ebx
0x14001c8cd  mov     rcx, [rbp+57h+var_B0]
0x14001c8d1  test    rcx, rcx
0x14001c8d4  jz      short loc_14001C8F0
0x14001c8d6  mov     eax, r14d
0x14001c8d9  lock xadd [rcx+8], eax
0x14001c8de  cmp     eax, 1
0x14001c8e1  jnz     short loc_14001C8F0
0x14001c8e3  mov     rax, [rcx]
0x14001c8e6  mov     rax, [rax+8]
0x14001c8ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c8ef  nop
0x14001c8f0  lea     rdx, [rdi+80h]
0x14001c8f7  lea     rax, [rbp+57h+var_A8]
0x14001c8fb  cmp     rdx, rax
0x14001c8fe  jz      short loc_14001C960
0x14001c900  mov     rcx, [rbp+57h+var_A0]
0x14001c904  mov     [rbp+57h+var_A0], 0
0x14001c90c  mov     rax, [rbp+57h+var_A8]
0x14001c910  mov     [rbp+57h+var_A8], 0
0x14001c918  mov     rbx, [rdx+8]
0x14001c91c  mov     [rdx+8], rcx
0x14001c920  mov     [rdx], rax
0x14001c923  test    rbx, rbx
0x14001c926  jz      short loc_14001C960
0x14001c928  mov     eax, r14d
0x14001c92b  lock xadd [rbx+8], eax
0x14001c930  add     eax, r14d
0x14001c933  jnz     short loc_14001C960
0x14001c935  mov     rax, [rbx]
0x14001c938  mov     rcx, rbx
0x14001c93b  mov     rax, [rax]
0x14001c93e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c943  mov     eax, r14d
0x14001c946  lock xadd [rbx+0Ch], eax
0x14001c94b  add     eax, r14d
0x14001c94e  jnz     short loc_14001C960
0x14001c950  mov     rax, [rbx]
0x14001c953  mov     rcx, rbx
0x14001c956  mov     rax, [rax+8]
0x14001c95a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c95f  nop
0x14001c960  mov     rbx, [rbp+57h+var_A0]
0x14001c964  test    rbx, rbx
0x14001c967  jz      short loc_14001C9A1
0x14001c969  mov     eax, r14d
0x14001c96c  lock xadd [rbx+8], eax
0x14001c971  add     eax, r14d
0x14001c974  jnz     short loc_14001C9A1
0x14001c976  mov     rax, [rbx]
0x14001c979  mov     rcx, rbx
0x14001c97c  mov     rax, [rax]
0x14001c97f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c984  mov     eax, r14d
0x14001c987  lock xadd [rbx+0Ch], eax
0x14001c98c  add     eax, r14d
0x14001c98f  jnz     short loc_14001C9A1
0x14001c991  mov     rax, [rbx]
0x14001c994  mov     rcx, rbx
0x14001c997  mov     rax, [rax+8]
0x14001c99b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c9a0  nop
0x14001c9a1  lea     rcx, [rdi+10h]
0x14001c9a5  add     rsp, 0B8h
0x14001c9ac  pop     r14
0x14001c9ae  pop     rdi
0x14001c9af  pop     rbx
0x14001c9b0  pop     rbp
0x14001c9b1  jmp     Concurrency__details___AsyncTaskThunkBase_Concurrency__details___AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency__details___TaskTypeTraits_void_0__0_0__void____Concurrency__details___AsyncInfoBase_Concurrency__details___AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency__details___TaskTypeTraits_void_0__0_0__1_____OnStart
```
