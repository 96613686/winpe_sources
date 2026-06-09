# AfdBuildPacketChain

- ea: `0x1400406dc`
- end: `0x140041032`
- name: `AfdBuildPacketChain`
- size: `2390`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x140056f20`

## callees

- `0x140007120`
- `0x14000cbe0`
- `0x140012610`
- `0x14002fd7c`
- `0x1400406dc`
- `0x1400417c4`
- `0x1400445d8`
- `0x140055c5c`
- `0x140066bc0`
- `0x140072870`
- `0x140093008`
- `0x14009304c`
- `0x1400930cc`
- `0x140093e58`
- `0x140094184`
- `0x140094900`

## import_xrefs

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400408cc`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400408cc`
- `ntoskrnl!IoGetRequestorProcess` at `0x140040a6a`
- `ntoskrnl!IoGetRequestorProcess` at `0x140040a6a`
- `ntoskrnl!KeAttachProcess` at `0x140040a8d`
- `ntoskrnl!KeAttachProcess` at `0x140040a8d`
- `ntoskrnl!FsRtlMdlRead` at `0x140040dd2`
- `ntoskrnl!FsRtlMdlRead` at `0x140040dd2`
- `ntoskrnl!KeDetachProcess` at `0x140040fc8`
- `ntoskrnl!KeDetachProcess` at `0x140040fc8`
- `ntoskrnl!IoBuildPartialMdl` at `0x140040a11`
- `ntoskrnl!IoBuildPartialMdl` at `0x140040a11`
- `ntoskrnl!IoFreeMdl` at `0x14004092d`
- `ntoskrnl!IoFreeMdl` at `0x140040958`
- `ntoskrnl!IoFreeMdl` at `0x14004092d`
- `ntoskrnl!IoFreeMdl` at `0x140040958`
- `ntoskrnl!MmProbeAndLockPages` at `0x140040b4c`
- `ntoskrnl!MmProbeAndLockPages` at `0x140040b4c`
- `ntoskrnl!IoAllocateMdl` at `0x1400408ab`
- `ntoskrnl!IoAllocateMdl` at `0x1400409e7`
- `ntoskrnl!IoAllocateMdl` at `0x140040aee`
- `ntoskrnl!IoAllocateMdl` at `0x1400408ab`
- `ntoskrnl!IoAllocateMdl` at `0x1400409e7`
- `ntoskrnl!IoAllocateMdl` at `0x140040aee`
- `ntoskrnl!IoGetCurrentProcess` at `0x140040a79`
- `ntoskrnl!IoGetCurrentProcess` at `0x140040a79`

## pseudocode

```c
__int64 __fastcall AfdBuildPacketChain(__int64 a1, __int64 *a2)
{
  unsigned int v3; // esi
  __int64 v4; // rbx
  int v5; // eax
  int ISB; // eax
  int v7; // ecx
  unsigned int v8; // eax
  __int64 v9; // rax
  __int64 v10; // r15
  unsigned int v11; // eax
  int v12; // ecx
  int v13; // r8d
  ULONG v14; // r12d
  unsigned int v15; // r9d
  struct _MDL *Mdl; // rax
  struct _MDL *v17; // r14
  struct _MDL **v18; // rax
  struct _MDL *v19; // rcx
  struct _MDL *v20; // r14
  PMDL v21; // r14
  struct _MDL *v22; // rax
  PVOID *v23; // r15
  struct _KPROCESS *RequestorProcess; // r14
  ULONG v25; // edx
  char *v26; // r14
  __int64 v27; // rcx
  size_t v28; // r8
  void *v29; // rdx
  PVOID v30; // rdx
  _QWORD *v31; // r8
  __int64 Buffer; // r14
  __int64 v33; // rcx
  __int64 v34; // r8
  __int64 v35; // rdx
  _QWORD **v36; // rax
  _QWORD **v37; // rdx
  _QWORD *i; // rcx
  __int16 v39; // ax
  __int16 v40; // ax
  __int64 v41; // rcx
  __int64 v42; // r8
  __int16 v43; // ax
  __int16 v44; // ax
  int v46; // [rsp+40h] [rbp-A8h]
  __int64 v47; // [rsp+48h] [rbp-A0h]
  __int128 v48; // [rsp+50h] [rbp-98h] BYREF
  __int64 v49; // [rsp+60h] [rbp-88h]
  __int64 v50; // [rsp+68h] [rbp-80h]
  PVOID Entry; // [rsp+70h] [rbp-78h]
  char *v52; // [rsp+80h] [rbp-68h]
  __int64 v53; // [rsp+88h] [rbp-60h]
  __int64 v54; // [rsp+90h] [rbp-58h]
  __int64 v55; // [rsp+98h] [rbp-50h]
  __int64 v56; // [rsp+A0h] [rbp-48h]
  char v59; // [rsp+100h] [rbp+18h]
  ULONG v60; // [rsp+108h] [rbp+20h]

  v3 = -1073741802;
  v46 = -1073741802;
  v59 = 0;
  v4 = *(_QWORD *)(a1 + 24);
  v50 = v4;
  v49 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 184) + 48LL) + 24LL);
  v54 = v49;
  v47 = 0;
  v60 = 0;
  v5 = *(_DWORD *)(a1 + 128);
  if ( (v5 & 0x40) != 0 )
  {
    if ( (v5 & 0x80u) == 0 )
    {
      ISB = AfdQueryISB(*(_QWORD *)(v4 + 16), v4 + 96);
      v7 = *(_DWORD *)(a1 + 128);
      if ( ISB >= 0 )
      {
        *(_DWORD *)(a1 + 128) = v7 | 0x80;
      }
      else
      {
        *(_DWORD *)(a1 + 128) = v7 & 0xFFFFFFBF;
        *(_DWORD *)(v4 + 96) = 0;
      }
    }
    v8 = *(_DWORD *)(v4 + 96) / (unsigned int)*(unsigned __int16 *)(v4 + 84);
    if ( v8 != *(_DWORD *)(v4 + 92) && v8 > *(_DWORD *)(v4 + 88) && v8 > AfdTransmitIoLength )
      *(_DWORD *)(v4 + 92) = v8;
  }
  while ( 1 )
  {
    while ( 1 )
    {
      while ( 1 )
      {
        if ( v3 != -1073741802 )
          goto LABEL_103;
        v9 = *(_QWORD *)(v4 + 64);
        v10 = v9 + 24LL * *(unsigned int *)(v4 + 72);
        if ( (BYTE2(xmmword_1400875E0) & 4) != 0 )
          WPP_SF_qq(
            1042,
            13,
            WPP_854aaf7e57ed31daf99bd98e8a0637b6_Traceguids,
            v4,
            v9 + 24LL * *(unsigned int *)(v4 + 72));
        *(_QWORD *)&v48 = v10 + 4;
        v11 = *(_DWORD *)(v10 + 4);
        v12 = *(_DWORD *)(v4 + 88);
        v13 = *(_DWORD *)(v4 + 92);
        v14 = v13 - v12;
        if ( v11 <= v13 - v12 )
        {
          v14 = *(_DWORD *)(v10 + 4);
          v15 = ++*(_DWORD *)(v4 + 72);
          if ( v12 + v11 == v13 || (*(_DWORD *)v10 & 4) != 0 || v15 >= *(_DWORD *)(v4 + 76) )
          {
            v3 = 0;
            v46 = 0;
            if ( (BYTE2(xmmword_1400875E0) & 4) != 0 )
              WPP_SF_qD(1042, 15, WPP_854aaf7e57ed31daf99bd98e8a0637b6_Traceguids, v4, v15);
          }
        }
        else
        {
          v3 = 0;
          v46 = 0;
          if ( (BYTE2(xmmword_1400875E0) & 4) != 0 )
            WPP_SF_qD(1042, 14, WPP_854aaf7e57ed31daf99bd98e8a0637b6_Traceguids, v4, v13);
        }
        *(_DWORD *)(v10 + 4) -= v14;
        *(_DWORD *)(v4 + 88) += v14;
        if ( v14 || v47 )
          break;
        if ( *(_QWORD *)(v4 + 32) == v4 + 24 )
        {
          *(_BYTE *)(v4 + 87) = 1;
          Mdl = IoAllocateMdl((PVOID)v4, 1u, 0, 0, 0);
          v17 = Mdl;
          if ( !Mdl )
            goto LABEL_25;
          MmBuildMdlForNonPagedPool(Mdl);
          v17->ByteCount = 0;
          if ( (BYTE2(xmmword_1400875E0) & 4) != 0 )
            WPP_SF_qq(1042, 16, WPP_854aaf7e57ed31daf99bd98e8a0637b6_Traceguids, v4, v17);
          **(_QWORD **)(v4 + 32) = v17;
          *(_QWORD *)(v4 + 32) = v17;
        }
      }
      v18 = (struct _MDL **)(v4 + 24);
      v19 = *(struct _MDL **)(v4 + 32);
      if ( v19 != (struct _MDL *)(v4 + 24) && !v19->ByteCount )
      {
        v20 = *v18;
        if ( *v18 == v19 )
        {
          IoFreeMdl(v19);
          *(_QWORD *)(v4 + 24) = 0;
          *(_QWORD *)(v4 + 32) = v4 + 24;
        }
        else
        {
          while ( v20->Next )
          {
            if ( v20->Next == v19 )
            {
              IoFreeMdl(v19);
              v20->Next = 0;
              *(_QWORD *)(v4 + 32) = v20;
              break;
            }
            v20 = v20->Next;
          }
        }
      }
      if ( (*(_DWORD *)v10 & 1) == 0 )
        break;
      if ( *(int *)v10 < 0 )
      {
        *(_BYTE *)(v4 + 87) = 1;
        v21 = *(PMDL *)(v10 + 16);
        if ( v21->ByteCount == v14 )
        {
          *(_QWORD *)(v10 + 16) = 0;
          if ( (BYTE2(xmmword_1400875E0) & 4) != 0 )
            WPP_SF_qqD(1042, 17, WPP_854aaf7e57ed31daf99bd98e8a0637b6_Traceguids, v4, v21, v21->ByteCount);
          *(_QWORD *)&v48 = v10 + 8;
        }
        else
        {
          *(_QWORD *)&v48 = v10 + 8;
          v22 = IoAllocateMdl(*(PVOID *)(v10 + 8), v14, 0, 0, 0);
          v21 = v22;
          if ( !v22 )
            goto LABEL_25;
          IoBuildPartialMdl(*(PMDL *)(v10 + 16), v22, *(PVOID *)v48, v14);
          if ( (BYTE2(xmmword_1400875E0) & 4) != 0 )
            WPP_SF_qqD(1042, 18, WPP_854aaf7e57ed31daf99bd98e8a0637b6_Traceguids, v4, v21, v21->ByteCount);
        }
        v23 = (PVOID *)v48;
        goto LABEL_76;
      }
      RequestorProcess = IoGetRequestorProcess((PIRP)a1);
      if ( IoGetCurrentProcess() != RequestorProcess )
      {
        KeAttachProcess(RequestorProcess);
        if ( (BYTE2(xmmword_1400875E0) & 4) != 0 )
          WPP_SF_qq(1042, 19, WPP_854aaf7e57ed31daf99bd98e8a0637b6_Traceguids, v4, RequestorProcess);
        v59 = 1;
      }
      if ( v14 <= AfdTPacketsCopyThreshold )
      {
        if ( (*(_DWORD *)v10 & 0x40000000) == 0 || v3 != -1073741802 )
        {
          Entry = 0;
          LODWORD(v48) = v14 + (v47 != 0 ? v60 : 0);
          Entry = (PVOID)AfdGetBuffer((unsigned int)v48);
          v26 = (char *)*((_QWORD *)Entry + 14);
          v52 = v26;
          v27 = v47;
          if ( v47 )
          {
            while ( v27 != v10 )
            {
              v28 = *(unsigned int *)(v27 + 4);
              v29 = *(void **)(v27 + 8);
              if ( *(_BYTE *)(a1 + 64) )
                RtlCopyFromUser(v26, v29, v28);
              else
                RtlCopyVolatileMemory(v26, v29, v28);
              v26 += *(unsigned int *)(v47 + 4);
              v52 = v26;
              v27 = v47 + 24;
              v47 = v27;
              v53 = v27;
            }
            v47 = 0;
            v53 = 0;
          }
          v23 = (PVOID *)(v10 + 8);
          v30 = *v23;
          if ( *(_BYTE *)(a1 + 64) )
            RtlCopyFromUser(v26, v30, v14);
          else
            RtlCopyVolatileMemory(v26, v30, v14);
          v31 = Entry;
          *((_QWORD *)Entry + 1) = 0;
          *v31 = 0;
          **(_QWORD **)(v4 + 48) = v31;
          *(_QWORD *)(v4 + 48) = v31;
          v21 = (PMDL)v31[7];
          v21->ByteCount = v48;
          if ( (BYTE2(xmmword_1400875E0) & 4) != 0 )
            WPP_SF_qqqL(1042, 22, WPP_854aaf7e57ed31daf99bd98e8a0637b6_Traceguids, v4, v31, v21, v14);
          goto LABEL_76;
        }
        v25 = v14;
        if ( v47 )
          v25 = v14 + v60;
        v60 = v25;
        if ( v47 )
          v10 = v47;
        v47 = v10;
        *(_DWORD *)v48 = v14;
        if ( (BYTE2(xmmword_1400875E0) & 4) != 0 )
          WPP_SF_qD(1042, 21, WPP_854aaf7e57ed31daf99bd98e8a0637b6_Traceguids, v4, v14);
      }
      else
      {
        *(_BYTE *)(v4 + 87) = 1;
        v23 = (PVOID *)(v10 + 8);
        v21 = IoAllocateMdl(*v23, v14, 0, 1u, 0);
        if ( !v21 )
          goto LABEL_25;
        if ( (BYTE2(xmmword_1400875E0) & 4) != 0 )
          WPP_SF_qqqL(1042, 20, WPP_854aaf7e57ed31daf99bd98e8a0637b6_Traceguids, v4, v21, *v23, v14);
        MmProbeAndLockPages(v21, *(_BYTE *)(a1 + 64), IoReadAccess);
LABEL_76:
        **(_QWORD **)(v4 + 32) = v21;
        *(_QWORD *)(v4 + 32) = v21;
        *v23 = (char *)*v23 + v14;
      }
    }
    if ( (*(_DWORD *)(*(_QWORD *)(v10 + 16) + 80LL) & 0x40) == 0 )
    {
      Buffer = AfdGetBuffer(v14);
      v56 = Buffer;
      if ( !Buffer )
      {
LABEL_25:
        v3 = -1073741670;
        goto LABEL_103;
      }
      if ( (BYTE2(xmmword_1400875E0) & 4) != 0 )
        WPP_SF_qqqLi(v41, 24, v42, v4, Buffer, *(_QWORD *)(Buffer + 56), v14, *(_QWORD *)(v10 + 8), v46);
      *(_QWORD *)(Buffer + 16) = *(_QWORD *)(v10 + 8);
      *(_QWORD *)(Buffer + 8) = *(_QWORD *)(v10 + 16);
      *(_QWORD *)(v10 + 8) += v14;
      *(_DWORD *)(Buffer + 64) = v14;
      *(_DWORD *)(*(_QWORD *)(Buffer + 56) + 40LL) = v14;
      *(_QWORD *)Buffer = 0;
      v43 = *(_WORD *)(Buffer + 96);
      if ( v3 )
        v44 = v43 | 4;
      else
        v44 = v43 & 0xFFFB;
      *(_WORD *)(Buffer + 96) = v44;
      goto LABEL_95;
    }
    v48 = 0;
    *(_BYTE *)(v4 + 87) = 1;
    Buffer = AfdGetBufferTag(0, *(_QWORD *)(v49 + 48), 1);
    v55 = Buffer;
    *(_QWORD *)(Buffer + 16) = *(_QWORD *)(v10 + 8);
    *(_QWORD *)(Buffer + 8) = *(_QWORD *)(v10 + 16);
    *(_QWORD *)(v10 + 8) += v14;
    *(_DWORD *)(Buffer + 64) = v14;
    *(_QWORD *)(Buffer + 56) = 0;
    if ( !(unsigned __int8)FsRtlMdlRead(*(_QWORD *)(Buffer + 8), Buffer + 16, v14, 0, Buffer + 56, &v48) )
    {
      v39 = *(_WORD *)(Buffer + 96);
      if ( v3 )
        v40 = v39 | 4;
      else
        v40 = v39 & 0xFFFB;
      *(_WORD *)(Buffer + 96) = v40;
      *(_QWORD *)Buffer = 0;
LABEL_95:
      *a2 = Buffer;
      v3 = 259;
      goto LABEL_103;
    }
    if ( *((_QWORD *)&v48 + 1) < (unsigned __int64)v14 )
      break;
    if ( (BYTE2(xmmword_1400875E0) & 4) != 0 )
      WPP_SF_qqqLi(v33, 23, v34, v4, Buffer, *(_QWORD *)(Buffer + 56), v14, *(_QWORD *)(v10 + 8), v46);
    **(_QWORD **)(v4 + 32) = *(_QWORD *)(Buffer + 56);
    v36 = *(_QWORD ***)(v4 + 32);
    v37 = (_QWORD **)*v36;
    for ( i = (_QWORD *)**v36; i; i = (_QWORD *)*i )
      v37 = (_QWORD **)i;
    *(_QWORD *)(v4 + 32) = v37;
    *(_QWORD *)Buffer = 0;
    **(_QWORD **)(v4 + 48) = Buffer;
    *(_QWORD *)(v4 + 48) = Buffer;
  }
  if ( (int)AfdMdlReadComplete(*(PVOID *)(Buffer + 8)) < 0 )
  {
    v35 = v49;
    if ( _InterlockedIncrement64((volatile signed __int64 *)(v49 + 64)) <= 1 )
      __fastfail(0xEu);
    *(_QWORD *)(Buffer + 48) = v35;
    AfdLRMdlReadComplete((PSLIST_ENTRY)Buffer);
  }
  else
  {
    AfdReturnBuffer((PVOID)Buffer, *(PEPROCESS *)(v49 + 48));
  }
  v3 = -1073741807;
