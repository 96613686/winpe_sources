# BconstructRPNtokenStream

- ea: `0x18000b848`
- end: `0x18000bcab`
- name: `BconstructRPNtokenStream`
- size: `1123`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180072540`

## callees

- `0x180007220`
- `0x18000aa88`
- `0x18000b848`
- `0x18000c818`
- `0x180045aa4`

## string_xrefs

- `0x18000b8fd`: `Command parameter: arithmetic syntax error in value construct.`
- `0x18000b96f`: `Command parameter: arithmetic syntax error in value construct.`
- `0x18000bc73`: `Command parameter: arithmetic syntax error in value construct.`
- `0x18000b904`: `BconstructRPNtokenStream`
- `0x18000b995`: `BconstructRPNtokenStream`
- `0x18000b9a8`: `BconstructRPNtokenStream`
- `0x18000bbb7`: `BconstructRPNtokenStream`
- `0x18000bc2d`: `BconstructRPNtokenStream`
- `0x18000bc83`: `BconstructRPNtokenStream`
- `0x18000b98e`: `Command parameter: syntax error in value construct.`
- `0x18000bbb0`: `Command parameter: syntax error in value construct.`
- `0x18000bbc3`: `  comma used outside of function argument list.`
- `0x18000bc7c`: `Command parameter: syntax error in value construct - unmatched  OP_OPENPAR.`
- `0x18000bc26`: `Command parameter: syntax error in value construct - unmatched  OP_CLOSEPAR.`

## pseudocode

```c
__int64 __fastcall BconstructRPNtokenStream(__int64 a1, _DWORD *a2, __int64 a3)
{
  int v3; // edi
  int v4; // r13d
  unsigned int v7; // r14d
  unsigned int v8; // ebx
  int v9; // esi
  bool v10; // zf
  int v11; // ecx
  bool v12; // zf
  const char *v13; // rdx
  _DWORD *v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rdx
  int v17; // eax
  __int64 v18; // rdx
  _DWORD *v19; // rcx
  const char *v20; // rdx
  __int64 v21; // rax
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rax
  unsigned int v26; // [rsp+20h] [rbp-28h]
  __int64 v27; // [rsp+28h] [rbp-20h]
  __int64 v28; // [rsp+30h] [rbp-18h] BYREF
  __int64 v29; // [rsp+38h] [rbp-10h]
  __int64 v30; // [rsp+90h] [rbp+48h]
  unsigned int v31; // [rsp+98h] [rbp+50h] BYREF
  int v32; // [rsp+A0h] [rbp+58h]
  int v33; // [rsp+A8h] [rbp+60h]

  v30 = a1;
  v3 = 0;
  v27 = *(_QWORD *)(a3 + 624);
  v4 = 0;
  v26 = *(_DWORD *)(a3 + 632);
  v7 = 0;
  v29 = *(_QWORD *)(a3 + 144);
  a2[1] = *(_DWORD *)(a3 + 156);
  *a2 = 0;
  v28 = 0;
  v33 = 0;
  v32 = 0;
  v31 = 0;
  while ( 1 )
  {
    v8 = BparseArithmeticToken(a1, &v28, a3);
    if ( !v8 )
      break;
    v9 = HIDWORD(v28);
    if ( SHIDWORD(v28) > 7 )
    {
      if ( HIDWORD(v28) != 8 )
      {
        switch ( HIDWORD(v28) )
        {
          case 9:
            if ( !v3 && !v4 && !v7 )
              goto LABEL_39;
            WriteDbgTraceErrorGpd("BconstructRPNtokenStream", "Command parameter: syntax error in value construct.");
            v13 = "  OP_MAX_REPEAT must appear as the outermost operator only.";
            goto LABEL_33;
          case 0xA:
            goto LABEL_28;
          case 0xB:
LABEL_25:
            v12 = v3 == v4;
            goto LABEL_26;
          case 0xC:
LABEL_28:
            v12 = v3 == v4 + 1;
LABEL_26:
            if ( v12 )
              goto LABEL_39;
            v13 = "Command parameter: arithmetic syntax error in value construct.";
LABEL_33:
            WriteDbgTraceErrorGpd("BconstructRPNtokenStream", v13);
            v8 = 0;
LABEL_34:
            if ( !v8 )
              goto LABEL_93;
            goto LABEL_39;
        }
        v10 = HIDWORD(v28) == 14;
        goto LABEL_20;
      }
    }
    else if ( HIDWORD(v28) != 7 )
    {
      if ( HIDWORD(v28) < 2 )
      {
        if ( v4 != v3 )
        {
          WriteDbgTraceErrorGpd(
            "BconstructRPNtokenStream",
            "Command parameter: arithmetic syntax error in value construct.");
          v8 = 0;
        }
        v33 = ++v3;
        goto LABEL_34;
      }
      if ( HIDWORD(v28) == 2 || HIDWORD(v28) == 3 )
        goto LABEL_25;
      if ( HIDWORD(v28) != 4 && HIDWORD(v28) != 5 )
      {
        v10 = HIDWORD(v28) == 6;
LABEL_20:
        if ( !v10 )
          goto LABEL_39;
      }
    }
    v11 = v4 + 1;
    if ( v4 + 1 == v3 )
    {
      ++v4;
      v32 = v11;
    }
    else
    {
      if ( v11 != v3 + 1 )
        goto LABEL_89;
      v32 = v4;
      if ( HIDWORD(v28) == 5 )
      {
        v9 = 13;
        HIDWORD(v28) = 13;
      }
      else
      {
        if ( HIDWORD(v28) != 4 )
        {
LABEL_89:
          v20 = "Command parameter: arithmetic syntax error in value construct.";
          goto LABEL_91;
        }
        v9 = 15;
        v32 = v4;
        HIDWORD(v28) = 15;
      }
    }
LABEL_39:
    if ( v9 <= 7 )
    {
      if ( v9 == 7 )
        goto LABEL_46;
      if ( (unsigned int)v9 < 2 )
      {
        v8 = BallocElementFromMasterTable(6, &v31, a3);
        if ( !v8 )
          break;
        v15 = v31;
        v16 = v29;
        ++*a2;
        v17 = v28;
        *(_DWORD *)(v16 + 8 * v15 + 4) = v9;
        *(_DWORD *)(v16 + 8 * v15) = v17;
        goto LABEL_54;
      }
      if ( v9 != 2 && v9 != 3 )
      {
        if ( v9 == 4 || (unsigned int)(v9 - 5) <= 1 )
        {
LABEL_46:
          if ( v7 )
          {
            do
            {
              if ( *(_DWORD *)(a3 + 4LL * v9 + 2152) > *(_DWORD *)(a3
                                                                 + 4LL * *(unsigned int *)(v27 + 4LL * v7 - 4)
                                                                 + 2152) )
                break;
              v8 = BallocElementFromMasterTable(6, &v31, a3);
              if ( !v8 )
                break;
              ++*a2;
              v14 = (_DWORD *)(v29 + 8LL * v31);
              v14[1] = *(_DWORD *)(v27 + 4LL * v7 - 4);
              *v14 = 0;
              bDivByZeroCheck();
              --v7;
            }
            while ( v7 );
            v4 = v32;
            v3 = v33;
          }
          v8 &= -(v7 < v26);
          if ( !v8 )
            goto LABEL_92;
          *(_DWORD *)(v27 + 4LL * v7) = v9;
          goto LABEL_53;
        }
        goto LABEL_54;
      }
LABEL_86:
      v23 = v7 + 1;
      v8 &= -((unsigned int)v23 < v26);
      if ( !v8 )
        break;
      v24 = v7++;
      *(_DWORD *)(v27 + 4 * v24) = 11;
      if ( v9 != 11 )
      {
        *(_DWORD *)(v27 + 4 * v23) = v9;
LABEL_53:
        ++v7;
        goto LABEL_54;
      }
      goto LABEL_54;
    }
    if ( v9 == 8 )
      goto LABEL_46;
    if ( v9 == 9 )
      goto LABEL_86;
    if ( v9 != 10 )
    {
      if ( v9 == 11 )
        goto LABEL_86;
      if ( v9 != 12 )
      {
        if ( v9 == 13 )
          goto LABEL_46;
        if ( v9 != 14 )
          goto LABEL_54;
      }
    }
    if ( v7 )
    {
      while ( 1 )
      {
        v18 = v27;
        if ( *(_DWORD *)(a3 + 4LL * v9 + 2152) > *(_DWORD *)(a3 + 4LL * *(unsigned int *)(v27 + 4LL * v7 - 4) + 2152) )
          break;
        v8 = BallocElementFromMasterTable(6, &v31, a3);
        if ( !v8 )
          goto LABEL_93;
        ++*a2;
        v19 = (_DWORD *)(v29 + 8LL * v31);
        v19[1] = *(_DWORD *)(v27 + 4LL * v7 - 4);
        *v19 = 0;
        bDivByZeroCheck();
        if ( !--v7 )
        {
          v3 = v33;
          goto LABEL_70;
        }
      }
      v3 = v33;
    }
    else
    {
LABEL_70:
      v18 = v27;
    }
    if ( v9 == 14 )
    {
      if ( !v7 || (unsigned int)(*(_DWORD *)(v18 + 4LL * v7 - 4) - 2) > 1 )
      {
        WriteDbgTraceErrorGpd("BconstructRPNtokenStream", "Command parameter: syntax error in value construct.");
        v20 = "  comma used outside of function argument list.";
LABEL_91:
        WriteDbgTraceErrorGpd("BconstructRPNtokenStream", v20);
LABEL_92:
        v8 = 0;
        break;
      }
      goto LABEL_84;
    }
    if ( v9 != 10 )
    {
      if ( v7 && *(_DWORD *)(v18 + 4LL * v7 - 4) == 11 )
      {
        --v7;
      }
      else
      {
        WriteDbgTraceErrorGpd(
          "BconstructRPNtokenStream",
          "Command parameter: syntax error in value construct - unmatched  OP_CLOSEPAR.");
        v8 = 0;
      }
LABEL_84:
      if ( !v8 )
        break;
      goto LABEL_54;
    }
    if ( v7 )
    {
      v20 = "Command parameter: syntax error in value construct - unmatched  OP_OPENPAR.";
      goto LABEL_91;
    }
    v8 = BallocElementFromMasterTable(6, &v31, a3);
    if ( !v8 )
      break;
    v21 = v31;
    v22 = v29;
    ++*a2;
    *(_DWORD *)(v22 + 8 * v21 + 4) = 10;
    *(_DWORD *)(v22 + 8 * v21) = 0;
LABEL_54:
    if ( v9 == 10 )
      return v8;
    a1 = v30;
  }
LABEL_93:
  *(_QWORD *)a2 = 0;
  return v8;
}

