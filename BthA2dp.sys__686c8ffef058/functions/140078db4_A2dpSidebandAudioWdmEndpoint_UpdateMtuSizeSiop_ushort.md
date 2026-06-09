# A2dpSidebandAudioWdmEndpoint::UpdateMtuSizeSiop(ushort)

- ea: `0x140078db4`
- end: `0x140078faf`
- name: `?UpdateMtuSizeSiop@A2dpSidebandAudioWdmEndpoint@@QEAAXG@Z`
- size: `507`
- prototype: `void __fastcall(A2dpSidebandAudioWdmEndpoint *__hidden this, unsigned __int16)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400786f0`

## callees

- `0x140003530`
- `0x140006410`
- `0x140010628`
- `0x14001f93c`
- `0x1400202e8`
- `0x140058410`
- `0x14005c7d0`
- `0x14005c870`
- `0x140078db4`
- `0x140078fb8`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140078e9e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140078e9e`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140078ead`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140078ead`

## pseudocode

```c
void __fastcall A2dpSidebandAudioWdmEndpoint::UpdateMtuSizeSiop(
        A2dpSidebandAudioWdmEndpoint *this,
        __int16 a2,
        __int64 a3)
{
  char v4; // si
  __int64 Next; // rbp
  unsigned int v6; // ebx
  __int64 (__fastcall ***v7)(_QWORD, __int128 *, __int64, __int16 *); // rcx
  int v8; // eax
  int v9; // edx
  int v10; // r8d
  __int16 v11; // [rsp+50h] [rbp-68h] BYREF
  char *v12; // [rsp+58h] [rbp-60h] BYREF
  __int64 v13; // [rsp+60h] [rbp-58h] BYREF
  utl::_RefCountBase *v14; // [rsp+68h] [rbp-50h]
  __int128 v15; // [rsp+70h] [rbp-48h] BYREF
  int v16; // [rsp+80h] [rbp-38h]

  v11 = a2;
  v4 = 1;
  LOBYTE(a2) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      a2,
      a3,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      5,
      21,
      (__int64)WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids,
      (char)this);
  Next = 0;
  utl::weak_ptr<BtaMpmContext>::lock((char *)this + 616, &v13, a3);
  if ( v13 )
  {
    v16 = 4;
    v15 = SIDEBANDAUDIO_PARAMS_SET_A2DP;
    KeEnterCriticalRegion();
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)((char *)this + 680));
    v7 = (__int64 (__fastcall ***)(_QWORD, __int128 *, __int64, __int16 *))*((_QWORD *)this + 3);
    v12 = (char *)this + 680;
    v8 = (**v7)(v7, &v15, 2, &v11);
    v6 = v8;
    if ( v8 < 0 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        v4 = 0;
      }
      if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v9) = v4;
        LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_dq(
          WPP_GLOBAL_Control->AttachedDevice,
          v9,
          v10,
          WPP_GLOBAL_Control->DeviceExtension,
          2,
          19,
          22,
          (__int64)WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids,
          v8,
          (char)this);
      }
    }
    else
    {
      Next = IoQueue_GetNext((char *)this + 968);
    }
    __1__unique_storage_U__resource_policy_PEAU_FAST_MUTEX____A6AXPEAU1___E_1_release_fast_mutex_with_critical_region_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAA_XZ(&v12);
  }
  else
  {
    v6 = 0;
  }
  CompleteA2dpSiopIrp(Next, 4, v6);
  if ( v14 )
    utl::_RefCountBase::_DecStrong(v14);
}

