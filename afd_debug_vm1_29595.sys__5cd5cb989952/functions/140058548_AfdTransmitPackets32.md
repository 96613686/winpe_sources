# AfdTransmitPackets32

- ea: `0x140058548`
- end: `0x140058be9`
- name: `AfdTransmitPackets32`
- size: `1697`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140057a30`

## callees

- `0x14002fd7c`
- `0x14003f8d8`
- `0x14003fc5c`
- `0x1400445d8`
- `0x140058548`
- `0x140058bf0`
- `0x140072840`
- `0x140072870`

## import_xrefs

- `ntoskrnl!IoQueryFileInformation` at `0x14005892c`
- `ntoskrnl!IoQueryFileInformation` at `0x14005892c`
- `ntoskrnl!ProbeForRead` at `0x140058719`
- `ntoskrnl!ProbeForRead` at `0x140058719`
- `ntoskrnl!ObfReferenceObject` at `0x140058839`
- `ntoskrnl!ObfReferenceObject` at `0x140058839`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140058605`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140058605`
- `ntoskrnl!IoFileObjectType` at `0x140058858`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14005887e`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14005887e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140058bb1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140058bb1`
- `ntoskrnl!ExAllocatePool2` at `0x14005873f`
- `ntoskrnl!ExAllocatePool2` at `0x14005873f`

## pseudocode

```c
__int64 __fastcall AfdTransmitPackets32(__int64 a1, __int64 a2, __int64 *a3, _BYTE *a4, _BYTE *a5, unsigned int *a6)
{
  __int64 *v6; // r12
  __int64 v8; // rdi
  unsigned int *Pool2; // r15
  __int64 v10; // rsi
  char v11; // cl
  void *v12; // rdx
  __int64 TpInfo; // rax
  size_t v14; // r8
  unsigned int v15; // r9d
  unsigned int v16; // r12d
  unsigned int v17; // r13d
  void *v18; // r10
  void *v19; // r11
  __int64 v20; // rax
  __int64 v21; // rsi
  __int64 v22; // r14
  unsigned int v23; // edx
  unsigned int v24; // r8d
  __int64 v25; // rax
  void *v26; // r12
  _QWORD *v27; // rdx
  KPROCESSOR_MODE v28; // r9
  NTSTATUS v29; // eax
  __int64 v30; // rcx
  __int64 v31; // rcx
  int IsEnabledDeviceUsageNoInline; // eax
  unsigned int v33; // ecx
  unsigned int v34; // r10d
  unsigned __int64 v35; // r8
  unsigned __int64 v36; // r11
  unsigned int v37; // ecx
  unsigned __int64 v38; // rdx
  NTSTATUS v40; // [rsp+30h] [rbp-E8h]
  unsigned int v41; // [rsp+34h] [rbp-E4h]
  PVOID i; // [rsp+58h] [rbp-C0h]
  ULONG ReturnedLength; // [rsp+60h] [rbp-B8h] BYREF
  unsigned __int64 v46; // [rsp+68h] [rbp-B0h]
  void *v47; // [rsp+70h] [rbp-A8h]
  PVOID Object; // [rsp+78h] [rbp-A0h] BYREF
  __int64 v49; // [rsp+80h] [rbp-98h]
  __int64 v50; // [rsp+88h] [rbp-90h]
  unsigned int *v51; // [rsp+90h] [rbp-88h]
  __int64 v52; // [rsp+98h] [rbp-80h]
  unsigned int *v53; // [rsp+A0h] [rbp-78h]
  __int64 *v54; // [rsp+A8h] [rbp-70h]
  __int128 Address; // [rsp+B0h] [rbp-68h] BYREF
  __int128 FileInformation; // [rsp+C0h] [rbp-58h] BYREF
  __int64 v57; // [rsp+D0h] [rbp-48h]

  v6 = a3;
  v49 = a1;
  v54 = a3;
  v53 = a6;
  v40 = 0;
  v8 = 0;
  v50 = 0;
  Address = 0;
  Pool2 = 0;
  v51 = 0;
  *a5 = 0;
  v10 = *(_QWORD *)(*(_QWORD *)(a2 + 48) + 24LL);
  if ( *(_DWORD *)(a2 + 16) < 0x10u )
  {
    v40 = -1073741811;
    goto LABEL_93;
  }
  v47 = 0;
  v11 = *(_BYTE *)(a1 + 64);
  if ( v11 && (*(_BYTE *)(a2 + 32) & 3) != 0 )
    ExRaiseDatatypeMisalignment();
  v12 = *(void **)(a2 + 32);
  if ( v11 )
    RtlCopyFromUser(&Address, v12, 0x10u);
  else
    RtlCopyVolatileMemory(&Address, v12, 0x10u);
  if ( (HIDWORD(Address) & 0xFFFFFFC8) != 0
    || (BYTE12(Address) & 0x30) == 0x30
    || *(_WORD *)v10 == 0xAFD1 && (BYTE12(Address) & 3) != 0 )
  {
    v40 = -1073741811;
  }
  else
  {
    if ( (_DWORD)Address && (unsigned int)(DWORD1(Address) - 1) <= 0xAAAAAA9 )
    {
      if ( (BYTE12(Address) & 0x30) == 0 )
        HIDWORD(Address) |= AfdDefaultTransmitWorker;
      if ( (*(_DWORD *)(v10 + 8) & 0x100) != 0 )
        TpInfo = AfdTliGetTpInfo(DWORD1(Address));
      else
        TpInfo = AfdTdiGetTpInfo(DWORD1(Address));
      v8 = TpInfo;
      v50 = TpInfo;
      if ( !TpInfo )
      {
        v40 = -1073741670;
        goto LABEL_93;
      }
      *(_DWORD *)(TpInfo + 76) = 0;
      *(_DWORD *)(TpInfo + 92) = DWORD2(Address);
      if ( DWORD2(Address) )
        *a5 = 1;
      else
        *(_DWORD *)(TpInfo + 92) = AfdTransmitIoLength;
      if ( *(_BYTE *)(a1 + 64) )
        ProbeForRead((volatile void *)(unsigned int)Address, 24LL * DWORD1(Address), 4u);
      Pool2 = (unsigned int *)ExAllocatePool2(97, 24LL * DWORD1(Address), 1180984897);
      v51 = Pool2;
      if ( !Pool2 )
      {
        v40 = -1073741670;
        goto LABEL_93;
      }
      v14 = 24LL * DWORD1(Address);
      if ( *(_BYTE *)(a1 + 64) )
        RtlCopyFromUser(Pool2, (void *)(unsigned int)Address, v14);
      else
        RtlCopyVolatileMemory(Pool2, (const void *)(unsigned int)Address, v14);
      v15 = 0;
      v41 = 0;
      v16 = 0;
      v46 = 0;
      *(_DWORD *)(v8 + 80) = 0;
      v17 = 0;
      v18 = 0;
      v47 = 0;
      v19 = 0;
      for ( i = 0; ; v19 = i )
      {
        v20 = *(unsigned int *)(v8 + 76);
        if ( (unsigned int)v20 >= DWORD1(Address) )
        {
          *(_DWORD *)(v49 + 128) = HIDWORD(Address);
          *v53 = v17;
          v6 = a3;
          goto LABEL_93;
        }
        v21 = 3 * v20;
        v22 = *(_QWORD *)(v8 + 64);
        v23 = Pool2[6 * v20];
        *(_DWORD *)(v22 + 24 * v20) = v23;
        if ( (v23 & 0xFFFFFFF8) != 0 || (v23 & 3) == 3 || (v23 & 3) == 0 )
        {
          v40 = -1073741811;
          v6 = a3;
          goto LABEL_93;
        }
        v24 = Pool2[6 * *(unsigned int *)(v8 + 76) + 1];
        *(_DWORD *)(v22 + 24 * v20 + 4) = v24;
        v25 = *(unsigned int *)(v8 + 76);
        if ( (v23 & 2) != 0 )
          break;
        *(_QWORD *)(v22 + 8 * v21 + 8) = Pool2[6 * v25 + 2];
        if ( v24 > AfdTPacketsCopyThreshold )
          goto LABEL_63;
        v33 = v41;
        if ( v15 && (v15 += v24, v15 <= AfdTPacketsCopyThreshold) && v15 + v41 <= *(_DWORD *)(v8 + 92) )
          *(_DWORD *)(v22 + 8 * v21 - 24) |= 0x40000000u;
        else
          v15 = v24;
        if ( (v23 & 4) != 0 )
          goto LABEL_64;
LABEL_65:
        if ( (v23 & 4) != 0 )
          v41 = 0;
        else
          v41 = (v33 + *(_DWORD *)(v22 + 8 * v21 + 4)) % *(_DWORD *)(v8 + 92);
        v34 = *(_DWORD *)(v8 + 80);
        if ( v34 != -1 )
        {
          v35 = v16 + *(_DWORD *)(v22 + 8 * v21 + 4);
          v36 = *(unsigned int *)(v8 + 92);
          v37 = v16 / (unsigned int)v36 + v34;
          v38 = v35 % v36;
          v16 = (v16 + *(_DWORD *)(v22 + 8 * v21 + 4)) % *(_DWORD *)(v8 + 92);
          v46 = v35 % v36;
          if ( v35 <= v36 )
          {
            if ( v17 < (unsigned int)v38 )
              v17 = v35 % v36;
          }
          else
          {
            v17 = v36;
          }
          if ( v37 < v34 || v37 == -1 )
          {
            *(_DWORD *)(v8 + 80) = -1;
          }
          else
          {
            *(_DWORD *)(v8 + 80) = v37;
            if ( (*(_DWORD *)(v22 + 8 * v21) & 4) != 0 && ((_DWORD)v38 || !*(_DWORD *)(v22 + 8 * v21 + 4)) )
            {
              *(_DWORD *)(v8 + 80) = v37 + 1;
              v16 = 0;
              v46 = 0;
            }
          }
        }
        ++*(_DWORD *)(v8 + 76);
        v18 = v47;
      }
      v26 = (void *)(int)Pool2[6 * v25 + 4];
      if ( v18 && v26 == v18 )
      {
        ObfReferenceObject(v19);
        v27 = i;
      }
      else
      {
        v28 = *(_BYTE *)(v49 + 64);
        Object = 0;
        v29 = ObReferenceObjectByHandle(v26, 1u, (POBJECT_TYPE)IoFileObjectType, v28, &Object, 0);
        v27 = Object;
        i = Object;
        v40 = v29;
        if ( v29 < 0 )
        {
          *a4 = 1;
          v6 = a3;
          goto LABEL_93;
        }
      }
      *(_QWORD *)(v22 + 8 * v21 + 16) = v27;
      v30 = *(unsigned int *)(v8 + 76);
      *(_DWORD *)(v8 + 76) = v30 + 1;
      *(_QWORD *)(v22 + 8 * v21 + 8) = *(_QWORD *)&Pool2[6 * v30 + 2];
      --*(_DWORD *)(v8 + 76);
      if ( (v27[10] & 2) != 0 && !*(_QWORD *)(v22 + 8 * v21 + 8) )
        *(_QWORD *)(v22 + 8 * v21 + 8) = v27[13];
      if ( *(_DWORD *)(v22 + 8 * v21 + 4) )
      {
        if ( *(__int64 *)(v22 + 8 * v21 + 8) < 0 )
        {
          ++*(_DWORD *)(v8 + 76);
          v40 = -1073741811;
          *a4 = 1;
          v6 = a3;
          goto LABEL_93;
        }
      }
      else
      {
        FileInformation = 0;
        v57 = 0;
        ReturnedLength = 0;
        v40 = IoQueryFileInformation(
                *(PFILE_OBJECT *)(v22 + 8 * v21 + 16),
                FileStandardInformation,
                0x18u,
                &FileInformation,
                &ReturnedLength);
        if ( v40 < 0 )
        {
          ++*(_DWORD *)(v8 + 76);
          *a4 = 1;
          v6 = a3;
          goto LABEL_93;
        }
        v31 = *(_QWORD *)(v22 + 8 * v21 + 8);
        if ( v31 < 0 || v31 > *((__int64 *)&FileInformation + 1) || *((_QWORD *)&FileInformation + 1) - v31 > 0x7FFFFFFF )
        {
          ++*(_DWORD *)(v8 + 76);
          v40 = -1073741811;
          *a4 = 1;
          v6 = a3;
          goto LABEL_93;
        }
        *(_DWORD *)(v22 + 8 * v21 + 4) = DWORD2(FileInformation) - v31;
      }
      v52 = (unsigned int)Feature_AfdtransmitFile_Overflow_Fix__private_featureState;
      if ( (Feature_AfdtransmitFile_Overflow_Fix__private_featureState & 0x10) != 0 )
        IsEnabledDeviceUsageNoInline = Feature_AfdtransmitFile_Overflow_Fix__private_featureState & 1;
      else
        IsEnabledDeviceUsageNoInline = Feature_AfdtransmitFile_Overflow_Fix__private_IsEnabledDeviceUsageNoInline();
      if ( IsEnabledDeviceUsageNoInline
        && 0x7FFFFFFFFFFFFFFFLL - *(_QWORD *)(v22 + 8 * v21 + 8) < *(unsigned int *)(v22 + 8 * v21 + 4) )
      {
        ++*(_DWORD *)(v8 + 76);
        v40 = -1073741811;
        *a4 = 1;
        v6 = a3;
        goto LABEL_93;
      }
      v47 = v26;
      v23 = *(_DWORD *)(v22 + 8 * v21);
      v16 = v46;
LABEL_63:
      v33 = v41;
LABEL_64:
      v15 = 0;
      goto LABEL_65;
    }
    v40 = -1073741811;
  }
LABEL_93:
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0x46646641u);
  *v6 = v8;
  return (unsigned int)v40;
}

