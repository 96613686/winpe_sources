# MSCryptImportKey

- ea: `0x18002cd40`
- end: `0x18002d0d5`
- name: `MSCryptImportKey`
- size: `917`
- prototype: `__int64 __fastcall(int, __int64, const wchar_t *, _QWORD *, __int64, unsigned int, _DWORD *, unsigned int, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18002b7b0`

## callees

- `0x18000c860`
- `0x18000ecb0`
- `0x18000ee60`
- `0x180010270`
- `0x1800102a0`
- `0x18002cd40`
- `0x18002d0e0`
- `0x18002d2e0`
- `0x18002e680`
- `0x1800495b0`
- `0x180067358`
- `0x18007f765`

## string_xrefs

- `0x18002ced3`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18002cf7d`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18002cfd4`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18002d0af`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x180081c5c`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x180081cdd`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`

## pseudocode

```c
__int64 __fastcall MSCryptImportKey(
        int a1,
        __int64 a2,
        const wchar_t *a3,
        _QWORD *a4,
        __int64 a5,
        unsigned int a6,
        _DWORD *a7,
        unsigned int a8,
        int a9)
{
  unsigned int v12; // r12d
  __int64 v13; // rdx
  __int64 v14; // r9
  __int64 v15; // r15
  __int64 v16; // rsi
  _DWORD *Src; // rdi
  unsigned int v18; // r14d
  int v19; // eax
  unsigned int v20; // ebx
  int SymmetricKey; // eax
  __int64 v23; // rcx
  __int64 v24; // r9
  int v25; // edx
  int v26; // eax
  __int64 v27; // rcx
  _BYTE *v28; // rax
  __int64 v29; // r9
  __int64 v30; // rcx
  __int64 v31; // r9
  __int64 v32; // rcx
  int v33; // eax
  __int64 v34; // rax
  int v35; // eax
  size_t Size; // [rsp+28h] [rbp-28h]
  size_t v37; // [rsp+30h] [rbp-20h]
  unsigned int v38; // [rsp+40h] [rbp-10h] BYREF
  int v39[2]; // [rsp+48h] [rbp-8h] BYREF

  v12 = 0;
  *(_QWORD *)v39 = 0;
  v38 = 0;
  if ( !a9 )
  {
    v15 = validateMSCryptSymmAlgorithm();
    if ( v15 )
    {
      v16 = (unsigned int)v13;
      if ( a5 == v13 || (Src = a7) == 0 )
      {
        v20 = -1073741811;
        v23 = 3221225485LL;
        v24 = 1435;
        goto LABEL_22;
      }
      if ( a3 )
      {
        if ( v14 )
        {
          if ( wcscmp_0(a3, L"PKCS11RsaAesWrapBlob") )
          {
            v18 = a8;
LABEL_9:
            if ( !wcscmp_0(a3, L"OpaqueKeyBlob") )
            {
              if ( a6 < *(_DWORD *)(v15 + 28) )
              {
                v20 = -1073741789;
                goto LABEL_13;
              }
              v19 = MSCryptImportKeyOpaque(v15, Src, v18);
              v20 = v19;
              if ( v19 >= 0 )
              {
LABEL_12:
                *a4 = *(_QWORD *)v39;
                goto LABEL_13;
              }
              v23 = (unsigned int)v19;
              v24 = 1520;
              goto LABEL_22;
            }
            if ( !wcscmp_0(a3, L"KeyDataBlob") )
            {
              if ( v18 < 0xC )
              {
                v20 = -1073741789;
                v31 = 1531;
                v32 = 3221225507LL;
              }
              else
              {
                if ( *Src == 1296188491 && Src[1] == 1 && (unsigned __int64)v18 - 12 >= (unsigned int)Src[2] )
                {
                  LODWORD(Size) = Src[2];
                  SymmetricKey = MSCryptGenerateSymmetricKey(a1, (int)v39, a5, a6, Src + 3, Size, 128);
                  v20 = SymmetricKey;
                  if ( SymmetricKey >= 0 )
                    goto LABEL_12;
                  v23 = (unsigned int)SymmetricKey;
                  v24 = 1554;
                  goto LABEL_22;
                }
                v20 = -1073741811;
                v31 = 1541;
                v32 = 3221225485LL;
              }
              DebugTraceError(v32, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c", v31);
              goto LABEL_13;
            }
            if ( wcscmp_0(a3, L"Rfc3565KeyWrapBlob") )
            {
              v20 = -1073741637;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_sDsd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  v25,
                  (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
                  (unsigned int)"Status",
                  187,
                  (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
                  42);
              }
LABEL_13:
              if ( !v16 )
                return v20;
              goto LABEL_34;
            }
            LODWORD(v37) = v18;
            v26 = MSCryptAesKeyUnwrap(a1, a2, (int)v39, a5, a6, Src, v37);
            v20 = v26;
            if ( v26 >= 0 )
              goto LABEL_12;
            v23 = (unsigned int)v26;
            v24 = 1571;
LABEL_22:
            DebugTraceError(v23, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c", v24);
            if ( *(_QWORD *)v39 )
              MSCryptDestroyKey();
            goto LABEL_13;
          }
          if ( a2 )
          {
            if ( *(_DWORD *)(v15 + 8) == 65538 )
            {
              v33 = Pkcs11ConvertToKeyBlob(a1, a2, 0, (unsigned int)&v38, (__int64)a7, a8);
              v20 = v33;
              if ( v33 >= 0 )
              {
                v34 = SafeAllocaAllocateFromHeap(v38);
                v16 = v34;
                if ( v34 )
                {
                  v35 = Pkcs11ConvertToKeyBlob(a1, a2, v34, (unsigned int)&v38, (__int64)a7, a8);
                  v20 = v35;
                  if ( v35 < 0 )
                  {
                    DebugTraceError(
                      (unsigned int)v35,
                      "Status",
                      "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
                      1497);
                    v12 = v38;
LABEL_34:
                    v27 = v12;
                    v28 = (_BYTE *)v16;
                    if ( v12 )
                    {
                      do
                      {
                        *v28++ = 0;
                        --v27;
                      }
                      while ( v27 );
                    }
                    MSCryptFree(v16);
                    return v20;
                  }
                  v12 = v38;
                  a3 = L"KeyDataBlob";
                  v18 = v38;
                  Src = (_DWORD *)v16;
                  goto LABEL_9;
                }
                v20 = -1073741801;
                v29 = 1485;
                v30 = 3221225495LL;
              }
              else
              {
                v29 = 1478;
                v30 = (unsigned int)v33;
              }
            }
            else
            {
              v20 = -1073741637;
              v29 = 1466;
              v30 = 3221225659LL;
            }
LABEL_52:
            DebugTraceError(v30, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c", v29);
            return v20;
          }
          v29 = 1459;
LABEL_50:
          v20 = -1073741816;
          v30 = 3221225480LL;
          goto LABEL_52;
        }
        v29 = 1449;
      }
      else
      {
        v29 = 1442;
      }
      v20 = -1073741811;
      v30 = 3221225485LL;
      goto LABEL_52;
    }
    v29 = 1428;
    goto LABEL_50;
  }
  v20 = -1073741811;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      0,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
      (unsigned int)"Status",
      13,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
      139);
  return v20;
}

```

