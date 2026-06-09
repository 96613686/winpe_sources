# ImportCompositeMlKemKeyPair

- ea: `0x1800642d4`
- end: `0x180064454`
- name: `ImportCompositeMlKemKeyPair`
- size: `384`
- prototype: `__int64 __fastcall(_DWORD *, unsigned int, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180064ff0`

## callees

- `0x18000ecb0`
- `0x180056cf0`
- `0x180063fdc`
- `0x180064094`
- `0x1800642d4`
- `0x18006ff00`
- `0x18006ffc0`
- `0x180070154`

## string_xrefs

- `0x18006431b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\kem.c`
- `0x180064413`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\kem.c`

## pseudocode

```c
__int64 __fastcall ImportCompositeMlKemKeyPair(_DWORD *a1, unsigned int a2, __int64 a3, __int64 a4)
{
  __int64 v7; // r9
  __int64 v8; // rbx
  __int64 v9; // rcx
  int CompositeMlKemBlobInfo; // eax
  __int64 v11; // r13
  __int64 v12; // r14
  unsigned int v13; // eax
  size_t v14; // r12
  __int64 v15; // r15
  unsigned int **v16; // rax
  unsigned int **v17; // rsi
  unsigned int v18; // eax
  __int64 v20; // [rsp+30h] [rbp-58h] BYREF
  __int64 v21; // [rsp+38h] [rbp-50h]

  v20 = 0;
  v21 = 0;
  if ( a2 < 0xC )
  {
    v7 = 1710;
LABEL_3:
    LODWORD(v8) = -1073741811;
    v9 = 3221225485LL;
LABEL_4:
    DebugTraceError(v9, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\kem.c", v7);
    return (unsigned int)v8;
  }
  CompositeMlKemBlobInfo = GetCompositeMlKemBlobInfo(a3, &v20);
  LODWORD(v8) = CompositeMlKemBlobInfo;
  if ( CompositeMlKemBlobInfo < 0 )
  {
    v7 = 1717;
LABEL_7:
    v9 = (unsigned int)CompositeMlKemBlobInfo;
    goto LABEL_4;
  }
  v11 = v20;
  if ( *a1 != *(_DWORD *)(v20 + 16) )
  {
    v7 = 1726;
    goto LABEL_3;
  }
  v12 = (unsigned int)a1[1];
  v13 = v12 + 12;
  if ( (unsigned int)v12 >= 0xFFFFFFF4 )
  {
    v7 = 1738;
LABEL_12:
    LODWORD(v8) = -1073741675;
    v9 = 3221225621LL;
    goto LABEL_4;
  }
  v14 = (unsigned int)a1[2];
  if ( (unsigned int)v14 + v13 < v13 )
  {
    v7 = 1745;
    goto LABEL_12;
  }
  if ( a2 < (unsigned int)v14 + v13 )
  {
    v7 = 1752;
    goto LABEL_3;
  }
  CompositeMlKemBlobInfo = GetCompositeMlKemParamSetInfo(a1 + 3, (unsigned int)v12);
  LODWORD(v8) = CompositeMlKemBlobInfo;
  if ( CompositeMlKemBlobInfo < 0 )
  {
    v7 = 1762;
    goto LABEL_7;
  }
  v15 = v21;
  v16 = (unsigned int **)SymCryptCompositeMlKemkeyAllocate(*(unsigned int *)(v21 + 28));
  v17 = v16;
  if ( !v16 )
  {
    LODWORD(v8) = -1073741801;
    v7 = 1770;
    v9 = 3221225495LL;
    goto LABEL_4;
  }
  v18 = SymCryptCompositeMlKemkeySetValue((char *)a1 + v12 + 12, v14, *(_DWORD *)(v11 + 20), *(_DWORD *)(a4 + 12), v16);
  if ( v18 )
  {
    v8 = (unsigned int)SymcryptErrorCodeToNtStatus(v18);
    DebugTraceError(v8, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\kem.c", 1778);
    SymCryptCompositeMlKemkeyFree(v17);
  }
  else
  {
    *(_QWORD *)(a4 + 32) = v17;
    *(_QWORD *)(a4 + 24) = v15;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800642d4  push    rbx
0x1800642d6  push    rbp
0x1800642d7  push    rsi
0x1800642d8  push    rdi
0x1800642d9  push    r12
0x1800642db  push    r13
0x1800642dd  push    r14
0x1800642df  push    r15
0x1800642e1  sub     rsp, 48h
0x1800642e5  mov     [rsp+88h+var_58], 0
0x1800642ee  mov     rbp, r9
0x1800642f1  mov     [rsp+88h+var_50], 0
0x1800642fa  mov     esi, edx
0x1800642fc  mov     rdi, rcx
0x1800642ff  cmp     edx, 0Ch
0x180064302  jnb     short loc_18006432C
0x180064304  mov     r9d, 6AEh
0x18006430a  mov     ebx, 0C000000Dh
0x18006430f  mov     ecx, 0C000000Dh
0x180064314  lea     rdx, aStatus; "Status"
0x18006431b  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180064322  call    DebugTraceError
0x180064327  jmp     loc_180064440
0x18006432c  lea     rdx, [rsp+88h+var_58]
0x180064331  mov     rcx, r8
0x180064334  call    GetCompositeMlKemBlobInfo
0x180064339  mov     ebx, eax
0x18006433b  test    eax, eax
0x18006433d  jns     short loc_180064349
0x18006433f  mov     r9d, 6B5h
0x180064345  mov     ecx, eax
0x180064347  jmp     short loc_180064314
0x180064349  mov     r13, [rsp+88h+var_58]
0x18006434e  mov     eax, [r13+10h]
0x180064352  cmp     [rdi], eax
0x180064354  jz      short loc_18006435E
0x180064356  mov     r9d, 6BEh
0x18006435c  jmp     short loc_18006430A
0x18006435e  mov     r14d, [rdi+4]
0x180064362  lea     eax, [r14+0Ch]
0x180064366  cmp     eax, 0Ch
0x180064369  jnb     short loc_18006437D
0x18006436b  mov     r9d, 6CAh
0x180064371  mov     ebx, 0C0000095h
0x180064376  mov     ecx, 0C0000095h
0x18006437b  jmp     short loc_180064314
0x18006437d  mov     r12d, [rdi+8]
0x180064381  lea     ecx, [r12+rax]
0x180064385  cmp     ecx, eax
0x180064387  jnb     short loc_180064391
0x180064389  mov     r9d, 6D1h
0x18006438f  jmp     short loc_180064371
0x180064391  cmp     esi, ecx
0x180064393  jnb     short loc_1800643A0
0x180064395  mov     r9d, 6D8h
0x18006439b  jmp     loc_18006430A
0x1800643a0  lea     rcx, [rdi+0Ch]; Buf1
0x1800643a4  mov     edx, r14d; Size
0x1800643a7  lea     r8, [rsp+88h+var_50]
0x1800643ac  call    GetCompositeMlKemParamSetInfo
0x1800643b1  mov     ebx, eax
0x1800643b3  test    eax, eax
0x1800643b5  jns     short loc_1800643BF
0x1800643b7  mov     r9d, 6E2h
0x1800643bd  jmp     short loc_180064345
0x1800643bf  mov     r15, [rsp+88h+var_50]
0x1800643c4  mov     ecx, [r15+1Ch]
0x1800643c8  call    SymCryptCompositeMlKemkeyAllocate
0x1800643cd  mov     rsi, rax
0x1800643d0  test    rax, rax
0x1800643d3  jnz     short loc_1800643EA
0x1800643d5  mov     ebx, 0C0000017h
0x1800643da  mov     r9d, 6EAh
0x1800643e0  mov     ecx, 0C0000017h
0x1800643e5  jmp     loc_180064314
0x1800643ea  mov     r9d, [rbp+0Ch]
0x1800643ee  lea     rcx, [rdi+0Ch]
0x1800643f2  mov     r8d, [r13+14h]
0x1800643f6  add     rcx, r14; Src
0x1800643f9  mov     rdx, r12; Size
0x1800643fc  mov     [rsp+88h+var_68], rsi; __int64
0x180064401  call    SymCryptCompositeMlKemkeySetValue
0x180064406  test    eax, eax
0x180064408  jz      short loc_180064438
0x18006440a  mov     ecx, eax
0x18006440c  call    SymcryptErrorCodeToNtStatus
0x180064411  mov     ecx, eax
0x180064413  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18006441a  mov     r9d, 6F2h
0x180064420  lea     rdx, aStatus; "Status"
0x180064427  mov     ebx, eax
0x180064429  call    DebugTraceError
0x18006442e  mov     rcx, rsi
0x180064431  call    SymCryptCompositeMlKemkeyFree
0x180064436  jmp     short loc_180064440
0x180064438  mov     [rbp+20h], rsi
0x18006443c  mov     [rbp+18h], r15
0x180064440  mov     eax, ebx
0x180064442  add     rsp, 48h
0x180064446  pop     r15
0x180064448  pop     r14
0x18006444a  pop     r13
0x18006444c  pop     r12
0x18006444e  pop     rdi
0x18006444f  pop     rsi
0x180064450  pop     rbp
0x180064451  pop     rbx
0x180064452  retn
```
