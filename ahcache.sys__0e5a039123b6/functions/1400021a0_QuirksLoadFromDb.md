# QuirksLoadFromDb

- ea: `0x1400021a0`
- end: `0x1400029f7`
- name: `QuirksLoadFromDb`
- size: `2135`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14002a898`

## callees

- `0x1400021a0`
- `0x140002a00`
- `0x140003830`
- `0x140007b40`
- `0x140007e40`
- `0x14003d820`
- `0x14003e364`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140002292`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002292`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x1400023e9`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x1400023e9`
- `ntoskrnl!RtlHashUnicodeString` at `0x1400024eb`
- `ntoskrnl!RtlHashUnicodeString` at `0x1400024eb`
- `ntoskrnl!ExAllocatePool2` at `0x14000223e`
- `ntoskrnl!ExAllocatePool2` at `0x14000223e`

## string_xrefs

- `0x14000265d`: `NewQuirk ComponentId invalid: 0x%x`
- `0x14000295d`: `NewQuirk ComponentId too big: 0x%x`
- `0x14000294b`: `NewComponent QuirksCount invalid: 0x%x`
- `0x140002993`: `NewQuirk ComponentId too small: 0x%x`
- `0x14000296f`: `NewComponent QuirksDataSize or NewComponent QuirksCount invalid: 0x%x`
- `0x1400029c1`: `Total number of quirk components invalid: 0x%x`

## pseudocode

```c
__int64 __fastcall QuirksLoadFromDb(__int64 a1, __int64 a2, unsigned __int16 *a3)
{
  unsigned int FirstTag; // eax
  int v7; // r14d
  size_t v8; // rbx
  void *Pool2; // rax
  void *v10; // rdi
  unsigned int v11; // ebx
  unsigned __int16 *v13; // r12
  unsigned __int16 *v14; // r15
  int v15; // r14d
  USHORT v16; // r10
  int v17; // r9d
  __int128 *v18; // rcx
  __int64 v19; // rdx
  unsigned __int64 v20; // rbx
  _OWORD *v21; // rax
  __int128 v22; // xmm0
  USHORT v23; // ax
  __int64 v24; // rcx
  NTSTATUS inited; // eax
  const char *v26; // r9
  __int64 v27; // r8
  ULONG v28; // eax
  char *v29; // rax
  int v30; // r8d
  int v31; // eax
  unsigned __int16 v32; // r8
  __int64 v33; // rcx
  int *v34; // rdx
  int NextQuirkAndQuirkTagId; // eax
  const char *v36; // r9
  __int64 v37; // r8
  const char *v38; // r9
  __int64 v39; // r8
  unsigned int v40; // eax
  HRESULT v41; // eax
  int v42; // r9d
  unsigned __int16 v43; // dx
  unsigned __int16 *v44; // r8
  __int64 v45; // rcx
  unsigned __int16 *v46; // r14
  _OWORD *v47; // rcx
  __int64 v48; // rdx
  unsigned __int16 *v49; // rax
  __int128 v50; // xmm1
  __int128 v51; // xmm0
  unsigned __int16 *v52; // rcx
  __int64 v53; // rax
  unsigned __int16 *v54; // r11
  __int16 v55; // dx
  unsigned __int16 *v56; // r10
  int v57; // r9d
  __int64 v58; // [rsp+20h] [rbp-79h]
  int v59; // [rsp+60h] [rbp-39h]
  int v60; // [rsp+64h] [rbp-35h]
  USHORT v61; // [rsp+68h] [rbp-31h]
  int v62; // [rsp+6Ch] [rbp-2Dh]
  int v63; // [rsp+70h] [rbp-29h] BYREF
  ULONG HashValue[2]; // [rsp+78h] [rbp-21h] BYREF
  int v65; // [rsp+80h] [rbp-19h] BYREF
  int v66; // [rsp+84h] [rbp-15h]
  __int128 *v67; // [rsp+88h] [rbp-11h] BYREF
  PVOID P; // [rsp+90h] [rbp-9h]
  __int64 v69; // [rsp+98h] [rbp-1h] BYREF
  int *v70; // [rsp+A0h] [rbp+7h]
  struct _UNICODE_STRING DestinationString; // [rsp+A8h] [rbp+Fh] BYREF
  int v72; // [rsp+100h] [rbp+67h]
  USHORT pusResult; // [rsp+110h] [rbp+77h] BYREF
  __int64 v74; // [rsp+118h] [rbp+7Fh] BYREF

  v72 = a1;
  if ( !*a3 )
    return 0;
  FirstTag = SdbFindFirstTag(a1, 0, 28673);
  if ( !FirstTag )
  {
    v38 = "TagDatabase missing from Pdb: 0x%x";
    v39 = 789;
    goto LABEL_47;
  }
  v66 = SdbFindFirstTag(a1, FirstTag, 28674);
  if ( !v66 )
  {
    v38 = "TagLibrary missing from Pdb: 0x%x";
    v39 = 796;
    goto LABEL_47;
  }
  if ( a2 )
  {
    v40 = SdbFindFirstTag(a2, 0, 28673);
    if ( v40 )
    {
      v62 = SdbFindFirstTag(a2, v40, 28674);
      v7 = v62;
      if ( v62 )
        goto LABEL_6;
      v38 = "TagLibrary missing from StubPdb: 0x%x";
      v39 = 811;
    }
    else
    {
      v38 = "TagDatabase missing from StubPdb: 0x%x";
      v39 = 804;
    }
LABEL_47:
    v11 = -1073741596;
    AslLogCallPrintf(1, "QuirksLoadFromDb", v39, v38, -1073741596);
    return v11;
  }
  v7 = 0;
  v62 = 0;
LABEL_6:
  v63 = 0;
  v65 = 0;
  v8 = 1112;
  if ( !a2 )
    v8 = 556;
  Pool2 = (void *)ExAllocatePool2(64, (unsigned int)v8, 1953517633);
  P = Pool2;
  v10 = Pool2;
  if ( !Pool2 )
    return (unsigned int)-1073741801;
  memset(Pool2, 0, v8);
  v33 = (__int64)v10 + 556;
  v69 = 0;
  LODWORD(v74) = 0;
  v67 = 0;
  if ( !a2 )
    v33 = 0;
  v34 = &v65;
  if ( !a2 )
    v34 = 0;
  v70 = v34;
  NextQuirkAndQuirkTagId = QuirksGetNextQuirkAndQuirkTagId(
                             a1,
                             v66,
                             (unsigned int)&v63,
                             (_DWORD)v10,
                             a2,
                             v7,
                             (__int64)v34,
                             v33,
                             (__int64)&v69,
                             (__int64)&v74,
                             (__int64)&v67);
  v32 = 0;
  v11 = NextQuirkAndQuirkTagId;
  if ( NextQuirkAndQuirkTagId < 0 )
  {
    LODWORD(v58) = NextQuirkAndQuirkTagId;
    v36 = "QuirksGetNextQuirkAndQuirkTagId failed: 0x%x";
    v37 = 861;
LABEL_44:
    AslLogCallPrintf(1, "QuirksLoadFromDb", v37, v36, v58);
    goto LABEL_12;
  }
  v13 = a3 + 4;
  v59 = 0;
  v14 = &a3[8 * a3[1] + 4];
  v61 = 0;
  pusResult = 0;
  v60 = 1;
  *((_QWORD *)a3 + 2) = (char *)v14 - (char *)a3;
  v15 = 0;
  v16 = 0;
  v17 = 1;
  while ( 1 )
  {
    if ( !(_DWORD)v74 )
    {
      if ( v17 )
        goto LABEL_37;
      v54 = a3 + 4;
      v55 = 0;
      v56 = &v14[278 * *a3];
      while ( 1 )
      {
        if ( v14 >= v56 )
        {
          if ( v32 + 1 != a3[1] )
          {
            v11 = -1073741596;
            LODWORD(v58) = -1073741596;
            AslLogCallPrintf(1, "QuirksLoadFromDb", 1101, "Total number of quirk components invalid: 0x%x", v58);
            goto LABEL_12;
          }
          AslLogCallPrintf(1, "QuirksLoadFromDb", 1105, "Quirks were out of order - fixed: 0x%x", v11);
LABEL_37:
          v11 = 0;
          goto LABEL_12;
        }
        if ( !*((_DWORD *)v14 + 64) )
        {
          v36 = "NewQuirk QuirkNameHash invalid: 0x%x";
          v37 = 1055;
          goto LABEL_84;
        }
        v57 = v14[139];
        if ( (unsigned __int16)v57 > v32 )
          break;
        if ( (unsigned __int16)v57 < v32 )
        {
          v36 = "NewQuirk ComponentId too small: 0x%x";
          v37 = 1078;
          goto LABEL_84;
        }
        if ( !v55 )
          goto LABEL_95;
LABEL_97:
        if ( v14[138] != v55 )
        {
          v36 = "NewQuirk QuirkId invalid: 0x%x";
          v37 = 1092;
          goto LABEL_84;
        }
        ++v55;
        v14 += 278;
      }
      if ( v57 != v32 + 1 )
      {
        v36 = "NewQuirk ComponentId too big: 0x%x";
        v37 = 1062;
        goto LABEL_84;
      }
      if ( *v54 != v55 )
      {
        v36 = "NewComponent QuirksCount invalid: 0x%x";
        v37 = 1068;
        goto LABEL_84;
      }
      ++v32;
      v55 = 0;
      v54 = &a3[8 * v14[139] + 4];
LABEL_95:
      if ( !*(_DWORD *)(v54 + 1) || !*v54 )
      {
        v36 = "NewComponent QuirksDataSize or NewComponent QuirksCount invalid: 0x%x";
        v37 = 1085;
        goto LABEL_84;
      }
      goto LABEL_97;
    }
    if ( (unsigned __int16)v15 >= *a3 )
    {
      v36 = "QuirksCounter invalid: 0x%x";
      v37 = 883;
      goto LABEL_84;
    }
    v18 = v67;
    v19 = 4;
    *(_QWORD *)HashValue = v67;
    v20 = (unsigned __int64)&v14[278 * (unsigned __int16)v15];
    v21 = (_OWORD *)v20;
    do
    {
      v22 = *v18;
      v18 += 8;
      *v21 = v22;
      v21 += 8;
      *(v21 - 7) = *(v18 - 7);
      *(v21 - 6) = *(v18 - 6);
      *(v21 - 5) = *(v18 - 5);
      *(v21 - 4) = *(v18 - 4);
      *(v21 - 3) = *(v18 - 3);
      *(v21 - 2) = *(v18 - 2);
      *(v21 - 1) = *(v18 - 1);
      --v19;
    }
    while ( v19 );
    *v21 = *v18;
    v21[1] = v18[1];
    *(_OWORD *)((char *)v21 + 28) = *(__int128 *)((char *)v18 + 28);
    v23 = *(_WORD *)(v20 + 278);
    if ( v23 > v16 )
    {
      if ( v23 >= a3[1] )
      {
        v36 = "NewQuirk ComponentId invalid: 0x%x";
        v37 = 899;
LABEL_84:
        v31 = -1073741596;
        v11 = -1073741596;
        goto LABEL_85;
      }
      while ( v16 < *(_WORD *)(v20 + 278) )
      {
        v41 = UShortAdd(v16, 1u, &pusResult);
        if ( v41 < 0 )
        {
          AslLogCallPrintf(1, "QuirksLoadFromDb", 911, "UShortAdd failed: 0x%x", v41);
          goto LABEL_11;
        }
        v16 = pusResult;
        if ( *(_WORD *)(v20 + 278) != pusResult )
          v42 = 0;
        v61 = pusResult;
        v60 = v42;
        v13 = &a3[8 * pusResult + 4];
        *v13 = 0;
        *(_DWORD *)(v13 + 1) = 0;
        v13[3] = *(_WORD *)(v20 + 278);
        *((_QWORD *)v13 + 1) = v20 - (_QWORD)a3;
      }
    }
    else
    {
      v24 = 8LL * *(unsigned __int16 *)(v20 + 278);
      if ( v23 < v16 || *(_WORD *)(v20 + 276) < a3[v24 + 4] )
      {
        v13 = &a3[v24 + 4];
        if ( !*(_DWORD *)(v13 + 1) )
        {
          *v13 = 0;
          *(_DWORD *)(v13 + 1) = 0;
          v13[3] = *(_WORD *)(v20 + 278);
        }
        v43 = 0;
        if ( !(_WORD)v15 )
          goto LABEL_66;
        while ( 1 )
        {
          v44 = &v14[278 * v43];
          if ( (unsigned __int64)v44 >= v20 || *((_DWORD *)v44 + 69) > *(_DWORD *)(v20 + 276) )
            break;
          if ( ++v43 >= (unsigned __int16)v15 )
            goto LABEL_66;
        }
        v45 = 278LL * v43;
        v46 = &v14[v45];
        if ( (unsigned __int64)&v14[v45] >= v20 )
        {
LABEL_66:
          v11 = -1073740768;
          v36 = "Quirk index not found: 0x%x";
          LODWORD(v58) = -1073740768;
          v37 = 956;
          goto LABEL_44;
        }
        memmove(v46 + 278, &v14[v45], v20 - v45 * 2 - (_QWORD)v14);
        v47 = *(_OWORD **)HashValue;
        v48 = 4;
        v20 = (unsigned __int64)v46;
        v49 = v46;
        do
        {
          *(_OWORD *)v49 = *v47;
          *((_OWORD *)v49 + 1) = v47[1];
          *((_OWORD *)v49 + 2) = v47[2];
          *((_OWORD *)v49 + 3) = v47[3];
          *((_OWORD *)v49 + 4) = v47[4];
          *((_OWORD *)v49 + 5) = v47[5];
          *((_OWORD *)v49 + 6) = v47[6];
          v50 = v47[7];
          v47 += 8;
          *((_OWORD *)v49 + 7) = v50;
          v49 += 64;
          --v48;
        }
        while ( v48 );
        *(_OWORD *)v49 = *v47;
        *((_OWORD *)v49 + 1) = v47[1];
        v51 = *(_OWORD *)((char *)v47 + 28);
        v52 = v13 + 8;
        *(_OWORD *)(v49 + 14) = v51;
        while ( v52 <= &a3[8 * v61 + 4] )
        {
          v53 = *((_QWORD *)v52 + 1);
          if ( v53 )
            *((_QWORD *)v52 + 1) = v53 + 556;
          v52 += 8;
        }
        v15 = v59;
      }
      else
      {
        v13 = &a3[8 * v16 + 4];
      }
    }
    HashValue[0] = 0;
    DestinationString = 0;
    inited = RtlInitUnicodeStringEx(&DestinationString, (PCWSTR)v20);
    if ( inited < 0 )
    {
      v26 = "RtlInitUnicodeStringEx failed: 0x%x";
      v27 = 90;
LABEL_25:
      LODWORD(v58) = inited;
      AslLogCallPrintf(1, "QuirksGetNameHash", v27, v26, v58);
      v28 = 0;
      goto LABEL_26;
    }
    inited = RtlHashUnicodeString(&DestinationString, 1u, 0, HashValue);
    if ( inited < 0 )
    {
      v26 = "RtlHashUnicodeString failed: 0x%x";
      v27 = 99;
      goto LABEL_25;
    }
    v28 = HashValue[0];
LABEL_26:
    *(_DWORD *)(v20 + 256) = v28;
    if ( !v28 )
    {
      v36 = "QuirkNameHash invalid: 0x%x";
      v37 = 993;
      goto LABEL_84;
    }
    LOWORD(v15) = v15 + 1;
    if ( (unsigned __int16)v15 < (unsigned __int16)v59 )
      break;
    ++*v13;
    v29 = 0;
    *(_DWORD *)(v13 + 1) += 556;
    v30 = v60;
    if ( *(unsigned __int16 *)(v20 + 276) != *v13 - 1 )
      v30 = 0;
    v60 = v30;
    if ( a2 )
      v29 = (char *)P + 556;
    v31 = QuirksGetNextQuirkAndQuirkTagId(
            v72,
            v66,
            (unsigned int)&v63,
            (_DWORD)P,
            a2,
            v62,
            (__int64)v70,
            (__int64)v29,
            (__int64)&v69,
            (__int64)&v74,
            (__int64)&v67);
    v32 = 0;
    v11 = v31;
    if ( v31 < 0 )
    {
      if ( v31 != -2147483622 )
      {
        v36 = "QuirksGetNextQuirkAndQuirkTagId failed: 0x%x";
        v37 = 1036;
LABEL_85:
        LODWORD(v58) = v31;
        goto LABEL_44;
      }
      v11 = 0;
      LODWORD(v74) = 0;
    }
    v16 = v61;
    v17 = v60;
    v59 = v15;
  }
  AslLogCallPrintf(1, "QuirksLoadFromDb", 999, "UShortAdd failed: 0x%x", -2147024362);
LABEL_11:
  v11 = -1073741823;
LABEL_12:
  ExFreePoolWithTag(P, 0x74705041u);
  return v11;
}

