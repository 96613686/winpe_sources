# Microsoft::Bluetooth::Protocols::Avctp::AvctpChannelProvider::OnConnectionStateChanged(Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransport::ChannelType,Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransport const &)

- ea: `0x180029200`
- end: `0x18002936e`
- name: `?OnConnectionStateChanged@AvctpChannelProvider@Avctp@Protocols@Bluetooth@Microsoft@@UEAAXW4ChannelType@AvrcpTransport@Avrcp@Profiles@45@AEBV78945@@Z`
- size: `366`
- prototype: `void __fastcall(Microsoft::Bluetooth::Protocols::Avctp::AvctpChannelProvider *__hidden this, enum ChannelType, const struct Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransport *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800021dc`
- `0x180004060`
- `0x18000e0c0`
- `0x18000f3a0`
- `0x1800291c4`
- `0x180029200`
- `0x1800302ac`
- `0x18004c124`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180029237`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180029237`

## string_xrefs

- `0x1800292b0`: `onecore\drivers\bluetooth\profiles\avrcp\avctp\service\lib\avctpchannel.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Microsoft::Bluetooth::Protocols::Avctp::AvctpChannelProvider::OnConnectionStateChanged(
        RTL_SRWLOCK *this,
        unsigned int a2,
        const struct Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransport *a3)
{
  __int64 v6; // r14
  AVCTPChannelPtr *v7; // r14
  char v8; // bp
  bool v9; // r15
  char v10; // al
  struct SynchronizedObject *v11; // rcx
  _QWORD *v12; // rax
  __int64 v13; // r9
  __int64 v14; // rdx
  struct AVCTPChannel *v15; // rax
  PVOID Ptr; // rdi
  void (__fastcall *v17)(PVOID, __int64); // rbx
  __int64 v18; // rdx
  int v19; // [rsp+20h] [rbp-58h]
  _QWORD v20[9]; // [rsp+30h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  RTL_SRWLOCK *v22; // [rsp+80h] [rbp+8h] BYREF
  void *v23; // [rsp+90h] [rbp+18h]
  _QWORD *v24; // [rsp+98h] [rbp+20h]

  v6 = 8;
  if ( a2 != 1 )
    v6 = 9;
  v7 = (AVCTPChannelPtr *)&this[v6];
  v8 = 0;
  v9 = 0;
  AcquireSRWLockExclusive(this + 7);
  v22 = this + 7;
  v10 = (*(__int64 (__fastcall **)(const struct Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransport *, _QWORD))(*(_QWORD *)a3 + 56LL))(
          a3,
          a2);
  v11 = *(struct SynchronizedObject **)v7;
  if ( v10 )
  {
    if ( !v11 )
    {
      v23 = operator new(0xF8u);
      v24 = v20;
      v12 = std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl>::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl>(
              v20,
              &this[3].Ptr);
      if ( a2 )
      {
        if ( a2 != 1 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x51,
            (unsigned int)"onecore\\drivers\\bluetooth\\profiles\\avrcp\\avctp\\service\\lib\\avctpchannel.cpp",
            (const char *)0x8000FFFFLL,
            v19);
        v14 = 1;
      }
      else
      {
        v14 = 0;
      }
      v15 = (struct AVCTPChannel *)AVCTPChannel::AVCTPChannel(v13, v14, v12);
      AVCTPChannelPtr::InnerRelease(v7, v15);
      v8 = 1;
    }
  }
  else if ( v11 )
  {
    Synchronizer::EnqueueEvent(*((Synchronizer **)v11 + 1), *(struct SynchronizedObject **)v7, 1u, 0);
    AVCTPChannelPtr::InnerRelease(v7, 0);
    v9 = a2 == 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v22);
  if ( v8 )
  {
    (*(void (__fastcall **)(PVOID, _QWORD))(*(_QWORD *)this[5].Ptr + 8LL))(this[5].Ptr, *(_QWORD *)v7);
  }
  else if ( v9 )
  {
    Ptr = this[5].Ptr;
    v17 = *(void (__fastcall **)(PVOID, __int64))(*(_QWORD *)Ptr + 16LL);
    v18 = (*(__int64 (__fastcall **)(const struct Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransport *))(*(_QWORD *)a3 + 72LL))(a3);
    v17(Ptr, v18);
  }
}

```

## disassembly

