# EapCreateAggregatedEventConditionVisitNode

- ea: `0x1800086d0`
- end: `0x1800088ca`
- name: `EapCreateAggregatedEventConditionVisitNode`
- size: `506`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800022b0`
- `0x180002e30`
- `0x180003630`
- `0x1800086d0`
- `0x18000bde9`

## pseudocode

```c
__int64 __fastcall EapCreateAggregatedEventConditionVisitNode(_QWORD *a1, int *a2)
{
  __int128 v2; // xmm6
  int v4; // ecx
  __int64 result; // rax
  int v7; // r14d
  __int64 v8; // rcx
  __int64 v9; // r9
  unsigned __int16 v10; // r10
  char *v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rdx
  void *v16; // r8
  __int64 v17; // rdx
  __int64 v18; // rax
  void *v19; // rdi
  __int128 v20; // xmm1
  __int64 v21; // rcx
  char *v22; // rax
  __int64 v23; // xmm0_8
  unsigned int v24; // [rsp+28h] [rbp-69h]
  __int64 v25[2]; // [rsp+58h] [rbp-39h] BYREF
  __int128 v26; // [rsp+68h] [rbp-29h]
  __int128 v27; // [rsp+78h] [rbp-19h]
  __int64 v28[2]; // [rsp+88h] [rbp-9h] BYREF
  __int128 v29; // [rsp+98h] [rbp+7h]
  __int64 v30; // [rsp+A8h] [rbp+17h]

  v2 = 0;
  LODWORD(v30) = 0;
  v4 = *a2;
  v27 = 0;
  *(_OWORD *)v28 = 0;
  v29 = 0;
  *(_OWORD *)v25 = 0;
  v26 = 0;
  if ( v4 )
  {
    if ( v4 != 1 || *((unsigned __int16 *)a1 + 5) < (unsigned int)a2[3] )
      return 3221225701LL;
    *((_QWORD *)&v27 + 1) = (unsigned int)a2[2];
    v7 = 0;
    v8 = 56LL * (unsigned int)a2[3];
    LODWORD(v27) = 1;
    v28[0] = EaLibAllocate(v8);
    v9 = v28[0];
    if ( !v28[0] )
      return 3221225495LL;
    v10 = 0;
    if ( a2[3] )
    {
      do
      {
        v11 = (char *)*a1;
        ++v7;
        v12 = 56LL * *((unsigned __int16 *)a1 + 5);
        v13 = v10++;
        v14 = 56 * v13;
        *(_OWORD *)(v14 + v9) = *(_OWORD *)(v12 + *a1 - 56);
        *(_OWORD *)(v14 + v9 + 16) = *(_OWORD *)&v11[v12 - 40];
        *(_OWORD *)(v14 + v9 + 32) = *(_OWORD *)&v11[v12 - 24];
        *(_QWORD *)(v14 + v9 + 48) = *(_QWORD *)&v11[v12 - 8];
        --*((_WORD *)a1 + 5);
      }
      while ( v10 < (unsigned int)a2[3] );
      HIDWORD(v27) = v7;
    }
  }
  else
  {
    v15 = a1[2];
    v16 = *(void **)(v15 + 64);
    v17 = *(_QWORD *)(v15 + 56);
    v24 = *((_DWORD *)a1 + 6);
    LOBYTE(v30) = 1;
    result = BriCreateBrokeredEventEx((UUID *)(a2 + 2), v17, v16, (__int64)(a2 + 6), v24, 0, v28, v25, 0);
    if ( (int)result < 0 )
      return result;
    v2 = v29;
    v28[1] = __PAIR64__(v25[1], v25[0]);
  }
  v18 = *((unsigned __int16 *)a1 + 4);
  if ( *((_WORD *)a1 + 5) == (_WORD)v18 )
  {
    v19 = (void *)EaLibAllocate(56 * (v18 + 5));
    if ( !v19 )
      return 3221225495LL;
    if ( *a1 )
    {
      memcpy_0(v19, (const void *)*a1, 56LL * *((unsigned __int16 *)a1 + 4));
      EaLibFree(*a1);
    }
    *((_WORD *)a1 + 4) += 5;
    *a1 = v19;
  }
  v20 = *(_OWORD *)v28;
  v21 = 56LL * *((unsigned __int16 *)a1 + 5);
  v22 = (char *)*a1;
  *(_OWORD *)&v22[v21] = v27;
  v23 = v30;
  *(_OWORD *)&v22[v21 + 16] = v20;
  *(_OWORD *)&v22[v21 + 32] = v2;
  *(_QWORD *)&v22[v21 + 48] = v23;
  ++*((_WORD *)a1 + 5);
  return 0;
}

