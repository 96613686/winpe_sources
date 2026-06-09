# ImportV2KeyBlob

- ea: `0x1800693c8`
- end: `0x1800696fc`
- name: `ImportV2KeyBlob`
- size: `820`
- prototype: `__int64 __fastcall(__int64, __int64, _DWORD *, unsigned int, unsigned int, _QWORD *)`
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x180069c80`

## callees

- `0x18000ecb0`
- `0x180010270`
- `0x1800102a0`
- `0x18001b67c`
- `0x18001bf34`
- `0x18001bf88`
- `0x18001c380`
- `0x18001c420`
- `0x18001c878`
- `0x1800497f0`
- `0x180056cf0`
- `0x1800581c0`
- `0x180058288`
- `0x180058834`
- `0x1800693ac`
- `0x1800693c8`

## string_xrefs

- `0x18006941b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dsa.c`
- `0x180069680`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dsa.c`

## pseudocode

```c
__int64 __fastcall ImportV2KeyBlob(__int64 a1, __int64 a2, _DWORD *a3, unsigned int a4, unsigned int a5, _QWORD *a6)
{
  int v8; // eax
  unsigned int v9; // edi
  __int64 v10; // r9
  __int64 v11; // rcx
  unsigned int v12; // edi
  int v13; // r15d
  __int64 v14; // rax
  unsigned int *v15; // rbx
  int v16; // edx
  __int64 v17; // rax
  __int64 v18; // rcx
  __int64 v19; // r9
  __int64 v20; // r14
  unsigned int v21; // r12d
  unsigned int v22; // eax
  unsigned int v23; // r15d
  int v24; // ebp
  __int64 SymCryptDlgroupHashAlgorithm; // rax
  int v26; // edx
  int v27; // r11d
  unsigned int v28; // eax
  __int64 v29; // rdx
  unsigned int v30; // eax
  __int64 v31; // rax
  __int64 v32; // rbp
  int v33; // eax
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 v36; // r9
  __int64 v37; // r11
  __int64 v38; // r10
  int v39; // eax
  int v40; // r10d
  unsigned int v41; // eax
  __int64 v42; // rcx
  __int64 v43; // rax
  _BYTE *v44; // rcx
  int v46; // [rsp+20h] [rbp-A8h]
  size_t Size; // [rsp+70h] [rbp-58h]
  __int64 v48; // [rsp+78h] [rbp-50h]
  int v49; // [rsp+80h] [rbp-48h]
  int v50; // [rsp+E0h] [rbp+18h] BYREF
  int v51; // [rsp+E8h] [rbp+20h] BYREF

  v51 = 0;
  v50 = 0;
  v8 = ValidateDSAKeyBlobV2Format(a3, a4, a2, &v51);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = 1837;
    v11 = (unsigned int)v8;
LABEL_3:
    DebugTraceError(v11, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\dsa\\dsa.c", v10);
    return v9;
  }
  v12 = a3[1];
  v13 = a3[5];
  v14 = SafeAllocaAllocateFromHeap(48);
  v15 = (unsigned int *)v14;
  if ( !v14 )
  {
    v9 = -1073741801;
    v10 = 1853;
    v11 = 3221225495LL;
    goto LABEL_3;
  }
  *(_OWORD *)v14 = 0;
  *(_OWORD *)(v14 + 16) = 0;
  *(_OWORD *)(v14 + 32) = 0;
  *(_DWORD *)v14 = 48;
  *(_DWORD *)(v14 + 12) = v12;
  v16 = a3[5];
  *(_DWORD *)(v14 + 16) = v16;
  *(_DWORD *)(v14 + 20) = a3[3];
  *(_DWORD *)(v14 + 24) = a3[2];
  v17 = SymCryptDlgroupAllocate(8 * v12, (unsigned int)(8 * v16));
  *((_QWORD *)v15 + 4) = v17;
  if ( v17 )
  {
    v20 = 0;
    v21 = 0;
    if ( v51 )
    {
      v21 = v15[4];
      v20 = (__int64)a3 + 3 * v12 + 2 * v13 + 28;
    }
    v15[1] = 1297304409;
    v22 = *(_DWORD *)(a1 + 8);
    v15[7] |= 1u;
    v15[2] = v22;
    Size = (unsigned int)a3[4];
    v49 = v15[4] + Size + (_DWORD)a3 + 28;
    v48 = (__int64)a3 + Size + v15[4] + v15[3] + 28;
    ReverseMemCopy(&v50, a3 + 6, 4);
    v23 = a5;
    v24 = v50;
    SymCryptDlgroupHashAlgorithm = GetSymCryptDlgroupHashAlgorithm(v15[6], v15[3]);
    v28 = SymCryptDlgroupSetValue(
            v49,
            v26,
            (int)Size + (int)a3 + 28,
            v15[4],
            v48,
            v26,
            2,
            SymCryptDlgroupHashAlgorithm,
            (__int64)(a3 + 7),
            Size,
            v24,
            v27,
            *((_QWORD *)v15 + 4));
    if ( v28 )
    {
      v30 = SymcryptErrorCodeToNtStatus(v28);
      v19 = 1924;
    }
    else
    {
      v31 = SymCryptDlkeyAllocate(*((_QWORD *)v15 + 4), v29);
      *((_QWORD *)v15 + 5) = v31;
      v32 = v31;
      if ( !v31 )
      {
        v9 = -1073741801;
        v18 = 3221225495LL;
        v19 = 1932;
        goto LABEL_24;
      }
      v33 = IsAllZeros((char *)a3 + 2 * v15[3] + a3[4] + a3[5] + 28, v12);
      v38 = 0;
      if ( v33 )
        v12 = 0;
      else
        v38 = v37;
      if ( (v23 & 0x20) != 0 && (!v20 || !v38) )
      {
        v9 = -1073741811;
        v18 = 3221225485LL;
        v19 = 1954;
        goto LABEL_24;
      }
      v39 = BCryptFlagsToSymCryptKeyValidationFlags(v23, v34, v35, v36);
      v41 = SymCryptDlkeySetValue(v20, v21, v40, v12, v46, v39 | 0x1000u, v32);
      if ( !v41 )
      {
        v9 = 0;
        *a6 = v15;
        return v9;
      }
      v30 = SymcryptErrorCodeToNtStatus(v41);
      v19 = 1972;
    }
    v18 = v30;
    v9 = v30;
    goto LABEL_24;
  }
  v9 = -1073741801;
  v18 = 3221225495LL;
  v19 = 1873;
LABEL_24:
  DebugTraceError(v18, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\dsa\\dsa.c", v19);
  if ( *((_QWORD *)v15 + 5) )
  {
    SymCryptDlkeyFree();
    *((_QWORD *)v15 + 5) = 0;
  }
  v42 = *((_QWORD *)v15 + 4);
  if ( v42 )
  {
    SymCryptMlDsaTemporariesFree(v42);
    *((_QWORD *)v15 + 4) = 0;
  }
  v43 = *v15;
  v44 = v15;
  if ( *v15 )
  {
    do
    {
      *v44++ = 0;
      --v43;
    }
    while ( v43 );
  }
  MSCryptFree(v15);
  return v9;
}

```

