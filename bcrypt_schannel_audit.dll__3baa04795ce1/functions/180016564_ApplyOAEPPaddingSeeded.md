# ApplyOAEPPaddingSeeded

- ea: `0x180016564`
- end: `0x1800168c1`
- name: `ApplyOAEPPaddingSeeded`
- size: `861`
- prototype: `__int64 __usercall@<rax>(BCRYPT_ALG_HANDLE hAlgorithm@<rcx>, ULONG cbBuffer@<edx>, ULONG cbHashObject@<r8d>, ULONG cbInput, BCRYPT_HASH_HANDLE phHash, void *Src, size_t Size, __int64, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180014084`

## callees

- `0x180004200`
- `0x180005060`
- `0x180005280`
- `0x180006020`
- `0x180006da0`
- `0x1800078e0`
- `0x180009430`
- `0x18000cc10`
- `0x180012cc4`
- `0x180016564`
- `0x18001b79d`
- `0x18001b7a9`

## string_xrefs

- `0x180016874`: `onecore\ds\security\cryptoapi\ncrypt\common\format.c`

## pseudocode

```c
__int64 __fastcall ApplyOAEPPaddingSeeded(
        BCRYPT_ALG_HANDLE hAlgorithm,
        ULONG cbBuffer,
        ULONG cbHashObject,
        UCHAR *a4,
        ULONG cbInput,
        BCRYPT_HASH_HANDLE phHash,
        void *Src,
        size_t Size,
        _BYTE *a9,
        unsigned int a10)
{
  __int64 v10; // rdi
  UCHAR *v11; // r14
  __int64 v12; // rbp
  __int64 v14; // r13
  unsigned __int64 v15; // rax
  unsigned int v16; // edx
  unsigned int v17; // r15d
  unsigned int v18; // ebx
  __int64 v19; // rcx
  unsigned int v20; // r12d
  ULONG v21; // esi
  unsigned __int64 v22; // rcx
  unsigned int v23; // ecx
  int v24; // eax
  UCHAR *v25; // rax
  UCHAR *v26; // r13
  __int64 v27; // r15
  size_t v28; // r8
  const void *v29; // rdx
  _BYTE *v30; // r15
  __int64 v31; // r8
  __int64 v32; // rax
  char v33; // dl
  __int64 v34; // rdx
  __int64 v35; // rax
  __int64 dwFlags; // [rsp+30h] [rbp-68h]
  __int64 dwFlagsa; // [rsp+30h] [rbp-68h]
  UCHAR *pbBuffer; // [rsp+40h] [rbp-58h]
  UCHAR *v40; // [rsp+50h] [rbp-48h]
  unsigned int v42; // [rsp+A8h] [rbp+10h]

  v10 = cbBuffer;
  v11 = 0;
  v12 = cbHashObject;
  phHash = 0;
  v14 = cbBuffer;
  v15 = 2LL * cbBuffer;
  if ( v15 > 0xFFFFFFFF )
    goto LABEL_26;
  v16 = v15 + Size;
  if ( (int)v15 + (int)Size < (unsigned int)Size )
    goto LABEL_26;
  v42 = v16 + 2;
  if ( v16 >= 0xFFFFFFFE )
    goto LABEL_26;
  v17 = a10;
  if ( a10 < v16 + 2 )
  {
    v18 = -1073741811;
    v19 = 3221225485LL;
LABEL_27:
    DebugTraceError(v19, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\format.c");
    goto LABEL_28;
  }
  v20 = v10 + 1;
  if ( (_DWORD)v10 == -1
    || a10 < v20
    || (v21 = a10 - v20, v22 = 2LL * (a10 - v20), v22 > 0xFFFFFFFF)
    || (v23 = v15 + v22, v23 < (unsigned int)v15)
    || v23 + cbHashObject < cbHashObject )
  {
LABEL_26:
    v19 = 3221225621LL;
    v18 = -1073741675;
    goto LABEL_27;
  }
  v11 = (UCHAR *)SafeAllocaAllocateFromHeap(v23 + cbHashObject);
  if ( !v11 )
  {
    v18 = -1073741801;
    v19 = 3221225495LL;
    goto LABEL_27;
  }
  v24 = BCryptCreateHash(hAlgorithm, &phHash, v11, v12, 0, 0, 0);
  v18 = v24;
  if ( v24 < 0 )
    goto LABEL_14;
  if ( cbInput )
  {
    v24 = BCryptHashData(phHash, a4, cbInput, 0);
    v18 = v24;
    if ( v24 < 0 )
      goto LABEL_14;
  }
  pbBuffer = &v11[v12];
  v25 = &v11[v12 + v14];
  v26 = &v25[v14];
  v40 = v25;
  v24 = BCryptFinishHash(phHash, v26, v10, 0);
  v18 = v24;
  if ( v24 < 0 )
    goto LABEL_14;
  v27 = v17 - v42;
  memset_0(&v26[v10], 0, (unsigned int)v27);
  v28 = (unsigned int)Size;
  v29 = Src;
  v26[(unsigned int)(v27 + v10)] = 1;
  memcpy_0(&v26[v27 + 1 + v10], v29, v28);
  v24 = BCryptGenRandom(0, pbBuffer, v10, 2u);
  v18 = v24;
  if ( v24 < 0 )
    goto LABEL_14;
  LODWORD(dwFlags) = v21;
  v24 = MaskGeneration(hAlgorithm, v10, v12, pbBuffer, v10, &v26[v21], dwFlags);
  v18 = v24;
  if ( v24 < 0 )
    goto LABEL_14;
  v30 = a9;
  v31 = 0;
  for ( *a9 = 0; (unsigned int)v31 < v21; v30[v32] = v33 )
  {
    v32 = v20 + (unsigned int)v31;
    v33 = v26[v21 + v31] ^ v26[v31];
    v31 = (unsigned int)(v31 + 1);
  }
  LODWORD(dwFlagsa) = v10;
  v24 = MaskGeneration(hAlgorithm, v10, v12, &v30[v10 + 1], v21, v40, dwFlagsa);
  v18 = v24;
  if ( v24 < 0 )
  {
LABEL_14:
    v19 = (unsigned int)v24;
    goto LABEL_27;
  }
  LODWORD(v34) = 0;
  if ( (_DWORD)v10 )
  {
    do
    {
      v35 = (unsigned int)v34;
      v34 = (unsigned int)(v34 + 1);
      v30[v34] = pbBuffer[v35] ^ v40[v35];
    }
    while ( (unsigned int)v34 < (unsigned int)v10 );
  }
  v18 = 0;
LABEL_28:
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( v11 )
    MSCryptFree(v11);
  return v18;
}

```

