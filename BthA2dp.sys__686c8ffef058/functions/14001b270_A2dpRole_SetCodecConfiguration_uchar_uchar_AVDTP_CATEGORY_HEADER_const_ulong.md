# A2dpRole::SetCodecConfiguration(uchar,uchar,_AVDTP_CATEGORY_HEADER const *,ulong)

- ea: `0x14001b270`
- end: `0x14001b4e4`
- name: `?SetCodecConfiguration@A2dpRole@@QEAAEEEPEBU_AVDTP_CATEGORY_HEADER@@K@Z`
- size: `628`
- prototype: `char __fastcall(A2dpRole *this, char, __int64, const struct _AVDTP_CATEGORY_HEADER *, unsigned int)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update`

## callers

- `0x140020c00`

## callees

- `0x140005030`
- `0x140006410`
- `0x14000f950`
- `0x140010628`
- `0x14001b270`
- `0x14001b614`
- `0x14001b6bc`
- `0x14001bbc4`
- `0x14001bd50`
- `0x14001bdd8`
- `0x14002b928`
- `0x14002d0a0`
- `0x14002da9c`
- `0x14005c870`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14001b4a9`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001b4a9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001b32b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001b32b`

## pseudocode

```c
char __fastcall A2dpRole::SetCodecConfiguration(
        A2dpRole *this,
        char a2,
        __int64 a3,
        const struct _AVDTP_CATEGORY_HEADER *a4,
        unsigned int a5)
{
  char v6; // si
  char v9; // bl
  bool v10; // dl
  bool v11; // r13
  int v12; // edx
  int v13; // r8d
  char v14; // bl
  __int64 v15; // rsi
  __int64 InbandCodecWithId; // rax
  KSPIN_LOCK *SpinLock; // [rsp+70h] [rbp-21h]
  _BYTE v19[16]; // [rsp+78h] [rbp-19h] BYREF
  __int64 v20; // [rsp+88h] [rbp-9h] BYREF
  utl::_RefCountBase *v21; // [rsp+90h] [rbp-1h]
  _BYTE v22[8]; // [rsp+98h] [rbp+7h] BYREF
  utl::_RefCountBase *v23; // [rsp+A0h] [rbp+Fh]
  KIRQL NewIrql; // [rsp+F0h] [rbp+5Fh]
  char v25; // [rsp+100h] [rbp+6Fh]

  v25 = a3;
  v6 = a3;
  v9 = 1;
  v10 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
     && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
     && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( v10 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_ddqdq(WPP_GLOBAL_Control->AttachedDevice, v10, a3, WPP_GLOBAL_Control->DeviceExtension);
  }
  LOBYTE(a3) = a2;
  v11 = 0;
  A2dpRole::GetCodecIdFromLocalSeid(this, v19, a3);
  SpinLock = (KSPIN_LOCK *)*((_QWORD *)this + 21);
  NewIrql = KeAcquireSpinLockRaiseToDpc(SpinLock);
  if ( CodecId::IsKnownCodec((CodecId *)v19) )
  {
    v14 = 18;
    A2dpAudioCodecManager::GetSidebandCodecWithId(*(_QWORD *)this, &v20, v19);
    v15 = v20;
    if ( v20 )
    {
      v14 = (*(__int64 (__fastcall **)(__int64, const struct _AVDTP_CATEGORY_HEADER *, _QWORD))(*(_QWORD *)v20 + 8LL))(
              v20,
              a4,
              a5);
      if ( !v14 )
        goto LABEL_17;
    }
    InbandCodecWithId = A2dpAudioCodecManager::GetInbandCodecWithId(*(_QWORD *)this, v22, v19);
    utl::shared_ptr<A2dpAudioCodec>::operator=(&v20, InbandCodecWithId);
    if ( v23 )
      utl::_RefCountBase::_DecStrong(v23);
    v15 = v20;
    if ( v20 )
      v14 = (*(__int64 (__fastcall **)(__int64, const struct _AVDTP_CATEGORY_HEADER *, _QWORD))(*(_QWORD *)v20 + 8LL))(
              v20,
              a4,
              a5);
    if ( !v14 )
    {
LABEL_17:
      wil::acquire_kspin_lock(v22, (char *)this + 96);
      utl::shared_ptr<A2dpAudioCodec>::operator=((char *)this + 112, &v20);
      *((_BYTE *)this + 104) = v25;
      *((_BYTE *)this + 105) = a2;
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&public: static void wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&public: static void wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>(v22);
      if ( !*((_QWORD *)this + 25) )
        v11 = (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15) == 0;
    }
    if ( v21 )
      utl::_RefCountBase::_DecStrong(v21);
  }
  else
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    {
      v9 = 0;
    }
    if ( v9 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v12) = v9;
      LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_dq(
        WPP_GLOBAL_Control->AttachedDevice,
        v12,
        v13,
        WPP_GLOBAL_Control->DeviceExtension,
        4,
        5,
        38,
        (__int64)WPP_7c0da6a8da193713e093ba9e03de3d02_Traceguids,
        v6,
        (char)this);
    }
    v14 = 18;
  }
  KeReleaseSpinLock(SpinLock, NewIrql);
  if ( !v14 && v11 )
    A2dpRole::UpdateDataRange(this);
  return v14;
}

```

