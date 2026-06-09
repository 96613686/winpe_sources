# Windows::Internal::ComTaskPool::QueueTask__Windows::Networking::UX::NetworkUXManager::OnInstanceRadioChange_::_22_::_lambda_1___

- ea: `0x180024188`
- end: `0x180024208`
- name: `Windows::Internal::ComTaskPool::QueueTask__Windows::Networking::UX::NetworkUXManager::OnInstanceRadioChange_::_22_::_lambda_1___`
- size: `128`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002e1f0`

## callees

- `0x180009e50`
- `0x180023bc0`
- `0x180024188`
- `0x180047010`

## import_xrefs

- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x1800241de`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x1800241de`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ComTaskPool::QueueTask__Windows::Networking::UX::NetworkUXManager::OnInstanceRadioChange_::_22_::_lambda_1___(
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

  v5 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__Windows::Networking::UX::NetworkUXManager::OnInstanceRadioChange_::_22_::_lambda_1_____Windows::Networking::UX::NetworkUXManager::OnInstanceRadioChange_::_22_::_lambda_1___(
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
0x180024188  mov     [rsp+arg_0], rbx
0x18002418d  push    rdi
0x18002418e  sub     rsp, 40h
0x180024192  mov     edi, r8d
0x180024195  mov     rdx, r9
0x180024198  lea     rcx, [rsp+48h+var_18]
0x18002419d  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CTaskWrapper__Windows__Networking__UX__NetworkUXManager__OnInstanceRadioChange____22____lambda_1_____Windows__Networking__UX__NetworkUXManager__OnInstanceRadioChange____22____lambda_1___
0x1800241a2  mov     rbx, [rax]
0x1800241a5  mov     qword ptr [rax], 0
0x1800241ac  mov     rcx, [rsp+48h+var_18]
0x1800241b1  test    rcx, rcx
0x1800241b4  jz      short loc_1800241C4
0x1800241b6  mov     [rsp+48h+var_18], 0
0x1800241bf  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x1800241c4  mov     [rsp+48h+var_20], 0
0x1800241cd  mov     [rsp+48h+var_28], rbx
0x1800241d2  xor     r9d, r9d
0x1800241d5  mov     r8d, edi
0x1800241d8  lea     edx, [r9+2]
0x1800241dc  xor     ecx, ecx
0x1800241de  call    cs:__imp_SHTaskPoolQueueTask
0x1800241e4  mov     edi, eax
0x1800241e6  test    rbx, rbx
0x1800241e9  jz      short loc_1800241FB
0x1800241eb  mov     rdx, [rbx]
0x1800241ee  mov     rcx, rbx
0x1800241f1  mov     rax, [rdx+10h]
0x1800241f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800241fa  nop
0x1800241fb  mov     eax, edi
0x1800241fd  mov     rbx, [rsp+48h+arg_0]
0x180024202  add     rsp, 40h
0x180024206  pop     rdi
0x180024207  retn
```
