# VsmmPhuIoctlCommit

- ea: `0x1400a0d0c`
- end: `0x1400a154c`
- name: `VsmmPhuIoctlCommit`
- size: `2112`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140035708`

## callees

- `0x1400029c0`
- `0x140006b68`
- `0x140006f64`
- `0x140007004`
- `0x14000a010`
- `0x140021c60`
- `0x1400248f4`
- `0x140024e18`
- `0x1400309d0`
- `0x140033b00`
- `0x1400347a4`
- `0x140034b64`
- `0x1400a0d0c`
- `0x1400b44f4`
- `0x1400f9410`

## import_xrefs

- `winhvr!WinHvPersistPartitionReservedPages` at `0x1400a1344`
- `winhvr!WinHvPersistPartitionReservedPages` at `0x1400a1344`

## string_xrefs

- `0x1400a0e04`: `VsmmPhuIoctlCommit`
- `0x1400a0f85`: `VsmmPhuIoctlCommit`
- `0x1400a1112`: `VsmmPhuIoctlCommit`
- `0x1400a11f9`: `VsmmPhuIoctlCommit`
- `0x1400a1236`: `VsmmPhuIoctlCommit`
- `0x1400a13bc`: `VsmmPhuIoctlCommit`
- `0x1400a1468`: `VsmmPhuIoctlCommit`

## pseudocode

```c
__int64 __fastcall VsmmPhuIoctlCommit(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  char *v5; // r15
  __int64 v6; // r12
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r15
  int v10; // edi
  char v11; // di
  bool v12; // r12
  __int64 v13; // rax
  void *v14; // rdx
  __int64 v15; // r11
  __int64 Next; // rax
  __int64 i; // rax
  __int64 v19; // r11
  int v20; // eax
  int v21; // r8d
  int v22; // [rsp+20h] [rbp-E0h]
  _BYTE v23[4]; // [rsp+40h] [rbp-C0h] BYREF
  int v24; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v25; // [rsp+48h] [rbp-B8h] BYREF
  char *v26; // [rsp+50h] [rbp-B0h]
  __int64 v27; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v28; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v29; // [rsp+68h] [rbp-98h] BYREF
  __int64 v30; // [rsp+70h] [rbp-90h] BYREF
  __int64 v31; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v32[2]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v33[32]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v34[16]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v35[16]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 *v36; // [rsp+D0h] [rbp-30h]
  __int64 v37; // [rsp+D8h] [rbp-28h]
  __int64 *v38; // [rsp+E0h] [rbp-20h]
  __int64 v39; // [rsp+E8h] [rbp-18h]
  __int64 v40; // [rsp+F0h] [rbp-10h]
  __int64 v41; // [rsp+F8h] [rbp-8h]
  int *v42; // [rsp+100h] [rbp+0h]
  __int64 v43; // [rsp+108h] [rbp+8h]
  __int64 v44; // [rsp+110h] [rbp+10h]
  int v45; // [rsp+118h] [rbp+18h] BYREF
  int v46; // [rsp+11Ch] [rbp+1Ch]
  __int64 *v47; // [rsp+120h] [rbp+20h]
  __int64 v48; // [rsp+128h] [rbp+28h]
  __int64 *v49; // [rsp+130h] [rbp+30h]
  __int64 v50; // [rsp+138h] [rbp+38h]
  __int64 *v51; // [rsp+140h] [rbp+40h]
  __int64 v52; // [rsp+148h] [rbp+48h]
  __int64 *v53; // [rsp+150h] [rbp+50h]
  __int64 v54; // [rsp+158h] [rbp+58h]
  __int64 *v55; // [rsp+160h] [rbp+60h]
  __int64 v56; // [rsp+168h] [rbp+68h]
  _BYTE *v57; // [rsp+170h] [rbp+70h]
  __int64 v58; // [rsp+178h] [rbp+78h]

  v5 = (char *)VidDeviceExtension + 1640;
  v26 = (char *)VidDeviceExtension + 1640;
  VidLockAcquireShared((char *)VidDeviceExtension + 1640, a2, a3, a4);
  v6 = a1 + 3736;
  v27 = a1 + 3736;
  VidObjectLockAcquireExclusive(a1 + 3736);
  if ( (BYTE1(WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink) & 4) != 0 )
    McTemplateK0j_EtwWriteTransfer(v7, &VID_PARTITION_PERSIST_START, v8, a1 + 656);
  if ( *(_DWORD *)(a1 + 8632) != 1 || *(_BYTE *)(a1 + 8656) )
  {
    v8 = 3221266435LL;
    v10 = -1073700861;
    if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
    {
      tlgCreate1Sz_char(v34, "VsmmPhuIoctlCommit");
      tlgCreate1Sz_char(v35, "onecore\\vm\\vid\\sys\\vsmm\\vsmmphu.c");
      v24 = v21;
      v36 = &v25;
      LODWORD(v25) = 560;
      v38 = (__int64 *)&v24;
      v37 = 4;
      v42 = &v45;
      v44 = *(_QWORD *)(a1 + 128);
      v45 = *(unsigned __int16 *)(a1 + 120);
      v30 = *(_QWORD *)(a1 + 648);
      v47 = &v30;
      v23[0] = *(_BYTE *)(a1 + 8656);
      v49 = (__int64 *)v23;
      v39 = 4;
      v40 = a1 + 656;
      v41 = 16;
      v43 = 2;
      v46 = 0;
      v48 = 8;
      v50 = 1;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &unk_14004B6A0, 0, 0, 11, v33);
    }
  }
  else
  {
    v9 = *(_QWORD *)(a1 + 8648);
    if ( *(_DWORD *)(a1 + 8636) != 2 || *(_QWORD *)(v9 + 1304) == *(_QWORD *)(v9 + 1296) )
    {
      v11 = 0;
      v25 = -1;
      v12 = 0;
      while ( 1 )
      {
        Next = VidHandleTableGetNext(a1 + 3232, &v25);
        if ( !Next )
          break;
        if ( (*(_DWORD *)(Next + 264) & 0x800) != 0 )
        {
          v13 = *(_QWORD *)(Next + 712);
          if ( v11 )
          {
            v7 = v13 != 0;
            if ( v12 != (_DWORD)v7 )
            {
              v10 = -1070137276;
              if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
              {
                tlgCreate1Sz_char(v34, "VsmmPhuIoctlCommit");
                tlgCreate1Sz_char(v35, "onecore\\vm\\vid\\sys\\vsmm\\vsmmphu.c");
                LODWORD(v25) = 627;
                v36 = &v25;
                v14 = &unk_14004B540;
                v37 = 4;
                v38 = (__int64 *)&v24;
                v42 = &v45;
                v44 = *(_QWORD *)(a1 + 128);
                v45 = *(unsigned __int16 *)(a1 + 120);
                v29 = *(_QWORD *)(a1 + 648);
                v47 = &v29;
                v28 = *(_QWORD *)(v15 + 24);
                v49 = &v28;
                v31 = *(_QWORD *)(v15 + 40);
                v51 = &v31;
                v32[0] = *(_QWORD *)(v15 + 48);
                v53 = v32;
                v30 = *(int *)(v15 + 264);
                v55 = &v30;
                v57 = v23;
                v22 = 15;
                v24 = -1070137276;
                v39 = 4;
                v40 = a1 + 656;
                v41 = 16;
                v43 = 2;
                v23[0] = v12;
                v58 = 1;
LABEL_17:
                v48 = 8;
                v46 = 0;
                v56 = 8;
                v54 = 8;
                v52 = 8;
                v50 = 8;
                tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, v14, 0, 0, v22, v33);
              }
              goto LABEL_18;
            }
          }
          else
          {
            v11 = 1;
            v12 = v13 != 0;
          }
        }
      }
      v25 = -1;
      for ( i = VidHandleTableGetNext(a1 + 3264, &v25); ; i = VidHandleTableGetNext(a1 + 3264, &v25) )
      {
        if ( !i )
        {
          if ( *(_DWORD *)(a1 + 8660) == 1 )
          {
            v10 = -1073700861;
            VidTracePartitionErrorInternal0(
              (unsigned int)"VsmmPhuIoctlCommit",
              (unsigned int)"onecore\\vm\\vid\\sys\\vsmm\\vsmmphu.c",
              678,
              a1 + 656,
              a1 + 120,
              *(_QWORD *)(a1 + 648),
              -1073700861);
          }
          else if ( *(_DWORD *)(a1 + 8660) == 3
                 && (v20 = WinHvPersistPartitionReservedPages(*(_QWORD *)(a1 + 648)), v10 = v20, v20 < 0) )
          {
            VidTracePartitionErrorInternal0(
              (unsigned int)"VsmmPhuIoctlCommit",
              (unsigned int)"onecore\\vm\\vid\\sys\\vsmm\\vsmmphu.c",
              691,
              a1 + 656,
              a1 + 120,
              *(_QWORD *)(a1 + 648),
              v20);
          }
          else
          {
            if ( *(_DWORD *)(a1 + 8636) == 2 )
              VsmmPhuStoreItemReadyModifyAll(v9);
            *(_DWORD *)(a1 + 8632) = 2;
            *(_DWORD *)(a1 + 8640) = 0;
            if ( (unsigned int)dword_140065110 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
            {
              tlgCreate1Sz_char(v34, "VsmmPhuIoctlCommit");
              tlgCreate1Sz_char(v35, "onecore\\vm\\vid\\sys\\vsmm\\vsmmphu.c");
              LODWORD(v25) = 718;
              v36 = &v25;
              v37 = 4;
              v38 = (__int64 *)(a1 + 656);
              v39 = 16;
              tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &unk_14004B4FD, 0, 0, 6, v33);
            }
            v10 = 0;
          }
          goto LABEL_18;
        }
        if ( *(_QWORD *)(i + 296) )
        {
          v7 = *(_QWORD *)(i + 384);
          if ( !*(_QWORD *)(v7 + 712) )
            break;
        }
      }
      v10 = -1070137282;
      if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
      {
        tlgCreate1Sz_char(v34, "VsmmPhuIoctlCommit");
        tlgCreate1Sz_char(v35, "onecore\\vm\\vid\\sys\\vsmm\\vsmmphu.c");
        LODWORD(v25) = 665;
        v36 = &v25;
        v14 = &unk_14004B602;
        v37 = 4;
        v38 = (__int64 *)&v24;
        v42 = &v45;
        v44 = *(_QWORD *)(a1 + 128);
        v45 = *(unsigned __int16 *)(a1 + 120);
        v30 = *(_QWORD *)(a1 + 648);
        v47 = &v30;
        v32[0] = *(_QWORD *)(v19 + 248);
        v49 = v32;
        v31 = *(_QWORD *)(v19 + 256);
        v51 = &v31;
        v29 = *(_QWORD *)(v19 + 264);
        v53 = &v29;
        v28 = *(int *)(v19 + 292);
        v55 = &v28;
        v22 = 14;
        v24 = -1070137282;
        v39 = 4;
        v40 = a1 + 656;
        v41 = 16;
        v43 = 2;
        goto LABEL_17;
      }
LABEL_18:
      v6 = v27;
    }
    else
    {
      v10 = -1070137273;
      if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
      {
        tlgCreate1Sz_char(v34, "VsmmPhuIoctlCommit");
        tlgCreate1Sz_char(v35, "onecore\\vm\\vid\\sys\\vsmm\\vsmmphu.c");
        v24 = 594;
        v36 = (__int64 *)&v24;
        v37 = 4;
        v38 = &v25;
        LODWORD(v25) = -1070137273;
        v42 = &v45;
        v44 = *(_QWORD *)(a1 + 128);
        v45 = *(unsigned __int16 *)(a1 + 120);
        v27 = *(_QWORD *)(a1 + 648);
        v47 = &v27;
        v28 = *(_QWORD *)(v9 + 1304);
        v49 = &v28;
        v29 = *(_QWORD *)(v9 + 1296);
        v51 = &v29;
        v39 = 4;
        v40 = a1 + 656;
        v41 = 16;
        v43 = 2;
        v46 = 0;
        v48 = 8;
        v50 = 8;
        v52 = 8;
        tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &unk_14004B717, 0, 0, 12, v33);
      }
    }
    v5 = v26;
  }
  if ( (BYTE1(WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink) & 4) != 0 )
    McTemplateK0x_EtwWriteTransfer(v7, &VID_PARTITION_PERSIST_STOP, v8, v10);
  VidObjectLockRelease(v6);
  VidLockRelease(v5);
  if ( v10 < 0 )
    VidTraceErrorStatusPartitionInternal0(
      (unsigned int)"VsmmPhuIoctlCommit",
      (unsigned int)"onecore\\vm\\vid\\sys\\vsmm\\vsmmphu.c",
      733,
      v10,
      a1 + 656);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1400a0d0c  push    rbp