## disassembly

```asm
0x14001b270  mov     [rsp-8+arg_8], rbx
0x14001b275  mov     [rsp-8+arg_10], r8b
0x14001b27a  push    rbp
0x14001b27b  push    rsi
0x14001b27c  push    rdi
0x14001b27d  push    r12
0x14001b27f  push    r13
0x14001b281  push    r14
0x14001b283  push    r15
0x14001b285  lea     rbp, [rsp-1Fh]
0x14001b28a  sub     rsp, 0B0h
0x14001b291  mov     r12, r9
0x14001b294  movzx   esi, r8b
0x14001b298  movzx   r15d, dl
0x14001b29c  mov     rdi, rcx
0x14001b29f  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b2a6  lea     rax, WPP_GLOBAL_Control
0x14001b2ad  mov     bl, 1
0x14001b2af  cmp     rcx, rax
0x14001b2b2  jz      short loc_14001B2C5
0x14001b2b4  mov     eax, [rcx+2Ch]
0x14001b2b7  test    al, 10h
0x14001b2b9  jz      short loc_14001B2C5
0x14001b2bb  cmp     byte ptr [rcx+29h], 4
0x14001b2bf  jb      short loc_14001B2C5
0x14001b2c1  mov     dl, bl
0x14001b2c3  jmp     short loc_14001B2C7
0x14001b2c5  xor     dl, dl
0x14001b2c7  mov     r14d, [rbp+4Fh+arg_20]
0x14001b2cb  lea     rax, WPP_RECORDER_INITIALIZED
0x14001b2d2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001b2d9  setnz   r8b
0x14001b2dd  test    dl, dl
0x14001b2df  jnz     short loc_14001B2E6
0x14001b2e1  test    r8b, r8b
0x14001b2e4  jz      short loc_14001B30B
0x14001b2e6  mov     r9, [rcx+40h]
0x14001b2ea  mov     rcx, [rcx+18h]
0x14001b2ee  mov     [rsp+0E0h+var_80], rdi
0x14001b2f3  mov     [rsp+0E0h+var_88], r14d
0x14001b2f8  mov     [rsp+0E0h+var_90], r12
0x14001b2fd  mov     dword ptr [rsp+0E0h+var_98], esi
0x14001b301  mov     [rsp+0E0h+var_A0], r15d
0x14001b306  call    WPP_RECORDER_AND_TRACE_SF_ddqdq
0x14001b30b  mov     r8b, r15b
0x14001b30e  lea     rdx, [rbp+4Fh+var_68]
0x14001b312  mov     rcx, rdi
0x14001b315  xor     r13b, r13b
0x14001b318  call    ?GetCodecIdFromLocalSeid@A2dpRole@@QEBA?AVCodecId@@E@Z; A2dpRole::GetCodecIdFromLocalSeid(uchar)
0x14001b31d  mov     rax, [rdi+0A8h]
0x14001b324  mov     rcx, rax; SpinLock
0x14001b327  mov     [rbp+4Fh+SpinLock], rax
0x14001b32b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001b332  nop     dword ptr [rax+rax+00h]
0x14001b337  lea     rcx, [rbp+4Fh+var_68]; this
0x14001b33b  mov     [rbp+4Fh+NewIrql], al
0x14001b33e  call    ?IsKnownCodec@CodecId@@QEBA_NXZ; CodecId::IsKnownCodec(void)
0x14001b343  test    al, al
0x14001b345  jz      loc_14001B42B
0x14001b34b  mov     rcx, [rdi]
0x14001b34e  lea     r8, [rbp+4Fh+var_68]
0x14001b352  lea     rdx, [rbp+4Fh+var_58]
0x14001b356  mov     bl, 12h
0x14001b358  call    ?GetSidebandCodecWithId@A2dpAudioCodecManager@@QEAA?AV?$shared_ptr@VA2dpAudioCodec@@@utl@@AEBVCodecId@@@Z; A2dpAudioCodecManager::GetSidebandCodecWithId(CodecId const &)
0x14001b35d  mov     rsi, [rbp+4Fh+var_58]
0x14001b361  test    rsi, rsi
0x14001b364  jz      short loc_14001B381
0x14001b366  mov     rax, [rsi]
0x14001b369  mov     r8d, r14d
0x14001b36c  mov     rdx, r12
0x14001b36f  mov     rcx, rsi
0x14001b372  mov     rax, [rax+8]
0x14001b376  call    _guard_dispatch_icall
0x14001b37b  mov     bl, al
0x14001b37d  test    al, al
0x14001b37f  jz      short loc_14001B3CF
0x14001b381  mov     rcx, [rdi]
0x14001b384  lea     r8, [rbp+4Fh+var_68]
0x14001b388  lea     rdx, [rbp+4Fh+var_48]
0x14001b38c  call    ?GetInbandCodecWithId@A2dpAudioCodecManager@@QEAA?AV?$shared_ptr@VA2dpAudioCodec@@@utl@@AEBVCodecId@@@Z; A2dpAudioCodecManager::GetInbandCodecWithId(CodecId const &)
0x14001b391  mov     rdx, rax
0x14001b394  lea     rcx, [rbp+4Fh+var_58]
0x14001b398  call    ??4?$shared_ptr@VA2dpAudioCodec@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::shared_ptr<A2dpAudioCodec>::operator=(utl::shared_ptr<A2dpAudioCodec> &&)
0x14001b39d  mov     rcx, [rbp+4Fh+var_40]; this
0x14001b3a1  test    rcx, rcx
0x14001b3a4  jz      short loc_14001B3AB
0x14001b3a6  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14001b3ab  mov     rsi, [rbp+4Fh+var_58]
0x14001b3af  test    rsi, rsi
0x14001b3b2  jz      short loc_14001B3CB
0x14001b3b4  mov     rax, [rsi]
0x14001b3b7  mov     r8d, r14d
0x14001b3ba  mov     rdx, r12
0x14001b3bd  mov     rcx, rsi
0x14001b3c0  mov     rax, [rax+8]
0x14001b3c4  call    _guard_dispatch_icall
0x14001b3c9  mov     bl, al
0x14001b3cb  test    bl, bl
0x14001b3cd  jnz     short loc_14001B41B
0x14001b3cf  lea     rdx, [rdi+60h]
0x14001b3d3  lea     rcx, [rbp+4Fh+var_48]
0x14001b3d7  call    ?acquire_kspin_lock@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUkspin_lock_saved_irql@details@wil@@@Z$1?Release@123@SAX0@ZU?$integral_constant@_K$01@wistd@@U123@PEA_K$0A@$$T@details@wil@@@details@wil@@@1@PEA_K@Z; wil::acquire_kspin_lock(unsigned __int64 *)
0x14001b3dc  lea     rcx, [rdi+70h]
0x14001b3e0  lea     rdx, [rbp+4Fh+var_58]
0x14001b3e4  call    ??4?$shared_ptr@VA2dpAudioCodec@@@utl@@QEAAAEAV01@AEBV01@@Z; utl::shared_ptr<A2dpAudioCodec>::operator=(utl::shared_ptr<A2dpAudioCodec> const &)
0x14001b3e9  mov     al, [rbp+4Fh+arg_10]
0x14001b3ec  lea     rcx, [rbp+4Fh+var_48]
0x14001b3f0  mov     [rdi+68h], al
0x14001b3f3  mov     [rdi+69h], r15b
0x14001b3f7  call    ??1?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUkspin_lock_saved_irql@details@wil@@@Z$1?Release@123@SAX0@ZU?$integral_constant@_K$01@wistd@@U123@PEA_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>(void)
0x14001b3fc  cmp     qword ptr [rdi+0C8h], 0
0x14001b404  jnz     short loc_14001B41B
0x14001b406  mov     rax, [rsi]
0x14001b409  mov     rcx, rsi
0x14001b40c  mov     rax, [rax+10h]
0x14001b410  call    _guard_dispatch_icall
0x14001b415  test    eax, eax
0x14001b417  setz    r13b
0x14001b41b  mov     rcx, [rbp+4Fh+var_50]; this
0x14001b41f  test    rcx, rcx
0x14001b422  jz      short loc_14001B4A2
0x14001b424  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14001b429  jmp     short loc_14001B4A2
0x14001b42b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b432  lea     rax, WPP_GLOBAL_Control
0x14001b439  cmp     rcx, rax
0x14001b43c  jz      short loc_14001B44B
0x14001b43e  mov     eax, [rcx+2Ch]
0x14001b441  test    al, 10h
0x14001b443  jz      short loc_14001B44B
0x14001b445  cmp     byte ptr [rcx+29h], 4
0x14001b449  jnb     short loc_14001B44D
0x14001b44b  xor     bl, bl
0x14001b44d  lea     rax, WPP_RECORDER_INITIALIZED
0x14001b454  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001b45b  setnz   r8b
0x14001b45f  test    bl, bl
0x14001b461  jnz     short loc_14001B468
0x14001b463  test    r8b, r8b
0x14001b466  jz      short loc_14001B4A0
0x14001b468  mov     r9, [rcx+40h]
0x14001b46c  lea     rax, WPP_7c0da6a8da193713e093ba9e03de3d02_Traceguids
0x14001b473  mov     rcx, [rcx+18h]
0x14001b477  mov     dl, bl
0x14001b479  mov     [rsp+0E0h+var_98], rdi
0x14001b47e  mov     [rsp+0E0h+var_A0], esi
0x14001b482  mov     [rsp+0E0h+var_A8], rax
0x14001b487  mov     [rsp+0E0h+var_B0], 26h ; '&'
0x14001b48e  mov     [rsp+0E0h+var_B8], 5
0x14001b496  mov     [rsp+0E0h+var_C0], 4
0x14001b49b  call    WPP_RECORDER_AND_TRACE_SF_dq
0x14001b4a0  mov     bl, 12h
0x14001b4a2  mov     dl, [rbp+4Fh+NewIrql]; NewIrql
0x14001b4a5  mov     rcx, [rbp+4Fh+SpinLock]; SpinLock
0x14001b4a9  call    cs:__imp_KeReleaseSpinLock
0x14001b4b0  nop     dword ptr [rax+rax+00h]
0x14001b4b5  test    bl, bl
0x14001b4b7  jnz     short loc_14001B4C6
0x14001b4b9  test    r13b, r13b
0x14001b4bc  jz      short loc_14001B4C6
0x14001b4be  mov     rcx, rdi; Context
0x14001b4c1  call    ?UpdateDataRange@A2dpRole@@QEAAXXZ; A2dpRole::UpdateDataRange(void)
0x14001b4c6  mov     al, bl
0x14001b4c8  mov     rbx, [rsp+0E0h+arg_8]
0x14001b4d0  add     rsp, 0B0h
0x14001b4d7  pop     r15
0x14001b4d9  pop     r14
0x14001b4db  pop     r13
0x14001b4dd  pop     r12
0x14001b4df  pop     rdi
0x14001b4e0  pop     rsi
0x14001b4e1  pop     rbp
0x14001b4e2  retn
```
