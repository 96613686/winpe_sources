# MSCryptDeriveKey

- ea: `0x1800568e0`
- end: `0x180056b63`
- name: `MSCryptDeriveKey`
- size: `643`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18006bd38`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x180049c68`
- `0x1800568e0`
- `0x180083010`

## string_xrefs

- `0x18005697b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\common\secret.c`
- `0x180056a8e`: `onecore\ds\security\cryptoapi\ncrypt\msprim\common\secret.c`
- `0x180056b2c`: `onecore\ds\security\cryptoapi\ncrypt\msprim\common\secret.c`

## pseudocode

```c
__int64 __fastcall MSCryptDeriveKey(
        __int64 a1,
        const wchar_t *a2,
        signed __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int a7)
{
  signed __int64 v8; // r13
  const wchar_t *v9; // rsi
  __int64 v10; // r14
  int v11; // r12d
  int v12; // edx
  unsigned int v13; // edi
  int v14; // r8d
  wchar_t **v15; // r10
  wchar_t *v16; // rax
  int v17; // ecx
  int v18; // edx
  __int64 v19; // rcx
  wchar_t v20; // ax
  __int64 v21; // rbx
  _QWORD *v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rdx
  int v25; // r14d
  __int64 v26; // rcx
  char v28; // [rsp+30h] [rbp-68h]
  __int64 v29; // [rsp+30h] [rbp-68h]
  __int64 v30; // [rsp+A0h] [rbp+8h] BYREF
  const wchar_t *v31; // [rsp+A8h] [rbp+10h]
  __int64 v32; // [rsp+B8h] [rbp+20h]

  v32 = a4;
  v31 = a2;
  v8 = a3;
  v9 = a2;
  v30 = 0;
  if ( a1 )
  {
    if ( a2 )
    {
      v10 = a6;
      if ( a6 )
      {
        v11 = a7;
        if ( (a7 & 0xFFFFFFFE) == 0 )
        {
          v13 = MSCryptValidateSecret(a1, &v30);
          if ( (v13 & 0x80000000) != 0 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_sDsd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v12,
                v14,
                (unsigned int)"Status",
                v13,
                (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\common\\secret.c",
                220);
            return v13;
          }
          v15 = &KdfRouterMapping;
          v13 = -1073741637;
          while ( 1 )
          {
            v16 = *v15;
            if ( !*v15 )
              return v13;
            a3 = (char *)v9 - (char *)v16;
            do
            {
              v17 = *(wchar_t *)((char *)v16 + a3);
              v18 = *v16 - v17;
              if ( v18 )
                break;
              ++v16;
            }
            while ( v17 );
            if ( !v18 )
              break;
            v15 += 2;
          }
          v19 = 0;
          a2 = L"HKDF";
          while ( 1 )
          {
            v20 = v9[v19++];
            if ( v20 != aHkdf[v19 - 1] )
              break;
            if ( v19 == 5 )
            {
              v21 = v30;
              if ( !*(_DWORD *)(v30 + 32) )
              {
                v13 = -1073741811;
                v22 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  v28 = -13;
                  goto LABEL_39;
                }
                return v13;
              }
              v23 = v30 + 64;
              v24 = 560;
LABEL_24:
              v29 = v10;
              v25 = a5;
              v13 = ((__int64 (__fastcall *)(__int64, __int64, _QWORD, signed __int64, __int64, int, __int64, int))v15[1])(
                      v23,
                      v24,
                      *(unsigned int *)(v21 + 8),
                      v8,
                      a4,
                      a5,
                      v29,
                      v11);
              if ( (v13 & 0x80000000) != 0 )
                DebugTraceError(
                  v13,
                  "Status",
                  "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\common\\secret.c",
                  270);
              v26 = -1;
              while ( v9[v26 + 1] == aSp80056aConcat[v26 + 1] )
              {
                v26 += 2;
                if ( v26 == 17 )
                {
                  if ( a4 && v25 && (v13 & 0x80000000) == 0 )
                    *(_DWORD *)(v21 + 16) = 0;
                  return v13;
                }
                if ( v9[v26] != aSp80056aConcat[v26] )
                  return v13;
              }
              return v13;
            }
          }
          v21 = v30;
          v23 = v30 + 624;
          v24 = *(unsigned int *)(v30 + 16);
          goto LABEL_24;
        }
      }
    }
  }
  v13 = -1073741811;
  v22 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v28 = -43;
LABEL_39:
    WPP_SF_sDsd(
      v22[2],
      (_DWORD)a2,
      a3,
      (unsigned int)"Status",
      13,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\common\\secret.c",
      v28);
  }
  return v13;
}

```

## disassembly

