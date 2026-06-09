# A2dpSidebandAudioWdmEndpoint::CloseStream(_IRP *)

- ea: `0x14007e530`
- end: `0x14007e7ab`
- name: `?CloseStream@A2dpSidebandAudioWdmEndpoint@@AEAAJPEAU_IRP@@@Z`
- size: `635`
- prototype: `__int64 __fastcall(A2dpSidebandAudioWdmEndpoint *__hidden this, struct _IRP *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x140080730`

## callees

- `0x140003530`
- `0x140006a88`
- `0x140010628`
- `0x140013e58`
- `0x1400202e8`
- `0x14002d8e8`
- `0x140036b7c`
- `0x14007e530`
- `0x140081ba0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14007e5c5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14007e5c5`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14007e5d4`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14007e5d4`

## pseudocode

```c
__int64 __fastcall A2dpSidebandAudioWdmEndpoint::CloseStream(A2dpSidebandAudioWdmEndpoint *this, struct _IRP *a2)
{
  char v3; // si
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  __int64 *v7; // rdx
  __int64 v8; // rdx
  __int64 *v9; // rdx
  unsigned int v10; // ebx
  int v11; // eax
  int v12; // r8d
  __int64 *v13; // rdx
  __int64 v14; // rdx
  struct _IRP *v16; // [rsp+98h] [rbp+10h] BYREF

  v16 = a2;
  v3 = 1;
  LOBYTE(a2) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x12u)
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)a2,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      19,
      97,
      (__int64)WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids,
      (char)this);
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)((char *)this + 744));
  v16 = (struct _IRP *)((char *)this + 744);
  if ( (unsigned int)Feature_60759990__private_IsEnabledDeviceUsageNoInline(v4) && *((_DWORD *)this + 200) == 3 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x12u)
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    {
      v3 = 0;
    }
    if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v7 = WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids;
      LOBYTE(v7) = v3;
      WPP_RECORDER_AND_TRACE_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        (_DWORD)v7,
        WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
        WPP_GLOBAL_Control->DeviceExtension,
        4,
        19,
        98,
        (__int64)WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids,
        (char)this);
    }
LABEL_37:
    v10 = 0;
    *((_DWORD *)this + 200) = 0;
    goto LABEL_38;
  }
  v8 = *((unsigned int *)this + 200);
  if ( (_DWORD)v8 == 1 )
  {
    v11 = A2dpSidebandAudioWdmEndpoint::SendAvdtpBrb<_BRB_HCI_VS_MSFT_AVDTP_CLOSE>(this, v8, v5, v6);
    if ( v11 < 0 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x12u)
        || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
      {
        v3 = 0;
      }
      if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v13 = WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids;
        LOBYTE(v13) = v3;
        LOBYTE(v12) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_dq(
          WPP_GLOBAL_Control->AttachedDevice,
          (_DWORD)v13,
          v12,
          WPP_GLOBAL_Control->DeviceExtension,
          3,
          19,
          100,
          (__int64)WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids,
          v11,
          (char)this);
      }
    }
    A2dpSidebandAudioWdmEndpoint::SetAvdtpOffloadHandle(this, 0);
    v14 = *((_QWORD *)this + 84);
    *((_QWORD *)this + 84) = 0;
    if ( v14 )
      utl::default_delete<SiopStore>::operator()();
    goto LABEL_37;
  }
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x12u)
    || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
  {
    v3 = 0;
  }
  if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v9 = WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids;
    LOBYTE(v9) = v3;
    LOBYTE(v5) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_Dq(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)v9,
      v5,
      WPP_GLOBAL_Control->DeviceExtension,
      2,
      19,
      99,
      (__int64)WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids,
      *((_DWORD *)this + 200),
      this);
  }
  v10 = -1073741436;
LABEL_38:
  __1__unique_storage_U__resource_policy_PEAU_FAST_MUTEX____A6AXPEAU1___E_1_release_fast_mutex_with_critical_region_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAA_XZ(&v16);
  return v10;
}

```

## disassembly

