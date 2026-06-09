# BprocessParam

- ea: `0x1800745c8`
- end: `0x1800748f2`
- name: `BprocessParam`
- size: `810`
- prototype: `__int64 __fastcall(__int64, _DWORD *, __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18000aafc`
- `0x18000bdbc`

## callees

- `0x180007150`
- `0x18000aa88`
- `0x18000af00`
- `0x18000b364`
- `0x18000b868`
- `0x18000bf20`
- `0x18000c14c`
- `0x180033f3c`
- `0x180049d00`
- `0x1800745c8`

## string_xrefs

- `0x18007463a`: `Command parameter: Missing format character.`
- `0x1800746ff`: `Command parameter: Syntax error in format width field.`
- `0x1800746c5`: `Command parameter: Unexpected chars found preceeding format specifier: '%0.*s'.`
- `0x180074738`: `Command parameter: missing '{' in Value construct.`
- `0x180074756`: `Command parameter: unexpected chars found preceeding Limits or Value construct: '%0.*s'.`
- `0x18007478b`: `Command parameter: missing comma delimiter in Limits construct.`
- `0x1800747b5`: `Command parameter: syntax error in Min Limit field.`
- `0x1800747eb`: `Command parameter: missing closing bracket in Limits construct.`
- `0x180074815`: `Command parameter: syntax error in Max Limit field.`
- `0x180074843`: `Command parameter: missing required '{' in Value construct.`

## pseudocode

```c
__int64 __fastcall BprocessParam(__int64 a1, _DWORD *a2, __int64 a3)
{
  __int64 result; // rax
  __int64 v6; // rbx
  unsigned int v7; // r15d
  __int64 v8; // r9
  __int64 v9; // rdi
  __int64 v10; // r9
  __int64 v11; // r12
  int v12; // eax
  _DWORD *v13; // r12
  int v14; // edx
  __int64 v15; // [rsp+30h] [rbp-30h] BYREF
  __int128 v16; // [rsp+38h] [rbp-28h] BYREF
  _DWORD *v17; // [rsp+48h] [rbp-18h]
  unsigned int v18; // [rsp+50h] [rbp-10h] BYREF
  char v19; // [rsp+55h] [rbp-Bh]

  v17 = a2;
  v18 = 0;
  v16 = 0;
  LODWORD(v15) = 0;
  if ( !(unsigned int)BeatDelimiter(a1) )
    return 0;
  if ( !(unsigned int)BdelimitToken(a1, (__int64)"dDcClmqgnvf", (__int64)&v16, &v15) )
  {
    WriteDbgTraceErrorGpd((__int64)"BprocessParam", "Command parameter: Missing format character.");
    return 0;
  }
  v6 = *(_QWORD *)(a3 + 120);
  if ( !(unsigned int)BallocElementFromMasterTable(5, &v18, (_DWORD *)a3) )
    return 0;
  v7 = v18;
  v8 = (unsigned int)v15;
  v9 = 28LL * v18;
  *(_DWORD *)(v9 + v6 + 8) = 0;
  *(_DWORD *)(v9 + v6) = (unsigned __int8)aDdcclmqgnvf[v8];
  BeatLeadingWhiteSpaces((__int64)&v16);
  if ( DWORD2(v16) )
  {
    if ( ((aDdcclmqgnvf[v10] - 68) & 0xDF) != 0 )
    {
      WriteDbgTraceErrorGpd(
        (__int64)"BprocessParam",
        "Command parameter: Unexpected chars found preceeding format specifier: '%0.*s'.",
        DWORD2(v16),
        (_QWORD)v16);
      return 0;
    }
    if ( !(unsigned int)BparseInteger((__int64)&v16, (unsigned int *)(v9 + v6 + 4), 1) )
    {
      WriteDbgTraceErrorGpd((__int64)"BprocessParam", "Command parameter: Syntax error in format width field.");
      return 0;
    }
    if ( *(_DWORD *)(v9 + v6 + 4) != 0x80000000 )
      *(_DWORD *)(v9 + v6 + 8) |= 4u;
  }
  if ( !(unsigned int)BdelimitToken(a1, (__int64)"[{", (__int64)&v16, &v15) )
  {
    WriteDbgTraceErrorGpd((__int64)"BprocessParam", "Command parameter: missing '{' in Value construct.");
    return 0;
  }
  BeatLeadingWhiteSpaces((__int64)&v16);
  if ( DWORD2(v16) )
  {
    WriteDbgTraceErrorGpd(
      (__int64)"BprocessParam",
      "Command parameter: unexpected chars found preceeding Limits or Value construct: '%0.*s'.",
      DWORD2(v16),
      (_QWORD)v16);
    return 0;
  }
  if ( asc_180089400[(unsigned int)v15] == 91 )
  {
    if ( !(unsigned int)BdelimitToken(a1, (__int64)",", (__int64)&v16, &v15) )
    {
      WriteDbgTraceErrorGpd((__int64)"BprocessParam", "Command parameter: missing comma delimiter in Limits construct.");
      return 0;
    }
    if ( !(unsigned int)BparseInteger((__int64)&v16, (unsigned int *)(v9 + v6 + 12), 1) )
    {
      WriteDbgTraceErrorGpd((__int64)"BprocessParam", "Command parameter: syntax error in Min Limit field.");
      return 0;
    }
    if ( *(_DWORD *)(v9 + v6 + 12) != 0x80000000 )
      *(_DWORD *)(v9 + v6 + 8) |= 1u;
    if ( !(unsigned int)BdelimitToken(a1, (__int64)"]", (__int64)&v16, &v15) )
    {
      WriteDbgTraceErrorGpd((__int64)"BprocessParam", "Command parameter: missing closing bracket in Limits construct.");
      return 0;
    }
    if ( !(unsigned int)BparseInteger((__int64)&v16, (unsigned int *)(v9 + v6 + 16), 1) )
    {
      WriteDbgTraceErrorGpd((__int64)"BprocessParam", "Command parameter: syntax error in Max Limit field.");
      return 0;
    }
    if ( *(_DWORD *)(v9 + v6 + 16) != 0x80000000 )
      *(_DWORD *)(v9 + v6 + 8) |= 2u;
    if ( !(unsigned int)BeatDelimiter(a1) )
    {
      WriteDbgTraceErrorGpd((__int64)"BprocessParam", "Command parameter: missing required '{' in Value construct.");
      return 0;
    }
  }
  if ( !(unsigned int)BconstructRPNtokenStream(a1, (_DWORD *)(v6 + v9 + 20), a3) )
    return 0;
  v15 = 0;
  v11 = 4;
  LOBYTE(v18) = 37;
  v19 = 0;
  do
  {
    *((_BYTE *)&v18 + v11) = v7 % 0xA + 48;
    v7 /= 0xAu;
    --v11;
  }
  while ( v11 );
  v12 = BwriteToHeap((_DWORD *)&v15 + 1, &v18, 5u, 1u, a3);
  v13 = v17;
  if ( !v12 )
    return 0;
  v14 = *v17;
  if ( !*v17 )
    v17[1] = HIDWORD(v15);
  result = 1;
  *v13 = v14 + 5;
  return result;
}

```

