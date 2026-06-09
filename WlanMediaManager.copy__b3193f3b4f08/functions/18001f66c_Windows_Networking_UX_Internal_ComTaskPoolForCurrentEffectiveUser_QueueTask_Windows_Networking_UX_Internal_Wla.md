# Windows::Networking::UX::Internal::ComTaskPoolForCurrentEffectiveUser::QueueTask__Windows::Networking::UX::Internal::WlanMediaManager::RunComTask_::_5_::_lambda_1___

- ea: `0x18001f66c`
- end: `0x18001f78f`
- name: `Windows::Networking::UX::Internal::ComTaskPoolForCurrentEffectiveUser::QueueTask__Windows::Networking::UX::Internal::WlanMediaManager::RunComTask_::_5_::_lambda_1___`
- size: `291`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800254c0`

## callees

- `0x180003ed0`
- `0x1800097b4`
- `0x18000bbf4`
- `0x18000d740`
- `0x18001ef38`
- `0x18001f66c`
- `0x18001fe28`
- `0x18002013c`
- `0x18007d4bc`
- `0x18008e010`

## import_xrefs

- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18001f706`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18001f706`

## string_xrefs

- `0x18001f73c`: `onecoreuap\net\ux\inc\ThreadImpersonation.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall Windows::Networking::UX::Internal::ComTaskPoolForCurrentEffectiveUser::QueueTask__Windows::Networking::UX::Internal::WlanMediaManager::RunComTask_::_5_::_lambda_1___(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4)
{
  __int64 *v6; // rax
  __int64 v7; // rdi
  int v8; // ebx
  int v10; // [rsp+20h] [rbp-88h]
  void *phNewToken; // [rsp+30h] [rbp-78h] BYREF
  __int64 v12; // [rsp+38h] [rbp-70h] BYREF
  void *v13; // [rsp+40h] [rbp-68h] BYREF
  _BYTE v14[72]; // [rsp+48h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  Windows::Networking::UX::Internal::GetCurrentEffectiveUserImpersonationToken(&phNewToken);
  v13 = phNewToken;
  phNewToken = 0;
  Windows::Networking::UX::Internal::WlanMediaManager::RunComTask_::_10_::_lambda_2_::_lambda_2_(v14, a4);
  v6 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__Windows::Networking::UX::Internal::ComTaskPoolForCurrentEffectiveUser::QueueTask__Windows::Networking::UX::Internal::WlanMediaManager::RunComTask_::_5_::_lambda_1____::_3_::_lambda_1_____Windows::Networking::UX::Internal::ComTaskPoolForCurrentEffectiveUser::QueueTask__Windows::Networking::UX::Internal::WlanMediaManager::RunComTask_::_5_::_lambda_1____::_3_::_lambda_1___(
                    &v12,
                    &v13);
  v7 = *v6;
  *v6 = 0;
  if ( v12 )
  {
    v12 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release();
  }
  v8 = SHTaskPoolQueueTask(0, 2, a3, 0, v7, 0);
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  Windows::Networking::UX::Internal::ComTaskPoolForCurrentEffectiveUser::QueueTask__Windows::Networking::UX::Internal::WlanMediaManager::RunComTask_::_5_::_lambda_1____::_3_::_lambda_1_::__lambda_1_(&v13);
  if ( v8 >= 0 )
  {
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x26,
      (unsigned int)"onecoreuap\\net\\ux\\inc\\ThreadImpersonation.h",
      (const char *)(unsigned int)v8,
      v10);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
    return (unsigned int)v8;
  }
}

