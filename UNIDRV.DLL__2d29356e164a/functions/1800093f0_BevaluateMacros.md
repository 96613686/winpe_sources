# BevaluateMacros

- ea: `0x1800093f0`
- end: `0x180009b33`
- name: `BevaluateMacros`
- size: `1859`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x1800701a8`

## callees

- `0x180005ee0`
- `0x180007220`
- `0x180008ee4`
- `0x1800093f0`
- `0x180009bcc`
- `0x180009c6c`
- `0x18000aa88`
- `0x180039e74`
- `0x1800445dc`
- `0x18004485c`
- `0x180072870`

## string_xrefs

- `0x1800099fb`: `expected openbrace to follow *BlockMacros keyword.`
- `0x180009a0c`: `expected openbrace to follow *Macros keyword.`

## pseudocode

```c
__int64 __fastcall BevaluateMacros(__int64 a1)
{
  __int64 v1; // rbp
  char **v2; // r8
  __int64 v3; // r14
  int v4; // r13d
  unsigned int v5; // esi
  __int64 v7; // rdx
  __int64 v8; // rdi
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rdi
  __int64 v12; // rdi
  __int64 v13; // r15
  __int64 v14; // r12
  int v15; // edx
  int v16; // ecx
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  int v22; // eax
  unsigned int v23; // edx
  __int64 v24; // r10
  __int64 i; // r8
  __int64 v26; // rax
  __int64 j; // r8
  unsigned int v28; // r9d
  unsigned int k; // edx
  __int64 v30; // rcx
  __int64 result; // rax
  unsigned int *v32; // rdi
  __int64 v33; // rax
  unsigned int v34; // edx
  __int64 v35; // rcx
  _DWORD *v36; // rcx
  __int64 v37; // rax
  __int64 v38; // rcx
  unsigned int v39; // ecx
  unsigned int v40; // [rsp+80h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 504);
  v2 = &mMainKeywordTable;
  v3 = *(_QWORD *)(a1 + 480);
  v40 = 0;
  v4 = 0;
  *(_DWORD *)(a1 + 588) = 0;
  v5 = 0;
  *(_DWORD *)(a1 + 564) = 0;
  *(_DWORD *)(a1 + 540) = 0;
  while ( 1 )
  {
    if ( *(int *)(a1 + 2220) >= 2 )
      return 0;
    v7 = 56LL * v5;
    v8 = v7 + v3;
    v9 = *(unsigned int *)(v7 + v3);
    if ( (_DWORD)v9 == *(_DWORD *)(a1 + 2232) )
      goto LABEL_28;
    if ( (_DWORD)v9 == 65280 )
      goto LABEL_20;
    if ( (_DWORD)v9 == 65283 )
      break;
    if ( v4 )
    {
      if ( (_DWORD)v9 == 65281 )
        goto LABEL_41;
      if ( (_DWORD)v9 == 65282 )
      {
        v12 = *(unsigned int *)(a1 + 516);
        if ( (unsigned int)v12 >= *(_DWORD *)(a1 + 512) )
          goto LABEL_52;
        v13 = 56 * v12;
        v40 = *(_DWORD *)(a1 + 516);
        *(_DWORD *)(a1 + 516) = v12 + 1;
        v14 = v7 + v3;
        *(_OWORD *)(v13 + v1) = *(_OWORD *)(v7 + v3);
        *(_OWORD *)(v13 + v1 + 16) = *(_OWORD *)(v7 + v3 + 16);
        *(_OWORD *)(v13 + v1 + 32) = *(_OWORD *)(v7 + v3 + 32);
        *(_QWORD *)(v13 + v1 + 48) = *(_QWORD *)(v7 + v3 + 48);
        if ( !(unsigned int)BDefineValueMacroName(v1, (unsigned int)v12, a1) )
        {
          *(_DWORD *)(v13 + v1) = 65280;
          vIdentifySource(v14, a1);
          WriteDbgTraceErrorGpd("BevaluateMacros", "Internal Error: valueMacro name registration failed.");
          goto LABEL_19;
        }
        if ( (*(_BYTE *)(v14 + 52) & 0x20) == 0 )
          goto LABEL_19;
        v22 = BResolveValueMacroReference(v1, (unsigned int)v12, a1);
        v2 = &mMainKeywordTable;
        if ( !v22 )
        {
          *(_DWORD *)(v13 + v1) = 65280;
          --*(_DWORD *)(a1 + 564);
        }
      }
      else
      {
        if ( LODWORD((&mMainKeywordTable)[4 * v9 + 2]) || *((_DWORD *)&mMainKeywordTable + 8 * v9 + 5) != 14 )
        {
LABEL_41:
          vIdentifySource(v8, a1);
          WriteDbgTraceErrorGpd("BevaluateMacros", "Only valueMacroDefinitions permitted within *Macros  constructs.");
          goto LABEL_19;
        }
        v4 = 0;
      }
    }
    else
    {
      if ( (unsigned int)(v9 - 65281) <= 1 )
        goto LABEL_8;
      v15 = (int)(&mMainKeywordTable)[4 * v9 + 2];
      v16 = *((_DWORD *)&mMainKeywordTable + 8 * v9 + 5);
      if ( v15 )
      {
        if ( v15 == 2 && v16 == 11 )
        {
          if ( (*(_BYTE *)(v8 + 52) & 0x20) == 0 )
          {
            vIdentifySource(v8, a1);
            WriteDbgTraceErrorGpd("BevaluateMacros", "expected a =MacroName as the value of *InsertBlockMacro keyword.");
            goto LABEL_27;
          }
          if ( !(unsigned int)BResolveBlockMacroReference(v3, v5, a1) )
          {
            vIdentifySource(v8, a1);
LABEL_27:
            WriteDbgTraceErrorGpd("BevaluateMacros", "   *InsertBlockMacro Construct ignored.");
LABEL_28:
            VIgnoreBlock(v8, 1, a1);
          }
LABEL_19:
          v2 = &mMainKeywordTable;
          goto LABEL_20;
        }
LABEL_8:
        v10 = *(unsigned int *)(a1 + 516);
        if ( (unsigned int)v10 < *(_DWORD *)(a1 + 512) )
        {
          v40 = *(_DWORD *)(a1 + 516);
          *(_DWORD *)(a1 + 516) = v10 + 1;
          v11 = v1 + 56 * v10;
          *(_OWORD *)v11 = *(_OWORD *)(56LL * v5 + v3);
          *(_OWORD *)(v11 + 16) = *(_OWORD *)(56LL * v5 + v3 + 16);
          *(_OWORD *)(v11 + 32) = *(_OWORD *)(56LL * v5 + v3 + 32);
          *(_QWORD *)(v11 + 48) = *(_QWORD *)(56LL * v5 + v3 + 48);
          if ( (*(_BYTE *)(56LL * v5 + v3 + 52) & 0x20) == 0 )
            goto LABEL_20;
          if ( !(unsigned int)BResolveValueMacroReference(v1, v10, a1) )
            *(_DWORD *)v11 = 65280;
          if ( *(_DWORD *)(a1 + 2228) >= 4u )
          {
            WriteDbgTraceErrorGpd("BevaluateMacros", "Enumerate ValueMacro Reference at:");
            vIdentifySource(v11, a1);
            WriteDbgTraceErrorGpd(
              "BevaluateMacros",
              "    %0.*s : %0.*s",
              *(_DWORD *)(v11 + 16),
              *(const char **)(v11 + 8),
              *(_DWORD *)(v11 + 32),
              *(const char **)(v11 + 24));
          }
          goto LABEL_19;
        }
LABEL_52:
        WriteDbgTraceErrorGpd(
          "BallocElementFromMasterTable",
          "BallocElementFromMasterTable: Out of array elements - restart.",
          &mMainKeywordTable);
        if ( *(int *)(a1 + 2220) < 2 )
        {
          *(_DWORD *)(a1 + 2224) = 2;
          *(_DWORD *)(a1 + 2216) = 21;
        }
LABEL_54:
        *(_DWORD *)(a1 + 2220) = 2;
        *(_DWORD *)(a1 + 2224) = 2;
        *(_DWORD *)(a1 + 2216) = 21;
        goto LABEL_19;
      }
      if ( v16 == 11 )
      {
        if ( !(unsigned int)BDefineBlockMacroName(v3, v5, a1) )
        {
          vIdentifySource(v8, a1);
          WriteDbgTraceErrorGpd("BevaluateMacros", "Internal Error: blockMacro name registration failed.");
          goto LABEL_19;
        }
        do
          ++v5;
        while ( *(_DWORD *)(56LL * v5 + v3) == 65280 );
        v32 = (unsigned int *)(v3 + 56LL * v5);
        if ( *v32 < 0xFF00 )
        {
          v33 = 4LL * *v32;
          if ( !LODWORD((&mMainKeywordTable)[v33 + 2]) && *((_DWORD *)&mMainKeywordTable + 2 * v33 + 5) == 13 )
          {
            if ( !(unsigned int)BallocElementFromMasterTable(21, &v40, a1) )
              goto LABEL_54;
            v34 = v40;
            v35 = 56LL * v40;
            *(_OWORD *)(v35 + v1) = *(_OWORD *)v32;
            *(_OWORD *)(v35 + v1 + 16) = *((_OWORD *)v32 + 1);
            *(_OWORD *)(v35 + v1 + 32) = *((_OWORD *)v32 + 2);
            *(_QWORD *)(v35 + v1 + 48) = *((_QWORD *)v32 + 6);
            *(_DWORD *)(*(_QWORD *)(a1 + 528) + 12LL * (unsigned int)(*(_DWORD *)(a1 + 540) - 1) + 4) = v34;
            v21 = 1;
            goto LABEL_37;
          }
        }
        vIdentifySource(v3 + 56LL * v5, a1);
        WriteDbgTraceErrorGpd("BevaluateMacros", "expected openbrace to follow *BlockMacros keyword.");
LABEL_68:
        *(_DWORD *)(a1 + 2224) = 1;
        *(_DWORD *)(a1 + 2220) = 3;
        goto LABEL_19;
      }
      if ( v16 != 12 )
      {
        if ( v16 != 13 )
        {
          if ( v16 != 14 )
            goto LABEL_8;
          if ( (unsigned int)BallocElementFromMasterTable(21, &v40, a1) )
          {
            v17 = v40;
            v18 = 56LL * v40;
            *(_OWORD *)(v18 + v1) = *(_OWORD *)(56LL * v5 + v3);
            *(_OWORD *)(v18 + v1 + 16) = *(_OWORD *)(56LL * v5 + v3 + 16);
            *(_OWORD *)(v18 + v1 + 32) = *(_OWORD *)(56LL * v5 + v3 + 32);
            *(_QWORD *)(v18 + v1 + 48) = *(_QWORD *)(56LL * v5 + v3 + 48);
            BDecreaseMacroLevel(v1, v17, a1);
            goto LABEL_19;
          }
          goto LABEL_54;
        }
        v19 = *(unsigned int *)(a1 + 516);
        if ( (unsigned int)v19 >= *(_DWORD *)(a1 + 512) )
          goto LABEL_52;
        v40 = *(_DWORD *)(a1 + 516);
        *(_DWORD *)(a1 + 516) = v19 + 1;
        v20 = 56 * v19;
        *(_OWORD *)(v20 + v1) = *(_OWORD *)(56LL * v5 + v3);
        *(_OWORD *)(v20 + v1 + 16) = *(_OWORD *)(56LL * v5 + v3 + 16);
        *(_OWORD *)(v20 + v1 + 32) = *(_OWORD *)(56LL * v5 + v3 + 32);
        *(_QWORD *)(v20 + v1 + 48) = *(_QWORD *)(56LL * v5 + v3 + 48);
        v21 = 0;
LABEL_37:
        BIncreaseMacroLevel(v21, a1, v2);
        goto LABEL_19;
      }
      do
        ++v5;
      while ( *(_DWORD *)(56LL * v5 + v3) == 65280 );
      v36 = (_DWORD *)(v3 + 56LL * v5);
      if ( *v36 >= 0xFF00u
        || (v37 = 4LL * (unsigned int)*v36, LODWORD((&mMainKeywordTable)[v37 + 2]))
        || *((_DWORD *)&mMainKeywordTable + 2 * v37 + 5) != 13 )
      {
        vIdentifySource(v36, a1);
        WriteDbgTraceErrorGpd("BevaluateMacros", "expected openbrace to follow *Macros keyword.");
        goto LABEL_68;
      }
      v4 = 1;
    }
LABEL_20:
    ++v5;
  }
  v23 = 0;
  v24 = *(_QWORD *)(a1 + 528);
  for ( i = *(_QWORD *)(a1 + 552);
        v23 < *(_DWORD *)(a1 + 564);
        *(_DWORD *)(56LL * *(unsigned int *)(i + 8 * v26 + 4) + v1) = 65280 )
  {
    v26 = v23++;
  }
  for ( j = 0; (unsigned int)j < *(_DWORD *)(a1 + 540); j = (unsigned int)(j + 1) )
  {
    v28 = *(_DWORD *)(v24 + 12LL * (unsigned int)j + 8);
    for ( k = *(_DWORD *)(v24 + 12LL * (unsigned int)j + 4); k <= v28; ++k )
    {
      v30 = 56LL * k;
      *(_DWORD *)(v30 + v1) = 65280;
    }
  }
  if ( *(_DWORD *)(a1 + 588) )
  {
    WriteDbgTraceErrorGpd("BevaluateMacros", "Too few closing braces.  Fatal syntax error.", j);
    *(_DWORD *)(a1 + 2220) = 3;
    *(_DWORD *)(a1 + 2224) = 1;
    return 0;
  }
  if ( !(unsigned int)BallocElementFromMasterTable(21, &v40, a1) )
  {
    *(_DWORD *)(a1 + 2220) = 2;
    *(_DWORD *)(a1 + 2224) = 2;
    *(_DWORD *)(a1 + 2216) = 21;
    return 0;
  }
  v38 = 56LL * v40;
  result = 0;
  *(_OWORD *)(v38 + v1) = *(_OWORD *)v8;
  *(_OWORD *)(v38 + v1 + 16) = *(_OWORD *)(v8 + 16);
  *(_OWORD *)(v38 + v1 + 32) = *(_OWORD *)(v8 + 32);
  *(_QWORD *)(v38 + v1 + 48) = *(_QWORD *)(v8 + 48);
  v39 = 0;
  if ( *(int *)(a1 + 2220) < 2 )
  {
    LOBYTE(v39) = *(_DWORD *)(a1 + 612) == 0;
    return v39;
  }
  return result;
}

