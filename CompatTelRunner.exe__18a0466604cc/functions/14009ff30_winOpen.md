# winOpen

- ea: `0x14009ff30`
- end: `0x1400a02c6`
- name: `winOpen`
- size: `918`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1400a02cc`

## callees

- `0x140001ba0`
- `0x1400026c0`
- `0x1400504f4`
- `0x14008ac90`
- `0x14008f690`
- `0x14009e7b0`
- `0x14009f404`
- `0x14009fa4c`
- `0x14009fb28`
- `0x14009ff30`
- `0x1400a07a8`
- `0x1400a1544`
- `0x1400a8010`

## string_xrefs

- `0x1400a01ce`: `winOpen`

## pseudocode

```c
__int64 __fastcall winOpen(__int64 a1, __int64 a2, __int64 **a3, unsigned int a4, _DWORD *a5)
{
  __int64 **v5; // rbx
  __int64 v7; // r12
  __int64 v8; // r14
  __int64 v9; // rsi
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 result; // rax
  __int64 v13; // rax
  __int64 v14; // r14
  int v15; // r15d
  int v16; // r13d
  int v17; // eax
  unsigned int v18; // r12d
  __int64 v19; // rsi
  unsigned int v20; // edx
  __int64 v21; // rbx
  int v22; // edi
  int v23; // eax
  __int64 v24; // r13
  unsigned int v25; // edi
  __int64 v26; // rsi
  int v27; // edx
  int v28; // r9d
  __int64 **v29; // r15
  __int64 *v30; // rax
  unsigned int v31; // [rsp+40h] [rbp-81h] BYREF
  int v32; // [rsp+44h] [rbp-7Dh] BYREF
  unsigned int v33; // [rsp+48h] [rbp-79h] BYREF
  int v34; // [rsp+4Ch] [rbp-75h] BYREF
  __int64 v35; // [rsp+50h] [rbp-71h]
  unsigned int v36; // [rsp+58h] [rbp-69h]
  unsigned int v37; // [rsp+5Ch] [rbp-65h]
  int v38; // [rsp+60h] [rbp-61h]
  int v39; // [rsp+64h] [rbp-5Dh]
  __int64 v40; // [rsp+68h] [rbp-59h] BYREF
  __int64 v41; // [rsp+70h] [rbp-51h]
  __int64 v42; // [rsp+78h] [rbp-49h]
  __int64 **v43; // [rsp+80h] [rbp-41h]
  __int64 v44; // [rsp+88h] [rbp-39h]
  _DWORD *v45; // [rsp+90h] [rbp-31h]
  _OWORD v46[2]; // [rsp+98h] [rbp-29h] BYREF
  int v47; // [rsp+B8h] [rbp-9h]

  v5 = a3;
  v43 = a3;
  v45 = a5;
  v7 = a2;
  v44 = a2;
  v8 = a1;
  v35 = a1;
  while ( 2 )
  {
    v37 = a4;
    v34 = 0;
    v33 = 0;
    v9 = 0;
    v40 = 0;
    memset_0(v5, 0, 0x60u);
    v5[2] = (__int64 *)-1LL;
    if ( v7 )
    {
      v13 = v7;
    }
    else
    {
      result = winGetTempname(v8, &v40);
      if ( (_DWORD)result )
        return result;
      v9 = v40;
      v13 = v40;
    }
    v41 = v13;
    v14 = winUtf8ToUnicode(v13, v10, v11);
    if ( v14 )
    {
      v32 = 0;
      v31 = 0;
      memset(v46, 0, sizeof(v46));
      v47 = 0;
      while ( !(unsigned int)((__int64 (__fastcall *)(__int64, _QWORD, _OWORD *))off_1400C5C08)(v14, 0, v46) )
      {
        if ( !(unsigned int)winRetryIoerr(&v31, &v32) )
          goto LABEL_13;
      }
      if ( LODWORD(v46[0]) != -1 && (v46[0] & 0x10) != 0 )
      {
        sqlite3_free(v14);
        sqlite3_free(v9);
        return 526;
      }
LABEL_13:
      v15 = a4 & 2;
      v39 = a4 & 1;
      v38 = a4 & 0x10;
      v31 = v15 != 0 ? -1073741824 : 0x80000000;
      if ( (a4 & 0x10) != 0 )
        v16 = 1;
      else
        v16 = ((a4 & 4) != 0) + 3;
      v17 = sqlite3_uri_boolean(v7, "exclusive", 0);
      v18 = v31;
      v19 = v35;
      v20 = 3;
      if ( v17 )
        v20 = 0;
      v21 = v41;
      v36 = v20;
      v22 = (a4 & 8) != 0 ? 67109122 : 128;
      do
      {
        v42 = ((__int64 (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD, int, int, _QWORD))off_1400C5A70)(
                v14,
                v18,
                v20,
                0,
                v16,
                v22,
                0);
        if ( v42 != -1 )
          break;
        if ( v15 )
        {
          v32 = 0;
          if ( qword_1400C9140 )
            qword_1400C9140();
          v31 = winAccess(v19, v21, 2, &v32);
          if ( qword_1400C9148 )
            qword_1400C9148();
          if ( !v31 && v32 )
            break;
        }
        v23 = winRetryIoerr(&v33, &v34);
        v20 = v36;
      }
      while ( v23 );
      winLogIoerr(v33, 51041);
      v24 = v42;
      v5 = v43;
      v25 = v37;
      v26 = v40;
      v7 = v44;
      if ( v42 == -1 )
      {
        sqlite3_free(v14);
        sqlite3_free(v26);
        if ( v15 && !v38 )
        {
          v8 = v35;
          a4 = v25 & 0xFFFFFFF8 | 1;
          continue;
        }
        v27 = v34;
        v28 = v41;
        *((_DWORD *)v5 + 8) = v34;
        winLogErrorAtLine(14, v27, (unsigned int)"winOpen", v28, 51056);
        return sqlite3CantopenError(51057);
      }
      else
      {
        if ( v45 )
          *v45 = (v15 != 0) + 1;
        v29 = *(__int64 ***)(v35 + 32);
        sqlite3_free(v14);
        sqlite3_free(v26);
        if ( v29 )
          v30 = *v29;
        else
          v30 = &qword_1400A9470;
        *v5 = v30;
        v5[1] = (__int64 *)v35;
        v5[2] = (__int64 *)v24;
        if ( v39 )
          *((_BYTE *)v5 + 28) |= 2u;
        if ( (v25 & 0x100) != 0 && (unsigned int)sqlite3_uri_boolean(v7, "psow", 1) )
          *((_BYTE *)v5 + 28) |= 0x10u;
        *((_DWORD *)v5 + 8) = 0;
        v5[6] = (__int64 *)v7;
        v5[8] = 0;
        v5[9] = 0;
        v5[10] = 0;
        v5[11] = (__int64 *)qword_1400C85D8;
        return 0;
      }
    }
    else
    {
      sqlite3_free(v9);
      return 3082;
    }
  }
}

