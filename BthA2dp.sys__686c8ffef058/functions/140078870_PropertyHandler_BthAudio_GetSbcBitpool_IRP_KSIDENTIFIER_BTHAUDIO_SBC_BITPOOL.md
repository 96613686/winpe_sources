# PropertyHandler_BthAudio_GetSbcBitpool(_IRP *,KSIDENTIFIER *,_BTHAUDIO_SBC_BITPOOL *)

- ea: `0x140078870`
- end: `0x140078a5e`
- name: `?PropertyHandler_BthAudio_GetSbcBitpool@@YAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEAU_BTHAUDIO_SBC_BITPOOL@@@Z`
- size: `494`
- prototype: `__int64 __fastcall(PIRP Irp, struct KSIDENTIFIER *, struct _BTHAUDIO_SBC_BITPOOL *)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x140006410`
- `0x14000e690`
- `0x14001027c`
- `0x140012a5c`
- `0x14001bc08`
- `0x14001bd20`
- `0x1400202b0`
- `0x14005c870`
- `0x140078870`

## import_xrefs

- `ks!KsGetFilterFromIrp` at `0x140078916`
- `ks!KsGetFilterFromIrp` at `0x140078916`

## string_xrefs

- `0x1400789c3`: `No configured SBC codec found`

## pseudocode

