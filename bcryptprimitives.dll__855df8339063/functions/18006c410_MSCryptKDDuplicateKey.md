# MSCryptKDDuplicateKey

- ea: `0x18006c410`
- end: `0x18006c5bd`
- name: `MSCryptKDDuplicateKey`
- size: `429`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18000ecb0`
- `0x180010270`
- `0x1800102a0`
- `0x180010ee0`
- `0x1800473b0`
- `0x180048f50`
- `0x1800593e0`
- `0x18006c410`

## string_xrefs

- `0x18006c464`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x18006c535`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`

## pseudocode

```c
__int64 __fastcall MSCryptKDDuplicateKey(__int64 a1, _QWORD *a2, __int64 a3, unsigned int a4, int a5)
{
  unsigned int v9; // ebx
  __int64 v10; // r9
  __int64 v11; // rcx
  int v12; // eax
  unsigned int v13; // ebx
  char *v14; // rdi
  int v15; // eax
  __int64 v16; // rsi
  __int64 v17; // r9
  unsigned int v19; // [rsp+50h] [rbp-58h] BYREF
  __int64 v20; // [rsp+58h] [rbp-50h] BYREF
  _QWORD v21[9]; // [rsp+60h] [rbp-48h] BYREF

  v20 = 0;
  v21[0] = 0;
  v19 = 0;
  if ( !a5 )
  {
    if ( (int)ValidateKeyDerivationKey(a1, &v20) < 0 )
    {
      v9 = -1073741816;
      v10 = 2227;
      v11 = 3221225480LL;
      goto LABEL_3;
    }
    v12 = MSCryptKDExportKey(a1, 0, L"KeyDataBlob", 0, 0, &v19, 0);
    v9 = v12;
    if ( v12 < 0 )
    {
      v10 = 2245;
      v11 = (unsigned int)v12;
      goto LABEL_3;
    }
    v13 = v19;
    v14 = (char *)SafeAllocaAllocateFromHeap(v19);
    if ( !v14 )
    {
      v9 = -1073741801;
      v10 = 2253;
      v11 = 3221225495LL;
      goto LABEL_3;
    }
    v15 = MSCryptKDExportKey(a1, 0, L"KeyDataBlob", v14, v13, &v19, 0);
    v16 = v19;
    v9 = v15;
    if ( v15 >= 0 )
    {
      v15 = MSCryptKDImportKey(*(_QWORD *)(v20 + 40), 0, L"KeyDataBlob", v21, a3, a4, v14, v19, 0);
      v9 = v15;
      if ( v15 >= 0 )
      {
        v9 = 0;
        *a2 = v21[0];
        goto LABEL_16;
      }
      v17 = 2288;
    }
    else
    {
      v17 = 2267;
    }
    DebugTraceError(
      (unsigned int)v15,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
      v17);
LABEL_16:
    SymCryptWipeAsm(v14, v16);
    MSCryptFree(v14);
    return v9;
  }
  v9 = -1073741811;
  v10 = 2216;
  v11 = 3221225485LL;
LABEL_3:
  DebugTraceError(
    v11,
    "Status",
    "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
    v10);
  return v9;
}

