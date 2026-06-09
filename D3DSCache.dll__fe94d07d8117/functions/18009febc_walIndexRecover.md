# walIndexRecover

- ea: `0x18009febc`
- end: `0x1800a0339`
- name: `walIndexRecover`
- size: `1149`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: ``

## callers

- `0x18001fd98`

## callees

- `0x180012470`
- `0x18001fd3c`
- `0x180020188`
- `0x180035bf0`
- `0x18003680c`
- `0x18003a860`
- `0x18003af40`
- `0x18003ea38`
- `0x180042244`
- `0x1800449f0`
- `0x1800964a0`
- `0x18009fb80`
- `0x18009febc`
- `0x1800a0340`
- `0x1800a0614`
- `0x1800a0a34`
- `0x1800a6d08`

## string_xrefs

- `0x1800a000c`: `cannot open file`

## pseudocode

```c
__int64 __fastcall walIndexRecover(__int64 a1)
{
  unsigned int v1; // eax
  unsigned int v2; // r12d
  __int64 result; // rax
  unsigned int v5; // edi
  int v6; // r15d
  int v7; // r13d
  unsigned __int32 v8; // ecx
  signed __int32 v9; // esi
  unsigned int v10; // eax
  int v11; // ecx
  __int64 v12; // rax
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rax
  __int64 v16; // r13
  __int64 v17; // r12
  __int64 v18; // r14
  __int64 v19; // rax
  unsigned __int64 v20; // rdx
  __int64 v21; // rcx
  unsigned int v22; // r15d
  unsigned int v23; // eax
  __int64 v24; // r9
  __int64 v25; // rax
  __int64 v26; // rcx
  unsigned int v27; // r12d
  __int64 v28; // r14
  __int64 v29; // rcx
  int v30; // ecx
  _DWORD *v31; // r14
  int v32; // esi
  unsigned int v33; // eax
  unsigned int v34; // [rsp+30h] [rbp-79h] BYREF
  int v35; // [rsp+34h] [rbp-75h] BYREF
  int v36; // [rsp+38h] [rbp-71h]
  int v37; // [rsp+3Ch] [rbp-6Dh]
  int v38; // [rsp+40h] [rbp-69h]
  unsigned int v39; // [rsp+44h] [rbp-65h]
  unsigned int v40; // [rsp+48h] [rbp-61h]
  __int64 v41; // [rsp+50h] [rbp-59h] BYREF
  __int64 v42; // [rsp+58h] [rbp-51h] BYREF
  __int64 v43; // [rsp+60h] [rbp-49h]
  __int64 v44; // [rsp+68h] [rbp-41h]
  __int64 v45; // [rsp+70h] [rbp-39h]
  __int64 v46; // [rsp+78h] [rbp-31h]
  unsigned __int64 v47; // [rsp+80h] [rbp-29h]
  unsigned __int64 v48; // [rsp+88h] [rbp-21h]
  unsigned int v49[4]; // [rsp+90h] [rbp-19h] BYREF
  __int64 v50; // [rsp+A0h] [rbp-9h]
  unsigned int v51; // [rsp+A8h] [rbp-1h]
  unsigned int v52; // [rsp+ACh] [rbp+3h]

  v1 = *(unsigned __int8 *)(a1 + 65) + 1;
  v41 = 0;
  v2 = 3 - v1;
  v40 = v1;
  v39 = 3 - v1;
  result = walLockExclusive(a1, v1, 3 - v1);
  if ( !(_DWORD)result )
  {
    *(_OWORD *)(a1 + 72) = 0;
    *(_OWORD *)(a1 + 88) = 0;
    *(_OWORD *)(a1 + 104) = 0;
    v5 = sqlite3OsFileSize(*(_QWORD *)(a1 + 16), &v41);
    if ( !v5 )
    {
      v6 = 0;
      v7 = 0;
      v37 = 0;
      v38 = 0;
      if ( v41 <= 32 )
        goto LABEL_34;
      v5 = sqlite3OsRead(*(_QWORD *)(a1 + 16), v49, 32, 0);
      if ( !v5 )
      {
        v8 = _byteswap_ulong(v49[0]);
        v9 = _byteswap_ulong(v49[2]);
        if ( (v8 & 0xFFFFFFFE) != 0x377F0682 )
          goto LABEL_34;
        if ( ((v9 - 1) & v9) != 0 )
          goto LABEL_34;
        if ( (unsigned int)(v9 - 512) > 0xFE00 )
          goto LABEL_34;
        v10 = v49[3];
        *(_DWORD *)(a1 + 56) = v9;
        v11 = v8 & 1;
        *(_DWORD *)(a1 + 136) = _byteswap_ulong(v10);
        v12 = v50;
        *(_BYTE *)(a1 + 85) = v11;
        *(_QWORD *)(a1 + 104) = v12;
        walChecksumBytes(v11 ^ 1, (unsigned int)v49, 24, 0, a1 + 96);
        if ( *(_DWORD *)(a1 + 96) != _byteswap_ulong(v51) || *(_DWORD *)(a1 + 100) != _byteswap_ulong(v52) )
        {
LABEL_34:
          *(_DWORD *)(a1 + 96) = v6;
          *(_DWORD *)(a1 + 100) = v7;
          walIndexWriteHdr(a1);
          sehInjectFault();
          v31 = **(_DWORD ***)(a1 + 48);
          v32 = 1;
          v31[24] = 0;
          v31[32] = *(_DWORD *)(a1 + 88);
          v31[25] = 0;
          while ( v32 < 5 )
          {
            v33 = walLockExclusive(a1, (unsigned int)(v32 + 3), 1);
            v5 = v33;
            if ( v33 )
            {
              if ( v33 != 5 )
                goto LABEL_46;
            }
            else
            {
              if ( v32 == 1 && *(_DWORD *)(a1 + 88) )
                v31[26] = *(_DWORD *)(a1 + 88);
              else
                v31[v32 + 25] = -1;
              sehInjectFault();
              walUnlockExclusive(a1, (unsigned int)(v32 + 3), 1);
            }
            ++v32;
          }
          if ( *(_DWORD *)(a1 + 92) )
            sqlite3_log(283, "recovered %d frames from WAL file %s", *(_DWORD *)(a1 + 88), *(const char **)(a1 + 128));
          goto LABEL_46;
        }
        if ( _byteswap_ulong(v49[1]) == 3007000 )
        {
          v44 = v9 + 24;
          v15 = sqlite3_malloc64(v44 + 0x8000, v13, v14);
          *(_QWORD *)(a1 + 144) = v15;
          v16 = v15;
          if ( !v15 )
          {
            v5 = 7;
            goto LABEL_46;
          }
          v17 = v15 + 24 + v9;
          v18 = 0;
          v46 = v17;
          v36 = 0;
          v19 = (v41 - 32) / (v9 + 24);
          v20 = (unsigned int)v19;
          v48 = (unsigned int)v19;
          v47 = ((unsigned __int64)(unsigned int)(v19 + 4096) - 4063) >> 12;
          do
          {
            v42 = 0;
            v21 = v20;
            if ( v20 >= (unsigned __int64)(unsigned int)((_DWORD)v18 << 12) + 4062 )
              v21 = (unsigned int)((_DWORD)v18 << 12) + 4062LL;
            v43 = v21;
            if ( (_DWORD)v18 )
              v22 = ((_DWORD)v18 << 12) - 33;
            else
              v22 = 1;
            v23 = walIndexPage(a1, (unsigned int)v18, &v42);
            v24 = v42;
            v5 = v23;
            if ( !v42 )
              break;
            v25 = *(_QWORD *)(a1 + 48);
            *(_DWORD *)(a1 + 160) = v18;
            *(_QWORD *)(a1 + 152) = v24;
            v26 = (unsigned int)v18;
            *(_QWORD *)(v25 + 8 * v18) = v17;
            v27 = v43;
            v45 = (unsigned int)v18;
            if ( v22 <= (unsigned int)v43 )
            {
              v28 = v44;
              do
              {
                v29 = *(_QWORD *)(a1 + 16);
                v34 = 0;
                v35 = 0;
                v5 = sqlite3OsRead(v29, v16, (unsigned int)(v9 + 24), v28 * (v22 - 1) + 32);
                if ( v5 )
                  break;
                if ( !(unsigned int)walDecodeFrame(a1, (unsigned int)&v34, (unsigned int)&v35, (int)v16 + 24, v16) )
                  break;
                v5 = walIndexAppend(a1, v22, v34);
                if ( v5 )
                  break;
                if ( v35 )
                {
                  *(_DWORD *)(a1 + 92) = v35;
                  *(_DWORD *)(a1 + 88) = v22;
                  *(_WORD *)(a1 + 86) = v9 & 0xFF00 | HIWORD(v9);
                  v30 = *(_DWORD *)(a1 + 100);
                  v37 = *(_DWORD *)(a1 + 96);
                  v38 = v30;
                }
                ++v22;
              }
              while ( v22 <= v27 );
              LODWORD(v18) = v36;
              v24 = v42;
              v26 = v45;
            }
            v17 = v46;
            *(_QWORD *)(*(_QWORD *)(a1 + 48) + 8 * v26) = v24;
            *(_DWORD *)(a1 + 160) = 0;
            *(_QWORD *)(a1 + 152) = 0;
            memcpy_0(
              (void *)(v24 + (-(__int64)((_DWORD)v18 == 0) & 0x88)),
              (const void *)((-(__int64)((_DWORD)v18 == 0) & 0x88) + v17),
              (-(__int64)((_DWORD)v18 != 0) & 0x88) + 32632);
            sehInjectFault();
            if ( v22 <= (unsigned int)v43 )
              break;
            v20 = v48;
            v18 = (unsigned int)(v18 + 1);
            v36 = v18;
          }
          while ( (unsigned int)v18 <= (unsigned int)v47 );
          *(_QWORD *)(a1 + 144) = 0;
          sqlite3_free(v16);
          v2 = v39;
          v6 = v37;
          v7 = v38;
        }
        else
        {
          v5 = sqlite3ReportError(v5 + 14, 66370, "cannot open file");
        }
        if ( !v5 )
          goto LABEL_34;
      }
    }
LABEL_46:
    walUnlockExclusive(a1, v40, v2);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x18009febc  push    rbp
0x18009febe  push    rbx
0x18009febf  push    rsi
0x18009fec0  push    rdi
0x18009fec1  push    r12
0x18009fec3  push    r13
0x18009fec5  push    r14
0x18009fec7  push    r15
0x18009fec9  lea     rbp, [rsp-1Fh]
0x18009fece  sub     rsp, 0C8h
0x18009fed5  mov     rax, cs:__security_cookie
0x18009fedc  xor     rax, rsp
0x18009fedf  mov     [rbp+57h+var_50], rax
0x18009fee3  movzx   eax, byte ptr [rcx+41h]
0x18009fee7  mov     r12d, 3
0x18009feed  inc     eax
0x18009feef  mov     [rbp+57h+var_B0], 0
0x18009fef7  sub     r12d, eax
0x18009fefa  mov     [rbp+57h+var_B8], eax
0x18009fefd  mov     r8d, r12d
0x18009ff00  mov     [rbp+57h+var_BC], r12d
0x18009ff04  mov     edx, eax
0x18009ff06  mov     rbx, rcx
0x18009ff09  call    walLockExclusive
0x18009ff0e  test    eax, eax
0x18009ff10  jnz     loc_1800A0319
0x18009ff16  xorps   xmm0, xmm0
0x18009ff19  lea     rdx, [rbp+57h+var_B0]
0x18009ff1d  movups  xmmword ptr [rbx+48h], xmm0
0x18009ff21  movups  xmmword ptr [rbx+58h], xmm0
0x18009ff25  movups  xmmword ptr [rbx+68h], xmm0
0x18009ff29  mov     rcx, [rbx+10h]
0x18009ff2d  call    sqlite3OsFileSize
0x18009ff32  mov     edi, eax
0x18009ff34  test    eax, eax
0x18009ff36  jnz     loc_1800A0309
0x18009ff3c  xor     r15d, r15d
0x18009ff3f  xor     r13d, r13d
0x18009ff42  cmp     [rbp+57h+var_B0], 20h ; ' '
0x18009ff47  mov     [rbp+57h+var_C4], r15d
0x18009ff4b  mov     [rbp+57h+var_C0], r13d
0x18009ff4f  jle     loc_1800A0255
0x18009ff55  mov     rcx, [rbx+10h]
0x18009ff59  lea     r8d, [rax+20h]
0x18009ff5d  xor     r9d, r9d
0x18009ff60  lea     rdx, [rbp+57h+var_70]
0x18009ff64  call    sqlite3OsRead
0x18009ff69  mov     edi, eax
0x18009ff6b  test    eax, eax
0x18009ff6d  jnz     loc_1800A0309
0x18009ff73  mov     ecx, [rbp+57h+var_70]
0x18009ff76  mov     esi, [rbp+57h+var_68]
0x18009ff79  bswap   ecx
0x18009ff7b  mov     eax, ecx
0x18009ff7d  and     eax, 0FFFFFFFEh
0x18009ff80  bswap   esi
0x18009ff82  cmp     eax, 377F0682h
0x18009ff87  jnz     loc_1800A0255
0x18009ff8d  lea     eax, [rsi-1]
0x18009ff90  test    esi, eax
0x18009ff92  jnz     loc_1800A0255
0x18009ff98  lea     eax, [rsi-200h]
0x18009ff9e  cmp     eax, 0FE00h
0x18009ffa3  ja      loc_1800A0255
0x18009ffa9  mov     eax, [rbp+57h+var_64]
0x18009ffac  lea     r14, [rbx+60h]
0x18009ffb0  and     cl, 1
0x18009ffb3  mov     [rbx+38h], esi
0x18009ffb6  bswap   eax
0x18009ffb8  movzx   ecx, cl
0x18009ffbb  lea     r8d, [r15+18h]
0x18009ffbf  mov     [rbx+88h], eax
0x18009ffc5  lea     rdx, [rbp+57h+var_70]
0x18009ffc9  mov     rax, [rbp+57h+var_60]
0x18009ffcd  xor     r9d, r9d
0x18009ffd0  mov     [rbx+55h], cl
0x18009ffd3  xor     ecx, 1
0x18009ffd6  mov     [rbx+68h], rax
0x18009ffda  mov     [rsp+100h+var_E0], r14
0x18009ffdf  call    walChecksumBytes
0x18009ffe4  mov     eax, [rbp+57h+var_58]
0x18009ffe7  bswap   eax
0x18009ffe9  cmp     [r14], eax
0x18009ffec  jnz     loc_1800A0255
0x18009fff2  mov     eax, [rbp+57h+var_54]
0x18009fff5  bswap   eax
0x18009fff7  cmp     [rbx+64h], eax
0x18009fffa  jnz     loc_1800A0255
0x1800a0000  mov     eax, [rbp+57h+var_6C]
0x1800a0003  bswap   eax
0x1800a0005  cmp     eax, 2DE218h
0x1800a000a  jz      short loc_1800A0027
0x1800a000c  lea     r8, aCannotOpenFile; "cannot open file"
0x1800a0013  mov     edx, 10342h
0x1800a0018  lea     ecx, [rdi+0Eh]
0x1800a001b  call    sqlite3ReportError
0x1800a0020  mov     edi, eax
0x1800a0022  jmp     loc_1800A024D
0x1800a0027  lea     eax, [rsi+18h]
0x1800a002a  movsxd  rdi, eax
0x1800a002d  mov     [rbp+57h+var_98], rdi
0x1800a0031  lea     rcx, [rdi+8000h]
0x1800a0038  call    sqlite3_malloc64
0x1800a003d  mov     [rbx+90h], rax
0x1800a0044  mov     r13, rax
0x1800a0047  test    rax, rax
0x1800a004a  jnz     short loc_1800A0054
0x1800a004c  lea     edi, [rax+7]
0x1800a004f  jmp     loc_1800A0309
0x1800a0054  add     rax, 18h
0x1800a0058  movsxd  r12, esi
0x1800a005b  add     r12, rax
0x1800a005e  xor     r14d, r14d
0x1800a0061  mov     rax, [rbp+57h+var_B0]
0x1800a0065  add     rax, 0FFFFFFFFFFFFFFE0h
0x1800a0069  mov     [rbp+57h+var_88], r12
0x1800a006d  cqo
0x1800a006f  mov     [rbp+57h+var_C8], r14d
0x1800a0073  idiv    rdi
0x1800a0076  mov     edx, eax
0x1800a0078  mov     [rbp+57h+var_78], rdx
0x1800a007c  lea     ecx, [rax+1000h]
0x1800a0082  sub     rcx, 0FDFh
0x1800a0089  shr     rcx, 0Ch
0x1800a008d  mov     [rbp+57h+var_80], rcx
0x1800a0091  mov     eax, r14d
0x1800a0094  mov     [rbp+57h+var_A8], 0
0x1800a009c  shl     eax, 0Ch
0x1800a009f  mov     rcx, rdx
0x1800a00a2  mov     r15d, eax
0x1800a00a5  add     rax, 0FDEh
0x1800a00ab  cmp     rdx, rax
0x1800a00ae  cmovnb  rcx, rax
0x1800a00b2  mov     [rbp+57h+var_A0], rcx
0x1800a00b6  test    r14d, r14d
0x1800a00b9  jnz     short loc_1800A00C1
0x1800a00bb  lea     r15d, [r14+1]
0x1800a00bf  jmp     short loc_1800A00C5
0x1800a00c1  add     r15d, 0FFFFFFDFh
0x1800a00c5  lea     r8, [rbp+57h+var_A8]
0x1800a00c9  mov     edx, r14d
0x1800a00cc  mov     rcx, rbx
0x1800a00cf  call    walIndexPage
0x1800a00d4  mov     r9, [rbp+57h+var_A8]
0x1800a00d8  mov     edi, eax
0x1800a00da  test    r9, r9
0x1800a00dd  jz      loc_1800A022E
0x1800a00e3  mov     rax, [rbx+30h]
0x1800a00e7  mov     [rbx+0A0h], r14d
0x1800a00ee  mov     [rbx+98h], r9
0x1800a00f5  mov     ecx, r14d
0x1800a00f8  mov     [rax+r14*8], r12
0x1800a00fc  mov     r12, [rbp+57h+var_A0]
0x1800a0100  mov     [rbp+57h+var_90], rcx
0x1800a0104  cmp     r15d, r12d
0x1800a0107  ja      loc_1800A01BC
0x1800a010d  mov     r14, [rbp+57h+var_98]
0x1800a0111  mov     rcx, [rbx+10h]
0x1800a0115  lea     r9d, [r15-1]
0x1800a0119  imul    r9, r14
0x1800a011d  lea     r8d, [rsi+18h]
0x1800a0121  mov     [rbp+57h+var_D0], 0
0x1800a0128  add     r9, 20h ; ' '
0x1800a012c  mov     [rbp+57h+var_CC], 0
0x1800a0133  mov     rdx, r13
0x1800a0136  call    sqlite3OsRead
0x1800a013b  mov     edi, eax
0x1800a013d  test    eax, eax
0x1800a013f  jnz     short loc_1800A01B0
0x1800a0141  lea     r9, [r13+18h]
0x1800a0145  mov     [rsp+100h+var_E0], r13
0x1800a014a  lea     r8, [rbp+57h+var_CC]
0x1800a014e  mov     rcx, rbx
0x1800a0151  lea     rdx, [rbp+57h+var_D0]
0x1800a0155  call    walDecodeFrame
0x1800a015a  test    eax, eax
0x1800a015c  jz      short loc_1800A01B0
0x1800a015e  mov     r8d, [rbp+57h+var_D0]
0x1800a0162  mov     edx, r15d
0x1800a0165  mov     rcx, rbx
0x1800a0168  call    walIndexAppend
0x1800a016d  mov     edi, eax
0x1800a016f  test    eax, eax
0x1800a0171  jnz     short loc_1800A01B0
0x1800a0173  mov     eax, [rbp+57h+var_CC]
0x1800a0176  test    eax, eax
0x1800a0178  jz      short loc_1800A01A4
0x1800a017a  mov     [rbx+5Ch], eax
0x1800a017d  mov     ecx, esi
0x1800a017f  movzx   eax, si
0x1800a0182  sar     ecx, 10h
0x1800a0185  mov     [rbx+58h], r15d
0x1800a0189  mov     edx, 0FF00h
0x1800a018e  and     ax, dx
0x1800a0191  or      cx, ax
0x1800a0194  mov     [rbx+56h], cx
0x1800a0198  mov     eax, [rbx+60h]
0x1800a019b  mov     ecx, [rbx+64h]
0x1800a019e  mov     [rbp+57h+var_C4], eax
0x1800a01a1  mov     [rbp+57h+var_C0], ecx
0x1800a01a4  inc     r15d
0x1800a01a7  cmp     r15d, r12d
0x1800a01aa  jbe     loc_1800A0111
0x1800a01b0  mov     r14d, [rbp+57h+var_C8]
0x1800a01b4  mov     r9, [rbp+57h+var_A8]
0x1800a01b8  mov     rcx, [rbp+57h+var_90]
0x1800a01bc  mov     rax, [rbx+30h]
0x1800a01c0  mov     edx, 88h
0x1800a01c5  mov     r12, [rbp+57h+var_88]
0x1800a01c9  mov     [rax+rcx*8], r9
0x1800a01cd  mov     eax, r14d
0x1800a01d0  neg     eax
0x1800a01d2  mov     dword ptr [rbx+0A0h], 0
0x1800a01dc  mov     eax, r14d
0x1800a01df  mov     qword ptr [rbx+98h], 0
0x1800a01ea  sbb     rcx, rcx
0x1800a01ed  not     rcx
0x1800a01f0  and     rcx, rdx
0x1800a01f3  neg     eax
0x1800a01f5  sbb     r8, r8
0x1800a01f8  and     r8, rdx
0x1800a01fb  lea     rdx, [rcx+r12]; Src
0x1800a01ff  add     r8, 7F78h; Size
0x1800a0206  add     rcx, r9; void *
0x1800a0209  call    memcpy_0
0x1800a020e  call    sehInjectFault
0x1800a0213  cmp     r15d, dword ptr [rbp+57h+var_A0]
0x1800a0217  jbe     short loc_1800A022E
0x1800a0219  mov     rdx, [rbp+57h+var_78]
0x1800a021d  inc     r14d
0x1800a0220  mov     [rbp+57h+var_C8], r14d
0x1800a0224  cmp     r14d, dword ptr [rbp+57h+var_80]
0x1800a0228  jbe     loc_1800A0091
0x1800a022e  mov     rcx, r13
0x1800a0231  mov     qword ptr [rbx+90h], 0
0x1800a023c  call    sqlite3_free
0x1800a0241  mov     r12d, [rbp+57h+var_BC]
0x1800a0245  mov     r15d, [rbp+57h+var_C4]
0x1800a0249  mov     r13d, [rbp+57h+var_C0]
0x1800a024d  test    edi, edi
0x1800a024f  jnz     loc_1800A0309
0x1800a0255  mov     rcx, rbx
0x1800a0258  mov     [rbx+60h], r15d
0x1800a025c  mov     [rbx+64h], r13d
0x1800a0260  call    walIndexWriteHdr
0x1800a0265  call    sehInjectFault
0x1800a026a  mov     rax, [rbx+30h]
0x1800a026e  xor     r13d, r13d
0x1800a0271  mov     r14, [rax]
0x1800a0274  lea     esi, [r13+1]
0x1800a0278  mov     [r14+60h], r13d
0x1800a027c  mov     eax, [rbx+58h]
0x1800a027f  mov     [r14+80h], eax
0x1800a0286  mov     [r14+64h], r13d
0x1800a028a  cmp     esi, 5
0x1800a028d  jge     short loc_1800A02E7
0x1800a028f  mov     r8d, 1
0x1800a0295  lea     edx, [rsi+3]
0x1800a0298  mov     rcx, rbx
0x1800a029b  call    walLockExclusive
0x1800a02a0  mov     edi, eax
0x1800a02a2  test    eax, eax
0x1800a02a4  jnz     short loc_1800A02DE
0x1800a02a6  cmp     esi, 1
0x1800a02a9  jnz     short loc_1800A02BA
0x1800a02ab  cmp     [rbx+58h], r13d
0x1800a02af  jz      short loc_1800A02BA
0x1800a02b1  mov     eax, [rbx+58h]
0x1800a02b4  mov     [r14+68h], eax
0x1800a02b8  jmp     short loc_1800A02C6
0x1800a02ba  movsxd  rax, esi
0x1800a02bd  mov     dword ptr [r14+rax*4+64h], 0FFFFFFFFh
0x1800a02c6  call    sehInjectFault
0x1800a02cb  mov     r8d, 1
0x1800a02d1  lea     edx, [rsi+3]
0x1800a02d4  mov     rcx, rbx
0x1800a02d7  call    walUnlockExclusive
0x1800a02dc  jmp     short loc_1800A02E3
0x1800a02de  cmp     eax, 5
0x1800a02e1  jnz     short loc_1800A0309
0x1800a02e3  inc     esi
0x1800a02e5  jmp     short loc_1800A028A
0x1800a02e7  cmp     [rbx+5Ch], r13d
0x1800a02eb  jz      short loc_1800A0309
0x1800a02ed  mov     r9, [rbx+80h]
0x1800a02f4  lea     rdx, aRecoveredDFram; "recovered %d frames from WAL file %s"
0x1800a02fb  mov     r8d, [rbx+58h]
0x1800a02ff  mov     ecx, 11Bh
0x1800a0304  call    sqlite3_log
0x1800a0309  mov     edx, [rbp+57h+var_B8]
0x1800a030c  mov     r8d, r12d
0x1800a030f  mov     rcx, rbx
0x1800a0312  call    walUnlockExclusive
0x1800a0317  mov     eax, edi
0x1800a0319  mov     rcx, [rbp+57h+var_50]
0x1800a031d  xor     rcx, rsp; StackCookie
0x1800a0320  call    __security_check_cookie
0x1800a0325  add     rsp, 0C8h
0x1800a032c  pop     r15
0x1800a032e  pop     r14
  ... truncated ...
```
