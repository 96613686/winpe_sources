# OobeEsimTaskManager::ExecuteEasyConnect(IUnknown *)

- ea: `0x180007494`
- end: `0x1800075a0`
- name: `?ExecuteEasyConnect@OobeEsimTaskManager@@AEAAJPEAUIUnknown@@@Z`
- size: `268`
- prototype: `__int64 __fastcall(OobeEsimTaskManager *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800079a0`

## callees

- `0x180002150`
- `0x180007330`
- `0x180007494`
- `0x180016880`
- `0x18001cb10`
- `0x18003469c`
- `0x180035f78`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000754c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000754c`

## string_xrefs

- `0x1800074e0`: `onecoreuap\net\ux\mbmediamanager\lib\oobeesimtaskmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall OobeEsimTaskManager::ExecuteEasyConnect(OobeEsimTaskManager *this, struct IUnknown *a2)
{
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbx
  int v5; // eax
  volatile int *v6; // rdx
  int v7; // ebx
  __int64 v8; // rcx
  volatile int *v9; // rdx
  Microsoft::WRL::Details *v10; // rcx
  DWORD CurrentThreadId; // eax
  __int64 v12; // rdx
  __int64 v13; // rcx
  _QWORD v15[3]; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+20h]
  __int64 v17; // [rsp+68h] [rbp+30h] BYREF

  v17 = 0;
  QueryInterface = a2->lpVtbl->QueryInterface;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
  v5 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))QueryInterface)(
         a2,
         &GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a,
         &v17);
  v7 = v5;
  if ( v5 >= 0 )
  {
    if ( this )
    {
      Microsoft::WRL::Details::SafeUnknownIncrementReference((OobeEsimTaskManager *)((char *)this + 44), v6);
      v15[0] = this;
      Microsoft::WRL::Details::SafeUnknownIncrementReference(v10, v9);
    }
    else
    {
      v15[0] = 0;
    }
    v15[1] = v17;
    if ( v17 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 8LL))(v17);
    CurrentThreadId = GetCurrentThreadId();
    v7 = ((__int64 (__fastcall *)(__int64, __int64, _QWORD, _QWORD *))Windows::Internal::ComTaskPool::QueueTask__OobeEsimTaskManager::ExecuteEasyConnect_::_2_::_lambda_1___)(
           v13,
           v12,
           CurrentThreadId,
           v15);
    OobeEsimTaskManager::ExecuteEasyConnect_::_2_::_lambda_1_::__lambda_1_(v15);
    if ( v7 < 0 )
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v17 + 32LL))(v17, (unsigned int)v7);
    if ( this )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ITaskHandler,Microsoft::WRL::FtmBase>::Release(this);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x81,
      (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobeesimtaskmanager.cpp",
      (const char *)(unsigned int)v5,
      v15[0]);
    v8 = v17;
    if ( v17 )
    {
      v17 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180007494  push    rbp
0x180007496  push    rbx
0x180007497  push    rsi
0x180007498  push    rdi
0x180007499  mov     rbp, rsp
0x18000749c  sub     rsp, 38h
0x1800074a0  mov     rdi, rdx
0x1800074a3  mov     rsi, rcx
0x1800074a6  mov     [rbp+arg_8], 0
0x1800074ae  mov     rax, [rdx]
0x1800074b1  mov     rbx, [rax]
0x1800074b4  lea     rcx, [rbp+arg_8]
0x1800074b8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800074bd  lea     r8, [rbp+arg_8]
0x1800074c1  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x1800074c8  mov     rcx, rdi
0x1800074cb  mov     rax, rbx
0x1800074ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074d3  mov     ebx, eax
0x1800074d5  test    eax, eax
0x1800074d7  jns     short loc_180007515
0x1800074d9  mov     rcx, [rbp+20h]; this
0x1800074dd  mov     r9d, eax; char *
0x1800074e0  lea     r8, aOnecoreuapNetU_11; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x1800074e7  mov     edx, 81h; void *
0x1800074ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800074f1  nop
0x1800074f2  mov     rcx, [rbp+arg_8]
0x1800074f6  test    rcx, rcx
0x1800074f9  jz      short loc_180007510
0x1800074fb  mov     [rbp+arg_8], 0
0x180007503  mov     rax, [rcx]
0x180007506  mov     rax, [rax+10h]
0x18000750a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000750f  nop
0x180007510  jmp     loc_180007595
0x180007515  test    rsi, rsi
0x180007518  jz      short loc_18000752E
0x18000751a  lea     rcx, [rsi+2Ch]; this
0x18000751e  call    ?SafeUnknownIncrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownIncrementReference(long volatile &)
0x180007523  mov     [rbp+var_18], rsi
0x180007527  call    ?SafeUnknownIncrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownIncrementReference(long volatile &)
0x18000752c  jmp     short loc_180007532
0x18000752e  mov     [rbp+var_18], rsi
0x180007532  mov     rcx, [rbp+arg_8]
0x180007536  mov     [rbp+var_10], rcx
0x18000753a  test    rcx, rcx
0x18000753d  jz      short loc_18000754C
0x18000753f  mov     rax, [rcx]
0x180007542  mov     rax, [rax+8]
0x180007546  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000754b  nop
0x18000754c  call    cs:__imp_GetCurrentThreadId
0x180007552  lea     r9, [rbp+var_18]
0x180007556  mov     r8d, eax
0x180007559  call    Windows__Internal__ComTaskPool__QueueTask__OobeEsimTaskManager__ExecuteEasyConnect____2____lambda_1___
0x18000755e  mov     ebx, eax
0x180007560  lea     rcx, [rbp+var_18]
0x180007564  call    _OobeEsimTaskManager__ExecuteEasyConnect____2____lambda_1_____lambda_1_
0x180007569  test    ebx, ebx
0x18000756b  jns     short loc_18000757F
0x18000756d  mov     rcx, [rbp+arg_8]
0x180007571  mov     rdx, [rcx]
0x180007574  mov     rax, [rdx+20h]
0x180007578  mov     edx, ebx
0x18000757a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000757f  test    rsi, rsi
0x180007582  jz      short loc_18000758C
0x180007584  mov     rcx, rsi
0x180007587  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UITaskHandler@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ITaskHandler,Microsoft::WRL::FtmBase>::Release(void)
0x18000758c  lea     rcx, [rbp+arg_8]
0x180007590  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180007595  mov     eax, ebx
0x180007597  add     rsp, 38h
0x18000759b  pop     rdi
0x18000759c  pop     rsi
0x18000759d  pop     rbx
0x18000759e  pop     rbp
0x18000759f  retn
```
