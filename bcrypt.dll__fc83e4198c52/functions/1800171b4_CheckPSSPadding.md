# CheckPSSPadding

- ea: `0x1800171b4`
- end: `0x180017418`
- name: `CheckPSSPadding`
- size: `612`
- prototype: `__int64 __fastcall(void *, unsigned int, unsigned int, unsigned int, void *Src, unsigned int Size, PUCHAR pbHashObject, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180017420`

## callees

- `0x180004200`
- `0x180005060`
- `0x180006020`
- `0x180006da0`
- `0x1800078e0`
- `0x180009430`
- `0x18000cc10`
- `0x180012cc4`
- `0x1800171b4`
- `0x18001b791`
- `0x18001b79d`

## string_xrefs

- `0x1800173d5`: `onecore\ds\security\cryptoapi\ncrypt\common\format.c`

## pseudocode

```c
__int64 __fastcall CheckPSSPadding(
        void *a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        void *Src,
        unsigned int Size,
        PUCHAR pbHashObject,
        int a8)
{
  size_t v9; // r12
  __int64 v10; // r15
  size_t v11; // r14
  bool v12; // sf
  __int64 v13; // rdi
  __int64 v14; // rax
  __int64 v15; // rbp
  unsigned int v16; // ebx
  __int64 v17; // r13
  NTSTATUS v18; // eax
  __int64 v19; // r9
  __int64 v20; // rcx
  __int64 i; // rdx
  __int64 v22; // rcx
  int v23; // edi
  __int64 v24; // rdx
  UCHAR *v25; // r13
  UCHAR *v26; // rdi
  UCHAR *v27; // rdi
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-58h] BYREF
  __int64 v30; // [rsp+48h] [rbp-50h]

  v9 = a4;
  v10 = a3;
  v11 = a2;
  v12 = (*pbHashObject & 0x80u) != 0;
  phHash = 0;
  if ( v12 || pbHashObject[a8 - 1] != 0xBC )
  {
    v15 = 0;
    v19 = 1136;
    goto LABEL_27;
  }
  v13 = a8 - a2 - 1;
  v14 = SafeAllocaAllocateFromHeap(a3 + a8 - 1 + a4 + Size + 23);
  v15 = v14;
  if ( !v14 )
  {
    v16 = -1073741801;
    goto LABEL_29;
  }
  v17 = (unsigned int)v13;
  v30 = (unsigned int)v13;
  v18 = MaskGeneration(a1, (unsigned int)v11, (unsigned int)v10, &pbHashObject[v13], v11, v14, v13);
  v16 = v18;
  if ( v18 >= 0 )
  {
    for ( i = 0; (unsigned int)i < (unsigned int)v13; i = (unsigned int)(i + 1) )
      pbHashObject[i] ^= *(_BYTE *)(i + v15);
    *pbHashObject &= ~0x80u;
    v22 = 0;
    v23 = v13 - v9;
    v24 = (unsigned int)(v23 - 1);
    while ( (unsigned int)v22 < (unsigned int)v24 )
    {
      if ( pbHashObject[v22] )
      {
        v19 = 1191;
        goto LABEL_27;
      }
      v22 = (unsigned int)(v22 + 1);
    }
    if ( pbHashObject[v24] == 1 )
    {
      v25 = (UCHAR *)(v15 + v17);
      *(_QWORD *)v25 = 0;
      memcpy_0(v25 + 8, Src, Size);
      memcpy_0(&v25[Size + 8], &pbHashObject[v23], v9);
      v26 = (UCHAR *)((unsigned __int64)&v25[(unsigned int)v9 + 23 + Size] & 0xFFFFFFFFFFFFFFF0uLL);
      v18 = BCryptCreateHash(a1, &phHash, v26, v10, 0, 0, 0);
      v16 = v18;
      if ( v18 < 0 )
      {
        v19 = 1221;
        goto LABEL_7;
      }
      v18 = BCryptHashData(phHash, v25, v9 + Size + 8, 0);
      v16 = v18;
      if ( v18 < 0 )
      {
        v19 = 1231;
        goto LABEL_7;
      }
      v27 = &v26[v10];
      v18 = BCryptFinishHash(phHash, v27, v11, 0);
      v16 = v18;
      if ( v18 < 0 )
      {
        v19 = 1241;
        goto LABEL_7;
      }
      if ( !memcmp_0(&pbHashObject[v30], v27, v11) )
      {
        v16 = 0;
        goto LABEL_29;
      }
      v19 = 1250;
    }
    else
    {
      v19 = 1200;
    }
LABEL_27:
    v20 = 3221225485LL;
    v16 = -1073741811;
    goto LABEL_28;
  }
  v19 = 1172;
LABEL_7:
  v20 = (unsigned int)v18;
LABEL_28:
  DebugTraceError(v20, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\format.c", v19);
LABEL_29:
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( v15 )
    MSCryptFree(v15);
  return v16;
}

```

