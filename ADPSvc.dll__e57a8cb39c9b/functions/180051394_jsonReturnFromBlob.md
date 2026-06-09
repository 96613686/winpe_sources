# jsonReturnFromBlob

- ea: `0x180051394`
- end: `0x180051821`
- name: `jsonReturnFromBlob`
- size: `1165`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config`

## callers

- `0x18004e6b0`
- `0x18004f190`

## callees

- `0x180051394`
- `0x180051b04`
- `0x180053498`
- `0x1800539e0`
- `0x180066588`
- `0x180068bdc`
- `0x1800716fc`
- `0x1800717b0`
- `0x180071aac`
- `0x180071b08`
- `0x180080b94`
- `0x18009b310`
- `0x18009b4ec`
- `0x1800ab280`
- `0x1800b4828`
- `0x1800b58d0`

## string_xrefs

- `0x18005165c`: `malformed JSON`

## pseudocode

```c
__int64 __fastcall jsonReturnFromBlob(char **a1, __int64 a2, _QWORD *a3, int a4)
{
  __int64 v4; // rbx
  __int64 v6; // r12
  int v9; // eax
  char *v10; // r9
  int v11; // r14d
  __int64 v12; // rcx
  __int64 v13; // r8
  char *v14; // rdx
  unsigned int v15; // ecx
  unsigned int v16; // ecx
  unsigned int v17; // ecx
  unsigned int v18; // ecx
  unsigned int v19; // ecx
  signed int v20; // ebx
  __int64 v21; // rdx
  __int64 v22; // r14
  __int64 v23; // rax
  __int64 v24; // r9
  __int64 v25; // r8
  int v26; // ebx
  __int64 result; // rax
  int v28; // r13d
  char *v29; // rax
  unsigned __int64 v30; // rcx
  __int64 v31; // r8
  unsigned __int64 v32; // rdx
  __int64 v33; // rcx
  unsigned int v34; // ecx
  unsigned int v35; // ecx
  unsigned int v36; // ecx
  unsigned int v37; // ecx
  unsigned int v38; // r8d
  unsigned int v39; // r13d
  __int64 v40; // rcx
  __int64 v41; // rax
  int v42; // r9d
  __int64 v43; // r15
  __int64 v44; // rbx
  char *v45; // r12
  int v46; // r14d
  char *v47; // rcx
  int v48; // eax
  unsigned int v49; // edx
  __int64 v50; // rbx
  __int64 v51; // rbx
  unsigned __int64 v52; // [rsp+30h] [rbp-20h] BYREF
  __int64 v53; // [rsp+38h] [rbp-18h]
  char *v54; // [rsp+40h] [rbp-10h]
  unsigned int v56; // [rsp+A0h] [rbp+50h] BYREF

  v4 = *a3;
  v6 = (unsigned int)a2;
  v56 = 0;
  v9 = jsonbPayloadSize(a1, a2, &v56);
  v11 = v9;
  if ( !v9 )
  {
    v12 = v4;
LABEL_57:
    *((_DWORD *)a3 + 9) = 1;
    LOBYTE(v10) = 1;
    return sqlite3VdbeMemSetStr(v12, "malformed JSON", -1, v10, -1);
  }
  v10 = *a1;
  v13 = *(_QWORD *)(v4 + 24);
  v53 = v13;
  v54 = v10;
  v14 = &v10[v6];
  v15 = v10[v6] & 0xF;
  if ( v15 > 6 )
  {
    v34 = v15 - 7;
    if ( !v34 )
      goto LABEL_82;
    v35 = v34 - 1;
    if ( v35 )
    {
      v36 = v35 - 1;
      if ( v36 )
      {
        v37 = v36 - 1;
        if ( v37 )
        {
          if ( v37 - 1 >= 2 )
            goto LABEL_56;
          if ( a4 || (*(_BYTE *)(a3[1] + 8LL) & 8) == 0 )
            return jsonReturnTextJsonFromBlob(a3, v14, v9 + v56);
          v38 = v9 + v56;
          LODWORD(v10) = 0;
          return setResultStrOrError((_DWORD)a3, (_DWORD)v14, v38, (_DWORD)v10, -1);
        }
LABEL_82:
        v38 = v56;
        LODWORD(v14) = (_DWORD)v10 + v9 + v6;
        LOBYTE(v10) = 1;
        return setResultStrOrError((_DWORD)a3, (_DWORD)v14, v38, (_DWORD)v10, -1);
      }
    }
    v39 = v56;
    v40 = v56 + 1;
    if ( v13 )
      v41 = sqlite3DbMallocRawNN(v13, (unsigned int)v40);
    else
      v41 = sqlite3Malloc(v40);
    v43 = v41;
    if ( !v41 )
      return sqlite3_result_error_nomem(a3);
    v44 = 0;
    v45 = &v54[(unsigned int)(v11 + v6)];
    v46 = 0;
    if ( !v39 )
    {
LABEL_81:
      *(_BYTE *)(v44 + v43) = 0;
      LOBYTE(v42) = 1;
      return setResultStrOrError((_DWORD)a3, v43, v44, v42, (__int64)sqlite3OomClear);
    }
    while ( 1 )
    {
      v47 = &v45[v46];
      if ( *v47 != 92 )
      {
        *(_BYTE *)(v44 + v43) = *v47;
        v44 = (unsigned int)(v44 + 1);
        goto LABEL_80;
      }
      v56 = 0;
      v48 = jsonUnescapeOneChar(v47, v39 - v46, &v56);
      v49 = v56;
      if ( v56 <= 0x7F )
        goto LABEL_77;
      if ( v56 <= 0x7FF )
        break;
      if ( v56 < 0x10000 )
      {
        *(_BYTE *)(v44 + v43) = (v56 >> 12) | 0xE0;
        v44 = (unsigned int)(v44 + 1);
        *(_BYTE *)(v44 + v43) = (v49 >> 6) & 0x3F | 0x80;
        goto LABEL_72;
      }
      if ( v56 != 629145 )
      {
        *(_BYTE *)(v44 + v43) = (v56 >> 18) | 0xF0;
        v50 = (unsigned int)(v44 + 1);
        *(_BYTE *)(v50 + v43) = (v49 >> 12) & 0x3F | 0x80;
        v51 = (unsigned int)(v50 + 1);
        *(_BYTE *)(v51 + v43) = (v49 >> 6) & 0x3F | 0x80;
        v44 = (unsigned int)(v51 + 1);
        LOBYTE(v49) = v49 & 0x3F | 0x80;
        goto LABEL_77;
      }
LABEL_78:
      v46 = v48 + v46 - 1;
LABEL_80:
      if ( ++v46 >= v39 )
        goto LABEL_81;
    }
    *(_BYTE *)(v44 + v43) = (v56 >> 6) | 0xC0;
LABEL_72:
    v44 = (unsigned int)(v44 + 1);
    LOBYTE(v49) = v49 & 0x3F | 0x80;
LABEL_77:
    *(_BYTE *)(v44 + v43) = v49;
    v44 = (unsigned int)(v44 + 1);
    goto LABEL_78;
  }
  if ( v15 == 6 )
  {
LABEL_11:
    v20 = v56;
    v52 = 0;
    if ( v56 )
      goto LABEL_12;
LABEL_56:
    v12 = *a3;
    goto LABEL_57;
  }
  if ( (v10[v6] & 0xF) != 0 )
  {
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
            if ( v19 != 1 )
              goto LABEL_56;
            goto LABEL_11;
          }
        }
        v20 = v56;
        v52 = 0;
        if ( !v56 )
          goto LABEL_56;
        v28 = 0;
        if ( v10[(unsigned int)(v6 + v9)] == 45 )
        {
          if ( v56 < 2 )
            goto LABEL_56;
          v11 = v9 + 1;
          v28 = 1;
          v20 = v56 - 1;
        }
        v29 = (char *)sqlite3DbStrNDup(v53, &v10[(unsigned int)(v11 + v6)], v20);
        v54 = v29;
        if ( v29 )
        {
          v56 = sqlite3DecOrHexToI64(v29);
          sqlite3DbFreeNN(v53);
          switch ( v56 )
          {
            case 0u:
              v30 = v52;
              if ( v28 )
                v30 = -(__int64)v52;
              v31 = *a3;
              result = 36864;
              if ( (*(_WORD *)(*a3 + 20LL) & 0x9000) == 0 )
              {
                *(_QWORD *)v31 = v30;
                *(_WORD *)(v31 + 20) = 4;
                return result;
              }
              v32 = v30;
              v33 = *a3;
              return vdbeReleaseAndSetInt64(v33, v32);
            case 3u:
              if ( v28 )
              {
                v33 = *a3;
                if ( (*(_WORD *)(*a3 + 20LL) & 0x9000) == 0 )
                {
                  result = 0x8000000000000000uLL;
                  *(_WORD *)(v33 + 20) = 4;
                  *(_QWORD *)v33 = 0x8000000000000000uLL;
                  return result;
                }
                v32 = 0x8000000000000000uLL;
                return vdbeReleaseAndSetInt64(v33, v32);
              }
              break;
            case 1u:
              goto LABEL_56;
            default:
              if ( v28 )
              {
                --v11;
                ++v20;
              }
              break;
          }
LABEL_12:
          v21 = (unsigned int)(v11 + v6);
          v22 = v53;
          v23 = sqlite3DbStrNDup(v53, &(*a1)[v21], v20);
          if ( v23 )
          {
            v25 = -1;
            do
              ++v25;
            while ( *(_BYTE *)(v23 + v25) );
            LOBYTE(v24) = 1;
            v26 = sqlite3AtoF(v23, &v52, v25 & 0x3FFFFFFF, v24);
            sqlite3DbFreeNN(v22);
            if ( v26 > 0 )
              return sqlite3VdbeMemSetDouble(*a3);
            goto LABEL_56;
          }
        }
        return sqlite3_result_error_nomem(a3);
      }
      if ( v56 )
        goto LABEL_56;
      result = 36864;
      if ( (*(_WORD *)(v4 + 20) & 0x9000) != 0 )
      {
        v32 = 0;
LABEL_40:
        v33 = v4;
        return vdbeReleaseAndSetInt64(v33, v32);
      }
      *(_QWORD *)v4 = 0;
    }
    else
    {
      if ( v56 )
        goto LABEL_56;
      result = 36864;
      if ( (*(_WORD *)(v4 + 20) & 0x9000) != 0 )
      {
        v32 = 1;
        goto LABEL_40;
      }
      *(_QWORD *)v4 = 1;
    }
    *(_WORD *)(v4 + 20) = 4;
    return result;
  }
  if ( v56 )
    goto LABEL_56;
  result = 36864;
  if ( (*(_WORD *)(v4 + 20) & 0x9000) != 0 )
    return vdbeMemClearExternAndSetNull(v4);
  *(_WORD *)(v4 + 20) = 1;
  return result;
}

