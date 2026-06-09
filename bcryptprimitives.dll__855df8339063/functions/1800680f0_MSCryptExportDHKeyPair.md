# MSCryptExportDHKeyPair

- ea: `0x1800680f0`
- end: `0x180068371`
- name: `MSCryptExportDHKeyPair`
- size: `641`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18000ecb0`
- `0x1800525dc`
- `0x180056cf0`
- `0x180058204`
- `0x180063180`
- `0x1800680f0`
- `0x18007186c`
- `0x18007f765`

## string_xrefs

- `0x180068346`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dh.c`

## pseudocode

```c
__int64 __fastcall MSCryptExportDHKeyPair(
        __int64 a1,
        __int64 a2,
        const wchar_t *a3,
        _DWORD *a4,
        unsigned int a5,
        unsigned int *a6,
        int a7)
{
  __int64 v9; // r9
  unsigned int v10; // ebx
  __int64 v11; // rcx
  unsigned int *v12; // r14
  int v13; // eax
  __int64 v14; // rdi
  unsigned int v15; // eax
  unsigned int v16; // ebp
  int v17; // r14d
  unsigned int v18; // ecx
  __int64 v19; // r8
  int v20; // edx
  __int64 v21; // rsi
  unsigned int Value; // eax
  unsigned int v23; // eax
  int v25; // [rsp+40h] [rbp-38h]
  __int64 v26; // [rsp+88h] [rbp+10h] BYREF

  v26 = 0;
  if ( a2 )
  {
    v9 = 1652;
LABEL_3:
    v10 = -1073741637;
    v11 = 3221225659LL;
LABEL_33:
    DebugTraceError(v11, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\dsa\\dh.c", v9);
    return v10;
  }
  if ( !a1 || !a3 || (v12 = a6) == 0 || a7 )
  {
    v9 = 1662;
    goto LABEL_32;
  }
  v13 = ValidateDHKey(a1, 0, &v26);
  v10 = v13;
  if ( v13 < 0 )
  {
    v9 = 1669;
LABEL_10:
    v11 = (unsigned int)v13;
    goto LABEL_33;
  }
  v14 = v26;
  if ( (*(_BYTE *)(v26 + 16) & 1) == 0 )
  {
    v10 = -1073741816;
    v9 = 1677;
    v11 = 3221225480LL;
    goto LABEL_33;
  }
  if ( !wcscmp_0(a3, L"DHPUBLICBLOB") || !wcscmp_0(a3, L"PUBLICBLOB") )
  {
    v18 = *(_DWORD *)(v14 + 12) + 2 * (*(_DWORD *)(v14 + 12) + 4);
    *v12 = v18;
    if ( !a4 )
      return v10;
    if ( a5 >= v18 )
    {
      v17 = 0;
      v16 = 0;
      a4[1] = *(_DWORD *)(v14 + 12);
      *a4 = 1112557636;
      goto LABEL_27;
    }
    return (unsigned int)-1073741789;
  }
  if ( wcscmp_0(a3, L"DHPRIVATEBLOB") && wcscmp_0(a3, L"PRIVATEBLOB") )
  {
    v9 = 1756;
    goto LABEL_3;
  }
  if ( !*(_BYTE *)(*(_QWORD *)(v14 + 32) + 4LL) )
  {
    v9 = 1715;
LABEL_32:
    v11 = 3221225485LL;
    v10 = -1073741811;
    goto LABEL_33;
  }
  v15 = 4 * *(_DWORD *)(v14 + 12) + 8;
  *v12 = v15;
  if ( a4 )
  {
    if ( a5 >= v15 )
    {
      a4[1] = *(_DWORD *)(v14 + 12);
      *a4 = 1448101956;
      v16 = *(_DWORD *)(v14 + 12);
      v17 = (_DWORD)a4 + 3 * v16 + 8;
      memset_0((char *)a4 + 3 * v16 + 8, 0, v16);
LABEL_27:
      v19 = *(unsigned int *)(v14 + 12);
      v20 = (_DWORD)a4 + 8;
      v21 = (__int64)a4 + v19 + 8;
      Value = SymCryptDlgroupGetValue(*(_QWORD *)(v14 + 24), v20, v19, 0, 0, v21, v19, 2, v25, 0, 0, 0);
      if ( Value )
      {
        v13 = SymcryptErrorCodeToNtStatus(Value);
        v10 = v13;
        v9 = 1779;
        goto LABEL_10;
      }
      v23 = SymCryptDlkeyGetValue(
              *(_QWORD *)(v14 + 32),
              v17,
              v16,
              (int)v21 + *(_DWORD *)(v14 + 12),
              *(unsigned int *)(v14 + 12));
      if ( v23 )
      {
        v13 = SymcryptErrorCodeToNtStatus(v23);
        v10 = v13;
        v9 = 1796;
        goto LABEL_10;
      }
      return v10;
    }
    return (unsigned int)-1073741789;
  }
  return v10;
}

```

