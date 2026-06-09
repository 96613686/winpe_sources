# FltpCreate

- ea: `0x18006e150`
- end: `0x18006e800`
- name: `FltpCreate`
- size: `1712`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180003380`
- `0x1800044e0`
- `0x180007500`
- `0x180007d80`
- `0x180009f20`
- `0x18000a340`
- `0x180014cf0`
- `0x180015970`
- `0x180016f40`
- `0x18001fd80`
- `0x18005c600`
- `0x180060110`
- `0x180069170`
- `0x18006e150`
- `0x18006ffc0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18006e347`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006e347`
- `ntoskrnl!RtlEqualUnicodeString` at `0x18006e36a`
- `ntoskrnl!RtlEqualUnicodeString` at `0x18006e3ad`
- `ntoskrnl!RtlEqualUnicodeString` at `0x18006e36a`
- `ntoskrnl!RtlEqualUnicodeString` at `0x18006e3ad`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18006e791`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18006e791`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18006e7c5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18006e7c5`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x18006e46f`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x18006e46f`
- `ntoskrnl!FsRtlGetEcpListFromIrp` at `0x18006e42b`
- `ntoskrnl!FsRtlGetEcpListFromIrp` at `0x18006e42b`
- `ntoskrnl!FsRtlIsEcpFromUserMode` at `0x18006e49a`
- `ntoskrnl!FsRtlIsEcpFromUserMode` at `0x18006e49a`
- `ntoskrnl!IofCompleteRequest` at `0x18006e199`
- `ntoskrnl!IofCompleteRequest` at `0x18006e247`
- `ntoskrnl!IofCompleteRequest` at `0x18006e199`
- `ntoskrnl!IofCompleteRequest` at `0x18006e247`

## string_xrefs

- `0x18006e5fe`: `FltpCreate`
- `0x18006e6aa`: `FltpCreate`

## pseudocode

```c
__int64 __fastcall FltpCreate(struct _DEVICE_OBJECT *a1, __int64 a2)
{
  __int128 v2; // rax
  char v3; // r12
  IRP *v4; // rbx
  char v7; // di
  __int64 v8; // r13
  char *v9; // r15
  __int64 v10; // rsi
  __int16 *v11; // rax
  __int64 v12; // rax
  unsigned int DeviceType; // eax
  int v14; // edx
  __int16 v15; // ax
  __int64 v16; // rax
  __int64 v17; // rax
  bool v18; // zf
  int v19; // r8d
  struct _FILE_OBJECT *v20; // rdx
  unsigned int InformationFile; // eax
  unsigned int EcpListFromIrp; // eax
  unsigned int ExtraCreateParameter; // eax
  int v24; // ecx
  struct _IRP *MasterIrp; // rax
  struct _IRP *v26; // rax
  char v27; // al
  int v28; // eax
  bool v29; // zf
  int v30; // eax
  __int64 v31; // rcx
  ULONG Flags; // r9d
  __int64 v33; // r8
  int v34; // ecx
  _WORD *v35; // rdi
  __int64 v36; // rax
  __int64 IrpCtrl; // rdi
  unsigned int v38; // eax
  unsigned int v39; // ebx
  UNICODE_STRING DestinationString; // [rsp+30h] [rbp-50h] BYREF
  __int128 v41; // [rsp+40h] [rbp-40h] BYREF
  ULONG_PTR BugCheckParameter3[2]; // [rsp+50h] [rbp-30h] BYREF
  __int128 v43; // [rsp+60h] [rbp-20h]
  char v44; // [rsp+B0h] [rbp+30h] BYREF
  __int64 EcpContextSize; // [rsp+C0h] [rbp+40h] BYREF
  PVOID EcpContext; // [rsp+C8h] [rbp+48h] BYREF

  *((_QWORD *)&v2 + 1) = a2;
  v3 = 0;
  v4 = (IRP *)*((_QWORD *)&v2 + 1);
  v44 = 0;
  v41 = 0;
  *(_OWORD *)BugCheckParameter3 = 0;
  v43 = 0;
  if ( a1 == DeviceObject )
  {
    *(_QWORD *)(*((_QWORD *)&v2 + 1) + 56LL) = 1;
    *(_DWORD *)(*((_QWORD *)&v2 + 1) + 48LL) = 0;
    IofCompleteRequest(*((PIRP *)&v2 + 1), 0);
    return 0;
  }
  if ( a1 == qword_18003E9B8 )
    return FltpMsgDispatch();
  *(_QWORD *)&v2 = a1->DeviceExtension;
  if ( (_QWORD)v2 && *(_WORD *)v2 == 0xF106 )
    goto LABEL_7;
  *(_QWORD *)&v2 = *(_QWORD *)(v2 + 80);
  v7 = 0;
  v41 = v2;
  *(_QWORD *)&v43 = 0;
  DWORD2(v43) = 0;
  *(__m128i *)BugCheckParameter3 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffff0000000000000000);
  if ( !(_QWORD)v2 )
  {
    *(_DWORD *)(*((_QWORD *)&v2 + 1) + 48LL) = -1073741436;
    *(_QWORD *)(*((_QWORD *)&v2 + 1) + 56LL) = 0;
    IofCompleteRequest(*((PIRP *)&v2 + 1), 0);
    return 3221225860LL;
  }
  if ( (*(_DWORD *)(v2 + 56) & 0x40) == 0 && (*(_DWORD *)(v41 + 56) & 2) == 0 )
  {
LABEL_7:
    ++*(_BYTE *)(*((_QWORD *)&v2 + 1) + 67LL);
    *(_QWORD *)(*((_QWORD *)&v2 + 1) + 184LL) += 72LL;
    return FltpCallDriver(*((PDEVICE_OBJECT *)a1->DeviceExtension + 1), *((PIRP *)&v2 + 1));
  }
  v8 = v41;
  v9 = *(char **)(*((_QWORD *)&v2 + 1) + 184LL);
  DestinationString = 0;
  EcpContextSize = 0;
  v10 = *((_QWORD *)v9 + 6);
  v11 = (__int16 *)(v10 + 88);
  if ( !*(_WORD *)(v10 + 88) )
  {
    v12 = *(_QWORD *)(v10 + 64);
    if ( !v12 || (*(_DWORD *)(v12 + 80) & 0x400000) != 0 )
    {
      DeviceType = a1->DeviceType;
      if ( DeviceType <= 0x11 )
      {
        v14 = 135432;
        if ( _bittest(&v14, DeviceType) )
          goto LABEL_34;
      }
    }
    v11 = (__int16 *)(v10 + 88);
  }
  if ( *(_DWORD *)(v41 + 60) != 2 )
    goto LABEL_35;
  if ( (*((_DWORD *)v9 + 4) & 0x2000) != 0 )
  {
    v15 = *v11;
    if ( v15 == 8 )
    {
      v16 = *(_QWORD *)(v10 + 96);
      if ( *(_DWORD *)v16 != 3 || *(_WORD *)(v16 + 4) )
        goto LABEL_35;
LABEL_34:
      *(_DWORD *)(v10 + 80) |= 0x400000u;
      goto LABEL_35;
    }
    if ( v15 == 10 )
    {
      v17 = *(_QWORD *)(v10 + 96);
      if ( *(_DWORD *)(v17 + 2) == 3 )
      {
        v18 = *(_WORD *)(v17 + 6) == 0;
        goto LABEL_33;
      }
    }
  }
  else
  {
    RtlInitUnicodeString(&DestinationString, L"\\$Volume");
    if ( RtlEqualUnicodeString((PCUNICODE_STRING)(v10 + 88), &DestinationString, (*(_DWORD *)(v10 + 80) & 0x20000) == 0)
      && !*(_QWORD *)(v10 + 64) )
    {
      goto LABEL_34;
    }
    v19 = *(_DWORD *)(v10 + 80);
    ++DestinationString.Buffer;
    DestinationString.Length -= 2;
    DestinationString.MaximumLength -= 2;
    if ( RtlEqualUnicodeString((PCUNICODE_STRING)(v10 + 88), &DestinationString, (v19 & 0x20000) == 0) )
    {
      v20 = *(struct _FILE_OBJECT **)(v10 + 64);
      if ( v20 )
      {
        InformationFile = FltpQueryInformationFile(
                            *(PDEVICE_OBJECT *)(*(_QWORD *)(*(_QWORD *)(v8 + 64) + 64LL) + 8LL),
                            v20,
                            6,
                            0);
        if ( (int)FltpDbgStatus(InformationFile, "minkernel\\fs\\filtermgr\\filter\\fltmgr.c", 5647, 0) >= 0 )
        {
          v18 = (_DWORD)EcpContextSize == 5;
LABEL_33:
          if ( !v18 )
            goto LABEL_35;
          goto LABEL_34;
        }
      }
    }
  }
