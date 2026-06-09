# Algorithms::QuickSort<SyncVersion,ClockVector::CompareFunctor,ClockVector::SwapFunctor>(SyncVersion *,ulong,ClockVector::CompareFunctor,ClockVector::SwapFunctor)

- ea: `0x1800166e0`
- end: `0x180016a31`
- name: `??$QuickSort@USyncVersion@@UCompareFunctor@ClockVector@@USwapFunctor@3@@Algorithms@@SAXPEAUSyncVersion@@KUCompareFunctor@ClockVector@@USwapFunctor@3@@Z`
- size: `849`
- prototype: `__int64(char *, unsigned int, __int64, ...)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180012260`
- `0x180013950`
- `0x180016540`

## callees

- `0x1800166e0`
- `0x18001dd6c`
- `0x18009323e`
- `0x180093270`

## pseudocode

```c
__int64 Algorithms::QuickSort<SyncVersion,ClockVector::CompareFunctor,ClockVector::SwapFunctor>(
        char *a1,
        unsigned int a2,
        __int64 a3,
        ...)
{
  __int64 v3; // rdi
  __int64 v5; // rbx
  __int64 result; // rax
  int v7; // ebp
  char *v8; // rdi
  char *v9; // rax
  char *v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // r9
  __int128 v14; // xmm1
  char *v15; // r15
  char *v16; // r14
  char *v17; // r12
  char *v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // xmm0_8
  __int64 v21; // r8
  __int64 v22; // xmm1_8
  __int64 v23; // rdx
  _QWORD v24[62]; // [rsp+20h] [rbp-428h] BYREF
  _QWORD v25[62]; // [rsp+210h] [rbp-238h] BYREF
  __int64 v26; // [rsp+468h] [rbp+20h] BYREF
  va_list va; // [rsp+468h] [rbp+20h]
  va_list va1; // [rsp+470h] [rbp+28h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v26 = va_arg(va1, _QWORD);
  v3 = a2;
  v5 = v26;
  memset_0(v24, 0, sizeof(v24));
  result = (__int64)memset_0(v25, 0, sizeof(v25));
  if ( (unsigned int)v3 >= 2 )
  {
    v7 = 0;
    v8 = &a1[16 * v3 - 16];
    while ( 1 )
    {
      while ( 1 )
      {
        result = (unsigned int)((v8 - a1) >> 4) + 1;
        if ( (unsigned int)result <= 8 )
        {
          for ( ; v8 > a1; v8 -= 16 )
          {
            v9 = a1;
            v10 = a1;
            do
            {
              if ( *(_DWORD *)v10 > *(_DWORD *)v9 )
                v9 = v10;
              v10 += 16;
            }
            while ( v10 <= v8 );
            v11 = *(_QWORD *)(v5 + 40);
            v12 = (unsigned int)((__int64)&v8[-v11] >> 4);
            v13 = (unsigned int)((__int64)&v9[-v11] >> 4);
            result = 2LL * (unsigned int)v13;
            v14 = *(_OWORD *)(v11 + 16LL * (unsigned int)v13);
            *(_OWORD *)(v11 + 16LL * (unsigned int)v13) = *(_OWORD *)(v11 + 16LL * (unsigned int)v12);
            *(_OWORD *)(v11 + 16LL * (unsigned int)v12) = v14;
            if ( (*(_BYTE *)(v5 + 36) & 2) != 0 )
            {
              v19 = *(_QWORD *)(v5 + 48);
              v20 = *(_QWORD *)(v19 + 12 * v12);
              v21 = v19 + 12 * v12;
              v22 = *(_QWORD *)(v19 + 12 * v13);
              v23 = v19 + 12 * v13;
              LODWORD(v19) = *(_DWORD *)(v23 + 8);
              *(_QWORD *)v23 = v20;
              result = *(unsigned int *)(v21 + 8);
              *(_DWORD *)(v23 + 8) = result;
              *(_QWORD *)v21 = v22;
              *(_DWORD *)(v21 + 8) = v19;
            }
          }
          goto LABEL_12;
        }
        v15 = &a1[16 * ((unsigned __int64)(unsigned int)result >> 1)];
        if ( *(_DWORD *)a1 > *(_DWORD *)v15 )
          ClockVector::SwapFunctor::operator()((__int64 *)va, a1, v15);
        if ( *(_DWORD *)a1 > *(_DWORD *)v8 )
          ClockVector::SwapFunctor::operator()((__int64 *)va, a1, v8);
        if ( *(_DWORD *)v15 > *(_DWORD *)v8 )
          ClockVector::SwapFunctor::operator()((__int64 *)va, v15, v8);
        v16 = a1;
        v17 = v8;
        while ( 1 )
        {
          if ( v15 > v16 )
          {
            while ( 1 )
            {
              v16 += 16;
              if ( v16 >= v15 )
                break;
              if ( *(_DWORD *)v16 > *(_DWORD *)v15 )
                goto LABEL_24;
            }
          }
          do
            v16 += 16;
          while ( v16 <= v8 && *(_DWORD *)v16 <= *(_DWORD *)v15 );
          do
          {
LABEL_24:
            v18 = v17;
            v17 -= 16;
          }
          while ( v17 > v15 && *(_DWORD *)v17 > *(_DWORD *)v15 );
          if ( v17 < v16 )
            break;
          ClockVector::SwapFunctor::operator()((__int64 *)va, v16, v17);
          if ( v15 == v17 )
            v15 = v16;
        }
        if ( v15 < v18 )
        {
          while ( 1 )
          {
            v18 -= 16;
            if ( v18 <= v15 )
              break;
            if ( *(_DWORD *)v18 > *(_DWORD *)v15 || *(_DWORD *)v18 < *(_DWORD *)v15 )
              goto LABEL_31;
          }
        }
        do
          v18 -= 16;
        while ( v18 > a1 && *(_DWORD *)v18 <= *(_DWORD *)v15 && *(_DWORD *)v18 >= *(_DWORD *)v15 );
LABEL_31:
        result = (v18 - a1) & 0xFFFFFFFFFFFFFFF0uLL;
        if ( result >= (__int64)((v8 - v16) & 0xFFFFFFFFFFFFFFF0uLL) )
          break;
        if ( v16 < v8 )
        {
          result = v7++;
          v24[result] = v16;
          v25[result] = v8;
        }
        if ( a1 >= v18 )
        {
LABEL_12:
          if ( --v7 < 0 )
            return result;
          a1 = (char *)v24[v7];
          v8 = (char *)v25[v7];
        }
        else
        {
          v8 = v18;
        }
      }
      if ( a1 < v18 )
      {
        result = v7++;
        v24[result] = a1;
        v25[result] = v18;
      }
      if ( v16 >= v8 )
        goto LABEL_12;
      a1 = v16;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800166e0  mov     [rsp+arg_18], r9
0x1800166e5  push    rbx
0x1800166e6  push    rsi
0x1800166e7  push    rdi
0x1800166e8  sub     rsp, 430h
0x1800166ef  mov     rax, cs:__security_cookie
0x1800166f6  xor     rax, rsp
0x1800166f9  mov     [rsp+448h+var_48], rax
0x180016701  mov     edi, edx
0x180016703  mov     rsi, rcx
0x180016706  xor     edx, edx; Val
0x180016708  lea     rcx, [rsp+448h+var_428]; void *
0x18001670d  mov     r8d, 1F0h; Size
0x180016713  mov     rbx, r9
0x180016716  call    memset_0
0x18001671b  xor     edx, edx; Val
0x18001671d  lea     rcx, [rsp+448h+var_238]; void *
0x180016725  mov     r8d, 1F0h; Size
0x18001672b  call    memset_0
0x180016730  cmp     edi, 2
0x180016733  jb      loc_180016804
0x180016739  mov     [rsp+448h+var_20], rbp
0x180016741  xor     ebp, ebp
0x180016743  shl     rdi, 4
0x180016747  mov     [rsp+448h+var_28], r12
0x18001674f  add     rdi, 0FFFFFFFFFFFFFFF0h
0x180016753  mov     [rsp+448h+var_30], r14
0x18001675b  add     rdi, rsi
0x18001675e  mov     [rsp+448h+var_38], r15
0x180016766  mov     rax, rdi
0x180016769  sub     rax, rsi
0x18001676c  sar     rax, 4
0x180016770  inc     eax
0x180016772  cmp     eax, 8
0x180016775  ja      loc_180016834
0x18001677b  cmp     rdi, rsi
0x18001677e  jbe     short loc_1800167DF
0x180016780  mov     rax, rsi
0x180016783  mov     rdx, rsi
0x180016786  mov     ecx, [rax]
0x180016788  cmp     [rdx], ecx
0x18001678a  cmova   rax, rdx
0x18001678e  add     rdx, 10h
0x180016792  cmp     rdx, rdi
0x180016795  jbe     short loc_180016786
0x180016797  mov     rdx, [rbx+28h]
0x18001679b  mov     rcx, rdi
0x18001679e  sub     rcx, rdx
0x1800167a1  sub     rax, rdx
0x1800167a4  sar     rcx, 4
0x1800167a8  sar     rax, 4
0x1800167ac  mov     r8d, ecx
0x1800167af  mov     r9d, eax
0x1800167b2  mov     ecx, ecx
0x1800167b4  add     rcx, rcx
0x1800167b7  mov     eax, eax
0x1800167b9  add     rax, rax
0x1800167bc  movups  xmm0, xmmword ptr [rdx+rcx*8]
0x1800167c0  movups  xmm1, xmmword ptr [rdx+rax*8]
0x1800167c4  movups  xmmword ptr [rdx+rax*8], xmm0
0x1800167c8  movups  xmmword ptr [rdx+rcx*8], xmm1
0x1800167cc  test    byte ptr [rbx+24h], 2
0x1800167d0  jnz     loc_180016963
0x1800167d6  sub     rdi, 10h
0x1800167da  cmp     rdi, rsi
0x1800167dd  ja      short loc_180016780
0x1800167df  sub     ebp, 1
0x1800167e2  jns     short loc_18001681F
0x1800167e4  mov     r14, [rsp+448h+var_30]
0x1800167ec  mov     r12, [rsp+448h+var_28]
0x1800167f4  mov     rbp, [rsp+448h+var_20]
0x1800167fc  mov     r15, [rsp+448h+var_38]
0x180016804  mov     rcx, [rsp+448h+var_48]
0x18001680c  xor     rcx, rsp; StackCookie
0x18001680f  call    __security_check_cookie
0x180016814  add     rsp, 430h
0x18001681b  pop     rdi
0x18001681c  pop     rsi
0x18001681d  pop     rbx
0x18001681e  retn
0x18001681f  movsxd  rax, ebp
0x180016822  mov     rsi, [rsp+rax*8+448h+var_428]
0x180016827  mov     rdi, [rsp+rax*8+448h+var_238]
0x18001682f  jmp     loc_180016766
0x180016834  mov     r15d, eax
0x180016837  shr     r15, 1
0x18001683a  shl     r15, 4
0x18001683e  add     r15, rsi
0x180016841  mov     eax, [r15]
0x180016844  cmp     [rsi], eax
0x180016846  ja      loc_18001699E
0x18001684c  mov     eax, [rdi]
0x18001684e  cmp     [rsi], eax
0x180016850  ja      loc_1800169B6
0x180016856  mov     eax, [rdi]
0x180016858  cmp     [r15], eax
0x18001685b  ja      loc_1800168F1
0x180016861  mov     r14, rsi
0x180016864  mov     r12, rdi
0x180016867  cmp     r15, r14
0x18001686a  ja      loc_180016910
0x180016870  add     r14, 10h
0x180016874  cmp     r14, rdi
0x180016877  jbe     loc_18001692A
0x18001687d  mov     rdx, r12
0x180016880  sub     r12, 10h
0x180016884  cmp     r12, r15
0x180016887  ja      loc_18001693B
0x18001688d  cmp     r12, r14
0x180016890  jnb     loc_1800169CE
0x180016896  cmp     r15, rdx
0x180016899  jnb     short loc_1800168A8
0x18001689b  sub     rdx, 10h
0x18001689f  cmp     rdx, r15
0x1800168a2  ja      loc_18001694D
0x1800168a8  sub     rdx, 10h
0x1800168ac  cmp     rdx, rsi
0x1800168af  jbe     short loc_1800168BA
0x1800168b1  mov     eax, [r15]
0x1800168b4  cmp     [rdx], eax
0x1800168b6  ja      short loc_1800168BA
0x1800168b8  jnb     short loc_1800168A8
0x1800168ba  mov     rcx, rdi
0x1800168bd  mov     rax, rdx
0x1800168c0  sub     rcx, r14
0x1800168c3  sub     rax, rsi
0x1800168c6  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800168ca  and     rax, 0FFFFFFFFFFFFFFF0h
0x1800168ce  cmp     rax, rcx
0x1800168d1  jl      loc_180016A09
0x1800168d7  cmp     rsi, rdx
0x1800168da  jb      loc_1800169F2
0x1800168e0  cmp     r14, rdi
0x1800168e3  jnb     loc_1800167DF
0x1800168e9  mov     rsi, r14
0x1800168ec  jmp     loc_180016766
0x1800168f1  mov     r8, rdi
0x1800168f4  lea     rcx, [rsp+448h+arg_18]
0x1800168fc  mov     rdx, r15
0x1800168ff  call    ??RSwapFunctor@ClockVector@@QEAAXPEAUSyncVersion@@0@Z; ClockVector::SwapFunctor::operator()(SyncVersion *,SyncVersion *)
0x180016904  jmp     loc_180016861
0x180016910  add     r14, 10h
0x180016914  cmp     r14, r15
0x180016917  jnb     loc_180016870
0x18001691d  mov     eax, [r15]
0x180016920  cmp     [r14], eax
0x180016923  jbe     short loc_180016910
0x180016925  jmp     loc_18001687D
0x18001692a  mov     eax, [r15]
0x18001692d  cmp     [r14], eax
0x180016930  jbe     loc_180016870
0x180016936  jmp     loc_18001687D
0x18001693b  mov     eax, [r15]
0x18001693e  cmp     [r12], eax
0x180016942  jbe     loc_18001688D
0x180016948  jmp     loc_18001687D
0x18001694d  mov     eax, [r15]
0x180016950  cmp     [rdx], eax
0x180016952  ja      loc_1800168BA
0x180016958  jnb     loc_18001689B
0x18001695e  jmp     loc_1800168BA
0x180016963  mov     rcx, [rbx+30h]
0x180016967  lea     rax, [r8+r8*2]
0x18001696b  movsd   xmm0, qword ptr [rcx+rax*4]
0x180016970  lea     r8, [rcx+rax*4]
0x180016974  lea     rax, [r9+r9*2]
0x180016978  movsd   xmm1, qword ptr [rcx+rax*4]
0x18001697d  lea     rdx, [rcx+rax*4]
0x180016981  mov     ecx, [rcx+rax*4+8]
0x180016985  movsd   qword ptr [rdx], xmm0
0x180016989  mov     eax, [r8+8]
0x18001698d  mov     [rdx+8], eax
0x180016990  movsd   qword ptr [r8], xmm1
0x180016995  mov     [r8+8], ecx
0x180016999  jmp     loc_1800167D6
0x18001699e  mov     r8, r15
0x1800169a1  lea     rcx, [rsp+448h+arg_18]
0x1800169a9  mov     rdx, rsi
0x1800169ac  call    ??RSwapFunctor@ClockVector@@QEAAXPEAUSyncVersion@@0@Z; ClockVector::SwapFunctor::operator()(SyncVersion *,SyncVersion *)
0x1800169b1  jmp     loc_18001684C
0x1800169b6  mov     r8, rdi
0x1800169b9  lea     rcx, [rsp+448h+arg_18]
0x1800169c1  mov     rdx, rsi
0x1800169c4  call    ??RSwapFunctor@ClockVector@@QEAAXPEAUSyncVersion@@0@Z; ClockVector::SwapFunctor::operator()(SyncVersion *,SyncVersion *)
0x1800169c9  jmp     loc_180016856
0x1800169ce  mov     r8, r12
0x1800169d1  lea     rcx, [rsp+448h+arg_18]
0x1800169d9  mov     rdx, r14
0x1800169dc  call    ??RSwapFunctor@ClockVector@@QEAAXPEAUSyncVersion@@0@Z; ClockVector::SwapFunctor::operator()(SyncVersion *,SyncVersion *)
0x1800169e1  cmp     r15, r12
0x1800169e4  jnz     loc_180016867
0x1800169ea  mov     r15, r14
0x1800169ed  jmp     loc_180016867
0x1800169f2  movsxd  rax, ebp
0x1800169f5  inc     ebp
0x1800169f7  mov     [rsp+rax*8+448h+var_428], rsi
0x1800169fc  mov     [rsp+rax*8+448h+var_238], rdx
0x180016a04  jmp     loc_1800168E0
0x180016a09  cmp     r14, rdi
0x180016a0c  jnb     short loc_180016A20
0x180016a0e  movsxd  rax, ebp
0x180016a11  inc     ebp
0x180016a13  mov     [rsp+rax*8+448h+var_428], r14
0x180016a18  mov     [rsp+rax*8+448h+var_238], rdi
0x180016a20  cmp     rsi, rdx
0x180016a23  jnb     loc_1800167DF
0x180016a29  mov     rdi, rdx
0x180016a2c  jmp     loc_180016766
```
