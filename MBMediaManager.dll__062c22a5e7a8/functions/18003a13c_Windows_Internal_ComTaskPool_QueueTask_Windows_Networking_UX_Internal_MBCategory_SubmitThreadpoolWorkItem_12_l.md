# Windows::Internal::ComTaskPool::QueueTask__Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolWorkItem_::_12_::_lambda_1___

- ea: `0x18003a13c`
- end: `0x18003a1bc`
- name: `Windows::Internal::ComTaskPool::QueueTask__Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolWorkItem_::_12_::_lambda_1___`
- size: `128`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d1f8`

## callees

- `0x180011cb0`
- `0x180039e44`
- `0x18003a13c`
- `0x180059010`

## import_xrefs

- `SHCORE!SHTaskPoolQueueTask` at `0x18003a192`
- `SHCORE!SHTaskPoolQueueTask` at `0x18003a192`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ComTaskPool::QueueTask__Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolWorkItem_::_12_::_lambda_1___(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4)
{
  __int64 *v5; // rax
  __int64 v6; // rbx
  unsigned int v7; // edi
  _QWORD v9[3]; // [rsp+30h] [rbp-18h] BYREF

  v5 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolWorkItem_::_12_::_lambda_1_____Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolWorkItem_::_12_::_lambda_1___(
                    v9,
                    a4);
  v6 = *v5;
  *v5 = 0;
  if ( v9[0] )
  {
    v9[0] = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release();
  }
  v7 = SHTaskPoolQueueTask(0, 2, a3, 0, v6, 0);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  return v7;
}

```

## disassembly

```asm
0x18003a13c  mov     [rsp+arg_0], rbx
0x18003a141  push    rdi
0x18003a142  sub     rsp, 40h
0x18003a146  mov     edi, r8d
0x18003a149  mov     rdx, r9
0x18003a14c  lea     rcx, [rsp+48h+var_18]
0x18003a151  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CTaskWrapper__Windows__Networking__UX__Internal__MBCategory___SubmitThreadpoolWorkItem____12____lambda_1_____Windows__Networking__UX__Internal__MBCategory___SubmitThreadpoolWorkItem____12____lambda_1___
0x18003a156  mov     rbx, [rax]
0x18003a159  mov     qword ptr [rax], 0
0x18003a160  mov     rcx, [rsp+48h+var_18]
0x18003a165  test    rcx, rcx
0x18003a168  jz      short loc_18003A178
0x18003a16a  mov     [rsp+48h+var_18], 0
0x18003a173  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x18003a178  mov     [rsp+48h+var_20], 0
0x18003a181  mov     [rsp+48h+var_28], rbx
0x18003a186  xor     r9d, r9d
0x18003a189  mov     r8d, edi
0x18003a18c  lea     edx, [r9+2]
0x18003a190  xor     ecx, ecx
0x18003a192  call    cs:__imp_SHTaskPoolQueueTask
0x18003a198  mov     edi, eax
0x18003a19a  test    rbx, rbx
0x18003a19d  jz      short loc_18003A1AF
0x18003a19f  mov     rdx, [rbx]
0x18003a1a2  mov     rcx, rbx
0x18003a1a5  mov     rax, [rdx+10h]
0x18003a1a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a1ae  nop
0x18003a1af  mov     eax, edi
0x18003a1b1  mov     rbx, [rsp+48h+arg_0]
0x18003a1b6  add     rsp, 40h
0x18003a1ba  pop     rdi
0x18003a1bb  retn
```
