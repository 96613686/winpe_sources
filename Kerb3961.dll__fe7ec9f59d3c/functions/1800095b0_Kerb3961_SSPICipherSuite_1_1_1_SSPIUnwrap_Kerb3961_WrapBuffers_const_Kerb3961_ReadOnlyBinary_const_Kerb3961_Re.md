# Kerb3961::SSPICipherSuite<1,1,1>::SSPIUnwrap(Kerb3961::WrapBuffers const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,bool,bool)

- ea: `0x1800095b0`
- end: `0x1800098b0`
- name: `?SSPIUnwrap@?$SSPICipherSuite@$00$00$00@Kerb3961@@EEAA?AU?$ReturnType@UVerifyMICResult@Kerb3961@@$1??$SingleGetter@UVerifyMICResult@Kerb3961@@$0M@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UVerifyMICResult@Kerb3961@@$0M@@2@YAAEAU32@AEAU12@@Z@2@AEBUWrapBuffers@2@AEBUReadOnlyBinary@2@11_N2@Z`
- size: `768`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *, __int64, _QWORD *, __int64, char, char)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001d40`
- `0x180001d64`
- `0x1800029bc`
- `0x180002c64`
- `0x180002fc0`
- `0x1800033f4`
- `0x180004cf4`
- `0x180006ee0`
- `0x1800095b0`
- `0x18000a040`
- `0x18001d360`
- `0x18001e010`

## string_xrefs

- `0x180009619`: `combinedBuffer`
- `0x180009664`: `completeWrapToken`
- `0x180009835`: `result.outputMessage.length == effectiveInput.length + ((compatFixes == GssApiCompatibilityFixes::RC4) ? trailerBuffer.length : 0)`

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
  void *v26; // rcx
  __int64 v28; // [rsp+48h] [rbp-B8h]
  char *Src; // [rsp+50h] [rbp-B0h]
  int v30; // [rsp+58h] [rbp-A8h]
  __int64 v31; // [rsp+60h] [rbp-A0h]
  int v32; // [rsp+68h] [rbp-98h]
  char v33; // [rsp+6Ch] [rbp-94h]
  char v34[8]; // [rsp+70h] [rbp-90h] BYREF
  void *v35; // [rsp+78h] [rbp-88h]
  char *v36; // [rsp+80h] [rbp-80h]
  char v37[8]; // [rsp+88h] [rbp-78h] BYREF
  void *v38; // [rsp+90h] [rbp-70h]
  char *v39; // [rsp+98h] [rbp-68h]
  __int64 v40; // [rsp+A0h] [rbp-60h]
  char v41[8]; // [rsp+A8h] [rbp-58h] BYREF
  void *v42; // [rsp+B0h] [rbp-50h]
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
  v18 = operator new(0x20u, v17);
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
    operator delete(v42, 0);
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
  if ( v28 != *(_QWORD *)v14 + *a5 )
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
        memcpy_0(*(void **)(v23 + 8), v24, *(_QWORD *)v23);
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
  operator delete(v26, 0);
LABEL_29:
  if ( v38 )
    operator delete(v38, 0);
LABEL_31:
  if ( v35 )
    operator delete(v35, 0);
  return a2;
}

```

## disassembly

