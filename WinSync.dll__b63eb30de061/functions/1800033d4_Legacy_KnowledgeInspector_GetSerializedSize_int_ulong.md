# Legacy::KnowledgeInspector::GetSerializedSize(int,ulong &)

- ea: `0x1800033d4`
- end: `0x18000382a`
- name: `?GetSerializedSize@KnowledgeInspector@Legacy@@AEAAJHAEAK@Z`
- size: `1110`
- prototype: `__int64 __fastcall(Legacy::KnowledgeInspector *__hidden this, int, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180003254`

## callees

- `0x1800028e0`
- `0x1800033d4`
- `0x1800084ec`
- `0x18000f810`
- `0x18001a038`
- `0x18001ae20`
- `0x180094010`

## string_xrefs

- `0x18000377b`: `Legacy::KnowledgeInspector::GetSerializedItemOverrideSize`
- `0x1800037d2`: `Legacy::KnowledgeInspector::GetSerializedItemOverrideSize`

## pseudocode

```c
__int64 __fastcall Legacy::KnowledgeInspector::GetSerializedSize(
        Legacy::KnowledgeInspector *this,
        int a2,
        unsigned int *a3)
{
  Legacy::KnowledgeInspector *v4; // r14
  int v5; // edi
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  int v9; // ecx
  __int64 i; // rsi
  __int64 v11; // rax
  __int64 v12; // rbx
  unsigned __int16 *v13; // rcx
  int v14; // eax
  int v15; // eax
  unsigned __int16 *v16; // rcx
  int v17; // edx
  int v18; // eax
  int v19; // eax
  __int64 v20; // r8
  int v21; // r9d
  int v22; // edx
  int v23; // eax
  int v24; // esi
  unsigned int v25; // r10d
  __int64 v26; // rdx
  __int64 v27; // rcx
  int v28; // r8d
  int v29; // r9d
  unsigned int v30; // esi
  __int64 v31; // r15
  unsigned int v32; // r13d
  unsigned int v33; // eax
  __int64 v34; // rcx
  __int64 v35; // rdi
  volatile signed __int32 *v36; // rbx
  int v37; // r12d
  unsigned __int16 v38; // ax
  int v39; // r14d
  PVOID *v41; // r11
  volatile signed __int32 *v42; // rcx
  SyncId *NextElement; // rax
  _QWORD v44[3]; // [rsp+30h] [rbp-18h] BYREF
  int v46; // [rsp+98h] [rbp+50h] BYREF
  unsigned int *v47; // [rsp+A0h] [rbp+58h]

  v47 = a3;
  v4 = this;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      24,
      WPP_48b71e9a06de38317ed143d1f750f029_Traceguids,
      "Legacy::KnowledgeInspector::GetSerializedSize");
  }
  v46 = 0;
  v5 = 8;
  if ( !a2 )
    goto LABEL_6;
  v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, int *))(**(_QWORD **)(*(_QWORD *)v4 + 272LL) + 40LL))(
         *(_QWORD *)(*(_QWORD *)v4 + 272LL),
         0,
         &v46);
  v7 = v6;
  if ( v6 == -2147024662 )
  {
    v5 = v46 + 8;
LABEL_6:
    v8 = *((_QWORD *)v4 + 1);
    v46 = 8;
    v9 = 12 * *(_DWORD *)(v8 + 28) + 8;
    v46 = v9;
    if ( (*(_BYTE *)(v8 + 36) & 2) != 0 )
    {
      v46 = v9 + 5;
      v9 += 5 + 8 * *(_DWORD *)(v8 + 28) + *(_DWORD *)(v8 + 28);
      v46 = v9;
    }
    v5 += v9 + 4 * *((_DWORD *)v4 + 56) + 14;
    for ( i = 0; ; i = (unsigned int)(i + 1) )
    {
      v7 = 0;
      if ( (unsigned int)i >= *((_DWORD *)v4 + 56) )
        break;
      v11 = *((_QWORD *)v4 + 30);
      v12 = *(_QWORD *)(v11 + 8 * i);
      if ( v12 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v12 + 8LL))(*(_QWORD *)(v11 + 8 * i));
      v13 = (unsigned __int16 *)(v12 + 52);
      v14 = *(_DWORD *)(v12 + 52);
      if ( (v14 & 0x10000) != 0 )
      {
        v13 = *(unsigned __int16 **)(v12 + 56);
        if ( (v14 & 0x20000) == 0 )
          v13 += 2;
      }
      v15 = *v13;
      v16 = (unsigned __int16 *)(v12 + 68);
      v46 = v15;
      v17 = v15 + v5;
      v18 = *(_DWORD *)(v12 + 68);
      if ( (v18 & 0x10000) != 0 )
      {
        v16 = *(unsigned __int16 **)(v12 + 72);
        if ( (v18 & 0x20000) == 0 )
          v16 += 2;
      }
      v19 = *v16;
      v46 = v19;
      v20 = *(_QWORD *)(v12 + 80);
      v46 = 8;
      v21 = v19 + v17;
      v22 = 12 * *(_DWORD *)(v20 + 28);
      v23 = v22 + 8;
      v46 = v22 + 8;
      if ( (*(_BYTE *)(v20 + 36) & 2) != 0 )
      {
        v46 = v22 + 13;
        v23 = *(_DWORD *)(v20 + 28) + v22 + 13 + 8 * *(_DWORD *)(v20 + 28);
        v46 = v23;
      }
      v5 = v23 + v21;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
    goto LABEL_23;
  }
  if ( v6 >= 0 )
    v7 = -2147217407;
LABEL_23:
  v24 = v5 + 12;
  if ( v7 )
  {
    v41 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    v25 = *((_DWORD *)v4 + 68);
    if ( v25 )
    {
      v26 = 0;
      do
      {
        v27 = *(_QWORD *)(*((_QWORD *)v4 + 36) + 8 * v26);
        v28 = *(_DWORD *)(v27 + 28);
        v29 = 12 * v28 + 8;
        if ( (*(_BYTE *)(v27 + 36) & 2) != 0 )
          v29 += v28 + 8 * v28 + 5;
        v7 = 0;
        v24 += v29;
        v26 = (unsigned int)(v26 + 1);
      }
      while ( (unsigned int)v26 < v25 );
    }
    v41 = (PVOID *)WPP_GLOBAL_Control;
    v30 = v24 + 4;
    v31 = 0;
    v32 = 0;
LABEL_31:
    v33 = *((_DWORD *)v4 + 88);
    if ( v33 && v32 < v33 )
    {
      while ( (unsigned int)v31 < *((_DWORD *)v4 + 84) )
      {
        v34 = 5 * v31;
        v31 = (unsigned int)(v31 + 1);
        v35 = *((_QWORD *)v4 + 43) + 8 * v34;
        if ( (*(_BYTE *)(v35 + 32) & 1) != 0 )
        {
          if ( !v35 )
            break;
          v36 = *(volatile signed __int32 **)(v35 + 8);
          ++v32;
          v37 = *(_DWORD *)(v35 + 4);
          if ( v36 )
          {
            _InterlockedIncrement(v36);
            v41 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v41 != &WPP_GLOBAL_Control && (*((_BYTE *)v41 + 28) & 0x40) != 0 && *((_BYTE *)v41 + 25) >= 5u )
          {
            WPP_SF_s(
              v41[2],
              32,
              WPP_48b71e9a06de38317ed143d1f750f029_Traceguids,
              "Legacy::KnowledgeInspector::GetSerializedItemOverrideSize");
            v41 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( (v37 & 0x10000) != 0 )
          {
            v42 = v36;
            if ( (v37 & 0x20000) == 0 )
              v42 = v36 + 1;
            v38 = *(_WORD *)v42;
          }
          else
          {
            v38 = v37;
          }
          v39 = v38 + 8;
          if ( *(_QWORD *)(v35 + 24) )
          {
            v44[0] = *(_QWORD *)(v35 + 24);
            v44[1] = 0;
            while ( 1 )
            {
              NextElement = (SyncId *)TableEnumerator<SyncId,int,DefaultHashTableContext>::GetNextElement(v44);
              if ( !NextElement )
                break;
              v39 += SyncId::GetSize(NextElement) + 4;
            }
          }
          v46 = v39;
          if ( v41 != &WPP_GLOBAL_Control && (*((_BYTE *)v41 + 28) & 0x40) != 0 && *((_BYTE *)v41 + 25) >= 5u )
          {
            WPP_SF_sD(
              (unsigned int)v41[2],
              33,
              (unsigned int)WPP_48b71e9a06de38317ed143d1f750f029_Traceguids,
              (unsigned int)"Legacy::KnowledgeInspector::GetSerializedItemOverrideSize",
              0);
            v41 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( (v37 & 0x20000) == 0 && v36 )
          {
            if ( _InterlockedExchangeAdd(v36, 0xFFFFFFFF) == 1 )
              SeFree((void *)v36);
            v41 = (PVOID *)WPP_GLOBAL_Control;
          }
          v4 = this;
          v7 = 0;
          v30 += v46;
          goto LABEL_31;
        }
      }
    }
    *v47 = v30;
  }
  if ( v41 != &WPP_GLOBAL_Control && (*((_BYTE *)v41 + 28) & 0x40) != 0 && *((_BYTE *)v41 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v41[2],
      25,
      (unsigned int)WPP_48b71e9a06de38317ed143d1f750f029_Traceguids,
      (unsigned int)"Legacy::KnowledgeInspector::GetSerializedSize",
      v7);
  return v7;
}

```

