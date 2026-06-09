# BipSystemHamActivityCreate

- ea: `0x180035740`
- end: `0x180035c55`
- name: `BipSystemHamActivityCreate`
- size: `1301`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x180058370`

## callees

- `0x18001222c`
- `0x180035740`
- `0x18009467a`
- `0x1800946a0`

## import_xrefs

- `ntdll!RtlCopySid` at `0x1800359a4`
- `ntdll!RtlCopySid` at `0x1800359a4`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180035906`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180035c23`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180035906`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180035c23`
- `RMCLIENT!HamCloseActivity` at `0x180035a35`
- `RMCLIENT!HamCloseActivity` at `0x180035a35`
- `RMCLIENT!HamCreateActivity` at `0x1800359ff`
- `RMCLIENT!HamCreateActivity` at `0x1800359ff`

## pseudocode

```c
__int64 __fastcall BipSystemHamActivityCreate(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        void *a5,
        struct _BI_PACKAGE_ID *a6,
        unsigned __int16 *a7,
        __int64 *a8)
{
  __int64 *v9; // rsi
  __int64 v11; // rbx
  __int128 v12; // xmm0
  int v13; // eax
  __int64 v14; // r14
  int v15; // ecx
  int v16; // edi
  __int64 v17; // rax
  _WORD *v18; // r9
  unsigned __int16 *v19; // rdx
  __int64 v20; // r10
  PSID v21; // r8
  _WORD *v22; // rcx
  int v23; // edi
  __int64 v24; // r14
  __int64 *v25; // rcx
  int v26; // eax
  int v28; // ebx
  int v30; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v31; // [rsp+34h] [rbp-CCh] BYREF
  PSID SourceSid; // [rsp+38h] [rbp-C8h]
  __int64 v33; // [rsp+40h] [rbp-C0h] BYREF
  struct _BI_PACKAGE_ID *v34; // [rsp+48h] [rbp-B8h] BYREF
  __int64 *v35; // [rsp+50h] [rbp-B0h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v37; // [rsp+68h] [rbp-98h]
  __int128 v38; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v39[464]; // [rsp+80h] [rbp-80h] BYREF
  char DestinationSid[68]; // [rsp+250h] [rbp+150h] BYREF
  int v41; // [rsp+294h] [rbp+194h]
  int v42; // [rsp+298h] [rbp+198h]
  __int64 v43; // [rsp+2A0h] [rbp+1A0h]
  _BYTE v44[400]; // [rsp+2B0h] [rbp+1B0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+440h] [rbp+340h] BYREF
  char *v46; // [rsp+450h] [rbp+350h]
  int v47; // [rsp+458h] [rbp+358h]
  int v48; // [rsp+45Ch] [rbp+35Ch]
  struct _BI_PACKAGE_ID **v49; // [rsp+460h] [rbp+360h]
  __int64 v50; // [rsp+468h] [rbp+368h]
  __int128 *v51; // [rsp+470h] [rbp+370h]
  __int64 v52; // [rsp+478h] [rbp+378h]
  __int64 v53; // [rsp+480h] [rbp+380h]
  __int64 v54; // [rsp+488h] [rbp+388h]
  __int64 **v55; // [rsp+490h] [rbp+390h]
  __int64 v56; // [rsp+498h] [rbp+398h]
  __int64 *v57; // [rsp+4A0h] [rbp+3A0h]
  int v58; // [rsp+4A8h] [rbp+3A8h]
  int v59; // [rsp+4ACh] [rbp+3ACh]
  int *v60; // [rsp+4B0h] [rbp+3B0h]
  __int64 v61; // [rsp+4B8h] [rbp+3B8h]
  __int64 *v62; // [rsp+4C0h] [rbp+3C0h]
  int v63; // [rsp+4C8h] [rbp+3C8h]
  int v64; // [rsp+4CCh] [rbp+3CCh]
  unsigned int *v65; // [rsp+4D0h] [rbp+3D0h]
  __int64 v66; // [rsp+4D8h] [rbp+3D8h]

  v9 = (__int64 *)a7;
  SourceSid = a5;
  v34 = a6;
  v37 = a1;
  v35 = a8;
  v30 = a4;
  memset_0(v39, 0, 0x228u);
  memset_0(v44, 0, 0x188u);
  v11 = -1;
  v33 = -1;
  if ( (unsigned int)dword_1800C3098 > 5 && (qword_1800C30A8 & 2) != 0 && (qword_1800C30B0 & 2) == qword_1800C30B0 )
  {
    v12 = 0;
    if ( a2 )
      v12 = *(_OWORD *)(a2 + 32);
    v38 = v12;
    v51 = &v38;
    v53 = a3;
    v49 = (struct _BI_PACKAGE_ID **)&qword_1800A1850;
    *(_DWORD *)&EventDescriptor.Level = 261;
    UserData.Ptr = (ULONGLONG)off_1800C30A0;
    v54 = 16;
    v52 = 16;
    v50 = 1;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 2;
    UserData.Size = *(unsigned __int16 *)off_1800C30A0;
    v46 = &byte_1800ADA9F;
    UserData.Reserved = 2;
    v47 = 61;
    v48 = 1;
    v31 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 5u, &UserData);
  }
  v13 = *(_DWORD *)(a2 + 400);
  v14 = *(_QWORD *)(a3 + 320);
  if ( v13 )
  {
    LOBYTE(v15) = 1;
    if ( v13 != 2 )
      LOBYTE(v15) = 4;
  }
  else
  {
    v15 = *(_DWORD *)(a2 + 448);
  }
  v16 = 1 << v15;
  memset_0(v39, 0, 0x228u);
  v17 = 2147483646;
  v18 = v39;
  v19 = a7;
  v20 = 232;
  do
  {
    if ( !v17 )
      break;
    if ( !*v19 )
      break;
    *v18++ = *v19++;
    --v17;
    --v20;
  }
  while ( v20 );
  v21 = SourceSid;
  v22 = v18 - 1;
  if ( v20 )
    v22 = v18;
  *v22 = 0;
  RtlCopySid(0x44u, DestinationSid, v21);
  v41 = v30;
  v42 = v16;
  v43 = v14;
  BipSystemHamActivitySetProperties(
    (struct _BI_ACTIVATED_TASK_INSTANCE *)a3,
    SourceSid,
    v34,
    a7,
    (struct _HAM_ACTIVITY_PROPERTIES *)v44);
  v23 = HamCreateActivity(v37, a3, v39, v44, &v33);
  if ( v23 < 0 )
  {
    v24 = -1;
    if ( v33 != -1 )
      HamCloseActivity(v37);
  }
  else
  {
    v24 = v33;
    v23 = 0;
    v33 = -1;
    *v35 = v24;
  }
  if ( (unsigned int)dword_1800C3098 > 4 && (qword_1800C30A8 & 3) != 0 && (qword_1800C30B0 & 3) == qword_1800C30B0 )
  {
    v25 = &BipTraceLoggingNullSid;
    v31 = v23;
    if ( SourceSid )
      v25 = (__int64 *)SourceSid;
    v35 = *(__int64 **)(a3 + 320);
    v34 = (struct _BI_PACKAGE_ID *)v24;
    v65 = &v31;
    v66 = 4;
    v38 = *(_OWORD *)(a2 + 32);
    v26 = *((unsigned __int8 *)v25 + 1);
    v62 = v25;
    v64 = 0;
    v61 = 4;
    v63 = 4 * v26 + 8;
    v60 = &v30;
    if ( a7 )
    {
      while ( a7[++v11] != 0 )
        ;
      v28 = 2 * v11 + 2;
    }
    else
    {
      v9 = &qword_1800A1670;
      v28 = 2;
    }
    v59 = 0;
    v55 = &v35;
    v57 = v9;
    v51 = &v38;
    v58 = v28;
    v49 = &v34;
    *(_DWORD *)&EventDescriptor.Level = 516;
    UserData.Ptr = (ULONGLONG)off_1800C30A0;
    v56 = 8;
    v53 = a3;
    v54 = 16;
    v52 = 16;
    v50 = 8;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 3;
    UserData.Size = *(unsigned __int16 *)off_1800C30A0;
    v46 = byte_1800AD57B;
    UserData.Reserved = 2;
    v47 = 113;
    v48 = 1;
    LODWORD(SourceSid) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 0xAu, &UserData);
  }
  return (unsigned int)v23;
}

