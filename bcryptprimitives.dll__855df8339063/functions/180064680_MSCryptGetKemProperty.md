# MSCryptGetKemProperty

- ea: `0x180064680`
- end: `0x1800648e5`
- name: `MSCryptGetKemProperty`
- size: `613`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18000ecb0`
- `0x180063170`
- `0x180064680`
- `0x180065430`
- `0x1800654e0`
- `0x18007f765`

## string_xrefs

- `0x180064762`: `Composite-ML-KEM`
- `0x1800648c0`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\kem.c`

## pseudocode

```c
__int64 __fastcall MSCryptGetKemProperty(
        __int64 a1,
        const wchar_t *a2,
        void *a3,
        unsigned int a4,
        unsigned int *a5,
        int a6)
{
  __int64 v10; // r9
  unsigned int v11; // ebx
  __int64 v12; // rcx
  int v13; // eax
  int *v14; // rdx
  unsigned int v15; // eax
  __int64 v16; // rdi
  int v18; // [rsp+20h] [rbp-20h] BYREF
  int v19; // [rsp+24h] [rbp-1Ch] BYREF
  __int64 v20; // [rsp+28h] [rbp-18h] BYREF
  __int64 v21; // [rsp+30h] [rbp-10h] BYREF

  v20 = 0;
  v21 = 0;
  v18 = 0;
  v19 = 0;
  if ( !a5 )
  {
    v10 = 866;
LABEL_3:
    v11 = -1073741811;
    v12 = 3221225485LL;
LABEL_47:
    DebugTraceError(v12, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\kem.c", v10);
    return v11;
  }
  *a5 = 0;
  if ( !a2 )
  {
    v10 = 875;
    goto LABEL_3;
  }
  if ( !a3 )
  {
    if ( !a4 )
      goto LABEL_8;
LABEL_11:
    v10 = 883;
    goto LABEL_3;
  }
  if ( !a4 )
    goto LABEL_11;
LABEL_8:
  if ( a6 )
  {
    v10 = 890;
    goto LABEL_3;
  }
  v13 = ValidateKemObject(a1, &v20);
  v11 = v13;
  if ( v13 < 0 )
  {
    v10 = 897;
LABEL_14:
    v12 = (unsigned int)v13;
    goto LABEL_47;
  }
  if ( wcscmp_0(a2, L"AlgorithmName") )
  {
    if ( !wcscmp_0(a2, L"KEMSharedSecretLength") )
    {
      if ( *(_DWORD *)(v20 + 8) != 458753 && *(_DWORD *)(v20 + 8) != 458754 )
      {
        v10 = 942;
        goto LABEL_46;
      }
      v18 = 32;
      v14 = &v18;
    }
    else
    {
      if ( *(_DWORD *)(v20 + 4) != 1297302859 )
      {
        v10 = 995;
        goto LABEL_46;
      }
      v13 = ValidateKemKey(a1, &v21, 1);
      v11 = v13;
      if ( v13 < 0 )
      {
        v10 = 957;
        goto LABEL_14;
      }
      if ( *(_DWORD *)(v21 + 8) != 458753 && *(_DWORD *)(v21 + 8) != 458754 || (v16 = *(_QWORD *)(v21 + 24)) == 0 )
      {
        v10 = 965;
        goto LABEL_46;
      }
      if ( !wcscmp_0(a2, L"PublicKeyLength") )
      {
        v14 = &v19;
        v19 = 8 * *(_DWORD *)(v16 + 12);
      }
      else
      {
        if ( wcscmp_0(a2, L"KEMCiphertextLength") )
        {
          if ( wcscmp_0(a2, L"ParameterSetName") )
          {
            v10 = 988;
            goto LABEL_46;
          }
          v14 = *(int **)v16;
          v15 = *(_DWORD *)(v16 + 8);
          goto LABEL_40;
        }
        v14 = (int *)(v16 + 20);
      }
    }
    v15 = 4;
    goto LABEL_40;
  }
  if ( *(_DWORD *)(v20 + 8) == 458753 )
  {
    v14 = (int *)L"ML-KEM";
    v15 = 14;
  }
  else
  {
    if ( *(_DWORD *)(v20 + 8) != 458754 )
    {
      v10 = 920;
LABEL_46:
      v11 = -1073741637;
      v12 = 3221225659LL;
      goto LABEL_47;
    }
    v14 = (int *)L"Composite-ML-KEM";
    v15 = 34;
  }
LABEL_40:
  *a5 = v15;
  if ( a3 )
  {
    if ( a4 < v15 )
    {
      v11 = -1073741789;
      v10 = 1010;
      v12 = 3221225507LL;
      goto LABEL_47;
    }
    memcpy_0(a3, v14, v15);
  }
  return v11;
}

```

