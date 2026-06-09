# Kerb3961::SSPICipherSuite<1,1,1>::GSSWrap(Kerb3961::ReadOnlyBinary const &,unsigned __int64,uint,Kerb3961::ReadOnlyBinary const &,bool,bool)

- ea: `0x1800051e0`
- end: `0x1800053aa`
- name: `?GSSWrap@?$SSPICipherSuite@$00$00$00@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@_KI0_N2@Z`
- size: `458`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180003910`
- `0x180003a54`
- `0x1800051e0`
- `0x180011760`
- `0x1800118cc`
- `0x180011b40`
- `0x180012240`

## string_xrefs

- `0x1800052c5`: `inputCopy`

## pseudocode

```c
__int64 __fastcall Kerb3961::SSPICipherSuite<1,1,1>::GSSWrap(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        __int64 a4,
        int a5,
        __int64 a6,
        char a7,
        char a8)
{
  int v12; // r8d
  int v13; // r14d
  int v14; // r8d
  int v15; // esi
  void (__fastcall *v16)(__int64, _BYTE *, _BYTE *, _QWORD *, __int64, int, __int64, char, char, _QWORD); // rax
  int v17; // r8d
  int v18; // esi
  _QWORD v20[2]; // [rsp+60h] [rbp-39h] BYREF
  _BYTE v21[8]; // [rsp+70h] [rbp-29h] BYREF
  __int64 v22; // [rsp+78h] [rbp-21h]
  char *v23; // [rsp+80h] [rbp-19h]
  _BYTE v24[8]; // [rsp+88h] [rbp-11h] BYREF
  __int64 v25; // [rsp+90h] [rbp-9h]
  char *v26; // [rsp+98h] [rbp-1h]

  if ( *a3 <= 0xFFFFFFFFFFFF0000uLL )
  {
    if ( a5 == -2147483647 )
    {
      (*(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a1 + 352LL))(a1, v21);
      v13 = (int)v23;
      if ( (int)v23 >= 0 )
      {
        Kerb3961::Concatenate(a2, v21, a3);
      }
      else
      {
        Kerb3961::Logging::Verify::StatusFailed(
          (Kerb3961::Logging::Verify *)"header",
          (const char *)(unsigned int)v23,
          v12);
        *(_QWORD *)a2 = 0;
        *(_QWORD *)(a2 + 8) = 0;
        *(_DWORD *)(a2 + 16) = v13;
      }
    }
    else
    {
      Kerb3961::CopyBuffer(v21, a3);
      v15 = (int)v23;
      if ( (int)v23 >= 0 )
      {
        v16 = *(void (__fastcall **)(__int64, _BYTE *, _BYTE *, _QWORD *, __int64, int, __int64, char, char, _QWORD))(*(_QWORD *)a1 + 344LL);
        v20[0] = 0;
        v20[1] = 0;
        v16(a1, v24, v21, v20, a4, a5, a6, a7, a8, 0);
        v18 = (int)v26;
        if ( (int)v26 >= 0 )
        {
          Kerb3961::Concatenate(a2, v24, v21);
        }
        else
        {
          Kerb3961::Logging::Verify::StatusFailed(
            (Kerb3961::Logging::Verify *)"header",
            (const char *)(unsigned int)v26,
            v17);
          *(_QWORD *)a2 = 0;
          *(_QWORD *)(a2 + 8) = 0;
          *(_DWORD *)(a2 + 16) = v18;
        }
        if ( v25 )
          Kerb3961Free(v25);
      }
      else
      {
        Kerb3961::Logging::Verify::StatusFailed(
          (Kerb3961::Logging::Verify *)"inputCopy",
          (const char *)(unsigned int)v23,
          v14);
        *(_QWORD *)a2 = 0;
        *(_QWORD *)(a2 + 8) = 0;
        *(_DWORD *)(a2 + 16) = v15;
      }
    }
    if ( v22 )
      Kerb3961Free(v22);
  }
  else
  {
    Kerb3961::Logging::Verify::ConditionFailed(
      (Kerb3961::Logging::Verify *)"inputMessage.length <= MessageLimit",
      (const char *)a2);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = -1073741675;
  }
  return a2;
}

