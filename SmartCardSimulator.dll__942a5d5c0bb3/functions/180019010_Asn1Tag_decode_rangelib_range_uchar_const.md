# Asn1Tag::decode(rangelib::range<uchar const *>)

- ea: `0x180019010`
- end: `0x1800191b3`
- name: `?decode@Asn1Tag@@SA?AV?$tuple@V?$scoped_error@Utag@ntstatus_error@@@errorlib@@Utype@Asn1Tag@@V?$range@PEBE@rangelib@@U_Nil@tr1@std@@U789@U789@U789@U789@U789@U789@@tr1@std@@V?$range@PEBE@rangelib@@@Z`
- size: `419`
- prototype: ``
- caller_count: `25`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000c98c`
- `0x18000ca78`
- `0x18000cb64`
- `0x18000cc50`
- `0x18000cd3c`
- `0x18000ce28`
- `0x18000cf14`
- `0x18000d000`
- `0x18000d0ec`
- `0x18000d1d8`
- `0x18000d2c4`
- `0x1800132d0`
- `0x180018a9c`
- `0x18003d2dc`
- `0x18003d3c8`
- `0x18003d4b4`
- `0x18003d5a0`
- `0x18003d68c`
- `0x18003d778`
- `0x18003d864`
- `0x18003d950`
- `0x18003da3c`
- `0x18003db28`
- `0x18003dc14`
- `0x180044e10`

## callees

- `0x1800089e8`
- `0x18000f1b8`
- `0x18000fb88`
- `0x180019010`
- `0x18001cfb8`
- `0x180056a94`

## string_xrefs

- `0x180019052`: `onecore\ds\security\asn1\ntasn1\ntasn1der\derdec.c`
- `0x180019084`: `onecore\ds\security\asn1\ntasn1\ntasn1der\derdec.c`
- `0x1800190ad`: `onecore\ds\security\asn1\ntasn1\ntasn1der\derdec.c`
- `0x1800190fb`: `onecore\ds\security\asn1\ntasn1\ntasn1der\derdec.c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Asn1Tag::decode(__int64 a1, __int64 a2)
{
  __int64 v4; // rdx
  __int64 v5; // r9
  unsigned __int64 v6; // r15
  char *v7; // rbp
  int v8; // esi
  char *v9; // r14
  unsigned int v10; // ebx
  __int64 v11; // r9
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  char v15; // al
  unsigned int v16; // eax
  unsigned int v18; // [rsp+68h] [rbp+10h] BYREF
  unsigned int v19; // [rsp+70h] [rbp+18h] BYREF
  int v20; // [rsp+74h] [rbp+1Ch]

  errorlib::scoped_error<ntstatus_error::tag>::scoped_error<ntstatus_error::tag>(&v19);
  v6 = *(_QWORD *)(a2 + 8);
  v7 = *(char **)a2;
  if ( *(_QWORD *)a2 >= v6 )
  {
    v8 = 0;
    v9 = *(char **)a2;
    v10 = -2146881278;
    v11 = 436;
    v12 = 2148086018LL;
LABEL_3:
    DebugTraceError(v12, v4, "onecore\\ds\\security\\asn1\\ntasn1\\ntasn1der\\derdec.c", v11);
    goto LABEL_20;
  }
  v13 = (unsigned __int8)*v7;
  v8 = *v7 & 0x1F;
  v9 = v7 + 1;
  if ( v8 == 31 )
  {
    if ( (unsigned __int64)v9 >= v6 )
    {
      v14 = 100;
LABEL_7:
      DebugTraceError(2148086018LL, v4, "onecore\\ds\\security\\asn1\\ntasn1\\ntasn1der\\derdec.c", v14);
      v10 = -2146881278;
      goto LABEL_17;
    }
    v15 = *v9;
    v9 = v7 + 2;
    if ( v15 == (char)0x80 )
    {
      DebugTraceError(2148086029LL, v4, "onecore\\ds\\security\\asn1\\ntasn1\\ntasn1der\\derdec.c", 114);
      v10 = -2146881267;
LABEL_17:
      v11 = 455;
      v12 = v10;
      goto LABEL_3;
    }
    v4 = 0;
    v5 = 127;
    while ( v15 < 0 )
    {
      if ( (v4 & 0xFE000000) != 0 )
      {
        DebugTraceError(2148086020LL, v4, "onecore\\ds\\security\\asn1\\ntasn1\\ntasn1der\\derdec.c", 127);
        v10 = -2146881276;
        goto LABEL_17;
      }
      if ( (unsigned __int64)v9 >= v6 )
      {
        v14 = 142;
        goto LABEL_7;
      }
      v4 = ((_DWORD)v4 << 7) | v15 & 0x7Fu;
      v15 = *v9++;
    }
    v8 = (unsigned __int8)v15 | ((_DWORD)v4 << 7);
  }
  v8 |= ((_DWORD)v13 << 24) & 0xE0000000;
  v10 = 0;
LABEL_20:
  v18 = v10;
  errorlib::scoped_error<ntstatus_error::tag>::receive<long>(&v19, &v18, v13, v5);
  v16 = (v19 >> 30) - 1;
  *(_DWORD *)a1 = v19;
  *(_DWORD *)(a1 + 4) = 2;
  v20 = 5;
  if ( v16 <= 2 )
  {
    errorlib::scoped_error<ntstatus_error::tag>::report(a1, 3);
    *(_DWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = v7;
  }
  else
  {
    errorlib::scoped_error<ntstatus_error::tag>::report(a1, 3);
    *(_DWORD *)(a1 + 8) = v8;
    *(_QWORD *)(a1 + 16) = v9;
  }
  *(_QWORD *)(a1 + 24) = v6;
  errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(&v19);
  return a1;
}

```

## disassembly

```asm
0x180019010  mov     [rsp+arg_0], rbx
0x180019015  push    rbp
0x180019016  push    rsi
0x180019017  push    rdi
0x180019018  push    r14
0x18001901a  push    r15
0x18001901c  sub     rsp, 30h
0x180019020  mov     rbx, rdx
0x180019023  mov     rdi, rcx
0x180019026  lea     rcx, [rsp+58h+arg_10]
0x18001902b  call    ??0?$scoped_error@Utag@ntstatus_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<ntstatus_error::tag>::scoped_error<ntstatus_error::tag>(void)
0x180019030  nop
0x180019031  mov     r15, [rbx+8]
0x180019035  mov     rbp, [rbx]
0x180019038  cmp     rbp, r15
0x18001903b  jb      short loc_180019063
0x18001903d  xor     esi, esi
0x18001903f  mov     r14, rbp
0x180019042  mov     ebx, 80093102h
0x180019047  mov     r9d, 1B4h
0x18001904d  mov     ecx, 80093102h
0x180019052  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\asn1\\ntasn1\\nt"...
0x180019059  call    DebugTraceError
0x18001905e  jmp     loc_180019137
0x180019063  movzx   r8d, byte ptr [rbp+0]
0x180019068  mov     esi, r8d
0x18001906b  and     esi, 1Fh
0x18001906e  lea     r14, [rbp+1]
0x180019072  cmp     esi, 1Fh
0x180019075  jnz     loc_180019128
0x18001907b  cmp     r14, r15
0x18001907e  jb      short loc_18001909C
0x180019080  lea     r9d, [rsi+45h]
0x180019084  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\asn1\\ntasn1\\nt"...
0x18001908b  mov     ecx, 80093102h
0x180019090  call    DebugTraceError
0x180019095  mov     ebx, 80093102h
0x18001909a  jmp     short loc_180019111
0x18001909c  mov     al, [r14]
0x18001909f  lea     r14, [rbp+2]
0x1800190a3  cmp     al, 80h
0x1800190a5  jnz     short loc_1800190C5
0x1800190a7  mov     r9d, 72h ; 'r'
0x1800190ad  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\asn1\\ntasn1\\nt"...
0x1800190b4  mov     ecx, 8009310Dh
0x1800190b9  call    DebugTraceError
0x1800190be  mov     ebx, 8009310Dh
0x1800190c3  jmp     short loc_180019111
0x1800190c5  xor     edx, edx
0x1800190c7  lea     r9d, [rdx+7Fh]
0x1800190cb  test    al, al
0x1800190cd  jns     short loc_18001911E
0x1800190cf  test    edx, 0FE000000h
0x1800190d5  jnz     short loc_1800190FB
0x1800190d7  cmp     r14, r15
0x1800190da  jnb     short loc_1800190F3
0x1800190dc  movzx   ecx, al
0x1800190df  and     ecx, r9d
0x1800190e2  mov     eax, edx
0x1800190e4  shl     eax, 7
0x1800190e7  mov     edx, ecx
0x1800190e9  or      edx, eax
0x1800190eb  mov     al, [r14]
0x1800190ee  inc     r14
0x1800190f1  jmp     short loc_1800190CB
0x1800190f3  mov     r9d, 8Eh
0x1800190f9  jmp     short loc_180019084
0x1800190fb  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\asn1\\ntasn1\\nt"...
0x180019102  mov     ecx, 80093104h
0x180019107  call    DebugTraceError
0x18001910c  mov     ebx, 80093104h
0x180019111  mov     r9d, 1C7h
0x180019117  mov     ecx, ebx
0x180019119  jmp     loc_180019052
0x18001911e  mov     esi, edx
0x180019120  shl     esi, 7
0x180019123  movzx   eax, al
0x180019126  or      esi, eax
0x180019128  mov     eax, r8d
0x18001912b  shl     eax, 18h
0x18001912e  and     eax, 0E0000000h
0x180019133  or      esi, eax
0x180019135  xor     ebx, ebx
0x180019137  mov     [rsp+58h+arg_8], ebx
0x18001913b  lea     rdx, [rsp+58h+arg_8]
0x180019140  lea     rcx, [rsp+58h+arg_10]
0x180019145  call    ??$receive@J@?$scoped_error@Utag@ntstatus_error@@@errorlib@@QEAAAEAV01@$$QEAJ@Z; errorlib::scoped_error<ntstatus_error::tag>::receive<long>(long &&)
0x18001914a  mov     ecx, [rsp+58h+arg_10]
0x18001914e  mov     eax, ecx
0x180019150  shr     eax, 1Eh
0x180019153  dec     eax
0x180019155  mov     edx, 2
0x18001915a  mov     [rdi], ecx
0x18001915c  mov     [rdi+4], edx
0x18001915f  mov     [rsp+58h+arg_14], 5
0x180019167  mov     rcx, rdi
0x18001916a  cmp     eax, edx
0x18001916c  mov     edx, 3
0x180019171  jbe     short loc_180019181
0x180019173  call    ?report@?$scoped_error@Utag@ntstatus_error@@@errorlib@@AEAAXW4type@ErrorSource@2@@Z; errorlib::scoped_error<ntstatus_error::tag>::report(errorlib::ErrorSource::type)
0x180019178  mov     [rdi+8], esi
0x18001917b  mov     [rdi+10h], r14
0x18001917f  jmp     short loc_180019191
0x180019181  call    ?report@?$scoped_error@Utag@ntstatus_error@@@errorlib@@AEAAXW4type@ErrorSource@2@@Z; errorlib::scoped_error<ntstatus_error::tag>::report(errorlib::ErrorSource::type)
0x180019186  mov     dword ptr [rdi+8], 0
0x18001918d  mov     [rdi+10h], rbp
0x180019191  mov     [rdi+18h], r15
0x180019195  lea     rcx, [rsp+58h+arg_10]
0x18001919a  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x18001919f  mov     rax, rdi
0x1800191a2  mov     rbx, [rsp+58h+arg_0]
0x1800191a7  add     rsp, 30h
0x1800191ab  pop     r15
0x1800191ad  pop     r14
0x1800191af  pop     rdi
0x1800191b0  pop     rsi
0x1800191b1  pop     rbp
0x1800191b2  retn
```
