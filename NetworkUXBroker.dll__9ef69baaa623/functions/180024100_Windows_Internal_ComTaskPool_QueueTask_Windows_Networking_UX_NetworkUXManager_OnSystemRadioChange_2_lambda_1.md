# Windows::Internal::ComTaskPool::QueueTask__Windows::Networking::UX::NetworkUXManager::OnSystemRadioChange_::_2_::_lambda_1___

- ea: `0x180024100`
- end: `0x180024180`
- name: `Windows::Internal::ComTaskPool::QueueTask__Windows::Networking::UX::NetworkUXManager::OnSystemRadioChange_::_2_::_lambda_1___`
- size: `128`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002e700`

## callees

- `0x180009e50`
- `0x180023b18`
- `0x180024100`
- `0x180047010`

## import_xrefs

- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180024156`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180024156`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::ComTaskPool::QueueTask__Windows::Networking::UX::NetworkUXManager::OnSystemRadioChange_::_2_::_lambda_1___(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4)
{
  __int64 *v5; // rax
  __int64 v6; // rbx
  __int64 v7; // rcx
  unsigned int v8; // edi
  _QWORD v10[3]; // [rsp+30h] [rbp-18h] BYREF

  v5 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__Windows::Networking::UX::NetworkUXManager::OnSystemRadioChange_::_2_::_lambda_1_____Windows::Networking::UX::NetworkUXManager::OnSystemRadioChange_::_2_::_lambda_1___(
                    v10,
                    a4);
  v6 = *v5;
  *v5 = 0;
  v7 = v10[0];
  if ( v10[0] )
  {
    v10[0] = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(v7);
  }
  v8 = SHTaskPoolQueueTask(0, 2, a3);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  return v8;
}

```

## disassembly

```asm
0x180024100  mov     [rsp+arg_0], rbx
0x180024105  push    rdi
0x180024106  sub     rsp, 40h
0x18002410a  mov     edi, r8d
0x18002410d  mov     rdx, r9
0x180024110  lea     rcx, [rsp+48h+var_18]
0x180024115  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CTaskWrapper__Windows__Networking__UX__NetworkUXManager__OnSystemRadioChange____2____lambda_1_____Windows__Networking__UX__NetworkUXManager__OnSystemRadioChange____2____lambda_1___
0x18002411a  mov     rbx, [rax]
0x18002411d  mov     qword ptr [rax], 0
0x180024124  mov     rcx, [rsp+48h+var_18]
0x180024129  test    rcx, rcx
0x18002412c  jz      short loc_18002413C
0x18002412e  mov     [rsp+48h+var_18], 0
0x180024137  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x18002413c  mov     [rsp+48h+var_20], 0
0x180024145  mov     [rsp+48h+var_28], rbx
0x18002414a  xor     r9d, r9d
0x18002414d  mov     r8d, edi
0x180024150  lea     edx, [r9+2]
0x180024154  xor     ecx, ecx
0x180024156  call    cs:__imp_SHTaskPoolQueueTask
0x18002415c  mov     edi, eax
0x18002415e  test    rbx, rbx
0x180024161  jz      short loc_180024173
0x180024163  mov     rdx, [rbx]
0x180024166  mov     rcx, rbx
0x180024169  mov     rax, [rdx+10h]
0x18002416d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024172  nop
0x180024173  mov     eax, edi
0x180024175  mov     rbx, [rsp+48h+arg_0]
0x18002417a  add     rsp, 40h
0x18002417e  pop     rdi
0x18002417f  retn
```
