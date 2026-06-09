# MSCryptKDGetProperty

- ea: `0x18000cc40`
- end: `0x18000cfa6`
- name: `MSCryptKDGetProperty`
- size: `870`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18000cc40`
- `0x18000ecb0`
- `0x18000ee60`
- `0x18004729c`
- `0x180063170`
- `0x18007f765`

## string_xrefs

- `0x18000cd7a`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x18000cddd`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x18000ce11`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x18000ce50`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x18000cea6`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x18000cee0`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x18000cf3f`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x18000cf4e`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x180080030`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x1800800ff`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x18008012d`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x180080182`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`

## pseudocode

```c
__int64 __fastcall MSCryptKDGetProperty(
        _DWORD *a1,
        const wchar_t *a2,
        _DWORD *a3,
        unsigned int a4,
        unsigned int *a5,
        int a6)
{
  unsigned int *v6; // rdi
  size_t v8; // r12
  unsigned int v11; // ebx
  int v12; // r13d
  int v13; // esi
  int v14; // edx
  int v15; // r8d
  unsigned int v16; // esi
  __int64 result; // rax
  int v18; // eax
  _QWORD *v19; // rcx
  unsigned int v20; // r14d
  __int64 v21; // r9
  const wchar_t *v22; // rdx
  __int64 v23; // rbx

  v6 = a5;
  v8 = a4;
  v11 = *a5;
  LODWORD(a5) = *a5;
  if ( !a1 )
  {
    v16 = -1073741816;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
        117);
    goto LABEL_15;
  }
  if ( a6 )
  {
    v16 = -1073741811;
    DebugTraceError(
      3221225485LL,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
      892);
    goto LABEL_15;
  }
  v12 = a1[1];
  if ( v12 != 1297301836 && v12 != 1297304409 )
  {
    v21 = 208;
LABEL_39:
    DebugTraceError(
      3221225480LL,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
      v21);
    v16 = -1073741816;
    goto LABEL_15;
  }
  v13 = a1[2];
  if ( (unsigned int)(v13 - 393217) > 6 )
  {
    v21 = 221;
    goto LABEL_39;
  }
  if ( !wcscmp_0(a2, L"AlgorithmName") )
  {
    switch ( v13 )
    {
      case 393217:
        v22 = L"SP800_108_CTR_HMAC";
        goto LABEL_48;
      case 393218:
        v22 = L"SP800_56A_CONCAT";
        goto LABEL_48;
      case 393219:
        v22 = L"PBKDF2";
        goto LABEL_48;
      case 393220:
        v22 = L"CAPI_KDF";
        goto LABEL_48;
      case 393221:
        v22 = L"TLS1_1_KDF";
        goto LABEL_48;
      case 393222:
        v22 = L"TLS1_2_KDF";
        goto LABEL_48;
      case 393223:
        v22 = L"HKDF";
LABEL_48:
        v23 = -1;
        while ( v22[++v23] != 0 )
          ;
        v11 = 2 * v23 + 2;
        if ( !a3 )
          goto LABEL_14;
        if ( (unsigned int)v8 >= v11 )
        {
          memcpy_0(a3, v22, v8);
          v16 = 0;
        }
        else
        {
          v16 = -1073741789;
        }
        break;
      default:
        v16 = -1073741637;
        DebugTraceError(
          3221225659LL,
          "Status",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
          952);
        goto LABEL_15;
    }
    goto LABEL_15;
  }
  if ( v12 != 1297301836 )
  {
    v18 = MSCryptKDGetKeyProperty(a1, a2, a3, (unsigned int)v8, &a5);
    v16 = v18;
    if ( v18 < 0 )
      DebugTraceError(
        (unsigned int)v18,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
        1007);
    v11 = (unsigned int)a5;
    goto LABEL_15;
  }
  if ( *a1 != 20 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v14,
        v15,
        (unsigned int)"Status",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
        17);
      v19 = WPP_GLOBAL_Control;
    }
    goto LABEL_24;
  }
  if ( (unsigned int)(v13 - 393217) > 6 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v14,
        v15,
        (unsigned int)"Status",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
        30);
      v19 = WPP_GLOBAL_Control;
    }
