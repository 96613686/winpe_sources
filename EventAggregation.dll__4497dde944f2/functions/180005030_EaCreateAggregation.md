# EaCreateAggregation

- ea: `0x180005030`
- end: `0x1800054b7`
- name: `EaCreateAggregation`
- size: `1159`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180001970`
- `0x180002ae0`
- `0x180005030`
- `0x1800072e0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800051d1`
- `ntdll!RtlFreeHeap` at `0x180005223`
- `ntdll!RtlFreeHeap` at `0x180005243`
- `ntdll!RtlFreeHeap` at `0x180005325`
- `ntdll!RtlFreeHeap` at `0x18000537b`
- `ntdll!RtlFreeHeap` at `0x180005397`
- `ntdll!RtlFreeHeap` at `0x1800051d1`
- `ntdll!RtlFreeHeap` at `0x180005223`
- `ntdll!RtlFreeHeap` at `0x180005243`
- `ntdll!RtlFreeHeap` at `0x180005325`
- `ntdll!RtlFreeHeap` at `0x18000537b`
- `ntdll!RtlFreeHeap` at `0x180005397`
- `ntdll!RtlAllocateHeap` at `0x18000513c`
- `ntdll!RtlAllocateHeap` at `0x18000519c`
- `ntdll!RtlAllocateHeap` at `0x18000513c`
- `ntdll!RtlAllocateHeap` at `0x18000519c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180005105`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180005499`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180005105`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180005499`

## pseudocode

