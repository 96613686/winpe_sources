# Kerb3961::RFC4121CipherSuite<1,1,0>::CommonGetMIC(Kerb3961::ReadOnlyBinary const &,unsigned __int64,uint,Kerb3961::ReadOnlyBinary const &,bool,bool)

- ea: `0x1800023e0`
- end: `0x1800025d7`
- name: `?CommonGetMIC@?$RFC4121CipherSuite@$00$00$0A@@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@_KI0_N2@Z`
- size: `503`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x1800018e8`
- `0x1800023e0`
- `0x180003910`
- `0x180003a38`
- `0x180005b1c`
- `0x1800118cc`
- `0x180011b40`
- `0x180012240`

## string_xrefs

- `0x180002512`: `combinedInput`

## pseudocode

```c
__int64 __fastcall Kerb3961::RFC4121CipherSuite<1,1,0>::CommonGetMIC(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        unsigned __int64 a4,
        int a5,
        __int64 a6,
        unsigned __int8 a7,
        char a8)
{
  _QWORD *v8; // r12
  unsigned int (__fastcall *v13)(_QWORD *); // rdi
  int v14; // ebx
  const unsigned __int16 *v15; // rdx
  int v16; // r8d
  int v17; // ebx
  int v18; // r8d
  int v19; // ebx
  _QWORD *v20; // rcx
  _QWORD *v21; // rbx
  char v22; // al
  int v23; // r8d
  int v24; // edi
  int v25; // r8d
  int v26; // edi
  char *v28[2]; // [rsp+30h] [rbp-61h] BYREF
  char *v29; // [rsp+40h] [rbp-51h]
  _BYTE v30[8]; // [rsp+48h] [rbp-49h] BYREF
  _QWORD *v31; // [rsp+50h] [rbp-41h]
  char *v32; // [rsp+58h] [rbp-39h]
  _BYTE v33[8]; // [rsp+60h] [rbp-31h] BYREF
  __int64 v34; // [rsp+68h] [rbp-29h]
  char *v35; // [rsp+70h] [rbp-21h]
  _BYTE v36[8]; // [rsp+78h] [rbp-19h] BYREF
  __int64 v37; // [rsp+80h] [rbp-11h]
  char *v38; // [rsp+88h] [rbp-9h]

  v8 = a1 + 1;
  v13 = *(unsigned int (__fastcall **)(_QWORD *))(*a1 + 224LL);
  v14 = (*(__int64 (__fastcall **)(_QWORD *))(a1[1] + 104LL))(a1 + 1);
  if ( v14 != v13(a1) )
    Kerb3961::ConsistencyFail(
      (Kerb3961 *)L"A cipher suite's included checksum must be the required checksum for the included cipher",
      v15);
  (*(void (__fastcall **)(_QWORD *, char **, __int64, __int64, int))(*a1 + 168LL))(a1, v28, a6, 2LL * a7 + 23, 2);
  v17 = (int)v29;
  if ( (int)v29 < 0 )
  {
    Kerb3961::Logging::Verify::StatusFailed(
      (Kerb3961::Logging::Verify *)"specificKey",
      (const char *)(unsigned int)v29,
      v16);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = v17;
    goto LABEL_23;
  }
  Kerb3961::MakeBuffer(v30);
  v19 = (int)v32;
  if ( (int)v32 < 0 )
  {
    Kerb3961::Logging::Verify::StatusFailed(
      (Kerb3961::Logging::Verify *)"headerBuffer",
      (const char *)(unsigned int)v32,
      v18);
    v20 = v31;
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = v19;
    if ( !v20 )
      goto LABEL_23;
    goto LABEL_22;
  }
  v21 = v31;
  v22 = 0;
  *v31 = -16776188;
  if ( !a7 )
  {
    v22 = 1;
    *((_BYTE *)v21 + 2) = 1;
  }
  if ( a8 )
    *((_BYTE *)v21 + 2) = v22 | 4;
  v21[1] = _byteswap_uint64(a4);
  Kerb3961::Concatenate(v33, a3, v30);
  v24 = (int)v35;
  if ( (int)v35 >= 0 )
  {
    (*(void (__fastcall **)(_QWORD *, _BYTE *, char **, _BYTE *))(*v8 + 88LL))(v8, v36, v28, v33);
    v26 = (int)v38;
    if ( (int)v38 >= 0 )
    {
      Kerb3961::Concatenate(a2, v30, v36);
    }
    else
    {
      Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)"hmac", (const char *)(unsigned int)v38, v25);
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = v26;
    }
    if ( v37 )
      Kerb3961Free(v37);
  }
  else
  {
    Kerb3961::Logging::Verify::StatusFailed(
      (Kerb3961::Logging::Verify *)"combinedInput",
      (const char *)(unsigned int)v35,
      v23);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = v24;
  }
  if ( v34 )
    Kerb3961Free(v34);
  if ( v21 )
  {
    v20 = v21;
LABEL_22:
    Kerb3961Free(v20);
  }