## disassembly

```asm
0x1800680f0  mov     rax, rsp
0x1800680f3  mov     [rax+8], rbx
0x1800680f7  mov     [rax+18h], rbp
0x1800680fb  push    rsi
0x1800680fc  push    rdi
0x1800680fd  push    r14
0x1800680ff  sub     rsp, 60h
0x180068103  mov     qword ptr [rax+10h], 0
0x18006810b  mov     rsi, r9
0x18006810e  mov     rbp, r8
0x180068111  test    rdx, rdx
0x180068114  jz      short loc_18006812B
0x180068116  mov     r9d, 674h
0x18006811c  mov     ebx, 0C00000BBh
0x180068121  mov     ecx, 0C00000BBh
0x180068126  jmp     loc_180068346
0x18006812b  test    rcx, rcx
0x18006812e  jz      loc_180068336
0x180068134  test    rbp, rbp
0x180068137  jz      loc_180068336
0x18006813d  mov     r14, [rsp+78h+arg_28]
0x180068145  test    r14, r14
0x180068148  jz      loc_180068336
0x18006814e  cmp     [rsp+78h+arg_30], 0
0x180068156  jnz     loc_180068336
0x18006815c  lea     r8, [rsp+78h+arg_8]
0x180068164  xor     edx, edx
0x180068166  call    ValidateDHKey
0x18006816b  mov     ebx, eax
0x18006816d  test    eax, eax
0x18006816f  jns     short loc_18006817E
0x180068171  mov     r9d, 685h
0x180068177  mov     ecx, eax
0x180068179  jmp     loc_180068346
0x18006817e  mov     rdi, [rsp+78h+arg_8]
0x180068186  test    byte ptr [rdi+10h], 1
0x18006818a  jnz     short loc_1800681A1
0x18006818c  mov     ebx, 0C0000008h
0x180068191  mov     r9d, 68Dh
0x180068197  mov     ecx, 0C0000008h
0x18006819c  jmp     loc_180068346
0x1800681a1  lea     rdx, aDhpublicblob; "DHPUBLICBLOB"
0x1800681a8  mov     rcx, rbp; String1
0x1800681ab  call    wcscmp_0
0x1800681b0  test    eax, eax
0x1800681b2  jz      loc_180068264
0x1800681b8  lea     rdx, aPublicblob; "PUBLICBLOB"
0x1800681bf  mov     rcx, rbp; String1
0x1800681c2  call    wcscmp_0
0x1800681c7  test    eax, eax
0x1800681c9  jz      loc_180068264
0x1800681cf  lea     rdx, aDhprivateblob; "DHPRIVATEBLOB"
0x1800681d6  mov     rcx, rbp; String1
0x1800681d9  call    wcscmp_0
0x1800681de  test    eax, eax
0x1800681e0  jz      short loc_180068200
0x1800681e2  lea     rdx, aPrivateblob; "PRIVATEBLOB"
0x1800681e9  mov     rcx, rbp; String1
0x1800681ec  call    wcscmp_0
0x1800681f1  test    eax, eax
0x1800681f3  jz      short loc_180068200
0x1800681f5  mov     r9d, 6DCh
0x1800681fb  jmp     loc_18006811C
0x180068200  mov     rax, [rdi+20h]
0x180068204  cmp     byte ptr [rax+4], 0
0x180068208  jnz     short loc_180068215
0x18006820a  mov     r9d, 6B3h
0x180068210  jmp     loc_18006833C
0x180068215  mov     eax, [rdi+0Ch]
0x180068218  lea     eax, ds:8[rax*4]
0x18006821f  mov     [r14], eax
0x180068222  test    rsi, rsi
0x180068225  jz      loc_180068359
0x18006822b  cmp     [rsp+78h+arg_20], eax
0x180068232  jb      short loc_180068282
0x180068234  mov     eax, [rdi+0Ch]
0x180068237  xor     edx, edx; Val
0x180068239  mov     [rsi+4], eax
0x18006823c  mov     dword ptr [rsi], 56504844h
0x180068242  mov     ebp, [rdi+0Ch]
0x180068245  mov     r8d, ebp; Size
0x180068248  lea     r14d, ds:0[rbp*2]
0x180068250  add     r14d, ebp
0x180068253  add     r14, 8
0x180068257  add     r14, rsi
0x18006825a  mov     rcx, r14; void *
0x18006825d  call    memset_0
0x180068262  jmp     short loc_18006829D
0x180068264  mov     eax, [rdi+0Ch]
0x180068267  lea     ecx, [rax+4]
0x18006826a  lea     ecx, [rax+rcx*2]
0x18006826d  mov     [r14], ecx
0x180068270  test    rsi, rsi
0x180068273  jz      loc_180068359
0x180068279  cmp     [rsp+78h+arg_20], ecx
0x180068280  jnb     short loc_18006828C
0x180068282  mov     ebx, 0C0000023h
0x180068287  jmp     loc_180068359
0x18006828c  mov     eax, [rdi+0Ch]
0x18006828f  xor     r14d, r14d
0x180068292  xor     ebp, ebp
0x180068294  mov     [rsi+4], eax
0x180068297  mov     dword ptr [rsi], 42504844h
0x18006829d  mov     r8d, [rdi+0Ch]; int
0x1800682a1  lea     rdx, [rsi+8]; int
0x1800682a5  mov     rcx, [rdi+18h]; int
0x1800682a9  xor     r9d, r9d; int
0x1800682ac  mov     [rsp+78h+var_20], 0; __int64
0x1800682b5  mov     [rsp+78h+var_28], 0; __int64
0x1800682be  mov     [rsp+78h+var_30], 0; void *
0x1800682c7  lea     rsi, [rdx+r8]
0x1800682cb  mov     [rsp+78h+var_40], 2; int
0x1800682d3  mov     [rsp+78h+var_48], r8; __int64
0x1800682d8  mov     [rsp+78h+var_50], rsi; __int64
0x1800682dd  mov     [rsp+78h+var_58], 0; __int64
0x1800682e6  call    SymCryptDlgroupGetValue
0x1800682eb  test    eax, eax
0x1800682ed  jz      short loc_180068303
0x1800682ef  mov     ecx, eax
0x1800682f1  call    SymcryptErrorCodeToNtStatus
0x1800682f6  mov     ebx, eax
0x1800682f8  mov     r9d, 6F3h
0x1800682fe  jmp     loc_180068177
0x180068303  mov     eax, [rdi+0Ch]
0x180068306  mov     rdx, r14
0x180068309  mov     rcx, [rdi+20h]
0x18006830d  mov     r8d, ebp
0x180068310  mov     [rsp+78h+var_58], rax
0x180068315  lea     r9, [rsi+rax]
0x180068319  call    SymCryptDlkeyGetValue
0x18006831e  test    eax, eax
0x180068320  jz      short loc_180068359
0x180068322  mov     ecx, eax
0x180068324  call    SymcryptErrorCodeToNtStatus
0x180068329  mov     ebx, eax
0x18006832b  mov     r9d, 704h
0x180068331  jmp     loc_180068177
0x180068336  mov     r9d, 67Eh
0x18006833c  mov     ecx, 0C000000Dh
0x180068341  mov     ebx, 0C000000Dh
0x180068346  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18006834d  lea     rdx, aStatus; "Status"
0x180068354  call    DebugTraceError
0x180068359  lea     r11, [rsp+78h+var_18]
0x18006835e  mov     eax, ebx
0x180068360  mov     rbx, [r11+20h]
0x180068364  mov     rbp, [r11+30h]
0x180068368  mov     rsp, r11
0x18006836b  pop     r14
0x18006836d  pop     rdi
0x18006836e  pop     rsi
0x18006836f  retn
```
