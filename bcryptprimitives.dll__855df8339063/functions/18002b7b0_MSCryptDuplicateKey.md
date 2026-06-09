# MSCryptDuplicateKey

- ea: `0x18002b7b0`
- end: `0x18002b953`
- name: `MSCryptDuplicateKey`
- size: `419`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x18002b7b0`
- `0x18002b960`
- `0x18002cd40`
- `0x1800593e0`
- `0x18007f790`

## string_xrefs

- `0x18002b8cd`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18002b91d`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18002b939`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`

## pseudocode

```c
__int64 __fastcall MSCryptDuplicateKey(__int64 a1, _QWORD *a2, __int64 a3, unsigned int a4, int a5)
{
  int v9; // edx
  int v10; // ebx
  int v11; // eax
  unsigned int v13; // [rsp+50h] [rbp-278h] BYREF
  __int64 v14; // [rsp+58h] [rbp-270h] BYREF
  _DWORD v15[140]; // [rsp+60h] [rbp-268h] BYREF

  v13 = 0;
  v14 = 0;
  if ( a5 )
  {
    v10 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
        85);
  }
  else
  {
    v10 = MSCryptExportKey((_DWORD *)a1, 0, L"OpaqueKeyBlob", v15, 0x230u, &v13, 0);
    if ( v10 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v9,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
          (unsigned int)"Status",
          v10,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
          101);
    }
    else
    {
      v11 = MSCryptImportKey(*(_QWORD *)(a1 + 32), 0, L"OpaqueKeyBlob", &v14, a3, a4, v15, v13, 0);
      v10 = v11;
      if ( v11 < 0 )
      {
        DebugTraceError(
          (unsigned int)v11,
          "Status",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
          1657);
      }
      else
      {
        v10 = 0;
        *a2 = v14;
      }
    }
  }
  SymCryptWipeAsm(v15, 560);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18002b7b0  push    rbx
0x18002b7b2  push    rbp
0x18002b7b3  push    rsi
0x18002b7b4  push    rdi
0x18002b7b5  push    r14
0x18002b7b7  sub     rsp, 2A0h
0x18002b7be  mov     rax, cs:__security_cookie
0x18002b7c5  xor     rax, rsp
0x18002b7c8  mov     [rsp+2C8h+var_38], rax
0x18002b7d0  cmp     [rsp+2C8h+arg_20], 0
0x18002b7d8  mov     ebp, r9d
0x18002b7db  mov     r14, r8
0x18002b7de  mov     [rsp+2C8h+var_278], 0
0x18002b7e6  mov     rdi, rdx
0x18002b7e9  mov     [rsp+2C8h+var_270], 0
0x18002b7f2  mov     rsi, rcx
0x18002b7f5  jnz     loc_18002B8EF
0x18002b7fb  lea     rax, [rsp+2C8h+var_278]
0x18002b800  mov     dword ptr [rsp+2C8h+var_298], 0
0x18002b808  mov     [rsp+2C8h+var_2A0], rax
0x18002b80d  lea     r9, [rsp+2C8h+var_268]
0x18002b812  lea     r8, aOpaquekeyblob; "OpaqueKeyBlob"
0x18002b819  mov     dword ptr [rsp+2C8h+var_2A8], 230h
0x18002b821  xor     edx, edx
0x18002b823  call    MSCryptExportKey
0x18002b828  mov     ebx, eax
0x18002b82a  test    eax, eax
0x18002b82c  js      short loc_18002B8AC
0x18002b82e  mov     eax, [rsp+2C8h+var_278]
0x18002b832  lea     r9, [rsp+2C8h+var_270]
0x18002b837  mov     rcx, [rsi+20h]
0x18002b83b  lea     r8, aOpaquekeyblob; "OpaqueKeyBlob"
0x18002b842  mov     [rsp+2C8h+var_288], 0
0x18002b84a  xor     edx, edx
0x18002b84c  mov     [rsp+2C8h+var_290], eax
0x18002b850  lea     rax, [rsp+2C8h+var_268]
0x18002b855  mov     [rsp+2C8h+var_298], rax
0x18002b85a  mov     dword ptr [rsp+2C8h+var_2A0], ebp
0x18002b85e  mov     [rsp+2C8h+var_2A8], r14
0x18002b863  call    MSCryptImportKey
0x18002b868  mov     ebx, eax
0x18002b86a  test    eax, eax
0x18002b86c  js      loc_18002B933
0x18002b872  mov     rax, [rsp+2C8h+var_270]
0x18002b877  xor     ebx, ebx
0x18002b879  mov     [rdi], rax
0x18002b87c  mov     edx, 230h
0x18002b881  lea     rcx, [rsp+2C8h+var_268]
0x18002b886  call    SymCryptWipeAsm
0x18002b88b  mov     eax, ebx
0x18002b88d  mov     rcx, [rsp+2C8h+var_38]
0x18002b895  xor     rcx, rsp; StackCookie
0x18002b898  call    __security_check_cookie
0x18002b89d  add     rsp, 2A0h
0x18002b8a4  pop     r14
0x18002b8a6  pop     rdi
0x18002b8a7  pop     rsi
0x18002b8a8  pop     rbp
0x18002b8a9  pop     rbx
0x18002b8aa  retn
0x18002b8ac  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b8b3  lea     rax, WPP_GLOBAL_Control
0x18002b8ba  cmp     rcx, rax
0x18002b8bd  jz      short loc_18002B87C
0x18002b8bf  test    byte ptr [rcx+1Ch], 1
0x18002b8c3  jz      short loc_18002B87C
0x18002b8c5  mov     dword ptr [rsp+2C8h+var_298], 665h
0x18002b8cd  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18002b8d4  mov     [rsp+2C8h+var_2A0], r8
0x18002b8d9  mov     dword ptr [rsp+2C8h+var_2A8], ebx
0x18002b8dd  mov     rcx, [rcx+10h]
0x18002b8e1  lea     r9, aStatus; "Status"
0x18002b8e8  call    WPP_SF_sDsd
0x18002b8ed  jmp     short loc_18002B87C
0x18002b8ef  mov     ebx, 0C000000Dh
0x18002b8f4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b8fb  lea     rax, WPP_GLOBAL_Control
0x18002b902  cmp     rcx, rax
0x18002b905  jz      loc_18002B87C
0x18002b90b  test    byte ptr [rcx+1Ch], 1
0x18002b90f  jz      loc_18002B87C
0x18002b915  mov     dword ptr [rsp+2C8h+var_298], 655h
0x18002b91d  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18002b924  mov     [rsp+2C8h+var_2A0], r8
0x18002b929  mov     dword ptr [rsp+2C8h+var_2A8], 0C000000Dh
0x18002b931  jmp     short loc_18002B8DD
0x18002b933  mov     r9d, 679h
0x18002b939  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18002b940  lea     rdx, aStatus; "Status"
0x18002b947  mov     ecx, eax
0x18002b949  call    DebugTraceError
0x18002b94e  jmp     loc_18002B87C
```
