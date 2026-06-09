# BiSrvCreateEvent

- ea: `0x1800317f0`
- end: `0x180031f11`
- name: `BiSrvCreateEvent`
- size: `1825`
- prototype: `__int64 __fastcall(int, int, int, int, void *Source1, __int64, PSID Sid1, __int64, int, __int64, int, __int64)`
- caller_count: `9`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180031150`
- `0x180031300`
- `0x1800315b0`
- `0x18004786c`
- `0x180065324`
- `0x180090e70`
- `0x180090fe0`
- `0x1800927b0`
- `0x180092dd0`

## callees

- `0x1800075f8`
- `0x1800095b0`
- `0x18000b9d0`
- `0x18001027c`
- `0x1800317f0`
- `0x18005f8f0`
- `0x18009467a`
- `0x1800946a0`

## import_xrefs

- `ntdll!RtlWaitOnAddress` at `0x18003198f`
- `ntdll!RtlWaitOnAddress` at `0x18003198f`
- `ntdll!RtlFreeHeap` at `0x180031b21`
- `ntdll!RtlFreeHeap` at `0x180031b31`
- `ntdll!RtlFreeHeap` at `0x180031b21`
- `ntdll!RtlFreeHeap` at `0x180031b31`
- `ntdll!RtlEqualSid` at `0x180031a13`
- `ntdll!RtlEqualSid` at `0x180031a13`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180031958`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180031ee6`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180031958`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180031ee6`

## pseudocode

```c
__int64 __fastcall BiSrvCreateEvent(
        __int64 a1,
        int a2,
        int a3,
        __int64 a4,
        UUID *Source1,
        __int64 *a6,
        __int64 *Sid1,
        __int64 *a8,
        int a9,
        void *a10,
        unsigned int a11,
        __int64 a12)
{
  __int64 *v12; // rdi
  __int64 *v13; // rbx
  __int64 *v14; // r12
  int v15; // r8d
  GUID *v16; // rdx
  __int64 v17; // r14
  int v18; // ecx
  int Event; // esi
  GUID v20; // xmm1
  GUID *v21; // rax
  int v22; // r15d
  struct _BI_WORK_ITEM *v23; // rdx
  GUID v24; // xmm0
  int v25; // eax
  int v26; // eax
  int v28; // r14d
  size_t Size; // [rsp+50h] [rbp-B0h]
  int v31; // [rsp+60h] [rbp-A0h] BYREF
  int v32[2]; // [rsp+68h] [rbp-98h] BYREF
  int v33; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v34; // [rsp+74h] [rbp-8Ch] BYREF
  PVOID P; // [rsp+78h] [rbp-88h]
  int v36[2]; // [rsp+80h] [rbp-80h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+88h] [rbp-78h] BYREF
  __int64 v38; // [rsp+98h] [rbp-68h] BYREF
  __int64 v39; // [rsp+A0h] [rbp-60h]
  void *Src; // [rsp+A8h] [rbp-58h]
  GUID v41; // [rsp+B0h] [rbp-50h] BYREF
  GUID v42; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v43[400]; // [rsp+D0h] [rbp-30h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+260h] [rbp+160h] BYREF
  __int16 *v45; // [rsp+270h] [rbp+170h]
  int v46; // [rsp+278h] [rbp+178h]
  int v47; // [rsp+27Ch] [rbp+17Ch]
  struct _EVENT_DATA_DESCRIPTOR v48; // [rsp+280h] [rbp+180h] BYREF
  int *v49; // [rsp+290h] [rbp+190h]
  int v50; // [rsp+298h] [rbp+198h]
  int v51; // [rsp+29Ch] [rbp+19Ch]
  GUID *v52; // [rsp+2A0h] [rbp+1A0h]
  __int64 v53; // [rsp+2A8h] [rbp+1A8h]
  __int64 *v54; // [rsp+2B0h] [rbp+1B0h]
  int v55; // [rsp+2B8h] [rbp+1B8h]
  int v56; // [rsp+2BCh] [rbp+1BCh]
  __int64 *v57; // [rsp+2C0h] [rbp+1C0h]
  int v58; // [rsp+2C8h] [rbp+1C8h]
  int v59; // [rsp+2CCh] [rbp+1CCh]
  __int64 *v60; // [rsp+2D0h] [rbp+1D0h]
  int v61; // [rsp+2D8h] [rbp+1D8h]
  int v62; // [rsp+2DCh] [rbp+1DCh]
  GUID *v63; // [rsp+2E0h] [rbp+1E0h]
  __int64 v64; // [rsp+2E8h] [rbp+1E8h]
  int *v65; // [rsp+2F0h] [rbp+1F0h]
  __int64 v66; // [rsp+2F8h] [rbp+1F8h]
  int *v67; // [rsp+300h] [rbp+200h]
  __int64 v68; // [rsp+308h] [rbp+208h]
  int *v69; // [rsp+310h] [rbp+210h]
  __int64 v70; // [rsp+318h] [rbp+218h]
  int *v71; // [rsp+320h] [rbp+220h]
  __int64 v72; // [rsp+328h] [rbp+228h]
  unsigned int *v73; // [rsp+330h] [rbp+230h]
  __int64 v74; // [rsp+338h] [rbp+238h]

  v12 = a8;
  v13 = Sid1;
  v14 = a6;
  v39 = a12;
  v31 = a3;
  v33 = a2;
  *(_QWORD *)v36 = a1;
  P = 0;
  v38 = 0;
  *(_QWORD *)v32 = a4;
  Src = a10;
  v41 = 0;
  v42 = 0;
  memset_0(v43, 0, 0x182u);
  if ( (unsigned int)dword_1800C3098 > 5 && (qword_1800C30A8 & 2) != 0 && (qword_1800C30B0 & 2) == qword_1800C30B0 )
  {
    *(_DWORD *)&EventDescriptor.Level = 261;
    UserData.Ptr = (ULONGLONG)off_1800C30A0;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 2;
    UserData.Size = *(unsigned __int16 *)off_1800C30A0;
    v45 = &word_1800B430E;
    UserData.Reserved = 2;
    v46 = 19;
    v47 = 1;
    v34 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 2u, &UserData);
  }
  v15 = v33;
  if ( (v33 & 1) == 0 )
  {
    while ( 1 )
    {
      v34 = dword_1800C4340;
      if ( (unsigned int)dword_1800C4340 > 1 )
        break;
      RtlWaitOnAddress(&dword_1800C4340, &v34, 4, 0);
    }
    v15 = v33;
  }
  v16 = *(GUID **)v36;
  v17 = -1;
  if ( !*(_QWORD *)v36 )
  {
    v20 = GUID_NULL;
    v18 = 10;
    Event = -1073741811;
    if ( !Sid1 )
      v13 = &BipTraceLoggingNullSid;
    v41 = GUID_NULL;
    if ( !a8 )
      v12 = &BipTraceLoggingNullSid;
    v21 = *(GUID **)v32;
    if ( !*(_QWORD *)v32 )
    {
      v22 = v31;
      goto LABEL_75;
    }
    goto LABEL_73;
  }
  if ( !*(_QWORD *)v32 )
  {
    v24 = GUID_NULL;
    v22 = v31;
    Event = -1073741811;
    v18 = 20;
    if ( !Sid1 )
      v13 = &BipTraceLoggingNullSid;
    v41 = GUID_NULL;
    if ( !a8 )
      v12 = &BipTraceLoggingNullSid;
    goto LABEL_78;
  }
  if ( (v15 & 4) == 0 && !a9 )
  {
    v18 = 30;
    goto LABEL_14;
  }
  if ( a8 && (!Sid1 || !RtlEqualSid(Sid1, &dword_1800C456C)) )
  {
    v20 = GUID_NULL;
    Event = -1073741776;
    v18 = 40;
    if ( !Sid1 )
      v13 = &BipTraceLoggingNullSid;
    v21 = *(GUID **)v32;
    v41 = GUID_NULL;
    goto LABEL_73;
  }
  if ( (v31 & 0xE2000000) != 0 )
  {
    v18 = 50;
LABEL_28:
    v20 = GUID_NULL;
    Event = -1073741811;
    v22 = v31;
    v41 = GUID_NULL;
    goto LABEL_29;
  }
  if ( (((v31 & 0xE0) - 1) & v31 & 0xE0) != 0 )
  {
    v18 = 60;
    goto LABEL_28;
  }
  if ( (v31 & 0x101) == 0x101 )
  {
    v18 = 70;
    goto LABEL_28;
  }
  if ( Source1 )
  {
    if ( (v33 & 1) == 0 )
    {
      v18 = 80;
      goto LABEL_28;
    }
    if ( (int)BipLookupEventByGuid(Source1) >= 0 )
    {
      v23 = (struct _BI_WORK_ITEM *)P;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)P + 7, 0xFFFFFFFF) == 1 )
      {
        if ( *((_DWORD *)v23 + 12) != 1 )
        {
          if ( *((_DWORD *)v23 + 12) == 2 )
            BipWorkItemCheckQueueDestroy(v23);
          else
            RtlFreeHeap(BipHeap, 0, v23);
          v18 = 100;
          goto LABEL_14;
        }
        BipEventQueueDestroy((struct _BI_LOCK *)&qword_1800C4600);
      }
      v18 = 100;
