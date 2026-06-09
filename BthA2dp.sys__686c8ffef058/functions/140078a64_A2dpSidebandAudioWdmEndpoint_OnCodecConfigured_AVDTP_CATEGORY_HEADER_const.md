# A2dpSidebandAudioWdmEndpoint::OnCodecConfigured(_AVDTP_CATEGORY_HEADER const *)

- ea: `0x140078a64`
- end: `0x140078dae`
- name: `?OnCodecConfigured@A2dpSidebandAudioWdmEndpoint@@QEAAJPEBU_AVDTP_CATEGORY_HEADER@@@Z`
- size: `842`
- prototype: `__int64 __fastcall(A2dpSidebandAudioWdmEndpoint *__hidden this, const struct _AVDTP_CATEGORY_HEADER *)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140078160`
- `0x14007b3ac`

## callees

- `0x140003530`
- `0x140006380`
- `0x140006410`
- `0x140010628`
- `0x1400202e8`
- `0x14002e378`
- `0x14002e5fc`
- `0x140058410`
- `0x14005c7d0`
- `0x14005c870`
- `0x140078a64`
- `0x140078fb8`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140078b2a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140078c96`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140078b2a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140078c96`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140078b39`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140078ca5`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140078b39`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140078ca5`

## pseudocode

```c
__int64 __fastcall A2dpSidebandAudioWdmEndpoint::OnCodecConfigured(
        A2dpSidebandAudioWdmEndpoint *this,
        const struct _AVDTP_CATEGORY_HEADER *a2)
{
  const struct _AVDTP_CATEGORY_HEADER *v2; // rsi
  char v4; // bl
  __int64 (__fastcall ***v5)(_QWORD, __int128 *, __int64, const struct _AVDTP_CATEGORY_HEADER *); // rcx
  __int64 v6; // r8
  int v7; // edx
  int v8; // r8d
  unsigned int v9; // r14d
  __int64 Next; // rsi
  char v11; // al
  __int64 (__fastcall ***v12)(_QWORD, __int128 *, __int64, char *); // rcx
  int v13; // eax
  int v14; // r8d
  __int64 *v15; // rdx
  char v17[8]; // [rsp+50h] [rbp-29h] BYREF
  unsigned __int64 v18; // [rsp+58h] [rbp-21h] BYREF
  __int64 v19; // [rsp+60h] [rbp-19h] BYREF
  utl::_RefCountBase *v20; // [rsp+68h] [rbp-11h]
  __int128 v21; // [rsp+70h] [rbp-9h] BYREF
  int v22; // [rsp+80h] [rbp+7h]
  __int128 v23; // [rsp+88h] [rbp+Fh] BYREF
  int v24; // [rsp+98h] [rbp+1Fh]

  v2 = a2;
  v4 = 1;
  LOBYTE(a2) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)a2,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      19,
      18,
      (__int64)WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids,
      (char)this);
  v22 = 2;
  v21 = SIDEBANDAUDIO_PARAMS_SET_A2DP;
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)((char *)this + 680));
  v5 = (__int64 (__fastcall ***)(_QWORD, __int128 *, __int64, const struct _AVDTP_CATEGORY_HEADER *))*((_QWORD *)this + 3);
  v6 = *((unsigned __int8 *)v2 + 1) + 2LL;
  v18 = (unsigned __int64)this + 680;
  v9 = (**v5)(v5, &v21, v6, v2);
  if ( (v9 & 0x80000000) != 0 )
  {
    Next = 0;
    LOBYTE(v7) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    if ( (_BYTE)v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v8) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_dq(
        WPP_GLOBAL_Control->AttachedDevice,
        v7,
        v8,
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        19,
        19,
        (__int64)WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids,
        v9,
        (char)this);
    }
  }
  else
  {
    Next = IoQueue_GetNext((char *)this + 808);
  }
  __1__unique_storage_U__resource_policy_PEAU_FAST_MUTEX____A6AXPEAU1___E_1_release_fast_mutex_with_critical_region_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAA_XZ(&v18);
  CompleteA2dpSiopIrp(Next, 2, v9);
  v18 = (unsigned int)Feature_A2dpAptxAdaptive__private_featureState;
  if ( (Feature_A2dpAptxAdaptive__private_featureState & 0x10) == 0 )
  {
    LODWORD(v18) = Feature_A2dpAptxAdaptive__private_featureState | 1;
    wil_details_FeatureReporting_ReportUsageToService(Feature_A2dpAptxAdaptive__private_descriptor, v18, 3);
    wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(v18, 3, Feature_A2dpAptxAdaptive__private_descriptor);
  }
  A2dpRole::GetCurrentSelectedCodec(*(_QWORD *)(*((_QWORD *)this + 79) + 8LL), &v19);
  if ( !v19 || (v11 = 2, !*(_BYTE *)(v19 + 8)) )
    v11 = 1;
  v17[0] = v11;
  v24 = 3;
  v23 = SIDEBANDAUDIO_PARAMS_SET_A2DP;
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)((char *)this + 680));
  v12 = (__int64 (__fastcall ***)(_QWORD, __int128 *, __int64, char *))*((_QWORD *)this + 3);
  v18 = (unsigned __int64)this + 680;
  v13 = (**v12)(v12, &v23, 1, v17);
  if ( v13 < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      v4 = 0;
    }
    if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v15 = WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids;
      LOBYTE(v15) = v4;
      LOBYTE(v14) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_dq(
        WPP_GLOBAL_Control->AttachedDevice,
        (_DWORD)v15,
        v14,
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        19,
        20,
        (__int64)WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids,
        v13,
        (char)this);
    }
  }
  else
  {
    Next = IoQueue_GetNext((char *)this + 888);
  }
  __1__unique_storage_U__resource_policy_PEAU_FAST_MUTEX____A6AXPEAU1___E_1_release_fast_mutex_with_critical_region_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAA_XZ(&v18);
  CompleteA2dpSiopIrp(Next, 3, v9);
  if ( v20 )
    utl::_RefCountBase::_DecStrong(v20);
  return v9;
}

```

