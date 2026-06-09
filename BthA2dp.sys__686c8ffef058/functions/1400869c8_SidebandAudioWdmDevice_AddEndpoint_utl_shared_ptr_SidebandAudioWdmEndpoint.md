# SidebandAudioWdmDevice::AddEndpoint(utl::shared_ptr<SidebandAudioWdmEndpoint>)

- ea: `0x1400869c8`
- end: `0x140086b31`
- name: `?AddEndpoint@SidebandAudioWdmDevice@@IEAAJV?$shared_ptr@VSidebandAudioWdmEndpoint@@@utl@@@Z`
- size: `361`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x14007d8b0`

## callees

- `0x140006410`
- `0x14000e690`
- `0x1400202e8`
- `0x140034630`
- `0x1400869c8`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1400869e1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400869e1`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400869f0`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400869f0`

## pseudocode

```c
__int64 __fastcall SidebandAudioWdmDevice::AddEndpoint(_QWORD *a1, __int64 *a2)
{
  struct _FAST_MUTEX *v3; // rbx
  int v5; // r8d
  __int64 v6; // rcx
  unsigned __int64 v7; // rcx
  unsigned __int64 v8; // rdx
  utl::_RefCountBase *v9; // rcx
  _QWORD *v11; // rdx
  __int64 v12; // rax
  utl::_RefCountBase *v13; // rcx
  struct _FAST_MUTEX *v14; // [rsp+60h] [rbp+8h] BYREF

  v3 = (struct _FAST_MUTEX *)(a1 + 3);
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe(v3);
  v6 = a1[13];
  v14 = v3;
  if ( a1[12] != v6 )
    goto LABEL_17;
  v7 = (v6 - a1[11]) >> 4;
  v8 = 7 * (v7 >> 2) + 8;
  if ( v8 > 0x7FFFFFFFFFFFFFFLL )
    v8 = 0x7FFFFFFFFFFFFFFLL;
  if ( v7 < v8
    && (unsigned __int8)utl::vector<utl::shared_ptr<wil::details::kernel_event_t<1>>,utl::allocator<utl::shared_ptr<wil::details::kernel_event_t<1>>>>::_SetCapacity(a1 + 11) )
  {
LABEL_17:
    v11 = (_QWORD *)a1[12];
    v12 = *a2;
    v11[1] = a2[1];
    *v11 = v12;
    *a2 = 0;
    a2[1] = 0;
    a1[12] += 16LL;
    __1__unique_storage_U__resource_policy_PEAU_FAST_MUTEX____A6AXPEAU1___E_1_release_fast_mutex_with_critical_region_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAA_XZ(&v14);
    v13 = (utl::_RefCountBase *)a2[1];
    if ( v13 )
      utl::_RefCountBase::_DecStrong(v13);
    return 0;
  }
  else
  {
    LOBYTE(v8) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    if ( (_BYTE)v8 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v5) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        v8,
        v5,
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        2,
        28,
        (__int64)WPP_6f6ca3ff72523c797fc054add42d8828_Traceguids,
        154);
    }
    __1__unique_storage_U__resource_policy_PEAU_FAST_MUTEX____A6AXPEAU1___E_1_release_fast_mutex_with_critical_region_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAA_XZ(&v14);
    v9 = (utl::_RefCountBase *)a2[1];
    if ( v9 )
      utl::_RefCountBase::_DecStrong(v9);
    return 3221225626LL;
  }
}

```

## disassembly

