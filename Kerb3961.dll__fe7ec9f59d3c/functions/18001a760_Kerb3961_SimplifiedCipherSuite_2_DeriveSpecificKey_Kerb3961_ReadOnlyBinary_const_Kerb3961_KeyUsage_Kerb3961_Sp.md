# Kerb3961::SimplifiedCipherSuite<2>::DeriveSpecificKey(Kerb3961::ReadOnlyBinary const &,Kerb3961::KeyUsage,Kerb3961::SpecificKeyScenario)

- ea: `0x18001a760`
- end: `0x18001aadd`
- name: `?DeriveSpecificKey@?$SimplifiedCipherSuite@$01@Kerb3961@@MEAA?AU?$ReturnType@USpecificKeyReturn@Kerb3961@@$1??$SingleGetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@W4KeyUsage@2@W4SpecificKeyScenario@2@@Z`
- size: `893`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops`

## callees

- `0x180001d40`
- `0x180001d64`
- `0x180002c64`
- `0x180002fc0`
- `0x18001023c`
- `0x18001a34c`
- `0x18001a760`
- `0x18001e010`

## pseudocode

```c
__int64 __fastcall Kerb3961::SimplifiedCipherSuite<2>::DeriveSpecificKey(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        int a5)
{
  const char *v8; // rdx
  void *v9; // rbx
  int v10; // r8d
  int v11; // r14d
  char *v12; // rcx
  __int64 v13; // rax
  int v14; // r8d
  void *v15; // rcx
  __int64 v16; // r14
  __int64 v17; // rax
  int v18; // r14d
  void *v19; // rcx
  void *v20; // rcx
  void *v21; // rcx
  void *v22; // rcx
  __int64 v23; // rax
  void *v24; // rcx
  __int64 v25; // r14
  __int64 v26; // rax
  __int64 v27; // rax
  void *v28; // rcx
  __int64 v29; // r14
  __int64 v30; // rax
  void *v31; // rcx
  _BYTE v33[8]; // [rsp+20h] [rbp-40h] BYREF
  void *v34; // [rsp+28h] [rbp-38h]
  char *v35; // [rsp+30h] [rbp-30h]
  void *v36; // [rsp+38h] [rbp-28h] BYREF
  void *v37; // [rsp+40h] [rbp-20h]
  __int64 v38; // [rsp+50h] [rbp-10h] BYREF

  v38 = _byteswap_ulong(a4);
  utl::make_unique<Kerb3961::SimplifiedSpecificKey,,0>(&v36);
  v9 = v36;
  if ( !v36 )
  {
    Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)"specificKey", v8);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = -1073741801;
    return a2;
  }
  if ( (unsigned int)(a5 - 2) <= 1 )
  {
    BYTE4(v38) = -103;
    v37 = &v38;
    v36 = (void *)5;
    Kerb3961::SimplifiedCipherSuite<2>::DeriveKey(a1, v33, a3, &v36);
    v11 = (int)v35;
    if ( (int)v35 < 0 )
    {
LABEL_5:
      v12 = "derivedKey";
      goto LABEL_39;
    }
    v13 = (*(__int64 (__fastcall **)(__int64, void **, _BYTE *))(*(_QWORD *)a1 + 128LL))(a1, &v36, v33);
    v15 = (void *)*((_QWORD *)v9 + 1);
    v16 = v13;
    if ( v15 )
      operator delete(v15, 0);
    *(_QWORD *)v9 = *(_QWORD *)v16;
    v17 = *(_QWORD *)(v16 + 8);
    *(_QWORD *)v16 = 0;
    *((_QWORD *)v9 + 1) = v17;
    LODWORD(v17) = *(_DWORD *)(v16 + 16);
    *(_QWORD *)(v16 + 8) = 0;
    *((_DWORD *)v9 + 4) = v17;
    *(_DWORD *)(v16 + 16) = -1073741823;
    v18 = *((_DWORD *)v9 + 4);
    if ( v37 )
      operator delete(v37, 0);
    if ( v18 < 0 )
    {
      Kerb3961::Logging::Verify::StatusFailed(
        (Kerb3961::Logging::Verify *)"specificKey->Kc = this->RandomToKey(derivedKey)",
        (const char *)(unsigned int)v18,
        v14);
      v19 = v34;
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = v18;
      if ( v19 )
        operator delete(v19, 0);
      goto LABEL_13;
    }
    if ( v34 )
      operator delete(v34, 0);
  }
  if ( ((a5 - 1) & 0xFFFFFFFD) != 0 )
  {
LABEL_45:
    *(_QWORD *)a2 = a1;
    *(_QWORD *)(a2 + 8) = v9;
    *(_DWORD *)(a2 + 16) = 0;
    return a2;
  }
  BYTE4(v38) = -86;
  v37 = &v38;
  v36 = (void *)5;
  Kerb3961::SimplifiedCipherSuite<2>::DeriveKey(a1, v33, a3, &v36);
  v11 = (int)v35;
  if ( (int)v35 < 0 )
    goto LABEL_5;
  v23 = (*(__int64 (__fastcall **)(__int64, void **, _BYTE *))(*(_QWORD *)a1 + 128LL))(a1, &v36, v33);
  v24 = (void *)*((_QWORD *)v9 + 4);
  v25 = v23;
  if ( v24 )
    operator delete(v24, 0);
  *((_QWORD *)v9 + 3) = *(_QWORD *)v25;
  v26 = *(_QWORD *)(v25 + 8);
  *(_QWORD *)v25 = 0;
  *((_QWORD *)v9 + 4) = v26;
  LODWORD(v26) = *(_DWORD *)(v25 + 16);
  *(_QWORD *)(v25 + 8) = 0;
  *((_DWORD *)v9 + 10) = v26;
  *(_DWORD *)(v25 + 16) = -1073741823;
  v11 = *((_DWORD *)v9 + 10);
  if ( v37 )
    operator delete(v37, 0);
  if ( v11 < 0 )
  {
    v12 = "specificKey->Ke = this->RandomToKey(derivedKey)";
    goto LABEL_39;
  }
  if ( v34 )
    operator delete(v34, 0);
  BYTE4(v38) = 85;
  v37 = &v38;
  v36 = (void *)5;
  Kerb3961::SimplifiedCipherSuite<2>::DeriveKey(a1, v33, a3, &v36);
  v11 = (int)v35;
  if ( (int)v35 < 0 )
    goto LABEL_5;
  v27 = (*(__int64 (__fastcall **)(__int64, void **, _BYTE *))(*(_QWORD *)a1 + 128LL))(a1, &v36, v33);
  v28 = (void *)*((_QWORD *)v9 + 7);
  v29 = v27;
  if ( v28 )
    operator delete(v28, 0);
  *((_QWORD *)v9 + 6) = *(_QWORD *)v29;
  v30 = *(_QWORD *)(v29 + 8);
  *(_QWORD *)v29 = 0;
  *((_QWORD *)v9 + 7) = v30;
  LODWORD(v30) = *(_DWORD *)(v29 + 16);
  *(_QWORD *)(v29 + 8) = 0;
  *((_DWORD *)v9 + 16) = v30;
  *(_DWORD *)(v29 + 16) = -1073741823;
  v11 = *((_DWORD *)v9 + 16);
  if ( v37 )
    operator delete(v37, 0);
  if ( v11 >= 0 )
  {
    if ( v34 )
      operator delete(v34, 0);
    goto LABEL_45;
  }
  v12 = "specificKey->Ki = this->RandomToKey(derivedKey)";
