# winOpen

- ea: `0x1800bf940`
- end: `0x1800bfcd6`
- name: `winOpen`
- size: `918`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1800bfcdc`

## callees

- `0x180002250`
- `0x180002cf8`
- `0x18006db1c`
- `0x1800a98a0`
- `0x1800ae540`
- `0x1800be1d0`
- `0x1800bee34`
- `0x1800bf47c`
- `0x1800bf558`
- `0x1800bf940`
- `0x1800c01b8`
- `0x1800c0f54`
- `0x1800ca010`

## string_xrefs

- `0x1800bfbde`: `winOpen`

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
      while ( !(unsigned int)((__int64 (__fastcall *)(__int64, _QWORD, _OWORD *))off_18010C018)(v14, 0, v46) )
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
        v42 = ((__int64 (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD, int, int, _QWORD))off_18010BE80)(
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
          if ( qword_18010F860 )
            qword_18010F860();
          v31 = winAccess(v19, v21, 2, &v32);
          if ( qword_18010F868 )
            qword_18010F868();
          if ( !v31 && v32 )
            break;
        }
        v23 = winRetryIoerr(&v33, &v34);
        v20 = v36;
      }
      while ( v23 );
      winLogIoerr(v33, 52000);
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
        winLogErrorAtLine(14, v27, (unsigned int)"winOpen", v28, 52015);
        return sqlite3CantopenError(52016);
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
          v30 = &qword_1800CBA70;
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
        v5[11] = (__int64 *)qword_18010EF78;
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
0x1800bf940  push    rbp
0x1800bf942  push    rbx
0x1800bf943  push    rsi
0x1800bf944  push    rdi
0x1800bf945  push    r12
0x1800bf947  push    r13
0x1800bf949  push    r14
0x1800bf94b  push    r15
0x1800bf94d  lea     rbp, [rsp-17h]
0x1800bf952  sub     rsp, 0D8h
0x1800bf959  mov     rax, cs:__security_cookie
0x1800bf960  xor     rax, rsp
0x1800bf963  mov     [rbp+4Fh+var_50], rax
0x1800bf967  mov     rax, [rbp+4Fh+arg_20]
0x1800bf96b  mov     rbx, r8
0x1800bf96e  mov     [rbp+4Fh+var_90], rbx
0x1800bf972  mov     edi, r9d
0x1800bf975  mov     [rbp+4Fh+var_80], rax
0x1800bf979  mov     r12, rdx
0x1800bf97c  mov     [rbp+4Fh+var_88], rdx
0x1800bf980  mov     r14, rcx
0x1800bf983  mov     [rbp+4Fh+var_C0], rcx
0x1800bf987  xor     r13d, r13d
0x1800bf98a  xor     edx, edx; Val
0x1800bf98c  mov     [rbp+4Fh+var_B4], edi
0x1800bf98f  mov     rcx, rbx; void *
0x1800bf992  mov     [rbp+4Fh+var_C4], r13d
0x1800bf996  mov     [rbp+4Fh+var_C8], r13d
0x1800bf99a  mov     rsi, r13
0x1800bf99d  mov     [rbp+4Fh+var_A8], r13
0x1800bf9a1  lea     r8d, [rdx+60h]; Size
0x1800bf9a5  call    memset_0
0x1800bf9aa  mov     qword ptr [rbx+10h], 0FFFFFFFFFFFFFFFFh
0x1800bf9b2  test    r12, r12
0x1800bf9b5  jnz     short loc_1800BF9D4
0x1800bf9b7  lea     rdx, [rbp+4Fh+var_A8]
0x1800bf9bb  mov     rcx, r14
0x1800bf9be  call    winGetTempname
0x1800bf9c3  test    eax, eax
0x1800bf9c5  jnz     loc_1800BFCB6
0x1800bf9cb  mov     rsi, [rbp+4Fh+var_A8]
0x1800bf9cf  mov     rax, rsi
0x1800bf9d2  jmp     short loc_1800BF9D7
0x1800bf9d4  mov     rax, r12
0x1800bf9d7  mov     rcx, rax
0x1800bf9da  mov     [rbp+4Fh+var_A0], rax
0x1800bf9de  call    winUtf8ToUnicode
0x1800bf9e3  mov     r14, rax
0x1800bf9e6  test    rax, rax
0x1800bf9e9  jz      loc_1800BFCA9
0x1800bf9ef  xorps   xmm0, xmm0
0x1800bf9f2  mov     [rbp+4Fh+var_CC], r13d
0x1800bf9f6  xor     eax, eax
0x1800bf9f8  mov     [rsp+110h+var_D0], r13d
0x1800bf9fd  movups  [rbp+4Fh+var_78], xmm0
0x1800bfa01  mov     [rbp+4Fh+var_58], eax
0x1800bfa04  movups  [rbp+4Fh+var_68], xmm0
0x1800bfa08  mov     rax, cs:off_18010C018
0x1800bfa0f  lea     r8, [rbp+4Fh+var_78]
0x1800bfa13  xor     edx, edx
0x1800bfa15  mov     rcx, r14
0x1800bfa18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bfa1d  test    eax, eax
0x1800bfa1f  jnz     short loc_1800BFA35
0x1800bfa21  lea     rdx, [rbp+4Fh+var_CC]
0x1800bfa25  lea     rcx, [rsp+110h+var_D0]
0x1800bfa2a  call    winRetryIoerr
0x1800bfa2f  test    eax, eax
0x1800bfa31  jnz     short loc_1800BFA08
0x1800bfa33  jmp     short loc_1800BFA45
0x1800bfa35  cmp     dword ptr [rbp+4Fh+var_78], 0FFFFFFFFh
0x1800bfa39  jz      short loc_1800BFA45
0x1800bfa3b  test    byte ptr [rbp+4Fh+var_78], 10h
0x1800bfa3f  jnz     loc_1800BFBC1
0x1800bfa45  mov     eax, edi
0x1800bfa47  mov     r15d, edi
0x1800bfa4a  and     eax, 1
0x1800bfa4d  and     r15d, 2
0x1800bfa51  mov     [rbp+4Fh+var_AC], eax
0x1800bfa54  mov     ecx, edi
0x1800bfa56  and     ecx, 10h
0x1800bfa59  mov     ebx, edi
0x1800bfa5b  and     ebx, 8
0x1800bfa5e  mov     [rbp+4Fh+var_B0], ecx
0x1800bfa61  mov     eax, r15d
0x1800bfa64  neg     eax
0x1800bfa66  sbb     eax, eax
0x1800bfa68  and     eax, 40000000h
0x1800bfa6d  add     eax, 80000000h
0x1800bfa72  mov     [rsp+110h+var_D0], eax
0x1800bfa76  test    ecx, ecx
0x1800bfa78  jz      short loc_1800BFA82
0x1800bfa7a  mov     r13d, 1
0x1800bfa80  jmp     short loc_1800BFA93
0x1800bfa82  mov     al, dil
0x1800bfa85  and     al, 4
0x1800bfa87  neg     al
0x1800bfa89  sbb     r13d, r13d
0x1800bfa8c  neg     r13d
0x1800bfa8f  add     r13d, 3
0x1800bfa93  xor     r8d, r8d
0x1800bfa96  lea     rdx, aExclusive; "exclusive"
0x1800bfa9d  mov     rcx, r12
0x1800bfaa0  call    sqlite3_uri_boolean
0x1800bfaa5  mov     r12d, [rsp+110h+var_D0]
0x1800bfaaa  xor     ecx, ecx
0x1800bfaac  mov     rsi, [rbp+4Fh+var_C0]
0x1800bfab0  test    eax, eax
0x1800bfab2  mov     edx, 3
0x1800bfab7  cmovnz  edx, ecx
0x1800bfaba  neg     ebx
0x1800bfabc  mov     rbx, [rbp+4Fh+var_A0]
0x1800bfac0  sbb     edi, edi
0x1800bfac2  mov     [rbp+4Fh+var_B8], edx
0x1800bfac5  and     edi, 4000082h
0x1800bfacb  sub     edi, 0FFFFFF80h
0x1800bface  mov     rax, cs:off_18010BE80
0x1800bfad5  mov     r8d, edx
0x1800bfad8  mov     [rsp+110h+var_E0], 0
0x1800bfae1  mov     edx, r12d
0x1800bfae4  mov     [rsp+110h+var_E8], edi
0x1800bfae8  xor     r9d, r9d
0x1800bfaeb  mov     rcx, r14
0x1800bfaee  mov     [rsp+110h+var_F0], r13d
0x1800bfaf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bfaf8  mov     [rbp+4Fh+var_98], rax
0x1800bfafc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800bfb00  jnz     short loc_1800BFB6E
0x1800bfb02  test    r15d, r15d
0x1800bfb05  jz      short loc_1800BFB56
0x1800bfb07  mov     rax, cs:qword_18010F860
0x1800bfb0e  mov     [rbp+4Fh+var_CC], 0
0x1800bfb15  test    rax, rax
0x1800bfb18  jz      short loc_1800BFB1F
0x1800bfb1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bfb1f  lea     r9, [rbp+4Fh+var_CC]
0x1800bfb23  mov     r8d, 2
0x1800bfb29  mov     rdx, rbx
0x1800bfb2c  mov     rcx, rsi
0x1800bfb2f  call    winAccess
0x1800bfb34  mov     [rsp+110h+var_D0], eax
0x1800bfb38  mov     rax, cs:qword_18010F868
0x1800bfb3f  test    rax, rax
0x1800bfb42  jz      short loc_1800BFB49
0x1800bfb44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bfb49  cmp     [rsp+110h+var_D0], 0
0x1800bfb4e  jnz     short loc_1800BFB56
0x1800bfb50  cmp     [rbp+4Fh+var_CC], 0
0x1800bfb54  jnz     short loc_1800BFB6E
0x1800bfb56  lea     rdx, [rbp+4Fh+var_C4]
0x1800bfb5a  lea     rcx, [rbp+4Fh+var_C8]
0x1800bfb5e  call    winRetryIoerr
0x1800bfb63  mov     edx, [rbp+4Fh+var_B8]
0x1800bfb66  test    eax, eax
0x1800bfb68  jnz     loc_1800BFACE
0x1800bfb6e  mov     ecx, [rbp+4Fh+var_C8]
0x1800bfb71  mov     edx, 0CB20h
0x1800bfb76  call    winLogIoerr
0x1800bfb7b  mov     r13, [rbp+4Fh+var_98]
0x1800bfb7f  mov     rbx, [rbp+4Fh+var_90]
0x1800bfb83  mov     edi, [rbp+4Fh+var_B4]
0x1800bfb86  mov     rsi, [rbp+4Fh+var_A8]
0x1800bfb8a  mov     r12, [rbp+4Fh+var_88]
0x1800bfb8e  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x1800bfb92  jnz     short loc_1800BFC0D
0x1800bfb94  mov     rcx, r14
0x1800bfb97  call    sqlite3_free
0x1800bfb9c  mov     rcx, rsi
0x1800bfb9f  call    sqlite3_free
0x1800bfba4  xor     r13d, r13d
0x1800bfba7  test    r15d, r15d
0x1800bfbaa  jz      short loc_1800BFBDB
0x1800bfbac  cmp     [rbp+4Fh+var_B0], r13d
0x1800bfbb0  jnz     short loc_1800BFBDB
0x1800bfbb2  mov     r14, [rbp+4Fh+var_C0]
0x1800bfbb6  and     edi, 0FFFFFFF9h
0x1800bfbb9  or      edi, 1
0x1800bfbbc  jmp     loc_1800BF98A
0x1800bfbc1  mov     rcx, r14
0x1800bfbc4  call    sqlite3_free
0x1800bfbc9  mov     rcx, rsi
0x1800bfbcc  call    sqlite3_free
0x1800bfbd1  mov     eax, 20Eh
0x1800bfbd6  jmp     loc_1800BFCB6
0x1800bfbdb  mov     edx, [rbp+4Fh+var_C4]
0x1800bfbde  lea     r8, aWinopen; "winOpen"
0x1800bfbe5  mov     r9, [rbp+4Fh+var_A0]
0x1800bfbe9  mov     ecx, 0Eh
0x1800bfbee  mov     [rbx+20h], edx
0x1800bfbf1  mov     [rsp+110h+var_F0], 0CB2Fh
0x1800bfbf9  call    winLogErrorAtLine
0x1800bfbfe  mov     ecx, 0CB30h
0x1800bfc03  call    sqlite3CantopenError
0x1800bfc08  jmp     loc_1800BFCB6
0x1800bfc0d  mov     rcx, [rbp+4Fh+var_80]
0x1800bfc11  test    rcx, rcx
0x1800bfc14  jz      short loc_1800BFC21
0x1800bfc16  neg     r15d
0x1800bfc19  sbb     eax, eax
0x1800bfc1b  neg     eax
0x1800bfc1d  inc     eax
0x1800bfc1f  mov     [rcx], eax
0x1800bfc21  mov     rax, [rbp+4Fh+var_C0]
0x1800bfc25  mov     rcx, r14
0x1800bfc28  mov     r15, [rax+20h]
0x1800bfc2c  call    sqlite3_free
0x1800bfc31  mov     rcx, rsi
0x1800bfc34  call    sqlite3_free
0x1800bfc39  xor     esi, esi
0x1800bfc3b  test    r15, r15
0x1800bfc3e  jz      short loc_1800BFC45
0x1800bfc40  mov     rax, [r15]
0x1800bfc43  jmp     short loc_1800BFC4C
0x1800bfc45  lea     rax, qword_1800CBA70
0x1800bfc4c  mov     [rbx], rax
0x1800bfc4f  mov     rax, [rbp+4Fh+var_C0]
0x1800bfc53  mov     [rbx+8], rax
0x1800bfc57  mov     [rbx+10h], r13
0x1800bfc5b  cmp     [rbp+4Fh+var_AC], esi
0x1800bfc5e  jz      short loc_1800BFC64
0x1800bfc60  or      byte ptr [rbx+1Ch], 2
0x1800bfc64  bt      edi, 8
0x1800bfc68  jnb     short loc_1800BFC87
0x1800bfc6a  mov     r8d, 1
0x1800bfc70  lea     rdx, aPsow; "psow"
0x1800bfc77  mov     rcx, r12
0x1800bfc7a  call    sqlite3_uri_boolean
0x1800bfc7f  test    eax, eax
0x1800bfc81  jz      short loc_1800BFC87
0x1800bfc83  or      byte ptr [rbx+1Ch], 10h
0x1800bfc87  mov     [rbx+20h], esi
0x1800bfc8a  mov     [rbx+30h], r12
0x1800bfc8e  mov     [rbx+40h], rsi
0x1800bfc92  mov     [rbx+48h], rsi
0x1800bfc96  mov     [rbx+50h], rsi
0x1800bfc9a  mov     rax, cs:qword_18010EF78
0x1800bfca1  mov     [rbx+58h], rax
0x1800bfca5  xor     eax, eax
0x1800bfca7  jmp     short loc_1800BFCB6
0x1800bfca9  mov     rcx, rsi
0x1800bfcac  call    sqlite3_free
0x1800bfcb1  mov     eax, 0C0Ah
0x1800bfcb6  mov     rcx, [rbp+4Fh+var_50]
0x1800bfcba  xor     rcx, rsp; StackCookie
0x1800bfcbd  call    __security_check_cookie
0x1800bfcc2  add     rsp, 0D8h
0x1800bfcc9  pop     r15
0x1800bfccb  pop     r14
0x1800bfccd  pop     r13
0x1800bfccf  pop     r12
0x1800bfcd1  pop     rdi
0x1800bfcd2  pop     rsi
0x1800bfcd3  pop     rbx
0x1800bfcd4  pop     rbp
0x1800bfcd5  retn
```