## disassembly

```asm
0x180016564  mov     rax, rsp
0x180016567  mov     [rax+18h], rbx
0x18001656b  mov     [rax+20h], r9
0x18001656f  mov     [rax+8], rcx
0x180016573  push    rbp
0x180016574  push    rsi
0x180016575  push    rdi
0x180016576  push    r12
0x180016578  push    r13
0x18001657a  push    r14
0x18001657c  push    r15
0x18001657e  sub     rsp, 60h
0x180016582  mov     edi, edx
0x180016584  xor     r14d, r14d
0x180016587  mov     ebp, r8d
0x18001658a  mov     rbx, rcx
0x18001658d  mov     qword ptr [rax+30h], 0
0x180016595  mov     r8d, 0FFFFFFFFh
0x18001659b  mov     r13d, edx
0x18001659e  lea     rax, ds:0[rdi*2]
0x1800165a6  cmp     rax, r8
0x1800165a9  ja      loc_180016864
0x1800165af  mov     ecx, dword ptr [rsp+98h+Size]
0x1800165b6  lea     edx, [rax+rcx]
0x1800165b9  cmp     edx, ecx
0x1800165bb  jnb     short loc_1800165C8
0x1800165bd  mov     r9d, 1D2h
0x1800165c3  jmp     loc_18001686A
0x1800165c8  lea     ecx, [rdx+2]
0x1800165cb  mov     [rsp+98h+arg_8], ecx
0x1800165d2  cmp     ecx, 2
0x1800165d5  jnb     short loc_1800165E2
0x1800165d7  mov     r9d, 1D7h
0x1800165dd  jmp     loc_18001686A
0x1800165e2  mov     r15d, [rsp+98h+arg_48]
0x1800165ea  cmp     r15d, ecx
0x1800165ed  jnb     short loc_180016604
0x1800165ef  mov     ebx, 0C000000Dh
0x1800165f4  mov     r9d, 1DEh
0x1800165fa  mov     ecx, 0C000000Dh
0x1800165ff  jmp     loc_180016874
0x180016604  lea     r12d, [rdi+1]
0x180016608  cmp     r12d, 1
0x18001660c  jnb     short loc_180016619
0x18001660e  mov     r9d, 1E6h
0x180016614  jmp     loc_18001686A
0x180016619  cmp     r15d, r12d
0x18001661c  jb      loc_18001685C
0x180016622  mov     esi, r15d
0x180016625  sub     esi, r12d
0x180016628  mov     ecx, esi
0x18001662a  add     rcx, rcx
0x18001662d  cmp     rcx, r8
0x180016630  ja      loc_180016854
0x180016636  add     ecx, eax
0x180016638  cmp     ecx, eax
0x18001663a  jnb     short loc_180016647
0x18001663c  mov     r9d, 1FCh
0x180016642  jmp     loc_18001686A
0x180016647  lea     eax, [rcx+rbp]
0x18001664a  cmp     eax, ebp
0x18001664c  jnb     short loc_180016659
0x18001664e  mov     r9d, 201h
0x180016654  jmp     loc_18001686A
0x180016659  mov     ecx, eax
0x18001665b  call    SafeAllocaAllocateFromHeap
0x180016660  mov     r14, rax
0x180016663  xor     eax, eax
0x180016665  test    r14, r14
0x180016668  jnz     short loc_18001667F
0x18001666a  mov     ebx, 0C0000017h
0x18001666f  mov     r9d, 20Ah
0x180016675  mov     ecx, 0C0000017h
0x18001667a  jmp     loc_180016874
0x18001667f  mov     [rsp+98h+dwFlags], eax; dwFlags
0x180016683  lea     rdx, [rsp+98h+phHash]; phHash
0x18001668b  mov     [rsp+98h+cbSecret], eax; cbSecret
0x18001668f  mov     r9d, ebp; cbHashObject
0x180016692  mov     r8, r14; pbHashObject
0x180016695  mov     [rsp+98h+pbSecret], rax; pbSecret
0x18001669a  mov     rcx, rbx; hAlgorithm
0x18001669d  call    BCryptCreateHash
0x1800166a2  mov     ebx, eax
0x1800166a4  test    eax, eax
0x1800166a6  jns     short loc_1800166B5
0x1800166a8  mov     r9d, 21Dh
0x1800166ae  mov     ecx, eax
0x1800166b0  jmp     loc_180016874
0x1800166b5  mov     r8d, [rsp+98h+cbInput]; cbInput
0x1800166bd  test    r8d, r8d
0x1800166c0  jz      short loc_1800166E8
0x1800166c2  mov     rdx, [rsp+98h+pbInput]; pbInput
0x1800166ca  xor     r9d, r9d; dwFlags
0x1800166cd  mov     rcx, [rsp+98h+phHash]; hHash
0x1800166d5  call    BCryptHashData
0x1800166da  mov     ebx, eax
0x1800166dc  test    eax, eax
0x1800166de  jns     short loc_1800166E8
0x1800166e0  mov     r9d, 22Ah
0x1800166e6  jmp     short loc_1800166AE
0x1800166e8  mov     rcx, [rsp+98h+phHash]; hHash
0x1800166f0  lea     rax, [r14+rbp]
0x1800166f4  mov     [rsp+98h+pbBuffer], rax
0x1800166f9  xor     r9d, r9d; dwFlags
0x1800166fc  add     rax, r13
0x1800166ff  mov     r8d, edi; cbOutput
0x180016702  add     r13, rax
0x180016705  mov     [rsp+98h+var_48], rax
0x18001670a  mov     rdx, r13; pbOutput
0x18001670d  call    BCryptFinishHash
0x180016712  mov     ebx, eax
0x180016714  test    eax, eax
0x180016716  jns     short loc_180016720
0x180016718  mov     r9d, 235h
0x18001671e  jmp     short loc_1800166AE
0x180016720  sub     r15d, [rsp+98h+arg_8]
0x180016728  lea     rcx, [rdi+r13]; void *
0x18001672c  mov     r8d, r15d; Size
0x18001672f  xor     edx, edx; Val
0x180016731  call    memset_0
0x180016736  mov     r8d, dword ptr [rsp+98h+Size]; Size
0x18001673e  lea     eax, [r15+rdi]
0x180016742  mov     rdx, [rsp+98h+Src]; Src
0x18001674a  lea     rcx, [rdi+1]
0x18001674e  mov     byte ptr [rax+r13], 1
0x180016753  lea     rax, [r15+r13]
0x180016757  add     rcx, rax; void *
0x18001675a  call    memcpy_0
0x18001675f  mov     r15, [rsp+98h+pbBuffer]
0x180016764  mov     r9d, 2; dwFlags
0x18001676a  mov     rdx, r15; pbBuffer
0x18001676d  mov     r8d, edi; cbBuffer
0x180016770  xor     ecx, ecx; hAlgorithm
0x180016772  call    BCryptGenRandom
0x180016777  mov     ebx, eax
0x180016779  test    eax, eax
0x18001677b  jns     short loc_180016788
0x18001677d  mov     r9d, 245h
0x180016783  jmp     loc_1800166AE
0x180016788  mov     rcx, [rsp+98h+arg_0]
0x180016790  mov     r9, r15
0x180016793  mov     [rsp+98h+dwFlags], esi
0x180016797  mov     r8d, ebp
0x18001679a  mov     eax, esi
0x18001679c  mov     edx, edi
0x18001679e  add     rax, r13
0x1800167a1  mov     qword ptr [rsp+98h+cbSecret], rax
0x1800167a6  mov     dword ptr [rsp+98h+pbSecret], edi
0x1800167aa  mov     [rsp+98h+var_50], rax
0x1800167af  call    MaskGeneration
0x1800167b4  mov     ebx, eax
0x1800167b6  test    eax, eax
0x1800167b8  jns     short loc_1800167C5
0x1800167ba  mov     r9d, 258h
0x1800167c0  jmp     loc_1800166AE
0x1800167c5  mov     r15, [rsp+98h+arg_40]
0x1800167cd  xor     r8d, r8d
0x1800167d0  mov     byte ptr [r15], 0
0x1800167d4  test    esi, esi
0x1800167d6  jz      short loc_1800167F5
0x1800167d8  mov     r9, [rsp+98h+var_50]
0x1800167dd  mov     dl, [r8+r13]
0x1800167e1  lea     eax, [r12+r8]
0x1800167e5  xor     dl, [r8+r9]
0x1800167e9  inc     r8d
0x1800167ec  mov     [rax+r15], dl
0x1800167f0  cmp     r8d, esi
0x1800167f3  jb      short loc_1800167DD
0x1800167f5  mov     r12, [rsp+98h+var_48]
0x1800167fa  lea     r9, [r15+1]
0x1800167fe  mov     rcx, [rsp+98h+arg_0]
0x180016806  add     r9, rdi
0x180016809  mov     [rsp+98h+dwFlags], edi
0x18001680d  mov     r8d, ebp
0x180016810  mov     qword ptr [rsp+98h+cbSecret], r12
0x180016815  mov     edx, edi
0x180016817  mov     dword ptr [rsp+98h+pbSecret], esi
0x18001681b  call    MaskGeneration
0x180016820  mov     ebx, eax
0x180016822  test    eax, eax
0x180016824  jns     short loc_180016831
0x180016826  mov     r9d, 26Fh
0x18001682c  jmp     loc_1800166AE
0x180016831  xor     edx, edx
0x180016833  test    edi, edi
0x180016835  jz      short loc_180016850
0x180016837  mov     r8, [rsp+98h+pbBuffer]
0x18001683c  mov     eax, edx
0x18001683e  inc     edx
0x180016840  mov     cl, [rax+r12]
0x180016844  xor     cl, [rax+r8]
0x180016848  mov     [rdx+r15], cl
0x18001684c  cmp     edx, edi
0x18001684e  jb      short loc_18001683C
0x180016850  xor     ebx, ebx
0x180016852  jmp     short loc_180016887
0x180016854  mov     r9d, 1F2h
0x18001685a  jmp     short loc_18001686A
0x18001685c  mov     r9d, 1EBh
0x180016862  jmp     short loc_18001686A
0x180016864  mov     r9d, 1CDh
0x18001686a  mov     ecx, 0C0000095h
0x18001686f  mov     ebx, 0C0000095h
0x180016874  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001687b  lea     rdx, aStatus; "Status"
0x180016882  call    DebugTraceError
0x180016887  mov     rcx, [rsp+98h+phHash]; hHash
0x18001688f  test    rcx, rcx
0x180016892  jz      short loc_180016899
0x180016894  call    BCryptDestroyHash
0x180016899  test    r14, r14
0x18001689c  jz      short loc_1800168A6
0x18001689e  mov     rcx, r14
0x1800168a1  call    MSCryptFree
0x1800168a6  mov     eax, ebx
0x1800168a8  mov     rbx, [rsp+98h+arg_10]
0x1800168b0  add     rsp, 60h
0x1800168b4  pop     r15
0x1800168b6  pop     r14
0x1800168b8  pop     r13
0x1800168ba  pop     r12
0x1800168bc  pop     rdi
0x1800168bd  pop     rsi
0x1800168be  pop     rbp
0x1800168bf  retn
```
