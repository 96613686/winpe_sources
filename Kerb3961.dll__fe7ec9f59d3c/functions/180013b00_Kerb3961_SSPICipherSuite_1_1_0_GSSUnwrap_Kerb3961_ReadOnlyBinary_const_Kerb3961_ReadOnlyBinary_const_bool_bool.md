# Kerb3961::SSPICipherSuite<1,1,0>::GSSUnwrap(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,bool,bool)

- ea: `0x180013b00`
- end: `0x180013c83`
- name: `?GSSUnwrap@?$SSPICipherSuite@$00$00$0A@@Kerb3961@@EEAA?AU?$ReturnType@UUnwrapResult@Kerb3961@@$1??$DoubleGetter@UUnwrapResult@Kerb3961@@UOwnedBinary@2@$0A@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$DoubleSetter@UUnwrapResult@Kerb3961@@UOwnedBinary@2@$0A@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0_N1@Z`
- size: `387`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *, __int64, char, char)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x180001d64`
- `0x180002c64`
- `0x180002fc0`
- `0x1800033f4`
- `0x180013b00`
- `0x18001e010`

## pseudocode

```c
__int64 __fastcall Kerb3961::SSPICipherSuite<1,1,0>::GSSUnwrap(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        __int64 a4,
        char a5,
        char a6)
{
  __int64 (__fastcall *v7)(__int64, _BYTE *, _QWORD *, _QWORD *, __int64, char, char); // rax
  __int64 v8; // rsi
  int v9; // r8d
  void *v10; // rcx
  int v11; // eax
  __int64 v12; // r9
  const unsigned __int16 *v13; // rdx
  int v14; // esi
  void *v15; // rcx
  _QWORD v17[2]; // [rsp+40h] [rbp-39h] BYREF
  __int64 v18; // [rsp+50h] [rbp-29h]
  void *v19; // [rsp+58h] [rbp-21h]
  _BYTE v20[20]; // [rsp+60h] [rbp-19h] BYREF
  int v21; // [rsp+74h] [rbp-5h]
  _BYTE v22[8]; // [rsp+78h] [rbp-1h] BYREF
  void *v23; // [rsp+80h] [rbp+7h]

  if ( *a3 <= 0xFFFFFFFFFFFF0000uLL )
  {
    v7 = *(__int64 (__fastcall **)(__int64, _BYTE *, _QWORD *, _QWORD *, __int64, char, char))(*(_QWORD *)a1 + 360LL);
    v21 = 0;
    v18 = 0;
    v19 = 0;
    memset(v20, 0, sizeof(v20));
    v17[0] = 0;
    v17[1] = 0;
    v8 = v7(a1, v22, a3, v17, a4, a5, a6);
    if ( v19 )
      operator delete(v19, 0);
    v18 = *(_QWORD *)v8;
    v10 = *(void **)(v8 + 8);
    *(_QWORD *)v8 = 0;
    v19 = v10;
    v11 = *(_DWORD *)(v8 + 16);
    *(_QWORD *)(v8 + 8) = 0;
    *(_DWORD *)v20 = v11;
    *(_DWORD *)(v8 + 16) = -1073741823;
    v12 = *(_QWORD *)(v8 + 24);
    *(_QWORD *)&v20[8] = v12;
    v13 = (const unsigned __int16 *)*(unsigned int *)(v8 + 32);
    *(_DWORD *)&v20[16] = *(_DWORD *)(v8 + 32);
    LOBYTE(v9) = *(_BYTE *)(v8 + 36);
    LOBYTE(v21) = v9;
    if ( v23 )
    {
      operator delete(v23, 0);
      LOBYTE(v9) = v21;
      v13 = (const unsigned __int16 *)*(unsigned int *)&v20[16];
      v12 = *(_QWORD *)&v20[8];
    }
    v14 = *(_DWORD *)v20;
    if ( *(int *)v20 >= 0 )
    {
      if ( !(_BYTE)v9 )
      {
        if ( (_DWORD)v13 )
          Kerb3961::ConsistencyFail((Kerb3961 *)L"GSS-API cannot havea QOP when conf = false", v13);
        LODWORD(v13) = -2147483647;
      }
      *(_QWORD *)a2 = v18;
      *(_QWORD *)(a2 + 8) = v19;
      *(_DWORD *)(a2 + 16) = v14;
      *(_QWORD *)(a2 + 24) = v12;
      *(_DWORD *)(a2 + 32) = (_DWORD)v13;
      *(_BYTE *)(a2 + 36) = v9;
    }
    else
    {
      Kerb3961::Logging::Verify::StatusFailed(
        (Kerb3961::Logging::Verify *)"result",
        (const char *)*(unsigned int *)v20,
        v9);
      *(_QWORD *)(a2 + 20) = 0;
      *(_QWORD *)(a2 + 28) = 0;
      *(_DWORD *)(a2 + 36) = 0;
      v15 = v19;
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = v14;
      if ( v15 )
        operator delete(v15, 0);
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
0x180013b00  push    rbp
0x180013b02  push    rbx
0x180013b03  push    rsi
0x180013b04  push    rdi
0x180013b05  lea     rbp, [rsp-2Fh]
0x180013b0a  sub     rsp, 0A8h
0x180013b11  cmp     qword ptr [r8], 0FFFFFFFFFFFF0000h
0x180013b18  mov     rbx, rdx
0x180013b1b  mov     r10, rcx
0x180013b1e  jbe     short loc_180013B4C
0x180013b20  lea     rcx, aInputmessageLe_0; "inputMessage.length <= MessageLimit"
0x180013b27  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180013b2c  xor     edi, edi
0x180013b2e  mov     [rbx+14h], rdi
0x180013b32  mov     [rbx+1Ch], rdi
0x180013b36  mov     [rbx+24h], edi
0x180013b39  mov     [rbx], rdi
0x180013b3c  mov     [rbx+8], rdi
0x180013b40  mov     dword ptr [rbx+10h], 0C0000095h
0x180013b47  jmp     loc_180013C67
0x180013b4c  mov     rax, [rcx]
0x180013b4f  lea     rdx, [rbp+47h+var_48]
0x180013b53  mov     cl, [rbp+47h+arg_28]
0x180013b56  xor     edi, edi
0x180013b58  mov     [rsp+0C0h+var_90], cl
0x180013b5c  xorps   xmm0, xmm0
0x180013b5f  mov     cl, [rbp+47h+arg_20]
0x180013b62  mov     rax, [rax+168h]
0x180013b69  mov     [rsp+0C0h+var_98], cl
0x180013b6d  mov     rcx, r10
0x180013b70  mov     [rsp+0C0h+var_A0], r9
0x180013b75  lea     r9, [rbp+47h+var_80]
0x180013b79  movdqu  xmmword ptr [rbp+47h+var_60+4], xmm0
0x180013b7e  mov     [rbp+47h+var_4C], edi
0x180013b81  mov     [rbp+47h+var_70], rdi
0x180013b85  mov     [rbp+47h+var_68], rdi
0x180013b89  mov     dword ptr [rbp+47h+var_60], edi
0x180013b8c  mov     [rbp+47h+var_80], rdi
0x180013b90  mov     [rbp+47h+var_78], rdi
0x180013b94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b99  mov     rcx, [rbp+47h+var_68]; void *
0x180013b9d  mov     rsi, rax
0x180013ba0  test    rcx, rcx
0x180013ba3  jz      short loc_180013BAC
0x180013ba5  xor     edx, edx; struct std::nothrow_t *
0x180013ba7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180013bac  mov     rcx, [rsi]
0x180013baf  mov     [rbp+47h+var_70], rcx
0x180013bb3  mov     rcx, [rsi+8]
0x180013bb7  mov     [rsi], rdi
0x180013bba  mov     [rbp+47h+var_68], rcx
0x180013bbe  mov     eax, [rsi+10h]
0x180013bc1  mov     [rsi+8], rdi
0x180013bc5  mov     dword ptr [rbp+47h+var_60], eax
0x180013bc8  mov     dword ptr [rsi+10h], 0C0000001h
0x180013bcf  mov     r9, [rsi+18h]
0x180013bd3  mov     rcx, [rbp+47h+var_40]; void *
0x180013bd7  mov     qword ptr [rbp+47h+var_60+8], r9
0x180013bdb  mov     edx, [rsi+20h]
0x180013bde  mov     dword ptr [rbp+47h+var_60+10h], edx
0x180013be1  mov     r8b, [rsi+24h]
0x180013be5  mov     byte ptr [rbp+47h+var_4C], r8b
0x180013be9  test    rcx, rcx
0x180013bec  jz      short loc_180013C00
0x180013bee  xor     edx, edx; struct std::nothrow_t *
0x180013bf0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180013bf5  mov     r8b, byte ptr [rbp+47h+var_4C]; int
0x180013bf9  mov     edx, dword ptr [rbp+47h+var_60+10h]; unsigned __int16 *
0x180013bfc  mov     r9, qword ptr [rbp+47h+var_60+8]
0x180013c00  mov     esi, dword ptr [rbp+47h+var_60]
0x180013c03  test    esi, esi
0x180013c05  jns     short loc_180013C3C
0x180013c07  mov     edx, esi; char *
0x180013c09  lea     rcx, aResult; "result"
0x180013c10  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180013c15  mov     [rbx+14h], rdi
0x180013c19  mov     [rbx+1Ch], rdi
0x180013c1d  mov     [rbx+24h], edi
0x180013c20  mov     rcx, [rbp+47h+var_68]; void *
0x180013c24  mov     [rbx], rdi
0x180013c27  mov     [rbx+8], rdi
0x180013c2b  mov     [rbx+10h], esi
0x180013c2e  test    rcx, rcx
0x180013c31  jz      short loc_180013C67
0x180013c33  xor     edx, edx; struct std::nothrow_t *
0x180013c35  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180013c3a  jmp     short loc_180013C67
0x180013c3c  test    r8b, r8b
0x180013c3f  jnz     short loc_180013C4A
0x180013c41  test    edx, edx
0x180013c43  jnz     short loc_180013C76
0x180013c45  mov     edx, 80000001h
0x180013c4a  mov     rax, [rbp+47h+var_70]
0x180013c4e  mov     [rbx], rax
0x180013c51  mov     rax, [rbp+47h+var_68]
0x180013c55  mov     [rbx+8], rax
0x180013c59  mov     [rbx+10h], esi
0x180013c5c  mov     [rbx+18h], r9
0x180013c60  mov     [rbx+20h], edx
0x180013c63  mov     [rbx+24h], r8b
0x180013c67  mov     rax, rbx
0x180013c6a  add     rsp, 0A8h
0x180013c71  pop     rdi
0x180013c72  pop     rsi
0x180013c73  pop     rbx
0x180013c74  pop     rbp
0x180013c75  retn
0x180013c76  lea     rcx, aGssApiCannotHa_0; "GSS-API cannot havea QOP when conf = fa"...
0x180013c7d  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
```
