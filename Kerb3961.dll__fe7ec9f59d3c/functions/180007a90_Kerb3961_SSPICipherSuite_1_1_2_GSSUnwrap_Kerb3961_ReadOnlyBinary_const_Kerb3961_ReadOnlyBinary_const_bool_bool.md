# Kerb3961::SSPICipherSuite<1,1,2>::GSSUnwrap(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,bool,bool)

- ea: `0x180007a90`
- end: `0x180007c6f`
- name: `?GSSUnwrap@?$SSPICipherSuite@$00$00$01@Kerb3961@@EEAA?AU?$ReturnType@UUnwrapResult@Kerb3961@@$1??$DoubleGetter@UUnwrapResult@Kerb3961@@UOwnedBinary@2@$0A@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$DoubleSetter@UUnwrapResult@Kerb3961@@UOwnedBinary@2@$0A@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0_N1@Z`
- size: `479`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *, __int64, char, char)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops`

## callees

- `0x180001d40`
- `0x180001d64`
- `0x180002c64`
- `0x180002fc0`
- `0x1800033f4`
- `0x180007a90`
- `0x18000a040`
- `0x18001e010`

## pseudocode

```c
__int64 __fastcall Kerb3961::SSPICipherSuite<1,1,2>::GSSUnwrap(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        __int64 a4,
        char a5,
        char a6)
{
  __int64 v10; // rbx
  void *v11; // rcx
  int v12; // eax
  const unsigned __int16 *v13; // rdx
  int v14; // r8d
  int v15; // ecx
  __int64 v17; // [rsp+40h] [rbp-79h]
  void *v18; // [rsp+48h] [rbp-71h]
  int v19; // [rsp+50h] [rbp-69h]
  __int64 v20; // [rsp+58h] [rbp-61h]
  int v21; // [rsp+60h] [rbp-59h]
  char v22; // [rsp+64h] [rbp-55h]
  unsigned __int16 *v23; // [rsp+68h] [rbp-51h] BYREF
  void *v24; // [rsp+70h] [rbp-49h]
  _QWORD v25[4]; // [rsp+90h] [rbp-29h] BYREF

  if ( *a3 <= 0xFFFFFFFFFFFF0000uLL )
  {
    v25[0] = &utl::_FuncEmpty<Kerb3961::ReturnType<Kerb3961::OwnedBinary,&Kerb3961::ResultBlock const & Kerb3961::SingleGetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary const &),&Kerb3961::ResultBlock & Kerb3961::SingleSetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary &)>,Kerb3961::ReadOnlyBinary const &>::`vftable';
    utl::_FuncEmpty<Kerb3961::ReturnType<Kerb3961::OwnedBinary,&Kerb3961::ResultBlock const & Kerb3961::SingleGetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary const &),&Kerb3961::ResultBlock & Kerb3961::SingleSetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary &)>,Kerb3961::ReadOnlyBinary const &>::_Destroy(v25);
    v25[0] = ___7___FuncSmall_V_lambda_1___9__GSSUnwrap___SSPICipherSuite__00_00_01_Kerb3961__EEAA_AU__ReturnType_UUnwrapResult_Kerb3961___1___DoubleGetter_UUnwrapResult_Kerb3961__UOwnedBinary_2__0A__0BA__2_YAAEBUResultBlock_2_AEBU12__Z_1___DoubleSetter_UUnwrapResult_Kerb3961__UOwnedBinary_2__0A__0BA__2_YAAEAU32_AEAU12__Z_4_AEBUReadOnlyBinary_4_0_N1_Z_U__ReturnType_UOwnedBinary_Kerb3961___1___SingleGetter_UOwnedBinary_Kerb3961___0BA__2_YAAEBUResultBlock_2_AEBU12__Z_1___SingleSetter_UOwnedBinary_Kerb3961___0BA__2_YAAEAU32_AEAU12__Z_4_AEBU64__utl__6B_;
    v10 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **, _QWORD *, _QWORD *, __int64, char, char))(*(_QWORD *)a1 + 360LL))(
            a1,
            &v23,
            a3,
            v25,
            a4,
            a5,
            a6);
    v17 = *(_QWORD *)v10;
    v11 = *(void **)(v10 + 8);
    *(_QWORD *)v10 = 0;
    v18 = v11;
    v12 = *(_DWORD *)(v10 + 16);
    *(_QWORD *)(v10 + 8) = 0;
    v19 = v12;
    *(_DWORD *)(v10 + 16) = -1073741823;
    v20 = *(_QWORD *)(v10 + 24);
    v21 = *(_DWORD *)(v10 + 32);
    v22 = *(_BYTE *)(v10 + 36);
    if ( v24 )
      operator delete(v24, 0);
    (*(void (__fastcall **)(_QWORD *))v25[0])(v25);
    if ( v19 >= 0 )
    {
      LOBYTE(v13) = v22;
      if ( v22 )
      {
        v15 = v21;
      }
      else
      {
        if ( v21 )
          Kerb3961::ConsistencyFail((Kerb3961 *)L"GSS-API cannot havea QOP when conf = false", v13);
        v15 = -2147483647;
      }
      *(_QWORD *)a2 = v17;
      *(_QWORD *)(a2 + 8) = v18;
      *(_QWORD *)(a2 + 24) = v20;
      *(_DWORD *)(a2 + 16) = v19;
      *(_DWORD *)(a2 + 32) = v15;
      *(_BYTE *)(a2 + 36) = v22;
    }
    else
    {
      Kerb3961::Logging::Verify::StatusFailed(
        (Kerb3961::Logging::Verify *)"result",
        (const char *)(unsigned int)v19,
        v14);
      *(_QWORD *)(a2 + 20) = 0;
      *(_QWORD *)(a2 + 28) = 0;
      *(_DWORD *)(a2 + 36) = 0;
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = v19;
      if ( v18 )
        operator delete(v18, 0);
    }
  }
  else
  {
    Kerb3961::Logging::Verify::ConditionFailed(
      (Kerb3961::Logging::Verify *)"inputMessage.length <= MessageLimit",
      (const char *)a2);
    *(_QWORD *)(a2 + 20) = 0;
    *(_QWORD *)(a2 + 28) = 0;
    *(_DWORD *)(a2 + 36) = 0;
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = -1073741675;
  }
  return a2;
}

```

