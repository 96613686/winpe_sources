# BampApplyThrottledProcessPolicy

- ea: `0x140013740`
- end: `0x140013c73`
- name: `BampApplyThrottledProcessPolicy`
- size: `1331`
- prototype: `NTSTATUS __fastcall(__int64, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140015100`

## callees

- `0x1400026d0`
- `0x140002710`
- `0x140013740`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x140013863`
- `ntoskrnl!EtwWriteTransfer` at `0x1400139dd`
- `ntoskrnl!EtwWriteTransfer` at `0x140013b0e`
- `ntoskrnl!EtwWriteTransfer` at `0x140013c3f`
- `ntoskrnl!EtwWriteTransfer` at `0x140013863`
- `ntoskrnl!EtwWriteTransfer` at `0x1400139dd`
- `ntoskrnl!EtwWriteTransfer` at `0x140013b0e`
- `ntoskrnl!EtwWriteTransfer` at `0x140013c3f`

## pseudocode

```c
NTSTATUS __fastcall BampApplyThrottledProcessPolicy(__int64 a1, int *a2)
{
  unsigned int v2; // r14d
  unsigned int v3; // r15d
  __int64 v6; // rax
  int v7; // ecx
  int v8; // ecx
  int v9; // r14d
  __int64 v10; // rcx
  int v11; // eax
  int v12; // r12d
  __int64 v13; // rcx
  unsigned int v14; // edx
  __int64 v15; // rdx
  unsigned int v16; // r14d
  __int64 v17; // rax
  unsigned int v18; // ecx
  NTSTATUS result; // eax
  __int64 v20; // rax
  unsigned int v21; // ecx
  unsigned int v22; // [rsp+30h] [rbp-99h] BYREF
  int v23; // [rsp+34h] [rbp-95h] BYREF
  int v24; // [rsp+38h] [rbp-91h] BYREF
  unsigned int v25; // [rsp+3Ch] [rbp-8Dh] BYREF
  unsigned int v26; // [rsp+40h] [rbp-89h] BYREF
  EVENT_DESCRIPTOR v27; // [rsp+48h] [rbp-81h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+58h] [rbp-71h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+70h] [rbp-59h] BYREF
  __int16 *v30; // [rsp+80h] [rbp-49h]
  int v31; // [rsp+88h] [rbp-41h]
  int v32; // [rsp+8Ch] [rbp-3Dh]
  unsigned int *v33; // [rsp+90h] [rbp-39h]
  __int64 v34; // [rsp+98h] [rbp-31h]
  int *v35; // [rsp+A0h] [rbp-29h]
  __int64 v36; // [rsp+A8h] [rbp-21h]
  unsigned int *v37; // [rsp+B0h] [rbp-19h]
  __int64 v38; // [rsp+B8h] [rbp-11h]
  int *v39; // [rsp+C0h] [rbp-9h]
  __int64 v40; // [rsp+C8h] [rbp-1h]
  int *v41; // [rsp+D0h] [rbp+7h]
  __int64 v42; // [rsp+D8h] [rbp+Fh]

  v2 = a2[1];
  v3 = 0;
  if ( *(_DWORD *)(a1 + 356) != v2 )
  {
    (*(void (__fastcall **)(_QWORD, _QWORD))(BampKernelInterface + 8))(*(_QWORD *)(a1 + 8), v2);
    if ( (unsigned int)dword_140007010 > 5 )
    {
      v6 = *(_QWORD *)(a1 + 8);
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 0;
      v7 = *(_DWORD *)(v6 + 464);
      v33 = (unsigned int *)&v23;
      v35 = &v24;
      *(_DWORD *)&EventDescriptor.Level = 5;
      UserData.Ptr = (ULONGLONG)off_140007018;
      v23 = v7;
      v34 = 4;
      v24 = v2;
      v36 = 4;
      UserData.Size = *(unsigned __int16 *)off_140007018;
      v30 = (__int16 *)&dword_140005534;
      UserData.Reserved = 2;
      v31 = 34;
      v32 = 1;
      v22 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, &UserData);
    }
    *(_DWORD *)(a1 + 352) ^= (*a2 ^ *(_DWORD *)(a1 + 352)) & 1;
    *(_DWORD *)(a1 + 356) = a2[1];
  }
  v8 = ((unsigned int)*a2 >> 1) & 1;
  if ( ((*(_DWORD *)(a1 + 352) >> 1) & 1) != v8 )
  {
    if ( v8 )
    {
      v9 = BampGlobalThrottlingSettings;
      v3 = DWORD1(BampGlobalThrottlingSettings);
    }
    else
    {
      v9 = 0;
    }
    v10 = *(_QWORD *)(a1 + 104);
    *(_DWORD *)&EventDescriptor.Id = 10000 * v9;
    *(_DWORD *)&EventDescriptor.Level = 10000 * v3;
    v11 = (*(__int64 (__fastcall **)(__int64, EVENT_DESCRIPTOR *))BampKernelInterface)(v10, &EventDescriptor);
    v12 = v11;
    if ( (unsigned int)dword_140007010 > 5 )
    {
      v13 = *(_QWORD *)(a1 + 8);
      *(_DWORD *)&v27.Id = 184549376;
      v14 = *(_DWORD *)(v13 + 464);
      v33 = &v22;
      v35 = &v24;
      v37 = (unsigned int *)&v23;
      v39 = (int *)&v25;
      *(_DWORD *)&v27.Level = 5;
      UserData.Ptr = (ULONGLONG)off_140007018;
      v25 = v3;
      v22 = v14;
      v34 = 4;
      v24 = v11;
      v36 = 4;
      v23 = v9;
      v38 = 4;
      v40 = 4;
      v27.Keyword = 0;
      UserData.Size = *(unsigned __int16 *)off_140007018;
      v30 = word_1400054F2;
      UserData.Reserved = 2;
      v31 = 54;
      v32 = 1;
      v26 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EtwWriteTransfer(RegHandle, &v27, 0, 0, 6u, &UserData);
    }
    if ( v12 >= 0 )
    {
      *(_DWORD *)(a1 + 352) ^= (*a2 ^ *(_DWORD *)(a1 + 352)) & 2;
      v15 = (unsigned int)*a2 >> 1;
      LOBYTE(v15) = (*a2 & 2) != 0;
      (*(void (__fastcall **)(_QWORD, __int64))(BampKernelInterface + 16))(*(_QWORD *)(a1 + 8), v15);
    }
  }
  v16 = a2[2];
  if ( *(_DWORD *)(a1 + 360) != v16 )
  {
    (*(void (__fastcall **)(_QWORD, _QWORD))(BampKernelInterface + 32))(*(_QWORD *)(a1 + 8), v16);
    if ( (unsigned int)dword_140007010 > 5 )
    {
      v17 = *(_QWORD *)(a1 + 8);
      *(_DWORD *)&v27.Id = 184549376;
      v27.Keyword = 0;
      v18 = *(_DWORD *)(v17 + 464);
      v33 = &v26;
      v35 = (int *)&v25;
      *(_DWORD *)&v27.Level = 5;
      UserData.Ptr = (ULONGLONG)off_140007018;
      v26 = v18;
      v34 = 4;
      v25 = v16;
      v36 = 4;
      UserData.Size = *(unsigned __int16 *)off_140007018;
      v30 = (__int16 *)&dword_1400054AC;
      UserData.Reserved = 2;
      v31 = 58;
      v32 = 1;
      v22 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EtwWriteTransfer(RegHandle, &v27, 0, 0, 4u, &UserData);
    }
    *(_DWORD *)(a1 + 352) ^= (*a2 ^ *(_DWORD *)(a1 + 352)) & 4;
    *(_DWORD *)(a1 + 360) = a2[2];
  }
  result = dword_140007010;
  if ( (unsigned int)dword_140007010 > 4 )
  {
    v20 = *(_QWORD *)(a1 + 8);
    *(_DWORD *)&v27.Id = 184549376;
    v27.Keyword = 0;
    v21 = *(_DWORD *)(v20 + 464);
    v33 = &v26;
    v25 = *(_DWORD *)(a1 + 352);
    v35 = (int *)&v25;
    v22 = *(_DWORD *)(a1 + 356);
    v37 = &v22;
    v24 = *a2;
    v39 = &v24;
    v23 = a2[1];
    v41 = &v23;
    *(_DWORD *)&v27.Level = 4;
    UserData.Ptr = (ULONGLONG)off_140007018;
    v26 = v21;
    v34 = 4;
    v36 = 4;
    v38 = 4;
    v40 = 4;
    v42 = 4;
    UserData.Size = *(unsigned __int16 *)off_140007018;
    v30 = word_140005672;
    UserData.Reserved = 2;
    v31 = 138;
    v32 = 1;
    *(_DWORD *)&EventDescriptor.Id = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    return EtwWriteTransfer(RegHandle, &v27, 0, 0, 7u, &UserData);
  }
  return result;
}

