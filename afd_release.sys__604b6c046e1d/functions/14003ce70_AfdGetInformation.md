# AfdGetInformation

- ea: `0x14003ce70`
- end: `0x14003d68b`
- name: `AfdGetInformation`
- size: `2075`
- prototype: `__int64 __fastcall(__int64, __int64, KPROCESSOR_MODE, int *, unsigned int, void *, unsigned int, _QWORD *)`
- caller_count: `0`
- callee_count: `15`
- tags: ``

## callees

- `0x14000fcd0`
- `0x14001c708`
- `0x14001e7e0`
- `0x14002c770`
- `0x14002fd5c`
- `0x140032778`
- `0x140033bdc`
- `0x14003ce70`
- `0x14004e800`
- `0x14004f3e0`
- `0x1400726a0`
- `0x1400726d0`
- `0x140072b00`
- `0x140092008`
- `0x14009214c`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x14003cfa0`
- `ntoskrnl!ProbeForRead` at `0x14003cfa0`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14003d248`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14003d248`
- `ntoskrnl!IoFreeMdl` at `0x14003d392`
- `ntoskrnl!IoFreeMdl` at `0x14003d392`
- `ntoskrnl!MmUnlockPages` at `0x14003d375`
- `ntoskrnl!MmUnlockPages` at `0x14003d375`
- `ntoskrnl!MmProbeAndLockPages` at `0x14003d1c9`
- `ntoskrnl!MmProbeAndLockPages` at `0x14003d1c9`
- `ntoskrnl!IoAllocateMdl` at `0x14003d19f`
- `ntoskrnl!IoAllocateMdl` at `0x14003d19f`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14003d5f8`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14003d626`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14003d5f8`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14003d626`
- `ntoskrnl!IoIs32bitProcess` at `0x14003cf54`
- `ntoskrnl!IoIs32bitProcess` at `0x14003d5d6`
- `ntoskrnl!IoIs32bitProcess` at `0x14003cf54`
- `ntoskrnl!IoIs32bitProcess` at `0x14003d5d6`

## pseudocode

```c
__int64 __fastcall AfdGetInformation(
        __int64 a1,
        __int64 a2,
        KPROCESSOR_MODE a3,
        int *a4,
        unsigned int a5,
        void *a6,
        unsigned int a7,
        _QWORD *a8)
{
  __int16 *v10; // rdi
  __int16 v11; // ax
  int DeliveryStatus; // esi
  int ULongFromUser; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  __int64 v21; // rax
  __int64 v22; // r8
  signed __int64 v23; // rax
  bool v24; // cc
  signed __int64 v25; // rax
  __int64 v26; // rcx
  __int64 ConnectionReferenceFromEndpoint; // rax
  int v28; // ecx
  signed __int64 v29; // rcx
  signed __int64 v30; // rcx
  int v31; // eax
  struct _MDL *Mdl; // rax
  struct _MDL *v33; // r15
  PVOID MappedSystemVa; // rax
  _BYTE *v35; // rsi
  bool v36; // cl
  __int64 v37; // r15
  signed __int64 v38; // rax
  signed __int64 v39; // rax
  char v42; // [rsp+38h] [rbp-100h]
  _QWORD v43[6]; // [rsp+68h] [rbp-D0h] BYREF
  __int128 Src; // [rsp+98h] [rbp-A0h] BYREF
  _OWORD VirtualAddress[5]; // [rsp+B0h] [rbp-88h] BYREF

  v43[5] = a6;
  DWORD2(Src) = 0;
  *(_QWORD *)&Src = 0;
  *a8 = 0;
  v10 = *(__int16 **)(a1 + 24);
  v43[0] = v10;
  v11 = *v10;
  if ( *v10 != -21763 && v11 != 2813 && v11 != -1527 )
  {
    Src = 0;
    DeliveryStatus = 0;
    if ( a5 < 0x10 )
      return 3221225507LL;
    v42 = 0;
    if ( a7 < 0x10 )
      return 3221225507LL;
    if ( IoIs32bitProcess(0) )
    {
      if ( a3 )
      {
        v43[2] = 1;
LABEL_11:
        ProbeForRead(a4, 1u, 4u);
      }
    }
    else if ( a3 )
    {
      v43[3] = 1;
      goto LABEL_11;
    }
    if ( a3 )
      ULongFromUser = RtlReadULongFromUser(a4);
    else
      ULongFromUser = *a4;
    LODWORD(Src) = ULongFromUser;
    v14 = ULongFromUser - 3;
    if ( !v14 )
      goto LABEL_78;
    v15 = v14 - 1;
    if ( !v15 )
    {
      if ( (*((_DWORD *)v10 + 2) & 0x100) == 0 && (*((_DWORD *)v10 + 4) & 0x200) != 0
        || (*v10 & 0xAFD2) != 0xAFD2
        || *((_BYTE *)v10 + 2) != 4
        || (ConnectionReferenceFromEndpoint = AfdGetConnectionReferenceFromEndpoint(v10)) == 0 )
      {
        DWORD2(Src) = 0;
        goto LABEL_104;
      }
      v28 = *(_DWORD *)(ConnectionReferenceFromEndpoint + 124);
LABEL_37:
      DWORD2(Src) = v28;
      v29 = _InterlockedExchangeAdd64(
              (volatile signed __int64 *)(ConnectionReferenceFromEndpoint + 48),
              0xFFFFFFFFFFFFFFFFuLL);
      v24 = v29 <= 1;
      v30 = v29 - 1;
      if ( !v24 )
        goto LABEL_104;
      if ( !v30 )
      {
        v26 = ConnectionReferenceFromEndpoint;
        goto LABEL_31;
      }
LABEL_86:
      __fastfail(0xEu);
    }
    v16 = v15 - 1;
    if ( v16 )
    {
      v17 = v16 - 1;
      if ( v17 )
      {
        v18 = v17 - 1;
        if ( v18 )
        {
          v19 = v18 - 1;
          if ( v19 )
          {
            v20 = v19 - 2;
            if ( v20 )
            {
              if ( v20 == 4 )
              {
                DeliveryStatus = AfdGetDeliveryStatus(v10, (char *)&Src + 8);
                goto LABEL_104;
              }
              return 3221225485LL;
            }
            *((_QWORD *)&Src + 1) = *((_QWORD *)v10 + 58);
LABEL_104:
            if ( DeliveryStatus >= 0 )
            {
              if ( IoIs32bitProcess(0) )
              {
                if ( a3 && ((unsigned __int8)a6 & 3) != 0 )
                  ExRaiseDatatypeMisalignment();
              }
              else if ( a3 && ((unsigned __int8)a6 & 3) != 0 )
              {
                ExRaiseDatatypeMisalignment();
              }
              if ( a3 )
                RtlCopyToUser(a6, &Src, 0x10u);
              else
                RtlCopyVolatileMemory(a6, &Src, 0x10u);
              *a8 = 16;
            }
            return (unsigned int)DeliveryStatus;
          }
          if ( *((_BYTE *)v10 + 2) != 4
            || *v10 == -20527
            || (v21 = AfdGetConnectionReferenceFromEndpoint(v10), (v22 = v21) == 0) )
          {
            DWORD2(Src) = -1;
            goto LABEL_104;
          }
          DWORD2(Src) = (MEMORY[0xFFFFF78000000008] - *(_QWORD *)(v21 + 40)) / 10000000LL;
          v23 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v21 + 48), 0xFFFFFFFFFFFFFFFFuLL);
          v24 = v23 <= 1;
          v25 = v23 - 1;
          if ( !v24 )
            goto LABEL_104;
          if ( !v25 )
          {
            v26 = v22;
LABEL_31:
            AfdCloseConnection(v26);
            goto LABEL_104;
          }
          goto LABEL_86;
        }
        if ( (*v10 & 0xAFD2) == 0xAFD2 && *((_BYTE *)v10 + 2) == 4 )
        {
          ConnectionReferenceFromEndpoint = AfdGetConnectionReferenceFromEndpoint(v10);
          if ( ConnectionReferenceFromEndpoint )
          {
            v28 = *(_DWORD *)(ConnectionReferenceFromEndpoint + 148);
            goto LABEL_37;
          }
        }
        v31 = AfdSendWindowSize;
      }
      else
      {
        v31 = AfdReceiveWindowSize;
      }
LABEL_103:
      DWORD2(Src) = v31;
      goto LABEL_104;
    }
    if ( (*((_DWORD *)v10 + 2) & 0x100) != 0 || a5 <= 0x10 || (unsigned __int8)(*((_BYTE *)v10 + 2) - 3) > 1u )
    {
LABEL_78:
      if ( (*((_DWORD *)v10 + 2) & 0x100) != 0 )
      {
        memset(VirtualAddress, 0, sizeof(VirtualAddress));
        *(_QWORD *)&VirtualAddress[1] = 0xFFFF00000002LL;
        DWORD2(VirtualAddress[1]) = 8195;
        *(_QWORD *)&VirtualAddress[3] = (char *)&Src + 8;
        *((_QWORD *)&VirtualAddress[3] + 1) = 4;
        if ( (*v10 & 0xAFD2) == 0xAFD2 && *((_BYTE *)v10 + 2) == 4 )
          v37 = AfdGetConnectionReferenceFromEndpoint(v10);
        else
          v37 = 0;
        if ( !v37 )
        {
          if ( *v10 != -20527
            && *v10 != 6909
            && ((*((_BYTE *)v10 + 5) & 0x10) == 0 || (v10[3] & 1) == 0)
            && (*((_DWORD *)v10 + 2) & 1) == 0
            && *((_BYTE *)v10 + 2) != 4 )
          {
            if ( !(unsigned __int8)AfdPreventUnbind(v10) )
              return (unsigned int)-1073741436;
            v42 = 1;
          }
          _InterlockedAdd64((volatile signed __int64 *)v10 + 33, 1u);
          DeliveryStatus = AfdTLIoControl(
                             *(_QWORD *)(*((_QWORD *)v10 + 3) + 8LL),
                             *((_QWORD *)v10 + 2),
                             VirtualAddress,
                             v10);
          _InterlockedDecrement64((volatile signed __int64 *)v10 + 33);
          if ( v42 )
            AfdReallowUnbind(v10);
          goto LABEL_104;
        }
        DeliveryStatus = AfdTLIoControl(
                           *(_QWORD *)(*(_QWORD *)(v37 + 24) + 8LL),
                           *(_QWORD *)(v37 + 16),
                           VirtualAddress,
                           0);
        v38 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v37 + 48), 0xFFFFFFFFFFFFFFFFuLL);
        v24 = v38 <= 1;
        v39 = v38 - 1;
        if ( !v24 )
          goto LABEL_104;
        if ( !v39 )
        {
          v26 = v37;
          goto LABEL_31;
        }
        goto LABEL_86;
      }
      memset(VirtualAddress, 0, 40);
      DeliveryStatus = AfdQueryProviderInfo(VirtualAddress);
      if ( DeliveryStatus < 0 )
        goto LABEL_104;
      v31 = DWORD1(VirtualAddress[0]);
      if ( *v10 == -20527 )
        v31 = HIDWORD(VirtualAddress[0]);
      goto LABEL_103;
    }
    memset(VirtualAddress, 0, 44);
    Mdl = IoAllocateMdl(a4 + 4, a5 - 16, 0, 1u, 0);
    v33 = Mdl;
    v43[4] = Mdl;
    if ( !Mdl )
    {
      DeliveryStatus = -1073741670;
LABEL_69:
      if ( DeliveryStatus >= 0 )
        goto LABEL_104;
      goto LABEL_78;
    }
    MmProbeAndLockPages(Mdl, a3, IoWriteAccess);
    if ( (v33->MdlFlags & 5) != 0 )
      MappedSystemVa = v33->MappedSystemVa;
    else
      MappedSystemVa = MmMapLockedPagesSpecifyCache(v33, 0, MmCached, 0, 0, 0x40000000u);
    *((_QWORD *)&VirtualAddress[2] + 1) = MappedSystemVa;
    if ( !MappedSystemVa )
    {
      DeliveryStatus = -1073741670;
LABEL_67:
      MmUnlockPages(v33);
      IoFreeMdl(v33);
      goto LABEL_69;
    }
    LODWORD(VirtualAddress[2]) = a5 - 16;
    v43[0] = 9;
    v43[1] = VirtualAddress;
    LODWORD(VirtualAddress[0]) = 0;
    *((_QWORD *)&VirtualAddress[0] + 1) = 0;
    LODWORD(VirtualAddress[1]) = 0;
    *((_QWORD *)&VirtualAddress[1] + 1) = 0;
    if ( *v10 == -20527 || *v10 == 6909 || (*((_BYTE *)v10 + 5) & 0x10) != 0 && (v10[3] & 1) != 0 )
    {
      v35 = v10 + 1;
    }
    else
    {
      v35 = v10 + 1;
      if ( (*((_DWORD *)v10 + 2) & 1) == 0 && *((_BYTE *)v10 + 2) != 4 )
      {
        v36 = (unsigned __int8)AfdPreventUnbind(v10) != 0;
        v42 = v36;
        goto LABEL_59;
      }
    }
    v36 = 0;
