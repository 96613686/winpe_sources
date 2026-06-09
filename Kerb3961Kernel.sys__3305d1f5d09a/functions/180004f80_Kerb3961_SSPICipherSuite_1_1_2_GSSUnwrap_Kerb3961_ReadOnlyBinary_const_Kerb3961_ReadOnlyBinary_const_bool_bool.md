# Kerb3961::SSPICipherSuite<1,1,2>::GSSUnwrap(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,bool,bool)

- ea: `0x180004f80`
- end: `0x18000515a`
- name: `?GSSUnwrap@?$SSPICipherSuite@$00$00$01@Kerb3961@@EEAA?AU?$ReturnType@UUnwrapResult@Kerb3961@@$1??$DoubleGetter@UUnwrapResult@Kerb3961@@UOwnedBinary@2@$0A@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$DoubleSetter@UUnwrapResult@Kerb3961@@UOwnedBinary@2@$0A@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0_N1@Z`
- size: `474`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180003a38`
- `0x180004f80`
- `0x180006af0`
- `0x180011760`
- `0x1800118cc`
- `0x180011b40`
- `0x180012200`
- `0x180012240`

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
  __int64 v11; // rcx
  int v12; // eax
  const unsigned __int16 *v13; // rdx
  int v14; // r8d
  int v15; // ecx
  __int64 v17; // [rsp+40h] [rbp-79h]
  __int64 v18; // [rsp+48h] [rbp-71h]
  int v19; // [rsp+50h] [rbp-69h]
  __int64 v20; // [rsp+58h] [rbp-61h]
  int v21; // [rsp+60h] [rbp-59h]
  char v22; // [rsp+64h] [rbp-55h]
  unsigned __int16 *v23; // [rsp+68h] [rbp-51h] BYREF
  __int64 v24; // [rsp+70h] [rbp-49h]
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
    v11 = *(_QWORD *)(v10 + 8);
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
      Kerb3961Free(v24);
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
        Kerb3961Free(v18);
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
0x180004f80  push    rbp
0x180004f82  push    rbx
0x180004f83  push    rsi
0x180004f84  push    rdi
0x180004f85  push    r12
0x180004f87  push    r13
0x180004f89  push    r14
0x180004f8b  push    r15
0x180004f8d  lea     rbp, [rsp-0Fh]
0x180004f92  sub     rsp, 0C8h
0x180004f99  mov     rax, cs:__security_cookie
0x180004fa0  xor     rax, rsp
0x180004fa3  mov     [rbp+47h+var_50], rax
0x180004fa7  cmp     qword ptr [r8], 0FFFFFFFFFFFF0000h
0x180004fae  mov     r15, r9
0x180004fb1  mov     r12b, [rbp+47h+arg_20]
0x180004fb5  mov     rbx, r8
0x180004fb8  mov     r13b, [rbp+47h+arg_28]
0x180004fbc  mov     rdi, rdx
0x180004fbf  mov     r14, rcx
0x180004fc2  jbe     short loc_180004FF0
0x180004fc4  lea     rcx, aInputmessageLe_0; "inputMessage.length <= MessageLimit"
0x180004fcb  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180004fd0  xor     esi, esi
0x180004fd2  mov     [rdi+14h], rsi
0x180004fd6  mov     [rdi+1Ch], rsi
0x180004fda  mov     [rdi+24h], esi
0x180004fdd  mov     [rdi], rsi
0x180004fe0  mov     [rdi+8], rsi
0x180004fe4  mov     dword ptr [rdi+10h], 0C0000095h
0x180004feb  jmp     loc_180005129
0x180004ff0  xor     esi, esi
0x180004ff2  lea     rax, ??_7?$_FuncEmpty@U?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@Kerb3961@@AEBUReadOnlyBinary@2@@utl@@6B@; const utl::_FuncEmpty<Kerb3961::ReturnType<Kerb3961::OwnedBinary,&Kerb3961::SingleGetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary const &),&Kerb3961::SingleSetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary &)>,Kerb3961::ReadOnlyBinary const &>::`vftable'
0x180004ff9  xorps   xmm0, xmm0
0x180004ffc  mov     dword ptr [rbp+47h+var_9C], esi
0x180004fff  lea     rcx, [rbp+47h+var_70]
0x180005003  mov     [rbp+47h+var_C0], rsi
0x180005007  movdqu  xmmword ptr [rbp+47h+var_B0+4], xmm0
0x18000500c  mov     [rbp+47h+var_B8], rsi
0x180005010  mov     dword ptr [rbp+47h+var_B0], esi
0x180005013  mov     [rbp+47h+var_70], rax
0x180005017  call    ?_Destroy@?$_FuncEmpty@U?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@Kerb3961@@AEBUReadOnlyBinary@2@@utl@@UEAAXXZ; utl::_FuncEmpty<Kerb3961::ReturnType<Kerb3961::OwnedBinary,&Kerb3961::SingleGetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary const &),&Kerb3961::SingleSetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary &)>,Kerb3961::ReadOnlyBinary const &>::_Destroy(void)
0x18000501c  lea     rax, ??_7?$_FuncSmall@V_lambda_1_@?9??GSSUnwrap@?$SSPICipherSuite@$00$00$01@Kerb3961@@EEAA?AU?$ReturnType@UUnwrapResult@Kerb3961@@$1??$DoubleGetter@UUnwrapResult@Kerb3961@@UOwnedBinary@2@$0A@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$DoubleSetter@UUnwrapResult@Kerb3961@@UOwnedBinary@2@$0A@$0BA@@2@YAAEAU32@AEAU12@@Z@4@AEBUReadOnlyBinary@4@0_N1@Z@U?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@4@AEBU64@@utl@@6B@; const utl::_FuncSmall<`Kerb3961::SSPICipherSuite<1,1,2>::GSSUnwrap(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,bool,bool)'::`10'::_lambda_1_,Kerb3961::ReturnType<Kerb3961::OwnedBinary,&Kerb3961::SingleGetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary const &),&Kerb3961::SingleSetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary &)>,Kerb3961::ReadOnlyBinary const &>::`vftable'
0x180005023  mov     [rsp+100h+var_D0], r13b
0x180005028  mov     [rbp+47h+var_70], rax
0x18000502c  lea     r9, [rbp+47h+var_70]
0x180005030  mov     rax, [r14]
0x180005033  lea     rdx, [rbp+47h+var_9C+4]
0x180005037  mov     [rsp+100h+var_D8], r12b
0x18000503c  mov     r8, rbx
0x18000503f  mov     rcx, r14
0x180005042  mov     [rsp+100h+var_E0], r15
0x180005047  mov     rax, [rax+168h]
0x18000504e  call    _guard_dispatch_icall
0x180005053  mov     rcx, [rbp+47h+var_B8]
0x180005057  mov     rbx, rax
0x18000505a  test    rcx, rcx
0x18000505d  jz      short loc_180005064
0x18000505f  call    Kerb3961Free
0x180005064  mov     rcx, [rbx]
0x180005067  mov     [rbp+47h+var_C0], rcx
0x18000506b  mov     rcx, [rbx+8]
0x18000506f  mov     [rbx], rsi
0x180005072  mov     [rbp+47h+var_B8], rcx
0x180005076  mov     eax, [rbx+10h]
0x180005079  mov     [rbx+8], rsi
0x18000507d  mov     dword ptr [rbp+47h+var_B0], eax
0x180005080  mov     dword ptr [rbx+10h], 0C0000001h
0x180005087  mov     rax, [rbx+18h]
0x18000508b  mov     rcx, [rbp+47h+var_90]
0x18000508f  mov     [rbp-61h], rax
0x180005093  mov     eax, [rbx+20h]
0x180005096  mov     [rbp-59h], eax
0x180005099  mov     al, [rbx+24h]
0x18000509c  mov     byte ptr [rbp+47h+var_9C], al
0x18000509f  test    rcx, rcx
0x1800050a2  jz      short loc_1800050A9
0x1800050a4  call    Kerb3961Free
0x1800050a9  mov     rax, [rbp+47h+var_70]
0x1800050ad  lea     rcx, [rbp+47h+var_70]
0x1800050b1  mov     rax, [rax]
0x1800050b4  call    _guard_dispatch_icall
0x1800050b9  mov     ebx, dword ptr [rbp+47h+var_B0]
0x1800050bc  test    ebx, ebx
0x1800050be  jns     short loc_1800050F3
0x1800050c0  mov     edx, ebx; char *
0x1800050c2  lea     rcx, aResult; "result"
0x1800050c9  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800050ce  mov     [rdi+14h], rsi
0x1800050d2  mov     [rdi+1Ch], rsi
0x1800050d6  mov     [rdi+24h], esi
0x1800050d9  mov     rcx, [rbp+47h+var_B8]
0x1800050dd  mov     [rdi], rsi
0x1800050e0  mov     [rdi+8], rsi
0x1800050e4  mov     [rdi+10h], ebx
0x1800050e7  test    rcx, rcx
0x1800050ea  jz      short loc_180005129
0x1800050ec  call    Kerb3961Free
0x1800050f1  jmp     short loc_180005129
0x1800050f3  mov     dl, byte ptr [rbp+47h+var_9C]; unsigned __int16 *
0x1800050f6  test    dl, dl
0x1800050f8  jnz     short loc_180005106
0x1800050fa  cmp     [rbp-59h], esi
0x1800050fd  jnz     short loc_18000514D
0x1800050ff  mov     ecx, 80000001h
0x180005104  jmp     short loc_180005109
0x180005106  mov     ecx, [rbp-59h]
0x180005109  mov     rax, [rbp+47h+var_C0]
0x18000510d  mov     [rdi], rax
0x180005110  mov     rax, [rbp+47h+var_B8]
0x180005114  mov     [rdi+8], rax
0x180005118  mov     rax, [rbp-61h]
0x18000511c  mov     [rdi+18h], rax
0x180005120  mov     [rdi+10h], ebx
0x180005123  mov     [rdi+20h], ecx
0x180005126  mov     [rdi+24h], dl
0x180005129  mov     rax, rdi
0x18000512c  mov     rcx, [rbp+47h+var_50]
0x180005130  xor     rcx, rsp; StackCookie
0x180005133  call    __security_check_cookie
0x180005138  add     rsp, 0C8h
0x18000513f  pop     r15
0x180005141  pop     r14
0x180005143  pop     r13
0x180005145  pop     r12
0x180005147  pop     rdi
0x180005148  pop     rsi
0x180005149  pop     rbx
0x18000514a  pop     rbp
0x18000514b  retn
0x18000514d  lea     rcx, aGssApiCannotHa_0; "GSS-API cannot havea QOP when conf = fa"...
0x180005154  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
```
