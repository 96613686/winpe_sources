# Kerb3961::SSPICipherSuite<1,1,1>::SSPIUnwrap(Kerb3961::WrapBuffers const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,bool,bool)

- ea: `0x180010460`
- end: `0x180010757`
- name: `?SSPIUnwrap@?$SSPICipherSuite@$00$00$00@Kerb3961@@EEAA?AU?$ReturnType@UVerifyMICResult@Kerb3961@@$1??$SingleGetter@UVerifyMICResult@Kerb3961@@$0M@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UVerifyMICResult@Kerb3961@@$0M@@2@YAAEAU32@AEAU12@@Z@2@AEBUWrapBuffers@2@AEBUReadOnlyBinary@2@11_N2@Z`
- size: `759`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180001ff4`
- `0x1800037e0`
- `0x180003a38`
- `0x180006af0`
- `0x180010460`
- `0x180011760`
- `0x1800118cc`
- `0x180011ab8`
- `0x180011b40`
- `0x180012200`
- `0x180012240`
- `0x180012300`

## string_xrefs

- `0x1800104c9`: `combinedBuffer`
- `0x180010514`: `completeWrapToken`
- `0x1800106e1`: `result.outputMessage.length == effectiveInput.length + ((compatFixes == GssApiCompatibilityFixes::RC4) ? trailerBuffer.length : 0)`

## pseudocode

```c
__int64 __fastcall Kerb3961::SSPICipherSuite<1,1,1>::SSPIUnwrap(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        __int64 a4,
        _QWORD *a5,
        __int64 a6,
        char a7,
        char a8)
{
  int v12; // r8d
  int v13; // ebx
  char *v14; // rsi
  int v15; // r8d
  int v16; // ebx
  const struct std::nothrow_t *v17; // rdx
  _QWORD *v18; // rax
  __int64 v19; // rbx
  char *v20; // rax
  const unsigned __int16 *v21; // rdx
  int v22; // r8d
  __int64 v23; // rbx
  char *v24; // rsi
  __int64 v25; // r14
  char *v26; // rcx
  __int64 v28; // [rsp+48h] [rbp-B8h]
  char *Src; // [rsp+50h] [rbp-B0h]
  int v30; // [rsp+58h] [rbp-A8h]
  __int64 v31; // [rsp+60h] [rbp-A0h]
  int v32; // [rsp+68h] [rbp-98h]
  char v33; // [rsp+6Ch] [rbp-94h]
  char v34[8]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v35; // [rsp+78h] [rbp-88h]
  char *v36; // [rsp+80h] [rbp-80h]
  char v37[8]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v38; // [rsp+90h] [rbp-70h]
  char *v39; // [rsp+98h] [rbp-68h]
  __int64 v40; // [rsp+A0h] [rbp-60h]
  char v41[8]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v42; // [rsp+B0h] [rbp-50h]
  _QWORD v43[4]; // [rsp+D0h] [rbp-30h] BYREF

  v40 = a6;
  Kerb3961::SSPICipherSuite<1,1,0>::CoalesceEncryptedWrapBuffers(v34, a3);
  v13 = (int)v36;
  if ( (int)v36 < 0 )
  {
    Kerb3961::Logging::Verify::StatusFailed(
      (Kerb3961::Logging::Verify *)"combinedBuffer",
      (const char *)(unsigned int)v36,
      v12);
    *(_OWORD *)a2 = 0;
    *(_DWORD *)(a2 + 12) = v13;
    goto LABEL_31;
  }
  if ( (_DWORD)v36 == 255 )
    v14 = (char *)a3[1];
  else
    v14 = v34;
  Kerb3961::Concatenate(v37, a4, v14, a5);
  v16 = (int)v39;
  if ( (int)v39 < 0 )
  {
    Kerb3961::Logging::Verify::StatusFailed(
      (Kerb3961::Logging::Verify *)"completeWrapToken",
      (const char *)(unsigned int)v39,
      v15);
    *(_OWORD *)a2 = 0;
    *(_DWORD *)(a2 + 12) = v16;
    goto LABEL_29;
  }
  v43[0] = &utl::_FuncEmpty<Kerb3961::ReturnType<Kerb3961::OwnedBinary,&Kerb3961::ResultBlock const & Kerb3961::SingleGetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary const &),&Kerb3961::ResultBlock & Kerb3961::SingleSetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary &)>,Kerb3961::ReadOnlyBinary const &>::`vftable';
  utl::_FuncEmpty<Kerb3961::ReturnType<Kerb3961::OwnedBinary,&Kerb3961::ResultBlock const & Kerb3961::SingleGetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary const &),&Kerb3961::ResultBlock & Kerb3961::SingleSetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary &)>,Kerb3961::ReadOnlyBinary const &>::_Destroy(v43);
  v18 = operator new[](0x20u, v17);
  if ( v18 )
  {
    v43[1] = v18;
    v43[0] = ___7___FuncBig_V_lambda_1___P___SSPIUnwrap___SSPICipherSuite__00_00_00_Kerb3961__EEAA_AU__ReturnType_UVerifyMICResult_Kerb3961___1___SingleGetter_UVerifyMICResult_Kerb3961___0M__2_YAAEBUResultBlock_2_AEBU12__Z_1___SingleSetter_UVerifyMICResult_Kerb3961___0M__2_YAAEAU32_AEAU12__Z_4_AEBUWrapBuffers_4_AEBUReadOnlyBinary_4_11_N2_Z_U__ReturnType_UOwnedBinary_Kerb3961___1___SingleGetter_UOwnedBinary_Kerb3961___0BA__2_YAAEBUResultBlock_2_AEBU12__Z_1___SingleSetter_UOwnedBinary_Kerb3961___0BA__2_YAAEAU32_AEAU12__Z_4_AEBU74__utl__6B_;
    *v18 = a1;
    v18[1] = a3;
    v18[2] = a5;
    v18[3] = v14;
  }
  else
  {
    v43[0] = &utl::_FuncEmpty<Kerb3961::ReturnType<Kerb3961::OwnedBinary,&Kerb3961::ResultBlock const & Kerb3961::SingleGetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary const &),&Kerb3961::ResultBlock & Kerb3961::SingleSetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary &)>,Kerb3961::ReadOnlyBinary const &>::`vftable';
  }
  v19 = (*(__int64 (__fastcall **)(__int64, char *, char *, _QWORD *, __int64, char, char))(*(_QWORD *)a1 + 360LL))(
          a1,
          v41,
          v37,
          v43,
          v40,
          a7,
          a8);
  v28 = *(_QWORD *)v19;
  v20 = *(char **)(v19 + 8);
  *(_QWORD *)v19 = 0;
  Src = v20;
  LODWORD(v20) = *(_DWORD *)(v19 + 16);
  *(_QWORD *)(v19 + 8) = 0;
  v30 = (int)v20;
  *(_DWORD *)(v19 + 16) = -1073741823;
  v31 = *(_QWORD *)(v19 + 24);
  v32 = *(_DWORD *)(v19 + 32);
  v33 = *(_BYTE *)(v19 + 36);
  if ( v42 )
    Kerb3961Free(v42);
  (*(void (__fastcall **)(_QWORD *))v43[0])(v43);
  if ( v30 < 0 )
  {
    Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)"result", (const char *)(unsigned int)v30, v22);
    *(_OWORD *)a2 = 0;
    *(_DWORD *)(a2 + 12) = v30;
    goto LABEL_27;
  }
  if ( !v33 )
  {
    if ( v32 )
      Kerb3961::ConsistencyFail((Kerb3961 *)L"GSS-API cannot have a QOP when conf = false", v21);
    v32 = -2147483647;
  }
  if ( v28 != *a5 + *(_QWORD *)v14 )
  {
    Kerb3961::Logging::Verify::ConditionFailed(
      (Kerb3961::Logging::Verify *)"result.outputMessage.length == effectiveInput.length + ((compatFixes == GssApiCompati"
                                   "bilityFixes::RC4) ? trailerBuffer.length : 0)",
      (const char *)v21);
    *(_OWORD *)a2 = 0;
    *(_DWORD *)(a2 + 12) = -2146893041;
LABEL_27:
    v26 = Src;
    if ( !Src )
      goto LABEL_29;
    goto LABEL_28;
  }
  v23 = a3[1];
  v24 = Src;
  v25 = v23 + 24LL * *a3;
  if ( v23 != v25 )
  {
    do
    {
      if ( *(_BYTE *)(v23 + 16) )
      {
        memmove(*(void **)(v23 + 8), v24, *(_QWORD *)v23);
        v24 += *(_QWORD *)v23;
      }
      v23 += 24;
    }
    while ( v23 != v25 );
    v24 = Src;
  }
  *(_QWORD *)a2 = v31;
  *(_DWORD *)(a2 + 8) = v32;
  *(_DWORD *)(a2 + 12) = 0;
  if ( !v24 )
    goto LABEL_29;
  v26 = v24;
