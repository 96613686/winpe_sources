# BevaluateMacros

- ea: `0x1800093b0`
- end: `0x180009af4`
- name: `BevaluateMacros`
- size: `1860`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x1800721d0`

## callees

- `0x180005e10`
- `0x180007150`
- `0x180008ea8`
- `0x1800093b0`
- `0x180009b8c`
- `0x180009c60`
- `0x18000aa88`
- `0x18003ab78`
- `0x180045898`
- `0x180045aa4`
- `0x1800748f8`

## string_xrefs

- `0x1800099bc`: `expected openbrace to follow *BlockMacros keyword.`
- `0x1800099cd`: `expected openbrace to follow *Macros keyword.`

## pseudocode

```c
__int64 __fastcall BevaluateMacros(__int64 a1)
{
  __int64 v1; // rbp
  __int64 v2; // r14
  int v3; // r13d
  unsigned int v4; // esi
  __int64 v6; // rdx
  __int64 v7; // rdi
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rdi
  __int64 v11; // r8
  __int64 v12; // rdi
  __int64 v13; // r15
  __int64 v14; // r12
  __int64 v15; // r8
  int v16; // edx
  int v17; // ecx
  __int64 v18; // r8
  int v19; // edx
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  unsigned int v23; // ecx
  unsigned int v24; // edx
  __int64 v25; // r10
  __int64 i; // r8
  __int64 v27; // rax
  __int64 j; // r8
  unsigned int v29; // r9d
  unsigned int k; // edx
  __int64 v31; // rcx
  __int64 result; // rax
  __int64 v33; // r8
  unsigned int *v34; // rdi
  __int64 v35; // rax
  unsigned int v36; // edx
  __int64 v37; // rcx
  _DWORD *v38; // rcx
  __int64 v39; // rax
  __int64 v40; // rcx
  unsigned int v41; // ecx
  unsigned int v42; // [rsp+80h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 504);
  v2 = *(_QWORD *)(a1 + 480);
  v42 = 0;
  v3 = 0;
  *(_DWORD *)(a1 + 588) = 0;
  v4 = 0;
  *(_DWORD *)(a1 + 564) = 0;
  *(_DWORD *)(a1 + 540) = 0;
  while ( 1 )
  {
    if ( *(int *)(a1 + 2220) >= 2 )
      return 0;
    v6 = 56LL * v4;
    v7 = v6 + v2;
    v8 = *(unsigned int *)(v6 + v2);
    if ( (_DWORD)v8 == *(_DWORD *)(a1 + 2232) )
      goto LABEL_27;
    if ( (_DWORD)v8 == 65280 )
      goto LABEL_19;
    if ( (_DWORD)v8 == 65283 )
      break;
    if ( v3 )
    {
      if ( (_DWORD)v8 == 65281 )
        goto LABEL_40;
      if ( (_DWORD)v8 == 65282 )
      {
        v12 = *(unsigned int *)(a1 + 516);
        if ( (unsigned int)v12 >= *(_DWORD *)(a1 + 512) )
          goto LABEL_51;
        v13 = 56 * v12;
        v42 = *(_DWORD *)(a1 + 516);
        *(_DWORD *)(a1 + 516) = v12 + 1;
        v14 = v6 + v2;
        *(_OWORD *)(v13 + v1) = *(_OWORD *)(v6 + v2);
        *(_OWORD *)(v13 + v1 + 16) = *(_OWORD *)(v6 + v2 + 16);
        *(_OWORD *)(v13 + v1 + 32) = *(_OWORD *)(v6 + v2 + 32);
        *(_QWORD *)(v13 + v1 + 48) = *(_QWORD *)(v6 + v2 + 48);
        if ( (unsigned int)BDefineValueMacroName(v1, v12, a1) )
        {
          if ( (*(_BYTE *)(v14 + 52) & 0x20) != 0 && !(unsigned int)BResolveValueMacroReference(v1, v12, a1) )
          {
            *(_DWORD *)(v13 + v1) = 65280;
            --*(_DWORD *)(a1 + 564);
          }
        }
        else
        {
          *(_DWORD *)(v13 + v1) = 65280;
          vIdentifySource((_DWORD *)v14, a1, v15);
          WriteDbgTraceErrorGpd((__int64)"BevaluateMacros", "Internal Error: valueMacro name registration failed.");
        }
      }
      else
      {
        if ( LODWORD((&mMainKeywordTable)[4 * v8 + 2]) || *((_DWORD *)&mMainKeywordTable + 8 * v8 + 5) != 14 )
        {
LABEL_40:
          vIdentifySource((_DWORD *)v7, a1, (__int64)&mMainKeywordTable);
          WriteDbgTraceErrorGpd(
            (__int64)"BevaluateMacros",
            "Only valueMacroDefinitions permitted within *Macros  constructs.");
          goto LABEL_19;
        }
        v3 = 0;
      }
    }
    else
    {
      if ( (unsigned int)(v8 - 65281) <= 1 )
        goto LABEL_8;
      v16 = (int)(&mMainKeywordTable)[4 * v8 + 2];
      v17 = *((_DWORD *)&mMainKeywordTable + 8 * v8 + 5);
      if ( v16 )
      {
        if ( v16 == 2 && v17 == 11 )
        {
          if ( (*(_BYTE *)(v7 + 52) & 0x20) != 0 )
          {
            if ( (unsigned int)BResolveBlockMacroReference(v2, v4, a1) )
              goto LABEL_19;
            vIdentifySource((_DWORD *)v7, a1, v18);
          }
          else
          {
            vIdentifySource((_DWORD *)v7, a1, (__int64)&mMainKeywordTable);
            WriteDbgTraceErrorGpd(
              (__int64)"BevaluateMacros",
              "expected a =MacroName as the value of *InsertBlockMacro keyword.");
          }
          WriteDbgTraceErrorGpd((__int64)"BevaluateMacros", "   *InsertBlockMacro Construct ignored.");
LABEL_27:
          VIgnoreBlock((_DWORD *)v7, 1, a1);
          goto LABEL_19;
        }
LABEL_8:
        v9 = *(unsigned int *)(a1 + 516);
        if ( (unsigned int)v9 >= *(_DWORD *)(a1 + 512) )
          goto LABEL_51;
        v42 = *(_DWORD *)(a1 + 516);
        *(_DWORD *)(a1 + 516) = v9 + 1;
        v10 = v1 + 56 * v9;
        *(_OWORD *)v10 = *(_OWORD *)(56LL * v4 + v2);
        *(_OWORD *)(v10 + 16) = *(_OWORD *)(56LL * v4 + v2 + 16);
        *(_OWORD *)(v10 + 32) = *(_OWORD *)(56LL * v4 + v2 + 32);
        *(_QWORD *)(v10 + 48) = *(_QWORD *)(56LL * v4 + v2 + 48);
        if ( (*(_BYTE *)(56LL * v4 + v2 + 52) & 0x20) != 0 )
        {
          if ( !(unsigned int)BResolveValueMacroReference(v1, v9, a1) )
            *(_DWORD *)v10 = 65280;
          if ( *(_DWORD *)(a1 + 2228) >= 4u )
          {
            WriteDbgTraceErrorGpd((__int64)"BevaluateMacros", "Enumerate ValueMacro Reference at:");
            vIdentifySource((_DWORD *)v10, a1, v11);
            WriteDbgTraceErrorGpd(
              (__int64)"BevaluateMacros",
              "    %0.*s : %0.*s",
              *(_DWORD *)(v10 + 16),
              *(const char **)(v10 + 8),
              *(_DWORD *)(v10 + 32),
              *(const char **)(v10 + 24));
          }
        }
        goto LABEL_19;
      }
      if ( v17 == 11 )
      {
        if ( !(unsigned int)BDefineBlockMacroName(v2, v4, a1) )
        {
          vIdentifySource((_DWORD *)v7, a1, v33);
          WriteDbgTraceErrorGpd((__int64)"BevaluateMacros", "Internal Error: blockMacro name registration failed.");
          goto LABEL_19;
        }
        do
          ++v4;
        while ( *(_DWORD *)(56LL * v4 + v2) == 65280 );
        v34 = (unsigned int *)(v2 + 56LL * v4);
        if ( *v34 < 0xFF00 )
        {
          v35 = 4LL * *v34;
          if ( !LODWORD((&mMainKeywordTable)[v35 + 2]) && *((_DWORD *)&mMainKeywordTable + 2 * v35 + 5) == 13 )
          {
            if ( (unsigned int)BallocElementFromMasterTable(21, &v42, (_DWORD *)a1) )
            {
              v36 = v42;
              v37 = 56LL * v42;
              *(_OWORD *)(v37 + v1) = *(_OWORD *)v34;
              *(_OWORD *)(v37 + v1 + 16) = *((_OWORD *)v34 + 1);
              *(_OWORD *)(v37 + v1 + 32) = *((_OWORD *)v34 + 2);
              *(_QWORD *)(v37 + v1 + 48) = *((_QWORD *)v34 + 6);
              *(_DWORD *)(*(_QWORD *)(a1 + 528) + 12LL * (unsigned int)(*(_DWORD *)(a1 + 540) - 1) + 4) = v36;
              v23 = 1;
              goto LABEL_36;
            }
            goto LABEL_53;
          }
        }
        vIdentifySource((_DWORD *)(v2 + 56LL * v4), a1, v33);
        WriteDbgTraceErrorGpd((__int64)"BevaluateMacros", "expected openbrace to follow *BlockMacros keyword.");
        goto LABEL_67;
      }
      if ( v17 != 12 )
      {
        if ( v17 == 13 )
        {
          v21 = *(unsigned int *)(a1 + 516);
          if ( (unsigned int)v21 < *(_DWORD *)(a1 + 512) )
          {
            v42 = *(_DWORD *)(a1 + 516);
            *(_DWORD *)(a1 + 516) = v21 + 1;
            v22 = 56 * v21;
            *(_OWORD *)(v22 + v1) = *(_OWORD *)(56LL * v4 + v2);
            *(_OWORD *)(v22 + v1 + 16) = *(_OWORD *)(56LL * v4 + v2 + 16);
            *(_OWORD *)(v22 + v1 + 32) = *(_OWORD *)(56LL * v4 + v2 + 32);
            *(_QWORD *)(v22 + v1 + 48) = *(_QWORD *)(56LL * v4 + v2 + 48);
            v23 = 0;
LABEL_36:
            BIncreaseMacroLevel(v23, a1);
            goto LABEL_19;
          }
LABEL_51:
          WriteDbgTraceErrorGpd(
            (__int64)"BallocElementFromMasterTable",
            "BallocElementFromMasterTable: Out of array elements - restart.",
            &mMainKeywordTable);
          if ( *(int *)(a1 + 2220) < 2 )
          {
            *(_DWORD *)(a1 + 2224) = 2;
            *(_DWORD *)(a1 + 2216) = 21;
          }
LABEL_53:
          *(_DWORD *)(a1 + 2220) = 2;
          *(_DWORD *)(a1 + 2224) = 2;
          *(_DWORD *)(a1 + 2216) = 21;
          goto LABEL_19;
        }
        if ( v17 == 14 )
        {
          if ( (unsigned int)BallocElementFromMasterTable(21, &v42, (_DWORD *)a1) )
          {
            v19 = v42;
            v20 = 56LL * v42;
            *(_OWORD *)(v20 + v1) = *(_OWORD *)(56LL * v4 + v2);
            *(_OWORD *)(v20 + v1 + 16) = *(_OWORD *)(56LL * v4 + v2 + 16);
            *(_OWORD *)(v20 + v1 + 32) = *(_OWORD *)(56LL * v4 + v2 + 32);
            *(_QWORD *)(v20 + v1 + 48) = *(_QWORD *)(56LL * v4 + v2 + 48);
            BDecreaseMacroLevel(v1, v19, a1);
            goto LABEL_19;
          }
          goto LABEL_53;
        }
        goto LABEL_8;
      }
      do
        ++v4;
      while ( *(_DWORD *)(56LL * v4 + v2) == 65280 );
      v38 = (_DWORD *)(v2 + 56LL * v4);
      if ( *v38 >= 0xFF00u
        || (v39 = 4LL * (unsigned int)*v38, LODWORD((&mMainKeywordTable)[v39 + 2]))
        || *((_DWORD *)&mMainKeywordTable + 2 * v39 + 5) != 13 )
      {
        vIdentifySource(v38, a1, (__int64)&mMainKeywordTable);
        WriteDbgTraceErrorGpd((__int64)"BevaluateMacros", "expected openbrace to follow *Macros keyword.");
LABEL_67:
        *(_DWORD *)(a1 + 2224) = 1;
        *(_DWORD *)(a1 + 2220) = 3;
        goto LABEL_19;
      }
      v3 = 1;
    }
LABEL_19:
    ++v4;
  }
  v24 = 0;
  v25 = *(_QWORD *)(a1 + 528);
  for ( i = *(_QWORD *)(a1 + 552);
        v24 < *(_DWORD *)(a1 + 564);
        *(_DWORD *)(56LL * *(unsigned int *)(i + 8 * v27 + 4) + v1) = 65280 )
  {
    v27 = v24++;
  }
  for ( j = 0; (unsigned int)j < *(_DWORD *)(a1 + 540); j = (unsigned int)(j + 1) )
  {
    v29 = *(_DWORD *)(v25 + 12LL * (unsigned int)j + 8);
    for ( k = *(_DWORD *)(v25 + 12LL * (unsigned int)j + 4); k <= v29; ++k )
    {
      v31 = 56LL * k;
      *(_DWORD *)(v31 + v1) = 65280;
    }
  }
  if ( *(_DWORD *)(a1 + 588) )
  {
    WriteDbgTraceErrorGpd((__int64)"BevaluateMacros", "Too few closing braces.  Fatal syntax error.", j);
    *(_DWORD *)(a1 + 2220) = 3;
    *(_DWORD *)(a1 + 2224) = 1;
    return 0;
  }
  if ( !(unsigned int)BallocElementFromMasterTable(21, &v42, (_DWORD *)a1) )
  {
    *(_DWORD *)(a1 + 2220) = 2;
    *(_DWORD *)(a1 + 2224) = 2;
    *(_DWORD *)(a1 + 2216) = 21;
    return 0;
  }
  v40 = 56LL * v42;
  result = 0;
  *(_OWORD *)(v40 + v1) = *(_OWORD *)v7;
  *(_OWORD *)(v40 + v1 + 16) = *(_OWORD *)(v7 + 16);
  *(_OWORD *)(v40 + v1 + 32) = *(_OWORD *)(v7 + 32);
  *(_QWORD *)(v40 + v1 + 48) = *(_QWORD *)(v7 + 48);
  v41 = 0;
  if ( *(int *)(a1 + 2220) < 2 )
  {
    LOBYTE(v41) = *(_DWORD *)(a1 + 612) == 0;
    return v41;
  }
  return result;
}

