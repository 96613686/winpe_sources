# MSCryptAesKeyUnwrap

- ea: `0x18000c860`
- end: `0x18000cc34`
- name: `MSCryptAesKeyUnwrap`
- size: `980`
- prototype: `__int64 __fastcall(int, int, int, int, int, void *Src, size_t Size)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18002cd40`

## callees

- `0x18000c040`
- `0x18000c860`
- `0x18000d630`
- `0x18000ecb0`
- `0x18000ee60`
- `0x180010270`
- `0x1800102a0`
- `0x18002e680`
- `0x180063170`
- `0x18007f790`

## string_xrefs

- `0x18000ca76`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\aeskeywrap.c`
- `0x18000cb2f`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\aeskeywrap.c`
- `0x18000cbd0`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\aeskeywrap.c`
- `0x180080007`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\aeskeywrap.c`

## pseudocode

```c
__int64 __fastcall MSCryptAesKeyUnwrap(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5, void *Src, size_t Size)
{
  int v7; // edx
  int Property; // ebx
  int v9; // r8d
  __int64 v10; // r14
  __int64 v11; // r15
  char *v12; // rdi
  unsigned __int64 v13; // rax
  char *v14; // r9
  unsigned int v15; // r12d
  unsigned int v16; // r8d
  int v17; // edx
  int v18; // r8d
  int v19; // edx
  int v20; // r8d
  __int64 v21; // rax
  __int64 v22; // rcx
  __int128 *v23; // rax
  unsigned __int64 *v24; // rax
  __int64 v25; // rcx
  int *v26; // rax
  __int64 v28; // rax
  __int64 v29; // r9
  __int64 v30; // rcx
  size_t v31; // [rsp+28h] [rbp-D8h]
  __int128 v32; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v33; // [rsp+60h] [rbp-A0h]
  int v34[2]; // [rsp+68h] [rbp-98h]
  int v35[2]; // [rsp+70h] [rbp-90h]
  unsigned __int64 v36; // [rsp+78h] [rbp-88h] BYREF
  __int64 v37; // [rsp+80h] [rbp-80h]
  int v38[2]; // [rsp+88h] [rbp-78h] BYREF
  __int128 v39; // [rsp+90h] [rbp-70h] BYREF
  char v40; // [rsp+A0h] [rbp-60h] BYREF

  *(_QWORD *)v38 = a1;
  *(_QWORD *)v34 = a4;
  *(_QWORD *)v35 = a3;
  *((_QWORD *)&v32 + 1) = a2;
  *(_QWORD *)&v32 = 0;
  Property = MSCryptGetProperty(a2, (__int64)L"BlockLength", &v32, 4u, (unsigned int *)&v32 + 1, 0);
  v10 = 16;
  if ( Property < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v7,
        v9,
        (unsigned int)"Status",
        Property,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\aeskeywrap.c",
        137);
    goto LABEL_22;
  }
  if ( (_QWORD)v32 != 0x400000010LL )
  {
    Property = -1073741816;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v7,
        v9,
        (unsigned int)"Status",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\aeskeywrap.c",
        145);
    goto LABEL_22;
  }
  if ( (Size & 7) != 0 || (unsigned int)Size < 0x10 )
  {
    Property = -1073741811;
    v29 = 409;
    v30 = 3221225485LL;
    goto LABEL_46;
  }
  if ( (unsigned int)Size <= 0x48 )
  {
    v11 = 0;
    v12 = &v40;
    goto LABEL_7;
  }
  v28 = SafeAllocaAllocateFromHeap((unsigned int)Size);
  v11 = v28;
  if ( !v28 )
  {
    Property = -1073741801;
    v29 = 429;
    v30 = 3221225495LL;
LABEL_46:
    DebugTraceError(v30, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\aeskeywrap.c", v29);
    goto LABEL_22;
  }
  v12 = (char *)v28;
LABEL_7:
  memcpy_0(v12, Src, (unsigned int)Size);
  v13 = *(_QWORD *)v12;
  v14 = v12 + 8;
  v15 = 0;
LABEL_8:
  if ( v15 >= 6 )
  {
    if ( v13 == 0xA6A6A6A6A6A6A6A6uLL )
    {
      LODWORD(v31) = Size - 8;
      Property = MSCryptGenerateSymmetricKey(v38[0], v35[0], v34[0], a5, v14, v31, 128);
      if ( Property < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v19,
            v20,
            (unsigned int)"Status",
            Property,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\aeskeywrap.c",
            244);
      }
      else
      {
        Property = 0;
      }
    }
    else
    {
      Property = -1073700862;
    }
  }
  else
  {
    v16 = (unsigned int)(Size - 8) >> 3;
    while ( 1 )
    {
      if ( !v16 )
      {
        ++v15;
        goto LABEL_8;
      }
      v36 = v13 ^ _byteswap_uint64(v16 + ((unsigned __int64)(unsigned int)(Size - 8) >> 3) * (5 - v15));
      LODWORD(v32) = v16 - 1;
      v33 = 8 * (v16 - 1);
      v37 = *(_QWORD *)&v14[v33];
      v39 = 0;
      Property = MSCryptDecrypt(
                   *((__int64 *)&v32 + 1),
                   (unsigned __int64)&v36,
                   0x10u,
                   0,
                   &v39,
                   16,
                   (unsigned __int64)&v36,
                   0x10u,
                   (_DWORD *)&v32 + 1,
                   0);
      if ( Property < 0 )
        break;
      v14 = v12 + 8;
      v13 = v36;
      v16 = v32;
      *(_QWORD *)&v12[v33 + 8] = v37;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v17,
        v18,
        (unsigned int)"Status",
        Property,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\aeskeywrap.c",
        218);
  }
  if ( v12 )
  {
    v21 = (unsigned int)Size;
    do
    {
      *v12++ = 0;
      --v21;
    }
    while ( v21 );
  }
  if ( v11 )
    MSCryptFree(v11);
LABEL_22:
  v22 = 16;
  v23 = &v39;
  do
  {
    *(_BYTE *)v23 = 0;
    v23 = (__int128 *)((char *)v23 + 1);
    --v22;
  }
  while ( v22 );
  v24 = &v36;
  do
  {
    *(_BYTE *)v24 = 0;
    v24 = (unsigned __int64 *)((char *)v24 + 1);
    --v10;
  }
  while ( v10 );
  v25 = 8;
  v26 = v38;
  do
  {
    *(_BYTE *)v26 = 0;
    v26 = (int *)((char *)v26 + 1);
    --v25;
  }
  while ( v25 );
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x18000c860  push    rbp
0x18000c862  push    rbx
0x18000c863  push    rsi
0x18000c864  push    rdi
0x18000c865  push    r12
0x18000c867  push    r13
0x18000c869  push    r14
0x18000c86b  push    r15
0x18000c86d  lea     rbp, [rsp-8]
0x18000c872  sub     rsp, 108h
0x18000c879  mov     rax, cs:__security_cookie
0x18000c880  xor     rax, rsp
0x18000c883  mov     [rbp+40h+var_50], rax
0x18000c887  mov     r13, [rbp+40h+Src]
0x18000c88b  mov     rax, rdx
0x18000c88e  mov     qword ptr [rbp+40h+var_B8], rcx
0x18000c892  lea     rcx, [rsp+140h+var_EC]
0x18000c897  mov     qword ptr [rsp+140h+var_D8], r9
0x18000c89c  mov     r9d, 4
0x18000c8a2  mov     qword ptr [rsp+140h+var_D0], r8
0x18000c8a7  lea     r8, [rsp+140h+var_F0]
0x18000c8ac  mov     [rsp+140h+var_E8], rdx
0x18000c8b1  lea     rdx, aBlocklength; "BlockLength"
0x18000c8b8  mov     dword ptr [rsp+140h+var_118], 0
0x18000c8c0  mov     [rsp+140h+var_120], rcx
0x18000c8c5  mov     rcx, rax
0x18000c8c8  mov     [rsp+140h+var_F0], 0
0x18000c8d0  mov     [rsp+140h+var_EC], 0
0x18000c8d8  call    MSCryptGetProperty
0x18000c8dd  mov     ebx, eax
0x18000c8df  mov     r14d, 10h
0x18000c8e5  test    eax, eax
0x18000c8e7  js      loc_18000CB0E
0x18000c8ed  cmp     [rsp+140h+var_EC], 4
0x18000c8f2  jnz     loc_18000CBA2
0x18000c8f8  cmp     [rsp+140h+var_F0], r14d
0x18000c8fd  jnz     loc_18000CBA2
0x18000c903  mov     esi, dword ptr [rbp+40h+Size]
0x18000c909  test    sil, 7
0x18000c90d  jnz     loc_18000CC1F
0x18000c913  cmp     esi, r14d
0x18000c916  jb      loc_18000CC1F
0x18000c91c  mov     ebx, esi
0x18000c91e  cmp     esi, 48h ; 'H'
0x18000c921  ja      loc_18000CBE9
0x18000c927  xor     r15d, r15d
0x18000c92a  lea     rdi, [rbp+40h+var_A0]
0x18000c92e  mov     r8, rbx; Size
0x18000c931  lea     r12d, [rsi-8]
0x18000c935  mov     rdx, r13; Src
0x18000c938  mov     rcx, rdi; void *
0x18000c93b  call    memcpy_0
0x18000c940  mov     rax, [rdi]
0x18000c943  lea     r9, [rdi+8]
0x18000c947  mov     r13d, r12d
0x18000c94a  shr     r13, 3
0x18000c94e  xor     r12d, r12d
0x18000c951  cmp     r12d, 6
0x18000c955  jnb     loc_18000CA1E
0x18000c95b  mov     r8d, r13d
0x18000c95e  test    r8d, r8d
0x18000c961  jz      loc_18000CA16
0x18000c967  mov     ecx, r8d
0x18000c96a  mov     edx, 5
0x18000c96f  sub     edx, r12d
0x18000c972  mov     [rsp+140h+var_F8], 0
0x18000c97a  imul    rdx, r13
0x18000c97e  xorps   xmm0, xmm0
0x18000c981  add     rdx, rcx
0x18000c984  mov     rcx, [rsp+140h+var_E8]
0x18000c989  bswap   rdx
0x18000c98c  xor     rdx, rax
0x18000c98f  dec     r8d
0x18000c992  mov     [rsp+140h+var_C8], rdx
0x18000c997  mov     [rsp+140h+var_F0], r8d
0x18000c99c  lea     rdx, [rsp+140h+var_C8]
0x18000c9a1  lea     eax, ds:0[r8*8]
0x18000c9a9  mov     r8d, r14d
0x18000c9ac  mov     [rsp+140h+var_E0], rax
0x18000c9b1  mov     rax, [rax+r9]
0x18000c9b5  xor     r9d, r9d
0x18000c9b8  mov     [rbp+40h+var_C0], rax
0x18000c9bc  lea     rax, [rsp+140h+var_EC]
0x18000c9c1  mov     [rsp+140h+var_100], rax
0x18000c9c6  lea     rax, [rsp+140h+var_C8]
0x18000c9cb  mov     [rsp+140h+var_108], r14d
0x18000c9d0  mov     qword ptr [rsp+140h+var_110], rax
0x18000c9d5  lea     rax, [rbp+40h+var_B0]
0x18000c9d9  mov     dword ptr [rsp+140h+var_118], r14d
0x18000c9de  mov     [rsp+140h+var_120], rax
0x18000c9e3  movups  [rbp+40h+var_B0], xmm0
0x18000c9e7  call    MSCryptDecrypt
0x18000c9ec  mov     ebx, eax
0x18000c9ee  test    eax, eax
0x18000c9f0  js      loc_18000CB44
0x18000c9f6  mov     rdx, [rsp+140h+var_E0]
0x18000c9fb  lea     r9, [rdi+8]
0x18000c9ff  mov     rcx, [rbp+40h+var_C0]
0x18000ca03  mov     rax, [rsp+140h+var_C8]
0x18000ca08  mov     r8d, [rsp+140h+var_F0]
0x18000ca0d  mov     [rdx+r9], rcx
0x18000ca11  jmp     loc_18000C95E
0x18000ca16  inc     r12d
0x18000ca19  jmp     loc_18000C951
0x18000ca1e  mov     rcx, 0A6A6A6A6A6A6A6A6h
0x18000ca28  cmp     rax, rcx
0x18000ca2b  jnz     loc_18000CB98
0x18000ca31  mov     r8, qword ptr [rsp+140h+var_D8]; int
0x18000ca36  lea     eax, [rsi-8]
0x18000ca39  mov     rdx, qword ptr [rsp+140h+var_D0]; int
0x18000ca3e  mov     rcx, qword ptr [rbp+40h+var_B8]; int
0x18000ca42  mov     [rsp+140h+var_110], 80h; int
0x18000ca4a  mov     dword ptr [rsp+140h+var_118], eax; Size
0x18000ca4e  mov     [rsp+140h+var_120], r9; Src
0x18000ca53  mov     r9d, [rbp+40h+arg_20]; int
0x18000ca57  call    MSCryptGenerateSymmetricKey
0x18000ca5c  mov     ebx, eax
0x18000ca5e  test    eax, eax
0x18000ca60  js      loc_18000CB6A
0x18000ca66  xor     ebx, ebx
0x18000ca68  jmp     short loc_18000CA92
0x18000ca6a  mov     [rsp+140h+var_110], 1DAh
0x18000ca72  mov     rcx, [rcx+10h]
0x18000ca76  lea     rax, aOnecoreDsSecur_26; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000ca7d  mov     [rsp+140h+var_118], rax
0x18000ca82  lea     r9, aStatus; "Status"
0x18000ca89  mov     dword ptr [rsp+140h+var_120], ebx
0x18000ca8d  call    WPP_SF_sDsd
0x18000ca92  test    rdi, rdi
0x18000ca95  jz      short loc_18000CAAA
0x18000ca97  mov     rax, rsi
0x18000ca9a  test    esi, esi
0x18000ca9c  jz      short loc_18000CAAA
0x18000ca9e  mov     byte ptr [rdi], 0
0x18000caa1  inc     rdi
0x18000caa4  sub     rax, 1
0x18000caa8  jnz     short loc_18000CA9E
0x18000caaa  test    r15, r15
0x18000caad  jnz     loc_18000CC12
0x18000cab3  mov     rcx, r14
0x18000cab6  lea     rax, [rbp+40h+var_B0]
0x18000caba  mov     byte ptr [rax], 0
0x18000cabd  inc     rax
0x18000cac0  sub     rcx, 1
0x18000cac4  jnz     short loc_18000CABA
0x18000cac6  lea     rax, [rsp+140h+var_C8]
0x18000cacb  mov     byte ptr [rax], 0
0x18000cace  inc     rax
0x18000cad1  sub     r14, 1
0x18000cad5  jnz     short loc_18000CACB
0x18000cad7  lea     ecx, [r14+8]
0x18000cadb  lea     rax, [rbp+40h+var_B8]
0x18000cadf  mov     byte ptr [rax], 0
0x18000cae2  inc     rax
0x18000cae5  sub     rcx, 1
0x18000cae9  jnz     short loc_18000CADF
0x18000caeb  mov     eax, ebx
0x18000caed  mov     rcx, [rbp+40h+var_50]
0x18000caf1  xor     rcx, rsp; StackCookie
0x18000caf4  call    __security_check_cookie
0x18000caf9  add     rsp, 108h
0x18000cb00  pop     r15
0x18000cb02  pop     r14
0x18000cb04  pop     r13
0x18000cb06  pop     r12
0x18000cb08  pop     rdi
0x18000cb09  pop     rsi
0x18000cb0a  pop     rbx
0x18000cb0b  pop     rbp
0x18000cb0c  retn
0x18000cb0e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cb15  lea     rax, WPP_GLOBAL_Control
0x18000cb1c  cmp     rcx, rax
0x18000cb1f  jz      short loc_18000CAB3
0x18000cb21  test    byte ptr [rcx+1Ch], 1
0x18000cb25  jz      short loc_18000CAB3
0x18000cb27  mov     [rsp+140h+var_110], 189h
0x18000cb2f  lea     rax, aOnecoreDsSecur_26; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000cb36  mov     [rsp+140h+var_118], rax
0x18000cb3b  mov     dword ptr [rsp+140h+var_120], ebx
0x18000cb3f  jmp     loc_180080019
0x18000cb44  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cb4b  lea     rax, WPP_GLOBAL_Control
0x18000cb52  cmp     rcx, rax
0x18000cb55  jz      loc_18000CA92
0x18000cb5b  test    byte ptr [rcx+1Ch], 1
0x18000cb5f  jz      loc_18000CA92
0x18000cb65  jmp     loc_18000CA6A
0x18000cb6a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cb71  lea     rax, WPP_GLOBAL_Control
0x18000cb78  cmp     rcx, rax
0x18000cb7b  jz      loc_18000CA92
0x18000cb81  test    byte ptr [rcx+1Ch], 1
0x18000cb85  jz      loc_18000CA92
0x18000cb8b  mov     [rsp+140h+var_110], 1F4h
0x18000cb93  jmp     loc_18000CA72
0x18000cb98  mov     ebx, 0C000A002h
0x18000cb9d  jmp     loc_18000CA92
0x18000cba2  mov     ebx, 0C0000008h
0x18000cba7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cbae  lea     rax, WPP_GLOBAL_Control
0x18000cbb5  cmp     rcx, rax
0x18000cbb8  jz      loc_18000CAB3
0x18000cbbe  test    byte ptr [rcx+1Ch], 1
0x18000cbc2  jz      loc_18000CAB3
0x18000cbc8  mov     [rsp+140h+var_110], 191h
0x18000cbd0  lea     rax, aOnecoreDsSecur_26; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000cbd7  mov     [rsp+140h+var_118], rax
0x18000cbdc  mov     dword ptr [rsp+140h+var_120], 0C0000008h
0x18000cbe4  jmp     loc_180080019
0x18000cbe9  mov     rcx, rbx
0x18000cbec  call    SafeAllocaAllocateFromHeap
0x18000cbf1  mov     r15, rax
0x18000cbf4  test    rax, rax
0x18000cbf7  jnz     loc_18007FFF8
0x18000cbfd  mov     ebx, 0C0000017h
0x18000cc02  mov     r9d, 1ADh
0x18000cc08  mov     ecx, 0C0000017h
0x18000cc0d  jmp     loc_180080000
0x18000cc12  mov     rcx, r15
0x18000cc15  call    MSCryptFree
0x18000cc1a  jmp     loc_18000CAB3
0x18000cc1f  mov     ebx, 0C000000Dh
0x18000cc24  mov     r9d, 199h
0x18000cc2a  mov     ecx, 0C000000Dh
0x18000cc2f  jmp     loc_180080000
0x18007fff8  mov     rdi, rax
0x18007fffb  jmp     loc_18000C92E
0x180080000  lea     rdx, aStatus; "Status"
0x180080007  lea     r8, aOnecoreDsSecur_26; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18008000e  call    DebugTraceError
0x180080013  nop
0x180080014  jmp     loc_18000CAB3
0x180080019  mov     rcx, [rcx+10h]
0x18008001d  lea     r9, aStatus; "Status"
0x180080024  call    WPP_SF_sDsd
0x180080029  nop
0x18008002a  jmp     loc_18000CAB3
```
