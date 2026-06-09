# sqlite3RunParser

- ea: `0x180021404`
- end: `0x1800217c3`
- name: `sqlite3RunParser`
- size: `959`
- prototype: ``
- caller_count: `4`
- callee_count: `15`
- tags: ``

## callers

- `0x180020bf0`
- `0x18004a9b8`
- `0x18008d3e4`
- `0x18009bf50`

## callees

- `0x180001f54`
- `0x180011bcc`
- `0x180021404`
- `0x180025770`
- `0x1800257e0`
- `0x180031e2c`
- `0x180040e00`
- `0x180041eb0`
- `0x18004f744`
- `0x18004f7c8`
- `0x18005166c`
- `0x18005a234`
- `0x180063014`
- `0x180078968`
- `0x1800789c0`

## string_xrefs

- `0x18002173e`: `unrecognized token: "%T"`

## pseudocode

```c
__int64 __fastcall sqlite3RunParser(__int64 *a1, _BYTE *a2)
{
  __int64 v2; // rdi
  int v5; // r14d
  int v6; // r12d
  __int64 v7; // r13
  unsigned int Token; // eax
  unsigned int v9; // r15d
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // r8
  const char *v13; // rax
  __int64 v14; // rcx
  unsigned int v15; // r14d
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // rdx
  const char *v21; // rax
  int v22; // eax
  int v23; // eax
  int v24; // eax
  int v25[4]; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v26; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v27[4]; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v28[594]; // [rsp+60h] [rbp-A0h] BYREF
  char v29; // [rsp+9A8h] [rbp+8A8h] BYREF

  v2 = *a1;
  v25[0] = 0;
  v5 = -1;
  memset_0(v27, 0, 0x980u);
  v6 = *(_DWORD *)(v2 + 140);
  if ( !*(_DWORD *)(v2 + 216) )
    *(_DWORD *)(v2 + 408) = 0;
  *((_DWORD *)a1 + 6) = 0;
  v27[3] = v28;
  v27[2] = &v29;
  v27[0] = v28;
  a1[43] = (__int64)a2;
  v27[1] = a1;
  v28[0] = 0;
  v7 = *(_QWORD *)(v2 + 352);
  *(_QWORD *)(v2 + 352) = a1;
  while ( 1 )
  {
    while ( 1 )
    {
      Token = sqlite3GetToken(a2, v25);
      v9 = Token;
      v6 -= Token;
      if ( v6 < 0 )
      {
        *((_DWORD *)a1 + 6) = 18;
        goto LABEL_10;
      }
      v10 = (unsigned int)v25[0];
      if ( v25[0] < 164 )
        goto LABEL_6;
      if ( *(_DWORD *)(v2 + 408) )
      {
        *((_DWORD *)a1 + 6) = 9;
LABEL_10:
        ++*((_DWORD *)a1 + 12);
        goto LABEL_11;
      }
      v10 = (unsigned int)v25[0];
      if ( v25[0] != 184 )
        break;
      a2 += (int)Token;
    }
    if ( *a2 )
      break;
    if ( v5 == 1 )
    {
      v10 = 0;
    }
    else
    {
      if ( !v5 )
        goto LABEL_11;
      v10 = 1;
    }
    v25[0] = v10;
    v9 = 0;
LABEL_6:
    a1[36] = (__int64)a2;
    *((_DWORD *)a1 + 74) = v9;
    v26 = *((_OWORD *)a1 + 18);
    sqlite3Parser(v27, v10, &v26);
    a2 += (int)v9;
    if ( *((_DWORD *)a1 + 6) )
      goto LABEL_11;
    v5 = v25[0];
  }
  switch ( v25[0] )
  {
    case 164:
      *(_QWORD *)&v26 = a2 + 6;
      if ( (unsigned int)getToken((__int64 *)&v26) == 59 )
      {
        v23 = getToken((__int64 *)&v26);
        v10 = 164;
        if ( v23 != 24 )
          v10 = 59;
        goto LABEL_26;
      }
      goto LABEL_49;
    case 165:
      *(_QWORD *)&v26 = a2 + 4;
      if ( v5 == 23 )
      {
        v22 = getToken((__int64 *)&v26);
        if ( v22 == 22 || v22 == 59 )
        {
          v10 = 165;
LABEL_26:
          v25[0] = v10;
          goto LABEL_6;
        }
      }
LABEL_49:
      v10 = 59;
      goto LABEL_26;
    case 166:
      *(_QWORD *)&v26 = a2 + 6;
      if ( v5 != 23 || (v24 = getToken((__int64 *)&v26), v10 = 166, v24 != 22) )
        v10 = 59;
      goto LABEL_26;
    case 183:
      goto LABEL_6;
  }
  *(_QWORD *)&v26 = a2;
  *((_QWORD *)&v26 + 1) = Token;
  sqlite3ErrorMsg(a1, "unrecognized token: \"%T\"", &v26);
LABEL_11:
  sqlite3ParserFinalize(v27);
  if ( *(_BYTE *)(v2 + 103) )
    *((_DWORD *)a1 + 6) = 7;
  v13 = (const char *)a1[1];
  if ( v13 )
  {
LABEL_24:
    sqlite3_log(*((unsigned int *)a1 + 6), "%s in \"%s\"", v13, (const char *)a1[43]);
    v15 = 1;
  }
  else
  {
    v14 = *((unsigned int *)a1 + 6);
    v15 = 0;
    if ( (_DWORD)v14 && (_DWORD)v14 != 101 )
    {
      v21 = (const char *)sqlite3ErrStr(v14, v11, v12);
      v13 = (const char *)sqlite3MPrintf(v2, "%s", v21);
      a1[1] = (__int64)v13;
      goto LABEL_24;
    }
  }
  v16 = a1[50];
  a1[43] = (__int64)a2;
  sqlite3_free(v16);
  v17 = a1[44];
  if ( v17 && !*((_BYTE *)a1 + 308) )
    sqlite3DeleteTable(v2, v17);
  v18 = a1[46];
  if ( v18 && *((_BYTE *)a1 + 308) < 2u )
    sqlite3DeleteTrigger(v2, v18);
  v19 = a1[41];
  if ( v19 )
    sqlite3DbNNFreeNN(v2, v19);
  *(_QWORD *)(v2 + 352) = v7;
  return v15;
}

```