```

## disassembly

```asm
0x180051394  mov     [rsp-38h+arg_8], rbx
0x180051399  mov     [rsp-38h+arg_0], rcx
0x18005139e  push    rbp
0x18005139f  push    rsi
0x1800513a0  push    rdi
0x1800513a1  push    r12
0x1800513a3  push    r13
0x1800513a5  push    r14
0x1800513a7  push    r15
0x1800513a9  mov     rbp, rsp
0x1800513ac  sub     rsp, 50h
0x1800513b0  mov     rbx, [r8]
0x1800513b3  mov     rsi, r8
0x1800513b6  lea     r8, [rbp+arg_10]
0x1800513ba  mov     r12d, edx
0x1800513bd  mov     r13d, r9d
0x1800513c0  mov     [rbp+arg_10], 0
0x1800513c7  mov     rdi, rcx
0x1800513ca  call    jsonbPayloadSize
0x1800513cf  xor     r10d, r10d
0x1800513d2  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800513d6  mov     r14d, eax
0x1800513d9  test    eax, eax
0x1800513db  jnz     short loc_1800513E8
0x1800513dd  lea     edi, [rax+1]
0x1800513e0  mov     rcx, rbx
0x1800513e3  jmp     loc_18005165C
0x1800513e8  mov     r9, [rdi]
0x1800513eb  mov     edi, 1
0x1800513f0  mov     r8, [rbx+18h]
0x1800513f4  mov     [rbp+var_18], r8
0x1800513f8  mov     [rbp+var_10], r9
0x1800513fc  lea     rdx, [r9+r12]
0x180051400  movzx   ecx, byte ptr [rdx]
0x180051403  and     ecx, 0Fh
0x180051406  cmp     ecx, 6
0x180051409  ja      loc_180051638
0x18005140f  jz      short loc_180051441
0x180051411  test    ecx, ecx
0x180051413  jz      loc_180051611
0x180051419  sub     ecx, edi
0x18005141b  jz      loc_1800515ED
0x180051421  sub     ecx, edi
0x180051423  jz      loc_1800515C9
0x180051429  sub     ecx, edi
0x18005142b  jz      loc_1800514C4
0x180051431  sub     ecx, edi
0x180051433  jz      loc_1800514C4
0x180051439  cmp     ecx, edi
0x18005143b  jnz     loc_180051659
0x180051441  mov     ebx, [rbp+arg_10]
0x180051444  xorps   xmm0, xmm0
0x180051447  movsd   [rbp+var_20], xmm0
0x18005144c  test    ebx, ebx
0x18005144e  jz      loc_180051659
0x180051454  mov     rax, [rbp+arg_0]
0x180051458  lea     edx, [r14+r12]
0x18005145c  mov     r14, [rbp+var_18]
0x180051460  movsxd  r8, ebx
0x180051463  mov     rcx, r14
0x180051466  add     rdx, [rax]
0x180051469  call    sqlite3DbStrNDup
0x18005146e  mov     r12, rax
0x180051471  test    rax, rax
0x180051474  jz      loc_1800516D3
0x18005147a  mov     r8, r15
0x18005147d  inc     r8
0x180051480  cmp     byte ptr [rax+r8], 0
0x180051485  jnz     short loc_18005147D
0x180051487  and     r8d, 3FFFFFFFh
0x18005148e  lea     rdx, [rbp+var_20]
0x180051492  mov     r9b, dil
0x180051495  mov     rcx, r12
0x180051498  call    sqlite3AtoF
0x18005149d  mov     rdx, r12
0x1800514a0  mov     rcx, r14
0x1800514a3  mov     ebx, eax
0x1800514a5  call    sqlite3DbFreeNN
0x1800514aa  test    ebx, ebx
0x1800514ac  jle     loc_180051659
0x1800514b2  movsd   xmm1, [rbp+var_20]
0x1800514b7  mov     rcx, [rsi]
0x1800514ba  call    sqlite3VdbeMemSetDouble
0x1800514bf  jmp     loc_180051809
0x1800514c4  mov     ebx, [rbp+arg_10]
0x1800514c7  mov     [rbp+var_20], r10
0x1800514cb  test    ebx, ebx
0x1800514cd  jz      loc_180051659
0x1800514d3  add     eax, r12d
0x1800514d6  mov     r13d, r10d
0x1800514d9  cmp     byte ptr [rax+r9], 2Dh ; '-'
0x1800514de  jnz     short loc_1800514F1
0x1800514e0  cmp     ebx, 2
0x1800514e3  jb      loc_180051659
0x1800514e9  add     r14d, edi
0x1800514ec  mov     r13d, edi
0x1800514ef  dec     ebx
0x1800514f1  mov     rcx, [rbp+var_18]
0x1800514f5  lea     edx, [r14+r12]
0x1800514f9  add     rdx, r9
0x1800514fc  movsxd  r8, ebx
0x1800514ff  call    sqlite3DbStrNDup
0x180051504  mov     [rbp+var_10], rax
0x180051508  test    rax, rax
0x18005150b  jz      loc_1800516D3
0x180051511  lea     rdx, [rbp+var_20]
0x180051515  mov     rcx, rax; Str
0x180051518  call    sqlite3DecOrHexToI64
0x18005151d  mov     rdx, [rbp+var_10]
0x180051521  mov     rcx, [rbp+var_18]
0x180051525  mov     [rbp+arg_10], eax
0x180051528  call    sqlite3DbFreeNN
0x18005152d  mov     eax, [rbp+arg_10]
0x180051530  test    eax, eax
0x180051532  jnz     short loc_18005156E
0x180051534  mov     rcx, [rbp+var_20]
0x180051538  test    r13d, r13d
0x18005153b  jz      short loc_180051540
0x18005153d  neg     rcx
0x180051540  mov     r8, [rsi]
0x180051543  mov     eax, 9000h
0x180051548  test    [r8+14h], ax
0x18005154d  jz      short loc_18005155F
0x18005154f  mov     rdx, rcx
0x180051552  mov     rcx, r8
0x180051555  call    vdbeReleaseAndSetInt64
0x18005155a  jmp     loc_180051809
0x18005155f  mov     [r8], rcx
0x180051562  mov     word ptr [r8+14h], 4
0x180051569  jmp     loc_180051809
0x18005156e  cmp     eax, 3
0x180051571  jnz     short loc_1800515AE
0x180051573  test    r13d, r13d
0x180051576  jz      loc_180051454
0x18005157c  mov     rcx, [rsi]
0x18005157f  mov     eax, 9000h
0x180051584  test    [rcx+14h], ax
0x180051588  jz      short loc_180051596
0x18005158a  mov     rdx, 8000000000000000h
0x180051594  jmp     short loc_180051555
0x180051596  mov     rax, 8000000000000000h
0x1800515a0  mov     word ptr [rcx+14h], 4
0x1800515a6  mov     [rcx], rax
0x1800515a9  jmp     loc_180051809
0x1800515ae  cmp     eax, edi
0x1800515b0  jz      loc_180051659
0x1800515b6  test    r13d, r13d
0x1800515b9  jz      loc_180051454
0x1800515bf  dec     r14d
0x1800515c2  add     ebx, edi
0x1800515c4  jmp     loc_180051454
0x1800515c9  cmp     [rbp+arg_10], r10d
0x1800515cd  jnz     loc_180051659
0x1800515d3  mov     eax, 9000h
0x1800515d8  test    [rbx+14h], ax
0x1800515dc  jz      short loc_1800515E8
0x1800515de  xor     edx, edx
0x1800515e0  mov     rcx, rbx
0x1800515e3  jmp     loc_180051555
0x1800515e8  mov     [rbx], r10
0x1800515eb  jmp     short loc_180051606
0x1800515ed  cmp     [rbp+arg_10], r10d
0x1800515f1  jnz     short loc_180051659
0x1800515f3  mov     eax, 9000h
0x1800515f8  test    [rbx+14h], ax
0x1800515fc  jz      short loc_180051603
0x1800515fe  mov     rdx, rdi
0x180051601  jmp     short loc_1800515E0
0x180051603  mov     [rbx], rdi
0x180051606  mov     word ptr [rbx+14h], 4
0x18005160c  jmp     loc_180051809
0x180051611  cmp     [rbp+arg_10], r10d
0x180051615  jnz     short loc_180051659
0x180051617  mov     eax, 9000h
0x18005161c  test    [rbx+14h], ax
0x180051620  jz      short loc_18005162F
0x180051622  mov     rcx, rbx
0x180051625  call    vdbeMemClearExternAndSetNull
0x18005162a  jmp     loc_180051809
0x18005162f  mov     [rbx+14h], di
0x180051633  jmp     loc_180051809
0x180051638  sub     ecx, 7
0x18005163b  jz      loc_1800517EE
0x180051641  sub     ecx, edi
0x180051643  jz      short loc_1800516AD
0x180051645  sub     ecx, edi
0x180051647  jz      short loc_1800516AD
0x180051649  sub     ecx, edi
0x18005164b  jz      loc_1800517EE
0x180051651  sub     ecx, edi
0x180051653  jz      short loc_18005167B
0x180051655  cmp     ecx, edi
0x180051657  jz      short loc_18005167B
0x180051659  mov     rcx, [rsi]
0x18005165c  lea     rdx, aMalformedJson; "malformed JSON"
0x180051663  mov     [rsp+50h+var_30], r15
0x180051668  mov     r8, r15
0x18005166b  mov     [rsi+24h], edi
0x18005166e  mov     r9b, dil
0x180051671  call    sqlite3VdbeMemSetStr
0x180051676  jmp     loc_180051809
0x18005167b  test    r13d, r13d
0x18005167e  jnz     short loc_180051699
0x180051680  mov     rax, [rsi+8]
0x180051684  test    byte ptr [rax+8], 8
0x180051688  jz      short loc_180051699
0x18005168a  mov     r8d, [rbp+arg_10]
0x18005168e  add     r8d, r14d
0x180051691  xor     r9d, r9d
0x180051694  jmp     loc_1800517FC
0x180051699  mov     r8d, [rbp+arg_10]
0x18005169d  mov     rcx, rsi
0x1800516a0  add     r8d, r14d
0x1800516a3  call    jsonReturnTextJsonFromBlob
0x1800516a8  jmp     loc_180051809
0x1800516ad  mov     r13d, [rbp+arg_10]
0x1800516b1  lea     ecx, [r13+1]
0x1800516b5  test    r8, r8
0x1800516b8  jz      short loc_1800516C6
0x1800516ba  mov     edx, ecx
0x1800516bc  mov     rcx, r8
0x1800516bf  call    sqlite3DbMallocRawNN
0x1800516c4  jmp     short loc_1800516CB
0x1800516c6  call    sqlite3Malloc
0x1800516cb  mov     r15, rax
0x1800516ce  test    rax, rax
0x1800516d1  jnz     short loc_1800516E0
0x1800516d3  mov     rcx, rsi
0x1800516d6  call    sqlite3_result_error_nomem
0x1800516db  jmp     loc_180051809
0x1800516e0  add     r12d, r14d
0x1800516e3  xor     ebx, ebx
0x1800516e5  add     r12, [rbp+var_10]
0x1800516e9  xor     r14d, r14d
0x1800516ec  test    r13d, r13d
0x1800516ef  jz      loc_1800517D2
0x1800516f5  mov     ecx, r14d
0x1800516f8  add     rcx, r12
0x1800516fb  mov     dl, [rcx]
0x1800516fd  cmp     dl, 5Ch ; '\'
0x180051700  jnz     loc_1800517C0
0x180051706  mov     edx, r13d
0x180051709  mov     [rbp+arg_10], 0
0x180051710  sub     edx, r14d
0x180051713  lea     r8, [rbp+arg_10]
0x180051717  call    jsonUnescapeOneChar
0x18005171c  mov     edx, [rbp+arg_10]
0x18005171f  mov     r8d, eax
0x180051722  cmp     edx, 7Fh
0x180051725  jbe     loc_1800517B2
0x18005172b  cmp     edx, 7FFh
0x180051731  ja      short loc_180051749
0x180051733  mov     ecx, edx
0x180051735  shr     ecx, 6
0x180051738  or      cl, 0C0h
0x18005173b  mov     [rbx+r15], cl
0x18005173f  add     ebx, edi
0x180051741  and     dl, 3Fh
0x180051744  or      dl, 80h
0x180051747  jmp     short loc_1800517B2
0x180051749  cmp     edx, 10000h
0x18005174f  jnb     short loc_18005176E
0x180051751  mov     ecx, edx
0x180051753  mov     eax, edx
0x180051755  shr     ecx, 0Ch
0x180051758  or      cl, 0E0h
0x18005175b  shr     eax, 6
0x18005175e  mov     [rbx+r15], cl
0x180051762  and     al, 3Fh
0x180051764  add     ebx, edi
0x180051766  or      al, 80h
0x180051768  mov     [rbx+r15], al
0x18005176c  jmp     short loc_18005173F
0x18005176e  cmp     edx, 99999h
0x180051774  jz      short loc_1800517B8
0x180051776  mov     ecx, edx
0x180051778  mov     eax, edx
0x18005177a  shr     eax, 0Ch
0x18005177d  mov     r9b, 3Fh ; '?'
0x180051780  and     al, r9b
0x180051783  shr     ecx, 12h
0x180051786  mov     r10b, 80h
0x180051789  or      cl, 0F0h
0x18005178c  or      al, r10b
0x18005178f  mov     [rbx+r15], cl
0x180051793  add     ebx, edi
0x180051795  mov     [rbx+r15], al
0x180051799  mov     eax, edx
0x18005179b  shr     eax, 6
0x18005179e  add     ebx, edi
0x1800517a0  and     al, r9b
0x1800517a3  and     dl, r9b
0x1800517a6  or      al, r10b
0x1800517a9  mov     [rbx+r15], al
0x1800517ad  add     ebx, edi
0x1800517af  or      dl, r10b
0x1800517b2  mov     [rbx+r15], dl
0x1800517b6  add     ebx, edi
0x1800517b8  dec     r14d
0x1800517bb  add     r14d, r8d
  ... truncated ...
```