```c
__int64 __fastcall EaCreateAggregation(
        __int64 *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        char a7,
        __int64 *a8)
{
  PVOID *Heap; // rax
  PVOID *v13; // rdi
  int Aggregation; // esi
  PVOID v15; // rax
  _OWORD *v16; // rcx
  PVOID *v17; // rbx
  PVOID v18; // rdx
  __int64 v19; // rax
  __int64 v20; // rdx
  PVOID v21; // rdx
  __int64 v22; // rcx
  unsigned int EventDescriptor; // [rsp+48h] [rbp-89h] BYREF
  EVENT_DESCRIPTOR EventDescriptor_8; // [rsp+50h] [rbp-81h] BYREF
  unsigned int v26; // [rsp+60h] [rbp-71h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+68h] [rbp-69h] BYREF
  char *v28; // [rsp+78h] [rbp-59h]
  __int64 v29; // [rsp+80h] [rbp-51h]
  __int64 (__fastcall *v30)(); // [rsp+88h] [rbp-49h]
  struct _EVENT_DATA_DESCRIPTOR v31; // [rsp+98h] [rbp-39h] BYREF
  char *v32; // [rsp+A8h] [rbp-29h]
  int v33; // [rsp+B0h] [rbp-21h]
  int v34; // [rsp+B4h] [rbp-1Dh]
  EVENT_DESCRIPTOR *p_EventDescriptor_8; // [rsp+B8h] [rbp-19h]
  __int64 v36; // [rsp+C0h] [rbp-11h]
  unsigned int *p_EventDescriptor; // [rsp+C8h] [rbp-9h]
  __int64 v38; // [rsp+D0h] [rbp-1h]

  if ( (unsigned int)dword_180012000 > 4 )
  {
    UserData.Ptr = (ULONGLONG)off_180012008;
    *(_QWORD *)&EventDescriptor_8.Id = 0x1040B000000LL;
    EventDescriptor_8.Keyword = 0;
    UserData.Size = *(unsigned __int16 *)off_180012008;
    v28 = byte_18000F6E9;
    UserData.Reserved = 2;
    v29 = 0x100000020LL;
    EventDescriptor = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor_8, 0, 0, 2u, &UserData);
  }
  EventDescriptor_8 = 0;
  if ( !a1 )
  {
    Aggregation = -1073741811;
    goto LABEL_21;
  }
  Heap = (PVOID *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x38u);
  v13 = Heap;
  if ( Heap )
  {
    *(_OWORD *)Heap = *(_OWORD *)a1;
    *((_OWORD *)Heap + 1) = *((_OWORD *)a1 + 1);
    *((_OWORD *)Heap + 2) = *((_OWORD *)a1 + 2);
    Heap[6] = (PVOID)a1[6];
    *Heap = 0;
    Heap[1] = 0;
    if ( *a1 )
    {
      v15 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x28u);
      *v13 = v15;
      v16 = v15;
      if ( !v15 )
      {
        Aggregation = -1073741801;
LABEL_9:
        v17 = 0;
        if ( *v13 )
        {
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *v13);
          *v13 = 0;
        }
        v18 = v13[1];
        if ( v18 )
        {
          UserData.Ptr = 0;
          v28 = 0;
          v29 = 0;
          *(_QWORD *)&UserData.Size = EaiAggregationConditionNextChild;
          v30 = EaiFreeAggregationConditionVisitNode;
          EapTreeTraverse(&UserData, v18);
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v13[1]);
          v13[1] = 0;
        }
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v13);
        goto LABEL_22;
      }
      v19 = *a1;
      *v16 = *(_OWORD *)*a1;
      v16[1] = *(_OWORD *)(v19 + 16);
      *((_QWORD *)v16 + 4) = *(_QWORD *)(v19 + 32);
    }
    v20 = a1[1];
    if ( v20 )
    {
      *(_QWORD *)&EventDescriptor_8.Id = 0;
      UserData.Ptr = (ULONGLONG)&EventDescriptor_8;
      LODWORD(EventDescriptor_8.Keyword) = 0;
      *(_QWORD *)&UserData.Size = EaiAggregationConditionNextChild;
      v30 = EaiDuplicateConditionsVisitNode;
      v28 = 0;
      v29 = 0;
      Aggregation = EapTreeTraverse(&UserData, v20);
      if ( Aggregation < 0 )
        goto LABEL_9;
      v13[1] = *(PVOID *)&EventDescriptor_8.Id;
    }
    v17 = v13;
    Aggregation = EaiCreateAggregation(v13, a2, a3, a4, a5, a6, a7, a8);
    if ( Aggregation >= 0 )
      goto LABEL_28;
    goto LABEL_22;
  }
  Aggregation = -1073741801;
LABEL_21:
  v17 = 0;
LABEL_22:
  if ( v17 )
  {
    if ( *v17 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *v17);
      *v17 = 0;
    }
    v21 = v17[1];
    if ( v21 )
    {
      UserData.Ptr = 0;
      *(_QWORD *)&UserData.Size = EaiAggregationConditionNextChild;
      v28 = 0;
      v30 = EaiFreeAggregationConditionVisitNode;
      v29 = 0;
      EapTreeTraverse(&UserData, v21);
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v17[1]);
      v17[1] = 0;
    }
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v17);
  }
LABEL_28:
  if ( a8 && Aggregation >= 0 )
    v22 = *a8;
  else
    v22 = 0;
  if ( (unsigned int)dword_180012000 > 4 )
  {
    *(_QWORD *)&EventDescriptor_8.Id = v22;
    p_EventDescriptor_8 = &EventDescriptor_8;
    *(_QWORD *)&UserData.Size = 0;
    p_EventDescriptor = &EventDescriptor;
    v31.Ptr = (ULONGLONG)off_180012008;
    v36 = 8;
    EventDescriptor = Aggregation;
    v38 = 4;
    UserData.Ptr = 0x2040B000000LL;
    v31.Size = *(unsigned __int16 *)off_180012008;
    v32 = byte_18000F269;
    v31.Reserved = 2;
    v33 = 54;
    v34 = 1;
    v26 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, (PCEVENT_DESCRIPTOR)&UserData, 0, 0, 4u, &v31);
  }
  return (unsigned int)Aggregation;
}

```

## disassembly

