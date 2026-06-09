# Microsoft::Bluetooth::Foundation::ComServiceModule::InitializeInternal(void)

- ea: `0x18000cc28`
- end: `0x18000ccd9`
- name: `?InitializeInternal@ComServiceModule@Foundation@Bluetooth@Microsoft@@AEAAXXZ`
- size: `177`
- prototype: `void __fastcall(Microsoft::Bluetooth::Foundation::ComServiceModule *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d1c8`

## callees

- `0x1800021dc`
- `0x18000aa78`
- `0x18000b69c`
- `0x18000cc28`
- `0x18000de78`
- `0x18000dfec`

## import_xrefs

- `combase!__imp_CoGetSharedServiceId` at `0x18000cc3e`
- `combase!__imp_CoGetSharedServiceId` at `0x18000cc3e`

## string_xrefs

- `0x18000cc55`: `onecore\drivers\bluetooth\foundation\lib\ComServiceModule.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Microsoft::Bluetooth::Foundation::ComServiceModule::InitializeInternal(
        Microsoft::Bluetooth::Foundation::ComServiceModule *this)
{
  int SharedServiceId; // eax
  char v3; // al
  char *v4; // [rsp+20h] [rbp-18h] BYREF
  std::_Ref_count_base *v5; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  _DWORD *v7; // [rsp+40h] [rbp+8h]

  SharedServiceId = CoGetSharedServiceId((char *)this + 16);
  if ( SharedServiceId >= 0 )
  {
    v3 = 1;
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x5D,
      (unsigned int)"onecore\\drivers\\bluetooth\\foundation\\lib\\ComServiceModule.h",
      (const char *)(unsigned int)SharedServiceId,
      (int)v4);
    v3 = 0;
  }
  *((_BYTE *)this + 20) = v3;
  v7 = operator new(0x20u);
  *(_OWORD *)v7 = 0;
  v7[2] = 1;
  v7[3] = 1;
  *(_QWORD *)v7 = &std::_Ref_count_obj2<Microsoft::Bluetooth::Foundation::Details::ComDisconnectableContextImpl>::`vftable';
  std::_Construct_in_place<Microsoft::Bluetooth::Foundation::Details::ComDisconnectableContextImpl,>((_QWORD *)v7 + 2);
  v4 = (char *)(v7 + 4);
  v5 = (std::_Ref_count_base *)v7;
  std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncDeviceInterfaceWatcher>::operator=((char *)this + 24, &v4);
  if ( v5 )
    std::_Ref_count_base::_Decref(v5);
}

```

## disassembly

```asm
0x18000cc28  mov     [rsp+arg_8], rbx
0x18000cc2d  mov     [rsp+arg_10], rsi
0x18000cc32  push    rdi
0x18000cc33  sub     rsp, 30h
0x18000cc37  mov     rsi, rcx
0x18000cc3a  add     rcx, 10h
0x18000cc3e  call    cs:__imp_CoGetSharedServiceId
0x18000cc44  mov     rcx, [rsp+38h]; this
0x18000cc49  mov     ebx, 1
0x18000cc4e  test    eax, eax
0x18000cc50  jns     short loc_18000CC68
0x18000cc52  mov     r9d, eax; char *
0x18000cc55  lea     r8, aOnecoreDrivers_6; "onecore\\drivers\\bluetooth\\foundation"...
0x18000cc5c  lea     edx, [rbx+5Ch]; void *
0x18000cc5f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000cc64  xor     al, al
0x18000cc66  jmp     short loc_18000CC6A
0x18000cc68  mov     al, bl
0x18000cc6a  mov     [rsi+14h], al
0x18000cc6d  mov     ecx, 20h ; ' '; Size
0x18000cc72  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000cc77  mov     rdi, rax
0x18000cc7a  mov     [rsp+38h+arg_0], rax
0x18000cc7f  xorps   xmm0, xmm0
0x18000cc82  movups  xmmword ptr [rax], xmm0
0x18000cc85  mov     [rax+8], ebx
0x18000cc88  mov     [rax+0Ch], ebx
0x18000cc8b  lea     rax, ??_7?$_Ref_count_obj2@VComDisconnectableContextImpl@Details@Foundation@Bluetooth@Microsoft@@@std@@6B@; const std::_Ref_count_obj2<Microsoft::Bluetooth::Foundation::Details::ComDisconnectableContextImpl>::`vftable'
0x18000cc92  mov     [rdi], rax
0x18000cc95  lea     rbx, [rdi+10h]
0x18000cc99  mov     rcx, rbx
0x18000cc9c  call    ??$_Construct_in_place@VComDisconnectableContextImpl@Details@Foundation@Bluetooth@Microsoft@@$$V@std@@YAXAEAVComDisconnectableContextImpl@Details@Foundation@Bluetooth@Microsoft@@@Z; std::_Construct_in_place<Microsoft::Bluetooth::Foundation::Details::ComDisconnectableContextImpl,>(Microsoft::Bluetooth::Foundation::Details::ComDisconnectableContextImpl &)
0x18000cca1  nop
0x18000cca2  mov     [rsp+38h+var_18], rbx
0x18000cca7  mov     [rsp+38h+var_10], rdi
0x18000ccac  lea     rcx, [rsi+18h]
0x18000ccb0  lea     rdx, [rsp+38h+var_18]
0x18000ccb5  call    ??4?$shared_ptr@VAsyncDeviceInterfaceWatcher@Foundation@Bluetooth@Microsoft@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncDeviceInterfaceWatcher>::operator=(std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncDeviceInterfaceWatcher> &&)
0x18000ccba  mov     rcx, [rsp+38h+var_10]; this
0x18000ccbf  test    rcx, rcx
0x18000ccc2  jz      short loc_18000CCC9
0x18000ccc4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000ccc9  mov     rbx, [rsp+38h+arg_8]
0x18000ccce  mov     rsi, [rsp+38h+arg_10]
0x18000ccd3  add     rsp, 30h
0x18000ccd7  pop     rdi
0x18000ccd8  retn
```
