# IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IServiceProvider>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IServiceProvider>>)

- ea: `0x180014718`
- end: `0x180014730`
- name: `??$IID_PPV_ARGS_Helper@V?$ComPtr@UIServiceProvider@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIServiceProvider@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z`
- size: `24`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180014df0`

## callees

- `0x18000cd44`

## pseudocode

```c
__int64 __fastcall IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IServiceProvider>>(__int64 a1)
{
  __int64 v2; // [rsp+30h] [rbp+8h] BYREF

  v2 = a1;
  return Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IServiceProvider>>::operator void * *(&v2);
}

```

## disassembly

```asm
0x180014718  mov     [rsp+arg_0], rcx
0x18001471d  sub     rsp, 28h
0x180014721  lea     rcx, [rsp+28h+arg_0]
0x180014726  call    ??B?$ComPtrRef@V?$ComPtr@UIServiceProvider@@@WRL@Microsoft@@@Details@WRL@Microsoft@@QEBAPEAPEAXXZ
0x18001472b  add     rsp, 28h
0x18001472f  retn
```
