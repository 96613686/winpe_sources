# SystemButtons::SystemButtonsSingleton::add_RawSystemButtonsChanged(Windows::Foundation::ITypedEventHandler<Windows::Internal::Gaming::GipControllerWatcher *,Windows::Internal::Gaming::GipSystemButtonEventArgs *> *,EventRegistrationToken *)

- ea: `0x18000e060`
- end: `0x18000e0eb`
- name: `?add_RawSystemButtonsChanged@SystemButtonsSingleton@SystemButtons@@UEAAJPEAU?$ITypedEventHandler@PEAVGipControllerWatcher@Gaming@Internal@Windows@@PEAVGipSystemButtonEventArgs@234@@Foundation@Windows@@PEAUEventRegistrationToken@@@Z`
- size: `139`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000c42c`
- `0x18000cc9c`
- `0x18000e060`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall SystemButtons::SystemButtonsSingleton::add_RawSystemButtonsChanged(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  int v6; // ebx
  __int64 v7; // rcx
  __int64 v9; // [rsp+50h] [rbp+8h] BYREF

  if ( a2 )
  {
    v9 = 0;
    v6 = Windows::Internal::Details::CreateGitHelper<Windows::Foundation::ITypedEventHandler<Windows::Internal::Gaming::GipControllerWatcher *,Windows::Internal::Gaming::GipSystemButtonEventArgs *>,Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::ITypedEventHandler<Windows::Internal::Gaming::GipControllerWatcher *,Windows::Internal::Gaming::GipSystemButtonEventArgs *>>>(
           a2,
           &v9);
    if ( v6 >= 0 )
    {
      if ( v9 )
        v6 = Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::Gaming::GipControllerWatcher *,Windows::Internal::Gaming::GipSystemButtonEventArgs *>,Microsoft::WRL::InvokeModeOptions<2>>::AddInternal(
               a1 + 72,
               v9,
               *(_QWORD *)(*(_QWORD *)a2 + 24LL),
               a3);
      else
        v6 = -2147024809;
    }
    v7 = v9;
    if ( v9 )
    {
      v9 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000e060  push    rbx
0x18000e062  push    rbp
0x18000e063  push    rsi
0x18000e064  push    rdi
0x18000e065  sub     rsp, 28h
0x18000e069  mov     rsi, r8
0x18000e06c  mov     rdi, rdx
0x18000e06f  mov     rbp, rcx
0x18000e072  test    rdx, rdx
0x18000e075  jnz     short loc_18000E07E
0x18000e077  mov     ebx, 80070057h
0x18000e07c  jmp     short loc_18000E0E0
0x18000e07e  mov     [rsp+48h+arg_0], 0
0x18000e087  lea     rdx, [rsp+48h+arg_0]
0x18000e08c  mov     rcx, rdi
0x18000e08f  call    ??$CreateGitHelper@U?$ITypedEventHandler@PEAVGipControllerWatcher@Gaming@Internal@Windows@@PEAVGipSystemButtonEventArgs@234@@Foundation@Windows@@V?$GitPtrSupportsAgile@U?$ITypedEventHandler@PEAVGipControllerWatcher@Gaming@Internal@Windows@@PEAVGipSystemButtonEventArgs@234@@Foundation@Windows@@@Internal@3@@Details@Internal@Windows@@YAJPEAU?$ITypedEventHandler@PEAVGipControllerWatcher@Gaming@Internal@Windows@@PEAVGipSystemButtonEventArgs@234@@Foundation@2@PEAPEAU342@@Z; Windows::Internal::Details::CreateGitHelper<Windows::Foundation::ITypedEventHandler<Windows::Internal::Gaming::GipControllerWatcher *,Windows::Internal::Gaming::GipSystemButtonEventArgs *>,Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::ITypedEventHandler<Windows::Internal::Gaming::GipControllerWatcher *,Windows::Internal::Gaming::GipSystemButtonEventArgs *>>>(Windows::Foundation::ITypedEventHandler<Windows::Internal::Gaming::GipControllerWatcher *,Windows::Internal::Gaming::GipSystemButtonEventArgs *> *,Windows::Foundation::ITypedEventHandler<Windows::Internal::Gaming::GipControllerWatcher *,Windows::Internal::Gaming::GipSystemButtonEventArgs *> * *)
0x18000e094  mov     ebx, eax
0x18000e096  test    eax, eax
0x18000e098  js      short loc_18000E0C0
0x18000e09a  mov     rdx, [rsp+48h+arg_0]
0x18000e09f  test    rdx, rdx
0x18000e0a2  jnz     short loc_18000E0AB
0x18000e0a4  mov     ebx, 80070057h
0x18000e0a9  jmp     short loc_18000E0C0
0x18000e0ab  mov     r8, [rdi]
0x18000e0ae  lea     rcx, [rbp+48h]
0x18000e0b2  mov     r9, rsi
0x18000e0b5  mov     r8, [r8+18h]
0x18000e0b9  call    ?AddInternal@?$EventSource@U?$ITypedEventHandler@PEAVGipControllerWatcher@Gaming@Internal@Windows@@PEAVGipSystemButtonEventArgs@234@@Foundation@Windows@@U?$InvokeModeOptions@$01@WRL@Microsoft@@@WRL@Microsoft@@AEAAJPEAU?$ITypedEventHandler@PEAVGipControllerWatcher@Gaming@Internal@Windows@@PEAVGipSystemButtonEventArgs@234@@Foundation@Windows@@PEAXPEAUEventRegistrationToken@@@Z; Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::Gaming::GipControllerWatcher *,Windows::Internal::Gaming::GipSystemButtonEventArgs *>,Microsoft::WRL::InvokeModeOptions<2>>::AddInternal(Windows::Foundation::ITypedEventHandler<Windows::Internal::Gaming::GipControllerWatcher *,Windows::Internal::Gaming::GipSystemButtonEventArgs *> *,void *,EventRegistrationToken *)
0x18000e0be  mov     ebx, eax
0x18000e0c0  mov     rcx, [rsp+48h+arg_0]
0x18000e0c5  test    rcx, rcx
0x18000e0c8  jz      short loc_18000E0E0
0x18000e0ca  mov     [rsp+48h+arg_0], 0
0x18000e0d3  mov     rdx, [rcx]
0x18000e0d6  mov     rax, [rdx+10h]
0x18000e0da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0df  nop
0x18000e0e0  mov     eax, ebx
0x18000e0e2  add     rsp, 28h
0x18000e0e6  pop     rdi
0x18000e0e7  pop     rsi
0x18000e0e8  pop     rbp
0x18000e0e9  pop     rbx
0x18000e0ea  retn
```
