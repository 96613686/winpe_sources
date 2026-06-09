# Windows::Internal::ComTaskPool::QueueTask__Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolWorkItemAndWait_::_3_::_lambda_1___

- ea: `0x18003a0ac`
- end: `0x18003a136`
- name: `Windows::Internal::ComTaskPool::QueueTask__Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolWorkItemAndWait_::_3_::_lambda_1___`
- size: `138`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d47c`

## callees

- `0x180011cb0`
- `0x180039da0`
- `0x18003a0ac`
- `0x180059010`

## import_xrefs

- `SHCORE!SHTaskPoolQueueTask` at `0x18003a107`
- `SHCORE!SHTaskPoolQueueTask` at `0x18003a107`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::ComTaskPool::QueueTask__Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolWorkItemAndWait_::_3_::_lambda_1___(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4)
{
  __int64 *v6; // rax
  __int64 v7; // rbx
  unsigned int v8; // edi
  _QWORD v10[3]; // [rsp+30h] [rbp-18h] BYREF

  v6 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolWorkItemAndWait_::_3_::_lambda_1_____Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolWorkItemAndWait_::_3_::_lambda_1___(
                    v10,
                    a4);
  v7 = *v6;
  *v6 = 0;
  if ( v10[0] )
  {
    v10[0] = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release();
  }
  v8 = SHTaskPoolQueueTask(0, a2, a3, 0, v7, 0);
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  return v8;
}

```

## disassembly

```asm
0x18003a0ac  mov     [rsp+arg_0], rbx
0x18003a0b1  mov     [rsp+arg_8], rsi
0x18003a0b6  push    rdi
0x18003a0b7  sub     rsp, 40h
0x18003a0bb  mov     edi, r8d
0x18003a0be  mov     esi, edx
0x18003a0c0  mov     rdx, r9
0x18003a0c3  lea     rcx, [rsp+48h+var_18]
0x18003a0c8  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CTaskWrapper__Windows__Networking__UX__Internal__MBCategory___SubmitThreadpoolWorkItemAndWait____3____lambda_1_____Windows__Networking__UX__Internal__MBCategory___SubmitThreadpoolWorkItemAndWait____3____lambda_1___
0x18003a0cd  mov     rbx, [rax]
0x18003a0d0  mov     qword ptr [rax], 0
0x18003a0d7  mov     rcx, [rsp+48h+var_18]
0x18003a0dc  test    rcx, rcx
0x18003a0df  jz      short loc_18003A0EF
0x18003a0e1  mov     [rsp+48h+var_18], 0
0x18003a0ea  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x18003a0ef  mov     [rsp+48h+var_20], 0
0x18003a0f8  mov     [rsp+48h+var_28], rbx
0x18003a0fd  xor     r9d, r9d
0x18003a100  mov     r8d, edi
0x18003a103  mov     edx, esi
0x18003a105  xor     ecx, ecx
0x18003a107  call    cs:__imp_SHTaskPoolQueueTask
0x18003a10d  mov     edi, eax
0x18003a10f  test    rbx, rbx
0x18003a112  jz      short loc_18003A124
0x18003a114  mov     rdx, [rbx]
0x18003a117  mov     rcx, rbx
0x18003a11a  mov     rax, [rdx+10h]
0x18003a11e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a123  nop
0x18003a124  mov     eax, edi
0x18003a126  mov     rbx, [rsp+48h+arg_0]
0x18003a12b  mov     rsi, [rsp+48h+arg_8]
0x18003a130  add     rsp, 40h
0x18003a134  pop     rdi
0x18003a135  retn
```