```asm
0x1800568e0  mov     rax, rsp
0x1800568e3  mov     [rax+20h], r9
0x1800568e7  mov     [rax+10h], rdx
0x1800568eb  push    rbx
0x1800568ec  push    rsi
0x1800568ed  push    rdi
0x1800568ee  push    r12
0x1800568f0  push    r13
0x1800568f2  push    r14
0x1800568f4  push    r15
0x1800568f6  sub     rsp, 60h
0x1800568fa  mov     r15, r9
0x1800568fd  mov     r13, r8
0x180056900  mov     rsi, rdx
0x180056903  mov     qword ptr [rax+8], 0
0x18005690b  test    rcx, rcx
0x18005690e  jz      loc_180056B06
0x180056914  test    rdx, rdx
0x180056917  jz      loc_180056B06
0x18005691d  mov     r14, [rsp+98h+arg_28]
0x180056925  test    r14, r14
0x180056928  jz      loc_180056B06
0x18005692e  mov     r12d, [rsp+98h+arg_30]
0x180056936  test    r12d, 0FFFFFFFEh
0x18005693d  jnz     loc_180056B06
0x180056943  lea     rdx, [rax+8]
0x180056947  call    MSCryptValidateSecret
0x18005694c  mov     edi, eax
0x18005694e  test    eax, eax
0x180056950  jns     short loc_180056990
0x180056952  lea     rax, WPP_GLOBAL_Control
0x180056959  mov     rcx, cs:WPP_GLOBAL_Control
0x180056960  cmp     rcx, rax
0x180056963  jz      loc_180056B50
0x180056969  test    byte ptr [rcx+1Ch], 1
0x18005696d  jz      loc_180056B50
0x180056973  mov     dword ptr [rsp+98h+var_68], 0DCh
0x18005697b  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180056982  mov     [rsp+98h+var_70], rax
0x180056987  mov     dword ptr [rsp+98h+var_78], edi
0x18005698b  jmp     loc_180056B40
0x180056990  lea     r10, KdfRouterMapping
0x180056997  mov     edi, 0C00000BBh
0x18005699c  mov     [rsp+98h+var_48], edi
0x1800569a0  mov     rax, [r10]
0x1800569a3  test    rax, rax
0x1800569a6  jz      loc_180056B50
0x1800569ac  mov     r8, rsi
0x1800569af  sub     r8, rax
0x1800569b2  movzx   edx, word ptr [rax]
0x1800569b5  movzx   ecx, word ptr [rax+r8]
0x1800569ba  sub     edx, ecx
0x1800569bc  jnz     short loc_1800569C6
0x1800569be  add     rax, 2
0x1800569c2  test    ecx, ecx
0x1800569c4  jnz     short loc_1800569B2
0x1800569c6  test    edx, edx
0x1800569c8  jnz     loc_180056AFD
0x1800569ce  xor     ecx, ecx
0x1800569d0  lea     rdx, aHkdf; "HKDF"
0x1800569d7  nop     word ptr [rax+rax+00000000h]
0x1800569e0  movzx   eax, word ptr [rsi+rcx*2]
0x1800569e4  inc     rcx
0x1800569e7  cmp     ax, [rdx+rcx*2-2]
0x1800569ec  jnz     short loc_180056A40
0x1800569ee  cmp     rcx, 5
0x1800569f2  jnz     short loc_1800569E0
0x1800569f4  mov     rbx, [rsp+98h+arg_0]
0x1800569fc  cmp     dword ptr [rbx+20h], 0
0x180056a00  jnz     short loc_180056A35
0x180056a02  mov     edi, 0C000000Dh
0x180056a07  lea     rax, WPP_GLOBAL_Control
0x180056a0e  mov     rcx, cs:WPP_GLOBAL_Control
0x180056a15  cmp     rcx, rax
0x180056a18  jz      loc_180056B50
0x180056a1e  test    byte ptr [rcx+1Ch], 1
0x180056a22  jz      loc_180056B50
0x180056a28  mov     dword ptr [rsp+98h+var_68], 0F3h
0x180056a30  jmp     loc_180056B2C
0x180056a35  lea     rcx, [rbx+40h]
0x180056a39  mov     edx, 230h
0x180056a3e  jmp     short loc_180056A52
0x180056a40  mov     rbx, [rsp+98h+arg_0]
0x180056a48  lea     rcx, [rbx+270h]
0x180056a4f  mov     edx, [rbx+10h]
0x180056a52  mov     [rsp+98h+var_60], r12d
0x180056a57  mov     [rsp+98h+var_68], r14
0x180056a5c  mov     r14d, [rsp+98h+arg_20]
0x180056a64  mov     dword ptr [rsp+98h+var_70], r14d
0x180056a69  mov     [rsp+98h+var_78], r15
0x180056a6e  mov     r9, r13
0x180056a71  mov     r8d, [rbx+8]
0x180056a75  mov     rax, [r10+8]
0x180056a79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056a7e  mov     edi, eax
0x180056a80  mov     [rsp+98h+var_48], eax
0x180056a84  test    eax, eax
0x180056a86  jns     short loc_180056AA7
0x180056a88  mov     r9d, 10Eh
0x180056a8e  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180056a95  mov     r8, rax
0x180056a98  lea     rdx, aStatus; "Status"
0x180056a9f  mov     ecx, edi
0x180056aa1  call    DebugTraceError
0x180056aa6  nop
0x180056aa7  lea     rdx, aSp80056aConcat; "SP800_56A_CONCAT"
0x180056aae  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180056ab5  nop     word ptr [rax+rax+00000000h]
0x180056ac0  movzx   eax, word ptr [rsi+rcx*2+2]
0x180056ac5  cmp     ax, [rdx+rcx*2+2]
0x180056aca  jnz     loc_180056B50
0x180056ad0  add     rcx, 2
0x180056ad4  cmp     rcx, 11h
0x180056ad8  jz      short loc_180056AE6
0x180056ada  movzx   eax, word ptr [rsi+rcx*2]
0x180056ade  cmp     ax, [rdx+rcx*2]
0x180056ae2  jz      short loc_180056AC0
0x180056ae4  jmp     short loc_180056B50
0x180056ae6  test    r15, r15
0x180056ae9  jz      short loc_180056B50
0x180056aeb  test    r14d, r14d
0x180056aee  jz      short loc_180056B50
0x180056af0  test    edi, edi
0x180056af2  js      short loc_180056B50
0x180056af4  mov     dword ptr [rbx+10h], 0
0x180056afb  jmp     short loc_180056B50
0x180056afd  add     r10, 10h
0x180056b01  jmp     loc_1800569A0
0x180056b06  mov     edi, 0C000000Dh
0x180056b0b  lea     rax, WPP_GLOBAL_Control
0x180056b12  mov     rcx, cs:WPP_GLOBAL_Control
0x180056b19  cmp     rcx, rax
0x180056b1c  jz      short loc_180056B50
0x180056b1e  test    byte ptr [rcx+1Ch], 1
0x180056b22  jz      short loc_180056B50
0x180056b24  mov     dword ptr [rsp+98h+var_68], 0D5h
0x180056b2c  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180056b33  mov     [rsp+98h+var_70], rax
0x180056b38  mov     dword ptr [rsp+98h+var_78], 0C000000Dh
0x180056b40  lea     r9, aStatus; "Status"
0x180056b47  mov     rcx, [rcx+10h]
0x180056b4b  call    WPP_SF_sDsd
0x180056b50  mov     eax, edi
0x180056b52  add     rsp, 60h
0x180056b56  pop     r15
0x180056b58  pop     r14
0x180056b5a  pop     r13
0x180056b5c  pop     r12
0x180056b5e  pop     rdi
0x180056b5f  pop     rsi
0x180056b60  pop     rbx
0x180056b61  retn
0x18007fc70  push    rbp
0x18007fc72  sub     rsp, 50h
0x18007fc76  mov     rbp, rdx
0x18007fc79  mov     rdx, [rbp+0A8h]
0x18007fc80  lea     r8, aSp80056aConcat; "SP800_56A_CONCAT"
0x18007fc87  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18007fc8e  xchg    ax, ax
0x18007fc90  movzx   eax, word ptr [rdx+rcx*2+2]
0x18007fc95  cmp     ax, [r8+rcx*2+2]
0x18007fc9b  jnz     short loc_18007FCDB
0x18007fc9d  add     rcx, 2
0x18007fca1  cmp     rcx, 11h
0x18007fca5  jz      short loc_18007FCB4
0x18007fca7  movzx   eax, word ptr [rdx+rcx*2]
0x18007fcab  cmp     ax, [r8+rcx*2]
0x18007fcb0  jz      short loc_18007FC90
0x18007fcb2  jmp     short loc_18007FCDB
0x18007fcb4  cmp     qword ptr [rbp+0B8h], 0
0x18007fcbc  jz      short loc_18007FCDB
0x18007fcbe  cmp     dword ptr [rbp+0C0h], 0
0x18007fcc5  jz      short loc_18007FCDB
0x18007fcc7  cmp     dword ptr [rbp+50h], 0
0x18007fccb  jl      short loc_18007FCDB
0x18007fccd  mov     rax, [rbp+0A0h]
0x18007fcd4  mov     dword ptr [rax+10h], 0
0x18007fcdb  add     rsp, 50h
0x18007fcdf  pop     rbp
0x18007fce0  retn
```
