# Windows::Networking::UX::Internal::ComTaskPoolForCurrentEffectiveUser::QueueTask__Windows::Networking::UX::Internal::WlanMediaManager::_InvokeAllWlanMediaManagerNotifications_::_10_::_lambda_1___

- ea: `0x18001f798`
- end: `0x18001f8bb`
- name: `Windows::Networking::UX::Internal::ComTaskPoolForCurrentEffectiveUser::QueueTask__Windows::Networking::UX::Internal::WlanMediaManager::_InvokeAllWlanMediaManagerNotifications_::_10_::_lambda_1___`
- size: `291`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180027950`

## callees

- `0x180003ed0`
- `0x1800097b4`
- `0x18000bbf4`
- `0x18000d740`
- `0x18001efdc`
- `0x18001f798`
- `0x18001fea0`
- `0x180020164`
- `0x18007d4bc`
- `0x18008e010`

## import_xrefs

- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18001f832`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18001f832`

## string_xrefs

- `0x18001f868`: `onecoreuap\net\ux\inc\ThreadImpersonation.h`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::Internal::ComTaskPoolForCurrentEffectiveUser::QueueTask__Windows::Networking::UX::Internal::WlanMediaManager::_InvokeAllWlanMediaManagerNotifications_::_10_::_lambda_1___(
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
  Windows::Networking::UX::Internal::WlanMediaManager::_InvokeAllWlanMediaManagerNotifications_::_10_::_lambda_1_::_lambda_1_(
    v14,
    a4);
  v6 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__Windows::Networking::UX::Internal::ComTaskPoolForCurrentEffectiveUser::QueueTask__Windows::Networking::UX::Internal::WlanMediaManager::_InvokeAllWlanMediaManagerNotifications_::_10_::_lambda_1____::_3_::_lambda_1_____Windows::Networking::UX::Internal::ComTaskPoolForCurrentEffectiveUser::QueueTask__Windows::Networking::UX::Internal::WlanMediaManager::_InvokeAllWlanMediaManagerNotifications_::_10_::_lambda_1____::_3_::_lambda_1___(
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
  Windows::Networking::UX::Internal::ComTaskPoolForCurrentEffectiveUser::QueueTask__Windows::Networking::UX::Internal::WlanMediaManager::_InvokeAllWlanMediaManagerNotifications_::_10_::_lambda_1____::_3_::_lambda_1_::__lambda_1_(&v13);
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
0x18001f798  mov     [rsp+arg_0], rbx
0x18001f79d  push    rdi
0x18001f79e  sub     rsp, 0A0h
0x18001f7a5  mov     rax, cs:__security_cookie
0x18001f7ac  xor     rax, rsp
0x18001f7af  mov     [rsp+0A8h+var_18], rax
0x18001f7b7  mov     rdi, r9
0x18001f7ba  mov     ebx, r8d
0x18001f7bd  lea     rcx, [rsp+0A8h+phNewToken]; phNewToken
0x18001f7c2  call    ?GetCurrentEffectiveUserImpersonationToken@Internal@UX@Networking@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; Windows::Networking::UX::Internal::GetCurrentEffectiveUserImpersonationToken(void)
0x18001f7c7  mov     rax, [rsp+0A8h+phNewToken]
0x18001f7cc  mov     [rsp+0A8h+var_68], rax
0x18001f7d1  mov     [rsp+0A8h+phNewToken], 0
0x18001f7da  mov     rdx, rdi
0x18001f7dd  lea     rcx, [rsp+0A8h+var_60]
0x18001f7e2  call    _Windows__Networking__UX__Internal__WlanMediaManager___InvokeAllWlanMediaManagerNotifications____10____lambda_1____lambda_1_
0x18001f7e7  lea     rdx, [rsp+0A8h+var_68]
0x18001f7ec  lea     rcx, [rsp+0A8h+var_70]
0x18001f7f1  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CTaskWrapper__Windows__Networking__UX__Internal__ComTaskPoolForCurrentEffectiveUser__QueueTask__Windows__Networking__UX__Internal__WlanMediaManager___InvokeAllWlanMediaManagerNotifications____10____lambda_1_______3____lambda_1_____Windows__Networking__UX__Internal__ComTaskPoolForCurrentEffectiveUser__QueueTask__Windows__Networking__UX__Internal__WlanMediaManager___InvokeAllWlanMediaManagerNotifications____10____lambda_1_______3____lambda_1___
0x18001f7f6  mov     rdi, [rax]
0x18001f7f9  mov     qword ptr [rax], 0
0x18001f800  mov     rcx, [rsp+0A8h+var_70]
0x18001f805  test    rcx, rcx
0x18001f808  jz      short loc_18001F818
0x18001f80a  mov     [rsp+0A8h+var_70], 0
0x18001f813  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x18001f818  mov     [rsp+0A8h+var_80], 0
0x18001f821  mov     qword ptr [rsp+0A8h+var_88], rdi; int
0x18001f826  xor     r9d, r9d
0x18001f829  mov     r8d, ebx
0x18001f82c  lea     edx, [r9+2]
0x18001f830  xor     ecx, ecx
0x18001f832  call    cs:__imp_SHTaskPoolQueueTask
0x18001f838  mov     ebx, eax
0x18001f83a  test    rdi, rdi
0x18001f83d  jz      short loc_18001F84F
0x18001f83f  mov     rdx, [rdi]
0x18001f842  mov     rcx, rdi
0x18001f845  mov     rax, [rdx+10h]
0x18001f849  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f84e  nop
0x18001f84f  lea     rcx, [rsp+0A8h+var_68]
0x18001f854  call    _Windows__Networking__UX__Internal__ComTaskPoolForCurrentEffectiveUser__QueueTask__Windows__Networking__UX__Internal__WlanMediaManager___InvokeAllWlanMediaManagerNotifications____10____lambda_1_______3____lambda_1_____lambda_1_
0x18001f859  test    ebx, ebx
0x18001f85b  jns     short loc_18001F887
0x18001f85d  mov     rcx, [rsp+0A8h]; this
0x18001f865  mov     r9d, ebx; char *
0x18001f868  lea     r8, aOnecoreuapNetU_8; "onecoreuap\\net\\ux\\inc\\ThreadImperso"...
0x18001f86f  mov     edx, 26h ; '&'; void *
0x18001f874  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f879  lea     rcx, [rsp+0A8h+phNewToken]
0x18001f87e  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001f883  mov     eax, ebx
0x18001f885  jmp     short loc_18001F899
0x18001f887  lea     rcx, [rsp+0A8h+phNewToken]
0x18001f88c  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001f891  xor     eax, eax
0x18001f893  jmp     short loc_18001F899
0x18001f895  mov     eax, dword ptr [rsp+0A8h+phNewToken]
0x18001f899  mov     rcx, [rsp+0A8h+var_18]
0x18001f8a1  xor     rcx, rsp; StackCookie
0x18001f8a4  call    __security_check_cookie
0x18001f8a9  mov     rbx, [rsp+0A8h+arg_0]
0x18001f8b1  add     rsp, 0A0h
0x18001f8b8  pop     rdi
0x18001f8b9  retn
```
