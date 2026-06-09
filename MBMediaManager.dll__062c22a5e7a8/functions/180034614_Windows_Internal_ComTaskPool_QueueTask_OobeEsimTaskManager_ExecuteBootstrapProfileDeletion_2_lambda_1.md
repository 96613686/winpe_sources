# Windows::Internal::ComTaskPool::QueueTask__OobeEsimTaskManager::ExecuteBootstrapProfileDeletion_::_2_::_lambda_1___

- ea: `0x180034614`
- end: `0x180034695`
- name: `Windows::Internal::ComTaskPool::QueueTask__OobeEsimTaskManager::ExecuteBootstrapProfileDeletion_::_2_::_lambda_1___`
- size: `129`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007380`

## callees

- `0x180011cb0`
- `0x1800343d0`
- `0x180034614`
- `0x180059010`

## import_xrefs

- `SHCORE!SHTaskPoolQueueTask` at `0x18003466b`
- `SHCORE!SHTaskPoolQueueTask` at `0x18003466b`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ComTaskPool::QueueTask__OobeEsimTaskManager::ExecuteBootstrapProfileDeletion_::_2_::_lambda_1___(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4)
{
  __int64 *v5; // rax
  __int64 v6; // rbx
  unsigned int v7; // edi
  _QWORD v9[3]; // [rsp+30h] [rbp-18h] BYREF

  v5 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__OobeEsimTaskManager::ExecuteBootstrapProfileDeletion_::_2_::_lambda_1_____OobeEsimTaskManager::ExecuteBootstrapProfileDeletion_::_2_::_lambda_1___(
                    v9,
                    a4);
  v6 = *v5;
  *v5 = 0;
  if ( v9[0] )
  {
    v9[0] = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release();
  }
  v7 = SHTaskPoolQueueTask(0, 20480, a3, 0, v6, 0);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  return v7;
}

```

## disassembly

```asm
0x180034614  mov     [rsp+arg_0], rbx
0x180034619  push    rdi
0x18003461a  sub     rsp, 40h
0x18003461e  mov     edi, r8d
0x180034621  mov     rdx, r9
0x180034624  lea     rcx, [rsp+48h+var_18]
0x180034629  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CTaskWrapper__OobeEsimTaskManager__ExecuteBootstrapProfileDeletion____2____lambda_1_____OobeEsimTaskManager__ExecuteBootstrapProfileDeletion____2____lambda_1___
0x18003462e  mov     rbx, [rax]
0x180034631  mov     qword ptr [rax], 0
0x180034638  mov     rcx, [rsp+48h+var_18]
0x18003463d  test    rcx, rcx
0x180034640  jz      short loc_180034650
0x180034642  mov     [rsp+48h+var_18], 0
0x18003464b  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x180034650  mov     [rsp+48h+var_20], 0
0x180034659  mov     [rsp+48h+var_28], rbx
0x18003465e  xor     r9d, r9d
0x180034661  mov     r8d, edi
0x180034664  mov     edx, 5000h
0x180034669  xor     ecx, ecx
0x18003466b  call    cs:__imp_SHTaskPoolQueueTask
0x180034671  mov     edi, eax
0x180034673  test    rbx, rbx
0x180034676  jz      short loc_180034688
0x180034678  mov     rdx, [rbx]
0x18003467b  mov     rcx, rbx
0x18003467e  mov     rax, [rdx+10h]
0x180034682  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034687  nop
0x180034688  mov     eax, edi
0x18003468a  mov     rbx, [rsp+48h+arg_0]
0x18003468f  add     rsp, 40h
0x180034693  pop     rdi
0x180034694  retn
```
