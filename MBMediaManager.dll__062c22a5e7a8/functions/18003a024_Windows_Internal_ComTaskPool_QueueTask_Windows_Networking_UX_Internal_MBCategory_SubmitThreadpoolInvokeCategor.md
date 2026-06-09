# Windows::Internal::ComTaskPool::QueueTask__Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolInvokeCategoryChange_::_3_::_lambda_1___

- ea: `0x18003a024`
- end: `0x18003a0a4`
- name: `Windows::Internal::ComTaskPool::QueueTask__Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolInvokeCategoryChange_::_3_::_lambda_1___`
- size: `128`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001c268`

## callees

- `0x180011cb0`
- `0x180039d0c`
- `0x18003a024`
- `0x180059010`

## import_xrefs

- `SHCORE!SHTaskPoolQueueTask` at `0x18003a07a`
- `SHCORE!SHTaskPoolQueueTask` at `0x18003a07a`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ComTaskPool::QueueTask__Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolInvokeCategoryChange_::_3_::_lambda_1___(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4)
{
  __int64 *v5; // rax
  __int64 v6; // rbx
  unsigned int v7; // edi
  _QWORD v9[3]; // [rsp+30h] [rbp-18h] BYREF

  v5 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolInvokeCategoryChange_::_3_::_lambda_1_____Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolInvokeCategoryChange_::_3_::_lambda_1___(
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
0x18003a024  mov     [rsp+arg_0], rbx
0x18003a029  push    rdi
0x18003a02a  sub     rsp, 40h
0x18003a02e  mov     edi, r8d
0x18003a031  mov     rdx, r9
0x18003a034  lea     rcx, [rsp+48h+var_18]
0x18003a039  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CTaskWrapper__Windows__Networking__UX__Internal__MBCategory___SubmitThreadpoolInvokeCategoryChange____3____lambda_1_____Windows__Networking__UX__Internal__MBCategory___SubmitThreadpoolInvokeCategoryChange____3____lambda_1___
0x18003a03e  mov     rbx, [rax]
0x18003a041  mov     qword ptr [rax], 0
0x18003a048  mov     rcx, [rsp+48h+var_18]
0x18003a04d  test    rcx, rcx
0x18003a050  jz      short loc_18003A060
0x18003a052  mov     [rsp+48h+var_18], 0
0x18003a05b  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x18003a060  mov     [rsp+48h+var_20], 0
0x18003a069  mov     [rsp+48h+var_28], rbx
0x18003a06e  xor     r9d, r9d
0x18003a071  mov     r8d, edi
0x18003a074  lea     edx, [r9+2]
0x18003a078  xor     ecx, ecx
0x18003a07a  call    cs:__imp_SHTaskPoolQueueTask
0x18003a080  mov     edi, eax
0x18003a082  test    rbx, rbx
0x18003a085  jz      short loc_18003A097
0x18003a087  mov     rdx, [rbx]
0x18003a08a  mov     rcx, rbx
0x18003a08d  mov     rax, [rdx+10h]
0x18003a091  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a096  nop
0x18003a097  mov     eax, edi
0x18003a099  mov     rbx, [rsp+48h+arg_0]
0x18003a09e  add     rsp, 40h
0x18003a0a2  pop     rdi
0x18003a0a3  retn
```
