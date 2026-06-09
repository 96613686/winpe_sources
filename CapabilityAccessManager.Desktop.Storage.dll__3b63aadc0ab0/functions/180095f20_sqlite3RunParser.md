# sqlite3RunParser

- ea: `0x180095f20`
- end: `0x18009648e`
- name: `sqlite3RunParser`
- size: `1390`
- prototype: ``
- caller_count: `4`
- callee_count: `12`
- tags: `installer_update`

## callers

- `0x180010500`
- `0x18005aed0`
- `0x180088ea0`
- `0x180091d10`

## callees

- `0x180003060`
- `0x180005980`
- `0x180016970`
- `0x180035360`
- `0x18004dba0`
- `0x180072a30`
- `0x1800743d0`
- `0x180082cd0`
- `0x180088530`
- `0x18008bf60`
- `0x180095f20`
- `0x1800d8990`

## string_xrefs

- `0x180096321`: `unrecognized token: "%T"`
- `0x180096346`: `abort due to ROLLBACK`

## pseudocode

```c
__int64 __fastcall sqlite3RunParser(__int64 *a1, _BYTE *a2)
{
  __int64 v2; // r14
  _BYTE *v4; // r15
  int v5; // edi
  int v6; // r13d
  int Token; // eax
  int v8; // r13d
  int v9; // r12d
  unsigned int v10; // ebx
  _BYTE *v11; // rbx
  unsigned __int64 v12; // rax
  __int64 v13; // rdx
  unsigned __int64 v14; // rax
  __int64 v15; // rdx
  _BYTE *v16; // rbx
  int v17; // ecx
  unsigned __int64 v18; // rax
  __int64 v19; // rdx
  _BYTE *v20; // rbx
  unsigned __int64 v21; // rax
  __int64 v22; // rdx
  int v23; // eax
  __int64 i; // rcx
  const char *v25; // rax
  int v26; // edx
  unsigned int v27; // ebx
  const char *v28; // r8
  __int64 v29; // rcx
  __int64 v30; // rdx
  bool v31; // zf
  __int64 v32; // rdx
  _QWORD *v33; // rcx
  int v35; // [rsp+20h] [rbp-E0h] BYREF
  int v36; // [rsp+24h] [rbp-DCh] BYREF
  int v37; // [rsp+28h] [rbp-D8h] BYREF
  int v38; // [rsp+2Ch] [rbp-D4h] BYREF
  int v39[4]; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v40; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v41; // [rsp+50h] [rbp-B0h]
  _QWORD v42[2]; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD v43[594]; // [rsp+70h] [rbp-90h] BYREF
  char v44; // [rsp+9B8h] [rbp+8B8h] BYREF
  char *v45; // [rsp+9D0h] [rbp+8D0h]

  v2 = *a1;
  v4 = a2;
  v5 = -1;
  v6 = *(_DWORD *)(*a1 + 140);
  if ( !*(_DWORD *)(*a1 + 216) )
    *(_DWORD *)(v2 + 408) = 0;
  *((_DWORD *)a1 + 6) = 0;
  v42[0] = v43;
  v43[0] = 0;
  v45 = &v44;
  a1[42] = (__int64)a2;
  v42[1] = a1;
  v41 = *(_QWORD *)(v2 + 352);
  *(_QWORD *)(v2 + 352) = a1;
  Token = sqlite3GetToken(a2, &v35);
  v8 = v6 - Token;
  v9 = Token;
  if ( v8 >= 0 )
  {
    while ( 1 )
    {
      v10 = v35;
      if ( v35 < 164 )
        goto LABEL_54;
      if ( *(_DWORD *)(v2 + 408) )
      {
        *((_DWORD *)a1 + 6) = 9;
        goto LABEL_58;
      }
      if ( v35 != 183 )
        break;
      v4 += v9;
LABEL_56:
      v23 = sqlite3GetToken(v4, &v35);
      v8 -= v23;
      v9 = v23;
      if ( v8 < 0 )
        goto LABEL_57;
    }
    if ( !*v4 )
    {
      if ( v5 == 1 )
      {
        v10 = 0;
        v9 = 0;
      }
      else
      {
        if ( !v5 )
          goto LABEL_59;
        v10 = 1;
        v9 = 0;
      }
      goto LABEL_53;
    }
    switch ( v35 )
    {
      case 164:
        v11 = v4 + 6;
        do
          v11 += (int)sqlite3GetToken(v11, &v37);
        while ( v37 == 183 );
        if ( v37 == 59
          || (v12 = (unsigned int)(v37 - 117), (unsigned int)v12 <= 0x30)
          && (v13 = 0x1800000000003LL, _bittest64(&v13, v12))
          || word_180112DA0[v37] == 59 )
        {
          v37 = 59;
          do
            v11 += (int)sqlite3GetToken(v11, &v38);
          while ( v38 == 183 );
          if ( v38 == 59
            || (v14 = (unsigned int)(v38 - 117), (unsigned int)v14 <= 0x30)
            && (v15 = 0x1800000000003LL, _bittest64(&v15, v14))
            || word_180112DA0[v38] == 59 )
          {
            v38 = 59;
          }
          else if ( v38 == 24 )
          {
            v10 = 164;
LABEL_53:
            v35 = v10;
LABEL_54:
            a1[35] = (__int64)v4;
            *((_DWORD *)a1 + 72) = v9;
            v40 = *(_OWORD *)(a1 + 35);
            sqlite3Parser(v42, v10, &v40);
            v4 += v9;
            if ( *((_DWORD *)a1 + 6) )
              goto LABEL_59;
            v5 = v10;
            goto LABEL_56;
          }
        }
        break;
      case 165:
        if ( v5 == 23 )
        {
          v16 = v4 + 4;
          do
          {
            v16 += (int)sqlite3GetToken(v16, v39);
            v17 = v39[0];
          }
          while ( v39[0] == 183 );
          if ( v39[0] == 59
            || (v18 = (unsigned int)(v39[0] - 117), (unsigned int)v18 <= 0x30)
            && (v19 = 0x1800000000003LL, _bittest64(&v19, v18))
            || word_180112DA0[v39[0]] == 59 )
          {
            v17 = 59;
            v39[0] = 59;
          }
          if ( v17 == 22 || v17 == 59 )
          {
            v10 = 165;
            goto LABEL_53;
          }
        }
        break;
      case 166:
        if ( v5 == 23 )
        {
          v20 = v4 + 6;
          do
            v20 += (int)sqlite3GetToken(v20, &v36);
          while ( v36 == 183 );
          if ( v36 == 59
            || (v21 = (unsigned int)(v36 - 117), (unsigned int)v21 <= 0x30)
            && (v22 = 0x1800000000003LL, _bittest64(&v22, v21))
            || word_180112DA0[v36] == 59 )
          {
            v36 = 59;
          }
          else if ( v36 == 22 )
          {
            v10 = 166;
            goto LABEL_53;
          }
        }
        break;
      default:
        *(_QWORD *)&v40 = v4;
        DWORD2(v40) = v9;
        sqlite3ErrorMsg(a1, "unrecognized token: \"%T\"", &v40);
        goto LABEL_59;
    }
    v10 = 59;
    goto LABEL_53;
  }
LABEL_57:
  *((_DWORD *)a1 + 6) = 18;
LABEL_58:
  ++*((_DWORD *)a1 + 12);
LABEL_59:
  for ( i = v42[0]; v42[0] > (unsigned __int64)v43; i = v42[0] )
  {
    v42[0] = i - 24;
    yy_destructor(v42, *(unsigned __int16 *)(i + 2), i + 8);
  }
  if ( *(_BYTE *)(v2 + 103) )
    *((_DWORD *)a1 + 6) = 7;
  v25 = (const char *)a1[1];
  if ( v25 )
    goto LABEL_76;
  v26 = *((_DWORD *)a1 + 6);
  v27 = 0;
  if ( v26 && v26 != 101 )
  {
    if ( v26 == 100 )
    {
      v28 = "another row available";
    }
    else if ( v26 == 516 )
    {
      v28 = "abort due to ROLLBACK";
    }
    else
    {
      v28 = "unknown error";
      if ( (unsigned __int8)v26 < 0x1Du && off_180113F00[(unsigned __int8)v26] )
        v28 = off_180113F00[(unsigned __int8)v26];
    }
    v25 = (const char *)sqlite3MPrintf(v2, "%s", v28);
    a1[1] = (__int64)v25;
LABEL_76:
    sqlite3_log(*((unsigned int *)a1 + 6), "%s in \"%s\"", v25, (const char *)a1[42]);
    v27 = 1;
  }
  v29 = a1[49];
  a1[42] = (__int64)v4;
  sqlite3_free(v29);
  v30 = a1[43];
  if ( v30 )
  {
    if ( !*((_BYTE *)a1 + 300) )
    {
      if ( *(_QWORD *)(v2 + 776) || (v31 = *(_DWORD *)(v30 + 44) == 1, --*(_DWORD *)(v30 + 44), v31) )
        deleteTable(v2, v30);
    }
  }
  v32 = a1[45];
  if ( v32 && *((_BYTE *)a1 + 300) < 2u )
    sqlite3DeleteTrigger(v2, v32);
  v33 = (_QWORD *)a1[40];
  if ( v33 )
  {
    if ( (unsigned __int64)v33 < *(_QWORD *)(v2 + 496) )
    {
      if ( (unsigned __int64)v33 >= *(_QWORD *)(v2 + 480) )
      {
        *v33 = *(_QWORD *)(v2 + 472);
        *(_QWORD *)(v2 + 472) = v33;
        goto LABEL_94;
      }
      if ( (unsigned __int64)v33 >= *(_QWORD *)(v2 + 488) )
      {
        *v33 = *(_QWORD *)(v2 + 456);
        *(_QWORD *)(v2 + 456) = v33;
        goto LABEL_94;
      }
    }
    if ( *(_QWORD *)(v2 + 776) )
      measureAllocationSize(v2, a1[40]);
    else
      sqlite3_free(v33);
  }
LABEL_94:
  *(_QWORD *)(v2 + 352) = v41;
  return v27;
}

```

