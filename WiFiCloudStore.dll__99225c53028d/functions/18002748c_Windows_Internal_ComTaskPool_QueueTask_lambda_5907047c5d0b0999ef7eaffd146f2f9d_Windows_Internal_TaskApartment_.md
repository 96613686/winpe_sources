# Windows::Internal::ComTaskPool::QueueTask<_lambda_5907047c5d0b0999ef7eaffd146f2f9d_>(Windows::Internal::TaskApartment,Windows::Internal::TaskOptions,ulong,_lambda_5907047c5d0b0999ef7eaffd146f2f9d_ &&)

- ea: `0x18002748c`
- end: `0x18002750d`
- name: `??$QueueTask@V_lambda_5907047c5d0b0999ef7eaffd146f2f9d_@@@ComTaskPool@Internal@Windows@@SAJW4TaskApartment@12@W4TaskOptions@12@K$$QEAV_lambda_5907047c5d0b0999ef7eaffd146f2f9d_@@@Z`
- size: `129`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180011db8`

## callees

- `0x18001b2d0`
- `0x18001e8dc`
- `0x18002748c`
- `0x180041010`

## import_xrefs

- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x1800274e3`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x1800274e3`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ComTaskPool::QueueTask<_lambda_5907047c5d0b0999ef7eaffd146f2f9d_>(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        _QWORD *a4)
{
  __int64 *v5; // rax
  __int64 v6; // rbx
  unsigned int v7; // edi
  _QWORD v9[3]; // [rsp+30h] [rbp-18h] BYREF

  v5 = Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_5907047c5d0b0999ef7eaffd146f2f9d_>,_lambda_5907047c5d0b0999ef7eaffd146f2f9d_>(
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
0x18002748c  mov     [rsp+arg_0], rbx
0x180027491  push    rdi
0x180027492  sub     rsp, 40h
0x180027496  mov     edi, r8d
0x180027499  mov     rdx, r9
0x18002749c  lea     rcx, [rsp+48h+var_18]
0x1800274a1  call    ??$Make@V?$CTaskWrapper@V_lambda_5907047c5d0b0999ef7eaffd146f2f9d_@@@ComTaskPool@Internal@Windows@@V_lambda_5907047c5d0b0999ef7eaffd146f2f9d_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@V_lambda_5907047c5d0b0999ef7eaffd146f2f9d_@@@ComTaskPool@Internal@Windows@@@12@$$QEAV_lambda_5907047c5d0b0999ef7eaffd146f2f9d_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_5907047c5d0b0999ef7eaffd146f2f9d_>,_lambda_5907047c5d0b0999ef7eaffd146f2f9d_>(_lambda_5907047c5d0b0999ef7eaffd146f2f9d_ &&)
0x1800274a6  mov     rbx, [rax]
0x1800274a9  mov     qword ptr [rax], 0
0x1800274b0  mov     rcx, [rsp+48h+var_18]
0x1800274b5  test    rcx, rcx
0x1800274b8  jz      short loc_1800274C8
0x1800274ba  mov     [rsp+48h+var_18], 0
0x1800274c3  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x1800274c8  mov     [rsp+48h+var_20], 0
0x1800274d1  mov     [rsp+48h+var_28], rbx
0x1800274d6  xor     r9d, r9d
0x1800274d9  mov     r8d, edi
0x1800274dc  mov     edx, 1000h
0x1800274e1  xor     ecx, ecx
0x1800274e3  call    cs:__imp_SHTaskPoolQueueTask
0x1800274e9  mov     edi, eax
0x1800274eb  test    rbx, rbx
0x1800274ee  jz      short loc_180027500
0x1800274f0  mov     rdx, [rbx]
0x1800274f3  mov     rcx, rbx
0x1800274f6  mov     rax, [rdx+10h]
0x1800274fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800274ff  nop
0x180027500  mov     eax, edi
0x180027502  mov     rbx, [rsp+48h+arg_0]
0x180027507  add     rsp, 40h
0x18002750b  pop     rdi
0x18002750c  retn
```
