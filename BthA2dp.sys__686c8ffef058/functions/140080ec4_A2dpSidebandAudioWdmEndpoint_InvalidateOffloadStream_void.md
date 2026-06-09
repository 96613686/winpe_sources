# A2dpSidebandAudioWdmEndpoint::InvalidateOffloadStream(void)

- ea: `0x140080ec4`
- end: `0x140081055`
- name: `?InvalidateOffloadStream@A2dpSidebandAudioWdmEndpoint@@QEAAXXZ`
- size: `401`
- prototype: `void __fastcall(A2dpSidebandAudioWdmEndpoint *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x14002c428`

## callees

- `0x140006a88`
- `0x140010628`
- `0x140013e58`
- `0x1400202e8`
- `0x140036b7c`
- `0x140080ec4`
- `0x140081ba0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140080ee1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140080ee1`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140080ef0`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140080ef0`

## pseudocode

```c
void __fastcall A2dpSidebandAudioWdmEndpoint::InvalidateOffloadStream(A2dpSidebandAudioWdmEndpoint *this)
{
  struct _FAST_MUTEX *v2; // rbx
  __int64 v3; // rdx
  __int64 v4; // r9
  __int64 v5; // r8
  char v6; // bl
  int v7; // eax
  int v8; // edx
  int v9; // r8d
  __int64 v10; // rdx
  char v11; // [rsp+40h] [rbp-28h]
  struct _FAST_MUTEX *v12; // [rsp+70h] [rbp+8h] BYREF

  v2 = (struct _FAST_MUTEX *)((char *)this + 744);
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe(v2);
  v5 = *((unsigned int *)this + 200);
  v12 = v2;
  v6 = 1;
  if ( (unsigned int)(v5 - 1) <= 1 )
  {
    LOBYTE(v3) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    if ( (_BYTE)v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v11 = v5;
      LOBYTE(v5) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_Dq(
        WPP_GLOBAL_Control->AttachedDevice,
        v3,
        v5,
        WPP_GLOBAL_Control->DeviceExtension,
        4,
        19,
        66,
        (__int64)WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids,
        v11,
        this);
    }
    v7 = A2dpSidebandAudioWdmEndpoint::SendAvdtpBrb<_BRB_HCI_VS_MSFT_AVDTP_CLOSE>(this, v3, v5, v4);
    if ( v7 < 0 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        v6 = 0;
      }
      if ( v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v8) = v6;
        LOBYTE(v9) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_dq(
          WPP_GLOBAL_Control->AttachedDevice,
          v8,
          v9,
          WPP_GLOBAL_Control->DeviceExtension,
          2,
          19,
          67,
          (__int64)WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids,
          v7,
          (char)this);
      }
    }
    A2dpSidebandAudioWdmEndpoint::SetAvdtpOffloadHandle(this, 0);
    v10 = *((_QWORD *)this + 84);
    *((_QWORD *)this + 84) = 0;
    if ( v10 )
      utl::default_delete<SiopStore>::operator()();
    *((_DWORD *)this + 200) = 3;
  }
  __1__unique_storage_U__resource_policy_PEAU_FAST_MUTEX____A6AXPEAU1___E_1_release_fast_mutex_with_critical_region_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAA_XZ(&v12);
}

```

## disassembly

