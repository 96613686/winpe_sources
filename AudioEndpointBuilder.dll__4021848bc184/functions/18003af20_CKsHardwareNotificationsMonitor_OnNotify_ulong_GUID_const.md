# CKsHardwareNotificationsMonitor::OnNotify(ulong,_GUID const *)

- ea: `0x18003af20`
- end: `0x18003b072`
- name: `?OnNotify@CKsHardwareNotificationsMonitor@@UEAAJKPEBU_GUID@@@Z`
- size: `338`
- prototype: `int(CKsHardwareNotificationsMonitor *__hidden this, unsigned int, const struct _GUID *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180006b0c`
- `0x18000fb60`
- `0x180010da8`
- `0x180021030`
- `0x180029ad4`
- `0x180034c5c`
- `0x180037090`
- `0x18003af20`
- `0x18005eb60`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b047`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b05a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b047`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b05a`

## string_xrefs

- `0x18003b02c`: `avcore\audiocore\server\audioendpointbuilder\dll\hardwarecaps.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CKsHardwareNotificationsMonitor::OnNotify(
        CKsHardwareNotificationsMonitor *this,
        __int64 a2,
        const struct _GUID *a3)
{
  int (__fastcall ***v4)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v5; // rdi
  void (__fastcall *v6)(__int64, LPVOID *); // rbx
  int v7; // eax
  unsigned int v8; // ebx
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+8h]
  LPVOID pv; // [rsp+30h] [rbp+10h] BYREF
  __int64 v13; // [rsp+48h] [rbp+28h] BYREF

  if ( (unsigned int)(*((_DWORD *)this + 20) - 1) > 1 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_f06042b6212335e2df5fac66dd8d83e4_Traceguids);
    }
    return 0;
  }
  pv = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56664216>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56664216>::GetImpl'::`2'::impl) )
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &pv,
      0);
    CKsNotificationsMonitor::GetDeviceId(this, (unsigned __int16 **)&pv);
  }
  else
  {
    v13 = 0;
    v4 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 11);
    wil::com_ptr_t<IPnpDevnode,wil::err_returncode_policy>::reset(&v13);
    if ( (**v4)(v4, &GUID_9c2c4058_23f5_41de_877a_df3af236a09e, &v13) >= 0 )
    {
      v5 = v13;
      v6 = *(void (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v13 + 80LL);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &pv,
        0);
      v6(v5, &pv);
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v13);
  }
  v7 = VAD_EndpointBuilderAudioKSNotification((const unsigned __int16 *)pv);
  v8 = v7;
  if ( v7 >= 0 )
  {
    if ( pv )
      CoTaskMemFree(pv);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x79,
    (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\hardwarecaps.cpp",
    (const char *)(unsigned int)v7,
    savedregs);
  if ( pv )
    CoTaskMemFree(pv);
  return v8;
}

