# OobeEsimTaskManager::ExecuteBootstrapProfileDeletion(IUnknown *)

- ea: `0x180007380`
- end: `0x18000748c`
- name: `?ExecuteBootstrapProfileDeletion@OobeEsimTaskManager@@AEAAJPEAUIUnknown@@@Z`
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
- `0x180007380`
- `0x180016880`
- `0x18001cb10`
- `0x180034614`
- `0x180035f78`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007438`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007438`

## string_xrefs

- `0x1800073cc`: `onecoreuap\net\ux\mbmediamanager\lib\oobeesimtaskmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall OobeEsimTaskManager::ExecuteBootstrapProfileDeletion(OobeEsimTaskManager *this, struct IUnknown *a2)
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
    v7 = ((__int64 (__fastcall *)(__int64, __int64, _QWORD, _QWORD *))Windows::Internal::ComTaskPool::QueueTask__OobeEsimTaskManager::ExecuteBootstrapProfileDeletion_::_2_::_lambda_1___)(
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
      (void *)0x60,
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
0x180007380  push    rbp
0x180007382  push    rbx
0x180007383  push    rsi
0x180007384  push    rdi
0x180007385  mov     rbp, rsp
0x180007388  sub     rsp, 38h
0x18000738c  mov     rdi, rdx
0x18000738f  mov     rsi, rcx
0x180007392  mov     [rbp+arg_8], 0
0x18000739a  mov     rax, [rdx]
0x18000739d  mov     rbx, [rax]
0x1800073a0  lea     rcx, [rbp+arg_8]
0x1800073a4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800073a9  lea     r8, [rbp+arg_8]
0x1800073ad  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x1800073b4  mov     rcx, rdi
0x1800073b7  mov     rax, rbx
0x1800073ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073bf  mov     ebx, eax
0x1800073c1  test    eax, eax
0x1800073c3  jns     short loc_180007401
0x1800073c5  mov     rcx, [rbp+20h]; this
0x1800073c9  mov     r9d, eax; char *
0x1800073cc  lea     r8, aOnecoreuapNetU_11; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x1800073d3  mov     edx, 60h ; '`'; void *
0x1800073d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800073dd  nop
0x1800073de  mov     rcx, [rbp+arg_8]
0x1800073e2  test    rcx, rcx
0x1800073e5  jz      short loc_1800073FC
0x1800073e7  mov     [rbp+arg_8], 0
0x1800073ef  mov     rax, [rcx]
0x1800073f2  mov     rax, [rax+10h]
0x1800073f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073fb  nop
0x1800073fc  jmp     loc_180007481
0x180007401  test    rsi, rsi
0x180007404  jz      short loc_18000741A
0x180007406  lea     rcx, [rsi+2Ch]; this
0x18000740a  call    ?SafeUnknownIncrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownIncrementReference(long volatile &)
0x18000740f  mov     [rbp+var_18], rsi
0x180007413  call    ?SafeUnknownIncrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownIncrementReference(long volatile &)
0x180007418  jmp     short loc_18000741E
0x18000741a  mov     [rbp+var_18], rsi
0x18000741e  mov     rcx, [rbp+arg_8]
0x180007422  mov     [rbp+var_10], rcx
0x180007426  test    rcx, rcx
0x180007429  jz      short loc_180007438
0x18000742b  mov     rax, [rcx]
0x18000742e  mov     rax, [rax+8]
0x180007432  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007437  nop
0x180007438  call    cs:__imp_GetCurrentThreadId
0x18000743e  lea     r9, [rbp+var_18]
0x180007442  mov     r8d, eax
0x180007445  call    Windows__Internal__ComTaskPool__QueueTask__OobeEsimTaskManager__ExecuteBootstrapProfileDeletion____2____lambda_1___
0x18000744a  mov     ebx, eax
0x18000744c  lea     rcx, [rbp+var_18]
0x180007450  call    _OobeEsimTaskManager__ExecuteEasyConnect____2____lambda_1_____lambda_1_
0x180007455  test    ebx, ebx
0x180007457  jns     short loc_18000746B
0x180007459  mov     rcx, [rbp+arg_8]
0x18000745d  mov     rdx, [rcx]
0x180007460  mov     rax, [rdx+20h]
0x180007464  mov     edx, ebx
0x180007466  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000746b  test    rsi, rsi
0x18000746e  jz      short loc_180007478
0x180007470  mov     rcx, rsi
0x180007473  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UITaskHandler@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ITaskHandler,Microsoft::WRL::FtmBase>::Release(void)
0x180007478  lea     rcx, [rbp+arg_8]
0x18000747c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180007481  mov     eax, ebx
0x180007483  add     rsp, 38h
0x180007487  pop     rdi
0x180007488  pop     rsi
0x180007489  pop     rbx
0x18000748a  pop     rbp
0x18000748b  retn
```