## disassembly

```asm
0x180007a90  push    rbp
0x180007a92  push    rbx
0x180007a93  push    rsi
0x180007a94  push    rdi
0x180007a95  push    r12
0x180007a97  push    r13
0x180007a99  push    r14
0x180007a9b  push    r15
0x180007a9d  lea     rbp, [rsp-0Fh]
0x180007aa2  sub     rsp, 0C8h
0x180007aa9  mov     rax, cs:__security_cookie
0x180007ab0  xor     rax, rsp
0x180007ab3  mov     [rbp+47h+var_50], rax
0x180007ab7  cmp     qword ptr [r8], 0FFFFFFFFFFFF0000h
0x180007abe  mov     r15, r9
0x180007ac1  mov     r12b, [rbp+47h+arg_20]
0x180007ac5  mov     rbx, r8
0x180007ac8  mov     r13b, [rbp+47h+arg_28]
0x180007acc  mov     rdi, rdx
0x180007acf  mov     r14, rcx
0x180007ad2  jbe     short loc_180007B00
0x180007ad4  lea     rcx, aInputmessageLe_0; "inputMessage.length <= MessageLimit"
0x180007adb  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180007ae0  xor     esi, esi
0x180007ae2  mov     [rdi+14h], rsi
0x180007ae6  mov     [rdi+1Ch], rsi
0x180007aea  mov     [rdi+24h], esi
0x180007aed  mov     [rdi], rsi
0x180007af0  mov     [rdi+8], rsi
0x180007af4  mov     dword ptr [rdi+10h], 0C0000095h
0x180007afb  jmp     loc_180007C3F
0x180007b00  xor     esi, esi
0x180007b02  lea     rax, ??_7?$_FuncEmpty@U?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@Kerb3961@@AEBUReadOnlyBinary@2@@utl@@6B@; const utl::_FuncEmpty<Kerb3961::ReturnType<Kerb3961::OwnedBinary,&Kerb3961::SingleGetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary const &),&Kerb3961::SingleSetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary &)>,Kerb3961::ReadOnlyBinary const &>::`vftable'
0x180007b09  xorps   xmm0, xmm0
0x180007b0c  mov     dword ptr [rbp+47h+var_9C], esi
0x180007b0f  lea     rcx, [rbp+47h+var_70]
0x180007b13  mov     [rbp+47h+var_C0], rsi
0x180007b17  movdqu  xmmword ptr [rbp+47h+var_B0+4], xmm0
0x180007b1c  mov     [rbp+47h+var_B8], rsi
0x180007b20  mov     dword ptr [rbp+47h+var_B0], esi
0x180007b23  mov     [rbp+47h+var_70], rax
0x180007b27  call    ?_Destroy@?$_FuncEmpty@U?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@Kerb3961@@AEBUReadOnlyBinary@2@@utl@@UEAAXXZ; utl::_FuncEmpty<Kerb3961::ReturnType<Kerb3961::OwnedBinary,&Kerb3961::SingleGetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary const &),&Kerb3961::SingleSetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary &)>,Kerb3961::ReadOnlyBinary const &>::_Destroy(void)
0x180007b2c  lea     rax, ??_7?$_FuncSmall@V_lambda_1_@?9??GSSUnwrap@?$SSPICipherSuite@$00$00$01@Kerb3961@@EEAA?AU?$ReturnType@UUnwrapResult@Kerb3961@@$1??$DoubleGetter@UUnwrapResult@Kerb3961@@UOwnedBinary@2@$0A@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$DoubleSetter@UUnwrapResult@Kerb3961@@UOwnedBinary@2@$0A@$0BA@@2@YAAEAU32@AEAU12@@Z@4@AEBUReadOnlyBinary@4@0_N1@Z@U?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@4@AEBU64@@utl@@6B@; const utl::_FuncSmall<`Kerb3961::SSPICipherSuite<1,1,2>::GSSUnwrap(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,bool,bool)'::`10'::_lambda_1_,Kerb3961::ReturnType<Kerb3961::OwnedBinary,&Kerb3961::SingleGetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary const &),&Kerb3961::SingleSetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary &)>,Kerb3961::ReadOnlyBinary const &>::`vftable'
0x180007b33  mov     [rsp+100h+var_D0], r13b
0x180007b38  mov     [rbp+47h+var_70], rax
0x180007b3c  lea     r9, [rbp+47h+var_70]
0x180007b40  mov     rax, [r14]
0x180007b43  lea     rdx, [rbp+47h+var_9C+4]
0x180007b47  mov     [rsp+100h+var_D8], r12b
0x180007b4c  mov     r8, rbx
0x180007b4f  mov     rcx, r14
0x180007b52  mov     [rsp+100h+var_E0], r15
0x180007b57  mov     rax, [rax+168h]
0x180007b5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b63  mov     rcx, [rbp+47h+var_B8]; void *
0x180007b67  mov     rbx, rax
0x180007b6a  test    rcx, rcx
0x180007b6d  jz      short loc_180007B76
0x180007b6f  xor     edx, edx; struct std::nothrow_t *
0x180007b71  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180007b76  mov     rcx, [rbx]
0x180007b79  mov     [rbp+47h+var_C0], rcx
0x180007b7d  mov     rcx, [rbx+8]
0x180007b81  mov     [rbx], rsi
0x180007b84  mov     [rbp+47h+var_B8], rcx
0x180007b88  mov     eax, [rbx+10h]
0x180007b8b  mov     [rbx+8], rsi
0x180007b8f  mov     dword ptr [rbp+47h+var_B0], eax
0x180007b92  mov     dword ptr [rbx+10h], 0C0000001h
0x180007b99  mov     rax, [rbx+18h]
0x180007b9d  mov     rcx, [rbp+47h+var_90]; void *
0x180007ba1  mov     [rbp-61h], rax
0x180007ba5  mov     eax, [rbx+20h]
0x180007ba8  mov     [rbp-59h], eax
0x180007bab  mov     al, [rbx+24h]
0x180007bae  mov     byte ptr [rbp+47h+var_9C], al
0x180007bb1  test    rcx, rcx
0x180007bb4  jz      short loc_180007BBD
0x180007bb6  xor     edx, edx; struct std::nothrow_t *
0x180007bb8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180007bbd  mov     rax, [rbp+47h+var_70]
0x180007bc1  lea     rcx, [rbp+47h+var_70]
0x180007bc5  mov     rax, [rax]
0x180007bc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bcd  mov     ebx, dword ptr [rbp+47h+var_B0]
0x180007bd0  test    ebx, ebx
0x180007bd2  jns     short loc_180007C09
0x180007bd4  mov     edx, ebx; char *
0x180007bd6  lea     rcx, aResult; "result"
0x180007bdd  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180007be2  mov     [rdi+14h], rsi
0x180007be6  mov     [rdi+1Ch], rsi
0x180007bea  mov     [rdi+24h], esi
0x180007bed  mov     rcx, [rbp+47h+var_B8]; void *
0x180007bf1  mov     [rdi], rsi
0x180007bf4  mov     [rdi+8], rsi
0x180007bf8  mov     [rdi+10h], ebx
0x180007bfb  test    rcx, rcx
0x180007bfe  jz      short loc_180007C3F
0x180007c00  xor     edx, edx; struct std::nothrow_t *
0x180007c02  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180007c07  jmp     short loc_180007C3F
0x180007c09  mov     dl, byte ptr [rbp+47h+var_9C]; unsigned __int16 *
0x180007c0c  test    dl, dl
0x180007c0e  jnz     short loc_180007C1C
0x180007c10  cmp     [rbp-59h], esi
0x180007c13  jnz     short loc_180007C62
0x180007c15  mov     ecx, 80000001h
0x180007c1a  jmp     short loc_180007C1F
0x180007c1c  mov     ecx, [rbp-59h]
0x180007c1f  mov     rax, [rbp+47h+var_C0]
0x180007c23  mov     [rdi], rax
0x180007c26  mov     rax, [rbp+47h+var_B8]
0x180007c2a  mov     [rdi+8], rax
0x180007c2e  mov     rax, [rbp-61h]
0x180007c32  mov     [rdi+18h], rax
0x180007c36  mov     [rdi+10h], ebx
0x180007c39  mov     [rdi+20h], ecx
0x180007c3c  mov     [rdi+24h], dl
0x180007c3f  mov     rax, rdi
0x180007c42  mov     rcx, [rbp+47h+var_50]
0x180007c46  xor     rcx, rsp; StackCookie
0x180007c49  call    __security_check_cookie
0x180007c4e  add     rsp, 0C8h
0x180007c55  pop     r15
0x180007c57  pop     r14
0x180007c59  pop     r13
0x180007c5b  pop     r12
0x180007c5d  pop     rdi
0x180007c5e  pop     rsi
0x180007c5f  pop     rbx
0x180007c60  pop     rbp
0x180007c61  retn
0x180007c62  lea     rcx, aGssApiCannotHa_0; "GSS-API cannot havea QOP when conf = fa"...
0x180007c69  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
```