## disassembly

```asm
0x1800745c8  mov     [rsp-38h+arg_18], rbx
0x1800745cd  push    rbp
0x1800745ce  push    rsi
0x1800745cf  push    rdi
0x1800745d0  push    r12
0x1800745d2  push    r13
0x1800745d4  push    r14
0x1800745d6  push    r15
0x1800745d8  mov     rbp, rsp
0x1800745db  sub     rsp, 60h
0x1800745df  mov     rax, cs:__security_cookie
0x1800745e6  xor     rax, rsp
0x1800745e9  mov     [rbp+var_8], rax
0x1800745ed  mov     [rbp+var_18], rdx
0x1800745f1  xorps   xmm0, xmm0
0x1800745f4  lea     rdx, asc_18008932C; "%"
0x1800745fb  mov     [rbp+var_10], 0
0x180074602  movups  [rbp+var_28], xmm0
0x180074606  mov     r14, r8
0x180074609  mov     dword ptr [rbp+var_30], 0
0x180074610  mov     rsi, rcx
0x180074613  call    BeatDelimiter
0x180074618  test    eax, eax
0x18007461a  jz      short loc_18007464D
0x18007461c  lea     r13, aDdcclmqgnvf; "dDcClmqgnvf"
0x180074623  mov     rcx, rsi
0x180074626  mov     rdx, r13
0x180074629  lea     r9, [rbp+var_30]
0x18007462d  lea     r8, [rbp+var_28]
0x180074631  call    BdelimitToken
0x180074636  test    eax, eax
0x180074638  jnz     short loc_180074674
0x18007463a  lea     rdx, aCommandParamet_16; "Command parameter: Missing format chara"...
0x180074641  lea     rcx, aBprocessparam; "BprocessParam"
0x180074648  call    WriteDbgTraceErrorGpd
0x18007464d  xor     eax, eax
0x18007464f  mov     rcx, [rbp+var_8]
0x180074653  xor     rcx, rsp; StackCookie
0x180074656  call    __security_check_cookie
0x18007465b  mov     rbx, [rsp+60h+arg_18]
0x180074663  add     rsp, 60h
0x180074667  pop     r15
0x180074669  pop     r14
0x18007466b  pop     r13
0x18007466d  pop     r12
0x18007466f  pop     rdi
0x180074670  pop     rsi
0x180074671  pop     rbp
0x180074672  retn
0x180074674  mov     rbx, [r14+78h]
0x180074678  lea     rdx, [rbp+var_10]
0x18007467c  mov     r8, r14
0x18007467f  mov     ecx, 5
0x180074684  call    BallocElementFromMasterTable
0x180074689  test    eax, eax
0x18007468b  jz      short loc_18007464D
0x18007468d  mov     r15d, [rbp+var_10]
0x180074691  lea     rcx, [rbp+var_28]
0x180074695  mov     r9d, dword ptr [rbp+var_30]
0x180074699  imul    rdi, r15, 1Ch
0x18007469d  mov     dword ptr [rdi+rbx+8], 0
0x1800746a5  movzx   eax, byte ptr [r9+r13]
0x1800746aa  mov     [rdi+rbx], eax
0x1800746ad  call    BeatLeadingWhiteSpaces
0x1800746b2  mov     r8d, dword ptr [rbp+var_28+8]
0x1800746b6  test    r8d, r8d
0x1800746b9  jz      short loc_18007471A
0x1800746bb  mov     al, [r9+r13]
0x1800746bf  sub     al, 44h ; 'D'
0x1800746c1  test    al, 0DFh
0x1800746c3  jz      short loc_1800746E1
0x1800746c5  lea     rdx, aCommandParamet_15; "Command parameter: Unexpected chars fou"...
0x1800746cc  mov     r9, qword ptr [rbp+var_28]
0x1800746d0  lea     rcx, aBprocessparam; "BprocessParam"
0x1800746d7  call    WriteDbgTraceErrorGpd
0x1800746dc  jmp     loc_18007464D
0x1800746e1  lea     r13, [rdi+rbx]
0x1800746e5  mov     r9, r14
0x1800746e8  lea     rdx, [r13+4]
0x1800746ec  mov     r8d, 1
0x1800746f2  lea     rcx, [rbp+var_28]
0x1800746f6  call    BparseInteger
0x1800746fb  test    eax, eax
0x1800746fd  jnz     short loc_18007470B
0x1800746ff  lea     rdx, aCommandParamet_0; "Command parameter: Syntax error in form"...
0x180074706  jmp     loc_180074641
0x18007470b  cmp     dword ptr [r13+4], 80000000h
0x180074713  jz      short loc_18007471A
0x180074715  or      dword ptr [rdi+rbx+8], 4
0x18007471a  lea     r13, asc_180089400; "[{"
0x180074721  mov     rcx, rsi
0x180074724  mov     rdx, r13
0x180074727  lea     r9, [rbp+var_30]
0x18007472b  lea     r8, [rbp+var_28]
0x18007472f  call    BdelimitToken
0x180074734  test    eax, eax
0x180074736  jnz     short loc_180074744
0x180074738  lea     rdx, aCommandParamet_6; "Command parameter: missing '{' in Value"...
0x18007473f  jmp     loc_180074641
0x180074744  lea     rcx, [rbp+var_28]
0x180074748  call    BeatLeadingWhiteSpaces
0x18007474d  mov     r8d, dword ptr [rbp+var_28+8]
0x180074751  test    r8d, r8d
0x180074754  jz      short loc_180074762
0x180074756  lea     rdx, aCommandParamet_5; "Command parameter: unexpected chars fou"...
0x18007475d  jmp     loc_1800746CC
0x180074762  mov     eax, dword ptr [rbp+var_30]
0x180074765  cmp     byte ptr [rax+r13], 5Bh ; '['
0x18007476a  jnz     loc_18007484F
0x180074770  lea     r9, [rbp+var_30]
0x180074774  mov     rcx, rsi
0x180074777  lea     r8, [rbp+var_28]
0x18007477b  lea     rdx, asc_180081AE4; ","
0x180074782  call    BdelimitToken
0x180074787  test    eax, eax
0x180074789  jnz     short loc_180074797
0x18007478b  lea     rdx, aCommandParamet_3; "Command parameter: missing comma delimi"...
0x180074792  jmp     loc_180074641
0x180074797  lea     r13, [rdi+rbx]
0x18007479b  mov     r9, r14
0x18007479e  lea     rdx, [r13+0Ch]
0x1800747a2  mov     r8d, 1
0x1800747a8  lea     rcx, [rbp+var_28]
0x1800747ac  call    BparseInteger
0x1800747b1  test    eax, eax
0x1800747b3  jnz     short loc_1800747C1
0x1800747b5  lea     rdx, aCommandParamet_13; "Command parameter: syntax error in Min "...
0x1800747bc  jmp     loc_180074641
0x1800747c1  cmp     dword ptr [r13+0Ch], 80000000h
0x1800747c9  jz      short loc_1800747D0
0x1800747cb  or      dword ptr [rdi+rbx+8], 1
0x1800747d0  lea     r9, [rbp+var_30]
0x1800747d4  mov     rcx, rsi
0x1800747d7  lea     r8, [rbp+var_28]
0x1800747db  lea     rdx, asc_180089514; "]"
0x1800747e2  call    BdelimitToken
0x1800747e7  test    eax, eax
0x1800747e9  jnz     short loc_1800747F7
0x1800747eb  lea     rdx, aCommandParamet_1; "Command parameter: missing closing brac"...
0x1800747f2  jmp     loc_180074641
0x1800747f7  lea     r13, [rdi+rbx]
0x1800747fb  mov     r9, r14
0x1800747fe  lea     rdx, [r13+10h]
0x180074802  mov     r8d, 1
0x180074808  lea     rcx, [rbp+var_28]
0x18007480c  call    BparseInteger
0x180074811  test    eax, eax
0x180074813  jnz     short loc_180074821
0x180074815  lea     rdx, aCommandParamet_4; "Command parameter: syntax error in Max "...
0x18007481c  jmp     loc_180074641
0x180074821  cmp     dword ptr [r13+10h], 80000000h
0x180074829  jz      short loc_180074830
0x18007482b  or      dword ptr [rdi+rbx+8], 2
0x180074830  lea     rdx, asc_18007F74C; "{"
0x180074837  mov     rcx, rsi
0x18007483a  call    BeatDelimiter
0x18007483f  test    eax, eax
0x180074841  jnz     short loc_18007484F
0x180074843  lea     rdx, aCommandParamet_2; "Command parameter: missing required '{'"...
0x18007484a  jmp     loc_180074641
0x18007484f  lea     rdx, [rdi+14h]
0x180074853  mov     r8, r14
0x180074856  add     rdx, rbx
0x180074859  mov     rcx, rsi
0x18007485c  call    BconstructRPNtokenStream
0x180074861  test    eax, eax
0x180074863  jz      loc_18007464D
0x180074869  mov     [rbp+var_30], 0
0x180074871  mov     r12d, 4
0x180074877  mov     byte ptr [rbp+var_10], 25h ; '%'
0x18007487b  mov     [rbp+var_B], 0
0x18007487f  mov     eax, 0CCCCCCCDh
0x180074884  mul     r15d
0x180074887  shr     edx, 3
0x18007488a  mov     al, dl
0x18007488c  shl     al, 2
0x18007488f  lea     ecx, [rax+rdx]
0x180074892  add     cl, cl
0x180074894  sub     r15b, cl
0x180074897  add     r15b, 30h ; '0'
0x18007489b  mov     byte ptr [rbp+r12+var_10], r15b
0x1800748a0  mov     r15d, edx
0x1800748a3  sub     r12, 1
0x1800748a7  jnz     short loc_18007487F
0x1800748a9  lea     r9d, [r12+1]
0x1800748ae  mov     [rsp+60h+var_40], r14
0x1800748b3  lea     r8d, [r12+5]
0x1800748b8  lea     rdx, [rbp+var_10]
0x1800748bc  lea     rcx, [rbp+var_30+4]
0x1800748c0  call    BwriteToHeap
0x1800748c5  mov     r12, [rbp+var_18]
0x1800748c9  test    eax, eax
0x1800748cb  jz      loc_18007464D
0x1800748d1  mov     edx, [r12]
0x1800748d5  test    edx, edx
0x1800748d7  jnz     short loc_1800748E1
0x1800748d9  mov     ecx, dword ptr [rbp+var_30+4]
0x1800748dc  mov     [r12+4], ecx
0x1800748e1  lea     ecx, [rdx+5]
0x1800748e4  mov     eax, 1
0x1800748e9  mov     [r12], ecx
0x1800748ed  jmp     loc_18007464F
```
