# Windows::Internal::ComTaskPool::QueueTask__Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolInvoke_::_3_::_lambda_1___

- ea: `0x180039f9c`
- end: `0x18003a01c`
- name: `Windows::Internal::ComTaskPool::QueueTask__Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolInvoke_::_3_::_lambda_1___`
- size: `128`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001bfa8`

## callees

- `0x180011cb0`
- `0x180039c70`
- `0x180039f9c`
- `0x180059010`

## import_xrefs

- `SHCORE!SHTaskPoolQueueTask` at `0x180039ff2`
- `SHCORE!SHTaskPoolQueueTask` at `0x180039ff2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::ComTaskPool::QueueTask__Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolInvoke_::_3_::_lambda_1___(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4)
{
  __int64 *v5; // rax
  __int64 v6; // rbx
  unsigned int v7; // edi
  _QWORD v9[3]; // [rsp+30h] [rbp-18h] BYREF

  v5 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolInvoke_::_3_::_lambda_1_____Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolInvoke_::_3_::_lambda_1____1(
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
0x180039f9c  mov     [rsp+arg_0], rbx
0x180039fa1  push    rdi
0x180039fa2  sub     rsp, 40h
0x180039fa6  mov     edi, r8d
0x180039fa9  mov     rdx, r9
0x180039fac  lea     rcx, [rsp+48h+var_18]
0x180039fb1  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CTaskWrapper__Windows__Networking__UX__Internal__MBCategory___SubmitThreadpoolInvoke____3____lambda_1_____Windows__Networking__UX__Internal__MBCategory___SubmitThreadpoolInvoke____3____lambda_1____1
0x180039fb6  mov     rbx, [rax]
0x180039fb9  mov     qword ptr [rax], 0
0x180039fc0  mov     rcx, [rsp+48h+var_18]
0x180039fc5  test    rcx, rcx
0x180039fc8  jz      short loc_180039FD8
0x180039fca  mov     [rsp+48h+var_18], 0
0x180039fd3  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x180039fd8  mov     [rsp+48h+var_20], 0
0x180039fe1  mov     [rsp+48h+var_28], rbx
0x180039fe6  xor     r9d, r9d
0x180039fe9  mov     r8d, edi
0x180039fec  lea     edx, [r9+2]
0x180039ff0  xor     ecx, ecx
0x180039ff2  call    cs:__imp_SHTaskPoolQueueTask
0x180039ff8  mov     edi, eax
0x180039ffa  test    rbx, rbx
0x180039ffd  jz      short loc_18003A00F
0x180039fff  mov     rdx, [rbx]
0x18003a002  mov     rcx, rbx
0x18003a005  mov     rax, [rdx+10h]
0x18003a009  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a00e  nop
0x18003a00f  mov     eax, edi
0x18003a011  mov     rbx, [rsp+48h+arg_0]
0x18003a016  add     rsp, 40h
0x18003a01a  pop     rdi
0x18003a01b  retn
```