## disassembly

```asm
0x18002cd40  mov     [rsp-38h+arg_8], rbx
0x18002cd45  mov     [rsp-38h+arg_18], r9
0x18002cd4a  mov     qword ptr [rsp-38h+arg_0], rcx
0x18002cd4f  push    rbp
0x18002cd50  push    rsi
0x18002cd51  push    rdi
0x18002cd52  push    r12
0x18002cd54  push    r13
0x18002cd56  push    r14
0x18002cd58  push    r15
0x18002cd5a  mov     rbp, rsp
0x18002cd5d  sub     rsp, 50h
0x18002cd61  mov     r13, rdx
0x18002cd64  mov     rbx, r8
0x18002cd67  xor     edx, edx
0x18002cd69  mov     r14, rcx
0x18002cd6c  mov     r12d, edx
0x18002cd6f  mov     qword ptr [rbp+var_8], rdx
0x18002cd73  mov     [rbp+var_10], edx
0x18002cd76  cmp     [rbp+arg_40], edx
0x18002cd7c  jnz     loc_18002CFAA
0x18002cd82  call    validateMSCryptSymmAlgorithm
0x18002cd87  mov     r15, rax
0x18002cd8a  test    rax, rax
0x18002cd8d  jz      loc_18002D025
0x18002cd93  mov     esi, edx
0x18002cd95  cmp     [rbp+arg_20], rdx
0x18002cd99  jz      loc_18002D0C0
0x18002cd9f  mov     rdi, [rbp+arg_30]
0x18002cda3  test    rdi, rdi
0x18002cda6  jz      loc_18002D0C0
0x18002cdac  test    rbx, rbx
0x18002cdaf  jz      loc_18002D030
0x18002cdb5  test    r9, r9
0x18002cdb8  jz      loc_18002D038
0x18002cdbe  lea     rdx, aPkcs11rsaaeswr; "PKCS11RsaAesWrapBlob"
0x18002cdc5  mov     rcx, rbx; String1
0x18002cdc8  call    wcscmp_0
0x18002cdcd  test    eax, eax
0x18002cdcf  jz      loc_18002D04D
0x18002cdd5  mov     r14d, dword ptr [rbp+arg_38]
0x18002cdd9  lea     rdx, aOpaquekeyblob; "OpaqueKeyBlob"
0x18002cde0  mov     rcx, rbx; String1
0x18002cde3  call    wcscmp_0
0x18002cde8  test    eax, eax
0x18002cdea  jnz     short loc_18002CE4D
0x18002cdec  mov     r9d, [rbp+arg_28]
0x18002cdf0  cmp     r9d, [r15+1Ch]
0x18002cdf4  jb      loc_18002CEFD
0x18002cdfa  mov     r8, [rbp+arg_20]
0x18002cdfe  lea     rdx, [rbp+var_8]
0x18002ce02  mov     dword ptr [rsp+50h+Size], r14d; int
0x18002ce07  mov     rcx, r15; int
0x18002ce0a  mov     [rsp+50h+Src], rdi; Src
0x18002ce0f  call    MSCryptImportKeyOpaque
0x18002ce14  mov     ebx, eax
0x18002ce16  test    eax, eax
0x18002ce18  js      loc_18002D079
0x18002ce1e  mov     rcx, [rbp+arg_18]
0x18002ce22  mov     rax, qword ptr [rbp+var_8]
0x18002ce26  mov     [rcx], rax
0x18002ce29  test    rsi, rsi
0x18002ce2c  jnz     loc_18002D001
0x18002ce32  mov     eax, ebx
0x18002ce34  mov     rbx, [rsp+50h+arg_8]
0x18002ce3c  add     rsp, 50h
0x18002ce40  pop     r15
0x18002ce42  pop     r14
0x18002ce44  pop     r13
0x18002ce46  pop     r12
0x18002ce48  pop     rdi
0x18002ce49  pop     rsi
0x18002ce4a  pop     rbp
0x18002ce4b  retn
0x18002ce4d  lea     rdx, aKeydatablob; "KeyDataBlob"
0x18002ce54  mov     rcx, rbx; String1
0x18002ce57  call    wcscmp_0
0x18002ce5c  test    eax, eax
0x18002ce5e  jnz     loc_18002CF07
0x18002ce64  cmp     r14d, 0Ch
0x18002ce68  jb      loc_18002D086
0x18002ce6e  cmp     dword ptr [rdi], 4D42444Bh
0x18002ce74  jnz     loc_18002D098
0x18002ce7a  cmp     dword ptr [rdi+4], 1
0x18002ce7e  jnz     loc_18002D098
0x18002ce84  mov     ecx, [rdi+8]
0x18002ce87  mov     eax, r14d
0x18002ce8a  sub     rax, 0Ch
0x18002ce8e  cmp     rax, rcx
0x18002ce91  jb      loc_18002D098
0x18002ce97  mov     r9d, [rbp+arg_28]; int
0x18002ce9b  lea     rax, [rdi+0Ch]
0x18002ce9f  mov     r8, [rbp+arg_20]; int
0x18002cea3  lea     rdx, [rbp+var_8]; int
0x18002cea7  mov     dword ptr [rsp+50h+var_20], 80h; int
0x18002ceaf  mov     dword ptr [rsp+50h+Size], ecx; Size
0x18002ceb3  mov     rcx, qword ptr [rbp+arg_0]; int
0x18002ceb7  mov     [rsp+50h+Src], rax; Src
0x18002cebc  call    MSCryptGenerateSymmetricKey
0x18002cec1  mov     ebx, eax
0x18002cec3  test    eax, eax
0x18002cec5  jns     loc_18002CE1E
0x18002cecb  mov     ecx, eax
0x18002cecd  mov     r9d, 612h
0x18002ced3  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18002ceda  lea     rdx, aStatus; "Status"
0x18002cee1  call    DebugTraceError
0x18002cee6  mov     rcx, qword ptr [rbp+var_8]
0x18002ceea  test    rcx, rcx
0x18002ceed  jz      loc_18002CE29
0x18002cef3  call    MSCryptDestroyKey
0x18002cef8  jmp     loc_18002CE29
0x18002cefd  mov     ebx, 0C0000023h
0x18002cf02  jmp     loc_18002CE29
0x18002cf07  lea     rdx, aRfc3565keywrap; "Rfc3565KeyWrapBlob"
0x18002cf0e  mov     rcx, rbx; String1
0x18002cf11  call    wcscmp_0
0x18002cf16  test    eax, eax
0x18002cf18  jnz     short loc_18002CF53
0x18002cf1a  mov     eax, [rbp+arg_28]
0x18002cf1d  lea     r8, [rbp+var_8]; int
0x18002cf21  mov     r9, [rbp+arg_20]; int
0x18002cf25  mov     rdx, r13; int
0x18002cf28  mov     rcx, qword ptr [rbp+arg_0]; int
0x18002cf2c  mov     dword ptr [rsp+50h+var_20], r14d; Size
0x18002cf31  mov     [rsp+50h+Size], rdi; Src
0x18002cf36  mov     dword ptr [rsp+50h+Src], eax; int
0x18002cf3a  call    MSCryptAesKeyUnwrap
0x18002cf3f  mov     ebx, eax
0x18002cf41  test    eax, eax
0x18002cf43  jns     loc_18002CE1E
0x18002cf49  mov     ecx, eax
0x18002cf4b  mov     r9d, 623h
0x18002cf51  jmp     short loc_18002CED3
0x18002cf53  mov     ebx, 0C00000BBh
0x18002cf58  mov     rax, cs:WPP_GLOBAL_Control
0x18002cf5f  lea     rcx, WPP_GLOBAL_Control
0x18002cf66  cmp     rax, rcx
0x18002cf69  jz      loc_18002CE29
0x18002cf6f  test    byte ptr [rax+1Ch], 1
0x18002cf73  jz      loc_18002CE29
0x18002cf79  mov     rcx, [rax+10h]
0x18002cf7d  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18002cf84  mov     dword ptr [rsp+50h+var_20], 62Ah
0x18002cf8c  lea     r9, aStatus; "Status"
0x18002cf93  mov     [rsp+50h+Size], r8
0x18002cf98  mov     dword ptr [rsp+50h+Src], 0C00000BBh
0x18002cfa0  call    WPP_SF_sDsd
0x18002cfa5  jmp     loc_18002CE29
0x18002cfaa  mov     ebx, 0C000000Dh
0x18002cfaf  mov     rax, cs:WPP_GLOBAL_Control
0x18002cfb6  lea     rcx, WPP_GLOBAL_Control
0x18002cfbd  cmp     rax, rcx
0x18002cfc0  jz      loc_18002CE32
0x18002cfc6  test    byte ptr [rax+1Ch], 1
0x18002cfca  jz      loc_18002CE32
0x18002cfd0  mov     rcx, [rax+10h]
0x18002cfd4  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18002cfdb  mov     dword ptr [rsp+50h+var_20], 58Bh
0x18002cfe3  lea     r9, aStatus; "Status"
0x18002cfea  mov     [rsp+50h+Size], r8
0x18002cfef  mov     dword ptr [rsp+50h+Src], 0C000000Dh
0x18002cff7  call    WPP_SF_sDsd
0x18002cffc  jmp     loc_18002CE32
0x18002d001  mov     ecx, r12d
0x18002d004  mov     rax, rsi
0x18002d007  test    r12d, r12d
0x18002d00a  jz      short loc_18002D018
0x18002d00c  mov     byte ptr [rax], 0
0x18002d00f  inc     rax
0x18002d012  sub     rcx, 1
0x18002d016  jnz     short loc_18002D00C
0x18002d018  mov     rcx, rsi
0x18002d01b  call    MSCryptFree
0x18002d020  jmp     loc_18002CE32
0x18002d025  mov     r9d, 594h
0x18002d02b  jmp     loc_180081C40
0x18002d030  mov     r9d, 5A2h
0x18002d036  jmp     short loc_18002D03E
0x18002d038  mov     r9d, 5A9h
0x18002d03e  mov     ebx, 0C000000Dh
0x18002d043  mov     ecx, 0C000000Dh
0x18002d048  jmp     loc_180081C5C
0x18002d04d  test    r13, r13
0x18002d050  jz      loc_180081C3A
0x18002d056  cmp     dword ptr [r15+8], 10002h
0x18002d05e  jz      loc_180081C75
0x18002d064  mov     ebx, 0C00000BBh
0x18002d069  mov     r9d, 5BAh
0x18002d06f  mov     ecx, 0C00000BBh
0x18002d074  jmp     loc_180081C5C
0x18002d079  mov     ecx, eax
0x18002d07b  mov     r9d, 5F0h
0x18002d081  jmp     loc_18002CED3
0x18002d086  mov     ebx, 0C0000023h
0x18002d08b  mov     r9d, 5FBh
0x18002d091  mov     ecx, 0C0000023h
0x18002d096  jmp     short loc_18002D0A8
0x18002d098  mov     ebx, 0C000000Dh
0x18002d09d  mov     r9d, 605h
0x18002d0a3  mov     ecx, 0C000000Dh
0x18002d0a8  lea     rdx, aStatus; "Status"
0x18002d0af  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18002d0b6  call    DebugTraceError
0x18002d0bb  jmp     loc_18002CE29
0x18002d0c0  mov     ebx, 0C000000Dh
0x18002d0c5  mov     ecx, 0C000000Dh
0x18002d0ca  mov     r9d, 59Bh
0x18002d0d0  jmp     loc_18002CED3
0x180081c3a  mov     r9d, 5B3h
0x180081c40  mov     ebx, 0C0000008h
0x180081c45  mov     ecx, 0C0000008h
0x180081c4a  jmp     short loc_180081C5C
0x180081c4c  mov     ebx, 0C0000017h
0x180081c51  mov     r9d, 5CDh
0x180081c57  mov     ecx, 0C0000017h
0x180081c5c  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180081c63  lea     rdx, aStatus; "Status"
0x180081c6a  call    DebugTraceError
0x180081c6f  nop
0x180081c70  jmp     loc_18002CE32
0x180081c75  mov     r12d, dword ptr [rbp+arg_38]
0x180081c79  lea     r9, [rbp+var_10]
0x180081c7d  mov     dword ptr [rsp+50h+Size], r12d
0x180081c82  xor     r8d, r8d
0x180081c85  mov     rdx, r13
0x180081c88  mov     [rsp+50h+Src], rdi
0x180081c8d  mov     rcx, r14
0x180081c90  call    Pkcs11ConvertToKeyBlob
0x180081c95  mov     ebx, eax
0x180081c97  test    eax, eax
0x180081c99  jns     short loc_180081CA5
0x180081c9b  mov     r9d, 5C6h
0x180081ca1  mov     ecx, eax
0x180081ca3  jmp     short loc_180081C5C
0x180081ca5  mov     ecx, [rbp+var_10]
0x180081ca8  call    SafeAllocaAllocateFromHeap
0x180081cad  mov     rsi, rax
0x180081cb0  test    rax, rax
0x180081cb3  jz      short loc_180081C4C
0x180081cb5  mov     dword ptr [rsp+50h+Size], r12d
0x180081cba  lea     r9, [rbp+var_10]
0x180081cbe  mov     r8, rax
0x180081cc1  mov     [rsp+50h+Src], rdi
0x180081cc6  mov     rdx, r13
0x180081cc9  mov     rcx, r14
0x180081ccc  call    Pkcs11ConvertToKeyBlob
0x180081cd1  mov     ebx, eax
0x180081cd3  test    eax, eax
0x180081cd5  jns     short loc_180081CFB
0x180081cd7  mov     r9d, 5D9h
0x180081cdd  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180081ce4  lea     rdx, aStatus; "Status"
0x180081ceb  mov     ecx, eax
0x180081ced  call    DebugTraceError
0x180081cf2  mov     r12d, [rbp+var_10]
0x180081cf6  jmp     loc_18002D001
0x180081cfb  mov     r12d, [rbp+var_10]
0x180081cff  lea     rbx, aKeydatablob; "KeyDataBlob"
0x180081d06  mov     r14d, r12d
0x180081d09  mov     rdi, rsi
0x180081d0c  jmp     loc_18002CDD9
```
