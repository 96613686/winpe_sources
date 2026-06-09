# MSCryptEccImportKeyPair

- ea: `0x1800476d0`
- end: `0x180047aa7`
- name: `MSCryptEccImportKeyPair`
- size: `983`
- prototype: `__int64 __fastcall(int, __int64, const wchar_t *, _QWORD *, __int64, unsigned int, int, int, _DWORD *)`
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180047560`
- `0x180047620`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x180010270`
- `0x1800102a0`
- `0x1800225d0`
- `0x1800476d0`
- `0x180047ab0`
- `0x180047c50`
- `0x180048430`
- `0x180067358`
- `0x18007f765`

## string_xrefs

- `0x1800478f7`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x18004794a`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x18004796d`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x1800479d6`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x1800827dd`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180082832`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

## pseudocode

```c
__int64 __fastcall MSCryptEccImportKeyPair(
        int a1,
        __int64 a2,
        const wchar_t *a3,
        _QWORD *a4,
        __int64 a5,
        unsigned int a6,
        int a7,
        int a8,
        _DWORD *a9)
{
  PVOID v9; // r14
  int v12; // edx
  unsigned int v13; // ebx
  _DWORD *v14; // r13
  __int64 v15; // r15
  unsigned int v16; // ebx
  unsigned int v17; // r12d
  int v18; // eax
  int v19; // eax
  PVOID v20; // rax
  __int64 v22; // r9
  __int64 v23; // rcx
  __int64 v24; // rcx
  _BYTE *v25; // rax
  bool v26; // zf
  BOOL v27; // ecx
  __int64 v28; // r9
  int v29; // eax
  int v30; // eax
  unsigned int v31; // [rsp+40h] [rbp-20h] BYREF
  int v32; // [rsp+44h] [rbp-1Ch] BYREF
  PVOID P; // [rsp+48h] [rbp-18h] BYREF
  __int64 v34; // [rsp+50h] [rbp-10h] BYREF

  v9 = 0;
  v34 = 0;
  v32 = 0;
  P = 0;
  v31 = 0;
  if ( (a7 & 0xFFFFFFC7) != 0 )
  {
    v13 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        198);
  }
  else
  {
    v13 = ValidateEccAlgorithm(a1, 0, a8, (unsigned int)&v32, (__int64)&v34);
    if ( (v13 & 0x80000000) == 0 )
    {
      v14 = (_DWORD *)a5;
      v15 = 0;
      if ( !a5 || (v16 = a6, a6 < 4) )
      {
        v17 = v31;
        v13 = -1073741811;
        v19 = -1073741811;
        v28 = 3029;
LABEL_32:
        DebugTraceError(
          (unsigned int)v19,
          "Status",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
          v28);
        if ( v9 )
          MSCryptEccDestroyKeyPair(v9);
LABEL_15:
        if ( !v15 )
          return v13;
        goto LABEL_34;
      }
      if ( a3 && !wcscmp_0(a3, L"PKCS11RsaAesWrapBlob") )
      {
        if ( !a2 )
        {
          v13 = -1073741816;
          v22 = 3039;
          v23 = 3221225480LL;
LABEL_38:
          DebugTraceError(v23, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", v22);
          return v13;
        }
        v29 = Pkcs11ConvertToKeyBlob(a1, a2, 0, (unsigned int)&v31, a5, a6);
        v13 = v29;
        if ( v29 < 0 )
        {
          v22 = 3051;
          v23 = (unsigned int)v29;
          goto LABEL_38;
        }
        v15 = SafeAllocaAllocateFromHeap(v31);
        if ( !v15 )
        {
          v13 = -1073741801;
          v22 = 3058;
          v23 = 3221225495LL;
          goto LABEL_38;
        }
        v30 = Pkcs11ConvertToKeyBlob(a1, a2, v15, (unsigned int)&v31, a5, a6);
        v13 = v30;
        if ( v30 < 0 )
        {
          DebugTraceError(
            (unsigned int)v30,
            "Status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
            3070);
          v17 = v31;
LABEL_34:
          v24 = v17;
          v25 = (_BYTE *)v15;
          if ( v17 )
          {
            do
            {
              *v25++ = 0;
              --v24;
            }
            while ( v24 );
          }
          MSCryptFree(v15);
          return v13;
        }
        v17 = v31;
        a3 = L"ECCPRIVATEBLOB";
        v16 = v31;
        v14 = (_DWORD *)v15;
      }
      else
      {
        if ( a2 )
        {
          v13 = -1073741637;
          v22 = 3080;
          v23 = 3221225659LL;
          goto LABEL_38;
        }
        v17 = v31;
      }
      if ( !wcscmp_0(a3, L"PUBLICBLOB") )
      {
        v26 = *v14 == 1346650949;
        *a9 = 0;
        v27 = v26 || *v14 == 1347109701;
        v18 = 0;
      }
      else
      {
        if ( wcscmp_0(a3, L"PRIVATEBLOB") )
        {
          if ( !wcscmp_0(a3, L"ECCPUBLICBLOB") )
          {
            *a9 = 0;
            v18 = 0;
LABEL_12:
            v19 = ImportEccKeyBlobWithoutParameters(v34, (_DWORD)v14, v16, v32, a8, v18, a7, (__int64)&P);
LABEL_13:
            v13 = v19;
            if ( v19 >= 0 )
            {
              v20 = P;
              *((_DWORD *)P + 8) |= 2u;
              v13 = 0;
              *a4 = v20;
              goto LABEL_15;
            }
            v9 = P;
            v28 = 3163;
            goto LABEL_32;
          }
          if ( !wcscmp_0(a3, L"ECCPRIVATEBLOB") )
          {
            *a9 = 1;
            v18 = 1;
            goto LABEL_12;
          }
          if ( !wcscmp_0(a3, L"ECCFULLPUBLICBLOB") )
          {
            *a9 = 0;
            v18 = 0;
          }
          else
          {
            if ( wcscmp_0(a3, L"ECCFULLPRIVATEBLOB") )
            {
              v13 = -1073741637;
              DebugTraceError(
                3221225659LL,
                "Status",
                "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
                3134);
              goto LABEL_15;
            }
            *a9 = 1;
            v18 = 1;
          }
LABEL_23:
          v19 = ImportEccKeyBlobWithParameters(v34, (_DWORD)v14, v16, a8, v18, a7, (__int64)&P);
          goto LABEL_13;
        }
        v26 = *v14 == 1447314245;
        *a9 = 1;
        v27 = v26 || *v14 == 1447772997;
        v18 = 1;
      }
      if ( !v27 )
        goto LABEL_12;
      goto LABEL_23;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v12,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        (unsigned int)"Status",
        v13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        205);
  }
  return v13;
}