```

## disassembly

```asm
0x140013740  mov     [rsp-8+arg_10], rbx
0x140013745  push    rbp
0x140013746  push    rsi
0x140013747  push    rdi
0x140013748  push    r12
0x14001374a  push    r13
0x14001374c  push    r14
0x14001374e  push    r15
0x140013750  lea     rbp, [rsp-27h]
0x140013755  sub     rsp, 0F0h
0x14001375c  mov     rax, cs:__security_cookie
0x140013763  xor     rax, rsp
0x140013766  mov     [rbp+57h+var_40], rax
0x14001376a  mov     r14d, [rdx+4]
0x14001376e  lea     r13, _TraceLoggingMetadataEnd
0x140013775  xor     r15d, r15d
0x140013778  lea     r12, _TraceLoggingMetadata
0x14001377f  mov     rdi, rdx
0x140013782  mov     rbx, rcx
0x140013785  cmp     [rcx+164h], r14d
0x14001378c  jz      loc_14001388D
0x140013792  mov     rax, cs:BampKernelInterface
0x140013799  mov     edx, r14d
0x14001379c  mov     rcx, [rcx+8]
0x1400137a0  mov     rax, [rax+8]
0x1400137a4  call    _guard_dispatch_icall
0x1400137a9  mov     eax, cs:dword_140007010
0x1400137af  cmp     eax, 5
0x1400137b2  jbe     loc_14001386F
0x1400137b8  mov     rax, [rbx+8]
0x1400137bc  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x1400137c0  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x1400137c7  xor     r9d, r9d; RelatedActivityId
0x1400137ca  mov     [rbp+57h+EventDescriptor.Keyword], r15
0x1400137ce  xor     r8d, r8d; ActivityId
0x1400137d1  mov     ecx, [rax+1D0h]
0x1400137d7  lea     rax, [rsp+120h+var_EC]
0x1400137dc  mov     [rbp+57h+var_90], rax
0x1400137e0  lea     rax, [rsp+120h+var_E8]
0x1400137e5  mov     [rbp+57h+var_80], rax
0x1400137e9  movzx   eax, cs:word_14000552A
0x1400137f0  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x1400137f3  mov     rax, cs:off_140007018
0x1400137fa  mov     [rbp+57h+var_B0.Ptr], rax
0x1400137fe  mov     [rsp+120h+var_EC], ecx
0x140013802  mov     [rbp+57h+var_88], 4
0x14001380a  mov     [rsp+120h+var_E8], r14d
0x14001380f  mov     [rbp+57h+var_78], 4
0x140013817  movzx   eax, word ptr [rax]
0x14001381a  mov     [rbp+57h+var_B0.Size], eax
0x14001381d  lea     rax, dword_140005534
0x140013824  mov     [rbp+57h+var_A0], rax
0x140013828  mov     rax, r13
0x14001382b  sub     eax, r12d
0x14001382e  mov     dword ptr [rbp+57h+var_B0.0Ch], 2
0x140013835  mov     [rbp+57h+var_98], 22h ; '"'
0x14001383c  mov     [rbp+57h+var_94], 1
0x140013843  mov     [rsp+120h+var_F0], eax
0x140013847  mov     eax, [rsp+120h+var_F0]
0x14001384b  mov     rcx, cs:RegHandle; RegHandle
0x140013852  lea     rax, [rbp+57h+var_B0]
0x140013856  mov     [rsp+120h+UserData], rax; UserData
0x14001385b  mov     [rsp+120h+UserDataCount], 4; UserDataCount
0x140013863  call    cs:__imp_EtwWriteTransfer
0x14001386a  nop     dword ptr [rax+rax+00h]
0x14001386f  mov     eax, [rbx+160h]
0x140013875  mov     ecx, eax
0x140013877  xor     ecx, [rdi]
0x140013879  and     ecx, 1
0x14001387c  xor     ecx, eax
0x14001387e  mov     [rbx+160h], ecx
0x140013884  mov     eax, [rdi+4]
0x140013887  mov     [rbx+164h], eax
0x14001388d  mov     ecx, [rdi]
0x14001388f  mov     eax, [rbx+160h]
0x140013895  shr     ecx, 1
0x140013897  shr     eax, 1
0x140013899  and     ecx, 1
0x14001389c  and     eax, 1
0x14001389f  cmp     eax, ecx
0x1400138a1  jz      loc_140013A2A
0x1400138a7  test    ecx, ecx
0x1400138a9  jz      short loc_1400138BB
0x1400138ab  mov     r14d, dword ptr cs:BampGlobalThrottlingSettings
0x1400138b2  mov     r15d, dword ptr cs:BampGlobalThrottlingSettings+4
0x1400138b9  jmp     short loc_1400138BE
0x1400138bb  mov     r14d, r15d
0x1400138be  mov     rcx, [rbx+68h]
0x1400138c2  lea     rdx, [rbp+57h+EventDescriptor]
0x1400138c6  imul    eax, r14d, 2710h
0x1400138cd  mov     dword ptr [rbp+57h+EventDescriptor.Id], eax
0x1400138d0  imul    eax, r15d, 2710h
0x1400138d7  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x1400138da  mov     rax, cs:BampKernelInterface
0x1400138e1  mov     rax, [rax]
0x1400138e4  call    _guard_dispatch_icall
0x1400138e9  mov     ecx, cs:dword_140007010
0x1400138ef  mov     r12d, eax
0x1400138f2  cmp     ecx, 5
0x1400138f5  jbe     loc_1400139EB
0x1400138fb  mov     rcx, [rbx+8]
0x1400138ff  lea     rax, [rsp+120h+var_F0]
0x140013904  mov     dword ptr [rsp+120h+var_D8.Id], 0B000000h
0x14001390c  xor     r9d, r9d; RelatedActivityId
0x14001390f  xor     r8d, r8d; ActivityId
0x140013912  mov     edx, [rcx+1D0h]
0x140013918  lea     rcx, _TraceLoggingMetadata
0x14001391f  mov     [rbp+57h+var_90], rax
0x140013923  lea     rax, [rsp+120h+var_E8]
0x140013928  mov     [rbp+57h+var_80], rax
0x14001392c  lea     rax, [rsp+120h+var_EC]
0x140013931  mov     [rbp+57h+var_70], rax
0x140013935  lea     rax, [rsp+120h+var_E4]
0x14001393a  mov     [rbp+57h+var_60], rax
0x14001393e  movzx   eax, cs:word_1400054E8
0x140013945  mov     dword ptr [rbp+57h+var_D8.Level], eax
0x140013948  mov     rax, cs:off_140007018
0x14001394f  mov     [rbp+57h+var_B0.Ptr], rax
0x140013953  mov     [rsp+120h+var_E4], r15d
0x140013958  xor     r15d, r15d
0x14001395b  mov     [rsp+120h+var_F0], edx
0x14001395f  lea     rdx, [rsp+120h+var_D8]; EventDescriptor
0x140013964  mov     [rbp+57h+var_88], 4
0x14001396c  mov     [rsp+120h+var_E8], r12d
0x140013971  mov     [rbp+57h+var_78], 4
0x140013979  mov     [rsp+120h+var_EC], r14d
0x14001397e  mov     [rbp+57h+var_68], 4
0x140013986  mov     [rbp+57h+var_58], 4
0x14001398e  mov     [rbp+57h+var_D8.Keyword], r15
0x140013992  movzx   eax, word ptr [rax]
0x140013995  mov     [rbp+57h+var_B0.Size], eax
0x140013998  lea     rax, word_1400054F2
0x14001399f  mov     [rbp+57h+var_A0], rax
0x1400139a3  mov     rax, r13
0x1400139a6  sub     eax, ecx
0x1400139a8  mov     dword ptr [rbp+57h+var_B0.0Ch], 2
0x1400139af  mov     [rbp+57h+var_98], 36h ; '6'
0x1400139b6  mov     [rbp+57h+var_94], 1
0x1400139bd  mov     [rsp+120h+var_E0], eax
0x1400139c1  mov     eax, [rsp+120h+var_E0]
0x1400139c5  mov     rcx, cs:RegHandle; RegHandle
0x1400139cc  lea     rax, [rbp+57h+var_B0]
0x1400139d0  mov     [rsp+120h+UserData], rax; UserData
0x1400139d5  mov     [rsp+120h+UserDataCount], 6; UserDataCount
0x1400139dd  call    cs:__imp_EtwWriteTransfer
0x1400139e4  nop     dword ptr [rax+rax+00h]
0x1400139e9  jmp     short loc_1400139EE
0x1400139eb  xor     r15d, r15d
0x1400139ee  test    r12d, r12d
0x1400139f1  js      short loc_140013A23
0x1400139f3  mov     eax, [rbx+160h]
0x1400139f9  mov     ecx, eax
0x1400139fb  xor     ecx, [rdi]
0x1400139fd  and     ecx, 2
0x140013a00  xor     ecx, eax
0x140013a02  mov     [rbx+160h], ecx
0x140013a08  mov     rax, cs:BampKernelInterface
0x140013a0f  mov     edx, [rdi]
0x140013a11  mov     rcx, [rbx+8]
0x140013a15  shr     edx, 1
0x140013a17  mov     rax, [rax+10h]
0x140013a1b  and     dl, 1
0x140013a1e  call    _guard_dispatch_icall
0x140013a23  lea     r12, _TraceLoggingMetadata
0x140013a2a  mov     r14d, [rdi+8]
0x140013a2e  cmp     [rbx+168h], r14d
0x140013a35  jz      loc_140013B38
0x140013a3b  mov     rax, cs:BampKernelInterface
0x140013a42  mov     edx, r14d
0x140013a45  mov     rcx, [rbx+8]
0x140013a49  mov     rax, [rax+20h]
0x140013a4d  call    _guard_dispatch_icall
0x140013a52  mov     eax, cs:dword_140007010
0x140013a58  cmp     eax, 5
0x140013a5b  jbe     loc_140013B1A
0x140013a61  mov     rax, [rbx+8]
0x140013a65  lea     rdx, [rsp+120h+var_D8]; EventDescriptor
0x140013a6a  mov     dword ptr [rsp+120h+var_D8.Id], 0B000000h
0x140013a72  xor     r9d, r9d; RelatedActivityId
0x140013a75  mov     [rbp+57h+var_D8.Keyword], r15
0x140013a79  xor     r8d, r8d; ActivityId
0x140013a7c  mov     ecx, [rax+1D0h]
0x140013a82  lea     rax, [rsp+120h+var_E0]
0x140013a87  mov     [rbp+57h+var_90], rax
0x140013a8b  lea     rax, [rsp+120h+var_E4]
0x140013a90  mov     [rbp+57h+var_80], rax
0x140013a94  movzx   eax, cs:word_1400054A2
0x140013a9b  mov     dword ptr [rbp+57h+var_D8.Level], eax
0x140013a9e  mov     rax, cs:off_140007018
0x140013aa5  mov     [rbp+57h+var_B0.Ptr], rax
0x140013aa9  mov     [rsp+120h+var_E0], ecx
0x140013aad  mov     [rbp+57h+var_88], 4
0x140013ab5  mov     [rsp+120h+var_E4], r14d
0x140013aba  mov     [rbp+57h+var_78], 4
0x140013ac2  movzx   eax, word ptr [rax]
0x140013ac5  mov     [rbp+57h+var_B0.Size], eax
0x140013ac8  lea     rax, dword_1400054AC
0x140013acf  mov     [rbp+57h+var_A0], rax
0x140013ad3  mov     rax, r13
0x140013ad6  sub     eax, r12d
0x140013ad9  mov     dword ptr [rbp+57h+var_B0.0Ch], 2
0x140013ae0  mov     [rbp+57h+var_98], 3Ah ; ':'
0x140013ae7  mov     [rbp+57h+var_94], 1
0x140013aee  mov     [rsp+120h+var_F0], eax
0x140013af2  mov     eax, [rsp+120h+var_F0]
0x140013af6  mov     rcx, cs:RegHandle; RegHandle
0x140013afd  lea     rax, [rbp+57h+var_B0]
0x140013b01  mov     [rsp+120h+UserData], rax; UserData
0x140013b06  mov     [rsp+120h+UserDataCount], 4; UserDataCount
0x140013b0e  call    cs:__imp_EtwWriteTransfer
0x140013b15  nop     dword ptr [rax+rax+00h]
0x140013b1a  mov     eax, [rbx+160h]
0x140013b20  mov     ecx, eax
0x140013b22  xor     ecx, [rdi]
0x140013b24  and     ecx, 4
0x140013b27  xor     ecx, eax
0x140013b29  mov     [rbx+160h], ecx
0x140013b2f  mov     eax, [rdi+8]
0x140013b32  mov     [rbx+168h], eax
0x140013b38  mov     eax, cs:dword_140007010
0x140013b3e  cmp     eax, 4
0x140013b41  jbe     loc_140013C4B
0x140013b47  mov     rax, [rbx+8]
0x140013b4b  lea     rdx, [rsp+120h+var_D8]; EventDescriptor
0x140013b50  mov     dword ptr [rsp+120h+var_D8.Id], 0B000000h
0x140013b58  sub     r13d, r12d
0x140013b5b  mov     [rbp+57h+var_D8.Keyword], r15
0x140013b5f  xor     r9d, r9d; RelatedActivityId
0x140013b62  xor     r8d, r8d; ActivityId
0x140013b65  mov     ecx, [rax+1D0h]
0x140013b6b  lea     rax, [rsp+120h+var_E0]
0x140013b70  mov     [rbp+57h+var_90], rax
0x140013b74  mov     eax, [rbx+160h]
0x140013b7a  mov     [rsp+120h+var_E4], eax
0x140013b7e  lea     rax, [rsp+120h+var_E4]
0x140013b83  mov     [rbp+57h+var_80], rax
0x140013b87  mov     eax, [rbx+164h]
0x140013b8d  mov     [rsp+120h+var_F0], eax
0x140013b91  lea     rax, [rsp+120h+var_F0]
0x140013b96  mov     [rbp+57h+var_70], rax
0x140013b9a  mov     eax, [rdi]
0x140013b9c  mov     [rsp+120h+var_E8], eax
0x140013ba0  lea     rax, [rsp+120h+var_E8]
0x140013ba5  mov     [rbp+57h+var_60], rax
0x140013ba9  mov     eax, [rdi+4]
0x140013bac  mov     [rsp+120h+var_EC], eax
0x140013bb0  lea     rax, [rsp+120h+var_EC]
0x140013bb5  mov     [rbp+57h+var_50], rax
0x140013bb9  movzx   eax, cs:word_140005668
0x140013bc0  mov     dword ptr [rbp+57h+var_D8.Level], eax
0x140013bc3  mov     rax, cs:off_140007018
0x140013bca  mov     [rbp+57h+var_B0.Ptr], rax
0x140013bce  mov     [rsp+120h+var_E0], ecx
0x140013bd2  mov     [rbp+57h+var_88], 4
0x140013bda  mov     [rbp+57h+var_78], 4
0x140013be2  mov     [rbp+57h+var_68], 4
0x140013bea  mov     [rbp+57h+var_58], 4
0x140013bf2  mov     [rbp+57h+var_48], 4
0x140013bfa  movzx   eax, word ptr [rax]
0x140013bfd  mov     [rbp+57h+var_B0.Size], eax
0x140013c00  lea     rax, word_140005672
0x140013c07  mov     [rbp+57h+var_A0], rax
0x140013c0b  mov     dword ptr [rbp+57h+var_B0.0Ch], 2
0x140013c12  mov     [rbp+57h+var_98], 8Ah
0x140013c19  mov     [rbp+57h+var_94], 1
0x140013c20  mov     dword ptr [rbp+57h+EventDescriptor.Id], r13d
0x140013c24  mov     eax, dword ptr [rbp+57h+EventDescriptor.Id]
0x140013c27  mov     rcx, cs:RegHandle; RegHandle
0x140013c2e  lea     rax, [rbp+57h+var_B0]
0x140013c32  mov     [rsp+120h+UserData], rax; UserData
0x140013c37  mov     [rsp+120h+UserDataCount], 7; UserDataCount
0x140013c3f  call    cs:__imp_EtwWriteTransfer
0x140013c46  nop     dword ptr [rax+rax+00h]
0x140013c4b  mov     rcx, [rbp+57h+var_40]
0x140013c4f  xor     rcx, rsp; StackCookie
0x140013c52  call    __security_check_cookie
0x140013c57  mov     rbx, [rsp+120h+arg_10]
0x140013c5f  add     rsp, 0F0h
0x140013c66  pop     r15
0x140013c68  pop     r14
0x140013c6a  pop     r13
0x140013c6c  pop     r12
0x140013c6e  pop     rdi
0x140013c6f  pop     rsi
0x140013c70  pop     rbp
0x140013c71  retn
```