LABEL_103:
  if ( v59 )
  {
    KeDetachProcess();
    if ( (BYTE2(xmmword_1400875E0) & 4) != 0 )
    {
      WPP_SF_q(1042, 25, WPP_854aaf7e57ed31daf99bd98e8a0637b6_Traceguids, v4);
      goto LABEL_106;
    }
  }
  else
  {
LABEL_106:
    if ( (BYTE2(xmmword_1400875E0) & 4) != 0 )
      WPP_SF_qD(1042, 26, WPP_854aaf7e57ed31daf99bd98e8a0637b6_Traceguids, v4, v3);
  }
  return v3;
}

```

## disassembly

```asm
0x1400406dc  mov     [rsp+arg_8], rdx
0x1400406e1  mov     [rsp+arg_0], rcx
0x1400406e6  push    rbx
0x1400406e7  push    rsi
0x1400406e8  push    rdi
0x1400406e9  push    r12
0x1400406eb  push    r13
0x1400406ed  push    r14
0x1400406ef  push    r15
0x1400406f1  sub     rsp, 0B0h
0x1400406f8  mov     r15, rcx
0x1400406fb  mov     esi, 0C0000016h
0x140040700  mov     [rsp+0E8h+var_A8], esi
0x140040704  xor     edi, edi
0x140040706  mov     [rsp+0E8h+arg_10], dil
0x14004070e  mov     rbx, [rcx+18h]
0x140040712  mov     [rsp+0E8h+var_80], rbx
0x140040717  mov     rax, [rcx+0B8h]
0x14004071e  mov     r8, [rax+30h]
0x140040722  mov     rax, [r8+18h]
0x140040726  mov     [rsp+0E8h+var_88], rax
0x14004072b  mov     [rsp+0E8h+var_58], rax
0x140040733  mov     [rsp+0E8h+var_A0], rdi
0x140040738  mov     [rsp+0E8h+arg_18], edi
0x14004073f  mov     eax, [rcx+80h]
0x140040745  test    al, 40h
0x140040747  jz      short loc_14004079F
0x140040749  test    al, al
0x14004074b  js      short loc_14004077F
0x14004074d  lea     rdx, [rbx+60h]
0x140040751  mov     rcx, [rbx+10h]
0x140040755  call    AfdQueryISB
0x14004075a  mov     ecx, [r15+80h]
0x140040761  test    eax, eax
0x140040763  jns     short loc_140040774
0x140040765  and     ecx, 0FFFFFFBFh
0x140040768  mov     [r15+80h], ecx
0x14004076f  mov     [rbx+60h], edi
0x140040772  jmp     short loc_14004077F
0x140040774  bts     ecx, 7
0x140040778  mov     [r15+80h], ecx
0x14004077f  movzx   ecx, word ptr [rbx+54h]
0x140040783  xor     edx, edx
0x140040785  mov     eax, [rbx+60h]
0x140040788  div     ecx
0x14004078a  cmp     eax, [rbx+5Ch]
0x14004078d  jz      short loc_14004079F
0x14004078f  cmp     eax, [rbx+58h]
0x140040792  jbe     short loc_14004079F
0x140040794  cmp     eax, cs:AfdTransmitIoLength
0x14004079a  jbe     short loc_14004079F
0x14004079c  mov     [rbx+5Ch], eax
0x14004079f  mov     r13w, 4
0x1400407a4  cmp     esi, 0C0000016h
0x1400407aa  jnz     loc_140040FBE
0x1400407b0  mov     eax, [rbx+48h]
0x1400407b3  lea     rcx, [rax+rax*2]
0x1400407b7  mov     rax, [rbx+40h]
0x1400407bb  lea     r15, [rax+rcx*8]
0x1400407bf  test    byte ptr cs:xmmword_1400875E0+2, r13b
0x1400407c6  jz      short loc_1400407E6
0x1400407c8  mov     edx, 0Dh
0x1400407cd  mov     ecx, 412h
0x1400407d2  mov     [rsp+0E8h+Irp], r15
0x1400407d7  mov     r9, rbx
0x1400407da  lea     r8, WPP_854aaf7e57ed31daf99bd98e8a0637b6_Traceguids
0x1400407e1  call    WPP_SF_qq
0x1400407e6  lea     r14, [r15+4]
0x1400407ea  mov     qword ptr [rsp+0E8h+var_98], r14
0x1400407ef  mov     eax, [r14]
0x1400407f2  mov     ecx, [rbx+58h]
0x1400407f5  mov     r8d, [rbx+5Ch]
0x1400407f9  mov     r12d, r8d
0x1400407fc  sub     r12d, ecx
0x1400407ff  cmp     eax, r12d
0x140040802  jbe     short loc_14004081F
0x140040804  mov     esi, edi
0x140040806  mov     [rsp+0E8h+var_A8], edi
0x14004080a  test    byte ptr cs:xmmword_1400875E0+2, r13b
0x140040811  jz      short loc_14004086B
0x140040813  mov     edx, 0Eh
0x140040818  mov     dword ptr [rsp+0E8h+Irp], r8d
0x14004081d  jmp     short loc_140040857
0x14004081f  mov     r12d, eax
0x140040822  inc     dword ptr [rbx+48h]
0x140040825  mov     r9d, [rbx+48h]
0x140040829  add     eax, ecx
0x14004082b  cmp     eax, r8d
0x14004082e  jz      short loc_14004083E
0x140040830  mov     eax, [r15]
0x140040833  test    r13b, al
0x140040836  jnz     short loc_14004083E
0x140040838  cmp     r9d, [rbx+4Ch]
0x14004083c  jb      short loc_14004086B
0x14004083e  mov     esi, edi
0x140040840  mov     [rsp+0E8h+var_A8], edi
0x140040844  test    byte ptr cs:xmmword_1400875E0+2, r13b
0x14004084b  jz      short loc_14004086B
0x14004084d  mov     edx, 0Fh
0x140040852  mov     dword ptr [rsp+0E8h+Irp], r9d
0x140040857  mov     r9, rbx
0x14004085a  lea     r8, WPP_854aaf7e57ed31daf99bd98e8a0637b6_Traceguids
0x140040861  mov     ecx, 412h
0x140040866  call    WPP_SF_qD
0x14004086b  sub     [r14], r12d
0x14004086e  add     [rbx+58h], r12d
0x140040872  test    r12d, r12d
0x140040875  jnz     loc_140040913
0x14004087b  cmp     [rsp+0E8h+var_A0], rdi
0x140040880  jnz     loc_140040913
0x140040886  lea     rax, [rbx+18h]
0x14004088a  cmp     [rbx+20h], rax
0x14004088e  jnz     loc_1400407A4
0x140040894  mov     byte ptr [rbx+57h], 1
0x140040898  mov     [rsp+0E8h+Irp], rdi; Irp
0x14004089d  xor     r9d, r9d; ChargeQuota
0x1400408a0  xor     r8d, r8d; SecondaryBuffer
0x1400408a3  lea     edx, [r12+1]; Length
0x1400408a8  mov     rcx, rbx; VirtualAddress
0x1400408ab  call    cs:__imp_IoAllocateMdl
0x1400408b2  nop     dword ptr [rax+rax+00h]
0x1400408b7  mov     r14, rax
0x1400408ba  test    rax, rax
0x1400408bd  jnz     short loc_1400408C9
0x1400408bf  mov     esi, 0C000009Ah
0x1400408c4  jmp     loc_140040FBE
0x1400408c9  mov     rcx, r14; MemoryDescriptorList
0x1400408cc  call    cs:__imp_MmBuildMdlForNonPagedPool
0x1400408d3  nop     dword ptr [rax+rax+00h]
0x1400408d8  mov     [r14+28h], edi
0x1400408dc  test    byte ptr cs:xmmword_1400875E0+2, r13b
0x1400408e3  jz      short loc_140040903
0x1400408e5  mov     edx, 10h
0x1400408ea  mov     ecx, 412h
0x1400408ef  mov     [rsp+0E8h+Irp], r14
0x1400408f4  mov     r9, rbx
0x1400408f7  lea     r8, WPP_854aaf7e57ed31daf99bd98e8a0637b6_Traceguids
0x1400408fe  call    WPP_SF_qq
0x140040903  mov     rax, [rbx+20h]
0x140040907  mov     [rax], r14
0x14004090a  mov     [rbx+20h], r14
0x14004090e  jmp     loc_1400407A4
0x140040913  lea     rax, [rbx+18h]
0x140040917  mov     rcx, [rbx+20h]; Mdl
0x14004091b  cmp     rcx, rax
0x14004091e  jz      short loc_14004096B
0x140040920  cmp     [rcx+28h], edi
0x140040923  jnz     short loc_14004096B
0x140040925  mov     r14, [rax]
0x140040928  cmp     r14, rcx
0x14004092b  jnz     short loc_140040946
0x14004092d  call    cs:__imp_IoFreeMdl
0x140040934  nop     dword ptr [rax+rax+00h]
0x140040939  lea     rax, [rbx+18h]
0x14004093d  mov     [rax], rdi
0x140040940  mov     [rbx+20h], rax
0x140040944  jmp     short loc_14004096B
0x140040946  mov     rax, [r14]
0x140040949  test    rax, rax
0x14004094c  jz      short loc_14004096B
0x14004094e  cmp     rax, rcx
0x140040951  jz      short loc_140040958
0x140040953  mov     r14, rax
0x140040956  jmp     short loc_140040946
0x140040958  call    cs:__imp_IoFreeMdl
0x14004095f  nop     dword ptr [rax+rax+00h]
0x140040964  mov     [r14], rdi
0x140040967  mov     [rbx+20h], r14
0x14004096b  mov     eax, [r15]
0x14004096e  test    al, 1
0x140040970  jz      loc_140040D56
0x140040976  test    eax, eax
0x140040978  jns     loc_140040A62
0x14004097e  mov     byte ptr [rbx+57h], 1
0x140040982  mov     r14, [r15+10h]
0x140040986  cmp     [r14+28h], r12d
0x14004098a  jnz     short loc_1400409CD
0x14004098c  mov     [r15+10h], rdi
0x140040990  test    byte ptr cs:xmmword_1400875E0+2, r13b
0x140040997  jz      short loc_1400409BF
0x140040999  mov     edx, 11h
0x14004099e  mov     ecx, 412h
0x1400409a3  mov     eax, [r14+28h]
0x1400409a7  mov     dword ptr [rsp+0E8h+var_C0], eax
0x1400409ab  mov     [rsp+0E8h+Irp], r14
0x1400409b0  mov     r9, rbx
0x1400409b3  lea     r8, WPP_854aaf7e57ed31daf99bd98e8a0637b6_Traceguids
0x1400409ba  call    WPP_SF_qqD
0x1400409bf  lea     r8, [r15+8]
0x1400409c3  mov     qword ptr [rsp+0E8h+var_98], r8
0x1400409c8  jmp     loc_140040A58
0x1400409cd  lea     rax, [r15+8]
0x1400409d1  mov     qword ptr [rsp+0E8h+var_98], rax
0x1400409d6  mov     [rsp+0E8h+Irp], rdi; Irp
0x1400409db  xor     r9d, r9d; ChargeQuota
0x1400409de  xor     r8d, r8d; SecondaryBuffer
0x1400409e1  mov     edx, r12d; Length
0x1400409e4  mov     rcx, [rax]; VirtualAddress
0x1400409e7  call    cs:__imp_IoAllocateMdl
0x1400409ee  nop     dword ptr [rax+rax+00h]
0x1400409f3  mov     r14, rax
0x1400409f6  test    rax, rax
0x1400409f9  jz      loc_1400408BF
0x1400409ff  mov     r9d, r12d; Length
0x140040a02  mov     r8, qword ptr [rsp+0E8h+var_98]
0x140040a07  mov     r8, [r8]; VirtualAddress
0x140040a0a  mov     rdx, rax; TargetMdl
0x140040a0d  mov     rcx, [r15+10h]; SourceMdl
0x140040a11  call    cs:__imp_IoBuildPartialMdl
0x140040a18  nop     dword ptr [rax+rax+00h]
0x140040a1d  test    byte ptr cs:xmmword_1400875E0+2, r13b
0x140040a24  jz      short loc_140040A4E
0x140040a26  mov     edx, 12h
0x140040a2b  mov     ecx, 412h
0x140040a30  mov     eax, [r14+28h]
0x140040a34  mov     dword ptr [rsp+0E8h+var_C0], eax
0x140040a38  mov     [rsp+0E8h+Irp], r14
0x140040a3d  mov     r9, rbx
0x140040a40  lea     r8, WPP_854aaf7e57ed31daf99bd98e8a0637b6_Traceguids
0x140040a47  call    WPP_SF_qqD
0x140040a4c  jmp     short loc_140040A58
0x140040a4e  mov     rax, qword ptr [rsp+0E8h+var_98]
0x140040a53  mov     qword ptr [rsp+0E8h+var_98], rax
0x140040a58  mov     r15, qword ptr [rsp+0E8h+var_98]
0x140040a5d  jmp     loc_140040D10
0x140040a62  mov     rcx, [rsp+0E8h+arg_0]; Irp
0x140040a6a  call    cs:__imp_IoGetRequestorProcess
0x140040a71  nop     dword ptr [rax+rax+00h]
0x140040a76  mov     r14, rax
0x140040a79  call    cs:__imp_IoGetCurrentProcess
0x140040a80  nop     dword ptr [rax+rax+00h]
0x140040a85  cmp     rax, r14
0x140040a88  jz      short loc_140040AC8
0x140040a8a  mov     rcx, r14; Process
0x140040a8d  call    cs:__imp_KeAttachProcess
0x140040a94  nop     dword ptr [rax+rax+00h]
0x140040a99  test    byte ptr cs:xmmword_1400875E0+2, r13b
0x140040aa0  jz      short loc_140040AC0
0x140040aa2  mov     edx, 13h
0x140040aa7  mov     ecx, 412h
0x140040aac  mov     [rsp+0E8h+Irp], r14
0x140040ab1  mov     r9, rbx
0x140040ab4  lea     r8, WPP_854aaf7e57ed31daf99bd98e8a0637b6_Traceguids
0x140040abb  call    WPP_SF_qq
0x140040ac0  mov     [rsp+0E8h+arg_10], 1
0x140040ac8  cmp     r12d, cs:AfdTPacketsCopyThreshold
0x140040acf  jbe     loc_140040B73
0x140040ad5  mov     byte ptr [rbx+57h], 1
0x140040ad9  add     r15, 8
0x140040add  mov     [rsp+0E8h+Irp], rdi; Irp
0x140040ae2  mov     r9b, 1; ChargeQuota
0x140040ae5  xor     r8d, r8d; SecondaryBuffer
0x140040ae8  mov     edx, r12d; Length
0x140040aeb  mov     rcx, [r15]; VirtualAddress
0x140040aee  call    cs:__imp_IoAllocateMdl
0x140040af5  nop     dword ptr [rax+rax+00h]
0x140040afa  mov     r14, rax
0x140040afd  test    rax, rax
0x140040b00  jz      loc_1400408BF
0x140040b06  test    byte ptr cs:xmmword_1400875E0+2, r13b
0x140040b0d  jz      short loc_140040B3B
0x140040b0f  mov     edx, 14h
0x140040b14  mov     ecx, 412h
0x140040b19  mov     [rsp+0E8h+var_B8], r12d
0x140040b1e  mov     rax, [r15]
0x140040b21  mov     [rsp+0E8h+var_C0], rax
0x140040b26  mov     [rsp+0E8h+Irp], r14
0x140040b2b  mov     r9, rbx
0x140040b2e  lea     r8, WPP_854aaf7e57ed31daf99bd98e8a0637b6_Traceguids
0x140040b35  call    WPP_SF_qqqL
0x140040b3a  nop
0x140040b3b  xor     r8d, r8d; Operation
0x140040b3e  mov     rax, [rsp+0E8h+arg_0]
0x140040b46  mov     dl, [rax+40h]; AccessMode
0x140040b49  mov     rcx, r14; MemoryDescriptorList
0x140040b4c  call    cs:__imp_MmProbeAndLockPages
0x140040b53  nop     dword ptr [rax+rax+00h]
0x140040b58  nop
0x140040b59  jmp     loc_140040D10
0x140040b5e  xor     edi, edi
0x140040b60  mov     r13w, 4
0x140040b65  mov     esi, [rsp+0E8h+var_A8]
0x140040b69  mov     rbx, [rsp+0E8h+var_80]
0x140040b6e  jmp     loc_140040FBE
0x140040b73  test    dword ptr [r15], 40000000h
0x140040b7a  jz      short loc_140040BE4
0x140040b7c  cmp     esi, 0C0000016h
0x140040b82  jnz     short loc_140040BE4
0x140040b84  mov     eax, [rsp+0E8h+arg_18]
0x140040b8b  add     eax, r12d
0x140040b8e  mov     edx, r12d
0x140040b91  mov     rcx, [rsp+0E8h+var_A0]
0x140040b96  test    rcx, rcx
0x140040b99  cmovnz  edx, eax
0x140040b9c  mov     [rsp+0E8h+arg_18], edx
0x140040ba3  cmovnz  r15, rcx
0x140040ba7  mov     [rsp+0E8h+var_A0], r15
0x140040bac  mov     rax, qword ptr [rsp+0E8h+var_98]
0x140040bb1  mov     [rax], r12d
0x140040bb4  test    byte ptr cs:xmmword_1400875E0+2, r13b
  ... truncated ...
```