```asm
0x180029200  push    rbx
0x180029202  push    rbp
0x180029203  push    rsi
0x180029204  push    rdi
0x180029205  push    r12
0x180029207  push    r14
0x180029209  push    r15
0x18002920b  sub     rsp, 40h
0x18002920f  mov     r12, r8
0x180029212  mov     edi, edx
0x180029214  mov     rsi, rcx
0x180029217  mov     ecx, 48h ; 'H'
0x18002921c  lea     r14d, [rcx-8]
0x180029220  cmp     edx, 1
0x180029223  cmovnz  r14d, ecx
0x180029227  add     r14, rsi
0x18002922a  xor     bpl, bpl
0x18002922d  xor     r15b, r15b
0x180029230  lea     rbx, [rsi+38h]
0x180029234  mov     rcx, rbx; SRWLock
0x180029237  call    cs:__imp_AcquireSRWLockExclusive
0x18002923d  mov     [rsp+78h+arg_0], rbx
0x180029245  mov     rax, [r12]
0x180029249  mov     edx, edi
0x18002924b  mov     rcx, r12
0x18002924e  mov     rax, [rax+38h]
0x180029252  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029257  mov     rcx, [r14]
0x18002925a  test    al, al
0x18002925c  jz      loc_1800292E7
0x180029262  test    rcx, rcx
0x180029265  jnz     loc_18002930F
0x18002926b  mov     ecx, 0F8h; Size
0x180029270  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180029275  mov     r9, rax
0x180029278  mov     [rsp+78h+arg_10], rax
0x180029280  lea     rax, [rsp+78h+var_48]
0x180029285  mov     [rsp+78h+arg_18], rax
0x18002928d  lea     rdx, [rsi+18h]
0x180029291  lea     rcx, [rsp+78h+var_48]
0x180029296  call    ??0?$shared_ptr@VThreadProcessorControlImpl@Details@Foundation@Bluetooth@Microsoft@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl>::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl>(std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl> const &)
0x18002929b  nop
0x18002929c  test    edi, edi
0x18002929e  jz      short loc_1800292C9
0x1800292a0  cmp     edi, 1
0x1800292a3  jz      short loc_1800292C2
0x1800292a5  mov     rcx, [rsp+78h]; this
0x1800292aa  mov     r9d, 8000FFFFh; char *
0x1800292b0  lea     r8, aOnecoreDrivers_40; "onecore\\drivers\\bluetooth\\profiles\\"...
0x1800292b7  mov     edx, 51h ; 'Q'; void *
0x1800292bc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800292c2  mov     edx, 1
0x1800292c7  jmp     short loc_1800292CB
0x1800292c9  xor     edx, edx
0x1800292cb  mov     r8, rax
0x1800292ce  mov     rcx, r9
0x1800292d1  call    ??0AVCTPChannel@@QEAA@W4AVCTP_CHANNEL_TYPE@@V?$shared_ptr@VAvrcpTransport@Avrcp@Profiles@Bluetooth@Microsoft@@@std@@@Z; AVCTPChannel::AVCTPChannel(AVCTP_CHANNEL_TYPE,std::shared_ptr<Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransport>)
0x1800292d6  nop
0x1800292d7  mov     rdx, rax; struct AVCTPChannel *
0x1800292da  mov     rcx, r14; this
0x1800292dd  call    ?InnerRelease@AVCTPChannelPtr@@AEAAXPEAVAVCTPChannel@@@Z; AVCTPChannelPtr::InnerRelease(AVCTPChannel *)
0x1800292e2  mov     bpl, 1
0x1800292e5  jmp     short loc_18002930F
0x1800292e7  test    rcx, rcx
0x1800292ea  jz      short loc_18002930F
0x1800292ec  xor     r9d, r9d; void *
0x1800292ef  lea     r8d, [r9+1]; int
0x1800292f3  mov     rdx, rcx; struct SynchronizedObject *
0x1800292f6  mov     rcx, [rcx+8]; this
0x1800292fa  call    ?EnqueueEvent@Synchronizer@@AEAAXPEAVSynchronizedObject@@HPEAX11@Z; Synchronizer::EnqueueEvent(SynchronizedObject *,int,void *,void *,void *)
0x1800292ff  xor     edx, edx; struct AVCTPChannel *
0x180029301  mov     rcx, r14; this
0x180029304  call    ?InnerRelease@AVCTPChannelPtr@@AEAAXPEAVAVCTPChannel@@@Z; AVCTPChannelPtr::InnerRelease(AVCTPChannel *)
0x180029309  test    edi, edi
0x18002930b  setz    r15b
0x18002930f  lea     rcx, [rsp+78h+arg_0]
0x180029317  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002931c  test    bpl, bpl
0x18002931f  jz      short loc_180029331
0x180029321  mov     rcx, [rsi+28h]
0x180029325  mov     rax, [rcx]
0x180029328  mov     rdx, [r14]
0x18002932b  mov     rax, [rax+8]
0x18002932f  jmp     short loc_18002935A
0x180029331  test    r15b, r15b
0x180029334  jz      short loc_18002935F
0x180029336  mov     rdi, [rsi+28h]
0x18002933a  mov     rax, [rdi]
0x18002933d  mov     rbx, [rax+10h]
0x180029341  mov     rdx, [r12]
0x180029345  mov     rcx, r12
0x180029348  mov     rax, [rdx+48h]
0x18002934c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029351  mov     rdx, rax
0x180029354  mov     rcx, rdi
0x180029357  mov     rax, rbx
0x18002935a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002935f  add     rsp, 40h
0x180029363  pop     r15
0x180029365  pop     r14
0x180029367  pop     r12
0x180029369  pop     rdi
0x18002936a  pop     rsi
0x18002936b  pop     rbp
0x18002936c  pop     rbx
0x18002936d  retn
```