LABEL_24:
    v16 = -1073741816;
    v20 = -1073741816;
    if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 1) != 0 )
      WPP_SF_sDsd(
        v19[2],
        v14,
        v15,
        (unsigned int)"Status",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
        96);
    goto LABEL_27;
  }
  if ( wcscmp_0(a2, L"KeyLengths") )
  {
    if ( !wcscmp_0(a2, L"ObjectLength") )
    {
      v11 = 4;
      if ( !a3 )
      {
LABEL_14:
        v16 = 0;
        goto LABEL_15;
      }
      if ( (unsigned int)v8 >= 4 )
      {
        *a3 = a1[3];
        goto LABEL_14;
      }
      v16 = -1073741789;
      v20 = -1073741789;
    }
    else
    {
      v16 = -1073741637;
      v20 = -1073741637;
      DebugTraceError(
        3221225659LL,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
        712);
    }
LABEL_27:
    DebugTraceError(
      v20,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
      991);
    goto LABEL_15;
  }
  if ( !a3 )
  {
    v11 = 12;
    v16 = 0;
    goto LABEL_15;
  }
  if ( (unsigned int)v8 < 0xC )
  {
    v16 = -1073741789;
    v20 = -1073741789;
    v11 = 12;
    goto LABEL_27;
  }
  switch ( v13 )
  {
    case 393217:
    case 393218:
    case 393219:
    case 393220:
    case 393221:
    case 393222:
    case 393223:
      v16 = 0;
      v11 = 12;
      *a3 = 0;
      a3[1] = 0x4000;
      a3[2] = 8;
      break;
    default:
      v16 = -1073741637;
      v20 = -1073741637;
      DebugTraceError(
        3221225659LL,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
        683);
      v11 = 12;
      goto LABEL_27;
  }
LABEL_15:
  result = v16;
  *v6 = v11;
  return result;
}

