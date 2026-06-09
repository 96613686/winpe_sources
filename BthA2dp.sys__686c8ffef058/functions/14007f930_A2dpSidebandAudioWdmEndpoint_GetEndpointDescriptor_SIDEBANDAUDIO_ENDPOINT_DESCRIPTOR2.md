# A2dpSidebandAudioWdmEndpoint::GetEndpointDescriptor(_SIDEBANDAUDIO_ENDPOINT_DESCRIPTOR2 *)

- ea: `0x14007f930`
- end: `0x14007faa6`
- name: `?GetEndpointDescriptor@A2dpSidebandAudioWdmEndpoint@@MEAAJPEAU_SIDEBANDAUDIO_ENDPOINT_DESCRIPTOR2@@@Z`
- size: `374`
- prototype: `int(A2dpSidebandAudioWdmEndpoint *__hidden this, struct _SIDEBANDAUDIO_ENDPOINT_DESCRIPTOR2 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting`

## callees

- `0x140003530`
- `0x1400202e8`
- `0x1400380dc`
- `0x14005ce00`
- `0x14007ea6c`
- `0x14007f930`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14007f9d6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14007f9d6`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14007f9e5`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14007f9e5`

## pseudocode

```c
__int64 __fastcall A2dpSidebandAudioWdmEndpoint::GetEndpointDescriptor(
        struct _FAST_MUTEX *this,
        struct _SIDEBANDAUDIO_ENDPOINT_DESCRIPTOR2 *a2)
{
  struct _SIDEBANDAUDIO_ENDPOINT_DESCRIPTOR2 *v2; // r14
  char v4; // bp
  ULONG *p_OldIrql; // rsi
  int v6; // edx
  int v7; // r8d
  const void **p_Flink; // rbx
  __int16 v9; // dx
  __int64 v10; // r8
  int v12; // [rsp+20h] [rbp-58h]
  int v13; // [rsp+28h] [rbp-50h]
  int v14; // [rsp+30h] [rbp-48h]
  int v15; // [rsp+38h] [rbp-40h]
  struct _FAST_MUTEX *v16; // [rsp+80h] [rbp+8h] BYREF

  v2 = a2;
  v4 = 1;
  LOBYTE(a2) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    p_OldIrql = &this[-1].OldIrql;
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)a2,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      19,
      25,
      (__int64)WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids,
      (_BYTE)this - 8);
  }
  else
  {
    p_OldIrql = &this[-1].OldIrql;
  }
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe(this + 12);
  v16 = this + 12;
  *((_BYTE *)p_OldIrql + 736) = 0;
  __1__unique_storage_U__resource_policy_PEAU_FAST_MUTEX____A6AXPEAU1___E_1_release_fast_mutex_with_critical_region_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAA_XZ(&v16);
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) == 0
    || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
  {
    v4 = 0;
  }
  if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    p_Flink = (const void **)&this[11].Event.Header.WaitListHead.Flink;
    LOBYTE(v6) = v4;
    LOBYTE(v7) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF__guid_q(
      WPP_GLOBAL_Control->AttachedDevice,
      v6,
      v7,
      WPP_GLOBAL_Control->DeviceExtension,
      v12,
      v13,
      v14,
      v15,
      (__int64)&this[11].Event.Header.WaitListHead.Flink->Flink + 4,
      (char)p_OldIrql);
  }
  else
  {
    p_Flink = (const void **)&this[11].Event.Header.WaitListHead.Flink;
  }
  memmove(v2, *p_Flink, LOWORD(this[11].Contention));
  return A2dpSidebandAudioWdmEndpoint::GetAvdtpConfiguration((A2dpSidebandAudioWdmEndpoint *)p_OldIrql, v9, v10);
}

