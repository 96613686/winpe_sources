# UbpmpRunConsumerQueuedActions(_UBPM_TRIGGER_CONSUMER_BLOCK *,_UBPM_CONSTRAINT_PRECHECK_INFO *,_UBPM_QUEUED_ACTION_QUEUE_REASON,uchar)

- ea: `0x18000e1b0`
- end: `0x18000e5a8`
- name: `?UbpmpRunConsumerQueuedActions@@YAXPEAU_UBPM_TRIGGER_CONSUMER_BLOCK@@PEAU_UBPM_CONSTRAINT_PRECHECK_INFO@@W4_UBPM_QUEUED_ACTION_QUEUE_REASON@@E@Z`
- size: `1016`
- prototype: `void __high(struct _UBPM_TRIGGER_CONSUMER_BLOCK *, struct _UBPM_CONSTRAINT_PRECHECK_INFO *, enum _UBPM_QUEUED_ACTION_QUEUE_REASON, unsigned __int8)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000e0a8`
- `0x18002e500`

## callees

- `0x1800036d0`
- `0x180003790`
- `0x180005320`
- `0x18000d0d0`
- `0x18000e1b0`
- `0x180035184`
- `0x180040260`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000e35c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000e35c`
- `ntdll!RtlFreeHeap` at `0x18000e407`
- `ntdll!RtlFreeHeap` at `0x18000e42e`
- `ntdll!RtlFreeHeap` at `0x18000e452`
- `ntdll!RtlFreeHeap` at `0x18000e470`
- `ntdll!RtlFreeHeap` at `0x18000e407`
- `ntdll!RtlFreeHeap` at `0x18000e42e`
- `ntdll!RtlFreeHeap` at `0x18000e452`
- `ntdll!RtlFreeHeap` at `0x18000e470`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000e574`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000e574`

## pseudocode

```c
ULONG __fastcall UbpmpRunConsumerQueuedActions(
        __int64 a1,
        struct _UBPM_CONSTRAINT_PRECHECK_INFO *a2,
        unsigned int a3,
        char a4)
{
  PVOID v8; // rbx
  PVOID *v9; // rax
  _QWORD *v10; // rax
  PVOID *v11; // rcx
  PVOID *v12; // rbx
  int v13; // r14d
  PVOID *v14; // rax
  PVOID **v15; // rcx
  PVOID *v16; // rsi
  PVOID *v17; // rdi
  PVOID v18; // rcx
  ULONG v19; // eax
  unsigned __int64 v20; // r8
  PVOID v21; // r8
  PVOID v22; // r8
  PVOID v23; // r8
  ULONG result; // eax
  __int64 v25; // rax
  __int64 *v26; // rcx
  __int64 v27; // rax
  unsigned int v29; // eax
  void *v30; // [rsp+60h] [rbp-69h] BYREF
  PVOID P; // [rsp+68h] [rbp-61h] BYREF
  PVOID *p_P; // [rsp+70h] [rbp-59h]
  int v33; // [rsp+78h] [rbp-51h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+80h] [rbp-49h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+90h] [rbp-39h] BYREF
  __int128 v36; // [rsp+A0h] [rbp-29h]
  __int128 v37; // [rsp+B0h] [rbp-19h]
  __int128 v38; // [rsp+C0h] [rbp-9h]
  PVOID v39; // [rsp+D0h] [rbp+7h]

  p_P = &P;
  P = &P;
  v30 = 0;
  UbpmpDequeueActionInstance(a3, a1, &v30);
  v8 = v30;
  if ( v30 )
  {
    while ( 1 )
    {
      v9 = p_P;
      if ( *p_P != &P )
        goto LABEL_33;
      *((_QWORD *)v8 + 1) = p_P;
      *(_QWORD *)v8 = &P;
      *v9 = v8;
      p_P = (PVOID *)v8;
      if ( !a4 )
        goto LABEL_15;
      v8 = *(PVOID *)(a1 + 256);
      if ( v8 == (PVOID)(a1 + 256) )
        break;
      while ( *((_DWORD *)v8 + 4) != a3 )
      {
        v8 = *(PVOID *)v8;
        if ( v8 == (PVOID)(a1 + 256) )
          goto LABEL_15;
      }
      UbpmQueueConsumerClose(*((void **)v8 + 17));
      v10 = *(_QWORD **)v8;
      if ( *(PVOID *)(*(_QWORD *)v8 + 8LL) != v8 )
        goto LABEL_33;
      v11 = (PVOID *)*((_QWORD *)v8 + 1);
      if ( *v11 != v8 )
        goto LABEL_33;
      *v11 = v10;
      v10[1] = v11;
      *((_QWORD *)v8 + 1) = v8;
      *(_QWORD *)v8 = v8;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          94,
          WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
          *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v8 + 17) + 24LL) + 8LL));
      UbpmTriggerConsumerPublishStateChange(a1);
    }
    v30 = 0;
  }
