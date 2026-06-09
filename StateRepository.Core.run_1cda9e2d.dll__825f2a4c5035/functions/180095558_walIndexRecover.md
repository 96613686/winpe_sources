# walIndexRecover

- ea: `0x180095558`
- end: `0x1800959d5`
- name: `walIndexRecover`
- size: `1149`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: ``

## callers

- `0x180049a40`

## callees

- `0x180005b90`
- `0x180007d74`
- `0x18000875c`
- `0x18000aac0`
- `0x1800275f0`
- `0x180049508`
- `0x180049668`
- `0x1800497b0`
- `0x180049c88`
- `0x18004a0d4`
- `0x18004e9f0`
- `0x180057978`
- `0x180060134`
- `0x180061cdc`
- `0x180068880`
- `0x180095558`
- `0x180099814`

## string_xrefs

- `0x1800956a8`: `cannot open file`

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
  __int64 v15; // r9
  __int64 v16; // rax
  __int64 v17; // r13
  __int64 v18; // r12
  __int64 v19; // r14
  __int64 v20; // rax
  unsigned __int64 v21; // rdx
  __int64 v22; // rcx
  unsigned int v23; // r15d
  unsigned int v24; // eax
  __int64 v25; // r9
  __int64 v26; // rax
  __int64 v27; // rcx
  unsigned int v28; // r12d
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
        goto LABEL_33;
      v5 = sqlite3OsRead(*(_QWORD *)(a1 + 16), v49, 32);
      if ( !v5 )
      {
        v8 = _byteswap_ulong(v49[0]);
        v9 = _byteswap_ulong(v49[2]);
        if ( (v8 & 0xFFFFFFFE) != 0x377F0682 )
          goto LABEL_33;
        if ( ((v9 - 1) & v9) != 0 )
          goto LABEL_33;
        if ( (unsigned int)(v9 - 512) > 0xFE00 )
          goto LABEL_33;
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
LABEL_33:
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
                goto LABEL_45;
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
          goto LABEL_45;
        }
        if ( _byteswap_ulong(v49[1]) == 3007000 )
        {
          v44 = v9 + 24;
          v16 = sqlite3_malloc64(v44 + 0x8000, v13, v14, v15);
          *(_QWORD *)(a1 + 144) = v16;
          v17 = v16;
          if ( !v16 )
          {
            v5 = 7;
            goto LABEL_45;
          }
          v18 = v16 + 24 + v9;
          v19 = 0;
          v46 = v18;
          v36 = 0;
          v20 = (v41 - 32) / (v9 + 24);
          v21 = (unsigned int)v20;
          v48 = (unsigned int)v20;
          v47 = ((unsigned __int64)(unsigned int)(v20 + 4096) - 4063) >> 12;
          do
          {
            v42 = 0;
            v22 = v21;
            if ( v21 >= (unsigned __int64)(unsigned int)((_DWORD)v19 << 12) + 4062 )
              v22 = (unsigned int)((_DWORD)v19 << 12) + 4062LL;
            v43 = v22;
            if ( (_DWORD)v19 )
              v23 = ((_DWORD)v19 << 12) - 33;
            else
              v23 = 1;
            v24 = walIndexPage(a1, (unsigned int)v19, &v42);
            v25 = v42;
            v5 = v24;
            if ( !v42 )
              break;
            v26 = *(_QWORD *)(a1 + 48);
            *(_DWORD *)(a1 + 160) = v19;
            *(_QWORD *)(a1 + 152) = v25;
            v27 = (unsigned int)v19;
            *(_QWORD *)(v26 + 8 * v19) = v18;
            v28 = v43;
            v45 = (unsigned int)v19;
            if ( v23 <= (unsigned int)v43 )
            {
              do
              {
                v29 = *(_QWORD *)(a1 + 16);
                v34 = 0;
                v35 = 0;
                v5 = sqlite3OsRead(v29, v17, (unsigned int)(v9 + 24));
                if ( v5 )
                  break;
                if ( !(unsigned int)walDecodeFrame(a1, (unsigned int)&v34, (unsigned int)&v35, (int)v17 + 24, v17) )
                  break;
                v5 = walIndexAppend(a1, v23, v34);
                if ( v5 )
                  break;
                if ( v35 )
                {
                  *(_DWORD *)(a1 + 92) = v35;
                  *(_DWORD *)(a1 + 88) = v23;
                  *(_WORD *)(a1 + 86) = v9 & 0xFF00 | HIWORD(v9);
                  v30 = *(_DWORD *)(a1 + 100);
                  v37 = *(_DWORD *)(a1 + 96);
                  v38 = v30;
                }
                ++v23;
              }
              while ( v23 <= v28 );
              LODWORD(v19) = v36;
              v25 = v42;
              v27 = v45;
            }
            v18 = v46;
            *(_QWORD *)(*(_QWORD *)(a1 + 48) + 8 * v27) = v25;
            *(_DWORD *)(a1 + 160) = 0;
            *(_QWORD *)(a1 + 152) = 0;
            memcpy_0(
              (void *)(v25 + (-(__int64)((_DWORD)v19 == 0) & 0x88)),
              (const void *)((-(__int64)((_DWORD)v19 == 0) & 0x88) + v18),
              (-(__int64)((_DWORD)v19 != 0) & 0x88) + 32632);
            sehInjectFault();
            if ( v23 <= (unsigned int)v43 )
              break;
            v21 = v48;
            v19 = (unsigned int)(v19 + 1);
            v36 = v19;
          }
          while ( (unsigned int)v19 <= (unsigned int)v47 );
          *(_QWORD *)(a1 + 144) = 0;
          sqlite3_free(v17);
          v2 = v39;
          v6 = v37;
          v7 = v38;
        }
        else
        {
          v5 = sqlite3ReportError(v5 + 14, 66479, "cannot open file");
        }
        if ( !v5 )
          goto LABEL_33;
      }
    }
