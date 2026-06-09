# VsmmHwIsoDebugReadMbpRange

- ea: `0x1400e5074`
- end: `0x1400e5b8b`
- name: `VsmmHwIsoDebugReadMbpRange`
- size: `2839`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140029790`

## callees

- `0x1400029c0`
- `0x140006b68`
- `0x14000a010`
- `0x140021c60`
- `0x14002e270`
- `0x1400e5074`
- `0x1400f0ff0`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400e5563`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400e5563`
- `ntoskrnl!IoFreeMdl` at `0x1400e5b43`
- `ntoskrnl!IoFreeMdl` at `0x1400e5b43`
- `ntoskrnl!IoAllocateMdl` at `0x1400e53f5`
- `ntoskrnl!IoAllocateMdl` at `0x1400e53f5`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400e5532`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400e5532`
- `ntoskrnl!MmUnlockPages` at `0x1400e5b2f`
- `ntoskrnl!MmUnlockPages` at `0x1400e5b2f`
- `winhvr!WinHvReadGpa` at `0x1400e56ed`
- `winhvr!WinHvReadGpa` at `0x1400e56ed`

## string_xrefs

- `0x1400e5134`: `VsmmHwIsoDebugReadMbpRange`
- `0x1400e52a7`: `VsmmHwIsoDebugReadMbpRange`
- `0x1400e5446`: `VsmmHwIsoDebugReadMbpRange`
- `0x1400e55ac`: `VsmmHwIsoDebugReadMbpRange`
- `0x1400e5757`: `VsmmHwIsoDebugReadMbpRange`
- `0x1400e58c7`: `VsmmHwIsoDebugReadMbpRange`
- `0x1400e59d7`: `VsmmHwIsoDebugReadMbpRange`

## pseudocode

```c
__int64 __fastcall VsmmHwIsoDebugReadMbpRange(__int64 a1, int a2, unsigned __int64 a3, void *a4, ULONG Length)
{
  struct _MDL *v8; // rsi
  unsigned __int64 v9; // rcx
  int v10; // r14d
  __int64 v11; // rdx
  int v12; // ecx
  __int64 v13; // rax
  unsigned __int64 *v14; // rax
  void *v15; // rdx
  __int64 v16; // rdx
  int v17; // ecx
  __int64 v18; // rax
  __int64 v19; // r8
  struct _MDL *Mdl; // rax
  int v21; // r8d
  __int64 v22; // rdx
  int v23; // ecx
  __int64 v24; // rax
  char *MappedSystemVa; // r15
  int v26; // r8d
  __int64 v27; // rdx
  int v28; // ecx
  __int64 v29; // rax
  __int64 v30; // r12
  __int64 v31; // rbx
  unsigned __int64 v32; // r13
  __int64 v33; // rax
  __int64 v34; // rdx
  int v35; // ecx
  __int64 v36; // rax
  __int64 v37; // rdx
  int v38; // ecx
  __int64 v39; // rax
  int Irp; // [rsp+20h] [rbp-188h]
  char v42; // [rsp+40h] [rbp-168h]
  _QWORD v43[2]; // [rsp+48h] [rbp-160h] BYREF
  unsigned __int64 v44; // [rsp+58h] [rbp-150h] BYREF
  __int64 v45; // [rsp+60h] [rbp-148h] BYREF
  unsigned __int64 v46; // [rsp+68h] [rbp-140h] BYREF
  __int64 v47; // [rsp+70h] [rbp-138h] BYREF
  __int64 v48; // [rsp+78h] [rbp-130h] BYREF
  _QWORD v49[4]; // [rsp+80h] [rbp-128h] BYREF
  _BYTE v50[24]; // [rsp+A0h] [rbp-108h] BYREF
  _BYTE v51[16]; // [rsp+C0h] [rbp-E8h] BYREF
  _BYTE v52[16]; // [rsp+D0h] [rbp-D8h] BYREF
  unsigned __int64 *v53; // [rsp+E0h] [rbp-C8h]
  __int64 v54; // [rsp+E8h] [rbp-C0h]
  unsigned __int64 *v55; // [rsp+F0h] [rbp-B8h]
  __int64 v56; // [rsp+F8h] [rbp-B0h]
  __int64 v57; // [rsp+100h] [rbp-A8h]
  __int64 v58; // [rsp+108h] [rbp-A0h]
  int *v59; // [rsp+110h] [rbp-98h]
  __int64 v60; // [rsp+118h] [rbp-90h]
  __int64 v61; // [rsp+120h] [rbp-88h]
  int v62; // [rsp+128h] [rbp-80h] BYREF
  int v63; // [rsp+12Ch] [rbp-7Ch]
  unsigned __int64 *v64; // [rsp+130h] [rbp-78h]
  __int64 v65; // [rsp+138h] [rbp-70h]
  __int64 *v66; // [rsp+140h] [rbp-68h]
  __int64 v67; // [rsp+148h] [rbp-60h]
  unsigned __int64 *v68; // [rsp+150h] [rbp-58h]
  __int64 v69; // [rsp+158h] [rbp-50h]

  v44 = a3;
  v47 = a1;
  v49[1] = a1;
  v48 = 0;
  v46 = *(_QWORD *)(a1 + 8);
  v45 = 0;
  v42 = 0;
  v8 = 0;
  v49[0] = 0;
  v10 = VsmmGpaRangeLookupGpaByMbp(v46, a1, a2, 0, 0, (__int64)&v45, (__int64)v49);
  if ( v10 >= 0 )
  {
    v9 = *(_QWORD *)(v49[0] + 272LL) - v45 + 1;
    if ( a3 < v9 )
      v9 = a3;
    if ( v9 >= a3 )
    {
      Mdl = IoAllocateMdl(a4, Length, 0, 0, 0);
      v8 = Mdl;
      v49[2] = Mdl;
      if ( Mdl )
      {
        MmProbeAndLockPages(Mdl, 1, IoWriteAccess);
        if ( (v8->MdlFlags & 5) != 0 )
          MappedSystemVa = (char *)v8->MappedSystemVa;
        else
          MappedSystemVa = (char *)MmMapLockedPagesSpecifyCache(v8, 0, MmCached, 0, 0, 0x40000010u);
        if ( MappedSystemVa )
        {
          v42 = 1;
          v43[0] = 6;
          v30 = 0;
          if ( a3 )
          {
            v31 = v43[0];
LABEL_26:
            v32 = 0;
            v33 = (v30 + v45) << 12;
            v43[0] = v33;
            while ( 1 )
            {
              v10 = WinHvReadGpa(*(_QWORD *)(v46 + 648), 0xFFFFFFFFLL, v33 + v32, 16, v31, &v48, MappedSystemVa);
              if ( v10 < 0 )
                break;
              if ( (_DWORD)v48 )
              {
                if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
                {
                  tlgCreate1Sz_char(v51, "VsmmHwIsoDebugReadMbpRange");
                  tlgCreate1Sz_char(v52, "onecore\\vm\\vid\\sys\\vsmm\\vsmmhwisolation.c");
                  LODWORD(v43[0]) = 833;
                  v53 = v43;
                  v54 = 4;
                  LODWORD(v44) = v10;
                  v55 = &v44;
                  v56 = 4;
                  v34 = *(_QWORD *)(v47 + 8);
                  v57 = v34 + 656;
                  v58 = 16;
                  v35 = *(unsigned __int16 *)(v34 + 120);
                  v36 = *(_QWORD *)(v34 + 128);
                  v59 = &v62;
                  v60 = 2;
                  v61 = v36;
                  v62 = v35;
                  v63 = 0;
                  v46 = *(_QWORD *)(v34 + 648);
                  v64 = &v46;
                  v65 = 8;
                  LODWORD(v45) = v48;
                  v66 = &v45;
                  v67 = 4;
                  tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &unk_14005B2F4, 0, 0, 11, v50);
                }
                v10 = -1073741790;
                goto LABEL_39;
              }
              MappedSystemVa += 16;
              v32 += 16LL;
              v33 = v43[0];
              if ( v32 >= 0x1000 )
              {
                if ( ++v30 < v44 )
                  goto LABEL_26;
                goto LABEL_39;
              }
            }
            if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
            {
              tlgCreate1Sz_char(v51, "VsmmHwIsoDebugReadMbpRange");
              tlgCreate1Sz_char(v52, "onecore\\vm\\vid\\sys\\vsmm\\vsmmhwisolation.c");
              LODWORD(v45) = 824;
              v53 = (unsigned __int64 *)&v45;
              v54 = 4;
              LODWORD(v43[0]) = v10;
              v55 = v43;
              v56 = 4;
              v37 = *(_QWORD *)(v47 + 8);
              v57 = v37 + 656;
              v58 = 16;
              v38 = *(unsigned __int16 *)(v37 + 120);
              v39 = *(_QWORD *)(v37 + 128);
              v59 = &v62;
              v60 = 2;
              v61 = v39;
              v62 = v38;
              v63 = 0;
              v46 = *(_QWORD *)(v37 + 648);
              v14 = &v46;
              v15 = &unk_14005B286;
              goto LABEL_5;
            }
          }
        }
        else
        {
          v10 = -1073741670;
          if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
          {
            tlgCreate1Sz_char(v51, "VsmmHwIsoDebugReadMbpRange");
            tlgCreate1Sz_char(v52, "onecore\\vm\\vid\\sys\\vsmm\\vsmmhwisolation.c");
            LODWORD(v43[0]) = 796;
            v53 = v43;
            v54 = 4;
            LODWORD(v44) = v26;
            v55 = &v44;
            v56 = 4;
            v27 = *(_QWORD *)(a1 + 8);
            v57 = v27 + 656;
            v58 = 16;
            v28 = *(unsigned __int16 *)(v27 + 120);
            v29 = *(_QWORD *)(v27 + 128);
            v59 = &v62;
            v60 = 2;
            v61 = v29;
            v62 = v28;
            v63 = 0;
            v46 = *(_QWORD *)(v27 + 648);
            v14 = &v46;
            v15 = &unk_14005B457;
            goto LABEL_5;
          }
        }
      }
      else
      {
        v10 = -1073741670;
        v9 = (unsigned int)dword_140065110;
        if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
        {
          tlgCreate1Sz_char(v51, "VsmmHwIsoDebugReadMbpRange");
          tlgCreate1Sz_char(v52, "onecore\\vm\\vid\\sys\\vsmm\\vsmmhwisolation.c");
          LODWORD(v43[0]) = 774;
          v53 = v43;
          v54 = 4;
          LODWORD(v44) = v21;
          v55 = &v44;
          v56 = 4;
          v22 = *(_QWORD *)(a1 + 8);
          v57 = v22 + 656;
          v58 = 16;
          v23 = *(unsigned __int16 *)(v22 + 120);
          v24 = *(_QWORD *)(v22 + 128);
          v59 = &v62;
          v60 = 2;
          v61 = v24;
          v62 = v23;
          v63 = 0;
          v46 = *(_QWORD *)(v22 + 648);
          v14 = &v46;
          v15 = &unk_14005B37B;
          goto LABEL_5;
        }
      }
    }
    else
    {
      v10 = -1073741811;
      if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
      {
        tlgCreate1Sz_char(v51, "VsmmHwIsoDebugReadMbpRange");
        tlgCreate1Sz_char(v52, "onecore\\vm\\vid\\sys\\vsmm\\vsmmhwisolation.c");
        LODWORD(v43[0]) = 759;
        v53 = v43;
        v54 = 4;
        LODWORD(v44) = -1073741811;
        v55 = &v44;
        v56 = 4;
        v16 = *(_QWORD *)(a1 + 8);
        v57 = v16 + 656;
        v58 = 16;
        v17 = *(unsigned __int16 *)(v16 + 120);
        v18 = *(_QWORD *)(v16 + 128);
        v59 = &v62;
        v60 = 2;
        v61 = v18;
        v62 = v17;
        v63 = 0;
        v47 = *(_QWORD *)(v16 + 648);
        v64 = (unsigned __int64 *)&v47;
        v45 = v19;
        v66 = &v45;
        v67 = 8;
        v46 = a3;
        v68 = &v46;
        v69 = 8;
        Irp = 12;
        v15 = &unk_14005B533;
        goto LABEL_6;
      }
    }
  }
  else if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
  {
    tlgCreate1Sz_char(v51, "VsmmHwIsoDebugReadMbpRange");
    tlgCreate1Sz_char(v52, "onecore\\vm\\vid\\sys\\vsmm\\vsmmhwisolation.c");
    LODWORD(v44) = 743;
    v53 = &v44;
    v54 = 4;
    LODWORD(v43[0]) = v10;
    v55 = v43;
    v56 = 4;
    v11 = *(_QWORD *)(a1 + 8);
    v57 = v11 + 656;
    v58 = 16;
    v12 = *(unsigned __int16 *)(v11 + 120);
    v13 = *(_QWORD *)(v11 + 128);
    v59 = &v62;
    v60 = 2;
    v61 = v13;
    v62 = v12;
    v63 = 0;
    v47 = *(_QWORD *)(v11 + 648);
    v14 = (unsigned __int64 *)&v47;
    v15 = &unk_14005B4C5;
LABEL_5:
    v64 = v14;
    Irp = 10;
LABEL_6:
    v65 = 8;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, v15, 0, 0, Irp, v50);
  }