## disassembly

```asm
0x1800693c8  mov     r11, rsp
0x1800693cb  mov     [r11+8], rbx
0x1800693cf  push    rbp
0x1800693d0  push    rsi
0x1800693d1  push    rdi
0x1800693d2  push    r12
0x1800693d4  push    r13
0x1800693d6  push    r14
0x1800693d8  push    r15
0x1800693da  sub     rsp, 90h
0x1800693e1  mov     eax, r9d
0x1800693e4  mov     rsi, r8
0x1800693e7  mov     r8, rdx
0x1800693ea  lea     r9, [r11+20h]
0x1800693ee  mov     rbp, rcx
0x1800693f1  xor     r13d, r13d
0x1800693f4  mov     edx, eax
0x1800693f6  mov     [r11+20h], r13d
0x1800693fa  mov     rcx, rsi
0x1800693fd  mov     [r11+18h], r13d
0x180069401  call    ValidateDSAKeyBlobV2Format
0x180069406  mov     edi, eax
0x180069408  test    eax, eax
0x18006940a  jns     short loc_18006942C
0x18006940c  mov     r9d, 72Dh
0x180069412  mov     ecx, eax
0x180069414  lea     rdx, aStatus; "Status"
0x18006941b  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180069422  call    DebugTraceError
0x180069427  jmp     loc_1800696DE
0x18006942c  mov     edi, [rsi+4]
0x18006942f  mov     r14d, 30h ; '0'
0x180069435  mov     r15d, [rsi+14h]
0x180069439  mov     ecx, r14d
0x18006943c  call    SafeAllocaAllocateFromHeap
0x180069441  mov     rbx, rax
0x180069444  test    rax, rax
0x180069447  jnz     short loc_18006945B
0x180069449  mov     edi, 0C0000017h
0x18006944e  mov     r9d, 73Dh
0x180069454  mov     ecx, 0C0000017h
0x180069459  jmp     short loc_180069414
0x18006945b  xorps   xmm0, xmm0
0x18006945e  lea     ecx, ds:0[rdi*8]
0x180069465  movups  xmmword ptr [rax], xmm0
0x180069468  movups  xmmword ptr [rax+10h], xmm0
0x18006946c  movups  xmmword ptr [rax+20h], xmm0
0x180069470  mov     [rax], r14d
0x180069473  mov     [rax+0Ch], edi
0x180069476  mov     edx, [rsi+14h]
0x180069479  mov     [rax+10h], edx
0x18006947c  mov     eax, [rsi+0Ch]
0x18006947f  mov     [rbx+14h], eax
0x180069482  mov     eax, [rsi+8]
0x180069485  shl     edx, 3
0x180069488  mov     [rbx+18h], eax
0x18006948b  call    SymCryptDlgroupAllocate
0x180069490  mov     [rbx+20h], rax
0x180069494  test    rax, rax
0x180069497  jnz     short loc_1800694AE
0x180069499  mov     edi, 0C0000017h
0x18006949e  mov     ecx, 0C0000017h
0x1800694a3  mov     r9d, 751h
0x1800694a9  jmp     loc_180069679
0x1800694ae  mov     r14, r13
0x1800694b1  mov     r12d, r13d
0x1800694b4  cmp     [rsp+0C8h+arg_18], r13d
0x1800694bc  jz      short loc_1800694D4
0x1800694be  mov     r12d, [rbx+10h]
0x1800694c2  lea     r14d, [rdi+rdi*2]
0x1800694c6  lea     ecx, [r15+r15]
0x1800694ca  add     r14, rsi
0x1800694cd  add     rcx, 1Ch
0x1800694d1  add     r14, rcx
0x1800694d4  mov     dword ptr [rbx+4], 4D534B59h
0x1800694db  lea     r13, [rsi+1Ch]
0x1800694df  mov     eax, [rbp+8]
0x1800694e2  lea     rdx, [rsi+18h]
0x1800694e6  or      dword ptr [rbx+1Ch], 1
0x1800694ea  mov     r8d, 4
0x1800694f0  mov     [rbx+8], eax
0x1800694f3  mov     eax, [rsi+10h]
0x1800694f6  mov     [rsp+0C8h+var_58], rax
0x1800694fb  lea     rcx, [rax+r13]
0x1800694ff  mov     eax, [rbx+10h]
0x180069502  add     rcx, rax
0x180069505  mov     eax, [rbx+0Ch]
0x180069508  add     rax, rcx
0x18006950b  mov     qword ptr [rsp+0C8h+var_48], rcx
0x180069513  lea     rcx, [rsp+0C8h+arg_10]
0x18006951b  mov     [rsp+0C8h+var_50], rax
0x180069520  call    ReverseMemCopy
0x180069525  mov     r15d, [rsp+0C8h+arg_20]
0x18006952d  mov     ebp, [rsp+0C8h+arg_10]
0x180069534  test    r15b, 8
0x180069538  jnz     short loc_180069545
0x18006953a  mov     r11d, 1
0x180069540  cmp     ebp, 0FFFFFFFFh
0x180069543  jnz     short loc_180069548
0x180069545  xor     r11d, r11d
0x180069548  mov     edx, [rbx+0Ch]
0x18006954b  add     r11d, r11d
0x18006954e  mov     ecx, [rbx+18h]
0x180069551  call    GetSymCryptDlgroupHashAlgorithm
0x180069556  mov     r10, [rbx+20h]
0x18006955a  mov     r9d, [rbx+10h]; int
0x18006955e  mov     rcx, qword ptr [rsp+0C8h+var_48]; int
0x180069566  mov     [rsp+0C8h+var_68], r10; __int64
0x18006956b  mov     r10, [rsp+0C8h+var_58]
0x180069570  mov     [rsp+0C8h+var_70], r11d; int
0x180069575  mov     [rsp+0C8h+var_78], ebp; int
0x180069579  mov     [rsp+0C8h+Size], r10; Size
0x18006957e  mov     [rsp+0C8h+var_88], r13; __int64
0x180069583  lea     r8, [r10+r13]; int
0x180069587  mov     [rsp+0C8h+var_90], rax; __int64
0x18006958c  mov     rax, [rsp+0C8h+var_50]
0x180069591  mov     [rsp+0C8h+var_98], 2; int
0x180069599  mov     qword ptr [rsp+0C8h+var_A0], rdx; int
0x18006959e  mov     [rsp+0C8h+var_A8], rax; __int64
0x1800695a3  call    SymCryptDlgroupSetValue
0x1800695a8  xor     r13d, r13d
0x1800695ab  test    eax, eax
0x1800695ad  jz      short loc_1800695C1
0x1800695af  mov     ecx, eax
0x1800695b1  call    SymcryptErrorCodeToNtStatus
0x1800695b6  mov     r9d, 784h
0x1800695bc  jmp     loc_180069675
0x1800695c1  mov     rcx, [rbx+20h]
0x1800695c5  call    SymCryptDlkeyAllocate
0x1800695ca  mov     [rbx+28h], rax
0x1800695ce  mov     rbp, rax
0x1800695d1  test    rax, rax
0x1800695d4  jnz     short loc_1800695EB
0x1800695d6  mov     edi, 0C0000017h
0x1800695db  mov     ecx, 0C0000017h
0x1800695e0  mov     r9d, 78Ch
0x1800695e6  jmp     loc_180069679
0x1800695eb  mov     eax, [rbx+0Ch]
0x1800695ee  mov     edx, edi
0x1800695f0  mov     r11d, [rsi+10h]
0x1800695f4  add     r11, rsi
0x1800695f7  lea     ecx, [rax+rax]
0x1800695fa  mov     eax, [rsi+14h]
0x1800695fd  add     r11, rcx
0x180069600  add     rax, 1Ch
0x180069604  add     r11, rax
0x180069607  mov     rcx, r11
0x18006960a  call    IsAllZeros
0x18006960f  test    eax, eax
0x180069611  mov     r10, r13
0x180069614  cmovnz  edi, r13d
0x180069618  cmovz   r10, r11
0x18006961c  test    r15b, 20h
0x180069620  jz      short loc_18006963E
0x180069622  test    r14, r14
0x180069625  jz      short loc_18006962C
0x180069627  test    r10, r10
0x18006962a  jnz     short loc_18006963E
0x18006962c  mov     edi, 0C000000Dh
0x180069631  mov     ecx, 0C000000Dh
0x180069636  mov     r9d, 7A2h
0x18006963c  jmp     short loc_180069679
0x18006963e  mov     ecx, r15d
0x180069641  call    BCryptFlagsToSymCryptKeyValidationFlags
0x180069646  bts     eax, 0Ch
0x18006964a  mov     r9d, edi
0x18006964d  mov     edx, r12d
0x180069650  mov     r8, r10
0x180069653  mov     qword ptr [rsp+0C8h+var_98], rbp
0x180069658  mov     rcx, r14
0x18006965b  mov     [rsp+0C8h+var_A0], eax
0x18006965f  call    SymCryptDlkeySetValue
0x180069664  test    eax, eax
0x180069666  jz      short loc_1800696D0
0x180069668  mov     ecx, eax
0x18006966a  call    SymcryptErrorCodeToNtStatus
0x18006966f  mov     r9d, 7B4h
0x180069675  mov     ecx, eax
0x180069677  mov     edi, eax
0x180069679  lea     rdx, aStatus; "Status"
0x180069680  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180069687  call    DebugTraceError
0x18006968c  mov     rcx, [rbx+28h]
0x180069690  test    rcx, rcx
0x180069693  jz      short loc_18006969E
0x180069695  call    SymCryptDlkeyFree
0x18006969a  mov     [rbx+28h], r13
0x18006969e  mov     rcx, [rbx+20h]
0x1800696a2  test    rcx, rcx
0x1800696a5  jz      short loc_1800696B0
0x1800696a7  call    SymCryptMlDsaTemporariesFree
0x1800696ac  mov     [rbx+20h], r13
0x1800696b0  mov     eax, [rbx]
0x1800696b2  mov     rcx, rbx
0x1800696b5  test    rax, rax
0x1800696b8  jz      short loc_1800696C6
0x1800696ba  mov     [rcx], r13b
0x1800696bd  inc     rcx
0x1800696c0  sub     rax, 1
0x1800696c4  jnz     short loc_1800696BA
0x1800696c6  mov     rcx, rbx
0x1800696c9  call    MSCryptFree
0x1800696ce  jmp     short loc_1800696DE
0x1800696d0  mov     rax, [rsp+0C8h+arg_28]
0x1800696d8  mov     edi, r13d
0x1800696db  mov     [rax], rbx
0x1800696de  mov     rbx, [rsp+0C8h+arg_0]
0x1800696e6  mov     eax, edi
0x1800696e8  add     rsp, 90h
0x1800696ef  pop     r15
0x1800696f1  pop     r14
0x1800696f3  pop     r13
0x1800696f5  pop     r12
0x1800696f7  pop     rdi
0x1800696f8  pop     rsi
0x1800696f9  pop     rbp
0x1800696fa  retn
```
