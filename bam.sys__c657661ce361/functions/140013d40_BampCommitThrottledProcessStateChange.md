# BampCommitThrottledProcessStateChange

- ea: `0x140013d40`
- end: `0x14001416f`
- name: `BampCommitThrottledProcessStateChange`
- size: `1071`
- prototype: `void __fastcall(char *P)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14000f460`

## callees

- `0x1400026d0`
- `0x1400100b0`
- `0x140010990`
- `0x140011560`
- `0x140013d40`
- `0x140015608`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x140013e31`
- `ntoskrnl!EtwWriteTransfer` at `0x140014060`
- `ntoskrnl!EtwWriteTransfer` at `0x140013e31`
- `ntoskrnl!EtwWriteTransfer` at `0x140014060`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140013e44`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140013e44`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140013e56`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140013e56`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140013eab`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400140ff`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140013eab`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400140ff`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140013e9f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400140f3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140013e9f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400140f3`

## pseudocode

```c
void __fastcall BampCommitThrottledProcessStateChange(char *P)
{
  __int64 v2; // rax
  int v3; // ecx
  int *v4; // rsi
  __int64 v5; // rax
  unsigned int v6; // ecx
  int v7; // edi
  bool v8; // r14
  __int64 v9; // xmm1_8
  __int64 v10; // rdx
  int v11; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v12; // [rsp+34h] [rbp-CCh] BYREF
  int v13; // [rsp+38h] [rbp-C8h] BYREF
  int v14; // [rsp+3Ch] [rbp-C4h] BYREF
  int v15; // [rsp+40h] [rbp-C0h] BYREF
  int v16; // [rsp+44h] [rbp-BCh] BYREF
  int v17; // [rsp+48h] [rbp-B8h] BYREF
  int v18; // [rsp+4Ch] [rbp-B4h] BYREF
  int v19; // [rsp+50h] [rbp-B0h] BYREF
  int v20; // [rsp+54h] [rbp-ACh] BYREF
  _DWORD v21[2]; // [rsp+58h] [rbp-A8h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v23; // [rsp+70h] [rbp-90h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+80h] [rbp-80h] BYREF
  __int16 *v25; // [rsp+90h] [rbp-70h]
  int v26; // [rsp+98h] [rbp-68h]
  int v27; // [rsp+9Ch] [rbp-64h]
  int *v28; // [rsp+A0h] [rbp-60h]
  __int64 v29; // [rsp+A8h] [rbp-58h]
  struct _EVENT_DATA_DESCRIPTOR v30; // [rsp+B0h] [rbp-50h] BYREF
  int *v31; // [rsp+C0h] [rbp-40h]
  int v32; // [rsp+C8h] [rbp-38h]
  int v33; // [rsp+CCh] [rbp-34h]
  unsigned int *v34; // [rsp+D0h] [rbp-30h]
  __int64 v35; // [rsp+D8h] [rbp-28h]
  int *v36; // [rsp+E0h] [rbp-20h]
  __int64 v37; // [rsp+E8h] [rbp-18h]
  int *v38; // [rsp+F0h] [rbp-10h]
  __int64 v39; // [rsp+F8h] [rbp-8h]
  int *v40; // [rsp+100h] [rbp+0h]
  __int64 v41; // [rsp+108h] [rbp+8h]
  int *v42; // [rsp+110h] [rbp+10h]
  __int64 v43; // [rsp+118h] [rbp+18h]
  int *v44; // [rsp+120h] [rbp+20h]
  __int64 v45; // [rsp+128h] [rbp+28h]
  int *v46; // [rsp+130h] [rbp+30h]
  __int64 v47; // [rsp+138h] [rbp+38h]
  int *v48; // [rsp+140h] [rbp+40h]
  __int64 v49; // [rsp+148h] [rbp+48h]
  int *v50; // [rsp+150h] [rbp+50h]
  __int64 v51; // [rsp+158h] [rbp+58h]
  int *v52; // [rsp+160h] [rbp+60h]
  __int64 v53; // [rsp+168h] [rbp+68h]
  _DWORD *v54; // [rsp+170h] [rbp+70h]
  __int64 v55; // [rsp+178h] [rbp+78h]

  v23 = 0;
  if ( (unsigned int)dword_140007010 > 5 )
  {
    v2 = *((_QWORD *)P + 1);
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    v3 = *(_DWORD *)(v2 + 464);
    v28 = &v11;
    *(_DWORD *)&EventDescriptor.Level = 5;
    UserData.Ptr = (ULONGLONG)off_140007018;
    v11 = v3;
    v29 = 4;
    UserData.Size = *(unsigned __int16 *)off_140007018;
    v25 = word_1400052F2;
    UserData.Reserved = 2;
    v26 = 41;
    v27 = 1;
    v12 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
  }
  v4 = (int *)(P + 304);
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(P + 16, 0);
  *((_QWORD *)P + 3) = KeGetCurrentThread();
  if ( *((_QWORD *)P + 38) == *((_QWORD *)P + 35)
    && *((_QWORD *)P + 39) == *((_QWORD *)P + 36)
    && *((_QWORD *)P + 40) == *((_QWORD *)P + 37) )
  {
    *((_QWORD *)P + 3) = 0;
    ExReleasePushLockExclusiveEx(P + 16, 0);
    KeLeaveCriticalRegion();
  }
  else
  {
    if ( (unsigned int)dword_140007010 > 4 )
    {
      v5 = *((_QWORD *)P + 1);
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 0;
      v6 = *(_DWORD *)(v5 + 464);
      v34 = &v12;
      v11 = *((_DWORD *)P + 70);
      v36 = &v11;
      v13 = *((_DWORD *)P + 71);
      v38 = &v13;
      v14 = *((_DWORD *)P + 73);
      v40 = &v14;
      v15 = *((_DWORD *)P + 74);
      v42 = &v15;
      v16 = *((_DWORD *)P + 75);
      v44 = &v16;
      v17 = *v4;
      v46 = &v17;
      v18 = *((_DWORD *)P + 77);
      v48 = &v18;
      v19 = *((_DWORD *)P + 79);
      v50 = &v19;
      v20 = *((_DWORD *)P + 80);
      v52 = &v20;
      v21[0] = *((_DWORD *)P + 81);
      v54 = v21;
      *(_DWORD *)&EventDescriptor.Level = 4;
      v30.Ptr = (ULONGLONG)off_140007018;
      v12 = v6;
      v35 = 4;
      v37 = 4;
      v39 = 4;
      v41 = 4;
      v43 = 4;
      v45 = 4;
      v47 = 4;
      v49 = 4;
      v51 = 4;
      v53 = 4;
      v55 = 4;
      v30.Size = *(unsigned __int16 *)off_140007018;
      v31 = &dword_140005214;
      v30.Reserved = 2;
      v32 = 210;
      v33 = 1;
      v21[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 0xDu, &v30);
    }
    v7 = *((_DWORD *)P + 70) & 1;
    if ( (*v4 & 1) == v7 )
    {
      LOBYTE(v7) = 0;
      v8 = 0;
    }
    else
    {
      v8 = !(P[280] & 1);
    }
    v9 = *((_QWORD *)P + 37);
    *((_OWORD *)P + 19) = *(_OWORD *)(P + 280);
    *((_QWORD *)P + 40) = v9;
    BampQueuePolicyActionItemAfterStateChange(P);
    if ( (*v4 & 1) != 0 || v8 )
    {
      *((_QWORD *)&v23 + 1) = 0;
      if ( v8 )
        *(_QWORD *)&v23 = P + 328;
      else
        *(_QWORD *)&v23 = P + 304;
      BampThrottlingProcessEnumerateWindowlessDescendants(P, v10, &v23);
    }
    *((_QWORD *)P + 3) = 0;
    ExReleasePushLockExclusiveEx(P + 16, 0);
    KeLeaveCriticalRegion();
    BampUpdateThrottledProcessSiufState(P);
    if ( (_BYTE)v7 )
    {
      if ( !*((_DWORD *)P + 81) )
        BamUserSettingsAddOrUpdate(
          (unsigned __int16 *)P + 196,
          (struct _UNICODE_STRING *)(P + 88),
          0,
          (*((unsigned __int16 *)P + 138) >> 1) & 1,
          1);
    }
  }
}

```

