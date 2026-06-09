# ConsoleToPipeRedirector::GenerateInput(uchar *,ulong)

- ea: `0x14001bff4`
- end: `0x14001c38f`
- name: `?GenerateInput@ConsoleToPipeRedirector@@AEAAXPEAEK@Z`
- size: `923`
- prototype: `void __fastcall(ConsoleToPipeRedirector *__hidden this, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14001c420`

## callees

- `0x140002310`
- `0x14001bff4`
- `0x14001c91c`
- `0x14001cd6c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_isdigit` at `0x14001c075`
- `api-ms-win-crt-private-l1-1-0!_o_isdigit` at `0x14001c075`
- `api-ms-win-crt-private-l1-1-0!_o_toupper` at `0x14001c2cc`
- `api-ms-win-crt-private-l1-1-0!_o_toupper` at `0x14001c2cc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14001c027`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14001c027`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001c364`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001c364`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14001c355`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14001c355`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x14001c331`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x14001c331`

## pseudocode

```c
void __fastcall ConsoleToPipeRedirector::GenerateInput(
        ConsoleToPipeRedirector *this,
        unsigned __int8 *a2,
        unsigned int a3)
{
  RTL_SRWLOCK *v6; // rbp
  __int64 v7; // rdx
  __int64 v8; // r15
  _DWORD *v9; // r14
  int v10; // esi
  int v11; // ebx
  int v12; // eax
  int v13; // ecx
  int v14; // eax
  int v15; // edx
  int v16; // ecx
  int v17; // r8d
  int v18; // ebx
  int v19; // ebx
  int v20; // ebx
  int v21; // ebx
  int v22; // ebx
  int v23; // ebx
  unsigned int v24; // eax
  unsigned int v25; // eax
  unsigned int v26; // eax
  unsigned int v27; // eax
  unsigned int v28; // eax
  unsigned int v29; // eax
  unsigned int v30; // eax
  unsigned __int16 v31; // dx
  unsigned int v32; // eax
  unsigned int v33; // eax
  unsigned int v34; // eax
  unsigned int v35; // eax
  unsigned int v36; // eax
  unsigned __int16 v37; // dx
  __int64 v38; // rcx
  unsigned __int16 v39; // dx
  unsigned __int16 v40; // r8
  unsigned __int16 v41; // r9
  unsigned __int16 v42; // dx
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp-48h] BYREF

  v6 = (RTL_SRWLOCK *)((char *)this + 40);
  AcquireSRWLockExclusive((PSRWLOCK)this + 5);
  pftDueTime = (struct _FILETIME)v6;
  v8 = 0;
  v9 = (_DWORD *)((char *)this + 12);
  if ( a3 )
  {
    while ( 1 )
    {
      v10 = a2[v8];
      if ( !*v9 )
        break;
      switch ( *v9 )
      {
        case 1:
          if ( (_BYTE)v10 == 79 )
          {
            *v9 = 2;
            goto LABEL_87;
          }
          if ( (_BYTE)v10 == 91 )
          {
            *v9 = 3;
            *((_DWORD *)this + 6) = 0;
            *((_QWORD *)this + 2) = 0;
            goto LABEL_87;
          }
          break;
        case 2:
          switch ( v10 )
          {
            case 'P':
              v37 = 112;
              goto LABEL_65;
            case 'Q':
              v37 = 113;
              goto LABEL_65;
            case 'R':
              v37 = 114;
              goto LABEL_65;
            case 'S':
              v37 = 115;
LABEL_65:
              ConsoleToPipeRedirector::WriteKey(this, v37, 8u, 0, 0);
              goto LABEL_56;
          }
          break;
        case 3:
          v11 = a2[v8];
          if ( (unsigned int)_o_isdigit(a2[v8], v7, 8) )
          {
            if ( *((_DWORD *)this + 6) < 2u )
            {
              v7 = *((unsigned int *)this + 6);
              *((_DWORD *)this + v7 + 4) = v10 + 2 * (5 * *((_DWORD *)this + v7 + 4) - 24);
            }
            goto LABEL_87;
          }
          ++*((_DWORD *)this + 6);
          if ( (_BYTE)v10 == 59 )
            goto LABEL_87;
          v12 = *((_DWORD *)this + 5);
          v13 = v12 - 1;
          v14 = -v12;
          v15 = v14 != 0 ? v13 : 0;
          v16 = 16 * ((unsigned __int8)v13 & (unsigned __int8)-(v14 != 0) & 1);
          v17 = v16 | 2;
          if ( (v15 & 2) == 0 )
            v17 = v16;
          if ( (v15 & 4) != 0 )
            v17 |= 8u;
          v18 = v11 - 65;
          if ( !v18 )
          {
            v31 = 38;
LABEL_54:
            v17 |= 0x100u;
LABEL_55:
            ConsoleToPipeRedirector::WriteKey(this, v31, v17, 0, v17);
LABEL_56:
            *v9 = 0;
LABEL_87:
            v8 = (unsigned int)(v8 + 1);
            goto LABEL_88;
          }
          v19 = v18 - 1;
          if ( !v19 )
          {
            v31 = 40;
            goto LABEL_54;
          }
          v20 = v19 - 1;
          if ( !v20 )
          {
            v31 = 39;
            goto LABEL_54;
          }
          v21 = v20 - 1;
          if ( !v21 )
          {
            v31 = 37;
            goto LABEL_54;
          }
          v22 = v21 - 2;
          if ( !v22 )
            goto LABEL_33;
          v23 = v22 - 2;
          if ( !v23 )
          {
LABEL_36:
            v31 = 36;
            goto LABEL_54;
          }
          if ( v23 == 54 )
          {
            v24 = *((_DWORD *)this + 4);
            if ( v24 > 0x11 )
            {
              v32 = v24 - 18;
              if ( !v32 )
              {
                v31 = 118;
                goto LABEL_55;
              }
              v33 = v32 - 1;
              if ( !v33 )
              {
                v31 = 119;
                goto LABEL_55;
              }
              v34 = v33 - 1;
              if ( !v34 )
              {
                v31 = 120;
                goto LABEL_55;
              }
              v35 = v34 - 1;
              if ( !v35 )
              {
                v31 = 121;
                goto LABEL_55;
              }
              v36 = v35 - 2;
              if ( !v36 )
              {
                v31 = 122;
                goto LABEL_55;
              }
              if ( v36 == 1 )
              {
                v31 = 123;
                goto LABEL_55;
              }
            }
            else
            {
              if ( v24 == 17 )
              {
                v31 = 117;
                goto LABEL_55;
              }
              v25 = v24 - 1;
              if ( !v25 )
                goto LABEL_36;
              v26 = v25 - 1;
              if ( !v26 )
              {
                v31 = 45;
                goto LABEL_54;
              }
              v27 = v26 - 1;
              if ( !v27 )
              {
                v31 = 46;
                goto LABEL_54;
              }
              v28 = v27 - 1;
              if ( !v28 )
              {
LABEL_33:
                v31 = 35;
                goto LABEL_54;
              }
              v29 = v28 - 1;
              if ( !v29 )
              {
                v31 = 33;
                goto LABEL_54;
              }
              v30 = v29 - 1;
              if ( !v30 )
              {
                v31 = 34;
                goto LABEL_54;
              }
              if ( v30 == 9 )
              {
                v31 = 116;
                goto LABEL_55;
              }
            }
          }
          break;
        default:
          goto LABEL_87;
      }
      ConsoleToPipeRedirector::ResetQueuedInput(this);
LABEL_88:
      if ( (unsigned int)v8 >= a3 )
        goto LABEL_89;
    }
    if ( v10 == 3 )
    {
      ConsoleToPipeRedirector::WriteKey(this, 0x43u, 8u, 3u, 8u);
      goto LABEL_87;
    }
    if ( v10 != 8 )
    {
      if ( v10 == 9 )
      {
        v42 = 9;
        v41 = 9;
        goto LABEL_83;
      }
      if ( v10 == 27 )
      {
        *v9 = 1;
        goto LABEL_87;
      }
      if ( v10 != 127 )
      {
        if ( (unsigned __int8)(v10 - 97) <= 0x19u
          || (unsigned __int8)(v10 - 48) <= 0x2Au && (v38 = 0x7FFFFFE03FFLL, _bittest64(&v38, (unsigned int)(v10 - 48)))
          || (_BYTE)v10 == 13 )
        {
          v39 = toupper(a2[v8]);
          ConsoleToPipeRedirector::WriteKey(this, v39, v40, v10, 0);
        }
        else
        {
          ConsoleToPipeRedirector::WriteKey(this, 0, 8u, v10, 0);
        }
        goto LABEL_87;
      }
    }
    v41 = 8;
    v42 = 8;
LABEL_83:
    ConsoleToPipeRedirector::WriteKey(this, v42, 8u, v41, 0);
    goto LABEL_87;
  }