0x1400a0d0e  push    rbx
0x1400a0d0f  push    rsi
0x1400a0d10  push    rdi
0x1400a0d11  push    r12
0x1400a0d13  push    r13
0x1400a0d15  push    r14
0x1400a0d17  push    r15
0x1400a0d19  lea     rbp, [rsp-98h]
0x1400a0d21  sub     rsp, 198h
0x1400a0d28  mov     rax, cs:__security_cookie
0x1400a0d2f  xor     rax, rsp
0x1400a0d32  mov     [rbp+0D0h+var_50], rax
0x1400a0d39  mov     r15, cs:VidDeviceExtension
0x1400a0d40  mov     rbx, rcx
0x1400a0d43  add     r15, 668h
0x1400a0d4a  mov     rcx, r15
0x1400a0d4d  mov     [rsp+1D0h+var_180], r15
0x1400a0d52  call    VidLockAcquireShared
0x1400a0d57  lea     r12, [rbx+0E98h]
0x1400a0d5e  mov     rcx, r12
0x1400a0d61  mov     [rsp+1D0h+var_178], r12
0x1400a0d66  call    VidObjectLockAcquireExclusive
0x1400a0d6b  mov     r9d, 4
0x1400a0d71  lea     r14, [rbx+290h]
0x1400a0d78  test    byte ptr cs:WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink+1, r9b
0x1400a0d7f  jz      short loc_1400A0D90
0x1400a0d81  mov     r9, r14
0x1400a0d84  lea     rdx, VID_PARTITION_PERSIST_START
0x1400a0d8b  call    McTemplateK0j_EtwWriteTransfer
0x1400a0d90  xor     r13d, r13d
0x1400a0d93  cmp     dword ptr [rbx+21B8h], 1
0x1400a0d9a  jnz     loc_1400A1433
0x1400a0da0  cmp     [rbx+21D0h], r13b
0x1400a0da7  jnz     loc_1400A1433
0x1400a0dad  mov     r15, [rbx+21C8h]
0x1400a0db4  lea     esi, [r13+2]
0x1400a0db8  cmp     [rbx+21BCh], esi
0x1400a0dbe  jnz     loc_1400A0F06
0x1400a0dc4  mov     rax, [r15+510h]
0x1400a0dcb  cmp     [r15+518h], rax
0x1400a0dd2  jz      loc_1400A0F06
0x1400a0dd8  mov     eax, cs:dword_140065110
0x1400a0dde  mov     edi, 0C0370047h
0x1400a0de3  cmp     eax, esi
0x1400a0de5  jbe     loc_1400A10CC
0x1400a0deb  mov     edx, 100h
0x1400a0df0  lea     rcx, dword_140065110
0x1400a0df7  call    _tlgKeywordOn
0x1400a0dfc  test    al, al
0x1400a0dfe  jz      loc_1400A10CC
0x1400a0e04  lea     rdx, aVsmmphuioctlco; "VsmmPhuIoctlCommit"
0x1400a0e0b  lea     rcx, [rbp+0D0h+var_120]
0x1400a0e0f  call    _tlgCreate1Sz_char
0x1400a0e14  lea     rdx, aOnecoreVmVidSy_9; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphu.c"
0x1400a0e1b  lea     rcx, [rbp+0D0h+var_110]
0x1400a0e1f  call    _tlgCreate1Sz_char
0x1400a0e24  lea     rax, [rsp+1D0h+var_18C]
0x1400a0e29  mov     [rsp+1D0h+var_18C], 252h
0x1400a0e31  mov     [rbp+0D0h+var_100], rax
0x1400a0e35  lea     rdx, unk_14004B717
0x1400a0e3c  lea     rax, [rsp+1D0h+var_188]
0x1400a0e41  mov     [rbp+0D0h+var_F8], 4
0x1400a0e49  mov     [rbp+0D0h+var_F0], rax
0x1400a0e4d  lea     rcx, dword_140065110
0x1400a0e54  lea     rax, [rbp+0D0h+var_B8]
0x1400a0e58  mov     dword ptr [rsp+1D0h+var_188], edi
0x1400a0e5c  mov     [rbp+0D0h+var_D0], rax
0x1400a0e60  xor     r9d, r9d
0x1400a0e63  mov     rax, [rbx+80h]
0x1400a0e6a  xor     r8d, r8d
0x1400a0e6d  mov     [rbp+0D0h+var_C0], rax
0x1400a0e71  movzx   eax, word ptr [rbx+78h]
0x1400a0e75  mov     [rbp+0D0h+var_B8], eax
0x1400a0e78  mov     rax, [rbx+288h]
0x1400a0e7f  mov     [rsp+1D0h+var_178], rax
0x1400a0e84  lea     rax, [rsp+1D0h+var_178]
0x1400a0e89  mov     [rbp+0D0h+var_B0], rax
0x1400a0e8d  mov     rax, [r15+518h]
0x1400a0e94  mov     [rsp+1D0h+var_170], rax
0x1400a0e99  lea     rax, [rsp+1D0h+var_170]
0x1400a0e9e  mov     [rbp+0D0h+var_A0], rax
0x1400a0ea2  mov     rax, [r15+510h]
0x1400a0ea9  mov     [rsp+1D0h+var_168], rax
0x1400a0eae  lea     rax, [rsp+1D0h+var_168]
0x1400a0eb3  mov     [rbp+0D0h+var_90], rax
0x1400a0eb7  lea     rax, [rbp+0D0h+var_140]
0x1400a0ebb  mov     [rsp+1D0h+var_1A8], rax
0x1400a0ec0  mov     dword ptr [rsp+1D0h+var_1B0], 0Ch
0x1400a0ec8  mov     [rbp+0D0h+var_E8], 4
0x1400a0ed0  mov     [rbp+0D0h+var_E0], r14
0x1400a0ed4  mov     [rbp+0D0h+var_D8], 10h
0x1400a0edc  mov     [rbp+0D0h+var_C8], rsi
0x1400a0ee0  mov     [rbp+0D0h+var_B4], r13d
0x1400a0ee4  mov     [rbp+0D0h+var_A8], 8
0x1400a0eec  mov     [rbp+0D0h+var_98], 8
0x1400a0ef4  mov     [rbp+0D0h+var_88], 8
0x1400a0efc  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400a0f01  jmp     loc_1400A10CC
0x1400a0f06  mov     dil, r13b
0x1400a0f09  mov     [rsp+1D0h+var_188], 0FFFFFFFFFFFFFFFFh
0x1400a0f12  mov     r12b, r13b
0x1400a0f15  lea     r13, [rbx+0CA0h]
0x1400a0f1c  jmp     loc_1400A114E
0x1400a0f21  test    dword ptr [r11+108h], 800h
0x1400a0f2c  jz      loc_1400A114E
0x1400a0f32  mov     rax, [r11+2C8h]
0x1400a0f39  test    dil, dil
0x1400a0f3c  jz      loc_1400A1144
0x1400a0f42  xor     ecx, ecx
0x1400a0f44  test    rax, rax
0x1400a0f47  movzx   eax, r12b
0x1400a0f4b  setnz   cl
0x1400a0f4e  cmp     eax, ecx
0x1400a0f50  jz      loc_1400A114E
0x1400a0f56  mov     eax, cs:dword_140065110
0x1400a0f5c  mov     edi, 0C0370044h
0x1400a0f61  cmp     eax, esi
0x1400a0f63  jbe     loc_1400A10C7
0x1400a0f69  mov     edx, 100h
0x1400a0f6e  lea     rcx, dword_140065110
0x1400a0f75  call    _tlgKeywordOn
0x1400a0f7a  xor     r13d, r13d
0x1400a0f7d  test    al, al
0x1400a0f7f  jz      loc_1400A10C7
0x1400a0f85  lea     rdx, aVsmmphuioctlco; "VsmmPhuIoctlCommit"
0x1400a0f8c  lea     rcx, [rbp+0D0h+var_120]
0x1400a0f90  call    _tlgCreate1Sz_char
0x1400a0f95  lea     rdx, aOnecoreVmVidSy_9; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphu.c"
0x1400a0f9c  lea     rcx, [rbp+0D0h+var_110]
0x1400a0fa0  call    _tlgCreate1Sz_char
0x1400a0fa5  lea     rax, [rsp+1D0h+var_188]
0x1400a0faa  mov     dword ptr [rsp+1D0h+var_188], 273h
0x1400a0fb2  mov     [rbp+0D0h+var_100], rax
0x1400a0fb6  lea     rdx, unk_14004B540
0x1400a0fbd  lea     rax, [rsp+1D0h+var_18C]
0x1400a0fc2  mov     [rbp+0D0h+var_F8], 4
0x1400a0fca  mov     [rbp+0D0h+var_F0], rax
0x1400a0fce  lea     rax, [rbp+0D0h+var_B8]
0x1400a0fd2  mov     [rbp+0D0h+var_D0], rax
0x1400a0fd6  mov     rax, [rbx+80h]
0x1400a0fdd  mov     [rbp+0D0h+var_C0], rax
0x1400a0fe1  movzx   eax, word ptr [rbx+78h]
0x1400a0fe5  mov     [rbp+0D0h+var_B8], eax
0x1400a0fe8  mov     rax, [rbx+288h]
0x1400a0fef  mov     [rsp+1D0h+var_168], rax
0x1400a0ff4  lea     rax, [rsp+1D0h+var_168]
0x1400a0ff9  mov     [rbp+0D0h+var_B0], rax
0x1400a0ffd  mov     rax, [r11+18h]
0x1400a1001  mov     [rsp+1D0h+var_170], rax
0x1400a1006  lea     rax, [rsp+1D0h+var_170]
0x1400a100b  mov     [rbp+0D0h+var_A0], rax
0x1400a100f  mov     rax, [r11+28h]
0x1400a1013  mov     [rsp+1D0h+var_158], rax
0x1400a1018  lea     rax, [rsp+1D0h+var_158]
0x1400a101d  mov     [rbp+0D0h+var_90], rax
0x1400a1021  mov     rax, [r11+30h]
0x1400a1025  mov     [rbp+0D0h+var_150], rax
0x1400a1029  lea     rax, [rbp+0D0h+var_150]
0x1400a102d  mov     [rbp+0D0h+var_80], rax
0x1400a1031  movsxd  rax, dword ptr [r11+108h]
0x1400a1038  mov     [rsp+1D0h+var_160], rax
0x1400a103d  lea     rax, [rsp+1D0h+var_160]
0x1400a1042  mov     [rbp+0D0h+var_70], rax
0x1400a1046  lea     rax, [rsp+1D0h+var_190]
0x1400a104b  mov     [rbp+0D0h+var_60], rax
0x1400a104f  lea     rax, [rbp+0D0h+var_140]
0x1400a1053  mov     [rsp+1D0h+var_1A8], rax
0x1400a1058  mov     dword ptr [rsp+1D0h+var_1B0], 0Fh
0x1400a1060  mov     [rsp+1D0h+var_18C], edi
0x1400a1064  mov     [rbp+0D0h+var_E8], 4
0x1400a106c  mov     [rbp+0D0h+var_E0], r14
0x1400a1070  mov     [rbp+0D0h+var_D8], 10h
0x1400a1078  mov     [rbp+0D0h+var_C8], rsi
0x1400a107c  mov     [rsp+1D0h+var_190], r12b
0x1400a1081  mov     [rbp+0D0h+var_58], 1
0x1400a1089  xor     r9d, r9d
0x1400a108c  mov     [rbp+0D0h+var_A8], 8
0x1400a1094  xor     r8d, r8d
0x1400a1097  mov     [rbp+0D0h+var_B4], r13d
0x1400a109b  lea     rcx, dword_140065110
0x1400a10a2  mov     [rbp+0D0h+var_68], 8
0x1400a10aa  mov     [rbp+0D0h+var_78], 8
0x1400a10b2  mov     [rbp+0D0h+var_88], 8
0x1400a10ba  mov     [rbp+0D0h+var_98], 8
0x1400a10c2  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400a10c7  mov     r12, [rsp+1D0h+var_178]
0x1400a10cc  mov     r15, [rsp+1D0h+var_180]
0x1400a10d1  test    byte ptr cs:WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink+1, 4
0x1400a10d8  jz      short loc_1400A10E9
0x1400a10da  movsxd  r9, edi
0x1400a10dd  lea     rdx, VID_PARTITION_PERSIST_STOP
0x1400a10e4  call    McTemplateK0x_EtwWriteTransfer
0x1400a10e9  mov     rcx, r12
0x1400a10ec  call    VidObjectLockRelease
0x1400a10f1  mov     rcx, r15
0x1400a10f4  call    VidLockRelease
0x1400a10f9  test    edi, edi
0x1400a10fb  jns     short loc_1400A111E
0x1400a10fd  mov     r9d, edi
0x1400a1100  mov     [rsp+1D0h+var_1B0], r14
0x1400a1105  mov     r8d, 2DDh
0x1400a110b  lea     rdx, aOnecoreVmVidSy_9; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphu.c"
0x1400a1112  lea     rcx, aVsmmphuioctlco; "VsmmPhuIoctlCommit"
0x1400a1119  call    VidTraceErrorStatusPartitionInternal0
0x1400a111e  mov     eax, edi
0x1400a1120  mov     rcx, [rbp+0D0h+var_50]
0x1400a1127  xor     rcx, rsp; StackCookie
0x1400a112a  call    __security_check_cookie
0x1400a112f  add     rsp, 198h
0x1400a1136  pop     r15
0x1400a1138  pop     r14
0x1400a113a  pop     r13
0x1400a113c  pop     r12
0x1400a113e  pop     rdi
0x1400a113f  pop     rsi
0x1400a1140  pop     rbx
0x1400a1141  pop     rbp
0x1400a1142  retn
0x1400a1144  test    rax, rax
0x1400a1147  mov     dil, 1
0x1400a114a  setnz   r12b
0x1400a114e  lea     rdx, [rsp+1D0h+var_188]
0x1400a1153  mov     rcx, r13
0x1400a1156  call    VidHandleTableGetNext
0x1400a115b  mov     r11, rax
0x1400a115e  test    rax, rax
0x1400a1161  jnz     loc_1400A0F21
0x1400a1167  lea     rdi, [rbx+0CC0h]
0x1400a116e  mov     [rsp+1D0h+var_188], 0FFFFFFFFFFFFFFFFh
0x1400a1177  mov     rcx, rdi
0x1400a117a  lea     rdx, [rsp+1D0h+var_188]
0x1400a117f  call    VidHandleTableGetNext
0x1400a1184  xor     r13d, r13d
0x1400a1187  jmp     short loc_1400A11AF
0x1400a1189  cmp     [r11+128h], r13
0x1400a1190  jz      short loc_1400A11A2
0x1400a1192  mov     rcx, [r11+180h]
0x1400a1199  cmp     [rcx+2C8h], r13
0x1400a11a0  jz      short loc_1400A120A
0x1400a11a2  lea     rdx, [rsp+1D0h+var_188]
0x1400a11a7  mov     rcx, rdi
0x1400a11aa  call    VidHandleTableGetNext
0x1400a11af  mov     r11, rax
0x1400a11b2  test    rax, rax
0x1400a11b5  jnz     short loc_1400A1189
0x1400a11b7  mov     eax, [rbx+21D4h]
0x1400a11bd  cmp     eax, 1
0x1400a11c0  jnz     loc_1400A1332
0x1400a11c6  mov     r8d, 0C000A003h
0x1400a11cc  mov     edi, r8d
0x1400a11cf  mov     rax, [rbx+288h]
0x1400a11d6  lea     rcx, [rbx+78h]
0x1400a11da  mov     [rsp+1D0h+var_1A0], r8d
0x1400a11df  mov     r8d, 2A6h
0x1400a11e5  mov     [rsp+1D0h+var_1A8], rax
0x1400a11ea  mov     [rsp+1D0h+var_1B0], rcx
0x1400a11ef  mov     r9, r14
0x1400a11f2  lea     rdx, aOnecoreVmVidSy_9; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphu.c"
0x1400a11f9  lea     rcx, aVsmmphuioctlco; "VsmmPhuIoctlCommit"
0x1400a1200  call    VidTracePartitionErrorInternal0
0x1400a1205  jmp     loc_1400A10C7
0x1400a120a  mov     eax, cs:dword_140065110
0x1400a1210  mov     edi, 0C037003Eh
0x1400a1215  cmp     eax, esi
0x1400a1217  jbe     loc_1400A10C7
0x1400a121d  mov     edx, 100h
0x1400a1222  lea     rcx, dword_140065110
0x1400a1229  call    _tlgKeywordOn
0x1400a122e  test    al, al
0x1400a1230  jz      loc_1400A10C7
0x1400a1236  lea     rdx, aVsmmphuioctlco; "VsmmPhuIoctlCommit"
0x1400a123d  lea     rcx, [rbp+0D0h+var_120]
0x1400a1241  call    _tlgCreate1Sz_char
0x1400a1246  lea     rdx, aOnecoreVmVidSy_9; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphu.c"
0x1400a124d  lea     rcx, [rbp+0D0h+var_110]
0x1400a1251  call    _tlgCreate1Sz_char
0x1400a1256  lea     rax, [rsp+1D0h+var_188]
0x1400a125b  mov     dword ptr [rsp+1D0h+var_188], 299h
0x1400a1263  mov     [rbp+0D0h+var_100], rax
0x1400a1267  lea     rdx, unk_14004B602
0x1400a126e  lea     rax, [rsp+1D0h+var_18C]
0x1400a1273  mov     [rbp+0D0h+var_F8], 4
0x1400a127b  mov     [rbp+0D0h+var_F0], rax
0x1400a127f  lea     rax, [rbp+0D0h+var_B8]
0x1400a1283  mov     [rbp+0D0h+var_D0], rax
0x1400a1287  mov     rax, [rbx+80h]
0x1400a128e  mov     [rbp+0D0h+var_C0], rax
0x1400a1292  movzx   eax, word ptr [rbx+78h]
0x1400a1296  mov     [rbp+0D0h+var_B8], eax
0x1400a1299  mov     rax, [rbx+288h]
0x1400a12a0  mov     [rsp+1D0h+var_160], rax
0x1400a12a5  lea     rax, [rsp+1D0h+var_160]
0x1400a12aa  mov     [rbp+0D0h+var_B0], rax
0x1400a12ae  mov     rax, [r11+0F8h]
0x1400a12b5  mov     [rbp+0D0h+var_150], rax
0x1400a12b9  lea     rax, [rbp+0D0h+var_150]
0x1400a12bd  mov     [rbp+0D0h+var_A0], rax
0x1400a12c1  mov     rax, [r11+100h]
0x1400a12c8  mov     [rsp+1D0h+var_158], rax
  ... truncated ...
```
