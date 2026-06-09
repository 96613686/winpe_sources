# MSCryptImportDHKeyPair

- ea: `0x1800686e0`
- end: `0x180068aaf`
- name: `MSCryptImportDHKeyPair`
- size: `975`
- prototype: `__int64 __fastcall(__int64, __int64, const wchar_t *, __int64 *, _DWORD *, int, unsigned int)`
- caller_count: `0`
- callee_count: `15`
- tags: `broker_com_uri`

## callees

- `0x18000ecb0`
- `0x180010270`
- `0x1800102a0`
- `0x18001b67c`
- `0x18001bf34`
- `0x18001bf88`
- `0x18001c380`
- `0x18001c420`
- `0x18001c878`
- `0x180050ab8`
- `0x180056cf0`
- `0x1800581c0`
- `0x180058288`
- `0x1800686e0`
- `0x18007f765`

## string_xrefs

- `0x180068790`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dh.c`
- `0x180068a5b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dh.c`

## pseudocode

```c
__int64 __fastcall MSCryptImportDHKeyPair(
        __int64 a1,
        __int64 a2,
        const wchar_t *a3,
        __int64 *a4,
        _DWORD *a5,
        int a6,
        unsigned int a7)
{
  int v10; // eax
  __int64 v11; // rbx
  __int64 v12; // r9
  __int64 v13; // rcx
  int v14; // ecx
  int v15; // r15d
  int v16; // ebp
  __int64 v17; // rax
  __int64 v18; // rdi
  __int64 v19; // rcx
  __int64 v20; // r9
  __int64 v21; // rax
  __int64 v22; // rdx
  __int64 v23; // r14
  unsigned int v24; // eax
  unsigned int v25; // r11d
  __int64 v26; // rbp
  __int64 v27; // r13
  int v28; // eax
  __int64 v29; // r8
  __int64 v30; // r9
  __int64 v31; // r11
  __int64 v32; // rdx
  __int64 v33; // r14
  int v34; // eax
  __int64 v35; // rcx
  int v36; // r15d
  __int64 v37; // rdx
  int v38; // esi
  __int64 v39; // rax
  unsigned int v40; // eax
  __int64 v41; // rcx
  int v42; // [rsp+20h] [rbp-A8h]
  int v43; // [rsp+70h] [rbp-58h] BYREF
  __int64 v44[10]; // [rsp+78h] [rbp-50h] BYREF
  int v45; // [rsp+F0h] [rbp+28h]
  int v46; // [rsp+F8h] [rbp+30h]

  v43 = 0;
  v44[0] = 0;
  if ( (a7 & 0xFFFFFFC7) != 0 )
    return 3221225485LL;
  if ( a2 )
    return 3221225659LL;
  if ( !a1 || !a3 || !a4 || !a5 || !a6 )
  {
    v18 = 0;
    v20 = 1419;
    goto LABEL_48;
  }
  v10 = ValidateDHAlgorithm(a1, 0, &v43, v44);
  LODWORD(v11) = v10;
  if ( v10 >= 0 )
  {
    if ( !wcscmp_0(a3, L"DHPUBLICBLOB") || !wcscmp_0(a3, L"PUBLICBLOB") )
    {
      if ( *a5 != 1112557636 )
      {
        v12 = 1442;
        goto LABEL_18;
      }
      v14 = 3;
      v15 = 0;
    }
    else
    {
      if ( wcscmp_0(a3, L"DHPRIVATEBLOB") && wcscmp_0(a3, L"PRIVATEBLOB") )
      {
        v12 = 1463;
LABEL_18:
        LODWORD(v11) = -1073741811;
        v13 = 3221225485LL;
        goto LABEL_12;
      }
      if ( *a5 != 1448101956 )
      {
        v12 = 1454;
        goto LABEL_18;
      }
      v14 = 4;
      v15 = 1;
    }
    v16 = a5[1];
    if ( a6 != (unsigned int)(v16 * v14) + 8LL || (unsigned int)(v16 - 64) > 0x1C0 )
    {
      v12 = 1476;
      goto LABEL_18;
    }
    v17 = SafeAllocaAllocateFromHeap(40);
    v18 = v17;
    if ( !v17 )
    {
      LODWORD(v11) = -1073741801;
      v19 = 3221225495LL;
      v20 = 1489;
      goto LABEL_49;
    }
    *(_QWORD *)(v17 + 8) = 0;
    *(_QWORD *)(v17 + 16) = 0;
    *(_QWORD *)(v17 + 24) = 0;
    *(_QWORD *)(v17 + 32) = 0;
    *(_DWORD *)v17 = 40;
    *(_DWORD *)(v17 + 4) = 1297304409;
    *(_DWORD *)(v17 + 8) = *(_DWORD *)(v44[0] + 8);
    *(_DWORD *)(v17 + 12) = v16;
    v21 = SymCryptDlgroupAllocate((unsigned int)(8 * v16), 0);
    *(_QWORD *)(v18 + 24) = v21;
    if ( !v21 )
    {
      LODWORD(v11) = -1073741801;
      v19 = 3221225495LL;
      v20 = 1508;
      goto LABEL_49;
    }
    v22 = *(unsigned int *)(v18 + 12);
    v23 = (__int64)a5 + v22 + 8;
    v24 = SymCryptDlgroupSetValue((int)a5 + 8, v22, 0, 0, v23, *(_DWORD *)(v18 + 12), 2, 0, 0, 0, 0, 0, v21);
    if ( v24 )
    {
      v11 = (unsigned int)SymcryptErrorCodeToNtStatus(v24);
      v19 = v11;
      v20 = 1532;
      goto LABEL_49;
    }
    v25 = *(_DWORD *)(v18 + 12);
    *(_DWORD *)(v18 + 16) |= 2u;
    v26 = 0;
    v27 = 2 * v25;
    v28 = IsAllZeros((char *)a5 + v27 + 8, v25);
    if ( !v28 )
      v26 = v23 + v31;
    v32 = (unsigned int)v31;
    if ( v28 )
      v32 = 0;
    v46 = v32;
    v45 = v15 != 0 ? v31 : 0;
    v33 = (v23 + v27) & -(__int64)(v15 != 0);
    if ( (a7 & 0x20) == 0 || v33 && v26 )
    {
      v34 = BCryptFlagsToSymCryptKeyValidationFlags(a7, v32, v29, v30);
      v35 = *(_QWORD *)(v18 + 24);
      v36 = v34;
      LOBYTE(v37) = -*(_BYTE *)(v35 + 40);
      v38 = *(_BYTE *)(v35 + 40) != 0 ? 0x2000 : 8448;
      v39 = SymCryptDlkeyAllocate(v35, v37);
      *(_QWORD *)(v18 + 32) = v39;
      if ( v39 )
      {
        v40 = SymCryptDlkeySetValue(v33, v45, v26, v46, v42, v36 | (unsigned int)v38, v39);
        if ( !v40 )
        {
          *(_DWORD *)(v18 + 16) |= 1u;
          *a4 = v18;
          return (unsigned int)v11;
        }
        v11 = (unsigned int)SymcryptErrorCodeToNtStatus(v40);
        v19 = v11;
        v20 = 1593;
      }
      else
      {
        LODWORD(v11) = -1073741801;
        v19 = 3221225495LL;
        v20 = 1578;
      }
LABEL_49:
      DebugTraceError(v19, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\dsa\\dh.c", v20);
      if ( v18 )
      {
        if ( *(_QWORD *)(v18 + 32) )
        {
          SymCryptDlkeyFree();
          *(_QWORD *)(v18 + 32) = 0;
        }
        v41 = *(_QWORD *)(v18 + 24);
        if ( v41 )
        {
          SymCryptMlDsaTemporariesFree(v41);
          *(_QWORD *)(v18 + 24) = 0;
        }
        MSCryptFree(v18);
      }
      return (unsigned int)v11;
    }
    v20 = 1559;
LABEL_48:
    v19 = 3221225485LL;
    LODWORD(v11) = -1073741811;
    goto LABEL_49;
  }
  v12 = 1426;
  v13 = (unsigned int)v10;
LABEL_12:
  DebugTraceError(v13, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\dsa\\dh.c", v12);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800686e0  push    rbx
0x1800686e2  push    rbp
0x1800686e3  push    rsi
0x1800686e4  push    rdi
0x1800686e5  push    r12
0x1800686e7  push    r13
0x1800686e9  push    r14
0x1800686eb  push    r15
0x1800686ed  sub     rsp, 88h
0x1800686f4  xor     r13d, r13d
0x1800686f7  mov     r12, r9
0x1800686fa  test    [rsp+0C8h+arg_30], 0FFFFFFC7h
0x180068705  mov     rdi, r8
0x180068708  mov     [rsp+0C8h+var_58], r13d
0x18006870d  mov     [rsp+0C8h+var_50], r13
0x180068712  jz      short loc_18006871E
0x180068714  mov     eax, 0C000000Dh
0x180068719  jmp     loc_180068A9A
0x18006871e  test    rdx, rdx
0x180068721  jz      short loc_18006872D
0x180068723  mov     eax, 0C00000BBh
0x180068728  jmp     loc_180068A9A
0x18006872d  test    rcx, rcx
0x180068730  jz      loc_180068A41
0x180068736  test    rdi, rdi
0x180068739  jz      loc_180068A41
0x18006873f  test    r12, r12
0x180068742  jz      loc_180068A41
0x180068748  mov     rsi, [rsp+0C8h+arg_20]
0x180068750  test    rsi, rsi
0x180068753  jz      loc_180068A41
0x180068759  mov     r14d, [rsp+0C8h+arg_28]
0x180068761  test    r14d, r14d
0x180068764  jz      loc_180068A41
0x18006876a  lea     r9, [rsp+0C8h+var_50]
0x18006876f  xor     edx, edx
0x180068771  lea     r8, [rsp+0C8h+var_58]
0x180068776  call    ValidateDHAlgorithm
0x18006877b  mov     ebx, eax
0x18006877d  test    eax, eax
0x18006877f  jns     short loc_1800687A1
0x180068781  mov     r9d, 592h
0x180068787  mov     ecx, eax
0x180068789  lea     rdx, aStatus; "Status"
0x180068790  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180068797  call    DebugTraceError
0x18006879c  jmp     loc_180068A98
0x1800687a1  lea     rdx, aDhpublicblob; "DHPUBLICBLOB"
0x1800687a8  mov     rcx, rdi; String1
0x1800687ab  call    wcscmp_0
0x1800687b0  test    eax, eax
0x1800687b2  jz      short loc_18006881A
0x1800687b4  lea     rdx, aPublicblob; "PUBLICBLOB"
0x1800687bb  mov     rcx, rdi; String1
0x1800687be  call    wcscmp_0
0x1800687c3  test    eax, eax
0x1800687c5  jz      short loc_18006881A
0x1800687c7  lea     rdx, aDhprivateblob; "DHPRIVATEBLOB"
0x1800687ce  mov     rcx, rdi; String1
0x1800687d1  call    wcscmp_0
0x1800687d6  test    eax, eax
0x1800687d8  jz      short loc_1800687FF
0x1800687da  lea     rdx, aPrivateblob; "PRIVATEBLOB"
0x1800687e1  mov     rcx, rdi; String1
0x1800687e4  call    wcscmp_0
0x1800687e9  test    eax, eax
0x1800687eb  jz      short loc_1800687FF
0x1800687ed  mov     r9d, 5B7h
0x1800687f3  mov     ebx, 0C000000Dh
0x1800687f8  mov     ecx, 0C000000Dh
0x1800687fd  jmp     short loc_180068789
0x1800687ff  cmp     dword ptr [rsi], 56504844h
0x180068805  jz      short loc_18006880F
0x180068807  mov     r9d, 5AEh
0x18006880d  jmp     short loc_1800687F3
0x18006880f  mov     ecx, 4
0x180068814  lea     r15d, [rcx-3]
0x180068818  jmp     short loc_180068832
0x18006881a  cmp     dword ptr [rsi], 42504844h
0x180068820  jz      short loc_18006882A
0x180068822  mov     r9d, 5A2h
0x180068828  jmp     short loc_1800687F3
0x18006882a  mov     ecx, 3
0x18006882f  mov     r15d, r13d
0x180068832  mov     ebp, [rsi+4]
0x180068835  imul    ecx, ebp
0x180068838  add     rcx, 8
0x18006883c  cmp     r14, rcx
0x18006883f  jnz     loc_180068A36
0x180068845  lea     eax, [rbp-40h]
0x180068848  cmp     eax, 1C0h
0x18006884d  ja      loc_180068A36
0x180068853  mov     r14d, 28h ; '('
0x180068859  mov     ecx, r14d
0x18006885c  call    SafeAllocaAllocateFromHeap
0x180068861  mov     rdi, rax
0x180068864  test    rax, rax
0x180068867  jnz     short loc_18006887E
0x180068869  mov     ebx, 0C0000017h
0x18006886e  mov     ecx, 0C0000017h
0x180068873  mov     r9d, 5D1h
0x180068879  jmp     loc_180068A54
0x18006887e  mov     [rax+8], r13
0x180068882  xor     edx, edx
0x180068884  mov     [rax+10h], r13
0x180068888  mov     [rax+18h], r13
0x18006888c  mov     [rax+20h], r13
0x180068890  mov     [rax], r14d
0x180068893  mov     dword ptr [rax+4], 4D534B59h
0x18006889a  mov     rax, [rsp+0C8h+var_50]
0x18006889f  mov     ecx, [rax+8]
0x1800688a2  mov     [rdi+8], ecx
0x1800688a5  lea     ecx, ds:0[rbp*8]
0x1800688ac  mov     [rdi+0Ch], ebp
0x1800688af  call    SymCryptDlgroupAllocate
0x1800688b4  mov     [rdi+18h], rax
0x1800688b8  test    rax, rax
0x1800688bb  jnz     short loc_1800688D2
0x1800688bd  mov     ebx, 0C0000017h
0x1800688c2  mov     ecx, 0C0000017h
0x1800688c7  mov     r9d, 5E4h
0x1800688cd  jmp     loc_180068A54
0x1800688d2  mov     edx, [rdi+0Ch]; int
0x1800688d5  lea     rcx, [rsi+8]; int
0x1800688d9  mov     [rsp+0C8h+var_68], rax; __int64
0x1800688de  xor     r9d, r9d; int
0x1800688e1  mov     [rsp+0C8h+var_70], r13d; int
0x1800688e6  xor     r8d, r8d; int
0x1800688e9  mov     [rsp+0C8h+var_78], r13d; int
0x1800688ee  mov     [rsp+0C8h+Size], r13; Size
0x1800688f3  lea     r14, [rdx+rcx]
0x1800688f7  mov     [rsp+0C8h+var_88], r13; __int64
0x1800688fc  mov     [rsp+0C8h+var_90], r13; __int64
0x180068901  mov     [rsp+0C8h+var_98], 2; int
0x180068909  mov     qword ptr [rsp+0C8h+var_A0], rdx; int
0x18006890e  mov     [rsp+0C8h+var_A8], r14; __int64
0x180068913  call    SymCryptDlgroupSetValue
0x180068918  test    eax, eax
0x18006891a  jz      short loc_180068932
0x18006891c  mov     ecx, eax
0x18006891e  call    SymcryptErrorCodeToNtStatus
0x180068923  mov     ebx, eax
0x180068925  mov     ecx, eax
0x180068927  mov     r9d, 5FCh
0x18006892d  jmp     loc_180068A54
0x180068932  mov     r11d, [rdi+0Ch]
0x180068936  lea     rcx, [rsi+8]
0x18006893a  or      dword ptr [rdi+10h], 2
0x18006893e  mov     rbp, r13
0x180068941  mov     edx, r11d
0x180068944  lea     r13d, [r11+r11]
0x180068948  add     rcx, r13
0x18006894b  call    IsAllZeros
0x180068950  test    eax, eax
0x180068952  jnz     short loc_180068958
0x180068954  lea     rbp, [r14+r11]
0x180068958  xor     ecx, ecx
0x18006895a  mov     edx, r11d
0x18006895d  test    eax, eax
0x18006895f  mov     eax, r15d
0x180068962  cmovnz  edx, ecx
0x180068965  neg     eax
0x180068967  mov     [rsp+0C8h+arg_28], edx
0x18006896e  sbb     eax, eax
0x180068970  and     eax, r11d
0x180068973  neg     r15d
0x180068976  mov     dword ptr [rsp+0C8h+arg_20], eax
0x18006897d  lea     rax, [r14+r13]
0x180068981  sbb     r14, r14
0x180068984  xor     r13d, r13d
0x180068987  and     r14, rax
0x18006898a  test    byte ptr [rsp+0C8h+arg_30], 20h
0x180068992  jz      short loc_1800689A9
0x180068994  test    r14, r14
0x180068997  jz      short loc_18006899E
0x180068999  test    rbp, rbp
0x18006899c  jnz     short loc_1800689A9
0x18006899e  mov     r9d, 617h
0x1800689a4  jmp     loc_180068A4A
0x1800689a9  mov     ecx, [rsp+0C8h+arg_30]
0x1800689b0  call    BCryptFlagsToSymCryptKeyValidationFlags
0x1800689b5  mov     rcx, [rdi+18h]
0x1800689b9  mov     r15d, eax
0x1800689bc  mov     dl, [rcx+28h]
0x1800689bf  neg     dl
0x1800689c1  sbb     esi, esi
0x1800689c3  and     esi, 0FFFFFF00h
0x1800689c9  add     esi, 2100h
0x1800689cf  call    SymCryptDlkeyAllocate
0x1800689d4  mov     [rdi+20h], rax
0x1800689d8  test    rax, rax
0x1800689db  jnz     short loc_1800689EF
0x1800689dd  mov     ebx, 0C0000017h
0x1800689e2  mov     ecx, 0C0000017h
0x1800689e7  mov     r9d, 62Ah
0x1800689ed  jmp     short loc_180068A54
0x1800689ef  mov     r9d, [rsp+0C8h+arg_28]
0x1800689f7  or      esi, r15d
0x1800689fa  mov     edx, dword ptr [rsp+0C8h+arg_20]
0x180068a01  mov     r8, rbp
0x180068a04  mov     qword ptr [rsp+0C8h+var_98], rax
0x180068a09  mov     rcx, r14
0x180068a0c  mov     [rsp+0C8h+var_A0], esi
0x180068a10  call    SymCryptDlkeySetValue
0x180068a15  test    eax, eax
0x180068a17  jz      short loc_180068A2C
0x180068a19  mov     ecx, eax
0x180068a1b  call    SymcryptErrorCodeToNtStatus
0x180068a20  mov     ebx, eax
0x180068a22  mov     ecx, eax
0x180068a24  mov     r9d, 639h
0x180068a2a  jmp     short loc_180068A54
0x180068a2c  or      dword ptr [rdi+10h], 1
0x180068a30  mov     [r12], rdi
0x180068a34  jmp     short loc_180068A98
0x180068a36  mov     r9d, 5C4h
0x180068a3c  jmp     loc_1800687F3
0x180068a41  mov     rdi, r13
0x180068a44  mov     r9d, 58Bh
0x180068a4a  mov     ecx, 0C000000Dh
0x180068a4f  mov     ebx, 0C000000Dh
0x180068a54  lea     rdx, aStatus; "Status"
0x180068a5b  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180068a62  call    DebugTraceError
0x180068a67  test    rdi, rdi
0x180068a6a  jz      short loc_180068A98
0x180068a6c  mov     rcx, [rdi+20h]
0x180068a70  test    rcx, rcx
0x180068a73  jz      short loc_180068A7E
0x180068a75  call    SymCryptDlkeyFree
0x180068a7a  mov     [rdi+20h], r13
0x180068a7e  mov     rcx, [rdi+18h]
0x180068a82  test    rcx, rcx
0x180068a85  jz      short loc_180068A90
0x180068a87  call    SymCryptMlDsaTemporariesFree
0x180068a8c  mov     [rdi+18h], r13
0x180068a90  mov     rcx, rdi
0x180068a93  call    MSCryptFree
0x180068a98  mov     eax, ebx
0x180068a9a  add     rsp, 88h
0x180068aa1  pop     r15
0x180068aa3  pop     r14
0x180068aa5  pop     r13
0x180068aa7  pop     r12
0x180068aa9  pop     rdi
0x180068aaa  pop     rsi
0x180068aab  pop     rbp
0x180068aac  pop     rbx
0x180068aad  retn
```