```asm
0x140080ec4  mov     [rsp+arg_8], rbx
0x140080ec9  mov     [rsp+arg_10], rbp
0x140080ece  push    rdi
0x140080ecf  push    r12
0x140080ed1  push    r14
0x140080ed3  sub     rsp, 50h
0x140080ed7  mov     rdi, rcx
0x140080eda  lea     rbx, [rcx+2E8h]
0x140080ee1  call    cs:__imp_KeEnterCriticalRegion
0x140080ee8  nop     dword ptr [rax+rax+00h]
0x140080eed  mov     rcx, rbx; FastMutex
0x140080ef0  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140080ef7  nop     dword ptr [rax+rax+00h]
0x140080efc  mov     r8d, [rdi+320h]
0x140080f03  mov     [rsp+68h+arg_0], rbx
0x140080f08  mov     ebx, 1
0x140080f0d  lea     eax, [r8-1]
0x140080f11  cmp     eax, ebx
0x140080f13  ja      loc_140081034
0x140080f19  mov     rcx, cs:WPP_GLOBAL_Control
0x140080f20  lea     rbp, WPP_GLOBAL_Control
0x140080f27  cmp     rcx, rbp
0x140080f2a  jz      short loc_140080F3F
0x140080f2c  test    dword ptr [rcx+2Ch], 40000h
0x140080f33  jz      short loc_140080F3F
0x140080f35  cmp     byte ptr [rcx+29h], 4
0x140080f39  jb      short loc_140080F3F
0x140080f3b  mov     dl, bl
0x140080f3d  jmp     short loc_140080F41
0x140080f3f  xor     dl, dl
0x140080f41  lea     r14, WPP_RECORDER_INITIALIZED
0x140080f48  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140080f4f  lea     r12, WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids
0x140080f56  setnz   al
0x140080f59  test    dl, dl
0x140080f5b  jnz     short loc_140080F61
0x140080f5d  test    al, al
0x140080f5f  jz      short loc_140080F94
0x140080f61  mov     r9, [rcx+40h]
0x140080f65  mov     rcx, [rcx+18h]
0x140080f69  mov     [rsp+68h+var_20], rdi
0x140080f6e  mov     dword ptr [rsp+68h+var_28], r8d
0x140080f73  mov     r8b, al
0x140080f76  mov     [rsp+68h+var_30], r12
0x140080f7b  mov     [rsp+68h+var_38], 42h ; 'B'
0x140080f82  mov     [rsp+68h+var_40], 13h
0x140080f8a  mov     [rsp+68h+var_48], 4
0x140080f8f  call    WPP_RECORDER_AND_TRACE_SF_Dq
0x140080f94  mov     rcx, rdi; this
0x140080f97  call    ??$SendAvdtpBrb@U_BRB_HCI_VS_MSFT_AVDTP_CLOSE@@@A2dpSidebandAudioWdmEndpoint@@AEAAJW4_BRB_TYPE@@@Z; A2dpSidebandAudioWdmEndpoint::SendAvdtpBrb<_BRB_HCI_VS_MSFT_AVDTP_CLOSE>(_BRB_TYPE)
0x140080f9c  test    eax, eax
0x140080f9e  jns     short loc_140081004
0x140080fa0  mov     r10, cs:WPP_GLOBAL_Control
0x140080fa7  cmp     r10, rbp
0x140080faa  jz      short loc_140080FBD
0x140080fac  test    dword ptr [r10+2Ch], 40000h
0x140080fb4  jz      short loc_140080FBD
0x140080fb6  cmp     byte ptr [r10+29h], 2
0x140080fbb  jnb     short loc_140080FBF
0x140080fbd  xor     bl, bl
0x140080fbf  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140080fc6  setnz   r8b
0x140080fca  test    bl, bl
0x140080fcc  jnz     short loc_140080FD3
0x140080fce  test    r8b, r8b
0x140080fd1  jz      short loc_140081004
0x140080fd3  mov     r9, [r10+40h]
0x140080fd7  mov     dl, bl
0x140080fd9  mov     rcx, [r10+18h]
0x140080fdd  mov     [rsp+68h+var_20], rdi
0x140080fe2  mov     dword ptr [rsp+68h+var_28], eax
0x140080fe6  mov     [rsp+68h+var_30], r12
0x140080feb  mov     [rsp+68h+var_38], 43h ; 'C'
0x140080ff2  mov     [rsp+68h+var_40], 13h
0x140080ffa  mov     [rsp+68h+var_48], 2
0x140080fff  call    WPP_RECORDER_AND_TRACE_SF_dq
0x140081004  xor     edx, edx; unsigned __int16
0x140081006  mov     rcx, rdi; this
0x140081009  call    ?SetAvdtpOffloadHandle@A2dpSidebandAudioWdmEndpoint@@_A2PAGE@@EAAXG@Z; A2dpSidebandAudioWdmEndpoint::SetAvdtpOffloadHandle(ushort)
0x14008100e  mov     rdx, [rdi+2A0h]
0x140081015  mov     qword ptr [rdi+2A0h], 0
0x140081020  test    rdx, rdx
0x140081023  jz      short loc_14008102A
0x140081025  call    ??R?$default_delete@VSiopStore@@@utl@@QEBAXPEAVSiopStore@@@Z; utl::default_delete<SiopStore>::operator()(SiopStore *)
0x14008102a  mov     dword ptr [rdi+320h], 3
0x140081034  lea     rcx, [rsp+68h+arg_0]
0x140081039  call    ??1?$unique_storage@U?$resource_policy@PEAU_FAST_MUTEX@@$$A6AXPEAU1@@_E$1?release_fast_mutex_with_critical_region@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14008103e  lea     r11, [rsp+68h+var_18]
0x140081043  mov     rbx, [r11+28h]
0x140081047  mov     rbp, [r11+30h]
0x14008104b  mov     rsp, r11
0x14008104e  pop     r14
0x140081050  pop     r12
0x140081052  pop     rdi
0x140081053  retn
```