LABEL_39:
  Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)v12, (const char *)(unsigned int)v11, v10);
  v31 = v34;
  *(_QWORD *)a2 = 0;
  *(_QWORD *)(a2 + 8) = 0;
  *(_DWORD *)(a2 + 16) = v11;
  if ( v31 )
    operator delete(v31, 0);
  if ( v9 )
  {
LABEL_13:
    v20 = (void *)*((_QWORD *)v9 + 7);
    if ( v20 )
      operator delete(v20, 0);
    v21 = (void *)*((_QWORD *)v9 + 4);
    if ( v21 )
      operator delete(v21, 0);
    v22 = (void *)*((_QWORD *)v9 + 1);
    if ( v22 )
      operator delete(v22, 0);
    operator delete(v9, (const struct std::nothrow_t *)0x48);
  }
  return a2;
}

```

## disassembly

```asm
0x18001a760  mov     [rsp-38h+arg_18], rbx
0x18001a765  push    rbp
0x18001a766  push    rsi
0x18001a767  push    rdi
0x18001a768  push    r12
0x18001a76a  push    r13
0x18001a76c  push    r14
0x18001a76e  push    r15
0x18001a770  mov     rbp, rsp
0x18001a773  sub     rsp, 60h
0x18001a777  mov     rax, cs:__security_cookie
0x18001a77e  xor     rax, rsp
0x18001a781  mov     [rbp+var_8], rax
0x18001a785  mov     rsi, rcx
0x18001a788  xor     r13d, r13d
0x18001a78b  bswap   r9d
0x18001a78e  mov     [rbp+var_10], r13
0x18001a792  lea     rcx, [rbp+var_28]
0x18001a796  mov     dword ptr [rbp+var_10], r9d
0x18001a79a  mov     r12, r8
0x18001a79d  mov     rdi, rdx
0x18001a7a0  call    ??$make_unique@USimplifiedSpecificKey@Kerb3961@@$$V$0A@@utl@@YA?AV?$unique_ptr@USimplifiedSpecificKey@Kerb3961@@U?$default_delete@USimplifiedSpecificKey@Kerb3961@@@utl@@@0@XZ; utl::make_unique<Kerb3961::SimplifiedSpecificKey,,0>(void)
0x18001a7a5  mov     rbx, [rbp+var_28]
0x18001a7a9  test    rbx, rbx
0x18001a7ac  jnz     short loc_18001A7CD
0x18001a7ae  lea     rcx, aSpecifickey; "specificKey"
0x18001a7b5  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18001a7ba  mov     [rdi], r13
0x18001a7bd  mov     [rdi+8], r13
0x18001a7c1  mov     dword ptr [rdi+10h], 0C0000017h
0x18001a7c8  jmp     loc_18001AAB6
0x18001a7cd  mov     r15d, [rbp+arg_20]
0x18001a7d1  lea     eax, [r15-2]
0x18001a7d5  cmp     eax, 1
0x18001a7d8  ja      loc_18001A900
0x18001a7de  lea     rax, [rbp+var_10]
0x18001a7e2  mov     byte ptr [rbp+var_10+4], 99h
0x18001a7e6  lea     r9, [rbp+var_28]
0x18001a7ea  mov     [rbp+var_20], rax
0x18001a7ee  mov     r8, r12
0x18001a7f1  mov     [rbp+var_28], 5
0x18001a7f9  lea     rdx, [rbp+var_40]
0x18001a7fd  mov     rcx, rsi
0x18001a800  call    ?DeriveKey@?$SimplifiedCipherSuite@$01@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z; Kerb3961::SimplifiedCipherSuite<2>::DeriveKey(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x18001a805  mov     r14d, dword ptr [rbp+var_30]
0x18001a809  test    r14d, r14d
0x18001a80c  jns     short loc_18001A81A
0x18001a80e  lea     rcx, aDerivedkey; "derivedKey"
0x18001a815  jmp     loc_18001AA6E
0x18001a81a  mov     rax, [rsi]
0x18001a81d  lea     r8, [rbp+var_40]
0x18001a821  lea     rdx, [rbp+var_28]
0x18001a825  mov     rcx, rsi
0x18001a828  mov     rax, [rax+80h]
0x18001a82f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a834  mov     rcx, [rbx+8]; void *
0x18001a838  mov     r14, rax
0x18001a83b  test    rcx, rcx
0x18001a83e  jz      short loc_18001A847
0x18001a840  xor     edx, edx; struct std::nothrow_t *
0x18001a842  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001a847  mov     rcx, [r14]
0x18001a84a  mov     [rbx], rcx
0x18001a84d  mov     rax, [r14+8]
0x18001a851  mov     [r14], r13
0x18001a854  mov     [rbx+8], rax
0x18001a858  mov     eax, [r14+10h]
0x18001a85c  mov     [r14+8], r13
0x18001a860  mov     [rbx+10h], eax
0x18001a863  mov     dword ptr [r14+10h], 0C0000001h
0x18001a86b  mov     rcx, [rbp+var_20]; void *
0x18001a86f  mov     r14d, [rbx+10h]
0x18001a873  test    rcx, rcx
0x18001a876  jz      short loc_18001A87F
0x18001a878  xor     edx, edx; struct std::nothrow_t *
0x18001a87a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001a87f  test    r14d, r14d
0x18001a882  jns     short loc_18001A8F0
0x18001a884  mov     edx, r14d; char *
0x18001a887  lea     rcx, aSpecifickeyKcT; "specificKey->Kc = this->RandomToKey(der"...
0x18001a88e  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18001a893  mov     rcx, [rbp+var_38]; void *
0x18001a897  mov     [rdi], r13
0x18001a89a  mov     [rdi+8], r13
0x18001a89e  mov     [rdi+10h], r14d
0x18001a8a2  test    rcx, rcx
0x18001a8a5  jz      short loc_18001A8AE
0x18001a8a7  xor     edx, edx; struct std::nothrow_t *
0x18001a8a9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001a8ae  mov     rcx, [rbx+38h]; void *
0x18001a8b2  test    rcx, rcx
0x18001a8b5  jz      short loc_18001A8BE
0x18001a8b7  xor     edx, edx; struct std::nothrow_t *
0x18001a8b9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001a8be  mov     rcx, [rbx+20h]; void *
0x18001a8c2  test    rcx, rcx
0x18001a8c5  jz      short loc_18001A8CE
0x18001a8c7  xor     edx, edx; struct std::nothrow_t *
0x18001a8c9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001a8ce  mov     rcx, [rbx+8]; void *
0x18001a8d2  test    rcx, rcx
0x18001a8d5  jz      short loc_18001A8DE
0x18001a8d7  xor     edx, edx; struct std::nothrow_t *
0x18001a8d9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001a8de  mov     edx, 48h ; 'H'; struct std::nothrow_t *
0x18001a8e3  mov     rcx, rbx; void *
0x18001a8e6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001a8eb  jmp     loc_18001AAB6
0x18001a8f0  mov     rcx, [rbp+var_38]; void *
0x18001a8f4  test    rcx, rcx
0x18001a8f7  jz      short loc_18001A900
0x18001a8f9  xor     edx, edx; struct std::nothrow_t *
0x18001a8fb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001a900  lea     eax, [r15-1]
0x18001a904  test    eax, 0FFFFFFFDh
0x18001a909  jnz     loc_18001AAAB
0x18001a90f  lea     rax, [rbp+var_10]
0x18001a913  mov     byte ptr [rbp+var_10+4], 0AAh
0x18001a917  lea     r9, [rbp+var_28]
0x18001a91b  mov     [rbp+var_20], rax
0x18001a91f  mov     r8, r12
0x18001a922  mov     [rbp+var_28], 5
0x18001a92a  lea     rdx, [rbp+var_40]
0x18001a92e  mov     rcx, rsi
0x18001a931  call    ?DeriveKey@?$SimplifiedCipherSuite@$01@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z; Kerb3961::SimplifiedCipherSuite<2>::DeriveKey(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x18001a936  mov     r14d, dword ptr [rbp+var_30]
0x18001a93a  test    r14d, r14d
0x18001a93d  js      loc_18001A80E
0x18001a943  mov     rax, [rsi]
0x18001a946  lea     r8, [rbp+var_40]
0x18001a94a  lea     rdx, [rbp+var_28]
0x18001a94e  mov     rcx, rsi
0x18001a951  mov     rax, [rax+80h]
0x18001a958  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a95d  mov     rcx, [rbx+20h]; void *
0x18001a961  mov     r14, rax
0x18001a964  test    rcx, rcx
0x18001a967  jz      short loc_18001A970
0x18001a969  xor     edx, edx; struct std::nothrow_t *
0x18001a96b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001a970  mov     rcx, [r14]
0x18001a973  mov     r15d, 0C0000001h
0x18001a979  mov     [rbx+18h], rcx
0x18001a97d  mov     rax, [r14+8]
0x18001a981  mov     [r14], r13
0x18001a984  mov     [rbx+20h], rax
0x18001a988  mov     eax, [r14+10h]
0x18001a98c  mov     [r14+8], r13
0x18001a990  mov     [rbx+28h], eax
0x18001a993  mov     [r14+10h], r15d
0x18001a997  mov     rcx, [rbp+var_20]; void *
0x18001a99b  mov     r14d, [rbx+28h]
0x18001a99f  test    rcx, rcx
0x18001a9a2  jz      short loc_18001A9AB
0x18001a9a4  xor     edx, edx; struct std::nothrow_t *
0x18001a9a6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001a9ab  test    r14d, r14d
0x18001a9ae  jns     short loc_18001A9BC
0x18001a9b0  lea     rcx, aSpecifickeyKeT; "specificKey->Ke = this->RandomToKey(der"...
0x18001a9b7  jmp     loc_18001AA6E
0x18001a9bc  mov     rcx, [rbp+var_38]; void *
0x18001a9c0  test    rcx, rcx
0x18001a9c3  jz      short loc_18001A9CC
0x18001a9c5  xor     edx, edx; struct std::nothrow_t *
0x18001a9c7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001a9cc  lea     rax, [rbp+var_10]
0x18001a9d0  mov     byte ptr [rbp+var_10+4], 55h ; 'U'
0x18001a9d4  lea     r9, [rbp+var_28]
0x18001a9d8  mov     [rbp+var_20], rax
0x18001a9dc  mov     r8, r12
0x18001a9df  mov     [rbp+var_28], 5
0x18001a9e7  lea     rdx, [rbp+var_40]
0x18001a9eb  mov     rcx, rsi
0x18001a9ee  call    ?DeriveKey@?$SimplifiedCipherSuite@$01@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z; Kerb3961::SimplifiedCipherSuite<2>::DeriveKey(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x18001a9f3  mov     r14d, dword ptr [rbp+var_30]
0x18001a9f7  test    r14d, r14d
0x18001a9fa  js      loc_18001A80E
0x18001aa00  mov     rax, [rsi]
0x18001aa03  lea     r8, [rbp+var_40]
0x18001aa07  lea     rdx, [rbp+var_28]
0x18001aa0b  mov     rcx, rsi
0x18001aa0e  mov     rax, [rax+80h]
0x18001aa15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa1a  mov     rcx, [rbx+38h]; void *
0x18001aa1e  mov     r14, rax
0x18001aa21  test    rcx, rcx
0x18001aa24  jz      short loc_18001AA2D
0x18001aa26  xor     edx, edx; struct std::nothrow_t *
0x18001aa28  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001aa2d  mov     rcx, [r14]
0x18001aa30  mov     [rbx+30h], rcx
0x18001aa34  mov     rax, [r14+8]
0x18001aa38  mov     [r14], r13
0x18001aa3b  mov     [rbx+38h], rax
0x18001aa3f  mov     eax, [r14+10h]
0x18001aa43  mov     [r14+8], r13
0x18001aa47  mov     [rbx+40h], eax
0x18001aa4a  mov     [r14+10h], r15d
0x18001aa4e  mov     rcx, [rbp+var_20]; void *
0x18001aa52  mov     r14d, [rbx+40h]
0x18001aa56  test    rcx, rcx
0x18001aa59  jz      short loc_18001AA62
0x18001aa5b  xor     edx, edx; struct std::nothrow_t *
0x18001aa5d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001aa62  test    r14d, r14d
0x18001aa65  jns     short loc_18001AA9B
0x18001aa67  lea     rcx, aSpecifickeyKiT; "specificKey->Ki = this->RandomToKey(der"...
0x18001aa6e  mov     edx, r14d; char *
0x18001aa71  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18001aa76  mov     rcx, [rbp+var_38]; void *
0x18001aa7a  mov     [rdi], r13
0x18001aa7d  mov     [rdi+8], r13
0x18001aa81  mov     [rdi+10h], r14d
0x18001aa85  test    rcx, rcx
0x18001aa88  jz      short loc_18001AA91
0x18001aa8a  xor     edx, edx; struct std::nothrow_t *
0x18001aa8c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001aa91  test    rbx, rbx
0x18001aa94  jz      short loc_18001AAB6
0x18001aa96  jmp     loc_18001A8AE
0x18001aa9b  mov     rcx, [rbp+var_38]; void *
0x18001aa9f  test    rcx, rcx
0x18001aaa2  jz      short loc_18001AAAB
0x18001aaa4  xor     edx, edx; struct std::nothrow_t *
0x18001aaa6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001aaab  mov     [rdi], rsi
0x18001aaae  mov     [rdi+8], rbx
0x18001aab2  mov     [rdi+10h], r13d
0x18001aab6  mov     rax, rdi
0x18001aab9  mov     rcx, [rbp+var_8]
0x18001aabd  xor     rcx, rsp; StackCookie
0x18001aac0  call    __security_check_cookie
0x18001aac5  mov     rbx, [rsp+60h+arg_18]
0x18001aacd  add     rsp, 60h
0x18001aad1  pop     r15
0x18001aad3  pop     r14
0x18001aad5  pop     r13
0x18001aad7  pop     r12
0x18001aad9  pop     rdi
0x18001aada  pop     rsi
0x18001aadb  pop     rbp
0x18001aadc  retn
```
