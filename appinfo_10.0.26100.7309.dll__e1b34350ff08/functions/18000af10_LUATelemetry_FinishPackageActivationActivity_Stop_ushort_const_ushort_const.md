# LUATelemetry::FinishPackageActivationActivity::Stop(ushort const *,ushort const *)

- ea: `0x18000af10`
- end: `0x18000b2a7`
- name: `?Stop@FinishPackageActivationActivity@LUATelemetry@@QEAAXPEBG0@Z`
- size: `919`
- prototype: `void __fastcall(LUATelemetry::FinishPackageActivationActivity *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x180027d78`

## callees

- `0x180002834`
- `0x18000af10`
- `0x18000cb30`
- `0x180018d70`
- `0x180018da8`
- `0x180018dcc`
- `0x18001fd6c`
- `0x180033a1c`
- `0x180033c0c`
- `0x1800444e0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000b0c6`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000b0c6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000af98`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000af98`

## pseudocode

```c
void __fastcall LUATelemetry::FinishPackageActivationActivity::Stop(
        LUATelemetry::FinishPackageActivationActivity *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  __int64 FailureInfo; // r14
  const struct _tlgProvider_t *v7; // rax
  const struct _tlgProvider_t *v8; // r14
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r9
  const GUID *v12; // rax
  __int64 v13; // r8
  __int64 v14; // rcx
  __int64 v15; // rdx
  bool v16; // zf
  int v17; // edx
  int v18; // ecx
  const struct _tlgProvider_t *v19; // rax
  __int64 v20; // rdx
  __int64 v21; // r9
  __int64 v22; // rcx
  DWORD v23; // eax
  int v24; // eax
  int v25; // r9d
  unsigned int v26; // [rsp+B0h] [rbp-80h] BYREF
  int Result; // [rsp+B4h] [rbp-7Ch] BYREF
  DWORD CurrentThreadId; // [rsp+B8h] [rbp-78h] BYREF
  int v29; // [rsp+BCh] [rbp-74h] BYREF
  int v30; // [rsp+C0h] [rbp-70h] BYREF
  int v31; // [rsp+C4h] [rbp-6Ch] BYREF
  __int64 v32; // [rsp+C8h] [rbp-68h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+D0h] [rbp-60h] BYREF
  const unsigned __int16 *v34; // [rsp+E0h] [rbp-50h] BYREF
  const unsigned __int16 *v35; // [rsp+E8h] [rbp-48h] BYREF
  __int64 v36; // [rsp+F0h] [rbp-40h] BYREF
  __int64 v37; // [rsp+F8h] [rbp-38h] BYREF
  __int64 v38; // [rsp+100h] [rbp-30h] BYREF
  __int64 v39; // [rsp+108h] [rbp-28h] BYREF
  __int64 v40; // [rsp+110h] [rbp-20h] BYREF
  __int64 v41; // [rsp+118h] [rbp-18h] BYREF
  __int64 v42; // [rsp+120h] [rbp-10h] BYREF
  __int64 v43; // [rsp+128h] [rbp-8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+130h] [rbp+0h] BYREF
  void *v45; // [rsp+140h] [rbp+10h]
  int v46; // [rsp+148h] [rbp+18h]
  int v47; // [rsp+14Ch] [rbp+1Ch]
  __int64 *v48; // [rsp+150h] [rbp+20h]
  __int64 v49; // [rsp+158h] [rbp+28h]
  int *p_Result; // [rsp+160h] [rbp+30h]
  __int64 v51; // [rsp+168h] [rbp+38h]
  DWORD *p_CurrentThreadId; // [rsp+170h] [rbp+40h]
  __int64 v53; // [rsp+178h] [rbp+48h]
  const unsigned __int16 *v54; // [rsp+180h] [rbp+50h]
  int v55; // [rsp+188h] [rbp+58h]
  int v56; // [rsp+18Ch] [rbp+5Ch]
  const unsigned __int16 *v57; // [rsp+190h] [rbp+60h]
  int v58; // [rsp+198h] [rbp+68h]
  int v59; // [rsp+19Ch] [rbp+6Ch]

  FailureInfo = wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::GetFailureInfo();
  if ( FailureInfo )
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(this);
    v19 = LUATelemetry::Provider();
    if ( *(_DWORD *)v19 > 5u && (unsigned __int8)tlgKeywordOn(v19, 0x200000000000LL) )
    {
      v22 = *(_QWORD *)(FailureInfo + 120);
      v37 = *(_QWORD *)(FailureInfo + 112);
      v29 = *(_DWORD *)(FailureInfo + 104);
      v38 = *(_QWORD *)(FailureInfo + 96);
      v39 = *(_QWORD *)(FailureInfo + 88);
      v30 = *(_DWORD *)(FailureInfo + 80);
      v40 = *(_QWORD *)(FailureInfo + 72);
      v31 = *(_DWORD *)(FailureInfo + 32);
      v41 = *(_QWORD *)(FailureInfo + 24);
      v26 = *(_DWORD *)FailureInfo;
      v42 = *(_QWORD *)(FailureInfo + 128);
      Result = *(_DWORD *)(FailureInfo + 64);
      v43 = *(_QWORD *)(FailureInfo + 56);
      v23 = *(_DWORD *)(FailureInfo + 8);
      v36 = v22;
      CurrentThreadId = v23;
      v34 = a3;
      v35 = a2;
      *(_QWORD *)&EventDescriptor.Id = 0x1000000;
      v32 = 0;
      v24 = wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(
              this,
              v20,
              0,
              v21);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        v25,
        (unsigned int)&unk_180052E0D,
        v24,
        v25,
        (__int64)&v32,
        (__int64)&EventDescriptor,
        (__int64)&CurrentThreadId,
        (__int64)&v43,
        (__int64)&Result,
        (__int64)&v42,
        (__int64)&v26,
        (__int64)&v41,
        (__int64)&v31,
        (__int64)&v40,
        (__int64)&v30,
        (__int64)&v39,
        (__int64)&v38,
        (__int64)&v29,
        (__int64)&v37,
        (__int64)&v36,
        (__int64)&v35,
        (__int64)&v34);
    }
  }
  else
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(this);
    v7 = LUATelemetry::Provider();
    v8 = v7;
    if ( *(_DWORD *)v7 > 5u
      && (*((_QWORD *)v7 + 2) & 0x200000000000LL) != 0
      && (*((_QWORD *)v7 + 3) & 0x200000000000LL) == *((_QWORD *)v7 + 3) )
    {
      CurrentThreadId = GetCurrentThreadId();
      Result = wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::GetResult(this);
      v32 = 0;
      v12 = (const GUID *)wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(
                            v10,
                            v9,
                            0,
                            v11);
      v14 = v13 - 1;
      if ( a3 )
      {
        v15 = v13 - 1;
        do
          v16 = a3[++v15] == (unsigned __int16)v13;
        while ( !v16 );
        v17 = 2 * v15 + 2;
      }
      else
      {
        a3 = &String2;
        v17 = 2;
      }
      v57 = a3;
      v58 = v17;
      v59 = v13;
      if ( a2 )
      {
        do
          v16 = a2[++v14] == (unsigned __int16)v13;
        while ( !v16 );
        v18 = 2 * v14 + 2;
      }
      else
      {
        a2 = &String2;
        v18 = 2;
      }
      v55 = v18;
      p_CurrentThreadId = &CurrentThreadId;
      v56 = v13;
      p_Result = &Result;
      v54 = a2;
      v48 = &v32;
      *(_DWORD *)&EventDescriptor.Level = 517;
      UserData.Ptr = *((_QWORD *)v8 + 1);
      v53 = 4;
      v51 = 4;
      v49 = 8;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 0x200000000000LL;
      UserData.Size = *(unsigned __int16 *)UserData.Ptr;
      v45 = &unk_180051F05;
      UserData.Reserved = 2;
      v46 = 118;
      v47 = 1;
      v26 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(*((_QWORD *)v8 + 4), &EventDescriptor, v12, 0, 7u, &UserData);
    }
  }
  wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(this);
}

```