```

## disassembly

```asm
0x180035740  mov     [rsp-8+arg_8], rbx
0x180035745  push    rbp
0x180035746  push    rsi
0x180035747  push    rdi
0x180035748  push    r12
0x18003574a  push    r13
0x18003574c  push    r14
0x18003574e  push    r15
0x180035750  lea     rbp, [rsp-3F0h]
0x180035758  sub     rsp, 4F0h
0x18003575f  mov     rax, cs:__security_cookie
0x180035766  xor     rax, rsp
0x180035769  mov     [rbp+420h+var_40], rax
0x180035770  mov     rax, [rbp+420h+arg_20]
0x180035777  mov     r13, r8
0x18003577a  mov     rsi, [rbp+420h+arg_30]
0x180035781  mov     r15, rdx
0x180035784  mov     [rsp+520h+SourceSid], rax
0x180035789  xor     edx, edx; Val
0x18003578b  mov     rax, [rbp+420h+arg_28]
0x180035792  mov     r8d, 228h; Size
0x180035798  mov     [rsp+520h+var_4D8], rax
0x18003579d  mov     rax, [rbp+420h+arg_38]
0x1800357a4  mov     [rsp+520h+var_4B8], rcx
0x1800357a9  lea     rcx, [rbp+420h+var_4A0]; void *
0x1800357ad  mov     [rsp+520h+var_4D0], rax
0x1800357b2  mov     [rsp+520h+var_4F0], r9d
0x1800357b7  call    memset_0
0x1800357bc  xor     edx, edx; Val
0x1800357be  lea     rcx, [rbp+420h+var_270]; void *
0x1800357c5  mov     r8d, 188h; Size
0x1800357cb  call    memset_0
0x1800357d0  mov     eax, cs:dword_1800C3098
0x1800357d6  lea     r12, _TraceLoggingMetadataEnd
0x1800357dd  lea     r8, _TraceLoggingMetadata
0x1800357e4  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1800357eb  mov     [rsp+520h+var_4E0], rbx
0x1800357f0  cmp     eax, 5
0x1800357f3  jbe     loc_18003590C
0x1800357f9  mov     rcx, cs:qword_1800C30B0
0x180035800  mov     rax, cs:qword_1800C30A8
0x180035807  test    al, 2
0x180035809  jz      loc_18003590C
0x18003580f  mov     rax, rcx
0x180035812  and     eax, 2
0x180035815  cmp     rax, rcx
0x180035818  jnz     loc_18003590C
0x18003581e  xorps   xmm0, xmm0
0x180035821  test    r15, r15
0x180035824  jz      short loc_18003582B
0x180035826  movups  xmm0, xmmword ptr [r15+20h]
0x18003582b  movdqa  [rsp+520h+var_4B0], xmm0
0x180035831  lea     rax, [rsp+520h+var_4B0]
0x180035836  mov     [rbp+420h+var_B0], rax
0x18003583d  lea     rdx, [rsp+520h+EventDescriptor]; EventDescriptor
0x180035842  lea     rax, qword_1800A1850
0x180035849  mov     [rbp+420h+var_A0], r13
0x180035850  mov     [rbp+420h+var_C0], rax
0x180035857  xor     r9d, r9d; RelatedActivityId
0x18003585a  movzx   eax, cs:word_1800ADA95
0x180035861  mov     dword ptr [rsp+520h+EventDescriptor.Level], eax
0x180035865  mov     rax, cs:off_1800C30A0
0x18003586c  mov     [rbp+420h+var_E0.Ptr], rax
0x180035873  mov     [rbp+420h+var_98], 10h
0x18003587e  mov     [rbp+420h+var_A8], 10h
0x180035889  mov     [rbp+420h+var_B8], 1
0x180035894  mov     dword ptr [rsp+520h+EventDescriptor.Id], 0B000000h
0x18003589c  mov     [rsp+520h+EventDescriptor.Keyword], 2
0x1800358a5  movzx   eax, word ptr [rax]
0x1800358a8  mov     [rbp+420h+var_E0.Size], eax
0x1800358ae  lea     rax, byte_1800ADA9F
0x1800358b5  mov     [rbp+420h+var_D0], rax
0x1800358bc  mov     rax, r12
0x1800358bf  sub     eax, r8d
0x1800358c2  mov     dword ptr [rbp+420h+var_E0.0Ch], 2
0x1800358cc  mov     [rbp+420h+var_C8], 3Dh ; '='
0x1800358d6  xor     r8d, r8d; ActivityId
0x1800358d9  mov     [rbp+420h+var_C4], 1
0x1800358e3  mov     [rsp+520h+var_4EC], eax
0x1800358e7  mov     eax, [rsp+520h+var_4EC]
0x1800358eb  mov     rcx, cs:RegHandle; RegHandle
0x1800358f2  lea     rax, [rbp+420h+var_E0]
0x1800358f9  mov     [rsp+520h+UserData], rax; UserData
0x1800358fe  mov     [rsp+520h+UserDataCount], 5; UserDataCount
0x180035906  call    cs:__imp_EventWriteTransfer
0x18003590c  mov     eax, [r15+190h]
0x180035913  mov     edx, 4
0x180035918  mov     r14, [r13+140h]
0x18003591f  test    eax, eax
0x180035921  jz      short loc_180035930
0x180035923  cmp     eax, 2
0x180035926  mov     ecx, 1
0x18003592b  cmovnz  ecx, edx
0x18003592e  jmp     short loc_180035937
0x180035930  mov     ecx, [r15+1C0h]
0x180035937  mov     edi, 1
0x18003593c  xor     edx, edx; Val
0x18003593e  shl     edi, cl
0x180035940  mov     r8d, 228h; Size
0x180035946  lea     rcx, [rbp+420h+var_4A0]; void *
0x18003594a  call    memset_0
0x18003594f  mov     eax, 7FFFFFFEh
0x180035954  lea     r9, [rbp+420h+var_4A0]
0x180035958  mov     rdx, rsi
0x18003595b  mov     r10d, 0E8h
0x180035961  test    rax, rax
0x180035964  jz      short loc_180035983
0x180035966  movzx   ecx, word ptr [rdx]
0x180035969  test    cx, cx
0x18003596c  jz      short loc_180035983
0x18003596e  mov     [r9], cx
0x180035972  add     rdx, 2
0x180035976  add     r9, 2
0x18003597a  dec     rax
0x18003597d  sub     r10, 1
0x180035981  jnz     short loc_180035961
0x180035983  mov     r8, [rsp+520h+SourceSid]; SourceSid
0x180035988  lea     rcx, [r9-2]
0x18003598c  test    r10, r10
0x18003598f  lea     rdx, [rbp+420h+DestinationSid]; DestinationSid
0x180035996  cmovnz  rcx, r9
0x18003599a  xor     eax, eax
0x18003599c  mov     [rcx], ax
0x18003599f  mov     ecx, 44h ; 'D'; DestinationSidLength
0x1800359a4  call    cs:__imp_RtlCopySid
0x1800359aa  mov     eax, [rsp+520h+var_4F0]
0x1800359ae  mov     r9, rsi; unsigned __int16 *
0x1800359b1  mov     r8, [rsp+520h+var_4D8]; struct _BI_PACKAGE_ID *
0x1800359b6  mov     rcx, r13; struct _BI_ACTIVATED_TASK_INSTANCE *
0x1800359b9  mov     rdx, [rsp+520h+SourceSid]; void *
0x1800359be  mov     [rbp+420h+var_28C], eax
0x1800359c4  lea     rax, [rbp+420h+var_270]
0x1800359cb  mov     qword ptr [rsp+520h+UserDataCount], rax; struct _HAM_ACTIVITY_PROPERTIES *
0x1800359d0  mov     [rbp+420h+var_288], edi
0x1800359d6  mov     [rbp+420h+var_280], r14
0x1800359dd  call    ?BipSystemHamActivitySetProperties@@YAXPEAU_BI_ACTIVATED_TASK_INSTANCE@@PEAXPEAU_BI_PACKAGE_ID@@PEBGPEAU_HAM_ACTIVITY_PROPERTIES@@@Z; BipSystemHamActivitySetProperties(_BI_ACTIVATED_TASK_INSTANCE *,void *,_BI_PACKAGE_ID *,ushort const *,_HAM_ACTIVITY_PROPERTIES *)
0x1800359e2  mov     rcx, [rsp+520h+var_4B8]
0x1800359e7  lea     rax, [rsp+520h+var_4E0]
0x1800359ec  lea     r9, [rbp+420h+var_270]
0x1800359f3  mov     qword ptr [rsp+520h+UserDataCount], rax
0x1800359f8  lea     r8, [rbp+420h+var_4A0]
0x1800359fc  mov     rdx, r13
0x1800359ff  call    cs:__imp_HamCreateActivity
0x180035a05  mov     edi, eax
0x180035a07  test    eax, eax
0x180035a09  js      short loc_180035A23
0x180035a0b  mov     r14, [rsp+520h+var_4E0]
0x180035a10  xor     edx, edx
0x180035a12  mov     rax, [rsp+520h+var_4D0]
0x180035a17  mov     edi, edx
0x180035a19  mov     [rsp+520h+var_4E0], rbx
0x180035a1e  mov     [rax], r14
0x180035a21  jmp     short loc_180035A3D
0x180035a23  mov     rdx, [rsp+520h+var_4E0]
0x180035a28  mov     r14, rbx
0x180035a2b  cmp     rdx, rbx
0x180035a2e  jz      short loc_180035A3B
0x180035a30  mov     rcx, [rsp+520h+var_4B8]
0x180035a35  call    cs:__imp_HamCloseActivity
0x180035a3b  xor     edx, edx
0x180035a3d  mov     eax, cs:dword_1800C3098
0x180035a43  cmp     eax, 4
0x180035a46  jbe     loc_180035C29
0x180035a4c  mov     rcx, cs:qword_1800C30B0
0x180035a53  mov     rax, cs:qword_1800C30A8
0x180035a5a  test    al, 3
0x180035a5c  jz      loc_180035C29
0x180035a62  mov     rax, rcx
0x180035a65  and     eax, 3
0x180035a68  cmp     rax, rcx
0x180035a6b  jnz     loc_180035C29
0x180035a71  mov     rax, [rsp+520h+SourceSid]
0x180035a76  lea     rcx, BipTraceLoggingNullSid
0x180035a7d  test    rax, rax
0x180035a80  mov     [rsp+520h+var_4EC], edi
0x180035a84  cmovnz  rcx, rax
0x180035a88  mov     eax, [rsp+520h+var_4F0]
0x180035a8c  mov     [rsp+520h+var_4F0], eax
0x180035a90  mov     rax, [r13+140h]
0x180035a97  mov     [rsp+520h+var_4D0], rax
0x180035a9c  mov     [rsp+520h+var_4D8], r14
0x180035aa1  lea     rax, [rsp+520h+var_4EC]
0x180035aa6  mov     [rbp+420h+var_50], rax
0x180035aad  mov     [rbp+420h+var_48], 4
0x180035ab8  movups  xmm0, xmmword ptr [r15+20h]
0x180035abd  movups  [rsp+520h+var_4B0], xmm0
0x180035ac2  movzx   eax, byte ptr [rcx+1]
0x180035ac6  mov     [rbp+420h+var_60], rcx
0x180035acd  mov     [rbp+420h+var_54], edx
0x180035ad3  mov     [rbp+420h+var_68], 4
0x180035ade  lea     eax, ds:8[rax*4]
0x180035ae5  mov     [rbp+420h+var_58], eax
0x180035aeb  lea     rax, [rsp+520h+var_4F0]
0x180035af0  mov     [rbp+420h+var_70], rax
0x180035af7  test    rsi, rsi
0x180035afa  jz      short loc_180035B15
0x180035afc  nop     dword ptr [rax+00h]
0x180035b00  cmp     word ptr [rsi+rbx*2+2], 0
0x180035b06  lea     rbx, [rbx+1]
0x180035b0a  jnz     short loc_180035B00
0x180035b0c  lea     ebx, ds:2[rbx*2]
0x180035b13  jmp     short loc_180035B21
0x180035b15  lea     rsi, qword_1800A1670
0x180035b1c  mov     ebx, 2
0x180035b21  mov     [rbp+420h+var_74], edx
0x180035b27  lea     rax, [rsp+520h+var_4D0]
0x180035b2c  mov     [rbp+420h+var_90], rax
0x180035b33  lea     rdx, [rsp+520h+EventDescriptor]; EventDescriptor
0x180035b38  mov     [rbp+420h+var_80], rsi
0x180035b3f  lea     rax, [rsp+520h+var_4B0]
0x180035b44  mov     [rbp+420h+var_B0], rax
0x180035b4b  xor     r9d, r9d; RelatedActivityId
0x180035b4e  lea     rax, [rsp+520h+var_4D8]
0x180035b53  mov     [rbp+420h+var_78], ebx
0x180035b59  mov     [rbp+420h+var_C0], rax
0x180035b60  xor     r8d, r8d; ActivityId
0x180035b63  movzx   eax, cs:word_1800AD571
0x180035b6a  mov     dword ptr [rsp+520h+EventDescriptor.Level], eax
0x180035b6e  mov     rax, cs:off_1800C30A0
0x180035b75  mov     [rbp+420h+var_E0.Ptr], rax
0x180035b7c  mov     [rbp+420h+var_88], 8
0x180035b87  mov     [rbp+420h+var_A0], r13
0x180035b8e  mov     [rbp+420h+var_98], 10h
0x180035b99  mov     [rbp+420h+var_A8], 10h
0x180035ba4  mov     [rbp+420h+var_B8], 8
0x180035baf  mov     dword ptr [rsp+520h+EventDescriptor.Id], 0B000000h
0x180035bb7  mov     [rsp+520h+EventDescriptor.Keyword], 3
0x180035bc0  movzx   eax, word ptr [rax]
0x180035bc3  mov     [rbp+420h+var_E0.Size], eax
0x180035bc9  lea     rax, byte_1800AD57B
0x180035bd0  mov     [rbp+420h+var_D0], rax
0x180035bd7  lea     rax, _TraceLoggingMetadata
0x180035bde  sub     r12d, eax
0x180035be1  mov     dword ptr [rbp+420h+var_E0.0Ch], 2
0x180035beb  mov     [rbp+420h+var_C8], 71h ; 'q'
0x180035bf5  mov     [rbp+420h+var_C4], 1
0x180035bff  mov     dword ptr [rsp+520h+SourceSid], r12d
0x180035c04  mov     eax, dword ptr [rsp+520h+SourceSid]
0x180035c08  mov     rcx, cs:RegHandle; RegHandle
0x180035c0f  lea     rax, [rbp+420h+var_E0]
0x180035c16  mov     [rsp+520h+UserData], rax; UserData
0x180035c1b  mov     [rsp+520h+UserDataCount], 0Ah; UserDataCount
0x180035c23  call    cs:__imp_EventWriteTransfer
0x180035c29  mov     eax, edi
0x180035c2b  mov     rcx, [rbp+420h+var_40]
0x180035c32  xor     rcx, rsp; StackCookie
0x180035c35  call    __security_check_cookie
0x180035c3a  mov     rbx, [rsp+520h+arg_8]
0x180035c42  add     rsp, 4F0h
0x180035c49  pop     r15
0x180035c4b  pop     r14
0x180035c4d  pop     r13
0x180035c4f  pop     r12
0x180035c51  pop     rdi
0x180035c52  pop     rsi
0x180035c53  pop     rbp
0x180035c54  retn
```
