# Kerb3961::SimplifiedCipherSuite<2>::DeriveSpecificKey(Kerb3961::ReadOnlyBinary const &,Kerb3961::KeyUsage,Kerb3961::SpecificKeyScenario)

- ea: `0x180004390`
- end: `0x1800046ed`
- name: `?DeriveSpecificKey@?$SimplifiedCipherSuite@$01@Kerb3961@@MEAA?AU?$ReturnType@USpecificKeyReturn@Kerb3961@@$1??$SingleGetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@W4KeyUsage@2@W4SpecificKeyScenario@2@@Z`
- size: `861`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x18000186c`
- `0x1800041a0`
- `0x180004390`
- `0x180011760`
- `0x1800118cc`
- `0x180011b40`
- `0x180012200`
- `0x180012240`

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
  __int64 v9; // rbx
  int v10; // r8d
  int v11; // r14d
  char *v12; // rcx
  __int64 v13; // rax
  int v14; // r8d
  __int64 v15; // rcx
  __int64 v16; // r14
  __int64 v17; // rax
  int v18; // r14d
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rax
  __int64 v24; // rcx
  __int64 v25; // r14
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rcx
  __int64 v29; // r14
  __int64 v30; // rax
  __int64 v31; // rcx
  _BYTE v33[8]; // [rsp+20h] [rbp-40h] BYREF
  __int64 v34; // [rsp+28h] [rbp-38h]
  char *v35; // [rsp+30h] [rbp-30h]
  __int64 v36; // [rsp+38h] [rbp-28h] BYREF
  __int64 *v37; // [rsp+40h] [rbp-20h]
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
    v36 = 5;
    Kerb3961::SimplifiedCipherSuite<2>::DeriveKey(a1, v33, a3, &v36);
    v11 = (int)v35;
    if ( (int)v35 < 0 )
    {
LABEL_5:
      v12 = "derivedKey";
      goto LABEL_39;
    }
    v13 = (*(__int64 (__fastcall **)(__int64, __int64 *, _BYTE *))(*(_QWORD *)a1 + 128LL))(a1, &v36, v33);
    v15 = *(_QWORD *)(v9 + 8);
    v16 = v13;
    if ( v15 )
      Kerb3961Free(v15);
    *(_QWORD *)v9 = *(_QWORD *)v16;
    v17 = *(_QWORD *)(v16 + 8);
    *(_QWORD *)v16 = 0;
    *(_QWORD *)(v9 + 8) = v17;
    LODWORD(v17) = *(_DWORD *)(v16 + 16);
    *(_QWORD *)(v16 + 8) = 0;
    *(_DWORD *)(v9 + 16) = v17;
    *(_DWORD *)(v16 + 16) = -1073741823;
    v18 = *(_DWORD *)(v9 + 16);
    if ( v37 )
      Kerb3961Free(v37);
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
        Kerb3961Free(v19);
      goto LABEL_13;
    }
    if ( v34 )
      Kerb3961Free(v34);
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
  v36 = 5;
  Kerb3961::SimplifiedCipherSuite<2>::DeriveKey(a1, v33, a3, &v36);
  v11 = (int)v35;
  if ( (int)v35 < 0 )
    goto LABEL_5;
  v23 = (*(__int64 (__fastcall **)(__int64, __int64 *, _BYTE *))(*(_QWORD *)a1 + 128LL))(a1, &v36, v33);
  v24 = *(_QWORD *)(v9 + 32);
  v25 = v23;
  if ( v24 )
    Kerb3961Free(v24);
  *(_QWORD *)(v9 + 24) = *(_QWORD *)v25;
  v26 = *(_QWORD *)(v25 + 8);
  *(_QWORD *)v25 = 0;
  *(_QWORD *)(v9 + 32) = v26;
  LODWORD(v26) = *(_DWORD *)(v25 + 16);
  *(_QWORD *)(v25 + 8) = 0;
  *(_DWORD *)(v9 + 40) = v26;
  *(_DWORD *)(v25 + 16) = -1073741823;
  v11 = *(_DWORD *)(v9 + 40);
  if ( v37 )
    Kerb3961Free(v37);
  if ( v11 < 0 )
  {
    v12 = "specificKey->Ke = this->RandomToKey(derivedKey)";
    goto LABEL_39;
  }
  if ( v34 )
    Kerb3961Free(v34);
  BYTE4(v38) = 85;
  v37 = &v38;
  v36 = 5;
  Kerb3961::SimplifiedCipherSuite<2>::DeriveKey(a1, v33, a3, &v36);
  v11 = (int)v35;
  if ( (int)v35 < 0 )
    goto LABEL_5;
  v27 = (*(__int64 (__fastcall **)(__int64, __int64 *, _BYTE *))(*(_QWORD *)a1 + 128LL))(a1, &v36, v33);
  v28 = *(_QWORD *)(v9 + 56);
  v29 = v27;
  if ( v28 )
    Kerb3961Free(v28);
  *(_QWORD *)(v9 + 48) = *(_QWORD *)v29;
  v30 = *(_QWORD *)(v29 + 8);
  *(_QWORD *)v29 = 0;
  *(_QWORD *)(v9 + 56) = v30;
  LODWORD(v30) = *(_DWORD *)(v29 + 16);
  *(_QWORD *)(v29 + 8) = 0;
  *(_DWORD *)(v9 + 64) = v30;
  *(_DWORD *)(v29 + 16) = -1073741823;
  v11 = *(_DWORD *)(v9 + 64);
  if ( v37 )
    Kerb3961Free(v37);
  if ( v11 >= 0 )
  {
    if ( v34 )
      Kerb3961Free(v34);
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
    Kerb3961Free(v31);
  if ( v9 )
  {
LABEL_13:
    v20 = *(_QWORD *)(v9 + 56);
    if ( v20 )
      Kerb3961Free(v20);
    v21 = *(_QWORD *)(v9 + 32);
    if ( v21 )
      Kerb3961Free(v21);
    v22 = *(_QWORD *)(v9 + 8);
    if ( v22 )
      Kerb3961Free(v22);
    Kerb3961Free(v9);
  }
  return a2;
}

```

