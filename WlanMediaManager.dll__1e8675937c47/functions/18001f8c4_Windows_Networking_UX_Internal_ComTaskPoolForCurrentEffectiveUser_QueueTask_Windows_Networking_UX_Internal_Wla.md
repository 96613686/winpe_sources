# Windows::Networking::UX::Internal::ComTaskPoolForCurrentEffectiveUser::QueueTask__Windows::Networking::UX::Internal::WlanMediaManager::RunComTask_::_10_::_lambda_2___

- ea: `0x18001f8c4`
- end: `0x18001f9e7`
- name: `Windows::Networking::UX::Internal::ComTaskPoolForCurrentEffectiveUser::QueueTask__Windows::Networking::UX::Internal::WlanMediaManager::RunComTask_::_10_::_lambda_2___`
- size: `291`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64)`
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
- `0x18001f080`
- `0x18001f8c4`
- `0x18001fe28`
- `0x18002018c`
- `0x18007d4bc`
- `0x18008e010`

## import_xrefs

- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18001f95e`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18001f95e`

## string_xrefs

- `0x18001f994`: `onecoreuap\net\ux\inc\ThreadImpersonation.h`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::Internal::ComTaskPoolForCurrentEffectiveUser::QueueTask__Windows::Networking::UX::Internal::WlanMediaManager::RunComTask_::_10_::_lambda_2___(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4)
{
  __int64 *v6; // rax
  __int64 v7; // rdi
  __int64 v8; // rcx
  int v9; // ebx
  void *phNewToken; // [rsp+30h] [rbp-78h] BYREF
  __int64 v12; // [rsp+38h] [rbp-70h] BYREF
  void *v13; // [rsp+40h] [rbp-68h] BYREF
  _BYTE v14[72]; // [rsp+48h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  Windows::Networking::UX::Internal::GetCurrentEffectiveUserImpersonationToken(&phNewToken);
  v13 = phNewToken;
  phNewToken = 0;
  Windows::Networking::UX::Internal::WlanMediaManager::RunComTask_::_10_::_lambda_2_::_lambda_2_(v14, a4);
  v6 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__Windows::Networking::UX::Internal::ComTaskPoolForCurrentEffectiveUser::QueueTask__Windows::Networking::UX::Internal::WlanMediaManager::RunComTask_::_10_::_lambda_2____::_3_::_lambda_1_____Windows::Networking::UX::Internal::ComTaskPoolForCurrentEffectiveUser::QueueTask__Windows::Networking::UX::Internal::WlanMediaManager::RunComTask_::_10_::_lambda_2____::_3_::_lambda_1___(
                    &v12,
                    &v13);
  v7 = *v6;
  *v6 = 0;
  v8 = v12;
  if ( v12 )
  {
    v12 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(v8);
  }
  v9 = SHTaskPoolQueueTask(0, 2, a3);
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  Windows::Networking::UX::Internal::ComTaskPoolForCurrentEffectiveUser::QueueTask__Windows::Networking::UX::Internal::WlanMediaManager::RunComTask_::_10_::_lambda_2____::_3_::_lambda_1_::__lambda_1_(&v13);
  if ( v9 >= 0 )
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
      (const char *)(unsigned int)v9,
      v7);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
    return (unsigned int)v9;
  }
}

```

## disassembly

