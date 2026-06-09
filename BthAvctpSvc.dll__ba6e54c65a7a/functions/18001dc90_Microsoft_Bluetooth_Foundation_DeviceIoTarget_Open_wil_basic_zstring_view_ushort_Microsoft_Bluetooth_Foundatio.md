# Microsoft::Bluetooth::Foundation::DeviceIoTarget::Open(wil::basic_zstring_view<ushort>,Microsoft::Bluetooth::Foundation::DeviceIoTarget::Options const &,std::function<void (Microsoft::Bluetooth::Foundation::DevicePnpCustomNotification const &)>,std::function<void (Microsoft::Bluetooth::Foundation::DeviceIoTarget::State,void *)>)

- ea: `0x18001dc90`
- end: `0x18001de69`
- name: `?Open@DeviceIoTarget@Foundation@Bluetooth@Microsoft@@QEAAXV?$basic_zstring_view@G@wil@@AEBUOptions@1234@V?$function@$$A6AXAEBUDevicePnpCustomNotification@Foundation@Bluetooth@Microsoft@@@Z@std@@V?$function@$$A6AXW4State@DeviceIoTarget@Foundation@Bluetooth@Microsoft@@PEAX@Z@9@@Z`
- size: `473`
- prototype: `__int64 __usercall@<rax>(Microsoft::Bluetooth::Foundation::DeviceIoTarget *this@<rcx>, __int64)`
- caller_count: `3`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001d610`
- `0x1800255c4`
- `0x180043d98`

## callees

- `0x180004060`
- `0x18000e0c0`
- `0x18000e16c`
- `0x180012f50`
- `0x18001525c`
- `0x1800189a0`
- `0x180019c68`
- `0x18001d160`
- `0x18001dc90`
- `0x18001de70`
- `0x18001dfa8`
- `0x18001e034`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001ddd0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001ddd0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::Bluetooth::Foundation::DeviceIoTarget::Open(
        Microsoft::Bluetooth::Foundation::DeviceIoTarget *this,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        Microsoft::Bluetooth::Foundation::DeviceIoTarget *a5)
{
  char v8; // al
  Microsoft::Bluetooth::Foundation::DeviceIoTarget *v9; // r14
  Microsoft::Bluetooth::Foundation::DeviceIoTarget *v10; // rcx
  void *v11; // rdi
  __int64 v12; // rbx
  Microsoft::Bluetooth::Foundation::DevicePnpEventMonitor *v13; // rax
  int v15; // [rsp+28h] [rbp-81h]
  _QWORD v16[8]; // [rsp+58h] [rbp-51h] BYREF
  _BYTE v17[64]; // [rsp+98h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+100h] [rbp+57h]
  char *v19; // [rsp+108h] [rbp+5Fh] BYREF
  __int64 v20; // [rsp+120h] [rbp+77h]

  v20 = a4;
  v8 = *((_BYTE *)this + 16);
  *((_BYTE *)this + 16) = 1;
  if ( v8 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xBBB,
      (unsigned int)"onecore\\drivers\\bluetooth\\foundation\\lib\\DeviceIoTarget.h",
      (const char *)0x8007139FLL,
      v15);
  std::wstring::_Assign<unsigned short>((char *)this + 24);
  *(_OWORD *)((char *)this + 56) = *(_OWORD *)a3;
  *((_QWORD *)this + 9) = *(_QWORD *)(a3 + 16);
  v9 = a5;
  if ( (Microsoft::Bluetooth::Foundation::DeviceIoTarget *)((char *)this + 88) != a5 )
  {
    std::_Func_class<void,enum Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransportEnumerator::DeviceChangeEventType,unsigned short const *,std::shared_ptr<Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransport> const &>::_Tidy((char *)this + 88);
    v10 = (Microsoft::Bluetooth::Foundation::DeviceIoTarget *)*((_QWORD *)v9 + 7);
    if ( v10 )
    {
      if ( v10 == v9 )
      {
        *((_QWORD *)this + 18) = (*(__int64 (__fastcall **)(Microsoft::Bluetooth::Foundation::DeviceIoTarget *, char *))(*(_QWORD *)v10 + 8LL))(
                                   v10,
                                   (char *)this + 88);
        std::_Func_class<void,enum Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransportEnumerator::DeviceChangeEventType,unsigned short const *,std::shared_ptr<Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransport> const &>::_Tidy(v9);
      }
      else
      {
        *((_QWORD *)this + 18) = v10;
        *((_QWORD *)v9 + 7) = 0;
      }
    }
  }
  Microsoft::Bluetooth::Foundation::DeviceIoTarget::OpenFileHandleTemplateMethod(this);
  v11 = (void *)(*(__int64 (__fastcall **)(Microsoft::Bluetooth::Foundation::DeviceIoTarget *))(*(_QWORD *)this + 56LL))(this);
  v12 = std::function<void (Microsoft::Bluetooth::Foundation::DevicePnpCustomNotification const &)>::function<void (Microsoft::Bluetooth::Foundation::DevicePnpCustomNotification const &)>(v17);
  v16[0] = &std::_Func_impl_no_alloc<_lambda_610f622319d59bfe946240c435e7e4ec_,void,enum Microsoft::Bluetooth::Foundation::DevicePnpEventMonitor::Event>::`vftable';
  v16[1] = this;
  v16[7] = v16;
  (*(void (__fastcall **)(Microsoft::Bluetooth::Foundation::DeviceIoTarget *))(*(_QWORD *)this + 32LL))(this);
  std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 24);
  Microsoft::Bluetooth::Foundation::DevicePnpEventMonitor::Prepare(v11, v12);
  AcquireSRWLockExclusive((PSRWLOCK)this + 1);
  v19 = (char *)this + 8;
  *((_DWORD *)this + 38) = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v19);
  Microsoft::Bluetooth::Foundation::Details::LockedFileHandleGate::Open((Microsoft::Bluetooth::Foundation::DeviceIoTarget *)((char *)this + 232));
  if ( *((_QWORD *)this + 18) )
    Microsoft::Bluetooth::Foundation::DeviceIoTarget::InvokeStateChangeCallback(this, 0);
  v13 = (Microsoft::Bluetooth::Foundation::DevicePnpEventMonitor *)(*(__int64 (__fastcall **)(Microsoft::Bluetooth::Foundation::DeviceIoTarget *))(*(_QWORD *)this + 56LL))(this);
  Microsoft::Bluetooth::Foundation::DevicePnpEventMonitor::Start(v13);
  std::_Func_class<void,enum Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransportEnumerator::DeviceChangeEventType,unsigned short const *,std::shared_ptr<Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransport> const &>::_Tidy(a4);
  return std::_Func_class<void,enum Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransportEnumerator::DeviceChangeEventType,unsigned short const *,std::shared_ptr<Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransport> const &>::_Tidy(v9);
}

