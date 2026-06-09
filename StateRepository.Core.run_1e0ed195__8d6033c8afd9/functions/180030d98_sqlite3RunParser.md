# sqlite3RunParser

- ea: `0x180030d98`
- end: `0x180031145`
- name: `sqlite3RunParser`
- size: `941`
- prototype: ``
- caller_count: `4`
- callee_count: `15`
- tags: ``

## callers

- `0x180030918`
- `0x18007e074`
- `0x1800857c4`
- `0x18008dfb0`

## callees

- `0x18000aac0`
- `0x1800256c4`
- `0x1800275f0`
- `0x180030354`
- `0x1800308b8`
- `0x180030d98`
- `0x18003114c`
- `0x180031928`
- `0x18004660c`
- `0x180046630`
- `0x18004d39c`
- `0x18005fbb8`
- `0x180060ce8`
- `0x180068880`
- `0x18006910e`

## string_xrefs

- `0x1800310ce`: `unrecognized token: "%T"`

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
  const char *v11; // rax
  __int64 v12; // rcx
  unsigned int v13; // r14d
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 v17; // rdx
  const char *v19; // rax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  int v23[4]; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v24; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v25[4]; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v26[594]; // [rsp+60h] [rbp-A0h] BYREF
  char v27; // [rsp+9A8h] [rbp+8A8h] BYREF

  v2 = *a1;
  v23[0] = 0;
  v5 = -1;
  memset_0(v25, 0, 0x980u);
  v6 = *(_DWORD *)(v2 + 140);
  if ( !*(_DWORD *)(v2 + 216) )
    *(_DWORD *)(v2 + 408) = 0;
  *((_DWORD *)a1 + 6) = 0;
  v25[3] = v26;
  v25[2] = &v27;
  v25[0] = v26;
  a1[43] = (__int64)a2;
  v25[1] = a1;
  v26[0] = 0;
  v7 = *(_QWORD *)(v2 + 352);
  *(_QWORD *)(v2 + 352) = a1;
  while ( 1 )
  {
    while ( 1 )
    {
      Token = sqlite3GetToken(a2, v23);
      v9 = Token;
      v6 -= Token;
      if ( v6 < 0 )
      {
        *((_DWORD *)a1 + 6) = 18;
        goto LABEL_10;
      }
      v10 = (unsigned int)v23[0];
      if ( v23[0] < 165 )
        goto LABEL_6;
      if ( *(_DWORD *)(v2 + 408) )
      {
        *((_DWORD *)a1 + 6) = 9;
LABEL_10:
        ++*((_DWORD *)a1 + 13);
        goto LABEL_11;
      }
      v10 = (unsigned int)v23[0];
      if ( v23[0] != 184 )
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
    v23[0] = v10;
    v9 = 0;
LABEL_6:
    a1[36] = (__int64)a2;
    *((_DWORD *)a1 + 74) = v9;
    v24 = *((_OWORD *)a1 + 18);
    sqlite3Parser(v25, v10, &v24);
    a2 += (int)v9;
    if ( *((_DWORD *)a1 + 6) )
      goto LABEL_11;
    v5 = v23[0];
  }
  switch ( v23[0] )
  {
    case 165:
      *(_QWORD *)&v24 = a2 + 6;
      if ( (unsigned int)getToken(&v24) == 60 )
      {
        v20 = getToken(&v24);
        v10 = 165;
        if ( v20 != 24 )
          v10 = 60;
        goto LABEL_32;
      }
      goto LABEL_31;
    case 166:
      *(_QWORD *)&v24 = a2 + 4;
      if ( v5 == 23 )
      {
        v21 = getToken(&v24);
        if ( v21 == 22 || v21 == 60 )
        {
          v10 = 166;
          goto LABEL_32;
        }
      }
LABEL_31:
      v10 = 60;
LABEL_32:
      v23[0] = v10;
      goto LABEL_6;
    case 167:
      *(_QWORD *)&v24 = a2 + 6;
      if ( v5 != 23 || (v22 = getToken(&v24), v10 = 167, v22 != 22) )
        v10 = 60;
      goto LABEL_32;
    case 183:
      goto LABEL_6;
  }
  *(_QWORD *)&v24 = a2;
  *((_QWORD *)&v24 + 1) = Token;
  sqlite3ErrorMsg(a1, "unrecognized token: \"%T\"", &v24);
LABEL_11:
  sqlite3ParserFinalize(v25);
  if ( *(_BYTE *)(v2 + 103) )
    *((_DWORD *)a1 + 6) = 7;
  v11 = (const char *)a1[1];
  if ( v11 )
  {
LABEL_28:
    sqlite3_log(*((unsigned int *)a1 + 6), "%s in \"%s\"", v11, (const char *)a1[43]);
    v13 = 1;
  }
  else
  {
    v12 = *((unsigned int *)a1 + 6);
    v13 = 0;
    if ( (_DWORD)v12 && (_DWORD)v12 != 101 )
    {
      v19 = (const char *)sqlite3ErrStr(v12);
      v11 = (const char *)sqlite3MPrintf(v2, "%s", v19);
      a1[1] = (__int64)v11;
      goto LABEL_28;
    }
  }
  v14 = a1[50];
  a1[43] = (__int64)a2;
  sqlite3_free(v14);
  v15 = a1[44];
  if ( v15 && !*((_BYTE *)a1 + 308) )
    sqlite3DeleteTable(v2, v15);
  v16 = a1[46];
  if ( v16 && *((_BYTE *)a1 + 308) < 2u )
    sqlite3DeleteTrigger(v2, v16);
  v17 = a1[41];
  if ( v17 )
    sqlite3DbNNFreeNN(v2, v17);
  *(_QWORD *)(v2 + 352) = v7;
  return v13;
}

