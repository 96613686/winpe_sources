# IISCryptoImportSessionKeyBlob

- ea: `0x180006508`
- end: `0x1800066fb`
- name: `IISCryptoImportSessionKeyBlob`
- size: `499`
- prototype: `__int64 __fastcall(HCRYPTKEY *phKey, __int64, HCRYPTPROV, HCRYPTKEY)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180005528`

## callees

- `0x180004870`
- `0x180006508`
- `0x180006a3c`
- `0x180006a98`
- `0x180007234`

## import_xrefs

- `ADVAPI32!CryptImportKey` at `0x180006683`
- `ADVAPI32!CryptImportKey` at `0x180006683`
- `ADVAPI32!CryptVerifySignatureA` at `0x180006638`
- `ADVAPI32!CryptVerifySignatureA` at `0x180006638`
- `ADVAPI32!CryptHashData` at `0x1800065d5`
- `ADVAPI32!CryptHashData` at `0x1800065d5`

## string_xrefs

- `0x18000658b`: `IISCryptoImportSessionKeyBlob.IISCryptoCreateHash failed err=0x%x.\n`

## pseudocode

```c
__int64 __fastcall IISCryptoImportSessionKeyBlob(HCRYPTKEY *phKey, __int64 a2, HCRYPTPROV a3, HCRYPTKEY a4)
{
  int Hash; // eax
  int v10; // ebx
  int LastError; // eax
  int v12; // eax
  int v13; // eax
  HCRYPTHASH hHash[7]; // [rsp+30h] [rbp-38h] BYREF

  if ( !dword_18000FC34 )
  {
    if ( a3 != 1984918096 || a4 != 1799842131 || *(_DWORD *)a2 != 1648583497 )
      return 2147942487LL;
    *phKey = 1800627539;
    return 0;
  }
  hHash[0] = 0;
  Hash = IISCryptoCreateHash(hHash, a3);
  v10 = Hash;
  if ( Hash < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        (struct _DEBUG_PRINTS *)g_pDebug,
        "inetsrv\\iis\\mb\\crypto\\key.cxx",
        0x2D8u,
        "IISCryptoImportSessionKeyBlob",
        "IISCryptoImportSessionKeyBlob.IISCryptoCreateHash failed err=0x%x.\n",
        Hash);
LABEL_23:
    if ( hHash[0] )
      IISCryptoDestroyHash(hHash[0]);
    return (unsigned int)v10;
  }
  if ( !hHash[0] )
    return (unsigned int)-2147467259;
  if ( !CryptHashData(hHash[0], (const BYTE *)(a2 + 16), *(_DWORD *)(a2 + 8), 0) )
  {
    LastError = IcpGetLastError();
    v10 = LastError;
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        (struct _DEBUG_PRINTS *)g_pDebug,
        "inetsrv\\iis\\mb\\crypto\\key.cxx",
        0x2EEu,
        "IISCryptoImportSessionKeyBlob",
        "IISCryptoImportSessionKeyBlob.CryptHashData failed err=0x%x.\n",
        LastError);
    goto LABEL_23;
  }
  if ( !CryptVerifySignatureA(
          hHash[0],
          (const BYTE *)(a2 + ((*(_DWORD *)(a2 + 8) + 7) & 0xFFFFFFF8) + 16LL),
          *(_DWORD *)(a2 + 12),
          a4,
          0,
          0) )
  {
    v12 = IcpGetLastError();
    v10 = v12;
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        (struct _DEBUG_PRINTS *)g_pDebug,
        "inetsrv\\iis\\mb\\crypto\\key.cxx",
        0x2FDu,
        "IISCryptoImportSessionKeyBlob",
        "IISCryptoImportSessionKeyBlob.CryptVerifySignature failed err=0x%x.\n",
        v12);
    goto LABEL_23;
  }
  if ( !CryptImportKey(a3, (const BYTE *)(a2 + 16), *(_DWORD *)(a2 + 8), 0, 0, phKey) )
  {
    v13 = IcpGetLastError();
    v10 = v13;
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        (struct _DEBUG_PRINTS *)g_pDebug,
        "inetsrv\\iis\\mb\\crypto\\key.cxx",
        0x310u,
        "IISCryptoImportSessionKeyBlob",
        "IISCryptoImportSessionKeyBlob.CryptImportKey failed err=0x%x.\n",
        v13);
    if ( v10 < 0 )
      goto LABEL_23;
  }
  IISCryptoDestroyHash(hHash[0]);
  return 0;
}

```

