# MSCryptConvertRsaPrivateBlobToFullRsaBlob

- ea: `0x18004a060`
- end: `0x18004a1ef`
- name: `MSCryptConvertRsaPrivateBlobToFullRsaBlob`
- size: `399`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x180021490`
- `0x18003c430`
- `0x18003c600`
- `0x18004a060`
- `0x18004a200`
- `0x18004a3b0`

## string_xrefs

- `0x18004a0c8`: `onecore\ds\security\cryptoapi\ncrypt\msprim\msprim\rsablob.c`
- `0x18004a14a`: `onecore\ds\security\cryptoapi\ncrypt\msprim\msprim\rsablob.c`
- `0x18004a1aa`: `onecore\ds\security\cryptoapi\ncrypt\msprim\msprim\rsablob.c`

## pseudocode

```c
__int64 __fastcall MSCryptConvertRsaPrivateBlobToFullRsaBlob(
        _DWORD *a1,
        unsigned int a2,
        __int64 a3,
        unsigned int a4,
        unsigned int *a5)
{
  int v9; // edx
  int v10; // ebx
  int v11; // eax
  __int64 v12; // rdx
  int v13; // r8d
  _QWORD *v14; // rdi
  int v15; // eax
  __int64 v17; // [rsp+40h] [rbp-38h] BYREF
  PVOID P[6]; // [rsp+48h] [rbp-30h] BYREF

  v17 = 0;
  P[0] = 0;
  v10 = MSCryptOpenRsaProvider(&v17, L"RSA", 0);
  if ( v10 >= 0 )
  {
    v11 = MSCryptRsaImportKeyPair(v17, 0, L"PRIVATEBLOB", P, a1, a2, 0, 4);
    v14 = P[0];
    v10 = v11;
    if ( v11 >= 0 )
    {
      v15 = MSCryptExportKeyPair((__int64)P[0], 0, L"RSAFULLPRIVATEBLOB", a3, a4, a5, 0);
      v10 = v15;
      if ( v15 < 0 )
        DebugTraceError(
          (unsigned int)v15,
          "Status",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\msprim\\rsablob.c",
          75);
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v12,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\msprim\\rsablob.c",
        (unsigned int)"Status",
        v11,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\msprim\\rsablob.c",
        61);
    }
    if ( v14 )
      MSCryptDestroyKeyPair(v14, v12, v13);
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v9,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\msprim\\rsablob.c",
      (unsigned int)"Status",
      v10,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\msprim\\rsablob.c",
      46);
  }
  if ( v17 )
    MSCryptCloseRsaProvider(v17, 0);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18004a060  push    rbx
0x18004a062  push    rbp
0x18004a063  push    rdi
0x18004a064  push    r14
0x18004a066  push    r15
0x18004a068  sub     rsp, 50h
0x18004a06c  mov     r15, r8
0x18004a06f  mov     [rsp+78h+var_38], 0
0x18004a078  mov     edi, edx
0x18004a07a  mov     [rsp+78h+P], 0
0x18004a083  mov     rbp, rcx
0x18004a086  lea     rdx, aRsa; "RSA"
0x18004a08d  xor     r8d, r8d
0x18004a090  lea     rcx, [rsp+78h+var_38]
0x18004a095  mov     r14d, r9d
0x18004a098  call    MSCryptOpenRsaProvider
0x18004a09d  mov     ebx, eax
0x18004a09f  test    eax, eax
0x18004a0a1  jns     short loc_18004A0F1
0x18004a0a3  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a0aa  lea     rax, WPP_GLOBAL_Control
0x18004a0b1  cmp     rcx, rax
0x18004a0b4  jz      loc_18004A1CC
0x18004a0ba  test    byte ptr [rcx+1Ch], 1
0x18004a0be  jz      loc_18004A1CC
0x18004a0c4  mov     rcx, [rcx+10h]
0x18004a0c8  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004a0cf  mov     [rsp+78h+var_48], 2Eh ; '.'
0x18004a0d7  lea     r9, aStatus; "Status"
0x18004a0de  mov     [rsp+78h+var_50], r8
0x18004a0e3  mov     dword ptr [rsp+78h+var_58], ebx
0x18004a0e7  call    WPP_SF_sDsd
0x18004a0ec  jmp     loc_18004A1CC
0x18004a0f1  mov     rcx, [rsp+78h+var_38]
0x18004a0f6  lea     r9, [rsp+78h+P]
0x18004a0fb  mov     [rsp+78h+var_40], 4
0x18004a103  lea     r8, aPrivateblob; "PRIVATEBLOB"
0x18004a10a  mov     [rsp+78h+var_48], 0
0x18004a112  xor     edx, edx
0x18004a114  mov     dword ptr [rsp+78h+var_50], edi
0x18004a118  mov     [rsp+78h+var_58], rbp
0x18004a11d  call    MSCryptRsaImportKeyPair
0x18004a122  mov     rdi, [rsp+78h+P]
0x18004a127  mov     ebx, eax
0x18004a129  test    eax, eax
0x18004a12b  jns     short loc_18004A170
0x18004a12d  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a134  lea     rax, WPP_GLOBAL_Control
0x18004a13b  cmp     rcx, rax
0x18004a13e  jz      short loc_18004A1BF
0x18004a140  test    byte ptr [rcx+1Ch], 1
0x18004a144  jz      short loc_18004A1BF
0x18004a146  mov     rcx, [rcx+10h]
0x18004a14a  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004a151  mov     [rsp+78h+var_48], 3Dh ; '='
0x18004a159  lea     r9, aStatus; "Status"
0x18004a160  mov     [rsp+78h+var_50], r8
0x18004a165  mov     dword ptr [rsp+78h+var_58], ebx
0x18004a169  call    WPP_SF_sDsd
0x18004a16e  jmp     short loc_18004A1BF
0x18004a170  mov     rax, [rsp+78h+arg_20]
0x18004a178  lea     r8, aRsafullprivate; "RSAFULLPRIVATEBLOB"
0x18004a17f  mov     [rsp+78h+var_48], 0
0x18004a187  mov     r9, r15
0x18004a18a  mov     [rsp+78h+var_50], rax
0x18004a18f  xor     edx, edx
0x18004a191  mov     rcx, rdi
0x18004a194  mov     dword ptr [rsp+78h+var_58], r14d
0x18004a199  call    MSCryptExportKeyPair
0x18004a19e  mov     ebx, eax
0x18004a1a0  test    eax, eax
0x18004a1a2  jns     short loc_18004A1BF
0x18004a1a4  mov     r9d, 4Bh ; 'K'
0x18004a1aa  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004a1b1  lea     rdx, aStatus; "Status"
0x18004a1b8  mov     ecx, eax
0x18004a1ba  call    DebugTraceError
0x18004a1bf  test    rdi, rdi
0x18004a1c2  jz      short loc_18004A1CC
0x18004a1c4  mov     rcx, rdi; P
0x18004a1c7  call    MSCryptDestroyKeyPair
0x18004a1cc  cmp     [rsp+78h+var_38], 0
0x18004a1d2  jz      short loc_18004A1E0
0x18004a1d4  mov     rcx, [rsp+78h+var_38]
0x18004a1d9  xor     edx, edx
0x18004a1db  call    MSCryptCloseRsaProvider
0x18004a1e0  mov     eax, ebx
0x18004a1e2  add     rsp, 50h
0x18004a1e6  pop     r15
0x18004a1e8  pop     r14
0x18004a1ea  pop     rdi
0x18004a1eb  pop     rbp
0x18004a1ec  pop     rbx
0x18004a1ed  retn
```