```

## disassembly

```asm
0x1800086d0  mov     rax, rsp
0x1800086d3  push    rbp
0x1800086d4  push    rbx
0x1800086d5  push    rsi
0x1800086d6  push    rdi
0x1800086d7  push    r14
0x1800086d9  lea     rbp, [rax-5Fh]
0x1800086dd  sub     rsp, 0C0h
0x1800086e4  movaps  xmmword ptr [rax-38h], xmm6
0x1800086e8  xorps   xmm0, xmm0
0x1800086eb  xorps   xmm6, xmm6
0x1800086ee  xor     eax, eax
0x1800086f0  mov     rbx, rcx
0x1800086f3  mov     dword ptr [rbp+57h+var_40], eax
0x1800086f6  mov     ecx, [rdx]
0x1800086f8  mov     rdi, rdx
0x1800086fb  movups  [rbp+57h+var_70], xmm6
0x1800086ff  movups  xmmword ptr [rbp+57h+var_60], xmm6
0x180008703  movups  [rbp+57h+var_50], xmm6
0x180008707  movups  xmmword ptr [rbp+57h+var_90], xmm0
0x18000870b  movups  [rbp+57h+var_80], xmm0
0x18000870f  test    ecx, ecx
0x180008711  jz      loc_1800087D1
0x180008717  cmp     ecx, 1
0x18000871a  jnz     short loc_180008725
0x18000871c  movzx   eax, word ptr [rbx+0Ah]
0x180008720  cmp     eax, [rdx+0Ch]
0x180008723  jnb     short loc_18000872F
0x180008725  mov     eax, 0C00000E5h
0x18000872a  jmp     loc_1800088B4
0x18000872f  mov     eax, [rdx+8]
0x180008732  mov     esi, 1
0x180008737  mov     dword ptr [rbp+57h+var_70+8], eax
0x18000873a  xor     r14d, r14d
0x18000873d  mov     eax, [rdx+0Ch]
0x180008740  imul    rcx, rax, 38h ; '8'
0x180008744  mov     dword ptr [rbp+57h+var_70], esi
0x180008747  mov     dword ptr [rbp+57h+var_70+0Ch], r14d
0x18000874b  call    EaLibAllocate
0x180008750  mov     [rbp+57h+var_60], rax
0x180008754  mov     r9, rax
0x180008757  test    rax, rax
0x18000875a  jnz     short loc_180008766
0x18000875c  mov     eax, 0C0000017h
0x180008761  jmp     loc_1800088B4
0x180008766  xor     r10d, r10d
0x180008769  cmp     [rdi+0Ch], r10d
0x18000876d  jbe     loc_180008832
0x180008773  mov     rdx, [rbx]
0x180008776  add     r14d, esi
0x180008779  movzx   eax, word ptr [rbx+0Ah]
0x18000877d  imul    r8, rax, 38h ; '8'
0x180008781  movzx   eax, r10w
0x180008785  add     r10w, si
0x180008789  imul    rcx, rax, 38h ; '8'
0x18000878d  movups  xmm0, xmmword ptr [r8+rdx-38h]
0x180008793  movzx   eax, r10w
0x180008797  movups  xmmword ptr [rcx+r9], xmm0
0x18000879c  movups  xmm1, xmmword ptr [r8+rdx-28h]
0x1800087a2  movups  xmmword ptr [rcx+r9+10h], xmm1
0x1800087a8  movups  xmm0, xmmword ptr [r8+rdx-18h]
0x1800087ae  movups  xmmword ptr [rcx+r9+20h], xmm0
0x1800087b4  movsd   xmm1, qword ptr [r8+rdx-8]
0x1800087bb  movsd   qword ptr [rcx+r9+30h], xmm1
0x1800087c2  sub     [rbx+0Ah], si
0x1800087c6  cmp     eax, [rdi+0Ch]
0x1800087c9  jb      short loc_180008773
0x1800087cb  mov     dword ptr [rbp+57h+var_70+0Ch], r14d
0x1800087cf  jmp     short loc_180008832
0x1800087d1  mov     rdx, [rbx+10h]
0x1800087d5  lea     r9, [rdi+18h]
0x1800087d9  mov     [rsp+40h], rax; __int64
0x1800087de  lea     rcx, [rdi+8]; Source1
0x1800087e2  lea     rax, [rbp+57h+var_90]
0x1800087e6  mov     esi, 1
0x1800087eb  mov     [rsp+0E0h+var_A8], rax; __int64
0x1800087f0  lea     rax, [rbp+57h+var_60]
0x1800087f4  mov     r8, [rdx+40h]
0x1800087f8  mov     rdx, [rdx+38h]
0x1800087fc  mov     [rsp+0E0h+var_B0], rax; __int64
0x180008801  mov     eax, [rbx+18h]
0x180008804  mov     [rsp+0E0h+var_B8], 0; __int64
0x18000880d  mov     [rsp+0E0h+var_C0], eax; int
0x180008811  mov     byte ptr [rbp+57h+var_40], sil
0x180008815  call    BriCreateBrokeredEventEx
0x18000881a  test    eax, eax
0x18000881c  js      loc_1800088B4
0x180008822  mov     eax, dword ptr [rbp+57h+var_90]
0x180008825  movups  xmm6, [rbp+57h+var_50]
0x180008829  mov     dword ptr [rbp+57h+var_60+8], eax
0x18000882c  mov     eax, dword ptr [rbp+57h+var_90+8]
0x18000882f  mov     dword ptr [rbp+57h+var_60+0Ch], eax
0x180008832  movzx   eax, word ptr [rbx+8]
0x180008836  cmp     [rbx+0Ah], ax
0x18000883a  jnz     short loc_180008882
0x18000883c  mov     r14d, 5
0x180008842  add     rax, r14
0x180008845  imul    rcx, rax, 38h ; '8'
0x180008849  call    EaLibAllocate
0x18000884e  mov     rdi, rax
0x180008851  test    rax, rax
0x180008854  jz      loc_18000875C
0x18000885a  mov     rdx, [rbx]; Src
0x18000885d  test    rdx, rdx
0x180008860  jz      short loc_18000887A
0x180008862  movzx   eax, word ptr [rbx+8]
0x180008866  mov     rcx, rdi; void *
0x180008869  imul    r8, rax, 38h ; '8'; Size
0x18000886d  call    memcpy_0
0x180008872  mov     rcx, [rbx]
0x180008875  call    EaLibFree
0x18000887a  add     [rbx+8], r14w
0x18000887f  mov     [rbx], rdi
0x180008882  movzx   eax, word ptr [rbx+0Ah]
0x180008886  movups  xmm0, [rbp+57h+var_70]
0x18000888a  movups  xmm1, xmmword ptr [rbp+57h+var_60]
0x18000888e  imul    rcx, rax, 38h ; '8'
0x180008892  mov     rax, [rbx]
0x180008895  movups  xmmword ptr [rcx+rax], xmm0
0x180008899  movsd   xmm0, [rbp+57h+var_40]
0x18000889e  movups  xmmword ptr [rcx+rax+10h], xmm1
0x1800088a3  movups  xmmword ptr [rcx+rax+20h], xmm6
0x1800088a8  movsd   qword ptr [rcx+rax+30h], xmm0
0x1800088ae  add     [rbx+0Ah], si
0x1800088b2  xor     eax, eax
0x1800088b4  movaps  xmm6, [rsp+0E0h+var_38+8]
0x1800088bc  add     rsp, 0C0h
0x1800088c3  pop     r14
0x1800088c5  pop     rdi
0x1800088c6  pop     rsi
0x1800088c7  pop     rbx
0x1800088c8  pop     rbp
0x1800088c9  retn
```
