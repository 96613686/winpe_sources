# Concurrency::task<bool>::task<bool>(Windows::Foundation::IAsyncOperation<bool> *,Concurrency::task_options const &)

- ea: `0x140012518`
- end: `0x1400128af`
- name: `??$?0PE$AAU?$IAsyncOperation@_N@Foundation@Windows@@@?$task@_N@Concurrency@@QEAA@PE$AAU?$IAsyncOperation@_N@Foundation@Windows@@AEBVtask_options@1@@Z`
- size: `919`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1400139f8`

## callees

- `0x1400017a0`
- `0x1400086b0`
- `0x140012420`
- `0x140012518`
- `0x1400128b8`
- `0x14001471c`
- `0x14001cafc`
- `0x140031960`
- `0x140035010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140012857`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140012857`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400127b5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400127b5`
- `wincorlib!?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x14001274d`
- `wincorlib!?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x14001274d`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
struct _RTL_CRITICAL_SECTION **__fastcall Concurrency::task<bool>::task<bool>(
        struct _RTL_CRITICAL_SECTION **a1,
        __int64 a2,
        __int64 *a3)
{
  volatile signed __int32 *v6; // rsi
  __int64 v7; // r12
  void *v8; // rax
  __int64 v9; // r13
  volatile signed __int32 *v10; // r15
  volatile signed __int32 *v11; // r15
  volatile signed __int32 *v12; // r15
  void *v13; // rbx
  __int64 v14; // rbx
  int v15; // eax
  Concurrency::details::_Task_impl_base *v16; // rbx
  struct _RTL_CRITICAL_SECTION *v17; // rsi
  int v18; // eax
  _QWORD *v19; // rbx
  int v20; // eax
  __int64 v21; // rcx
  __int64 v23; // [rsp+30h] [rbp-59h] BYREF
  __int64 *v24; // [rsp+38h] [rbp-51h]
  __int64 v25; // [rsp+40h] [rbp-49h] BYREF
  volatile signed __int32 *v26; // [rsp+48h] [rbp-41h]
  __int64 v27; // [rsp+50h] [rbp-39h]
  _QWORD v28[2]; // [rsp+58h] [rbp-31h] BYREF
  __int64 v29; // [rsp+68h] [rbp-21h] BYREF
  volatile signed __int32 *v30; // [rsp+70h] [rbp-19h]
  __int64 v31; // [rsp+78h] [rbp-11h]
  struct _RTL_CRITICAL_SECTION **v32; // [rsp+80h] [rbp-9h]
  __int64 *v33; // [rsp+88h] [rbp-1h]
  _QWORD *v34; // [rsp+90h] [rbp+7h] BYREF
  __int64 v35; // [rsp+98h] [rbp+Fh]
  ULONG_PTR retaddr; // [rsp+E8h] [rbp+5Fh]

  v32 = a1;
  v35 = a2;
  LODWORD(v34) = 0;
  if ( a2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
  v35 = a2;
  *a1 = 0;
  a1[1] = 0;
  std::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>(
    &v25,
    a3);
  v27 = a3[2];
  v33 = &v25;
  v6 = (volatile signed __int32 *)a3[3];
  if ( v6 )
    _InterlockedIncrement(v6 + 2);
  v28[0] = v6;
  v7 = (__int64)v6;
  if ( !v6 )
    v7 = 2;
  std::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>(
    &v29,
    &v25);
  v31 = v27;
  v24 = &v29;
  v23 = v7;
  v8 = operator new(0xC8u);
  if ( v8 )
    v9 = std::_Ref_count_obj<Concurrency::details::_Task_impl<bool>>::_Ref_count_obj<Concurrency::details::_Task_impl<bool>>(
           v8,
           &v23,
           &v29);
  else
    v9 = 0;
  LODWORD(v34) = 1;
  v10 = v30;
  if ( v30 )
  {
    if ( _InterlockedExchangeAdd(v30 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
      if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
    }
  }
  v11 = (volatile signed __int32 *)a1[1];
  a1[1] = (struct _RTL_CRITICAL_SECTION *)v9;
  *a1 = (struct _RTL_CRITICAL_SECTION *)(v9 + 16);
  if ( v11 )
  {
    if ( _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
      if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
    }
  }
  if ( v7 != 2 )
    Concurrency::details::_Task_impl_base::_RegisterCancellation((Concurrency::details::_Task_impl_base *)*a1);
  v12 = v26;
  if ( v26 )
  {
    if ( _InterlockedExchangeAdd(v26 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
      if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
    }
  }
  if ( v6 && _InterlockedExchangeAdd(v6 + 2, 0xFFFFFFFF) == 1 )
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
  (*a1)[3].SpinCount = retaddr;
  BYTE4((*a1)->OwningThread) = 1;
  LODWORD((*a1)->OwningThread) = 1;
  v13 = Platform::Details::Heap::Allocate(0x18u, 0x130u);
  std::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>(
    v28,
    (__int64 *)a1);
  v14 = Windows::Foundation::AsyncOperationCompletedHandler<bool>::AsyncOperationCompletedHandler<bool>(v13, v28);
  v15 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a2 + 48LL))(a2, v14);
  if ( v15 < 0 )
    __abi_WinRTraiseException(v15);
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  v16 = (Concurrency::details::_Task_impl_base *)*a1;
  v17 = *a1 + 1;
  EnterCriticalSection(v17);
  if ( *((_DWORD *)v16 + 4) == 2 )
  {
    v34 = 0;
    v18 = (**(__int64 (__fastcall ***)(__int64, char *, _QWORD **))a2)(
            a2,
            _uuidof__AUIAsyncInfo_Foundation_Windows__,
            &v34);
    if ( v18 < 0 )
      __abi_WinRTraiseException(v18);
    v19 = v34;
    v24 = v34;
    v20 = (*(__int64 (__fastcall **)(_QWORD *))(*v34 + 72LL))(v34);
    if ( v20 < 0 )
      __abi_WinRTraiseException(v20);
    (*(void (__fastcall **)(_QWORD *))(*v19 + 16LL))(v19);
  }
  else if ( a2 != *((_QWORD *)v16 + 21) )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
    v21 = *((_QWORD *)v16 + 21);
    if ( v21 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    *((_QWORD *)v16 + 21) = a2;
  }
  LeaveCriticalSection(v17);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 16LL))(a2);
  return a1;
}

```

