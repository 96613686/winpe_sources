# Kerb3961::SSPICipherSuite<1,1,2>::SSPIUnwrap(Kerb3961::WrapBuffers const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,bool,bool)

- ea: `0x1800060f0`
- end: `0x1800063e4`
- name: `?SSPIUnwrap@?$SSPICipherSuite@$00$00$01@Kerb3961@@EEAA?AU?$ReturnType@UVerifyMICResult@Kerb3961@@$1??$SingleGetter@UVerifyMICResult@Kerb3961@@$0M@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UVerifyMICResult@Kerb3961@@$0M@@2@YAAEAU32@AEAU12@@Z@2@AEBUWrapBuffers@2@AEBUReadOnlyBinary@2@11_N2@Z`
- size: `756`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180001ff4`
- `0x1800037e0`
- `0x180003a38`
- `0x1800060f0`
- `0x180006af0`
- `0x180011760`
- `0x1800118cc`
- `0x180011ab8`
- `0x180011b40`
- `0x180012200`
- `0x180012240`
- `0x180012300`

## string_xrefs

- `0x180006159`: `combinedBuffer`
- `0x1800061a4`: `completeWrapToken`
- `0x18000636e`: `result.outputMessage.length == effectiveInput.length + ((compatFixes == GssApiCompatibilityFixes::RC4) ? trailerBuffer.length : 0)`

## pseudocode

```c
__int64 __fastcall Kerb3961::SSPICipherSuite<1,1,2>::SSPIUnwrap(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        __int64 a4,
        __int64 a5,
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
    v43[0] = ___7___FuncBig_V_lambda_1___P___SSPIUnwrap___SSPICipherSuite__00_00_01_Kerb3961__EEAA_AU__ReturnType_UVerifyMICResult_Kerb3961___1___SingleGetter_UVerifyMICResult_Kerb3961___0M__2_YAAEBUResultBlock_2_AEBU12__Z_1___SingleSetter_UVerifyMICResult_Kerb3961___0M__2_YAAEAU32_AEAU12__Z_4_AEBUWrapBuffers_4_AEBUReadOnlyBinary_4_11_N2_Z_U__ReturnType_UOwnedBinary_Kerb3961___1___SingleGetter_UOwnedBinary_Kerb3961___0BA__2_YAAEBUResultBlock_2_AEBU12__Z_1___SingleSetter_UOwnedBinary_Kerb3961___0BA__2_YAAEAU32_AEAU12__Z_4_AEBU74__utl__6B_;
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
  if ( v28 != *(_QWORD *)v14 )
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
0x1800060f0  push    rbp
0x1800060f2  push    rbx
0x1800060f3  push    rsi
0x1800060f4  push    rdi
0x1800060f5  push    r12
0x1800060f7  push    r13
0x1800060f9  push    r14
0x1800060fb  push    r15
0x1800060fd  lea     rbp, [rsp-8]
0x180006102  sub     rsp, 108h
0x180006109  mov     rax, cs:__security_cookie
0x180006110  xor     rax, rsp
0x180006113  mov     [rbp+40h+var_50], rax
0x180006117  mov     rax, [rbp+40h+arg_28]
0x18000611b  mov     rdi, rdx
0x18000611e  mov     r15, [rbp+40h+arg_20]
0x180006122  mov     r12, rcx
0x180006125  mov     [rbp+40h+var_A0], rax
0x180006129  lea     rcx, [rsp+140h+var_D0]
0x18000612e  mov     al, [rbp+40h+arg_30]
0x180006134  mov     rdx, r8
0x180006137  mov     [rsp+140h+var_FF], al
0x18000613b  mov     r13, r9
0x18000613e  mov     al, [rbp+40h+arg_38]
0x180006144  mov     r14, r8
0x180006147  mov     [rsp+140h+var_100], al
0x18000614b  call    ?CoalesceEncryptedWrapBuffers@?$SSPICipherSuite@$00$00$0A@@Kerb3961@@KA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUWrapBuffers@2@@Z; Kerb3961::SSPICipherSuite<1,1,0>::CoalesceEncryptedWrapBuffers(Kerb3961::WrapBuffers const &)
0x180006150  mov     ebx, dword ptr [rbp+40h+var_C0]
0x180006153  test    ebx, ebx
0x180006155  jns     short loc_180006173
0x180006157  mov     edx, ebx; char *
0x180006159  lea     rcx, aCombinedbuffer; "combinedBuffer"
0x180006160  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180006165  xorps   xmm0, xmm0
0x180006168  movups  xmmword ptr [rdi], xmm0
0x18000616b  mov     [rdi+0Ch], ebx
0x18000616e  jmp     loc_1800063A4
0x180006173  cmp     ebx, 0FFh
0x180006179  jnz     short loc_180006181
0x18000617b  mov     rsi, [r14+8]
0x18000617f  jmp     short loc_180006186
0x180006181  lea     rsi, [rsp+140h+var_D0]
0x180006186  mov     r9, r15
0x180006189  lea     rcx, [rbp+40h+var_B8]
0x18000618d  mov     r8, rsi
0x180006190  mov     rdx, r13
0x180006193  call    ?Concatenate@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@00@Z; Kerb3961::Concatenate(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x180006198  mov     ebx, dword ptr [rbp+40h+var_A8]
0x18000619b  xor     r13d, r13d
0x18000619e  test    ebx, ebx
0x1800061a0  jns     short loc_1800061BE
0x1800061a2  mov     edx, ebx; char *
0x1800061a4  lea     rcx, aCompletewrapto; "completeWrapToken"
0x1800061ab  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800061b0  xorps   xmm0, xmm0
0x1800061b3  movups  xmmword ptr [rdi], xmm0
0x1800061b6  mov     [rdi+0Ch], ebx
0x1800061b9  jmp     loc_180006396
0x1800061be  xorps   xmm0, xmm0
0x1800061c1  mov     [rsp+140h+var_D4], r13d
0x1800061c6  lea     rbx, ??_7?$_FuncEmpty@U?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@Kerb3961@@AEBUReadOnlyBinary@2@@utl@@6B@; const utl::_FuncEmpty<Kerb3961::ReturnType<Kerb3961::OwnedBinary,&Kerb3961::SingleGetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary const &),&Kerb3961::SingleSetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary &)>,Kerb3961::ReadOnlyBinary const &>::`vftable'
0x1800061cd  mov     [rsp+140h+var_F8], r13
0x1800061d2  lea     rcx, [rbp+40h+var_70]
0x1800061d6  mov     [rbp+40h+var_70], rbx
0x1800061da  movdqu  xmmword ptr [rsp+140h+var_E8+4], xmm0
0x1800061e0  mov     [rsp+140h+Src], r13
0x1800061e5  mov     dword ptr [rsp+140h+var_E8], 0C0000001h
0x1800061ed  call    ?_Destroy@?$_FuncEmpty@U?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@Kerb3961@@AEBUReadOnlyBinary@2@@utl@@UEAAXXZ; utl::_FuncEmpty<Kerb3961::ReturnType<Kerb3961::OwnedBinary,&Kerb3961::SingleGetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary const &),&Kerb3961::SingleSetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary &)>,Kerb3961::ReadOnlyBinary const &>::_Destroy(void)
0x1800061f2  mov     ecx, 20h ; ' '; unsigned __int64
0x1800061f7  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800061fc  test    rax, rax
0x1800061ff  jnz     short loc_180006207
0x180006201  mov     [rbp+40h+var_70], rbx
0x180006205  jmp     short loc_180006225
0x180006207  mov     [rbp+40h+var_68], rax
0x18000620b  lea     rcx, ??_7?$_FuncBig@V_lambda_1_@?P@??SSPIUnwrap@?$SSPICipherSuite@$00$00$01@Kerb3961@@EEAA?AU?$ReturnType@UVerifyMICResult@Kerb3961@@$1??$SingleGetter@UVerifyMICResult@Kerb3961@@$0M@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UVerifyMICResult@Kerb3961@@$0M@@2@YAAEAU32@AEAU12@@Z@4@AEBUWrapBuffers@4@AEBUReadOnlyBinary@4@11_N2@Z@U?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@4@AEBU74@@utl@@6B@; const utl::_FuncBig<`Kerb3961::SSPICipherSuite<1,1,2>::SSPIUnwrap(Kerb3961::WrapBuffers const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,bool,bool)'::`15'::_lambda_1_,Kerb3961::ReturnType<Kerb3961::OwnedBinary,&Kerb3961::SingleGetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary const &),&Kerb3961::SingleSetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary &)>,Kerb3961::ReadOnlyBinary const &>::`vftable'
0x180006212  mov     [rbp+40h+var_70], rcx
0x180006216  mov     [rax], r12
0x180006219  mov     [rax+8], r14
0x18000621d  mov     [rax+10h], r15
0x180006221  mov     [rax+18h], rsi
0x180006225  mov     cl, [rsp+140h+var_100]
0x180006229  lea     r9, [rbp+40h+var_70]
0x18000622d  mov     rax, [r12]
0x180006231  lea     r8, [rbp+40h+var_B8]
0x180006235  mov     [rsp+140h+var_110], cl
0x180006239  lea     rdx, [rbp+40h+var_98]
0x18000623d  mov     cl, [rsp+140h+var_FF]
0x180006241  mov     [rsp+140h+var_118], cl
0x180006245  mov     rcx, [rbp+40h+var_A0]
0x180006249  mov     rax, [rax+168h]
0x180006250  mov     [rsp+140h+var_120], rcx
0x180006255  mov     rcx, r12
0x180006258  call    _guard_dispatch_icall
0x18000625d  mov     rcx, [rsp+140h+Src]
0x180006262  mov     rbx, rax
0x180006265  test    rcx, rcx
0x180006268  jz      short loc_18000626F
0x18000626a  call    Kerb3961Free
0x18000626f  mov     rax, [rbx]
0x180006272  mov     [rsp+140h+var_F8], rax
0x180006277  mov     rax, [rbx+8]
0x18000627b  mov     [rbx], r13
0x18000627e  mov     [rsp+140h+Src], rax
0x180006283  mov     eax, [rbx+10h]
0x180006286  mov     [rbx+8], r13
0x18000628a  mov     dword ptr [rsp+140h+var_E8], eax
0x18000628e  mov     dword ptr [rbx+10h], 0C0000001h
0x180006295  mov     rax, [rbx+18h]
0x180006299  mov     rcx, [rbp+40h+var_90]
0x18000629d  mov     [rsp+60h], rax
0x1800062a2  mov     eax, [rbx+20h]
0x1800062a5  mov     [rsp+68h], eax
0x1800062a9  mov     al, [rbx+24h]
0x1800062ac  mov     byte ptr [rsp+140h+var_D4], al
0x1800062b0  test    rcx, rcx
0x1800062b3  jz      short loc_1800062BA
0x1800062b5  call    Kerb3961Free
0x1800062ba  mov     rax, [rbp+40h+var_70]
0x1800062be  lea     rcx, [rbp+40h+var_70]
0x1800062c2  mov     rax, [rax]
0x1800062c5  call    _guard_dispatch_icall
0x1800062ca  mov     ebx, dword ptr [rsp+140h+var_E8]
0x1800062ce  test    ebx, ebx
0x1800062d0  jns     short loc_1800062EE
0x1800062d2  mov     edx, ebx; char *
0x1800062d4  lea     rcx, aResult; "result"
0x1800062db  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800062e0  xorps   xmm0, xmm0
0x1800062e3  movups  xmmword ptr [rdi], xmm0
0x1800062e6  mov     [rdi+0Ch], ebx
0x1800062e9  jmp     loc_180006387
0x1800062ee  cmp     byte ptr [rsp+140h+var_D4], r13b
0x1800062f3  jnz     short loc_180006308
0x1800062f5  cmp     [rsp+68h], r13d
0x1800062fa  jnz     loc_1800063D7
0x180006300  mov     dword ptr [rsp+68h], 80000001h
0x180006308  mov     rax, [rsi]
0x18000630b  cmp     [rsp+140h+var_F8], rax
0x180006310  jnz     short loc_18000636E
0x180006312  mov     rax, [r14]
0x180006315  mov     rbx, [r14+8]
0x180006319  mov     rsi, [rsp+140h+Src]
0x18000631e  lea     rcx, [rax+rax*2]
0x180006322  lea     r14, [rbx+rcx*8]
0x180006326  cmp     rbx, r14
0x180006329  jz      short loc_180006351
0x18000632b  cmp     [rbx+10h], r13b
0x18000632f  jz      short loc_180006343
0x180006331  mov     r8, [rbx]; Size
0x180006334  mov     rdx, rsi; Src
0x180006337  mov     rcx, [rbx+8]; void *
0x18000633b  call    memmove
0x180006340  add     rsi, [rbx]
0x180006343  add     rbx, 18h
0x180006347  cmp     rbx, r14
0x18000634a  jnz     short loc_18000632B
0x18000634c  mov     rsi, [rsp+140h+Src]
0x180006351  mov     rax, [rsp+60h]
0x180006356  mov     [rdi], rax
0x180006359  mov     eax, [rsp+68h]
0x18000635d  mov     [rdi+8], eax
0x180006360  mov     [rdi+0Ch], r13d
0x180006364  test    rsi, rsi
0x180006367  jz      short loc_180006396
0x180006369  mov     rcx, rsi
0x18000636c  jmp     short loc_180006391
0x18000636e  lea     rcx, aResultOutputme; "result.outputMessage.length == effectiv"...
0x180006375  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000637a  xorps   xmm0, xmm0
0x18000637d  movups  xmmword ptr [rdi], xmm0
0x180006380  mov     dword ptr [rdi+0Ch], 8009030Fh
0x180006387  mov     rcx, [rsp+140h+Src]
0x18000638c  test    rcx, rcx
0x18000638f  jz      short loc_180006396
0x180006391  call    Kerb3961Free
0x180006396  mov     rcx, [rbp+40h+var_B0]
0x18000639a  test    rcx, rcx
0x18000639d  jz      short loc_1800063A4
0x18000639f  call    Kerb3961Free
0x1800063a4  mov     rcx, [rsp+140h+var_C8]
0x1800063a9  test    rcx, rcx
0x1800063ac  jz      short loc_1800063B3
0x1800063ae  call    Kerb3961Free
0x1800063b3  mov     rax, rdi
0x1800063b6  mov     rcx, [rbp+40h+var_50]
0x1800063ba  xor     rcx, rsp; StackCookie
0x1800063bd  call    __security_check_cookie
0x1800063c2  add     rsp, 108h
0x1800063c9  pop     r15
0x1800063cb  pop     r14
0x1800063cd  pop     r13
0x1800063cf  pop     r12
0x1800063d1  pop     rdi
0x1800063d2  pop     rsi
0x1800063d3  pop     rbx
0x1800063d4  pop     rbp
0x1800063d5  retn
0x1800063d7  lea     rcx, aGssApiCannotHa; "GSS-API cannot have a QOP when conf = f"...
0x1800063de  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
```
