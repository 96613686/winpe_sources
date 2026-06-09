# Kerb3961::SSPICipherSuite<1,1,0>::GSSUnwrap(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,bool,bool)

- ea: `0x180008840`
- end: `0x1800089be`
- name: `?GSSUnwrap@?$SSPICipherSuite@$00$00$0A@@Kerb3961@@EEAA?AU?$ReturnType@UUnwrapResult@Kerb3961@@$1??$DoubleGetter@UUnwrapResult@Kerb3961@@UOwnedBinary@2@$0A@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$DoubleSetter@UUnwrapResult@Kerb3961@@UOwnedBinary@2@$0A@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0_N1@Z`
- size: `382`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180003a38`
- `0x180008840`
- `0x180011760`
- `0x1800118cc`
- `0x180011b40`
- `0x180012240`

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
  __int64 v10; // rcx
  int v11; // eax
  __int64 v12; // r9
  const unsigned __int16 *v13; // rdx
  int v14; // esi
  __int64 v15; // rcx
  _QWORD v17[2]; // [rsp+40h] [rbp-39h] BYREF
  __int64 v18; // [rsp+50h] [rbp-29h]
  __int64 v19; // [rsp+58h] [rbp-21h]
  _BYTE v20[20]; // [rsp+60h] [rbp-19h] BYREF
  int v21; // [rsp+74h] [rbp-5h]
  _BYTE v22[8]; // [rsp+78h] [rbp-1h] BYREF
  __int64 v23; // [rsp+80h] [rbp+7h]

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
      Kerb3961Free(v19);
    v18 = *(_QWORD *)v8;
    v10 = *(_QWORD *)(v8 + 8);
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
      Kerb3961Free(v23);
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
        Kerb3961Free(v15);
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
0x180008840  push    rbp
0x180008842  push    rbx
0x180008843  push    rsi
0x180008844  push    rdi
0x180008845  lea     rbp, [rsp-2Fh]
0x18000884a  sub     rsp, 0A8h
0x180008851  cmp     qword ptr [r8], 0FFFFFFFFFFFF0000h
0x180008858  mov     rbx, rdx
0x18000885b  mov     r10, rcx
0x18000885e  jbe     short loc_18000888C
0x180008860  lea     rcx, aInputmessageLe_0; "inputMessage.length <= MessageLimit"
0x180008867  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000886c  xor     edi, edi
0x18000886e  mov     [rbx+14h], rdi
0x180008872  mov     [rbx+1Ch], rdi
0x180008876  mov     [rbx+24h], edi
0x180008879  mov     [rbx], rdi
0x18000887c  mov     [rbx+8], rdi
0x180008880  mov     dword ptr [rbx+10h], 0C0000095h
0x180008887  jmp     loc_1800089A1
0x18000888c  mov     rax, [rcx]
0x18000888f  lea     rdx, [rbp+47h+var_48]
0x180008893  mov     cl, [rbp+47h+arg_28]
0x180008896  xor     edi, edi
0x180008898  mov     [rsp+0C0h+var_90], cl
0x18000889c  xorps   xmm0, xmm0
0x18000889f  mov     cl, [rbp+47h+arg_20]
0x1800088a2  mov     rax, [rax+168h]
0x1800088a9  mov     [rsp+0C0h+var_98], cl
0x1800088ad  mov     rcx, r10
0x1800088b0  mov     [rsp+0C0h+var_A0], r9
0x1800088b5  lea     r9, [rbp+47h+var_80]
0x1800088b9  movdqu  xmmword ptr [rbp+47h+var_60+4], xmm0
0x1800088be  mov     [rbp+47h+var_4C], edi
0x1800088c1  mov     [rbp+47h+var_70], rdi
0x1800088c5  mov     [rbp+47h+var_68], rdi
0x1800088c9  mov     dword ptr [rbp+47h+var_60], edi
0x1800088cc  mov     [rbp+47h+var_80], rdi
0x1800088d0  mov     [rbp+47h+var_78], rdi
0x1800088d4  call    _guard_dispatch_icall
0x1800088d9  mov     rcx, [rbp+47h+var_68]
0x1800088dd  mov     rsi, rax
0x1800088e0  test    rcx, rcx
0x1800088e3  jz      short loc_1800088EA
0x1800088e5  call    Kerb3961Free
0x1800088ea  mov     rcx, [rsi]
0x1800088ed  mov     [rbp+47h+var_70], rcx
0x1800088f1  mov     rcx, [rsi+8]
0x1800088f5  mov     [rsi], rdi
0x1800088f8  mov     [rbp+47h+var_68], rcx
0x1800088fc  mov     eax, [rsi+10h]
0x1800088ff  mov     [rsi+8], rdi
0x180008903  mov     dword ptr [rbp+47h+var_60], eax
0x180008906  mov     dword ptr [rsi+10h], 0C0000001h
0x18000890d  mov     r9, [rsi+18h]
0x180008911  mov     rcx, [rbp+47h+var_40]
0x180008915  mov     qword ptr [rbp+47h+var_60+8], r9
0x180008919  mov     edx, [rsi+20h]
0x18000891c  mov     dword ptr [rbp+47h+var_60+10h], edx
0x18000891f  mov     r8b, [rsi+24h]
0x180008923  mov     byte ptr [rbp+47h+var_4C], r8b
0x180008927  test    rcx, rcx
0x18000892a  jz      short loc_18000893C
0x18000892c  call    Kerb3961Free
0x180008931  mov     r8b, byte ptr [rbp+47h+var_4C]; int
0x180008935  mov     edx, dword ptr [rbp+47h+var_60+10h]; unsigned __int16 *
0x180008938  mov     r9, qword ptr [rbp+47h+var_60+8]
0x18000893c  mov     esi, dword ptr [rbp+47h+var_60]
0x18000893f  test    esi, esi
0x180008941  jns     short loc_180008976
0x180008943  mov     edx, esi; char *
0x180008945  lea     rcx, aResult; "result"
0x18000894c  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180008951  mov     [rbx+14h], rdi
0x180008955  mov     [rbx+1Ch], rdi
0x180008959  mov     [rbx+24h], edi
0x18000895c  mov     rcx, [rbp+47h+var_68]
0x180008960  mov     [rbx], rdi
0x180008963  mov     [rbx+8], rdi
0x180008967  mov     [rbx+10h], esi
0x18000896a  test    rcx, rcx
0x18000896d  jz      short loc_1800089A1
0x18000896f  call    Kerb3961Free
0x180008974  jmp     short loc_1800089A1
0x180008976  test    r8b, r8b
0x180008979  jnz     short loc_180008984
0x18000897b  test    edx, edx
0x18000897d  jnz     short loc_1800089B1
0x18000897f  mov     edx, 80000001h
0x180008984  mov     rax, [rbp+47h+var_70]
0x180008988  mov     [rbx], rax
0x18000898b  mov     rax, [rbp+47h+var_68]
0x18000898f  mov     [rbx+8], rax
0x180008993  mov     [rbx+10h], esi
0x180008996  mov     [rbx+18h], r9
0x18000899a  mov     [rbx+20h], edx
0x18000899d  mov     [rbx+24h], r8b
0x1800089a1  mov     rax, rbx
0x1800089a4  add     rsp, 0A8h
0x1800089ab  pop     rdi
0x1800089ac  pop     rsi
0x1800089ad  pop     rbx
0x1800089ae  pop     rbp
0x1800089af  retn
0x1800089b1  lea     rcx, aGssApiCannotHa_0; "GSS-API cannot havea QOP when conf = fa"...
0x1800089b8  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
```