LABEL_35:
  EcpContext = 0;
  *(_QWORD *)&DestinationString.Length = 0;
  LODWORD(EcpContextSize) = 0;
  EcpListFromIrp = FsRtlGetEcpListFromIrp(v4, (PECP_LIST *)&DestinationString);
  if ( (int)FltpDbgStatus(EcpListFromIrp, "minkernel\\fs\\filtermgr\\filter\\targetediosup.c", 1165, 0) >= 0 )
  {
    if ( *(_QWORD *)&DestinationString.Length )
    {
      ExtraCreateParameter = FsRtlFindExtraCreateParameter(
                               *(PECP_LIST *)&DestinationString.Length,
                               &FLTMGR_TIOCTRL_ECP_GUID,
                               &EcpContext,
                               (ULONG *)&EcpContextSize);
      if ( (int)FltpDbgStatus(ExtraCreateParameter, "minkernel\\fs\\filtermgr\\filter\\targetediosup.c", 1180, 0) >= 0
        && !FsRtlIsEcpFromUserMode(EcpContext) )
      {
        FltpSetUpIrpCallControl((__int64)EcpContext, *(_QWORD *)(v41 + 104), (__int64)&v41, 0, &v44);
        v3 = v44;
      }
    }
  }
  if ( (*(_DWORD *)(v41 + 56) & 0x100) != 0 )
  {
    if ( *v9 == 6 )
    {
      v24 = *((_DWORD *)v9 + 4);
      if ( (unsigned int)(v24 - 19) <= 1 || v24 == 39 )
        goto LABEL_71;
      if ( v24 == 13 )
      {
        MasterIrp = v4->AssociatedIrp.MasterIrp;
        if ( MasterIrp && LOBYTE(MasterIrp->Type) )
          goto LABEL_71;
      }
      else if ( v24 == 64 )
      {
        v26 = v4->AssociatedIrp.MasterIrp;
        if ( v26 )
        {
          if ( (*(_DWORD *)&v26->Type & 1) != 0 )
            goto LABEL_71;
        }
      }
    }
    else if ( *v9 == 4
           && ((v4->Flags & 1) != 0 || (*(_DWORD *)(v41 + 56) & 1) != 0 || *(_DWORD *)(v41 + 60) == 27)
           && (v4->Flags & 0x42) == 0 )
    {
      goto LABEL_71;
    }
    v27 = *v9;
    if ( *v9 )
    {
      if ( v27 == 13 )
      {
        v28 = *((_DWORD *)v9 + 6);
        if ( v28 == 622792 || v28 == 623208 || v28 == 1327346 || v28 == 1343730 )
          goto LABEL_71;
        v29 = v28 == 590047;
      }
      else
      {
        if ( v27 != 14 )
          goto LABEL_70;
        v30 = *((_DWORD *)v9 + 6);
        if ( v30 == 1328152 )
          goto LABEL_71;
        v29 = v30 == 1344540;
      }
      if ( !v29 )
        goto LABEL_70;
    }
    else if ( *((_DWORD *)v9 + 4) >= 0x1000000u )
    {
      goto LABEL_70;
    }
LABEL_71:
    v7 = 1;
    goto LABEL_72;
  }
