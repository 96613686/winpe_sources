# MSCryptKemImportKeyPair

- ea: `0x180064ff0`
- end: `0x18006515a`
- name: `MSCryptKemImportKeyPair`
- size: `362`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64 *, _DWORD *, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x18000ecb0`
- `0x180063b00`
- `0x180063bcc`
- `0x1800642d4`
- `0x18006445c`
- `0x180064ff0`
- `0x1800653d4`

## string_xrefs

- `0x180065033`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\kem.c`
- `0x18006512c`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\kem.c`

## pseudocode

```c
__int64 __fastcall MSCryptKemImportKeyPair(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 *a4,
        _DWORD *a5,
        unsigned int a6,
        unsigned int a7)
{
  __int64 v8; // rdi
  int v11; // eax
  unsigned int v12; // ebx
  __int64 v13; // r9
  __int64 v14; // rcx
  __int64 v15; // rdi
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // r9
  int v19; // ecx
  int v20; // ecx
  int v21; // eax
  __int64 v23; // [rsp+20h] [rbp-38h] BYREF
  _QWORD v24[6]; // [rsp+28h] [rbp-30h] BYREF

  v24[0] = 0;
  v8 = 0;
  v23 = 0;
  v11 = ValidateKemAlgorithm(a1, v24);
  v12 = v11;
  if ( v11 < 0 )
  {
    v13 = 1815;
    v14 = (unsigned int)v11;
LABEL_3:
    DebugTraceError(v14, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\kem.c", v13);
    return v12;
  }
  if ( a2 )
  {
    v12 = -1073741637;
    v13 = 1822;
    v14 = 3221225659LL;
    goto LABEL_3;
  }
  if ( a5 && a3 && a4 )
  {
    v15 = v24[0];
    v16 = CreateNewMSCryptKemKey(&v23, a7, *(unsigned int *)(v24[0] + 8LL));
    v12 = v16;
    if ( v16 < 0 )
    {
      v8 = v23;
      v17 = (unsigned int)v16;
      v18 = 1838;
      goto LABEL_20;
    }
    v19 = *(_DWORD *)(v15 + 8);
    v8 = v23;
    v20 = v19 - 458753;
    if ( v20 )
    {
      if ( v20 != 1 )
      {
        v12 = -1073741637;
        v17 = 3221225659LL;
        v18 = 1857;
        goto LABEL_20;
      }
      v21 = ImportCompositeMlKemKeyPair(a5, a6, a3, v23);
    }
    else
    {
      v21 = ImportMlKemKeyPair(a5, a6, a3, v23);
    }
    v12 = v21;
    if ( v21 >= 0 )
    {
      *(_DWORD *)(v8 + 16) = 1;
      *a4 = v8;
      return v12;
    }
    v17 = (unsigned int)v21;
    v18 = 1864;
    goto LABEL_20;
  }
  v12 = -1073741811;
  v17 = 3221225485LL;
  v18 = 1831;
LABEL_20:
  DebugTraceError(v17, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\kem.c", v18);
  if ( v8 )
    DestroyKemKey(v8);
  return v12;
}

```

## disassembly

```asm
0x180064ff0  push    rbx
0x180064ff2  push    rbp
0x180064ff3  push    rsi
0x180064ff4  push    rdi
0x180064ff5  push    r14
0x180064ff7  sub     rsp, 30h
0x180064ffb  mov     rsi, rdx
0x180064ffe  mov     [rsp+58h+var_30], 0
0x180065007  xor     edi, edi
0x180065009  lea     rdx, [rsp+58h+var_30]
0x18006500e  mov     [rsp+58h+var_38], rdi
0x180065013  mov     r14, r9
0x180065016  mov     rbp, r8
0x180065019  call    ValidateKemAlgorithm
0x18006501e  mov     ebx, eax
0x180065020  test    eax, eax
0x180065022  jns     short loc_180065044
0x180065024  mov     r9d, 717h
0x18006502a  mov     ecx, eax
0x18006502c  lea     rdx, aStatus; "Status"
0x180065033  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18006503a  call    DebugTraceError
0x18006503f  jmp     loc_18006514C
0x180065044  test    rsi, rsi
0x180065047  jz      short loc_18006505B
0x180065049  mov     ebx, 0C00000BBh
0x18006504e  mov     r9d, 71Eh
0x180065054  mov     ecx, 0C00000BBh
0x180065059  jmp     short loc_18006502C
0x18006505b  mov     rsi, [rsp+58h+arg_20]
0x180065063  test    rsi, rsi
0x180065066  jz      loc_18006511C
0x18006506c  test    rbp, rbp
0x18006506f  jz      loc_18006511C
0x180065075  test    r14, r14
0x180065078  jz      loc_18006511C
0x18006507e  mov     rdi, [rsp+58h+var_30]
0x180065083  lea     rcx, [rsp+58h+var_38]
0x180065088  mov     edx, [rsp+58h+arg_30]
0x18006508f  mov     r8d, [rdi+8]
0x180065093  call    CreateNewMSCryptKemKey
0x180065098  mov     ebx, eax
0x18006509a  test    eax, eax
0x18006509c  jns     short loc_1800650AD
0x18006509e  mov     rdi, [rsp+58h+var_38]
0x1800650a3  mov     ecx, eax
0x1800650a5  mov     r9d, 72Eh
0x1800650ab  jmp     short loc_18006512C
0x1800650ad  mov     ecx, [rdi+8]
0x1800650b0  mov     rdi, [rsp+58h+var_38]
0x1800650b5  sub     ecx, 70001h
0x1800650bb  jz      short loc_1800650EB
0x1800650bd  cmp     ecx, 1
0x1800650c0  jz      short loc_1800650D4
0x1800650c2  mov     ebx, 0C00000BBh
0x1800650c7  mov     ecx, 0C00000BBh
0x1800650cc  mov     r9d, 741h
0x1800650d2  jmp     short loc_18006512C
0x1800650d4  mov     edx, [rsp+58h+arg_28]
0x1800650db  mov     r9, rdi
0x1800650de  mov     r8, rbp
0x1800650e1  mov     rcx, rsi
0x1800650e4  call    ImportCompositeMlKemKeyPair
0x1800650e9  jmp     short loc_180065100
0x1800650eb  mov     edx, [rsp+58h+arg_28]
0x1800650f2  mov     r9, rdi
0x1800650f5  mov     r8, rbp
0x1800650f8  mov     rcx, rsi
0x1800650fb  call    ImportMlKemKeyPair
0x180065100  mov     ebx, eax
0x180065102  test    eax, eax
0x180065104  jns     short loc_180065110
0x180065106  mov     ecx, eax
0x180065108  mov     r9d, 748h
0x18006510e  jmp     short loc_18006512C
0x180065110  mov     dword ptr [rdi+10h], 1
0x180065117  mov     [r14], rdi
0x18006511a  jmp     short loc_18006514C
0x18006511c  mov     ebx, 0C000000Dh
0x180065121  mov     ecx, 0C000000Dh
0x180065126  mov     r9d, 727h
0x18006512c  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180065133  lea     rdx, aStatus; "Status"
0x18006513a  call    DebugTraceError
0x18006513f  test    rdi, rdi
0x180065142  jz      short loc_18006514C
0x180065144  mov     rcx, rdi
0x180065147  call    DestroyKemKey
0x18006514c  mov     eax, ebx
0x18006514e  add     rsp, 30h
0x180065152  pop     r14
0x180065154  pop     rdi
0x180065155  pop     rsi
0x180065156  pop     rbp
0x180065157  pop     rbx
0x180065158  retn
```
