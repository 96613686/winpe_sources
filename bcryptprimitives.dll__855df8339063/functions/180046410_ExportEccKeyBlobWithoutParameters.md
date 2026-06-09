# ExportEccKeyBlobWithoutParameters

- ea: `0x180046410`
- end: `0x180046650`
- name: `ExportEccKeyBlobWithoutParameters`
- size: `576`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180045b60`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x180046410`
- `0x180046658`
- `0x180046738`
- `0x180056cf0`
- `0x180063180`
- `0x180063190`

## string_xrefs

- `0x18004655e`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x1800465aa`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x1800465e2`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

## pseudocode

```c
__int64 __fastcall ExportEccKeyBlobWithoutParameters(
        __int64 a1,
        _DWORD *a2,
        unsigned int a3,
        unsigned int *a4,
        int a5,
        int a6)
{
  __int64 *v6; // rbx
  __int64 v9; // rbx
  unsigned int v10; // esi
  unsigned int v11; // eax
  int KeyMagicForAlgId; // eax
  unsigned int v13; // ebp
  _DWORD *v14; // r14
  int v15; // edx
  unsigned int v16; // r10d
  int v17; // r9d
  unsigned int Value; // eax
  __int64 v19; // rax
  int v21; // edx
  int v22; // r8d
  __int64 v23; // r9
  __int64 v24; // rcx

  v6 = *(__int64 **)(a1 + 16);
  if ( v6 && *(_QWORD *)(a1 + 24) )
  {
    v9 = *v6;
    if ( v9 )
    {
      v10 = *(_DWORD *)(v9 + 12);
      if ( v10 <= *(_DWORD *)(v9 + 16) )
        v10 = *(_DWORD *)(v9 + 16);
      v11 = 2 * v10 + 8;
      *a4 = v11;
      if ( !a6 )
      {
LABEL_7:
        if ( !a2 )
          return 0;
        if ( a3 < v11 )
        {
          v13 = -1073741789;
          v23 = 1740;
          v24 = 3221225507LL;
        }
        else
        {
          memset_0(a2, 0, v11);
          a2[1] = v10;
          KeyMagicForAlgId = MSCryptEcGetKeyMagicForAlgId(
                               *(_DWORD *)(a1 + 8),
                               *(_QWORD *)(a1 + 16),
                               a5,
                               a6,
                               (__int64)a2);
          v13 = KeyMagicForAlgId;
          if ( KeyMagicForAlgId >= 0 )
          {
            v14 = a2 + 2;
            v15 = 0;
            if ( a6 )
            {
              v17 = *(_DWORD *)(v9 + 16);
              v16 = (_DWORD)v14 + 2 * v10;
            }
            else
            {
              v16 = 0;
              v17 = 0;
            }
            LOBYTE(v15) = *(_DWORD *)(**(_QWORD **)(a1 + 16) + 4LL) != 3;
            Value = SymCryptEckeyGetValue(
                      *(_QWORD *)(a1 + 24),
                      v16,
                      v17,
                      (_DWORD)v14,
                      (unsigned int)(2 * *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 8LL) + 20LL)),
                      v15 + 1,
                      2);
            if ( Value )
            {
              v13 = SymcryptErrorCodeToNtStatus(Value);
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_sDsd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  v21,
                  v22,
                  (unsigned int)"Status",
                  v13,
                  (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
                  249);
              }
            }
            else
            {
              v19 = *(unsigned int *)(v9 + 12);
              if ( (unsigned int)v19 < v10 )
              {
                memmove_0((char *)v14 + v10, (char *)v14 + v19, *(unsigned int *)(v9 + 12));
                memset_0((char *)v14 + *(unsigned int *)(v9 + 12), 0, v10 - *(_DWORD *)(v9 + 12));
              }
            }
            return v13;
          }
          v23 = 1754;
          v24 = (unsigned int)KeyMagicForAlgId;
        }
LABEL_26:
        DebugTraceError(v24, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", v23);
        return v13;
      }
      if ( *(_BYTE *)(*(_QWORD *)(a1 + 24) + 4LL) )
      {
        v11 = v10 + 2 * (v10 + 4);
        *a4 = v11;
        goto LABEL_7;
      }
      v23 = 1724;
    }
    else
    {
      v23 = 1702;
    }
    v13 = -1073741811;
    v24 = 3221225485LL;
    goto LABEL_26;
  }
  v13 = -1073741811;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)a2,
      a3,
      (unsigned int)"Status",
      13,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
      157);
  return v13;
}

```