```

## disassembly

```asm
0x18001f66c  mov     [rsp+arg_0], rbx
0x18001f671  push    rdi
0x18001f672  sub     rsp, 0A0h
0x18001f679  mov     rax, cs:__security_cookie
0x18001f680  xor     rax, rsp
0x18001f683  mov     [rsp+0A8h+var_18], rax
0x18001f68b  mov     rdi, r9
0x18001f68e  mov     ebx, r8d
0x18001f691  lea     rcx, [rsp+0A8h+phNewToken]; phNewToken
0x18001f696  call    ?GetCurrentEffectiveUserImpersonationToken@Internal@UX@Networking@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; Windows::Networking::UX::Internal::GetCurrentEffectiveUserImpersonationToken(void)
0x18001f69b  mov     rax, [rsp+0A8h+phNewToken]
0x18001f6a0  mov     [rsp+0A8h+var_68], rax
0x18001f6a5  mov     [rsp+0A8h+phNewToken], 0
0x18001f6ae  mov     rdx, rdi
0x18001f6b1  lea     rcx, [rsp+0A8h+var_60]
0x18001f6b6  call    _Windows__Networking__UX__Internal__WlanMediaManager__RunComTask____10____lambda_2____lambda_2_
0x18001f6bb  lea     rdx, [rsp+0A8h+var_68]
0x18001f6c0  lea     rcx, [rsp+0A8h+var_70]
0x18001f6c5  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CTaskWrapper__Windows__Networking__UX__Internal__ComTaskPoolForCurrentEffectiveUser__QueueTask__Windows__Networking__UX__Internal__WlanMediaManager__RunComTask____5____lambda_1_______3____lambda_1_____Windows__Networking__UX__Internal__ComTaskPoolForCurrentEffectiveUser__QueueTask__Windows__Networking__UX__Internal__WlanMediaManager__RunComTask____5____lambda_1_______3____lambda_1___
0x18001f6ca  mov     rdi, [rax]
0x18001f6cd  mov     qword ptr [rax], 0
0x18001f6d4  mov     rcx, [rsp+0A8h+var_70]
0x18001f6d9  test    rcx, rcx
0x18001f6dc  jz      short loc_18001F6EC
0x18001f6de  mov     [rsp+0A8h+var_70], 0
0x18001f6e7  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x18001f6ec  mov     [rsp+0A8h+var_80], 0
0x18001f6f5  mov     qword ptr [rsp+0A8h+var_88], rdi; int
0x18001f6fa  xor     r9d, r9d
0x18001f6fd  mov     r8d, ebx
0x18001f700  lea     edx, [r9+2]
0x18001f704  xor     ecx, ecx
0x18001f706  call    cs:__imp_SHTaskPoolQueueTask
0x18001f70c  mov     ebx, eax
0x18001f70e  test    rdi, rdi
0x18001f711  jz      short loc_18001F723
0x18001f713  mov     rdx, [rdi]
0x18001f716  mov     rcx, rdi
0x18001f719  mov     rax, [rdx+10h]
0x18001f71d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f722  nop
0x18001f723  lea     rcx, [rsp+0A8h+var_68]
0x18001f728  call    _Windows__Networking__UX__Internal__ComTaskPoolForCurrentEffectiveUser__QueueTask__Windows__Networking__UX__Internal__WlanMediaManager__RunComTask____5____lambda_1_______3____lambda_1_____lambda_1_
0x18001f72d  test    ebx, ebx
0x18001f72f  jns     short loc_18001F75B
0x18001f731  mov     rcx, [rsp+0A8h]; this
0x18001f739  mov     r9d, ebx; char *
0x18001f73c  lea     r8, aOnecoreuapNetU_8; "onecoreuap\\net\\ux\\inc\\ThreadImperso"...
0x18001f743  mov     edx, 26h ; '&'; void *
0x18001f748  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f74d  lea     rcx, [rsp+0A8h+phNewToken]
0x18001f752  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001f757  mov     eax, ebx
0x18001f759  jmp     short loc_18001F76D
0x18001f75b  lea     rcx, [rsp+0A8h+phNewToken]
0x18001f760  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001f765  xor     eax, eax
0x18001f767  jmp     short loc_18001F76D
0x18001f769  mov     eax, dword ptr [rsp+0A8h+phNewToken]
0x18001f76d  mov     rcx, [rsp+0A8h+var_18]
0x18001f775  xor     rcx, rsp; StackCookie
0x18001f778  call    __security_check_cookie
0x18001f77d  mov     rbx, [rsp+0A8h+arg_0]
0x18001f785  add     rsp, 0A0h
0x18001f78c  pop     rdi
0x18001f78d  retn
```
