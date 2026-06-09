# Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::add_VectorChanged(Windows::Foundation::Collections::VectorChangedEventHandler<SystemSettings::DataModel::ISettingItem *> *,EventRegistrationToken *)

- ea: `0x1800225b0`
- end: `0x180022649`
- name: `?add_VectorChanged@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@UEAAJPEAU?$VectorChangedEventHandler@PEAUISettingItem@DataModel@SystemSettings@@@345@PEAUEventRegistrationToken@@@Z`
- size: `153`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000f468`
- `0x180013350`
- `0x1800225b0`
- `0x18002b010`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::add_VectorChanged(
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
    v6 = Windows::Internal::Details::CreateGitHelper<Windows::Foundation::Collections::VectorChangedEventHandler<SystemSettings::DataModel::ISettingItem *>,Windows::Internal::GitPtr>(
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
0x1800225b0  push    rbx
0x1800225b2  push    rbp
0x1800225b3  push    rsi
0x1800225b4  push    rdi
0x1800225b5  sub     rsp, 28h
0x1800225b9  mov     rbp, r8
0x1800225bc  mov     rsi, rdx
0x1800225bf  mov     rdi, rcx
0x1800225c2  test    rdx, rdx
0x1800225c5  jnz     short loc_1800225CE
0x1800225c7  mov     ebx, 80070057h
0x1800225cc  jmp     short loc_180022633
0x1800225ce  mov     [rsp+48h+arg_8], 0
0x1800225d7  lea     rdx, [rsp+48h+arg_8]
0x1800225dc  mov     rcx, rsi
0x1800225df  call    ??$CreateGitHelper@U?$VectorChangedEventHandler@PEAUISettingItem@DataModel@SystemSettings@@@Collections@Foundation@Windows@@VGitPtr@Internal@4@@Details@Internal@Windows@@YAJPEAU?$VectorChangedEventHandler@PEAUISettingItem@DataModel@SystemSettings@@@Collections@Foundation@2@PEAPEAU3452@@Z; Windows::Internal::Details::CreateGitHelper<Windows::Foundation::Collections::VectorChangedEventHandler<SystemSettings::DataModel::ISettingItem *>,Windows::Internal::GitPtr>(Windows::Foundation::Collections::VectorChangedEventHandler<SystemSettings::DataModel::ISettingItem *> *,Windows::Foundation::Collections::VectorChangedEventHandler<SystemSettings::DataModel::ISettingItem *> * *)
0x1800225e4  mov     ebx, eax
0x1800225e6  test    eax, eax
0x1800225e8  js      short loc_180022613
0x1800225ea  mov     rdx, [rsp+48h+arg_8]
0x1800225ef  test    rdx, rdx
0x1800225f2  jnz     short loc_1800225FB
0x1800225f4  mov     ebx, 80070057h
0x1800225f9  jmp     short loc_180022613
0x1800225fb  mov     r8, [rsi]
0x1800225fe  lea     rcx, [rdi+88h]
0x180022605  mov     r9, rbp
0x180022608  mov     r8, [r8+18h]
0x18002260c  call    ?AddInternal@?$EventSource@U?$VectorChangedEventHandler@PEAUISettingItem@DataModel@SystemSettings@@@Collections@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@AEAAJPEAU?$VectorChangedEventHandler@PEAUISettingItem@DataModel@SystemSettings@@@Collections@Foundation@Windows@@PEAXPEAUEventRegistrationToken@@@Z; Microsoft::WRL::EventSource<Windows::Foundation::Collections::VectorChangedEventHandler<SystemSettings::DataModel::ISettingItem *>,Microsoft::WRL::InvokeModeOptions<-2>>::AddInternal(Windows::Foundation::Collections::VectorChangedEventHandler<SystemSettings::DataModel::ISettingItem *> *,void *,EventRegistrationToken *)
0x180022611  mov     ebx, eax
0x180022613  mov     rcx, [rsp+48h+arg_8]
0x180022618  test    rcx, rcx
0x18002261b  jz      short loc_180022633
0x18002261d  mov     [rsp+48h+arg_8], 0
0x180022626  mov     rax, [rcx]
0x180022629  mov     rax, [rax+10h]
0x18002262d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022632  nop
0x180022633  test    ebx, ebx
0x180022635  js      short loc_18002263E
0x180022637  lock inc dword ptr [rdi+0A0h]
0x18002263e  mov     eax, ebx
0x180022640  add     rsp, 28h
0x180022644  pop     rdi
0x180022645  pop     rsi
0x180022646  pop     rbp
0x180022647  pop     rbx
0x180022648  retn
```
