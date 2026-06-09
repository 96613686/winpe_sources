# MSCryptDsaSetKeyPairProperty

- ea: `0x180069e28`
- end: `0x18006a05f`
- name: `MSCryptDsaSetKeyPairProperty`
- size: `567`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18006a070`

## callees

- `0x18000ecb0`
- `0x18001c878`
- `0x18005196c`
- `0x18005723c`
- `0x1800581c0`
- `0x180058288`
- `0x180069e28`
- `0x18006a34c`
- `0x18006a48c`
- `0x18007f765`

## string_xrefs

- `0x18006a036`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dsa.c`

## pseudocode

```c
__int64 __fastcall MSCryptDsaSetKeyPairProperty(__int64 a1, const wchar_t *a2, _DWORD *a3, unsigned int a4, int a5)
{
  int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // r9
  __int64 v11; // rcx
  __int64 v12; // rdi
  unsigned int v13; // esi
  __int64 v14; // rax
  __int64 v16; // [rsp+40h] [rbp+8h] BYREF

  v16 = 0;
  if ( !a1 || !a2 || !a3 || !a4 || a5 )
  {
    v10 = 839;
    goto LABEL_41;
  }
  v8 = ValidateDSAKey(a1, 0, &v16);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = 846;
LABEL_8:
    v11 = (unsigned int)v8;
LABEL_42:
    DebugTraceError(v11, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\dsa\\dsa.c", v10);
    return v9;
  }
  v12 = v16;
  if ( (*(_BYTE *)(v16 + 28) & 1) != 0 )
  {
    v9 = -1073741816;
    v10 = 857;
    v11 = 3221225480LL;
    goto LABEL_42;
  }
  if ( wcscmp_0(a2, L"DSAParameters") )
  {
    if ( !wcscmp_0(a2, L"KeyLength") || !wcscmp_0(a2, L"KeyStrength") )
    {
      if ( (*(_BYTE *)(v12 + 28) & 2) == 0 )
      {
        if ( a4 != 4 )
        {
          v10 = 925;
          goto LABEL_41;
        }
        v13 = *a3 >> 3;
        if ( v13 - 64 > 0x140 || (v13 & 7) != 0 )
        {
          v10 = 935;
          goto LABEL_41;
        }
        if ( *(_DWORD *)(v12 + 12) != v13 && *(_QWORD *)(v12 + 32) )
        {
          if ( *(_QWORD *)(v12 + 40) )
          {
            SymCryptDlkeyFree();
            *(_QWORD *)(v12 + 40) = 0;
          }
          SymCryptMlDsaTemporariesFree(*(_QWORD *)(v12 + 32));
          *(_QWORD *)(v12 + 32) = 0;
        }
        *(_DWORD *)(v12 + 12) = v13;
        SetKeyPropertiesBasedOnKeyLength(v13, v12);
        if ( !*(_QWORD *)(v12 + 32) )
        {
          v14 = SymCryptDlgroupAllocate(
                  (unsigned int)(8 * *(_DWORD *)(v12 + 12)),
                  (unsigned int)(8 * *(_DWORD *)(v12 + 16)));
          *(_QWORD *)(v12 + 32) = v14;
          if ( !v14 )
          {
            v9 = -1073741801;
            v10 = 961;
            v11 = 3221225495LL;
            goto LABEL_42;
          }
        }
        return v9;
      }
      v10 = 918;
    }
    else
    {
      v10 = 1035;
    }
    v9 = -1073741637;
    v11 = 3221225659LL;
    goto LABEL_42;
  }
  if ( a4 < 0x20 )
  {
    v10 = 867;
LABEL_41:
    v9 = -1073741811;
    v11 = 3221225485LL;
    goto LABEL_42;
  }
  if ( a3[1] == 1297109828 )
  {
    v8 = SetParameterV1Format((__int64)a3, a4, v12);
    v9 = v8;
    if ( v8 < 0 )
    {
      v10 = 879;
      goto LABEL_8;
    }
  }
  else
  {
    if ( a3[1] != 843927620 )
    {
      v10 = 898;
      goto LABEL_41;
    }
    v8 = SetParameterV2Format(a3, a4, v12);
    v9 = v8;
    if ( v8 < 0 )
    {
      v10 = 891;
      goto LABEL_8;
    }
  }
  return v9;
}

```