## disassembly

```asm
0x180006508  push    rbx
0x18000650a  push    rbp
0x18000650b  push    rsi
0x18000650c  push    rdi
0x18000650d  push    r14
0x18000650f  sub     rsp, 40h
0x180006513  cmp     cs:dword_18000FC34, 0
0x18000651a  mov     rbp, r9
0x18000651d  mov     rsi, r8
0x180006520  mov     rdi, rdx
0x180006523  mov     r14, rcx
0x180006526  jnz     short loc_180006558
0x180006528  cmp     r8, 764F7250h
0x18000652f  jnz     short loc_18000654E
0x180006531  cmp     r9, 6B476953h
0x180006538  jnz     short loc_18000654E
0x18000653a  cmp     dword ptr [rdx], 62436349h
0x180006540  jnz     short loc_18000654E
0x180006542  mov     qword ptr [rcx], 6B536553h
0x180006549  jmp     loc_1800066EE
0x18000654e  mov     eax, 80070057h
0x180006553  jmp     loc_1800066F0
0x180006558  mov     rdx, rsi; hProv
0x18000655b  mov     [rsp+68h+hHash], 0
0x180006564  lea     rcx, [rsp+68h+hHash]; phHash
0x180006569  call    IISCryptoCreateHash
0x18000656e  mov     ebx, eax
0x180006570  test    eax, eax
0x180006572  jns     short loc_1800065B6
0x180006574  test    byte ptr cs:g_dwDebugFlags, 3
0x18000657b  jz      loc_1800066D1
0x180006581  mov     [rsp+68h+dwFlags], eax; char
0x180006585  mov     r8d, 2D8h; unsigned int
0x18000658b  lea     rax, aIiscryptoimpor_3; "IISCryptoImportSessionKeyBlob.IISCrypto"...
0x180006592  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180006599  lea     r9, aIiscryptoimpor_5; "IISCryptoImportSessionKeyBlob"
0x1800065a0  lea     rdx, aInetsrvIisMbCr_1; "inetsrv\\iis\\mb\\crypto\\key.cxx"
0x1800065a7  mov     [rsp+68h+szDescription], rax; char *
0x1800065ac  call    PuDbgPrint
0x1800065b1  jmp     loc_1800066D1
0x1800065b6  mov     rcx, [rsp+68h+hHash]; hHash
0x1800065bb  test    rcx, rcx
0x1800065be  jnz     short loc_1800065CA
0x1800065c0  mov     ebx, 80004005h
0x1800065c5  jmp     loc_1800066E0
0x1800065ca  mov     r8d, [rdi+8]; dwDataLen
0x1800065ce  lea     rdx, [rdi+10h]; pbData
0x1800065d2  xor     r9d, r9d; dwFlags
0x1800065d5  call    cs:__imp_CryptHashData
0x1800065db  test    eax, eax
0x1800065dd  jnz     short loc_180006606
0x1800065df  call    ?IcpGetLastError@@YAJXZ; IcpGetLastError(void)
0x1800065e4  test    byte ptr cs:g_dwDebugFlags, 3
0x1800065eb  mov     ebx, eax
0x1800065ed  jz      loc_1800066D1
0x1800065f3  mov     [rsp+68h+dwFlags], eax
0x1800065f7  mov     r8d, 2EEh
0x1800065fd  lea     rax, aIiscryptoimpor_4; "IISCryptoImportSessionKeyBlob.CryptHash"...
0x180006604  jmp     short loc_180006592
0x180006606  mov     edx, [rdi+8]
0x180006609  mov     ecx, 0FFFFFFF8h
0x18000660e  mov     r8d, [rdi+0Ch]; dwSigLen
0x180006612  add     edx, 7
0x180006615  and     rdx, rcx
0x180006618  mov     [rsp+68h+dwFlags], 0; dwFlags
0x180006620  mov     rcx, [rsp+68h+hHash]; hHash
0x180006625  add     rdx, 10h
0x180006629  add     rdx, rdi; pbSignature
0x18000662c  mov     [rsp+68h+szDescription], 0; szDescription
0x180006635  mov     r9, rbp; hPubKey
0x180006638  call    cs:__imp_CryptVerifySignatureA
0x18000663e  test    eax, eax
0x180006640  jnz     short loc_180006668
0x180006642  call    ?IcpGetLastError@@YAJXZ; IcpGetLastError(void)
0x180006647  test    byte ptr cs:g_dwDebugFlags, 3
0x18000664e  mov     ebx, eax
0x180006650  jz      short loc_1800066D1
0x180006652  mov     [rsp+68h+dwFlags], eax
0x180006656  mov     r8d, 2FDh
0x18000665c  lea     rax, aIiscryptoimpor_2; "IISCryptoImportSessionKeyBlob.CryptVeri"...
0x180006663  jmp     loc_180006592
0x180006668  mov     r8d, [rdi+8]; dwDataLen
0x18000666c  lea     rdx, [rdi+10h]; pbData
0x180006670  mov     qword ptr [rsp+68h+dwFlags], r14; phKey
0x180006675  xor     r9d, r9d; hPubKey
0x180006678  mov     rcx, rsi; hProv
0x18000667b  mov     dword ptr [rsp+68h+szDescription], 0; dwFlags
0x180006683  call    cs:__imp_CryptImportKey
0x180006689  test    eax, eax
0x18000668b  jnz     short loc_1800066E4
0x18000668d  call    ?IcpGetLastError@@YAJXZ; IcpGetLastError(void)
0x180006692  test    byte ptr cs:g_dwDebugFlags, 3
0x180006699  mov     ebx, eax
0x18000669b  jz      short loc_1800066CD
0x18000669d  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x1800066a4  lea     r9, aIiscryptoimpor_5; "IISCryptoImportSessionKeyBlob"
0x1800066ab  mov     [rsp+68h+dwFlags], eax; char
0x1800066af  lea     rdx, aInetsrvIisMbCr_1; "inetsrv\\iis\\mb\\crypto\\key.cxx"
0x1800066b6  lea     rax, aIiscryptoimpor_1; "IISCryptoImportSessionKeyBlob.CryptImpo"...
0x1800066bd  mov     r8d, 310h; unsigned int
0x1800066c3  mov     [rsp+68h+szDescription], rax; char *
0x1800066c8  call    PuDbgPrint
0x1800066cd  test    ebx, ebx
0x1800066cf  jns     short loc_1800066E4
0x1800066d1  mov     rcx, [rsp+68h+hHash]
0x1800066d6  test    rcx, rcx
0x1800066d9  jz      short loc_1800066E0
0x1800066db  call    IISCryptoDestroyHash
0x1800066e0  mov     eax, ebx
0x1800066e2  jmp     short loc_1800066F0
0x1800066e4  mov     rcx, [rsp+68h+hHash]
0x1800066e9  call    IISCryptoDestroyHash
0x1800066ee  xor     eax, eax
0x1800066f0  add     rsp, 40h
0x1800066f4  pop     r14
0x1800066f6  pop     rdi
0x1800066f7  pop     rsi
0x1800066f8  pop     rbp
0x1800066f9  pop     rbx
0x1800066fa  retn
```
