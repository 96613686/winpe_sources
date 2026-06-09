# NsiEnumerateObjectsAllParametersEx

- ea: `0x140025b90`
- end: `0x140026562`
- name: `NsiEnumerateObjectsAllParametersEx`
- size: `2514`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int)`
- caller_count: `3`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140025780`
- `0x140026620`
- `0x140050258`

## callees

- `0x1400223f0`
- `0x140023a40`
- `0x140023c30`
- `0x140025a60`
- `0x140025b90`
- `0x140027810`
- `0x14004e930`
- `0x140050ea4`
- `0x1400512d8`
- `0x14005f0b0`
- `0x14005f1c4`
- `0x140077fa0`
- `0x140078080`
- `0x140078100`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x140025c3b`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140025c3b`
- `ntoskrnl!qsort` at `0x14002608b`
- `ntoskrnl!qsort` at `0x140026222`
- `ntoskrnl!qsort` at `0x1400262ce`
- `ntoskrnl!qsort` at `0x14002608b`
- `ntoskrnl!qsort` at `0x140026222`
- `ntoskrnl!qsort` at `0x1400262ce`
- `ntoskrnl!KeGetCurrentIrql` at `0x140025de3`
- `ntoskrnl!KeGetCurrentIrql` at `0x140025de3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400262df`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002644c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400262df`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002644c`
- `NDIS!NdisGetThreadObjectCompartmentScope` at `0x140025c6b`
- `NDIS!NdisGetThreadObjectCompartmentScope` at `0x140025c6b`

## pseudocode