```

## disassembly

```asm
0x1400021a0  mov     [rsp-8+arg_8], rbx
0x1400021a5  mov     [rsp-8+arg_0], rcx
0x1400021aa  push    rbp
0x1400021ab  push    rsi
0x1400021ac  push    rdi
0x1400021ad  push    r12
0x1400021af  push    r13
0x1400021b1  push    r14
0x1400021b3  push    r15
0x1400021b5  lea     rbp, [rsp-27h]
0x1400021ba  sub     rsp, 0C0h
0x1400021c1  xor     edi, edi
0x1400021c3  mov     rsi, r8
0x1400021c6  mov     r13, rdx
0x1400021c9  mov     r15, rcx
0x1400021cc  cmp     [r8], di
0x1400021d0  jz      loc_1400025C7
0x1400021d6  mov     ebx, 7001h
0x1400021db  xor     edx, edx
0x1400021dd  mov     r8d, ebx
0x1400021e0  call    SdbFindFirstTag
0x1400021e5  test    eax, eax
0x1400021e7  jz      loc_1400025CE
0x1400021ed  lea     r14d, [rbx+1]
0x1400021f1  mov     edx, eax
0x1400021f3  mov     r8d, r14d
0x1400021f6  mov     rcx, r15
0x1400021f9  call    SdbFindFirstTag
0x1400021fe  mov     [rbp+57h+var_6C], eax
0x140002201  mov     r12d, eax
0x140002204  test    eax, eax
0x140002206  jz      loc_14000260B
0x14000220c  test    r13, r13
0x14000220f  jnz     loc_14000261A
0x140002215  mov     r14d, edi
0x140002218  mov     [rbp+57h+var_84], edi
0x14000221b  mov     eax, 22Ch
0x140002220  mov     [rbp+57h+var_80], edi
0x140002223  test    r13, r13
0x140002226  mov     [rbp+57h+var_70], edi
0x140002229  mov     ebx, 458h
0x14000222e  mov     r8d, 74705041h
0x140002234  cmovz   ebx, eax
0x140002237  mov     ecx, 40h ; '@'
0x14000223c  mov     edx, ebx
0x14000223e  call    cs:__imp_ExAllocatePool2
0x140002245  nop     dword ptr [rax+rax+00h]
0x14000224a  mov     [rbp+57h+P], rax
0x14000224e  mov     rdi, rax
0x140002251  test    rax, rax
0x140002254  jnz     loc_140002518
0x14000225a  mov     ebx, 0C0000017h
0x14000225f  jmp     short loc_14000229E
0x140002261  mov     dword ptr [rsp+0F0h+var_D0], 80070216h
0x140002269  mov     r8d, 3E7h
0x14000226f  lea     r9, aUshortaddFaile; "UShortAdd failed: 0x%x"
0x140002276  mov     ecx, edi
0x140002278  lea     rdx, aQuirksloadfrom; "QuirksLoadFromDb"
0x14000227f  call    AslLogCallPrintf
0x140002284  mov     ebx, 0C0000001h
0x140002289  mov     rcx, [rbp+57h+P]; P
0x14000228d  mov     edx, 74705041h; Tag
0x140002292  call    cs:__imp_ExFreePoolWithTag
0x140002299  nop     dword ptr [rax+rax+00h]
0x14000229e  mov     eax, ebx
0x1400022a0  mov     rbx, [rsp+0F0h+arg_8]
0x1400022a8  add     rsp, 0C0h
0x1400022af  pop     r15
0x1400022b1  pop     r14
0x1400022b3  pop     r13
0x1400022b5  pop     r12
0x1400022b7  pop     rdi
0x1400022b8  pop     rsi
0x1400022b9  pop     rbp
0x1400022ba  retn
0x1400022bc  movzx   r15d, word ptr [rsi+2]
0x1400022c1  lea     r12, [rsi+8]
0x1400022c5  shl     r15, 4
0x1400022c9  mov     edi, 1
0x1400022ce  add     r15, 8
0x1400022d2  mov     [rbp+57h+var_90], r8d
0x1400022d6  add     r15, rsi
0x1400022d9  mov     [rbp+57h+var_88], r8d
0x1400022dd  mov     rax, r15
0x1400022e0  mov     [rbp+57h+pusResult], r8w
0x1400022e5  sub     rax, rsi
0x1400022e8  mov     [rbp+57h+var_8C], edi
0x1400022eb  mov     [rsi+10h], rax
0x1400022ef  mov     r14d, r8d
0x1400022f2  mov     r10d, r8d
0x1400022f5  mov     r9d, edi
0x1400022f8  cmp     dword ptr [rbp+57h+arg_18], r8d
0x1400022fc  jz      loc_140002507
0x140002302  cmp     r14w, [rsi]
0x140002306  jnb     loc_140002895
0x14000230c  mov     rcx, [rbp+57h+var_68]
0x140002310  mov     edx, 4
0x140002315  movzx   eax, r14w
0x140002319  imul    rbx, rax, 22Ch
0x140002320  mov     qword ptr [rbp+57h+HashValue], rcx
0x140002324  add     rbx, r15
0x140002327  mov     rax, rbx
0x14000232a  movups  xmm0, xmmword ptr [rcx]
0x14000232d  lea     rcx, [rcx+80h]
0x140002334  movups  xmmword ptr [rax], xmm0
0x140002337  lea     rax, [rax+80h]
0x14000233e  movups  xmm1, xmmword ptr [rcx-70h]
0x140002342  movups  xmmword ptr [rax-70h], xmm1
0x140002346  movups  xmm0, xmmword ptr [rcx-60h]
0x14000234a  movups  xmmword ptr [rax-60h], xmm0
0x14000234e  movups  xmm1, xmmword ptr [rcx-50h]
0x140002352  movups  xmmword ptr [rax-50h], xmm1
0x140002356  movups  xmm0, xmmword ptr [rcx-40h]
0x14000235a  movups  xmmword ptr [rax-40h], xmm0
0x14000235e  movups  xmm1, xmmword ptr [rcx-30h]
0x140002362  movups  xmmword ptr [rax-30h], xmm1
0x140002366  movups  xmm0, xmmword ptr [rcx-20h]
0x14000236a  movups  xmmword ptr [rax-20h], xmm0
0x14000236e  movups  xmm1, xmmword ptr [rcx-10h]
0x140002372  movups  xmmword ptr [rax-10h], xmm1
0x140002376  sub     rdx, rdi
0x140002379  jnz     short loc_14000232A
0x14000237b  movups  xmm0, xmmword ptr [rcx]
0x14000237e  movups  xmmword ptr [rax], xmm0
0x140002381  movups  xmm1, xmmword ptr [rcx+10h]
0x140002385  movups  xmmword ptr [rax+10h], xmm1
0x140002389  movups  xmm0, xmmword ptr [rcx+1Ch]
0x14000238d  movups  xmmword ptr [rax+1Ch], xmm0
0x140002391  movzx   eax, word ptr [rbx+116h]
0x140002398  cmp     ax, r10w
0x14000239c  ja      loc_140002657
0x1400023a2  mov     ecx, eax
0x1400023a4  lea     r9, [rbx+114h]
0x1400023ab  shl     rcx, 4
0x1400023af  cmp     ax, r10w
0x1400023b3  jb      loc_1400026E3
0x1400023b9  movzx   eax, word ptr [rcx+rsi+8]
0x1400023be  cmp     [r9], ax
0x1400023c2  jb      loc_1400026E3
0x1400023c8  movzx   r12d, r10w
0x1400023cc  shl     r12, 4
0x1400023d0  add     r12, 8
0x1400023d4  add     r12, rsi
0x1400023d7  xorps   xmm0, xmm0
0x1400023da  mov     [rbp+57h+HashValue], r8d
0x1400023de  mov     rdx, rbx; SourceString
0x1400023e1  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400023e5  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1400023e9  call    cs:__imp_RtlInitUnicodeStringEx
0x1400023f0  nop     dword ptr [rax+rax+00h]
0x1400023f5  test    eax, eax
0x1400023f7  jns     loc_1400024DD
0x1400023fd  lea     r9, aRtlinitunicode; "RtlInitUnicodeStringEx failed: 0x%x"
0x140002404  mov     r8d, 5Ah ; 'Z'
0x14000240a  lea     rdx, aQuirksgetnameh; "QuirksGetNameHash"
0x140002411  mov     dword ptr [rsp+0F0h+var_D0], eax
0x140002415  mov     ecx, edi
0x140002417  call    AslLogCallPrintf
0x14000241c  xor     eax, eax
0x14000241e  mov     [rbx+100h], eax
0x140002424  test    eax, eax
0x140002426  jz      loc_140002886
0x14000242c  add     r14w, di
0x140002430  cmp     r14w, word ptr [rbp+57h+var_90]
0x140002435  jb      loc_140002261
0x14000243b  add     [r12], di
0x140002440  xor     eax, eax
0x140002442  add     dword ptr [r12+2], 22Ch
0x14000244b  mov     r8d, [rbp+57h+var_8C]
0x14000244f  movzx   edx, word ptr [r12]
0x140002454  movzx   ecx, word ptr [rbx+114h]
0x14000245b  sub     edx, edi
0x14000245d  cmp     ecx, edx
0x14000245f  cmovnz  r8d, eax
0x140002463  mov     [rbp+57h+var_8C], r8d
0x140002467  test    r13, r13
0x14000246a  jz      short loc_140002476
0x14000246c  mov     rax, [rbp+57h+P]
0x140002470  add     rax, 22Ch
0x140002476  mov     r9, [rbp+57h+P]
0x14000247a  lea     rcx, [rbp+57h+var_68]
0x14000247e  mov     edx, [rbp+57h+var_6C]
0x140002481  lea     r8, [rbp+57h+var_80]
0x140002485  mov     [rsp+0F0h+var_A0], rcx
0x14000248a  lea     rcx, [rbp+57h+arg_18]
0x14000248e  mov     [rsp+0F0h+var_A8], rcx
0x140002493  lea     rcx, [rbp+57h+var_58]
0x140002497  mov     [rsp+0F0h+var_B0], rcx
0x14000249c  mov     rcx, [rbp+57h+arg_0]
0x1400024a0  mov     [rsp+0F0h+var_B8], rax
0x1400024a5  mov     rax, [rbp+57h+var_50]
0x1400024a9  mov     [rsp+0F0h+var_C0], rax
0x1400024ae  mov     eax, [rbp+57h+var_84]
0x1400024b1  mov     [rsp+0F0h+var_C8], eax
0x1400024b5  mov     [rsp+0F0h+var_D0], r13
0x1400024ba  call    QuirksGetNextQuirkAndQuirkTagId
0x1400024bf  xor     r8d, r8d
0x1400024c2  mov     ebx, eax
0x1400024c4  test    eax, eax
0x1400024c6  js      loc_140002855
0x1400024cc  mov     r10d, [rbp+57h+var_88]
0x1400024d0  mov     r9d, [rbp+57h+var_8C]
0x1400024d4  mov     [rbp+57h+var_90], r14d
0x1400024d8  jmp     loc_1400022F8
0x1400024dd  lea     r9, [rbp+57h+HashValue]; HashValue
0x1400024e1  xor     r8d, r8d; HashAlgorithm
0x1400024e4  mov     dl, dil; CaseInSensitive
0x1400024e7  lea     rcx, [rbp+57h+DestinationString]; String
0x1400024eb  call    cs:__imp_RtlHashUnicodeString
0x1400024f2  nop     dword ptr [rax+rax+00h]
0x1400024f7  test    eax, eax
0x1400024f9  js      loc_140002843
0x1400024ff  mov     eax, [rbp+57h+HashValue]
0x140002502  jmp     loc_14000241E
0x140002507  test    r9d, r9d
0x14000250a  jz      loc_1400028C3
0x140002510  mov     ebx, r8d
0x140002513  jmp     loc_140002289
0x140002518  mov     r8, rbx; Size
0x14000251b  xor     edx, edx; Val
0x14000251d  mov     rcx, rdi; void *
0x140002520  call    memset
0x140002525  xor     r8d, r8d
0x140002528  lea     rcx, [rdi+22Ch]
0x14000252f  mov     [rbp+57h+var_58], r8
0x140002533  mov     dword ptr [rbp+57h+arg_18], r8d
0x140002537  mov     [rbp+57h+var_68], r8
0x14000253b  test    r13, r13
0x14000253e  jnz     short loc_140002543
0x140002540  mov     ecx, r8d
0x140002543  lea     rax, [rbp+57h+var_68]
0x140002547  test    r13, r13
0x14000254a  mov     [rsp+0F0h+var_A0], rax
0x14000254f  lea     rdx, [rbp+57h+var_70]
0x140002553  cmovz   rdx, r8
0x140002557  lea     rax, [rbp+57h+arg_18]
0x14000255b  mov     [rsp+0F0h+var_A8], rax
0x140002560  lea     r8, [rbp+57h+var_80]
0x140002564  lea     rax, [rbp+57h+var_58]
0x140002568  mov     [rbp+57h+var_50], rdx
0x14000256c  mov     [rsp+0F0h+var_B0], rax
0x140002571  mov     r9, rdi
0x140002574  mov     [rsp+0F0h+var_B8], rcx
0x140002579  mov     rcx, r15
0x14000257c  mov     [rsp+0F0h+var_C0], rdx
0x140002581  mov     edx, r12d
0x140002584  mov     [rsp+0F0h+var_C8], r14d
0x140002589  mov     [rsp+0F0h+var_D0], r13
0x14000258e  call    QuirksGetNextQuirkAndQuirkTagId
0x140002593  xor     r8d, r8d
0x140002596  mov     ebx, eax
0x140002598  test    eax, eax
0x14000259a  jns     loc_1400022BC
0x1400025a0  mov     dword ptr [rsp+0F0h+var_D0], eax
0x1400025a4  lea     r9, aQuirksgetnextq_0; "QuirksGetNextQuirkAndQuirkTagId failed:"...
0x1400025ab  mov     r8d, 35Dh
0x1400025b1  mov     ecx, 1
0x1400025b6  lea     rdx, aQuirksloadfrom; "QuirksLoadFromDb"
0x1400025bd  call    AslLogCallPrintf
0x1400025c2  jmp     loc_140002289
0x1400025c7  mov     ebx, edi
0x1400025c9  jmp     loc_14000229E
0x1400025ce  lea     r9, aTagdatabaseMis; "TagDatabase missing from Pdb: 0x%x"
0x1400025d5  mov     r8d, 315h
0x1400025db  jmp     short loc_1400025EA
0x1400025dd  lea     r9, aTaglibraryMiss_0; "TagLibrary missing from StubPdb: 0x%x"
0x1400025e4  mov     r8d, 32Bh
0x1400025ea  mov     eax, 0C00000E4h
0x1400025ef  lea     rdx, aQuirksloadfrom; "QuirksLoadFromDb"
0x1400025f6  mov     ecx, 1
0x1400025fb  mov     dword ptr [rsp+0F0h+var_D0], eax
0x1400025ff  mov     ebx, eax
0x140002601  call    AslLogCallPrintf
0x140002606  jmp     loc_14000229E
0x14000260b  lea     r9, aTaglibraryMiss; "TagLibrary missing from Pdb: 0x%x"
0x140002612  mov     r8d, 31Ch
0x140002618  jmp     short loc_1400025EA
0x14000261a  mov     r8d, ebx
0x14000261d  xor     edx, edx
0x14000261f  mov     rcx, r13
0x140002622  call    SdbFindFirstTag
0x140002627  test    eax, eax
0x140002629  jnz     short loc_14000263A
0x14000262b  lea     r9, aTagdatabaseMis_1; "TagDatabase missing from StubPdb: 0x%x"
0x140002632  mov     r8d, 324h
0x140002638  jmp     short loc_1400025EA
0x14000263a  mov     r8d, r14d
0x14000263d  mov     edx, eax
0x14000263f  mov     rcx, r13
0x140002642  call    SdbFindFirstTag
0x140002647  mov     [rbp+57h+var_84], eax
0x14000264a  mov     r14d, eax
0x14000264d  test    eax, eax
0x14000264f  jnz     loc_14000221B
0x140002655  jmp     short loc_1400025DD
0x140002657  cmp     ax, [rsi+2]
0x14000265b  jb      short loc_14000266F
0x14000265d  lea     r9, aNewquirkCompon; "NewQuirk ComponentId invalid: 0x%x"
0x140002664  mov     r8d, 383h
0x14000266a  jmp     loc_1400028B1
  ... truncated ...
```