```

## disassembly

```asm
0x18000b848  mov     [rsp-40h+arg_0], rcx
0x18000b84d  push    rbp
0x18000b84e  push    rbx
0x18000b84f  push    rsi
0x18000b850  push    rdi
0x18000b851  push    r12
0x18000b853  push    r13
0x18000b855  push    r14
0x18000b857  push    r15
0x18000b859  mov     rbp, rsp
0x18000b85c  sub     rsp, 48h
0x18000b860  mov     rax, [r8+270h]
0x18000b867  xor     edi, edi
0x18000b869  mov     [rbp+var_20], rax
0x18000b86d  xor     r13d, r13d
0x18000b870  mov     eax, [r8+278h]
0x18000b877  mov     r12, r8
0x18000b87a  mov     [rbp+var_28], eax
0x18000b87d  mov     r15, rdx
0x18000b880  mov     rax, [r8+90h]
0x18000b887  xor     r14d, r14d
0x18000b88a  mov     [rbp+var_10], rax
0x18000b88e  mov     eax, [r8+9Ch]
0x18000b895  mov     [rdx+4], eax
0x18000b898  mov     [rdx], edi
0x18000b89a  mov     [rbp+var_18], 0
0x18000b8a2  mov     [rbp+arg_18], edi
0x18000b8a5  mov     [rbp+arg_10], r13d
0x18000b8a9  mov     [rbp+arg_8], edi
0x18000b8ac  mov     r8, r12
0x18000b8af  lea     rdx, [rbp+var_18]
0x18000b8b3  call    BparseArithmeticToken
0x18000b8b8  mov     ebx, eax
0x18000b8ba  test    eax, eax
0x18000b8bc  jz      loc_18000BC91
0x18000b8c2  mov     esi, dword ptr [rbp+var_18+4]
0x18000b8c5  cmp     esi, 7
0x18000b8c8  jg      short loc_18000B91C
0x18000b8ca  jz      short loc_18000B940
0x18000b8cc  mov     edx, esi
0x18000b8ce  test    esi, esi
0x18000b8d0  jz      short loc_18000B8F8
0x18000b8d2  sub     edx, 1
0x18000b8d5  jz      short loc_18000B8F8
0x18000b8d7  sub     edx, 1
0x18000b8da  jz      loc_18000B96A
0x18000b8e0  sub     edx, 1
0x18000b8e3  jz      loc_18000B96A
0x18000b8e9  sub     edx, 1
0x18000b8ec  jz      short loc_18000B940
0x18000b8ee  sub     edx, 1
0x18000b8f1  jz      short loc_18000B940
0x18000b8f3  cmp     edx, 1
0x18000b8f6  jmp     short loc_18000B93A
0x18000b8f8  cmp     r13d, edi
0x18000b8fb  jz      short loc_18000B912
0x18000b8fd  lea     rdx, aCommandParamet_7; "Command parameter: arithmetic syntax er"...
0x18000b904  lea     rcx, aBconstructrpnt; "BconstructRPNtokenStream"
0x18000b90b  call    WriteDbgTraceErrorGpd
0x18000b910  xor     ebx, ebx
0x18000b912  inc     edi
0x18000b914  mov     [rbp+arg_18], edi
0x18000b917  jmp     loc_18000B9B6
0x18000b91c  mov     ecx, esi
0x18000b91e  sub     ecx, 8
0x18000b921  jz      short loc_18000B940
0x18000b923  sub     ecx, 1
0x18000b926  jz      short loc_18000B980
0x18000b928  sub     ecx, 1
0x18000b92b  jz      short loc_18000B978
0x18000b92d  sub     ecx, 1
0x18000b930  jz      short loc_18000B96A
0x18000b932  sub     ecx, 1
0x18000b935  jz      short loc_18000B978
0x18000b937  cmp     ecx, 2
0x18000b93a  jnz     loc_18000B9DD
0x18000b940  lea     ecx, [r13+1]
0x18000b944  cmp     ecx, edi
0x18000b946  jz      loc_18000B9D7
0x18000b94c  lea     eax, [rdi+1]
0x18000b94f  cmp     ecx, eax
0x18000b951  jnz     loc_18000BC73
0x18000b957  mov     [rbp+arg_10], r13d
0x18000b95b  cmp     esi, 5
0x18000b95e  jnz     short loc_18000B9C0
0x18000b960  mov     esi, 0Dh
0x18000b965  mov     dword ptr [rbp+var_18+4], esi
0x18000b968  jmp     short loc_18000B9DD
0x18000b96a  cmp     edi, r13d
0x18000b96d  jz      short loc_18000B9DD
0x18000b96f  lea     rdx, aCommandParamet_7; "Command parameter: arithmetic syntax er"...
0x18000b976  jmp     short loc_18000B9A8
0x18000b978  lea     eax, [r13+1]
0x18000b97c  cmp     edi, eax
0x18000b97e  jmp     short loc_18000B96D
0x18000b980  test    edi, edi
0x18000b982  jnz     short loc_18000B98E
0x18000b984  test    r13d, r13d
0x18000b987  jnz     short loc_18000B98E
0x18000b989  test    r14d, r14d
0x18000b98c  jz      short loc_18000B9DD
0x18000b98e  lea     rdx, aCommandParamet_9; "Command parameter: syntax error in valu"...
0x18000b995  lea     rcx, aBconstructrpnt; "BconstructRPNtokenStream"
0x18000b99c  call    WriteDbgTraceErrorGpd
0x18000b9a1  lea     rdx, aOpMaxRepeatMus; "  OP_MAX_REPEAT must appear as the oute"...
0x18000b9a8  lea     rcx, aBconstructrpnt; "BconstructRPNtokenStream"
0x18000b9af  call    WriteDbgTraceErrorGpd
0x18000b9b4  xor     ebx, ebx
0x18000b9b6  test    ebx, ebx
0x18000b9b8  jz      loc_18000BC91
0x18000b9be  jmp     short loc_18000B9DD
0x18000b9c0  cmp     esi, 4
0x18000b9c3  jnz     loc_18000BC73
0x18000b9c9  mov     esi, 0Fh
0x18000b9ce  mov     [rbp+arg_10], r13d
0x18000b9d2  mov     dword ptr [rbp+var_18+4], esi
0x18000b9d5  jmp     short loc_18000B9DD
0x18000b9d7  mov     r13d, ecx
0x18000b9da  mov     [rbp+arg_10], ecx
0x18000b9dd  cmp     esi, 7
0x18000b9e0  jg      loc_18000BAE9
0x18000b9e6  jz      short loc_18000BA20
0x18000b9e8  mov     ecx, esi
0x18000b9ea  test    esi, esi
0x18000b9ec  jz      loc_18000BAB8
0x18000b9f2  sub     ecx, 1
0x18000b9f5  jz      loc_18000BAB8
0x18000b9fb  sub     ecx, 1
0x18000b9fe  jz      loc_18000BC44
0x18000ba04  sub     ecx, 1
0x18000ba07  jz      loc_18000BC44
0x18000ba0d  sub     ecx, 1
0x18000ba10  jz      short loc_18000BA20
0x18000ba12  sub     ecx, 1
0x18000ba15  jz      short loc_18000BA20
0x18000ba17  cmp     ecx, 1
0x18000ba1a  jnz     loc_18000BAA6
0x18000ba20  test    r14d, r14d
0x18000ba23  jz      short loc_18000BA8B
0x18000ba25  mov     r13, [rbp+var_20]
0x18000ba29  mov     edi, r14d
0x18000ba2c  movsxd  rcx, esi
0x18000ba2f  mov     eax, [r13+rdi*4-4]
0x18000ba34  mov     eax, [r12+rax*4+868h]
0x18000ba3c  cmp     [r12+rcx*4+868h], eax
0x18000ba44  ja      short loc_18000BA84
0x18000ba46  mov     r8, r12
0x18000ba49  lea     rdx, [rbp+arg_8]
0x18000ba4d  mov     ecx, 6
0x18000ba52  call    BallocElementFromMasterTable
0x18000ba57  mov     ebx, eax
0x18000ba59  test    eax, eax
0x18000ba5b  jz      short loc_18000BA84
0x18000ba5d  inc     dword ptr [r15]
0x18000ba60  mov     eax, [rbp+arg_8]
0x18000ba63  mov     rcx, [rbp+var_10]
0x18000ba67  lea     rcx, [rcx+rax*8]
0x18000ba6b  mov     eax, [r13+rdi*4-4]
0x18000ba70  mov     [rcx+4], eax
0x18000ba73  mov     dword ptr [rcx], 0
0x18000ba79  call    bDivByZeroCheck
0x18000ba7e  add     r14d, 0FFFFFFFFh
0x18000ba82  jnz     short loc_18000BA29
0x18000ba84  mov     r13d, [rbp+arg_10]
0x18000ba88  mov     edi, [rbp+arg_18]
0x18000ba8b  cmp     r14d, [rbp+var_28]
0x18000ba8f  sbb     eax, eax
0x18000ba91  and     ebx, eax
0x18000ba93  jz      loc_18000BC8F
0x18000ba99  mov     rcx, [rbp+var_20]
0x18000ba9d  mov     eax, r14d
0x18000baa0  mov     [rcx+rax*4], esi
0x18000baa3  inc     r14d
0x18000baa6  cmp     esi, 0Ah
0x18000baa9  jz      loc_18000BC98
0x18000baaf  mov     rcx, [rbp+arg_0]
0x18000bab3  jmp     loc_18000B8AC
0x18000bab8  mov     r8, r12
0x18000babb  lea     rdx, [rbp+arg_8]
0x18000babf  mov     ecx, 6
0x18000bac4  call    BallocElementFromMasterTable
0x18000bac9  mov     ebx, eax
0x18000bacb  test    eax, eax
0x18000bacd  jz      loc_18000BC91
0x18000bad3  mov     ecx, [rbp+arg_8]
0x18000bad6  mov     rdx, [rbp+var_10]
0x18000bada  inc     dword ptr [r15]
0x18000badd  mov     eax, dword ptr [rbp+var_18]
0x18000bae0  mov     [rdx+rcx*8+4], esi
0x18000bae4  mov     [rdx+rcx*8], eax
0x18000bae7  jmp     short loc_18000BAA6
0x18000bae9  mov     ecx, esi
0x18000baeb  sub     ecx, 8
0x18000baee  jz      loc_18000BA20
0x18000baf4  sub     ecx, 1
0x18000baf7  jz      loc_18000BC44
0x18000bafd  sub     ecx, 1
0x18000bb00  jz      short loc_18000BB1E
0x18000bb02  sub     ecx, 1
0x18000bb05  jz      loc_18000BC44
0x18000bb0b  sub     ecx, 1
0x18000bb0e  jz      short loc_18000BB1E
0x18000bb10  sub     ecx, 1
0x18000bb13  jz      loc_18000BA20
0x18000bb19  cmp     ecx, 1
0x18000bb1c  jnz     short loc_18000BAA6
0x18000bb1e  test    r14d, r14d
0x18000bb21  jz      short loc_18000BB8F
0x18000bb23  mov     rdx, [rbp+var_20]
0x18000bb27  mov     edi, r14d
0x18000bb2a  movsxd  rcx, esi
0x18000bb2d  mov     eax, [rdx+rdi*4-4]
0x18000bb31  mov     eax, [r12+rax*4+868h]
0x18000bb39  cmp     [r12+rcx*4+868h], eax
0x18000bb41  ja      loc_18000BBCF
0x18000bb47  mov     r8, r12
0x18000bb4a  lea     rdx, [rbp+arg_8]
0x18000bb4e  mov     ecx, 6
0x18000bb53  call    BallocElementFromMasterTable
0x18000bb58  mov     ebx, eax
0x18000bb5a  test    eax, eax
0x18000bb5c  jz      loc_18000BC91
0x18000bb62  inc     dword ptr [r15]
0x18000bb65  mov     eax, [rbp+arg_8]
0x18000bb68  mov     rcx, [rbp+var_10]
0x18000bb6c  lea     rcx, [rcx+rax*8]
0x18000bb70  mov     rax, [rbp+var_20]
0x18000bb74  mov     eax, [rax+rdi*4-4]
0x18000bb78  mov     [rcx+4], eax
0x18000bb7b  mov     dword ptr [rcx], 0
0x18000bb81  call    bDivByZeroCheck
0x18000bb86  add     r14d, 0FFFFFFFFh
0x18000bb8a  jnz     short loc_18000BB23
0x18000bb8c  mov     edi, [rbp+arg_18]
0x18000bb8f  mov     rdx, [rbp+var_20]
0x18000bb93  cmp     esi, 0Eh
0x18000bb96  jnz     short loc_18000BBD4
0x18000bb98  test    r14d, r14d
0x18000bb9b  jz      short loc_18000BBB0
0x18000bb9d  mov     eax, r14d
0x18000bba0  mov     ecx, [rdx+rax*4-4]
0x18000bba4  sub     ecx, 2
0x18000bba7  cmp     ecx, 1
0x18000bbaa  jbe     loc_18000BC3B
0x18000bbb0  lea     rdx, aCommandParamet_9; "Command parameter: syntax error in valu"...
0x18000bbb7  lea     rcx, aBconstructrpnt; "BconstructRPNtokenStream"
0x18000bbbe  call    WriteDbgTraceErrorGpd
0x18000bbc3  lea     rdx, aCommaUsedOutsi; "  comma used outside of function argume"...
0x18000bbca  jmp     loc_18000BC83
0x18000bbcf  mov     edi, [rbp+arg_18]
0x18000bbd2  jmp     short loc_18000BB93
0x18000bbd4  cmp     esi, 0Ah
0x18000bbd7  jnz     short loc_18000BC12
0x18000bbd9  test    r14d, r14d
0x18000bbdc  jnz     loc_18000BC7C
0x18000bbe2  mov     r8, r12
0x18000bbe5  lea     rdx, [rbp+arg_8]
0x18000bbe9  lea     ecx, [rsi-4]
0x18000bbec  call    BallocElementFromMasterTable
0x18000bbf1  mov     ebx, eax
0x18000bbf3  test    eax, eax
0x18000bbf5  jz      loc_18000BC91
0x18000bbfb  mov     eax, [rbp+arg_8]
0x18000bbfe  mov     rcx, [rbp+var_10]
0x18000bc02  inc     dword ptr [r15]
0x18000bc05  mov     [rcx+rax*8+4], esi
0x18000bc09  mov     [rcx+rax*8], r14d
0x18000bc0d  jmp     loc_18000BAA6
0x18000bc12  test    r14d, r14d
0x18000bc15  jz      short loc_18000BC26
0x18000bc17  mov     eax, r14d
0x18000bc1a  cmp     dword ptr [rdx+rax*4-4], 0Bh
0x18000bc1f  jnz     short loc_18000BC26
0x18000bc21  dec     r14d
0x18000bc24  jmp     short loc_18000BC3B
0x18000bc26  lea     rdx, aCommandParamet; "Command parameter: syntax error in valu"...
0x18000bc2d  lea     rcx, aBconstructrpnt; "BconstructRPNtokenStream"
0x18000bc34  call    WriteDbgTraceErrorGpd
0x18000bc39  xor     ebx, ebx
0x18000bc3b  test    ebx, ebx
0x18000bc3d  jz      short loc_18000BC91
0x18000bc3f  jmp     loc_18000BAA6
0x18000bc44  lea     ecx, [r14+1]
0x18000bc48  cmp     ecx, [rbp+var_28]
0x18000bc4b  sbb     eax, eax
0x18000bc4d  and     ebx, eax
0x18000bc4f  jz      short loc_18000BC91
0x18000bc51  mov     rdx, [rbp+var_20]
0x18000bc55  mov     eax, r14d
0x18000bc58  mov     r14d, ecx
0x18000bc5b  mov     dword ptr [rdx+rax*4], 0Bh
0x18000bc62  cmp     esi, 0Bh
0x18000bc65  jz      loc_18000BAA6
0x18000bc6b  mov     [rdx+rcx*4], esi
0x18000bc6e  jmp     loc_18000BAA3
0x18000bc73  lea     rdx, aCommandParamet_7; "Command parameter: arithmetic syntax er"...
0x18000bc7a  jmp     short loc_18000BC83
0x18000bc7c  lea     rdx, aCommandParamet_14; "Command parameter: syntax error in valu"...
0x18000bc83  lea     rcx, aBconstructrpnt; "BconstructRPNtokenStream"
0x18000bc8a  call    WriteDbgTraceErrorGpd
  ... truncated ...
```
