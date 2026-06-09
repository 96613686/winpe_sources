# ??$MakeAndInitialize@VVirtualTouchPadServer@VirtualInput@Docking@@V123@PEAUVirtualTouchPadOptions@23@$$T@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VVirtualTouchPadServer@VirtualInput@Docking@@@WRL@Microsoft@@@012@$$QEAPEAUVirtualTouchPadOptions@VirtualInput@Docking@@$$QEA$$T@Z

- ea: `0x18000bca8`
- end: `0x18000bd01`
- name: `??$MakeAndInitialize@VVirtualTouchPadServer@VirtualInput@Docking@@V123@PEAUVirtualTouchPadOptions@23@$$T@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VVirtualTouchPadServer@VirtualInput@Docking@@@WRL@Microsoft@@@012@$$QEAPEAUVirtualTouchPadOptions@VirtualInput@Docking@@$$QEA$$T@Z`
- size: `89`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180012960`
- `0x1800148f8`

## callees

- `0x18000b810`
- `0x18000bb28`
- `0x18000cd44`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<Docking::VirtualInput::VirtualTouchPadServer,Docking::VirtualInput::VirtualTouchPadServer,Docking::VirtualInput::VirtualTouchPadOptions *,std::nullptr_t>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v4; // [rsp+20h] [rbp-28h]
  __int64 v5; // [rsp+28h] [rbp-20h]
  __int64 v6; // [rsp+30h] [rbp-18h]
  __int64 v7; // [rsp+50h] [rbp+8h] BYREF
  __int64 v8; // [rsp+58h] [rbp+10h]
  __int64 v9; // [rsp+60h] [rbp+18h]

  v9 = a3;
  v8 = a2;
  v7 = a1;
  v4 = Microsoft::WRL::Details::Forward<std::nullptr_t>(a3);
  v5 = Microsoft::WRL::Details::Forward<std::nullptr_t>(v8);
  v6 = Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IServiceProvider>>::operator void * *(&v7);
  return Microsoft::WRL::Details::MakeAndInitialize<Docking::VirtualInput::VirtualTouchPadServer,Docking::VirtualInput::VirtualTouchPadServer,Docking::VirtualInput::VirtualTouchPadOptions *,std::nullptr_t>(
           v6,
           v5,
           v4);
}

```

## disassembly

```asm
0x18000bca8  mov     [rsp+arg_10], r8
0x18000bcad  mov     [rsp+arg_8], rdx
0x18000bcb2  mov     [rsp+arg_0], rcx
0x18000bcb7  sub     rsp, 48h
0x18000bcbb  mov     rcx, [rsp+48h+arg_10]
0x18000bcc0  call    ??$Forward@$$T@Details@WRL@Microsoft@@YA$$QEA$$TAEA$$T@Z
0x18000bcc5  mov     [rsp+48h+var_28], rax
0x18000bcca  mov     rcx, [rsp+48h+arg_8]
0x18000bccf  call    ??$Forward@$$T@Details@WRL@Microsoft@@YA$$QEA$$TAEA$$T@Z
0x18000bcd4  mov     [rsp+48h+var_20], rax
0x18000bcd9  lea     rcx, [rsp+48h+arg_0]
0x18000bcde  call    ??B?$ComPtrRef@V?$ComPtr@UIServiceProvider@@@WRL@Microsoft@@@Details@WRL@Microsoft@@QEBAPEAPEAXXZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IServiceProvider>>::operator void * *(void)
0x18000bce3  mov     [rsp+48h+var_18], rax
0x18000bce8  mov     r8, [rsp+48h+var_28]
0x18000bced  mov     rdx, [rsp+48h+var_20]
0x18000bcf2  mov     rcx, [rsp+48h+var_18]
0x18000bcf7  call    ??$MakeAndInitialize@VVirtualTouchPadServer@VirtualInput@Docking@@V123@PEAUVirtualTouchPadOptions@23@$$T@Details@WRL@Microsoft@@YAJPEAPEAVVirtualTouchPadServer@VirtualInput@Docking@@$$QEAPEAUVirtualTouchPadOptions@45@$$QEA$$T@Z
0x18000bcfc  add     rsp, 48h
0x18000bd00  retn
```
