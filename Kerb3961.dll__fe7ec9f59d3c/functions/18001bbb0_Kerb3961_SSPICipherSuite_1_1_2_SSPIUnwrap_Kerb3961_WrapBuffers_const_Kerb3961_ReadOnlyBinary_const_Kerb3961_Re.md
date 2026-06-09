# Kerb3961::SSPICipherSuite<1,1,2>::SSPIUnwrap(Kerb3961::WrapBuffers const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,bool,bool)

- ea: `0x18001bbb0`
- end: `0x18001bead`
- name: `?SSPIUnwrap@?$SSPICipherSuite@$00$00$01@Kerb3961@@EEAA?AU?$ReturnType@UVerifyMICResult@Kerb3961@@$1??$SingleGetter@UVerifyMICResult@Kerb3961@@$0M@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UVerifyMICResult@Kerb3961@@$0M@@2@YAAEAU32@AEAU12@@Z@2@AEBUWrapBuffers@2@AEBUReadOnlyBinary@2@11_N2@Z`
- size: `765`
- prototype: ``
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
- `0x18000a040`
- `0x18001bbb0`
- `0x18001d360`
- `0x18001e010`

## string_xrefs

- `0x18001bc19`: `combinedBuffer`
- `0x18001bc64`: `completeWrapToken`
- `0x18001be32`: `result.outputMessage.length == effectiveInput.length + ((compatFixes == GssApiCompatibilityFixes::RC4) ? trailerBuffer.length : 0)`

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
  Kerb3961::SSPICipherSuite<1,1,0>::CoalesceEncryptedWrapBuffers((__int64)v34, a3);
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
0x18001bbb0  push    rbp
0x18001bbb2  push    rbx
0x18001bbb3  push    rsi
0x18001bbb4  push    rdi
0x18001bbb5  push    r12
0x18001bbb7  push    r13
0x18001bbb9  push    r14
0x18001bbbb  push    r15
0x18001bbbd  lea     rbp, [rsp-8]
0x18001bbc2  sub     rsp, 108h
0x18001bbc9  mov     rax, cs:__security_cookie
0x18001bbd0  xor     rax, rsp
0x18001bbd3  mov     [rbp+40h+var_50], rax
0x18001bbd7  mov     rax, [rbp+40h+arg_28]
0x18001bbdb  mov     rdi, rdx
0x18001bbde  mov     r15, [rbp+40h+arg_20]
0x18001bbe2  mov     r12, rcx
0x18001bbe5  mov     [rbp+40h+var_A0], rax
0x18001bbe9  lea     rcx, [rsp+140h+var_D0]
0x18001bbee  mov     al, [rbp+40h+arg_30]
0x18001bbf4  mov     rdx, r8
0x18001bbf7  mov     [rsp+140h+var_FF], al
0x18001bbfb  mov     r13, r9
0x18001bbfe  mov     al, [rbp+40h+arg_38]
0x18001bc04  mov     r14, r8
0x18001bc07  mov     [rsp+140h+var_100], al
0x18001bc0b  call    ?CoalesceEncryptedWrapBuffers@?$SSPICipherSuite@$00$00$0A@@Kerb3961@@KA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUWrapBuffers@2@@Z; Kerb3961::SSPICipherSuite<1,1,0>::CoalesceEncryptedWrapBuffers(Kerb3961::WrapBuffers const &)
0x18001bc10  mov     ebx, dword ptr [rbp+40h+var_C0]
0x18001bc13  test    ebx, ebx
0x18001bc15  jns     short loc_18001BC33
0x18001bc17  mov     edx, ebx; char *
0x18001bc19  lea     rcx, aCombinedbuffer; "combinedBuffer"
0x18001bc20  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18001bc25  xorps   xmm0, xmm0
0x18001bc28  movups  xmmword ptr [rdi], xmm0
0x18001bc2b  mov     [rdi+0Ch], ebx
0x18001bc2e  jmp     loc_18001BE6C
0x18001bc33  cmp     ebx, 0FFh
0x18001bc39  jnz     short loc_18001BC41
0x18001bc3b  mov     rsi, [r14+8]
0x18001bc3f  jmp     short loc_18001BC46
0x18001bc41  lea     rsi, [rsp+140h+var_D0]
0x18001bc46  mov     r9, r15
0x18001bc49  lea     rcx, [rbp+40h+var_B8]
0x18001bc4d  mov     r8, rsi
0x18001bc50  mov     rdx, r13
0x18001bc53  call    ?Concatenate@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@00@Z; Kerb3961::Concatenate(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x18001bc58  mov     ebx, dword ptr [rbp+40h+var_A8]
0x18001bc5b  xor     r13d, r13d
0x18001bc5e  test    ebx, ebx
0x18001bc60  jns     short loc_18001BC7E
0x18001bc62  mov     edx, ebx; char *
0x18001bc64  lea     rcx, aCompletewrapto; "completeWrapToken"
0x18001bc6b  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18001bc70  xorps   xmm0, xmm0
0x18001bc73  movups  xmmword ptr [rdi], xmm0
0x18001bc76  mov     [rdi+0Ch], ebx
0x18001bc79  jmp     loc_18001BE5C
0x18001bc7e  xorps   xmm0, xmm0
0x18001bc81  mov     [rsp+140h+var_D4], r13d
0x18001bc86  lea     rbx, ??_7?$_FuncEmpty@U?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@Kerb3961@@AEBUReadOnlyBinary@2@@utl@@6B@; const utl::_FuncEmpty<Kerb3961::ReturnType<Kerb3961::OwnedBinary,&Kerb3961::SingleGetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary const &),&Kerb3961::SingleSetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary &)>,Kerb3961::ReadOnlyBinary const &>::`vftable'
0x18001bc8d  mov     [rsp+140h+var_F8], r13
0x18001bc92  lea     rcx, [rbp+40h+var_70]
0x18001bc96  mov     [rbp+40h+var_70], rbx
0x18001bc9a  movdqu  xmmword ptr [rsp+140h+var_E8+4], xmm0
0x18001bca0  mov     [rsp+140h+Src], r13
0x18001bca5  mov     dword ptr [rsp+140h+var_E8], 0C0000001h
0x18001bcad  call    ?_Destroy@?$_FuncEmpty@U?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@Kerb3961@@AEBUReadOnlyBinary@2@@utl@@UEAAXXZ; utl::_FuncEmpty<Kerb3961::ReturnType<Kerb3961::OwnedBinary,&Kerb3961::SingleGetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary const &),&Kerb3961::SingleSetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary &)>,Kerb3961::ReadOnlyBinary const &>::_Destroy(void)
0x18001bcb2  mov     ecx, 20h ; ' '; unsigned __int64
0x18001bcb7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001bcbc  test    rax, rax
0x18001bcbf  jnz     short loc_18001BCC7
0x18001bcc1  mov     [rbp+40h+var_70], rbx
0x18001bcc5  jmp     short loc_18001BCE5
0x18001bcc7  mov     [rbp+40h+var_68], rax
0x18001bccb  lea     rcx, ??_7?$_FuncBig@V_lambda_1_@?P@??SSPIUnwrap@?$SSPICipherSuite@$00$00$01@Kerb3961@@EEAA?AU?$ReturnType@UVerifyMICResult@Kerb3961@@$1??$SingleGetter@UVerifyMICResult@Kerb3961@@$0M@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UVerifyMICResult@Kerb3961@@$0M@@2@YAAEAU32@AEAU12@@Z@4@AEBUWrapBuffers@4@AEBUReadOnlyBinary@4@11_N2@Z@U?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@4@AEBU74@@utl@@6B@; const utl::_FuncBig<`Kerb3961::SSPICipherSuite<1,1,2>::SSPIUnwrap(Kerb3961::WrapBuffers const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,bool,bool)'::`15'::_lambda_1_,Kerb3961::ReturnType<Kerb3961::OwnedBinary,&Kerb3961::SingleGetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary const &),&Kerb3961::SingleSetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary &)>,Kerb3961::ReadOnlyBinary const &>::`vftable'
0x18001bcd2  mov     [rbp+40h+var_70], rcx
0x18001bcd6  mov     [rax], r12
0x18001bcd9  mov     [rax+8], r14
0x18001bcdd  mov     [rax+10h], r15
0x18001bce1  mov     [rax+18h], rsi
0x18001bce5  mov     cl, [rsp+140h+var_100]
0x18001bce9  lea     r9, [rbp+40h+var_70]
0x18001bced  mov     rax, [r12]
0x18001bcf1  lea     r8, [rbp+40h+var_B8]
0x18001bcf5  mov     [rsp+140h+var_110], cl
0x18001bcf9  lea     rdx, [rbp+40h+var_98]
0x18001bcfd  mov     cl, [rsp+140h+var_FF]
0x18001bd01  mov     [rsp+140h+var_118], cl
0x18001bd05  mov     rcx, [rbp+40h+var_A0]
0x18001bd09  mov     rax, [rax+168h]
0x18001bd10  mov     [rsp+140h+var_120], rcx
0x18001bd15  mov     rcx, r12
0x18001bd18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bd1d  mov     rcx, [rsp+140h+Src]; void *
0x18001bd22  mov     rbx, rax
0x18001bd25  test    rcx, rcx
0x18001bd28  jz      short loc_18001BD31
0x18001bd2a  xor     edx, edx; struct std::nothrow_t *
0x18001bd2c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001bd31  mov     rax, [rbx]
0x18001bd34  mov     [rsp+140h+var_F8], rax
0x18001bd39  mov     rax, [rbx+8]
0x18001bd3d  mov     [rbx], r13
0x18001bd40  mov     [rsp+140h+Src], rax
0x18001bd45  mov     eax, [rbx+10h]
0x18001bd48  mov     [rbx+8], r13
0x18001bd4c  mov     dword ptr [rsp+140h+var_E8], eax
0x18001bd50  mov     dword ptr [rbx+10h], 0C0000001h
0x18001bd57  mov     rax, [rbx+18h]
0x18001bd5b  mov     rcx, [rbp+40h+var_90]; void *
0x18001bd5f  mov     [rsp+60h], rax
0x18001bd64  mov     eax, [rbx+20h]
0x18001bd67  mov     [rsp+68h], eax
0x18001bd6b  mov     al, [rbx+24h]
0x18001bd6e  mov     byte ptr [rsp+140h+var_D4], al
0x18001bd72  test    rcx, rcx
0x18001bd75  jz      short loc_18001BD7E
0x18001bd77  xor     edx, edx; struct std::nothrow_t *
0x18001bd79  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001bd7e  mov     rax, [rbp+40h+var_70]
0x18001bd82  lea     rcx, [rbp+40h+var_70]
0x18001bd86  mov     rax, [rax]
0x18001bd89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bd8e  mov     ebx, dword ptr [rsp+140h+var_E8]
0x18001bd92  test    ebx, ebx
0x18001bd94  jns     short loc_18001BDB2
0x18001bd96  mov     edx, ebx; char *
0x18001bd98  lea     rcx, aResult; "result"
0x18001bd9f  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18001bda4  xorps   xmm0, xmm0
0x18001bda7  movups  xmmword ptr [rdi], xmm0
0x18001bdaa  mov     [rdi+0Ch], ebx
0x18001bdad  jmp     loc_18001BE4B
0x18001bdb2  cmp     byte ptr [rsp+140h+var_D4], r13b
0x18001bdb7  jnz     short loc_18001BDCC
0x18001bdb9  cmp     [rsp+68h], r13d
0x18001bdbe  jnz     loc_18001BEA0
0x18001bdc4  mov     dword ptr [rsp+68h], 80000001h
0x18001bdcc  mov     rax, [rsi]
0x18001bdcf  cmp     [rsp+140h+var_F8], rax
0x18001bdd4  jnz     short loc_18001BE32
0x18001bdd6  mov     rax, [r14]
0x18001bdd9  mov     rbx, [r14+8]
0x18001bddd  mov     rsi, [rsp+140h+Src]
0x18001bde2  lea     rcx, [rax+rax*2]
0x18001bde6  lea     r14, [rbx+rcx*8]
0x18001bdea  cmp     rbx, r14
0x18001bded  jz      short loc_18001BE15
0x18001bdef  cmp     [rbx+10h], r13b
0x18001bdf3  jz      short loc_18001BE07
0x18001bdf5  mov     r8, [rbx]; Size
0x18001bdf8  mov     rdx, rsi; Src
0x18001bdfb  mov     rcx, [rbx+8]; void *
0x18001bdff  call    memcpy_0
0x18001be04  add     rsi, [rbx]
0x18001be07  add     rbx, 18h
0x18001be0b  cmp     rbx, r14
0x18001be0e  jnz     short loc_18001BDEF
0x18001be10  mov     rsi, [rsp+140h+Src]
0x18001be15  mov     rax, [rsp+60h]
0x18001be1a  mov     [rdi], rax
0x18001be1d  mov     eax, [rsp+68h]
0x18001be21  mov     [rdi+8], eax
0x18001be24  mov     [rdi+0Ch], r13d
0x18001be28  test    rsi, rsi
0x18001be2b  jz      short loc_18001BE5C
0x18001be2d  mov     rcx, rsi
0x18001be30  jmp     short loc_18001BE55
0x18001be32  lea     rcx, aResultOutputme; "result.outputMessage.length == effectiv"...
0x18001be39  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18001be3e  xorps   xmm0, xmm0
0x18001be41  movups  xmmword ptr [rdi], xmm0
0x18001be44  mov     dword ptr [rdi+0Ch], 8009030Fh
0x18001be4b  mov     rcx, [rsp+140h+Src]; void *
0x18001be50  test    rcx, rcx
0x18001be53  jz      short loc_18001BE5C
0x18001be55  xor     edx, edx; struct std::nothrow_t *
0x18001be57  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001be5c  mov     rcx, [rbp+40h+var_B0]; void *
0x18001be60  test    rcx, rcx
0x18001be63  jz      short loc_18001BE6C
0x18001be65  xor     edx, edx; struct std::nothrow_t *
0x18001be67  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001be6c  mov     rcx, [rsp+140h+var_C8]; void *
0x18001be71  test    rcx, rcx
0x18001be74  jz      short loc_18001BE7D
0x18001be76  xor     edx, edx; struct std::nothrow_t *
0x18001be78  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001be7d  mov     rax, rdi
0x18001be80  mov     rcx, [rbp+40h+var_50]
0x18001be84  xor     rcx, rsp; StackCookie
0x18001be87  call    __security_check_cookie
0x18001be8c  add     rsp, 108h
0x18001be93  pop     r15
0x18001be95  pop     r14
0x18001be97  pop     r13
0x18001be99  pop     r12
0x18001be9b  pop     rdi
0x18001be9c  pop     rsi
0x18001be9d  pop     rbx
0x18001be9e  pop     rbp
0x18001be9f  retn
0x18001bea0  lea     rcx, aGssApiCannotHa; "GSS-API cannot have a QOP when conf = f"...
0x18001bea7  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
```
