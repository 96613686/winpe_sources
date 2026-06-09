# BampThrottlingRegisterProcessEx

- ea: `0x140012530`
- end: `0x140012c16`
- name: `BampThrottlingRegisterProcessEx`
- size: `1766`
- prototype: `__int64 __fastcall(PVOID Object)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x140012420`
- `0x140014f90`

## callees

- `0x1400014f8`
- `0x1400026d0`
- `0x1400027c0`
- `0x140002ac0`
- `0x140012530`
- `0x1400143ec`
- `0x14001474c`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x140012ae4`
- `ntoskrnl!EtwWriteTransfer` at `0x140012ae4`
- `ntoskrnl!ExAllocatePool2` at `0x140012632`
- `ntoskrnl!ExAllocatePool2` at `0x140012632`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012b45`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012b67`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012bbe`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012b45`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012b67`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012bbe`
- `ntoskrnl!ZwClose` at `0x140012b31`
- `ntoskrnl!ZwClose` at `0x140012baa`
- `ntoskrnl!ZwClose` at `0x140012bdd`
- `ntoskrnl!ZwClose` at `0x140012b31`
- `ntoskrnl!ZwClose` at `0x140012baa`
- `ntoskrnl!ZwClose` at `0x140012bdd`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400125d3`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400125d3`
- `ntoskrnl!PsProcessType` at `0x140012585`
- `ntoskrnl!PsGetProcessSessionId` at `0x1400128e1`
- `ntoskrnl!PsGetProcessSessionId` at `0x1400128e1`
- `ntoskrnl!ZwQueryInformationProcess` at `0x1400128a5`
- `ntoskrnl!ZwQueryInformationProcess` at `0x1400128a5`
- `ntoskrnl!ExUnsubscribeWnfStateChange` at `0x140012b1c`
- `ntoskrnl!ExUnsubscribeWnfStateChange` at `0x140012b95`
- `ntoskrnl!ExUnsubscribeWnfStateChange` at `0x140012b1c`
- `ntoskrnl!ExUnsubscribeWnfStateChange` at `0x140012b95`

## pseudocode

```c
__int64 __fastcall BampThrottlingRegisterProcessEx(_DWORD *Object, __int64 a2, __int64 a3, _QWORD *a4)
{
  _DWORD *v4; // r12
  int v6; // ebx
  __int64 v7; // r14
  const void **v8; // r15
  char *v9; // rsi
  NTSTATUS v10; // edi
  char v11; // r12
  int v12; // eax
  char *Pool2; // rax
  int v14; // r10d
  const void *v15; // rdx
  __int16 v16; // r9
  unsigned __int64 v17; // rax
  unsigned __int64 v18; // rcx
  __int16 v19; // ax
  unsigned __int64 v20; // r8
  HANDLE v21; // rdi
  __int64 v22; // rax
  unsigned __int64 v23; // rdi
  unsigned __int64 v24; // rcx
  unsigned __int64 v25; // rdx
  __int16 v26; // ax
  unsigned __int64 v27; // rcx
  __int16 v28; // ax
  __int16 v29; // ax
  void *v30; // rcx
  __int64 v31; // rcx
  __int128 v32; // xmm1
  __int128 v33; // xmm0
  int ProcessSessionId; // eax
  int v35; // r9d
  int started; // eax
  __int16 v37; // r9
  __int64 *v38; // rcx
  signed __int64 v39; // rax
  bool v40; // cc
  signed __int64 v41; // rax
  void *v42; // rcx
  signed __int64 v43; // rbx
  signed __int64 v44; // rbx
  void *v45; // rcx
  char v47[4]; // [rsp+40h] [rbp-C0h] BYREF
  int v48; // [rsp+44h] [rbp-BCh] BYREF
  __int128 v49; // [rsp+50h] [rbp-B0h]
  __int64 v50; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE Handle; // [rsp+68h] [rbp-98h] BYREF
  __int128 v52; // [rsp+70h] [rbp-90h] BYREF
  NTSTATUS v53; // [rsp+80h] [rbp-80h] BYREF
  int v54; // [rsp+84h] [rbp-7Ch] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+88h] [rbp-78h] BYREF
  __int128 v56; // [rsp+A0h] [rbp-60h] BYREF
  __int128 ProcessInformation; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v58; // [rsp+C0h] [rbp-40h]
  __int128 v59; // [rsp+D0h] [rbp-30h]
  __int64 v60; // [rsp+E0h] [rbp-20h] BYREF
  int v61; // [rsp+E8h] [rbp-18h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+F0h] [rbp-10h] BYREF
  void *v63; // [rsp+100h] [rbp+0h]
  int v64; // [rsp+108h] [rbp+8h]
  int v65; // [rsp+10Ch] [rbp+Ch]
  int *v66; // [rsp+110h] [rbp+10h]
  __int64 v67; // [rsp+118h] [rbp+18h]
  NTSTATUS *v68; // [rsp+120h] [rbp+20h]
  __int64 v69; // [rsp+128h] [rbp+28h]
  _DWORD *v70; // [rsp+130h] [rbp+30h]
  __int64 v71; // [rsp+138h] [rbp+38h]
  __int64 v72; // [rsp+140h] [rbp+40h]
  _DWORD v73[2]; // [rsp+148h] [rbp+48h] BYREF
  int *v74; // [rsp+150h] [rbp+50h]
  __int64 v75; // [rsp+158h] [rbp+58h]
  char *v76; // [rsp+160h] [rbp+60h]
  __int64 v77; // [rsp+168h] [rbp+68h]
  __int64 *v78; // [rsp+170h] [rbp+70h]
  __int64 v79; // [rsp+178h] [rbp+78h]
  __int128 *v80; // [rsp+180h] [rbp+80h]
  __int64 v81; // [rsp+188h] [rbp+88h]
  __int64 *v82; // [rsp+190h] [rbp+90h]
  __int64 v83; // [rsp+198h] [rbp+98h]

  *(_QWORD *)&v49 = Object;
  v60 = 0;
  v4 = Object;
  v61 = 0;
  *(_QWORD *)&EventDescriptor.Id = a2;
  v6 = 0;
  v7 = 0;
  v8 = 0;
  v47[0] = 0;
  v9 = 0;
  v50 = 0;
  *(_QWORD *)&v52 = 0;
  Handle = 0;
  v56 = 0;
  v48 = 3;
  v10 = ObOpenObjectByPointer(Object, 0x200u, 0, 0x1FFFFFu, (POBJECT_TYPE)PsProcessType, 0, &Handle);
  if ( v10 < 0 )
    goto LABEL_6;
  BampIsProcessModern(v4, v47);
  v11 = v47[0];
  v12 = BampQueryProcessIdentifier((struct _KPROCESS *)v49, Handle, v47[0], &v52);
  v8 = (const void **)v52;
  v10 = v12;
  if ( v12 < 0 )
  {
LABEL_5:
    v4 = (_DWORD *)v49;
LABEL_6:
    v14 = v48;
    goto LABEL_7;
  }
  Pool2 = (char *)ExAllocatePool2(256, *(unsigned __int16 *)(v52 + 2) + 792LL, 1265459522);
  v9 = Pool2;
  if ( !Pool2 )
  {
    v10 = -1073741801;
    goto LABEL_5;
  }
  v21 = Handle;
  memset(Pool2, 0, 0x318u);
  *((_QWORD *)v9 + 13) = v21;
  *((_DWORD *)v9 + 72) = 1;
  *((_QWORD *)v9 + 5) = v9 + 32;
  *((_QWORD *)v9 + 4) = v9 + 32;
  *((_QWORD *)v9 + 2) = 0;
  *((_QWORD *)v9 + 21) = 0;
  *((_QWORD *)v9 + 22) = 0;
  *((_QWORD *)v9 + 23) = 0;
  *((_QWORD *)v9 + 24) = 1;
  *((_QWORD *)v9 + 25) = 0;
  *((_QWORD *)v9 + 26) = 0;
  *((_QWORD *)v9 + 27) = 0;
  *((_DWORD *)v9 + 56) = 1;
  *((_DWORD *)v9 + 57) = 1;
  *((_QWORD *)v9 + 29) = 0;
  *((_QWORD *)v9 + 30) = 0;
  *((_QWORD *)v9 + 31) = 0;
  v22 = v49;
  *((_DWORD *)v9 + 64) = 1;
  *((_DWORD *)v9 + 65) = 2;
  *((_QWORD *)v9 + 1) = v22;
  LODWORD(v22) = _InterlockedIncrement(&BampThrottledProcessSequenceNumber);
  *((_DWORD *)v9 + 91) = 0;
  *((_DWORD *)v9 + 68) = v22;
  if ( v8 && *(_WORD *)v8 )
  {
    v23 = (unsigned __int64)(v9 + 784);
    memmove(v9 + 784, v8[1], *(unsigned __int16 *)v8);
    *((_QWORD *)v9 + 12) = v9 + 784;
    v24 = *(unsigned __int16 *)v8;
    *((_WORD *)v9 + 44) = v24;
    *((_WORD *)v9 + 45) = *(_WORD *)v8;
    v52 = 0;
    v25 = (unsigned __int64)&v9[2 * (v24 >> 1) + 784];
    if ( v25 > (unsigned __int64)(v9 + 784) )
    {
      while ( 1 )
      {
        v26 = *(_WORD *)(v25 - 2);
        v27 = v25;
        v25 -= 2LL;
        if ( v26 == 92 || v26 == 47 )
          break;
        if ( v25 <= v23 )
          goto LABEL_22;
      }
      v25 = v27;
    }
LABEL_22:
    v28 = *((_WORD *)v9 + 44);
    *((_QWORD *)&v52 + 1) = v25;
    LOWORD(v52) = v28 - 2 * ((__int64)(v25 - v23) >> 1);
    WORD1(v52) = v52;
    *(_OWORD *)(v9 + 72) = v52;
  }
  v29 = *((_WORD *)v9 + 138);
  *((_QWORD *)v9 + 33) = 1;
  v59 = 0;
  *(_QWORD *)((char *)&v59 + 4) = 0x6000000060LL;
  *((_WORD *)v9 + 138) = v29 & 0xFFFD | (2 * (v11 & 1));
  Handle = 0;
  v30 = (void *)*((_QWORD *)v9 + 13);
  ProcessInformation = 0;
  v58 = 0;
  v10 = ZwQueryInformationProcess(v30, ProcessEnableAlignmentFaultFixup|0x40, &ProcessInformation, 0x30u, 0);
  v4 = (_DWORD *)v49;
  if ( v10 < 0 )
    goto LABEL_6;
  v31 = v49;
  v32 = v58;
  *(_OWORD *)(v9 + 120) = ProcessInformation;
  v33 = v59;
  *(_OWORD *)(v9 + 136) = v32;
  *(_OWORD *)(v9 + 152) = v33;
  ProcessSessionId = PsGetProcessSessionId(v31);
  started = BampStartThrottledProcessInformation(
              (_DWORD)v9,
              *(_DWORD *)&EventDescriptor.Id,
              ProcessSessionId,
              v35,
              (__int64)&v50);
  v7 = v50;
  v10 = started;
  if ( started < 0 )
    goto LABEL_6;
  v6 = *(_DWORD *)(v50 + 376);
  v60 = *(_QWORD *)(v50 + 380);
  v61 = *(_DWORD *)(v50 + 388);
  v14 = *(_DWORD *)(v50 + 324);
  if ( a4 )
  {
    *a4 = v50;
    v7 = 0;
  }
  v10 = 0;
LABEL_7:
  if ( dword_140007010 )
  {
    if ( v8 )
    {
      v15 = v8[1];
      v16 = *(_WORD *)v8;
      v17 = (unsigned __int64)*(unsigned __int16 *)v8 >> 1;
      v49 = 0;
      v18 = (unsigned __int64)v15 + 2 * v17;
      if ( v18 > (unsigned __int64)v15 )
      {
        while ( 1 )
        {
          v19 = *(_WORD *)(v18 - 2);
          v20 = v18;
          v18 -= 2LL;
          if ( v19 == 92 || v19 == 47 )
            break;
          if ( v18 <= (unsigned __int64)v15 )
            goto LABEL_29;
        }
        v18 = v20;
      }
LABEL_29:
      *((_QWORD *)&v49 + 1) = v18;
      v37 = v16 - 2 * ((__int64)(v18 - (_QWORD)v15) >> 1);
      v38 = (__int64 *)&v56;
      LOWORD(v49) = v37;
      WORD1(v49) = v37;
      v56 = v49;
    }
    else
    {
      v38 = &BampEmptyString;
    }
    if ( (unsigned int)dword_140007010 > 4 )
    {
      v48 = v4[116];
      v67 = 4;
      v66 = &v48;
      v53 = v10;
      v68 = &v53;
      v70 = v73;
      v72 = v38[1];
      v73[0] = *(unsigned __int16 *)v38;
      v74 = &v54;
      *(_WORD *)v47 = 3;
      v76 = v47;
      v78 = &v60;
      v80 = &v52;
      LODWORD(v50) = *(_DWORD *)&EventDescriptor.Id;
      v82 = &v50;
      *(_DWORD *)&EventDescriptor.Level = 4;
      UserData.Ptr = (ULONGLONG)off_140007018;
      v69 = 4;
      v71 = 2;
      v73[1] = 0;
      v54 = v6;
      v75 = 4;
      v77 = 2;
      v79 = 12;
      LODWORD(v52) = v14;
      v81 = 4;
      v83 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 0;
      UserData.Size = *(unsigned __int16 *)off_140007018;
      v63 = &unk_1400057E0;
      UserData.Reserved = 2;
      v64 = 116;
      v65 = 1;
      LODWORD(v49) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 0xBu, &UserData);
    }
  }
  if ( v7 )
  {
    v39 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v7 + 264), 0xFFFFFFFFFFFFFFFFuLL);
    v40 = v39 <= 1;
    v41 = v39 - 1;
    if ( v40 )
    {
      if ( v41 )
        __fastfail(0xEu);
      if ( *(_QWORD *)(v7 + 112) )
        ExUnsubscribeWnfStateChange();
      v42 = *(void **)(v7 + 104);
      if ( v42 )
        ZwClose(v42);
      ExFreePoolWithTag((PVOID)v7, 0x4B6D6142u);
    }
  }
  if ( v8 )
    ExFreePoolWithTag(v8, 0x4B6D6142u);
  if ( v9 )
  {
    v43 = _InterlockedExchangeAdd64((volatile signed __int64 *)v9 + 33, 0xFFFFFFFFFFFFFFFFuLL);
    v40 = v43 <= 1;
    v44 = v43 - 1;
    if ( v40 )
    {
      if ( v44 )
        __fastfail(0xEu);
      if ( *((_QWORD *)v9 + 14) )
        ExUnsubscribeWnfStateChange();
      v45 = (void *)*((_QWORD *)v9 + 13);
      if ( v45 )
        ZwClose(v45);
      ExFreePoolWithTag(v9, 0x4B6D6142u);
    }
  }
  if ( Handle )
    ZwClose(Handle);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140012530  mov     [rsp-8+arg_10], rbx
