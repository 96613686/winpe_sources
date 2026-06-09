# AfdBuildPacketChain

- ea: `0x1400406bc`
- end: `0x140041012`
- name: `AfdBuildPacketChain`
- size: `2390`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x140056e80`

## callees

- `0x140007120`
- `0x14000cbe0`
- `0x140012610`
- `0x14002fd5c`
- `0x1400406bc`
- `0x1400417a4`
- `0x1400445b8`
- `0x140055bbc`
- `0x140066a20`
- `0x1400726d0`
- `0x140093008`
- `0x14009304c`
- `0x1400930cc`
- `0x140093e58`
- `0x140094184`
- `0x140094900`

## import_xrefs

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400408ac`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400408ac`
- `ntoskrnl!IoGetRequestorProcess` at `0x140040a4a`
- `ntoskrnl!IoGetRequestorProcess` at `0x140040a4a`
- `ntoskrnl!KeAttachProcess` at `0x140040a6d`
- `ntoskrnl!KeAttachProcess` at `0x140040a6d`
- `ntoskrnl!FsRtlMdlRead` at `0x140040db2`
- `ntoskrnl!FsRtlMdlRead` at `0x140040db2`
- `ntoskrnl!KeDetachProcess` at `0x140040fa8`
- `ntoskrnl!KeDetachProcess` at `0x140040fa8`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400409f1`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400409f1`
- `ntoskrnl!IoFreeMdl` at `0x14004090d`
- `ntoskrnl!IoFreeMdl` at `0x140040938`
- `ntoskrnl!IoFreeMdl` at `0x14004090d`
- `ntoskrnl!IoFreeMdl` at `0x140040938`
- `ntoskrnl!MmProbeAndLockPages` at `0x140040b2c`
- `ntoskrnl!MmProbeAndLockPages` at `0x140040b2c`
- `ntoskrnl!IoAllocateMdl` at `0x14004088b`
- `ntoskrnl!IoAllocateMdl` at `0x1400409c7`
- `ntoskrnl!IoAllocateMdl` at `0x140040ace`
- `ntoskrnl!IoAllocateMdl` at `0x14004088b`
- `ntoskrnl!IoAllocateMdl` at `0x1400409c7`
- `ntoskrnl!IoAllocateMdl` at `0x140040ace`
- `ntoskrnl!IoGetCurrentProcess` at `0x140040a59`
- `ntoskrnl!IoGetCurrentProcess` at `0x140040a59`

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
  __int64 v46; // [rsp+48h] [rbp-A0h]
  __int128 v47; // [rsp+50h] [rbp-98h] BYREF
  __int64 v48; // [rsp+60h] [rbp-88h]
  __int64 v49; // [rsp+68h] [rbp-80h]
  PVOID Entry; // [rsp+70h] [rbp-78h]
  char *v51; // [rsp+80h] [rbp-68h]
  __int64 v52; // [rsp+88h] [rbp-60h]
  __int64 v53; // [rsp+90h] [rbp-58h]
  __int64 v54; // [rsp+98h] [rbp-50h]
  __int64 v55; // [rsp+A0h] [rbp-48h]
  char v58; // [rsp+100h] [rbp+18h]
  ULONG v59; // [rsp+108h] [rbp+20h]

  v3 = -1073741802;
  v58 = 0;
  v4 = *(_QWORD *)(a1 + 24);
  v49 = v4;
  v48 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 184) + 48LL) + 24LL);
  v53 = v48;
  v46 = 0;
  v59 = 0;
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
            WPP_148169eadf5b37b5a85ea383b1e42419_Traceguids,
            v4,
            v9 + 24LL * *(unsigned int *)(v4 + 72));
        *(_QWORD *)&v47 = v10 + 4;
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
            if ( (BYTE2(xmmword_1400875E0) & 4) != 0 )
              WPP_SF_qD(1042, 15, WPP_148169eadf5b37b5a85ea383b1e42419_Traceguids, v4, v15);
          }
        }
        else
        {
          v3 = 0;
          if ( (BYTE2(xmmword_1400875E0) & 4) != 0 )
            WPP_SF_qD(1042, 14, WPP_148169eadf5b37b5a85ea383b1e42419_Traceguids, v4, v13);
        }
        *(_DWORD *)(v10 + 4) -= v14;
        *(_DWORD *)(v4 + 88) += v14;
        if ( v14 || v46 )
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
            WPP_SF_qq(1042, 16, WPP_148169eadf5b37b5a85ea383b1e42419_Traceguids, v4, v17);
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
            WPP_SF_qqD(1042, 17, WPP_148169eadf5b37b5a85ea383b1e42419_Traceguids, v4, v21, v21->ByteCount);
          *(_QWORD *)&v47 = v10 + 8;
        }
        else
        {
          *(_QWORD *)&v47 = v10 + 8;
          v22 = IoAllocateMdl(*(PVOID *)(v10 + 8), v14, 0, 0, 0);
          v21 = v22;
          if ( !v22 )
            goto LABEL_25;
          IoBuildPartialMdl(*(PMDL *)(v10 + 16), v22, *(PVOID *)v47, v14);
          if ( (BYTE2(xmmword_1400875E0) & 4) != 0 )
            WPP_SF_qqD(1042, 18, WPP_148169eadf5b37b5a85ea383b1e42419_Traceguids, v4, v21, v21->ByteCount);
        }
        v23 = (PVOID *)v47;
        goto LABEL_76;
      }
      RequestorProcess = IoGetRequestorProcess((PIRP)a1);
      if ( IoGetCurrentProcess() != RequestorProcess )
      {
        KeAttachProcess(RequestorProcess);
        if ( (BYTE2(xmmword_1400875E0) & 4) != 0 )
          WPP_SF_qq(1042, 19, WPP_148169eadf5b37b5a85ea383b1e42419_Traceguids, v4, RequestorProcess);
        v58 = 1;
      }
      if ( v14 <= AfdTPacketsCopyThreshold )
      {
        if ( (*(_DWORD *)v10 & 0x40000000) == 0 || v3 != -1073741802 )
        {
          Entry = 0;
          LODWORD(v47) = v14 + (v46 != 0 ? v59 : 0);
          Entry = (PVOID)AfdGetBuffer((unsigned int)v47, 0, *(struct _KPROCESS **)(v48 + 48), 1);
          v26 = (char *)*((_QWORD *)Entry + 14);
          v51 = v26;
          v27 = v46;
          if ( v46 )
          {
            while ( v27 != v10 )
            {
              v28 = *(unsigned int *)(v27 + 4);
              v29 = *(void **)(v27 + 8);
              if ( *(_BYTE *)(a1 + 64) )
                RtlCopyFromUser(v26, v29, v28);
              else
                RtlCopyVolatileMemory(v26, v29, v28);
              v26 += *(unsigned int *)(v46 + 4);
              v51 = v26;
              v27 = v46 + 24;
              v46 = v27;
              v52 = v27;
            }
            v46 = 0;
            v52 = 0;
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
          v21->ByteCount = v47;
          if ( (BYTE2(xmmword_1400875E0) & 4) != 0 )
            WPP_SF_qqqL(1042, 22, WPP_148169eadf5b37b5a85ea383b1e42419_Traceguids, v4, v31, v21, v14);
          goto LABEL_76;
        }
        v25 = v14;
        if ( v46 )
          v25 = v14 + v59;
        v59 = v25;
        if ( v46 )
          v10 = v46;
        v46 = v10;
        *(_DWORD *)v47 = v14;
        if ( (BYTE2(xmmword_1400875E0) & 4) != 0 )
          WPP_SF_qD(1042, 21, WPP_148169eadf5b37b5a85ea383b1e42419_Traceguids, v4, v14);
      }
      else
      {
        *(_BYTE *)(v4 + 87) = 1;
        v23 = (PVOID *)(v10 + 8);
        v21 = IoAllocateMdl(*v23, v14, 0, 1u, 0);
        if ( !v21 )
          goto LABEL_25;
        if ( (BYTE2(xmmword_1400875E0) & 4) != 0 )
          WPP_SF_qqqL(1042, 20, WPP_148169eadf5b37b5a85ea383b1e42419_Traceguids, v4, v21, *v23, v14);
        MmProbeAndLockPages(v21, *(_BYTE *)(a1 + 64), IoReadAccess);
LABEL_76:
        **(_QWORD **)(v4 + 32) = v21;
        *(_QWORD *)(v4 + 32) = v21;
        *v23 = (char *)*v23 + v14;
      }
    }
    if ( (*(_DWORD *)(*(_QWORD *)(v10 + 16) + 80LL) & 0x40) == 0 )
    {
      Buffer = AfdGetBuffer(v14, 0, *(struct _KPROCESS **)(v48 + 48), 1);
      v55 = Buffer;
      if ( !Buffer )
      {
LABEL_25:
        v3 = -1073741670;
        goto LABEL_103;
      }
      if ( (BYTE2(xmmword_1400875E0) & 4) != 0 )
        WPP_SF_qqqLi(v41, 24, v42, v4, Buffer, *(_QWORD *)(Buffer + 56), v14, *(_QWORD *)(v10 + 8));
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
    v47 = 0;
    *(_BYTE *)(v4 + 87) = 1;
    Buffer = (__int64)AfdGetBufferTag(0, *(struct _KPROCESS **)(v48 + 48), 1);
    v54 = Buffer;
    *(_QWORD *)(Buffer + 16) = *(_QWORD *)(v10 + 8);
    *(_QWORD *)(Buffer + 8) = *(_QWORD *)(v10 + 16);
    *(_QWORD *)(v10 + 8) += v14;
    *(_DWORD *)(Buffer + 64) = v14;
    *(_QWORD *)(Buffer + 56) = 0;
    if ( !(unsigned __int8)FsRtlMdlRead(*(_QWORD *)(Buffer + 8), Buffer + 16, v14, 0, Buffer + 56, &v47) )
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
    if ( *((_QWORD *)&v47 + 1) < (unsigned __int64)v14 )
      break;
    if ( (BYTE2(xmmword_1400875E0) & 4) != 0 )
      WPP_SF_qqqLi(v33, 23, v34, v4, Buffer, *(_QWORD *)(Buffer + 56), v14, *(_QWORD *)(v10 + 8));
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
    v35 = v48;
    if ( _InterlockedIncrement64((volatile signed __int64 *)(v48 + 64)) <= 1 )
      __fastfail(0xEu);
    *(_QWORD *)(Buffer + 48) = v35;
    AfdLRMdlReadComplete((PSLIST_ENTRY)Buffer);
  }
  else
  {
    AfdReturnBuffer((unsigned __int16 *)Buffer, *(PEPROCESS *)(v48 + 48));
  }
  v3 = -1073741807;
LABEL_103:
  if ( v58 )
  {
    KeDetachProcess();
    if ( (BYTE2(xmmword_1400875E0) & 4) != 0 )
    {
      WPP_SF_q(1042, 25, WPP_148169eadf5b37b5a85ea383b1e42419_Traceguids, v4);
      goto LABEL_106;
    }
  }
  else
  {
LABEL_106:
    if ( (BYTE2(xmmword_1400875E0) & 4) != 0 )
      WPP_SF_qD(1042, 26, WPP_148169eadf5b37b5a85ea383b1e42419_Traceguids, v4, v3);
  }
  return v3;
}

```

