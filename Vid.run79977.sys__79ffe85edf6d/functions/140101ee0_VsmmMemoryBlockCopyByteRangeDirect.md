# VsmmMemoryBlockCopyByteRangeDirect

- ea: `0x140101ee0`
- end: `0x14010272c`
- name: `VsmmMemoryBlockCopyByteRangeDirect`
- size: `2124`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x14001c040`

## callees

- `0x1400029c0`
- `0x140006820`
- `0x140006b68`
- `0x14000a010`
- `0x14000fb80`
- `0x140021c60`
- `0x140023008`
- `0x1400bbebc`
- `0x140101ee0`

## import_xrefs

- `ntoskrnl!KeInvalidateRangeAllCaches` at `0x14010253d`
- `ntoskrnl!KeInvalidateRangeAllCaches` at `0x14010253d`

## string_xrefs

- `0x140101f6b`: `VsmmMemoryBlockCopyByteRangeDirect`
- `0x1401020e2`: `VsmmMemoryBlockCopyByteRangeDirect`
- `0x140102246`: `VsmmMemoryBlockCopyByteRangeDirect`
- `0x1401023a6`: `VsmmMemoryBlockCopyByteRangeDirect`
- `0x1401025bb`: `VsmmMemoryBlockCopyByteRangeDirect`

## pseudocode

```c
__int64 __fastcall VsmmMemoryBlockCopyByteRangeDirect(__int64 *a1, __int64 a2, __int64 a3, __int64 a4)
{
  char *v5; // rsi
  __int64 v6; // rcx
  int v7; // edi
  __int64 result; // rax
  __int64 v9; // r8
  __int64 v10; // rax
  int v11; // edx
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r8
  __int64 v15; // rax
  int v16; // edx
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // rax
  int v20; // edx
  __int64 v21; // rcx
  __int64 v22; // r8
  __int64 v23; // rax
  int v24; // edx
  __int64 v25; // rcx
  __int64 v26; // rdx
  char *v27; // r8
  char *v28; // rcx
  unsigned __int64 i; // rdi
  ULONG v30; // r15d
  int v31; // [rsp+34h] [rbp-304h] BYREF
  int v32; // [rsp+38h] [rbp-300h] BYREF
  int v33; // [rsp+3Ch] [rbp-2FCh] BYREF
  int v34; // [rsp+40h] [rbp-2F8h] BYREF
  int v35; // [rsp+44h] [rbp-2F4h] BYREF
  int v36; // [rsp+48h] [rbp-2F0h] BYREF
  int v37; // [rsp+4Ch] [rbp-2ECh] BYREF
  int v38; // [rsp+50h] [rbp-2E8h] BYREF
  _QWORD v39[2]; // [rsp+58h] [rbp-2E0h] BYREF
  __int64 v40; // [rsp+68h] [rbp-2D0h] BYREF
  __int64 v41; // [rsp+70h] [rbp-2C8h] BYREF
  __int64 v42; // [rsp+78h] [rbp-2C0h] BYREF
  char v43[24]; // [rsp+80h] [rbp-2B8h] BYREF
  char v44[16]; // [rsp+A0h] [rbp-298h] BYREF
  char v45[16]; // [rsp+B0h] [rbp-288h] BYREF
  int *v46; // [rsp+C0h] [rbp-278h]
  __int64 v47; // [rsp+C8h] [rbp-270h]
  int *v48; // [rsp+D0h] [rbp-268h]
  __int64 v49; // [rsp+D8h] [rbp-260h]
  __int64 v50; // [rsp+E0h] [rbp-258h]
  __int64 v51; // [rsp+E8h] [rbp-250h]
  _DWORD *v52; // [rsp+F0h] [rbp-248h]
  __int64 v53; // [rsp+F8h] [rbp-240h]
  __int64 v54; // [rsp+100h] [rbp-238h]
  _DWORD v55[2]; // [rsp+108h] [rbp-230h] BYREF
  _QWORD *v56; // [rsp+110h] [rbp-228h]
  __int64 v57; // [rsp+118h] [rbp-220h]
  char v58[32]; // [rsp+120h] [rbp-218h] BYREF
  char v59[16]; // [rsp+140h] [rbp-1F8h] BYREF
  char v60[16]; // [rsp+150h] [rbp-1E8h] BYREF
  int *v61; // [rsp+160h] [rbp-1D8h]
  __int64 v62; // [rsp+168h] [rbp-1D0h]
  int *v63; // [rsp+170h] [rbp-1C8h]
  __int64 v64; // [rsp+178h] [rbp-1C0h]
  __int64 v65; // [rsp+180h] [rbp-1B8h]
  __int64 v66; // [rsp+188h] [rbp-1B0h]
  _DWORD *v67; // [rsp+190h] [rbp-1A8h]
  __int64 v68; // [rsp+198h] [rbp-1A0h]
  __int64 v69; // [rsp+1A0h] [rbp-198h]
  _DWORD v70[2]; // [rsp+1A8h] [rbp-190h] BYREF
  __int64 *v71; // [rsp+1B0h] [rbp-188h]
  __int64 v72; // [rsp+1B8h] [rbp-180h]
  char v73[32]; // [rsp+1C0h] [rbp-178h] BYREF
  char v74[16]; // [rsp+1E0h] [rbp-158h] BYREF
  char v75[16]; // [rsp+1F0h] [rbp-148h] BYREF
  int *v76; // [rsp+200h] [rbp-138h]
  __int64 v77; // [rsp+208h] [rbp-130h]
  int *v78; // [rsp+210h] [rbp-128h]
  __int64 v79; // [rsp+218h] [rbp-120h]
  __int64 v80; // [rsp+220h] [rbp-118h]
  __int64 v81; // [rsp+228h] [rbp-110h]
  _DWORD *v82; // [rsp+230h] [rbp-108h]
  __int64 v83; // [rsp+238h] [rbp-100h]
  __int64 v84; // [rsp+240h] [rbp-F8h]
  _DWORD v85[2]; // [rsp+248h] [rbp-F0h] BYREF
  __int64 *v86; // [rsp+250h] [rbp-E8h]
  __int64 v87; // [rsp+258h] [rbp-E0h]
  char v88[32]; // [rsp+260h] [rbp-D8h] BYREF
  char v89[16]; // [rsp+280h] [rbp-B8h] BYREF
  char v90[16]; // [rsp+290h] [rbp-A8h] BYREF
  int *v91; // [rsp+2A0h] [rbp-98h]
  __int64 v92; // [rsp+2A8h] [rbp-90h]
  int *v93; // [rsp+2B0h] [rbp-88h]
  __int64 v94; // [rsp+2B8h] [rbp-80h]
  __int64 v95; // [rsp+2C0h] [rbp-78h]
  __int64 v96; // [rsp+2C8h] [rbp-70h]
  _DWORD *v97; // [rsp+2D0h] [rbp-68h]
  __int64 v98; // [rsp+2D8h] [rbp-60h]
  __int64 v99; // [rsp+2E0h] [rbp-58h]
  _DWORD v100[2]; // [rsp+2E8h] [rbp-50h] BYREF
  __int64 *v101; // [rsp+2F0h] [rbp-48h]
  __int64 v102; // [rsp+2F8h] [rbp-40h]

  v39[1] = a1;
  v31 = 0;
  v5 = (char *)(a1[3] + a2);
  v6 = a1[2];
  if ( !v6 )
  {
    v26 = a1[4];
    if ( (*((_DWORD *)a1 + 11) & 1) != 0 )
    {
      LOBYTE(a4) = *((_BYTE *)a1 + 41);
      v27 = (char *)a1[1];
      LOBYTE(v26) = (*(_DWORD *)(*a1 + 264) & 8) != 0;
      v28 = v5;
    }
    else
    {
      LOBYTE(a4) = (*(_DWORD *)(*a1 + 264) & 8) != 0;
      v27 = v5;
      LOBYTE(v26) = *((_BYTE *)a1 + 41);
      v28 = (char *)a1[1];
    }
    VsmmpCopyFromModeToMode(v28, v26, v27, a4, a1[4]);
    goto LABEL_27;
  }
  if ( (unsigned __int64)a1[4] > 0xFFFFFFFF )
  {
    v7 = -1073741637;
    result = (unsigned int)dword_140065110;
    if ( (unsigned int)dword_140065110 > 2 )
    {
      result = tlgKeywordOn(&dword_140065110, 256);
      if ( (_BYTE)result )
      {
        tlgCreate1Sz_char(v59, "VsmmMemoryBlockCopyByteRangeDirect");
        tlgCreate1Sz_char(v60, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemoryblock.c");
        v31 = 6720;
        v61 = &v31;
        v62 = 4;
        v34 = -1073741637;
        v63 = &v34;
        v64 = 4;
        v9 = *a1;
        v65 = *(_QWORD *)(*a1 + 8) + 656LL;
        v66 = 16;
        v10 = *(_QWORD *)(v9 + 8);
        v11 = *(unsigned __int16 *)(v10 + 120);
        v12 = *(_QWORD *)(v10 + 128);
        v67 = v70;
        v68 = 2;
        v69 = v12;
        v70[0] = v11;
        v70[1] = 0;
        v40 = *(_QWORD *)(*(_QWORD *)(v9 + 8) + 648LL);
        v71 = &v40;
        v72 = 8;
        result = tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &unk_140059A19, 0, 0, 10, v58);
      }
    }
    goto LABEL_37;
  }
  v13 = *((unsigned int *)a1 + 8);
  if ( (*((_DWORD *)a1 + 11) & 1) != 0 )
  {
    result = VmCompressUnpackEx(v6, v5, v13, &v31);
    v7 = result;
    if ( (int)result < 0 )
    {
      if ( (unsigned int)dword_140065110 > 2 )
      {
        result = tlgKeywordOn(&dword_140065110, 256);
        if ( (_BYTE)result )
        {
          tlgCreate1Sz_char(v74, "VsmmMemoryBlockCopyByteRangeDirect");
          tlgCreate1Sz_char(v75, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemoryblock.c");
          v35 = 6741;
          v76 = &v35;
          v77 = 4;
          v36 = v7;
          v78 = &v36;
          v79 = 4;
          v14 = *a1;
          v80 = *(_QWORD *)(*a1 + 8) + 656LL;
          v81 = 16;
          v15 = *(_QWORD *)(v14 + 8);
          v16 = *(unsigned __int16 *)(v15 + 120);
          v17 = *(_QWORD *)(v15 + 128);
          v82 = v85;
          v83 = 2;
          v84 = v17;
          v85[0] = v16;
          v85[1] = 0;
          v41 = *(_QWORD *)(*(_QWORD *)(v14 + 8) + 648LL);
          v86 = &v41;
          v87 = 8;
          result = tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &unk_140059A87, 0, 0, 10, v73);
        }
      }
      goto LABEL_37;
    }
    if ( v31 != a1[4] )
    {
      v7 = -1073741811;
      result = (unsigned int)dword_140065110;
      if ( (unsigned int)dword_140065110 > 2 )
      {
        result = tlgKeywordOn(&dword_140065110, 256);
        if ( (_BYTE)result )
        {
          tlgCreate1Sz_char(v89, "VsmmMemoryBlockCopyByteRangeDirect");
          tlgCreate1Sz_char(v90, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemoryblock.c");
          v37 = 6756;
          v91 = &v37;
          v92 = 4;
          v38 = -1073741811;
          v93 = &v38;
          v94 = 4;
          v18 = *a1;
          v95 = *(_QWORD *)(*a1 + 8) + 656LL;
          v96 = 16;
          v19 = *(_QWORD *)(v18 + 8);
          v20 = *(unsigned __int16 *)(v19 + 120);
          v21 = *(_QWORD *)(v19 + 128);
          v97 = v100;
          v98 = 2;
          v99 = v21;
          v100[0] = v20;
          v100[1] = 0;
          v42 = *(_QWORD *)(*(_QWORD *)(v18 + 8) + 648LL);
          v101 = &v42;
          v102 = 8;
          result = tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &unk_140059AF5, 0, 0, 10, v88);
        }
      }
      goto LABEL_37;
    }
LABEL_27:
    result = *((unsigned int *)a1 + 11);
    if ( (result & 1) != 0 )
    {
      if ( *((_BYTE *)a1 + 40) )
      {
        for ( i = a1[4]; i; i -= v30 )
        {
          v30 = i;
          if ( i >= 0xFFFFFFFF )
            v30 = -1;
          KeInvalidateRangeAllCaches(v5, v30);
          result = v30;
          v5 += v30;
        }
      }
      else if ( (*(_DWORD *)(*a1 + 264) & 0x2000) != 0 )
      {
        result = VsmmDaxFileFlushVaRange(*(_QWORD *)(*a1 + 840), v5, a1[4], 0);
        v7 = result;
        if ( (int)result < 0 )
          goto LABEL_37;
      }
    }
    v7 = 0;
    goto LABEL_37;
  }
  v7 = VmCompressPackEx(v6, v5, v13);
  if ( v7 >= 0 )
    goto LABEL_27;
  result = (unsigned int)dword_140065110;
  if ( (unsigned int)dword_140065110 > 2 )
  {
    result = tlgKeywordOn(&dword_140065110, 256);
    if ( (_BYTE)result )
    {
      tlgCreate1Sz_char(v44, "VsmmMemoryBlockCopyByteRangeDirect");
      tlgCreate1Sz_char(v45, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemoryblock.c");
      v32 = 6772;
      v46 = &v32;
      v47 = 4;
      v33 = v7;
      v48 = &v33;
      v49 = 4;
      v22 = *a1;
      v50 = *(_QWORD *)(*a1 + 8) + 656LL;
      v51 = 16;
      v23 = *(_QWORD *)(v22 + 8);
      v24 = *(unsigned __int16 *)(v23 + 120);
      v25 = *(_QWORD *)(v23 + 128);
      v52 = v55;
      v53 = 2;
      v54 = v25;
      v55[0] = v24;
      v55[1] = 0;
      v39[0] = *(_QWORD *)(*(_QWORD *)(v22 + 8) + 648LL);
      v56 = v39;
      v57 = 8;
      result = tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &unk_14005993D, 0, 0, 10, v43);
    }
  }
LABEL_37:
  *((_DWORD *)a1 + 12) = v7;
  return result;
}