LABEL_14:
      Event = -1073741811;
LABEL_15:
      v20 = GUID_NULL;
      if ( !Sid1 )
        v13 = &BipTraceLoggingNullSid;
      v41 = GUID_NULL;
      if ( !a8 )
        v12 = &BipTraceLoggingNullSid;
      v21 = *(GUID **)v32;
LABEL_73:
      v22 = v31;
      v16 = *(GUID **)v36;
      v15 = v33;
      v41 = *v21;
      goto LABEL_75;
    }
  }
  else if ( (v33 & 1) != 0 )
  {
    v18 = 90;
    goto LABEL_28;
  }
  if ( a10 )
  {
    if ( a11 )
    {
      if ( a11 > 0x2000 )
      {
        v18 = 120;
        goto LABEL_14;
      }
      goto LABEL_58;
    }
LABEL_57:
    v18 = 110;
    goto LABEL_14;
  }
  if ( a11 )
    goto LABEL_57;
LABEL_58:
  Event = BipPackageIdFromOptionalFullName(&v38, v43, a6);
  if ( Event < 0 )
  {
    v18 = 130;
    goto LABEL_15;
  }
  LODWORD(Size) = a11;
  v22 = v31;
  v20 = GUID_NULL;
  Event = BipCreateEvent(
            *(__int64 *)v36,
            v33,
            v31,
            *(_OWORD **)v32,
            Source1,
            (__int64 *)v38,
            Sid1,
            a8,
            a9,
            Src,
            Size,
            (void *)v39);
  v41 = GUID_NULL;
  if ( Event >= 0 )
    v18 = 0;
  else
    v18 = 140;