LABEL_15:
  v12 = (PVOID *)P;
  v13 = 0;
  if ( P != &P )
  {
    while ( 1 )
    {
      v14 = (PVOID *)*v12;
      if ( *((PVOID **)*v12 + 1) != v12 )
        break;
      v15 = (PVOID **)v12[1];
      if ( *v15 != v12 )
        break;
      *v15 = v14;
      v16 = v12;
      v14[1] = v15;
      v12[1] = v12;
      v17 = v12;
      v12 = v14;
      *v16 = v16;
      v18 = v16[7];
      v39 = 0;
      v19 = *((_DWORD *)v16 + 12);
      UserData = 0;
      UserData.Size = v19;
      v36 = 0;
      v37 = 0;
      v38 = 0;
      if ( v18 )
        LODWORD(v36) = GetLengthSid(v18);
      else
        LODWORD(v36) = 0;
      v20 = (unsigned __int64)v17[5];
      *((_QWORD *)&v36 + 1) = v17[7];
      HIDWORD(UserData.Ptr) = *((_DWORD *)v17 + 30);
      BYTE8(v37) = *((_BYTE *)v17 + 104);
      *(_QWORD *)&v38 = v17[14];
      BYTE8(v38) = *((_BYTE *)v17 + 124);
      v39 = v17[16];
      UbpmpRunConsumerActions(
        (struct _UBPM_TRIGGER_CONSUMER_BLOCK *)v17[17],
        a2,
        v20,
        v20,
        (struct _GUID *)((char *)v16 + 20),
        *((_DWORD *)v17 + 18),
        (unsigned __int64)v17[10],
        *((_DWORD *)v17 + 22),
        *((_DWORD *)v17 + 23),
        (unsigned __int8 *)v17[12],
        (struct _UBPM_TRIGGER_CONSUMER_CONTROL_INFO_IN_1 *)&UserData);
      v21 = v17[14];
      if ( v21 )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v21);
      v22 = v17[16];
      if ( v22 )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v22);
      v23 = v17[12];
      if ( v23 )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v23);
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v16);
      ++v13;
      if ( v12 == &P )
        goto LABEL_28;
    }
LABEL_33:
    __fastfail(3u);
  }
LABEL_28:
  result = dword_18004F0F0;
  if ( (unsigned int)dword_18004F0F0 > 4 )
  {
    v25 = *(_QWORD *)(a1 + 24);
    v33 = v13;
    *((_QWORD *)&v38 + 1) = 4;
    v26 = *(__int64 **)(v25 + 8);
    *(_QWORD *)&v38 = &v33;
    if ( v26 )
    {
      v27 = -1;
      while ( *((_WORD *)v26 + ++v27) != 0 )
        ;
      v29 = 2 * v27 + 2;
    }
    else
    {
      v26 = &qword_1800439C0;
      v29 = 2;
    }
    *((_QWORD *)&v37 + 1) = v29;
    *(_DWORD *)&EventDescriptor.Level = 4;
    UserData.Ptr = (ULONGLONG)off_18004F0F8;
    *(_QWORD *)&v37 = v26;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = *(unsigned __int16 *)off_18004F0F8;
    *(_QWORD *)&v36 = byte_1800462F1;
    UserData.Reserved = 2;
    *((_QWORD *)&v36 + 1) = 0x100000029LL;
    LODWORD(v30) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    return EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, &UserData);
  }
  return result;
}

