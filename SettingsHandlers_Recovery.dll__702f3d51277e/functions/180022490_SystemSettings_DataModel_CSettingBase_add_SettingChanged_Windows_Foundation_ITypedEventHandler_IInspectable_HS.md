# SystemSettings::DataModel::CSettingBase::add_SettingChanged(Windows::Foundation::ITypedEventHandler<IInspectable *,HSTRING__ *> *,EventRegistrationToken *)

- ea: `0x180022490`
- end: `0x1800224ff`
- name: `?add_SettingChanged@CSettingBase@DataModel@SystemSettings@@UEAAJPEAU?$ITypedEventHandler@PEAUIInspectable@@PEAUHSTRING__@@@Foundation@Windows@@PEAUEventRegistrationToken@@@Z`
- size: `111`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180008c24`
- `0x180013350`
- `0x180022490`

## import_xrefs

- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1800224e2`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1800224e2`

## pseudocode

```c
__int64 __fastcall SystemSettings::DataModel::CSettingBase::add_SettingChanged(RTL_SRWLOCK *a1, __int64 a2, PVOID *a3)
{
  int v4; // ebx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !a2 )
  {
    v4 = -2147024809;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x344,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\SettingHandlersBaseCore.h",
      (const char *)(unsigned int)v4,
      v6);
    return (unsigned int)v4;
  }
  v4 = Microsoft::WRL::EventSource<Windows::Foundation::Collections::VectorChangedEventHandler<SystemSettings::DataModel::ISettingItem *>,Microsoft::WRL::InvokeModeOptions<-2>>::AddInternal(
         a1 + 16,
         a2,
         *(_QWORD *)(*(_QWORD *)a2 + 24LL),
         a3);
  if ( v4 < 0 )
    goto LABEL_4;
  *a3 = EncodePointer(*a3);
  return 0;
}

```

## disassembly

```asm
0x180022490  mov     [rsp+arg_0], rbx
0x180022495  push    rdi; int
0x180022496  sub     rsp, 20h
0x18002249a  mov     rdi, r8
0x18002249d  test    rdx, rdx
0x1800224a0  jnz     short loc_1800224A9
0x1800224a2  mov     ebx, 80070057h
0x1800224a7  jmp     short loc_1800224C2
0x1800224a9  mov     r8, [rdx]
0x1800224ac  sub     rcx, 0FFFFFFFFFFFFFF80h
0x1800224b0  mov     r9, rdi
0x1800224b3  mov     r8, [r8+18h]
0x1800224b7  call    ?AddInternal@?$EventSource@U?$VectorChangedEventHandler@PEAUISettingItem@DataModel@SystemSettings@@@Collections@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@AEAAJPEAU?$VectorChangedEventHandler@PEAUISettingItem@DataModel@SystemSettings@@@Collections@Foundation@Windows@@PEAXPEAUEventRegistrationToken@@@Z; Microsoft::WRL::EventSource<Windows::Foundation::Collections::VectorChangedEventHandler<SystemSettings::DataModel::ISettingItem *>,Microsoft::WRL::InvokeModeOptions<-2>>::AddInternal(Windows::Foundation::Collections::VectorChangedEventHandler<SystemSettings::DataModel::ISettingItem *> *,void *,EventRegistrationToken *)
0x1800224bc  mov     ebx, eax
0x1800224be  test    eax, eax
0x1800224c0  jns     short loc_1800224DF
0x1800224c2  mov     rcx, [rsp+28h]; this
0x1800224c7  mov     r9d, ebx; char *
0x1800224ca  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x1800224d1  mov     edx, 344h; void *
0x1800224d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800224db  mov     eax, ebx
0x1800224dd  jmp     short loc_1800224F3
0x1800224df  mov     rcx, [rdi]; Ptr
0x1800224e2  call    cs:__imp_EncodePointer
0x1800224e8  mov     [rdi], rax
0x1800224eb  xor     eax, eax
0x1800224ed  jmp     short loc_1800224F3
0x1800224ef  mov     eax, [rsp+28h+arg_18]
0x1800224f3  mov     rbx, [rsp+28h+arg_0]
0x1800224f8  add     rsp, 20h
0x1800224fc  pop     rdi
0x1800224fd  retn
```