LABEL_59:
    if ( *v35 == 3 && v36 || *v35 == 4 )
      DeliveryStatus = AfdIssueDeviceControl(*((PFILE_OBJECT *)v10 + 3), v43, 0x10u, (char *)&Src + 8, 4u, 0xCu);
    else
      DeliveryStatus = -1073741436;
    if ( v42 )
      AfdReallowUnbind(v10);
    goto LABEL_67;
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x14003ce70  mov     [rsp+arg_8], rsi
0x14003ce75  push    rdi
0x14003ce76  push    r12
0x14003ce78  push    r13
0x14003ce7a  push    r14
0x14003ce7c  push    r15
0x14003ce7e  sub     rsp, 110h
0x14003ce85  mov     rax, cs:__security_cookie
0x14003ce8c  xor     rax, rsp
0x14003ce8f  mov     [rsp+138h+var_38], rax
0x14003ce97  mov     r15, r9
0x14003ce9a  mov     r14b, r8b
0x14003ce9d  mov     [rsp+138h+AccessMode], r8b
0x14003cea2  mov     [rsp+138h+var_F8], r8b
0x14003cea7  mov     r13d, [rsp+138h+arg_20]
0x14003ceaf  mov     rax, [rsp+138h+arg_28]
0x14003ceb7  mov     [rsp+138h+var_E8], rax
0x14003cebc  mov     [rsp+138h+var_A8], rax
0x14003cec4  mov     rax, [rsp+138h+arg_38]
0x14003cecc  mov     [rsp+138h+var_D8], rax
0x14003ced1  xor     edx, edx
0x14003ced3  mov     qword ptr [rsp+138h+Src+4], rdx
0x14003cedb  mov     qword ptr [rsp+138h+Src], rdx
0x14003cee3  mov     [rax], rdx
0x14003cee6  mov     rdi, [rcx+18h]
0x14003ceea  mov     [rsp+138h+var_D0], rdi
0x14003ceef  movzx   eax, word ptr [rdi]
0x14003cef2  mov     ecx, 0AAFDh
0x14003cef7  cmp     ax, cx
0x14003cefa  jz      loc_14003D65C
0x14003cf00  mov     ecx, 0AFDh
0x14003cf05  cmp     ax, cx
0x14003cf08  jz      loc_14003D65C
0x14003cf0e  mov     ecx, 0FA09h
0x14003cf13  cmp     ax, cx
0x14003cf16  jz      loc_14003D65C
0x14003cf1c  xorps   xmm0, xmm0
0x14003cf1f  movups  [rsp+138h+Src], xmm0
0x14003cf27  xor     esi, esi
0x14003cf29  mov     [rsp+138h+var_104], esi
0x14003cf2d  lea     r12d, [rdx+10h]
0x14003cf31  cmp     r13d, r12d
0x14003cf34  jb      loc_14003D655
0x14003cf3a  xor     al, al
0x14003cf3c  mov     [rsp+138h+var_100], eax
0x14003cf40  mov     [rsp+138h+var_FC], al
0x14003cf44  cmp     [rsp+138h+arg_30], r12d
0x14003cf4c  jb      loc_14003D655
0x14003cf52  xor     ecx, ecx; Irp
0x14003cf54  call    cs:__imp_IoIs32bitProcess
0x14003cf5b  nop     dword ptr [rax+rax+00h]
0x14003cf60  test    al, al
0x14003cf62  jz      short loc_14003CF79
0x14003cf64  test    r14b, r14b
0x14003cf67  lea     r14d, [rsi+1]
0x14003cf6b  jz      short loc_14003CFAC
0x14003cf6d  mov     [rsp+138h+var_C0], r12
0x14003cf72  mov     [rsp+138h+var_C0], r14
0x14003cf77  jmp     short loc_14003CF94
0x14003cf79  test    r14b, r14b
0x14003cf7c  mov     r14d, 1
0x14003cf82  jz      short loc_14003CFAC
0x14003cf84  mov     [rsp+138h+var_B8], r12
0x14003cf8c  mov     [rsp+138h+var_B8], r14
0x14003cf94  mov     r8d, 4; Alignment
0x14003cf9a  mov     rdx, r14; Length
0x14003cf9d  mov     rcx, r15; Address
0x14003cfa0  call    cs:__imp_ProbeForRead
0x14003cfa7  nop     dword ptr [rax+rax+00h]
0x14003cfac  cmp     [rsp+138h+AccessMode], 0
0x14003cfb1  jz      short loc_14003CFBD
0x14003cfb3  mov     rcx, r15
0x14003cfb6  call    RtlReadULongFromUser
0x14003cfbb  jmp     short loc_14003CFC0
0x14003cfbd  mov     eax, [r15]
0x14003cfc0  mov     dword ptr [rsp+138h+Src], eax
0x14003cfc7  sub     eax, 3
0x14003cfca  jz      loc_14003D40B
0x14003cfd0  sub     eax, 1
0x14003cfd3  jz      loc_14003D3BE
0x14003cfd9  sub     eax, 1
0x14003cfdc  jz      loc_14003D13B
0x14003cfe2  sub     eax, 1
0x14003cfe5  jz      loc_14003D130
0x14003cfeb  sub     eax, 1
0x14003cfee  jz      loc_14003D0D3
0x14003cff4  sub     eax, 1
0x14003cff7  jz      short loc_14003D041
0x14003cff9  sub     eax, 2
0x14003cffc  jz      short loc_14003D022
0x14003cffe  cmp     eax, 4
0x14003d001  jnz     loc_14003D65C
0x14003d007  lea     rdx, [rsp+138h+Src+8]
0x14003d00f  mov     rcx, rdi
0x14003d012  call    AfdGetDeliveryStatus
0x14003d017  mov     esi, eax
0x14003d019  mov     [rsp+138h+var_104], eax
0x14003d01d  jmp     loc_14003D5CC
0x14003d022  mov     eax, [rdi+1D0h]
0x14003d028  mov     dword ptr [rsp+138h+Src+8], eax
0x14003d02f  mov     eax, [rdi+1D4h]
0x14003d035  mov     dword ptr [rsp+138h+Src+0Ch], eax
0x14003d03c  jmp     loc_14003D5CC
0x14003d041  cmp     byte ptr [rdi+2], 4
0x14003d045  jnz     short loc_14003D0C3
0x14003d047  mov     r12d, 0AFD1h
0x14003d04d  cmp     [rdi], r12w
0x14003d051  jz      short loc_14003D0C3
0x14003d053  mov     rcx, rdi
0x14003d056  call    AfdGetConnectionReferenceFromEndpoint
0x14003d05b  mov     r8, rax
0x14003d05e  test    rax, rax
0x14003d061  jz      short loc_14003D0C3
0x14003d063  mov     rcx, 0FFFFF78000000008h
0x14003d06d  mov     rcx, [rcx]
0x14003d070  sub     rcx, [rax+28h]
0x14003d074  mov     rax, 0D6BF94D5E57A42BDh
0x14003d07e  imul    rcx
0x14003d081  add     rdx, rcx
0x14003d084  sar     rdx, 17h
0x14003d088  mov     rax, rdx
0x14003d08b  shr     rax, 3Fh
0x14003d08f  add     rdx, rax
0x14003d092  mov     dword ptr [rsp+138h+Src+8], edx
0x14003d099  or      rax, 0FFFFFFFFFFFFFFFFh
0x14003d09d  lock xadd [r8+30h], rax
0x14003d0a3  sub     rax, 1
0x14003d0a7  jg      loc_14003D5CC
0x14003d0ad  test    rax, rax
0x14003d0b0  jnz     loc_14003D4DA
0x14003d0b6  mov     rcx, r8
0x14003d0b9  call    AfdCloseConnection
0x14003d0be  jmp     loc_14003D5CC
0x14003d0c3  mov     dword ptr [rsp+138h+Src+8], 0FFFFFFFFh
0x14003d0ce  jmp     loc_14003D5CC
0x14003d0d3  movzx   eax, word ptr [rdi]
0x14003d0d6  mov     ecx, 0AFD2h
0x14003d0db  and     ax, cx
0x14003d0de  cmp     ax, cx
0x14003d0e1  jnz     short loc_14003D125
0x14003d0e3  cmp     byte ptr [rdi+2], 4
0x14003d0e7  jnz     short loc_14003D125
0x14003d0e9  mov     rcx, rdi
0x14003d0ec  call    AfdGetConnectionReferenceFromEndpoint
0x14003d0f1  test    rax, rax
0x14003d0f4  jz      short loc_14003D125
0x14003d0f6  mov     ecx, [rax+94h]
0x14003d0fc  mov     dword ptr [rsp+138h+Src+8], ecx
0x14003d103  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14003d107  lock xadd [rax+30h], rcx
0x14003d10d  sub     rcx, 1
0x14003d111  jg      loc_14003D5CC
0x14003d117  test    rcx, rcx
0x14003d11a  jnz     loc_14003D4DA
0x14003d120  mov     rcx, rax
0x14003d123  jmp     short loc_14003D0B9
0x14003d125  mov     eax, cs:AfdSendWindowSize
0x14003d12b  jmp     loc_14003D5C5
0x14003d130  mov     eax, cs:AfdReceiveWindowSize
0x14003d136  jmp     loc_14003D5C5
0x14003d13b  mov     eax, [rdi+8]
0x14003d13e  bt      eax, 8
0x14003d142  jb      loc_14003D40B
0x14003d148  cmp     r13d, r12d
0x14003d14b  jbe     loc_14003D40B
0x14003d151  lea     rax, [rdi+2]
0x14003d155  mov     [rsp+138h+var_F0], rax
0x14003d15a  mov     al, [rax]
0x14003d15c  sub     al, 3
0x14003d15e  cmp     al, r14b
0x14003d161  ja      loc_14003D40B
0x14003d167  xor     eax, eax
0x14003d169  xorps   xmm0, xmm0
0x14003d16c  movups  [rsp+138h+VirtualAddress], xmm0
0x14003d174  movups  [rsp+138h+var_78], xmm0
0x14003d17c  movups  [rsp+138h+var_78+0Ch], xmm0
0x14003d184  lea     r12d, [r13-10h]
0x14003d188  mov     [rsp+138h+var_E0], r12d
0x14003d18d  lea     rcx, [r15+10h]; VirtualAddress
0x14003d191  mov     [rsp+138h+Irp], rax; Irp
0x14003d196  mov     r9b, r14b; ChargeQuota
0x14003d199  xor     r8d, r8d; SecondaryBuffer
0x14003d19c  mov     edx, r12d; Length
0x14003d19f  call    cs:__imp_IoAllocateMdl
0x14003d1a6  nop     dword ptr [rax+rax+00h]
0x14003d1ab  mov     r15, rax
0x14003d1ae  mov     [rsp+138h+var_B0], rax
0x14003d1b6  test    rax, rax
0x14003d1b9  jz      loc_14003D3A0
0x14003d1bf  mov     r8d, r14d; Operation
0x14003d1c2  mov     dl, [rsp+138h+AccessMode]; AccessMode
0x14003d1c6  mov     rcx, rax; MemoryDescriptorList
0x14003d1c9  call    cs:__imp_MmProbeAndLockPages
0x14003d1d0  nop     dword ptr [rax+rax+00h]
0x14003d1d5  mov     [rsp+138h+var_104], 0
0x14003d1dd  jmp     short loc_14003D214
0x14003d1df  mov     r14d, 1
0x14003d1e5  mov     al, [rsp+138h+var_FC]
0x14003d1e9  mov     [rsp+138h+var_100], eax
0x14003d1ed  mov     r15, [rsp+138h+var_B0]
0x14003d1f5  mov     al, [rsp+138h+var_F8]
0x14003d1f9  mov     [rsp+138h+AccessMode], al
0x14003d1fd  mov     rcx, [rsp+138h+var_A8]
0x14003d205  mov     [rsp+138h+var_E8], rcx
0x14003d20a  mov     rdi, [rsp+138h+var_D0]
0x14003d20f  mov     r12d, [rsp+138h+var_E0]
0x14003d214  mov     esi, [rsp+138h+var_104]
0x14003d218  test    esi, esi
0x14003d21a  js      loc_14003D383
0x14003d220  test    byte ptr [r15+0Ah], 5
0x14003d225  jz      short loc_14003D22D
0x14003d227  mov     rax, [r15+18h]
0x14003d22b  jmp     short loc_14003D254
0x14003d22d  mov     [rsp+138h+Priority], 40000000h; Priority
0x14003d235  mov     dword ptr [rsp+138h+Irp], 0; BugCheckOnFailure
0x14003d23d  xor     r9d, r9d; RequestedAddress
0x14003d240  mov     r8d, r14d; CacheType
0x14003d243  xor     edx, edx; AccessMode
0x14003d245  mov     rcx, r15; MemoryDescriptorList
0x14003d248  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14003d24f  nop     dword ptr [rax+rax+00h]
0x14003d254  mov     [rsp+138h+var_60], rax
0x14003d25c  mov     r13d, 1AFDh
0x14003d262  test    rax, rax
0x14003d265  jz      loc_14003D363
0x14003d26b  mov     dword ptr [rsp+138h+var_68], r12d
0x14003d273  mov     [rsp+138h+var_D0], 9
0x14003d27c  lea     rax, [rsp+138h+VirtualAddress]
0x14003d284  mov     [rsp+138h+var_C8], rax
0x14003d289  mov     dword ptr [rsp+138h+VirtualAddress], 0
0x14003d294  mov     qword ptr [rsp+138h+VirtualAddress+8], 0
0x14003d2a0  mov     dword ptr [rsp+138h+var_78], 0
0x14003d2ab  mov     qword ptr [rsp+138h+var_78+8], 0
0x14003d2b7  movzx   eax, word ptr [rdi]
0x14003d2ba  mov     r12d, 0AFD1h
0x14003d2c0  cmp     ax, r12w
0x14003d2c4  jz      short loc_14003D305
0x14003d2c6  cmp     ax, r13w
0x14003d2ca  jz      short loc_14003D305
0x14003d2cc  test    byte ptr [rdi+5], 10h
0x14003d2d0  jz      short loc_14003D2D8
0x14003d2d2  test    [rdi+6], r14b
0x14003d2d6  jnz     short loc_14003D305
0x14003d2d8  mov     eax, [rdi+8]
0x14003d2db  mov     rsi, [rsp+138h+var_F0]
0x14003d2e0  test    r14b, al
0x14003d2e3  jnz     short loc_14003D30A
0x14003d2e5  cmp     byte ptr [rsi], 4
0x14003d2e8  jz      short loc_14003D30A
0x14003d2ea  mov     rcx, rdi
0x14003d2ed  call    AfdPreventUnbind
0x14003d2f2  mov     ecx, [rsp+138h+var_100]
0x14003d2f6  movzx   ecx, cl
0x14003d2f9  test    al, al
0x14003d2fb  cmovnz  ecx, r14d
0x14003d2ff  mov     [rsp+138h+var_100], ecx
0x14003d303  jmp     short loc_14003D30E
0x14003d305  mov     rsi, [rsp+138h+var_F0]
0x14003d30a  mov     ecx, [rsp+138h+var_100]
0x14003d30e  mov     al, [rsi]
0x14003d310  cmp     al, 3
0x14003d312  jnz     short loc_14003D318
0x14003d314  test    cl, cl
0x14003d316  jnz     short loc_14003D31C
0x14003d318  cmp     al, 4
0x14003d31a  jnz     short loc_14003D349
0x14003d31c  mov     byte ptr [rsp+138h+Priority], 0Ch; char
0x14003d321  mov     dword ptr [rsp+138h+Irp], 4; Length
0x14003d329  lea     r9, [rsp+138h+Src+8]; VirtualAddress
0x14003d331  mov     r8d, 10h; Size
0x14003d337  lea     rdx, [rsp+138h+var_D0]; Src
0x14003d33c  mov     rcx, [rdi+18h]; FileObject
0x14003d340  call    AfdIssueDeviceControl
0x14003d345  mov     esi, eax
0x14003d347  jmp     short loc_14003D34E
0x14003d349  mov     esi, 0C0000184h
0x14003d34e  mov     [rsp+138h+var_104], esi
0x14003d352  cmp     byte ptr [rsp+138h+var_100], 0
0x14003d357  jz      short loc_14003D372
0x14003d359  mov     rcx, rdi
0x14003d35c  call    AfdReallowUnbind
0x14003d361  jmp     short loc_14003D372
0x14003d363  mov     esi, 0C000009Ah
0x14003d368  mov     [rsp+138h+var_104], esi
0x14003d36c  mov     r12d, 0AFD1h
0x14003d372  mov     rcx, r15; MemoryDescriptorList
0x14003d375  call    cs:__imp_MmUnlockPages
0x14003d37c  nop     dword ptr [rax+rax+00h]
0x14003d381  jmp     short loc_14003D38F
0x14003d383  mov     r12d, 0AFD1h
0x14003d389  mov     r13d, 1AFDh
0x14003d38f  mov     rcx, r15; Mdl
0x14003d392  call    cs:__imp_IoFreeMdl
0x14003d399  nop     dword ptr [rax+rax+00h]
0x14003d39e  jmp     short loc_14003D3B5
0x14003d3a0  mov     esi, 0C000009Ah
0x14003d3a5  mov     [rsp+138h+var_104], esi
0x14003d3a9  mov     r12d, 0AFD1h
0x14003d3af  mov     r13d, 1AFDh
0x14003d3b5  test    esi, esi
  ... truncated ...
```
