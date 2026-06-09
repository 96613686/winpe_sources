# BprocessParam

- ea: `0x180072540`
- end: `0x180072869`
- name: `BprocessParam`
- size: `809`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18000aafc`
- `0x18000bdc8`

## callees

- `0x180007220`
- `0x18000aa88`
- `0x18000aef4`
- `0x18000b354`
- `0x18000b848`
- `0x18000bf30`
- `0x18000c15c`
- `0x1800335c8`
- `0x1800487e0`
- `0x180072540`

## string_xrefs

- `0x1800725b2`: `Command parameter: Missing format character.`
- `0x180072676`: `Command parameter: Syntax error in format width field.`
- `0x18007263c`: `Command parameter: Unexpected chars found preceeding format specifier: '%0.*s'.`
- `0x1800726af`: `Command parameter: missing '{' in Value construct.`
- `0x1800726cd`: `Command parameter: unexpected chars found preceeding Limits or Value construct: '%0.*s'.`
- `0x180072702`: `Command parameter: missing comma delimiter in Limits construct.`
- `0x18007272c`: `Command parameter: syntax error in Min Limit field.`
- `0x180072762`: `Command parameter: missing closing bracket in Limits construct.`
- `0x18007278c`: `Command parameter: syntax error in Max Limit field.`
- `0x1800727ba`: `Command parameter: missing required '{' in Value construct.`

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
  if ( !(unsigned int)BeatDelimiter(a1, "%") )
    return 0;
  if ( !(unsigned int)BdelimitToken(a1, "dDcClmqgnvf", &v16, &v15) )
  {
    WriteDbgTraceErrorGpd("BprocessParam", "Command parameter: Missing format character.");
    return 0;
  }
  v6 = *(_QWORD *)(a3 + 120);
  if ( !(unsigned int)BallocElementFromMasterTable(5, &v18, a3) )
    return 0;
  v7 = v18;
  v8 = (unsigned int)v15;
  v9 = 28LL * v18;
  *(_DWORD *)(v9 + v6 + 8) = 0;
  *(_DWORD *)(v9 + v6) = (unsigned __int8)aDdcclmqgnvf[v8];
  BeatLeadingWhiteSpaces(&v16);
  if ( DWORD2(v16) )
  {
    if ( ((aDdcclmqgnvf[v10] - 68) & 0xDF) != 0 )
    {
      WriteDbgTraceErrorGpd(
        "BprocessParam",
        "Command parameter: Unexpected chars found preceeding format specifier: '%0.*s'.",
        DWORD2(v16),
        (_QWORD)v16);
      return 0;
    }
    if ( !(unsigned int)BparseInteger(&v16, v9 + v6 + 4, 1, a3) )
    {
      WriteDbgTraceErrorGpd("BprocessParam", "Command parameter: Syntax error in format width field.");
      return 0;
    }
    if ( *(_DWORD *)(v9 + v6 + 4) != 0x80000000 )
      *(_DWORD *)(v9 + v6 + 8) |= 4u;
  }
  if ( !(unsigned int)BdelimitToken(a1, "[{", &v16, &v15) )
  {
    WriteDbgTraceErrorGpd("BprocessParam", "Command parameter: missing '{' in Value construct.");
    return 0;
  }
  BeatLeadingWhiteSpaces(&v16);
  if ( DWORD2(v16) )
  {
    WriteDbgTraceErrorGpd(
      "BprocessParam",
      "Command parameter: unexpected chars found preceeding Limits or Value construct: '%0.*s'.",
      DWORD2(v16),
      (_QWORD)v16);
    return 0;
  }
  if ( asc_180087420[(unsigned int)v15] == 91 )
  {
    if ( !(unsigned int)BdelimitToken(a1, ",", &v16, &v15) )
    {
      WriteDbgTraceErrorGpd("BprocessParam", "Command parameter: missing comma delimiter in Limits construct.");
      return 0;
    }
    if ( !(unsigned int)BparseInteger(&v16, v9 + v6 + 12, 1, a3) )
    {
      WriteDbgTraceErrorGpd("BprocessParam", "Command parameter: syntax error in Min Limit field.");
      return 0;
    }
    if ( *(_DWORD *)(v9 + v6 + 12) != 0x80000000 )
      *(_DWORD *)(v9 + v6 + 8) |= 1u;
    if ( !(unsigned int)BdelimitToken(a1, "]", &v16, &v15) )
    {
      WriteDbgTraceErrorGpd("BprocessParam", "Command parameter: missing closing bracket in Limits construct.");
      return 0;
    }
    if ( !(unsigned int)BparseInteger(&v16, v9 + v6 + 16, 1, a3) )
    {
      WriteDbgTraceErrorGpd("BprocessParam", "Command parameter: syntax error in Max Limit field.");
      return 0;
    }
    if ( *(_DWORD *)(v9 + v6 + 16) != 0x80000000 )
      *(_DWORD *)(v9 + v6 + 8) |= 2u;
    if ( !(unsigned int)BeatDelimiter(a1, "{") )
    {
      WriteDbgTraceErrorGpd("BprocessParam", "Command parameter: missing required '{' in Value construct.");
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
  v12 = BwriteToHeap((char *)&v15 + 4, &v18, 5, 1, a3);
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
0x180072540  mov     [rsp-38h+arg_18], rbx
0x180072545  push    rbp
0x180072546  push    rsi
0x180072547  push    rdi
0x180072548  push    r12
0x18007254a  push    r13
0x18007254c  push    r14
0x18007254e  push    r15
0x180072550  mov     rbp, rsp
0x180072553  sub     rsp, 60h
0x180072557  mov     rax, cs:__security_cookie
0x18007255e  xor     rax, rsp
0x180072561  mov     [rbp+var_8], rax
0x180072565  mov     [rbp+var_18], rdx
0x180072569  xorps   xmm0, xmm0
0x18007256c  lea     rdx, asc_18008734C; "%"
0x180072573  mov     [rbp+var_10], 0
0x18007257a  movups  [rbp+var_28], xmm0
0x18007257e  mov     r14, r8
0x180072581  mov     dword ptr [rbp+var_30], 0
0x180072588  mov     rsi, rcx
0x18007258b  call    BeatDelimiter
0x180072590  test    eax, eax
0x180072592  jz      short loc_1800725C5
0x180072594  lea     r13, aDdcclmqgnvf; "dDcClmqgnvf"
0x18007259b  mov     rcx, rsi
0x18007259e  mov     rdx, r13
0x1800725a1  lea     r9, [rbp+var_30]
0x1800725a5  lea     r8, [rbp+var_28]
0x1800725a9  call    BdelimitToken
0x1800725ae  test    eax, eax
0x1800725b0  jnz     short loc_1800725EB
0x1800725b2  lea     rdx, aCommandParamet_16; "Command parameter: Missing format chara"...
0x1800725b9  lea     rcx, aBprocessparam; "BprocessParam"
0x1800725c0  call    WriteDbgTraceErrorGpd
0x1800725c5  xor     eax, eax
0x1800725c7  mov     rcx, [rbp+var_8]
0x1800725cb  xor     rcx, rsp; StackCookie
0x1800725ce  call    __security_check_cookie
0x1800725d3  mov     rbx, [rsp+60h+arg_18]
0x1800725db  add     rsp, 60h
0x1800725df  pop     r15
0x1800725e1  pop     r14
0x1800725e3  pop     r13
0x1800725e5  pop     r12
0x1800725e7  pop     rdi
0x1800725e8  pop     rsi
0x1800725e9  pop     rbp
0x1800725ea  retn
0x1800725eb  mov     rbx, [r14+78h]
0x1800725ef  lea     rdx, [rbp+var_10]
0x1800725f3  mov     r8, r14
0x1800725f6  mov     ecx, 5
0x1800725fb  call    BallocElementFromMasterTable
0x180072600  test    eax, eax
0x180072602  jz      short loc_1800725C5
0x180072604  mov     r15d, [rbp+var_10]
0x180072608  lea     rcx, [rbp+var_28]
0x18007260c  mov     r9d, dword ptr [rbp+var_30]
0x180072610  imul    rdi, r15, 1Ch
0x180072614  mov     dword ptr [rdi+rbx+8], 0
0x18007261c  movzx   eax, byte ptr [r9+r13]
0x180072621  mov     [rdi+rbx], eax
0x180072624  call    BeatLeadingWhiteSpaces
0x180072629  mov     r8d, dword ptr [rbp+var_28+8]
0x18007262d  test    r8d, r8d
0x180072630  jz      short loc_180072691
0x180072632  mov     al, [r9+r13]
0x180072636  sub     al, 44h ; 'D'
0x180072638  test    al, 0DFh
0x18007263a  jz      short loc_180072658
0x18007263c  lea     rdx, aCommandParamet_15; "Command parameter: Unexpected chars fou"...
0x180072643  mov     r9, qword ptr [rbp+var_28]
0x180072647  lea     rcx, aBprocessparam; "BprocessParam"
0x18007264e  call    WriteDbgTraceErrorGpd
0x180072653  jmp     loc_1800725C5
0x180072658  lea     r13, [rdi+rbx]
0x18007265c  mov     r9, r14
0x18007265f  lea     rdx, [r13+4]
0x180072663  mov     r8d, 1
0x180072669  lea     rcx, [rbp+var_28]
0x18007266d  call    BparseInteger
0x180072672  test    eax, eax
0x180072674  jnz     short loc_180072682
0x180072676  lea     rdx, aCommandParamet_0; "Command parameter: Syntax error in form"...
0x18007267d  jmp     loc_1800725B9
0x180072682  cmp     dword ptr [r13+4], 80000000h
0x18007268a  jz      short loc_180072691
0x18007268c  or      dword ptr [rdi+rbx+8], 4
0x180072691  lea     r13, asc_180087420; "[{"
0x180072698  mov     rcx, rsi
0x18007269b  mov     rdx, r13
0x18007269e  lea     r9, [rbp+var_30]
0x1800726a2  lea     r8, [rbp+var_28]
0x1800726a6  call    BdelimitToken
0x1800726ab  test    eax, eax
0x1800726ad  jnz     short loc_1800726BB
0x1800726af  lea     rdx, aCommandParamet_6; "Command parameter: missing '{' in Value"...
0x1800726b6  jmp     loc_1800725B9
0x1800726bb  lea     rcx, [rbp+var_28]
0x1800726bf  call    BeatLeadingWhiteSpaces
0x1800726c4  mov     r8d, dword ptr [rbp+var_28+8]
0x1800726c8  test    r8d, r8d
0x1800726cb  jz      short loc_1800726D9
0x1800726cd  lea     rdx, aCommandParamet_5; "Command parameter: unexpected chars fou"...
0x1800726d4  jmp     loc_180072643
0x1800726d9  mov     eax, dword ptr [rbp+var_30]
0x1800726dc  cmp     byte ptr [rax+r13], 5Bh ; '['
0x1800726e1  jnz     loc_1800727C6
0x1800726e7  lea     r9, [rbp+var_30]
0x1800726eb  mov     rcx, rsi
0x1800726ee  lea     r8, [rbp+var_28]
0x1800726f2  lea     rdx, asc_18007FAE4; ","
0x1800726f9  call    BdelimitToken
0x1800726fe  test    eax, eax
0x180072700  jnz     short loc_18007270E
0x180072702  lea     rdx, aCommandParamet_3; "Command parameter: missing comma delimi"...
0x180072709  jmp     loc_1800725B9
0x18007270e  lea     r13, [rdi+rbx]
0x180072712  mov     r9, r14
0x180072715  lea     rdx, [r13+0Ch]
0x180072719  mov     r8d, 1
0x18007271f  lea     rcx, [rbp+var_28]
0x180072723  call    BparseInteger
0x180072728  test    eax, eax
0x18007272a  jnz     short loc_180072738
0x18007272c  lea     rdx, aCommandParamet_13; "Command parameter: syntax error in Min "...
0x180072733  jmp     loc_1800725B9
0x180072738  cmp     dword ptr [r13+0Ch], 80000000h
0x180072740  jz      short loc_180072747
0x180072742  or      dword ptr [rdi+rbx+8], 1
0x180072747  lea     r9, [rbp+var_30]
0x18007274b  mov     rcx, rsi
0x18007274e  lea     r8, [rbp+var_28]
0x180072752  lea     rdx, asc_180087534; "]"
0x180072759  call    BdelimitToken
0x18007275e  test    eax, eax
0x180072760  jnz     short loc_18007276E
0x180072762  lea     rdx, aCommandParamet_1; "Command parameter: missing closing brac"...
0x180072769  jmp     loc_1800725B9
0x18007276e  lea     r13, [rdi+rbx]
0x180072772  mov     r9, r14
0x180072775  lea     rdx, [r13+10h]
0x180072779  mov     r8d, 1
0x18007277f  lea     rcx, [rbp+var_28]
0x180072783  call    BparseInteger
0x180072788  test    eax, eax
0x18007278a  jnz     short loc_180072798
0x18007278c  lea     rdx, aCommandParamet_4; "Command parameter: syntax error in Max "...
0x180072793  jmp     loc_1800725B9
0x180072798  cmp     dword ptr [r13+10h], 80000000h
0x1800727a0  jz      short loc_1800727A7
0x1800727a2  or      dword ptr [rdi+rbx+8], 2
0x1800727a7  lea     rdx, asc_18007D74C; "{"
0x1800727ae  mov     rcx, rsi
0x1800727b1  call    BeatDelimiter
0x1800727b6  test    eax, eax
0x1800727b8  jnz     short loc_1800727C6
0x1800727ba  lea     rdx, aCommandParamet_2; "Command parameter: missing required '{'"...
0x1800727c1  jmp     loc_1800725B9
0x1800727c6  lea     rdx, [rdi+14h]
0x1800727ca  mov     r8, r14
0x1800727cd  add     rdx, rbx
0x1800727d0  mov     rcx, rsi
0x1800727d3  call    BconstructRPNtokenStream
0x1800727d8  test    eax, eax
0x1800727da  jz      loc_1800725C5
0x1800727e0  mov     [rbp+var_30], 0
0x1800727e8  mov     r12d, 4
0x1800727ee  mov     byte ptr [rbp+var_10], 25h ; '%'
0x1800727f2  mov     [rbp+var_B], 0
0x1800727f6  mov     eax, 0CCCCCCCDh
0x1800727fb  mul     r15d
0x1800727fe  shr     edx, 3
0x180072801  mov     al, dl
0x180072803  shl     al, 2
0x180072806  lea     ecx, [rax+rdx]
0x180072809  add     cl, cl
0x18007280b  sub     r15b, cl
0x18007280e  add     r15b, 30h ; '0'
0x180072812  mov     byte ptr [rbp+r12+var_10], r15b
0x180072817  mov     r15d, edx
0x18007281a  sub     r12, 1
0x18007281e  jnz     short loc_1800727F6
0x180072820  lea     r9d, [r12+1]
0x180072825  mov     [rsp+60h+var_40], r14
0x18007282a  lea     r8d, [r12+5]
0x18007282f  lea     rdx, [rbp+var_10]
0x180072833  lea     rcx, [rbp+var_30+4]
0x180072837  call    BwriteToHeap
0x18007283c  mov     r12, [rbp+var_18]
0x180072840  test    eax, eax
0x180072842  jz      loc_1800725C5
0x180072848  mov     edx, [r12]
0x18007284c  test    edx, edx
0x18007284e  jnz     short loc_180072858
0x180072850  mov     ecx, dword ptr [rbp+var_30+4]
0x180072853  mov     [r12+4], ecx
0x180072858  lea     ecx, [rdx+5]
0x18007285b  mov     eax, 1
0x180072860  mov     [r12], ecx
0x180072864  jmp     loc_1800725C7
```