```

## disassembly

```asm
0x1800476d0  mov     r11, rsp
0x1800476d3  mov     [r11+10h], rbx
0x1800476d7  mov     [r11+18h], rsi
0x1800476db  mov     [r11+20h], r9
0x1800476df  mov     [r11+8], rcx
0x1800476e3  push    rbp
0x1800476e4  push    r12
0x1800476e6  push    r13
0x1800476e8  push    r14
0x1800476ea  push    r15
0x1800476ec  mov     rbp, rsp
0x1800476ef  sub     rsp, 60h
0x1800476f3  xor     r14d, r14d
0x1800476f6  mov     [rbp+var_10], 0
0x1800476fe  test    [rbp+arg_30], 0FFFFFFC7h
0x180047705  mov     rsi, r8
0x180047708  mov     r12, rdx
0x18004770b  mov     [rbp+var_1C], 0
0x180047712  mov     rax, rcx
0x180047715  mov     [rbp+P], r14
0x180047719  mov     [rbp+var_20], r14d
0x18004771d  jnz     loc_18004791C
0x180047723  mov     r8d, [rbp+arg_38]
0x180047727  lea     rcx, [rbp+var_10]
0x18004772b  mov     [r11-68h], rcx
0x18004772f  lea     r9, [rbp+var_1C]
0x180047733  mov     rcx, rax
0x180047736  xor     edx, edx
0x180047738  call    ValidateEccAlgorithm
0x18004773d  mov     ebx, eax
0x18004773f  test    eax, eax
0x180047741  js      loc_1800478CE
0x180047747  mov     r13, [rbp+arg_20]
0x18004774b  xor     r15d, r15d
0x18004774e  test    r13, r13
0x180047751  jz      loc_180047A8E
0x180047757  mov     ebx, [rbp+arg_28]
0x18004775a  cmp     ebx, 4
0x18004775d  jb      loc_180047A8E
0x180047763  test    rsi, rsi
0x180047766  jnz     loc_180047836
0x18004776c  test    r12, r12
0x18004776f  jnz     loc_1800479BF
0x180047775  mov     r12d, [rbp+var_20]
0x180047779  lea     rdx, aPublicblob; "PUBLICBLOB"
0x180047780  mov     rcx, rsi; String1
0x180047783  call    wcscmp_0
0x180047788  test    eax, eax
0x18004778a  jz      loc_1800479E7
0x180047790  lea     rdx, aPrivateblob; "PRIVATEBLOB"
0x180047797  mov     rcx, rsi; String1
0x18004779a  call    wcscmp_0
0x18004779f  test    eax, eax
0x1800477a1  jz      loc_180047A11
0x1800477a7  lea     rdx, aEccpublicblob; "ECCPUBLICBLOB"
0x1800477ae  mov     rcx, rsi; String1
0x1800477b1  call    wcscmp_0
0x1800477b6  test    eax, eax
0x1800477b8  jnz     loc_18004786B
0x1800477be  mov     rax, [rbp+arg_40]
0x1800477c2  mov     [rax], r14d
0x1800477c5  xor     eax, eax
0x1800477c7  mov     r9d, [rbp+var_1C]
0x1800477cb  lea     rcx, [rbp+P]
0x1800477cf  mov     [rsp+60h+var_28], rcx
0x1800477d4  mov     r8d, ebx
0x1800477d7  mov     ecx, [rbp+arg_30]
0x1800477da  mov     rdx, r13
0x1800477dd  mov     dword ptr [rsp+60h+var_30], ecx
0x1800477e1  mov     rcx, [rbp+var_10]
0x1800477e5  mov     dword ptr [rsp+60h+var_38], eax
0x1800477e9  mov     eax, [rbp+arg_38]
0x1800477ec  mov     dword ptr [rsp+60h+var_40], eax
0x1800477f0  call    ImportEccKeyBlobWithoutParameters
0x1800477f5  mov     ebx, eax
0x1800477f7  test    eax, eax
0x1800477f9  js      loc_180047A7D
0x1800477ff  mov     rax, [rbp+P]
0x180047803  mov     rcx, [rbp+arg_18]
0x180047807  or      dword ptr [rax+20h], 2
0x18004780b  xor     ebx, ebx
0x18004780d  mov     [rcx], rax
0x180047810  test    r15, r15
0x180047813  jnz     loc_18004799B
0x180047819  lea     r11, [rsp+60h+var_s0]
0x18004781e  mov     eax, ebx
0x180047820  mov     rbx, [r11+38h]
0x180047824  mov     rsi, [r11+40h]
0x180047828  mov     rsp, r11
0x18004782b  pop     r15
0x18004782d  pop     r14
0x18004782f  pop     r13
0x180047831  pop     r12
0x180047833  pop     rbp
0x180047834  retn
0x180047836  lea     rdx, aPkcs11rsaaeswr; "PKCS11RsaAesWrapBlob"
0x18004783d  mov     rcx, rsi; String1
0x180047840  call    wcscmp_0
0x180047845  test    eax, eax
0x180047847  jnz     loc_18004776C
0x18004784d  test    r12, r12
0x180047850  jnz     loc_18008275C
0x180047856  mov     ebx, 0C0000008h
0x18004785b  mov     r9d, 0BDFh
0x180047861  mov     ecx, 0C0000008h
0x180047866  jmp     loc_1800479CF
0x18004786b  lea     rdx, aEccprivateblob; "ECCPRIVATEBLOB"
0x180047872  mov     rcx, rsi; String1
0x180047875  call    wcscmp_0
0x18004787a  test    eax, eax
0x18004787c  jz      loc_180047A3E
0x180047882  lea     rdx, aEccfullpublicb; "ECCFULLPUBLICBLOB"
0x180047889  mov     rcx, rsi; String1
0x18004788c  call    wcscmp_0
0x180047891  test    eax, eax
0x180047893  jnz     loc_180047A52
0x180047899  mov     rax, [rbp+arg_40]
0x18004789d  mov     [rax], r14d
0x1800478a0  xor     eax, eax
0x1800478a2  mov     r9d, [rbp+arg_38]
0x1800478a6  lea     rcx, [rbp+P]
0x1800478aa  mov     [rsp+60h+var_30], rcx
0x1800478af  mov     r8d, ebx
0x1800478b2  mov     ecx, [rbp+arg_30]
0x1800478b5  mov     rdx, r13
0x1800478b8  mov     dword ptr [rsp+60h+var_38], ecx
0x1800478bc  mov     rcx, [rbp+var_10]
0x1800478c0  mov     dword ptr [rsp+60h+var_40], eax
0x1800478c4  call    ImportEccKeyBlobWithParameters
0x1800478c9  jmp     loc_1800477F5
0x1800478ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800478d5  lea     rax, WPP_GLOBAL_Control
0x1800478dc  cmp     rcx, rax
0x1800478df  jz      loc_180047819
0x1800478e5  test    byte ptr [rcx+1Ch], 1
0x1800478e9  jz      loc_180047819
0x1800478ef  mov     dword ptr [rsp+60h+var_30], 0BCDh
0x1800478f7  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800478fe  mov     [rsp+60h+var_38], r8
0x180047903  mov     dword ptr [rsp+60h+var_40], ebx
0x180047907  mov     rcx, [rcx+10h]
0x18004790b  lea     r9, aStatus; "Status"
0x180047912  call    WPP_SF_sDsd
0x180047917  jmp     loc_180047819
0x18004791c  mov     ebx, 0C000000Dh
0x180047921  mov     rcx, cs:WPP_GLOBAL_Control
0x180047928  lea     rax, WPP_GLOBAL_Control
0x18004792f  cmp     rcx, rax
0x180047932  jz      loc_180047819
0x180047938  test    byte ptr [rcx+1Ch], 1
0x18004793c  jz      loc_180047819
0x180047942  mov     dword ptr [rsp+60h+var_30], 0BC6h
0x18004794a  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180047951  mov     [rsp+60h+var_38], r8
0x180047956  mov     dword ptr [rsp+60h+var_40], 0C000000Dh
0x18004795e  jmp     short loc_180047907
0x180047960  test    ecx, ecx
0x180047962  jnz     loc_1800478A2
0x180047968  jmp     loc_1800477C7
0x18004796d  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180047974  lea     rdx, aStatus; "Status"
0x18004797b  mov     ecx, eax
0x18004797d  call    DebugTraceError
0x180047982  test    r14, r14
0x180047985  jz      loc_180047810
0x18004798b  mov     edx, [rbp+arg_38]
0x18004798e  mov     rcx, r14; P
0x180047991  call    MSCryptEccDestroyKeyPair
0x180047996  jmp     loc_180047810
0x18004799b  mov     ecx, r12d
0x18004799e  mov     rax, r15
0x1800479a1  test    r12d, r12d
0x1800479a4  jz      short loc_1800479B2
0x1800479a6  mov     byte ptr [rax], 0
0x1800479a9  inc     rax
0x1800479ac  sub     rcx, 1
0x1800479b0  jnz     short loc_1800479A6
0x1800479b2  mov     rcx, r15
0x1800479b5  call    MSCryptFree
0x1800479ba  jmp     loc_180047819
0x1800479bf  mov     ebx, 0C00000BBh
0x1800479c4  mov     r9d, 0C08h
0x1800479ca  mov     ecx, 0C00000BBh
0x1800479cf  lea     rdx, aStatus; "Status"
0x1800479d6  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800479dd  call    DebugTraceError
0x1800479e2  jmp     loc_180047819
0x1800479e7  cmp     dword ptr [r13+0], 50444345h
0x1800479ef  mov     rax, [rbp+arg_40]
0x1800479f3  mov     [rax], r14d
0x1800479f6  jz      loc_180082811
0x1800479fc  cmp     dword ptr [r13+0], 504B4345h
0x180047a04  jz      loc_180082811
0x180047a0a  xor     ecx, ecx
0x180047a0c  jmp     loc_180082816
0x180047a11  cmp     dword ptr [r13+0], 56444345h
0x180047a19  mov     rax, [rbp+arg_40]
0x180047a1d  mov     dword ptr [rax], 1
0x180047a23  jz      loc_18008281D
0x180047a29  cmp     dword ptr [r13+0], 564B4345h
0x180047a31  jz      loc_18008281D
0x180047a37  xor     ecx, ecx
0x180047a39  jmp     loc_180082822
0x180047a3e  mov     rax, [rbp+arg_40]
0x180047a42  mov     dword ptr [rax], 1
0x180047a48  mov     eax, 1
0x180047a4d  jmp     loc_1800477C7
0x180047a52  lea     rdx, aEccfullprivate; "ECCFULLPRIVATEBLOB"
0x180047a59  mov     rcx, rsi; String1
0x180047a5c  call    wcscmp_0
0x180047a61  test    eax, eax
0x180047a63  jnz     loc_18008282C
0x180047a69  mov     rax, [rbp+arg_40]
0x180047a6d  mov     dword ptr [rax], 1
0x180047a73  mov     eax, 1
0x180047a78  jmp     loc_1800478A2
0x180047a7d  mov     r14, [rbp+P]
0x180047a81  mov     eax, ebx
0x180047a83  mov     r9d, 0C5Bh
0x180047a89  jmp     loc_18004796D
0x180047a8e  mov     r12d, [rbp+var_20]
0x180047a92  mov     ebx, 0C000000Dh
0x180047a97  mov     eax, 0C000000Dh
0x180047a9c  mov     r9d, 0BD5h
0x180047aa2  jmp     loc_18004796D
0x18008275c  mov     rsi, [rbp+arg_0]
0x180082760  lea     r9, [rbp+var_20]
0x180082764  mov     rcx, rsi
0x180082767  mov     dword ptr [rsp+60h+var_38], ebx
0x18008276b  xor     r8d, r8d
0x18008276e  mov     [rsp+60h+var_40], r13
0x180082773  mov     rdx, r12
0x180082776  call    Pkcs11ConvertToKeyBlob
0x18008277b  mov     ebx, eax
0x18008277d  test    eax, eax
0x18008277f  jns     short loc_18008278E
0x180082781  mov     r9d, 0BEBh
0x180082787  mov     ecx, eax
0x180082789  jmp     loc_1800479CF
0x18008278e  mov     ecx, [rbp+var_20]
0x180082791  call    SafeAllocaAllocateFromHeap
0x180082796  mov     r15, rax
0x180082799  test    rax, rax
0x18008279c  jnz     short loc_1800827B3
0x18008279e  mov     ebx, 0C0000017h
0x1800827a3  mov     r9d, 0BF2h
0x1800827a9  mov     ecx, 0C0000017h
0x1800827ae  jmp     loc_1800479CF
0x1800827b3  mov     eax, [rbp+arg_28]
0x1800827b6  lea     r9, [rbp+var_20]
0x1800827ba  mov     dword ptr [rsp+60h+var_38], eax
0x1800827be  mov     r8, r15
0x1800827c1  mov     rdx, r12
0x1800827c4  mov     [rsp+60h+var_40], r13
0x1800827c9  mov     rcx, rsi
0x1800827cc  call    Pkcs11ConvertToKeyBlob
0x1800827d1  mov     ebx, eax
0x1800827d3  test    eax, eax
0x1800827d5  jns     short loc_1800827FB
0x1800827d7  mov     r9d, 0BFEh
0x1800827dd  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800827e4  lea     rdx, aStatus; "Status"
0x1800827eb  mov     ecx, eax
0x1800827ed  call    DebugTraceError
0x1800827f2  mov     r12d, [rbp+var_20]
0x1800827f6  jmp     loc_18004799B
0x1800827fb  mov     r12d, [rbp+var_20]
0x1800827ff  lea     rsi, aEccprivateblob; "ECCPRIVATEBLOB"
0x180082806  mov     ebx, r12d
0x180082809  mov     r13, r15
0x18008280c  jmp     loc_180047779
0x180082811  mov     ecx, 1
0x180082816  xor     eax, eax
0x180082818  jmp     loc_180047960
0x18008281d  mov     ecx, 1
0x180082822  mov     eax, 1
0x180082827  jmp     loc_180047960
0x18008282c  mov     r9d, 0C3Eh
0x180082832  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180082839  lea     rdx, aStatus; "Status"
0x180082840  mov     ecx, 0C00000BBh
0x180082845  mov     ebx, 0C00000BBh
0x18008284a  call    DebugTraceError
0x18008284f  nop
0x180082850  jmp     loc_180047810
```
