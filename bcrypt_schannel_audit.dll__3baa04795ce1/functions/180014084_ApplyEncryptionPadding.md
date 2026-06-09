# ApplyEncryptionPadding

- ea: `0x180014084`
- end: `0x18001430d`
- name: `ApplyEncryptionPadding`
- size: `649`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800049a0`

## callees

- `0x180005060`
- `0x180005280`
- `0x1800066f0`
- `0x180014084`
- `0x18001620c`
- `0x180016298`
- `0x180016564`
- `0x18001b79d`

## string_xrefs

- `0x180014199`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x1800141e3`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x1800142d9`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
__int64 __fastcall ApplyEncryptionPadding(char a1, __int64 a2, void *a3, unsigned int a4, __int64 a5, int a6)
{
  size_t v6; // r15
  BCRYPT_HANDLE v9; // rdi
  unsigned int v10; // eax
  __int64 v11; // r14
  ULONG v12; // r8d
  UCHAR *v13; // rdx
  NTSTATUS v14; // eax
  unsigned int v15; // ebx
  __int64 v16; // rcx
  ULONG i; // esi
  int v18; // eax
  NTSTATUS Property; // eax
  __int64 v20; // rcx
  void *dwFlags; // [rsp+28h] [rbp-40h]
  size_t Size; // [rsp+38h] [rbp-30h]
  UCHAR pbOutput[4]; // [rsp+50h] [rbp-18h] BYREF
  UCHAR v25[4]; // [rsp+54h] [rbp-14h] BYREF
  BCRYPT_HANDLE hObject[2]; // [rsp+58h] [rbp-10h] BYREF
  ULONG pcbResult; // [rsp+B0h] [rbp+48h] BYREF

  v6 = a4;
  hObject[0] = 0;
  *(_DWORD *)pbOutput = 0;
  *(_DWORD *)v25 = 0;
  v9 = 0;
  pcbResult = 0;
  if ( (a1 & 2) != 0 )
  {
    v10 = a4 + 3;
    if ( a4 + 3 < a4 || a6 < v10 )
    {
      v15 = -2147024362;
      pcbResult = -1;
      v16 = 2147942934LL;
      goto LABEL_15;
    }
    v11 = a5;
    v12 = a6 - v10;
    pcbResult = a6 - v10;
    v13 = (UCHAR *)(a5 + 2);
    *(_WORD *)a5 = 512;
    v14 = BCryptGenRandom(0, v13, v12, 2u);
    v15 = v14;
    if ( v14 < 0 )
    {
LABEL_5:
      v16 = (unsigned int)v14;
LABEL_15:
      DebugTraceError(v16, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c");
      return v15;
    }
    for ( i = 0; i < pcbResult; ++i )
    {
      while ( !*(_BYTE *)(i + 2 + v11) )
      {
        v14 = BCryptGenRandom(0, (PUCHAR)(v11 + i + 2LL), 1u, 2u);
        v15 = v14;
        if ( v14 < 0 )
          goto LABEL_5;
      }
    }
    *(_BYTE *)(pcbResult + 2 + v11) = 0;
    memcpy_0((void *)(v11 + pcbResult + 3LL), a3, v6);
    goto LABEL_13;
  }
  if ( (a1 & 4) != 0 )
  {
    if ( !a2 || !*(_QWORD *)a2 )
    {
      v15 = -1073741811;
      v16 = 3221225485LL;
      goto LABEL_15;
    }
    v18 = CachedOpenAlgorithmProvider(hObject);
    v15 = v18;
    if ( v18 < 0 )
    {
      DebugTraceError((unsigned int)v18, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c");
      v9 = hObject[0];
      goto LABEL_29;
    }
    v9 = hObject[0];
    Property = BCryptGetProperty(hObject[0], L"ObjectLength", pbOutput, 4u, &pcbResult, 0);
    v15 = Property;
    if ( Property >= 0 )
    {
      Property = BCryptGetProperty(v9, L"HashDigestLength", v25, 4u, &pcbResult, 0);
      v15 = Property;
      if ( Property >= 0 )
      {
        LODWORD(Size) = v6;
        Property = ApplyOAEPPaddingSeeded(
                     v9,
                     *(ULONG *)v25,
                     *(ULONG *)pbOutput,
                     *(_DWORD *)(a2 + 16),
                     dwFlags,
                     a3,
                     Size,
                     a5,
                     a6);
        v15 = Property;
        if ( Property >= 0 )
        {
LABEL_13:
          v15 = 0;
          goto LABEL_29;
        }
      }
    }
    v20 = (unsigned int)Property;
  }
  else
  {
    v15 = -1073741811;
    v20 = 3221225485LL;
  }
  DebugTraceError(v20, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c");
LABEL_29:
  if ( v9 )
    CachedCloseAlgorithmProvider(v9);
  return v15;
}

```

