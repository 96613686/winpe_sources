# Windows::Internal::ComTaskPool::QueueTask____Windows::Networking::UX::NetworkUXManager::_RefreshMMList_::_2_::_lambda_1_::operator()_::_2_::_lambda_1_::operator()_::_2_::_lambda_1___

- ea: `0x180023fd8`
- end: `0x180024056`
- name: `Windows::Internal::ComTaskPool::QueueTask____Windows::Networking::UX::NetworkUXManager::_RefreshMMList_::_2_::_lambda_1_::operator()_::_2_::_lambda_1_::operator()_::_2_::_lambda_1___`
- size: `126`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002901c`

## callees

- `0x180009e50`
- `0x180023a70`
- `0x180023fd8`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002400e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002400e`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18002402c`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18002402c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 Windows::Internal::ComTaskPool::QueueTask____Windows::Networking::UX::NetworkUXManager::_RefreshMMList_::_2_::_lambda_1_::operator()_::_2_::_lambda_1_::operator()_::_2_::_lambda_1___()
{
  __int64 *v0; // rax
  __int64 v1; // rbx
  __int64 v2; // rcx
  DWORD CurrentThreadId; // eax
  unsigned int v4; // edi
  __int64 v6; // [rsp+50h] [rbp+18h] BYREF

  v0 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper____Windows::Networking::UX::NetworkUXManager::_RefreshMMList_::_2_::_lambda_1_::operator()_::_2_::_lambda_1_::operator()_::_2_::_lambda_1_______Windows::Networking::UX::NetworkUXManager::_RefreshMMList_::_2_::_lambda_1_::operator()_::_2_::_lambda_1_::operator()_::_2_::_lambda_1___(&v6);
  v1 = *v0;
  *v0 = 0;
  v2 = v6;
  if ( v6 )
  {
    v6 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(v2);
  }
  CurrentThreadId = GetCurrentThreadId();
  v4 = SHTaskPoolQueueTask(0, 0, CurrentThreadId);
  if ( v1 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
  return v4;
}

```

## disassembly

```asm
0x180023fd8  mov     [rsp+arg_0], rbx
0x180023fdd  push    rdi
0x180023fde  sub     rsp, 30h
0x180023fe2  lea     rcx, [rsp+38h+arg_10]
0x180023fe7  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CTaskWrapper____Windows__Networking__UX__NetworkUXManager___RefreshMMList____2____lambda_1___operator______2____lambda_1___operator______2____lambda_1_______Windows__Networking__UX__NetworkUXManager___RefreshMMList____2____lambda_1___operator______2____lambda_1___operator______2____lambda_1___
0x180023fec  mov     rbx, [rax]
0x180023fef  mov     qword ptr [rax], 0
0x180023ff6  mov     rcx, [rsp+38h+arg_10]
0x180023ffb  test    rcx, rcx
0x180023ffe  jz      short loc_18002400E
0x180024000  mov     [rsp+38h+arg_10], 0
0x180024009  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x18002400e  call    cs:__imp_GetCurrentThreadId
0x180024014  mov     [rsp+38h+var_10], 0
0x18002401d  mov     [rsp+38h+var_18], rbx
0x180024022  xor     r9d, r9d
0x180024025  mov     r8d, eax
0x180024028  xor     edx, edx
0x18002402a  xor     ecx, ecx
0x18002402c  call    cs:__imp_SHTaskPoolQueueTask
0x180024032  mov     edi, eax
0x180024034  test    rbx, rbx
0x180024037  jz      short loc_180024049
0x180024039  mov     rdx, [rbx]
0x18002403c  mov     rcx, rbx
0x18002403f  mov     rax, [rdx+10h]
0x180024043  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024048  nop
0x180024049  mov     eax, edi
0x18002404b  mov     rbx, [rsp+38h+arg_0]
0x180024050  add     rsp, 30h
0x180024054  pop     rdi
0x180024055  retn
```