## disassembly

```asm
0x140078a64  mov     [rsp-8+arg_10], rbx
0x140078a69  mov     [rsp-8+arg_18], rsi
0x140078a6e  push    rbp
0x140078a6f  push    rdi
0x140078a70  push    r12
0x140078a72  push    r14
0x140078a74  push    r15
0x140078a76  lea     rbp, [rsp-37h]
0x140078a7b  sub     rsp, 0B0h
0x140078a82  mov     rax, cs:__security_cookie
0x140078a89  xor     rax, rsp
0x140078a8c  mov     [rbp+57h+var_30], rax
0x140078a90  mov     rsi, rdx
0x140078a93  mov     rdi, rcx
0x140078a96  mov     rcx, cs:WPP_GLOBAL_Control
0x140078a9d  lea     r12, WPP_GLOBAL_Control
0x140078aa4  mov     ebx, 1
0x140078aa9  cmp     rcx, r12
0x140078aac  jz      short loc_140078AC1
0x140078aae  test    dword ptr [rcx+2Ch], 40000h
0x140078ab5  jz      short loc_140078AC1
0x140078ab7  cmp     byte ptr [rcx+29h], 4
0x140078abb  jb      short loc_140078AC1
0x140078abd  mov     dl, bl
0x140078abf  jmp     short loc_140078AC3
0x140078ac1  xor     dl, dl
0x140078ac3  lea     rax, WPP_RECORDER_INITIALIZED
0x140078aca  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140078ad1  lea     r9, WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids
0x140078ad8  setnz   r8b
0x140078adc  test    dl, dl
0x140078ade  jnz     short loc_140078AE5
0x140078ae0  test    r8b, r8b
0x140078ae3  jz      short loc_140078B10
0x140078ae5  mov     [rsp+0D0h+var_90], rdi
0x140078aea  mov     [rsp+0D0h+var_98], r9
0x140078aef  mov     r9, [rcx+40h]
0x140078af3  mov     rcx, [rcx+18h]
0x140078af7  mov     [rsp+0D0h+var_A0], 12h
0x140078afe  mov     [rsp+0D0h+var_A8], 13h
0x140078b06  mov     [rsp+0D0h+var_B0], 4
0x140078b0b  call    WPP_RECORDER_AND_TRACE_SF_q
0x140078b10  movups  xmm0, cs:SIDEBANDAUDIO_PARAMS_SET_A2DP
0x140078b17  mov     [rbp+57h+var_50], 2
0x140078b1e  lea     r15, [rdi+2A8h]
0x140078b25  movdqu  [rbp+57h+var_60], xmm0
0x140078b2a  call    cs:__imp_KeEnterCriticalRegion
0x140078b31  nop     dword ptr [rax+rax+00h]
0x140078b36  mov     rcx, r15; FastMutex
0x140078b39  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140078b40  nop     dword ptr [rax+rax+00h]
0x140078b45  mov     rcx, [rdi+18h]
0x140078b49  lea     rdx, [rbp+57h+var_60]
0x140078b4d  movzx   r8d, byte ptr [rsi+1]
0x140078b52  mov     r9, rsi
0x140078b55  add     r8, 2
0x140078b59  mov     [rbp+57h+var_78], r15
0x140078b5d  mov     rax, [rcx]
0x140078b60  mov     rax, [rax]
0x140078b63  call    _guard_dispatch_icall
0x140078b68  mov     r14d, eax
0x140078b6b  test    eax, eax
0x140078b6d  js      short loc_140078B80
0x140078b6f  lea     rcx, [rdi+328h]
0x140078b76  call    IoQueue_GetNext
0x140078b7b  mov     rsi, rax
0x140078b7e  jmp     short loc_140078BF4
0x140078b80  xor     esi, esi
0x140078b82  mov     rcx, cs:WPP_GLOBAL_Control
0x140078b89  cmp     rcx, r12
0x140078b8c  jz      short loc_140078BA1
0x140078b8e  test    dword ptr [rcx+2Ch], 40000h
0x140078b95  jz      short loc_140078BA1
0x140078b97  cmp     byte ptr [rcx+29h], 2
0x140078b9b  jb      short loc_140078BA1
0x140078b9d  mov     dl, bl
0x140078b9f  jmp     short loc_140078BA3
0x140078ba1  xor     dl, dl
0x140078ba3  lea     rax, WPP_RECORDER_INITIALIZED
0x140078baa  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140078bb1  setnz   r8b
0x140078bb5  test    dl, dl
0x140078bb7  jnz     short loc_140078BBE
0x140078bb9  test    r8b, r8b
0x140078bbc  jz      short loc_140078BF4
0x140078bbe  mov     r9, [rcx+40h]
0x140078bc2  lea     rax, WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids
0x140078bc9  mov     rcx, [rcx+18h]
0x140078bcd  mov     [rsp+0D0h+var_88], rdi
0x140078bd2  mov     dword ptr [rsp+0D0h+var_90], r14d
0x140078bd7  mov     [rsp+0D0h+var_98], rax
0x140078bdc  mov     eax, 13h
0x140078be1  mov     [rsp+0D0h+var_A0], ax
0x140078be6  mov     [rsp+0D0h+var_A8], eax
0x140078bea  mov     [rsp+0D0h+var_B0], 2
0x140078bef  call    WPP_RECORDER_AND_TRACE_SF_dq
0x140078bf4  lea     rcx, [rbp+57h+var_78]
0x140078bf8  call    ??1?$unique_storage@U?$resource_policy@PEAU_FAST_MUTEX@@$$A6AXPEAU1@@_E$1?release_fast_mutex_with_critical_region@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140078bfd  mov     r8d, r14d
0x140078c00  mov     edx, 2
0x140078c05  mov     rcx, rsi
0x140078c08  call    CompleteA2dpSiopIrp
0x140078c0d  mov     ecx, cs:Feature_A2dpAptxAdaptive__private_featureState
0x140078c13  mov     r12d, 3
0x140078c19  mov     [rbp+57h+var_78], 0
0x140078c21  mov     dword ptr [rbp+57h+var_78], ecx
0x140078c24  test    cl, 10h
0x140078c27  jnz     short loc_140078C5C
0x140078c29  mov     rax, [rbp+57h+var_78]
0x140078c2d  or      ecx, ebx
0x140078c2f  mov     [rbp+57h+var_78], rax
0x140078c33  mov     r8d, r12d
0x140078c36  mov     dword ptr [rbp+57h+var_78], ecx
0x140078c39  lea     rcx, Feature_A2dpAptxAdaptive__private_descriptor
0x140078c40  mov     rdx, [rbp+57h+var_78]
0x140078c44  call    wil_details_FeatureReporting_ReportUsageToService
0x140078c49  mov     rcx, [rbp+57h+var_78]
0x140078c4d  lea     r8, Feature_A2dpAptxAdaptive__private_descriptor
0x140078c54  mov     edx, r12d
0x140078c57  call    wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath
0x140078c5c  mov     rcx, [rdi+278h]
0x140078c63  lea     rdx, [rbp+57h+var_70]
0x140078c67  mov     rcx, [rcx+8]
0x140078c6b  call    ?GetCurrentSelectedCodec@A2dpRole@@QEBA?AV?$shared_ptr@VA2dpAudioCodec@@@utl@@XZ; A2dpRole::GetCurrentSelectedCodec(void)
0x140078c70  mov     rax, [rbp+57h+var_70]
0x140078c74  test    rax, rax
0x140078c77  jz      short loc_140078C81
0x140078c79  cmp     byte ptr [rax+8], 0
0x140078c7d  mov     al, 2
0x140078c7f  jnz     short loc_140078C83
0x140078c81  mov     al, bl
0x140078c83  movups  xmm0, cs:SIDEBANDAUDIO_PARAMS_SET_A2DP
0x140078c8a  mov     [rbp+57h+var_80], al
0x140078c8d  mov     [rbp+57h+var_38], r12d
0x140078c91  movdqu  [rbp+57h+var_48], xmm0
0x140078c96  call    cs:__imp_KeEnterCriticalRegion
0x140078c9d  nop     dword ptr [rax+rax+00h]
0x140078ca2  mov     rcx, r15; FastMutex
0x140078ca5  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140078cac  nop     dword ptr [rax+rax+00h]
0x140078cb1  mov     rcx, [rdi+18h]
0x140078cb5  lea     r9, [rbp+57h+var_80]
0x140078cb9  mov     r8, rbx
0x140078cbc  mov     [rbp+57h+var_78], r15
0x140078cc0  lea     rdx, [rbp+57h+var_48]
0x140078cc4  mov     rax, [rcx]
0x140078cc7  mov     rax, [rax]
0x140078cca  call    _guard_dispatch_icall
0x140078ccf  mov     edx, eax
0x140078cd1  test    eax, eax
0x140078cd3  js      short loc_140078CE6
0x140078cd5  lea     rcx, [rdi+378h]
0x140078cdc  call    IoQueue_GetNext
0x140078ce1  mov     rsi, rax
0x140078ce4  jmp     short loc_140078D5D
0x140078ce6  mov     rcx, cs:WPP_GLOBAL_Control
0x140078ced  lea     rax, WPP_GLOBAL_Control
0x140078cf4  cmp     rcx, rax
0x140078cf7  jz      short loc_140078D08
0x140078cf9  test    dword ptr [rcx+2Ch], 40000h
0x140078d00  jz      short loc_140078D08
0x140078d02  cmp     byte ptr [rcx+29h], 2
0x140078d06  jnb     short loc_140078D0A
0x140078d08  xor     bl, bl
0x140078d0a  lea     rax, WPP_RECORDER_INITIALIZED
0x140078d11  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140078d18  setnz   r8b
0x140078d1c  test    bl, bl
0x140078d1e  jnz     short loc_140078D25
0x140078d20  test    r8b, r8b
0x140078d23  jz      short loc_140078D5D
0x140078d25  mov     r9, [rcx+40h]
0x140078d29  mov     rcx, [rcx+18h]
0x140078d2d  mov     [rsp+0D0h+var_88], rdi
0x140078d32  mov     dword ptr [rsp+0D0h+var_90], edx
0x140078d36  lea     rdx, WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids
0x140078d3d  mov     [rsp+0D0h+var_98], rdx
0x140078d42  mov     dl, bl
0x140078d44  mov     [rsp+0D0h+var_A0], 14h
0x140078d4b  mov     [rsp+0D0h+var_A8], 13h
0x140078d53  mov     [rsp+0D0h+var_B0], 2
0x140078d58  call    WPP_RECORDER_AND_TRACE_SF_dq
0x140078d5d  lea     rcx, [rbp+57h+var_78]
0x140078d61  call    ??1?$unique_storage@U?$resource_policy@PEAU_FAST_MUTEX@@$$A6AXPEAU1@@_E$1?release_fast_mutex_with_critical_region@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140078d66  mov     r8d, r14d
0x140078d69  mov     edx, r12d
0x140078d6c  mov     rcx, rsi
0x140078d6f  call    CompleteA2dpSiopIrp
0x140078d74  mov     rcx, [rbp+57h+var_68]; this
0x140078d78  test    rcx, rcx
0x140078d7b  jz      short loc_140078D82
0x140078d7d  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140078d82  mov     eax, r14d
0x140078d85  mov     rcx, [rbp+57h+var_30]
0x140078d89  xor     rcx, rsp; StackCookie
0x140078d8c  call    __security_check_cookie
0x140078d91  lea     r11, [rsp+0D0h+var_20]
0x140078d99  mov     rbx, [r11+40h]
0x140078d9d  mov     rsi, [r11+48h]
0x140078da1  mov     rsp, r11
0x140078da4  pop     r15
0x140078da6  pop     r14
0x140078da8  pop     r12
0x140078daa  pop     rdi
0x140078dab  pop     rbp
0x140078dac  retn
```
