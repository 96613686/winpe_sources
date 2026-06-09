# Broker::SebEvent::SignalSyncEvent(uchar *,uchar const *,ulong,_GUID const *,_BI_ACTIVATION_STATUS *)

- ea: `0x180001730`
- end: `0x180001b3b`
- name: `?SignalSyncEvent@SebEvent@Broker@@QEAAKPEAEPEBEKPEBU_GUID@@PEAW4_BI_ACTIVATION_STATUS@@@Z`
- size: `1035`
- prototype: `unsigned int __fastcall(Broker::SebEvent *__hidden this, unsigned __int8 *, const unsigned __int8 *, unsigned int, const struct _GUID *, enum _BI_ACTIVATION_STATUS *)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800026d0`
- `0x180017cd0`
- `0x18001ecd0`

## callees

- `0x180001730`
- `0x180008c00`
- `0x18001cf50`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180001796`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180001a71`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180001796`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180001a71`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180001873`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180001b13`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180001873`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180001b13`
- `ntdll!RtlWakeAddressAll` at `0x18000186a`
- `ntdll!RtlWakeAddressAll` at `0x180001ac5`
- `ntdll!RtlWakeAddressAll` at `0x180001adb`
- `ntdll!RtlWakeAddressAll` at `0x18000186a`
- `ntdll!RtlWakeAddressAll` at `0x180001ac5`
- `ntdll!RtlWakeAddressAll` at `0x180001adb`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001a54`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001a54`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000179c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001a77`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000179c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001a77`
- `BrokerLib!BrSignalBrokerEvent2Ex` at `0x1800018ab`
- `BrokerLib!BrSignalBrokerEvent2Ex` at `0x1800018ab`

## pseudocode