LABEL_28:
  Kerb3961Free(v26);
LABEL_29:
  if ( v38 )
    Kerb3961Free(v38);
LABEL_31:
  if ( v35 )
    Kerb3961Free(v35);
  return a2;
}

```

## disassembly

```asm
0x180010460  push    rbp
0x180010462  push    rbx
0x180010463  push    rsi
0x180010464  push    rdi
0x180010465  push    r12
0x180010467  push    r13
0x180010469  push    r14
0x18001046b  push    r15
0x18001046d  lea     rbp, [rsp-8]
0x180010472  sub     rsp, 108h
0x180010479  mov     rax, cs:__security_cookie
0x180010480  xor     rax, rsp
0x180010483  mov     [rbp+40h+var_50], rax
0x180010487  mov     rax, [rbp+40h+arg_28]
0x18001048b  mov     rdi, rdx
0x18001048e  mov     r15, [rbp+40h+arg_20]
0x180010492  mov     r12, rcx
0x180010495  mov     [rbp+40h+var_A0], rax
0x180010499  lea     rcx, [rsp+140h+var_D0]
0x18001049e  mov     al, [rbp+40h+arg_30]
0x1800104a4  mov     rdx, r8
0x1800104a7  mov     [rsp+140h+var_FF], al
0x1800104ab  mov     r13, r9
0x1800104ae  mov     al, [rbp+40h+arg_38]
0x1800104b4  mov     r14, r8
0x1800104b7  mov     [rsp+140h+var_100], al
0x1800104bb  call    ?CoalesceEncryptedWrapBuffers@?$SSPICipherSuite@$00$00$0A@@Kerb3961@@KA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUWrapBuffers@2@@Z; Kerb3961::SSPICipherSuite<1,1,0>::CoalesceEncryptedWrapBuffers(Kerb3961::WrapBuffers const &)
0x1800104c0  mov     ebx, dword ptr [rbp+40h+var_C0]
0x1800104c3  test    ebx, ebx
0x1800104c5  jns     short loc_1800104E3
0x1800104c7  mov     edx, ebx; char *
0x1800104c9  lea     rcx, aCombinedbuffer; "combinedBuffer"
0x1800104d0  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800104d5  xorps   xmm0, xmm0
0x1800104d8  movups  xmmword ptr [rdi], xmm0
0x1800104db  mov     [rdi+0Ch], ebx
0x1800104de  jmp     loc_180010717
0x1800104e3  cmp     ebx, 0FFh
0x1800104e9  jnz     short loc_1800104F1
0x1800104eb  mov     rsi, [r14+8]
0x1800104ef  jmp     short loc_1800104F6
0x1800104f1  lea     rsi, [rsp+140h+var_D0]
0x1800104f6  mov     r9, r15
0x1800104f9  lea     rcx, [rbp+40h+var_B8]
0x1800104fd  mov     r8, rsi
0x180010500  mov     rdx, r13
0x180010503  call    ?Concatenate@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@00@Z; Kerb3961::Concatenate(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x180010508  mov     ebx, dword ptr [rbp+40h+var_A8]
0x18001050b  xor     r13d, r13d
0x18001050e  test    ebx, ebx
0x180010510  jns     short loc_18001052E
0x180010512  mov     edx, ebx; char *
0x180010514  lea     rcx, aCompletewrapto; "completeWrapToken"
0x18001051b  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180010520  xorps   xmm0, xmm0
0x180010523  movups  xmmword ptr [rdi], xmm0
0x180010526  mov     [rdi+0Ch], ebx
0x180010529  jmp     loc_180010709
0x18001052e  xorps   xmm0, xmm0
0x180010531  mov     [rsp+140h+var_D4], r13d
0x180010536  lea     rbx, ??_7?$_FuncEmpty@U?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@Kerb3961@@AEBUReadOnlyBinary@2@@utl@@6B@; const utl::_FuncEmpty<Kerb3961::ReturnType<Kerb3961::OwnedBinary,&Kerb3961::SingleGetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary const &),&Kerb3961::SingleSetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary &)>,Kerb3961::ReadOnlyBinary const &>::`vftable'
0x18001053d  mov     [rsp+140h+var_F8], r13
0x180010542  lea     rcx, [rbp+40h+var_70]
0x180010546  mov     [rbp+40h+var_70], rbx
0x18001054a  movdqu  xmmword ptr [rsp+140h+var_E8+4], xmm0
0x180010550  mov     [rsp+140h+Src], r13
0x180010555  mov     dword ptr [rsp+140h+var_E8], 0C0000001h
0x18001055d  call    ?_Destroy@?$_FuncEmpty@U?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@Kerb3961@@AEBUReadOnlyBinary@2@@utl@@UEAAXXZ; utl::_FuncEmpty<Kerb3961::ReturnType<Kerb3961::OwnedBinary,&Kerb3961::SingleGetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary const &),&Kerb3961::SingleSetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary &)>,Kerb3961::ReadOnlyBinary const &>::_Destroy(void)
0x180010562  mov     ecx, 20h ; ' '; unsigned __int64
0x180010567  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001056c  test    rax, rax
0x18001056f  jnz     short loc_180010577
0x180010571  mov     [rbp+40h+var_70], rbx
0x180010575  jmp     short loc_180010595
0x180010577  mov     [rbp+40h+var_68], rax
0x18001057b  lea     rcx, ??_7?$_FuncBig@V_lambda_1_@?P@??SSPIUnwrap@?$SSPICipherSuite@$00$00$00@Kerb3961@@EEAA?AU?$ReturnType@UVerifyMICResult@Kerb3961@@$1??$SingleGetter@UVerifyMICResult@Kerb3961@@$0M@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UVerifyMICResult@Kerb3961@@$0M@@2@YAAEAU32@AEAU12@@Z@4@AEBUWrapBuffers@4@AEBUReadOnlyBinary@4@11_N2@Z@U?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@4@AEBU74@@utl@@6B@; const utl::_FuncBig<`Kerb3961::SSPICipherSuite<1,1,1>::SSPIUnwrap(Kerb3961::WrapBuffers const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,bool,bool)'::`15'::_lambda_1_,Kerb3961::ReturnType<Kerb3961::OwnedBinary,&Kerb3961::SingleGetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary const &),&Kerb3961::SingleSetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary &)>,Kerb3961::ReadOnlyBinary const &>::`vftable'
0x180010582  mov     [rbp+40h+var_70], rcx
0x180010586  mov     [rax], r12
0x180010589  mov     [rax+8], r14
0x18001058d  mov     [rax+10h], r15
0x180010591  mov     [rax+18h], rsi
0x180010595  mov     cl, [rsp+140h+var_100]
0x180010599  lea     r9, [rbp+40h+var_70]
0x18001059d  mov     rax, [r12]
0x1800105a1  lea     r8, [rbp+40h+var_B8]
0x1800105a5  mov     [rsp+140h+var_110], cl
0x1800105a9  lea     rdx, [rbp+40h+var_98]
0x1800105ad  mov     cl, [rsp+140h+var_FF]
0x1800105b1  mov     [rsp+140h+var_118], cl
0x1800105b5  mov     rcx, [rbp+40h+var_A0]
0x1800105b9  mov     rax, [rax+168h]
0x1800105c0  mov     [rsp+140h+var_120], rcx
0x1800105c5  mov     rcx, r12
0x1800105c8  call    _guard_dispatch_icall
0x1800105cd  mov     rcx, [rsp+140h+Src]
0x1800105d2  mov     rbx, rax
0x1800105d5  test    rcx, rcx
0x1800105d8  jz      short loc_1800105DF
0x1800105da  call    Kerb3961Free
0x1800105df  mov     rax, [rbx]
0x1800105e2  mov     [rsp+140h+var_F8], rax
0x1800105e7  mov     rax, [rbx+8]
0x1800105eb  mov     [rbx], r13
0x1800105ee  mov     [rsp+140h+Src], rax
0x1800105f3  mov     eax, [rbx+10h]
0x1800105f6  mov     [rbx+8], r13
0x1800105fa  mov     dword ptr [rsp+140h+var_E8], eax
0x1800105fe  mov     dword ptr [rbx+10h], 0C0000001h
0x180010605  mov     rax, [rbx+18h]
0x180010609  mov     rcx, [rbp+40h+var_90]
0x18001060d  mov     [rsp+60h], rax
0x180010612  mov     eax, [rbx+20h]
0x180010615  mov     [rsp+68h], eax
0x180010619  mov     al, [rbx+24h]
0x18001061c  mov     byte ptr [rsp+140h+var_D4], al
0x180010620  test    rcx, rcx
0x180010623  jz      short loc_18001062A
0x180010625  call    Kerb3961Free
0x18001062a  mov     rax, [rbp+40h+var_70]
0x18001062e  lea     rcx, [rbp+40h+var_70]
0x180010632  mov     rax, [rax]
0x180010635  call    _guard_dispatch_icall
0x18001063a  mov     ebx, dword ptr [rsp+140h+var_E8]
0x18001063e  test    ebx, ebx
0x180010640  jns     short loc_18001065E
0x180010642  mov     edx, ebx; char *
0x180010644  lea     rcx, aResult; "result"
0x18001064b  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180010650  xorps   xmm0, xmm0
0x180010653  movups  xmmword ptr [rdi], xmm0
0x180010656  mov     [rdi+0Ch], ebx
0x180010659  jmp     loc_1800106FA
0x18001065e  cmp     byte ptr [rsp+140h+var_D4], r13b
0x180010663  jnz     short loc_180010678
0x180010665  cmp     [rsp+68h], r13d
0x18001066a  jnz     loc_18001074A
0x180010670  mov     dword ptr [rsp+68h], 80000001h
0x180010678  mov     rax, [rsi]
0x18001067b  add     rax, [r15]
0x18001067e  cmp     [rsp+140h+var_F8], rax
0x180010683  jnz     short loc_1800106E1
0x180010685  mov     rax, [r14]
0x180010688  mov     rbx, [r14+8]
0x18001068c  mov     rsi, [rsp+140h+Src]
0x180010691  lea     rcx, [rax+rax*2]
0x180010695  lea     r14, [rbx+rcx*8]
0x180010699  cmp     rbx, r14
0x18001069c  jz      short loc_1800106C4
0x18001069e  cmp     [rbx+10h], r13b
0x1800106a2  jz      short loc_1800106B6
0x1800106a4  mov     r8, [rbx]; Size
0x1800106a7  mov     rdx, rsi; Src
0x1800106aa  mov     rcx, [rbx+8]; void *
0x1800106ae  call    memmove
0x1800106b3  add     rsi, [rbx]
0x1800106b6  add     rbx, 18h
0x1800106ba  cmp     rbx, r14
0x1800106bd  jnz     short loc_18001069E
0x1800106bf  mov     rsi, [rsp+140h+Src]
0x1800106c4  mov     rax, [rsp+60h]
0x1800106c9  mov     [rdi], rax
0x1800106cc  mov     eax, [rsp+68h]
0x1800106d0  mov     [rdi+8], eax
0x1800106d3  mov     [rdi+0Ch], r13d
0x1800106d7  test    rsi, rsi
0x1800106da  jz      short loc_180010709
0x1800106dc  mov     rcx, rsi
0x1800106df  jmp     short loc_180010704
0x1800106e1  lea     rcx, aResultOutputme; "result.outputMessage.length == effectiv"...
0x1800106e8  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x1800106ed  xorps   xmm0, xmm0
0x1800106f0  movups  xmmword ptr [rdi], xmm0
0x1800106f3  mov     dword ptr [rdi+0Ch], 8009030Fh
0x1800106fa  mov     rcx, [rsp+140h+Src]
0x1800106ff  test    rcx, rcx
0x180010702  jz      short loc_180010709
0x180010704  call    Kerb3961Free
0x180010709  mov     rcx, [rbp+40h+var_B0]
0x18001070d  test    rcx, rcx
0x180010710  jz      short loc_180010717
0x180010712  call    Kerb3961Free
0x180010717  mov     rcx, [rsp+140h+var_C8]
0x18001071c  test    rcx, rcx
0x18001071f  jz      short loc_180010726
0x180010721  call    Kerb3961Free
0x180010726  mov     rax, rdi
0x180010729  mov     rcx, [rbp+40h+var_50]
0x18001072d  xor     rcx, rsp; StackCookie
0x180010730  call    __security_check_cookie
0x180010735  add     rsp, 108h
0x18001073c  pop     r15
0x18001073e  pop     r14
0x180010740  pop     r13
0x180010742  pop     r12
0x180010744  pop     rdi
0x180010745  pop     rsi
0x180010746  pop     rbx
0x180010747  pop     rbp
0x180010748  retn
0x18001074a  lea     rcx, aGssApiCannotHa; "GSS-API cannot have a QOP when conf = f"...
0x180010751  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
```
