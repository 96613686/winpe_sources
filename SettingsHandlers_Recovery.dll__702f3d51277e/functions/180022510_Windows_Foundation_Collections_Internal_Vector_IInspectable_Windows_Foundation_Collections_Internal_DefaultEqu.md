# Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::add_VectorChanged(Windows::Foundation::Collections::VectorChangedEventHandler<IInspectable *> *,EventRegistrationToken *)

- ea: `0x180022510`
- end: `0x1800225a9`
- name: `?add_VectorChanged@?$Vector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@U?$VectorOptions@PEAUIInspectable@@$00$00$0A@@3456@@Internal@Collections@Foundation@Windows@@UEAAJPEAU?$VectorChangedEventHandler@PEAUIInspectable@@@345@PEAUEventRegistrationToken@@@Z`
- size: `153`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000f2cc`
- `0x180013350`
- `0x180022510`
- `0x18002b010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::add_VectorChanged(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  int v6; // ebx
  __int64 v7; // rcx
  __int64 v9; // [rsp+58h] [rbp+10h] BYREF

  if ( a2 )
  {
    v9 = 0;
    v6 = Windows::Internal::Details::CreateGitHelper<Windows::Foundation::Collections::VectorChangedEventHandler<IInspectable *>,Windows::Internal::GitPtr>(
           a2,
           &v9);
    if ( v6 >= 0 )
    {
      if ( v9 )
        v6 = Microsoft::WRL::EventSource<Windows::Foundation::Collections::VectorChangedEventHandler<SystemSettings::DataModel::ISettingItem *>,Microsoft::WRL::InvokeModeOptions<-2>>::AddInternal(
               (RTL_SRWLOCK *)(a1 + 136),
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
    v6 = -2147024809;
  }
  if ( v6 >= 0 )
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 160));
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180022510  push    rbx
0x180022512  push    rbp
0x180022513  push    rsi
0x180022514  push    rdi
0x180022515  sub     rsp, 28h
0x180022519  mov     rbp, r8
0x18002251c  mov     rsi, rdx
0x18002251f  mov     rdi, rcx
0x180022522  test    rdx, rdx
0x180022525  jnz     short loc_18002252E
0x180022527  mov     ebx, 80070057h
0x18002252c  jmp     short loc_180022593
0x18002252e  mov     [rsp+48h+arg_8], 0
0x180022537  lea     rdx, [rsp+48h+arg_8]
0x18002253c  mov     rcx, rsi
0x18002253f  call    ??$CreateGitHelper@U?$VectorChangedEventHandler@PEAUIInspectable@@@Collections@Foundation@Windows@@VGitPtr@Internal@4@@Details@Internal@Windows@@YAJPEAU?$VectorChangedEventHandler@PEAUIInspectable@@@Collections@Foundation@2@PEAPEAU3452@@Z; Windows::Internal::Details::CreateGitHelper<Windows::Foundation::Collections::VectorChangedEventHandler<IInspectable *>,Windows::Internal::GitPtr>(Windows::Foundation::Collections::VectorChangedEventHandler<IInspectable *> *,Windows::Foundation::Collections::VectorChangedEventHandler<IInspectable *> * *)
0x180022544  mov     ebx, eax
0x180022546  test    eax, eax
0x180022548  js      short loc_180022573
0x18002254a  mov     rdx, [rsp+48h+arg_8]
0x18002254f  test    rdx, rdx
0x180022552  jnz     short loc_18002255B
0x180022554  mov     ebx, 80070057h
0x180022559  jmp     short loc_180022573
0x18002255b  mov     r8, [rsi]
0x18002255e  lea     rcx, [rdi+88h]
0x180022565  mov     r9, rbp
0x180022568  mov     r8, [r8+18h]
0x18002256c  call    ?AddInternal@?$EventSource@U?$VectorChangedEventHandler@PEAUISettingItem@DataModel@SystemSettings@@@Collections@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@AEAAJPEAU?$VectorChangedEventHandler@PEAUISettingItem@DataModel@SystemSettings@@@Collections@Foundation@Windows@@PEAXPEAUEventRegistrationToken@@@Z; Microsoft::WRL::EventSource<Windows::Foundation::Collections::VectorChangedEventHandler<SystemSettings::DataModel::ISettingItem *>,Microsoft::WRL::InvokeModeOptions<-2>>::AddInternal(Windows::Foundation::Collections::VectorChangedEventHandler<SystemSettings::DataModel::ISettingItem *> *,void *,EventRegistrationToken *)
0x180022571  mov     ebx, eax
0x180022573  mov     rcx, [rsp+48h+arg_8]
0x180022578  test    rcx, rcx
0x18002257b  jz      short loc_180022593
0x18002257d  mov     [rsp+48h+arg_8], 0
0x180022586  mov     rax, [rcx]
0x180022589  mov     rax, [rax+10h]
0x18002258d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022592  nop
0x180022593  test    ebx, ebx
0x180022595  js      short loc_18002259E
0x180022597  lock inc dword ptr [rdi+0A0h]
0x18002259e  mov     eax, ebx
0x1800225a0  add     rsp, 28h
0x1800225a4  pop     rdi
0x1800225a5  pop     rsi
0x1800225a6  pop     rbp
0x1800225a7  pop     rbx
0x1800225a8  retn
```