```asm
0x1400869c8  mov     [rsp+arg_8], rbx
0x1400869cd  mov     [rsp+arg_10], rsi
0x1400869d2  push    rdi
0x1400869d3  sub     rsp, 50h
0x1400869d7  mov     rsi, rdx
0x1400869da  lea     rbx, [rcx+18h]
0x1400869de  mov     rdi, rcx
0x1400869e1  call    cs:__imp_KeEnterCriticalRegion
0x1400869e8  nop     dword ptr [rax+rax+00h]
0x1400869ed  mov     rcx, rbx; FastMutex
0x1400869f0  call    cs:__imp_ExAcquireFastMutexUnsafe
0x1400869f7  nop     dword ptr [rax+rax+00h]
0x1400869fc  mov     rcx, [rdi+68h]
0x140086a00  mov     [rsp+58h+arg_0], rbx
0x140086a05  cmp     [rdi+60h], rcx
0x140086a09  jnz     loc_140086AE0
0x140086a0f  sub     rcx, [rdi+58h]
0x140086a13  sar     rcx, 4
0x140086a17  mov     rax, rcx
0x140086a1a  shr     rax, 2
0x140086a1e  imul    rdx, rax, 7
0x140086a22  mov     rax, 7FFFFFFFFFFFFFFh
0x140086a2c  add     rdx, 8
0x140086a30  cmp     rdx, rax
0x140086a33  cmova   rdx, rax
0x140086a37  cmp     rcx, rdx
0x140086a3a  jnb     short loc_140086A4D
0x140086a3c  lea     rcx, [rdi+58h]
0x140086a40  call    ?_SetCapacity@?$vector@V?$shared_ptr@V?$kernel_event_t@$00@details@wil@@@utl@@V?$allocator@V?$shared_ptr@V?$kernel_event_t@$00@details@wil@@@utl@@@2@@utl@@AEAA_N_K@Z; utl::vector<utl::shared_ptr<wil::details::kernel_event_t<1>>,utl::allocator<utl::shared_ptr<wil::details::kernel_event_t<1>>>>::_SetCapacity(unsigned __int64)
0x140086a45  test    al, al
0x140086a47  jnz     loc_140086AE0
0x140086a4d  mov     rcx, cs:WPP_GLOBAL_Control
0x140086a54  lea     rax, WPP_GLOBAL_Control
0x140086a5b  cmp     rcx, rax
0x140086a5e  jz      short loc_140086A71
0x140086a60  mov     eax, [rcx+2Ch]
0x140086a63  test    al, 2
0x140086a65  jz      short loc_140086A71
0x140086a67  cmp     byte ptr [rcx+29h], 2
0x140086a6b  jb      short loc_140086A71
0x140086a6d  mov     dl, 1
0x140086a6f  jmp     short loc_140086A73
0x140086a71  xor     dl, dl
0x140086a73  lea     rax, WPP_RECORDER_INITIALIZED
0x140086a7a  mov     ebx, 0C000009Ah
0x140086a7f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140086a86  setnz   r8b
0x140086a8a  test    dl, dl
0x140086a8c  jnz     short loc_140086A93
0x140086a8e  test    r8b, r8b
0x140086a91  jz      short loc_140086AC4
0x140086a93  mov     r9, [rcx+40h]
0x140086a97  lea     rax, WPP_6f6ca3ff72523c797fc054add42d8828_Traceguids
0x140086a9e  mov     rcx, [rcx+18h]
0x140086aa2  mov     [rsp+58h+var_18], ebx
0x140086aa6  mov     [rsp+58h+var_20], rax
0x140086aab  mov     [rsp+58h+var_28], 1Ch
0x140086ab2  mov     [rsp+58h+var_30], 2
0x140086aba  mov     [rsp+58h+var_38], 2
0x140086abf  call    WPP_RECORDER_AND_TRACE_SF_d
0x140086ac4  lea     rcx, [rsp+58h+arg_0]
0x140086ac9  call    ??1?$unique_storage@U?$resource_policy@PEAU_FAST_MUTEX@@$$A6AXPEAU1@@_E$1?release_fast_mutex_with_critical_region@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140086ace  mov     rcx, [rsi+8]; this
0x140086ad2  test    rcx, rcx
0x140086ad5  jz      short loc_140086ADC
0x140086ad7  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140086adc  mov     eax, ebx
0x140086ade  jmp     short loc_140086B20
0x140086ae0  mov     rdx, [rdi+60h]
0x140086ae4  mov     rcx, [rsi+8]
0x140086ae8  mov     rax, [rsi]
0x140086aeb  mov     [rdx+8], rcx
0x140086aef  lea     rcx, [rsp+58h+arg_0]
0x140086af4  mov     [rdx], rax
0x140086af7  mov     qword ptr [rsi], 0
0x140086afe  mov     qword ptr [rsi+8], 0
0x140086b06  add     qword ptr [rdi+60h], 10h
0x140086b0b  call    ??1?$unique_storage@U?$resource_policy@PEAU_FAST_MUTEX@@$$A6AXPEAU1@@_E$1?release_fast_mutex_with_critical_region@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140086b10  mov     rcx, [rsi+8]; this
0x140086b14  test    rcx, rcx
0x140086b17  jz      short loc_140086B1E
0x140086b19  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140086b1e  xor     eax, eax
0x140086b20  mov     rbx, [rsp+58h+arg_8]
0x140086b25  mov     rsi, [rsp+58h+arg_10]
0x140086b2a  add     rsp, 50h
0x140086b2e  pop     rdi
0x140086b2f  retn
```