## disassembly

```asm
0x180069e28  mov     rax, rsp
0x180069e2b  mov     [rax+10h], rbx
0x180069e2f  mov     [rax+18h], rbp
0x180069e33  push    rsi
0x180069e34  push    rdi
0x180069e35  push    r14
0x180069e37  sub     rsp, 20h
0x180069e3b  mov     qword ptr [rax+8], 0
0x180069e43  mov     esi, r9d
0x180069e46  mov     r14, r8
0x180069e49  mov     rbp, rdx
0x180069e4c  test    rcx, rcx
0x180069e4f  jz      loc_18006A026
0x180069e55  test    rdx, rdx
0x180069e58  jz      loc_18006A026
0x180069e5e  test    r8, r8
0x180069e61  jz      loc_18006A026
0x180069e67  test    r9d, r9d
0x180069e6a  jz      loc_18006A026
0x180069e70  cmp     [rsp+38h+arg_20], 0
0x180069e75  jnz     loc_18006A026
0x180069e7b  lea     r8, [rax+8]
0x180069e7f  xor     edx, edx
0x180069e81  call    ValidateDSAKey
0x180069e86  mov     ebx, eax
0x180069e88  test    eax, eax
0x180069e8a  jns     short loc_180069E99
0x180069e8c  mov     r9d, 34Eh
0x180069e92  mov     ecx, eax
0x180069e94  jmp     loc_18006A036
0x180069e99  mov     rdi, [rsp+38h+arg_0]
0x180069e9e  test    byte ptr [rdi+1Ch], 1
0x180069ea2  jz      short loc_180069EB9
0x180069ea4  mov     ebx, 0C0000008h
0x180069ea9  mov     r9d, 359h
0x180069eaf  mov     ecx, 0C0000008h
0x180069eb4  jmp     loc_18006A036
0x180069eb9  lea     rdx, aDsaparameters; "DSAParameters"
0x180069ec0  mov     rcx, rbp; String1
0x180069ec3  call    wcscmp_0
0x180069ec8  test    eax, eax
0x180069eca  jnz     short loc_180069F3C
0x180069ecc  cmp     esi, 20h ; ' '
0x180069ecf  jnb     short loc_180069EDC
0x180069ed1  mov     r9d, 363h
0x180069ed7  jmp     loc_18006A02C
0x180069edc  cmp     dword ptr [r14+4], 4D505344h
0x180069ee4  jnz     short loc_180069F05
0x180069ee6  mov     r8, rdi
0x180069ee9  mov     edx, esi
0x180069eeb  mov     rcx, r14
0x180069eee  call    SetParameterV1Format
0x180069ef3  mov     ebx, eax
0x180069ef5  test    eax, eax
0x180069ef7  jns     loc_18006A049
0x180069efd  mov     r9d, 36Fh
0x180069f03  jmp     short loc_180069E92
0x180069f05  cmp     dword ptr [r14+4], 324D5044h
0x180069f0d  jnz     short loc_180069F31
0x180069f0f  mov     r8, rdi
0x180069f12  mov     edx, esi
0x180069f14  mov     rcx, r14
0x180069f17  call    SetParameterV2Format
0x180069f1c  mov     ebx, eax
0x180069f1e  test    eax, eax
0x180069f20  jns     loc_18006A049
0x180069f26  mov     r9d, 37Bh
0x180069f2c  jmp     loc_180069E92
0x180069f31  mov     r9d, 382h
0x180069f37  jmp     loc_18006A02C
0x180069f3c  lea     rdx, aKeylength; "KeyLength"
0x180069f43  mov     rcx, rbp; String1
0x180069f46  call    wcscmp_0
0x180069f4b  test    eax, eax
0x180069f4d  jz      short loc_180069F77
0x180069f4f  lea     rdx, aKeystrength; "KeyStrength"
0x180069f56  mov     rcx, rbp; String1
0x180069f59  call    wcscmp_0
0x180069f5e  test    eax, eax
0x180069f60  jz      short loc_180069F77
0x180069f62  mov     r9d, 40Bh
0x180069f68  mov     ebx, 0C00000BBh
0x180069f6d  mov     ecx, 0C00000BBh
0x180069f72  jmp     loc_18006A036
0x180069f77  test    byte ptr [rdi+1Ch], 2
0x180069f7b  jz      short loc_180069F85
0x180069f7d  mov     r9d, 396h
0x180069f83  jmp     short loc_180069F68
0x180069f85  cmp     esi, 4
0x180069f88  jz      short loc_180069F95
0x180069f8a  mov     r9d, 39Dh
0x180069f90  jmp     loc_18006A02C
0x180069f95  mov     esi, [r14]
0x180069f98  shr     esi, 3
0x180069f9b  lea     eax, [rsi-40h]
0x180069f9e  cmp     eax, 140h
0x180069fa3  ja      short loc_18006A01E
0x180069fa5  test    sil, 7
0x180069fa9  jnz     short loc_18006A01E
0x180069fab  cmp     [rdi+0Ch], esi
0x180069fae  jz      short loc_180069FDE
0x180069fb0  cmp     qword ptr [rdi+20h], 0
0x180069fb5  jz      short loc_180069FDE
0x180069fb7  mov     rcx, [rdi+28h]
0x180069fbb  test    rcx, rcx
0x180069fbe  jz      short loc_180069FCD
0x180069fc0  call    SymCryptDlkeyFree
0x180069fc5  mov     qword ptr [rdi+28h], 0
0x180069fcd  mov     rcx, [rdi+20h]
0x180069fd1  call    SymCryptMlDsaTemporariesFree
0x180069fd6  mov     qword ptr [rdi+20h], 0
0x180069fde  mov     rdx, rdi
0x180069fe1  mov     [rdi+0Ch], esi
0x180069fe4  mov     ecx, esi
0x180069fe6  call    SetKeyPropertiesBasedOnKeyLength
0x180069feb  cmp     qword ptr [rdi+20h], 0
0x180069ff0  jnz     short loc_18006A049
0x180069ff2  mov     edx, [rdi+10h]
0x180069ff5  mov     ecx, [rdi+0Ch]
0x180069ff8  shl     edx, 3
0x180069ffb  shl     ecx, 3
0x180069ffe  call    SymCryptDlgroupAllocate
0x18006a003  mov     [rdi+20h], rax
0x18006a007  test    rax, rax
0x18006a00a  jnz     short loc_18006A049
0x18006a00c  mov     ebx, 0C0000017h
0x18006a011  mov     r9d, 3C1h
0x18006a017  mov     ecx, 0C0000017h
0x18006a01c  jmp     short loc_18006A036
0x18006a01e  mov     r9d, 3A7h
0x18006a024  jmp     short loc_18006A02C
0x18006a026  mov     r9d, 347h
0x18006a02c  mov     ebx, 0C000000Dh
0x18006a031  mov     ecx, 0C000000Dh
0x18006a036  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18006a03d  lea     rdx, aStatus; "Status"
0x18006a044  call    DebugTraceError
0x18006a049  mov     rbp, [rsp+38h+arg_10]
0x18006a04e  mov     eax, ebx
0x18006a050  mov     rbx, [rsp+38h+arg_8]
0x18006a055  add     rsp, 20h
0x18006a059  pop     r14
0x18006a05b  pop     rdi
0x18006a05c  pop     rsi
0x18006a05d  retn
```
