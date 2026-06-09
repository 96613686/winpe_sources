# Windows::Internal::ComTaskPool::QueueTask__lambda_b9edf738e17dc43f74c922ccb415010b__&_

- ea: `0x18000cdbc`
- end: `0x18000ce3d`
- name: `Windows::Internal::ComTaskPool::QueueTask__lambda_b9edf738e17dc43f74c922ccb415010b__&_`
- size: `129`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180022280`

## callees

- `0x18000cb90`
- `0x18000cdbc`
- `0x180020b20`
- `0x180031010`

## import_xrefs

- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18000ce13`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18000ce13`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ComTaskPool::QueueTask__lambda_b9edf738e17dc43f74c922ccb415010b____(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4)
{
  __int64 *v5; // rax
  __int64 v6; // rbx
  unsigned int v7; // edi
  _QWORD v9[3]; // [rsp+30h] [rbp-18h] BYREF

  v5 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_b9edf738e17dc43f74c922ccb415010b______lambda_b9edf738e17dc43f74c922ccb415010b____(
                    v9,
                    a4);
  v6 = *v5;
  *v5 = 0;
  if ( v9[0] )
  {
    v9[0] = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release();
  }
  v7 = SHTaskPoolQueueTask(0, 4096, a3, 0, v6, 0);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  return v7;
}

```

## disassembly

```asm
0x18000cdbc  mov     [rsp+arg_0], rbx
0x18000cdc1  push    rdi
0x18000cdc2  sub     rsp, 40h
0x18000cdc6  mov     edi, r8d
0x18000cdc9  mov     rdx, r9
0x18000cdcc  lea     rcx, [rsp+48h+var_18]
0x18000cdd1  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_b9edf738e17dc43f74c922ccb415010b______lambda_b9edf738e17dc43f74c922ccb415010b____
0x18000cdd6  mov     rbx, [rax]
0x18000cdd9  mov     qword ptr [rax], 0
0x18000cde0  mov     rcx, [rsp+48h+var_18]
0x18000cde5  test    rcx, rcx
0x18000cde8  jz      short loc_18000CDF8
0x18000cdea  mov     [rsp+48h+var_18], 0
0x18000cdf3  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x18000cdf8  mov     [rsp+48h+var_20], 0
0x18000ce01  mov     [rsp+48h+var_28], rbx
0x18000ce06  xor     r9d, r9d
0x18000ce09  mov     r8d, edi
0x18000ce0c  mov     edx, 1000h
0x18000ce11  xor     ecx, ecx
0x18000ce13  call    cs:__imp_SHTaskPoolQueueTask
0x18000ce19  mov     edi, eax
0x18000ce1b  test    rbx, rbx
0x18000ce1e  jz      short loc_18000CE30
0x18000ce20  mov     rdx, [rbx]
0x18000ce23  mov     rcx, rbx
0x18000ce26  mov     rax, [rdx+10h]
0x18000ce2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce2f  nop
0x18000ce30  mov     eax, edi
0x18000ce32  mov     rbx, [rsp+48h+arg_0]
0x18000ce37  add     rsp, 40h
0x18000ce3b  pop     rdi
0x18000ce3c  retn
```