## disassembly

```asm
0x180046410  push    rbx
0x180046412  push    rbp
0x180046413  push    rsi
0x180046414  push    rdi
0x180046415  push    r13
0x180046417  push    r14
0x180046419  push    r15
0x18004641b  sub     rsp, 40h
0x18004641f  mov     rbx, [rcx+10h]
0x180046423  mov     r14, rdx
0x180046426  mov     rdi, rcx
0x180046429  test    rbx, rbx
0x18004642c  jz      loc_180046580
0x180046432  cmp     qword ptr [rcx+18h], 0
0x180046437  jz      loc_180046580
0x18004643d  mov     rbx, [rbx]
0x180046440  test    rbx, rbx
0x180046443  jz      loc_1800465CF
0x180046449  mov     esi, [rbx+0Ch]
0x18004644c  cmp     esi, [rbx+10h]
0x18004644f  mov     r15d, [rsp+78h+arg_28]
0x180046457  cmovbe  esi, [rbx+10h]
0x18004645b  lea     r13d, [rsi+rsi]
0x18004645f  lea     eax, [r13+8]
0x180046463  mov     [r9], eax
0x180046466  test    r15d, r15d
0x180046469  jnz     loc_1800465FA
0x18004646f  test    r14, r14
0x180046472  jz      loc_18004652E
0x180046478  cmp     r8d, eax
0x18004647b  jb      loc_180046616
0x180046481  mov     r8d, eax; Size
0x180046484  xor     edx, edx; Val
0x180046486  mov     rcx, r14; void *
0x180046489  call    memset_0
0x18004648e  mov     r8d, [rsp+78h+arg_20]
0x180046496  mov     r9d, r15d
0x180046499  mov     [r14+4], esi
0x18004649d  mov     rdx, [rdi+10h]
0x1800464a1  mov     ecx, [rdi+8]
0x1800464a4  mov     [rsp+78h+var_58], r14
0x1800464a9  call    MSCryptEcGetKeyMagicForAlgId
0x1800464ae  mov     ebp, eax
0x1800464b0  test    eax, eax
0x1800464b2  js      loc_1800465DA
0x1800464b8  add     r14, 8
0x1800464bc  xor     edx, edx
0x1800464be  test    r15d, r15d
0x1800464c1  jnz     loc_1800465C0
0x1800464c7  mov     r10d, edx
0x1800464ca  mov     r9d, edx
0x1800464cd  mov     rax, [rdi+10h]
0x1800464d1  mov     rcx, [rdi+18h]
0x1800464d5  mov     [rsp+78h+var_48], 2
0x1800464dd  mov     r8, [rax]
0x1800464e0  mov     rax, [rcx+8]
0x1800464e4  cmp     dword ptr [r8+4], 3
0x1800464e9  mov     r8d, [rax+14h]
0x1800464ed  setnz   dl
0x1800464f0  inc     edx
0x1800464f2  mov     dword ptr [rsp+78h+var_50], edx
0x1800464f6  mov     rdx, r10
0x1800464f9  lea     eax, [r8+r8]
0x1800464fd  mov     r8d, r9d
0x180046500  mov     r9, r14
0x180046503  mov     [rsp+78h+var_58], rax
0x180046508  call    SymCryptEckeyGetValue
0x18004650d  test    eax, eax
0x18004650f  jnz     short loc_180046534
0x180046511  mov     eax, [rbx+0Ch]
0x180046514  cmp     eax, esi
0x180046516  jb      loc_180046628
0x18004651c  mov     eax, ebp
0x18004651e  add     rsp, 40h
0x180046522  pop     r15
0x180046524  pop     r14
0x180046526  pop     r13
0x180046528  pop     rdi
0x180046529  pop     rsi
0x18004652a  pop     rbp
0x18004652b  pop     rbx
0x18004652c  retn
0x18004652e  xor     edx, edx
0x180046530  mov     ebp, edx
0x180046532  jmp     short loc_18004651C
0x180046534  mov     ecx, eax
0x180046536  call    SymcryptErrorCodeToNtStatus
0x18004653b  mov     ebp, eax
0x18004653d  mov     rcx, cs:WPP_GLOBAL_Control
0x180046544  lea     rax, WPP_GLOBAL_Control
0x18004654b  cmp     rcx, rax
0x18004654e  jz      short loc_18004651C
0x180046550  test    byte ptr [rcx+1Ch], 1
0x180046554  jz      short loc_18004651C
0x180046556  mov     [rsp+78h+var_48], 6F9h
0x18004655e  lea     rax, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180046565  mov     [rsp+78h+var_50], rax
0x18004656a  mov     dword ptr [rsp+78h+var_58], ebp
0x18004656e  mov     rcx, [rcx+10h]
0x180046572  lea     r9, aStatus; "Status"
0x180046579  call    WPP_SF_sDsd
0x18004657e  jmp     short loc_18004651C
0x180046580  mov     ebp, 0C000000Dh
0x180046585  mov     rcx, cs:WPP_GLOBAL_Control
0x18004658c  lea     rax, WPP_GLOBAL_Control
0x180046593  cmp     rcx, rax
0x180046596  jz      short loc_18004651C
0x180046598  test    byte ptr [rcx+1Ch], 1
0x18004659c  jz      loc_18004651C
0x1800465a2  mov     [rsp+78h+var_48], 69Dh
0x1800465aa  lea     rax, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800465b1  mov     [rsp+78h+var_50], rax
0x1800465b6  mov     dword ptr [rsp+78h+var_58], 0C000000Dh
0x1800465be  jmp     short loc_18004656E
0x1800465c0  mov     r9d, [rbx+10h]
0x1800465c4  mov     r10d, r13d
0x1800465c7  add     r10, r14
0x1800465ca  jmp     loc_1800464CD
0x1800465cf  mov     r9d, 6A6h
0x1800465d5  jmp     loc_18008274C
0x1800465da  mov     r9d, 6DAh
0x1800465e0  mov     ecx, eax
0x1800465e2  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800465e9  lea     rdx, aStatus; "Status"
0x1800465f0  call    DebugTraceError
0x1800465f5  jmp     loc_18004651C
0x1800465fa  mov     rax, [rcx+18h]
0x1800465fe  cmp     byte ptr [rax+4], 0
0x180046602  jz      loc_180082746
0x180046608  lea     eax, [rsi+4]
0x18004660b  lea     eax, [rsi+rax*2]
0x18004660e  mov     [r9], eax
0x180046611  jmp     loc_18004646F
0x180046616  mov     ebp, 0C0000023h
0x18004661b  mov     r9d, 6CCh
0x180046621  mov     ecx, 0C0000023h
0x180046626  jmp     short loc_1800465E2
0x180046628  mov     ecx, esi
0x18004662a  lea     rdx, [rax+r14]; Src
0x18004662e  add     rcx, r14; void *
0x180046631  mov     r8, rax; Size
0x180046634  call    memmove_0
0x180046639  mov     ecx, [rbx+0Ch]
0x18004663c  xor     edx, edx; Val
0x18004663e  sub     esi, ecx
0x180046640  add     rcx, r14; void *
0x180046643  mov     r8d, esi; Size
0x180046646  call    memset_0
0x18004664b  jmp     loc_18004651C
0x180082746  mov     r9d, 6BCh
0x18008274c  mov     ebp, 0C000000Dh
0x180082751  mov     ecx, 0C000000Dh
0x180082756  jmp     loc_1800465E2
```