```

## disassembly

```asm
0x14007f930  mov     [rsp+arg_8], rbx
0x14007f935  mov     [rsp+arg_10], rbp
0x14007f93a  push    rsi
0x14007f93b  push    rdi
0x14007f93c  push    r12
0x14007f93e  push    r13
0x14007f940  push    r14
0x14007f942  sub     rsp, 50h
0x14007f946  mov     r14, rdx
0x14007f949  mov     rdi, rcx
0x14007f94c  mov     rcx, cs:WPP_GLOBAL_Control
0x14007f953  lea     r13, WPP_GLOBAL_Control
0x14007f95a  mov     bpl, 1
0x14007f95d  cmp     rcx, r13
0x14007f960  jz      short loc_14007F976
0x14007f962  test    dword ptr [rcx+2Ch], 40000h
0x14007f969  jz      short loc_14007F976
0x14007f96b  cmp     byte ptr [rcx+29h], 4
0x14007f96f  jb      short loc_14007F976
0x14007f971  mov     dl, bpl
0x14007f974  jmp     short loc_14007F978
0x14007f976  xor     dl, dl
0x14007f978  lea     r12, WPP_RECORDER_INITIALIZED
0x14007f97f  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14007f986  setnz   r8b
0x14007f98a  test    dl, dl
0x14007f98c  jnz     short loc_14007F999
0x14007f98e  test    r8b, r8b
0x14007f991  jnz     short loc_14007F999
0x14007f993  lea     rsi, [rdi-8]
0x14007f997  jmp     short loc_14007F9CF
0x14007f999  mov     r9, [rcx+40h]
0x14007f99d  lea     rax, WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids
0x14007f9a4  mov     rcx, [rcx+18h]
0x14007f9a8  lea     rsi, [rdi-8]
0x14007f9ac  mov     [rsp+78h+var_38], rsi
0x14007f9b1  mov     [rsp+78h+var_40], rax
0x14007f9b6  mov     [rsp+78h+var_48], 19h
0x14007f9bd  mov     [rsp+78h+var_50], 13h
0x14007f9c5  mov     [rsp+78h+var_58], 4
0x14007f9ca  call    WPP_RECORDER_AND_TRACE_SF_q
0x14007f9cf  lea     rbx, [rdi+2A0h]
0x14007f9d6  call    cs:__imp_KeEnterCriticalRegion
0x14007f9dd  nop     dword ptr [rax+rax+00h]
0x14007f9e2  mov     rcx, rbx; FastMutex
0x14007f9e5  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14007f9ec  nop     dword ptr [rax+rax+00h]
0x14007f9f1  lea     rcx, [rsp+78h+arg_0]
0x14007f9f9  mov     [rsp+78h+arg_0], rbx
0x14007fa01  mov     byte ptr [rsi+2E0h], 0
0x14007fa08  call    ??1?$unique_storage@U?$resource_policy@PEAU_FAST_MUTEX@@$$A6AXPEAU1@@_E$1?release_fast_mutex_with_critical_region@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14007fa0d  mov     rcx, cs:WPP_GLOBAL_Control
0x14007fa14  cmp     rcx, r13
0x14007fa17  jz      short loc_14007FA28
0x14007fa19  test    dword ptr [rcx+2Ch], 40000h
0x14007fa20  jz      short loc_14007FA28
0x14007fa22  cmp     byte ptr [rcx+29h], 4
0x14007fa26  jnb     short loc_14007FA2B
0x14007fa28  xor     bpl, bpl
0x14007fa2b  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14007fa32  setnz   r8b
0x14007fa36  test    bpl, bpl
0x14007fa39  jnz     short loc_14007FA49
0x14007fa3b  test    r8b, r8b
0x14007fa3e  jnz     short loc_14007FA49
0x14007fa40  lea     rbx, [rdi+288h]
0x14007fa47  jmp     short loc_14007FA71
0x14007fa49  mov     r9, [rcx+40h]
0x14007fa4d  lea     rbx, [rdi+288h]
0x14007fa54  mov     rax, [rbx]
0x14007fa57  mov     dl, bpl
0x14007fa5a  mov     rcx, [rcx+18h]
0x14007fa5e  add     rax, 4
0x14007fa62  mov     [rsp+78h+var_30], rsi
0x14007fa67  mov     [rsp+78h+var_38], rax
0x14007fa6c  call    WPP_RECORDER_AND_TRACE_SF__guid_q
0x14007fa71  movzx   r8d, word ptr [rdi+278h]; Size
0x14007fa79  mov     rcx, r14; void *
0x14007fa7c  mov     rdx, [rbx]; Src
0x14007fa7f  call    memmove
0x14007fa84  mov     rcx, rsi; this
0x14007fa87  call    ?GetAvdtpConfiguration@A2dpSidebandAudioWdmEndpoint@@IEAAJXZ; A2dpSidebandAudioWdmEndpoint::GetAvdtpConfiguration(void)
0x14007fa8c  lea     r11, [rsp+78h+var_28]
0x14007fa91  mov     rbx, [r11+38h]
0x14007fa95  mov     rbp, [r11+40h]
0x14007fa99  mov     rsp, r11
0x14007fa9c  pop     r14
0x14007fa9e  pop     r13
0x14007faa0  pop     r12
0x14007faa2  pop     rdi
0x14007faa3  pop     rsi
0x14007faa4  retn
```