```

## disassembly

```asm
0x140101ee0  mov     [rsp+arg_10], rbx
0x140101ee5  push    rsi
0x140101ee6  push    rdi
0x140101ee7  push    r12
0x140101ee9  push    r14
0x140101eeb  push    r15
0x140101eed  sub     rsp, 310h
0x140101ef4  mov     rax, cs:__security_cookie
0x140101efb  xor     rax, rsp
0x140101efe  mov     [rsp+338h+var_38], rax
0x140101f06  mov     rsi, rdx
0x140101f09  mov     rbx, rcx
0x140101f0c  mov     [rsp+338h+var_2D8], rcx
0x140101f11  xor     r12d, r12d
0x140101f14  mov     [rsp+338h+var_304], r12d
0x140101f19  add     rsi, [rcx+18h]
0x140101f1d  mov     rcx, [rcx+10h]
0x140101f21  test    rcx, rcx
0x140101f24  jz      loc_1401024CB
0x140101f2a  mov     r14d, 0FFFFFFFFh
0x140101f30  cmp     [rbx+20h], r14
0x140101f34  jbe     loc_140102090
0x140101f3a  mov     edi, 0C00000BBh
0x140101f3f  mov     [rsp+338h+var_308], edi
0x140101f43  mov     eax, cs:dword_140065110
0x140101f49  cmp     eax, 2
0x140101f4c  jbe     loc_14010208B
0x140101f52  mov     edx, 100h
0x140101f57  lea     rcx, dword_140065110
0x140101f5e  call    _tlgKeywordOn
0x140101f63  test    al, al
0x140101f65  jz      loc_14010208B
0x140101f6b  lea     rdx, aVsmmmemorybloc_22; "VsmmMemoryBlockCopyByteRangeDirect"
0x140101f72  lea     rcx, [rsp+338h+var_1F8]
0x140101f7a  call    _tlgCreate1Sz_char
0x140101f7f  lea     rdx, aOnecoreVmVidSy_39; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemory"...
0x140101f86  lea     rcx, [rsp+338h+var_1E8]
0x140101f8e  call    _tlgCreate1Sz_char
0x140101f93  mov     [rsp+338h+var_304], 1A40h
0x140101f9b  lea     rax, [rsp+338h+var_304]
0x140101fa0  mov     [rsp+338h+var_1D8], rax
0x140101fa8  mov     [rsp+338h+var_1D0], 4
0x140101fb4  mov     [rsp+338h+var_2F8], edi
0x140101fb8  lea     rcx, [rsp+338h+var_2F8]
0x140101fbd  mov     [rsp+338h+var_1C8], rcx
0x140101fc5  mov     [rsp+338h+var_1C0], 4
0x140101fd1  mov     r8, [rbx]
0x140101fd4  mov     rax, [r8+8]
0x140101fd8  add     rax, 290h
0x140101fde  mov     [rsp+338h+var_1B8], rax
0x140101fe6  mov     [rsp+338h+var_1B0], 10h
0x140101ff2  mov     rax, [r8+8]
0x140101ff6  movzx   edx, word ptr [rax+78h]
0x140101ffa  mov     rcx, [rax+80h]
0x140102001  lea     rax, [rsp+338h+var_190]
0x140102009  mov     [rsp+338h+var_1A8], rax
0x140102011  mov     [rsp+338h+var_1A0], 2
0x14010201d  mov     [rsp+338h+var_198], rcx
0x140102025  mov     [rsp+338h+var_190], edx
0x14010202c  mov     [rsp+338h+var_18C], r12d
0x140102034  mov     rax, [r8+8]
0x140102038  mov     rdx, [rax+288h]
0x14010203f  mov     [rsp+338h+var_2D0], rdx
0x140102044  lea     rax, [rsp+338h+var_2D0]
0x140102049  mov     [rsp+338h+var_188], rax
0x140102051  mov     [rsp+338h+var_180], 8
0x14010205d  lea     rax, [rsp+338h+var_218]
0x140102065  mov     [rsp+338h+var_310], rax
0x14010206a  mov     dword ptr [rsp+338h+var_318], 0Ah
0x140102072  xor     r9d, r9d
0x140102075  xor     r8d, r8d
0x140102078  lea     rdx, unk_140059A19
0x14010207f  lea     rcx, dword_140065110
0x140102086  call    _tlgWriteTransfer_EtwWriteTransfer
0x14010208b  jmp     loc_140102700
0x140102090  mov     r8d, [rbx+20h]
0x140102094  mov     eax, [rbx+2Ch]
0x140102097  mov     rdx, rsi
0x14010209a  test    al, 1
0x14010209c  jz      loc_14010236B
0x1401020a2  lea     r9, [rsp+338h+var_304]
0x1401020a7  call    VmCompressUnpackEx
0x1401020ac  mov     edi, eax
0x1401020ae  mov     [rsp+338h+var_308], eax
0x1401020b2  test    eax, eax
0x1401020b4  jns     loc_140102207
0x1401020ba  mov     ecx, cs:dword_140065110
0x1401020c0  cmp     ecx, 2
0x1401020c3  jbe     loc_140102202
0x1401020c9  mov     edx, 100h
0x1401020ce  lea     rcx, dword_140065110
0x1401020d5  call    _tlgKeywordOn
0x1401020da  test    al, al
0x1401020dc  jz      loc_140102202
0x1401020e2  lea     rdx, aVsmmmemorybloc_22; "VsmmMemoryBlockCopyByteRangeDirect"
0x1401020e9  lea     rcx, [rsp+338h+var_158]
0x1401020f1  call    _tlgCreate1Sz_char
0x1401020f6  lea     rdx, aOnecoreVmVidSy_39; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemory"...
0x1401020fd  lea     rcx, [rsp+338h+var_148]
0x140102105  call    _tlgCreate1Sz_char
0x14010210a  mov     [rsp+338h+var_2F4], 1A55h
0x140102112  lea     rax, [rsp+338h+var_2F4]
0x140102117  mov     [rsp+338h+var_138], rax
0x14010211f  mov     [rsp+338h+var_130], 4
0x14010212b  mov     [rsp+338h+var_2F0], edi
0x14010212f  lea     rcx, [rsp+338h+var_2F0]
0x140102134  mov     [rsp+338h+var_128], rcx
0x14010213c  mov     [rsp+338h+var_120], 4
0x140102148  mov     r8, [rbx]
0x14010214b  mov     rax, [r8+8]
0x14010214f  add     rax, 290h
0x140102155  mov     [rsp+338h+var_118], rax
0x14010215d  mov     [rsp+338h+var_110], 10h
0x140102169  mov     rax, [r8+8]
0x14010216d  movzx   edx, word ptr [rax+78h]
0x140102171  mov     rcx, [rax+80h]
0x140102178  lea     rax, [rsp+338h+var_F0]
0x140102180  mov     [rsp+338h+var_108], rax
0x140102188  mov     [rsp+338h+var_100], 2
0x140102194  mov     [rsp+338h+var_F8], rcx
0x14010219c  mov     [rsp+338h+var_F0], edx
0x1401021a3  mov     [rsp+338h+var_EC], r12d
0x1401021ab  mov     rax, [r8+8]
0x1401021af  mov     rcx, [rax+288h]
0x1401021b6  mov     [rsp+338h+var_2C8], rcx
0x1401021bb  lea     rax, [rsp+338h+var_2C8]
0x1401021c0  mov     [rsp+338h+var_E8], rax
0x1401021c8  mov     [rsp+338h+var_E0], 8
0x1401021d4  lea     rax, [rsp+338h+var_178]
0x1401021dc  mov     [rsp+338h+var_310], rax
0x1401021e1  mov     dword ptr [rsp+338h+var_318], 0Ah
0x1401021e9  xor     r9d, r9d
0x1401021ec  xor     r8d, r8d
0x1401021ef  lea     rdx, unk_140059A87
0x1401021f6  lea     rcx, dword_140065110
0x1401021fd  call    _tlgWriteTransfer_EtwWriteTransfer
0x140102202  jmp     loc_140102700
0x140102207  mov     eax, [rsp+338h+var_304]
0x14010220b  cmp     rax, [rbx+20h]
0x14010220f  jz      loc_140102516
0x140102215  mov     edi, 0C000000Dh
0x14010221a  mov     [rsp+338h+var_308], edi
0x14010221e  mov     eax, cs:dword_140065110
0x140102224  cmp     eax, 2
0x140102227  jbe     loc_140102366
0x14010222d  mov     edx, 100h
0x140102232  lea     rcx, dword_140065110
0x140102239  call    _tlgKeywordOn
0x14010223e  test    al, al
0x140102240  jz      loc_140102366
0x140102246  lea     rdx, aVsmmmemorybloc_22; "VsmmMemoryBlockCopyByteRangeDirect"
0x14010224d  lea     rcx, [rsp+338h+var_B8]
0x140102255  call    _tlgCreate1Sz_char
0x14010225a  lea     rdx, aOnecoreVmVidSy_39; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemory"...
0x140102261  lea     rcx, [rsp+338h+var_A8]
0x140102269  call    _tlgCreate1Sz_char
0x14010226e  mov     [rsp+338h+var_2EC], 1A64h
0x140102276  lea     rax, [rsp+338h+var_2EC]
0x14010227b  mov     [rsp+338h+var_98], rax
0x140102283  mov     [rsp+338h+var_90], 4
0x14010228f  mov     [rsp+338h+var_2E8], edi
0x140102293  lea     rcx, [rsp+338h+var_2E8]
0x140102298  mov     [rsp+338h+var_88], rcx
0x1401022a0  mov     [rsp+338h+var_80], 4
0x1401022ac  mov     r8, [rbx]
0x1401022af  mov     rax, [r8+8]
0x1401022b3  add     rax, 290h
0x1401022b9  mov     [rsp+338h+var_78], rax
0x1401022c1  mov     [rsp+338h+var_70], 10h
0x1401022cd  mov     rax, [r8+8]
0x1401022d1  movzx   edx, word ptr [rax+78h]
0x1401022d5  mov     rcx, [rax+80h]
0x1401022dc  lea     rax, [rsp+338h+var_50]
0x1401022e4  mov     [rsp+338h+var_68], rax
0x1401022ec  mov     [rsp+338h+var_60], 2
0x1401022f8  mov     [rsp+338h+var_58], rcx
0x140102300  mov     [rsp+338h+var_50], edx
0x140102307  mov     [rsp+338h+var_4C], r12d
0x14010230f  mov     rax, [r8+8]
0x140102313  mov     rcx, [rax+288h]
0x14010231a  mov     [rsp+338h+var_2C0], rcx
0x14010231f  lea     rax, [rsp+338h+var_2C0]
0x140102324  mov     [rsp+338h+var_48], rax
0x14010232c  mov     [rsp+338h+var_40], 8
0x140102338  lea     rax, [rsp+338h+var_D8]
0x140102340  mov     [rsp+338h+var_310], rax
0x140102345  mov     dword ptr [rsp+338h+var_318], 0Ah
0x14010234d  xor     r9d, r9d
0x140102350  xor     r8d, r8d
0x140102353  lea     rdx, unk_140059AF5
0x14010235a  lea     rcx, dword_140065110
0x140102361  call    _tlgWriteTransfer_EtwWriteTransfer
0x140102366  jmp     loc_140102700
0x14010236b  call    VmCompressPackEx
0x140102370  mov     edi, eax
0x140102372  mov     [rsp+338h+var_308], eax
0x140102376  test    eax, eax
0x140102378  jns     loc_140102516
0x14010237e  mov     eax, cs:dword_140065110
0x140102384  cmp     eax, 2
0x140102387  jbe     loc_1401024C6
0x14010238d  mov     edx, 100h
0x140102392  lea     rcx, dword_140065110
0x140102399  call    _tlgKeywordOn
0x14010239e  test    al, al
0x1401023a0  jz      loc_1401024C6
0x1401023a6  lea     rdx, aVsmmmemorybloc_22; "VsmmMemoryBlockCopyByteRangeDirect"
0x1401023ad  lea     rcx, [rsp+338h+var_298]
0x1401023b5  call    _tlgCreate1Sz_char
0x1401023ba  lea     rdx, aOnecoreVmVidSy_39; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemory"...
0x1401023c1  lea     rcx, [rsp+338h+var_288]
0x1401023c9  call    _tlgCreate1Sz_char
0x1401023ce  mov     [rsp+338h+var_300], 1A74h
0x1401023d6  lea     rax, [rsp+338h+var_300]
0x1401023db  mov     [rsp+338h+var_278], rax
0x1401023e3  mov     [rsp+338h+var_270], 4
0x1401023ef  mov     [rsp+338h+var_2FC], edi
0x1401023f3  lea     rcx, [rsp+338h+var_2FC]
0x1401023f8  mov     [rsp+338h+var_268], rcx
0x140102400  mov     [rsp+338h+var_260], 4
0x14010240c  mov     r8, [rbx]
0x14010240f  mov     rax, [r8+8]
0x140102413  add     rax, 290h
0x140102419  mov     [rsp+338h+var_258], rax
0x140102421  mov     [rsp+338h+var_250], 10h
0x14010242d  mov     rax, [r8+8]
0x140102431  movzx   edx, word ptr [rax+78h]
0x140102435  mov     rcx, [rax+80h]
0x14010243c  lea     rax, [rsp+338h+var_230]
0x140102444  mov     [rsp+338h+var_248], rax
0x14010244c  mov     [rsp+338h+var_240], 2
0x140102458  mov     [rsp+338h+var_238], rcx
0x140102460  mov     [rsp+338h+var_230], edx
0x140102467  mov     [rsp+338h+var_22C], r12d
0x14010246f  mov     rax, [r8+8]
0x140102473  mov     rcx, [rax+288h]
0x14010247a  mov     [rsp+338h+var_2E0], rcx
0x14010247f  lea     rax, [rsp+338h+var_2E0]
0x140102484  mov     [rsp+338h+var_228], rax
0x14010248c  mov     [rsp+338h+var_220], 8
0x140102498  lea     rax, [rsp+338h+var_2B8]
0x1401024a0  mov     [rsp+338h+var_310], rax
0x1401024a5  mov     dword ptr [rsp+338h+var_318], 0Ah
0x1401024ad  xor     r9d, r9d
0x1401024b0  xor     r8d, r8d
0x1401024b3  lea     rdx, unk_14005993D
0x1401024ba  lea     rcx, dword_140065110
0x1401024c1  call    _tlgWriteTransfer_EtwWriteTransfer
0x1401024c6  jmp     loc_140102700
0x1401024cb  mov     rax, [rbx]
0x1401024ce  mov     ecx, [rax+108h]
0x1401024d4  shr     ecx, 3
0x1401024d7  and     cl, 1
0x1401024da  mov     rdx, [rbx+20h]
0x1401024de  mov     r10b, [rbx+29h]
0x1401024e2  mov     r11, [rbx+8]
0x1401024e6  mov     eax, [rbx+2Ch]
0x1401024e9  mov     [rsp+338h+var_318], rdx
0x1401024ee  test    al, 1
0x1401024f0  jz      short loc_1401024FF
0x1401024f2  mov     r9b, r10b
0x1401024f5  mov     r8, r11
0x1401024f8  mov     dl, cl
0x1401024fa  mov     rcx, rsi
0x1401024fd  jmp     short loc_14010250B
0x1401024ff  mov     r9b, cl
0x140102502  mov     r8, rsi
0x140102505  mov     dl, r10b
0x140102508  mov     rcx, r11
0x14010250b  call    VsmmpCopyFromModeToMode
0x140102510  mov     r14d, 0FFFFFFFFh
0x140102516  mov     eax, [rbx+2Ch]
0x140102519  test    al, 1
0x14010251b  jz      short loc_140102585
0x14010251d  cmp     [rbx+28h], r12b
0x140102521  jz      short loc_140102556
0x140102523  mov     rdi, [rbx+20h]
0x140102527  test    rdi, rdi
0x14010252a  jz      short loc_140102585
0x14010252c  cmp     rdi, r14
0x14010252f  mov     r15d, edi
0x140102532  jb      short loc_140102537
0x140102534  mov     r15d, r14d
0x140102537  mov     edx, r15d; Length
0x14010253a  mov     rcx, rsi; BaseAddress
0x14010253d  call    cs:__imp_KeInvalidateRangeAllCaches
0x140102544  nop     dword ptr [rax+rax+00h]
0x140102549  mov     eax, r15d
0x14010254c  add     rsi, rax
0x14010254f  sub     rdi, rax
0x140102552  jnz     short loc_14010252C
0x140102554  jmp     short loc_140102585
0x140102556  mov     rcx, [rbx]
0x140102559  test    dword ptr [rcx+108h], 2000h
0x140102563  jz      short loc_140102585
0x140102565  mov     r9d, r12d
0x140102568  mov     r8, [rbx+20h]
0x14010256c  mov     rdx, rsi
0x14010256f  mov     rcx, [rcx+348h]
0x140102576  call    VsmmDaxFileFlushVaRange
  ... truncated ...
```