LABEL_23:
  if ( v28[1] )
     Kerb3961::EncryptionAlgorithm::`vcall'{160,{flat}}(v28[0]);
  return a2;
}

```

## disassembly

```asm
0x1800023e0  push    rbp
0x1800023e2  push    rbx
0x1800023e3  push    rsi
0x1800023e4  push    rdi
0x1800023e5  push    r12
0x1800023e7  push    r13
0x1800023e9  push    r14
0x1800023eb  push    r15
0x1800023ed  lea     rbp, [rsp-7]
0x1800023f2  sub     rsp, 98h
0x1800023f9  mov     r10, [rcx]
0x1800023fc  lea     r12, [rcx+8]
0x180002400  mov     rax, [r12]
0x180002404  mov     r15, rcx
0x180002407  mov     rcx, r12
0x18000240a  mov     r14, r9
0x18000240d  mov     r13, r8
0x180002410  mov     rsi, rdx
0x180002413  mov     rdi, [r10+0E0h]
0x18000241a  mov     rax, [rax+68h]
0x18000241e  call    _guard_dispatch_icall
0x180002423  mov     ebx, eax
0x180002425  mov     rcx, r15
0x180002428  mov     rax, rdi
0x18000242b  call    _guard_dispatch_icall
0x180002430  cmp     ebx, eax
0x180002432  jnz     loc_1800025CA
0x180002438  mov     rax, [r15]
0x18000243b  lea     rdx, [rbp+3Fh+var_A0]
0x18000243f  movzx   edi, [rbp+3Fh+arg_30]
0x180002443  mov     rcx, r15
0x180002446  mov     r8, [rbp+3Fh+arg_28]
0x18000244a  mov     [rsp+0D0h+var_B0], 2
0x180002452  mov     rax, [rax+0A8h]
0x180002459  lea     r9, ds:17h[rdi*2]
0x180002461  call    _guard_dispatch_icall
0x180002466  mov     ebx, dword ptr [rbp+3Fh+var_90]
0x180002469  xor     r15d, r15d
0x18000246c  test    ebx, ebx
0x18000246e  jns     short loc_18000248D
0x180002470  mov     edx, ebx; char *
0x180002472  lea     rcx, aSpecifickey; "specificKey"
0x180002479  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000247e  mov     [rsi], r15
0x180002481  mov     [rsi+8], r15
0x180002485  mov     [rsi+10h], ebx
0x180002488  jmp     loc_1800025A0
0x18000248d  mov     edx, 10h
0x180002492  lea     rcx, [rbp+3Fh+var_88]
0x180002496  call    ?MakeBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@_K@Z; Kerb3961::MakeBuffer(unsigned __int64)
0x18000249b  mov     ebx, dword ptr [rbp+3Fh+var_78]
0x18000249e  test    ebx, ebx
0x1800024a0  jns     short loc_1800024CC
0x1800024a2  mov     edx, ebx; char *
0x1800024a4  lea     rcx, aHeaderbuffer; "headerBuffer"
0x1800024ab  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800024b0  mov     rcx, [rbp+3Fh+var_80]
0x1800024b4  mov     [rsi], r15
0x1800024b7  mov     [rsi+8], r15
0x1800024bb  mov     [rsi+10h], ebx
0x1800024be  test    rcx, rcx
0x1800024c1  jz      loc_1800025A0
0x1800024c7  jmp     loc_18000259B
0x1800024cc  mov     rbx, [rbp+3Fh+var_80]
0x1800024d0  mov     al, r15b
0x1800024d3  mov     qword ptr [rbx], 0FFFFFFFFFF000404h
0x1800024da  test    dil, dil
0x1800024dd  jnz     short loc_1800024E4
0x1800024df  mov     al, 1
0x1800024e1  mov     [rbx+2], al
0x1800024e4  cmp     [rbp+3Fh+arg_38], r15b
0x1800024eb  jz      short loc_1800024F2
0x1800024ed  or      al, 4
0x1800024ef  mov     [rbx+2], al
0x1800024f2  bswap   r14
0x1800024f5  lea     r8, [rbp+3Fh+var_88]
0x1800024f9  mov     [rbx+8], r14
0x1800024fd  mov     rdx, r13
0x180002500  lea     rcx, [rbp+3Fh+var_70]
0x180002504  call    ?Concatenate@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@0@Z; Kerb3961::Concatenate(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x180002509  mov     edi, dword ptr [rbp+3Fh+var_60]
0x18000250c  test    edi, edi
0x18000250e  jns     short loc_18000252A
0x180002510  mov     edx, edi; char *
0x180002512  lea     rcx, aCombinedinput; "combinedInput"
0x180002519  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000251e  mov     [rsi], r15
0x180002521  mov     [rsi+8], r15
0x180002525  mov     [rsi+10h], edi
0x180002528  jmp     short loc_180002585
0x18000252a  mov     rax, [r12]
0x18000252e  lea     r9, [rbp+3Fh+var_70]
0x180002532  lea     r8, [rbp+3Fh+var_A0]
0x180002536  mov     rcx, r12
0x180002539  lea     rdx, [rbp+3Fh+var_58]
0x18000253d  mov     rax, [rax+58h]
0x180002541  call    _guard_dispatch_icall
0x180002546  mov     edi, dword ptr [rbp+3Fh+var_48]
0x180002549  test    edi, edi
0x18000254b  jns     short loc_180002567
0x18000254d  mov     edx, edi; char *
0x18000254f  lea     rcx, aHmac; "hmac"
0x180002556  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000255b  mov     [rsi], r15
0x18000255e  mov     [rsi+8], r15
0x180002562  mov     [rsi+10h], edi
0x180002565  jmp     short loc_180002577
0x180002567  lea     r8, [rbp+3Fh+var_58]
0x18000256b  mov     rcx, rsi
0x18000256e  lea     rdx, [rbp+3Fh+var_88]
0x180002572  call    ?Concatenate@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@0@Z; Kerb3961::Concatenate(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x180002577  mov     rcx, [rbp+3Fh+var_50]
0x18000257b  test    rcx, rcx
0x18000257e  jz      short loc_180002585
0x180002580  call    Kerb3961Free
0x180002585  mov     rcx, [rbp+3Fh+var_68]
0x180002589  test    rcx, rcx
0x18000258c  jz      short loc_180002593
0x18000258e  call    Kerb3961Free
0x180002593  test    rbx, rbx
0x180002596  jz      short loc_1800025A0
0x180002598  mov     rcx, rbx
0x18000259b  call    Kerb3961Free
0x1800025a0  mov     rdx, [rbp+3Fh+var_98]
0x1800025a4  test    rdx, rdx
0x1800025a7  jz      short loc_1800025B2
0x1800025a9  mov     rcx, [rbp+3Fh+var_A0]
0x1800025ad  call    ??_9EncryptionAlgorithm@Kerb3961@@$BKA@AA; [thunk]: Kerb3961::EncryptionAlgorithm::`vcall'{160,{flat}}
0x1800025b2  mov     rax, rsi
0x1800025b5  add     rsp, 98h
0x1800025bc  pop     r15
0x1800025be  pop     r14
0x1800025c0  pop     r13
0x1800025c2  pop     r12
0x1800025c4  pop     rdi
0x1800025c5  pop     rsi
0x1800025c6  pop     rbx
0x1800025c7  pop     rbp
0x1800025c8  retn
0x1800025ca  lea     rcx, aACipherSuiteSI; "A cipher suite's included checksum must"...
0x1800025d1  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
```