0x140012535  push    rbp
0x140012536  push    rsi
0x140012537  push    rdi
0x140012538  push    r12
0x14001253a  push    r13
0x14001253c  push    r14
0x14001253e  push    r15
0x140012540  lea     rbp, [rsp-0B0h]
0x140012548  sub     rsp, 1B0h
0x14001254f  mov     rax, cs:__security_cookie
0x140012556  xor     rax, rsp
0x140012559  mov     [rbp+0E0h+var_40], rax
0x140012560  xor     eax, eax
0x140012562  mov     qword ptr [rsp+1E0h+var_190], rcx
0x140012567  mov     [rbp+0E0h+var_100], rax
0x14001256b  mov     r12, rcx
0x14001256e  mov     [rbp+0E0h+var_F8], eax
0x140012571  mov     r13, r9
0x140012574  lea     rax, [rsp+1E0h+var_178]
0x140012579  mov     qword ptr [rbp+0E0h+EventDescriptor.Id], rdx
0x14001257d  mov     [rsp+1E0h+Handle], rax; Handle
0x140012582  xorps   xmm0, xmm0
0x140012585  mov     rax, cs:__imp_PsProcessType
0x14001258c  xor     ebx, ebx
0x14001258e  mov     [rsp+1E0h+AccessMode], bl; AccessMode
0x140012592  xor     r14d, r14d
0x140012595  xor     r15d, r15d
0x140012598  mov     [rsp+1E0h+var_1A0], 0
0x14001259d  xor     esi, esi
0x14001259f  mov     [rsp+1E0h+var_180], r14
0x1400125a4  mov     rcx, [rax]
0x1400125a7  mov     r9d, 1FFFFFh; DesiredAccess
0x1400125ad  mov     [rsp+1E0h+ObjectType], rcx; ObjectType
0x1400125b2  xor     r8d, r8d; PassedAccessState
0x1400125b5  mov     rcx, r12; Object
0x1400125b8  mov     qword ptr [rsp+1E0h+var_170], r15
0x1400125bd  mov     edx, 200h; HandleAttributes
0x1400125c2  mov     [rsp+1E0h+var_178], rsi
0x1400125c7  movups  [rbp+0E0h+var_140], xmm0
0x1400125cb  mov     [rsp+1E0h+var_19C], 3
0x1400125d3  call    cs:__imp_ObOpenObjectByPointer
0x1400125da  nop     dword ptr [rax+rax+00h]
0x1400125df  mov     edi, eax
0x1400125e1  test    eax, eax
0x1400125e3  js      short loc_140012654
0x1400125e5  lea     rdx, [rsp+1E0h+var_1A0]
0x1400125ea  mov     rcx, r12
0x1400125ed  call    BampIsProcessModern
0x1400125f2  movzx   r12d, [rsp+1E0h+var_1A0]
0x1400125f8  lea     r9, [rsp+1E0h+var_170]
0x1400125fd  mov     rdx, [rsp+1E0h+var_178]
0x140012602  movzx   r8d, r12b
0x140012606  mov     rcx, qword ptr [rsp+1E0h+var_190]
0x14001260b  call    BampQueryProcessIdentifier
0x140012610  mov     r15, qword ptr [rsp+1E0h+var_170]
0x140012615  mov     edi, eax
0x140012617  test    eax, eax
0x140012619  js      short loc_14001264F
0x14001261b  movzx   edx, word ptr [r15+2]
0x140012620  mov     ecx, 100h
0x140012625  add     rdx, 318h
0x14001262c  mov     r8d, 4B6D6142h
0x140012632  call    cs:__imp_ExAllocatePool2
0x140012639  nop     dword ptr [rax+rax+00h]
0x14001263e  mov     rsi, rax
0x140012641  test    rax, rax
0x140012644  jnz     loc_1400126C9
0x14001264a  mov     edi, 0C0000017h
0x14001264f  mov     r12, qword ptr [rsp+1E0h+var_190]
0x140012654  mov     r10d, [rsp+1E0h+var_19C]
0x140012659  xor     r11d, r11d
0x14001265c  mov     eax, cs:dword_140007010
0x140012662  test    eax, eax
0x140012664  jz      loc_140012AF0
0x14001266a  test    r15, r15
0x14001266d  jz      loc_140012983
0x140012673  mov     rdx, [r15+8]
0x140012677  xorps   xmm0, xmm0
0x14001267a  movzx   r9d, word ptr [r15]
0x14001267e  mov     eax, r9d
0x140012681  shr     rax, 1
0x140012684  movups  [rsp+1E0h+var_190], xmm0
0x140012689  lea     rcx, [rdx+rax*2]
0x14001268d  cmp     rcx, rdx
0x140012690  jbe     loc_140012955
0x140012696  nop     word ptr [rax+rax+00000000h]
0x1400126a0  movzx   eax, word ptr [rcx-2]
0x1400126a4  mov     r8, rcx
0x1400126a7  sub     rcx, 2
0x1400126ab  cmp     ax, 5Ch ; '\'
0x1400126af  jz      loc_140012952
0x1400126b5  cmp     ax, 2Fh ; '/'
0x1400126b9  jz      loc_140012952
0x1400126bf  cmp     rcx, rdx
0x1400126c2  ja      short loc_1400126A0
0x1400126c4  jmp     loc_140012955
0x1400126c9  mov     rdi, [rsp+1E0h+var_178]
0x1400126ce  xor     edx, edx; Val
0x1400126d0  mov     r8d, 318h; Size
0x1400126d6  mov     rcx, rsi; void *
0x1400126d9  call    memset
0x1400126de  mov     [rsi+68h], rdi
0x1400126e2  lea     rax, [rsi+20h]
0x1400126e6  mov     dword ptr [rsi+120h], 1
0x1400126f0  xor     r8d, r8d
0x1400126f3  mov     [rax+8], rax
0x1400126f7  mov     [rax], rax
0x1400126fa  mov     [rsi+10h], r8
0x1400126fe  mov     [rsi+0A8h], r8
0x140012705  mov     [rsi+0B0h], r8
0x14001270c  mov     [rsi+0B8h], r8
0x140012713  mov     qword ptr [rsi+0C0h], 1
0x14001271e  mov     [rsi+0C8h], r8
0x140012725  mov     [rsi+0D0h], r8
0x14001272c  mov     [rsi+0D8h], r8
0x140012733  mov     dword ptr [rsi+0E0h], 1
0x14001273d  mov     dword ptr [rsi+0E4h], 1
0x140012747  mov     [rsi+0E8h], r8
0x14001274e  mov     [rsi+0F0h], r8
0x140012755  mov     [rsi+0F8h], r8
0x14001275c  mov     rax, qword ptr [rsp+1E0h+var_190]
0x140012761  mov     dword ptr [rsi+100h], 1
0x14001276b  mov     dword ptr [rsi+104h], 2
0x140012775  mov     [rsi+8], rax
0x140012779  mov     eax, 1
0x14001277e  lock xadd cs:BampThrottledProcessSequenceNumber, eax
0x140012786  inc     eax
0x140012788  mov     [rsi+16Ch], r8d
0x14001278f  mov     [rsi+110h], eax
0x140012795  test    r15, r15
0x140012798  jz      loc_14001283C
0x14001279e  movzx   eax, word ptr [r15]
0x1400127a2  test    ax, ax
0x1400127a5  jz      loc_14001283C
0x1400127ab  mov     rdx, [r15+8]; Src
0x1400127af  lea     rdi, [rsi+310h]
0x1400127b6  mov     rcx, rdi; void *
0x1400127b9  mov     r8d, eax; Size
0x1400127bc  call    memmove
0x1400127c1  mov     [rsi+60h], rdi
0x1400127c5  xorps   xmm0, xmm0
0x1400127c8  movzx   ecx, word ptr [r15]
0x1400127cc  mov     [rsi+58h], cx
0x1400127d0  movzx   eax, word ptr [r15]
0x1400127d4  shr     rcx, 1
0x1400127d7  mov     [rsi+5Ah], ax
0x1400127db  movups  [rsp+1E0h+var_170], xmm0
0x1400127e0  lea     rdx, [rdi+rcx*2]
0x1400127e4  cmp     rdx, rdi
0x1400127e7  jbe     short loc_140012811
0x1400127e9  nop     dword ptr [rax+00000000h]
0x1400127f0  movzx   eax, word ptr [rdx-2]
0x1400127f4  mov     rcx, rdx
0x1400127f7  sub     rdx, 2
0x1400127fb  cmp     ax, 5Ch ; '\'
0x1400127ff  jz      short loc_14001280E
0x140012801  cmp     ax, 2Fh ; '/'
0x140012805  jz      short loc_14001280E
0x140012807  cmp     rdx, rdi
0x14001280a  ja      short loc_1400127F0
0x14001280c  jmp     short loc_140012811
0x14001280e  mov     rdx, rcx
0x140012811  movzx   eax, word ptr [rsi+58h]
0x140012815  mov     qword ptr [rsp+1E0h+var_170+8], rdx
0x14001281a  sub     rdx, rdi
0x14001281d  sar     rdx, 1
0x140012820  add     dx, dx
0x140012823  sub     ax, dx
0x140012826  mov     word ptr [rsp+1E0h+var_170], ax
0x14001282b  xor     r8d, r8d
0x14001282e  mov     word ptr [rsp+1E0h+var_170+2], ax
0x140012833  movups  xmm0, [rsp+1E0h+var_170]
0x140012838  movups  xmmword ptr [rsi+48h], xmm0
0x14001283c  movzx   eax, word ptr [rsi+114h]
0x140012843  xorps   xmm0, xmm0
0x140012846  mov     edx, 0FFFDh
0x14001284b  mov     qword ptr [rsi+108h], 1
0x140012856  and     ax, dx
0x140012859  mov     [rsp+1E0h+ObjectType], r8; ReturnLength
0x14001285e  movups  [rbp+0E0h+var_110], xmm0
0x140012862  and     r12b, 1
0x140012866  mov     dword ptr [rbp+0E0h+var_110+8], 60h ; '`'
0x14001286d  movzx   ecx, r12b
0x140012871  mov     r9d, 30h ; '0'; ProcessInformationLength
0x140012877  add     cx, cx
0x14001287a  mov     dword ptr [rbp+0E0h+var_110+4], 60h ; '`'
0x140012881  or      cx, ax
0x140012884  mov     edx, 51h ; 'Q'; ProcessInformationClass
0x140012889  mov     [rsi+114h], cx
0x140012890  mov     [rsp+1E0h+var_178], r8
0x140012895  lea     r8, [rbp+0E0h+ProcessInformation]; ProcessInformation
0x140012899  mov     rcx, [rsi+68h]; ProcessHandle
0x14001289d  movups  [rbp+0E0h+ProcessInformation], xmm0
0x1400128a1  movups  [rbp+0E0h+var_120], xmm0
0x1400128a5  call    cs:__imp_ZwQueryInformationProcess
0x1400128ac  nop     dword ptr [rax+rax+00h]
0x1400128b1  mov     edi, eax
0x1400128b3  mov     r12, qword ptr [rsp+1E0h+var_190]
0x1400128b8  test    eax, eax
0x1400128ba  js      loc_140012654
0x1400128c0  movups  xmm0, [rbp+0E0h+ProcessInformation]
0x1400128c4  mov     rcx, r12
0x1400128c7  movups  xmm1, [rbp+0E0h+var_120]
0x1400128cb  movups  xmmword ptr [rsi+78h], xmm0
0x1400128cf  movups  xmm0, [rbp+0E0h+var_110]
0x1400128d3  movups  xmmword ptr [rsi+88h], xmm1
0x1400128da  movups  xmmword ptr [rsi+98h], xmm0
0x1400128e1  call    cs:__imp_PsGetProcessSessionId
0x1400128e8  nop     dword ptr [rax+rax+00h]
0x1400128ed  mov     rdx, qword ptr [rbp+0E0h+EventDescriptor.Id]
0x1400128f1  mov     rcx, rsi
0x1400128f4  mov     r8d, eax
0x1400128f7  lea     rax, [rsp+1E0h+var_180]
0x1400128fc  mov     [rsp+1E0h+ObjectType], rax
0x140012901  call    BampStartThrottledProcessInformation
0x140012906  mov     r14, [rsp+1E0h+var_180]
0x14001290b  mov     edi, eax
0x14001290d  test    eax, eax
0x14001290f  js      loc_140012654
0x140012915  movsd   xmm0, qword ptr [r14+17Ch]
0x14001291e  xor     r11d, r11d
0x140012921  mov     ebx, [r14+178h]
0x140012928  movsd   [rbp+0E0h+var_100], xmm0
0x14001292d  mov     eax, [r14+184h]
0x140012934  mov     [rbp+0E0h+var_F8], eax
0x140012937  mov     r10d, [r14+144h]
0x14001293e  test    r13, r13
0x140012941  jz      short loc_14001294A
0x140012943  mov     [r13+0], r14
0x140012947  mov     r14d, r11d
0x14001294a  mov     edi, r11d
0x14001294d  jmp     loc_14001265C
0x140012952  mov     rcx, r8
0x140012955  mov     qword ptr [rsp+1E0h+var_190+8], rcx
0x14001295a  sub     rcx, rdx
0x14001295d  sar     rcx, 1
0x140012960  add     cx, cx
0x140012963  sub     r9w, cx
0x140012967  lea     rcx, [rbp+0E0h+var_140]
0x14001296b  mov     word ptr [rsp+1E0h+var_190], r9w
0x140012971  mov     word ptr [rsp+1E0h+var_190+2], r9w
0x140012977  movaps  xmm0, [rsp+1E0h+var_190]
0x14001297c  movdqa  [rbp+0E0h+var_140], xmm0
0x140012981  jmp     short loc_14001298A
0x140012983  lea     rcx, BampEmptyString
0x14001298a  mov     eax, cs:dword_140007010
0x140012990  cmp     eax, 4
0x140012993  jbe     loc_140012AF0
0x140012999  mov     eax, [r12+1D0h]
0x1400129a1  lea     rdx, [rbp+0E0h+EventDescriptor]; EventDescriptor
0x1400129a5  mov     [rsp+1E0h+var_19C], eax
0x1400129a9  xor     r9d, r9d; RelatedActivityId
0x1400129ac  lea     rax, [rsp+1E0h+var_19C]
0x1400129b1  mov     [rbp+0E0h+var_C8], 4
0x1400129b9  mov     [rbp+0E0h+var_D0], rax
0x1400129bd  xor     r8d, r8d; ActivityId
0x1400129c0  lea     rax, [rbp+0E0h+var_160]
0x1400129c4  mov     [rbp+0E0h+var_160], edi
0x1400129c7  mov     [rbp+0E0h+var_C0], rax
0x1400129cb  lea     rax, [rbp+0E0h+var_98]
0x1400129cf  mov     [rbp+0E0h+var_B0], rax
0x1400129d3  mov     rax, [rcx+8]
0x1400129d7  mov     [rbp+0E0h+var_A0], rax
0x1400129db  movzx   eax, word ptr [rcx]
0x1400129de  lea     rcx, _TraceLoggingMetadata
0x1400129e5  mov     [rbp+0E0h+var_98], eax
0x1400129e8  lea     rax, [rbp+0E0h+var_15C]
0x1400129ec  mov     [rbp+0E0h+var_90], rax
0x1400129f0  mov     eax, 3
0x1400129f5  mov     word ptr [rsp+1E0h+var_1A0], ax
0x1400129fa  lea     rax, [rsp+1E0h+var_1A0]
0x1400129ff  mov     [rbp+0E0h+var_80], rax
0x140012a03  lea     rax, [rbp+0E0h+var_100]
0x140012a07  mov     [rbp+0E0h+var_70], rax
0x140012a0b  lea     rax, [rsp+1E0h+var_170]
0x140012a10  mov     [rbp+0E0h+var_60], rax
0x140012a17  mov     rax, qword ptr [rbp+0E0h+EventDescriptor.Id]
0x140012a1b  mov     dword ptr [rsp+1E0h+var_180], eax
0x140012a1f  lea     rax, [rsp+1E0h+var_180]
0x140012a24  mov     [rbp+0E0h+var_50], rax
0x140012a2b  movzx   eax, cs:word_1400057D6
0x140012a32  mov     dword ptr [rbp+0E0h+EventDescriptor.Level], eax
0x140012a35  mov     rax, cs:off_140007018
0x140012a3c  mov     [rbp+0E0h+UserData.Ptr], rax
0x140012a40  mov     [rbp+0E0h+var_B8], 4
0x140012a48  mov     [rbp+0E0h+var_A8], 2
0x140012a50  mov     [rbp+0E0h+var_94], r11d
0x140012a54  mov     [rbp+0E0h+var_15C], ebx
0x140012a57  mov     [rbp+0E0h+var_88], 4
0x140012a5f  mov     [rbp+0E0h+var_78], 2
0x140012a67  mov     [rbp+0E0h+var_68], 0Ch
0x140012a6f  mov     dword ptr [rsp+1E0h+var_170], r10d
0x140012a74  mov     [rbp+0E0h+var_58], 4
0x140012a7f  mov     [rbp+0E0h+var_48], 4
0x140012a8a  mov     dword ptr [rbp+0E0h+EventDescriptor.Id], 0B000000h
0x140012a91  mov     [rbp+0E0h+EventDescriptor.Keyword], r11
0x140012a95  movzx   eax, word ptr [rax]
0x140012a98  mov     [rbp+0E0h+UserData.Size], eax
0x140012a9b  lea     rax, unk_1400057E0
  ... truncated ...
```