```asm
0x180005030  mov     r11, rsp
0x180005033  push    rbp
0x180005034  push    rsi
0x180005035  lea     rbp, [r11-3Fh]
0x180005039  sub     rsp, 0F8h
0x180005040  mov     rax, cs:__security_cookie
0x180005047  xor     rax, rsp
0x18000504a  mov     [rbp+37h+var_30], rax
0x18000504e  mov     eax, cs:dword_180012000
0x180005054  xor     esi, esi
0x180005056  mov     [r11+8], rbx
0x18000505a  mov     rbx, rcx
0x18000505d  mov     [r11+18h], r12
0x180005061  mov     r12, r8
0x180005064  mov     [r11-18h], r13
0x180005068  mov     r13, rdx
0x18000506b  mov     [r11-20h], r14
0x18000506f  lea     rcx, _TraceLoggingMetadata
0x180005076  mov     r14, [rbp+37h+arg_38]
0x18000507a  mov     [r11-28h], r15
0x18000507e  mov     r15, r9
0x180005081  cmp     eax, 4
0x180005084  jbe     loc_18000510B
0x18000508a  movzx   eax, cs:word_18000F6DF
0x180005091  lea     rdx, [rsp+100h+EventDescriptor.Keyword]; EventDescriptor
0x180005096  mov     dword ptr [rbp+37h+EventDescriptor.Keyword+4], eax
0x180005099  xor     r9d, r9d; RelatedActivityId
0x18000509c  mov     rax, cs:off_180012008
0x1800050a3  xor     r8d, r8d; ActivityId
0x1800050a6  mov     [rbp+37h+var_A0.Ptr], rax
0x1800050aa  mov     dword ptr [rsp+100h+EventDescriptor.Keyword], 0B000000h
0x1800050b2  mov     [rbp+37h+var_B0], rsi
0x1800050b6  movzx   eax, word ptr [rax]
0x1800050b9  mov     [rbp+37h+var_A0.Size], eax
0x1800050bc  lea     rax, byte_18000F6E9
0x1800050c3  mov     [rbp+37h+var_90], rax
0x1800050c7  lea     rax, _TraceLoggingMetadataEnd
0x1800050ce  sub     eax, ecx
0x1800050d0  mov     dword ptr [rbp+37h+var_A0.0Ch], 2
0x1800050d7  mov     dword ptr [rbp+37h+var_88], 20h ; ' '
0x1800050de  mov     dword ptr [rbp+37h+var_88+4], 1
0x1800050e5  mov     dword ptr [rsp+100h+EventDescriptor.Id], eax
0x1800050e9  mov     eax, dword ptr [rsp+100h+EventDescriptor.Id]
0x1800050ed  mov     rcx, cs:RegHandle; RegHandle
0x1800050f4  lea     rax, [rbp+37h+var_A0]
0x1800050f8  mov     [rsp+100h+UserData], rax; UserData
0x1800050fd  mov     [rsp+100h+UserDataCount], 2; UserDataCount
0x180005105  call    cs:__imp_EventWriteTransfer
0x18000510b  mov     [rsp+100h+arg_8], rdi
0x180005113  xorps   xmm0, xmm0
0x180005116  movups  xmmword ptr [rsp+100h+EventDescriptor.Keyword], xmm0
0x18000511b  test    rbx, rbx
0x18000511e  jz      loc_1800052FE
0x180005124  mov     rcx, gs:60h
0x18000512d  mov     edx, 8; Flags
0x180005132  mov     r8d, 38h ; '8'; Size
0x180005138  mov     rcx, [rcx+30h]; HeapHandle
0x18000513c  call    cs:__imp_RtlAllocateHeap
0x180005142  mov     rdi, rax
0x180005145  test    rax, rax
0x180005148  jnz     short loc_180005154
0x18000514a  mov     esi, 0C0000017h
0x18000514f  jmp     loc_180005303
0x180005154  movups  xmm0, xmmword ptr [rbx]
0x180005157  movups  xmmword ptr [rax], xmm0
0x18000515a  movups  xmm1, xmmword ptr [rbx+10h]
0x18000515e  movups  xmmword ptr [rax+10h], xmm1
0x180005162  movups  xmm0, xmmword ptr [rbx+20h]
0x180005166  movups  xmmword ptr [rax+20h], xmm0
0x18000516a  movsd   xmm1, qword ptr [rbx+30h]
0x18000516f  movsd   qword ptr [rax+30h], xmm1
0x180005174  mov     [rax], rsi
0x180005177  mov     [rax+8], rsi
0x18000517b  cmp     [rbx], rsi
0x18000517e  jz      loc_18000526D
0x180005184  mov     rcx, gs:60h
0x18000518d  mov     edx, 8; Flags
0x180005192  mov     r8d, 28h ; '('; Size
0x180005198  mov     rcx, [rcx+30h]; HeapHandle
0x18000519c  call    cs:__imp_RtlAllocateHeap
0x1800051a2  mov     [rdi], rax
0x1800051a5  mov     rcx, rax
0x1800051a8  test    rax, rax
0x1800051ab  jnz     loc_180005252
0x1800051b1  mov     esi, 0C0000017h
0x1800051b6  mov     r8, [rdi]; P
0x1800051b9  xor     eax, eax
0x1800051bb  mov     ebx, eax
0x1800051bd  test    r8, r8
0x1800051c0  jz      short loc_1800051DC
0x1800051c2  mov     rcx, gs:60h
0x1800051cb  xor     edx, edx; Flags
0x1800051cd  mov     rcx, [rcx+30h]; HeapHandle
0x1800051d1  call    cs:__imp_RtlFreeHeap
0x1800051d7  xor     eax, eax
0x1800051d9  mov     [rdi], rax
0x1800051dc  mov     rdx, [rdi+8]
0x1800051e0  test    rdx, rdx
0x1800051e3  jz      short loc_180005231
0x1800051e5  lea     rcx, EaiAggregationConditionNextChild
0x1800051ec  mov     [rbp+37h+var_A0.Ptr], rax
0x1800051f0  mov     [rbp+37h+var_90], rax
0x1800051f4  mov     [rbp+37h+var_88], rax
0x1800051f8  lea     rax, EaiFreeAggregationConditionVisitNode
0x1800051ff  mov     qword ptr [rbp+37h+var_A0.Size], rcx
0x180005203  lea     rcx, [rbp+37h+var_A0]
0x180005207  mov     [rbp+37h+var_80], rax
0x18000520b  call    EapTreeTraverse
0x180005210  mov     rcx, gs:60h
0x180005219  xor     edx, edx; Flags
0x18000521b  mov     r8, [rdi+8]; P
0x18000521f  mov     rcx, [rcx+30h]; HeapHandle
0x180005223  call    cs:__imp_RtlFreeHeap
0x180005229  mov     qword ptr [rdi+8], 0
0x180005231  mov     rcx, gs:60h
0x18000523a  mov     r8, rdi; P
0x18000523d  xor     edx, edx; Flags
0x18000523f  mov     rcx, [rcx+30h]; HeapHandle
0x180005243  call    cs:__imp_RtlFreeHeap
0x180005249  test    esi, esi
0x18000524b  jns     short loc_1800052C4
0x18000524d  jmp     loc_180005305
0x180005252  mov     rax, [rbx]
0x180005255  movups  xmm0, xmmword ptr [rax]
0x180005258  movups  xmmword ptr [rcx], xmm0
0x18000525b  movups  xmm1, xmmword ptr [rax+10h]
0x18000525f  movups  xmmword ptr [rcx+10h], xmm1
0x180005263  movsd   xmm0, qword ptr [rax+20h]
0x180005268  movsd   qword ptr [rcx+20h], xmm0
0x18000526d  mov     rdx, [rbx+8]
0x180005271  test    rdx, rdx
0x180005274  jz      short loc_1800052C1
0x180005276  lea     rax, [rsp+100h+EventDescriptor.Keyword]
0x18000527b  mov     [rsp+100h+EventDescriptor.Keyword], rsi
0x180005280  mov     [rbp+37h+var_A0.Ptr], rax
0x180005284  lea     rcx, [rbp+37h+var_A0]
0x180005288  lea     rax, EaiAggregationConditionNextChild
0x18000528f  mov     dword ptr [rbp+37h+var_B0], esi
0x180005292  mov     qword ptr [rbp+37h+var_A0.Size], rax
0x180005296  lea     rax, EaiDuplicateConditionsVisitNode
0x18000529d  mov     [rbp+37h+var_80], rax
0x1800052a1  mov     [rbp+37h+var_90], rsi
0x1800052a5  mov     [rbp+37h+var_88], rsi
0x1800052a9  call    EapTreeTraverse
0x1800052ae  mov     esi, eax
0x1800052b0  test    eax, eax
0x1800052b2  js      loc_1800051B6
0x1800052b8  mov     rax, [rsp+100h+EventDescriptor.Keyword]
0x1800052bd  mov     [rdi+8], rax
0x1800052c1  mov     rbx, rdi
0x1800052c4  mov     eax, dword ptr [rbp+37h+arg_30]
0x1800052c7  mov     r9, r15
0x1800052ca  mov     qword ptr [rsp+100h+var_C8], r14
0x1800052cf  mov     r8, r12
0x1800052d2  mov     dword ptr [rsp+100h+var_D0], eax
0x1800052d6  mov     rdx, r13
0x1800052d9  mov     rax, [rbp+37h+arg_28]
0x1800052dd  mov     rcx, rbx
0x1800052e0  mov     [rsp+100h+UserData], rax
0x1800052e5  mov     rax, [rbp+37h+arg_20]
0x1800052e9  mov     qword ptr [rsp+100h+UserDataCount], rax
0x1800052ee  call    EaiCreateAggregation
0x1800052f3  mov     esi, eax
0x1800052f5  test    eax, eax
0x1800052f7  js      short loc_180005305
0x1800052f9  jmp     loc_18000539D
0x1800052fe  mov     esi, 0C000000Dh
0x180005303  xor     ebx, ebx
0x180005305  test    rbx, rbx
0x180005308  jz      loc_18000539D
0x18000530e  mov     r8, [rbx]; P
0x180005311  test    r8, r8
0x180005314  jz      short loc_180005332
0x180005316  mov     rcx, gs:60h
0x18000531f  xor     edx, edx; Flags
0x180005321  mov     rcx, [rcx+30h]; HeapHandle
0x180005325  call    cs:__imp_RtlFreeHeap
0x18000532b  xor     edi, edi
0x18000532d  mov     [rbx], rdi
0x180005330  jmp     short loc_180005334
0x180005332  xor     edi, edi
0x180005334  mov     rdx, [rbx+8]
0x180005338  test    rdx, rdx
0x18000533b  jz      short loc_180005385
0x18000533d  lea     rax, EaiAggregationConditionNextChild
0x180005344  mov     [rbp+37h+var_A0.Ptr], rdi
0x180005348  mov     qword ptr [rbp+37h+var_A0.Size], rax
0x18000534c  lea     rcx, [rbp+37h+var_A0]
0x180005350  lea     rax, EaiFreeAggregationConditionVisitNode
0x180005357  mov     [rbp+37h+var_90], rdi
0x18000535b  mov     [rbp+37h+var_80], rax
0x18000535f  mov     [rbp+37h+var_88], rdi
0x180005363  call    EapTreeTraverse
0x180005368  mov     rcx, gs:60h
0x180005371  xor     edx, edx; Flags
0x180005373  mov     r8, [rbx+8]; P
0x180005377  mov     rcx, [rcx+30h]; HeapHandle
0x18000537b  call    cs:__imp_RtlFreeHeap
0x180005381  mov     [rbx+8], rdi
0x180005385  mov     rcx, gs:60h
0x18000538e  mov     r8, rbx; P
0x180005391  xor     edx, edx; Flags
0x180005393  mov     rcx, [rcx+30h]; HeapHandle
0x180005397  call    cs:__imp_RtlFreeHeap
0x18000539d  mov     r15, [rsp+100h+var_20]
0x1800053a5  mov     r13, [rsp+0F0h]
0x1800053ad  mov     r12, [rsp+100h+arg_10]
0x1800053b5  mov     rdi, [rsp+100h+arg_8]
0x1800053bd  mov     rbx, [rsp+100h+arg_0]
0x1800053c5  test    r14, r14
0x1800053c8  jz      short loc_1800053D5
0x1800053ca  test    esi, esi
0x1800053cc  js      short loc_1800053D5
0x1800053ce  mov     rcx, [r14]
0x1800053d1  xor     edx, edx
0x1800053d3  jmp     short loc_1800053D9
0x1800053d5  xor     edx, edx
0x1800053d7  mov     ecx, edx
0x1800053d9  mov     eax, cs:dword_180012000
0x1800053df  mov     r14, [rsp+100h+var_18]
0x1800053e7  cmp     eax, 4
0x1800053ea  jbe     loc_18000549F
0x1800053f0  mov     [rsp+100h+EventDescriptor.Keyword], rcx
0x1800053f5  lea     rax, [rsp+100h+EventDescriptor.Keyword]
0x1800053fa  mov     [rbp+37h+var_50], rax
0x1800053fe  lea     rcx, _TraceLoggingMetadata
0x180005405  mov     qword ptr [rbp+37h+var_A0.Size], rdx
0x180005409  lea     rax, [rsp+100h+EventDescriptor]
0x18000540e  mov     [rbp+37h+var_40], rax
0x180005412  lea     rdx, [rbp+37h+var_A0]; EventDescriptor
0x180005416  movzx   eax, cs:word_18000F25F
0x18000541d  xor     r9d, r9d; RelatedActivityId
0x180005420  mov     dword ptr [rbp+37h+var_A0.Ptr+4], eax
0x180005423  xor     r8d, r8d; ActivityId
0x180005426  mov     rax, cs:off_180012008
0x18000542d  mov     [rbp+37h+var_70.Ptr], rax
0x180005431  mov     [rbp+37h+var_48], 8
0x180005439  mov     dword ptr [rsp+100h+EventDescriptor.Id], esi
0x18000543d  mov     [rbp+37h+var_38], 4
0x180005445  mov     dword ptr [rbp+37h+var_A0.Ptr], 0B000000h
0x18000544c  movzx   eax, word ptr [rax]
0x18000544f  mov     [rbp+37h+var_70.Size], eax
0x180005452  lea     rax, byte_18000F269
0x180005459  mov     [rbp+37h+var_60], rax
0x18000545d  lea     rax, _TraceLoggingMetadataEnd
0x180005464  sub     eax, ecx
0x180005466  mov     dword ptr [rbp+37h+var_70.0Ch], 2
0x18000546d  mov     [rbp+37h+var_58], 36h ; '6'
0x180005474  mov     [rbp+37h+var_54], 1
0x18000547b  mov     [rbp+37h+var_A8], eax
0x18000547e  mov     eax, [rbp+37h+var_A8]
0x180005481  mov     rcx, cs:RegHandle; RegHandle
0x180005488  lea     rax, [rbp+37h+var_70]
0x18000548c  mov     [rsp+100h+UserData], rax; UserData
0x180005491  mov     [rsp+100h+UserDataCount], 4; UserDataCount
0x180005499  call    cs:__imp_EventWriteTransfer
0x18000549f  mov     eax, esi
0x1800054a1  mov     rcx, [rbp+37h+var_30]
0x1800054a5  xor     rcx, rsp; StackCookie
0x1800054a8  call    __security_check_cookie
0x1800054ad  add     rsp, 0F8h
0x1800054b4  pop     rsi
0x1800054b5  pop     rbp
0x1800054b6  retn
```