```

## disassembly

```asm
0x1800051e0  push    rbp
0x1800051e2  push    rsi
0x1800051e3  push    rdi
0x1800051e4  push    r12
0x1800051e6  push    r14
0x1800051e8  push    r15
0x1800051ea  lea     rbp, [rsp-0Fh]
0x1800051ef  sub     rsp, 0A8h
0x1800051f6  cmp     qword ptr [r8], 0FFFFFFFFFFFF0000h
0x1800051fd  mov     r12, r9
0x180005200  mov     rsi, r8
0x180005203  mov     rdi, rdx
0x180005206  mov     r15, rcx
0x180005209  jbe     short loc_180005232
0x18000520b  lea     rcx, aInputmessageLe_0; "inputMessage.length <= MessageLimit"
0x180005212  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180005217  mov     qword ptr [rdi], 0
0x18000521e  mov     qword ptr [rdi+8], 0
0x180005226  mov     dword ptr [rdi+10h], 0C0000095h
0x18000522d  jmp     loc_180005395
0x180005232  mov     r14d, [rbp+37h+arg_20]
0x180005236  cmp     r14d, 80000001h
0x18000523d  jnz     short loc_1800052B0
0x18000523f  mov     rax, [rcx]
0x180005242  lea     rdx, [rbp+37h+var_60]
0x180005246  mov     cl, [rbp+37h+arg_38]
0x180005249  mov     byte ptr [rsp+0D0h+var_A0], cl
0x18000524d  mov     cl, [rbp+37h+arg_30]
0x180005250  mov     rax, [rax+160h]
0x180005257  mov     byte ptr [rsp+0D0h+var_A8], cl
0x18000525b  mov     rcx, [rbp+37h+arg_28]
0x18000525f  mov     [rsp+0D0h+var_B0], rcx
0x180005264  mov     rcx, r15
0x180005267  call    _guard_dispatch_icall
0x18000526c  mov     r14d, dword ptr [rbp+37h+var_50]
0x180005270  test    r14d, r14d
0x180005273  jns     short loc_18000529C
0x180005275  mov     edx, r14d; char *
0x180005278  lea     rcx, aHeader; "header"
0x18000527f  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180005284  mov     qword ptr [rdi], 0
0x18000528b  mov     qword ptr [rdi+8], 0
0x180005293  mov     [rdi+10h], r14d
0x180005297  jmp     loc_180005387
0x18000529c  mov     r8, rsi
0x18000529f  lea     rdx, [rbp+37h+var_60]
0x1800052a3  mov     rcx, rdi
0x1800052a6  call    ?Concatenate@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@0@Z; Kerb3961::Concatenate(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x1800052ab  jmp     loc_180005387
0x1800052b0  mov     rdx, rsi
0x1800052b3  lea     rcx, [rbp+37h+var_60]
0x1800052b7  call    ?CopyBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@@Z; Kerb3961::CopyBuffer(Kerb3961::ReadOnlyBinary const &)
0x1800052bc  mov     esi, dword ptr [rbp+37h+var_50]
0x1800052bf  test    esi, esi
0x1800052c1  jns     short loc_1800052E8
0x1800052c3  mov     edx, esi; char *
0x1800052c5  lea     rcx, aInputcopy; "inputCopy"
0x1800052cc  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800052d1  mov     qword ptr [rdi], 0
0x1800052d8  mov     qword ptr [rdi+8], 0
0x1800052e0  mov     [rdi+10h], esi
0x1800052e3  jmp     loc_180005387
0x1800052e8  mov     cl, [rbp+37h+arg_38]
0x1800052eb  lea     r9, [rbp+37h+var_70]
0x1800052ef  mov     rax, [r15]
0x1800052f2  lea     r8, [rbp+37h+var_60]
0x1800052f6  mov     [rsp+0D0h+var_88], 0
0x1800052ff  lea     rdx, [rbp+37h+var_48]
0x180005303  mov     [rsp+0D0h+var_90], cl
0x180005307  mov     cl, [rbp+37h+arg_30]
0x18000530a  mov     rax, [rax+158h]
0x180005311  mov     [rsp+0D0h+var_98], cl
0x180005315  mov     rcx, [rbp+37h+arg_28]
0x180005319  mov     [rsp+0D0h+var_A0], rcx
0x18000531e  mov     rcx, r15
0x180005321  mov     [rsp+0D0h+var_A8], r14d
0x180005326  mov     [rsp+0D0h+var_B0], r12
0x18000532b  mov     [rbp+37h+var_70], 0
0x180005333  mov     [rbp+37h+var_68], 0
0x18000533b  call    _guard_dispatch_icall
0x180005340  mov     esi, dword ptr [rbp+37h+var_38]
0x180005343  test    esi, esi
0x180005345  jns     short loc_180005369
0x180005347  mov     edx, esi; char *
0x180005349  lea     rcx, aHeader; "header"
0x180005350  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180005355  mov     qword ptr [rdi], 0
0x18000535c  mov     qword ptr [rdi+8], 0
0x180005364  mov     [rdi+10h], esi
0x180005367  jmp     short loc_180005379
0x180005369  lea     r8, [rbp+37h+var_60]
0x18000536d  mov     rcx, rdi
0x180005370  lea     rdx, [rbp+37h+var_48]
0x180005374  call    ?Concatenate@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@0@Z; Kerb3961::Concatenate(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x180005379  mov     rcx, [rbp+37h+var_40]
0x18000537d  test    rcx, rcx
0x180005380  jz      short loc_180005387
0x180005382  call    Kerb3961Free
0x180005387  mov     rcx, [rbp+37h+var_58]
0x18000538b  test    rcx, rcx
0x18000538e  jz      short loc_180005395
0x180005390  call    Kerb3961Free
0x180005395  mov     rax, rdi
0x180005398  add     rsp, 0A8h
0x18000539f  pop     r15
0x1800053a1  pop     r14
0x1800053a3  pop     r12
0x1800053a5  pop     rdi
0x1800053a6  pop     rsi
0x1800053a7  pop     rbp
0x1800053a8  retn
```