LABEL_89:
  QueryUnbiasedInterruptTime((PULONGLONG)this + 10);
  if ( *v9 )
  {
    pftDueTime = (struct _FILETIME)-300000LL;
    SetThreadpoolTimer(*((PTP_TIMER *)this + 9), &pftDueTime, 0, 0);
  }
  if ( v6 )
    ReleaseSRWLockExclusive(v6);
}

```

## disassembly

```asm
0x14001bff4  mov     [rsp+arg_10], rbx
0x14001bff9  push    rbp
0x14001bffa  push    rsi
0x14001bffb  push    rdi
0x14001bffc  push    r12
0x14001bffe  push    r13
0x14001c000  push    r14
0x14001c002  push    r15
0x14001c004  sub     rsp, 40h
0x14001c008  mov     rax, cs:__security_cookie
0x14001c00f  xor     rax, rsp
0x14001c012  mov     [rsp+78h+var_40], rax
0x14001c017  mov     r12d, r8d
0x14001c01a  mov     r13, rdx
0x14001c01d  mov     rdi, rcx
0x14001c020  lea     rbp, [rcx+28h]
0x14001c024  mov     rcx, rbp; SRWLock
0x14001c027  call    cs:__imp_AcquireSRWLockExclusive
0x14001c02d  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], rbp
0x14001c032  xor     r15d, r15d
0x14001c035  lea     r14, [rdi+0Ch]
0x14001c039  test    r12d, r12d
0x14001c03c  jz      loc_14001C32D
0x14001c042  lea     r8d, [r15+8]; unsigned __int16
0x14001c046  movzx   esi, byte ptr [r15+r13]
0x14001c04b  mov     ecx, [r14]
0x14001c04e  test    ecx, ecx
0x14001c050  jz      loc_14001C27F
0x14001c056  sub     ecx, 1
0x14001c059  jz      loc_14001C241
0x14001c05f  sub     ecx, 1
0x14001c062  jz      loc_14001C209
0x14001c068  cmp     ecx, 1
0x14001c06b  jnz     loc_14001C31B
0x14001c071  mov     ebx, esi
0x14001c073  mov     ecx, esi
0x14001c075  call    cs:__imp__o_isdigit
0x14001c07b  test    eax, eax
0x14001c07d  jz      short loc_14001C0A2
0x14001c07f  cmp     dword ptr [rdi+18h], 2
0x14001c083  jnb     loc_14001C31B
0x14001c089  mov     edx, [rdi+18h]
0x14001c08c  mov     eax, [rdi+rdx*4+10h]
0x14001c090  lea     eax, [rax+rax*4]
0x14001c093  lea     eax, [rax-18h]
0x14001c096  lea     eax, [rsi+rax*2]
0x14001c099  mov     [rdi+rdx*4+10h], eax
0x14001c09d  jmp     loc_14001C31B
0x14001c0a2  inc     dword ptr [rdi+18h]
0x14001c0a5  cmp     sil, 3Bh ; ';'
0x14001c0a9  jz      loc_14001C31B
0x14001c0af  mov     eax, [rdi+14h]
0x14001c0b2  lea     ecx, [rax-1]
0x14001c0b5  neg     eax
0x14001c0b7  sbb     edx, edx
0x14001c0b9  and     edx, ecx
0x14001c0bb  mov     ecx, edx
0x14001c0bd  and     ecx, 1
0x14001c0c0  shl     ecx, 4
0x14001c0c3  mov     r8d, ecx
0x14001c0c6  or      r8d, 2
0x14001c0ca  test    dl, 2
0x14001c0cd  cmovz   r8d, ecx
0x14001c0d1  test    dl, 4
0x14001c0d4  jz      short loc_14001C0DA
0x14001c0d6  or      r8d, 8
0x14001c0da  sub     ebx, 41h ; 'A'
0x14001c0dd  jz      loc_14001C1E3
0x14001c0e3  sub     ebx, 1
0x14001c0e6  jz      loc_14001C1DC
0x14001c0ec  sub     ebx, 1
0x14001c0ef  jz      loc_14001C1D5
0x14001c0f5  sub     ebx, 1
0x14001c0f8  jz      loc_14001C1CE
0x14001c0fe  sub     ebx, 2
0x14001c101  jz      short loc_14001C15E
0x14001c103  sub     ebx, 2
0x14001c106  jz      short loc_14001C176
0x14001c108  cmp     ebx, 36h ; '6'
0x14001c10b  jnz     loc_14001C24D
0x14001c111  mov     eax, [rdi+10h]
0x14001c114  cmp     eax, 11h
0x14001c117  ja      short loc_14001C184
0x14001c119  jz      short loc_14001C17D
0x14001c11b  sub     eax, 1
0x14001c11e  jz      short loc_14001C176
0x14001c120  sub     eax, 1
0x14001c123  jz      short loc_14001C16F
0x14001c125  sub     eax, 1
0x14001c128  jz      short loc_14001C168
0x14001c12a  sub     eax, 1
0x14001c12d  jz      short loc_14001C15E
0x14001c12f  sub     eax, 1
0x14001c132  jz      short loc_14001C154
0x14001c134  sub     eax, 1
0x14001c137  jz      short loc_14001C14A
0x14001c139  cmp     eax, 9
0x14001c13c  jnz     loc_14001C24D
0x14001c142  lea     edx, [rbx+3Eh]
0x14001c145  jmp     loc_14001C1ED
0x14001c14a  mov     edx, 22h ; '"'
0x14001c14f  jmp     loc_14001C1E8
0x14001c154  mov     edx, 21h ; '!'
0x14001c159  jmp     loc_14001C1E8
0x14001c15e  mov     edx, 23h ; '#'
0x14001c163  jmp     loc_14001C1E8
0x14001c168  mov     edx, 2Eh ; '.'
0x14001c16d  jmp     short loc_14001C1E8
0x14001c16f  mov     edx, 2Dh ; '-'
0x14001c174  jmp     short loc_14001C1E8
0x14001c176  mov     edx, 24h ; '$'
0x14001c17b  jmp     short loc_14001C1E8
0x14001c17d  mov     edx, 75h ; 'u'
0x14001c182  jmp     short loc_14001C1ED
0x14001c184  sub     eax, 12h
0x14001c187  jz      short loc_14001C1C7
0x14001c189  sub     eax, 1
0x14001c18c  jz      short loc_14001C1C0
0x14001c18e  sub     eax, 1
0x14001c191  jz      short loc_14001C1B9
0x14001c193  sub     eax, 1
0x14001c196  jz      short loc_14001C1B2
0x14001c198  sub     eax, 2
0x14001c19b  jz      short loc_14001C1AB
0x14001c19d  cmp     eax, 1
0x14001c1a0  jnz     loc_14001C24D
0x14001c1a6  lea     edx, [rax+7Ah]
0x14001c1a9  jmp     short loc_14001C1ED
0x14001c1ab  mov     edx, 7Ah ; 'z'
0x14001c1b0  jmp     short loc_14001C1ED
0x14001c1b2  mov     edx, 79h ; 'y'
0x14001c1b7  jmp     short loc_14001C1ED
0x14001c1b9  mov     edx, 78h ; 'x'
0x14001c1be  jmp     short loc_14001C1ED
0x14001c1c0  mov     edx, 77h ; 'w'
0x14001c1c5  jmp     short loc_14001C1ED
0x14001c1c7  mov     edx, 76h ; 'v'
0x14001c1cc  jmp     short loc_14001C1ED
0x14001c1ce  mov     edx, 25h ; '%'
0x14001c1d3  jmp     short loc_14001C1E8
0x14001c1d5  mov     edx, 27h ; '''
0x14001c1da  jmp     short loc_14001C1E8
0x14001c1dc  mov     edx, 28h ; '('
0x14001c1e1  jmp     short loc_14001C1E8
0x14001c1e3  mov     edx, 26h ; '&'; unsigned __int16
0x14001c1e8  bts     r8d, 8; unsigned __int16
0x14001c1ed  mov     [rsp+78h+var_58], r8d; unsigned int
0x14001c1f2  xor     r9d, r9d; unsigned __int16
0x14001c1f5  mov     rcx, rdi; this
0x14001c1f8  call    ?WriteKey@ConsoleToPipeRedirector@@AEAAKGGGK@Z; ConsoleToPipeRedirector::WriteKey(ushort,ushort,ushort,ulong)
0x14001c1fd  mov     dword ptr [r14], 0
0x14001c204  jmp     loc_14001C31B
0x14001c209  mov     ecx, esi
0x14001c20b  sub     ecx, 50h ; 'P'
0x14001c20e  jz      short loc_14001C232
0x14001c210  sub     ecx, 1
0x14001c213  jz      short loc_14001C22B
0x14001c215  sub     ecx, 1
0x14001c218  jz      short loc_14001C224
0x14001c21a  cmp     ecx, 1
0x14001c21d  jnz     short loc_14001C24D
0x14001c21f  lea     edx, [rcx+72h]
0x14001c222  jmp     short loc_14001C237
0x14001c224  mov     edx, 72h ; 'r'
0x14001c229  jmp     short loc_14001C237
0x14001c22b  mov     edx, 71h ; 'q'
0x14001c230  jmp     short loc_14001C237
0x14001c232  mov     edx, 70h ; 'p'
0x14001c237  xor     r9d, r9d
0x14001c23a  mov     [rsp+78h+var_58], r9d
0x14001c23f  jmp     short loc_14001C1F5
0x14001c241  cmp     sil, 4Fh ; 'O'
0x14001c245  jz      short loc_14001C273
0x14001c247  cmp     sil, 5Bh ; '['
0x14001c24b  jz      short loc_14001C25A
0x14001c24d  mov     rcx, rdi; this
0x14001c250  call    ?ResetQueuedInput@ConsoleToPipeRedirector@@AEAAXXZ; ConsoleToPipeRedirector::ResetQueuedInput(void)
0x14001c255  jmp     loc_14001C31E
0x14001c25a  mov     dword ptr [r14], 3
0x14001c261  mov     dword ptr [rdi+18h], 0
0x14001c268  xor     eax, eax
0x14001c26a  mov     [rdi+10h], rax
0x14001c26e  jmp     loc_14001C31B
0x14001c273  mov     dword ptr [r14], 2
0x14001c27a  jmp     loc_14001C31B
0x14001c27f  mov     ecx, esi
0x14001c281  sub     ecx, 3
0x14001c284  jz      short loc_14001C305
0x14001c286  sub     ecx, 5
0x14001c289  jz      short loc_14001C2E2
0x14001c28b  sub     ecx, 1
0x14001c28e  jz      short loc_14001C2FB
0x14001c290  sub     ecx, 12h
0x14001c293  jz      short loc_14001C2F2
0x14001c295  cmp     ecx, 64h ; 'd'
0x14001c298  jz      short loc_14001C2E2
0x14001c29a  lea     eax, [rsi-61h]
0x14001c29d  cmp     al, 19h
0x14001c29f  jbe     short loc_14001C2CA
0x14001c2a1  lea     eax, [rsi-30h]
0x14001c2a4  cmp     al, 2Ah ; '*'
0x14001c2a6  ja      short loc_14001C2B8
0x14001c2a8  mov     rcx, 7FFFFFE03FFh
0x14001c2b2  bt      rcx, rax
0x14001c2b6  jb      short loc_14001C2CA
0x14001c2b8  cmp     sil, 0Dh
0x14001c2bc  jz      short loc_14001C2CA
0x14001c2be  movzx   r9d, si
0x14001c2c2  xor     edx, edx
0x14001c2c4  mov     [rsp+78h+var_58], edx
0x14001c2c8  jmp     short loc_14001C313
0x14001c2ca  mov     ecx, esi; C
0x14001c2cc  call    cs:__imp_toupper
0x14001c2d2  mov     edx, eax
0x14001c2d4  mov     [rsp+78h+var_58], 0
0x14001c2dc  movzx   r9d, si
0x14001c2e0  jmp     short loc_14001C313
0x14001c2e2  mov     r9d, r8d
0x14001c2e5  mov     edx, r8d
0x14001c2e8  mov     [rsp+78h+var_58], 0
0x14001c2f0  jmp     short loc_14001C313
0x14001c2f2  mov     dword ptr [r14], 1
0x14001c2f9  jmp     short loc_14001C31B
0x14001c2fb  mov     edx, 9
0x14001c300  mov     r9d, edx
0x14001c303  jmp     short loc_14001C2E8
0x14001c305  mov     edx, 43h ; 'C'; unsigned __int16
0x14001c30a  lea     r9d, [rdx-40h]; unsigned __int16
0x14001c30e  mov     [rsp+78h+var_58], r8d; unsigned int
0x14001c313  mov     rcx, rdi; this
0x14001c316  call    ?WriteKey@ConsoleToPipeRedirector@@AEAAKGGGK@Z; ConsoleToPipeRedirector::WriteKey(ushort,ushort,ushort,ulong)
0x14001c31b  inc     r15d
0x14001c31e  cmp     r15d, r12d
0x14001c321  mov     r8d, 8
0x14001c327  jb      loc_14001C046
0x14001c32d  lea     rcx, [rdi+50h]; UnbiasedTime
0x14001c331  call    cs:__imp_QueryUnbiasedInterruptTime
0x14001c337  cmp     dword ptr [r14], 0
0x14001c33b  jz      short loc_14001C35C
0x14001c33d  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0FFFFFFFFFFFB6C20h
0x14001c346  xor     r9d, r9d; msWindowLength
0x14001c349  xor     r8d, r8d; msPeriod
0x14001c34c  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x14001c351  mov     rcx, [rdi+48h]; pti
0x14001c355  call    cs:__imp_SetThreadpoolTimer
0x14001c35b  nop
0x14001c35c  test    rbp, rbp
0x14001c35f  jz      short loc_14001C36A
0x14001c361  mov     rcx, rbp; SRWLock
0x14001c364  call    cs:__imp_ReleaseSRWLockExclusive
0x14001c36a  mov     rcx, [rsp+78h+var_40]
0x14001c36f  xor     rcx, rsp; StackCookie
0x14001c372  call    __security_check_cookie
0x14001c377  mov     rbx, [rsp+78h+arg_10]
0x14001c37f  add     rsp, 40h
0x14001c383  pop     r15
0x14001c385  pop     r14
0x14001c387  pop     r13
0x14001c389  pop     r12
0x14001c38b  pop     rdi
0x14001c38c  pop     rsi
0x14001c38d  pop     rbp
0x14001c38e  retn
```