LABEL_29:
  v16 = *(GUID **)v36;
  v15 = v33;
  if ( !Sid1 )
    v13 = &BipTraceLoggingNullSid;
  if ( !a8 )
    v12 = &BipTraceLoggingNullSid;
  v41 = **(GUID **)v32;
LABEL_75:
  v42 = v20;
  if ( Event >= 0 && v16 )
  {
    v24 = *v16;
LABEL_78:
    v42 = v24;
  }
  if ( (unsigned int)dword_1800C3098 > 4 && (qword_1800C30A8 & 3) != 0 && (qword_1800C30B0 & 3) == qword_1800C30B0 )
  {
    v31 = a9;
    v73 = &v34;
    v71 = &v33;
    v69 = &v31;
    v67 = v36;
    v65 = v32;
    v63 = &v41;
    v34 = v18;
    v33 = Event;
    v36[0] = v22;
    v32[0] = v15;
    v74 = 4;
    v72 = 4;
    v70 = 4;
    v68 = 4;
    v66 = 4;
    v64 = 16;
    v25 = *((unsigned __int8 *)v12 + 1);
    v60 = v12;
    v62 = 0;
    v61 = 4 * v25 + 8;
    v26 = *((unsigned __int8 *)v13 + 1);
    v57 = v13;
    v59 = 0;
    v58 = 4 * v26 + 8;
    if ( a6 )
    {
      while ( *((_WORD *)a6 + ++v17) != 0 )
        ;
      v28 = 2 * v17 + 2;
    }
    else
    {
      v14 = &qword_1800A1670;
      v28 = 2;
    }
    v56 = 0;
    v52 = &v42;
    *(_DWORD *)&EventDescriptor.Level = 516;
    v48.Ptr = (ULONGLONG)off_1800C30A0;
    v54 = v14;
    v55 = v28;
    v53 = 16;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 3;
    v48.Size = *(unsigned __int16 *)off_1800C30A0;
    v49 = &dword_1800B44DC;
    v48.Reserved = 2;
    v50 = 136;
    v51 = 1;
    LODWORD(P) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 0xCu, &v48);
  }
  return (unsigned int)Event;
}