```

## disassembly

```asm
0x140078db4  mov     [rsp+arg_10], rbx
0x140078db9  mov     [rsp+arg_18], rbp
0x140078dbe  push    rsi
0x140078dbf  push    rdi
0x140078dc0  push    r12
0x140078dc2  push    r13
0x140078dc4  push    r15
0x140078dc6  sub     rsp, 90h
0x140078dcd  mov     rax, cs:__security_cookie
0x140078dd4  xor     rax, rsp
0x140078dd7  mov     [rsp+0B8h+var_30], rax
0x140078ddf  mov     rdi, rcx
0x140078de2  mov     [rsp+0B8h+var_68], dx
0x140078de7  mov     rcx, cs:WPP_GLOBAL_Control
0x140078dee  lea     r15, WPP_GLOBAL_Control
0x140078df5  mov     sil, 1
0x140078df8  cmp     rcx, r15
0x140078dfb  jz      short loc_140078E0F
0x140078dfd  mov     eax, [rcx+2Ch]
0x140078e00  test    al, 10h
0x140078e02  jz      short loc_140078E0F
0x140078e04  cmp     byte ptr [rcx+29h], 4
0x140078e08  jb      short loc_140078E0F
0x140078e0a  mov     dl, sil
0x140078e0d  jmp     short loc_140078E11
0x140078e0f  xor     dl, dl
0x140078e11  lea     r12, WPP_RECORDER_INITIALIZED
0x140078e18  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140078e1f  lea     r13, WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids
0x140078e26  setnz   r8b
0x140078e2a  test    dl, dl
0x140078e2c  jnz     short loc_140078E33
0x140078e2e  test    r8b, r8b
0x140078e31  jz      short loc_140078E5E
0x140078e33  mov     r9, [rcx+40h]
0x140078e37  mov     rcx, [rcx+18h]
0x140078e3b  mov     [rsp+0B8h+var_78], rdi
0x140078e40  mov     [rsp+0B8h+var_80], r13
0x140078e45  mov     [rsp+0B8h+var_88], 15h
0x140078e4c  mov     [rsp+0B8h+var_90], 5
0x140078e54  mov     [rsp+0B8h+var_98], 4
0x140078e59  call    WPP_RECORDER_AND_TRACE_SF_q
0x140078e5e  lea     rcx, [rdi+268h]
0x140078e65  xor     ebp, ebp
0x140078e67  lea     rdx, [rsp+0B8h+var_58]
0x140078e6c  call    ?lock@?$weak_ptr@VBtaMpmContext@@@utl@@QEBA?AV?$shared_ptr@VBtaMpmContext@@@2@XZ; utl::weak_ptr<BtaMpmContext>::lock(void)
0x140078e71  cmp     [rsp+0B8h+var_58], rbp
0x140078e76  jnz     short loc_140078E7F
0x140078e78  xor     ebx, ebx
0x140078e7a  jmp     loc_140078F63
0x140078e7f  movups  xmm0, cs:SIDEBANDAUDIO_PARAMS_SET_A2DP
0x140078e86  mov     [rsp+0B8h+var_38], 4
0x140078e91  lea     rbx, [rdi+2A8h]
0x140078e98  movdqu  [rsp+0B8h+var_48], xmm0
0x140078e9e  call    cs:__imp_KeEnterCriticalRegion
0x140078ea5  nop     dword ptr [rax+rax+00h]
0x140078eaa  mov     rcx, rbx; FastMutex
0x140078ead  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140078eb4  nop     dword ptr [rax+rax+00h]
0x140078eb9  mov     rcx, [rdi+18h]
0x140078ebd  lea     r9, [rsp+0B8h+var_68]
0x140078ec2  mov     r8d, 2
0x140078ec8  mov     [rsp+0B8h+var_60], rbx
0x140078ecd  lea     rdx, [rsp+0B8h+var_48]
0x140078ed2  mov     rax, [rcx]
0x140078ed5  mov     rax, [rax]
0x140078ed8  call    _guard_dispatch_icall
0x140078edd  mov     ebx, eax
0x140078edf  test    eax, eax
0x140078ee1  js      short loc_140078EF4
0x140078ee3  lea     rcx, [rdi+3C8h]
0x140078eea  call    IoQueue_GetNext
0x140078eef  mov     rbp, rax
0x140078ef2  jmp     short loc_140078F59
0x140078ef4  mov     rcx, cs:WPP_GLOBAL_Control
0x140078efb  cmp     rcx, r15
0x140078efe  jz      short loc_140078F0F
0x140078f00  test    dword ptr [rcx+2Ch], 40000h
0x140078f07  jz      short loc_140078F0F
0x140078f09  cmp     byte ptr [rcx+29h], 2
0x140078f0d  jnb     short loc_140078F12
0x140078f0f  xor     sil, sil
0x140078f12  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140078f19  setnz   r8b
0x140078f1d  test    sil, sil
0x140078f20  jnz     short loc_140078F27
0x140078f22  test    r8b, r8b
0x140078f25  jz      short loc_140078F59
0x140078f27  mov     r9, [rcx+40h]
0x140078f2b  mov     dl, sil
0x140078f2e  mov     rcx, [rcx+18h]
0x140078f32  mov     [rsp+0B8h+var_70], rdi
0x140078f37  mov     dword ptr [rsp+0B8h+var_78], eax
0x140078f3b  mov     [rsp+0B8h+var_80], r13
0x140078f40  mov     [rsp+0B8h+var_88], 16h
0x140078f47  mov     [rsp+0B8h+var_90], 13h
0x140078f4f  mov     [rsp+0B8h+var_98], 2
0x140078f54  call    WPP_RECORDER_AND_TRACE_SF_dq
0x140078f59  lea     rcx, [rsp+0B8h+var_60]
0x140078f5e  call    ??1?$unique_storage@U?$resource_policy@PEAU_FAST_MUTEX@@$$A6AXPEAU1@@_E$1?release_fast_mutex_with_critical_region@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140078f63  mov     r8d, ebx
0x140078f66  mov     edx, 4
0x140078f6b  mov     rcx, rbp
0x140078f6e  call    CompleteA2dpSiopIrp
0x140078f73  mov     rcx, [rsp+0B8h+var_50]; this
0x140078f78  test    rcx, rcx
0x140078f7b  jz      short loc_140078F82
0x140078f7d  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140078f82  mov     rcx, [rsp+0B8h+var_30]
0x140078f8a  xor     rcx, rsp; StackCookie
0x140078f8d  call    __security_check_cookie
0x140078f92  lea     r11, [rsp+0B8h+var_28]
0x140078f9a  mov     rbx, [r11+40h]
0x140078f9e  mov     rbp, [r11+48h]
0x140078fa2  mov     rsp, r11
0x140078fa5  pop     r15
0x140078fa7  pop     r13
0x140078fa9  pop     r12
0x140078fab  pop     rdi
0x140078fac  pop     rsi
0x140078fad  retn
```
