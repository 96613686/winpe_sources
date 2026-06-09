# HostAppEnvironment::Setup(void)

- ea: `0x180040914`
- end: `0x180040af7`
- name: `?Setup@HostAppEnvironment@@QEAAJXZ`
- size: `483`
- prototype: `__int64 __fastcall(HostAppEnvironment *__hidden this)`
- caller_count: `4`
- callee_count: `11`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800312b0`
- `0x180039f50`
- `0x180039fd0`
- `0x18003bac0`

## callees

- `0x180004acc`
- `0x180007114`
- `0x18000d400`
- `0x18003808c`
- `0x18003fce4`
- `0x18003fd74`
- `0x18003fe94`
- `0x18003ff24`
- `0x1800401c0`
- `0x180040914`
- `0x18004e010`

## import_xrefs

- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x1800409e2`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180040a48`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180040aae`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x1800409e2`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180040a48`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180040aae`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180040965`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180040965`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18004093e`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18004093e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800409c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180040a2e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180040a94`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800409c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180040a2e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180040a94`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall HostAppEnvironment::Setup(HostAppEnvironment *this)
{
  HANDLE MutexW; // rdi
  HANDLE EventW; // rax
  const char *v4; // r9
  __int64 v6; // rax
  __int64 *v7; // rax
  __int64 v8; // rdi
  __int64 v9; // rcx
  DWORD CurrentThreadId; // eax
  __int64 v11; // rax
  __int64 *v12; // rax
  __int64 v13; // rdi
  __int64 v14; // rcx
  DWORD v15; // eax
  __int64 v16; // rax
  __int64 *v17; // rax
  __int64 v18; // rdi
  __int64 v19; // rcx
  DWORD v20; // eax
  __int64 v21; // rax
  __int64 v22; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  __int64 v24; // [rsp+50h] [rbp+20h] BYREF
  char v25; // [rsp+58h] [rbp+28h] BYREF

  if ( !*((_BYTE *)this + 32) )
  {
    MutexW = CreateMutexW(0, 1, L"Global\\Windows.User.OOBE");
    if ( MutexW != *((HANDLE *)this + 1) )
    {
      Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(this);
      *((_QWORD *)this + 1) = MutexW;
    }
    EventW = CreateEventW(0, 1, 0, 0);
    Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Attach(
      (char *)this + 16,
      EventW);
    if ( !*((_QWORD *)this + 3) )
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x62,
               (unsigned int)"shell\\lib\\cloudexperiencehostappmanager\\hostappenvironment.cpp",
               v4);
    v6 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v25, this);
    v7 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_46c2733e2687afde5245bd084a2f7edf_____lambda_46c2733e2687afde5245bd084a2f7edf___(
                      &v24,
                      v6);
    v8 = *v7;
    *v7 = 0;
    v9 = v24;
    if ( v24 )
    {
      v24 = 0;
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICreateObject>::Release(v9);
    }
    CurrentThreadId = GetCurrentThreadId();
    SHTaskPoolQueueTask(1, 0, CurrentThreadId, 0, v8, 0);
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    v11 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v25, this);
    v12 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_deee8152b7769f5e304c76a887ad1fef_____lambda_deee8152b7769f5e304c76a887ad1fef___(
                       &v24,
                       v11);
    v13 = *v12;
    *v12 = 0;
    v14 = v24;
    if ( v24 )
    {
      v24 = 0;
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICreateObject>::Release(v14);
    }
    v15 = GetCurrentThreadId();
    SHTaskPoolQueueTask(0, 0, v15, 0, v13, 0);
    if ( v13 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    v16 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v25, this);
    v17 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_7b0b85b4ff8a2c75a053dae0df721d9e_____lambda_7b0b85b4ff8a2c75a053dae0df721d9e___(
                       &v24,
                       v16);
    v18 = *v17;
    *v17 = 0;
    v19 = v24;
    if ( v24 )
    {
      v24 = 0;
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICreateObject>::Release(v19);
    }
    v20 = GetCurrentThreadId();
    SHTaskPoolQueueTask(0, 0, v20, 0, v18, 0);
    if ( v18 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    if ( !*((_BYTE *)this + 34) )
    {
      v21 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v24, this);
      Windows::Internal::ComTaskPool::QueueTask__lambda_983deade1ef85b175d24d05d87d8a1b3___(v22, v21);
    }
    *((_BYTE *)this + 32) = 1;
  }
  return 0;
}