LABEL_45:
    walUnlockExclusive(a1, v40, v2);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x180095558  push    rbp
0x18009555a  push    rbx
0x18009555b  push    rsi
0x18009555c  push    rdi
0x18009555d  push    r12
0x18009555f  push    r13
0x180095561  push    r14
0x180095563  push    r15
0x180095565  lea     rbp, [rsp-1Fh]
0x18009556a  sub     rsp, 0C8h
0x180095571  mov     rax, cs:__security_cookie
0x180095578  xor     rax, rsp
0x18009557b  mov     [rbp+57h+var_50], rax
0x18009557f  movzx   eax, byte ptr [rcx+41h]
0x180095583  mov     r12d, 3
0x180095589  inc     eax
0x18009558b  mov     [rbp+57h+var_B0], 0
0x180095593  sub     r12d, eax
0x180095596  mov     [rbp+57h+var_B8], eax
0x180095599  mov     r8d, r12d
0x18009559c  mov     [rbp+57h+var_BC], r12d
0x1800955a0  mov     edx, eax
0x1800955a2  mov     rbx, rcx
0x1800955a5  call    walLockExclusive
0x1800955aa  test    eax, eax
0x1800955ac  jnz     loc_1800959B5
0x1800955b2  xorps   xmm0, xmm0
0x1800955b5  lea     rdx, [rbp+57h+var_B0]
0x1800955b9  movups  xmmword ptr [rbx+48h], xmm0
0x1800955bd  movups  xmmword ptr [rbx+58h], xmm0
0x1800955c1  movups  xmmword ptr [rbx+68h], xmm0
0x1800955c5  mov     rcx, [rbx+10h]
0x1800955c9  call    sqlite3OsFileSize
0x1800955ce  mov     edi, eax
0x1800955d0  test    eax, eax
0x1800955d2  jnz     loc_1800959A5
0x1800955d8  xor     r15d, r15d
0x1800955db  xor     r13d, r13d
0x1800955de  cmp     [rbp+57h+var_B0], 20h ; ' '
0x1800955e3  mov     [rbp+57h+var_C4], r15d
0x1800955e7  mov     [rbp+57h+var_C0], r13d
0x1800955eb  jle     loc_1800958F1
0x1800955f1  mov     rcx, [rbx+10h]
0x1800955f5  lea     r8d, [rax+20h]
0x1800955f9  xor     r9d, r9d
0x1800955fc  lea     rdx, [rbp+57h+var_70]
0x180095600  call    sqlite3OsRead
0x180095605  mov     edi, eax
0x180095607  test    eax, eax
0x180095609  jnz     loc_1800959A5
0x18009560f  mov     ecx, [rbp+57h+var_70]
0x180095612  mov     esi, [rbp+57h+var_68]
0x180095615  bswap   ecx
0x180095617  mov     eax, ecx
0x180095619  and     eax, 0FFFFFFFEh
0x18009561c  bswap   esi
0x18009561e  cmp     eax, 377F0682h
0x180095623  jnz     loc_1800958F1
0x180095629  lea     eax, [rsi-1]
0x18009562c  test    esi, eax
0x18009562e  jnz     loc_1800958F1
0x180095634  lea     eax, [rsi-200h]
0x18009563a  cmp     eax, 0FE00h
0x18009563f  ja      loc_1800958F1
0x180095645  mov     eax, [rbp+57h+var_64]
0x180095648  lea     r14, [rbx+60h]
0x18009564c  and     cl, 1
0x18009564f  mov     [rbx+38h], esi
0x180095652  bswap   eax
0x180095654  movzx   ecx, cl
0x180095657  lea     r8d, [r15+18h]
0x18009565b  mov     [rbx+88h], eax
0x180095661  lea     rdx, [rbp+57h+var_70]
0x180095665  mov     rax, [rbp+57h+var_60]
0x180095669  xor     r9d, r9d
0x18009566c  mov     [rbx+55h], cl
0x18009566f  xor     ecx, 1
0x180095672  mov     [rbx+68h], rax
0x180095676  mov     [rsp+100h+var_E0], r14
0x18009567b  call    walChecksumBytes
0x180095680  mov     eax, [rbp+57h+var_58]
0x180095683  bswap   eax
0x180095685  cmp     [r14], eax
0x180095688  jnz     loc_1800958F1
0x18009568e  mov     eax, [rbp+57h+var_54]
0x180095691  bswap   eax
0x180095693  cmp     [rbx+64h], eax
0x180095696  jnz     loc_1800958F1
0x18009569c  mov     eax, [rbp+57h+var_6C]
0x18009569f  bswap   eax
0x1800956a1  cmp     eax, 2DE218h
0x1800956a6  jz      short loc_1800956C3
0x1800956a8  lea     r8, aCannotOpenFile; "cannot open file"
0x1800956af  mov     edx, 103AFh
0x1800956b4  lea     ecx, [rdi+0Eh]
0x1800956b7  call    sqlite3ReportError
0x1800956bc  mov     edi, eax
0x1800956be  jmp     loc_1800958E9
0x1800956c3  lea     eax, [rsi+18h]
0x1800956c6  movsxd  rdi, eax
0x1800956c9  mov     [rbp+57h+var_98], rdi
0x1800956cd  lea     rcx, [rdi+8000h]
0x1800956d4  call    sqlite3_malloc64
0x1800956d9  mov     [rbx+90h], rax
0x1800956e0  mov     r13, rax
0x1800956e3  test    rax, rax
0x1800956e6  jnz     short loc_1800956F0
0x1800956e8  lea     edi, [rax+7]
0x1800956eb  jmp     loc_1800959A5
0x1800956f0  add     rax, 18h
0x1800956f4  movsxd  r12, esi
0x1800956f7  add     r12, rax
0x1800956fa  xor     r14d, r14d
0x1800956fd  mov     rax, [rbp+57h+var_B0]
0x180095701  add     rax, 0FFFFFFFFFFFFFFE0h
0x180095705  mov     [rbp+57h+var_88], r12
0x180095709  cqo
0x18009570b  mov     [rbp+57h+var_C8], r14d
0x18009570f  idiv    rdi
0x180095712  mov     edx, eax
0x180095714  mov     [rbp+57h+var_78], rdx
0x180095718  lea     ecx, [rax+1000h]
0x18009571e  sub     rcx, 0FDFh
0x180095725  shr     rcx, 0Ch
0x180095729  mov     [rbp+57h+var_80], rcx
0x18009572d  mov     eax, r14d
0x180095730  mov     [rbp+57h+var_A8], 0
0x180095738  shl     eax, 0Ch
0x18009573b  mov     rcx, rdx
0x18009573e  mov     r15d, eax
0x180095741  add     rax, 0FDEh
0x180095747  cmp     rdx, rax
0x18009574a  cmovnb  rcx, rax
0x18009574e  mov     [rbp+57h+var_A0], rcx
0x180095752  test    r14d, r14d
0x180095755  jnz     short loc_18009575D
0x180095757  lea     r15d, [r14+1]
0x18009575b  jmp     short loc_180095761
0x18009575d  add     r15d, 0FFFFFFDFh
0x180095761  lea     r8, [rbp+57h+var_A8]
0x180095765  mov     edx, r14d
0x180095768  mov     rcx, rbx
0x18009576b  call    walIndexPage
0x180095770  mov     r9, [rbp+57h+var_A8]
0x180095774  mov     edi, eax
0x180095776  test    r9, r9
0x180095779  jz      loc_1800958CA
0x18009577f  mov     rax, [rbx+30h]
0x180095783  mov     [rbx+0A0h], r14d
0x18009578a  mov     [rbx+98h], r9
0x180095791  mov     ecx, r14d
0x180095794  mov     [rax+r14*8], r12
0x180095798  mov     r12, [rbp+57h+var_A0]
0x18009579c  mov     [rbp+57h+var_90], rcx
0x1800957a0  cmp     r15d, r12d
0x1800957a3  ja      loc_180095858
0x1800957a9  mov     r14, [rbp+57h+var_98]
0x1800957ad  mov     rcx, [rbx+10h]
0x1800957b1  lea     r9d, [r15-1]
0x1800957b5  imul    r9, r14
0x1800957b9  lea     r8d, [rsi+18h]
0x1800957bd  mov     [rbp+57h+var_D0], 0
0x1800957c4  add     r9, 20h ; ' '
0x1800957c8  mov     [rbp+57h+var_CC], 0
0x1800957cf  mov     rdx, r13
0x1800957d2  call    sqlite3OsRead
0x1800957d7  mov     edi, eax
0x1800957d9  test    eax, eax
0x1800957db  jnz     short loc_18009584C
0x1800957dd  lea     r9, [r13+18h]
0x1800957e1  mov     [rsp+100h+var_E0], r13
0x1800957e6  lea     r8, [rbp+57h+var_CC]
0x1800957ea  mov     rcx, rbx
0x1800957ed  lea     rdx, [rbp+57h+var_D0]
0x1800957f1  call    walDecodeFrame
0x1800957f6  test    eax, eax
0x1800957f8  jz      short loc_18009584C
0x1800957fa  mov     r8d, [rbp+57h+var_D0]
0x1800957fe  mov     edx, r15d
0x180095801  mov     rcx, rbx
0x180095804  call    walIndexAppend
0x180095809  mov     edi, eax
0x18009580b  test    eax, eax
0x18009580d  jnz     short loc_18009584C
0x18009580f  mov     eax, [rbp+57h+var_CC]
0x180095812  test    eax, eax
0x180095814  jz      short loc_180095840
0x180095816  mov     [rbx+5Ch], eax
0x180095819  mov     ecx, esi
0x18009581b  movzx   eax, si
0x18009581e  sar     ecx, 10h
0x180095821  mov     [rbx+58h], r15d
0x180095825  mov     edx, 0FF00h
0x18009582a  and     ax, dx
0x18009582d  or      cx, ax
0x180095830  mov     [rbx+56h], cx
0x180095834  mov     eax, [rbx+60h]
0x180095837  mov     ecx, [rbx+64h]
0x18009583a  mov     [rbp+57h+var_C4], eax
0x18009583d  mov     [rbp+57h+var_C0], ecx
0x180095840  inc     r15d
0x180095843  cmp     r15d, r12d
0x180095846  jbe     loc_1800957AD
0x18009584c  mov     r14d, [rbp+57h+var_C8]
0x180095850  mov     r9, [rbp+57h+var_A8]
0x180095854  mov     rcx, [rbp+57h+var_90]
0x180095858  mov     rax, [rbx+30h]
0x18009585c  mov     edx, 88h
0x180095861  mov     r12, [rbp+57h+var_88]
0x180095865  mov     [rax+rcx*8], r9
0x180095869  mov     eax, r14d
0x18009586c  neg     eax
0x18009586e  mov     dword ptr [rbx+0A0h], 0
0x180095878  mov     eax, r14d
0x18009587b  mov     qword ptr [rbx+98h], 0
0x180095886  sbb     rcx, rcx
0x180095889  not     rcx
0x18009588c  and     rcx, rdx
0x18009588f  neg     eax
0x180095891  sbb     r8, r8
0x180095894  and     r8, rdx
0x180095897  lea     rdx, [rcx+r12]; Src
0x18009589b  add     r8, 7F78h; Size
0x1800958a2  add     rcx, r9; void *
0x1800958a5  call    memcpy_0
0x1800958aa  call    sehInjectFault
0x1800958af  cmp     r15d, dword ptr [rbp+57h+var_A0]
0x1800958b3  jbe     short loc_1800958CA
0x1800958b5  mov     rdx, [rbp+57h+var_78]
0x1800958b9  inc     r14d
0x1800958bc  mov     [rbp+57h+var_C8], r14d
0x1800958c0  cmp     r14d, dword ptr [rbp+57h+var_80]
0x1800958c4  jbe     loc_18009572D
0x1800958ca  mov     rcx, r13
0x1800958cd  mov     qword ptr [rbx+90h], 0
0x1800958d8  call    sqlite3_free
0x1800958dd  mov     r12d, [rbp+57h+var_BC]
0x1800958e1  mov     r15d, [rbp+57h+var_C4]
0x1800958e5  mov     r13d, [rbp+57h+var_C0]
0x1800958e9  test    edi, edi
0x1800958eb  jnz     loc_1800959A5
0x1800958f1  mov     rcx, rbx
0x1800958f4  mov     [rbx+60h], r15d
0x1800958f8  mov     [rbx+64h], r13d
0x1800958fc  call    walIndexWriteHdr
0x180095901  call    sehInjectFault
0x180095906  mov     rax, [rbx+30h]
0x18009590a  xor     r13d, r13d
0x18009590d  mov     r14, [rax]
0x180095910  lea     esi, [r13+1]
0x180095914  mov     [r14+60h], r13d
0x180095918  mov     eax, [rbx+58h]
0x18009591b  mov     [r14+80h], eax
0x180095922  mov     [r14+64h], r13d
0x180095926  cmp     esi, 5
0x180095929  jge     short loc_180095983
0x18009592b  mov     r8d, 1
0x180095931  lea     edx, [rsi+3]
0x180095934  mov     rcx, rbx
0x180095937  call    walLockExclusive
0x18009593c  mov     edi, eax
0x18009593e  test    eax, eax
0x180095940  jnz     short loc_18009597A
0x180095942  cmp     esi, 1
0x180095945  jnz     short loc_180095956
0x180095947  cmp     [rbx+58h], r13d
0x18009594b  jz      short loc_180095956
0x18009594d  mov     eax, [rbx+58h]
0x180095950  mov     [r14+68h], eax
0x180095954  jmp     short loc_180095962
0x180095956  movsxd  rax, esi
0x180095959  mov     dword ptr [r14+rax*4+64h], 0FFFFFFFFh
0x180095962  call    sehInjectFault
0x180095967  mov     r8d, 1
0x18009596d  lea     edx, [rsi+3]
0x180095970  mov     rcx, rbx
0x180095973  call    walUnlockExclusive
0x180095978  jmp     short loc_18009597F
0x18009597a  cmp     eax, 5
0x18009597d  jnz     short loc_1800959A5
0x18009597f  inc     esi
0x180095981  jmp     short loc_180095926
0x180095983  cmp     [rbx+5Ch], r13d
0x180095987  jz      short loc_1800959A5
0x180095989  mov     r9, [rbx+80h]
0x180095990  lea     rdx, aRecoveredDFram; "recovered %d frames from WAL file %s"
0x180095997  mov     r8d, [rbx+58h]
0x18009599b  mov     ecx, 11Bh
0x1800959a0  call    sqlite3_log
0x1800959a5  mov     edx, [rbp+57h+var_B8]
0x1800959a8  mov     r8d, r12d
0x1800959ab  mov     rcx, rbx
0x1800959ae  call    walUnlockExclusive
0x1800959b3  mov     eax, edi
0x1800959b5  mov     rcx, [rbp+57h+var_50]
0x1800959b9  xor     rcx, rsp; StackCookie
0x1800959bc  call    __security_check_cookie
0x1800959c1  add     rsp, 0C8h
0x1800959c8  pop     r15
0x1800959ca  pop     r14
  ... truncated ...
```
