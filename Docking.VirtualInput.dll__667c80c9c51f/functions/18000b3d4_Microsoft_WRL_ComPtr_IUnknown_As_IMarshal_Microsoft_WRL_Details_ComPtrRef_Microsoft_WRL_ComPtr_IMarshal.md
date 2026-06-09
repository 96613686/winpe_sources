# Microsoft::WRL::ComPtr<IUnknown>::As<IMarshal>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IMarshal>>)

- ea: `0x18000b3d4`
- end: `0x18000b43c`
- name: `??$As@UIMarshal@@@?$ComPtr@UIUnknown@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIMarshal@@@WRL@Microsoft@@@Details@12@@Z`
- size: `104`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000c464`

## callees

- `0x18000cd44`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<IUnknown>::As<IMarshal>(
        __int64 (__fastcall ****a1)(_QWORD, GUID *, __int64),
        __int64 a2)
{
  __int64 (__fastcall *v3)(_QWORD, GUID *, __int64); // [rsp+20h] [rbp-28h]
  __int64 v4; // [rsp+28h] [rbp-20h]
  __int64 (__fastcall ***v5)(_QWORD, GUID *, __int64); // [rsp+30h] [rbp-18h]
  __int64 v6; // [rsp+58h] [rbp+10h] BYREF

  v6 = a2;
  v5 = *a1;
  v3 = ***a1;
  v4 = Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IServiceProvider>>::operator void * *(&v6);
  return v3(v5, &GUID_00000003_0000_0000_c000_000000000046, v4);
}

```

## disassembly

```asm
0x18000b3d4  mov     [rsp+arg_8], rdx
0x18000b3d9  mov     [rsp+arg_0], rcx
0x18000b3de  sub     rsp, 48h
0x18000b3e2  mov     rax, [rsp+48h+arg_0]
0x18000b3e7  mov     rax, [rax]
0x18000b3ea  mov     [rsp+48h+var_18], rax
0x18000b3ef  mov     rax, [rsp+48h+arg_0]
0x18000b3f4  mov     rax, [rax]
0x18000b3f7  mov     rax, [rax]
0x18000b3fa  mov     rax, [rax]
0x18000b3fd  mov     [rsp+48h+var_28], rax
0x18000b402  lea     rcx, [rsp+48h+arg_8]
0x18000b407  call    ??B?$ComPtrRef@V?$ComPtr@UIServiceProvider@@@WRL@Microsoft@@@Details@WRL@Microsoft@@QEBAPEAPEAXXZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IServiceProvider>>::operator void * *(void)
0x18000b40c  mov     [rsp+48h+var_20], rax
0x18000b411  mov     rax, [rsp+48h+var_28]
0x18000b416  mov     [rsp+48h+var_10], rax
0x18000b41b  mov     r8, [rsp+48h+var_20]
0x18000b420  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x18000b427  mov     rcx, [rsp+48h+var_18]
0x18000b42c  mov     rax, [rsp+48h+var_10]
0x18000b431  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b436  nop
0x18000b437  add     rsp, 48h
0x18000b43b  retn
```