LABEL_70:
  if ( v3 )
    goto LABEL_71;
LABEL_72:
  if ( !BugCheckParameter3[1] && !v7 )
    goto LABEL_103;
  v31 = *(unsigned int *)(v41 + 56);
  if ( (v31 & 2) != 0 )
  {
    if ( !v3
      || BugCheckParameter3[1] == -1
      || BugCheckParameter3[1]
      && (v31 = *(unsigned int *)(*(_QWORD *)(BugCheckParameter3[1] + 16) + 80LL), (v31 & 4) != 0) )
    {
      if ( (byte_1800404C2 & 0x20) != 0 )
        McTemplateU0s_EtwWriteTransfer(v31, fltmgr_c5947, "FltpCreate");
      FltpDoFilterNotificationForNewVolume(v41);
    }
  }
  if ( !*(_DWORD *)(v41 + 312) )
    goto LABEL_95;
  Flags = v4->Flags;
  v33 = (unsigned __int8)(*v9 + 22);
  if ( *(_QWORD *)(v41 + 16 * (v33 + 20)) == (_QWORD)v41 + 16 * (v33 + 20) )
    goto LABEL_95;
  v34 = *(_DWORD *)(v41 + 4 * v33 + 1120);
  if ( v10 )
  {
    if ( (*(_DWORD *)(v10 + 80) & 0x400000) == 0 && (v34 & 8) != 0 )
      goto LABEL_95;
  }
  if ( (unsigned __int8)(*v9 - 3) > 1u )
    goto LABEL_96;
  if ( (Flags & 2) != 0 && (v34 & 1) != 0 )
  {
LABEL_95:
    if ( v7 )
      goto LABEL_96;
LABEL_103:
    ++v4->CurrentLocation;
    ++v4->Tail.Overlay.CurrentStackLocation;
    return FltpCallDriver(*((PDEVICE_OBJECT *)a1->DeviceExtension + 1), v4);
  }
  if ( (Flags & 1) == 0 )
  {
    if ( (v34 & 2) == 0 )
      goto LABEL_96;
    goto LABEL_95;
  }
  if ( (Flags & 2) == 0 && (v34 & 0x10) != 0 )
    goto LABEL_95;