## disassembly

```asm
0x18000af10  mov     [rsp-8+arg_10], rbx
0x18000af15  mov     [rsp-8+arg_18], rsi
0x18000af1a  push    rbp
0x18000af1b  push    rdi
0x18000af1c  push    r14
0x18000af1e  lea     rbp, [rsp-80h]
0x18000af23  sub     rsp, 1B0h
0x18000af2a  mov     rax, cs:__security_cookie
0x18000af31  xor     rax, rsp
0x18000af34  mov     [rbp+90h+var_20], rax
0x18000af38  mov     rdi, r8
0x18000af3b  mov     rbx, rdx
0x18000af3e  mov     rsi, rcx
0x18000af41  call    ?GetFailureInfo@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAPEBUFailureInfo@2@XZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::GetFailureInfo(void)
0x18000af46  mov     r14, rax
0x18000af49  mov     rcx, rsi
0x18000af4c  test    rax, rax
0x18000af4f  jnz     loc_18000B129
0x18000af55  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18000af5a  call    ?Provider@LUATelemetry@@SAPEBU_tlgProvider_t@@XZ; LUATelemetry::Provider(void)
0x18000af5f  mov     r14, rax
0x18000af62  cmp     dword ptr [rax], 5
0x18000af65  jbe     loc_18000B0DA
0x18000af6b  mov     [rsp+1C0h+arg_8], r15
0x18000af73  mov     r15, 200000000000h
0x18000af7d  test    [rax+10h], r15
0x18000af81  jz      loc_18000B0D2
0x18000af87  mov     rcx, [rax+18h]
0x18000af8b  and     rcx, r15
0x18000af8e  cmp     rcx, [rax+18h]
0x18000af92  jnz     loc_18000B0D2
0x18000af98  call    cs:__imp_GetCurrentThreadId
0x18000af9f  nop     dword ptr [rax+rax+00h]
0x18000afa4  mov     rcx, rsi
0x18000afa7  mov     [rbp+90h+var_108], eax
0x18000afaa  call    ?GetResult@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEBAJXZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::GetResult(void)
0x18000afaf  xor     r8d, r8d
0x18000afb2  mov     [rbp+90h+var_10C], eax
0x18000afb5  mov     [rbp+90h+var_F8], r8
0x18000afb9  call    ?Id@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEBAPEBU_GUID@@XZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(void)
0x18000afbe  lea     rcx, [r8-1]
0x18000afc2  mov     r10, rax
0x18000afc5  test    rdi, rdi
0x18000afc8  jz      loc_18000B107
0x18000afce  mov     rdx, rcx
0x18000afd1  cmp     [rdi+rdx*2+2], r8w
0x18000afd7  lea     rdx, [rdx+1]
0x18000afdb  jnz     short loc_18000AFD1
0x18000afdd  lea     edx, ds:2[rdx*2]
0x18000afe4  mov     [rbp+90h+var_30], rdi
0x18000afe8  mov     [rbp+90h+var_28], edx
0x18000afeb  mov     [rbp+90h+var_24], r8d
0x18000afef  test    rbx, rbx
0x18000aff2  jz      loc_18000B118
0x18000aff8  nop     dword ptr [rax+rax+00000000h]
0x18000b000  cmp     [rbx+rcx*2+2], r8w
0x18000b006  lea     rcx, [rcx+1]
0x18000b00a  jnz     short loc_18000B000
0x18000b00c  lea     ecx, ds:2[rcx*2]
0x18000b013  mov     [rbp+90h+var_38], ecx
0x18000b016  lea     rax, [rbp+90h+var_108]
0x18000b01a  mov     [rbp+90h+var_50], rax
0x18000b01e  lea     rcx, _TraceLoggingMetadata
0x18000b025  mov     [rbp+90h+var_34], r8d
0x18000b029  lea     rax, [rbp+90h+var_10C]
0x18000b02d  mov     [rbp+90h+var_60], rax
0x18000b031  lea     rdx, [rbp+90h+EventDescriptor]; EventDescriptor
0x18000b035  lea     rax, [rbp+90h+var_F8]
0x18000b039  mov     [rbp+90h+var_40], rbx
0x18000b03d  mov     [rbp+90h+var_70], rax
0x18000b041  xor     r9d, r9d; RelatedActivityId
0x18000b044  movzx   eax, cs:word_180051EFB
0x18000b04b  mov     r8, r10; ActivityId
0x18000b04e  mov     dword ptr [rbp+90h+EventDescriptor.Level], eax
0x18000b051  mov     rax, [r14+8]
0x18000b055  mov     [rbp+90h+var_90.Ptr], rax
0x18000b059  mov     [rbp+90h+var_48], 4
0x18000b061  mov     [rbp+90h+var_58], 4
0x18000b069  mov     [rbp+90h+var_68], 8
0x18000b071  mov     dword ptr [rbp+90h+EventDescriptor.Id], 0B000000h
0x18000b078  mov     [rbp+90h+EventDescriptor.Keyword], r15
0x18000b07c  movzx   eax, word ptr [rax]
0x18000b07f  mov     [rbp+90h+var_90.Size], eax
0x18000b082  lea     rax, unk_180051F05
0x18000b089  mov     [rbp+90h+var_80], rax
0x18000b08d  lea     rax, _TraceLoggingMetadataEnd
0x18000b094  sub     eax, ecx
0x18000b096  mov     dword ptr [rbp+90h+var_90.0Ch], 2
0x18000b09d  mov     [rbp+90h+var_78], 76h ; 'v'
0x18000b0a4  mov     [rbp+90h+var_74], 1
0x18000b0ab  mov     [rbp+90h+var_110], eax
0x18000b0ae  mov     eax, [rbp+90h+var_110]
0x18000b0b1  mov     rcx, [r14+20h]; RegHandle
0x18000b0b5  lea     rax, [rbp+90h+var_90]
0x18000b0b9  mov     [rsp+1C0h+UserData], rax; UserData
0x18000b0be  mov     [rsp+1C0h+UserDataCount], 7; UserDataCount
0x18000b0c6  call    cs:__imp_EventWriteTransfer
0x18000b0cd  nop     dword ptr [rax+rax+00h]
0x18000b0d2  mov     r15, [rsp+1C0h+arg_8]
0x18000b0da  mov     rcx, rsi
0x18000b0dd  call    ?IgnoreCurrentThread@?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x18000b0e2  mov     rcx, [rbp+90h+var_20]
0x18000b0e6  xor     rcx, rsp; StackCookie
0x18000b0e9  call    __security_check_cookie
0x18000b0ee  lea     r11, [rsp+1C0h+var_10]
0x18000b0f6  mov     rbx, [r11+30h]
0x18000b0fa  mov     rsi, [r11+38h]
0x18000b0fe  mov     rsp, r11
0x18000b101  pop     r14
0x18000b103  pop     rdi
0x18000b104  pop     rbp
0x18000b105  retn
0x18000b107  lea     rdi, String2
0x18000b10e  mov     edx, 2
0x18000b113  jmp     loc_18000AFE4
0x18000b118  lea     rbx, String2
0x18000b11f  mov     ecx, 2
0x18000b124  jmp     loc_18000B013
0x18000b129  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18000b12e  call    ?Provider@LUATelemetry@@SAPEBU_tlgProvider_t@@XZ; LUATelemetry::Provider(void)
0x18000b133  mov     r9, rax
0x18000b136  cmp     dword ptr [rax], 5
0x18000b139  jbe     short loc_18000B0DA
0x18000b13b  mov     rdx, 200000000000h
0x18000b145  mov     rcx, rax
0x18000b148  call    _tlgKeywordOn
0x18000b14d  test    al, al
0x18000b14f  jz      short loc_18000B0DA
0x18000b151  mov     rax, [r14+70h]
0x18000b155  xor     r8d, r8d
0x18000b158  mov     rcx, [r14+78h]
0x18000b15c  mov     [rbp+90h+var_C8], rax
0x18000b160  mov     eax, [r14+68h]
0x18000b164  mov     [rbp+90h+var_104], eax
0x18000b167  mov     rax, [r14+60h]
0x18000b16b  mov     [rbp+90h+var_C0], rax
0x18000b16f  mov     rax, [r14+58h]
0x18000b173  mov     [rbp+90h+var_B8], rax
0x18000b177  mov     eax, [r14+50h]
0x18000b17b  mov     [rbp+90h+var_100], eax
0x18000b17e  mov     rax, [r14+48h]
0x18000b182  mov     [rbp+90h+var_B0], rax
0x18000b186  mov     eax, [r14+20h]
0x18000b18a  mov     [rbp+90h+var_FC], eax
0x18000b18d  mov     rax, [r14+18h]
0x18000b191  mov     [rbp+90h+var_A8], rax
0x18000b195  mov     eax, [r14]
0x18000b198  mov     [rbp+90h+var_110], eax
0x18000b19b  mov     rax, [r14+80h]
0x18000b1a2  mov     [rbp+90h+var_A0], rax
0x18000b1a6  mov     eax, [r14+40h]
0x18000b1aa  mov     [rbp+90h+var_10C], eax
0x18000b1ad  mov     rax, [r14+38h]
0x18000b1b1  mov     [rbp+90h+var_98], rax
0x18000b1b5  mov     eax, [r14+8]
0x18000b1b9  mov     [rbp+90h+var_D0], rcx
0x18000b1bd  mov     rcx, rsi
0x18000b1c0  mov     [rbp+90h+var_108], eax
0x18000b1c3  mov     [rbp+90h+var_E0], rdi
0x18000b1c7  mov     [rbp+90h+var_D8], rbx
0x18000b1cb  mov     qword ptr [rbp+90h+EventDescriptor.Id], 1000000h
0x18000b1d3  mov     [rbp+90h+var_F8], r8
0x18000b1d7  call    ?Id@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEBAPEBU_GUID@@XZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(void)
0x18000b1dc  lea     rcx, [rbp+90h+var_E0]
0x18000b1e0  mov     r8, rax
0x18000b1e3  mov     [rsp+1C0h+var_118], rcx
0x18000b1eb  lea     rdx, unk_180052E0D
0x18000b1f2  lea     rcx, [rbp+90h+var_D8]
0x18000b1f6  mov     [rsp+1C0h+var_120], rcx
0x18000b1fe  lea     rcx, [rbp+90h+var_D0]
0x18000b202  mov     [rsp+1C0h+var_128], rcx
0x18000b20a  lea     rcx, [rbp+90h+var_C8]
0x18000b20e  mov     [rsp+1C0h+var_130], rcx
0x18000b216  lea     rcx, [rbp+90h+var_104]
0x18000b21a  mov     [rsp+1C0h+var_138], rcx
0x18000b222  lea     rcx, [rbp+90h+var_C0]
0x18000b226  mov     [rsp+1C0h+var_140], rcx
0x18000b22e  lea     rcx, [rbp+90h+var_B8]
0x18000b232  mov     [rsp+1C0h+var_148], rcx
0x18000b237  lea     rcx, [rbp+90h+var_100]
0x18000b23b  mov     [rsp+1C0h+var_150], rcx
0x18000b240  lea     rcx, [rbp+90h+var_B0]
0x18000b244  mov     [rsp+1C0h+var_158], rcx
0x18000b249  lea     rcx, [rbp+90h+var_FC]
0x18000b24d  mov     [rsp+1C0h+var_160], rcx
0x18000b252  lea     rcx, [rbp+90h+var_A8]
0x18000b256  mov     [rsp+1C0h+var_168], rcx
0x18000b25b  lea     rcx, [rbp+90h+var_110]
0x18000b25f  mov     [rsp+1C0h+var_170], rcx
0x18000b264  lea     rcx, [rbp+90h+var_A0]
0x18000b268  mov     [rsp+1C0h+var_178], rcx
0x18000b26d  lea     rcx, [rbp+90h+var_10C]
0x18000b271  mov     [rsp+1C0h+var_180], rcx
0x18000b276  lea     rcx, [rbp+90h+var_98]
0x18000b27a  mov     [rsp+1C0h+var_188], rcx
0x18000b27f  lea     rcx, [rbp+90h+var_108]
0x18000b283  mov     [rsp+1C0h+var_190], rcx
0x18000b288  lea     rcx, [rbp+90h+EventDescriptor]
0x18000b28c  mov     [rsp+1C0h+UserData], rcx
0x18000b291  lea     rcx, [rbp+90h+var_F8]
0x18000b295  mov     qword ptr [rsp+1C0h+UserDataCount], rcx
0x18000b29a  mov     rcx, r9
0x18000b29d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@4545645666@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18000b2a2  jmp     loc_18000B0DA
```