```

## disassembly

```asm
0x18006c410  push    rbx
0x18006c412  push    rbp
0x18006c413  push    rsi
0x18006c414  push    rdi
0x18006c415  push    r14
0x18006c417  push    r15
0x18006c419  sub     rsp, 78h
0x18006c41d  cmp     [rsp+0A8h+arg_20], 0
0x18006c425  mov     ebp, r9d
0x18006c428  mov     r15, r8
0x18006c42b  mov     [rsp+0A8h+var_50], 0
0x18006c434  mov     r14, rdx
0x18006c437  mov     [rsp+0A8h+var_48], 0
0x18006c440  mov     rsi, rcx
0x18006c443  mov     [rsp+0A8h+var_58], 0
0x18006c44b  jz      short loc_18006C475
0x18006c44d  mov     ebx, 0C000000Dh
0x18006c452  mov     r9d, 8A8h
0x18006c458  mov     ecx, 0C000000Dh
0x18006c45d  lea     rdx, aStatus; "Status"
0x18006c464  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18006c46b  call    DebugTraceError
0x18006c470  jmp     loc_18006C5AD
0x18006c475  lea     rdx, [rsp+0A8h+var_50]
0x18006c47a  call    ValidateKeyDerivationKey
0x18006c47f  test    eax, eax
0x18006c481  jns     short loc_18006C495
0x18006c483  mov     ebx, 0C0000008h
0x18006c488  mov     r9d, 8B3h
0x18006c48e  mov     ecx, 0C0000008h
0x18006c493  jmp     short loc_18006C45D
0x18006c495  lea     rax, [rsp+0A8h+var_58]
0x18006c49a  mov     dword ptr [rsp+0A8h+var_78], 0
0x18006c4a2  mov     [rsp+0A8h+var_80], rax
0x18006c4a7  lea     r8, aKeydatablob; "KeyDataBlob"
0x18006c4ae  xor     r9d, r9d
0x18006c4b1  mov     dword ptr [rsp+0A8h+var_88], 0
0x18006c4b9  xor     edx, edx
0x18006c4bb  mov     rcx, rsi
0x18006c4be  call    MSCryptKDExportKey
0x18006c4c3  mov     ebx, eax
0x18006c4c5  test    eax, eax
0x18006c4c7  jns     short loc_18006C4D3
0x18006c4c9  mov     r9d, 8C5h
0x18006c4cf  mov     ecx, eax
0x18006c4d1  jmp     short loc_18006C45D
0x18006c4d3  mov     ebx, [rsp+0A8h+var_58]
0x18006c4d7  mov     ecx, ebx
0x18006c4d9  call    SafeAllocaAllocateFromHeap
0x18006c4de  mov     rdi, rax
0x18006c4e1  test    rax, rax
0x18006c4e4  jnz     short loc_18006C4FB
0x18006c4e6  mov     ebx, 0C0000017h
0x18006c4eb  mov     r9d, 8CDh
0x18006c4f1  mov     ecx, 0C0000017h
0x18006c4f6  jmp     loc_18006C45D
0x18006c4fb  lea     rax, [rsp+0A8h+var_58]
0x18006c500  mov     dword ptr [rsp+0A8h+var_78], 0
0x18006c508  mov     [rsp+0A8h+var_80], rax
0x18006c50d  lea     r8, aKeydatablob; "KeyDataBlob"
0x18006c514  mov     r9, rdi
0x18006c517  mov     dword ptr [rsp+0A8h+var_88], ebx
0x18006c51b  xor     edx, edx
0x18006c51d  mov     rcx, rsi
0x18006c520  call    MSCryptKDExportKey
0x18006c525  mov     esi, [rsp+0A8h+var_58]
0x18006c529  mov     ebx, eax
0x18006c52b  test    eax, eax
0x18006c52d  jns     short loc_18006C54C
0x18006c52f  mov     r9d, 8DBh
0x18006c535  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18006c53c  mov     ecx, eax
0x18006c53e  lea     rdx, aStatus; "Status"
0x18006c545  call    DebugTraceError
0x18006c54a  jmp     short loc_18006C59A
0x18006c54c  mov     rcx, [rsp+0A8h+var_50]
0x18006c551  lea     r9, [rsp+0A8h+var_48]
0x18006c556  mov     [rsp+0A8h+var_68], 0
0x18006c55e  lea     r8, aKeydatablob; "KeyDataBlob"
0x18006c565  mov     [rsp+0A8h+var_70], esi
0x18006c569  xor     edx, edx
0x18006c56b  mov     [rsp+0A8h+var_78], rdi
0x18006c570  mov     rcx, [rcx+28h]
0x18006c574  mov     dword ptr [rsp+0A8h+var_80], ebp
0x18006c578  mov     [rsp+0A8h+var_88], r15
0x18006c57d  call    MSCryptKDImportKey
0x18006c582  mov     ebx, eax
0x18006c584  test    eax, eax
0x18006c586  jns     short loc_18006C590
0x18006c588  mov     r9d, 8F0h
0x18006c58e  jmp     short loc_18006C535
0x18006c590  mov     rax, [rsp+0A8h+var_48]
0x18006c595  xor     ebx, ebx
0x18006c597  mov     [r14], rax
0x18006c59a  mov     rdx, rsi
0x18006c59d  mov     rcx, rdi
0x18006c5a0  call    SymCryptWipeAsm
0x18006c5a5  mov     rcx, rdi
0x18006c5a8  call    MSCryptFree
0x18006c5ad  mov     eax, ebx
0x18006c5af  add     rsp, 78h
0x18006c5b3  pop     r15
0x18006c5b5  pop     r14
0x18006c5b7  pop     rdi
0x18006c5b8  pop     rsi
0x18006c5b9  pop     rbp
0x18006c5ba  pop     rbx
0x18006c5bb  retn
```