LABEL_96:
  v35 = (_WORD *)(v10 + 88);
  if ( (byte_1800404C2 & 8) != 0 )
    McTemplateU0spw_EtwWriteTransfer(
      (unsigned __int16)*v35 >> 1,
      (unsigned int)fltmgr_c5985,
      (unsigned int)"FltpCreate",
      v10,
      *v35 >> 1,
      *(_QWORD *)(v10 + 96));
  if ( (*(_DWORD *)(v41 + 56) & 1) != 0 )
  {
    if ( (*((_DWORD *)v9 + 4) & 0x80u) != 0 )
      goto LABEL_103;
    if ( !*v35 )
    {
      v36 = *(_QWORD *)(v10 + 64);
      if ( !v36 || !*(_WORD *)(v36 + 88) )
        goto LABEL_103;
    }
  }
  IrpCtrl = (unsigned int)FltpAllocateIrpCtrl(a1, 1, v4, BugCheckParameter3);
  if ( (int)FltpDbgStatus(IrpCtrl, "minkernel\\fs\\filtermgr\\filter\\fltmgr.c", 6044, 0) < 0 )
    goto LABEL_107;
  *(_DWORD *)(BugCheckParameter3[0] + 4) |= 8u;
  LODWORD(IrpCtrl) = FltpCreatePreserveFileObject(&v41);
  if ( (int)FltpDbgStatus((unsigned int)IrpCtrl, "minkernel\\fs\\filtermgr\\filter\\fltmgr.c", 6075, 0) < 0 )
  {
    FltpFreeIrpCtrl(BugCheckParameter3[0]);
LABEL_107:
    FltpCompleteRequest(v4, (unsigned int)IrpCtrl);
    return (unsigned int)IrpCtrl;
  }
  KeEnterCriticalRegion();
  v38 = FltpPassThroughInternal(&v41, FltDeletePushLock);
  v39 = v38;
  if ( (BYTE8(v43) & 4) != 0 )
    v39 = FltpLegacyProcessingAfterPreCallbacksCompleted(&v41, v38, 0);
  KeLeaveCriticalRegion();
  return v39;
}