## disassembly

```asm
0x1400406bc  mov     [rsp+arg_8], rdx
0x1400406c1  mov     [rsp+arg_0], rcx
0x1400406c6  push    rbx
0x1400406c7  push    rsi
0x1400406c8  push    rdi
0x1400406c9  push    r12
0x1400406cb  push    r13
0x1400406cd  push    r14
0x1400406cf  push    r15
0x1400406d1  sub     rsp, 0B0h
0x1400406d8  mov     r15, rcx
0x1400406db  mov     esi, 0C0000016h
0x1400406e0  mov     [rsp+0E8h+var_A8], esi
0x1400406e4  xor     edi, edi
0x1400406e6  mov     [rsp+0E8h+arg_10], dil
0x1400406ee  mov     rbx, [rcx+18h]
0x1400406f2  mov     [rsp+0E8h+var_80], rbx
0x1400406f7  mov     rax, [rcx+0B8h]
0x1400406fe  mov     r8, [rax+30h]
0x140040702  mov     rax, [r8+18h]
0x140040706  mov     [rsp+0E8h+var_88], rax
0x14004070b  mov     [rsp+0E8h+var_58], rax
0x140040713  mov     [rsp+0E8h+var_A0], rdi
0x140040718  mov     [rsp+0E8h+arg_18], edi
0x14004071f  mov     eax, [rcx+80h]
0x140040725  test    al, 40h
0x140040727  jz      short loc_14004077F
0x140040729  test    al, al
0x14004072b  js      short loc_14004075F
0x14004072d  lea     rdx, [rbx+60h]
0x140040731  mov     rcx, [rbx+10h]
0x140040735  call    AfdQueryISB
0x14004073a  mov     ecx, [r15+80h]
0x140040741  test    eax, eax
0x140040743  jns     short loc_140040754
0x140040745  and     ecx, 0FFFFFFBFh
0x140040748  mov     [r15+80h], ecx
0x14004074f  mov     [rbx+60h], edi
0x140040752  jmp     short loc_14004075F
0x140040754  bts     ecx, 7
0x140040758  mov     [r15+80h], ecx
0x14004075f  movzx   ecx, word ptr [rbx+54h]
0x140040763  xor     edx, edx
0x140040765  mov     eax, [rbx+60h]
0x140040768  div     ecx
0x14004076a  cmp     eax, [rbx+5Ch]
0x14004076d  jz      short loc_14004077F
0x14004076f  cmp     eax, [rbx+58h]
0x140040772  jbe     short loc_14004077F
0x140040774  cmp     eax, cs:AfdTransmitIoLength
0x14004077a  jbe     short loc_14004077F
0x14004077c  mov     [rbx+5Ch], eax
0x14004077f  mov     r13w, 4
0x140040784  cmp     esi, 0C0000016h
0x14004078a  jnz     loc_140040F9E
0x140040790  mov     eax, [rbx+48h]
0x140040793  lea     rcx, [rax+rax*2]
0x140040797  mov     rax, [rbx+40h]
0x14004079b  lea     r15, [rax+rcx*8]
0x14004079f  test    byte ptr cs:xmmword_1400875E0+2, r13b
0x1400407a6  jz      short loc_1400407C6
0x1400407a8  mov     edx, 0Dh
0x1400407ad  mov     ecx, 412h
0x1400407b2  mov     [rsp+0E8h+Irp], r15
0x1400407b7  mov     r9, rbx
0x1400407ba  lea     r8, WPP_148169eadf5b37b5a85ea383b1e42419_Traceguids
0x1400407c1  call    WPP_SF_qq
0x1400407c6  lea     r14, [r15+4]
0x1400407ca  mov     qword ptr [rsp+0E8h+var_98], r14
0x1400407cf  mov     eax, [r14]
0x1400407d2  mov     ecx, [rbx+58h]
0x1400407d5  mov     r8d, [rbx+5Ch]
0x1400407d9  mov     r12d, r8d
0x1400407dc  sub     r12d, ecx
0x1400407df  cmp     eax, r12d
0x1400407e2  jbe     short loc_1400407FF
0x1400407e4  mov     esi, edi
0x1400407e6  mov     [rsp+0E8h+var_A8], edi
0x1400407ea  test    byte ptr cs:xmmword_1400875E0+2, r13b
0x1400407f1  jz      short loc_14004084B
0x1400407f3  mov     edx, 0Eh
0x1400407f8  mov     dword ptr [rsp+0E8h+Irp], r8d
0x1400407fd  jmp     short loc_140040837
0x1400407ff  mov     r12d, eax
0x140040802  inc     dword ptr [rbx+48h]
0x140040805  mov     r9d, [rbx+48h]
0x140040809  add     eax, ecx
0x14004080b  cmp     eax, r8d
0x14004080e  jz      short loc_14004081E
0x140040810  mov     eax, [r15]
0x140040813  test    r13b, al
0x140040816  jnz     short loc_14004081E
0x140040818  cmp     r9d, [rbx+4Ch]
0x14004081c  jb      short loc_14004084B
0x14004081e  mov     esi, edi
0x140040820  mov     [rsp+0E8h+var_A8], edi
0x140040824  test    byte ptr cs:xmmword_1400875E0+2, r13b
0x14004082b  jz      short loc_14004084B
0x14004082d  mov     edx, 0Fh
0x140040832  mov     dword ptr [rsp+0E8h+Irp], r9d
0x140040837  mov     r9, rbx
0x14004083a  lea     r8, WPP_148169eadf5b37b5a85ea383b1e42419_Traceguids
0x140040841  mov     ecx, 412h
0x140040846  call    WPP_SF_qD
0x14004084b  sub     [r14], r12d
0x14004084e  add     [rbx+58h], r12d
0x140040852  test    r12d, r12d
0x140040855  jnz     loc_1400408F3
0x14004085b  cmp     [rsp+0E8h+var_A0], rdi
0x140040860  jnz     loc_1400408F3
0x140040866  lea     rax, [rbx+18h]
0x14004086a  cmp     [rbx+20h], rax
0x14004086e  jnz     loc_140040784
0x140040874  mov     byte ptr [rbx+57h], 1
0x140040878  mov     [rsp+0E8h+Irp], rdi; Irp
0x14004087d  xor     r9d, r9d; ChargeQuota
0x140040880  xor     r8d, r8d; SecondaryBuffer
0x140040883  lea     edx, [r12+1]; Length
0x140040888  mov     rcx, rbx; VirtualAddress
0x14004088b  call    cs:__imp_IoAllocateMdl
0x140040892  nop     dword ptr [rax+rax+00h]
0x140040897  mov     r14, rax
0x14004089a  test    rax, rax
0x14004089d  jnz     short loc_1400408A9
0x14004089f  mov     esi, 0C000009Ah
0x1400408a4  jmp     loc_140040F9E
0x1400408a9  mov     rcx, r14; MemoryDescriptorList
0x1400408ac  call    cs:__imp_MmBuildMdlForNonPagedPool
0x1400408b3  nop     dword ptr [rax+rax+00h]
0x1400408b8  mov     [r14+28h], edi
0x1400408bc  test    byte ptr cs:xmmword_1400875E0+2, r13b
0x1400408c3  jz      short loc_1400408E3
0x1400408c5  mov     edx, 10h
0x1400408ca  mov     ecx, 412h
0x1400408cf  mov     [rsp+0E8h+Irp], r14
0x1400408d4  mov     r9, rbx
0x1400408d7  lea     r8, WPP_148169eadf5b37b5a85ea383b1e42419_Traceguids
0x1400408de  call    WPP_SF_qq
0x1400408e3  mov     rax, [rbx+20h]
0x1400408e7  mov     [rax], r14
0x1400408ea  mov     [rbx+20h], r14
0x1400408ee  jmp     loc_140040784
0x1400408f3  lea     rax, [rbx+18h]
0x1400408f7  mov     rcx, [rbx+20h]; Mdl
0x1400408fb  cmp     rcx, rax
0x1400408fe  jz      short loc_14004094B
0x140040900  cmp     [rcx+28h], edi
0x140040903  jnz     short loc_14004094B
0x140040905  mov     r14, [rax]
0x140040908  cmp     r14, rcx
0x14004090b  jnz     short loc_140040926
0x14004090d  call    cs:__imp_IoFreeMdl
0x140040914  nop     dword ptr [rax+rax+00h]
0x140040919  lea     rax, [rbx+18h]
0x14004091d  mov     [rax], rdi
0x140040920  mov     [rbx+20h], rax
0x140040924  jmp     short loc_14004094B
0x140040926  mov     rax, [r14]
0x140040929  test    rax, rax
0x14004092c  jz      short loc_14004094B
0x14004092e  cmp     rax, rcx
0x140040931  jz      short loc_140040938
0x140040933  mov     r14, rax
0x140040936  jmp     short loc_140040926
0x140040938  call    cs:__imp_IoFreeMdl
0x14004093f  nop     dword ptr [rax+rax+00h]
0x140040944  mov     [r14], rdi
0x140040947  mov     [rbx+20h], r14
0x14004094b  mov     eax, [r15]
0x14004094e  test    al, 1
0x140040950  jz      loc_140040D36
0x140040956  test    eax, eax
0x140040958  jns     loc_140040A42
0x14004095e  mov     byte ptr [rbx+57h], 1
0x140040962  mov     r14, [r15+10h]
0x140040966  cmp     [r14+28h], r12d
0x14004096a  jnz     short loc_1400409AD
0x14004096c  mov     [r15+10h], rdi
0x140040970  test    byte ptr cs:xmmword_1400875E0+2, r13b
0x140040977  jz      short loc_14004099F
0x140040979  mov     edx, 11h
0x14004097e  mov     ecx, 412h
0x140040983  mov     eax, [r14+28h]
0x140040987  mov     dword ptr [rsp+0E8h+var_C0], eax
0x14004098b  mov     [rsp+0E8h+Irp], r14
0x140040990  mov     r9, rbx
0x140040993  lea     r8, WPP_148169eadf5b37b5a85ea383b1e42419_Traceguids
0x14004099a  call    WPP_SF_qqD
0x14004099f  lea     r8, [r15+8]
0x1400409a3  mov     qword ptr [rsp+0E8h+var_98], r8
0x1400409a8  jmp     loc_140040A38
0x1400409ad  lea     rax, [r15+8]
0x1400409b1  mov     qword ptr [rsp+0E8h+var_98], rax
0x1400409b6  mov     [rsp+0E8h+Irp], rdi; Irp
0x1400409bb  xor     r9d, r9d; ChargeQuota
0x1400409be  xor     r8d, r8d; SecondaryBuffer
0x1400409c1  mov     edx, r12d; Length
0x1400409c4  mov     rcx, [rax]; VirtualAddress
0x1400409c7  call    cs:__imp_IoAllocateMdl
0x1400409ce  nop     dword ptr [rax+rax+00h]
0x1400409d3  mov     r14, rax
0x1400409d6  test    rax, rax
0x1400409d9  jz      loc_14004089F
0x1400409df  mov     r9d, r12d; Length
0x1400409e2  mov     r8, qword ptr [rsp+0E8h+var_98]
0x1400409e7  mov     r8, [r8]; VirtualAddress
0x1400409ea  mov     rdx, rax; TargetMdl
0x1400409ed  mov     rcx, [r15+10h]; SourceMdl
0x1400409f1  call    cs:__imp_IoBuildPartialMdl
0x1400409f8  nop     dword ptr [rax+rax+00h]
0x1400409fd  test    byte ptr cs:xmmword_1400875E0+2, r13b
0x140040a04  jz      short loc_140040A2E
0x140040a06  mov     edx, 12h
0x140040a0b  mov     ecx, 412h
0x140040a10  mov     eax, [r14+28h]
0x140040a14  mov     dword ptr [rsp+0E8h+var_C0], eax
0x140040a18  mov     [rsp+0E8h+Irp], r14
0x140040a1d  mov     r9, rbx
0x140040a20  lea     r8, WPP_148169eadf5b37b5a85ea383b1e42419_Traceguids
0x140040a27  call    WPP_SF_qqD
0x140040a2c  jmp     short loc_140040A38
0x140040a2e  mov     rax, qword ptr [rsp+0E8h+var_98]
0x140040a33  mov     qword ptr [rsp+0E8h+var_98], rax
0x140040a38  mov     r15, qword ptr [rsp+0E8h+var_98]
0x140040a3d  jmp     loc_140040CF0
0x140040a42  mov     rcx, [rsp+0E8h+arg_0]; Irp
0x140040a4a  call    cs:__imp_IoGetRequestorProcess
0x140040a51  nop     dword ptr [rax+rax+00h]
0x140040a56  mov     r14, rax
0x140040a59  call    cs:__imp_IoGetCurrentProcess
0x140040a60  nop     dword ptr [rax+rax+00h]
0x140040a65  cmp     rax, r14
0x140040a68  jz      short loc_140040AA8
0x140040a6a  mov     rcx, r14; Process
0x140040a6d  call    cs:__imp_KeAttachProcess
0x140040a74  nop     dword ptr [rax+rax+00h]
0x140040a79  test    byte ptr cs:xmmword_1400875E0+2, r13b
0x140040a80  jz      short loc_140040AA0
0x140040a82  mov     edx, 13h
0x140040a87  mov     ecx, 412h
0x140040a8c  mov     [rsp+0E8h+Irp], r14
0x140040a91  mov     r9, rbx
0x140040a94  lea     r8, WPP_148169eadf5b37b5a85ea383b1e42419_Traceguids
0x140040a9b  call    WPP_SF_qq
0x140040aa0  mov     [rsp+0E8h+arg_10], 1
0x140040aa8  cmp     r12d, cs:AfdTPacketsCopyThreshold
0x140040aaf  jbe     loc_140040B53
0x140040ab5  mov     byte ptr [rbx+57h], 1
0x140040ab9  add     r15, 8
0x140040abd  mov     [rsp+0E8h+Irp], rdi; Irp
0x140040ac2  mov     r9b, 1; ChargeQuota
0x140040ac5  xor     r8d, r8d; SecondaryBuffer
0x140040ac8  mov     edx, r12d; Length
0x140040acb  mov     rcx, [r15]; VirtualAddress
0x140040ace  call    cs:__imp_IoAllocateMdl
0x140040ad5  nop     dword ptr [rax+rax+00h]
0x140040ada  mov     r14, rax
0x140040add  test    rax, rax
0x140040ae0  jz      loc_14004089F
0x140040ae6  test    byte ptr cs:xmmword_1400875E0+2, r13b
0x140040aed  jz      short loc_140040B1B
0x140040aef  mov     edx, 14h
0x140040af4  mov     ecx, 412h
0x140040af9  mov     [rsp+0E8h+var_B8], r12d
0x140040afe  mov     rax, [r15]
0x140040b01  mov     [rsp+0E8h+var_C0], rax
0x140040b06  mov     [rsp+0E8h+Irp], r14
0x140040b0b  mov     r9, rbx
0x140040b0e  lea     r8, WPP_148169eadf5b37b5a85ea383b1e42419_Traceguids
0x140040b15  call    WPP_SF_qqqL
0x140040b1a  nop
0x140040b1b  xor     r8d, r8d; Operation
0x140040b1e  mov     rax, [rsp+0E8h+arg_0]
0x140040b26  mov     dl, [rax+40h]; AccessMode
0x140040b29  mov     rcx, r14; MemoryDescriptorList
0x140040b2c  call    cs:__imp_MmProbeAndLockPages
0x140040b33  nop     dword ptr [rax+rax+00h]
0x140040b38  nop
0x140040b39  jmp     loc_140040CF0
0x140040b3e  xor     edi, edi
0x140040b40  mov     r13w, 4
0x140040b45  mov     esi, [rsp+0E8h+var_A8]
0x140040b49  mov     rbx, [rsp+0E8h+var_80]
0x140040b4e  jmp     loc_140040F9E
0x140040b53  test    dword ptr [r15], 40000000h
0x140040b5a  jz      short loc_140040BC4
0x140040b5c  cmp     esi, 0C0000016h
0x140040b62  jnz     short loc_140040BC4
0x140040b64  mov     eax, [rsp+0E8h+arg_18]
0x140040b6b  add     eax, r12d
0x140040b6e  mov     edx, r12d
0x140040b71  mov     rcx, [rsp+0E8h+var_A0]
0x140040b76  test    rcx, rcx
0x140040b79  cmovnz  edx, eax
0x140040b7c  mov     [rsp+0E8h+arg_18], edx
0x140040b83  cmovnz  r15, rcx
0x140040b87  mov     [rsp+0E8h+var_A0], r15
0x140040b8c  mov     rax, qword ptr [rsp+0E8h+var_98]
0x140040b91  mov     [rax], r12d
0x140040b94  test    byte ptr cs:xmmword_1400875E0+2, r13b
  ... truncated ...
```