```c
__int64 __fastcall Broker::SebEvent::SignalSyncEvent(
        Broker::SebEvent *this,
        unsigned __int8 *a2,
        const unsigned __int8 *a3,
        int a4,
        const struct _GUID *a5,
        enum _BI_ACTIVATION_STATUS *a6)
{
  char *v6; // r14
  int v8; // r13d
  _DWORD *v11; // rsi
  char v12; // r12
  unsigned int v13; // edi
  int v14; // eax
  int v15; // eax
  const unsigned __int8 *v16; // r12
  int v17; // r13d
  __int64 v18; // rdx
  _QWORD *v19; // rcx
  int v21; // [rsp+40h] [rbp-C0h] BYREF
  enum _BI_ACTIVATION_STATUS *v22; // [rsp+48h] [rbp-B8h] BYREF
  const unsigned __int8 *v23; // [rsp+50h] [rbp-B0h]
  unsigned int v24; // [rsp+58h] [rbp-A8h] BYREF
  int v25; // [rsp+5Ch] [rbp-A4h] BYREF
  int v26; // [rsp+60h] [rbp-A0h] BYREF
  int v27; // [rsp+64h] [rbp-9Ch] BYREF
  __int64 v28; // [rsp+68h] [rbp-98h] BYREF
  const struct _GUID *v29; // [rsp+70h] [rbp-90h] BYREF
  __int64 v30; // [rsp+78h] [rbp-88h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+80h] [rbp-80h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+90h] [rbp-70h] BYREF
  __int16 *v33; // [rsp+A0h] [rbp-60h]
  int v34; // [rsp+A8h] [rbp-58h]
  int v35; // [rsp+ACh] [rbp-54h]
  __int64 *v36; // [rsp+B0h] [rbp-50h]
  __int64 v37; // [rsp+B8h] [rbp-48h]
  __int64 v38; // [rsp+C0h] [rbp-40h]
  __int64 v39; // [rsp+C8h] [rbp-38h]
  enum _BI_ACTIVATION_STATUS **v40; // [rsp+D0h] [rbp-30h]
  __int64 v41; // [rsp+D8h] [rbp-28h]
  const struct _GUID **v42; // [rsp+E0h] [rbp-20h]
  __int64 v43; // [rsp+E8h] [rbp-18h]
  __int64 *v44; // [rsp+F0h] [rbp-10h]
  __int64 v45; // [rsp+F8h] [rbp-8h]
  int *v46; // [rsp+100h] [rbp+0h]
  __int64 v47; // [rsp+108h] [rbp+8h]
  int *v48; // [rsp+110h] [rbp+10h]
  __int64 v49; // [rsp+118h] [rbp+18h]
  int *v50; // [rsp+120h] [rbp+20h]
  __int64 v51; // [rsp+128h] [rbp+28h]
  unsigned int *v52; // [rsp+130h] [rbp+30h]
  __int64 v53; // [rsp+138h] [rbp+38h]
  int *v54; // [rsp+140h] [rbp+40h]
  __int64 v55; // [rsp+148h] [rbp+48h]

  v6 = (char *)this + 208;
  v29 = a5;
  v8 = a4;
  v22 = a6;
  v28 = *((_QWORD *)this + 24);
  v21 = a4;
  RtlAcquireSRWLockExclusive((char *)this + 208);
  GetCurrentThreadId();
  v11 = (_DWORD *)((char *)this + 132);
  v12 = 1;
  if ( *((_DWORD *)this + 33) != 1 )
  {
    if ( *((_DWORD *)this + 34) && *((_BYTE *)this + 169) )
    {
      v13 = 2;
      v14 = 4096;
    }
    else
    {
      v13 = 1056;
      v14 = 0x2000;
    }
    goto LABEL_20;
  }
  v15 = *((_DWORD *)this + 25);
  if ( v15 )
  {
    if ( *((_BYTE *)this + 168) == *a2 )
    {
      v13 = 0;
      v14 = 12288;
      goto LABEL_20;
    }
    *((_BYTE *)this + 168) = *a2;
    if ( v15 == 2 )
    {
      if ( !*a2 )
      {
        v13 = 0;
        v14 = 0x4000;
        goto LABEL_20;
      }
    }
    else if ( v15 == 3 && *a2 == 1 )
    {
      v13 = 0;
      v14 = 20480;
      goto LABEL_20;
    }
  }
  v23 = 0;
  v16 = 0;
  v17 = 0;
  if ( a3 && *((_DWORD *)this + 30) )
  {
    v23 = a3 + 16;
    v17 = v21 - 16;
    v16 = a3;
  }
  *((_BYTE *)this + 169) = 1;
  *v11 = 2;
  RtlWakeAddressAll((char *)this + 132, 0);
  RtlReleaseSRWLockExclusive(v6);
  v13 = BrSignalBrokerEvent2Ex(*(_QWORD *)(v28 + 136), *((_QWORD *)this + 28), a2, v16, v17, v23, v29);
  if ( !v13 )
  {
    *(_DWORD *)v22 = 3;
    RtlAcquireSRWLockExclusive(v6);
    GetCurrentThreadId();
    v19 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF__guid_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        34,
        &WPP_9df6945760b0344b8172a1c9d53360ec_Traceguids,
        *((_QWORD *)this + 28));
      v19 = WPP_GLOBAL_Control;
    }
    if ( *((_DWORD *)this + 34) )
    {
      *v11 = 3;
      RtlWakeAddressAll((char *)this + 132, v18);
    }
    else
    {
      if ( *v11 == 2 )
      {
        *v11 = 1;
        RtlWakeAddressAll((char *)this + 132, v18);
        v19 = WPP_GLOBAL_Control;
      }
      if ( (*((_BYTE *)v19 + 28) & 0x40) != 0 && *((_BYTE *)v19 + 25) >= 4u )
        WPP_SF__guid_(v19[2], 35, &WPP_9df6945760b0344b8172a1c9d53360ec_Traceguids, *((_QWORD *)this + 28));
    }
    goto LABEL_34;
  }
  v8 = v21;
  v12 = 0;
  *(_DWORD *)v22 = 4;
  v14 = 24576;
LABEL_20:
  if ( (unsigned int)dword_180035050 > 2 )
  {
    v21 = v14;
    v25 = *((_DWORD *)this + 46);
    v27 = *((_DWORD *)this + 43);
    LODWORD(v28) = *((_DWORD *)this + 34);
    LODWORD(v29) = *v11;
    LODWORD(v22) = *((_DWORD *)this + 50);
    v30 = *(_QWORD *)((char *)this + 124);
    v54 = &v21;
    v52 = &v24;
    v50 = &v25;
    v48 = &v26;
    v46 = &v27;
    v44 = &v28;
    v42 = &v29;
    v40 = &v22;
    v38 = *((_QWORD *)this + 28);
    v36 = &v30;
    *(_DWORD *)&EventDescriptor.Level = 2;
    UserData.Ptr = (ULONGLONG)off_180035058;
    EventDescriptor.Keyword = 0;
    v24 = v13;
    v26 = v8;
    v55 = 4;
    v53 = 4;
    v51 = 4;
    v49 = 4;
    v47 = 4;
    v45 = 4;
    v43 = 4;
    v41 = 4;
    v39 = 16;
    v37 = 8;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    UserData.Size = *(unsigned __int16 *)off_180035058;
    v33 = word_18002DFC2;
    UserData.Reserved = 2;
    v34 = 144;
    v35 = 1;
    LODWORD(v23) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 0xCu, &UserData);
  }
  if ( v12 )
LABEL_34:
    RtlReleaseSRWLockExclusive(v6);
  return v13;
}

```