```

## disassembly

```asm
0x1800093f0  mov     rax, rsp
0x1800093f3  push    rbx
0x1800093f4  push    rbp
0x1800093f5  push    rsi
0x1800093f6  push    rdi
0x1800093f7  push    r12
0x1800093f9  push    r13
0x1800093fb  push    r14
0x1800093fd  push    r15
0x1800093ff  sub     rsp, 38h
0x180009403  mov     rbp, [rcx+1F8h]
0x18000940a  lea     r8, mMainKeywordTable
0x180009411  mov     r14, [rcx+1E0h]
0x180009418  xor     r12d, r12d
0x18000941b  mov     [rax+8], r12d
0x18000941f  mov     r13d, r12d
0x180009422  mov     [rcx+24Ch], r12d
0x180009429  mov     esi, r12d
0x18000942c  mov     [rcx+234h], r12d
0x180009433  mov     rbx, rcx
0x180009436  mov     [rcx+21Ch], r12d
0x18000943d  cmp     dword ptr [rbx+8ACh], 2
0x180009444  jge     loc_180009877
0x18000944a  mov     r15d, esi
0x18000944d  imul    rdx, r15, 38h ; '8'
0x180009451  lea     rdi, [rdx+r14]
0x180009455  mov     ecx, [rdi]
0x180009457  cmp     ecx, [rbx+8B8h]
0x18000945d  jz      loc_180009668
0x180009463  mov     eax, ecx
0x180009465  sub     eax, 0FF00h
0x18000946a  jz      loc_180009601
0x180009470  cmp     eax, 3
0x180009473  jz      loc_1800097CE
0x180009479  test    r13d, r13d
0x18000947c  jnz     loc_180009564
0x180009482  lea     eax, [rcx-0FF01h]
0x180009488  cmp     eax, 1
0x18000948b  ja      loc_180009608
0x180009491  mov     edx, [rbx+204h]
0x180009497  cmp     edx, [rbx+200h]
0x18000949d  jnb     loc_18000988A
0x1800094a3  lea     eax, [rdx+1]
0x1800094a6  mov     [rsp+78h+arg_0], edx
0x1800094ad  mov     [rbx+204h], eax
0x1800094b3  imul    rax, r15, 38h ; '8'
0x1800094b7  imul    rdi, rdx, 38h ; '8'
0x1800094bb  movups  xmm0, xmmword ptr [rax+r14]
0x1800094c0  add     rdi, rbp
0x1800094c3  movups  xmmword ptr [rdi], xmm0
0x1800094c6  movups  xmm1, xmmword ptr [rax+r14+10h]
0x1800094cc  movups  xmmword ptr [rdi+10h], xmm1
0x1800094d0  movups  xmm0, xmmword ptr [rax+r14+20h]
0x1800094d6  movups  xmmword ptr [rdi+20h], xmm0
0x1800094da  movsd   xmm1, qword ptr [rax+r14+30h]
0x1800094e1  imul    rax, r15, 38h ; '8'
0x1800094e5  movsd   qword ptr [rdi+30h], xmm1
0x1800094ea  test    byte ptr [rax+r14+34h], 20h
0x1800094f0  jz      loc_180009601
0x1800094f6  mov     r8, rbx
0x1800094f9  mov     rcx, rbp
0x1800094fc  call    BResolveValueMacroReference
0x180009501  test    eax, eax
0x180009503  jz      loc_180009A9E
0x180009509  cmp     dword ptr [rbx+8B4h], 4
0x180009510  jb      loc_1800095FA
0x180009516  lea     rdx, aEnumerateValue; "Enumerate ValueMacro Reference at:"
0x18000951d  lea     rcx, aBevaluatemacro; "BevaluateMacros"
0x180009524  call    WriteDbgTraceErrorGpd
0x180009529  mov     rdx, rbx
0x18000952c  mov     rcx, rdi
0x18000952f  call    vIdentifySource
0x180009534  mov     rax, [rdi+18h]
0x180009538  lea     rdx, a0S0S; "    %0.*s : %0.*s"
0x18000953f  mov     r9, [rdi+8]
0x180009543  lea     rcx, aBevaluatemacro; "BevaluateMacros"
0x18000954a  mov     r8d, [rdi+10h]
0x18000954e  mov     [rsp+78h+var_50], rax
0x180009553  mov     eax, [rdi+20h]
0x180009556  mov     [rsp+78h+var_58], eax
0x18000955a  call    WriteDbgTraceErrorGpd
0x18000955f  jmp     loc_1800095FA
0x180009564  cmp     ecx, 0FF01h
0x18000956a  jz      loc_1800097AB
0x180009570  cmp     ecx, 0FF02h
0x180009576  jnz     loc_180009799
0x18000957c  mov     edi, [rbx+204h]
0x180009582  cmp     edi, [rbx+200h]
0x180009588  jnb     loc_18000988A
0x18000958e  imul    r15, rdi, 38h ; '8'
0x180009592  lea     eax, [rdi+1]
0x180009595  mov     [rsp+78h+arg_0], edi
0x18000959c  mov     [rbx+204h], eax
0x1800095a2  lea     r12, [rdx+r14]
0x1800095a6  movups  xmm0, xmmword ptr [rdx+r14]
0x1800095ab  mov     r8, rbx
0x1800095ae  mov     rcx, rbp
0x1800095b1  movups  xmmword ptr [r15+rbp], xmm0
0x1800095b6  movups  xmm1, xmmword ptr [rdx+r14+10h]
0x1800095bc  movups  xmmword ptr [r15+rbp+10h], xmm1
0x1800095c2  movups  xmm0, xmmword ptr [rdx+r14+20h]
0x1800095c8  movups  xmmword ptr [r15+rbp+20h], xmm0
0x1800095ce  movsd   xmm1, qword ptr [rdx+r14+30h]
0x1800095d5  mov     edx, edi
0x1800095d7  movsd   qword ptr [r15+rbp+30h], xmm1
0x1800095de  call    BDefineValueMacroName
0x1800095e3  test    eax, eax
0x1800095e5  jz      loc_1800098DD
0x1800095eb  test    byte ptr [r12+34h], 20h
0x1800095f1  jnz     loc_180009767
0x1800095f7  xor     r12d, r12d
0x1800095fa  lea     r8, mMainKeywordTable
0x180009601  inc     esi
0x180009603  jmp     loc_18000943D
0x180009608  mov     rax, rcx
0x18000960b  shl     rax, 5
0x18000960f  mov     edx, [rax+r8+10h]
0x180009614  mov     ecx, [rax+r8+14h]
0x180009619  test    edx, edx
0x18000961b  jz      short loc_18000967A
0x18000961d  cmp     edx, 2
0x180009620  jnz     loc_180009491
0x180009626  cmp     ecx, 0Bh
0x180009629  jnz     loc_180009491
0x18000962f  test    byte ptr [rdi+34h], 20h
0x180009633  jz      loc_180009A7B
0x180009639  mov     r8, rbx
0x18000963c  mov     edx, esi
0x18000963e  mov     rcx, r14
0x180009641  call    BResolveBlockMacroReference
0x180009646  test    eax, eax
0x180009648  jnz     short loc_1800095FA
0x18000964a  mov     rdx, rbx
0x18000964d  mov     rcx, rdi
0x180009650  call    vIdentifySource
0x180009655  lea     rdx, aInsertblockmac; "   *InsertBlockMacro Construct ignored."
0x18000965c  lea     rcx, aBevaluatemacro; "BevaluateMacros"
0x180009663  call    WriteDbgTraceErrorGpd
0x180009668  mov     r8, rbx
0x18000966b  mov     edx, 1
0x180009670  mov     rcx, rdi
0x180009673  call    VIgnoreBlock
0x180009678  jmp     short loc_1800095FA
0x18000967a  cmp     ecx, 0Bh
0x18000967d  jz      loc_18000991C
0x180009683  cmp     ecx, 0Ch
0x180009686  jz      loc_180009A38
0x18000968c  cmp     ecx, 0Dh
0x18000968f  jz      short loc_180009702
0x180009691  cmp     ecx, 0Eh
0x180009694  jnz     loc_180009491
0x18000969a  mov     r8, rbx
0x18000969d  lea     rdx, [rsp+78h+arg_0]
0x1800096a5  mov     ecx, 15h
0x1800096aa  call    BallocElementFromMasterTable
0x1800096af  test    eax, eax
0x1800096b1  jz      loc_1800098BA
0x1800096b7  mov     edx, [rsp+78h+arg_0]
0x1800096be  imul    r8, r15, 38h ; '8'
0x1800096c2  imul    rcx, rdx, 38h ; '8'
0x1800096c6  movups  xmm0, xmmword ptr [r8+r14]
0x1800096cb  movups  xmmword ptr [rcx+rbp], xmm0
0x1800096cf  movups  xmm1, xmmword ptr [r8+r14+10h]
0x1800096d5  movups  xmmword ptr [rcx+rbp+10h], xmm1
0x1800096da  movups  xmm0, xmmword ptr [r8+r14+20h]
0x1800096e0  movups  xmmword ptr [rcx+rbp+20h], xmm0
0x1800096e5  movsd   xmm1, qword ptr [r8+r14+30h]
0x1800096ec  mov     r8, rbx
0x1800096ef  movsd   qword ptr [rcx+rbp+30h], xmm1
0x1800096f5  mov     rcx, rbp
0x1800096f8  call    BDecreaseMacroLevel
0x1800096fd  jmp     loc_1800095FA
0x180009702  mov     ecx, [rbx+204h]
0x180009708  cmp     ecx, [rbx+200h]
0x18000970e  jnb     loc_18000988A
0x180009714  imul    rdx, r15, 38h ; '8'
0x180009718  lea     eax, [rcx+1]
0x18000971b  mov     [rsp+78h+arg_0], ecx
0x180009722  mov     [rbx+204h], eax
0x180009728  imul    rcx, 38h ; '8'
0x18000972c  movups  xmm0, xmmword ptr [rdx+r14]
0x180009731  movups  xmmword ptr [rcx+rbp], xmm0
0x180009735  movups  xmm1, xmmword ptr [rdx+r14+10h]
0x18000973b  movups  xmmword ptr [rcx+rbp+10h], xmm1
0x180009740  movups  xmm0, xmmword ptr [rdx+r14+20h]
0x180009746  movups  xmmword ptr [rcx+rbp+20h], xmm0
0x18000974b  movsd   xmm1, qword ptr [rdx+r14+30h]
0x180009752  movsd   qword ptr [rcx+rbp+30h], xmm1
0x180009758  xor     ecx, ecx
0x18000975a  mov     rdx, rbx
0x18000975d  call    BIncreaseMacroLevel
0x180009762  jmp     loc_1800095FA
0x180009767  mov     r8, rbx
0x18000976a  mov     edx, edi
0x18000976c  mov     rcx, rbp
0x18000976f  call    BResolveValueMacroReference
0x180009774  xor     r12d, r12d
0x180009777  lea     r8, mMainKeywordTable
0x18000977e  test    eax, eax
0x180009780  jnz     loc_180009601
0x180009786  mov     dword ptr [r15+rbp], 0FF00h
0x18000978e  dec     dword ptr [rbx+234h]
0x180009794  jmp     loc_180009601
0x180009799  mov     rax, rcx
0x18000979c  shl     rax, 5
0x1800097a0  cmp     [rax+r8+10h], r12d
0x1800097a5  jz      loc_180009908
0x1800097ab  mov     rdx, rbx
0x1800097ae  mov     rcx, rdi
0x1800097b1  call    vIdentifySource
0x1800097b6  lea     rdx, aOnlyValuemacro; "Only valueMacroDefinitions permitted wi"...
0x1800097bd  lea     rcx, aBevaluatemacro; "BevaluateMacros"
0x1800097c4  call    WriteDbgTraceErrorGpd
0x1800097c9  jmp     loc_1800095FA
0x1800097ce  mov     edx, r12d
0x1800097d1  mov     r10, [rbx+210h]
0x1800097d8  mov     r8, [rbx+228h]
0x1800097df  cmp     [rbx+234h], r12d
0x1800097e6  jbe     short loc_180009804
0x1800097e8  mov     eax, edx
0x1800097ea  inc     edx
0x1800097ec  mov     ecx, [r8+rax*8+4]
0x1800097f1  imul    rax, rcx, 38h ; '8'
0x1800097f5  mov     dword ptr [rax+rbp], 0FF00h
0x1800097fc  cmp     edx, [rbx+234h]
0x180009802  jb      short loc_1800097E8
0x180009804  mov     r8d, r12d
0x180009807  cmp     [rbx+21Ch], r12d
0x18000980e  jbe     short loc_180009843
0x180009810  mov     eax, r8d
0x180009813  lea     rcx, [rax+rax*2]
0x180009817  mov     r9d, [r10+rcx*4+8]
0x18000981c  mov     edx, [r10+rcx*4+4]
0x180009821  jmp     short loc_180009832
0x180009823  mov     eax, edx
0x180009825  imul    rcx, rax, 38h ; '8'
0x180009829  inc     edx
0x18000982b  mov     dword ptr [rcx+rbp], 0FF00h
0x180009832  cmp     edx, r9d
0x180009835  jbe     short loc_180009823
0x180009837  inc     r8d
0x18000983a  cmp     r8d, [rbx+21Ch]
0x180009841  jb      short loc_180009810
0x180009843  cmp     [rbx+24Ch], r12d
0x18000984a  jz      loc_180009AA9
0x180009850  lea     rdx, aTooFewClosingB; "Too few closing braces.  Fatal syntax e"...
0x180009857  lea     rcx, aBevaluatemacro; "BevaluateMacros"
0x18000985e  call    WriteDbgTraceErrorGpd
0x180009863  mov     dword ptr [rbx+8ACh], 3
0x18000986d  mov     dword ptr [rbx+8B0h], 1
0x180009877  xor     eax, eax
0x180009879  add     rsp, 38h
0x18000987d  pop     r15
0x18000987f  pop     r14
0x180009881  pop     r13
0x180009883  pop     r12
0x180009885  pop     rdi
0x180009886  pop     rsi
0x180009887  pop     rbp
0x180009888  pop     rbx
0x180009889  retn
0x18000988a  lea     rdx, aBallocelementf; "BallocElementFromMasterTable: Out of ar"...
0x180009891  lea     rcx, aBallocelementf_0; "BallocElementFromMasterTable"
0x180009898  call    WriteDbgTraceErrorGpd
0x18000989d  cmp     dword ptr [rbx+8ACh], 2
0x1800098a4  jge     short loc_1800098BA
0x1800098a6  mov     dword ptr [rbx+8B0h], 2
0x1800098b0  mov     dword ptr [rbx+8A8h], 15h
0x1800098ba  mov     dword ptr [rbx+8ACh], 2
0x1800098c4  mov     dword ptr [rbx+8B0h], 2
0x1800098ce  mov     dword ptr [rbx+8A8h], 15h
0x1800098d8  jmp     loc_1800095FA
0x1800098dd  mov     rdx, rbx
0x1800098e0  mov     dword ptr [r15+rbp], 0FF00h
0x1800098e8  mov     rcx, r12
0x1800098eb  call    vIdentifySource
0x1800098f0  lea     rdx, aInternalErrorV; "Internal Error: valueMacro name registr"...
0x1800098f7  lea     rcx, aBevaluatemacro; "BevaluateMacros"
0x1800098fe  call    WriteDbgTraceErrorGpd
0x180009903  jmp     loc_1800095F7
0x180009908  cmp     dword ptr [rax+r8+14h], 0Eh
0x18000990e  jnz     loc_1800097AB
0x180009914  mov     r13d, r12d
0x180009917  jmp     loc_180009601
0x18000991c  mov     r8, rbx
0x18000991f  mov     edx, esi
0x180009921  mov     rcx, r14
0x180009924  call    BDefineBlockMacroName
0x180009929  test    eax, eax
0x18000992b  jnz     short loc_180009944
0x18000992d  mov     rdx, rbx
0x180009930  mov     rcx, rdi
0x180009933  call    vIdentifySource
0x180009938  lea     rdx, aInternalErrorB_4; "Internal Error: blockMacro name registr"...
0x18000993f  jmp     loc_1800097BD
0x180009944  mov     edx, 0FF00h
0x180009949  inc     esi
0x18000994b  mov     eax, esi
0x18000994d  imul    rcx, rax, 38h ; '8'
0x180009951  cmp     [rcx+r14], edx
  ... truncated ...
```