```

## disassembly

```asm
0x180030d98  mov     [rsp-8+arg_10], rbx
0x180030d9d  push    rbp
0x180030d9e  push    rsi
0x180030d9f  push    rdi
0x180030da0  push    r12
0x180030da2  push    r13
0x180030da4  push    r14
0x180030da6  push    r15
0x180030da8  lea     rbp, [rsp-8D0h]
0x180030db0  sub     rsp, 9D0h
0x180030db7  mov     rax, cs:__security_cookie
0x180030dbe  xor     rax, rsp
0x180030dc1  mov     [rbp+900h+var_40], rax
0x180030dc8  mov     rdi, [rcx]
0x180030dcb  mov     rsi, rdx
0x180030dce  mov     rbx, rcx
0x180030dd1  xor     r15d, r15d
0x180030dd4  xor     edx, edx; Val
0x180030dd6  mov     [rsp+0A00h+var_9E0], r15d
0x180030ddb  lea     rcx, [rsp+0A00h+var_9C0]; void *
0x180030de0  mov     r8d, 980h; Size
0x180030de6  or      r14d, 0FFFFFFFFh
0x180030dea  call    memset_0
0x180030def  mov     r12d, [rdi+8Ch]
0x180030df6  cmp     [rdi+0D8h], r15d
0x180030dfd  jnz     short loc_180030E06
0x180030dff  mov     [rdi+198h], r15d
0x180030e06  lea     rax, [rsp+0A00h+var_9A0]
0x180030e0b  mov     [rbx+18h], r15d
0x180030e0f  mov     [rsp+0A00h+var_9A8], rax
0x180030e14  lea     rax, [rbp+900h+var_58]
0x180030e1b  mov     [rsp+0A00h+var_9B0], rax
0x180030e20  lea     rax, [rsp+0A00h+var_9A0]
0x180030e25  mov     [rsp+0A00h+var_9C0], rax
0x180030e2a  mov     [rbx+158h], rsi
0x180030e31  mov     [rsp+0A00h+var_9B8], rbx
0x180030e36  mov     [rsp+0A00h+var_9A0], r15d
0x180030e3b  mov     r13, [rdi+160h]
0x180030e42  mov     [rdi+160h], rbx
0x180030e49  lea     rdx, [rsp+0A00h+var_9E0]
0x180030e4e  mov     rcx, rsi
0x180030e51  call    sqlite3GetToken
0x180030e56  movsxd  r15, eax
0x180030e59  sub     r12d, r15d
0x180030e5c  js      loc_1800310EC
0x180030e62  mov     edx, [rsp+0A00h+var_9E0]
0x180030e66  mov     eax, 0A5h
0x180030e6b  cmp     edx, eax
0x180030e6d  jge     short loc_180030EAC
0x180030e6f  mov     [rbx+120h], rsi
0x180030e76  lea     r8, [rsp+0A00h+var_9D0]
0x180030e7b  mov     [rbx+128h], r15d
0x180030e82  lea     rcx, [rsp+0A00h+var_9C0]
0x180030e87  movups  xmm0, xmmword ptr [rbx+120h]
0x180030e8e  movdqu  [rsp+0A00h+var_9D0], xmm0
0x180030e94  call    sqlite3Parser
0x180030e99  movsxd  rax, r15d
0x180030e9c  add     rsi, rax
0x180030e9f  cmp     dword ptr [rbx+18h], 0
0x180030ea3  jnz     short loc_180030EC4
0x180030ea5  mov     r14d, [rsp+0A00h+var_9E0]
0x180030eaa  jmp     short loc_180030E49
0x180030eac  mov     ecx, [rdi+198h]
0x180030eb2  test    ecx, ecx
0x180030eb4  jz      loc_180030F6A
0x180030eba  mov     dword ptr [rbx+18h], 9
0x180030ec1  inc     dword ptr [rbx+34h]
0x180030ec4  lea     rcx, [rsp+0A00h+var_9C0]
0x180030ec9  call    sqlite3ParserFinalize
0x180030ece  cmp     byte ptr [rdi+67h], 0
0x180030ed2  jnz     loc_1800310F8
0x180030ed8  mov     rax, [rbx+8]
0x180030edc  test    rax, rax
0x180030edf  jnz     loc_180030FBF
0x180030ee5  mov     ecx, [rbx+18h]
0x180030ee8  xor     r14d, r14d
0x180030eeb  test    ecx, ecx
0x180030eed  jnz     loc_180030F9B
0x180030ef3  mov     rcx, [rbx+190h]
0x180030efa  mov     [rbx+158h], rsi
0x180030f01  call    sqlite3_free
0x180030f06  mov     rdx, [rbx+160h]
0x180030f0d  test    rdx, rdx
0x180030f10  jnz     loc_180031104
0x180030f16  mov     rdx, [rbx+170h]
0x180030f1d  test    rdx, rdx
0x180030f20  jnz     loc_18003111E
0x180030f26  mov     rdx, [rbx+148h]
0x180030f2d  test    rdx, rdx
0x180030f30  jnz     loc_180031138
0x180030f36  mov     [rdi+160h], r13
0x180030f3d  mov     eax, r14d
0x180030f40  mov     rcx, [rbp+900h+var_40]
0x180030f47  xor     rcx, rsp; StackCookie
0x180030f4a  call    __security_check_cookie
0x180030f4f  mov     rbx, [rsp+0A00h+arg_10]
0x180030f57  add     rsp, 9D0h
0x180030f5e  pop     r15
0x180030f60  pop     r14
0x180030f62  pop     r13
0x180030f64  pop     r12
0x180030f66  pop     rdi
0x180030f67  pop     rsi
0x180030f68  pop     rbp
0x180030f69  retn
0x180030f6a  mov     edx, [rsp+0A00h+var_9E0]
0x180030f6e  cmp     edx, 0B8h
0x180030f74  jnz     short loc_180030F7E
0x180030f76  add     rsi, r15
0x180030f79  jmp     loc_180030E49
0x180030f7e  cmp     byte ptr [rsi], 0
0x180030f81  jnz     short loc_180030FE3
0x180030f83  cmp     r14d, 1
0x180030f87  jnz     loc_180031011
0x180030f8d  xor     edx, edx
0x180030f8f  mov     [rsp+0A00h+var_9E0], edx
0x180030f93  xor     r15d, r15d
0x180030f96  jmp     loc_180030E6F
0x180030f9b  cmp     ecx, 65h ; 'e'
0x180030f9e  jz      loc_180030EF3
0x180030fa4  call    sqlite3ErrStr
0x180030fa9  mov     r8, rax
0x180030fac  lea     rdx, aS_7; "%s"
0x180030fb3  mov     rcx, rdi
0x180030fb6  call    sqlite3MPrintf
0x180030fbb  mov     [rbx+8], rax
0x180030fbf  mov     r9, [rbx+158h]
0x180030fc6  lea     rdx, aSInS; "%s in \"%s\""
0x180030fcd  mov     ecx, [rbx+18h]
0x180030fd0  mov     r8, rax
0x180030fd3  call    sqlite3_log
0x180030fd8  mov     r14d, 1
0x180030fde  jmp     loc_180030EF3
0x180030fe3  cmp     edx, eax
0x180030fe5  jnz     short loc_18003103C
0x180030fe7  lea     rax, [rsi+6]
0x180030feb  lea     rcx, [rsp+0A00h+var_9D0]
0x180030ff0  mov     qword ptr [rsp+0A00h+var_9D0], rax
0x180030ff5  call    getToken
0x180030ffa  mov     r14d, 3Ch ; '<'
0x180031000  cmp     eax, r14d
0x180031003  jz      short loc_180031024
0x180031005  mov     edx, r14d
0x180031008  mov     [rsp+0A00h+var_9E0], edx
0x18003100c  jmp     loc_180030E6F
0x180031011  test    r14d, r14d
0x180031014  jz      loc_180030EC4
0x18003101a  mov     edx, 1
0x18003101f  jmp     loc_180030F8F
0x180031024  lea     rcx, [rsp+0A00h+var_9D0]
0x180031029  call    getToken
0x18003102e  cmp     eax, 18h
0x180031031  mov     edx, 0A5h
0x180031036  cmovnz  edx, r14d
0x18003103a  jmp     short loc_180031008
0x18003103c  cmp     edx, 0A6h
0x180031042  jnz     short loc_18003107C
0x180031044  lea     rax, [rsi+4]
0x180031048  mov     qword ptr [rsp+0A00h+var_9D0], rax
0x18003104d  cmp     r14d, 17h
0x180031051  jnz     short loc_180031074
0x180031053  lea     rcx, [rsp+0A00h+var_9D0]
0x180031058  call    getToken
0x18003105d  cmp     eax, 16h
0x180031060  jz      short loc_18003106D
0x180031062  mov     r14d, 3Ch ; '<'
0x180031068  cmp     eax, r14d
0x18003106b  jnz     short loc_180031005
0x18003106d  mov     edx, 0A6h
0x180031072  jmp     short loc_180031008
0x180031074  mov     r14d, 3Ch ; '<'
0x18003107a  jmp     short loc_180031005
0x18003107c  cmp     edx, 0A7h
0x180031082  jnz     short loc_1800310B5
0x180031084  lea     rax, [rsi+6]
0x180031088  mov     qword ptr [rsp+0A00h+var_9D0], rax
0x18003108d  cmp     r14d, 17h
0x180031091  jnz     short loc_1800310AB
0x180031093  lea     rcx, [rsp+0A00h+var_9D0]
0x180031098  call    getToken
0x18003109d  mov     edx, 0A7h
0x1800310a2  cmp     eax, 16h
0x1800310a5  jz      loc_180031008
0x1800310ab  mov     edx, 3Ch ; '<'
0x1800310b0  jmp     loc_180031008
0x1800310b5  cmp     edx, 0B7h
0x1800310bb  jz      loc_180030E6F
0x1800310c1  lea     r8, [rsp+0A00h+var_9D0]
0x1800310c6  mov     dword ptr [rsp+0A00h+var_9D0+0Ch], 0
0x1800310ce  lea     rdx, aUnrecognizedTo_0; "unrecognized token: \"%T\""
0x1800310d5  mov     qword ptr [rsp+0A00h+var_9D0], rsi
0x1800310da  mov     rcx, rbx
0x1800310dd  mov     dword ptr [rsp+0A00h+var_9D0+8], r15d
0x1800310e2  call    sqlite3ErrorMsg
0x1800310e7  jmp     loc_180030EC4
0x1800310ec  mov     dword ptr [rbx+18h], 12h
0x1800310f3  jmp     loc_180030EC1
0x1800310f8  mov     dword ptr [rbx+18h], 7
0x1800310ff  jmp     loc_180030ED8
0x180031104  cmp     byte ptr [rbx+134h], 0
0x18003110b  jnz     loc_180030F16
0x180031111  mov     rcx, rdi
0x180031114  call    sqlite3DeleteTable
0x180031119  jmp     loc_180030F16
0x18003111e  cmp     byte ptr [rbx+134h], 2
0x180031125  jnb     loc_180030F26
0x18003112b  mov     rcx, rdi
0x18003112e  call    sqlite3DeleteTrigger
0x180031133  jmp     loc_180030F26
0x180031138  mov     rcx, rdi
0x18003113b  call    sqlite3DbNNFreeNN
0x180031140  jmp     loc_180030F36
```