```asm
0x14007e530  mov     [rsp+arg_8], rdx
0x14007e535  push    rbx
0x14007e536  push    rsi
0x14007e537  push    rdi
0x14007e538  push    r12
0x14007e53a  push    r14
0x14007e53c  push    r15
0x14007e53e  sub     rsp, 58h
0x14007e542  mov     rdi, rcx
0x14007e545  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e54c  lea     r15, WPP_GLOBAL_Control
0x14007e553  mov     esi, 1
0x14007e558  cmp     rcx, r15
0x14007e55b  jz      short loc_14007E56F
0x14007e55d  bt      dword ptr [rcx+2Ch], 12h
0x14007e562  jnb     short loc_14007E56F
0x14007e564  cmp     byte ptr [rcx+29h], 4
0x14007e568  jb      short loc_14007E56F
0x14007e56a  mov     dl, sil
0x14007e56d  jmp     short loc_14007E571
0x14007e56f  xor     dl, dl
0x14007e571  lea     r12, WPP_RECORDER_INITIALIZED
0x14007e578  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14007e57f  lea     r9, WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids
0x14007e586  setnz   r8b
0x14007e58a  test    dl, dl
0x14007e58c  jnz     short loc_14007E593
0x14007e58e  test    r8b, r8b
0x14007e591  jz      short loc_14007E5BE
0x14007e593  mov     [rsp+88h+var_48], rdi
0x14007e598  mov     [rsp+88h+var_50], r9
0x14007e59d  mov     r9, [rcx+40h]
0x14007e5a1  mov     rcx, [rcx+18h]
0x14007e5a5  mov     [rsp+88h+var_58], 61h ; 'a'
0x14007e5ac  mov     [rsp+88h+var_60], 13h
0x14007e5b4  mov     [rsp+88h+var_68], 4
0x14007e5b9  call    WPP_RECORDER_AND_TRACE_SF_q
0x14007e5be  lea     rbx, [rdi+2E8h]
0x14007e5c5  call    cs:__imp_KeEnterCriticalRegion
0x14007e5cc  nop     dword ptr [rax+rax+00h]
0x14007e5d1  mov     rcx, rbx; FastMutex
0x14007e5d4  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14007e5db  nop     dword ptr [rax+rax+00h]
0x14007e5e0  mov     [rsp+88h+arg_8], rbx
0x14007e5e8  call    Feature_60759990__private_IsEnabledDeviceUsageNoInline
0x14007e5ed  test    eax, eax
0x14007e5ef  jz      short loc_14007E669
0x14007e5f1  cmp     dword ptr [rdi+320h], 3
0x14007e5f8  jnz     short loc_14007E669
0x14007e5fa  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e601  cmp     rcx, r15
0x14007e604  jz      short loc_14007E613
0x14007e606  bt      dword ptr [rcx+2Ch], 12h
0x14007e60b  jnb     short loc_14007E613
0x14007e60d  cmp     byte ptr [rcx+29h], 4
0x14007e611  jnb     short loc_14007E616
0x14007e613  xor     sil, sil
0x14007e616  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14007e61d  setnz   r8b
0x14007e621  test    sil, sil
0x14007e624  jnz     short loc_14007E62F
0x14007e626  test    r8b, r8b
0x14007e629  jz      loc_14007E785
0x14007e62f  mov     r9, [rcx+40h]
0x14007e633  lea     rdx, WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids
0x14007e63a  mov     rcx, [rcx+18h]
0x14007e63e  mov     [rsp+88h+var_48], rdi
0x14007e643  mov     [rsp+88h+var_50], rdx
0x14007e648  mov     dl, sil
0x14007e64b  mov     [rsp+88h+var_58], 62h ; 'b'
0x14007e652  mov     [rsp+88h+var_60], 13h
0x14007e65a  mov     [rsp+88h+var_68], 4
0x14007e65f  call    WPP_RECORDER_AND_TRACE_SF_q
0x14007e664  jmp     loc_14007E785
0x14007e669  mov     edx, [rdi+320h]
0x14007e66f  cmp     edx, esi
0x14007e671  jz      short loc_14007E6E7
0x14007e673  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e67a  cmp     rcx, r15
0x14007e67d  jz      short loc_14007E68C
0x14007e67f  bt      dword ptr [rcx+2Ch], 12h
0x14007e684  jnb     short loc_14007E68C
0x14007e686  cmp     byte ptr [rcx+29h], 2
0x14007e68a  jnb     short loc_14007E68F
0x14007e68c  xor     sil, sil
0x14007e68f  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14007e696  setnz   r8b
0x14007e69a  test    sil, sil
0x14007e69d  jnz     short loc_14007E6A4
0x14007e69f  test    r8b, r8b
0x14007e6a2  jz      short loc_14007E6DD
0x14007e6a4  mov     r9, [rcx+40h]
0x14007e6a8  mov     rcx, [rcx+18h]
0x14007e6ac  mov     [rsp+88h+var_40], rdi
0x14007e6b1  mov     dword ptr [rsp+88h+var_48], edx
0x14007e6b5  lea     rdx, WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids
0x14007e6bc  mov     [rsp+88h+var_50], rdx
0x14007e6c1  mov     dl, sil
0x14007e6c4  mov     [rsp+88h+var_58], 63h ; 'c'
0x14007e6cb  mov     [rsp+88h+var_60], 13h
0x14007e6d3  mov     [rsp+88h+var_68], 2
0x14007e6d8  call    WPP_RECORDER_AND_TRACE_SF_Dq
0x14007e6dd  mov     ebx, 0C0000184h
0x14007e6e2  jmp     loc_14007E78D
0x14007e6e7  mov     rcx, rdi; this
0x14007e6ea  call    ??$SendAvdtpBrb@U_BRB_HCI_VS_MSFT_AVDTP_CLOSE@@@A2dpSidebandAudioWdmEndpoint@@AEAAJW4_BRB_TYPE@@@Z; A2dpSidebandAudioWdmEndpoint::SendAvdtpBrb<_BRB_HCI_VS_MSFT_AVDTP_CLOSE>(_BRB_TYPE)
0x14007e6ef  test    eax, eax
0x14007e6f1  jns     short loc_14007E75F
0x14007e6f3  mov     r10, cs:WPP_GLOBAL_Control
0x14007e6fa  cmp     r10, r15
0x14007e6fd  jz      short loc_14007E70E
0x14007e6ff  bt      dword ptr [r10+2Ch], 12h
0x14007e705  jnb     short loc_14007E70E
0x14007e707  cmp     byte ptr [r10+29h], 3
0x14007e70c  jnb     short loc_14007E711
0x14007e70e  xor     sil, sil
0x14007e711  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14007e718  setnz   r8b
0x14007e71c  test    sil, sil
0x14007e71f  jnz     short loc_14007E726
0x14007e721  test    r8b, r8b
0x14007e724  jz      short loc_14007E75F
0x14007e726  mov     r9, [r10+40h]
0x14007e72a  lea     rdx, WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids
0x14007e731  mov     rcx, [r10+18h]
0x14007e735  mov     [rsp+88h+var_40], rdi
0x14007e73a  mov     dword ptr [rsp+88h+var_48], eax
0x14007e73e  mov     [rsp+88h+var_50], rdx
0x14007e743  mov     dl, sil
0x14007e746  mov     [rsp+88h+var_58], 64h ; 'd'
0x14007e74d  mov     [rsp+88h+var_60], 13h
0x14007e755  mov     [rsp+88h+var_68], 3
0x14007e75a  call    WPP_RECORDER_AND_TRACE_SF_dq
0x14007e75f  xor     edx, edx; unsigned __int16
0x14007e761  mov     rcx, rdi; this
0x14007e764  call    ?SetAvdtpOffloadHandle@A2dpSidebandAudioWdmEndpoint@@_A2PAGE@@EAAXG@Z; A2dpSidebandAudioWdmEndpoint::SetAvdtpOffloadHandle(ushort)
0x14007e769  mov     rdx, [rdi+2A0h]
0x14007e770  mov     qword ptr [rdi+2A0h], 0
0x14007e77b  test    rdx, rdx
0x14007e77e  jz      short loc_14007E785
0x14007e780  call    ??R?$default_delete@VSiopStore@@@utl@@QEBAXPEAVSiopStore@@@Z; utl::default_delete<SiopStore>::operator()(SiopStore *)
0x14007e785  xor     ebx, ebx
0x14007e787  mov     [rdi+320h], ebx
0x14007e78d  lea     rcx, [rsp+88h+arg_8]
0x14007e795  call    ??1?$unique_storage@U?$resource_policy@PEAU_FAST_MUTEX@@$$A6AXPEAU1@@_E$1?release_fast_mutex_with_critical_region@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14007e79a  mov     eax, ebx
0x14007e79c  add     rsp, 58h
0x14007e7a0  pop     r15
0x14007e7a2  pop     r14
0x14007e7a4  pop     r12
0x14007e7a6  pop     rdi
0x14007e7a7  pop     rsi
0x14007e7a8  pop     rbx
0x14007e7a9  retn
```