```

## disassembly

```asm
0x18000cc40  mov     rax, rsp
0x18000cc43  mov     [rax+10h], rbx
0x18000cc47  mov     [rax+18h], rbp
0x18000cc4b  push    rsi
0x18000cc4c  push    rdi
0x18000cc4d  push    r12
0x18000cc4f  push    r14
0x18000cc51  push    r15
0x18000cc53  sub     rsp, 40h
0x18000cc57  mov     rdi, [rsp+68h+arg_20]
0x18000cc5f  mov     r14, r8
0x18000cc62  mov     r12d, r9d
0x18000cc65  mov     r15, rdx
0x18000cc68  mov     rbp, rcx
0x18000cc6b  mov     ebx, [rdi]
0x18000cc6d  mov     [rax+28h], ebx
0x18000cc70  test    rcx, rcx
0x18000cc73  jz      loc_18000CD58
0x18000cc79  cmp     [rsp+68h+arg_28], 0
0x18000cc81  jnz     loc_18000CEDA
0x18000cc87  mov     [rax+8], r13
0x18000cc8b  mov     r13d, [rcx+4]
0x18000cc8f  cmp     r13d, 4D53414Ch
0x18000cc96  jnz     loc_18000CF02
0x18000cc9c  mov     esi, [rcx+8]
0x18000cc9f  lea     eax, [rsi-60001h]
0x18000cca5  cmp     eax, 6
0x18000cca8  ja      loc_18000CF1A
0x18000ccae  lea     rdx, aAlgorithmname; "AlgorithmName"
0x18000ccb5  mov     rcx, r15; String1
0x18000ccb8  call    wcscmp_0
0x18000ccbd  test    eax, eax
0x18000ccbf  jz      loc_180080052
0x18000ccc5  cmp     r13d, 4D53414Ch
0x18000cccc  jnz     loc_18000CDA4
0x18000ccd2  cmp     dword ptr [rbp+0], 14h
0x18000ccd6  jnz     loc_18000CDF8
0x18000ccdc  lea     eax, [rsi-60001h]
0x18000cce2  cmp     eax, 6
0x18000cce5  ja      loc_18000CE81
0x18000cceb  lea     rdx, aKeylengths; "KeyLengths"
0x18000ccf2  mov     rcx, r15; String1
0x18000ccf5  call    wcscmp_0
0x18000ccfa  test    eax, eax
0x18000ccfc  jz      loc_18000CF25
0x18000cd02  lea     rdx, aObjectlength; "ObjectLength"
0x18000cd09  mov     rcx, r15; String1
0x18000cd0c  call    wcscmp_0
0x18000cd11  test    eax, eax
0x18000cd13  jnz     loc_18000CF4E
0x18000cd19  mov     ebx, 4
0x18000cd1e  test    r14, r14
0x18000cd21  jz      short loc_18000CD32
0x18000cd23  cmp     r12d, ebx
0x18000cd26  jb      loc_18000CF3A
0x18000cd2c  mov     eax, [rbp+0Ch]
0x18000cd2f  mov     [r14], eax
0x18000cd32  xor     esi, esi
0x18000cd34  mov     r13, [rsp+68h+arg_0]
0x18000cd39  mov     rbp, [rsp+68h+arg_10]
0x18000cd41  mov     eax, esi
0x18000cd43  mov     [rdi], ebx
0x18000cd45  mov     rbx, [rsp+68h+arg_8]
0x18000cd4a  add     rsp, 40h
0x18000cd4e  pop     r15
0x18000cd50  pop     r14
0x18000cd52  pop     r12
0x18000cd54  pop     rdi
0x18000cd55  pop     rsi
0x18000cd56  retn
0x18000cd58  mov     esi, 0C0000008h
0x18000cd5d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cd64  lea     rbp, WPP_GLOBAL_Control
0x18000cd6b  cmp     rcx, rbp
0x18000cd6e  jz      short loc_18000CD39
0x18000cd70  test    byte ptr [rcx+1Ch], 1
0x18000cd74  jz      short loc_18000CD39
0x18000cd76  mov     rcx, [rcx+10h]
0x18000cd7a  lea     r15, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000cd81  mov     [rsp+68h+var_38], 375h
0x18000cd89  lea     r9, aStatus; "Status"
0x18000cd90  mov     [rsp+68h+var_40], r15
0x18000cd95  mov     dword ptr [rsp+68h+var_48], 0C0000008h
0x18000cd9d  call    WPP_SF_sDsd
0x18000cda2  jmp     short loc_18000CD39
0x18000cda4  xor     esi, esi
0x18000cda6  cmp     r13d, 4D534B59h
0x18000cdad  jnz     short loc_18000CD34
0x18000cdaf  lea     rax, [rsp+68h+arg_20]
0x18000cdb7  mov     r9d, r12d
0x18000cdba  mov     r8, r14
0x18000cdbd  mov     [rsp+68h+var_48], rax
0x18000cdc2  mov     rdx, r15
0x18000cdc5  mov     rcx, rbp
0x18000cdc8  call    MSCryptKDGetKeyProperty
0x18000cdcd  mov     esi, eax
0x18000cdcf  test    eax, eax
0x18000cdd1  jns     loc_1800801B5
0x18000cdd7  mov     r9d, 3EFh
0x18000cddd  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000cde4  lea     rdx, aStatus; "Status"
0x18000cdeb  mov     ecx, eax
0x18000cded  call    DebugTraceError
0x18000cdf2  nop
0x18000cdf3  jmp     loc_1800801B5
0x18000cdf8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cdff  lea     rbp, WPP_GLOBAL_Control
0x18000ce06  cmp     rcx, rbp
0x18000ce09  jz      short loc_18000CE11
0x18000ce0b  test    byte ptr [rcx+1Ch], 1
0x18000ce0f  jnz     short loc_18000CE4C
0x18000ce11  lea     r15, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000ce18  mov     esi, 0C0000008h
0x18000ce1d  mov     r14d, esi
0x18000ce20  cmp     rcx, rbp
0x18000ce23  jz      short loc_18000CE2F
0x18000ce25  test    byte ptr [rcx+1Ch], 1
0x18000ce29  jnz     loc_18000CF7C
0x18000ce2f  mov     r9d, 3DFh
0x18000ce35  lea     rdx, aStatus; "Status"
0x18000ce3c  mov     r8, r15
0x18000ce3f  mov     ecx, r14d
0x18000ce42  call    DebugTraceError
0x18000ce47  jmp     loc_18000CD34
0x18000ce4c  mov     rcx, [rcx+10h]
0x18000ce50  lea     r15, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000ce57  mov     [rsp+68h+var_38], 111h
0x18000ce5f  lea     r9, aStatus; "Status"
0x18000ce66  mov     [rsp+68h+var_40], r15
0x18000ce6b  mov     dword ptr [rsp+68h+var_48], 0C0000008h
0x18000ce73  call    WPP_SF_sDsd
0x18000ce78  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ce7f  jmp     short loc_18000CE18
0x18000ce81  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ce88  lea     rbp, WPP_GLOBAL_Control
0x18000ce8f  cmp     rcx, rbp
0x18000ce92  jz      loc_18000CE11
0x18000ce98  test    byte ptr [rcx+1Ch], 1
0x18000ce9c  jz      loc_18000CE11
0x18000cea2  mov     rcx, [rcx+10h]
0x18000cea6  lea     r15, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000cead  mov     [rsp+68h+var_38], 11Eh
0x18000ceb5  lea     r9, aStatus; "Status"
0x18000cebc  mov     [rsp+68h+var_40], r15
0x18000cec1  mov     dword ptr [rsp+68h+var_48], 0C0000008h
0x18000cec9  call    WPP_SF_sDsd
0x18000cece  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ced5  jmp     loc_18000CE18
0x18000ceda  mov     r9d, 37Ch
0x18000cee0  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000cee7  lea     rdx, aStatus; "Status"
0x18000ceee  mov     ecx, 0C000000Dh
0x18000cef3  mov     esi, 0C000000Dh
0x18000cef8  call    DebugTraceError
0x18000cefd  jmp     loc_18000CD39
0x18000cf02  cmp     r13d, 4D534B59h
0x18000cf09  jz      loc_18000CC9C
0x18000cf0f  mov     r9d, 0D0h
0x18000cf15  jmp     loc_180080030
0x18000cf1a  mov     r9d, 0DDh
0x18000cf20  jmp     loc_180080030
0x18000cf25  test    r14, r14
0x18000cf28  jnz     loc_180080122
0x18000cf2e  mov     ebx, 0Ch
0x18000cf33  xor     esi, esi
0x18000cf35  jmp     loc_18000CD34
0x18000cf3a  mov     esi, 0C0000023h
0x18000cf3f  lea     r15, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000cf46  mov     r14d, esi
0x18000cf49  jmp     loc_18000CE2F
0x18000cf4e  lea     r15, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000cf55  mov     esi, 0C00000BBh
0x18000cf5a  mov     r8, r15
0x18000cf5d  lea     rdx, aStatus; "Status"
0x18000cf64  mov     r9d, 2C8h
0x18000cf6a  mov     ecx, 0C00000BBh
0x18000cf6f  mov     r14d, esi
0x18000cf72  call    DebugTraceError
0x18000cf77  jmp     loc_18000CE2F
0x18000cf7c  mov     rcx, [rcx+10h]
0x18000cf80  lea     r9, aStatus; "Status"
0x18000cf87  mov     [rsp+68h+var_38], 260h
0x18000cf8f  mov     [rsp+68h+var_40], r15
0x18000cf94  mov     dword ptr [rsp+68h+var_48], 0C0000008h
0x18000cf9c  call    WPP_SF_sDsd
0x18000cfa1  jmp     loc_18000CE2F
0x180080030  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180080037  mov     ecx, 0C0000008h
0x18008003c  lea     rdx, aStatus; "Status"
0x180080043  call    DebugTraceError
0x180080048  mov     esi, 0C0000008h
0x18008004d  jmp     loc_18000CD34
0x180080052  add     esi, 0FFF9FFFFh; switch 7 cases
0x180080058  cmp     esi, 6
0x18008005b  ja      def_180080072; jumptable 0000000180080072 default case
0x180080061  lea     rcx, cs:180000000h
0x180080068  mov     eax, ds:(jpt_180080072 - 180000000h)[rcx+rsi*4]
0x18008006f  add     rax, rcx
0x180080072  jmp     rax; switch jump
0x180080078  lea     rdx, aSp800108CtrHma; jumptable 0000000180080072 case 393217
0x18008007f  jmp     short loc_1800800B5
0x180080081  lea     rdx, aSp80056aConcat; jumptable 0000000180080072 case 393218
0x180080088  jmp     short loc_1800800B5
0x18008008a  lea     rdx, aPbkdf2; jumptable 0000000180080072 case 393219
0x180080091  jmp     short loc_1800800B5
0x180080093  lea     rdx, aCapiKdf; jumptable 0000000180080072 case 393220
0x18008009a  jmp     short loc_1800800B5
0x18008009c  lea     rdx, aTls11Kdf; jumptable 0000000180080072 case 393221
0x1800800a3  jmp     short loc_1800800B5
0x1800800a5  lea     rdx, aTls12Kdf; jumptable 0000000180080072 case 393222
0x1800800ac  jmp     short loc_1800800B5
0x1800800ae  lea     rdx, aHkdf; jumptable 0000000180080072 case 393223
0x1800800b5  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1800800bc  cmp     word ptr [rdx+rbx*2+2], 0
0x1800800c2  lea     rbx, [rbx+1]
0x1800800c6  jnz     short loc_1800800BC
0x1800800c8  lea     ebx, ds:2[rbx*2]
0x1800800cf  test    r14, r14
0x1800800d2  jz      loc_18000CD32
0x1800800d8  cmp     r12d, ebx
0x1800800db  jnb     short loc_1800800E7
0x1800800dd  mov     esi, 0C0000023h
0x1800800e2  jmp     loc_18000CD34
0x1800800e7  mov     r8, r12; Size
0x1800800ea  mov     rcx, r14; void *
0x1800800ed  call    memcpy_0
0x1800800f2  xor     esi, esi
0x1800800f4  jmp     loc_18000CD34
0x1800800f9  mov     r9d, 3B8h; jumptable 0000000180080072 default case
0x1800800ff  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180080106  lea     rdx, aStatus; "Status"
0x18008010d  mov     ecx, 0C00000BBh
0x180080112  mov     esi, 0C00000BBh
0x180080117  call    DebugTraceError
0x18008011c  nop
0x18008011d  jmp     loc_18000CD34
0x180080122  cmp     r12d, 0Ch
0x180080126  jnb     short loc_180080141
0x180080128  mov     esi, 0C0000023h
0x18008012d  lea     r15, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180080134  mov     r14d, esi
0x180080137  mov     ebx, 0Ch
0x18008013c  jmp     loc_18000CE2F
0x180080141  add     esi, 0FFF9FFFFh; switch 7 cases
0x180080147  cmp     esi, 6
0x18008014a  ja      short def_18008015D; jumptable 000000018008015D default case
0x18008014c  lea     rcx, cs:180000000h
0x180080153  mov     eax, ds:(jpt_18008015D - 180000000h)[rcx+rsi*4]
0x18008015a  add     rax, rcx
0x18008015d  jmp     rax; switch jump
0x180080163  xor     esi, esi; jumptable 000000018008015D cases 393217-393223
0x180080165  mov     ebx, 0Ch
0x18008016a  mov     [r14], esi
0x18008016d  mov     dword ptr [r14+4], 4000h
0x180080175  mov     dword ptr [r14+8], 8
0x18008017d  jmp     loc_18000CD34
0x180080182  lea     r15, aOnecoreDsSecur_2; jumptable 000000018008015D default case
0x180080189  mov     esi, 0C00000BBh
0x18008018e  mov     r8, r15
0x180080191  lea     rdx, aStatus; "Status"
0x180080198  mov     r9d, 2ABh
0x18008019e  mov     ecx, 0C00000BBh
0x1800801a3  mov     r14d, esi
0x1800801a6  call    DebugTraceError
0x1800801ab  mov     ebx, 0Ch
0x1800801b0  jmp     loc_18000CE2F
0x1800801b5  mov     ebx, dword ptr [rsp+68h+arg_20]
0x1800801bc  jmp     loc_18000CD34
```