```asm
0x18001f8c4  mov     [rsp+arg_0], rbx
0x18001f8c9  push    rdi
0x18001f8ca  sub     rsp, 0A0h
0x18001f8d1  mov     rax, cs:__security_cookie
0x18001f8d8  xor     rax, rsp
0x18001f8db  mov     [rsp+0A8h+var_18], rax
0x18001f8e3  mov     rdi, r9
0x18001f8e6  mov     ebx, r8d
0x18001f8e9  lea     rcx, [rsp+0A8h+phNewToken]; phNewToken
0x18001f8ee  call    ?GetCurrentEffectiveUserImpersonationToken@Internal@UX@Networking@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; Windows::Networking::UX::Internal::GetCurrentEffectiveUserImpersonationToken(void)
0x18001f8f3  mov     rax, [rsp+0A8h+phNewToken]
0x18001f8f8  mov     [rsp+0A8h+var_68], rax
0x18001f8fd  mov     [rsp+0A8h+phNewToken], 0
0x18001f906  mov     rdx, rdi
0x18001f909  lea     rcx, [rsp+0A8h+var_60]
0x18001f90e  call    _Windows__Networking__UX__Internal__WlanMediaManager__RunComTask____10____lambda_2____lambda_2_
0x18001f913  lea     rdx, [rsp+0A8h+var_68]
0x18001f918  lea     rcx, [rsp+0A8h+var_70]
0x18001f91d  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CTaskWrapper__Windows__Networking__UX__Internal__ComTaskPoolForCurrentEffectiveUser__QueueTask__Windows__Networking__UX__Internal__WlanMediaManager__RunComTask____10____lambda_2_______3____lambda_1_____Windows__Networking__UX__Internal__ComTaskPoolForCurrentEffectiveUser__QueueTask__Windows__Networking__UX__Internal__WlanMediaManager__RunComTask____10____lambda_2_______3____lambda_1___
0x18001f922  mov     rdi, [rax]
0x18001f925  mov     qword ptr [rax], 0
0x18001f92c  mov     rcx, [rsp+0A8h+var_70]
0x18001f931  test    rcx, rcx
0x18001f934  jz      short loc_18001F944
0x18001f936  mov     [rsp+0A8h+var_70], 0
0x18001f93f  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x18001f944  mov     [rsp+0A8h+var_80], 0
0x18001f94d  mov     qword ptr [rsp+0A8h+var_88], rdi; int
0x18001f952  xor     r9d, r9d
0x18001f955  mov     r8d, ebx
0x18001f958  lea     edx, [r9+2]
0x18001f95c  xor     ecx, ecx
0x18001f95e  call    cs:__imp_SHTaskPoolQueueTask
0x18001f964  mov     ebx, eax
0x18001f966  test    rdi, rdi
0x18001f969  jz      short loc_18001F97B
0x18001f96b  mov     rdx, [rdi]
0x18001f96e  mov     rcx, rdi
0x18001f971  mov     rax, [rdx+10h]
0x18001f975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f97a  nop
0x18001f97b  lea     rcx, [rsp+0A8h+var_68]
0x18001f980  call    _Windows__Networking__UX__Internal__ComTaskPoolForCurrentEffectiveUser__QueueTask__Windows__Networking__UX__Internal__WlanMediaManager__RunComTask____10____lambda_2_______3____lambda_1_____lambda_1_
0x18001f985  test    ebx, ebx
0x18001f987  jns     short loc_18001F9B3
0x18001f989  mov     rcx, [rsp+0A8h]; this
0x18001f991  mov     r9d, ebx; char *
0x18001f994  lea     r8, aOnecoreuapNetU_8; "onecoreuap\\net\\ux\\inc\\ThreadImperso"...
0x18001f99b  mov     edx, 26h ; '&'; void *
0x18001f9a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f9a5  lea     rcx, [rsp+0A8h+phNewToken]
0x18001f9aa  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001f9af  mov     eax, ebx
0x18001f9b1  jmp     short loc_18001F9C5
0x18001f9b3  lea     rcx, [rsp+0A8h+phNewToken]
0x18001f9b8  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001f9bd  xor     eax, eax
0x18001f9bf  jmp     short loc_18001F9C5
0x18001f9c1  mov     eax, dword ptr [rsp+0A8h+phNewToken]
0x18001f9c5  mov     rcx, [rsp+0A8h+var_18]
0x18001f9cd  xor     rcx, rsp; StackCookie
0x18001f9d0  call    __security_check_cookie
0x18001f9d5  mov     rbx, [rsp+0A8h+arg_0]
0x18001f9dd  add     rsp, 0A0h
0x18001f9e4  pop     rdi
0x18001f9e5  retn
```