## disassembly

```asm
0x180064680  push    rbp
0x180064682  push    rbx
0x180064683  push    rsi
0x180064684  push    rdi
0x180064685  push    r12
0x180064687  push    r14
0x180064689  push    r15
0x18006468b  mov     rbp, rsp
0x18006468e  sub     rsp, 40h
0x180064692  mov     r12, [rbp+arg_20]
0x180064696  mov     r14d, r9d
0x180064699  mov     [rbp+var_18], 0
0x1800646a1  mov     r15, r8
0x1800646a4  mov     [rbp+var_10], 0
0x1800646ac  mov     rsi, rdx
0x1800646af  mov     [rbp+var_20], 0
0x1800646b6  mov     rdi, rcx
0x1800646b9  mov     [rbp+var_1C], 0
0x1800646c0  test    r12, r12
0x1800646c3  jnz     short loc_1800646DA
0x1800646c5  mov     r9d, 362h
0x1800646cb  mov     ebx, 0C000000Dh
0x1800646d0  mov     ecx, 0C000000Dh
0x1800646d5  jmp     loc_1800648C0
0x1800646da  mov     dword ptr [r12], 0
0x1800646e2  test    rsi, rsi
0x1800646e5  jnz     short loc_1800646EF
0x1800646e7  mov     r9d, 36Bh
0x1800646ed  jmp     short loc_1800646CB
0x1800646ef  test    r15, r15
0x1800646f2  jnz     short loc_180064707
0x1800646f4  test    r14d, r14d
0x1800646f7  jnz     short loc_18006470C
0x1800646f9  cmp     [rbp+arg_28], 0
0x1800646fd  jz      short loc_180064714
0x1800646ff  mov     r9d, 37Ah
0x180064705  jmp     short loc_1800646CB
0x180064707  test    r14d, r14d
0x18006470a  jnz     short loc_1800646F9
0x18006470c  mov     r9d, 373h
0x180064712  jmp     short loc_1800646CB
0x180064714  lea     rdx, [rbp+var_18]
0x180064718  call    ValidateKemObject
0x18006471d  mov     ebx, eax
0x18006471f  test    eax, eax
0x180064721  jns     short loc_180064730
0x180064723  mov     r9d, 381h
0x180064729  mov     ecx, eax
0x18006472b  jmp     loc_1800648C0
0x180064730  lea     rdx, aAlgorithmname; "AlgorithmName"
0x180064737  mov     rcx, rsi; String1
0x18006473a  call    wcscmp_0
0x18006473f  test    eax, eax
0x180064741  jnz     short loc_180064784
0x180064743  mov     rcx, [rbp+var_18]
0x180064747  mov     edx, [rcx+8]
0x18006474a  sub     edx, 70001h
0x180064750  jz      short loc_180064773
0x180064752  cmp     edx, 1
0x180064755  jz      short loc_180064762
0x180064757  mov     r9d, 398h
0x18006475d  jmp     loc_1800648B6
0x180064762  lea     rdx, aCompositeMlKem; "Composite-ML-KEM"
0x180064769  mov     eax, 22h ; '"'
0x18006476e  jmp     loc_18006487B
0x180064773  lea     rdx, aMlKem; "ML-KEM"
0x18006477a  mov     eax, 0Eh
0x18006477f  jmp     loc_18006487B
0x180064784  lea     rdx, aKemsharedsecre; "KEMSharedSecretLength"
0x18006478b  mov     rcx, rsi; String1
0x18006478e  call    wcscmp_0
0x180064793  test    eax, eax
0x180064795  jnz     short loc_1800647C6
0x180064797  mov     rcx, [rbp+var_18]
0x18006479b  mov     edx, [rcx+8]
0x18006479e  sub     edx, 70001h
0x1800647a4  jz      short loc_1800647B6
0x1800647a6  cmp     edx, 1
0x1800647a9  jz      short loc_1800647B6
0x1800647ab  mov     r9d, 3AEh
0x1800647b1  jmp     loc_1800648B6
0x1800647b6  mov     [rbp+var_20], 20h ; ' '
0x1800647bd  lea     rdx, [rbp+var_20]
0x1800647c1  jmp     loc_18006485B
0x1800647c6  mov     rax, [rbp+var_18]
0x1800647ca  cmp     dword ptr [rax+4], 4D53454Bh
0x1800647d1  jnz     loc_1800648B0
0x1800647d7  mov     r8d, 1
0x1800647dd  lea     rdx, [rbp+var_10]
0x1800647e1  mov     rcx, rdi
0x1800647e4  call    ValidateKemKey
0x1800647e9  mov     ebx, eax
0x1800647eb  test    eax, eax
0x1800647ed  jns     short loc_1800647FA
0x1800647ef  mov     r9d, 3BDh
0x1800647f5  jmp     loc_180064729
0x1800647fa  mov     rdi, [rbp+var_10]
0x1800647fe  mov     ecx, [rdi+8]
0x180064801  sub     ecx, 70001h
0x180064807  jz      short loc_18006480E
0x180064809  cmp     ecx, 1
0x18006480c  jnz     short loc_180064817
0x18006480e  mov     rdi, [rdi+18h]
0x180064812  test    rdi, rdi
0x180064815  jnz     short loc_180064822
0x180064817  mov     r9d, 3C5h
0x18006481d  jmp     loc_1800648B6
0x180064822  lea     rdx, aPublickeylengt; "PublicKeyLength"
0x180064829  mov     rcx, rsi; String1
0x18006482c  call    wcscmp_0
0x180064831  test    eax, eax
0x180064833  jnz     short loc_180064844
0x180064835  mov     eax, [rdi+0Ch]
0x180064838  lea     rdx, [rbp+var_1C]
0x18006483c  shl     eax, 3
0x18006483f  mov     [rbp+var_1C], eax
0x180064842  jmp     short loc_18006485B
0x180064844  lea     rdx, aKemciphertextl; "KEMCiphertextLength"
0x18006484b  mov     rcx, rsi; String1
0x18006484e  call    wcscmp_0
0x180064853  test    eax, eax
0x180064855  jnz     short loc_180064862
0x180064857  lea     rdx, [rdi+14h]
0x18006485b  mov     eax, 4
0x180064860  jmp     short loc_18006487B
0x180064862  lea     rdx, aParametersetna; "ParameterSetName"
0x180064869  mov     rcx, rsi; String1
0x18006486c  call    wcscmp_0
0x180064871  test    eax, eax
0x180064873  jnz     short loc_1800648A8
0x180064875  mov     rdx, [rdi]; Src
0x180064878  mov     eax, [rdi+8]
0x18006487b  mov     [r12], eax
0x18006487f  test    r15, r15
0x180064882  jz      short loc_1800648D3
0x180064884  cmp     r14d, eax
0x180064887  jnb     short loc_18006489B
0x180064889  mov     ebx, 0C0000023h
0x18006488e  mov     r9d, 3F2h
0x180064894  mov     ecx, 0C0000023h
0x180064899  jmp     short loc_1800648C0
0x18006489b  mov     r8d, eax; Size
0x18006489e  mov     rcx, r15; void *
0x1800648a1  call    memcpy_0
0x1800648a6  jmp     short loc_1800648D3
0x1800648a8  mov     r9d, 3DCh
0x1800648ae  jmp     short loc_1800648B6
0x1800648b0  mov     r9d, 3E3h
0x1800648b6  mov     ebx, 0C00000BBh
0x1800648bb  mov     ecx, 0C00000BBh
0x1800648c0  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800648c7  lea     rdx, aStatus; "Status"
0x1800648ce  call    DebugTraceError
0x1800648d3  mov     eax, ebx
0x1800648d5  add     rsp, 40h
0x1800648d9  pop     r15
0x1800648db  pop     r14
0x1800648dd  pop     r12
0x1800648df  pop     rdi
0x1800648e0  pop     rsi
0x1800648e1  pop     rbx
0x1800648e2  pop     rbp
0x1800648e3  retn
```