```

## disassembly

```asm
0x18003af20  mov     [rsp-8+arg_8], rbx
0x18003af25  mov     [rsp-8+arg_10], rdi
0x18003af2a  push    rbp; int
0x18003af2b  mov     rbp, rsp
0x18003af2e  sub     rsp, 20h
0x18003af32  mov     rbx, rcx
0x18003af35  mov     eax, [rcx+50h]
0x18003af38  dec     eax
0x18003af3a  cmp     eax, 1
0x18003af3d  jbe     short loc_18003AF84
0x18003af3f  lea     rax, WPP_GLOBAL_Control
0x18003af46  mov     rcx, cs:WPP_GLOBAL_Control
0x18003af4d  cmp     rcx, rax
0x18003af50  jz      loc_18003B060
0x18003af56  test    byte ptr [rcx+1Ch], 20h
0x18003af5a  jz      loc_18003B060
0x18003af60  cmp     byte ptr [rcx+19h], 4
0x18003af64  jb      loc_18003B060
0x18003af6a  mov     edx, 0Ah
0x18003af6f  lea     r8, WPP_f06042b6212335e2df5fac66dd8d83e4_Traceguids
0x18003af76  mov     rcx, [rcx+10h]
0x18003af7a  call    WPP_SF_
0x18003af7f  jmp     loc_18003B060
0x18003af84  mov     [rbp+pv], 0
0x18003af8c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56664216@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56664216@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56664216> `wil::Feature<__WilFeatureTraits_Feature_56664216>::GetImpl(void)'::`2'::impl
0x18003af93  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56664216@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56664216>::__private_IsEnabled(void)
0x18003af98  test    al, al
0x18003af9a  jz      short loc_18003AFB5
0x18003af9c  xor     edx, edx
0x18003af9e  lea     rcx, [rbp+pv]
0x18003afa2  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18003afa7  lea     rdx, [rbp+pv]; unsigned __int16 **
0x18003afab  mov     rcx, rbx; this
0x18003afae  call    ?GetDeviceId@CKsNotificationsMonitor@@QEAAJPEAPEAG@Z; CKsNotificationsMonitor::GetDeviceId(ushort * *)
0x18003afb3  jmp     short loc_18003B016
0x18003afb5  mov     [rbp+arg_18], 0
0x18003afbd  mov     rbx, [rbx+58h]
0x18003afc1  lea     rcx, [rbp+arg_18]
0x18003afc5  call    ?reset@?$com_ptr_t@UIPnpDevnode@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IPnpDevnode,wil::err_returncode_policy>::reset(void)
0x18003afca  mov     rax, [rbx]
0x18003afcd  lea     r8, [rbp+arg_18]
0x18003afd1  lea     rdx, _GUID_9c2c4058_23f5_41de_877a_df3af236a09e
0x18003afd8  mov     rcx, rbx
0x18003afdb  mov     rax, [rax]
0x18003afde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003afe3  test    eax, eax
0x18003afe5  js      short loc_18003B00D
0x18003afe7  mov     rdi, [rbp+arg_18]
0x18003afeb  mov     rax, [rdi]
0x18003afee  mov     rbx, [rax+50h]
0x18003aff2  xor     edx, edx
0x18003aff4  lea     rcx, [rbp+pv]
0x18003aff8  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18003affd  lea     rdx, [rbp+pv]
0x18003b001  mov     rcx, rdi
0x18003b004  mov     rax, rbx
0x18003b007  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b00c  nop
0x18003b00d  lea     rcx, [rbp+arg_18]
0x18003b011  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003b016  mov     rcx, [rbp+pv]; unsigned __int16 *
0x18003b01a  call    ?VAD_EndpointBuilderAudioKSNotification@@YAJPEBG@Z; VAD_EndpointBuilderAudioKSNotification(ushort const *)
0x18003b01f  mov     ebx, eax
0x18003b021  test    eax, eax
0x18003b023  jns     short loc_18003B051
0x18003b025  mov     rcx, [rbp+8]; this
0x18003b029  mov     r9d, eax; char *
0x18003b02c  lea     r8, aAvcoreAudiocor_11; "avcore\\audiocore\\server\\audioendpoin"...
0x18003b033  mov     edx, 79h ; 'y'; void *
0x18003b038  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b03d  nop
0x18003b03e  mov     rcx, [rbp+pv]; pv
0x18003b042  test    rcx, rcx
0x18003b045  jz      short loc_18003B04D
0x18003b047  call    cs:__imp_CoTaskMemFree
0x18003b04d  mov     eax, ebx
0x18003b04f  jmp     short loc_18003B062
0x18003b051  mov     rcx, [rbp+pv]; pv
0x18003b055  test    rcx, rcx
0x18003b058  jz      short loc_18003B060
0x18003b05a  call    cs:__imp_CoTaskMemFree
0x18003b060  xor     eax, eax
0x18003b062  mov     rbx, [rsp+20h+arg_8]
0x18003b067  mov     rdi, [rsp+20h+arg_10]
0x18003b06c  add     rsp, 20h
0x18003b070  pop     rbp
0x18003b071  retn
```