## disassembly

```asm
0x1800033d4  mov     [rsp-40h+arg_10], r8
0x1800033d9  mov     [rsp-40h+arg_0], rcx
0x1800033de  push    rbp
0x1800033df  push    rbx
0x1800033e0  push    rsi
0x1800033e1  push    rdi
0x1800033e2  push    r12
0x1800033e4  push    r13
0x1800033e6  push    r14
0x1800033e8  push    r15
0x1800033ea  mov     rbp, rsp
0x1800033ed  sub     rsp, 48h
0x1800033f1  mov     ebx, edx
0x1800033f3  mov     r14, rcx
0x1800033f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800033fd  lea     r12, WPP_GLOBAL_Control
0x180003404  cmp     rcx, r12
0x180003407  jz      short loc_180003413
0x180003409  test    byte ptr [rcx+1Ch], 40h
0x18000340d  jnz     loc_1800036EF
0x180003413  mov     [rbp+arg_8], 0
0x18000341a  mov     r13d, 8
0x180003420  mov     edi, r13d
0x180003423  mov     r15b, 2
0x180003426  test    ebx, ebx
0x180003428  jz      short loc_180003459
0x18000342a  mov     rax, [r14]
0x18000342d  lea     r8, [rbp+arg_8]
0x180003431  xor     edx, edx
0x180003433  mov     rcx, [rax+110h]
0x18000343a  mov     rax, [rcx]
0x18000343d  mov     rax, [rax+28h]
0x180003441  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003446  mov     ebx, eax
0x180003448  cmp     eax, 800700EAh
0x18000344d  jnz     loc_18000371A
0x180003453  mov     edi, [rbp+arg_8]
0x180003456  add     edi, r13d
0x180003459  mov     rdx, [r14+8]
0x18000345d  mov     [rbp+arg_8], r13d
0x180003461  mov     eax, [rdx+1Ch]
0x180003464  lea     ecx, [rax+rax*2]
0x180003467  lea     ecx, ds:8[rcx*4]
0x18000346e  mov     [rbp+arg_8], ecx
0x180003471  test    [rdx+24h], r15b
0x180003475  jnz     loc_18000372C
0x18000347b  mov     eax, [r14+0E0h]
0x180003482  add     edi, 0Eh
0x180003485  lea     ecx, [rcx+rax*4]
0x180003488  add     edi, ecx
0x18000348a  xor     esi, esi
0x18000348c  xor     ebx, ebx
0x18000348e  cmp     esi, [r14+0E0h]
0x180003495  jnb     loc_180003549
0x18000349b  mov     rax, [r14+0F0h]
0x1800034a2  mov     rbx, [rax+rsi*8]
0x1800034a6  test    rbx, rbx
0x1800034a9  jz      short loc_1800034BA
0x1800034ab  mov     rax, [rbx]
0x1800034ae  mov     rcx, rbx
0x1800034b1  mov     rax, [rax+8]
0x1800034b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034ba  lea     rcx, [rbx+34h]
0x1800034be  mov     eax, [rcx]
0x1800034c0  bt      eax, 10h
0x1800034c4  jb      short loc_180003525
0x1800034c6  movzx   eax, word ptr [rcx]
0x1800034c9  lea     rcx, [rbx+44h]
0x1800034cd  mov     [rbp+arg_8], eax
0x1800034d0  lea     edx, [rax+rdi]
0x1800034d3  mov     eax, [rcx]
0x1800034d5  bt      eax, 10h
0x1800034d9  jb      short loc_180003537
0x1800034db  movzx   eax, word ptr [rcx]
0x1800034de  mov     [rbp+arg_8], eax
0x1800034e1  mov     r8, [rbx+50h]
0x1800034e5  mov     [rbp+arg_8], r13d
0x1800034e9  lea     r9d, [rax+rdx]
0x1800034ed  mov     eax, [r8+1Ch]
0x1800034f1  lea     ecx, [rax+rax*2]
0x1800034f4  lea     edx, ds:0[rcx*4]
0x1800034fb  lea     eax, [rdx+8]
0x1800034fe  mov     [rbp+arg_8], eax
0x180003501  test    [r8+24h], r15b
0x180003505  jnz     loc_180003742
0x18000350b  lea     edi, [rax+r9]
0x18000350f  mov     rcx, rbx
0x180003512  mov     rax, [rbx]
0x180003515  mov     rax, [rax+10h]
0x180003519  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000351e  inc     esi
0x180003520  jmp     loc_18000348C
0x180003525  mov     rcx, [rbx+38h]
0x180003529  bt      eax, 11h
0x18000352d  lea     rax, [rcx+4]
0x180003531  cmovnb  rcx, rax
0x180003535  jmp     short loc_1800034C6
0x180003537  mov     rcx, [rbx+48h]
0x18000353b  bt      eax, 11h
0x18000353f  lea     rax, [rcx+4]
0x180003543  cmovnb  rcx, rax
0x180003547  jmp     short loc_1800034DB
0x180003549  test    ebx, ebx
0x18000354b  lea     esi, [rdi+0Ch]
0x18000354e  cmovnz  esi, edi
0x180003551  jnz     loc_1800036CE
0x180003557  mov     r10d, [r14+110h]
0x18000355e  test    r10d, r10d
0x180003561  jz      short loc_180003596
0x180003563  mov     r11, [r14+120h]
0x18000356a  xor     edx, edx
0x18000356c  mov     rcx, [r11+rdx*8]
0x180003570  mov     r8d, [rcx+1Ch]
0x180003574  lea     eax, [r8+r8*2]
0x180003578  lea     r9d, ds:8[rax*4]
0x180003580  test    [rcx+24h], r15b
0x180003584  jnz     loc_18000375C
0x18000358a  xor     ebx, ebx
0x18000358c  add     esi, r9d
0x18000358f  inc     edx
0x180003591  cmp     edx, r10d
0x180003594  jb      short loc_18000356C
0x180003596  mov     r11, cs:WPP_GLOBAL_Control
0x18000359d  add     esi, 4
0x1800035a0  xor     r15d, r15d
0x1800035a3  xor     r13d, r13d
0x1800035a6  mov     eax, [r14+160h]
0x1800035ad  test    eax, eax
0x1800035af  jz      loc_180003694
0x1800035b5  cmp     r13d, eax
0x1800035b8  jnb     loc_180003694
0x1800035be  cmp     r15d, [r14+150h]
0x1800035c5  jnb     loc_180003694
0x1800035cb  mov     rax, [r14+158h]
0x1800035d2  lea     rcx, [r15+r15*4]
0x1800035d6  inc     r15d
0x1800035d9  lea     rdi, [rax+rcx*8]
0x1800035dd  test    byte ptr [rdi+20h], 1
0x1800035e1  jz      short loc_1800035BE
0x1800035e3  test    rdi, rdi
0x1800035e6  jz      loc_180003694
0x1800035ec  mov     rbx, [rdi+8]
0x1800035f0  inc     r13d
0x1800035f3  mov     r12d, [rdi+4]
0x1800035f7  test    rbx, rbx
0x1800035fa  jz      short loc_180003606
0x1800035fc  lock inc dword ptr [rbx]
0x1800035ff  mov     r11, cs:WPP_GLOBAL_Control
0x180003606  lea     rax, WPP_GLOBAL_Control
0x18000360d  cmp     r11, rax
0x180003610  jz      short loc_18000361D
0x180003612  test    byte ptr [r11+1Ch], 40h
0x180003617  jnz     loc_18000376C
0x18000361d  bt      r12d, 10h
0x180003622  jb      loc_1800036D7
0x180003628  movzx   eax, r12w
0x18000362c  movzx   r14d, ax
0x180003630  mov     rax, [rdi+18h]
0x180003634  add     r14d, 8
0x180003638  xor     edi, edi
0x18000363a  test    rax, rax
0x18000363d  jnz     short loc_180003687
0x18000363f  mov     [rbp+arg_8], r14d
0x180003643  lea     rax, WPP_GLOBAL_Control
0x18000364a  cmp     r11, rax
0x18000364d  jz      short loc_18000365A
0x18000364f  test    byte ptr [r11+1Ch], 40h
0x180003654  jnz     loc_1800037C3
0x18000365a  bt      r12d, 11h
0x18000365f  jb      short loc_180003679
0x180003661  test    rbx, rbx
0x180003664  jz      short loc_180003679
0x180003666  or      eax, 0FFFFFFFFh
0x180003669  lock xadd [rbx], eax
0x18000366d  cmp     eax, 1
0x180003670  jz      short loc_1800036C4
0x180003672  mov     r11, cs:WPP_GLOBAL_Control
0x180003679  mov     r14, [rbp+arg_0]
0x18000367d  xor     ebx, ebx
0x18000367f  add     esi, [rbp+arg_8]
0x180003682  jmp     loc_1800035A6
0x180003687  mov     [rbp+var_18], rax
0x18000368b  mov     [rbp+var_10], rdi
0x18000368f  jmp     loc_1800037B0
0x180003694  mov     rax, [rbp+arg_10]
0x180003698  lea     r12, WPP_GLOBAL_Control
0x18000369f  mov     [rax], esi
0x1800036a1  cmp     r11, r12
0x1800036a4  jz      short loc_1800036B1
0x1800036a6  test    byte ptr [r11+1Ch], 40h
0x1800036ab  jnz     loc_1800037FA
0x1800036b1  mov     eax, ebx
0x1800036b3  add     rsp, 48h
0x1800036b7  pop     r15
0x1800036b9  pop     r14
0x1800036bb  pop     r13
0x1800036bd  pop     r12
0x1800036bf  pop     rdi
0x1800036c0  pop     rsi
0x1800036c1  pop     rbx
0x1800036c2  pop     rbp
0x1800036c3  retn
0x1800036c4  mov     rcx, rbx; void *
0x1800036c7  call    ?SeFree@@YAXPEAX@Z; SeFree(void *)
0x1800036cc  jmp     short loc_180003672
0x1800036ce  mov     r11, cs:WPP_GLOBAL_Control
0x1800036d5  jmp     short loc_1800036A1
0x1800036d7  lea     rax, [rbx+4]
0x1800036db  bt      r12d, 11h
0x1800036e0  mov     rcx, rbx
0x1800036e3  cmovnb  rcx, rax
0x1800036e7  movzx   eax, word ptr [rcx]
0x1800036ea  jmp     loc_18000362C
0x1800036ef  cmp     byte ptr [rcx+19h], 5
0x1800036f3  jb      loc_180003413
0x1800036f9  mov     rcx, [rcx+10h]
0x1800036fd  lea     r9, aLegacyKnowledg_11; "Legacy::KnowledgeInspector::GetSerializ"...
0x180003704  mov     edx, 18h
0x180003709  lea     r8, WPP_48b71e9a06de38317ed143d1f750f029_Traceguids
0x180003710  call    WPP_SF_s
0x180003715  jmp     loc_180003413
0x18000371a  test    eax, eax
0x18000371c  js      loc_180003549
0x180003722  mov     ebx, 80041001h
0x180003727  jmp     loc_180003549
0x18000372c  lea     eax, [rcx+5]
0x18000372f  mov     [rbp+arg_8], eax
0x180003732  mov     ecx, [rdx+1Ch]
0x180003735  lea     eax, [rax+rcx*8]
0x180003738  add     ecx, eax
0x18000373a  mov     [rbp+arg_8], ecx
0x18000373d  jmp     loc_18000347B
0x180003742  lea     eax, [rdx+0Dh]
0x180003745  mov     [rbp+arg_8], eax
0x180003748  lea     eax, [rdx+0Dh]
0x18000374b  mov     ecx, [r8+1Ch]
0x18000374f  lea     eax, [rax+rcx*8]
0x180003752  add     eax, ecx
0x180003754  mov     [rbp+arg_8], eax
0x180003757  jmp     loc_18000350B
0x18000375c  lea     r9d, [r9+r8*8]
0x180003760  add     r9d, 5
0x180003764  add     r9d, r8d
0x180003767  jmp     loc_18000358A
0x18000376c  cmp     byte ptr [r11+19h], 5
0x180003771  jb      loc_18000361D
0x180003777  mov     rcx, [r11+10h]
0x18000377b  lea     r9, aLegacyKnowledg_2; "Legacy::KnowledgeInspector::GetSerializ"...
0x180003782  mov     edx, 20h ; ' '
0x180003787  lea     r8, WPP_48b71e9a06de38317ed143d1f750f029_Traceguids
0x18000378e  call    WPP_SF_s
0x180003793  mov     r11, cs:WPP_GLOBAL_Control
0x18000379a  jmp     loc_18000361D
0x18000379f  mov     rcx, rax; this
0x1800037a2  call    ?GetSize@SyncId@@QEBAGXZ; SyncId::GetSize(void)
0x1800037a7  movzx   edx, ax
0x1800037aa  add     edx, 4
0x1800037ad  add     r14d, edx
0x1800037b0  lea     rcx, [rbp+var_18]
0x1800037b4  call    ?GetNextElement@?$TableEnumerator@VSyncId@@HVDefaultHashTableContext@@@@QEAAPEAV?$TableElement@VSyncId@@HVDefaultHashTableContext@@@@XZ; TableEnumerator<SyncId,int,DefaultHashTableContext>::GetNextElement(void)
0x1800037b9  test    rax, rax
0x1800037bc  jnz     short loc_18000379F
0x1800037be  jmp     loc_18000363F
0x1800037c3  cmp     byte ptr [r11+19h], 5
0x1800037c8  jb      loc_18000365A
0x1800037ce  mov     rcx, [r11+10h]
0x1800037d2  lea     r9, aLegacyKnowledg_2; "Legacy::KnowledgeInspector::GetSerializ"...
0x1800037d9  mov     edx, 21h ; '!'
0x1800037de  mov     [rsp+48h+var_28], edi
0x1800037e2  lea     r8, WPP_48b71e9a06de38317ed143d1f750f029_Traceguids
0x1800037e9  call    WPP_SF_sD
0x1800037ee  mov     r11, cs:WPP_GLOBAL_Control
0x1800037f5  jmp     loc_18000365A
0x1800037fa  cmp     byte ptr [r11+19h], 5
0x1800037ff  jb      loc_1800036B1
0x180003805  mov     rcx, [r11+10h]
0x180003809  lea     r9, aLegacyKnowledg_11; "Legacy::KnowledgeInspector::GetSerializ"...
0x180003810  mov     edx, 19h
0x180003815  mov     [rsp+48h+var_28], ebx
0x180003819  lea     r8, WPP_48b71e9a06de38317ed143d1f750f029_Traceguids
0x180003820  call    WPP_SF_sD
0x180003825  jmp     loc_1800036B1
```