## disassembly

```asm
0x180004390  mov     [rsp-38h+arg_18], rbx
0x180004395  push    rbp
0x180004396  push    rsi
0x180004397  push    rdi
0x180004398  push    r12
0x18000439a  push    r13
0x18000439c  push    r14
0x18000439e  push    r15
0x1800043a0  mov     rbp, rsp
0x1800043a3  sub     rsp, 60h
0x1800043a7  mov     rax, cs:__security_cookie
0x1800043ae  xor     rax, rsp
0x1800043b1  mov     [rbp+var_8], rax
0x1800043b5  mov     rsi, rcx
0x1800043b8  xor     r13d, r13d
0x1800043bb  bswap   r9d
0x1800043be  mov     [rbp+var_10], r13
0x1800043c2  lea     rcx, [rbp+var_28]
0x1800043c6  mov     dword ptr [rbp+var_10], r9d
0x1800043ca  mov     r12, r8
0x1800043cd  mov     rdi, rdx
0x1800043d0  call    ??$make_unique@USimplifiedSpecificKey@Kerb3961@@$$V$0A@@utl@@YA?AV?$unique_ptr@USimplifiedSpecificKey@Kerb3961@@U?$default_delete@USimplifiedSpecificKey@Kerb3961@@@utl@@@0@XZ; utl::make_unique<Kerb3961::SimplifiedSpecificKey,,0>(void)
0x1800043d5  mov     rbx, [rbp+var_28]
0x1800043d9  test    rbx, rbx
0x1800043dc  jnz     short loc_1800043FD
0x1800043de  lea     rcx, aSpecifickey; "specificKey"
0x1800043e5  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x1800043ea  mov     [rdi], r13
0x1800043ed  mov     [rdi+8], r13
0x1800043f1  mov     dword ptr [rdi+10h], 0C0000017h
0x1800043f8  jmp     loc_1800046C5
0x1800043fd  mov     r15d, [rbp+arg_20]
0x180004401  lea     eax, [r15-2]
0x180004405  cmp     eax, 1
0x180004408  ja      loc_18000451D
0x18000440e  lea     rax, [rbp+var_10]
0x180004412  mov     byte ptr [rbp+var_10+4], 99h
0x180004416  lea     r9, [rbp+var_28]
0x18000441a  mov     [rbp+var_20], rax
0x18000441e  mov     r8, r12
0x180004421  mov     [rbp+var_28], 5
0x180004429  lea     rdx, [rbp+var_40]
0x18000442d  mov     rcx, rsi
0x180004430  call    ?DeriveKey@?$SimplifiedCipherSuite@$01@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z; Kerb3961::SimplifiedCipherSuite<2>::DeriveKey(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x180004435  mov     r14d, dword ptr [rbp+var_30]
0x180004439  test    r14d, r14d
0x18000443c  jns     short loc_18000444A
0x18000443e  lea     rcx, aDerivedkey; "derivedKey"
0x180004445  jmp     loc_180004681
0x18000444a  mov     rax, [rsi]
0x18000444d  lea     r8, [rbp+var_40]
0x180004451  lea     rdx, [rbp+var_28]
0x180004455  mov     rcx, rsi
0x180004458  mov     rax, [rax+80h]
0x18000445f  call    _guard_dispatch_icall
0x180004464  mov     rcx, [rbx+8]
0x180004468  mov     r14, rax
0x18000446b  test    rcx, rcx
0x18000446e  jz      short loc_180004475
0x180004470  call    Kerb3961Free
0x180004475  mov     rcx, [r14]
0x180004478  mov     [rbx], rcx
0x18000447b  mov     rax, [r14+8]
0x18000447f  mov     [r14], r13
0x180004482  mov     [rbx+8], rax
0x180004486  mov     eax, [r14+10h]
0x18000448a  mov     [r14+8], r13
0x18000448e  mov     [rbx+10h], eax
0x180004491  mov     dword ptr [r14+10h], 0C0000001h
0x180004499  mov     rcx, [rbp+var_20]
0x18000449d  mov     r14d, [rbx+10h]
0x1800044a1  test    rcx, rcx
0x1800044a4  jz      short loc_1800044AB
0x1800044a6  call    Kerb3961Free
0x1800044ab  test    r14d, r14d
0x1800044ae  jns     short loc_18000450F
0x1800044b0  mov     edx, r14d; char *
0x1800044b3  lea     rcx, aSpecifickeyKcT; "specificKey->Kc = this->RandomToKey(der"...
0x1800044ba  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800044bf  mov     rcx, [rbp+var_38]
0x1800044c3  mov     [rdi], r13
0x1800044c6  mov     [rdi+8], r13
0x1800044ca  mov     [rdi+10h], r14d
0x1800044ce  test    rcx, rcx
0x1800044d1  jz      short loc_1800044D8
0x1800044d3  call    Kerb3961Free
0x1800044d8  mov     rcx, [rbx+38h]
0x1800044dc  test    rcx, rcx
0x1800044df  jz      short loc_1800044E6
0x1800044e1  call    Kerb3961Free
0x1800044e6  mov     rcx, [rbx+20h]
0x1800044ea  test    rcx, rcx
0x1800044ed  jz      short loc_1800044F4
0x1800044ef  call    Kerb3961Free
0x1800044f4  mov     rcx, [rbx+8]
0x1800044f8  test    rcx, rcx
0x1800044fb  jz      short loc_180004502
0x1800044fd  call    Kerb3961Free
0x180004502  mov     rcx, rbx
0x180004505  call    Kerb3961Free
0x18000450a  jmp     loc_1800046C5
0x18000450f  mov     rcx, [rbp+var_38]
0x180004513  test    rcx, rcx
0x180004516  jz      short loc_18000451D
0x180004518  call    Kerb3961Free
0x18000451d  lea     eax, [r15-1]
0x180004521  test    eax, 0FFFFFFFDh
0x180004526  jnz     loc_1800046BA
0x18000452c  lea     rax, [rbp+var_10]
0x180004530  mov     byte ptr [rbp+var_10+4], 0AAh
0x180004534  lea     r9, [rbp+var_28]
0x180004538  mov     [rbp+var_20], rax
0x18000453c  mov     r8, r12
0x18000453f  mov     [rbp+var_28], 5
0x180004547  lea     rdx, [rbp+var_40]
0x18000454b  mov     rcx, rsi
0x18000454e  call    ?DeriveKey@?$SimplifiedCipherSuite@$01@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z; Kerb3961::SimplifiedCipherSuite<2>::DeriveKey(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x180004553  mov     r14d, dword ptr [rbp+var_30]
0x180004557  test    r14d, r14d
0x18000455a  js      loc_18000443E
0x180004560  mov     rax, [rsi]
0x180004563  lea     r8, [rbp+var_40]
0x180004567  lea     rdx, [rbp+var_28]
0x18000456b  mov     rcx, rsi
0x18000456e  mov     rax, [rax+80h]
0x180004575  call    _guard_dispatch_icall
0x18000457a  mov     rcx, [rbx+20h]
0x18000457e  mov     r14, rax
0x180004581  test    rcx, rcx
0x180004584  jz      short loc_18000458B
0x180004586  call    Kerb3961Free
0x18000458b  mov     rcx, [r14]
0x18000458e  mov     r15d, 0C0000001h
0x180004594  mov     [rbx+18h], rcx
0x180004598  mov     rax, [r14+8]
0x18000459c  mov     [r14], r13
0x18000459f  mov     [rbx+20h], rax
0x1800045a3  mov     eax, [r14+10h]
0x1800045a7  mov     [r14+8], r13
0x1800045ab  mov     [rbx+28h], eax
0x1800045ae  mov     [r14+10h], r15d
0x1800045b2  mov     rcx, [rbp+var_20]
0x1800045b6  mov     r14d, [rbx+28h]
0x1800045ba  test    rcx, rcx
0x1800045bd  jz      short loc_1800045C4
0x1800045bf  call    Kerb3961Free
0x1800045c4  test    r14d, r14d
0x1800045c7  jns     short loc_1800045D5
0x1800045c9  lea     rcx, aSpecifickeyKeT; "specificKey->Ke = this->RandomToKey(der"...
0x1800045d0  jmp     loc_180004681
0x1800045d5  mov     rcx, [rbp+var_38]
0x1800045d9  test    rcx, rcx
0x1800045dc  jz      short loc_1800045E3
0x1800045de  call    Kerb3961Free
0x1800045e3  lea     rax, [rbp+var_10]
0x1800045e7  mov     byte ptr [rbp+var_10+4], 55h ; 'U'
0x1800045eb  lea     r9, [rbp+var_28]
0x1800045ef  mov     [rbp+var_20], rax
0x1800045f3  mov     r8, r12
0x1800045f6  mov     [rbp+var_28], 5
0x1800045fe  lea     rdx, [rbp+var_40]
0x180004602  mov     rcx, rsi
0x180004605  call    ?DeriveKey@?$SimplifiedCipherSuite@$01@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z; Kerb3961::SimplifiedCipherSuite<2>::DeriveKey(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x18000460a  mov     r14d, dword ptr [rbp+var_30]
0x18000460e  test    r14d, r14d
0x180004611  js      loc_18000443E
0x180004617  mov     rax, [rsi]
0x18000461a  lea     r8, [rbp+var_40]
0x18000461e  lea     rdx, [rbp+var_28]
0x180004622  mov     rcx, rsi
0x180004625  mov     rax, [rax+80h]
0x18000462c  call    _guard_dispatch_icall
0x180004631  mov     rcx, [rbx+38h]
0x180004635  mov     r14, rax
0x180004638  test    rcx, rcx
0x18000463b  jz      short loc_180004642
0x18000463d  call    Kerb3961Free
0x180004642  mov     rcx, [r14]
0x180004645  mov     [rbx+30h], rcx
0x180004649  mov     rax, [r14+8]
0x18000464d  mov     [r14], r13
0x180004650  mov     [rbx+38h], rax
0x180004654  mov     eax, [r14+10h]
0x180004658  mov     [r14+8], r13
0x18000465c  mov     [rbx+40h], eax
0x18000465f  mov     [r14+10h], r15d
0x180004663  mov     rcx, [rbp+var_20]
0x180004667  mov     r14d, [rbx+40h]
0x18000466b  test    rcx, rcx
0x18000466e  jz      short loc_180004675
0x180004670  call    Kerb3961Free
0x180004675  test    r14d, r14d
0x180004678  jns     short loc_1800046AC
0x18000467a  lea     rcx, aSpecifickeyKiT; "specificKey->Ki = this->RandomToKey(der"...
0x180004681  mov     edx, r14d; char *
0x180004684  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180004689  mov     rcx, [rbp+var_38]
0x18000468d  mov     [rdi], r13
0x180004690  mov     [rdi+8], r13
0x180004694  mov     [rdi+10h], r14d
0x180004698  test    rcx, rcx
0x18000469b  jz      short loc_1800046A2
0x18000469d  call    Kerb3961Free
0x1800046a2  test    rbx, rbx
0x1800046a5  jz      short loc_1800046C5
0x1800046a7  jmp     loc_1800044D8
0x1800046ac  mov     rcx, [rbp+var_38]
0x1800046b0  test    rcx, rcx
0x1800046b3  jz      short loc_1800046BA
0x1800046b5  call    Kerb3961Free
0x1800046ba  mov     [rdi], rsi
0x1800046bd  mov     [rdi+8], rbx
0x1800046c1  mov     [rdi+10h], r13d
0x1800046c5  mov     rax, rdi
0x1800046c8  mov     rcx, [rbp+var_8]
0x1800046cc  xor     rcx, rsp; StackCookie
0x1800046cf  call    __security_check_cookie
0x1800046d4  mov     rbx, [rsp+60h+arg_18]
0x1800046dc  add     rsp, 60h
0x1800046e0  pop     r15
0x1800046e2  pop     r14
0x1800046e4  pop     r13
0x1800046e6  pop     r12
0x1800046e8  pop     rdi
0x1800046e9  pop     rsi
0x1800046ea  pop     rbp
0x1800046eb  retn
```
