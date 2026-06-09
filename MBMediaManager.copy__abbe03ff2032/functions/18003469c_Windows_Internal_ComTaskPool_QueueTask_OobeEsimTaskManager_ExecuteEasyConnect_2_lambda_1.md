# Windows::Internal::ComTaskPool::QueueTask__OobeEsimTaskManager::ExecuteEasyConnect_::_2_::_lambda_1___

- ea: `0x18003469c`
- end: `0x18003471d`
- name: `Windows::Internal::ComTaskPool::QueueTask__OobeEsimTaskManager::ExecuteEasyConnect_::_2_::_lambda_1___`
- size: `129`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007494`

## callees

- `0x180011cb0`
- `0x180034498`
- `0x18003469c`
- `0x180059010`

## import_xrefs

- `SHCORE!SHTaskPoolQueueTask` at `0x1800346f3`
- `SHCORE!SHTaskPoolQueueTask` at `0x1800346f3`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ComTaskPool::QueueTask__OobeEsimTaskManager::ExecuteEasyConnect_::_2_::_lambda_1___(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4)
{
  __int64 *v5; // rax
  __int64 v6; // rbx
  unsigned int v7; // edi
  _QWORD v9[3]; // [rsp+30h] [rbp-18h] BYREF

  v5 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__OobeEsimTaskManager::ExecuteEasyConnect_::_2_::_lambda_1_____OobeEsimTaskManager::ExecuteEasyConnect_::_2_::_lambda_1___(
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
0x18003469c  mov     [rsp+arg_0], rbx
0x1800346a1  push    rdi
0x1800346a2  sub     rsp, 40h
0x1800346a6  mov     edi, r8d
0x1800346a9  mov     rdx, r9
0x1800346ac  lea     rcx, [rsp+48h+var_18]
0x1800346b1  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CTaskWrapper__OobeEsimTaskManager__ExecuteEasyConnect____2____lambda_1_____OobeEsimTaskManager__ExecuteEasyConnect____2____lambda_1___
0x1800346b6  mov     rbx, [rax]
0x1800346b9  mov     qword ptr [rax], 0
0x1800346c0  mov     rcx, [rsp+48h+var_18]
0x1800346c5  test    rcx, rcx
0x1800346c8  jz      short loc_1800346D8
0x1800346ca  mov     [rsp+48h+var_18], 0
0x1800346d3  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x1800346d8  mov     [rsp+48h+var_20], 0
0x1800346e1  mov     [rsp+48h+var_28], rbx
0x1800346e6  xor     r9d, r9d
0x1800346e9  mov     r8d, edi
0x1800346ec  mov     edx, 5000h
0x1800346f1  xor     ecx, ecx
0x1800346f3  call    cs:__imp_SHTaskPoolQueueTask
0x1800346f9  mov     edi, eax
0x1800346fb  test    rbx, rbx
0x1800346fe  jz      short loc_180034710
0x180034700  mov     rdx, [rbx]
0x180034703  mov     rcx, rbx
0x180034706  mov     rax, [rdx+10h]
0x18003470a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003470f  nop
0x180034710  mov     eax, edi
0x180034712  mov     rbx, [rsp+48h+arg_0]
0x180034717  add     rsp, 40h
0x18003471b  pop     rdi
0x18003471c  retn
```