## disassembly

```asm
0x140013d40  push    rbp
0x140013d42  push    rbx
0x140013d43  push    rsi
0x140013d44  push    rdi
0x140013d45  push    r12
0x140013d47  push    r13
0x140013d49  push    r14
0x140013d4b  push    r15
0x140013d4d  lea     rbp, [rsp-98h]
0x140013d55  sub     rsp, 198h
0x140013d5c  mov     rax, cs:__security_cookie
0x140013d63  xor     rax, rsp
0x140013d66  mov     [rbp+0D0h+var_50], rax
0x140013d6d  mov     eax, cs:dword_140007010
0x140013d73  lea     r14, _TraceLoggingMetadataEnd
0x140013d7a  xor     r12d, r12d
0x140013d7d  lea     r13, _TraceLoggingMetadata
0x140013d84  xorps   xmm0, xmm0
0x140013d87  mov     rbx, rcx
0x140013d8a  movups  [rsp+1D0h+var_160], xmm0
0x140013d8f  cmp     eax, 5
0x140013d92  jbe     loc_140013E3D
0x140013d98  mov     rax, [rcx+8]
0x140013d9c  lea     rdx, [rsp+1D0h+EventDescriptor]; EventDescriptor
0x140013da1  mov     dword ptr [rsp+1D0h+EventDescriptor.Id], 0B000000h
0x140013da9  xor     r9d, r9d; RelatedActivityId
0x140013dac  mov     [rsp+1D0h+EventDescriptor.Keyword], r12
0x140013db1  xor     r8d, r8d; ActivityId
0x140013db4  mov     ecx, [rax+1D0h]
0x140013dba  lea     rax, [rsp+1D0h+var_1A0]
0x140013dbf  mov     [rbp+0D0h+var_130], rax
0x140013dc3  movzx   eax, cs:word_1400052E8
0x140013dca  mov     dword ptr [rsp+1D0h+EventDescriptor.Level], eax
0x140013dce  mov     rax, cs:off_140007018
0x140013dd5  mov     [rbp+0D0h+var_150.Ptr], rax
0x140013dd9  mov     [rsp+1D0h+var_1A0], ecx
0x140013ddd  mov     [rbp+0D0h+var_128], 4
0x140013de5  movzx   eax, word ptr [rax]
0x140013de8  mov     [rbp+0D0h+var_150.Size], eax
0x140013deb  lea     rax, word_1400052F2
0x140013df2  mov     [rbp+0D0h+var_140], rax
0x140013df6  mov     rax, r14
0x140013df9  sub     eax, r13d
0x140013dfc  mov     dword ptr [rbp+0D0h+var_150.0Ch], 2
0x140013e03  mov     [rbp+0D0h+var_138], 29h ; ')'
0x140013e0a  mov     [rbp+0D0h+var_134], 1
0x140013e11  mov     [rsp+1D0h+var_19C], eax
0x140013e15  mov     eax, [rsp+1D0h+var_19C]
0x140013e19  mov     rcx, cs:RegHandle; RegHandle
0x140013e20  lea     rax, [rbp+0D0h+var_150]
0x140013e24  mov     [rsp+1D0h+UserData], rax; UserData
0x140013e29  mov     [rsp+1D0h+UserDataCount], 3; UserDataCount
0x140013e31  call    cs:__imp_EtwWriteTransfer
0x140013e38  nop     dword ptr [rax+rax+00h]
0x140013e3d  lea     rsi, [rbx+130h]
0x140013e44  call    cs:__imp_KeEnterCriticalRegion
0x140013e4b  nop     dword ptr [rax+rax+00h]
0x140013e50  xor     edx, edx
0x140013e52  lea     rcx, [rbx+10h]
0x140013e56  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140013e5d  nop     dword ptr [rax+rax+00h]
0x140013e62  mov     rax, gs:188h
0x140013e6b  mov     [rbx+18h], rax
0x140013e6f  mov     rax, [rsi]
0x140013e72  cmp     rax, [rbx+118h]
0x140013e79  jnz     short loc_140013EBC
0x140013e7b  mov     rax, [rsi+8]
0x140013e7f  cmp     rax, [rbx+120h]
0x140013e86  jnz     short loc_140013EBC
0x140013e88  mov     rax, [rsi+10h]
0x140013e8c  cmp     rax, [rbx+128h]
0x140013e93  jnz     short loc_140013EBC
0x140013e95  xor     edx, edx
0x140013e97  mov     [rbx+18h], r12
0x140013e9b  lea     rcx, [rbx+10h]
0x140013e9f  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140013ea6  nop     dword ptr [rax+rax+00h]
0x140013eab  call    cs:__imp_KeLeaveCriticalRegion
0x140013eb2  nop     dword ptr [rax+rax+00h]
0x140013eb7  jmp     loc_14001414B
0x140013ebc  mov     eax, cs:dword_140007010
0x140013ec2  cmp     eax, 4
0x140013ec5  jbe     loc_14001406C
0x140013ecb  mov     rax, [rbx+8]
0x140013ecf  lea     rdx, [rsp+1D0h+EventDescriptor]; EventDescriptor
0x140013ed4  mov     dword ptr [rsp+1D0h+EventDescriptor.Id], 0B000000h
0x140013edc  sub     r14d, r13d
0x140013edf  mov     [rsp+1D0h+EventDescriptor.Keyword], r12
0x140013ee4  xor     r9d, r9d; RelatedActivityId
0x140013ee7  xor     r8d, r8d; ActivityId
0x140013eea  mov     ecx, [rax+1D0h]
0x140013ef0  lea     rax, [rsp+1D0h+var_19C]
0x140013ef5  mov     [rbp+0D0h+var_100], rax
0x140013ef9  mov     eax, [rbx+118h]
0x140013eff  mov     [rsp+1D0h+var_1A0], eax
0x140013f03  lea     rax, [rsp+1D0h+var_1A0]
0x140013f08  mov     [rbp+0D0h+var_F0], rax
0x140013f0c  mov     eax, [rbx+11Ch]
0x140013f12  mov     [rsp+1D0h+var_198], eax
0x140013f16  lea     rax, [rsp+1D0h+var_198]
0x140013f1b  mov     [rbp+0D0h+var_E0], rax
0x140013f1f  mov     eax, [rbx+124h]
0x140013f25  mov     [rsp+1D0h+var_194], eax
0x140013f29  lea     rax, [rsp+1D0h+var_194]
0x140013f2e  mov     [rbp+0D0h+var_D0], rax
0x140013f32  mov     eax, [rbx+128h]
0x140013f38  mov     [rsp+1D0h+var_190], eax
0x140013f3c  lea     rax, [rsp+1D0h+var_190]
0x140013f41  mov     [rbp+0D0h+var_C0], rax
0x140013f45  mov     eax, [rbx+12Ch]
0x140013f4b  mov     [rsp+1D0h+var_18C], eax
0x140013f4f  lea     rax, [rsp+1D0h+var_18C]
0x140013f54  mov     [rbp+0D0h+var_B0], rax
0x140013f58  mov     eax, [rsi]
0x140013f5a  mov     [rsp+1D0h+var_188], eax
0x140013f5e  lea     rax, [rsp+1D0h+var_188]
0x140013f63  mov     [rbp+0D0h+var_A0], rax
0x140013f67  mov     eax, [rsi+4]
0x140013f6a  mov     [rsp+1D0h+var_184], eax
0x140013f6e  lea     rax, [rsp+1D0h+var_184]
0x140013f73  mov     [rbp+0D0h+var_90], rax
0x140013f77  mov     eax, [rsi+0Ch]
0x140013f7a  mov     [rsp+1D0h+var_180], eax
0x140013f7e  lea     rax, [rsp+1D0h+var_180]
0x140013f83  mov     [rbp+0D0h+var_80], rax
0x140013f87  mov     eax, [rsi+10h]
0x140013f8a  mov     [rsp+1D0h+var_17C], eax
0x140013f8e  lea     rax, [rsp+1D0h+var_17C]
0x140013f93  mov     [rbp+0D0h+var_70], rax
0x140013f97  mov     eax, [rsi+14h]
0x140013f9a  mov     [rsp+1D0h+var_178], eax
0x140013f9e  lea     rax, [rsp+1D0h+var_178]
0x140013fa3  mov     [rbp+0D0h+var_60], rax
0x140013fa7  movzx   eax, cs:word_14000520A
0x140013fae  mov     dword ptr [rsp+1D0h+EventDescriptor.Level], eax
0x140013fb2  mov     rax, cs:off_140007018
0x140013fb9  mov     [rbp+0D0h+var_120.Ptr], rax
0x140013fbd  mov     [rsp+1D0h+var_19C], ecx
0x140013fc1  mov     [rbp+0D0h+var_F8], 4
0x140013fc9  mov     [rbp+0D0h+var_E8], 4
0x140013fd1  mov     [rbp+0D0h+var_D8], 4
0x140013fd9  mov     [rbp+0D0h+var_C8], 4
0x140013fe1  mov     [rbp+0D0h+var_B8], 4
0x140013fe9  mov     [rbp+0D0h+var_A8], 4
0x140013ff1  mov     [rbp+0D0h+var_98], 4
0x140013ff9  mov     [rbp+0D0h+var_88], 4
0x140014001  mov     [rbp+0D0h+var_78], 4
0x140014009  mov     [rbp+0D0h+var_68], 4
0x140014011  mov     [rbp+0D0h+var_58], 4
0x140014019  movzx   eax, word ptr [rax]
0x14001401c  mov     [rbp+0D0h+var_120.Size], eax
0x14001401f  lea     rax, dword_140005214
0x140014026  mov     [rbp+0D0h+var_110], rax
0x14001402a  mov     dword ptr [rbp+0D0h+var_120.0Ch], 2
0x140014031  mov     [rbp+0D0h+var_108], 0D2h
0x140014038  mov     [rbp+0D0h+var_104], 1
0x14001403f  mov     [rsp+1D0h+var_174], r14d
0x140014044  mov     eax, [rsp+1D0h+var_174]
0x140014048  mov     rcx, cs:RegHandle; RegHandle
0x14001404f  lea     rax, [rbp+0D0h+var_120]
0x140014053  mov     [rsp+1D0h+UserData], rax; UserData
0x140014058  mov     [rsp+1D0h+UserDataCount], 0Dh; UserDataCount
0x140014060  call    cs:__imp_EtwWriteTransfer
0x140014067  nop     dword ptr [rax+rax+00h]
0x14001406c  mov     edi, [rbx+118h]
0x140014072  mov     eax, [rsi]
0x140014074  and     edi, 1
0x140014077  and     eax, 1
0x14001407a  cmp     eax, edi
0x14001407c  jz      short loc_140014088
0x14001407e  movzx   r14d, dil
0x140014082  xor     r14b, 1
0x140014086  jmp     short loc_14001408E
0x140014088  xor     dil, dil
0x14001408b  xor     r14b, r14b
0x14001408e  movups  xmm0, xmmword ptr [rbx+118h]
0x140014095  mov     rcx, rbx
0x140014098  movsd   xmm1, qword ptr [rbx+128h]
0x1400140a0  movups  xmmword ptr [rbx+130h], xmm0
0x1400140a7  movsd   qword ptr [rbx+140h], xmm1
0x1400140af  call    BampQueuePolicyActionItemAfterStateChange
0x1400140b4  mov     eax, [rsi]
0x1400140b6  test    al, 1
0x1400140b8  jnz     short loc_1400140BF
0x1400140ba  test    r14b, r14b
0x1400140bd  jz      short loc_1400140E9
0x1400140bf  mov     qword ptr [rsp+1D0h+var_160+8], r12
0x1400140c4  test    r14b, r14b
0x1400140c7  jz      short loc_1400140D7
0x1400140c9  lea     rax, [rbx+148h]
0x1400140d0  mov     qword ptr [rsp+1D0h+var_160], rax
0x1400140d5  jmp     short loc_1400140DC
0x1400140d7  mov     qword ptr [rsp+1D0h+var_160], rsi
0x1400140dc  lea     r8, [rsp+1D0h+var_160]
0x1400140e1  mov     rcx, rbx
0x1400140e4  call    BampThrottlingProcessEnumerateWindowlessDescendants
0x1400140e9  xor     edx, edx
0x1400140eb  mov     [rbx+18h], r12
0x1400140ef  lea     rcx, [rbx+10h]
0x1400140f3  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400140fa  nop     dword ptr [rax+rax+00h]
0x1400140ff  call    cs:__imp_KeLeaveCriticalRegion
0x140014106  nop     dword ptr [rax+rax+00h]
0x14001410b  mov     rcx, rbx; P
0x14001410e  call    BampUpdateThrottledProcessSiufState
0x140014113  test    dil, dil
0x140014116  jz      short loc_14001414B
0x140014118  cmp     [rbx+144h], r12d
0x14001411f  jnz     short loc_14001414B
0x140014121  movzx   r9d, word ptr [rbx+114h]
0x140014129  lea     rdx, [rbx+58h]
0x14001412d  shr     r9d, 1
0x140014130  lea     rcx, [rbx+188h]
0x140014137  and     r9d, 1
0x14001413b  mov     [rsp+1D0h+UserDataCount], 1
0x140014143  xor     r8d, r8d
0x140014146  call    BamUserSettingsAddOrUpdate
0x14001414b  mov     rcx, [rbp+0D0h+var_50]
0x140014152  xor     rcx, rsp; StackCookie
0x140014155  call    __security_check_cookie
0x14001415a  add     rsp, 198h
0x140014161  pop     r15
0x140014163  pop     r14
0x140014165  pop     r13
0x140014167  pop     r12
0x140014169  pop     rdi
0x14001416a  pop     rsi
0x14001416b  pop     rbx
0x14001416c  pop     rbp
0x14001416d  retn
```
