# GetKeyDerivationInterface

- ea: `0x18004fbd0`
- end: `0x18004fcab`
- name: `GetKeyDerivationInterface`
- size: `219`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000ecb0`
- `0x18004fbd0`
- `0x18007f765`

## string_xrefs

- `0x18004fc89`: `onecore\ds\security\cryptoapi\ncrypt\msprim\msprim\interface.c`

## pseudocode

```c
__int64 __fastcall GetKeyDerivationInterface(__int64 a1, const wchar_t *a2, _QWORD *a3)
{
  unsigned int v5; // ebx

  if ( !wcscmp_0(a2, L"SP800_108_CTR_HMAC")
    || !wcscmp_0(a2, L"SP800_56A_CONCAT")
    || !wcscmp_0(a2, L"PBKDF2")
    || !wcscmp_0(a2, L"CAPI_KDF")
    || !wcscmp_0(a2, L"TLS1_1_KDF")
    || !wcscmp_0(a2, L"TLS1_2_KDF")
    || !wcscmp_0(a2, L"HKDF") )
  {
    v5 = 0;
    *a3 = &MSKeyDerivationFunctionTable;
  }
  else
  {
    v5 = -1073741637;
    DebugTraceError(
      3221225659LL,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\msprim\\interface.c",
      330);
  }
  return v5;
}

```

## disassembly

```asm
0x18004fbd0  mov     [rsp+arg_0], rbx
0x18004fbd5  push    rdi
0x18004fbd6  sub     rsp, 20h
0x18004fbda  mov     rbx, rdx
0x18004fbdd  mov     rdi, r8
0x18004fbe0  mov     rcx, rbx; String1
0x18004fbe3  lea     rdx, aSp800108CtrHma; "SP800_108_CTR_HMAC"
0x18004fbea  call    wcscmp_0
0x18004fbef  test    eax, eax
0x18004fbf1  jnz     short loc_18004FC0D
0x18004fbf3  lea     rax, MSKeyDerivationFunctionTable
0x18004fbfa  xor     ebx, ebx
0x18004fbfc  mov     [rdi], rax
0x18004fbff  mov     eax, ebx
0x18004fc01  mov     rbx, [rsp+28h+arg_0]
0x18004fc06  add     rsp, 20h
0x18004fc0a  pop     rdi
0x18004fc0b  retn
0x18004fc0d  lea     rdx, aSp80056aConcat; "SP800_56A_CONCAT"
0x18004fc14  mov     rcx, rbx; String1
0x18004fc17  call    wcscmp_0
0x18004fc1c  test    eax, eax
0x18004fc1e  jz      short loc_18004FBF3
0x18004fc20  lea     rdx, aPbkdf2; "PBKDF2"
0x18004fc27  mov     rcx, rbx; String1
0x18004fc2a  call    wcscmp_0
0x18004fc2f  test    eax, eax
0x18004fc31  jz      short loc_18004FBF3
0x18004fc33  lea     rdx, aCapiKdf; "CAPI_KDF"
0x18004fc3a  mov     rcx, rbx; String1
0x18004fc3d  call    wcscmp_0
0x18004fc42  test    eax, eax
0x18004fc44  jz      short loc_18004FBF3
0x18004fc46  lea     rdx, aTls11Kdf; "TLS1_1_KDF"
0x18004fc4d  mov     rcx, rbx; String1
0x18004fc50  call    wcscmp_0
0x18004fc55  test    eax, eax
0x18004fc57  jz      short loc_18004FBF3
0x18004fc59  lea     rdx, aTls12Kdf; "TLS1_2_KDF"
0x18004fc60  mov     rcx, rbx; String1
0x18004fc63  call    wcscmp_0
0x18004fc68  test    eax, eax
0x18004fc6a  jz      short loc_18004FBF3
0x18004fc6c  lea     rdx, aHkdf; "HKDF"
0x18004fc73  mov     rcx, rbx; String1
0x18004fc76  call    wcscmp_0
0x18004fc7b  test    eax, eax
0x18004fc7d  jz      loc_18004FBF3
0x18004fc83  mov     r9d, 14Ah
0x18004fc89  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004fc90  lea     rdx, aStatus; "Status"
0x18004fc97  mov     ecx, 0C00000BBh
0x18004fc9c  mov     ebx, 0C00000BBh
0x18004fca1  call    DebugTraceError
0x18004fca6  jmp     loc_18004FBFF
```