```

## disassembly

```asm
0x140058548  mov     r11, rsp
0x14005854b  push    rbx
0x14005854c  push    rsi
0x14005854d  push    rdi
0x14005854e  push    r12
0x140058550  push    r13
0x140058552  push    r14
0x140058554  push    r15
0x140058556  sub     rsp, 0E0h
0x14005855d  mov     rax, cs:__security_cookie
0x140058564  xor     rax, rsp
0x140058567  mov     [rsp+118h+var_40], rax
0x14005856f  mov     [rsp+118h+var_C8], r9
0x140058574  mov     r12, r8
0x140058577  mov     [rsp+118h+var_D8], r8
0x14005857c  mov     r13, rcx
0x14005857f  mov     [rsp+118h+var_98], rcx
0x140058587  mov     [rsp+118h+var_70], r8
0x14005858f  mov     r14, [rsp+118h+arg_20]
0x140058597  mov     rax, [rsp+118h+arg_28]
0x14005859f  mov     [rsp+118h+var_78], rax
0x1400585a7  xor     ebx, ebx
0x1400585a9  mov     [rsp+118h+var_E8], ebx
0x1400585ad  mov     edi, ebx
0x1400585af  mov     [r11-90h], rbx
0x1400585b6  xorps   xmm0, xmm0
0x1400585b9  movups  xmmword ptr [r11-68h], xmm0
0x1400585be  mov     r15d, ebx
0x1400585c1  mov     [r11-88h], rbx
0x1400585c8  mov     [r14], bl
0x1400585cb  mov     rax, [rdx+30h]
0x1400585cf  mov     rsi, [rax+18h]
0x1400585d3  cmp     dword ptr [rdx+10h], 10h
0x1400585d7  jnb     short loc_1400585E6
0x1400585d9  mov     [rsp+118h+var_E8], 0C000000Dh
0x1400585e1  jmp     loc_140058BA4
0x1400585e6  mov     [rsp+118h+var_C0], rbx
0x1400585eb  mov     [rsp+118h+var_A8], rbx
0x1400585f0  mov     [rsp+118h+var_E0], ebx
0x1400585f4  mov     [rsp+118h+var_DC], ebx
0x1400585f8  mov     cl, [rcx+40h]
0x1400585fb  test    cl, cl
0x1400585fd  jz      short loc_140058611
0x1400585ff  test    byte ptr [rdx+20h], 3
0x140058603  jz      short loc_140058611
0x140058605  call    cs:__imp_ExRaiseDatatypeMisalignment
0x14005860c  nop     dword ptr [rax+rax+00h]
0x140058611  mov     rdx, [rdx+20h]; Src
0x140058615  mov     r8d, 10h; Size
0x14005861b  test    cl, cl
0x14005861d  lea     rcx, [rsp+118h+Address]; void *
0x140058625  jz      short loc_14005862E
0x140058627  call    RtlCopyFromUser
0x14005862c  jmp     short loc_140058633
0x14005862e  call    RtlCopyVolatileMemory
0x140058633  mov     ecx, [rsp+118h+var_5C]
0x14005863a  test    ecx, 0FFFFFFC8h
0x140058640  jnz     loc_140058B82
0x140058646  mov     edx, ecx
0x140058648  and     edx, 30h
0x14005864b  cmp     edx, 30h ; '0'
0x14005864e  jz      loc_140058B82
0x140058654  mov     eax, 0AFD1h
0x140058659  cmp     [rsi], ax
0x14005865c  jnz     short loc_140058667
0x14005865e  test    cl, 3
0x140058661  jnz     loc_140058B82
0x140058667  cmp     dword ptr [rsp+118h+Address], ebx
0x14005866e  jz      loc_140058B78
0x140058674  mov     eax, dword ptr [rsp+118h+Address+4]
0x14005867b  dec     eax
0x14005867d  cmp     eax, 0AAAAAA9h
0x140058682  ja      loc_140058B78
0x140058688  test    edx, edx
0x14005868a  jnz     short loc_140058699
0x14005868c  or      ecx, cs:AfdDefaultTransmitWorker
0x140058692  mov     [rsp+118h+var_5C], ecx
0x140058699  mov     eax, [rsi+8]
0x14005869c  mov     ecx, dword ptr [rsp+118h+Address+4]
0x1400586a3  bt      eax, 8
0x1400586a7  jnb     short loc_1400586B0
0x1400586a9  call    AfdTliGetTpInfo
0x1400586ae  jmp     short loc_1400586B5
0x1400586b0  call    AfdTdiGetTpInfo
0x1400586b5  mov     rdi, rax
0x1400586b8  mov     [rsp+118h+var_90], rax
0x1400586c0  test    rax, rax
0x1400586c3  jnz     short loc_1400586D2
0x1400586c5  mov     [rsp+118h+var_E8], 0C000009Ah
0x1400586cd  jmp     loc_140058BA4
0x1400586d2  mov     [rdi+4Ch], ebx
0x1400586d5  mov     eax, [rsp+118h+var_60]
0x1400586dc  mov     [rdi+5Ch], eax
0x1400586df  cmp     [rsp+118h+var_60], ebx
0x1400586e6  jnz     short loc_1400586F3
0x1400586e8  mov     eax, cs:AfdTransmitIoLength
0x1400586ee  mov     [rdi+5Ch], eax
0x1400586f1  jmp     short loc_1400586F7
0x1400586f3  mov     byte ptr [r14], 1
0x1400586f7  cmp     [r13+40h], bl
0x1400586fb  jz      short loc_140058725
0x1400586fd  mov     eax, dword ptr [rsp+118h+Address+4]
0x140058704  lea     rdx, [rax+rax*2]
0x140058708  shl     rdx, 3; Length
0x14005870c  mov     ecx, dword ptr [rsp+118h+Address]; Address
0x140058713  mov     r8d, 4; Alignment
0x140058719  call    cs:__imp_ProbeForRead
0x140058720  nop     dword ptr [rax+rax+00h]
0x140058725  mov     eax, dword ptr [rsp+118h+Address+4]
0x14005872c  lea     rdx, [rax+rax*2]
0x140058730  shl     rdx, 3
0x140058734  mov     ecx, 61h ; 'a'
0x140058739  mov     r8d, 46646641h
0x14005873f  call    cs:__imp_ExAllocatePool2
0x140058746  nop     dword ptr [rax+rax+00h]
0x14005874b  mov     r15, rax
0x14005874e  mov     [rsp+118h+var_88], rax
0x140058756  test    rax, rax
0x140058759  jnz     short loc_140058768
0x14005875b  mov     [rsp+118h+var_E8], 0C000009Ah
0x140058763  jmp     loc_140058BA4
0x140058768  mov     edx, dword ptr [rsp+118h+Address]; Src
0x14005876f  mov     eax, dword ptr [rsp+118h+Address+4]
0x140058776  lea     r8, [rax+rax*2]
0x14005877a  shl     r8, 3; Size
0x14005877e  mov     rcx, r15; void *
0x140058781  cmp     [r13+40h], bl
0x140058785  jz      short loc_14005878E
0x140058787  call    RtlCopyFromUser
0x14005878c  jmp     short loc_140058793
0x14005878e  call    RtlCopyVolatileMemory
0x140058793  mov     r9d, ebx
0x140058796  mov     [rsp+118h+var_E0], ebx
0x14005879a  mov     [rsp+118h+var_E4], ebx
0x14005879e  mov     r12d, ebx
0x1400587a1  mov     [rsp+118h+var_B0], r12
0x1400587a6  mov     [rsp+118h+var_DC], ebx
0x1400587aa  mov     [rdi+50h], ebx
0x1400587ad  mov     r13d, ebx
0x1400587b0  mov     [rsp+118h+var_D0], ebx
0x1400587b4  mov     r10, rbx
0x1400587b7  mov     [rsp+118h+var_A8], rbx
0x1400587bc  mov     r11, rbx
0x1400587bf  mov     [rsp+118h+var_C0], rbx
0x1400587c4  mov     eax, [rdi+4Ch]
0x1400587c7  cmp     eax, dword ptr [rsp+118h+Address+4]
0x1400587ce  jnb     loc_140058B51
0x1400587d4  lea     rsi, [rax+rax*2]
0x1400587d8  mov     r14, [rdi+40h]
0x1400587dc  mov     edx, [r15+rsi*8]
0x1400587e0  mov     [r14+rsi*8], edx
0x1400587e4  test    edx, 0FFFFFFF8h
0x1400587ea  jnz     loc_140058B42
0x1400587f0  mov     eax, edx
0x1400587f2  and     eax, 3
0x1400587f5  cmp     eax, 3
0x1400587f8  jz      loc_140058B42
0x1400587fe  test    eax, eax
0x140058800  jz      loc_140058B42
0x140058806  mov     eax, [rdi+4Ch]
0x140058809  lea     rcx, [rax+rax*2]
0x14005880d  mov     r8d, [r15+rcx*8+4]
0x140058812  mov     [r14+rsi*8+4], r8d
0x140058817  mov     eax, [rdi+4Ch]
0x14005881a  lea     rcx, [rax+rax*2]
0x14005881e  test    dl, 2
0x140058821  jz      loc_140058A44
0x140058827  movsxd  r12, dword ptr [r15+rcx*8+10h]
0x14005882c  test    r10, r10
0x14005882f  jz      short loc_14005884C
0x140058831  cmp     r12, r10
0x140058834  jnz     short loc_14005884C
0x140058836  mov     rcx, r11; Object
0x140058839  call    cs:__imp_ObfReferenceObject
0x140058840  nop     dword ptr [rax+rax+00h]
0x140058845  mov     rdx, [rsp+118h+var_C0]
0x14005884a  jmp     short loc_1400588B2
0x14005884c  mov     rax, [rsp+118h+var_98]
0x140058854  mov     r9b, [rax+40h]; AccessMode
0x140058858  mov     rax, cs:__imp_IoFileObjectType
0x14005885f  mov     r8, [rax]; ObjectType
0x140058862  mov     [rsp+118h+var_A0], rbx
0x140058867  mov     [rsp+118h+HandleInformation], rbx; HandleInformation
0x14005886c  lea     rax, [rsp+118h+var_A0]
0x140058871  mov     [rsp+118h+Object], rax; Object
0x140058876  mov     edx, 1; DesiredAccess
0x14005887b  mov     rcx, r12; Handle
0x14005887e  call    cs:__imp_ObReferenceObjectByHandle
0x140058885  nop     dword ptr [rax+rax+00h]
0x14005888a  mov     rdx, [rsp+118h+var_A0]
0x14005888f  mov     [rsp+118h+var_C0], rdx
0x140058894  mov     [rsp+118h+var_E8], eax
0x140058898  mov     eax, [rsp+118h+var_E8]
0x14005889c  test    eax, eax
0x14005889e  jns     short loc_1400588B2
0x1400588a0  mov     rax, [rsp+118h+var_C8]
0x1400588a5  mov     byte ptr [rax], 1
0x1400588a8  mov     r12, [rsp+118h+var_D8]
0x1400588ad  jmp     loc_140058BA4
0x1400588b2  mov     [r14+rsi*8+10h], rdx
0x1400588b7  mov     ecx, [rdi+4Ch]
0x1400588ba  lea     eax, [rcx+1]
0x1400588bd  mov     [rdi+4Ch], eax
0x1400588c0  lea     rcx, [rcx+rcx*2]
0x1400588c4  mov     rax, [r15+rcx*8+8]
0x1400588c9  mov     [r14+rsi*8+8], rax
0x1400588ce  dec     dword ptr [rdi+4Ch]
0x1400588d1  mov     eax, [rdx+50h]
0x1400588d4  test    al, 2
0x1400588d6  jz      short loc_1400588E8
0x1400588d8  cmp     [r14+rsi*8+8], rbx
0x1400588dd  jnz     short loc_1400588E8
0x1400588df  mov     rax, [rdx+68h]
0x1400588e3  mov     [r14+rsi*8+8], rax
0x1400588e8  cmp     [r14+rsi*8+4], ebx
0x1400588ed  jnz     loc_14005899F
0x1400588f3  xorps   xmm0, xmm0
0x1400588f6  xor     eax, eax
0x1400588f8  movups  [rsp+118h+FileInformation], xmm0
0x140058900  mov     [rsp+118h+var_48], rax
0x140058908  mov     [rsp+118h+ReturnedLength], ebx
0x14005890c  lea     rax, [rsp+118h+ReturnedLength]
0x140058911  mov     [rsp+118h+Object], rax; ReturnedLength
0x140058916  lea     r9, [rsp+118h+FileInformation]; FileInformation
0x14005891e  mov     edx, 5; FileInformationClass
0x140058923  lea     r8d, [rdx+13h]; Length
0x140058927  mov     rcx, [r14+rsi*8+10h]; FileObject
0x14005892c  call    cs:__imp_IoQueryFileInformation
0x140058933  nop     dword ptr [rax+rax+00h]
0x140058938  mov     [rsp+118h+var_E8], eax
0x14005893c  mov     eax, [rsp+118h+var_E8]
0x140058940  test    eax, eax
0x140058942  jns     short loc_140058959
0x140058944  inc     dword ptr [rdi+4Ch]
0x140058947  mov     rax, [rsp+118h+var_C8]
0x14005894c  mov     byte ptr [rax], 1
0x14005894f  mov     r12, [rsp+118h+var_D8]
0x140058954  jmp     loc_140058BA4
0x140058959  mov     rcx, [r14+rsi*8+8]
0x14005895e  test    rcx, rcx
0x140058961  js      short loc_140058982
0x140058963  mov     rax, qword ptr [rsp+118h+FileInformation+8]
0x14005896b  cmp     rcx, rax
0x14005896e  jg      short loc_140058982
0x140058970  sub     rax, rcx
0x140058973  cmp     rax, 7FFFFFFFh
0x140058979  jg      short loc_140058982
0x14005897b  mov     [r14+rsi*8+4], eax
0x140058980  jmp     short loc_1400589C3
0x140058982  inc     dword ptr [rdi+4Ch]
0x140058985  mov     [rsp+118h+var_E8], 0C000000Dh
0x14005898d  mov     rax, [rsp+118h+var_C8]
0x140058992  mov     byte ptr [rax], 1
0x140058995  mov     r12, [rsp+118h+var_D8]
0x14005899a  jmp     loc_140058BA4
0x14005899f  cmp     [r14+rsi*8+8], rbx
0x1400589a4  jge     short loc_1400589C3
0x1400589a6  inc     dword ptr [rdi+4Ch]
0x1400589a9  mov     [rsp+118h+var_E8], 0C000000Dh
0x1400589b1  mov     rax, [rsp+118h+var_C8]
0x1400589b6  mov     byte ptr [rax], 1
0x1400589b9  mov     r12, [rsp+118h+var_D8]
0x1400589be  jmp     loc_140058BA4
0x1400589c3  mov     [rsp+118h+var_80], rbx
0x1400589cb  mov     eax, cs:Feature_AfdtransmitFile_Overflow_Fix__private_featureState
0x1400589d1  mov     dword ptr [rsp+118h+var_80], eax
0x1400589d8  test    al, 10h
0x1400589da  jz      short loc_1400589E1
0x1400589dc  and     eax, 1
0x1400589df  jmp     short loc_1400589E6
0x1400589e1  call    Feature_AfdtransmitFile_Overflow_Fix__private_IsEnabledDeviceUsageNoInline
0x1400589e6  test    eax, eax
0x1400589e8  jz      short loc_140058A20
0x1400589ea  mov     rcx, 7FFFFFFFFFFFFFFFh
0x1400589f4  sub     rcx, [r14+rsi*8+8]
0x1400589f9  mov     eax, [r14+rsi*8+4]
0x1400589fe  cmp     rcx, rax
0x140058a01  jge     short loc_140058A20
0x140058a03  inc     dword ptr [rdi+4Ch]
0x140058a06  mov     [rsp+118h+var_E8], 0C000000Dh
0x140058a0e  mov     rax, [rsp+118h+var_C8]
0x140058a13  mov     byte ptr [rax], 1
0x140058a16  mov     r12, [rsp+118h+var_D8]
0x140058a1b  jmp     loc_140058BA4
0x140058a20  mov     [rsp+118h+var_A8], r12
0x140058a25  mov     edx, [r14+rsi*8]
0x140058a29  mov     r12, [rsp+118h+var_B0]
0x140058a2e  mov     ecx, [rsp+118h+var_E4]
0x140058a32  mov     r9d, ebx
0x140058a35  mov     [rsp+118h+var_E0], ebx
0x140058a39  test    dl, 4
0x140058a3c  jz      short loc_140058A90
0x140058a3e  mov     [rsp+118h+var_E4], ebx
0x140058a42  jmp     short loc_140058AA0
0x140058a44  mov     eax, [r15+rcx*8+8]
0x140058a49  mov     [r14+rsi*8+8], rax
0x140058a4e  mov     eax, cs:AfdTPacketsCopyThreshold
0x140058a54  cmp     r8d, eax
0x140058a57  ja      short loc_140058A2E
0x140058a59  mov     ecx, [rsp+118h+var_E4]
  ... truncated ...
```