## disassembly

```asm
0x140012518  mov     [rsp-8+arg_18], rbx
0x14001251d  push    rbp
0x14001251e  push    rsi
0x14001251f  push    rdi
0x140012520  push    r12
0x140012522  push    r13
0x140012524  push    r14
0x140012526  push    r15
0x140012528  lea     rbp, [rsp-27h]
0x14001252d  sub     rsp, 0B0h
0x140012534  mov     rax, cs:__security_cookie
0x14001253b  xor     rax, rsp
0x14001253e  mov     [rbp+57h+var_40], rax
0x140012542  mov     rsi, r8
0x140012545  mov     rdi, rdx
0x140012548  mov     r14, rcx
0x14001254b  mov     [rbp+57h+var_60], rcx
0x14001254f  mov     [rbp+57h+var_48], rdx
0x140012553  xor     ebx, ebx
0x140012555  mov     dword ptr [rbp+57h+var_50], ebx
0x140012558  test    rdx, rdx
0x14001255b  jz      short loc_14001256C
0x14001255d  mov     rax, [rdx]
0x140012560  mov     rcx, rdx
0x140012563  mov     rax, [rax+8]
0x140012567  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001256c  mov     [rbp+57h+var_48], rdi
0x140012570  mov     [r14], rbx
0x140012573  mov     [r14+8], rbx
0x140012577  mov     rdx, rsi
0x14001257a  lea     rcx, [rbp+57h+var_A0]
0x14001257e  call    ??0?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Concurrency::details::_Task_impl<uchar>>::shared_ptr<Concurrency::details::_Task_impl<uchar>>(std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &)
0x140012583  mov     rax, [rsi+10h]
0x140012587  mov     [rbp+57h+var_90], rax
0x14001258b  lea     rax, [rbp+57h+var_A0]
0x14001258f  mov     [rbp+57h+var_58], rax
0x140012593  mov     rsi, [rsi+18h]
0x140012597  test    rsi, rsi
0x14001259a  jz      short loc_1400125A0
0x14001259c  lock inc dword ptr [rsi+8]
0x1400125a0  mov     [rbp+57h+var_88], rsi
0x1400125a4  mov     r12, rsi
0x1400125a7  mov     eax, 2
0x1400125ac  test    rsi, rsi
0x1400125af  cmovz   r12, rax
0x1400125b3  lea     rdx, [rbp+57h+var_A0]
0x1400125b7  lea     rcx, [rbp+57h+var_78]
0x1400125bb  call    ??0?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Concurrency::details::_Task_impl<uchar>>::shared_ptr<Concurrency::details::_Task_impl<uchar>>(std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &)
0x1400125c0  mov     rax, [rbp+57h+var_90]
0x1400125c4  mov     [rbp+57h+var_68], rax
0x1400125c8  lea     rax, [rbp+57h+var_78]
0x1400125cc  mov     [rbp+57h+var_A8], rax
0x1400125d0  mov     [rbp+57h+var_B0], r12
0x1400125d4  mov     ecx, 0C8h; Size
0x1400125d9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400125de  mov     qword ptr [rbp+57h+var_C0], rax
0x1400125e2  test    rax, rax
0x1400125e5  jz      short loc_1400125FC
0x1400125e7  lea     r8, [rbp+57h+var_78]
0x1400125eb  lea     rdx, [rbp+57h+var_B0]
0x1400125ef  mov     rcx, rax
0x1400125f2  call    ??$?0AEAPEAV_CancellationTokenState@details@pplx@@AEAUscheduler_ptr@Concurrency@@@?$_Ref_count_obj@U?$_Task_impl@_N@details@Concurrency@@@std@@QEAA@AEAPEAV_CancellationTokenState@details@pplx@@AEAUscheduler_ptr@Concurrency@@@Z; std::_Ref_count_obj<Concurrency::details::_Task_impl<bool>>::_Ref_count_obj<Concurrency::details::_Task_impl<bool>>(pplx::details::_CancellationTokenState * &,Concurrency::scheduler_ptr &)
0x1400125f7  mov     r13, rax
0x1400125fa  jmp     short loc_1400125FF
0x1400125fc  mov     r13, rbx
0x1400125ff  xorps   xmm0, xmm0
0x140012602  movups  [rbp+57h+var_C0], xmm0
0x140012606  mov     qword ptr [rbp+57h+var_C0+8], r13
0x14001260a  lea     rbx, [r13+10h]
0x14001260e  mov     qword ptr [rbp+57h+var_C0], rbx
0x140012612  mov     dword ptr [rbp+57h+var_50], 1
0x140012619  mov     r15, [rbp+57h+var_70]
0x14001261d  or      ebx, 0FFFFFFFFh
0x140012620  test    r15, r15
0x140012623  jz      short loc_14001265B
0x140012625  mov     eax, ebx
0x140012627  lock xadd [r15+8], eax
0x14001262d  add     eax, ebx
0x14001262f  jnz     short loc_14001265B
0x140012631  mov     rax, [r15]
0x140012634  mov     rcx, r15
0x140012637  mov     rax, [rax]
0x14001263a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001263f  mov     eax, ebx
0x140012641  lock xadd [r15+0Ch], eax
0x140012647  add     eax, ebx
0x140012649  jnz     short loc_14001265B
0x14001264b  mov     rax, [r15]
0x14001264e  mov     rcx, r15
0x140012651  mov     rax, [rax+8]
0x140012655  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001265a  nop
0x14001265b  mov     qword ptr [rbp+57h+var_C0+8], 0
0x140012663  mov     qword ptr [rbp+57h+var_C0], 0
0x14001266b  mov     r15, [r14+8]
0x14001266f  mov     [r14+8], r13
0x140012673  lea     rax, [r13+10h]
0x140012677  mov     [r14], rax
0x14001267a  test    r15, r15
0x14001267d  jz      short loc_1400126B5
0x14001267f  mov     eax, ebx
0x140012681  lock xadd [r15+8], eax
0x140012687  add     eax, ebx
0x140012689  jnz     short loc_1400126B5
0x14001268b  mov     rax, [r15]
0x14001268e  mov     rcx, r15
0x140012691  mov     rax, [rax]
0x140012694  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012699  mov     eax, ebx
0x14001269b  lock xadd [r15+0Ch], eax
0x1400126a1  add     eax, ebx
0x1400126a3  jnz     short loc_1400126B5
0x1400126a5  mov     rax, [r15]
0x1400126a8  mov     rcx, r15
0x1400126ab  mov     rax, [rax+8]
0x1400126af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400126b4  nop
0x1400126b5  cmp     r12, 2
0x1400126b9  jz      short loc_1400126C4
0x1400126bb  mov     rcx, [r14]; this
0x1400126be  call    ?_RegisterCancellation@_Task_impl_base@details@Concurrency@@QEAAXXZ; Concurrency::details::_Task_impl_base::_RegisterCancellation(void)
0x1400126c3  nop
0x1400126c4  mov     r15, [rbp+57h+var_98]
0x1400126c8  test    r15, r15
0x1400126cb  jz      short loc_140012703
0x1400126cd  mov     eax, ebx
0x1400126cf  lock xadd [r15+8], eax
0x1400126d5  add     eax, ebx
0x1400126d7  jnz     short loc_140012703
0x1400126d9  mov     rax, [r15]
0x1400126dc  mov     rcx, r15
0x1400126df  mov     rax, [rax]
0x1400126e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400126e7  mov     eax, ebx
0x1400126e9  lock xadd [r15+0Ch], eax
0x1400126ef  add     eax, ebx
0x1400126f1  jnz     short loc_140012703
0x1400126f3  mov     rax, [r15]
0x1400126f6  mov     rcx, r15
0x1400126f9  mov     rax, [rax+8]
0x1400126fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012702  nop
0x140012703  test    rsi, rsi
0x140012706  jz      short loc_140012724
0x140012708  lock xadd [rsi+8], ebx
0x14001270d  lea     eax, [rbx-1]
0x140012710  test    eax, eax
0x140012712  jnz     short loc_140012724
0x140012714  mov     rax, [rsi]
0x140012717  mov     rcx, rsi
0x14001271a  mov     rax, [rax+8]
0x14001271e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012723  nop
0x140012724  mov     rcx, [rbp+5Fh]
0x140012728  mov     rax, [r14]
0x14001272b  mov     [rax+98h], rcx
0x140012732  mov     rax, [r14]
0x140012735  mov     byte ptr [rax+14h], 1
0x140012739  mov     rax, [r14]
0x14001273c  mov     dword ptr [rax+10h], 1
0x140012743  mov     edx, 130h
0x140012748  mov     ecx, 18h
0x14001274d  call    cs:__imp_?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z; Platform::Details::Heap::Allocate(unsigned __int64,unsigned __int64)
0x140012753  mov     rbx, rax
0x140012756  mov     qword ptr [rbp+57h+var_C0], rax
0x14001275a  mov     rdx, r14
0x14001275d  lea     rcx, [rbp+57h+var_88]
0x140012761  call    ??0?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Concurrency::details::_Task_impl<uchar>>::shared_ptr<Concurrency::details::_Task_impl<uchar>>(std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &)
0x140012766  lea     rdx, [rbp+57h+var_88]
0x14001276a  mov     rcx, rbx
0x14001276d  call    ??$?0V_lambda_0f17ac5bb141cf2bc7352f8cf74b5f7d_@@@?$AsyncOperationCompletedHandler@_N@Foundation@Windows@@QE$AAA@V_lambda_0f17ac5bb141cf2bc7352f8cf74b5f7d_@@W4CallbackContext@Platform@@_N@Z; Windows::Foundation::AsyncOperationCompletedHandler<bool>::AsyncOperationCompletedHandler<bool>(_lambda_0f17ac5bb141cf2bc7352f8cf74b5f7d_,Platform::CallbackContext,bool)
0x140012772  mov     rbx, rax
0x140012775  mov     qword ptr [rbp+57h+var_C0], rax
0x140012779  mov     rax, [rdi]
0x14001277c  mov     rdx, rbx
0x14001277f  mov     rcx, rdi
0x140012782  mov     rax, [rax+30h]
0x140012786  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001278b  test    eax, eax
0x14001278d  js      loc_14001289F
0x140012793  test    rbx, rbx
0x140012796  jz      short loc_1400127A7
0x140012798  mov     rax, [rbx]
0x14001279b  mov     rcx, rbx
0x14001279e  mov     rax, [rax+10h]
0x1400127a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400127a7  mov     rbx, [r14]
0x1400127aa  lea     rsi, [rbx+28h]
0x1400127ae  mov     qword ptr [rbp+57h+var_C0], rsi
0x1400127b2  mov     rcx, rsi; lpCriticalSection
0x1400127b5  call    cs:__imp_EnterCriticalSection
0x1400127bb  nop
0x1400127bc  mov     eax, [rbx+10h]
0x1400127bf  cmp     eax, 2
0x1400127c2  jnz     short loc_14001281D
0x1400127c4  mov     [rbp+57h+var_50], 0
0x1400127cc  mov     rax, [rdi]
0x1400127cf  lea     r8, [rbp+57h+var_50]
0x1400127d3  lea     rdx, __uuidof_?AUIAsyncInfo@Foundation@Windows@@
0x1400127da  mov     rcx, rdi
0x1400127dd  mov     rax, [rax]
0x1400127e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400127e5  test    eax, eax
0x1400127e7  js      loc_1400128A7
0x1400127ed  mov     rbx, [rbp+57h+var_50]
0x1400127f1  mov     [rbp+57h+var_A8], rbx
0x1400127f5  mov     rax, [rbx]
0x1400127f8  mov     rcx, rbx
0x1400127fb  mov     rax, [rax+48h]
0x1400127ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012804  test    eax, eax
0x140012806  js      loc_140012897
0x14001280c  mov     rax, [rbx]
0x14001280f  mov     rcx, rbx
0x140012812  mov     rax, [rax+10h]
0x140012816  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001281b  jmp     short loc_140012854
0x14001281d  cmp     rdi, [rbx+0A8h]
0x140012824  jz      short loc_140012854
0x140012826  mov     rax, [rdi]
0x140012829  mov     rcx, rdi
0x14001282c  mov     rax, [rax+8]
0x140012830  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012835  mov     rcx, [rbx+0A8h]
0x14001283c  test    rcx, rcx
0x14001283f  jz      short loc_14001284D
0x140012841  mov     rax, [rcx]
0x140012844  mov     rax, [rax+10h]
0x140012848  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001284d  mov     [rbx+0A8h], rdi
0x140012854  mov     rcx, rsi; lpCriticalSection
0x140012857  call    cs:__imp_LeaveCriticalSection
0x14001285d  nop
0x14001285e  mov     rdx, [rdi]
0x140012861  mov     rcx, rdi
0x140012864  mov     rax, [rdx+10h]
0x140012868  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001286d  mov     rax, r14
0x140012870  mov     rcx, [rbp+57h+var_40]
0x140012874  xor     rcx, rsp; StackCookie
0x140012877  call    __security_check_cookie
0x14001287c  mov     rbx, [rsp+0E0h+arg_18]
0x140012884  add     rsp, 0B0h
0x14001288b  pop     r15
0x14001288d  pop     r14
0x14001288f  pop     r13
0x140012891  pop     r12
0x140012893  pop     rdi
0x140012894  pop     rsi
0x140012895  pop     rbp
0x140012896  retn
0x140012897  mov     ecx, eax; int
0x140012899  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x14001289f  mov     ecx, eax; int
0x1400128a1  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x1400128a7  mov     ecx, eax; int
0x1400128a9  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
```