## disassembly

```asm
0x1800171b4  mov     [rsp+hAlgorithm], rcx
0x1800171b9  push    rbx
0x1800171ba  push    rbp
0x1800171bb  push    rsi
0x1800171bc  push    rdi
0x1800171bd  push    r12
0x1800171bf  push    r13
0x1800171c1  push    r14
0x1800171c3  push    r15
0x1800171c5  sub     rsp, 58h
0x1800171c9  mov     rsi, [rsp+98h+pbHashObject]
0x1800171d1  mov     rbx, rcx
0x1800171d4  mov     r12d, r9d
0x1800171d7  mov     r15d, r8d
0x1800171da  mov     r14d, edx
0x1800171dd  cmp     byte ptr [rsi], 0
0x1800171e0  mov     [rsp+98h+phHash], 0
0x1800171e9  jl      loc_1800173C3
0x1800171ef  mov     edi, [rsp+98h+arg_38]
0x1800171f6  lea     eax, [rdi-1]
0x1800171f9  cmp     byte ptr [rax+rsi], 0BCh
0x1800171fd  jnz     loc_1800173C3
0x180017203  mov     ecx, dword ptr [rsp+98h+Size]
0x18001720a  sub     edi, r14d
0x18001720d  add     ecx, 17h
0x180017210  dec     edi
0x180017212  add     ecx, r12d
0x180017215  add     ecx, edi
0x180017217  add     ecx, r14d
0x18001721a  add     ecx, r15d
0x18001721d  call    SafeAllocaAllocateFromHeap
0x180017222  mov     rbp, rax
0x180017225  test    rax, rax
0x180017228  jnz     short loc_180017234
0x18001722a  mov     ebx, 0C0000017h
0x18001722f  jmp     loc_1800173E8
0x180017234  mov     [rsp+98h+dwFlags], edi
0x180017238  lea     r9, [rsi+rdi]
0x18001723c  mov     r13d, edi
0x18001723f  mov     r8d, r15d
0x180017242  mov     qword ptr [rsp+98h+cbSecret], rbp
0x180017247  mov     edx, r14d
0x18001724a  mov     rcx, rbx
0x18001724d  mov     [rsp+98h+var_50], r13
0x180017252  mov     dword ptr [rsp+98h+pbSecret], r14d
0x180017257  call    MaskGeneration
0x18001725c  mov     ebx, eax
0x18001725e  test    eax, eax
0x180017260  jns     short loc_18001726F
0x180017262  mov     r9d, 494h
0x180017268  mov     ecx, eax
0x18001726a  jmp     loc_1800173D5
0x18001726f  xor     edx, edx
0x180017271  test    edi, edi
0x180017273  jz      short loc_180017281
0x180017275  mov     al, [rdx+rbp]
0x180017278  xor     [rdx+rsi], al
0x18001727b  inc     edx
0x18001727d  cmp     edx, edi
0x18001727f  jb      short loc_180017275
0x180017281  and     byte ptr [rsi], 7Fh
0x180017284  xor     ecx, ecx
0x180017286  sub     edi, r12d
0x180017289  lea     edx, [rdi-1]
0x18001728c  cmp     ecx, edx
0x18001728e  jnb     short loc_1800172A5
0x180017290  cmp     byte ptr [rcx+rsi], 0
0x180017294  jnz     short loc_18001729A
0x180017296  inc     ecx
0x180017298  jmp     short loc_18001728C
0x18001729a  mov     r9d, 4A7h
0x1800172a0  jmp     loc_1800173CB
0x1800172a5  cmp     byte ptr [rdx+rsi], 1
0x1800172a9  jz      short loc_1800172B6
0x1800172ab  mov     r9d, 4B0h
0x1800172b1  jmp     loc_1800173CB
0x1800172b6  mov     ecx, dword ptr [rsp+98h+Size]
0x1800172bd  add     r13, rbp
0x1800172c0  mov     rdx, [rsp+98h+Src]; Src
0x1800172c8  mov     ebx, ecx
0x1800172ca  mov     r8d, ebx; Size
0x1800172cd  lea     eax, [rcx+8]
0x1800172d0  add     eax, r12d
0x1800172d3  lea     rcx, [r13+8]; void *
0x1800172d7  add     rax, 0Fh
0x1800172db  add     rax, r13
0x1800172de  and     rax, 0FFFFFFFFFFFFFFF0h
0x1800172e2  mov     [rsp+98h+pbHashObject], rax
0x1800172ea  xor     eax, eax
0x1800172ec  mov     [r13+0], rax
0x1800172f0  call    memcpy_0
0x1800172f5  mov     edx, edi
0x1800172f7  lea     rcx, [rbx+8]
0x1800172fb  add     rdx, rsi; Src
0x1800172fe  add     rcx, r13; void *
0x180017301  mov     r8, r12; Size
0x180017304  call    memcpy_0
0x180017309  mov     rdi, [rsp+98h+pbHashObject]
0x180017311  lea     rdx, [rsp+98h+phHash]; phHash
0x180017316  mov     rcx, [rsp+98h+hAlgorithm]; hAlgorithm
0x18001731e  xor     eax, eax
0x180017320  mov     [rsp+98h+dwFlags], eax; dwFlags
0x180017324  mov     r9d, r15d; cbHashObject
0x180017327  mov     [rsp+98h+cbSecret], eax; cbSecret
0x18001732b  mov     r8, rdi; pbHashObject
0x18001732e  mov     [rsp+98h+pbSecret], rax; pbSecret
0x180017333  call    BCryptCreateHash
0x180017338  mov     ebx, eax
0x18001733a  test    eax, eax
0x18001733c  jns     short loc_180017349
0x18001733e  mov     r9d, 4C5h
0x180017344  jmp     loc_180017268
0x180017349  mov     r8d, dword ptr [rsp+98h+Size]
0x180017351  xor     r9d, r9d; dwFlags
0x180017354  mov     rcx, [rsp+98h+phHash]; hHash
0x180017359  add     r8d, 8
0x18001735d  add     r8d, r12d; cbInput
0x180017360  mov     rdx, r13; pbInput
0x180017363  call    BCryptHashData
0x180017368  mov     ebx, eax
0x18001736a  test    eax, eax
0x18001736c  jns     short loc_180017379
0x18001736e  mov     r9d, 4CFh
0x180017374  jmp     loc_180017268
0x180017379  mov     rcx, [rsp+98h+phHash]; hHash
0x18001737e  add     rdi, r15
0x180017381  mov     rdx, rdi; pbOutput
0x180017384  xor     r9d, r9d; dwFlags
0x180017387  mov     r8d, r14d; cbOutput
0x18001738a  call    BCryptFinishHash
0x18001738f  mov     ebx, eax
0x180017391  test    eax, eax
0x180017393  jns     short loc_1800173A0
0x180017395  mov     r9d, 4D9h
0x18001739b  jmp     loc_180017268
0x1800173a0  mov     rcx, [rsp+98h+var_50]
0x1800173a5  mov     r8, r14; Size
0x1800173a8  add     rcx, rsi; Buf1
0x1800173ab  mov     rdx, rdi; Buf2
0x1800173ae  call    memcmp_0
0x1800173b3  test    eax, eax
0x1800173b5  jz      short loc_1800173BF
0x1800173b7  mov     r9d, 4E2h
0x1800173bd  jmp     short loc_1800173CB
0x1800173bf  xor     ebx, ebx
0x1800173c1  jmp     short loc_1800173E8
0x1800173c3  xor     ebp, ebp
0x1800173c5  mov     r9d, 470h
0x1800173cb  mov     ecx, 0C000000Dh
0x1800173d0  mov     ebx, 0C000000Dh
0x1800173d5  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800173dc  lea     rdx, aStatus; "Status"
0x1800173e3  call    DebugTraceError
0x1800173e8  mov     rcx, [rsp+98h+phHash]; hHash
0x1800173ed  test    rcx, rcx
0x1800173f0  jz      short loc_1800173F7
0x1800173f2  call    BCryptDestroyHash
0x1800173f7  test    rbp, rbp
0x1800173fa  jz      short loc_180017404
0x1800173fc  mov     rcx, rbp
0x1800173ff  call    MSCryptFree
0x180017404  mov     eax, ebx
0x180017406  add     rsp, 58h
0x18001740a  pop     r15
0x18001740c  pop     r14
0x18001740e  pop     r13
0x180017410  pop     r12
0x180017412  pop     rdi
0x180017413  pop     rsi
0x180017414  pop     rbp
0x180017415  pop     rbx
0x180017416  retn
```