```

## disassembly

```asm
0x14009ff30  push    rbp
0x14009ff32  push    rbx
0x14009ff33  push    rsi
0x14009ff34  push    rdi
0x14009ff35  push    r12
0x14009ff37  push    r13
0x14009ff39  push    r14
0x14009ff3b  push    r15
0x14009ff3d  lea     rbp, [rsp-17h]
0x14009ff42  sub     rsp, 0D8h
0x14009ff49  mov     rax, cs:__security_cookie
0x14009ff50  xor     rax, rsp
0x14009ff53  mov     [rbp+4Fh+var_50], rax
0x14009ff57  mov     rax, [rbp+4Fh+arg_20]
0x14009ff5b  mov     rbx, r8
0x14009ff5e  mov     [rbp+4Fh+var_90], rbx
0x14009ff62  mov     edi, r9d
0x14009ff65  mov     [rbp+4Fh+var_80], rax
0x14009ff69  mov     r12, rdx
0x14009ff6c  mov     [rbp+4Fh+var_88], rdx
0x14009ff70  mov     r14, rcx
0x14009ff73  mov     [rbp+4Fh+var_C0], rcx
0x14009ff77  xor     r13d, r13d
0x14009ff7a  xor     edx, edx; Val
0x14009ff7c  mov     [rbp+4Fh+var_B4], edi
0x14009ff7f  mov     rcx, rbx; void *
0x14009ff82  mov     [rbp+4Fh+var_C4], r13d
0x14009ff86  mov     [rbp+4Fh+var_C8], r13d
0x14009ff8a  mov     rsi, r13
0x14009ff8d  mov     [rbp+4Fh+var_A8], r13
0x14009ff91  lea     r8d, [rdx+60h]; Size
0x14009ff95  call    memset_0
0x14009ff9a  mov     qword ptr [rbx+10h], 0FFFFFFFFFFFFFFFFh
0x14009ffa2  test    r12, r12
0x14009ffa5  jnz     short loc_14009FFC4
0x14009ffa7  lea     rdx, [rbp+4Fh+var_A8]
0x14009ffab  mov     rcx, r14
0x14009ffae  call    winGetTempname
0x14009ffb3  test    eax, eax
0x14009ffb5  jnz     loc_1400A02A6
0x14009ffbb  mov     rsi, [rbp+4Fh+var_A8]
0x14009ffbf  mov     rax, rsi
0x14009ffc2  jmp     short loc_14009FFC7
0x14009ffc4  mov     rax, r12
0x14009ffc7  mov     rcx, rax
0x14009ffca  mov     [rbp+4Fh+var_A0], rax
0x14009ffce  call    winUtf8ToUnicode
0x14009ffd3  mov     r14, rax
0x14009ffd6  test    rax, rax
0x14009ffd9  jz      loc_1400A0299
0x14009ffdf  xorps   xmm0, xmm0
0x14009ffe2  mov     [rbp+4Fh+var_CC], r13d
0x14009ffe6  xor     eax, eax
0x14009ffe8  mov     [rsp+110h+var_D0], r13d
0x14009ffed  movups  [rbp+4Fh+var_78], xmm0
0x14009fff1  mov     [rbp+4Fh+var_58], eax
0x14009fff4  movups  [rbp+4Fh+var_68], xmm0
0x14009fff8  mov     rax, cs:off_1400C5C08
0x14009ffff  lea     r8, [rbp+4Fh+var_78]
0x1400a0003  xor     edx, edx
0x1400a0005  mov     rcx, r14
0x1400a0008  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a000d  test    eax, eax
0x1400a000f  jnz     short loc_1400A0025
0x1400a0011  lea     rdx, [rbp+4Fh+var_CC]
0x1400a0015  lea     rcx, [rsp+110h+var_D0]
0x1400a001a  call    winRetryIoerr
0x1400a001f  test    eax, eax
0x1400a0021  jnz     short loc_14009FFF8
0x1400a0023  jmp     short loc_1400A0035
0x1400a0025  cmp     dword ptr [rbp+4Fh+var_78], 0FFFFFFFFh
0x1400a0029  jz      short loc_1400A0035
0x1400a002b  test    byte ptr [rbp+4Fh+var_78], 10h
0x1400a002f  jnz     loc_1400A01B1
0x1400a0035  mov     eax, edi
0x1400a0037  mov     r15d, edi
0x1400a003a  and     eax, 1
0x1400a003d  and     r15d, 2
0x1400a0041  mov     [rbp+4Fh+var_AC], eax
0x1400a0044  mov     ecx, edi
0x1400a0046  and     ecx, 10h
0x1400a0049  mov     ebx, edi
0x1400a004b  and     ebx, 8
0x1400a004e  mov     [rbp+4Fh+var_B0], ecx
0x1400a0051  mov     eax, r15d
0x1400a0054  neg     eax
0x1400a0056  sbb     eax, eax
0x1400a0058  and     eax, 40000000h
0x1400a005d  add     eax, 80000000h
0x1400a0062  mov     [rsp+110h+var_D0], eax
0x1400a0066  test    ecx, ecx
0x1400a0068  jz      short loc_1400A0072
0x1400a006a  mov     r13d, 1
0x1400a0070  jmp     short loc_1400A0083
0x1400a0072  mov     al, dil
0x1400a0075  and     al, 4
0x1400a0077  neg     al
0x1400a0079  sbb     r13d, r13d
0x1400a007c  neg     r13d
0x1400a007f  add     r13d, 3
0x1400a0083  xor     r8d, r8d
0x1400a0086  lea     rdx, aExclusive; "exclusive"
0x1400a008d  mov     rcx, r12
0x1400a0090  call    sqlite3_uri_boolean
0x1400a0095  mov     r12d, [rsp+110h+var_D0]
0x1400a009a  xor     ecx, ecx
0x1400a009c  mov     rsi, [rbp+4Fh+var_C0]
0x1400a00a0  test    eax, eax
0x1400a00a2  mov     edx, 3
0x1400a00a7  cmovnz  edx, ecx
0x1400a00aa  neg     ebx
0x1400a00ac  mov     rbx, [rbp+4Fh+var_A0]
0x1400a00b0  sbb     edi, edi
0x1400a00b2  mov     [rbp+4Fh+var_B8], edx
0x1400a00b5  and     edi, 4000082h
0x1400a00bb  sub     edi, 0FFFFFF80h
0x1400a00be  mov     rax, cs:off_1400C5A70
0x1400a00c5  mov     r8d, edx
0x1400a00c8  mov     [rsp+110h+var_E0], 0
0x1400a00d1  mov     edx, r12d
0x1400a00d4  mov     [rsp+110h+var_E8], edi
0x1400a00d8  xor     r9d, r9d
0x1400a00db  mov     rcx, r14
0x1400a00de  mov     [rsp+110h+var_F0], r13d
0x1400a00e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a00e8  mov     [rbp+4Fh+var_98], rax
0x1400a00ec  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400a00f0  jnz     short loc_1400A015E
0x1400a00f2  test    r15d, r15d
0x1400a00f5  jz      short loc_1400A0146
0x1400a00f7  mov     rax, cs:qword_1400C9140
0x1400a00fe  mov     [rbp+4Fh+var_CC], 0
0x1400a0105  test    rax, rax
0x1400a0108  jz      short loc_1400A010F
0x1400a010a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a010f  lea     r9, [rbp+4Fh+var_CC]
0x1400a0113  mov     r8d, 2
0x1400a0119  mov     rdx, rbx
0x1400a011c  mov     rcx, rsi
0x1400a011f  call    winAccess
0x1400a0124  mov     [rsp+110h+var_D0], eax
0x1400a0128  mov     rax, cs:qword_1400C9148
0x1400a012f  test    rax, rax
0x1400a0132  jz      short loc_1400A0139
0x1400a0134  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a0139  cmp     [rsp+110h+var_D0], 0
0x1400a013e  jnz     short loc_1400A0146
0x1400a0140  cmp     [rbp+4Fh+var_CC], 0
0x1400a0144  jnz     short loc_1400A015E
0x1400a0146  lea     rdx, [rbp+4Fh+var_C4]
0x1400a014a  lea     rcx, [rbp+4Fh+var_C8]
0x1400a014e  call    winRetryIoerr
0x1400a0153  mov     edx, [rbp+4Fh+var_B8]
0x1400a0156  test    eax, eax
0x1400a0158  jnz     loc_1400A00BE
0x1400a015e  mov     ecx, [rbp+4Fh+var_C8]
0x1400a0161  mov     edx, 0C761h
0x1400a0166  call    winLogIoerr
0x1400a016b  mov     r13, [rbp+4Fh+var_98]
0x1400a016f  mov     rbx, [rbp+4Fh+var_90]
0x1400a0173  mov     edi, [rbp+4Fh+var_B4]
0x1400a0176  mov     rsi, [rbp+4Fh+var_A8]
0x1400a017a  mov     r12, [rbp+4Fh+var_88]
0x1400a017e  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x1400a0182  jnz     short loc_1400A01FD
0x1400a0184  mov     rcx, r14
0x1400a0187  call    sqlite3_free
0x1400a018c  mov     rcx, rsi
0x1400a018f  call    sqlite3_free
0x1400a0194  xor     r13d, r13d
0x1400a0197  test    r15d, r15d
0x1400a019a  jz      short loc_1400A01CB
0x1400a019c  cmp     [rbp+4Fh+var_B0], r13d
0x1400a01a0  jnz     short loc_1400A01CB
0x1400a01a2  mov     r14, [rbp+4Fh+var_C0]
0x1400a01a6  and     edi, 0FFFFFFF9h
0x1400a01a9  or      edi, 1
0x1400a01ac  jmp     loc_14009FF7A
0x1400a01b1  mov     rcx, r14
0x1400a01b4  call    sqlite3_free
0x1400a01b9  mov     rcx, rsi
0x1400a01bc  call    sqlite3_free
0x1400a01c1  mov     eax, 20Eh
0x1400a01c6  jmp     loc_1400A02A6
0x1400a01cb  mov     edx, [rbp+4Fh+var_C4]
0x1400a01ce  lea     r8, aWinopen; "winOpen"
0x1400a01d5  mov     r9, [rbp+4Fh+var_A0]
0x1400a01d9  mov     ecx, 0Eh
0x1400a01de  mov     [rbx+20h], edx
0x1400a01e1  mov     [rsp+110h+var_F0], 0C770h
0x1400a01e9  call    winLogErrorAtLine
0x1400a01ee  mov     ecx, 0C771h
0x1400a01f3  call    sqlite3CantopenError
0x1400a01f8  jmp     loc_1400A02A6
0x1400a01fd  mov     rcx, [rbp+4Fh+var_80]
0x1400a0201  test    rcx, rcx
0x1400a0204  jz      short loc_1400A0211
0x1400a0206  neg     r15d
0x1400a0209  sbb     eax, eax
0x1400a020b  neg     eax
0x1400a020d  inc     eax
0x1400a020f  mov     [rcx], eax
0x1400a0211  mov     rax, [rbp+4Fh+var_C0]
0x1400a0215  mov     rcx, r14
0x1400a0218  mov     r15, [rax+20h]
0x1400a021c  call    sqlite3_free
0x1400a0221  mov     rcx, rsi
0x1400a0224  call    sqlite3_free
0x1400a0229  xor     esi, esi
0x1400a022b  test    r15, r15
0x1400a022e  jz      short loc_1400A0235
0x1400a0230  mov     rax, [r15]
0x1400a0233  jmp     short loc_1400A023C
0x1400a0235  lea     rax, qword_1400A9470
0x1400a023c  mov     [rbx], rax
0x1400a023f  mov     rax, [rbp+4Fh+var_C0]
0x1400a0243  mov     [rbx+8], rax
0x1400a0247  mov     [rbx+10h], r13
0x1400a024b  cmp     [rbp+4Fh+var_AC], esi
0x1400a024e  jz      short loc_1400A0254
0x1400a0250  or      byte ptr [rbx+1Ch], 2
0x1400a0254  bt      edi, 8
0x1400a0258  jnb     short loc_1400A0277
0x1400a025a  mov     r8d, 1
0x1400a0260  lea     rdx, aPsow; "psow"
0x1400a0267  mov     rcx, r12
0x1400a026a  call    sqlite3_uri_boolean
0x1400a026f  test    eax, eax
0x1400a0271  jz      short loc_1400A0277
0x1400a0273  or      byte ptr [rbx+1Ch], 10h
0x1400a0277  mov     [rbx+20h], esi
0x1400a027a  mov     [rbx+30h], r12
0x1400a027e  mov     [rbx+40h], rsi
0x1400a0282  mov     [rbx+48h], rsi
0x1400a0286  mov     [rbx+50h], rsi
0x1400a028a  mov     rax, cs:qword_1400C85D8
0x1400a0291  mov     [rbx+58h], rax
0x1400a0295  xor     eax, eax
0x1400a0297  jmp     short loc_1400A02A6
0x1400a0299  mov     rcx, rsi
0x1400a029c  call    sqlite3_free
0x1400a02a1  mov     eax, 0C0Ah
0x1400a02a6  mov     rcx, [rbp+4Fh+var_50]
0x1400a02aa  xor     rcx, rsp; StackCookie
0x1400a02ad  call    __security_check_cookie
0x1400a02b2  add     rsp, 0D8h
0x1400a02b9  pop     r15
0x1400a02bb  pop     r14
0x1400a02bd  pop     r13
0x1400a02bf  pop     r12
0x1400a02c1  pop     rdi
0x1400a02c2  pop     rsi
0x1400a02c3  pop     rbx
0x1400a02c4  pop     rbp
0x1400a02c5  retn
```