```asm
0x1800095b0  push    rbp
0x1800095b2  push    rbx
0x1800095b3  push    rsi
0x1800095b4  push    rdi
0x1800095b5  push    r12
0x1800095b7  push    r13
0x1800095b9  push    r14
0x1800095bb  push    r15
0x1800095bd  lea     rbp, [rsp-8]
0x1800095c2  sub     rsp, 108h
0x1800095c9  mov     rax, cs:__security_cookie
0x1800095d0  xor     rax, rsp
0x1800095d3  mov     [rbp+40h+var_50], rax
0x1800095d7  mov     rax, [rbp+40h+arg_28]
0x1800095db  mov     rdi, rdx
0x1800095de  mov     r15, [rbp+40h+arg_20]
0x1800095e2  mov     r12, rcx
0x1800095e5  mov     [rbp+40h+var_A0], rax
0x1800095e9  lea     rcx, [rsp+140h+var_D0]
0x1800095ee  mov     al, [rbp+40h+arg_30]
0x1800095f4  mov     rdx, r8
0x1800095f7  mov     [rsp+140h+var_FF], al
0x1800095fb  mov     r13, r9
0x1800095fe  mov     al, [rbp+40h+arg_38]
0x180009604  mov     r14, r8
0x180009607  mov     [rsp+140h+var_100], al
0x18000960b  call    ?CoalesceEncryptedWrapBuffers@?$SSPICipherSuite@$00$00$0A@@Kerb3961@@KA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUWrapBuffers@2@@Z; Kerb3961::SSPICipherSuite<1,1,0>::CoalesceEncryptedWrapBuffers(Kerb3961::WrapBuffers const &)
0x180009610  mov     ebx, dword ptr [rbp+40h+var_C0]
0x180009613  test    ebx, ebx
0x180009615  jns     short loc_180009633
0x180009617  mov     edx, ebx; char *
0x180009619  lea     rcx, aCombinedbuffer; "combinedBuffer"
0x180009620  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180009625  xorps   xmm0, xmm0
0x180009628  movups  xmmword ptr [rdi], xmm0
0x18000962b  mov     [rdi+0Ch], ebx
0x18000962e  jmp     loc_18000986F
0x180009633  cmp     ebx, 0FFh
0x180009639  jnz     short loc_180009641
0x18000963b  mov     rsi, [r14+8]
0x18000963f  jmp     short loc_180009646
0x180009641  lea     rsi, [rsp+140h+var_D0]
0x180009646  mov     r9, r15
0x180009649  lea     rcx, [rbp+40h+var_B8]
0x18000964d  mov     r8, rsi
0x180009650  mov     rdx, r13
0x180009653  call    ?Concatenate@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@00@Z; Kerb3961::Concatenate(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x180009658  mov     ebx, dword ptr [rbp+40h+var_A8]
0x18000965b  xor     r13d, r13d
0x18000965e  test    ebx, ebx
0x180009660  jns     short loc_18000967E
0x180009662  mov     edx, ebx; char *
0x180009664  lea     rcx, aCompletewrapto; "completeWrapToken"
0x18000966b  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180009670  xorps   xmm0, xmm0
0x180009673  movups  xmmword ptr [rdi], xmm0
0x180009676  mov     [rdi+0Ch], ebx
0x180009679  jmp     loc_18000985F
0x18000967e  xorps   xmm0, xmm0
0x180009681  mov     [rsp+140h+var_D4], r13d
0x180009686  lea     rbx, ??_7?$_FuncEmpty@U?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@Kerb3961@@AEBUReadOnlyBinary@2@@utl@@6B@; const utl::_FuncEmpty<Kerb3961::ReturnType<Kerb3961::OwnedBinary,&Kerb3961::SingleGetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary const &),&Kerb3961::SingleSetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary &)>,Kerb3961::ReadOnlyBinary const &>::`vftable'
0x18000968d  mov     [rsp+140h+var_F8], r13
0x180009692  lea     rcx, [rbp+40h+var_70]
0x180009696  mov     [rbp+40h+var_70], rbx
0x18000969a  movdqu  xmmword ptr [rsp+140h+var_E8+4], xmm0
0x1800096a0  mov     [rsp+140h+Src], r13
0x1800096a5  mov     dword ptr [rsp+140h+var_E8], 0C0000001h
0x1800096ad  call    ?_Destroy@?$_FuncEmpty@U?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@Kerb3961@@AEBUReadOnlyBinary@2@@utl@@UEAAXXZ; utl::_FuncEmpty<Kerb3961::ReturnType<Kerb3961::OwnedBinary,&Kerb3961::SingleGetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary const &),&Kerb3961::SingleSetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary &)>,Kerb3961::ReadOnlyBinary const &>::_Destroy(void)
0x1800096b2  mov     ecx, 20h ; ' '; unsigned __int64
0x1800096b7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800096bc  test    rax, rax
0x1800096bf  jnz     short loc_1800096C7
0x1800096c1  mov     [rbp+40h+var_70], rbx
0x1800096c5  jmp     short loc_1800096E5
0x1800096c7  mov     [rbp+40h+var_68], rax
0x1800096cb  lea     rcx, ??_7?$_FuncBig@V_lambda_1_@?P@??SSPIUnwrap@?$SSPICipherSuite@$00$00$00@Kerb3961@@EEAA?AU?$ReturnType@UVerifyMICResult@Kerb3961@@$1??$SingleGetter@UVerifyMICResult@Kerb3961@@$0M@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UVerifyMICResult@Kerb3961@@$0M@@2@YAAEAU32@AEAU12@@Z@4@AEBUWrapBuffers@4@AEBUReadOnlyBinary@4@11_N2@Z@U?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@4@AEBU74@@utl@@6B@; const utl::_FuncBig<`Kerb3961::SSPICipherSuite<1,1,1>::SSPIUnwrap(Kerb3961::WrapBuffers const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,bool,bool)'::`15'::_lambda_1_,Kerb3961::ReturnType<Kerb3961::OwnedBinary,&Kerb3961::SingleGetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary const &),&Kerb3961::SingleSetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary &)>,Kerb3961::ReadOnlyBinary const &>::`vftable'
0x1800096d2  mov     [rbp+40h+var_70], rcx
0x1800096d6  mov     [rax], r12
0x1800096d9  mov     [rax+8], r14
0x1800096dd  mov     [rax+10h], r15
0x1800096e1  mov     [rax+18h], rsi
0x1800096e5  mov     cl, [rsp+140h+var_100]
0x1800096e9  lea     r9, [rbp+40h+var_70]
0x1800096ed  mov     rax, [r12]
0x1800096f1  lea     r8, [rbp+40h+var_B8]
0x1800096f5  mov     [rsp+140h+var_110], cl
0x1800096f9  lea     rdx, [rbp+40h+var_98]
0x1800096fd  mov     cl, [rsp+140h+var_FF]
0x180009701  mov     [rsp+140h+var_118], cl
0x180009705  mov     rcx, [rbp+40h+var_A0]
0x180009709  mov     rax, [rax+168h]
0x180009710  mov     [rsp+140h+var_120], rcx
0x180009715  mov     rcx, r12
0x180009718  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000971d  mov     rcx, [rsp+140h+Src]; void *
0x180009722  mov     rbx, rax
0x180009725  test    rcx, rcx
0x180009728  jz      short loc_180009731
0x18000972a  xor     edx, edx; struct std::nothrow_t *
0x18000972c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180009731  mov     rax, [rbx]
0x180009734  mov     [rsp+140h+var_F8], rax
0x180009739  mov     rax, [rbx+8]
0x18000973d  mov     [rbx], r13
0x180009740  mov     [rsp+140h+Src], rax
0x180009745  mov     eax, [rbx+10h]
0x180009748  mov     [rbx+8], r13
0x18000974c  mov     dword ptr [rsp+140h+var_E8], eax
0x180009750  mov     dword ptr [rbx+10h], 0C0000001h
0x180009757  mov     rax, [rbx+18h]
0x18000975b  mov     rcx, [rbp+40h+var_90]; void *
0x18000975f  mov     [rsp+60h], rax
0x180009764  mov     eax, [rbx+20h]
0x180009767  mov     [rsp+68h], eax
0x18000976b  mov     al, [rbx+24h]
0x18000976e  mov     byte ptr [rsp+140h+var_D4], al
0x180009772  test    rcx, rcx
0x180009775  jz      short loc_18000977E
0x180009777  xor     edx, edx; struct std::nothrow_t *
0x180009779  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000977e  mov     rax, [rbp+40h+var_70]
0x180009782  lea     rcx, [rbp+40h+var_70]
0x180009786  mov     rax, [rax]
0x180009789  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000978e  mov     ebx, dword ptr [rsp+140h+var_E8]
0x180009792  test    ebx, ebx
0x180009794  jns     short loc_1800097B2
0x180009796  mov     edx, ebx; char *
0x180009798  lea     rcx, aResult; "result"
0x18000979f  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800097a4  xorps   xmm0, xmm0
0x1800097a7  movups  xmmword ptr [rdi], xmm0
0x1800097aa  mov     [rdi+0Ch], ebx
0x1800097ad  jmp     loc_18000984E
0x1800097b2  cmp     byte ptr [rsp+140h+var_D4], r13b
0x1800097b7  jnz     short loc_1800097CC
0x1800097b9  cmp     [rsp+68h], r13d
0x1800097be  jnz     loc_1800098A3
0x1800097c4  mov     dword ptr [rsp+68h], 80000001h
0x1800097cc  mov     rax, [r15]
0x1800097cf  add     rax, [rsi]
0x1800097d2  cmp     [rsp+140h+var_F8], rax
0x1800097d7  jnz     short loc_180009835
0x1800097d9  mov     rax, [r14]
0x1800097dc  mov     rbx, [r14+8]
0x1800097e0  mov     rsi, [rsp+140h+Src]
0x1800097e5  lea     rcx, [rax+rax*2]
0x1800097e9  lea     r14, [rbx+rcx*8]
0x1800097ed  cmp     rbx, r14
0x1800097f0  jz      short loc_180009818
0x1800097f2  cmp     [rbx+10h], r13b
0x1800097f6  jz      short loc_18000980A
0x1800097f8  mov     r8, [rbx]; Size
0x1800097fb  mov     rdx, rsi; Src
0x1800097fe  mov     rcx, [rbx+8]; void *
0x180009802  call    memcpy_0
0x180009807  add     rsi, [rbx]
0x18000980a  add     rbx, 18h
0x18000980e  cmp     rbx, r14
0x180009811  jnz     short loc_1800097F2
0x180009813  mov     rsi, [rsp+140h+Src]
0x180009818  mov     rax, [rsp+60h]
0x18000981d  mov     [rdi], rax
0x180009820  mov     eax, [rsp+68h]
0x180009824  mov     [rdi+8], eax
0x180009827  mov     [rdi+0Ch], r13d
0x18000982b  test    rsi, rsi
0x18000982e  jz      short loc_18000985F
0x180009830  mov     rcx, rsi
0x180009833  jmp     short loc_180009858
0x180009835  lea     rcx, aResultOutputme; "result.outputMessage.length == effectiv"...
0x18000983c  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180009841  xorps   xmm0, xmm0
0x180009844  movups  xmmword ptr [rdi], xmm0
0x180009847  mov     dword ptr [rdi+0Ch], 8009030Fh
0x18000984e  mov     rcx, [rsp+140h+Src]; void *
0x180009853  test    rcx, rcx
0x180009856  jz      short loc_18000985F
0x180009858  xor     edx, edx; struct std::nothrow_t *
0x18000985a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000985f  mov     rcx, [rbp+40h+var_B0]; void *
0x180009863  test    rcx, rcx
0x180009866  jz      short loc_18000986F
0x180009868  xor     edx, edx; struct std::nothrow_t *
0x18000986a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000986f  mov     rcx, [rsp+140h+var_C8]; void *
0x180009874  test    rcx, rcx
0x180009877  jz      short loc_180009880
0x180009879  xor     edx, edx; struct std::nothrow_t *
0x18000987b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180009880  mov     rax, rdi
0x180009883  mov     rcx, [rbp+40h+var_50]
0x180009887  xor     rcx, rsp; StackCookie
0x18000988a  call    __security_check_cookie
0x18000988f  add     rsp, 108h
0x180009896  pop     r15
0x180009898  pop     r14
0x18000989a  pop     r13
0x18000989c  pop     r12
0x18000989e  pop     rdi
0x18000989f  pop     rsi
0x1800098a0  pop     rbx
0x1800098a1  pop     rbp
0x1800098a2  retn
0x1800098a3  lea     rcx, aGssApiCannotHa; "GSS-API cannot have a QOP when conf = f"...
0x1800098aa  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
```