## disassembly

```asm
0x180021404  mov     [rsp-8+arg_10], rbx
0x180021409  push    rbp
0x18002140a  push    rsi
0x18002140b  push    rdi
0x18002140c  push    r12
0x18002140e  push    r13
0x180021410  push    r14
0x180021412  push    r15
0x180021414  lea     rbp, [rsp-8D0h]
0x18002141c  sub     rsp, 9D0h
0x180021423  mov     rax, cs:__security_cookie
0x18002142a  xor     rax, rsp
0x18002142d  mov     [rbp+900h+var_40], rax
0x180021434  mov     rdi, [rcx]
0x180021437  mov     rsi, rdx
0x18002143a  mov     rbx, rcx
0x18002143d  xor     r15d, r15d
0x180021440  xor     edx, edx; Val
0x180021442  mov     [rsp+0A00h+var_9E0], r15d
0x180021447  lea     rcx, [rsp+0A00h+var_9C0]; void *
0x18002144c  mov     r8d, 980h; Size
0x180021452  or      r14d, 0FFFFFFFFh
0x180021456  call    memset_0
0x18002145b  mov     r12d, [rdi+8Ch]
0x180021462  cmp     [rdi+0D8h], r15d
0x180021469  jnz     short loc_180021472
0x18002146b  mov     [rdi+198h], r15d
0x180021472  lea     rax, [rsp+0A00h+var_9A0]
0x180021477  mov     [rbx+18h], r15d
0x18002147b  mov     [rsp+0A00h+var_9A8], rax
0x180021480  lea     rax, [rbp+900h+var_58]
0x180021487  mov     [rsp+0A00h+var_9B0], rax
0x18002148c  lea     rax, [rsp+0A00h+var_9A0]
0x180021491  mov     [rsp+0A00h+var_9C0], rax
0x180021496  mov     [rbx+158h], rsi
0x18002149d  mov     [rsp+0A00h+var_9B8], rbx
0x1800214a2  mov     [rsp+0A00h+var_9A0], r15d
0x1800214a7  mov     r13, [rdi+160h]
0x1800214ae  mov     [rdi+160h], rbx
0x1800214b5  lea     rdx, [rsp+0A00h+var_9E0]
0x1800214ba  mov     rcx, rsi
0x1800214bd  call    sqlite3GetToken
0x1800214c2  movsxd  r15, eax
0x1800214c5  sub     r12d, r15d
0x1800214c8  js      loc_18002176A
0x1800214ce  mov     edx, [rsp+0A00h+var_9E0]
0x1800214d2  mov     eax, 0A4h
0x1800214d7  cmp     edx, eax
0x1800214d9  jge     short loc_180021518
0x1800214db  mov     [rbx+120h], rsi
0x1800214e2  lea     r8, [rsp+0A00h+var_9D0]
0x1800214e7  mov     [rbx+128h], r15d
0x1800214ee  lea     rcx, [rsp+0A00h+var_9C0]
0x1800214f3  movups  xmm0, xmmword ptr [rbx+120h]
0x1800214fa  movdqu  [rsp+0A00h+var_9D0], xmm0
0x180021500  call    sqlite3Parser
0x180021505  movsxd  rax, r15d
0x180021508  add     rsi, rax
0x18002150b  cmp     dword ptr [rbx+18h], 0
0x18002150f  jnz     short loc_180021530
0x180021511  mov     r14d, [rsp+0A00h+var_9E0]
0x180021516  jmp     short loc_1800214B5
0x180021518  mov     ecx, [rdi+198h]
0x18002151e  test    ecx, ecx
0x180021520  jz      loc_1800215D6
0x180021526  mov     dword ptr [rbx+18h], 9
0x18002152d  inc     dword ptr [rbx+30h]
0x180021530  lea     rcx, [rsp+0A00h+var_9C0]
0x180021535  call    sqlite3ParserFinalize
0x18002153a  cmp     byte ptr [rdi+67h], 0
0x18002153e  jnz     loc_180021776
0x180021544  mov     rax, [rbx+8]
0x180021548  test    rax, rax
0x18002154b  jnz     loc_180021612
0x180021551  mov     ecx, [rbx+18h]
0x180021554  xor     r14d, r14d
0x180021557  test    ecx, ecx
0x180021559  jnz     loc_1800215EE
0x18002155f  mov     rcx, [rbx+190h]
0x180021566  mov     [rbx+158h], rsi
0x18002156d  call    sqlite3_free
0x180021572  mov     rdx, [rbx+160h]
0x180021579  test    rdx, rdx
0x18002157c  jnz     loc_180021782
0x180021582  mov     rdx, [rbx+170h]
0x180021589  test    rdx, rdx
0x18002158c  jnz     loc_18002179C
0x180021592  mov     rdx, [rbx+148h]
0x180021599  test    rdx, rdx
0x18002159c  jnz     loc_1800217B6
0x1800215a2  mov     [rdi+160h], r13
0x1800215a9  mov     eax, r14d
0x1800215ac  mov     rcx, [rbp+900h+var_40]
0x1800215b3  xor     rcx, rsp; StackCookie
0x1800215b6  call    __security_check_cookie
0x1800215bb  mov     rbx, [rsp+0A00h+arg_10]
0x1800215c3  add     rsp, 9D0h
0x1800215ca  pop     r15
0x1800215cc  pop     r14
0x1800215ce  pop     r13
0x1800215d0  pop     r12
0x1800215d2  pop     rdi
0x1800215d3  pop     rsi
0x1800215d4  pop     rbp
0x1800215d5  retn
0x1800215d6  mov     edx, [rsp+0A00h+var_9E0]
0x1800215da  cmp     edx, 0B8h
0x1800215e0  jnz     loc_1800216E0
0x1800215e6  add     rsi, r15
0x1800215e9  jmp     loc_1800214B5
0x1800215ee  cmp     ecx, 65h ; 'e'
0x1800215f1  jz      loc_18002155F
0x1800215f7  call    sqlite3ErrStr
0x1800215fc  mov     r8, rax
0x1800215ff  lea     rdx, aS_7; "%s"
0x180021606  mov     rcx, rdi
0x180021609  call    sqlite3MPrintf
0x18002160e  mov     [rbx+8], rax
0x180021612  mov     r9, [rbx+158h]
0x180021619  lea     rdx, aSInS; "%s in \"%s\""
0x180021620  mov     ecx, [rbx+18h]
0x180021623  mov     r8, rax
0x180021626  call    sqlite3_log
0x18002162b  mov     r14d, 1
0x180021631  jmp     loc_18002155F
0x180021636  mov     edx, 0A5h
0x18002163b  mov     [rsp+0A00h+var_9E0], edx
0x18002163f  jmp     loc_1800214DB
0x180021644  lea     rax, [rsi+4]
0x180021648  mov     qword ptr [rsp+0A00h+var_9D0], rax
0x18002164d  cmp     r14d, 17h
0x180021651  jnz     loc_18002175C
0x180021657  lea     rcx, [rsp+0A00h+var_9D0]
0x18002165c  call    getToken
0x180021661  cmp     eax, 16h
0x180021664  jz      short loc_180021636
0x180021666  mov     r14d, 3Bh ; ';'
0x18002166c  cmp     eax, r14d
0x18002166f  jz      short loc_180021636
0x180021671  jmp     loc_180021762
0x180021676  lea     rax, [rsi+6]
0x18002167a  lea     rcx, [rsp+0A00h+var_9D0]
0x18002167f  mov     qword ptr [rsp+0A00h+var_9D0], rax
0x180021684  call    getToken
0x180021689  mov     r14d, 3Bh ; ';'
0x18002168f  cmp     eax, r14d
0x180021692  jnz     loc_180021762
0x180021698  lea     rcx, [rsp+0A00h+var_9D0]
0x18002169d  call    getToken
0x1800216a2  cmp     eax, 18h
0x1800216a5  lea     edx, [r14+69h]
0x1800216a9  cmovnz  edx, r14d
0x1800216ad  jmp     short loc_18002163B
0x1800216af  lea     rax, [rsi+6]
0x1800216b3  mov     qword ptr [rsp+0A00h+var_9D0], rax
0x1800216b8  cmp     r14d, 17h
0x1800216bc  jnz     short loc_1800216D6
0x1800216be  lea     rcx, [rsp+0A00h+var_9D0]
0x1800216c3  call    getToken
0x1800216c8  mov     edx, 0A6h
0x1800216cd  cmp     eax, 16h
0x1800216d0  jz      loc_18002163B
0x1800216d6  mov     edx, 3Bh ; ';'
0x1800216db  jmp     loc_18002163B
0x1800216e0  cmp     byte ptr [rsi], 0
0x1800216e3  jnz     short loc_180021709
0x1800216e5  cmp     r14d, 1
0x1800216e9  jnz     short loc_1800216EF
0x1800216eb  xor     edx, edx
0x1800216ed  jmp     short loc_1800216FD
0x1800216ef  test    r14d, r14d
0x1800216f2  jz      loc_180021530
0x1800216f8  mov     edx, 1
0x1800216fd  mov     [rsp+0A00h+var_9E0], edx
0x180021701  xor     r15d, r15d
0x180021704  jmp     loc_1800214DB
0x180021709  cmp     edx, eax
0x18002170b  jz      loc_180021676
0x180021711  cmp     edx, 0A5h
0x180021717  jz      loc_180021644
0x18002171d  cmp     edx, 0A6h
0x180021723  jz      short loc_1800216AF
0x180021725  cmp     edx, 0B7h
0x18002172b  jz      loc_1800214DB
0x180021731  lea     r8, [rsp+0A00h+var_9D0]
0x180021736  mov     dword ptr [rsp+0A00h+var_9D0+0Ch], 0
0x18002173e  lea     rdx, aUnrecognizedTo_0; "unrecognized token: \"%T\""
0x180021745  mov     qword ptr [rsp+0A00h+var_9D0], rsi
0x18002174a  mov     rcx, rbx
0x18002174d  mov     dword ptr [rsp+0A00h+var_9D0+8], r15d
0x180021752  call    sqlite3ErrorMsg
0x180021757  jmp     loc_180021530
0x18002175c  mov     r14d, 3Bh ; ';'
0x180021762  mov     edx, r14d
0x180021765  jmp     loc_18002163B
0x18002176a  mov     dword ptr [rbx+18h], 12h
0x180021771  jmp     loc_18002152D
0x180021776  mov     dword ptr [rbx+18h], 7
0x18002177d  jmp     loc_180021544
0x180021782  cmp     byte ptr [rbx+134h], 0
0x180021789  jnz     loc_180021582
0x18002178f  mov     rcx, rdi
0x180021792  call    sqlite3DeleteTable
0x180021797  jmp     loc_180021582
0x18002179c  cmp     byte ptr [rbx+134h], 2
0x1800217a3  jnb     loc_180021592
0x1800217a9  mov     rcx, rdi
0x1800217ac  call    sqlite3DeleteTrigger
0x1800217b1  jmp     loc_180021592
0x1800217b6  mov     rcx, rdi
0x1800217b9  call    sqlite3DbNNFreeNN
0x1800217be  jmp     loc_1800215A2
```
