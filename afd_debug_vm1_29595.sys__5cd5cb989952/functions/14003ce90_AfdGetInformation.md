# AfdGetInformation

- ea: `0x14003ce90`
- end: `0x14003d6ab`
- name: `AfdGetInformation`
- size: `2075`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: ``

## callees

- `0x14000fcd0`
- `0x14001c708`
- `0x14001e7e0`
- `0x14002c770`
- `0x14002fd7c`
- `0x140032798`
- `0x140033bfc`
- `0x14003ce90`
- `0x14004e8a0`
- `0x14004f480`
- `0x140072840`
- `0x140072870`
- `0x140072c80`
- `0x140092008`
- `0x14009214c`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x14003cfc0`
- `ntoskrnl!ProbeForRead` at `0x14003cfc0`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14003d268`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14003d268`
- `ntoskrnl!IoFreeMdl` at `0x14003d3b2`
- `ntoskrnl!IoFreeMdl` at `0x14003d3b2`
- `ntoskrnl!MmUnlockPages` at `0x14003d395`
- `ntoskrnl!MmUnlockPages` at `0x14003d395`
- `ntoskrnl!MmProbeAndLockPages` at `0x14003d1e9`
- `ntoskrnl!MmProbeAndLockPages` at `0x14003d1e9`
- `ntoskrnl!IoAllocateMdl` at `0x14003d1bf`
- `ntoskrnl!IoAllocateMdl` at `0x14003d1bf`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14003d618`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14003d646`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14003d618`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14003d646`
- `ntoskrnl!IoIs32bitProcess` at `0x14003cf74`
- `ntoskrnl!IoIs32bitProcess` at `0x14003d5f6`
- `ntoskrnl!IoIs32bitProcess` at `0x14003cf74`
- `ntoskrnl!IoIs32bitProcess` at `0x14003d5f6`

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
      DeliveryStatus = AfdIssueDeviceControl(*((PFILE_OBJECT *)v10 + 3), v43, 0x10u, (char *)&Src + 8, 4u, 12);
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
0x14003ce90  mov     [rsp+arg_8], rsi
0x14003ce95  push    rdi
0x14003ce96  push    r12
0x14003ce98  push    r13
0x14003ce9a  push    r14
0x14003ce9c  push    r15
0x14003ce9e  sub     rsp, 110h
0x14003cea5  mov     rax, cs:__security_cookie
0x14003ceac  xor     rax, rsp
0x14003ceaf  mov     [rsp+138h+var_38], rax
0x14003ceb7  mov     r15, r9
0x14003ceba  mov     r14b, r8b
0x14003cebd  mov     [rsp+138h+AccessMode], r8b
0x14003cec2  mov     [rsp+138h+var_F8], r8b
0x14003cec7  mov     r13d, [rsp+138h+arg_20]
0x14003cecf  mov     rax, [rsp+138h+arg_28]
0x14003ced7  mov     [rsp+138h+var_E8], rax
0x14003cedc  mov     [rsp+138h+var_A8], rax
0x14003cee4  mov     rax, [rsp+138h+arg_38]
0x14003ceec  mov     [rsp+138h+var_D8], rax
0x14003cef1  xor     edx, edx
0x14003cef3  mov     qword ptr [rsp+138h+Src+4], rdx
0x14003cefb  mov     qword ptr [rsp+138h+Src], rdx
0x14003cf03  mov     [rax], rdx
0x14003cf06  mov     rdi, [rcx+18h]
0x14003cf0a  mov     [rsp+138h+var_D0], rdi
0x14003cf0f  movzx   eax, word ptr [rdi]
0x14003cf12  mov     ecx, 0AAFDh
0x14003cf17  cmp     ax, cx
0x14003cf1a  jz      loc_14003D67C
0x14003cf20  mov     ecx, 0AFDh
0x14003cf25  cmp     ax, cx
0x14003cf28  jz      loc_14003D67C
0x14003cf2e  mov     ecx, 0FA09h
0x14003cf33  cmp     ax, cx
0x14003cf36  jz      loc_14003D67C
0x14003cf3c  xorps   xmm0, xmm0
0x14003cf3f  movups  [rsp+138h+Src], xmm0
0x14003cf47  xor     esi, esi
0x14003cf49  mov     [rsp+138h+var_104], esi
0x14003cf4d  lea     r12d, [rdx+10h]
0x14003cf51  cmp     r13d, r12d
0x14003cf54  jb      loc_14003D675
0x14003cf5a  xor     al, al
0x14003cf5c  mov     [rsp+138h+var_100], eax
0x14003cf60  mov     [rsp+138h+var_FC], al
0x14003cf64  cmp     [rsp+138h+arg_30], r12d
0x14003cf6c  jb      loc_14003D675
0x14003cf72  xor     ecx, ecx; Irp
0x14003cf74  call    cs:__imp_IoIs32bitProcess
0x14003cf7b  nop     dword ptr [rax+rax+00h]
0x14003cf80  test    al, al
0x14003cf82  jz      short loc_14003CF99
0x14003cf84  test    r14b, r14b
0x14003cf87  lea     r14d, [rsi+1]
0x14003cf8b  jz      short loc_14003CFCC
0x14003cf8d  mov     [rsp+138h+var_C0], r12
0x14003cf92  mov     [rsp+138h+var_C0], r14
0x14003cf97  jmp     short loc_14003CFB4
0x14003cf99  test    r14b, r14b
0x14003cf9c  mov     r14d, 1
0x14003cfa2  jz      short loc_14003CFCC
0x14003cfa4  mov     [rsp+138h+var_B8], r12
0x14003cfac  mov     [rsp+138h+var_B8], r14
0x14003cfb4  mov     r8d, 4; Alignment
0x14003cfba  mov     rdx, r14; Length
0x14003cfbd  mov     rcx, r15; Address
0x14003cfc0  call    cs:__imp_ProbeForRead
0x14003cfc7  nop     dword ptr [rax+rax+00h]
0x14003cfcc  cmp     [rsp+138h+AccessMode], 0
0x14003cfd1  jz      short loc_14003CFDD
0x14003cfd3  mov     rcx, r15
0x14003cfd6  call    RtlReadULongFromUser
0x14003cfdb  jmp     short loc_14003CFE0
0x14003cfdd  mov     eax, [r15]
0x14003cfe0  mov     dword ptr [rsp+138h+Src], eax
0x14003cfe7  sub     eax, 3
0x14003cfea  jz      loc_14003D42B
0x14003cff0  sub     eax, 1
0x14003cff3  jz      loc_14003D3DE
0x14003cff9  sub     eax, 1
0x14003cffc  jz      loc_14003D15B
0x14003d002  sub     eax, 1
0x14003d005  jz      loc_14003D150
0x14003d00b  sub     eax, 1
0x14003d00e  jz      loc_14003D0F3
0x14003d014  sub     eax, 1
0x14003d017  jz      short loc_14003D061
0x14003d019  sub     eax, 2
0x14003d01c  jz      short loc_14003D042
0x14003d01e  cmp     eax, 4
0x14003d021  jnz     loc_14003D67C
0x14003d027  lea     rdx, [rsp+138h+Src+8]
0x14003d02f  mov     rcx, rdi
0x14003d032  call    AfdGetDeliveryStatus
0x14003d037  mov     esi, eax
0x14003d039  mov     [rsp+138h+var_104], eax
0x14003d03d  jmp     loc_14003D5EC
0x14003d042  mov     eax, [rdi+1D0h]
0x14003d048  mov     dword ptr [rsp+138h+Src+8], eax
0x14003d04f  mov     eax, [rdi+1D4h]
0x14003d055  mov     dword ptr [rsp+138h+Src+0Ch], eax
0x14003d05c  jmp     loc_14003D5EC
0x14003d061  cmp     byte ptr [rdi+2], 4
0x14003d065  jnz     short loc_14003D0E3
0x14003d067  mov     r12d, 0AFD1h
0x14003d06d  cmp     [rdi], r12w
0x14003d071  jz      short loc_14003D0E3
0x14003d073  mov     rcx, rdi
0x14003d076  call    AfdGetConnectionReferenceFromEndpoint
0x14003d07b  mov     r8, rax
0x14003d07e  test    rax, rax
0x14003d081  jz      short loc_14003D0E3
0x14003d083  mov     rcx, 0FFFFF78000000008h
0x14003d08d  mov     rcx, [rcx]
0x14003d090  sub     rcx, [rax+28h]
0x14003d094  mov     rax, 0D6BF94D5E57A42BDh
0x14003d09e  imul    rcx
0x14003d0a1  add     rdx, rcx
0x14003d0a4  sar     rdx, 17h
0x14003d0a8  mov     rax, rdx
0x14003d0ab  shr     rax, 3Fh
0x14003d0af  add     rdx, rax
0x14003d0b2  mov     dword ptr [rsp+138h+Src+8], edx
0x14003d0b9  or      rax, 0FFFFFFFFFFFFFFFFh
0x14003d0bd  lock xadd [r8+30h], rax
0x14003d0c3  sub     rax, 1
0x14003d0c7  jg      loc_14003D5EC
0x14003d0cd  test    rax, rax
0x14003d0d0  jnz     loc_14003D4FA
0x14003d0d6  mov     rcx, r8
0x14003d0d9  call    AfdCloseConnection
0x14003d0de  jmp     loc_14003D5EC
0x14003d0e3  mov     dword ptr [rsp+138h+Src+8], 0FFFFFFFFh
0x14003d0ee  jmp     loc_14003D5EC
0x14003d0f3  movzx   eax, word ptr [rdi]
0x14003d0f6  mov     ecx, 0AFD2h
0x14003d0fb  and     ax, cx
0x14003d0fe  cmp     ax, cx
0x14003d101  jnz     short loc_14003D145
0x14003d103  cmp     byte ptr [rdi+2], 4
0x14003d107  jnz     short loc_14003D145
0x14003d109  mov     rcx, rdi
0x14003d10c  call    AfdGetConnectionReferenceFromEndpoint
0x14003d111  test    rax, rax
0x14003d114  jz      short loc_14003D145
0x14003d116  mov     ecx, [rax+94h]
0x14003d11c  mov     dword ptr [rsp+138h+Src+8], ecx
0x14003d123  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14003d127  lock xadd [rax+30h], rcx
0x14003d12d  sub     rcx, 1
0x14003d131  jg      loc_14003D5EC
0x14003d137  test    rcx, rcx
0x14003d13a  jnz     loc_14003D4FA
0x14003d140  mov     rcx, rax
0x14003d143  jmp     short loc_14003D0D9
0x14003d145  mov     eax, cs:AfdSendWindowSize
0x14003d14b  jmp     loc_14003D5E5
0x14003d150  mov     eax, cs:AfdReceiveWindowSize
0x14003d156  jmp     loc_14003D5E5
0x14003d15b  mov     eax, [rdi+8]
0x14003d15e  bt      eax, 8
0x14003d162  jb      loc_14003D42B
0x14003d168  cmp     r13d, r12d
0x14003d16b  jbe     loc_14003D42B
0x14003d171  lea     rax, [rdi+2]
0x14003d175  mov     [rsp+138h+var_F0], rax
0x14003d17a  mov     al, [rax]
0x14003d17c  sub     al, 3
0x14003d17e  cmp     al, r14b
0x14003d181  ja      loc_14003D42B
0x14003d187  xor     eax, eax
0x14003d189  xorps   xmm0, xmm0
0x14003d18c  movups  [rsp+138h+VirtualAddress], xmm0
0x14003d194  movups  [rsp+138h+var_78], xmm0
0x14003d19c  movups  [rsp+138h+var_78+0Ch], xmm0
0x14003d1a4  lea     r12d, [r13-10h]
0x14003d1a8  mov     [rsp+138h+var_E0], r12d
0x14003d1ad  lea     rcx, [r15+10h]; VirtualAddress
0x14003d1b1  mov     [rsp+138h+Irp], rax; Irp
0x14003d1b6  mov     r9b, r14b; ChargeQuota
0x14003d1b9  xor     r8d, r8d; SecondaryBuffer
0x14003d1bc  mov     edx, r12d; Length
0x14003d1bf  call    cs:__imp_IoAllocateMdl
0x14003d1c6  nop     dword ptr [rax+rax+00h]
0x14003d1cb  mov     r15, rax
0x14003d1ce  mov     [rsp+138h+var_B0], rax
0x14003d1d6  test    rax, rax
0x14003d1d9  jz      loc_14003D3C0
0x14003d1df  mov     r8d, r14d; Operation
0x14003d1e2  mov     dl, [rsp+138h+AccessMode]; AccessMode
0x14003d1e6  mov     rcx, rax; MemoryDescriptorList
0x14003d1e9  call    cs:__imp_MmProbeAndLockPages
0x14003d1f0  nop     dword ptr [rax+rax+00h]
0x14003d1f5  mov     [rsp+138h+var_104], 0
0x14003d1fd  jmp     short loc_14003D234
0x14003d1ff  mov     r14d, 1
0x14003d205  mov     al, [rsp+138h+var_FC]
0x14003d209  mov     [rsp+138h+var_100], eax
0x14003d20d  mov     r15, [rsp+138h+var_B0]
0x14003d215  mov     al, [rsp+138h+var_F8]
0x14003d219  mov     [rsp+138h+AccessMode], al
0x14003d21d  mov     rcx, [rsp+138h+var_A8]
0x14003d225  mov     [rsp+138h+var_E8], rcx
0x14003d22a  mov     rdi, [rsp+138h+var_D0]
0x14003d22f  mov     r12d, [rsp+138h+var_E0]
0x14003d234  mov     esi, [rsp+138h+var_104]
0x14003d238  test    esi, esi
0x14003d23a  js      loc_14003D3A3
0x14003d240  test    byte ptr [r15+0Ah], 5
0x14003d245  jz      short loc_14003D24D
0x14003d247  mov     rax, [r15+18h]
0x14003d24b  jmp     short loc_14003D274
0x14003d24d  mov     [rsp+138h+Priority], 40000000h; Priority
0x14003d255  mov     dword ptr [rsp+138h+Irp], 0; BugCheckOnFailure
0x14003d25d  xor     r9d, r9d; RequestedAddress
0x14003d260  mov     r8d, r14d; CacheType
0x14003d263  xor     edx, edx; AccessMode
0x14003d265  mov     rcx, r15; MemoryDescriptorList
0x14003d268  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14003d26f  nop     dword ptr [rax+rax+00h]
0x14003d274  mov     [rsp+138h+var_60], rax
0x14003d27c  mov     r13d, 1AFDh
0x14003d282  test    rax, rax
0x14003d285  jz      loc_14003D383
0x14003d28b  mov     dword ptr [rsp+138h+var_68], r12d
0x14003d293  mov     [rsp+138h+var_D0], 9
0x14003d29c  lea     rax, [rsp+138h+VirtualAddress]
0x14003d2a4  mov     [rsp+138h+var_C8], rax
0x14003d2a9  mov     dword ptr [rsp+138h+VirtualAddress], 0
0x14003d2b4  mov     qword ptr [rsp+138h+VirtualAddress+8], 0
0x14003d2c0  mov     dword ptr [rsp+138h+var_78], 0
0x14003d2cb  mov     qword ptr [rsp+138h+var_78+8], 0
0x14003d2d7  movzx   eax, word ptr [rdi]
0x14003d2da  mov     r12d, 0AFD1h
0x14003d2e0  cmp     ax, r12w
0x14003d2e4  jz      short loc_14003D325
0x14003d2e6  cmp     ax, r13w
0x14003d2ea  jz      short loc_14003D325
0x14003d2ec  test    byte ptr [rdi+5], 10h
0x14003d2f0  jz      short loc_14003D2F8
0x14003d2f2  test    [rdi+6], r14b
0x14003d2f6  jnz     short loc_14003D325
0x14003d2f8  mov     eax, [rdi+8]
0x14003d2fb  mov     rsi, [rsp+138h+var_F0]
0x14003d300  test    r14b, al
0x14003d303  jnz     short loc_14003D32A
0x14003d305  cmp     byte ptr [rsi], 4
0x14003d308  jz      short loc_14003D32A
0x14003d30a  mov     rcx, rdi
0x14003d30d  call    AfdPreventUnbind
0x14003d312  mov     ecx, [rsp+138h+var_100]
0x14003d316  movzx   ecx, cl
0x14003d319  test    al, al
0x14003d31b  cmovnz  ecx, r14d
0x14003d31f  mov     [rsp+138h+var_100], ecx
0x14003d323  jmp     short loc_14003D32E
0x14003d325  mov     rsi, [rsp+138h+var_F0]
0x14003d32a  mov     ecx, [rsp+138h+var_100]
0x14003d32e  mov     al, [rsi]
0x14003d330  cmp     al, 3
0x14003d332  jnz     short loc_14003D338
0x14003d334  test    cl, cl
0x14003d336  jnz     short loc_14003D33C
0x14003d338  cmp     al, 4
0x14003d33a  jnz     short loc_14003D369
0x14003d33c  mov     byte ptr [rsp+138h+Priority], 0Ch; char
0x14003d341  mov     dword ptr [rsp+138h+Irp], 4; Length
0x14003d349  lea     r9, [rsp+138h+Src+8]; VirtualAddress
0x14003d351  mov     r8d, 10h; Size
0x14003d357  lea     rdx, [rsp+138h+var_D0]; Src
0x14003d35c  mov     rcx, [rdi+18h]; FileObject
0x14003d360  call    AfdIssueDeviceControl
0x14003d365  mov     esi, eax
0x14003d367  jmp     short loc_14003D36E
0x14003d369  mov     esi, 0C0000184h
0x14003d36e  mov     [rsp+138h+var_104], esi
0x14003d372  cmp     byte ptr [rsp+138h+var_100], 0
0x14003d377  jz      short loc_14003D392
0x14003d379  mov     rcx, rdi
0x14003d37c  call    AfdReallowUnbind
0x14003d381  jmp     short loc_14003D392
0x14003d383  mov     esi, 0C000009Ah
0x14003d388  mov     [rsp+138h+var_104], esi
0x14003d38c  mov     r12d, 0AFD1h
0x14003d392  mov     rcx, r15; MemoryDescriptorList
0x14003d395  call    cs:__imp_MmUnlockPages
0x14003d39c  nop     dword ptr [rax+rax+00h]
0x14003d3a1  jmp     short loc_14003D3AF
0x14003d3a3  mov     r12d, 0AFD1h
0x14003d3a9  mov     r13d, 1AFDh
0x14003d3af  mov     rcx, r15; Mdl
0x14003d3b2  call    cs:__imp_IoFreeMdl
0x14003d3b9  nop     dword ptr [rax+rax+00h]
0x14003d3be  jmp     short loc_14003D3D5
0x14003d3c0  mov     esi, 0C000009Ah
0x14003d3c5  mov     [rsp+138h+var_104], esi
0x14003d3c9  mov     r12d, 0AFD1h
0x14003d3cf  mov     r13d, 1AFDh
0x14003d3d5  test    esi, esi
  ... truncated ...
```