```

## disassembly

```asm
0x18006e150  push    rbp
0x18006e152  push    rbx
0x18006e153  push    rdi
0x18006e154  push    r12
0x18006e156  push    r14
0x18006e158  mov     rbp, rsp
0x18006e15b  sub     rsp, 80h
0x18006e162  xorps   xmm0, xmm0
0x18006e165  xor     r12b, r12b
0x18006e168  cmp     rcx, cs:DeviceObject
0x18006e16f  mov     rbx, rdx
0x18006e172  mov     r14, rcx
0x18006e175  mov     [rbp+arg_0], r12b
0x18006e179  movups  [rbp+var_40], xmm0
0x18006e17d  movups  xmmword ptr [rbp+BugCheckParameter3], xmm0
0x18006e181  movups  [rbp+var_20], xmm0
0x18006e185  jnz     short loc_18006E1B7
0x18006e187  mov     qword ptr [rdx+38h], 1
0x18006e18f  xor     edi, edi
0x18006e191  mov     [rdx+30h], edi
0x18006e194  mov     rcx, rbx; Irp
0x18006e197  xor     edx, edx; PriorityBoost
0x18006e199  call    cs:__imp_IofCompleteRequest
0x18006e1a0  nop     dword ptr [rax+rax+00h]
0x18006e1a5  xor     eax, eax
0x18006e1a7  add     rsp, 80h
0x18006e1ae  pop     r14
0x18006e1b0  pop     r12
0x18006e1b2  pop     rdi
0x18006e1b3  pop     rbx
0x18006e1b4  pop     rbp
0x18006e1b5  retn
0x18006e1b7  cmp     r14, cs:qword_18003E9B8
0x18006e1be  jnz     short loc_18006E1D5
0x18006e1c0  call    FltpMsgDispatch
0x18006e1c5  add     rsp, 80h
0x18006e1cc  pop     r14
0x18006e1ce  pop     r12
0x18006e1d0  pop     rdi
0x18006e1d1  pop     rbx
0x18006e1d2  pop     rbp
0x18006e1d3  retn
0x18006e1d5  mov     rax, [rcx+40h]
0x18006e1d9  test    rax, rax
0x18006e1dc  jz      short loc_18006E210
0x18006e1de  mov     ecx, 0F106h
0x18006e1e3  cmp     [rax], cx
0x18006e1e6  jnz     short loc_18006E210
0x18006e1e8  inc     byte ptr [rdx+43h]
0x18006e1eb  add     qword ptr [rdx+0B8h], 48h ; 'H'
0x18006e1f3  mov     rcx, [r14+40h]
0x18006e1f7  mov     rcx, [rcx+8]; DeviceObject
0x18006e1fb  call    FltpCallDriver
0x18006e200  add     rsp, 80h
0x18006e207  pop     r14
0x18006e209  pop     r12
0x18006e20b  pop     rdi
0x18006e20c  pop     rbx
0x18006e20d  pop     rbp
0x18006e20e  retn
0x18006e210  mov     rax, [rax+50h]
0x18006e214  xor     edi, edi
0x18006e216  movdqa  xmm0, cs:__xmm@ffffffffffffffff0000000000000000
0x18006e21e  mov     qword ptr [rbp+var_40], rax
0x18006e222  mov     qword ptr [rbp+var_40+8], rbx
0x18006e226  mov     qword ptr [rbp+var_20], rdi
0x18006e22a  mov     dword ptr [rbp+var_20+8], edi
0x18006e22d  movdqu  xmmword ptr [rbp+BugCheckParameter3], xmm0
0x18006e232  test    rax, rax
0x18006e235  jnz     short loc_18006E268
0x18006e237  mov     dword ptr [rdx+30h], 0C0000184h
0x18006e23e  mov     rcx, rbx; Irp
0x18006e241  mov     [rdx+38h], rdi
0x18006e245  xor     edx, edx; PriorityBoost
0x18006e247  call    cs:__imp_IofCompleteRequest
0x18006e24e  nop     dword ptr [rax+rax+00h]
0x18006e253  mov     eax, 0C0000184h
0x18006e258  add     rsp, 80h
0x18006e25f  pop     r14
0x18006e261  pop     r12
0x18006e263  pop     rdi
0x18006e264  pop     rbx
0x18006e265  pop     rbp
0x18006e266  retn
0x18006e268  mov     eax, [rax+38h]
0x18006e26b  test    al, 40h
0x18006e26d  jnz     short loc_18006E27F
0x18006e26f  mov     rax, qword ptr [rbp+var_40]
0x18006e273  mov     ecx, [rax+38h]
0x18006e276  test    cl, 2
0x18006e279  jz      loc_18006E1E8
0x18006e27f  mov     [rsp+80h+arg_8], rsi
0x18006e287  xorps   xmm0, xmm0
0x18006e28a  mov     [rsp+80h+var_8], r13
0x18006e28f  mov     r13, qword ptr [rbp+var_40]
0x18006e293  mov     [rsp+80h+var_10], r15
0x18006e298  mov     r15, [rdx+0B8h]
0x18006e29f  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18006e2a3  mov     [rbp+EcpContextSize], rdi
0x18006e2a7  mov     rsi, [r15+30h]
0x18006e2ab  lea     rax, [rsi+58h]
0x18006e2af  mov     ecx, [r15+10h]
0x18006e2b3  cmp     [rax], di
0x18006e2b6  jnz     short loc_18006E2E5
0x18006e2b8  mov     rax, [rsi+40h]
0x18006e2bc  test    rax, rax
0x18006e2bf  jz      short loc_18006E2CA
0x18006e2c1  mov     eax, [rax+50h]
0x18006e2c4  bt      eax, 16h
0x18006e2c8  jnb     short loc_18006E2E1
0x18006e2ca  mov     eax, [r14+48h]
0x18006e2ce  cmp     eax, 11h
0x18006e2d1  ja      short loc_18006E2E1
0x18006e2d3  mov     edx, 21108h
0x18006e2d8  bt      edx, eax
0x18006e2db  jb      loc_18006E40F
0x18006e2e1  lea     rax, [rsi+58h]
0x18006e2e5  cmp     dword ptr [r13+3Ch], 2
0x18006e2ea  jnz     loc_18006E419
0x18006e2f0  bt      ecx, 0Dh
0x18006e2f4  jnb     short loc_18006E33C
0x18006e2f6  movzx   eax, word ptr [rax]
0x18006e2f9  cmp     ax, 8
0x18006e2fd  jnz     short loc_18006E31B
0x18006e2ff  mov     rax, [rsi+60h]
0x18006e303  cmp     dword ptr [rax], 3
0x18006e306  jnz     loc_18006E419
0x18006e30c  cmp     [rax+4], di
0x18006e310  jz      loc_18006E40F
0x18006e316  jmp     loc_18006E419
0x18006e31b  cmp     ax, 0Ah
0x18006e31f  jnz     loc_18006E419
0x18006e325  mov     rax, [rsi+60h]
0x18006e329  cmp     dword ptr [rax+2], 3
0x18006e32d  jnz     loc_18006E419
0x18006e333  cmp     [rax+6], di
0x18006e337  jmp     loc_18006E40D
0x18006e33c  lea     rdx, aVolume; "\\$Volume"
0x18006e343  lea     rcx, [rbp+DestinationString]; DestinationString
0x18006e347  call    cs:__imp_RtlInitUnicodeString
0x18006e34e  nop     dword ptr [rax+rax+00h]
0x18006e353  mov     r8d, [rsi+50h]
0x18006e357  lea     rdx, [rbp+DestinationString]; String2
0x18006e35b  shr     r8d, 11h
0x18006e35f  lea     rcx, [rsi+58h]; String1
0x18006e363  not     r8b
0x18006e366  and     r8b, 1; CaseInSensitive
0x18006e36a  call    cs:__imp_RtlEqualUnicodeString
0x18006e371  nop     dword ptr [rax+rax+00h]
0x18006e376  test    al, al
0x18006e378  jz      short loc_18006E384
0x18006e37a  cmp     [rsi+40h], rdi
0x18006e37e  jz      loc_18006E40F
0x18006e384  mov     r8d, [rsi+50h]
0x18006e388  lea     rdx, [rbp+DestinationString]; String2
0x18006e38c  add     [rbp+DestinationString.Buffer], 2
0x18006e391  lea     rcx, [rsi+58h]; String1
0x18006e395  shr     r8d, 11h
0x18006e399  mov     eax, 0FFFEh
0x18006e39e  add     [rbp+DestinationString.Length], ax
0x18006e3a2  not     r8b
0x18006e3a5  add     [rbp+DestinationString.MaximumLength], ax
0x18006e3a9  and     r8b, 1; CaseInSensitive
0x18006e3ad  call    cs:__imp_RtlEqualUnicodeString
0x18006e3b4  nop     dword ptr [rax+rax+00h]
0x18006e3b9  test    al, al
0x18006e3bb  jz      short loc_18006E419
0x18006e3bd  mov     rdx, [rsi+40h]; FileObject
0x18006e3c1  test    rdx, rdx
0x18006e3c4  jz      short loc_18006E419
0x18006e3c6  mov     rax, [r13+40h]
0x18006e3ca  lea     r8, [rbp+EcpContextSize]
0x18006e3ce  mov     [rsp+80h+var_58], rdi; __int64
0x18006e3d3  mov     r9d, 8
0x18006e3d9  mov     [rsp+80h+var_60], 6; int
0x18006e3e1  mov     rcx, [rax+40h]
0x18006e3e5  mov     rcx, [rcx+8]; DeviceObject
0x18006e3e9  call    FltpQueryInformationFile
0x18006e3ee  mov     r8d, 160Fh
0x18006e3f4  lea     rdx, aMinkernelFsFil_28; "minkernel\\fs\\filtermgr\\filter\\fltmg"...
0x18006e3fb  xor     r9d, r9d
0x18006e3fe  mov     ecx, eax
0x18006e400  call    FltpDbgStatus
0x18006e405  test    eax, eax
0x18006e407  js      short loc_18006E419
0x18006e409  cmp     dword ptr [rbp+EcpContextSize], 5
0x18006e40d  jnz     short loc_18006E419
0x18006e40f  mov     eax, [rsi+50h]
0x18006e412  bts     eax, 16h
0x18006e416  mov     [rsi+50h], eax
0x18006e419  lea     rdx, [rbp+DestinationString]; EcpList
0x18006e41d  mov     [rbp+EcpContext], rdi
0x18006e421  mov     rcx, rbx; Irp
0x18006e424  mov     qword ptr [rbp+DestinationString.Length], rdi
0x18006e428  mov     dword ptr [rbp+EcpContextSize], edi
0x18006e42b  call    cs:__imp_FsRtlGetEcpListFromIrp
0x18006e432  nop     dword ptr [rax+rax+00h]
0x18006e437  mov     r8d, 48Dh
0x18006e43d  lea     rdx, aMinkernelFsFil_7; "minkernel\\fs\\filtermgr\\filter\\targe"...
0x18006e444  mov     ecx, eax
0x18006e446  xor     r9d, r9d
0x18006e449  call    FltpDbgStatus
0x18006e44e  mov     r13, [rsp+80h+var_8]
0x18006e453  test    eax, eax
0x18006e455  js      short loc_18006E4D0
0x18006e457  mov     rcx, qword ptr [rbp+DestinationString.Length]; EcpList
0x18006e45b  test    rcx, rcx
0x18006e45e  jz      short loc_18006E4D0
0x18006e460  lea     r9, [rbp+EcpContextSize]; EcpContextSize
0x18006e464  lea     r8, [rbp+EcpContext]; EcpContext
0x18006e468  lea     rdx, FLTMGR_TIOCTRL_ECP_GUID; EcpType
0x18006e46f  call    cs:__imp_FsRtlFindExtraCreateParameter
0x18006e476  nop     dword ptr [rax+rax+00h]
0x18006e47b  mov     r8d, 49Ch
0x18006e481  lea     rdx, aMinkernelFsFil_7; "minkernel\\fs\\filtermgr\\filter\\targe"...
0x18006e488  mov     ecx, eax
0x18006e48a  xor     r9d, r9d
0x18006e48d  call    FltpDbgStatus
0x18006e492  test    eax, eax
0x18006e494  js      short loc_18006E4D0
0x18006e496  mov     rcx, [rbp+EcpContext]; EcpContext
0x18006e49a  call    cs:__imp_FsRtlIsEcpFromUserMode
0x18006e4a1  nop     dword ptr [rax+rax+00h]
0x18006e4a6  test    al, al
0x18006e4a8  jnz     short loc_18006E4D0
0x18006e4aa  mov     rdx, qword ptr [rbp+var_40]
0x18006e4ae  lea     rax, [rbp+arg_0]
0x18006e4b2  mov     rcx, [rbp+EcpContext]
0x18006e4b6  lea     r8, [rbp+var_40]
0x18006e4ba  xor     r9d, r9d
0x18006e4bd  mov     qword ptr [rsp+80h+var_60], rax
0x18006e4c2  mov     rdx, [rdx+68h]
0x18006e4c6  call    FltpSetUpIrpCallControl
0x18006e4cb  movzx   r12d, [rbp+arg_0]
0x18006e4d0  mov     rax, qword ptr [rbp+var_40]
0x18006e4d4  mov     ecx, [rax+38h]
0x18006e4d7  bt      ecx, 8
0x18006e4db  jnb     loc_18006E5B1
0x18006e4e1  movzx   eax, byte ptr [r15]
0x18006e4e5  cmp     al, 6
0x18006e4e7  jnz     short loc_18006E534
0x18006e4e9  mov     ecx, [r15+10h]
0x18006e4ed  lea     eax, [rcx-13h]
0x18006e4f0  cmp     eax, 1
0x18006e4f3  jbe     loc_18006E5B6
0x18006e4f9  cmp     ecx, 27h ; '''
0x18006e4fc  jz      loc_18006E5B6
0x18006e502  cmp     ecx, 0Dh
0x18006e505  jnz     short loc_18006E51B
0x18006e507  mov     rax, [rbx+18h]
0x18006e50b  test    rax, rax
0x18006e50e  jz      short loc_18006E55C
0x18006e510  cmp     [rax], dil
0x18006e513  jnz     loc_18006E5B6
0x18006e519  jmp     short loc_18006E55C
0x18006e51b  cmp     ecx, 40h ; '@'
0x18006e51e  jnz     short loc_18006E55C
0x18006e520  mov     rax, [rbx+18h]
0x18006e524  test    rax, rax
0x18006e527  jz      short loc_18006E55C
0x18006e529  mov     eax, [rax]
0x18006e52b  test    al, 1
0x18006e52d  jz      short loc_18006E55C
0x18006e52f  jmp     loc_18006E5B6
0x18006e534  cmp     al, 4
0x18006e536  jnz     short loc_18006E55C
0x18006e538  mov     eax, [rbx+10h]
0x18006e53b  test    al, 1
0x18006e53d  jnz     short loc_18006E555
0x18006e53f  mov     rax, qword ptr [rbp+var_40]
0x18006e543  mov     ecx, [rax+38h]
0x18006e546  test    cl, 1
0x18006e549  jnz     short loc_18006E555
0x18006e54b  mov     rax, qword ptr [rbp+var_40]
0x18006e54f  cmp     dword ptr [rax+3Ch], 1Bh
0x18006e553  jnz     short loc_18006E55C
0x18006e555  mov     eax, [rbx+10h]
0x18006e558  test    al, 42h
0x18006e55a  jz      short loc_18006E5B6
0x18006e55c  movzx   eax, byte ptr [r15]
0x18006e560  test    al, al
0x18006e562  jnz     short loc_18006E570
0x18006e564  cmp     dword ptr [r15+10h], 1000000h
0x18006e56c  jb      short loc_18006E5B6
0x18006e56e  jmp     short loc_18006E5B1
0x18006e570  cmp     al, 0Dh
0x18006e572  jnz     short loc_18006E59B
0x18006e574  mov     eax, [r15+18h]
0x18006e578  cmp     eax, 980C8h
0x18006e57d  jz      short loc_18006E5B6
0x18006e57f  cmp     eax, 98268h
0x18006e584  jz      short loc_18006E5B6
0x18006e586  cmp     eax, 1440F2h
0x18006e58b  jz      short loc_18006E5B6
0x18006e58d  cmp     eax, 1480F2h
0x18006e592  jz      short loc_18006E5B6
0x18006e594  cmp     eax, 900DFh
0x18006e599  jmp     short loc_18006E5AF
0x18006e59b  cmp     al, 0Eh
0x18006e59d  jnz     short loc_18006E5B1
  ... truncated ...
```