LABEL_39:
  if ( v42 )
    MmUnlockPages(v8);
  if ( v8 )
    IoFreeMdl(v8);
  if ( v49[0] )
    VsmmGpaRangeRelease(v9, v49[0], 0);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1400e5074  push    rbx
0x1400e5076  push    rsi
0x1400e5077  push    rdi
0x1400e5078  push    r12
0x1400e507a  push    r13
0x1400e507c  push    r14
0x1400e507e  push    r15
0x1400e5080  sub     rsp, 170h
0x1400e5087  mov     rax, cs:__security_cookie
0x1400e508e  xor     rax, rsp
0x1400e5091  mov     [rsp+1A8h+var_48], rax
0x1400e5099  mov     r15, r9
0x1400e509c  mov     rbx, r8
0x1400e509f  mov     [rsp+1A8h+var_150], rbx
0x1400e50a4  mov     r13, rcx
0x1400e50a7  mov     [rsp+1A8h+var_138], rcx
0x1400e50ac  mov     [rsp+1A8h+var_120], rcx
0x1400e50b4  xor     edi, edi
0x1400e50b6  mov     [rsp+1A8h+var_130], rdi
0x1400e50bb  mov     rcx, [rcx+8]
0x1400e50bf  mov     [rsp+1A8h+var_140], rcx
0x1400e50c4  mov     [rsp+1A8h+var_148], rdi
0x1400e50c9  mov     [rsp+1A8h+var_168], dil
0x1400e50ce  mov     esi, edi
0x1400e50d0  mov     [rsp+1A8h+var_128], rdi
0x1400e50d8  lea     rax, [rsp+1A8h+var_128]
0x1400e50e0  mov     [rsp+1A8h+var_178], rax
0x1400e50e5  lea     rax, [rsp+1A8h+var_148]
0x1400e50ea  mov     qword ptr [rsp+1A8h+Priority], rax
0x1400e50ef  mov     dword ptr [rsp+1A8h+Irp], edi
0x1400e50f3  xor     r9d, r9d
0x1400e50f6  mov     r8, rdx
0x1400e50f9  mov     rdx, r13
0x1400e50fc  call    VsmmGpaRangeLookupGpaByMbp
0x1400e5101  mov     r14d, eax
0x1400e5104  test    eax, eax
0x1400e5106  jns     loc_1400E524F
0x1400e510c  mov     eax, cs:dword_140065110
0x1400e5112  cmp     eax, 2
0x1400e5115  jbe     loc_1400E5B25
0x1400e511b  mov     edx, 100h
0x1400e5120  lea     rcx, dword_140065110
0x1400e5127  call    _tlgKeywordOn
0x1400e512c  test    al, al
0x1400e512e  jz      loc_1400E5B25
0x1400e5134  lea     rdx, aVsmmhwisodebug; "VsmmHwIsoDebugReadMbpRange"
0x1400e513b  lea     rcx, [rsp+1A8h+var_E8]
0x1400e5143  call    _tlgCreate1Sz_char
0x1400e5148  lea     rdx, aOnecoreVmVidSy_24; "onecore\\vm\\vid\\sys\\vsmm\\vsmmhwisol"...
0x1400e514f  lea     rcx, [rsp+1A8h+var_D8]
0x1400e5157  call    _tlgCreate1Sz_char
0x1400e515c  mov     dword ptr [rsp+1A8h+var_150], 2E7h
0x1400e5164  lea     rax, [rsp+1A8h+var_150]
0x1400e5169  mov     [rsp+1A8h+var_C8], rax
0x1400e5171  mov     [rsp+1A8h+var_C0], 4
0x1400e517d  mov     dword ptr [rsp+1A8h+var_160], r14d
0x1400e5182  lea     rax, [rsp+1A8h+var_160]
0x1400e5187  mov     [rsp+1A8h+var_B8], rax
0x1400e518f  mov     [rsp+1A8h+var_B0], 4
0x1400e519b  mov     rdx, [r13+8]
0x1400e519f  lea     rax, [rdx+290h]
0x1400e51a6  mov     [rsp+1A8h+var_A8], rax
0x1400e51ae  mov     [rsp+1A8h+var_A0], 10h
0x1400e51ba  movzx   ecx, word ptr [rdx+78h]
0x1400e51be  mov     rax, [rdx+80h]
0x1400e51c5  lea     r8, [rsp+1A8h+var_80]
0x1400e51cd  mov     [rsp+1A8h+var_98], r8
0x1400e51d5  mov     [rsp+1A8h+var_90], 2
0x1400e51e1  mov     [rsp+1A8h+var_88], rax
0x1400e51e9  mov     [rsp+1A8h+var_80], ecx
0x1400e51f0  mov     [rsp+1A8h+var_7C], edi
0x1400e51f7  mov     rax, [rdx+288h]
0x1400e51fe  mov     [rsp+1A8h+var_138], rax
0x1400e5203  lea     rax, [rsp+1A8h+var_138]
0x1400e5208  lea     rdx, unk_14005B4C5
0x1400e520f  mov     [rsp+1A8h+var_78], rax
0x1400e5217  lea     rax, [rsp+1A8h+var_108]
0x1400e521f  mov     qword ptr [rsp+1A8h+Priority], rax
0x1400e5224  mov     dword ptr [rsp+1A8h+Irp], 0Ah
0x1400e522c  xor     r9d, r9d
0x1400e522f  mov     [rsp+1A8h+var_70], 8
0x1400e523b  xor     r8d, r8d
0x1400e523e  lea     rcx, dword_140065110
0x1400e5245  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400e524a  jmp     loc_1400E5B25
0x1400e524f  mov     rax, [rsp+1A8h+var_128]
0x1400e5257  mov     rcx, [rax+110h]
0x1400e525e  mov     r8, [rsp+1A8h+var_148]
0x1400e5263  sub     rcx, r8
0x1400e5266  inc     rcx
0x1400e5269  cmp     rbx, rcx
0x1400e526c  cmovb   rcx, rbx
0x1400e5270  cmp     rcx, rbx
0x1400e5273  jnb     loc_1400E53E0
0x1400e5279  mov     r14d, 0C000000Dh
0x1400e527f  mov     eax, cs:dword_140065110
0x1400e5285  cmp     eax, 2
0x1400e5288  jbe     loc_1400E5B25
0x1400e528e  mov     edx, 100h
0x1400e5293  lea     rcx, dword_140065110
0x1400e529a  call    _tlgKeywordOn
0x1400e529f  test    al, al
0x1400e52a1  jz      loc_1400E5B25
0x1400e52a7  lea     rdx, aVsmmhwisodebug; "VsmmHwIsoDebugReadMbpRange"
0x1400e52ae  lea     rcx, [rsp+1A8h+var_E8]
0x1400e52b6  call    _tlgCreate1Sz_char
0x1400e52bb  lea     rdx, aOnecoreVmVidSy_24; "onecore\\vm\\vid\\sys\\vsmm\\vsmmhwisol"...
0x1400e52c2  lea     rcx, [rsp+1A8h+var_D8]
0x1400e52ca  call    _tlgCreate1Sz_char
0x1400e52cf  mov     dword ptr [rsp+1A8h+var_160], 2F7h
0x1400e52d7  lea     rax, [rsp+1A8h+var_160]
0x1400e52dc  mov     [rsp+1A8h+var_C8], rax
0x1400e52e4  mov     [rsp+1A8h+var_C0], 4
0x1400e52f0  mov     dword ptr [rsp+1A8h+var_150], r14d
0x1400e52f5  lea     rax, [rsp+1A8h+var_150]
0x1400e52fa  mov     [rsp+1A8h+var_B8], rax
0x1400e5302  mov     [rsp+1A8h+var_B0], 4
0x1400e530e  mov     rdx, [r13+8]
0x1400e5312  lea     rax, [rdx+290h]
0x1400e5319  mov     [rsp+1A8h+var_A8], rax
0x1400e5321  mov     [rsp+1A8h+var_A0], 10h
0x1400e532d  movzx   ecx, word ptr [rdx+78h]
0x1400e5331  mov     rax, [rdx+80h]
0x1400e5338  lea     r9, [rsp+1A8h+var_80]
0x1400e5340  mov     [rsp+1A8h+var_98], r9
0x1400e5348  mov     [rsp+1A8h+var_90], 2
0x1400e5354  mov     [rsp+1A8h+var_88], rax
0x1400e535c  mov     [rsp+1A8h+var_80], ecx
0x1400e5363  mov     [rsp+1A8h+var_7C], edi
0x1400e536a  mov     rax, [rdx+288h]
0x1400e5371  mov     [rsp+1A8h+var_138], rax
0x1400e5376  lea     rax, [rsp+1A8h+var_138]
0x1400e537b  mov     [rsp+1A8h+var_78], rax
0x1400e5383  mov     [rsp+1A8h+var_148], r8
0x1400e5388  lea     rax, [rsp+1A8h+var_148]
0x1400e538d  mov     [rsp+1A8h+var_68], rax
0x1400e5395  mov     [rsp+1A8h+var_60], 8
0x1400e53a1  mov     [rsp+1A8h+var_140], rbx
0x1400e53a6  lea     rax, [rsp+1A8h+var_140]
0x1400e53ab  mov     [rsp+1A8h+var_58], rax
0x1400e53b3  mov     [rsp+1A8h+var_50], 8
0x1400e53bf  lea     rax, [rsp+1A8h+var_108]
0x1400e53c7  mov     qword ptr [rsp+1A8h+Priority], rax
0x1400e53cc  mov     dword ptr [rsp+1A8h+Irp], 0Ch
0x1400e53d4  lea     rdx, unk_14005B533
0x1400e53db  jmp     loc_1400E522C
0x1400e53e0  mov     edx, [rsp+1A8h+Length]; Length
0x1400e53e7  mov     [rsp+1A8h+Irp], rdi; Irp
0x1400e53ec  xor     r9d, r9d; ChargeQuota
0x1400e53ef  xor     r8d, r8d; SecondaryBuffer
0x1400e53f2  mov     rcx, r15; VirtualAddress
0x1400e53f5  call    cs:__imp_IoAllocateMdl
0x1400e53fc  nop     dword ptr [rax+rax+00h]
0x1400e5401  mov     rsi, rax
0x1400e5404  mov     [rsp+1A8h+var_118], rax
0x1400e540c  test    rax, rax
0x1400e540f  jnz     loc_1400E5526
0x1400e5415  mov     r8d, 0C000009Ah
0x1400e541b  mov     r14d, r8d
0x1400e541e  mov     ecx, cs:dword_140065110
0x1400e5424  cmp     ecx, 2
0x1400e5427  jbe     loc_1400E5B25
0x1400e542d  mov     edx, 100h
0x1400e5432  lea     rcx, dword_140065110
0x1400e5439  call    _tlgKeywordOn
0x1400e543e  test    al, al
0x1400e5440  jz      loc_1400E5B25
0x1400e5446  lea     rdx, aVsmmhwisodebug; "VsmmHwIsoDebugReadMbpRange"
0x1400e544d  lea     rcx, [rsp+1A8h+var_E8]
0x1400e5455  call    _tlgCreate1Sz_char
0x1400e545a  lea     rdx, aOnecoreVmVidSy_24; "onecore\\vm\\vid\\sys\\vsmm\\vsmmhwisol"...
0x1400e5461  lea     rcx, [rsp+1A8h+var_D8]
0x1400e5469  call    _tlgCreate1Sz_char
0x1400e546e  mov     dword ptr [rsp+1A8h+var_160], 306h
0x1400e5476  lea     rax, [rsp+1A8h+var_160]
0x1400e547b  mov     [rsp+1A8h+var_C8], rax
0x1400e5483  mov     [rsp+1A8h+var_C0], 4
0x1400e548f  mov     dword ptr [rsp+1A8h+var_150], r8d
0x1400e5494  lea     rax, [rsp+1A8h+var_150]
0x1400e5499  mov     [rsp+1A8h+var_B8], rax
0x1400e54a1  mov     [rsp+1A8h+var_B0], 4
0x1400e54ad  mov     rdx, [r13+8]
0x1400e54b1  lea     rax, [rdx+290h]
0x1400e54b8  mov     [rsp+1A8h+var_A8], rax
0x1400e54c0  mov     [rsp+1A8h+var_A0], 10h
0x1400e54cc  movzx   ecx, word ptr [rdx+78h]
0x1400e54d0  mov     rax, [rdx+80h]
0x1400e54d7  lea     r8, [rsp+1A8h+var_80]
0x1400e54df  mov     [rsp+1A8h+var_98], r8
0x1400e54e7  mov     [rsp+1A8h+var_90], 2
0x1400e54f3  mov     [rsp+1A8h+var_88], rax
0x1400e54fb  mov     [rsp+1A8h+var_80], ecx
0x1400e5502  mov     [rsp+1A8h+var_7C], edi
0x1400e5509  mov     rax, [rdx+288h]
0x1400e5510  mov     [rsp+1A8h+var_140], rax
0x1400e5515  lea     rax, [rsp+1A8h+var_140]
0x1400e551a  lea     rdx, unk_14005B37B
0x1400e5521  jmp     loc_1400E520F
0x1400e5526  mov     r8d, 1; Operation
0x1400e552c  mov     dl, r8b; AccessMode
0x1400e552f  mov     rcx, rsi; MemoryDescriptorList
0x1400e5532  call    cs:__imp_MmProbeAndLockPages
0x1400e5539  nop     dword ptr [rax+rax+00h]
0x1400e553e  nop
0x1400e553f  test    byte ptr [rsi+0Ah], 5
0x1400e5543  jz      short loc_1400E554B
0x1400e5545  mov     r15, [rsi+18h]
0x1400e5549  jmp     short loc_1400E5572
0x1400e554b  mov     [rsp+1A8h+Priority], 40000010h; Priority
0x1400e5553  mov     dword ptr [rsp+1A8h+Irp], edi; BugCheckOnFailure
0x1400e5557  xor     r9d, r9d; RequestedAddress
0x1400e555a  xor     edx, edx; AccessMode
0x1400e555c  lea     r8d, [r9+1]; CacheType
0x1400e5560  mov     rcx, rsi; MemoryDescriptorList
0x1400e5563  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400e556a  nop     dword ptr [rax+rax+00h]
0x1400e556f  mov     r15, rax
0x1400e5572  test    r15, r15
0x1400e5575  jnz     loc_1400E568C
0x1400e557b  mov     r8d, 0C000009Ah
0x1400e5581  mov     r14d, r8d
0x1400e5584  mov     eax, cs:dword_140065110
0x1400e558a  cmp     eax, 2
0x1400e558d  jbe     loc_1400E5B25
0x1400e5593  mov     edx, 100h
0x1400e5598  lea     rcx, dword_140065110
0x1400e559f  call    _tlgKeywordOn
0x1400e55a4  test    al, al
0x1400e55a6  jz      loc_1400E5B25
0x1400e55ac  lea     rdx, aVsmmhwisodebug; "VsmmHwIsoDebugReadMbpRange"
0x1400e55b3  lea     rcx, [rsp+1A8h+var_E8]
0x1400e55bb  call    _tlgCreate1Sz_char
0x1400e55c0  lea     rdx, aOnecoreVmVidSy_24; "onecore\\vm\\vid\\sys\\vsmm\\vsmmhwisol"...
0x1400e55c7  lea     rcx, [rsp+1A8h+var_D8]
0x1400e55cf  call    _tlgCreate1Sz_char
0x1400e55d4  mov     dword ptr [rsp+1A8h+var_160], 31Ch
0x1400e55dc  lea     rax, [rsp+1A8h+var_160]
0x1400e55e1  mov     [rsp+1A8h+var_C8], rax
0x1400e55e9  mov     [rsp+1A8h+var_C0], 4
0x1400e55f5  mov     dword ptr [rsp+1A8h+var_150], r8d
0x1400e55fa  lea     rax, [rsp+1A8h+var_150]
0x1400e55ff  mov     [rsp+1A8h+var_B8], rax
0x1400e5607  mov     [rsp+1A8h+var_B0], 4
0x1400e5613  mov     rdx, [r13+8]
0x1400e5617  lea     rax, [rdx+290h]
0x1400e561e  mov     [rsp+1A8h+var_A8], rax
0x1400e5626  mov     [rsp+1A8h+var_A0], 10h
0x1400e5632  movzx   ecx, word ptr [rdx+78h]
0x1400e5636  mov     rax, [rdx+80h]
0x1400e563d  lea     r8, [rsp+1A8h+var_80]
0x1400e5645  mov     [rsp+1A8h+var_98], r8
0x1400e564d  mov     [rsp+1A8h+var_90], 2
0x1400e5659  mov     [rsp+1A8h+var_88], rax
0x1400e5661  mov     [rsp+1A8h+var_80], ecx
0x1400e5668  mov     [rsp+1A8h+var_7C], edi
0x1400e566f  mov     rax, [rdx+288h]
0x1400e5676  mov     [rsp+1A8h+var_140], rax
0x1400e567b  lea     rax, [rsp+1A8h+var_140]
0x1400e5680  lea     rdx, unk_14005B457
0x1400e5687  jmp     loc_1400E520F
0x1400e568c  mov     [rsp+1A8h+var_168], 1
0x1400e5691  mov     [rsp+1A8h+var_160], rdi
0x1400e5696  mov     byte ptr [rsp+1A8h+var_160], 6
0x1400e569b  mov     r12, rdi
0x1400e569e  test    rbx, rbx
0x1400e56a1  jz      loc_1400E5B25
0x1400e56a7  mov     rbx, [rsp+1A8h+var_160]
0x1400e56ac  mov     r13, rdi
0x1400e56af  mov     rax, [rsp+1A8h+var_148]
0x1400e56b4  add     rax, r12
0x1400e56b7  shl     rax, 0Ch
0x1400e56bb  mov     [rsp+1A8h+var_160], rax
0x1400e56c0  lea     r8, [rax+r13]
0x1400e56c4  mov     [rsp+1A8h+var_178], r15
0x1400e56c9  lea     rax, [rsp+1A8h+var_130]
0x1400e56ce  mov     qword ptr [rsp+1A8h+Priority], rax
0x1400e56d3  mov     [rsp+1A8h+Irp], rbx
0x1400e56d8  mov     r9d, 10h
0x1400e56de  or      edx, 0FFFFFFFFh
0x1400e56e1  mov     rax, [rsp+1A8h+var_140]
0x1400e56e6  mov     rcx, [rax+288h]
0x1400e56ed  call    cs:__imp_WinHvReadGpa
0x1400e56f4  nop     dword ptr [rax+rax+00h]
0x1400e56f9  mov     r14d, eax
0x1400e56fc  test    eax, eax
0x1400e56fe  js      loc_1400E589F
0x1400e5704  cmp     dword ptr [rsp+1A8h+var_130], edi
0x1400e5708  jnz     short loc_1400E572F
0x1400e570a  add     r15, 10h
0x1400e570e  add     r13, 10h
0x1400e5712  cmp     r13, 1000h
0x1400e5719  mov     rax, [rsp+1A8h+var_160]
0x1400e571e  jb      short loc_1400E56C0
0x1400e5720  inc     r12
0x1400e5723  cmp     r12, [rsp+1A8h+var_150]
0x1400e5728  jb      short loc_1400E56AC
0x1400e572a  jmp     loc_1400E5B25
0x1400e572f  mov     eax, cs:dword_140065110
0x1400e5735  cmp     eax, 2
0x1400e5738  jbe     loc_1400E5894
  ... truncated ...
```
