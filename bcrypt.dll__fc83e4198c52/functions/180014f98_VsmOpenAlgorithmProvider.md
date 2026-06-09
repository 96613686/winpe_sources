# VsmOpenAlgorithmProvider

- ea: `0x180014f98`
- end: `0x180015359`
- name: `VsmOpenAlgorithmProvider`
- size: `961`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800070d0`

## callees

- `0x180004200`
- `0x180005060`
- `0x180009430`
- `0x18000d030`
- `0x180014f98`
- `0x18001a61c`
- `0x18001b791`
- `0x18001b7a9`
- `0x18001c010`

## import_xrefs

- `ntdll!wcsncpy_s` at `0x1800150d2`
- `ntdll!wcsncpy_s` at `0x1800150d2`

## string_xrefs

- `0x1800152bd`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180015328`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
__int64 __fastcall VsmOpenAlgorithmProvider(_QWORD *a1, const wchar_t *a2, const void *a3, unsigned int a4)
{
  unsigned int v6; // ebx
  __int64 v7; // r9
  __int64 v8; // rcx
  unsigned int i; // ecx
  __int64 v10; // r15
  wchar_t *v11; // rax
  signed __int64 v12; // r9
  int v13; // r8d
  int v14; // edx
  int v15; // esi
  char *v16; // rax
  char *v17; // rdi
  _OWORD *v18; // r14
  int Interface; // eax
  __int64 v20; // r9
  __int64 v21; // rax
  _OWORD *v22; // rcx
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  __int128 v26; // xmm0
  __int128 v27; // xmm1
  __int128 v28; // xmm0
  __int128 v29; // xmm1
  _QWORD *v30; // r14
  __int64 v31; // rcx
  wchar_t *v32; // rdx
  __int64 (__fastcall *v34)(char *, const wchar_t *, _QWORD); // [rsp+40h] [rbp-C0h] BYREF
  int v35; // [rsp+48h] [rbp-B8h] BYREF
  __int64 (__fastcall *v36)(_QWORD, const wchar_t *, char *, __int64, int *, _DWORD); // [rsp+50h] [rbp-B0h] BYREF
  void (__fastcall *v37)(_QWORD, wchar_t *, __int64 *, _QWORD, _DWORD); // [rsp+58h] [rbp-A8h] BYREF
  __int64 v38; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v39[448]; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v41; // [rsp+250h] [rbp+150h] BYREF

  v41 = 4;
  v34 = 0;
  v38 = 0;
  v37 = 0;
  v36 = 0;
  v35 = 0;
  if ( !a3 || !memcmp_0(a3, L"Microsoft Primitive Provider", 0x3Au) )
  {
    for ( i = 0; i < 0x35; ++i )
    {
      v10 = 4LL * i;
      v11 = (&AlgorithmClassPropertyTable)[v10];
      v12 = (char *)a2 - (char *)v11;
      do
      {
        v13 = *(wchar_t *)((char *)v11 + v12);
        v14 = *v11 - v13;
        if ( v14 )
          break;
        ++v11;
      }
      while ( v13 );
      if ( !v14 )
      {
        v15 = *((_DWORD *)&AlgorithmClassPropertyTable + 2 * v10 + 2);
        if ( (unsigned int)(v15 - 1) > 7 )
        {
          v7 = 1677;
          goto LABEL_41;
        }
        v16 = (char *)SafeAllocaAllocateFromHeap(968);
        v17 = v16;
        if ( !v16 )
        {
          v6 = -1073741801;
          v7 = 1691;
          v8 = 3221225495LL;
          goto LABEL_42;
        }
        memset_0(v16, 0, 0x3C8u);
        *(_DWORD *)v17 = 968;
        *((_DWORD *)v17 + 1) = 1431655761;
        *((_DWORD *)v17 + 4) = 1;
        *((_DWORD *)v17 + 9) = v15;
        wcsncpy_s((wchar_t *)v17 + 222, 0x104u, a2, 0xFFFFFFFFFFFFFFFFuLL);
        v18 = v17 + 48;
        *((_DWORD *)v17 + 8) = a4 & 1;
        Interface = VsmLoadInterface(*((unsigned int *)v17 + 9), a2, a4, v17 + 48);
        v6 = Interface;
        if ( Interface < 0 )
        {
          v20 = 1722;
          goto LABEL_35;
        }
        v21 = 3;
        v22 = v39;
        do
        {
          v23 = v18[1];
          *v22 = *v18;
          v24 = v18[2];
          v22[1] = v23;
          v25 = v18[3];
          v22[2] = v24;
          v26 = v18[4];
          v22[3] = v25;
          v27 = v18[5];
          v22[4] = v26;
          v28 = v18[6];
          v22[5] = v27;
          v29 = v18[7];
          v18 += 8;
          v22[6] = v28;
          v22[7] = v29;
          v22 += 8;
          --v21;
        }
        while ( v21 );
        *(_QWORD *)v22 = *(_QWORD *)v18;
        Interface = ValidateFunctionTable(
                      v15,
                      (unsigned int)v39,
                      (unsigned int)&v34,
                      (unsigned int)&v38,
                      (__int64)&v37,
                      (__int64)&v36);
        v6 = Interface;
        if ( Interface < 0 )
        {
          v20 = 1731;
          goto LABEL_35;
        }
        v30 = v17 + 24;
        v6 = v34(v17 + 24, a2, a4);
        if ( v6 == -1073700863 )
        {
          if ( v15 == 2 )
          {
            if ( (a4 & 0x28) == 8 )
            {
              v34(v17 + 24, a2, a4 & 0xFFFFFFF7);
              *((_DWORD *)v17 + 2) |= 8u;
            }
LABEL_26:
            if ( !v36 )
            {
              v6 = -1073741595;
              v31 = 3221225701LL;
              v20 = 1769;
LABEL_36:
              DebugTraceError(v31, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v20);
              MSCryptFree(v17);
              return v6;
            }
            Interface = v36(*v30, L"HashBlockLength", v17 + 12, 4, &v35, 0);
            v6 = Interface;
            if ( Interface < 0 )
            {
              v20 = 1781;
LABEL_35:
              v31 = (unsigned int)Interface;
              goto LABEL_36;
            }
LABEL_37:
            v32 = (&AlgorithmClassPropertyTable)[v10 + 1];
            if ( v32 )
              v37(*v30, v32, &qword_18001D1C8[v10], *((unsigned int *)&AlgorithmClassPropertyTable + 2 * v10 + 7), 0);
            *a1 = v17;
            return v6;
          }
        }
        else if ( v15 == 2 )
        {
          goto LABEL_26;
        }
        if ( v15 == 3 )
        {
          if ( !v36 )
          {
            v6 = -1073741595;
            v31 = 3221225701LL;
            v20 = 1790;
            goto LABEL_36;
          }
          Interface = v36(*v30, L"PaddingSchemes", v17 + 440, v41, (int *)&v41, 0);
          v6 = Interface;
          if ( Interface < 0 )
          {
            v20 = 1802;
            goto LABEL_35;
          }
        }
        goto LABEL_37;
      }
    }
    v7 = 1668;
LABEL_41:
    v8 = 3221225480LL;
    v6 = -1073741816;
  }
  else
  {
    v6 = -1073741811;
    v7 = 1660;
    v8 = 3221225485LL;
  }
LABEL_42:
  DebugTraceError(v8, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v7);
  return v6;
}