```

## disassembly

```asm
0x1800317f0  push    rbp
0x1800317f2  push    rbx
0x1800317f3  push    rsi
0x1800317f4  push    rdi
0x1800317f5  push    r12
0x1800317f7  push    r13
0x1800317f9  push    r14
0x1800317fb  push    r15
0x1800317fd  lea     rbp, [rsp-258h]
0x180031805  sub     rsp, 358h
0x18003180c  mov     rax, cs:__security_cookie
0x180031813  xor     rax, rsp
0x180031816  mov     [rbp+290h+var_50], rax
0x18003181d  mov     rax, [rbp+290h+arg_58]
0x180031824  xorps   xmm0, xmm0
0x180031827  mov     r15, [rbp+290h+arg_48]
0x18003182e  xorps   xmm1, xmm1
0x180031831  mov     rdi, [rbp+290h+arg_38]
0x180031838  mov     rbx, [rbp+290h+Sid1]
0x18003183f  mov     r13, [rbp+290h+Source1]
0x180031846  mov     r12, [rbp+290h+arg_28]
0x18003184d  mov     [rbp+290h+var_2F0], rax
0x180031851  xor     eax, eax
0x180031853  mov     [rsp+390h+var_330], r8d
0x180031858  mov     r8d, 182h; Size
0x18003185e  mov     [rsp+390h+var_320], edx
0x180031862  xor     edx, edx; Val
0x180031864  mov     qword ptr [rbp+290h+var_310], rcx
0x180031868  lea     rcx, [rbp+290h+var_2C0]; void *
0x18003186c  mov     [rsp+390h+P], rax
0x180031871  mov     [rbp+290h+var_2F8], rax
0x180031875  mov     qword ptr [rsp+390h+var_328], r9
0x18003187a  mov     [rbp+290h+var_2E8], r15
0x18003187e  movups  [rbp+290h+var_2E0], xmm0
0x180031882  movups  [rbp+290h+var_2D0], xmm1
0x180031886  call    memset_0
0x18003188b  mov     eax, cs:dword_1800C3098
0x180031891  lea     rdx, _TraceLoggingMetadata
0x180031898  cmp     eax, 5
0x18003189b  jbe     loc_18003195E
0x1800318a1  mov     rcx, cs:qword_1800C30B0
0x1800318a8  mov     rax, cs:qword_1800C30A8
0x1800318af  test    al, 2
0x1800318b1  jz      loc_18003195E
0x1800318b7  mov     rax, rcx
0x1800318ba  and     eax, 2
0x1800318bd  cmp     rax, rcx
0x1800318c0  jnz     loc_18003195E
0x1800318c6  movzx   eax, cs:word_1800B4304
0x1800318cd  xor     r9d, r9d; RelatedActivityId
0x1800318d0  mov     dword ptr [rbp+290h+EventDescriptor.Level], eax
0x1800318d3  xor     r8d, r8d; ActivityId
0x1800318d6  mov     rax, cs:off_1800C30A0
0x1800318dd  mov     [rbp+290h+var_130.Ptr], rax
0x1800318e4  mov     dword ptr [rbp+290h+EventDescriptor.Id], 0B000000h
0x1800318eb  mov     [rbp+290h+EventDescriptor.Keyword], 2
0x1800318f3  movzx   eax, word ptr [rax]
0x1800318f6  mov     [rbp+290h+var_130.Size], eax
0x1800318fc  lea     rax, word_1800B430E
0x180031903  mov     [rbp+290h+var_120], rax
0x18003190a  lea     rax, _TraceLoggingMetadataEnd
0x180031911  sub     eax, edx
0x180031913  mov     dword ptr [rbp+290h+var_130.0Ch], 2
0x18003191d  mov     [rbp+290h+var_118], 13h
0x180031927  lea     rdx, [rbp+290h+EventDescriptor]; EventDescriptor
0x18003192b  mov     [rbp+290h+var_114], 1
0x180031935  mov     [rsp+390h+var_31C], eax
0x180031939  mov     eax, [rsp+390h+var_31C]
0x18003193d  mov     rcx, cs:RegHandle; RegHandle
0x180031944  lea     rax, [rbp+290h+var_130]
0x18003194b  mov     [rsp+390h+UserData], rax; UserData
0x180031950  mov     [rsp+390h+UserDataCount], 2; UserDataCount
0x180031958  call    cs:__imp_EventWriteTransfer
0x18003195e  mov     r8d, [rsp+390h+var_320]
0x180031963  mov     esi, r8d
0x180031966  and     esi, 1
0x180031969  jnz     short loc_18003199C
0x18003196b  mov     eax, cs:dword_1800C4340
0x180031971  mov     [rsp+390h+var_31C], eax
0x180031975  cmp     eax, 1
0x180031978  ja      short loc_180031997
0x18003197a  xor     r9d, r9d
0x18003197d  lea     rdx, [rsp+390h+var_31C]
0x180031982  mov     r8d, 4
0x180031988  lea     rcx, dword_1800C4340
0x18003198f  call    cs:__imp_RtlWaitOnAddress
0x180031995  jmp     short loc_18003196B
0x180031997  mov     r8d, [rsp+390h+var_320]
0x18003199c  mov     rdx, qword ptr [rbp+290h+var_310]
0x1800319a0  mov     r14, 0FFFFFFFFFFFFFFFFh
0x1800319a7  test    rdx, rdx
0x1800319aa  jz      loc_180031C77
0x1800319b0  cmp     qword ptr [rsp+390h+var_328], 0
0x1800319b6  jz      loc_180031C46
0x1800319bc  test    r8b, 4
0x1800319c0  jnz     short loc_1800319FF
0x1800319c2  cmp     [rbp+290h+arg_40], 0
0x1800319c9  jnz     short loc_1800319FF
0x1800319cb  mov     ecx, 1Eh
0x1800319d0  mov     esi, 0C000000Dh
0x1800319d5  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x1800319dc  lea     rax, BipTraceLoggingNullSid
0x1800319e3  test    rbx, rbx
0x1800319e6  cmovz   rbx, rax
0x1800319ea  test    rdi, rdi
0x1800319ed  movups  [rbp+290h+var_2E0], xmm1
0x1800319f1  cmovz   rdi, rax
0x1800319f5  mov     rax, qword ptr [rsp+390h+var_328]
0x1800319fa  jmp     loc_180031CAB
0x1800319ff  test    rdi, rdi
0x180031a02  jz      short loc_180031A4A
0x180031a04  test    rbx, rbx
0x180031a07  jz      short loc_180031A1D
0x180031a09  lea     rdx, dword_1800C456C; Sid2
0x180031a10  mov     rcx, rbx; Sid1
0x180031a13  call    cs:__imp_RtlEqualSid
0x180031a19  test    al, al
0x180031a1b  jnz     short loc_180031A4A
0x180031a1d  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x180031a24  lea     rax, BipTraceLoggingNullSid
0x180031a2b  test    rbx, rbx
0x180031a2e  mov     esi, 0C0000030h
0x180031a33  mov     ecx, 28h ; '('
0x180031a38  cmovz   rbx, rax
0x180031a3c  mov     rax, qword ptr [rsp+390h+var_328]
0x180031a41  movups  [rbp+290h+var_2E0], xmm1
0x180031a45  jmp     loc_180031CAB
0x180031a4a  mov     edx, [rsp+390h+var_330]
0x180031a4e  test    edx, 0E2000000h
0x180031a54  jz      short loc_180031A9D
0x180031a56  mov     ecx, 32h ; '2'
0x180031a5b  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x180031a62  mov     esi, 0C000000Dh
0x180031a67  lea     rax, BipTraceLoggingNullSid
0x180031a6e  mov     r15d, edx
0x180031a71  movups  [rbp+290h+var_2E0], xmm1
0x180031a75  mov     rdx, qword ptr [rbp+290h+var_310]
0x180031a79  test    rbx, rbx
0x180031a7c  mov     r8d, [rsp+390h+var_320]
0x180031a81  cmovz   rbx, rax
0x180031a85  test    rdi, rdi
0x180031a88  cmovz   rdi, rax
0x180031a8c  mov     rax, qword ptr [rsp+390h+var_328]
0x180031a91  movups  xmm0, xmmword ptr [rax]
0x180031a94  movups  [rbp+290h+var_2E0], xmm0
0x180031a98  jmp     loc_180031CC7
0x180031a9d  mov     ecx, edx
0x180031a9f  and     ecx, 0E0h
0x180031aa5  lea     eax, [rcx-1]
0x180031aa8  test    ecx, eax
0x180031aaa  jz      short loc_180031AB3
0x180031aac  mov     ecx, 3Ch ; '<'
0x180031ab1  jmp     short loc_180031A5B
0x180031ab3  mov     eax, edx
0x180031ab5  and     eax, 101h
0x180031aba  cmp     eax, 101h
0x180031abf  jnz     short loc_180031AC8
0x180031ac1  mov     ecx, 46h ; 'F'
0x180031ac6  jmp     short loc_180031A5B
0x180031ac8  test    r13, r13
0x180031acb  jz      loc_180031B69
0x180031ad1  test    esi, esi
0x180031ad3  jnz     short loc_180031ADF
0x180031ad5  mov     ecx, 50h ; 'P'
0x180031ada  jmp     loc_180031A5B
0x180031adf  lea     rdx, [rsp+390h+P]
0x180031ae4  mov     rcx, r13; Source1
0x180031ae7  call    BipLookupEventByGuid
0x180031aec  test    eax, eax
0x180031aee  js      loc_180031B77
0x180031af4  mov     rdx, [rsp+390h+P]
0x180031af9  mov     eax, r14d
0x180031afc  lock xadd [rdx+1Ch], eax
0x180031b01  cmp     eax, 1
0x180031b04  jnz     short loc_180031B5F
0x180031b06  mov     ecx, [rdx+30h]
0x180031b09  sub     ecx, eax
0x180031b0b  jz      short loc_180031B53
0x180031b0d  sub     ecx, eax
0x180031b0f  jz      short loc_180031B41
0x180031b11  mov     r8, rdx; P
0x180031b14  xor     edx, edx; Flags
0x180031b16  cmp     ecx, eax
0x180031b18  mov     rcx, cs:BipHeap; HeapHandle
0x180031b1f  jz      short loc_180031B31
0x180031b21  call    cs:__imp_RtlFreeHeap
0x180031b27  mov     ecx, 64h ; 'd'
0x180031b2c  jmp     loc_1800319D0
0x180031b31  call    cs:__imp_RtlFreeHeap
0x180031b37  mov     ecx, 64h ; 'd'
0x180031b3c  jmp     loc_1800319D0
0x180031b41  mov     rcx, rdx; struct _BI_WORK_ITEM *
0x180031b44  call    BipWorkItemCheckQueueDestroy
0x180031b49  mov     ecx, 64h ; 'd'
0x180031b4e  jmp     loc_1800319D0
0x180031b53  lea     rcx, qword_1800C4600; struct _BI_LOCK *
0x180031b5a  call    BipEventQueueDestroy
0x180031b5f  mov     ecx, 64h ; 'd'
0x180031b64  jmp     loc_1800319D0
0x180031b69  test    esi, esi
0x180031b6b  jz      short loc_180031B77
0x180031b6d  mov     ecx, 5Ah ; 'Z'
0x180031b72  jmp     loc_180031A5B
0x180031b77  test    r15, r15
0x180031b7a  mov     r15d, dword ptr [rbp+290h+arg_50]
0x180031b81  jz      short loc_180031B9B
0x180031b83  test    r15d, r15d
0x180031b86  jz      short loc_180031BA0
0x180031b88  cmp     r15d, 2000h
0x180031b8f  jbe     short loc_180031BAA
0x180031b91  mov     ecx, 78h ; 'x'
0x180031b96  jmp     loc_1800319D0
0x180031b9b  test    r15d, r15d
0x180031b9e  jz      short loc_180031BAA
0x180031ba0  mov     ecx, 6Eh ; 'n'
0x180031ba5  jmp     loc_1800319D0
0x180031baa  mov     r8, r12
0x180031bad  lea     rdx, [rbp+290h+var_2C0]
0x180031bb1  lea     rcx, [rbp+290h+var_2F8]
0x180031bb5  call    BipPackageIdFromOptionalFullName
0x180031bba  mov     esi, eax
0x180031bbc  test    eax, eax
0x180031bbe  jns     short loc_180031BCA
0x180031bc0  mov     ecx, 82h
0x180031bc5  jmp     loc_1800319D5
0x180031bca  mov     rax, [rbp+290h+var_2F0]
0x180031bce  mov     r9, qword ptr [rsp+390h+var_328]; int
0x180031bd3  mov     edx, [rsp+390h+var_320]; int
0x180031bd7  mov     rcx, qword ptr [rbp+290h+var_310]; int
0x180031bdb  mov     [rsp+390h+var_338], rax; __int64
0x180031be0  mov     rax, [rbp+290h+var_2E8]
0x180031be4  mov     dword ptr [rsp+390h+Size], r15d; Size
0x180031be9  mov     r15d, [rsp+390h+var_330]
0x180031bee  mov     r8d, r15d; int
0x180031bf1  mov     [rsp+390h+Src], rax; Src
0x180031bf6  mov     eax, [rbp+290h+arg_40]
0x180031bfc  mov     [rsp+390h+var_350], eax; int
0x180031c00  mov     rax, [rbp+290h+var_2F8]
0x180031c04  mov     [rsp+390h+var_358], rdi; PSID
0x180031c09  mov     [rsp+390h+Sid], rbx; Sid
0x180031c0e  mov     [rsp+390h+UserData], rax; __int64
0x180031c13  mov     qword ptr [rsp+390h+UserDataCount], r13; __int64
0x180031c18  call    BipCreateEvent
0x180031c1d  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x180031c24  mov     esi, eax
0x180031c26  test    eax, eax
0x180031c28  lea     rax, BipTraceLoggingNullSid
0x180031c2f  movups  [rbp+290h+var_2E0], xmm1
0x180031c33  jns     short loc_180031C3F
0x180031c35  mov     ecx, 8Ch
0x180031c3a  jmp     loc_180031A75
0x180031c3f  xor     ecx, ecx
0x180031c41  jmp     loc_180031A75
0x180031c46  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180031c4d  mov     r15d, [rsp+390h+var_330]
0x180031c52  lea     rax, BipTraceLoggingNullSid
0x180031c59  test    rbx, rbx
0x180031c5c  mov     esi, 0C000000Dh
0x180031c61  mov     ecx, 14h
0x180031c66  cmovz   rbx, rax
0x180031c6a  test    rdi, rdi
0x180031c6d  movups  [rbp+290h+var_2E0], xmm0
0x180031c71  cmovz   rdi, rax
0x180031c75  jmp     short loc_180031CD7
0x180031c77  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x180031c7e  test    rbx, rbx
0x180031c81  lea     rax, BipTraceLoggingNullSid
0x180031c88  mov     ecx, 0Ah
0x180031c8d  mov     esi, 0C000000Dh
0x180031c92  cmovz   rbx, rax
0x180031c96  test    rdi, rdi
0x180031c99  movups  [rbp+290h+var_2E0], xmm1
0x180031c9d  cmovz   rdi, rax
0x180031ca1  mov     rax, qword ptr [rsp+390h+var_328]
0x180031ca6  test    rax, rax
0x180031ca9  jz      short loc_180031CC2
0x180031cab  movups  xmm0, xmmword ptr [rax]
0x180031cae  mov     r15d, [rsp+390h+var_330]
0x180031cb3  mov     rdx, qword ptr [rbp+290h+var_310]
0x180031cb7  mov     r8d, [rsp+390h+var_320]
0x180031cbc  movups  [rbp+290h+var_2E0], xmm0
0x180031cc0  jmp     short loc_180031CC7
0x180031cc2  mov     r15d, [rsp+390h+var_330]
0x180031cc7  movups  [rbp+290h+var_2D0], xmm1
0x180031ccb  test    esi, esi
0x180031ccd  js      short loc_180031CDB
0x180031ccf  test    rdx, rdx
0x180031cd2  jz      short loc_180031CDB
0x180031cd4  movups  xmm0, xmmword ptr [rdx]
0x180031cd7  movups  [rbp+290h+var_2D0], xmm0
0x180031cdb  mov     eax, cs:dword_1800C3098
0x180031ce1  cmp     eax, 4
0x180031ce4  jbe     loc_180031EEC
0x180031cea  mov     rdx, cs:qword_1800C30B0
0x180031cf1  mov     rax, cs:qword_1800C30A8
0x180031cf8  test    al, 3
0x180031cfa  jz      loc_180031EEC
0x180031d00  mov     rax, rdx
0x180031d03  and     eax, 3
0x180031d06  cmp     rax, rdx
  ... truncated ...
```