## disassembly

```asm
0x180095f20  mov     [rsp-8+arg_10], rbx
0x180095f25  push    rbp
0x180095f26  push    rsi
0x180095f27  push    rdi
0x180095f28  push    r12
0x180095f2a  push    r13
0x180095f2c  push    r14
0x180095f2e  push    r15
0x180095f30  lea     rbp, [rsp-8F0h]
0x180095f38  sub     rsp, 9F0h
0x180095f3f  mov     rax, cs:__security_cookie
0x180095f46  xor     rax, rsp
0x180095f49  mov     [rbp+920h+var_40], rax
0x180095f50  mov     r14, [rcx]
0x180095f53  mov     rsi, rcx
0x180095f56  xor     ecx, ecx
0x180095f58  mov     r15, rdx
0x180095f5b  mov     edi, 0FFFFFFFFh
0x180095f60  mov     r13d, [r14+8Ch]
0x180095f67  cmp     [r14+0D8h], ecx
0x180095f6e  jnz     short loc_180095F77
0x180095f70  mov     [r14+198h], ecx
0x180095f77  mov     [rsi+18h], ecx
0x180095f7a  lea     rax, [rsp+0A20h+var_9B0]
0x180095f7f  mov     [rsp+0A20h+var_9C0], rax
0x180095f84  lea     rdx, [rsp+0A20h+var_A00]
0x180095f89  mov     [rsp+0A20h+var_9B0], ecx
0x180095f8d  lea     rax, [rbp+920h+var_68]
0x180095f94  mov     [rbp+920h+var_50], rax
0x180095f9b  mov     rcx, r15
0x180095f9e  mov     [rsi+150h], r15
0x180095fa5  mov     [rsp+0A20h+var_9B8], rsi
0x180095faa  mov     rax, [r14+160h]
0x180095fb1  mov     [rsp+0A20h+var_9D0], rax
0x180095fb6  mov     [r14+160h], rsi
0x180095fbd  call    sqlite3GetToken
0x180095fc2  sub     r13d, eax
0x180095fc5  mov     r12d, eax
0x180095fc8  js      loc_180096260
0x180095fce  xchg    ax, ax
0x180095fd0  mov     ebx, [rsp+0A20h+var_A00]
0x180095fd4  cmp     ebx, 0A4h
0x180095fda  jl      loc_18009620E
0x180095fe0  mov     eax, [r14+198h]
0x180095fe7  test    eax, eax
0x180095fe9  jnz     loc_18009633A
0x180095fef  cmp     ebx, 0B7h
0x180095ff5  jnz     short loc_180096002
0x180095ff7  movsxd  rax, r12d
0x180095ffa  add     r15, rax
0x180095ffd  jmp     loc_180096247
0x180096002  cmp     byte ptr [r15], 0
0x180096006  jnz     short loc_18009602C
0x180096008  cmp     edi, 1
0x18009600b  jnz     short loc_180096017
0x18009600d  xor     ebx, ebx
0x18009600f  xor     r12d, r12d
0x180096012  jmp     loc_18009620A
0x180096017  test    edi, edi
0x180096019  jz      loc_18009626A
0x18009601f  mov     ebx, 1
0x180096024  xor     r12d, r12d
0x180096027  jmp     loc_18009620A
0x18009602c  cmp     ebx, 0A4h
0x180096032  jnz     loc_18009610B
0x180096038  lea     rbx, [r15+6]
0x18009603c  nop     dword ptr [rax+00h]
0x180096040  lea     rdx, [rsp+0A20h+var_9F8]
0x180096045  mov     rcx, rbx
0x180096048  call    sqlite3GetToken
0x18009604d  movsxd  rcx, eax
0x180096050  add     rbx, rcx
0x180096053  movsxd  rcx, [rsp+0A20h+var_9F8]
0x180096058  cmp     ecx, 0B7h
0x18009605e  jz      short loc_180096040
0x180096060  cmp     ecx, 3Bh ; ';'
0x180096063  jz      short loc_180096094
0x180096065  lea     eax, [rcx-75h]
0x180096068  cmp     eax, 30h ; '0'
0x18009606b  ja      short loc_18009607D
0x18009606d  mov     rdx, 1800000000003h
0x180096077  bt      rdx, rax
0x18009607b  jb      short loc_180096094
0x18009607d  lea     rdi, cs:180000000h
0x180096084  cmp     ds:rva word_180112DA0[rdi+rcx*2], 3Bh ; ';'
0x18009608d  jz      short loc_18009609B
0x18009608f  jmp     loc_180096205
0x180096094  lea     rdi, cs:180000000h
0x18009609b  mov     [rsp+0A20h+var_9F8], 3Bh ; ';'
0x1800960a3  lea     rdx, [rsp+0A20h+var_9F4]
0x1800960a8  mov     rcx, rbx
0x1800960ab  call    sqlite3GetToken
0x1800960b0  movsxd  rcx, eax
0x1800960b3  add     rbx, rcx
0x1800960b6  movsxd  rcx, [rsp+0A20h+var_9F4]
0x1800960bb  cmp     ecx, 0B7h
0x1800960c1  jz      short loc_1800960A3
0x1800960c3  cmp     ecx, 3Bh ; ';'
0x1800960c6  jz      short loc_1800960FE
0x1800960c8  lea     eax, [rcx-75h]
0x1800960cb  cmp     eax, 30h ; '0'
0x1800960ce  ja      short loc_1800960E0
0x1800960d0  mov     rdx, 1800000000003h
0x1800960da  bt      rdx, rax
0x1800960de  jb      short loc_1800960FE
0x1800960e0  cmp     ds:rva word_180112DA0[rdi+rcx*2], 3Bh ; ';'
0x1800960e9  jz      short loc_1800960FE
0x1800960eb  cmp     ecx, 18h
0x1800960ee  jnz     loc_180096205
0x1800960f4  mov     ebx, 0A4h
0x1800960f9  jmp     loc_18009620A
0x1800960fe  mov     [rsp+0A20h+var_9F4], 3Bh ; ';'
0x180096106  jmp     loc_180096205
0x18009610b  cmp     ebx, 0A5h
0x180096111  jnz     short loc_18009618D
0x180096113  cmp     edi, 17h
0x180096116  jnz     loc_180096205
0x18009611c  lea     rbx, [r15+4]
0x180096120  lea     rdx, [rsp+0A20h+var_9F0]
0x180096125  mov     rcx, rbx
0x180096128  call    sqlite3GetToken
0x18009612d  movsxd  rcx, eax
0x180096130  add     rbx, rcx
0x180096133  movsxd  rcx, [rsp+0A20h+var_9F0]
0x180096138  cmp     ecx, 0B7h
0x18009613e  jz      short loc_180096120
0x180096140  cmp     ecx, 3Bh ; ';'
0x180096143  jz      short loc_18009616F
0x180096145  lea     eax, [rcx-75h]
0x180096148  cmp     eax, 30h ; '0'
0x18009614b  ja      short loc_18009615D
0x18009614d  mov     rdx, 1800000000003h
0x180096157  bt      rdx, rax
0x18009615b  jb      short loc_18009616F
0x18009615d  lea     rdx, cs:180000000h
0x180096164  cmp     ds:rva word_180112DA0[rdx+rcx*2], 3Bh ; ';'
0x18009616d  jnz     short loc_180096178
0x18009616f  mov     ecx, 3Bh ; ';'
0x180096174  mov     [rsp+0A20h+var_9F0], ecx
0x180096178  cmp     ecx, 16h
0x18009617b  jz      short loc_180096186
0x18009617d  cmp     ecx, 3Bh ; ';'
0x180096180  jnz     loc_180096205
0x180096186  mov     ebx, 0A5h
0x18009618b  jmp     short loc_18009620A
0x18009618d  cmp     ebx, 0A6h
0x180096193  jnz     loc_180096317
0x180096199  cmp     edi, 17h
0x18009619c  jnz     short loc_180096205
0x18009619e  lea     rbx, [r15+6]
0x1800961a2  lea     rdx, [rsp+0A20h+var_9FC]
0x1800961a7  mov     rcx, rbx
0x1800961aa  call    sqlite3GetToken
0x1800961af  movsxd  rcx, eax
0x1800961b2  add     rbx, rcx
0x1800961b5  movsxd  rcx, [rsp+0A20h+var_9FC]
0x1800961ba  cmp     ecx, 0B7h
0x1800961c0  jz      short loc_1800961A2
0x1800961c2  cmp     ecx, 3Bh ; ';'
0x1800961c5  jz      short loc_1800961FD
0x1800961c7  lea     eax, [rcx-75h]
0x1800961ca  cmp     eax, 30h ; '0'
0x1800961cd  ja      short loc_1800961DF
0x1800961cf  mov     rdx, 1800000000003h
0x1800961d9  bt      rdx, rax
0x1800961dd  jb      short loc_1800961FD
0x1800961df  lea     rdx, cs:180000000h
0x1800961e6  cmp     ds:rva word_180112DA0[rdx+rcx*2], 3Bh ; ';'
0x1800961ef  jz      short loc_1800961FD
0x1800961f1  cmp     ecx, 16h
0x1800961f4  jnz     short loc_180096205
0x1800961f6  mov     ebx, 0A6h
0x1800961fb  jmp     short loc_18009620A
0x1800961fd  mov     [rsp+0A20h+var_9FC], 3Bh ; ';'
0x180096205  mov     ebx, 3Bh ; ';'
0x18009620a  mov     [rsp+0A20h+var_A00], ebx
0x18009620e  mov     [rsi+118h], r15
0x180096215  lea     r8, [rsp+0A20h+var_9E0]
0x18009621a  mov     [rsi+120h], r12d
0x180096221  lea     rcx, [rsp+0A20h+var_9C0]
0x180096226  movups  xmm0, xmmword ptr [rsi+118h]
0x18009622d  mov     edx, ebx
0x18009622f  movaps  [rsp+0A20h+var_9E0], xmm0
0x180096234  call    sqlite3Parser
0x180096239  movsxd  rax, r12d
0x18009623c  add     r15, rax
0x18009623f  cmp     dword ptr [rsi+18h], 0
0x180096243  jnz     short loc_18009626A
0x180096245  mov     edi, ebx
0x180096247  lea     rdx, [rsp+0A20h+var_A00]
0x18009624c  mov     rcx, r15
0x18009624f  call    sqlite3GetToken
0x180096254  sub     r13d, eax
0x180096257  mov     r12d, eax
0x18009625a  jns     loc_180095FD0
0x180096260  mov     dword ptr [rsi+18h], 12h
0x180096267  inc     dword ptr [rsi+30h]
0x18009626a  mov     rcx, [rsp+0A20h+var_9C0]
0x18009626f  lea     rax, [rsp+0A20h+var_9B0]
0x180096274  cmp     rcx, rax
0x180096277  jbe     short loc_1800962AA
0x180096279  nop     dword ptr [rax+00000000h]
0x180096280  lea     rax, [rcx-18h]
0x180096284  mov     [rsp+0A20h+var_9C0], rax
0x180096289  lea     r8, [rcx+8]
0x18009628d  movzx   edx, word ptr [rcx+2]
0x180096291  lea     rcx, [rsp+0A20h+var_9C0]
0x180096296  call    yy_destructor
0x18009629b  mov     rcx, [rsp+0A20h+var_9C0]
0x1800962a0  lea     rax, [rsp+0A20h+var_9B0]
0x1800962a5  cmp     rcx, rax
0x1800962a8  ja      short loc_180096280
0x1800962aa  cmp     byte ptr [r14+67h], 0
0x1800962af  jz      short loc_1800962B8
0x1800962b1  mov     dword ptr [rsi+18h], 7
0x1800962b8  mov     rax, [rsi+8]
0x1800962bc  test    rax, rax
0x1800962bf  jnz     loc_180096372
0x1800962c5  mov     edx, [rsi+18h]
0x1800962c8  xor     ebx, ebx
0x1800962ca  test    edx, edx
0x1800962cc  jz      loc_180096390
0x1800962d2  cmp     edx, 65h ; 'e'
0x1800962d5  jz      loc_180096390
0x1800962db  mov     ecx, edx
0x1800962dd  sub     ecx, 64h ; 'd'
0x1800962e0  jz      short loc_180096358
0x1800962e2  sub     ecx, 1
0x1800962e5  jz      short loc_18009634F
0x1800962e7  cmp     ecx, 19Fh
0x1800962ed  jz      short loc_180096346
0x1800962ef  movzx   eax, dl
0x1800962f2  lea     r8, aUnknownError; "unknown error"
0x1800962f9  cmp     eax, 1Dh
0x1800962fc  jnb     short loc_18009635F
0x1800962fe  lea     rcx, cs:180000000h
0x180096305  mov     rcx, ds:rva off_180113F00[rcx+rax*8]; "not an error" ...
0x18009630d  test    rcx, rcx
0x180096310  jz      short loc_18009635F
0x180096312  mov     r8, rcx
0x180096315  jmp     short loc_18009635F
0x180096317  lea     r8, [rsp+0A20h+var_9E0]
0x18009631c  mov     qword ptr [rsp+0A20h+var_9E0], r15
0x180096321  lea     rdx, aUnrecognizedTo; "unrecognized token: \"%T\""
0x180096328  mov     dword ptr [rsp+0A20h+var_9E0+8], r12d
0x18009632d  mov     rcx, rsi
0x180096330  call    sqlite3ErrorMsg
0x180096335  jmp     loc_18009626A
0x18009633a  mov     dword ptr [rsi+18h], 9
0x180096341  jmp     loc_180096267
0x180096346  lea     r8, aAbortDueToRoll; "abort due to ROLLBACK"
0x18009634d  jmp     short loc_18009635F
0x18009634f  lea     r8, aNoMoreRowsAvai; "no more rows available"
0x180096356  jmp     short loc_18009635F
0x180096358  lea     r8, aAnotherRowAvai; "another row available"
0x18009635f  lea     rdx, aS_7; "%s"
0x180096366  mov     rcx, r14
0x180096369  call    sqlite3MPrintf
0x18009636e  mov     [rsi+8], rax
0x180096372  mov     r9, [rsi+150h]
0x180096379  lea     rdx, aSInS; "%s in \"%s\""
0x180096380  mov     ecx, [rsi+18h]
0x180096383  mov     r8, rax
0x180096386  call    sqlite3_log
0x18009638b  mov     ebx, 1
0x180096390  mov     rcx, [rsi+188h]
0x180096397  mov     [rsi+150h], r15
0x18009639e  call    sqlite3_free
0x1800963a3  mov     rdx, [rsi+158h]
0x1800963aa  test    rdx, rdx
0x1800963ad  jz      short loc_1800963D0
0x1800963af  cmp     byte ptr [rsi+12Ch], 0
0x1800963b6  jnz     short loc_1800963D0
0x1800963b8  cmp     qword ptr [r14+308h], 0
0x1800963c0  jnz     short loc_1800963C8
0x1800963c2  add     dword ptr [rdx+2Ch], 0FFFFFFFFh
0x1800963c6  jnz     short loc_1800963D0
0x1800963c8  mov     rcx, r14
0x1800963cb  call    deleteTable
0x1800963d0  mov     rdx, [rsi+168h]
0x1800963d7  test    rdx, rdx
0x1800963da  jz      short loc_1800963ED
0x1800963dc  cmp     byte ptr [rsi+12Ch], 2
0x1800963e3  jnb     short loc_1800963ED
0x1800963e5  mov     rcx, r14
0x1800963e8  call    sqlite3DeleteTrigger
0x1800963ed  mov     rcx, [rsi+140h]
0x1800963f4  test    rcx, rcx
0x1800963f7  jz      short loc_180096456
0x1800963f9  cmp     rcx, [r14+1F0h]
0x180096400  jnb     short loc_18009643A
0x180096402  cmp     rcx, [r14+1E0h]
0x180096409  jb      short loc_18009641E
0x18009640b  mov     rax, [r14+1D8h]
0x180096412  mov     [rcx], rax
0x180096415  mov     [r14+1D8h], rcx
0x18009641c  jmp     short loc_180096456
0x18009641e  cmp     rcx, [r14+1E8h]
0x180096425  jb      short loc_18009643A
0x180096427  mov     rax, [r14+1C8h]
  ... truncated ...
```