```

## disassembly

```asm
0x180014f98  mov     [rsp-8+arg_8], rbx
0x180014f9d  mov     [rsp-8+arg_0], rcx
0x180014fa2  push    rbp
0x180014fa3  push    rsi
0x180014fa4  push    rdi
0x180014fa5  push    r12
0x180014fa7  push    r13
0x180014fa9  push    r14
0x180014fab  push    r15
0x180014fad  lea     rbp, [rsp-100h]
0x180014fb5  sub     rsp, 200h
0x180014fbc  xor     ebx, ebx
0x180014fbe  mov     [rbp+130h+arg_10], 4
0x180014fc8  mov     [rsp+230h+var_1F0], rbx
0x180014fcd  mov     r12d, r9d
0x180014fd0  mov     [rsp+230h+var_1D0], rbx
0x180014fd5  mov     rax, r8
0x180014fd8  mov     [rsp+230h+var_1D8], rbx
0x180014fdd  mov     r13, rdx
0x180014fe0  mov     [rsp+230h+var_1E0], rbx
0x180014fe5  mov     [rsp+230h+var_1E8], ebx
0x180014fe9  test    r8, r8
0x180014fec  jz      short loc_18001501A
0x180014fee  lea     r8d, [rbx+3Ah]; Size
0x180014ff2  mov     rcx, rax; Buf1
0x180014ff5  lea     rdx, pszProvider; "Microsoft Primitive Provider"
0x180014ffc  call    memcmp_0
0x180015001  test    eax, eax
0x180015003  jz      short loc_18001501A
0x180015005  mov     ebx, 0C000000Dh
0x18001500a  mov     r9d, 67Ch
0x180015010  mov     ecx, 0C000000Dh
0x180015015  jmp     loc_180015328
0x18001501a  mov     ecx, ebx
0x18001501c  lea     r10, AlgorithmClassPropertyTable
0x180015023  cmp     ecx, 35h ; '5'
0x180015026  jnb     loc_180015318
0x18001502c  mov     r15d, ecx
0x18001502f  mov     r9, r13
0x180015032  shl     r15, 5
0x180015036  mov     rax, [r15+r10]
0x18001503a  sub     r9, rax
0x18001503d  movzx   edx, word ptr [rax]
0x180015040  movzx   r8d, word ptr [rax+r9]
0x180015045  sub     edx, r8d
0x180015048  jnz     short loc_180015053
0x18001504a  add     rax, 2
0x18001504e  test    r8d, r8d
0x180015051  jnz     short loc_18001503D
0x180015053  test    edx, edx
0x180015055  jz      short loc_18001505B
0x180015057  inc     ecx
0x180015059  jmp     short loc_180015023
0x18001505b  mov     esi, [r15+r10+8]
0x180015060  lea     eax, [rsi-1]
0x180015063  cmp     eax, 7
0x180015066  jbe     short loc_180015073
0x180015068  mov     r9d, 68Dh
0x18001506e  jmp     loc_18001531E
0x180015073  mov     r14d, 3C8h
0x180015079  mov     ecx, r14d
0x18001507c  call    SafeAllocaAllocateFromHeap
0x180015081  mov     rdi, rax
0x180015084  test    rax, rax
0x180015087  jnz     short loc_18001509E
0x180015089  mov     ebx, 0C0000017h
0x18001508e  mov     r9d, 69Bh
0x180015094  mov     ecx, 0C0000017h
0x180015099  jmp     loc_180015328
0x18001509e  mov     r8, r14; Size
0x1800150a1  xor     edx, edx; Val
0x1800150a3  mov     rcx, rdi; void *
0x1800150a6  call    memset_0
0x1800150ab  lea     rcx, [rdi+1BCh]; Destination
0x1800150b2  mov     [rdi], r14d
0x1800150b5  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1800150b9  mov     dword ptr [rdi+4], 55555551h
0x1800150c0  mov     r8, r13; Source
0x1800150c3  mov     dword ptr [rdi+10h], 1
0x1800150ca  mov     edx, 104h; SizeInWords
0x1800150cf  mov     [rdi+24h], esi
0x1800150d2  call    cs:__imp_wcsncpy_s
0x1800150d9  nop     dword ptr [rax+rax+00h]
0x1800150de  mov     eax, r12d
0x1800150e1  lea     r14, [rdi+30h]
0x1800150e5  and     eax, 1
0x1800150e8  mov     r9, r14
0x1800150eb  mov     [rdi+20h], eax
0x1800150ee  mov     r8d, r12d
0x1800150f1  mov     ecx, [rdi+24h]
0x1800150f4  mov     rdx, r13
0x1800150f7  call    VsmLoadInterface
0x1800150fc  mov     ebx, eax
0x1800150fe  test    eax, eax
0x180015100  jns     short loc_18001510D
0x180015102  mov     r9d, 6BAh
0x180015108  jmp     loc_1800152BB
0x18001510d  mov     eax, 3
0x180015112  lea     rcx, [rsp+230h+var_1C0]
0x180015117  lea     edx, [rax+7Dh]
0x18001511a  movups  xmm0, xmmword ptr [r14]
0x18001511e  movups  xmm1, xmmword ptr [r14+10h]
0x180015123  movups  xmmword ptr [rcx], xmm0
0x180015126  movups  xmm0, xmmword ptr [r14+20h]
0x18001512b  movups  xmmword ptr [rcx+10h], xmm1
0x18001512f  movups  xmm1, xmmword ptr [r14+30h]
0x180015134  movups  xmmword ptr [rcx+20h], xmm0
0x180015138  movups  xmm0, xmmword ptr [r14+40h]
0x18001513d  movups  xmmword ptr [rcx+30h], xmm1
0x180015141  movups  xmm1, xmmword ptr [r14+50h]
0x180015146  movups  xmmword ptr [rcx+40h], xmm0
0x18001514a  movups  xmm0, xmmword ptr [r14+60h]
0x18001514f  movups  xmmword ptr [rcx+50h], xmm1
0x180015153  movups  xmm1, xmmword ptr [r14+70h]
0x180015158  add     r14, rdx
0x18001515b  movups  xmmword ptr [rcx+60h], xmm0
0x18001515f  movups  xmmword ptr [rcx+70h], xmm1
0x180015163  add     rcx, rdx
0x180015166  sub     rax, 1
0x18001516a  jnz     short loc_18001511A
0x18001516c  mov     rax, [r14]
0x18001516f  lea     r9, [rsp+230h+var_1D0]
0x180015174  mov     [rcx], rax
0x180015177  lea     r8, [rsp+230h+var_1F0]
0x18001517c  lea     rax, [rsp+230h+var_1E0]
0x180015181  mov     ecx, esi
0x180015183  mov     [rsp+230h+var_208], rax
0x180015188  lea     rdx, [rsp+230h+var_1C0]
0x18001518d  lea     rax, [rsp+230h+var_1D8]
0x180015192  mov     [rsp+230h+var_210], rax
0x180015197  call    ValidateFunctionTable
0x18001519c  mov     ebx, eax
0x18001519e  test    eax, eax
0x1800151a0  jns     short loc_1800151AD
0x1800151a2  mov     r9d, 6C3h
0x1800151a8  jmp     loc_1800152BB
0x1800151ad  mov     rax, [rsp+230h+var_1F0]
0x1800151b2  lea     r14, [rdi+18h]
0x1800151b6  mov     rcx, r14
0x1800151b9  mov     r8d, r12d
0x1800151bc  mov     rdx, r13
0x1800151bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800151c4  mov     ebx, eax
0x1800151c6  cmp     eax, 0C000A001h
0x1800151cb  jnz     short loc_1800151FC
0x1800151cd  cmp     esi, 2
0x1800151d0  jnz     loc_18001525D
0x1800151d6  mov     eax, r12d
0x1800151d9  and     al, 28h
0x1800151db  cmp     al, 8
0x1800151dd  jnz     short loc_180015201
0x1800151df  mov     rax, [rsp+230h+var_1F0]
0x1800151e4  and     r12d, 0FFFFFFF7h
0x1800151e8  mov     r8d, r12d
0x1800151eb  mov     rdx, r13
0x1800151ee  mov     rcx, r14
0x1800151f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800151f6  or      dword ptr [rdi+8], 8
0x1800151fa  jmp     short loc_180015201
0x1800151fc  cmp     esi, 2
0x1800151ff  jnz     short loc_18001525D
0x180015201  mov     rax, [rsp+230h+var_1E0]
0x180015206  test    rax, rax
0x180015209  jnz     short loc_180015220
0x18001520b  mov     ebx, 0C00000E5h
0x180015210  mov     ecx, 0C00000E5h
0x180015215  mov     r9d, 6E9h
0x18001521b  jmp     loc_1800152BD
0x180015220  lea     rcx, [rsp+230h+var_1E8]
0x180015225  mov     dword ptr [rsp+230h+var_208], 0
0x18001522d  mov     [rsp+230h+var_210], rcx
0x180015232  lea     r8, [rdi+0Ch]
0x180015236  mov     rcx, [r14]
0x180015239  lea     rdx, aHashblocklengt; "HashBlockLength"
0x180015240  mov     r9d, 4
0x180015246  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001524b  mov     ebx, eax
0x18001524d  test    eax, eax
0x18001524f  jns     loc_1800152DA
0x180015255  mov     r9d, 6F5h
0x18001525b  jmp     short loc_1800152BB
0x18001525d  cmp     esi, 3
0x180015260  jnz     short loc_1800152DA
0x180015262  mov     rax, [rsp+230h+var_1E0]
0x180015267  test    rax, rax
0x18001526a  jnz     short loc_18001527E
0x18001526c  mov     ebx, 0C00000E5h
0x180015271  mov     ecx, 0C00000E5h
0x180015276  mov     r9d, 6FEh
0x18001527c  jmp     short loc_1800152BD
0x18001527e  mov     r9d, [rbp+130h+arg_10]
0x180015285  lea     rcx, [rbp+130h+arg_10]
0x18001528c  mov     dword ptr [rsp+230h+var_208], 0
0x180015294  lea     r8, [rdi+1B8h]
0x18001529b  mov     [rsp+230h+var_210], rcx
0x1800152a0  lea     rdx, aPaddingschemes; "PaddingSchemes"
0x1800152a7  mov     rcx, [r14]
0x1800152aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800152af  mov     ebx, eax
0x1800152b1  test    eax, eax
0x1800152b3  jns     short loc_1800152DA
0x1800152b5  mov     r9d, 70Ah
0x1800152bb  mov     ecx, eax
0x1800152bd  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800152c4  lea     rdx, aStatus; "Status"
0x1800152cb  call    DebugTraceError
0x1800152d0  mov     rcx, rdi
0x1800152d3  call    MSCryptFree
0x1800152d8  jmp     short loc_18001533B
0x1800152da  lea     r9, AlgorithmClassPropertyTable
0x1800152e1  mov     rdx, [r15+r9+10h]
0x1800152e6  test    rdx, rdx
0x1800152e9  jz      short loc_18001530C
0x1800152eb  mov     rcx, [r14]
0x1800152ee  lea     r8, [r9+18h]
0x1800152f2  mov     r9d, [r15+r9+1Ch]
0x1800152f7  add     r8, r15
0x1800152fa  mov     rax, [rsp+230h+var_1D8]
0x1800152ff  mov     dword ptr [rsp+230h+var_210], 0
0x180015307  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001530c  mov     rax, [rbp+130h+arg_0]
0x180015313  mov     [rax], rdi
0x180015316  jmp     short loc_18001533B
0x180015318  mov     r9d, 684h
0x18001531e  mov     ecx, 0C0000008h
0x180015323  mov     ebx, 0C0000008h
0x180015328  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001532f  lea     rdx, aStatus; "Status"
0x180015336  call    DebugTraceError
0x18001533b  mov     eax, ebx
0x18001533d  mov     rbx, [rsp+230h+arg_8]
0x180015345  add     rsp, 200h
0x18001534c  pop     r15
0x18001534e  pop     r14
0x180015350  pop     r13
0x180015352  pop     r12
0x180015354  pop     rdi
0x180015355  pop     rsi
0x180015356  pop     rbp
0x180015357  retn
```