```c
__int64 __fastcall NsiEnumerateObjectsAllParametersEx(__int64 a1, __int64 a2, unsigned int a3)
{
  __int64 v3; // rdi
  __int64 v4; // rax
  int v5; // r14d
  int v6; // r15d
  size_t *v7; // rbx
  char CurrentProcessId; // si
  __int64 v9; // r9
  PDEVICE_OBJECT v10; // rcx
  __int64 v11; // rdx
  int v12; // ebx
  bool v13; // zf
  __int64 v14; // rax
  int v15; // eax
  __int64 v16; // rcx
  __int64 NmpContext; // rax
  __int64 v18; // rsi
  __int64 v19; // rdx
  int v20; // eax
  void *v21; // r10
  __int64 v22; // rbx
  __int64 v23; // r15
  __int64 v24; // rcx
  int v25; // r11d
  __int64 v26; // r12
  __int64 v27; // rax
  __int64 v28; // rdx
  unsigned int *v29; // r14
  size_t v30; // r13
  unsigned int v31; // ecx
  unsigned int v32; // r15d
  __int64 v33; // rdx
  __int64 v34; // r12
  unsigned int v35; // ecx
  __int64 v36; // rax
  unsigned int v37; // esi
  char *LowPriority; // rax
  char *v39; // r14
  unsigned int v40; // edx
  unsigned int v41; // esi
  size_t v42; // r8
  __int64 v43; // rdi
  char *v44; // rcx
  __int64 v45; // rcx
  unsigned int v46; // ecx
  size_t v47; // r8
  __int64 v48; // rbx
  unsigned int i; // esi
  unsigned int v50; // eax
  __int64 v51; // rbx
  char *v52; // rcx
  __int64 v53; // rcx
  unsigned int v54; // ecx
  unsigned int v55; // esi
  size_t v56; // r8
  __int64 v57; // rdi
  unsigned int v58; // eax
  __int64 v59; // rax
  char *v60; // r15
  unsigned int v61; // esi
  int v62; // eax
  void *v63; // r9
  char *v64; // rcx
  __int64 v65; // rax
  size_t *v66; // rdx
  int v68; // [rsp+38h] [rbp-D0h]
  unsigned int Size; // [rsp+68h] [rbp-A0h]
  size_t v70; // [rsp+70h] [rbp-98h] BYREF
  size_t SizeOfElements; // [rsp+78h] [rbp-90h]
  unsigned int v72; // [rsp+80h] [rbp-88h] BYREF
  unsigned int v73; // [rsp+88h] [rbp-80h]
  __int64 v74; // [rsp+90h] [rbp-78h]
  __int64 v75; // [rsp+98h] [rbp-70h]
  __int64 v76; // [rsp+A0h] [rbp-68h]
  int v77; // [rsp+A8h] [rbp-60h]
  __int64 v78; // [rsp+B0h] [rbp-58h]
  __int64 v79; // [rsp+B8h] [rbp-50h]
  __int64 v80; // [rsp+C0h] [rbp-48h]
  _QWORD v81[2]; // [rsp+C8h] [rbp-40h] BYREF
  void *Src; // [rsp+D8h] [rbp-30h]
  __int64 v83; // [rsp+E0h] [rbp-28h]
  int v84; // [rsp+E8h] [rbp-20h]
  int v85; // [rsp+ECh] [rbp-1Ch]
  __int64 v86; // [rsp+F0h] [rbp-18h]
  __int64 v87; // [rsp+F8h] [rbp-10h]
  __int64 v88; // [rsp+100h] [rbp-8h]
  __int64 v89; // [rsp+108h] [rbp+0h]
  __int64 v90; // [rsp+110h] [rbp+8h]
  __int64 v91; // [rsp+118h] [rbp+10h]
  __int128 v92; // [rsp+128h] [rbp+20h] BYREF
  __int128 v93; // [rsp+138h] [rbp+30h]
  __int128 v94; // [rsp+148h] [rbp+40h]
  __int128 v95; // [rsp+158h] [rbp+50h]
  __int128 v96; // [rsp+168h] [rbp+60h]
  __int128 v97; // [rsp+178h] [rbp+70h]
  size_t v98[2]; // [rsp+188h] [rbp+80h] BYREF

  v92 = 0;
  v72 = 0;
  v3 = a1;
  v93 = 0;
  LODWORD(v70) = 0;
  v94 = 0;
  v95 = 0;
  v96 = 0;
  v80 = a1;
  v97 = 0;
  if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
  {
    v4 = *(_QWORD *)(a1 + 16);
    v5 = *(_DWORD *)(a1 + 32);
    v6 = *(_DWORD *)(a1 + 24);
    *(_OWORD *)v98 = 0;
    v7 = (size_t *)(v4 + 8);
    if ( !v4 )
      v7 = v98;
    CurrentProcessId = (unsigned __int8)PsGetCurrentProcessId();
    NdisGetThreadObjectCompartmentScope(KeGetCurrentThread(), &v72, &v70);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    {
      WPP_SF_s_guid_dddqdd(
        WPP_GLOBAL_Control->AttachedDevice,
        v72,
        a3,
        (unsigned int)"NsiEnumerateObjectsAllParametersEx",
        (__int64)v7,
        v6,
        v5,
        CurrentProcessId,
        0,
        v70,
        v72);
    }
  }
  v9 = *(unsigned int *)(v3 + 32);
  if ( (_DWORD)v9 == 2 || (unsigned int)v9 > 3 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0 )
    {
      goto LABEL_116;
    }
    v11 = 44;
LABEL_115:
    WPP_SF_d(v10->AttachedDevice, v11, WPP_b802283a6c2b3e3c6b570e68b8145ddd_Traceguids, v9);
    goto LABEL_116;
  }
  a3 = *(_DWORD *)(v3 + 36);
  if ( a3 - 1 > 1 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0 )
    {
      goto LABEL_116;
    }
    v11 = 45;
    v9 = a3;
    goto LABEL_115;
  }
  if ( *(_QWORD *)v3 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_b802283a6c2b3e3c6b570e68b8145ddd_Traceguids);
    }
    v12 = -1073741822;
    goto LABEL_117;
  }
  if ( (_DWORD)v9 )
  {
    if ( KeGetCurrentIrql() < 2u )
    {
      v12 = NsipAccessCheck((unsigned int *)(v3 + 8), 1, 0);
      if ( v12 < 0 )
        goto LABEL_117;
    }
    NmpContext = NsipGetNmpContext(v3 + 8);
    v74 = NmpContext;
    if ( !NmpContext )
    {
      v12 = -1073741637;
      goto LABEL_117;
    }
    v18 = *(_QWORD *)(NmpContext + 48);
    v12 = NsipValidateEnumerateObjectsAllParametersRequest(v18, v3);
    if ( v12 < 0 )
    {
LABEL_110:
      NsipDereferenceNmpContext(v74);
      goto LABEL_117;
    }
    v19 = *(_QWORD *)(v3 + 88);
    v20 = *(_DWORD *)(v3 + 64);
    v21 = *(void **)(v3 + 40);
    v22 = *(_QWORD *)(v3 + 56);
    v23 = *(_QWORD *)(v3 + 72);
    v24 = *(_QWORD *)(v3 + 80);
    v25 = *(_DWORD *)(v3 + 36);
    v26 = *(unsigned int *)(v3 + 96);
    DWORD2(v97) = *(_DWORD *)(v3 + 104);
    *((_QWORD *)&v96 + 1) = v19;
    LODWORD(v94) = v25;
    *(_QWORD *)&v93 = v21;
    *((_QWORD *)&v94 + 1) = v22;
    *((_QWORD *)&v95 + 1) = v23;
    *(_QWORD *)&v96 = v24;
    LODWORD(v70) = v20;
    *((_QWORD *)&v93 + 1) = *(_QWORD *)(v3 + 48);
    v27 = *(_QWORD *)(v3 + 64);
    *(_QWORD *)&v95 = v27;
    v75 = v19;
    v28 = *(_QWORD *)(v3 + 96);
    *(_QWORD *)&v97 = v28;
    *(_QWORD *)&v92 = *(_QWORD *)(v74 + 40);
    v98[0] = v92;
    v29 = (unsigned int *)(*(_QWORD *)(v18 + 8) + 104LL * *(unsigned int *)(v3 + 24));
    v30 = *(unsigned int *)(v3 + 80);
    v72 = v26;
    if ( *((_QWORD *)v29 + 8) )
    {
      *((_QWORD *)&v92 + 1) = *((_QWORD *)v29 + 3);
      v77 = (*((__int64 (__fastcall **)(__int128 *))v29 + 8))(&v92);
      v12 = v77;
      if ( v77 < 0 || (v29[4] & 1) != 0 || (v31 = *(_DWORD *)(v3 + 104), v31 <= 1) )
      {
LABEL_81:
        v32 = DWORD2(v97);
LABEL_82:
        *(_DWORD *)(v3 + 104) = v32;
        goto LABEL_110;
      }
      v32 = DWORD2(v97);
      if ( DWORD2(v97) <= 1 || !*(_DWORD *)(v3 + 48) )
        goto LABEL_82;
      v33 = *(_QWORD *)(v3 + 56);
      v34 = *(_QWORD *)(v3 + 88);
      if ( DWORD2(v97) > v31 )
        v32 = *(_DWORD *)(v3 + 104);
      v35 = *v29;
      v78 = *(_QWORD *)(v3 + 40);
      v36 = *(_QWORD *)(v3 + 72);
      v75 = v33;
      v79 = v36;
      v37 = v35 + 4;
      LODWORD(SizeOfElements) = v35 + 4;
      Size = v35;
      if ( v33 )
      {
        v37 += v70;
        LODWORD(SizeOfElements) = v37;
      }
      if ( v34 )
      {
        v37 += v72;
        LODWORD(SizeOfElements) = v37;
      }
      if ( v36 )
      {
        v37 += v30;
        LODWORD(SizeOfElements) = v37;
      }
      LowPriority = (char *)NsipAllocateLowPriority(v37 * v32);
      v39 = LowPriority;
      if ( LowPriority )
      {
        if ( v32 )
        {
          v40 = Size;
          v41 = 0;
          v42 = Size;
          v98[0] = Size;
          if ( v75 )
          {
            v43 = v79;
            v98[0] = (size_t)&LowPriority[Size + 4];
            v73 = Size + v70 + 4;
            do
            {
              v76 = v41 * (unsigned int)SizeOfElements;
              v44 = &v39[v76 + 4];
              *(_DWORD *)&v39[v76] = v40;
              memmove(v44, (const void *)(v78 + v41 * v40), v42);
              memmove((void *)(v76 + v98[0]), (const void *)(v75 + (unsigned int)v70 * v41), (unsigned int)v70);
              v45 = v73;
              if ( v43 )
              {
                memmove(&v39[v76 + v73], (const void *)(v43 + (unsigned int)v30 * v41), v30);
                v45 = (unsigned int)v30 + v73;
              }
              if ( v34 )
                memmove(&v39[v76 + v45], (const void *)(v34 + v41 * v72), v72);
              v40 = Size;
              ++v41;
              v42 = Size;
            }
            while ( v41 < v32 );
            qsort(v39, v32, (unsigned int)SizeOfElements, NsipCompare);
            v46 = Size;
            v3 = v80;
            v47 = Size;
            v48 = v79;
            v98[0] = (size_t)&v39[Size + 4];
            for ( i = 0; i < v32; ++i )
            {
              v76 = i * (unsigned int)SizeOfElements;
              memmove((void *)(v78 + i * v46), &v39[v76 + 4], v47);
              memmove((void *)(v75 + (unsigned int)v70 * i), (const void *)(v98[0] + v76), (unsigned int)v70);
              if ( v48 )
              {
                memmove((void *)(v48 + (unsigned int)v30 * i), &v39[v76 + 4 + Size + (unsigned int)v70], v30);
                v50 = v30 + Size + v70 + 4;
              }
              else
              {
                v50 = Size + v70 + 4;
              }
              if ( v34 )
                memmove((void *)(v34 + i * v72), &v39[v76 + v50], v72);
              v46 = Size;
              v47 = Size;
            }
            v12 = v77;
          }
          else
          {
            v51 = v79;
            while ( 1 )
            {
              v75 = v41 * (unsigned int)SizeOfElements;
              v52 = &v39[v75 + 4];
              *(_DWORD *)&v39[v75] = v40;
              memmove(v52, (const void *)(v78 + v41 * v40), v42);
              v53 = Size + 4;
              if ( v51 )
              {
                memmove(&v39[v75 + 4 + Size], (const void *)(v51 + (unsigned int)v30 * v41), v30);
                v53 = (unsigned int)v30 + Size + 4;
              }
              if ( v34 )
                memmove(&v39[v75 + v53], (const void *)(v34 + v41 * v72), v72);
              v42 = v98[0];
              if ( ++v41 >= v32 )
                break;
              v40 = Size;
            }
            qsort(v39, v32, (unsigned int)SizeOfElements, NsipCompare);
            v54 = Size;
            v55 = 0;
            v12 = v77;
            v56 = Size;
            v57 = Size + 4;
            do
            {
              v75 = v55 * (unsigned int)SizeOfElements;
              memmove((void *)(v78 + v55 * v54), &v39[v75 + 4], v56);
              if ( v79 )
              {
                memmove((void *)(v79 + (unsigned int)v30 * v55), &v39[v75 + v57], v30);
                v58 = v57 + v30;
              }
              else
              {
                v58 = Size + 4;
              }
              if ( v34 )
                memmove((void *)(v34 + v55 * v72), &v39[v75 + v58], v72);
              v54 = Size;
              ++v55;
              v56 = Size;
            }
            while ( v55 < v32 );
            v3 = v80;
          }
        }
        else
        {
          qsort(LowPriority, 0, v37, NsipCompare);
        }
        ExFreePoolWithTag(v39, 0);
        goto LABEL_81;
      }
LABEL_109:
      v12 = -1073741670;
      goto LABEL_110;
    }
    v85 = 0;
    if ( !*((_QWORD *)v29 + 6) )
    {
      v12 = -1073741822;
      goto LABEL_110;
    }
    v87 = v27;
    v90 = v75;
    v83 = *((_QWORD *)&v93 + 1);
    v59 = *v29;
    v81[0] = v98[0];
    v81[1] = *((_QWORD *)v29 + 3);
    v84 = v25;
    v86 = v22;
    v88 = v23;
    v89 = v24;
    v91 = v28;
    Src = v21;
    if ( (_DWORD)v59 )
    {
      v60 = (char *)NsipAllocateLowPriority(v59);
      if ( !v60 )
        goto LABEL_109;
      v21 = Src;
    }
    else
    {
      v60 = 0;
    }
    v61 = 0;
    if ( !v21 )
    {
      LODWORD(v83) = *v29;
      v84 = 1;
      Src = v60;
    }
    while ( 1 )
    {
      v62 = (*((__int64 (__fastcall **)(_QWORD *))v29 + 6))(v81);
      v12 = v62;
      if ( v62 == -2147483622 )
        break;
      if ( v62 < 0 )
        goto LABEL_107;
      ++v61;
      if ( (_QWORD)v93 )
      {
        v63 = Src;
        if ( v61 >= DWORD2(v97) )
        {
          if ( v61 != DWORD2(v97) )
          {
            v61 = DWORD2(v97);
            v12 = 261;
            goto LABEL_107;
          }
          v64 = v60;
          Src = v60;
          v86 = 0;
          v88 = 0;
          v90 = 0;
        }
        else
        {
          v64 = (char *)Src + *v29;
          Src = v64;
          if ( v86 )
            v86 += (unsigned int)v70;
          if ( v88 )
            v88 += v30;
          if ( v90 )
            v90 += v26;
        }
        memmove(v64, v63, *v29);
      }
      v84 = 2;
    }
    v12 = 0;
LABEL_107:
    *(_DWORD *)(v3 + 104) = v61;
    if ( v60 )
      ExFreePoolWithTag(v60, 0);
    goto LABEL_110;
  }
  v13 = *(_QWORD *)(v3 + 16) == 0;
  v74 = 0;
  if ( v13 )
  {
    v14 = NsipGetNmpContext(v3 + 8);
    v74 = v14;
    if ( !v14 )
    {
LABEL_116:
      v12 = -1073741811;
      goto LABEL_117;
    }
    *(_QWORD *)(v3 + 16) = *(_QWORD *)(v14 + 24);
  }
  v15 = NsipEnumeratePersistentData(
          (int)v3 + 8,
          *(_DWORD *)(v3 + 36),
          (int)v3 + 40,
          *(_QWORD *)(v3 + 56),
          0,
          v3 + 64,
          v68,
          v3 + 104);
  v16 = v74;
  v12 = v15;
  if ( v74 )
  {
    *(_QWORD *)(v3 + 16) = 0;
    NsipDereferenceNmpContext(v16);
  }
LABEL_117:
  if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
  {
    v65 = *(_QWORD *)(v3 + 16);
    *(_OWORD *)v98 = 0;
    v66 = (size_t *)(v65 + 8);
    if ( !v65 )
      v66 = v98;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_s_guid_dddqddD(
        WPP_GLOBAL_Control->AttachedDevice,
        (_DWORD)v66,
        a3,
        (unsigned int)"NsiEnumerateObjectsAllParametersEx",
        (__int64)v66,
        *(_DWORD *)(v3 + 24),
        *(_DWORD *)(v3 + 32),
        0,
        0,
        0,
        0,
        v12);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140025b90  mov     r11, rsp
0x140025b93  push    rbp
0x140025b94  push    rbx
0x140025b95  push    rdi
0x140025b96  push    r12
0x140025b98  lea     rbp, [r11-0C8h]
0x140025b9f  sub     rsp, 1A8h
0x140025ba6  mov     rax, cs:__security_cookie
0x140025bad  xor     rax, rsp
0x140025bb0  mov     [rbp+0C0h+var_30], rax
0x140025bb7  mov     rax, cs:WPP_GLOBAL_Control
0x140025bbe  lea     r12, WPP_GLOBAL_Control
0x140025bc5  xorps   xmm0, xmm0
0x140025bc8  mov     [r11+10h], rsi
0x140025bcc  movups  [rbp+0C0h+var_A0], xmm0
0x140025bd0  mov     [rsp+1C0h+var_148], 0
0x140025bd8  mov     rdi, rcx
0x140025bdb  movups  [rbp+0C0h+var_90], xmm0
0x140025bdf  mov     dword ptr [rsp+1C0h+var_158], 0
0x140025be7  movups  [rbp+0C0h+var_80], xmm0
0x140025beb  mov     [r11+20h], r14
0x140025bef  movups  [rbp+0C0h+var_70], xmm0
0x140025bf3  mov     [r11-28h], r15
0x140025bf7  movups  [rbp+0C0h+var_60], xmm0
0x140025bfb  mov     [rbp+0C0h+var_108], rcx
0x140025bff  movups  [rbp+0C0h+var_50], xmm0
0x140025c03  cmp     byte ptr [rax+29h], 5
0x140025c07  jb      loc_140025CCC
0x140025c0d  mov     eax, [rax+2Ch]
0x140025c10  test    al, 10h
0x140025c12  jz      loc_140025CCC
0x140025c18  mov     rax, [rcx+10h]
0x140025c1c  mov     r14d, [rcx+20h]
0x140025c20  mov     r15d, [rcx+18h]
0x140025c24  movups  xmmword ptr [rbp+0C0h+var_40], xmm0
0x140025c2b  lea     rbx, [rax+8]
0x140025c2f  test    rax, rax
0x140025c32  jnz     short loc_140025C3B
0x140025c34  lea     rbx, [rbp+0C0h+var_40]
0x140025c3b  call    cs:__imp_PsGetCurrentProcessId
0x140025c42  nop     dword ptr [rax+rax+00h]
0x140025c47  mov     edx, [rsp+1C0h+var_148]
0x140025c4b  mov     rsi, rax
0x140025c4e  test    edx, edx
0x140025c50  jnz     short loc_140025C7B
0x140025c52  cmp     dword ptr [rsp+1C0h+var_158], edx
0x140025c56  jnz     short loc_140025C7B
0x140025c58  mov     rcx, gs:188h
0x140025c61  lea     r8, [rsp+1C0h+var_158]
0x140025c66  lea     rdx, [rsp+1C0h+var_148]
0x140025c6b  call    cs:__imp_NdisGetThreadObjectCompartmentScope
0x140025c72  nop     dword ptr [rax+rax+00h]
0x140025c77  mov     edx, [rsp+1C0h+var_148]
0x140025c7b  mov     rcx, cs:WPP_GLOBAL_Control
0x140025c82  cmp     rcx, r12
0x140025c85  jz      short loc_140025CCC
0x140025c87  cmp     byte ptr [rcx+29h], 5
0x140025c8b  jb      short loc_140025CCC
0x140025c8d  mov     eax, [rcx+2Ch]
0x140025c90  test    al, 10h
0x140025c92  jz      short loc_140025CCC
0x140025c94  mov     eax, dword ptr [rsp+1C0h+var_158]
0x140025c98  lea     r9, aNsienumerateob; "NsiEnumerateObjectsAllParametersEx"
0x140025c9f  mov     rcx, [rcx+18h]
0x140025ca3  mov     [rsp+1C0h+var_170], edx
0x140025ca7  mov     [rsp+1C0h+var_178], eax
0x140025cab  mov     qword ptr [rsp+1C0h+var_180], 0
0x140025cb4  mov     dword ptr [rsp+1C0h+var_188], esi
0x140025cb8  mov     dword ptr [rsp+1C0h+var_190], r14d
0x140025cbd  mov     [rsp+1C0h+var_198], r15d
0x140025cc2  mov     [rsp+1C0h+var_1A0], rbx
0x140025cc7  call    WPP_SF_s_guid_dddqdd
0x140025ccc  mov     r9d, [rdi+20h]
0x140025cd0  cmp     r9d, 2
0x140025cd4  jz      loc_140026479
0x140025cda  cmp     r9d, 3
0x140025cde  ja      loc_140026479
0x140025ce4  mov     r8d, [rdi+24h]
0x140025ce8  lea     eax, [r8-1]
0x140025cec  cmp     eax, 1
0x140025cef  jbe     short loc_140025D23
0x140025cf1  mov     rcx, cs:WPP_GLOBAL_Control
0x140025cf8  cmp     rcx, r12
0x140025cfb  jz      loc_1400264A7
0x140025d01  cmp     byte ptr [rcx+29h], 2
0x140025d05  jb      loc_1400264A7
0x140025d0b  mov     eax, [rcx+2Ch]
0x140025d0e  test    al, 10h
0x140025d10  jz      loc_1400264A7
0x140025d16  mov     edx, 2Dh ; '-'
0x140025d1b  mov     r9d, r8d
0x140025d1e  jmp     loc_140026497
0x140025d23  cmp     qword ptr [rdi], 0
0x140025d27  jz      short loc_140025D61
0x140025d29  mov     rcx, cs:WPP_GLOBAL_Control
0x140025d30  cmp     rcx, r12
0x140025d33  jz      short loc_140025D57
0x140025d35  cmp     byte ptr [rcx+29h], 2
0x140025d39  jb      short loc_140025D57
0x140025d3b  mov     eax, [rcx+2Ch]
0x140025d3e  test    al, 10h
0x140025d40  jz      short loc_140025D57
0x140025d42  mov     rcx, [rcx+18h]
0x140025d46  lea     r8, WPP_b802283a6c2b3e3c6b570e68b8145ddd_Traceguids
0x140025d4d  mov     edx, 2Eh ; '.'
0x140025d52  call    WPP_SF_
0x140025d57  mov     ebx, 0C0000002h
0x140025d5c  jmp     loc_1400264AC
0x140025d61  test    r9d, r9d
0x140025d64  jnz     short loc_140025DE3
0x140025d66  cmp     qword ptr [rdi+10h], 0
0x140025d6b  mov     [rbp+0C0h+var_138], 0
0x140025d73  jnz     short loc_140025D93
0x140025d75  lea     rcx, [rdi+8]
0x140025d79  call    NsipGetNmpContext
0x140025d7e  mov     [rbp+0C0h+var_138], rax
0x140025d82  test    rax, rax
0x140025d85  jz      loc_1400264A7
0x140025d8b  mov     rax, [rax+18h]
0x140025d8f  mov     [rdi+10h], rax
0x140025d93  mov     r9, [rdi+38h]
0x140025d97  lea     rdx, [rdi+40h]
0x140025d9b  lea     rax, [rdi+68h]
0x140025d9f  mov     [rsp+1C0h+var_188], rax
0x140025da4  lea     r8, [rdi+28h]
0x140025da8  mov     qword ptr [rsp+1C0h+var_198], rdx
0x140025dad  lea     rcx, [rdi+8]
0x140025db1  mov     edx, [rdi+24h]
0x140025db4  mov     [rsp+1C0h+var_1A0], 0
0x140025dbd  call    NsipEnumeratePersistentData
0x140025dc2  mov     rcx, [rbp+0C0h+var_138]
0x140025dc6  mov     ebx, eax
0x140025dc8  test    rcx, rcx
0x140025dcb  jz      loc_1400264AC
0x140025dd1  mov     qword ptr [rdi+10h], 0
0x140025dd9  call    NsipDereferenceNmpContext
0x140025dde  jmp     loc_1400264AC
0x140025de3  call    cs:__imp_KeGetCurrentIrql
0x140025dea  nop     dword ptr [rax+rax+00h]
0x140025def  cmp     al, 2
0x140025df1  jnb     short loc_140025E0B
0x140025df3  lea     rcx, [rdi+8]
0x140025df7  xor     r8d, r8d
0x140025dfa  mov     dl, 1
0x140025dfc  call    NsipAccessCheck
0x140025e01  mov     ebx, eax
0x140025e03  test    eax, eax
0x140025e05  js      loc_1400264AC
0x140025e0b  lea     rcx, [rdi+8]
0x140025e0f  call    NsipGetNmpContext
0x140025e14  mov     [rbp+0C0h+var_138], rax
0x140025e18  test    rax, rax
0x140025e1b  jnz     short loc_140025E27
0x140025e1d  mov     ebx, 0C00000BBh
0x140025e22  jmp     loc_1400264AC
0x140025e27  mov     rsi, [rax+30h]
0x140025e2b  mov     rdx, rdi
0x140025e2e  mov     rcx, rsi
0x140025e31  call    NsipValidateEnumerateObjectsAllParametersRequest
0x140025e36  mov     ebx, eax
0x140025e38  test    eax, eax
0x140025e3a  js      loc_14002646E
0x140025e40  mov     rdx, [rdi+58h]
0x140025e44  mov     eax, [rdi+40h]
0x140025e47  mov     r8d, [rdi+68h]
0x140025e4b  mov     r10, [rdi+28h]
0x140025e4f  mov     rbx, [rdi+38h]
0x140025e53  mov     r15, [rdi+48h]
0x140025e57  mov     rcx, [rdi+50h]
0x140025e5b  mov     r11d, [rdi+24h]
0x140025e5f  mov     r12d, [rdi+60h]
0x140025e63  mov     dword ptr [rbp+0C0h+var_50+8], r8d
0x140025e67  mov     r8, [rbp+0C0h+var_138]
0x140025e6b  mov     qword ptr [rbp+0C0h+var_60+8], rdx
0x140025e6f  mov     dword ptr [rbp+0C0h+var_80], r11d
0x140025e73  mov     qword ptr [rbp+0C0h+var_90], r10
0x140025e77  mov     qword ptr [rbp+0C0h+var_80+8], rbx
0x140025e7b  mov     qword ptr [rbp+0C0h+var_70+8], r15
0x140025e7f  mov     qword ptr [rbp+0C0h+var_60], rcx
0x140025e83  mov     dword ptr [rsp+1C0h+var_158], eax
0x140025e87  mov     rax, [rdi+30h]
0x140025e8b  mov     qword ptr [rbp+0C0h+var_90+8], rax
0x140025e8f  mov     rax, [rdi+40h]
0x140025e93  mov     qword ptr [rbp+0C0h+var_70], rax
0x140025e97  mov     [rbp+0C0h+var_130], rdx
0x140025e9b  mov     rdx, [rdi+60h]
0x140025e9f  mov     qword ptr [rbp+0C0h+var_50], rdx
0x140025ea3  mov     r8, [r8+28h]
0x140025ea7  mov     qword ptr [rbp+0C0h+var_A0], r8
0x140025eab  mov     [rbp+0C0h+var_40], r8
0x140025eb2  mov     r8d, [rdi+18h]
0x140025eb6  imul    r14, r8, 68h ; 'h'
0x140025eba  mov     [rsp+1C0h+arg_10], r13
0x140025ec2  add     r14, [rsi+8]
0x140025ec6  mov     r13d, [rdi+50h]
0x140025eca  mov     [rsp+1C0h+var_148], r12d
0x140025ecf  cmp     qword ptr [r14+40h], 0
0x140025ed4  jz      loc_1400262F8
0x140025eda  mov     rax, [r14+18h]
0x140025ede  lea     rcx, [rbp+0C0h+var_A0]
0x140025ee2  mov     qword ptr [rbp+0C0h+var_A0+8], rax
0x140025ee6  mov     rax, [r14+40h]
0x140025eea  call    _guard_dispatch_icall
0x140025eef  mov     [rbp+0C0h+var_120], eax
0x140025ef2  mov     ebx, eax
0x140025ef4  test    eax, eax
0x140025ef6  js      loc_1400262EB
0x140025efc  test    byte ptr [r14+10h], 1
0x140025f01  jnz     loc_1400262EB
0x140025f07  mov     ecx, [rdi+68h]
0x140025f0a  cmp     ecx, 1
0x140025f0d  jbe     loc_1400262EB
0x140025f13  mov     r15d, dword ptr [rbp+0C0h+var_50+8]
0x140025f17  cmp     r15d, 1
0x140025f1b  jbe     loc_1400262EF
0x140025f21  cmp     dword ptr [rdi+30h], 0
0x140025f25  jz      loc_1400262EF
0x140025f2b  mov     rax, [rdi+28h]
0x140025f2f  cmp     r15d, ecx
0x140025f32  mov     rdx, [rdi+38h]
0x140025f36  mov     r12, [rdi+58h]
0x140025f3a  cmova   r15d, ecx
0x140025f3e  mov     ecx, [r14]
0x140025f41  mov     [rbp+0C0h+var_118], rax
0x140025f45  mov     rax, [rdi+48h]
0x140025f49  mov     [rbp+0C0h+var_130], rdx
0x140025f4d  mov     [rbp+0C0h+var_110], rax
0x140025f51  lea     esi, [rcx+4]
0x140025f54  mov     dword ptr [rsp+1C0h+SizeOfElements], esi
0x140025f58  mov     dword ptr [rsp+1C0h+Size], ecx
0x140025f5c  test    rdx, rdx
0x140025f5f  jz      short loc_140025F69
0x140025f61  add     esi, dword ptr [rsp+1C0h+var_158]
0x140025f65  mov     dword ptr [rsp+1C0h+SizeOfElements], esi
0x140025f69  test    r12, r12
0x140025f6c  jz      short loc_140025F76
0x140025f6e  add     esi, [rsp+1C0h+var_148]
0x140025f72  mov     dword ptr [rsp+1C0h+SizeOfElements], esi
0x140025f76  test    rax, rax
0x140025f79  jz      short loc_140025F82
0x140025f7b  add     esi, r13d
0x140025f7e  mov     dword ptr [rsp+1C0h+SizeOfElements], esi
0x140025f82  mov     ecx, r15d
0x140025f85  imul    ecx, esi
0x140025f88  call    NsipAllocateLowPriority
0x140025f8d  mov     r14, rax
0x140025f90  test    rax, rax
0x140025f93  jz      loc_14002645A
0x140025f99  test    r15d, r15d
0x140025f9c  jz      loc_1400262BE
0x140025fa2  mov     edx, dword ptr [rsp+1C0h+Size]
0x140025fa6  xor     esi, esi
0x140025fa8  mov     r8d, edx; Size
0x140025fab  mov     [rbp+0C0h+var_40], rdx
0x140025fb2  lea     eax, [rdx+4]
0x140025fb5  cmp     [rbp+0C0h+var_130], rsi
0x140025fb9  jz      loc_14002617C
0x140025fbf  mov     r9d, dword ptr [rsp+1C0h+var_158]
0x140025fc4  add     rax, r14
0x140025fc7  mov     rdi, [rbp+0C0h+var_110]
0x140025fcb  mov     [rbp+0C0h+var_40], rax
0x140025fd2  lea     eax, [r9+4]
0x140025fd6  add     eax, edx
0x140025fd8  mov     [rbp+0C0h+var_140], eax
0x140025fdb  nop     dword ptr [rax+rax+00h]
0x140025fe0  mov     eax, dword ptr [rsp+1C0h+SizeOfElements]
0x140025fe4  imul    eax, esi
0x140025fe7  mov     ecx, eax
0x140025fe9  mov     [rbp+0C0h+var_128], rcx
0x140025fed  add     rcx, 4
0x140025ff1  add     rcx, r14; void *
0x140025ff4  mov     [rax+r14], edx
0x140025ff8  imul    edx, esi
0x140025ffb  add     rdx, [rbp+0C0h+var_118]; Src
0x140025fff  call    memmove
0x140026004  mov     r8d, dword ptr [rsp+1C0h+var_158]; Size
0x140026009  mov     edx, esi
0x14002600b  mov     rcx, [rbp+0C0h+var_40]
0x140026012  add     rcx, [rbp+0C0h+var_128]; void *
0x140026016  imul    edx, r8d
0x14002601a  add     rdx, [rbp+0C0h+var_130]; Src
0x14002601e  call    memmove
0x140026023  mov     ecx, [rbp+0C0h+var_140]
0x140026026  test    rdi, rdi
0x140026029  jz      short loc_140026049
0x14002602b  add     rcx, [rbp+0C0h+var_128]
0x14002602f  mov     edx, esi
0x140026031  imul    edx, r13d
0x140026035  mov     r8, r13; Size
0x140026038  add     rcx, r14; void *
0x14002603b  add     rdx, rdi; Src
0x14002603e  call    memmove
0x140026043  mov     ecx, [rbp+0C0h+var_140]
0x140026046  add     ecx, r13d
0x140026049  test    r12, r12
0x14002604c  jz      short loc_140026067
0x14002604e  mov     edx, [rsp+1C0h+var_148]
0x140026052  add     rcx, [rbp+0C0h+var_128]
0x140026056  mov     r8d, edx; Size
0x140026059  imul    edx, esi
  ... truncated ...
```