```c
__int64 __fastcall PropertyHandler_BthAudio_GetSbcBitpool(
        PIRP Irp,
        struct KSIDENTIFIER *a2,
        struct _BTHAUDIO_SBC_BITPOOL *a3)
{
  struct _BTHAUDIO_SBC_BITPOOL *v3; // rsi
  char v4; // r9
  char v6; // di
  bool v7; // dl
  int v8; // ebx
  PKSFILTER FilterFromIrp; // rax
  int v10; // r8d
  __int64 *v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 *v14; // rdx
  __int64 v16; // [rsp+50h] [rbp-20h] BYREF
  __int16 v17; // [rsp+58h] [rbp-18h]
  __int64 v18; // [rsp+60h] [rbp-10h] BYREF
  utl::_RefCountBase *v19; // [rsp+68h] [rbp-8h]
  int v20; // [rsp+B8h] [rbp+48h] BYREF

  v3 = a3;
  v4 = (char)a2;
  v6 = 1;
  v7 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_qi(
      WPP_GLOBAL_Control->AttachedDevice,
      v7,
      (_DWORD)a3,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      5,
      28,
      (__int64)WPP_6c4f75d1f4a33ce04ed2e3eb893acb24_Traceguids,
      (char)Irp,
      v4);
  }
  v8 = -1073741823;
  FilterFromIrp = KsGetFilterFromIrp(Irp);
  if ( FilterFromIrp )
  {
    if ( v3 )
    {
      if ( FilterFromIrp->Context )
      {
        v11 = (__int64 *)*((_QWORD *)AVFilter::FromKsFilter(FilterFromIrp) + 1);
        if ( v11 )
        {
          v12 = *v11;
          LOBYTE(v16) = 0;
          v17 = 0;
          HIDWORD(v16) = 0;
          A2dpAudioCodecManager::GetConfiguredCodecWithId(v12, &v18, &v16);
          if ( v18 )
          {
            v16 = 0;
            v20 = 0;
            v8 = (*(__int64 (__fastcall **)(__int64, __int64 *, int *))(*(_QWORD *)v18 + 72LL))(v18, &v16, &v20);
            if ( v8 >= 0 )
            {
              v13 = v16;
              v8 = 0;
              *(_BYTE *)v3 = *(_BYTE *)(v16 + 6);
              *((_BYTE *)v3 + 1) = *(_BYTE *)(v13 + 7);
            }
            __1__unique_storage_U__resource_policy_PEAU_AVDTP_CATEGORY_HEADER____A6AXPEAU1___E_1_FreePoolWithTag___pool_helpers_PEAU_AVDTP_CATEGORY_HEADER___0EDEBFEEC__details_wil__SAX0_ZU__integral_constant__K_0A__wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAA_XZ(&v16);
          }
          else
          {
            MicrosoftTelemetryAssertTriggeredMsgKM("No configured SBC codec found");
          }
          if ( v19 )
            utl::_RefCountBase::_DecStrong(v19);
        }
      }
    }
  }
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
    || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
  {
    v6 = 0;
  }
  if ( v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v14 = WPP_6c4f75d1f4a33ce04ed2e3eb893acb24_Traceguids;
    LOBYTE(v14) = v6;
    LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)v14,
      v10,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      5,
      29,
      (__int64)WPP_6c4f75d1f4a33ce04ed2e3eb893acb24_Traceguids,
      v8);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140078870  mov     [rsp-28h+arg_0], rbx
0x140078875  mov     [rsp-28h+arg_8], rsi
0x14007887a  push    rbp
0x14007887b  push    rdi
0x14007887c  push    r12
0x14007887e  push    r13
0x140078880  push    r14
0x140078882  mov     rbp, rsp
0x140078885  sub     rsp, 70h
0x140078889  mov     rsi, r8
0x14007888c  mov     r9, rdx
0x14007888f  mov     r14, rcx
0x140078892  mov     rcx, cs:WPP_GLOBAL_Control
0x140078899  lea     r12, WPP_GLOBAL_Control
0x1400788a0  mov     dil, 1
0x1400788a3  cmp     rcx, r12
0x1400788a6  jz      short loc_1400788BA
0x1400788a8  mov     eax, [rcx+2Ch]
0x1400788ab  test    al, 10h
0x1400788ad  jz      short loc_1400788BA
0x1400788af  cmp     byte ptr [rcx+29h], 4
0x1400788b3  jb      short loc_1400788BA
0x1400788b5  mov     dl, dil
0x1400788b8  jmp     short loc_1400788BC
0x1400788ba  xor     dl, dl
0x1400788bc  lea     r13, WPP_RECORDER_INITIALIZED
0x1400788c3  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400788ca  lea     r10, WPP_6c4f75d1f4a33ce04ed2e3eb893acb24_Traceguids
0x1400788d1  setnz   r8b
0x1400788d5  test    dl, dl
0x1400788d7  jnz     short loc_1400788DE
0x1400788d9  test    r8b, r8b
0x1400788dc  jz      short loc_14007890E
0x1400788de  mov     [rsp+70h+var_28], r9
0x1400788e3  mov     r9, [rcx+40h]
0x1400788e7  mov     rcx, [rcx+18h]
0x1400788eb  mov     [rsp+70h+var_30], r14
0x1400788f0  mov     [rsp+70h+var_38], r10
0x1400788f5  mov     [rsp+70h+var_40], 1Ch
0x1400788fc  mov     [rsp+70h+var_48], 5
0x140078904  mov     [rsp+70h+var_50], 4
0x140078909  call    WPP_RECORDER_AND_TRACE_SF_qi
0x14007890e  mov     rcx, r14; Irp
0x140078911  mov     ebx, 0C0000001h
0x140078916  call    cs:__imp_KsGetFilterFromIrp
0x14007891d  nop     dword ptr [rax+rax+00h]
0x140078922  test    rax, rax
0x140078925  jz      loc_1400789DD
0x14007892b  test    rsi, rsi
0x14007892e  jz      loc_1400789DD
0x140078934  cmp     qword ptr [rax+10h], 0
0x140078939  jz      loc_1400789DD
0x14007893f  mov     rcx, rax; struct _KSFILTER *
0x140078942  call    ?FromKsFilter@AVFilter@@SAPEAV1@PEAU_KSFILTER@@@Z; AVFilter::FromKsFilter(_KSFILTER *)
0x140078947  mov     rcx, [rax+8]
0x14007894b  test    rcx, rcx
0x14007894e  jz      loc_1400789DD
0x140078954  mov     rcx, [rcx]
0x140078957  lea     r8, [rbp+var_20]
0x14007895b  xor     eax, eax
0x14007895d  mov     byte ptr [rbp+var_20], 0
0x140078961  lea     rdx, [rbp+var_10]
0x140078965  mov     [rbp+var_18], ax
0x140078969  mov     dword ptr [rbp+var_20+4], 0
0x140078970  call    ?GetConfiguredCodecWithId@A2dpAudioCodecManager@@QEAA?AV?$shared_ptr@VA2dpAudioCodec@@@utl@@AEBVCodecId@@@Z; A2dpAudioCodecManager::GetConfiguredCodecWithId(CodecId const &)
0x140078975  mov     rcx, [rbp+var_10]
0x140078979  test    rcx, rcx
0x14007897c  jz      short loc_1400789C3
0x14007897e  mov     [rbp+var_20], 0
0x140078986  lea     r8, [rbp+arg_18]
0x14007898a  mov     [rbp+arg_18], 0
0x140078991  lea     rdx, [rbp+var_20]
0x140078995  mov     rax, [rcx]
0x140078998  mov     rax, [rax+48h]
0x14007899c  call    _guard_dispatch_icall
0x1400789a1  mov     ebx, eax
0x1400789a3  test    eax, eax
0x1400789a5  js      short loc_1400789B8
0x1400789a7  mov     rcx, [rbp+var_20]
0x1400789ab  xor     ebx, ebx
0x1400789ad  mov     al, [rcx+6]
0x1400789b0  mov     [rsi], al
0x1400789b2  mov     al, [rcx+7]
0x1400789b5  mov     [rsi+1], al
0x1400789b8  lea     rcx, [rbp+var_20]
0x1400789bc  call    ??1?$unique_storage@U?$resource_policy@PEAU_AVDTP_CATEGORY_HEADER@@$$A6AXPEAU1@@_E$1?FreePoolWithTag@?$pool_helpers@PEAU_AVDTP_CATEGORY_HEADER@@$0EDEBFEEC@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400789c1  jmp     short loc_1400789CF
0x1400789c3  lea     rcx, aNoConfiguredSb; "No configured SBC codec found"
0x1400789ca  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x1400789cf  mov     rcx, [rbp+var_8]; this
0x1400789d3  test    rcx, rcx
0x1400789d6  jz      short loc_1400789DD
0x1400789d8  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1400789dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400789e4  cmp     rcx, r12
0x1400789e7  jz      short loc_1400789F6
0x1400789e9  mov     eax, [rcx+2Ch]
0x1400789ec  test    al, 10h
0x1400789ee  jz      short loc_1400789F6
0x1400789f0  cmp     byte ptr [rcx+29h], 4
0x1400789f4  jnb     short loc_1400789F9
0x1400789f6  xor     dil, dil
0x1400789f9  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140078a00  setnz   r8b
0x140078a04  test    dil, dil
0x140078a07  jnz     short loc_140078A0E
0x140078a09  test    r8b, r8b
0x140078a0c  jz      short loc_140078A42
0x140078a0e  mov     r9, [rcx+40h]
0x140078a12  lea     rdx, WPP_6c4f75d1f4a33ce04ed2e3eb893acb24_Traceguids
0x140078a19  mov     rcx, [rcx+18h]
0x140078a1d  mov     dword ptr [rsp+70h+var_30], ebx
0x140078a21  mov     [rsp+70h+var_38], rdx
0x140078a26  mov     dl, dil
0x140078a29  mov     [rsp+70h+var_40], 1Dh
0x140078a30  mov     [rsp+70h+var_48], 5
0x140078a38  mov     [rsp+70h+var_50], 4
0x140078a3d  call    WPP_RECORDER_AND_TRACE_SF_d
0x140078a42  lea     r11, [rsp+70h+var_s0]
0x140078a47  mov     eax, ebx
0x140078a49  mov     rbx, [r11+30h]
0x140078a4d  mov     rsi, [r11+38h]
0x140078a51  mov     rsp, r11
0x140078a54  pop     r14
0x140078a56  pop     r13
0x140078a58  pop     r12
0x140078a5a  pop     rdi
0x140078a5b  pop     rbp
0x140078a5c  retn
```