## disassembly

```asm
0x180014084  push    rbp
0x180014086  push    rbx
0x180014087  push    rsi
0x180014088  push    rdi
0x180014089  push    r12
0x18001408b  push    r13
0x18001408d  push    r14
0x18001408f  push    r15
0x180014091  mov     rbp, rsp
0x180014094  sub     rsp, 68h
0x180014098  xor     r12d, r12d
0x18001409b  mov     r15d, r9d
0x18001409e  mov     [rbp+hObject], r12
0x1800140a2  mov     r13, r8
0x1800140a5  mov     dword ptr [rbp+pbOutput], r12d
0x1800140a9  mov     rsi, rdx
0x1800140ac  mov     dword ptr [rbp+var_14], r12d
0x1800140b0  mov     edi, r12d
0x1800140b3  mov     [rbp+arg_0], r12d
0x1800140b7  test    cl, 2
0x1800140ba  jz      loc_1800141AA
0x1800140c0  lea     eax, [r15+3]
0x1800140c4  cmp     eax, r15d
0x1800140c7  jb      loc_18001417B
0x1800140cd  mov     r8d, [rbp+arg_28]
0x1800140d1  cmp     r8d, eax
0x1800140d4  jb      loc_180014173
0x1800140da  mov     r14, [rbp+arg_20]
0x1800140de  lea     r9d, [r12+2]; dwFlags
0x1800140e3  sub     r8d, eax; cbBuffer
0x1800140e6  xor     ecx, ecx; hAlgorithm
0x1800140e8  mov     [rbp+arg_0], r8d
0x1800140ec  lea     rdx, [r14+2]; pbBuffer
0x1800140f0  mov     word ptr [r14], 200h
0x1800140f6  call    BCryptGenRandom
0x1800140fb  mov     ebx, eax
0x1800140fd  test    eax, eax
0x1800140ff  jns     short loc_18001410E
0x180014101  mov     r9d, 0E4Bh
0x180014107  mov     ecx, eax
0x180014109  jmp     loc_180014192
0x18001410e  mov     esi, r12d
0x180014111  mov     eax, [rbp+arg_0]
0x180014114  cmp     esi, eax
0x180014116  jnb     short loc_18001414C
0x180014118  lea     r12d, [rsi+2]
0x18001411c  cmp     [r12+r14], dil
0x180014120  jnz     short loc_180014148
0x180014122  xor     ecx, ecx; hAlgorithm
0x180014124  mov     edx, esi
0x180014126  add     rdx, 2
0x18001412a  add     rdx, r14; pbBuffer
0x18001412d  lea     r9d, [rcx+2]; dwFlags
0x180014131  lea     r8d, [rcx+1]; cbBuffer
0x180014135  call    BCryptGenRandom
0x18001413a  mov     ebx, eax
0x18001413c  test    eax, eax
0x18001413e  jns     short loc_18001411C
0x180014140  mov     r9d, 0E59h
0x180014146  jmp     short loc_180014107
0x180014148  inc     esi
0x18001414a  jmp     short loc_180014111
0x18001414c  add     eax, 2
0x18001414f  xor     r12d, r12d
0x180014152  mov     r8, r15; Size
0x180014155  mov     rdx, r13; Src
0x180014158  mov     [rax+r14], r12b
0x18001415c  mov     ecx, [rbp+arg_0]
0x18001415f  add     rcx, 3
0x180014163  add     rcx, r14; void *
0x180014166  call    memcpy_0
0x18001416b  mov     ebx, r12d
0x18001416e  jmp     loc_1800142EC
0x180014173  mov     r9d, 0E3Eh
0x180014179  jmp     short loc_180014181
0x18001417b  mov     r9d, 0E39h
0x180014181  mov     ebx, 80070216h
0x180014186  mov     [rbp+arg_0], 0FFFFFFFFh
0x18001418d  mov     ecx, 80070216h
0x180014192  lea     rdx, aStatus; "Status"
0x180014199  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800141a0  call    DebugTraceError
0x1800141a5  jmp     loc_1800142F9
0x1800141aa  mov     r14d, 4
0x1800141b0  test    r14b, cl
0x1800141b3  jz      loc_1800142C9
0x1800141b9  test    rsi, rsi
0x1800141bc  jz      loc_1800142B4
0x1800141c2  mov     rdx, [rdx]
0x1800141c5  test    rdx, rdx
0x1800141c8  jz      loc_1800142B4
0x1800141ce  lea     rcx, [rbp+hObject]
0x1800141d2  call    CachedOpenAlgorithmProvider
0x1800141d7  mov     ebx, eax
0x1800141d9  test    eax, eax
0x1800141db  jns     short loc_180014201
0x1800141dd  mov     r9d, 0E75h
0x1800141e3  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800141ea  lea     rdx, aStatus; "Status"
0x1800141f1  mov     ecx, eax
0x1800141f3  call    DebugTraceError
0x1800141f8  mov     rdi, [rbp+hObject]
0x1800141fc  jmp     loc_1800142EC
0x180014201  mov     rdi, [rbp+hObject]
0x180014205  lea     rax, [rbp+arg_0]
0x180014209  mov     rcx, rdi; hObject
0x18001420c  mov     dword ptr [rsp+68h+dwFlags], r12d; dwFlags
0x180014211  mov     r9d, r14d; cbOutput
0x180014214  mov     [rsp+68h+pcbResult], rax; pcbResult
0x180014219  lea     r8, [rbp+pbOutput]; pbOutput
0x18001421d  lea     rdx, aObjectlength; "ObjectLength"
0x180014224  call    BCryptGetProperty
0x180014229  mov     ebx, eax
0x18001422b  test    eax, eax
0x18001422d  jns     short loc_18001423C
0x18001422f  mov     r9d, 0E81h
0x180014235  mov     ecx, eax
0x180014237  jmp     loc_1800142D9
0x18001423c  lea     rax, [rbp+arg_0]
0x180014240  mov     dword ptr [rsp+68h+dwFlags], r12d; phHash
0x180014245  mov     r9d, r14d; cbOutput
0x180014248  mov     [rsp+68h+pcbResult], rax; pcbResult
0x18001424d  lea     r8, [rbp+var_14]; pbOutput
0x180014251  mov     rcx, rdi; hObject
0x180014254  lea     rdx, aHashdigestleng; "HashDigestLength"
0x18001425b  call    BCryptGetProperty
0x180014260  mov     ebx, eax
0x180014262  test    eax, eax
0x180014264  jns     short loc_18001426E
0x180014266  mov     r9d, 0E8Dh
0x18001426c  jmp     short loc_180014235
0x18001426e  mov     eax, [rbp+arg_28]
0x180014271  mov     rcx, rdi; hAlgorithm
0x180014274  mov     r9, [rsi+8]
0x180014278  mov     r8d, dword ptr [rbp+pbOutput]; cbHashObject
0x18001427c  mov     edx, dword ptr [rbp+var_14]; cbBuffer
0x18001427f  mov     [rsp+68h+var_20], eax; int
0x180014283  mov     rax, [rbp+arg_20]
0x180014287  mov     [rsp+68h+var_28], rax; __int64
0x18001428c  mov     eax, [rsi+10h]
0x18001428f  mov     dword ptr [rsp+68h+Size], r15d; Size
0x180014294  mov     [rsp+68h+Src], r13; Src
0x180014299  mov     dword ptr [rsp+68h+pcbResult], eax; cbInput
0x18001429d  call    ApplyOAEPPaddingSeeded
0x1800142a2  mov     ebx, eax
0x1800142a4  test    eax, eax
0x1800142a6  jns     loc_18001416B
0x1800142ac  mov     r9d, 0E9Ch
0x1800142b2  jmp     short loc_180014235
0x1800142b4  mov     ebx, 0C000000Dh
0x1800142b9  mov     r9d, 0E6Ah
0x1800142bf  mov     ecx, 0C000000Dh
0x1800142c4  jmp     loc_180014192
0x1800142c9  mov     ebx, 0C000000Dh
0x1800142ce  mov     r9d, 0EA3h
0x1800142d4  mov     ecx, 0C000000Dh
0x1800142d9  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800142e0  lea     rdx, aStatus; "Status"
0x1800142e7  call    DebugTraceError
0x1800142ec  test    rdi, rdi
0x1800142ef  jz      short loc_1800142F9
0x1800142f1  mov     rcx, rdi; hAlgorithm
0x1800142f4  call    CachedCloseAlgorithmProvider
0x1800142f9  mov     eax, ebx
0x1800142fb  add     rsp, 68h
0x1800142ff  pop     r15
0x180014301  pop     r14
0x180014303  pop     r13
0x180014305  pop     r12
0x180014307  pop     rdi
0x180014308  pop     rsi
0x180014309  pop     rbx
0x18001430a  pop     rbp
0x18001430b  retn
```