```

## disassembly

```asm
0x1800093b0  mov     rax, rsp
0x1800093b3  push    rbx
0x1800093b4  push    rbp
0x1800093b5  push    rsi
0x1800093b6  push    rdi
0x1800093b7  push    r12
0x1800093b9  push    r13
0x1800093bb  push    r14
0x1800093bd  push    r15
0x1800093bf  sub     rsp, 38h
0x1800093c3  mov     rbp, [rcx+1F8h]
0x1800093ca  lea     r8, mMainKeywordTable
0x1800093d1  mov     r14, [rcx+1E0h]
0x1800093d8  xor     r12d, r12d
0x1800093db  mov     [rax+8], r12d
0x1800093df  mov     r13d, r12d
0x1800093e2  mov     [rcx+24Ch], r12d
0x1800093e9  mov     esi, r12d
0x1800093ec  mov     [rcx+234h], r12d
0x1800093f3  mov     rbx, rcx
0x1800093f6  mov     [rcx+21Ch], r12d
0x1800093fd  cmp     dword ptr [rbx+8ACh], 2
0x180009404  jge     loc_180009837
0x18000940a  mov     r15d, esi
0x18000940d  imul    rdx, r15, 38h ; '8'
0x180009411  lea     rdi, [rdx+r14]
0x180009415  mov     ecx, [rdi]
0x180009417  cmp     ecx, [rbx+8B8h]
0x18000941d  jz      loc_180009628
0x180009423  mov     eax, ecx
0x180009425  sub     eax, 0FF00h
0x18000942a  jz      loc_1800095C1
0x180009430  cmp     eax, 3
0x180009433  jz      loc_18000978E
0x180009439  test    r13d, r13d
0x18000943c  jnz     loc_180009524
0x180009442  lea     eax, [rcx-0FF01h]
0x180009448  cmp     eax, 1
0x18000944b  ja      loc_1800095C8
0x180009451  mov     edx, [rbx+204h]
0x180009457  cmp     edx, [rbx+200h]
0x18000945d  jnb     loc_18000984B
0x180009463  lea     eax, [rdx+1]
0x180009466  mov     [rsp+78h+arg_0], edx
0x18000946d  mov     [rbx+204h], eax
0x180009473  imul    rax, r15, 38h ; '8'
0x180009477  imul    rdi, rdx, 38h ; '8'
0x18000947b  movups  xmm0, xmmword ptr [rax+r14]
0x180009480  add     rdi, rbp
0x180009483  movups  xmmword ptr [rdi], xmm0
0x180009486  movups  xmm1, xmmword ptr [rax+r14+10h]
0x18000948c  movups  xmmword ptr [rdi+10h], xmm1
0x180009490  movups  xmm0, xmmword ptr [rax+r14+20h]
0x180009496  movups  xmmword ptr [rdi+20h], xmm0
0x18000949a  movsd   xmm1, qword ptr [rax+r14+30h]
0x1800094a1  imul    rax, r15, 38h ; '8'
0x1800094a5  movsd   qword ptr [rdi+30h], xmm1
0x1800094aa  test    byte ptr [rax+r14+34h], 20h
0x1800094b0  jz      loc_1800095C1
0x1800094b6  mov     r8, rbx
0x1800094b9  mov     rcx, rbp
0x1800094bc  call    BResolveValueMacroReference
0x1800094c1  test    eax, eax
0x1800094c3  jz      loc_180009A5F
0x1800094c9  cmp     dword ptr [rbx+8B4h], 4
0x1800094d0  jb      loc_1800095BA
0x1800094d6  lea     rdx, aEnumerateValue; "Enumerate ValueMacro Reference at:"
0x1800094dd  lea     rcx, aBevaluatemacro; "BevaluateMacros"
0x1800094e4  call    WriteDbgTraceErrorGpd
0x1800094e9  mov     rdx, rbx
0x1800094ec  mov     rcx, rdi
0x1800094ef  call    vIdentifySource
0x1800094f4  mov     rax, [rdi+18h]
0x1800094f8  lea     rdx, a0S0S; "    %0.*s : %0.*s"
0x1800094ff  mov     r9, [rdi+8]
0x180009503  lea     rcx, aBevaluatemacro; "BevaluateMacros"
0x18000950a  mov     r8d, [rdi+10h]
0x18000950e  mov     [rsp+78h+var_50], rax
0x180009513  mov     eax, [rdi+20h]
0x180009516  mov     [rsp+78h+var_58], eax
0x18000951a  call    WriteDbgTraceErrorGpd
0x18000951f  jmp     loc_1800095BA
0x180009524  cmp     ecx, 0FF01h
0x18000952a  jz      loc_18000976B
0x180009530  cmp     ecx, 0FF02h
0x180009536  jnz     loc_180009759
0x18000953c  mov     edi, [rbx+204h]
0x180009542  cmp     edi, [rbx+200h]
0x180009548  jnb     loc_18000984B
0x18000954e  imul    r15, rdi, 38h ; '8'
0x180009552  lea     eax, [rdi+1]
0x180009555  mov     [rsp+78h+arg_0], edi
0x18000955c  mov     [rbx+204h], eax
0x180009562  lea     r12, [rdx+r14]
0x180009566  movups  xmm0, xmmword ptr [rdx+r14]
0x18000956b  mov     r8, rbx
0x18000956e  mov     rcx, rbp
0x180009571  movups  xmmword ptr [r15+rbp], xmm0
0x180009576  movups  xmm1, xmmword ptr [rdx+r14+10h]
0x18000957c  movups  xmmword ptr [r15+rbp+10h], xmm1
0x180009582  movups  xmm0, xmmword ptr [rdx+r14+20h]
0x180009588  movups  xmmword ptr [r15+rbp+20h], xmm0
0x18000958e  movsd   xmm1, qword ptr [rdx+r14+30h]
0x180009595  mov     edx, edi
0x180009597  movsd   qword ptr [r15+rbp+30h], xmm1
0x18000959e  call    BDefineValueMacroName
0x1800095a3  test    eax, eax
0x1800095a5  jz      loc_18000989E
0x1800095ab  test    byte ptr [r12+34h], 20h
0x1800095b1  jnz     loc_180009727
0x1800095b7  xor     r12d, r12d
0x1800095ba  lea     r8, mMainKeywordTable
0x1800095c1  inc     esi
0x1800095c3  jmp     loc_1800093FD
0x1800095c8  mov     rax, rcx
0x1800095cb  shl     rax, 5
0x1800095cf  mov     edx, [rax+r8+10h]
0x1800095d4  mov     ecx, [rax+r8+14h]
0x1800095d9  test    edx, edx
0x1800095db  jz      short loc_18000963A
0x1800095dd  cmp     edx, 2
0x1800095e0  jnz     loc_180009451
0x1800095e6  cmp     ecx, 0Bh
0x1800095e9  jnz     loc_180009451
0x1800095ef  test    byte ptr [rdi+34h], 20h
0x1800095f3  jz      loc_180009A3C
0x1800095f9  mov     r8, rbx
0x1800095fc  mov     edx, esi
0x1800095fe  mov     rcx, r14
0x180009601  call    BResolveBlockMacroReference
0x180009606  test    eax, eax
0x180009608  jnz     short loc_1800095BA
0x18000960a  mov     rdx, rbx
0x18000960d  mov     rcx, rdi
0x180009610  call    vIdentifySource
0x180009615  lea     rdx, aInsertblockmac; "   *InsertBlockMacro Construct ignored."
0x18000961c  lea     rcx, aBevaluatemacro; "BevaluateMacros"
0x180009623  call    WriteDbgTraceErrorGpd
0x180009628  mov     r8, rbx
0x18000962b  mov     edx, 1
0x180009630  mov     rcx, rdi
0x180009633  call    VIgnoreBlock
0x180009638  jmp     short loc_1800095BA
0x18000963a  cmp     ecx, 0Bh
0x18000963d  jz      loc_1800098DD
0x180009643  cmp     ecx, 0Ch
0x180009646  jz      loc_1800099F9
0x18000964c  cmp     ecx, 0Dh
0x18000964f  jz      short loc_1800096C2
0x180009651  cmp     ecx, 0Eh
0x180009654  jnz     loc_180009451
0x18000965a  mov     r8, rbx
0x18000965d  lea     rdx, [rsp+78h+arg_0]
0x180009665  mov     ecx, 15h
0x18000966a  call    BallocElementFromMasterTable
0x18000966f  test    eax, eax
0x180009671  jz      loc_18000987B
0x180009677  mov     edx, [rsp+78h+arg_0]
0x18000967e  imul    r8, r15, 38h ; '8'
0x180009682  imul    rcx, rdx, 38h ; '8'
0x180009686  movups  xmm0, xmmword ptr [r8+r14]
0x18000968b  movups  xmmword ptr [rcx+rbp], xmm0
0x18000968f  movups  xmm1, xmmword ptr [r8+r14+10h]
0x180009695  movups  xmmword ptr [rcx+rbp+10h], xmm1
0x18000969a  movups  xmm0, xmmword ptr [r8+r14+20h]
0x1800096a0  movups  xmmword ptr [rcx+rbp+20h], xmm0
0x1800096a5  movsd   xmm1, qword ptr [r8+r14+30h]
0x1800096ac  mov     r8, rbx
0x1800096af  movsd   qword ptr [rcx+rbp+30h], xmm1
0x1800096b5  mov     rcx, rbp
0x1800096b8  call    BDecreaseMacroLevel
0x1800096bd  jmp     loc_1800095BA
0x1800096c2  mov     ecx, [rbx+204h]
0x1800096c8  cmp     ecx, [rbx+200h]
0x1800096ce  jnb     loc_18000984B
0x1800096d4  imul    rdx, r15, 38h ; '8'
0x1800096d8  lea     eax, [rcx+1]
0x1800096db  mov     [rsp+78h+arg_0], ecx
0x1800096e2  mov     [rbx+204h], eax
0x1800096e8  imul    rcx, 38h ; '8'
0x1800096ec  movups  xmm0, xmmword ptr [rdx+r14]
0x1800096f1  movups  xmmword ptr [rcx+rbp], xmm0
0x1800096f5  movups  xmm1, xmmword ptr [rdx+r14+10h]
0x1800096fb  movups  xmmword ptr [rcx+rbp+10h], xmm1
0x180009700  movups  xmm0, xmmword ptr [rdx+r14+20h]
0x180009706  movups  xmmword ptr [rcx+rbp+20h], xmm0
0x18000970b  movsd   xmm1, qword ptr [rdx+r14+30h]
0x180009712  movsd   qword ptr [rcx+rbp+30h], xmm1
0x180009718  xor     ecx, ecx
0x18000971a  mov     rdx, rbx
0x18000971d  call    BIncreaseMacroLevel
0x180009722  jmp     loc_1800095BA
0x180009727  mov     r8, rbx
0x18000972a  mov     edx, edi
0x18000972c  mov     rcx, rbp
0x18000972f  call    BResolveValueMacroReference
0x180009734  xor     r12d, r12d
0x180009737  lea     r8, mMainKeywordTable
0x18000973e  test    eax, eax
0x180009740  jnz     loc_1800095C1
0x180009746  mov     dword ptr [r15+rbp], 0FF00h
0x18000974e  dec     dword ptr [rbx+234h]
0x180009754  jmp     loc_1800095C1
0x180009759  mov     rax, rcx
0x18000975c  shl     rax, 5
0x180009760  cmp     [rax+r8+10h], r12d
0x180009765  jz      loc_1800098C9
0x18000976b  mov     rdx, rbx
0x18000976e  mov     rcx, rdi
0x180009771  call    vIdentifySource
0x180009776  lea     rdx, aOnlyValuemacro; "Only valueMacroDefinitions permitted wi"...
0x18000977d  lea     rcx, aBevaluatemacro; "BevaluateMacros"
0x180009784  call    WriteDbgTraceErrorGpd
0x180009789  jmp     loc_1800095BA
0x18000978e  mov     edx, r12d
0x180009791  mov     r10, [rbx+210h]
0x180009798  mov     r8, [rbx+228h]
0x18000979f  cmp     [rbx+234h], r12d
0x1800097a6  jbe     short loc_1800097C4
0x1800097a8  mov     eax, edx
0x1800097aa  inc     edx
0x1800097ac  mov     ecx, [r8+rax*8+4]
0x1800097b1  imul    rax, rcx, 38h ; '8'
0x1800097b5  mov     dword ptr [rax+rbp], 0FF00h
0x1800097bc  cmp     edx, [rbx+234h]
0x1800097c2  jb      short loc_1800097A8
0x1800097c4  mov     r8d, r12d
0x1800097c7  cmp     [rbx+21Ch], r12d
0x1800097ce  jbe     short loc_180009803
0x1800097d0  mov     eax, r8d
0x1800097d3  lea     rcx, [rax+rax*2]
0x1800097d7  mov     r9d, [r10+rcx*4+8]
0x1800097dc  mov     edx, [r10+rcx*4+4]
0x1800097e1  jmp     short loc_1800097F2
0x1800097e3  mov     eax, edx
0x1800097e5  imul    rcx, rax, 38h ; '8'
0x1800097e9  inc     edx
0x1800097eb  mov     dword ptr [rcx+rbp], 0FF00h
0x1800097f2  cmp     edx, r9d
0x1800097f5  jbe     short loc_1800097E3
0x1800097f7  inc     r8d
0x1800097fa  cmp     r8d, [rbx+21Ch]
0x180009801  jb      short loc_1800097D0
0x180009803  cmp     [rbx+24Ch], r12d
0x18000980a  jz      loc_180009A6A
0x180009810  lea     rdx, aTooFewClosingB; "Too few closing braces.  Fatal syntax e"...
0x180009817  lea     rcx, aBevaluatemacro; "BevaluateMacros"
0x18000981e  call    WriteDbgTraceErrorGpd
0x180009823  mov     dword ptr [rbx+8ACh], 3
0x18000982d  mov     dword ptr [rbx+8B0h], 1
0x180009837  xor     eax, eax
0x180009839  add     rsp, 38h
0x18000983d  pop     r15
0x18000983f  pop     r14
0x180009841  pop     r13
0x180009843  pop     r12
0x180009845  pop     rdi
0x180009846  pop     rsi
0x180009847  pop     rbp
0x180009848  pop     rbx
0x180009849  retn
0x18000984b  lea     rdx, aBallocelementf; "BallocElementFromMasterTable: Out of ar"...
0x180009852  lea     rcx, aBallocelementf_0; "BallocElementFromMasterTable"
0x180009859  call    WriteDbgTraceErrorGpd
0x18000985e  cmp     dword ptr [rbx+8ACh], 2
0x180009865  jge     short loc_18000987B
0x180009867  mov     dword ptr [rbx+8B0h], 2
0x180009871  mov     dword ptr [rbx+8A8h], 15h
0x18000987b  mov     dword ptr [rbx+8ACh], 2
0x180009885  mov     dword ptr [rbx+8B0h], 2
0x18000988f  mov     dword ptr [rbx+8A8h], 15h
0x180009899  jmp     loc_1800095BA
0x18000989e  mov     rdx, rbx
0x1800098a1  mov     dword ptr [r15+rbp], 0FF00h
0x1800098a9  mov     rcx, r12
0x1800098ac  call    vIdentifySource
0x1800098b1  lea     rdx, aInternalErrorV; "Internal Error: valueMacro name registr"...
0x1800098b8  lea     rcx, aBevaluatemacro; "BevaluateMacros"
0x1800098bf  call    WriteDbgTraceErrorGpd
0x1800098c4  jmp     loc_1800095B7
0x1800098c9  cmp     dword ptr [rax+r8+14h], 0Eh
0x1800098cf  jnz     loc_18000976B
0x1800098d5  mov     r13d, r12d
0x1800098d8  jmp     loc_1800095C1
0x1800098dd  mov     r8, rbx
0x1800098e0  mov     edx, esi
0x1800098e2  mov     rcx, r14
0x1800098e5  call    BDefineBlockMacroName
0x1800098ea  test    eax, eax
0x1800098ec  jnz     short loc_180009905
0x1800098ee  mov     rdx, rbx
0x1800098f1  mov     rcx, rdi
0x1800098f4  call    vIdentifySource
0x1800098f9  lea     rdx, aInternalErrorB_4; "Internal Error: blockMacro name registr"...
0x180009900  jmp     loc_18000977D
0x180009905  mov     edx, 0FF00h
0x18000990a  inc     esi
0x18000990c  mov     eax, esi
0x18000990e  imul    rcx, rax, 38h ; '8'
0x180009912  cmp     [rcx+r14], edx
  ... truncated ...
```