```

## disassembly

```asm
0x18000e1b0  mov     [rsp-8+arg_10], rbx
0x18000e1b5  push    rbp
0x18000e1b6  push    rsi
0x18000e1b7  push    rdi
0x18000e1b8  push    r12
0x18000e1ba  push    r13
0x18000e1bc  push    r14
0x18000e1be  push    r15
0x18000e1c0  lea     rbp, [rsp-27h]
0x18000e1c5  sub     rsp, 0F0h
0x18000e1cc  mov     rax, cs:__security_cookie
0x18000e1d3  xor     rax, rsp
0x18000e1d6  mov     [rbp+57h+var_40], rax
0x18000e1da  mov     edi, r8d
0x18000e1dd  lea     rax, [rbp+57h+P]
0x18000e1e1  mov     [rbp+57h+var_B0], rax
0x18000e1e5  lea     r8, [rbp+57h+var_C0]
0x18000e1e9  mov     r12, rdx
0x18000e1ec  lea     rax, [rbp+57h+P]
0x18000e1f0  mov     r15, rcx
0x18000e1f3  mov     [rbp+57h+P], rax
0x18000e1f7  mov     rdx, rcx
0x18000e1fa  xor     r13d, r13d
0x18000e1fd  mov     ecx, edi
0x18000e1ff  mov     [rbp+57h+var_C0], r13
0x18000e203  movzx   esi, r9b
0x18000e207  call    ?UbpmpDequeueActionInstance@@YAXW4_UBPM_QUEUED_ACTION_QUEUE_REASON@@PEAU_UBPM_TRIGGER_CONSUMER_BLOCK@@PEAPEAU_UBPM_QUEUED_ACTION_INSTANCE@@@Z; UbpmpDequeueActionInstance(_UBPM_QUEUED_ACTION_QUEUE_REASON,_UBPM_TRIGGER_CONSUMER_BLOCK *,_UBPM_QUEUED_ACTION_INSTANCE * *)
0x18000e20c  mov     rbx, [rbp+57h+var_C0]
0x18000e210  test    rbx, rbx
0x18000e213  jz      loc_18000E2EA
0x18000e219  lea     r14, WPP_GLOBAL_Control
0x18000e220  mov     rax, [rbp+57h+var_B0]
0x18000e224  lea     rcx, [rbp+57h+P]
0x18000e228  cmp     [rax], rcx
0x18000e22b  jnz     loc_18000E4D8
0x18000e231  mov     [rbx+8], rax
0x18000e235  lea     rcx, [rbp+57h+P]
0x18000e239  mov     [rbx], rcx
0x18000e23c  mov     [rax], rbx
0x18000e23f  mov     [rbp+57h+var_B0], rbx
0x18000e243  test    sil, sil
0x18000e246  jz      loc_18000E2EA
0x18000e24c  lea     rax, [r15+100h]
0x18000e253  mov     rbx, [rax]
0x18000e256  cmp     rbx, rax
0x18000e259  jz      loc_18000E2E6
0x18000e25f  nop
0x18000e260  cmp     [rbx+10h], edi
0x18000e263  jz      short loc_18000E26F
0x18000e265  mov     rbx, [rbx]
0x18000e268  cmp     rbx, rax
0x18000e26b  jnz     short loc_18000E260
0x18000e26d  jmp     short loc_18000E2EA
0x18000e26f  mov     rcx, [rbx+88h]; void *
0x18000e276  call    UbpmQueueConsumerClose
0x18000e27b  mov     rax, [rbx]
0x18000e27e  cmp     [rax+8], rbx
0x18000e282  jnz     loc_18000E4D8
0x18000e288  mov     rcx, [rbx+8]
0x18000e28c  cmp     [rcx], rbx
0x18000e28f  jnz     loc_18000E4D8
0x18000e295  mov     [rcx], rax
0x18000e298  mov     [rax+8], rcx
0x18000e29c  mov     [rbx+8], rbx
0x18000e2a0  mov     [rbx], rbx
0x18000e2a3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e2aa  cmp     rcx, r14
0x18000e2ad  jz      short loc_18000E2D9
0x18000e2af  test    byte ptr [rcx+1Ch], 20h
0x18000e2b3  jz      short loc_18000E2D9
0x18000e2b5  mov     rax, [rbx+88h]
0x18000e2bc  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x18000e2c3  mov     rcx, [rcx+10h]
0x18000e2c7  mov     edx, 5Eh ; '^'
0x18000e2cc  mov     r9, [rax+18h]
0x18000e2d0  mov     r9, [r9+8]
0x18000e2d4  call    WPP_SF_S
0x18000e2d9  mov     rcx, r15
0x18000e2dc  call    UbpmTriggerConsumerPublishStateChange
0x18000e2e1  jmp     loc_18000E220
0x18000e2e6  mov     [rbp+57h+var_C0], r13
0x18000e2ea  mov     rbx, [rbp+57h+P]
0x18000e2ee  lea     rax, [rbp+57h+P]
0x18000e2f2  mov     r14d, r13d
0x18000e2f5  cmp     rbx, rax
0x18000e2f8  jz      loc_18000E48C
0x18000e2fe  xchg    ax, ax
0x18000e300  mov     rax, [rbx]
0x18000e303  cmp     [rax+8], rbx
0x18000e307  jnz     loc_18000E4D8
0x18000e30d  mov     rcx, [rbx+8]
0x18000e311  lea     rdx, [rbx+8]
0x18000e315  cmp     [rcx], rbx
0x18000e318  jnz     loc_18000E4D8
0x18000e31e  mov     [rcx], rax
0x18000e321  mov     rsi, rbx
0x18000e324  mov     [rax+8], rcx
0x18000e328  xorps   xmm0, xmm0
0x18000e32b  mov     [rdx], rsi
0x18000e32e  mov     rdi, rbx
0x18000e331  mov     rbx, rax
0x18000e334  xor     eax, eax
0x18000e336  mov     [rsi], rsi
0x18000e339  mov     rcx, [rsi+38h]; pSid
0x18000e33d  mov     [rbp+57h+var_50], rax
0x18000e341  mov     eax, [rsi+30h]
0x18000e344  movups  xmmword ptr [rbp+57h+var_90.Ptr], xmm0
0x18000e348  mov     [rbp+57h+var_90.Size], eax
0x18000e34b  movups  [rbp+57h+var_80], xmm0
0x18000e34f  movups  [rbp+57h+var_70], xmm0
0x18000e353  movups  [rbp+57h+var_60], xmm0
0x18000e357  test    rcx, rcx
0x18000e35a  jz      short loc_18000E36D
0x18000e35c  call    cs:__imp_GetLengthSid
0x18000e363  nop     dword ptr [rax+rax+00h]
0x18000e368  mov     dword ptr [rbp+57h+var_80], eax
0x18000e36b  jmp     short loc_18000E371
0x18000e36d  mov     dword ptr [rbp+57h+var_80], r13d
0x18000e371  mov     rax, [rdi+38h]
0x18000e375  lea     rcx, [rsi+14h]
0x18000e379  mov     r8, [rdi+28h]; unsigned __int64
0x18000e37d  mov     rdx, r12; struct _UBPM_CONSTRAINT_PRECHECK_INFO *
0x18000e380  mov     qword ptr [rbp+57h+var_80+8], rax
0x18000e384  mov     r9, r8; unsigned __int64
0x18000e387  mov     eax, [rdi+78h]
0x18000e38a  mov     dword ptr [rbp+57h+var_90.Ptr+4], eax
0x18000e38d  movzx   eax, byte ptr [rdi+68h]
0x18000e391  mov     byte ptr [rbp+57h+var_70+8], al
0x18000e394  mov     rax, [rdi+70h]
0x18000e398  mov     qword ptr [rbp+57h+var_60], rax
0x18000e39c  movzx   eax, byte ptr [rdi+7Ch]
0x18000e3a0  mov     byte ptr [rbp+57h+var_60+8], al
0x18000e3a3  mov     rax, [rdi+80h]
0x18000e3aa  mov     [rbp+57h+var_50], rax
0x18000e3ae  lea     rax, [rbp+57h+var_90]
0x18000e3b2  mov     [rsp+120h+var_D0], rax; struct _UBPM_TRIGGER_CONSUMER_CONTROL_INFO_IN_1 *
0x18000e3b7  mov     rax, [rdi+60h]
0x18000e3bb  mov     [rsp+120h+var_D8], rax; unsigned __int8 *
0x18000e3c0  mov     eax, [rdi+5Ch]
0x18000e3c3  mov     [rsp+120h+var_E0], eax; unsigned int
0x18000e3c7  mov     eax, [rdi+58h]
0x18000e3ca  mov     [rsp+120h+var_E8], eax; unsigned int
0x18000e3ce  mov     rax, [rdi+50h]
0x18000e3d2  mov     [rsp+120h+var_F0], rax; unsigned __int64
0x18000e3d7  mov     eax, [rdi+48h]
0x18000e3da  mov     dword ptr [rsp+120h+UserData], eax; unsigned int
0x18000e3de  mov     qword ptr [rsp+120h+UserDataCount], rcx; struct _GUID *
0x18000e3e3  mov     rcx, [rdi+88h]; struct _UBPM_TRIGGER_CONSUMER_BLOCK *
0x18000e3ea  call    ?UbpmpRunConsumerActions@@YAKPEAU_UBPM_TRIGGER_CONSUMER_BLOCK@@PEAU_UBPM_CONSTRAINT_PRECHECK_INFO@@_K2PEAU_GUID@@K2KKPEAEPEAU_UBPM_TRIGGER_CONSUMER_CONTROL_INFO_IN_1@@@Z; UbpmpRunConsumerActions(_UBPM_TRIGGER_CONSUMER_BLOCK *,_UBPM_CONSTRAINT_PRECHECK_INFO *,unsigned __int64,unsigned __int64,_GUID *,ulong,unsigned __int64,ulong,ulong,uchar *,_UBPM_TRIGGER_CONSUMER_CONTROL_INFO_IN_1 *)
0x18000e3ef  mov     r8, [rdi+70h]; P
0x18000e3f3  test    r8, r8
0x18000e3f6  jz      short loc_18000E413
0x18000e3f8  mov     rcx, gs:60h
0x18000e401  xor     edx, edx; Flags
0x18000e403  mov     rcx, [rcx+30h]; HeapHandle
0x18000e407  call    cs:__imp_RtlFreeHeap
0x18000e40e  nop     dword ptr [rax+rax+00h]
0x18000e413  mov     r8, [rdi+80h]; P
0x18000e41a  test    r8, r8
0x18000e41d  jz      short loc_18000E43A
0x18000e41f  mov     rcx, gs:60h
0x18000e428  xor     edx, edx; Flags
0x18000e42a  mov     rcx, [rcx+30h]; HeapHandle
0x18000e42e  call    cs:__imp_RtlFreeHeap
0x18000e435  nop     dword ptr [rax+rax+00h]
0x18000e43a  mov     r8, [rdi+60h]; P
0x18000e43e  test    r8, r8
0x18000e441  jz      short loc_18000E45E
0x18000e443  mov     rcx, gs:60h
0x18000e44c  xor     edx, edx; Flags
0x18000e44e  mov     rcx, [rcx+30h]; HeapHandle
0x18000e452  call    cs:__imp_RtlFreeHeap
0x18000e459  nop     dword ptr [rax+rax+00h]
0x18000e45e  mov     rcx, gs:60h
0x18000e467  mov     r8, rsi; P
0x18000e46a  xor     edx, edx; Flags
0x18000e46c  mov     rcx, [rcx+30h]; HeapHandle
0x18000e470  call    cs:__imp_RtlFreeHeap
0x18000e477  nop     dword ptr [rax+rax+00h]
0x18000e47c  lea     rax, [rbp+57h+P]
0x18000e480  inc     r14d
0x18000e483  cmp     rbx, rax
0x18000e486  jnz     loc_18000E300
0x18000e48c  mov     eax, cs:dword_18004F0F0
0x18000e492  cmp     eax, 4
0x18000e495  jbe     loc_18000E580
0x18000e49b  mov     rax, [r15+18h]
0x18000e49f  mov     [rbp+57h+var_A8], r14d
0x18000e4a3  mov     qword ptr [rbp+57h+var_60+8], 4
0x18000e4ab  mov     rcx, [rax+8]
0x18000e4af  lea     rax, [rbp+57h+var_A8]
0x18000e4b3  mov     qword ptr [rbp+57h+var_60], rax
0x18000e4b7  test    rcx, rcx
0x18000e4ba  jz      short loc_18000E4DF
0x18000e4bc  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000e4c3  cmp     [rcx+rax*2+2], r13w
0x18000e4c9  lea     rax, [rax+1]
0x18000e4cd  jnz     short loc_18000E4C3
0x18000e4cf  lea     eax, ds:2[rax*2]
0x18000e4d6  jmp     short loc_18000E4EB
0x18000e4d8  mov     ecx, 3
0x18000e4dd  int     29h; Win8: RtlFailFast(ecx)
0x18000e4df  lea     rcx, qword_1800439C0
0x18000e4e6  mov     eax, 2
0x18000e4eb  mov     dword ptr [rbp+57h+var_70+8], eax
0x18000e4ee  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x18000e4f2  movzx   eax, cs:word_1800462E7
0x18000e4f9  xor     r9d, r9d; RelatedActivityId
0x18000e4fc  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x18000e4ff  xor     r8d, r8d; ActivityId
0x18000e502  mov     rax, cs:off_18004F0F8
0x18000e509  mov     [rbp+57h+var_90.Ptr], rax
0x18000e50d  mov     qword ptr [rbp+57h+var_70], rcx
0x18000e511  lea     rcx, _TraceLoggingMetadata
0x18000e518  mov     dword ptr [rbp+57h+var_70+0Ch], r13d
0x18000e51c  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x18000e523  mov     [rbp+57h+EventDescriptor.Keyword], r13
0x18000e527  movzx   eax, word ptr [rax]
0x18000e52a  mov     [rbp+57h+var_90.Size], eax
0x18000e52d  lea     rax, byte_1800462F1
0x18000e534  mov     qword ptr [rbp+57h+var_80], rax
0x18000e538  lea     rax, _TraceLoggingMetadataEnd
0x18000e53f  sub     eax, ecx
0x18000e541  mov     dword ptr [rbp+57h+var_90.0Ch], 2
0x18000e548  mov     dword ptr [rbp+57h+var_80+8], 29h ; ')'
0x18000e54f  mov     dword ptr [rbp+57h+var_80+0Ch], 1
0x18000e556  mov     dword ptr [rbp+57h+var_C0], eax
0x18000e559  mov     eax, dword ptr [rbp+57h+var_C0]
0x18000e55c  mov     rcx, cs:RegHandle; RegHandle
0x18000e563  lea     rax, [rbp+57h+var_90]
0x18000e567  mov     [rsp+120h+UserData], rax; UserData
0x18000e56c  mov     [rsp+120h+UserDataCount], 4; UserDataCount
0x18000e574  call    cs:__imp_EventWriteTransfer
0x18000e57b  nop     dword ptr [rax+rax+00h]
0x18000e580  mov     rcx, [rbp+57h+var_40]
0x18000e584  xor     rcx, rsp; StackCookie
0x18000e587  call    __security_check_cookie
0x18000e58c  mov     rbx, [rsp+120h+arg_10]
0x18000e594  add     rsp, 0F0h
0x18000e59b  pop     r15
0x18000e59d  pop     r14
0x18000e59f  pop     r13
0x18000e5a1  pop     r12
0x18000e5a3  pop     rdi
0x18000e5a4  pop     rsi
0x18000e5a5  pop     rbp
0x18000e5a6  retn
```