```

## disassembly

```asm
0x180040914  mov     [rsp-18h+arg_10], rbx
0x180040919  push    rbp
0x18004091a  push    rsi
0x18004091b  push    rdi
0x18004091c  mov     rbp, rsp
0x18004091f  sub     rsp, 30h
0x180040923  mov     rbx, rcx
0x180040926  xor     esi, esi
0x180040928  cmp     [rcx+20h], sil
0x18004092c  jnz     loc_180040AE8
0x180040932  lea     r8, aGlobalWindowsU; "Global\\Windows.User.OOBE"
0x180040939  lea     edx, [rsi+1]; bInitialOwner
0x18004093c  xor     ecx, ecx; lpMutexAttributes
0x18004093e  call    cs:__imp_CreateMutexW
0x180040944  mov     rdi, rax
0x180040947  cmp     rax, [rbx+8]
0x18004094b  jz      short loc_180040959
0x18004094d  mov     rcx, rbx
0x180040950  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x180040955  mov     [rbx+8], rdi
0x180040959  xor     r9d, r9d; lpName
0x18004095c  xor     r8d, r8d; bInitialState
0x18004095f  lea     edx, [r9+1]; bManualReset
0x180040963  xor     ecx, ecx; lpEventAttributes
0x180040965  call    cs:__imp_CreateEventW
0x18004096b  mov     rdx, rax
0x18004096e  lea     rcx, [rbx+10h]
0x180040972  call    ?Attach@?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXPEAX@Z; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Attach(void *)
0x180040977  cmp     [rbx+18h], rsi
0x18004097b  jnz     short loc_180040997
0x18004097d  mov     rcx, [rbp+18h]; this
0x180040981  lea     r8, aShellLibCloude_1; "shell\\lib\\cloudexperiencehostappmanag"...
0x180040988  mov     edx, 62h ; 'b'; void *
0x18004098d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180040992  jmp     loc_180040AEA
0x180040997  mov     rdx, rbx
0x18004099a  lea     rcx, [rbp+arg_8]
0x18004099e  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x1800409a3  mov     rdx, rax
0x1800409a6  lea     rcx, [rbp+arg_0]
0x1800409aa  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_46c2733e2687afde5245bd084a2f7edf_____lambda_46c2733e2687afde5245bd084a2f7edf___
0x1800409af  mov     rdi, [rax]
0x1800409b2  mov     [rax], rsi
0x1800409b5  mov     rcx, [rbp+arg_0]
0x1800409b9  test    rcx, rcx
0x1800409bc  jz      short loc_1800409C7
0x1800409be  mov     [rbp+arg_0], rsi
0x1800409c2  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UICreateObject@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICreateObject>::Release(void)
0x1800409c7  call    cs:__imp_GetCurrentThreadId
0x1800409cd  mov     [rsp+30h+var_8], rsi
0x1800409d2  mov     [rsp+30h+var_10], rdi
0x1800409d7  xor     r9d, r9d
0x1800409da  mov     r8d, eax
0x1800409dd  xor     edx, edx
0x1800409df  lea     ecx, [rdx+1]
0x1800409e2  call    cs:__imp_SHTaskPoolQueueTask
0x1800409e8  nop
0x1800409e9  test    rdi, rdi
0x1800409ec  jz      short loc_1800409FE
0x1800409ee  mov     rax, [rdi]
0x1800409f1  mov     rcx, rdi
0x1800409f4  mov     rax, [rax+10h]
0x1800409f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800409fd  nop
0x1800409fe  mov     rdx, rbx
0x180040a01  lea     rcx, [rbp+arg_8]
0x180040a05  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x180040a0a  mov     rdx, rax
0x180040a0d  lea     rcx, [rbp+arg_0]
0x180040a11  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_deee8152b7769f5e304c76a887ad1fef_____lambda_deee8152b7769f5e304c76a887ad1fef___
0x180040a16  mov     rdi, [rax]
0x180040a19  mov     [rax], rsi
0x180040a1c  mov     rcx, [rbp+arg_0]
0x180040a20  test    rcx, rcx
0x180040a23  jz      short loc_180040A2E
0x180040a25  mov     [rbp+arg_0], rsi
0x180040a29  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UICreateObject@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICreateObject>::Release(void)
0x180040a2e  call    cs:__imp_GetCurrentThreadId
0x180040a34  mov     [rsp+30h+var_8], rsi
0x180040a39  mov     [rsp+30h+var_10], rdi
0x180040a3e  xor     r9d, r9d
0x180040a41  mov     r8d, eax
0x180040a44  xor     edx, edx
0x180040a46  xor     ecx, ecx
0x180040a48  call    cs:__imp_SHTaskPoolQueueTask
0x180040a4e  nop
0x180040a4f  test    rdi, rdi
0x180040a52  jz      short loc_180040A64
0x180040a54  mov     rax, [rdi]
0x180040a57  mov     rcx, rdi
0x180040a5a  mov     rax, [rax+10h]
0x180040a5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040a63  nop
0x180040a64  mov     rdx, rbx
0x180040a67  lea     rcx, [rbp+arg_8]
0x180040a6b  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x180040a70  mov     rdx, rax
0x180040a73  lea     rcx, [rbp+arg_0]
0x180040a77  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_7b0b85b4ff8a2c75a053dae0df721d9e_____lambda_7b0b85b4ff8a2c75a053dae0df721d9e___
0x180040a7c  mov     rdi, [rax]
0x180040a7f  mov     [rax], rsi
0x180040a82  mov     rcx, [rbp+arg_0]
0x180040a86  test    rcx, rcx
0x180040a89  jz      short loc_180040A94
0x180040a8b  mov     [rbp+arg_0], rsi
0x180040a8f  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UICreateObject@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICreateObject>::Release(void)
0x180040a94  call    cs:__imp_GetCurrentThreadId
0x180040a9a  mov     [rsp+30h+var_8], rsi
0x180040a9f  mov     [rsp+30h+var_10], rdi
0x180040aa4  xor     r9d, r9d
0x180040aa7  mov     r8d, eax
0x180040aaa  xor     edx, edx
0x180040aac  xor     ecx, ecx
0x180040aae  call    cs:__imp_SHTaskPoolQueueTask
0x180040ab4  nop
0x180040ab5  test    rdi, rdi
0x180040ab8  jz      short loc_180040ACA
0x180040aba  mov     rax, [rdi]
0x180040abd  mov     rcx, rdi
0x180040ac0  mov     rax, [rax+10h]
0x180040ac4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040ac9  nop
0x180040aca  cmp     [rbx+22h], sil
0x180040ace  jnz     short loc_180040AE4
0x180040ad0  mov     rdx, rbx
0x180040ad3  lea     rcx, [rbp+arg_0]
0x180040ad7  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x180040adc  mov     rdx, rax
0x180040adf  call    Windows__Internal__ComTaskPool__QueueTask__lambda_983deade1ef85b175d24d05d87d8a1b3___
0x180040ae4  mov     byte ptr [rbx+20h], 1
0x180040ae8  xor     eax, eax
0x180040aea  mov     rbx, [rsp+30h+arg_10]
0x180040aef  add     rsp, 30h
0x180040af3  pop     rdi
0x180040af4  pop     rsi
0x180040af5  pop     rbp
0x180040af6  retn
```