## disassembly

```asm
0x180001730  push    rbp
0x180001732  push    rbx
0x180001733  push    rsi
0x180001734  push    rdi
0x180001735  push    r12
0x180001737  push    r13
0x180001739  push    r14
0x18000173b  push    r15
0x18000173d  lea     rbp, [rsp-68h]
0x180001742  sub     rsp, 168h
0x180001749  mov     rax, cs:__security_cookie
0x180001750  xor     rax, rsp
0x180001753  mov     [rbp+0A0h+var_50], rax
0x180001757  mov     rax, [rbp+0A0h+arg_20]
0x18000175e  lea     r14, [rcx+0D0h]
0x180001765  mov     [rsp+1A0h+var_130], rax
0x18000176a  mov     rbx, rcx
0x18000176d  mov     rax, [rbp+0A0h+arg_28]
0x180001774  mov     r13d, r9d
0x180001777  mov     [rsp+1A0h+var_158], rax
0x18000177c  mov     r15, r8
0x18000177f  mov     rax, [rcx+0C0h]
0x180001786  mov     rdi, rdx
0x180001789  mov     rcx, r14
0x18000178c  mov     [rsp+1A0h+var_138], rax
0x180001791  mov     [rsp+1A0h+var_160], r9d
0x180001796  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000179c  call    cs:__imp_GetCurrentThreadId
0x1800017a2  xor     edx, edx
0x1800017a4  lea     rsi, [rbx+84h]
0x1800017ab  cmp     dword ptr [rsi], 1
0x1800017ae  mov     r12b, 1
0x1800017b1  jz      short loc_1800017E1
0x1800017b3  cmp     [rbx+88h], edx
0x1800017b9  jz      short loc_1800017D2
0x1800017bb  cmp     [rbx+0A9h], dl
0x1800017c1  jz      short loc_1800017D2
0x1800017c3  mov     edi, 2
0x1800017c8  mov     eax, 1000h
0x1800017cd  jmp     loc_1800018D5
0x1800017d2  mov     edi, 420h
0x1800017d7  mov     eax, 2000h
0x1800017dc  jmp     loc_1800018D5
0x1800017e1  mov     eax, [rbx+64h]
0x1800017e4  test    eax, eax
0x1800017e6  jz      short loc_180001830
0x1800017e8  movzx   ecx, byte ptr [rdi]
0x1800017eb  cmp     [rbx+0A8h], cl
0x1800017f1  jnz     short loc_1800017FF
0x1800017f3  mov     edi, edx
0x1800017f5  mov     eax, 3000h
0x1800017fa  jmp     loc_1800018D5
0x1800017ff  mov     [rbx+0A8h], cl
0x180001805  cmp     eax, 2
0x180001808  jnz     short loc_18000181A
0x18000180a  cmp     [rdi], dl
0x18000180c  jnz     short loc_180001830
0x18000180e  mov     edi, edx
0x180001810  mov     eax, 4000h
0x180001815  jmp     loc_1800018D5
0x18000181a  cmp     eax, 3
0x18000181d  jnz     short loc_180001830
0x18000181f  cmp     [rdi], r12b
0x180001822  jnz     short loc_180001830
0x180001824  mov     edi, edx
0x180001826  mov     eax, 5000h
0x18000182b  jmp     loc_1800018D5
0x180001830  mov     [rsp+1A0h+var_150], rdx
0x180001835  mov     r12, rdx
0x180001838  mov     r13d, edx
0x18000183b  test    r15, r15
0x18000183e  jz      short loc_18000185A
0x180001840  cmp     [rbx+78h], edx
0x180001843  jz      short loc_18000185A
0x180001845  mov     r13d, [rsp+1A0h+var_160]
0x18000184a  lea     rax, [r15+10h]
0x18000184e  mov     [rsp+1A0h+var_150], rax
0x180001853  add     r13d, 0FFFFFFF0h
0x180001857  mov     r12, r15
0x18000185a  mov     rcx, rsi
0x18000185d  mov     byte ptr [rbx+0A9h], 1
0x180001864  mov     dword ptr [rsi], 2
0x18000186a  call    cs:__imp_RtlWakeAddressAll
0x180001870  mov     rcx, r14
0x180001873  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180001879  mov     rax, [rsp+1A0h+var_130]
0x18000187e  mov     r9, r12
0x180001881  mov     rcx, [rsp+1A0h+var_138]
0x180001886  mov     r8, rdi
0x180001889  mov     rdx, [rbx+0E0h]
0x180001890  mov     [rsp+1A0h+var_170], rax
0x180001895  mov     rax, [rsp+1A0h+var_150]
0x18000189a  mov     rcx, [rcx+88h]
0x1800018a1  mov     [rsp+1A0h+UserData], rax
0x1800018a6  mov     [rsp+1A0h+UserDataCount], r13d
0x1800018ab  call    cs:__imp_BrSignalBrokerEvent2Ex
0x1800018b1  mov     edi, eax
0x1800018b3  test    eax, eax
0x1800018b5  mov     rax, [rsp+1A0h+var_158]
0x1800018ba  jz      loc_180001A68
0x1800018c0  mov     r13d, [rsp+1A0h+var_160]
0x1800018c5  xor     r12b, r12b
0x1800018c8  mov     dword ptr [rax], 4
0x1800018ce  xor     edx, edx
0x1800018d0  mov     eax, 6000h
0x1800018d5  mov     ecx, cs:dword_180035050
0x1800018db  cmp     ecx, 2
0x1800018de  jbe     loc_180001A5A
0x1800018e4  mov     [rsp+1A0h+var_160], eax
0x1800018e8  lea     rcx, _TraceLoggingMetadata
0x1800018ef  mov     eax, [rbx+0B8h]
0x1800018f5  xor     r9d, r9d; RelatedActivityId
0x1800018f8  mov     [rsp+1A0h+var_144], eax
0x1800018fc  xor     r8d, r8d; ActivityId
0x1800018ff  mov     eax, [rbx+0ACh]
0x180001905  mov     [rsp+1A0h+var_13C], eax
0x180001909  mov     eax, [rbx+88h]
0x18000190f  mov     dword ptr [rsp+1A0h+var_138], eax
0x180001913  mov     eax, [rsi]
0x180001915  mov     dword ptr [rsp+1A0h+var_130], eax
0x180001919  mov     eax, [rbx+0C8h]
0x18000191f  mov     dword ptr [rsp+1A0h+var_158], eax
0x180001923  mov     rax, [rbx+7Ch]
0x180001927  mov     [rsp+1A0h+var_128], rax
0x18000192c  lea     rax, [rsp+1A0h+var_160]
0x180001931  mov     [rbp+0A0h+var_60], rax
0x180001935  lea     rax, [rsp+1A0h+var_148]
0x18000193a  mov     [rbp+0A0h+var_70], rax
0x18000193e  lea     rax, [rsp+1A0h+var_144]
0x180001943  mov     [rbp+0A0h+var_80], rax
0x180001947  lea     rax, [rsp+1A0h+var_140]
0x18000194c  mov     [rbp+0A0h+var_90], rax
0x180001950  lea     rax, [rsp+1A0h+var_13C]
0x180001955  mov     [rbp+0A0h+var_A0], rax
0x180001959  lea     rax, [rsp+1A0h+var_138]
0x18000195e  mov     [rbp+0A0h+var_B0], rax
0x180001962  lea     rax, [rsp+1A0h+var_130]
0x180001967  mov     [rbp+0A0h+var_C0], rax
0x18000196b  lea     rax, [rsp+1A0h+var_158]
0x180001970  mov     [rbp+0A0h+var_D0], rax
0x180001974  mov     rax, [rbx+0E0h]
0x18000197b  mov     [rbp+0A0h+var_E0], rax
0x18000197f  lea     rax, [rsp+1A0h+var_128]
0x180001984  mov     [rbp+0A0h+var_F0], rax
0x180001988  movzx   eax, cs:word_18002DFB8
0x18000198f  mov     dword ptr [rbp+0A0h+EventDescriptor.Level], eax
0x180001992  mov     rax, cs:off_180035058
0x180001999  mov     [rbp+0A0h+var_110.Ptr], rax
0x18000199d  mov     [rbp+0A0h+EventDescriptor.Keyword], rdx
0x1800019a1  lea     rdx, [rbp+0A0h+EventDescriptor]; EventDescriptor
0x1800019a5  mov     [rsp+1A0h+var_148], edi
0x1800019a9  mov     [rsp+1A0h+var_140], r13d
0x1800019ae  mov     [rbp+0A0h+var_58], 4
0x1800019b6  mov     [rbp+0A0h+var_68], 4
0x1800019be  mov     [rbp+0A0h+var_78], 4
0x1800019c6  mov     [rbp+0A0h+var_88], 4
0x1800019ce  mov     [rbp+0A0h+var_98], 4
0x1800019d6  mov     [rbp+0A0h+var_A8], 4
0x1800019de  mov     [rbp+0A0h+var_B8], 4
0x1800019e6  mov     [rbp+0A0h+var_C8], 4
0x1800019ee  mov     [rbp+0A0h+var_D8], 10h
0x1800019f6  mov     [rbp+0A0h+var_E8], 8
0x1800019fe  mov     dword ptr [rbp+0A0h+EventDescriptor.Id], 0B000000h
0x180001a05  movzx   eax, word ptr [rax]
0x180001a08  mov     [rbp+0A0h+var_110.Size], eax
0x180001a0b  lea     rax, word_18002DFC2
0x180001a12  mov     [rbp+0A0h+var_100], rax
0x180001a16  lea     rax, _TraceLoggingMetadataEnd
0x180001a1d  sub     eax, ecx
0x180001a1f  mov     dword ptr [rbp+0A0h+var_110.0Ch], 2
0x180001a26  mov     [rbp+0A0h+var_F8], 90h
0x180001a2d  mov     [rbp+0A0h+var_F4], 1
0x180001a34  mov     dword ptr [rsp+1A0h+var_150], eax
0x180001a38  mov     eax, dword ptr [rsp+1A0h+var_150]
0x180001a3c  mov     rcx, cs:RegHandle; RegHandle
0x180001a43  lea     rax, [rbp+0A0h+var_110]
0x180001a47  mov     [rsp+1A0h+UserData], rax; UserData
0x180001a4c  mov     [rsp+1A0h+UserDataCount], 0Ch; UserDataCount
0x180001a54  call    cs:__imp_EventWriteTransfer
0x180001a5a  test    r12b, r12b
0x180001a5d  jnz     loc_180001B10
0x180001a63  jmp     loc_180001B19
0x180001a68  mov     rcx, r14
0x180001a6b  mov     dword ptr [rax], 3
0x180001a71  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180001a77  call    cs:__imp_GetCurrentThreadId
0x180001a7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180001a84  test    byte ptr [rcx+1Ch], 40h
0x180001a88  jz      short loc_180001AB3
0x180001a8a  cmp     byte ptr [rcx+19h], 4
0x180001a8e  jb      short loc_180001AB3
0x180001a90  mov     r9, [rbx+0E0h]
0x180001a97  lea     r8, WPP_9df6945760b0344b8172a1c9d53360ec_Traceguids
0x180001a9e  mov     rcx, [rcx+10h]
0x180001aa2  mov     edx, 22h ; '"'
0x180001aa7  call    WPP_SF__guid_
0x180001aac  mov     rcx, cs:WPP_GLOBAL_Control
0x180001ab3  cmp     dword ptr [rbx+88h], 0
0x180001aba  jz      short loc_180001ACD
0x180001abc  mov     rcx, rsi
0x180001abf  mov     dword ptr [rsi], 3
0x180001ac5  call    cs:__imp_RtlWakeAddressAll
0x180001acb  jmp     short loc_180001B10
0x180001acd  cmp     dword ptr [rsi], 2
0x180001ad0  jnz     short loc_180001AE8
0x180001ad2  mov     rcx, rsi
0x180001ad5  mov     dword ptr [rsi], 1
0x180001adb  call    cs:__imp_RtlWakeAddressAll
0x180001ae1  mov     rcx, cs:WPP_GLOBAL_Control
0x180001ae8  test    byte ptr [rcx+1Ch], 40h
0x180001aec  jz      short loc_180001B10
0x180001aee  cmp     byte ptr [rcx+19h], 4
0x180001af2  jb      short loc_180001B10
0x180001af4  mov     r9, [rbx+0E0h]
0x180001afb  lea     r8, WPP_9df6945760b0344b8172a1c9d53360ec_Traceguids
0x180001b02  mov     rcx, [rcx+10h]
0x180001b06  mov     edx, 23h ; '#'
0x180001b0b  call    WPP_SF__guid_
0x180001b10  mov     rcx, r14
0x180001b13  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180001b19  mov     eax, edi
0x180001b1b  mov     rcx, [rbp+0A0h+var_50]
0x180001b1f  xor     rcx, rsp; StackCookie
0x180001b22  call    __security_check_cookie
0x180001b27  add     rsp, 168h
0x180001b2e  pop     r15
0x180001b30  pop     r14
0x180001b32  pop     r13
0x180001b34  pop     r12
0x180001b36  pop     rdi
0x180001b37  pop     rsi
0x180001b38  pop     rbx
0x180001b39  pop     rbp
0x180001b3a  retn
```