```

## disassembly

```asm
0x18001dc90  mov     rax, rsp
0x18001dc93  mov     [rax+10h], rbx
0x18001dc97  mov     [rax+18h], rsi
0x18001dc9b  mov     [rax+20h], r9
0x18001dc9f  push    rbp
0x18001dca0  push    rdi
0x18001dca1  push    r13
0x18001dca3  push    r14
0x18001dca5  push    r15
0x18001dca7  lea     rbp, [rax-57h]
0x18001dcab  sub     rsp, 0D0h
0x18001dcb2  mov     r15, r9
0x18001dcb5  mov     rbx, r8
0x18001dcb8  mov     rsi, rcx
0x18001dcbb  mov     eax, 1
0x18001dcc0  xchg    al, [rcx+10h]
0x18001dcc3  test    al, al
0x18001dcc5  setnz   al
0x18001dcc8  mov     rcx, [rbp+57h]; this
0x18001dccc  test    al, al
0x18001dcce  jnz     loc_18001DE51
0x18001dcd4  mov     [rbp+4Fh+var_B0], rsi
0x18001dcd8  mov     [rbp+4Fh+var_A8], 1
0x18001dcdc  mov     r8, [rdx+8]
0x18001dce0  mov     rdx, [rdx]
0x18001dce3  lea     rcx, [rsi+18h]
0x18001dce7  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18001dcec  movups  xmm0, xmmword ptr [rbx]
0x18001dcef  movups  xmmword ptr [rsi+38h], xmm0
0x18001dcf3  movsd   xmm1, qword ptr [rbx+10h]
0x18001dcf8  movsd   qword ptr [rsi+48h], xmm1
0x18001dcfd  lea     rbx, [rsi+58h]
0x18001dd01  mov     r14, [rbp+4Fh+arg_20]
0x18001dd05  cmp     rbx, r14
0x18001dd08  jz      short loc_18001DD49
0x18001dd0a  mov     rcx, rbx
0x18001dd0d  call    ?_Tidy@?$_Func_class@XW4DeviceChangeEventType@AvrcpTransportEnumerator@Avrcp@Profiles@Bluetooth@Microsoft@@PEBGAEBV?$shared_ptr@VAvrcpTransport@Avrcp@Profiles@Bluetooth@Microsoft@@@std@@@std@@IEAAXXZ; std::_Func_class<void,Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransportEnumerator::DeviceChangeEventType,ushort const *,std::shared_ptr<Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransport> const &>::_Tidy(void)
0x18001dd12  mov     rcx, [r14+38h]
0x18001dd16  test    rcx, rcx
0x18001dd19  jz      short loc_18001DD49
0x18001dd1b  cmp     rcx, r14
0x18001dd1e  jnz     short loc_18001DD3D
0x18001dd20  mov     rax, [rcx]
0x18001dd23  mov     rdx, rbx
0x18001dd26  mov     rax, [rax+8]
0x18001dd2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd2f  mov     [rbx+38h], rax
0x18001dd33  mov     rcx, r14
0x18001dd36  call    ?_Tidy@?$_Func_class@XW4DeviceChangeEventType@AvrcpTransportEnumerator@Avrcp@Profiles@Bluetooth@Microsoft@@PEBGAEBV?$shared_ptr@VAvrcpTransport@Avrcp@Profiles@Bluetooth@Microsoft@@@std@@@std@@IEAAXXZ; std::_Func_class<void,Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransportEnumerator::DeviceChangeEventType,ushort const *,std::shared_ptr<Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransport> const &>::_Tidy(void)
0x18001dd3b  jmp     short loc_18001DD49
0x18001dd3d  mov     [rbx+38h], rcx
0x18001dd41  mov     qword ptr [r14+38h], 0
0x18001dd49  mov     rcx, rsi; this
0x18001dd4c  call    ?OpenFileHandleTemplateMethod@DeviceIoTarget@Foundation@Bluetooth@Microsoft@@AEAAXXZ; Microsoft::Bluetooth::Foundation::DeviceIoTarget::OpenFileHandleTemplateMethod(void)
0x18001dd51  mov     rax, [rsi]
0x18001dd54  mov     rcx, rsi
0x18001dd57  mov     rax, [rax+38h]
0x18001dd5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd60  mov     rdi, rax
0x18001dd63  mov     rdx, r15
0x18001dd66  lea     rcx, [rbp+4Fh+var_60]
0x18001dd6a  call    ??0?$function@$$A6AXAEBUDevicePnpCustomNotification@Foundation@Bluetooth@Microsoft@@@Z@std@@QEAA@$$QEAV01@@Z; std::function<void (Microsoft::Bluetooth::Foundation::DevicePnpCustomNotification const &)>::function<void (Microsoft::Bluetooth::Foundation::DevicePnpCustomNotification const &)>(std::function<void (Microsoft::Bluetooth::Foundation::DevicePnpCustomNotification const &)> &&)
0x18001dd6f  mov     rbx, rax
0x18001dd72  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_610f622319d59bfe946240c435e7e4ec_@@XW4Event@DevicePnpEventMonitor@Foundation@Bluetooth@Microsoft@@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_610f622319d59bfe946240c435e7e4ec_,void,Microsoft::Bluetooth::Foundation::DevicePnpEventMonitor::Event>::`vftable'
0x18001dd79  mov     [rbp+4Fh+var_A0], rax
0x18001dd7d  mov     [rbp+4Fh+var_98], rsi
0x18001dd81  lea     rax, [rbp+4Fh+var_A0]
0x18001dd85  mov     [rbp+4Fh+var_68], rax
0x18001dd89  mov     rcx, [rsi]
0x18001dd8c  mov     rax, [rcx+20h]
0x18001dd90  mov     rcx, rsi
0x18001dd93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd98  mov     r8, rax
0x18001dd9b  lea     rcx, [rsi+18h]
0x18001dd9f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001dda4  mov     [rbp+4Fh+var_C0], rax
0x18001dda8  mov     rcx, [rsi+28h]
0x18001ddac  mov     [rbp+4Fh+var_B8], rcx
0x18001ddb0  mov     qword ptr [rsp+0F0h+var_D0], rbx; __int64
0x18001ddb5  lea     r9, [rbp+4Fh+var_A0]
0x18001ddb9  lea     rdx, [rbp+4Fh+var_C0]
0x18001ddbd  mov     rcx, rdi; pv
0x18001ddc0  call    ?Prepare@DevicePnpEventMonitor@Foundation@Bluetooth@Microsoft@@QEAAXV?$basic_zstring_view@G@wil@@PEAXV?$function@$$A6AXW4Event@DevicePnpEventMonitor@Foundation@Bluetooth@Microsoft@@@Z@std@@V?$function@$$A6AXAEBUDevicePnpCustomNotification@Foundation@Bluetooth@Microsoft@@@Z@8@W4MonitorInterfaceRemovals@1234@@Z; Microsoft::Bluetooth::Foundation::DevicePnpEventMonitor::Prepare(wil::basic_zstring_view<ushort>,void *,std::function<void (Microsoft::Bluetooth::Foundation::DevicePnpEventMonitor::Event)>,std::function<void (Microsoft::Bluetooth::Foundation::DevicePnpCustomNotification const &)>,Microsoft::Bluetooth::Foundation::DevicePnpEventMonitor::MonitorInterfaceRemovals)
0x18001ddc5  mov     [rbp+4Fh+var_A8], 0
0x18001ddc9  lea     rbx, [rsi+8]
0x18001ddcd  mov     rcx, rbx; SRWLock
0x18001ddd0  call    cs:__imp_AcquireSRWLockExclusive
0x18001ddd6  mov     [rbp+4Fh+arg_0], rbx
0x18001ddda  mov     dword ptr [rsi+98h], 1
0x18001dde4  lea     rcx, [rbp+4Fh+arg_0]
0x18001dde8  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001dded  lea     rcx, [rsi+0E8h]; this
0x18001ddf4  call    ?Open@LockedFileHandleGate@Details@Foundation@Bluetooth@Microsoft@@QEAAXXZ; Microsoft::Bluetooth::Foundation::Details::LockedFileHandleGate::Open(void)
0x18001ddf9  cmp     qword ptr [rsi+90h], 0
0x18001de01  jz      short loc_18001DE0D
0x18001de03  xor     edx, edx
0x18001de05  mov     rcx, rsi
0x18001de08  call    ?InvokeStateChangeCallback@DeviceIoTarget@Foundation@Bluetooth@Microsoft@@AEBAXW4State@1234@@Z; Microsoft::Bluetooth::Foundation::DeviceIoTarget::InvokeStateChangeCallback(Microsoft::Bluetooth::Foundation::DeviceIoTarget::State)
0x18001de0d  mov     rax, [rsi]
0x18001de10  mov     rcx, rsi
0x18001de13  mov     rax, [rax+38h]
0x18001de17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001de1c  mov     rcx, rax; this
0x18001de1f  call    ?Start@DevicePnpEventMonitor@Foundation@Bluetooth@Microsoft@@QEAAXXZ; Microsoft::Bluetooth::Foundation::DevicePnpEventMonitor::Start(void)
0x18001de24  nop
0x18001de25  mov     rcx, r15
0x18001de28  call    ?_Tidy@?$_Func_class@XW4DeviceChangeEventType@AvrcpTransportEnumerator@Avrcp@Profiles@Bluetooth@Microsoft@@PEBGAEBV?$shared_ptr@VAvrcpTransport@Avrcp@Profiles@Bluetooth@Microsoft@@@std@@@std@@IEAAXXZ; std::_Func_class<void,Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransportEnumerator::DeviceChangeEventType,ushort const *,std::shared_ptr<Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransport> const &>::_Tidy(void)
0x18001de2d  nop
0x18001de2e  mov     rcx, r14
0x18001de31  lea     r11, [rsp+0F0h+var_20]
0x18001de39  mov     rbx, [r11+38h]
0x18001de3d  mov     rsi, [r11+40h]
0x18001de41  mov     rsp, r11
0x18001de44  pop     r15
0x18001de46  pop     r14
0x18001de48  pop     r13
0x18001de4a  pop     rdi
0x18001de4b  pop     rbp
0x18001de4c  jmp     ?_Tidy@?$_Func_class@XW4DeviceChangeEventType@AvrcpTransportEnumerator@Avrcp@Profiles@Bluetooth@Microsoft@@PEBGAEBV?$shared_ptr@VAvrcpTransport@Avrcp@Profiles@Bluetooth@Microsoft@@@std@@@std@@IEAAXXZ; std::_Func_class<void,Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransportEnumerator::DeviceChangeEventType,ushort const *,std::shared_ptr<Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransport> const &>::_Tidy(void)
0x18001de51  mov     r9d, 8007139Fh; char *
0x18001de57  lea     r8, aOnecoreDrivers_19; "onecore\\drivers\\bluetooth\\foundation"...
0x18001de5e  mov     edx, 0BBBh; void *
0x18001de63  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
