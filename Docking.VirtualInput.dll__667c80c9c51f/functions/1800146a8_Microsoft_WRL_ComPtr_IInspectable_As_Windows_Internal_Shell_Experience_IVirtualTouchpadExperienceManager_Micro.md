# Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>>)

- ea: `0x1800146a8`
- end: `0x180014710`
- name: `??$As@UIVirtualTouchpadExperienceManager@Experience@Shell@Internal@Windows@@@?$ComPtr@UIInspectable@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIVirtualTouchpadExperienceManager@Experience@Shell@Internal@Windows@@@WRL@Microsoft@@@Details@12@@Z`
- size: `104`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180014df0`

## callees

- `0x18000cd44`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>(
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
  return v3(v5, &GUID_17c4ec91_62df_486d_aa0d_6a11c725e414, v4);
}

```

## disassembly

```asm
0x1800146a8  mov     [rsp+arg_8], rdx
0x1800146ad  mov     [rsp+arg_0], rcx
0x1800146b2  sub     rsp, 48h
0x1800146b6  mov     rax, [rsp+48h+arg_0]
0x1800146bb  mov     rax, [rax]
0x1800146be  mov     [rsp+48h+var_18], rax
0x1800146c3  mov     rax, [rsp+48h+arg_0]
0x1800146c8  mov     rax, [rax]
0x1800146cb  mov     rax, [rax]
0x1800146ce  mov     rax, [rax]
0x1800146d1  mov     [rsp+48h+var_28], rax
0x1800146d6  lea     rcx, [rsp+48h+arg_8]
0x1800146db  call    ??B?$ComPtrRef@V?$ComPtr@UIServiceProvider@@@WRL@Microsoft@@@Details@WRL@Microsoft@@QEBAPEAPEAXXZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IServiceProvider>>::operator void * *(void)
0x1800146e0  mov     [rsp+48h+var_20], rax
0x1800146e5  mov     rax, [rsp+48h+var_28]
0x1800146ea  mov     [rsp+48h+var_10], rax
0x1800146ef  mov     r8, [rsp+48h+var_20]
0x1800146f4  lea     rdx, _GUID_17c4ec91_62df_486d_aa0d_6a11c725e414
0x1800146fb  mov     rcx, [rsp+48h+var_18]
0x180014700  mov     rax, [rsp+48h+var_10]
0x180014705  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001470a  nop
0x18001470b  add     rsp, 48h
0x18001470f  retn
```
