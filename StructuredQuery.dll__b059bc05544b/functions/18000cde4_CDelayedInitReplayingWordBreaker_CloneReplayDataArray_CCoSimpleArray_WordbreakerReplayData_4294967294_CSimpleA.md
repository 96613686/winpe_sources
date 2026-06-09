# CDelayedInitReplayingWordBreaker::_CloneReplayDataArray(CCoSimpleArray<WordbreakerReplayData,4294967294,CSimpleArrayStandardCompareHelper<WordbreakerReplayData>> const &,CCoSimpleArray<WordbreakerReplayData,4294967294,CSimpleArrayStandardCompareHelper<WordbreakerReplayData>> &)

- ea: `0x18000cde4`
- end: `0x18000d07d`
- name: `?_CloneReplayDataArray@CDelayedInitReplayingWordBreaker@@AEAAJAEBV?$CCoSimpleArray@UWordbreakerReplayData@@$0PPPPPPPO@V?$CSimpleArrayStandardCompareHelper@UWordbreakerReplayData@@@@@@AEAV2@@Z`
- size: `665`
- prototype: `__int64 __fastcall(__int64, __int64 *, _QWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000cb40`
- `0x180047a98`

## callees

- `0x18000cda8`
- `0x18000cde4`
- `0x18000d084`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cfe6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cfe6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000cecb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000cecb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDelayedInitReplayingWordBreaker::_CloneReplayDataArray(__int64 a1, __int64 *a2, _QWORD *a3)
{
  __int64 *v4; // rax
  int v5; // ebx
  unsigned __int64 i; // r12
  __int64 v7; // rdx
  __int64 v8; // r9
  int v9; // r10d
  int v10; // r11d
  unsigned __int64 v11; // rax
  __int16 *v12; // r15
  unsigned __int64 v13; // r14
  unsigned __int64 v14; // rsi
  _WORD *v15; // rax
  void *v16; // rdi
  unsigned __int64 v17; // rdx
  __int16 v18; // cx
  _WORD *v19; // rcx
  int v20; // esi
  int v21; // r14d
  __int64 v22; // rdx
  __int64 v23; // rdx
  void *v24; // rax
  __int64 v26; // r8
  int v27; // [rsp+20h] [rbp-50h]
  int v28; // [rsp+24h] [rbp-4Ch]
  int v29; // [rsp+28h] [rbp-48h]
  __int128 v30; // [rsp+40h] [rbp-30h] BYREF
  unsigned __int64 v31; // [rsp+50h] [rbp-20h]
  int v32; // [rsp+58h] [rbp-18h]
  int v33; // [rsp+5Ch] [rbp-14h]
  int v34; // [rsp+60h] [rbp-10h]
  int v35; // [rsp+64h] [rbp-Ch]
  unsigned int v36; // [rsp+B0h] [rbp+40h]
  int v38; // [rsp+C8h] [rbp+58h]

  v4 = a2;
  v5 = 0;
  for ( i = 0; i < v4[1]; ++i )
  {
    v7 = *v4;
    v30 = 0;
    v31 = 0;
    v8 = *(unsigned int *)(v7 + 48 * i);
    v36 = *(_DWORD *)(v7 + 48 * i);
    v9 = *(_DWORD *)(v7 + 48 * i + 32);
    v38 = v9;
    v32 = v9;
    v10 = *(_DWORD *)(v7 + 48 * i + 36);
    v27 = v10;
    v33 = v10;
    v28 = *(_DWORD *)(v7 + 48 * i + 40);
    v34 = v28;
    v29 = *(_DWORD *)(v7 + 48 * i + 44);
    v35 = v29;
    v11 = *(_QWORD *)(v7 + 48 * i + 16);
    if ( v11 == -1 )
    {
      v26 = *(_QWORD *)(v7 + 48 * i + 8);
      if ( !v26 )
      {
LABEL_41:
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<wchar_t>>::~NativeString<Windows::Internal::CoTaskMemPolicy<wchar_t>>((__int64)&v30);
        v21 = v35;
        v20 = v34;
        v10 = v33;
        v27 = v33;
        v9 = v32;
        v38 = v32;
        v16 = (void *)v30;
        v8 = v36;
LABEL_27:
        v5 = 0;
        v22 = a3[1];
        if ( v22 != a3[3] )
          goto LABEL_30;
        v5 = CTSimpleArray<WordbreakerReplayData,4294967294,CTPolicyCoTaskMem<WordbreakerReplayData>,CSimpleArrayStandardCompareHelper<WordbreakerReplayData>,CSimpleArrayStandardMergeHelper<WordbreakerReplayData>>::_EnsureCapacity(
               a3,
               v22 + 1,
               0,
               v8);
        if ( v5 >= 0 )
        {
          LODWORD(v8) = v36;
          v9 = v38;
          v10 = v27;
LABEL_30:
          ++a3[1];
          v23 = 48LL * a3[1] + *a3 - 48LL;
          if ( v23 )
          {
            *(_DWORD *)v23 = v8;
            *(_QWORD *)(v23 + 16) = *((_QWORD *)&v30 + 1);
            *(_QWORD *)(v23 + 24) = v31;
            v24 = v16;
            v16 = 0;
            *(_QWORD *)(v23 + 8) = v24;
            *(_DWORD *)(v23 + 32) = v9;
            *(_DWORD *)(v23 + 36) = v10;
            *(_DWORD *)(v23 + 40) = v20;
            *(_DWORD *)(v23 + 44) = v21;
          }
          goto LABEL_32;
        }
        goto LABEL_32;
      }
      v11 = -1;
      do
        ++v11;
      while ( *(_WORD *)(v26 + 2 * v11) );
      v12 = *(__int16 **)(v7 + 48 * i + 8);
    }
    else
    {
      v12 = *(__int16 **)(v7 + 48 * i + 8);
      if ( !v12 )
        goto LABEL_41;
    }
    v13 = -1;
    do
      ++v13;
    while ( v12[v13] );
    if ( v11 == -1 )
    {
      v11 = v13;
    }
    else if ( v11 < v13 )
    {
      v13 = v11;
    }
    v14 = v11 + 1;
    if ( v11 + 1 >= v11 && is_mul_ok(v14, 2u) )
    {
      v15 = CoTaskMemAlloc(2 * v14);
      v16 = v15;
      if ( !v15 )
      {
        v5 = -2147024882;
        v16 = (void *)v30;
        goto LABEL_32;
      }
      v31 = v14;
      *(_QWORD *)&v30 = v15;
      *v15 = 0;
      v5 = 0;
      if ( v14 )
      {
        if ( v14 > 0x7FFFFFFF || v13 > 0x7FFFFFFE )
        {
          *v15 = 0;
        }
        else
        {
          v17 = v13;
          do
          {
            if ( !v17 )
              break;
            v18 = *v12;
            if ( !*v12 )
              break;
            ++v12;
            *v15++ = v18;
            --v17;
            --v14;
          }
          while ( v14 );
          v19 = v15 - 1;
          if ( v14 )
            v19 = v15;
          *v19 = 0;
        }
      }
      *((_QWORD *)&v30 + 1) = v13;
      v8 = v36;
      v9 = v38;
      v10 = v27;
    }
    else
    {
      v16 = (void *)v30;
      v5 = -2147024362;
    }
    if ( v5 >= 0 )
    {
      v20 = v28;
      v21 = v29;
      goto LABEL_27;
    }
LABEL_32:
    if ( v16 )
      CoTaskMemFree(v16);
    v4 = a2;
    if ( v5 < 0 )
      return (unsigned int)v5;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000cde4  mov     [rsp-38h+arg_10], rbx
0x18000cde9  mov     [rsp-38h+arg_8], rdx
0x18000cdee  mov     [rsp-38h+arg_0], rcx
0x18000cdf3  push    rbp
0x18000cdf4  push    rsi
0x18000cdf5  push    rdi
0x18000cdf6  push    r12
0x18000cdf8  push    r13
0x18000cdfa  push    r14
0x18000cdfc  push    r15
0x18000cdfe  mov     rbp, rsp
0x18000ce01  sub     rsp, 70h
0x18000ce05  mov     r13, r8
0x18000ce08  mov     rax, rdx
0x18000ce0b  xor     r8d, r8d
0x18000ce0e  mov     ebx, r8d
0x18000ce11  mov     r12d, r8d
0x18000ce14  cmp     r12, [rax+8]
0x18000ce18  jnb     loc_18000CFFE
0x18000ce1e  lea     rcx, [r12+r12*2]
0x18000ce22  add     rcx, rcx
0x18000ce25  mov     rdx, [rax]
0x18000ce28  xorps   xmm0, xmm0
0x18000ce2b  movdqu  [rbp+var_30], xmm0
0x18000ce30  mov     [rbp+var_20], r8
0x18000ce34  mov     r9d, [rdx+rcx*8]
0x18000ce38  mov     dword ptr [rbp+arg_0], r9d
0x18000ce3c  mov     [rbp+var_38], r9d
0x18000ce40  mov     r10d, [rdx+rcx*8+20h]
0x18000ce45  mov     [rbp+arg_18], r10d
0x18000ce49  mov     [rbp+var_18], r10d
0x18000ce4d  mov     r11d, [rdx+rcx*8+24h]
0x18000ce52  mov     [rbp+var_50], r11d
0x18000ce56  mov     [rbp+var_14], r11d
0x18000ce5a  mov     eax, [rdx+rcx*8+28h]
0x18000ce5e  mov     [rbp+var_4C], eax
0x18000ce61  mov     [rbp+var_10], eax
0x18000ce64  mov     eax, [rdx+rcx*8+2Ch]
0x18000ce68  mov     [rbp+var_48], eax
0x18000ce6b  mov     [rbp+var_C], eax
0x18000ce6e  mov     rax, [rdx+rcx*8+10h]
0x18000ce73  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000ce77  jz      loc_18000D02B
0x18000ce7d  mov     r15, [rdx+rcx*8+8]
0x18000ce82  test    r15, r15
0x18000ce85  jz      loc_18000D049
0x18000ce8b  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000ce8f  inc     r14
0x18000ce92  cmp     [r15+r14*2], r8w
0x18000ce97  jnz     short loc_18000CE8F
0x18000ce99  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000ce9d  jz      loc_18000D018
0x18000cea3  cmp     rax, r14
0x18000cea6  cmovb   r14, rax
0x18000ceaa  lea     rsi, [rax+1]
0x18000ceae  cmp     rsi, rax
0x18000ceb1  jb      loc_18000CF54
0x18000ceb7  mov     eax, 2
0x18000cebc  mul     rsi
0x18000cebf  test    rdx, rdx
0x18000cec2  jnz     loc_18000CF54
0x18000cec8  mov     rcx, rax; cb
0x18000cecb  call    cs:__imp_CoTaskMemAlloc
0x18000ced1  mov     rdi, rax
0x18000ced4  xor     r8d, r8d
0x18000ced7  test    rax, rax
0x18000ceda  jz      loc_18000D020
0x18000cee0  mov     [rbp+var_20], rsi
0x18000cee4  mov     qword ptr [rbp+var_30], rax
0x18000cee8  mov     [rax], r8w
0x18000ceec  mov     ebx, r8d
0x18000ceef  test    rsi, rsi
0x18000cef2  jz      short loc_18000CF42
0x18000cef4  cmp     rsi, 7FFFFFFFh
0x18000cefb  ja      loc_18000D040
0x18000cf01  cmp     r14, 7FFFFFFEh
0x18000cf08  ja      loc_18000D040
0x18000cf0e  mov     rdx, r14
0x18000cf11  test    rdx, rdx
0x18000cf14  jz      short loc_18000CF33
0x18000cf16  movzx   ecx, word ptr [r15]
0x18000cf1a  test    cx, cx
0x18000cf1d  jz      short loc_18000CF33
0x18000cf1f  add     r15, 2
0x18000cf23  mov     [rax], cx
0x18000cf26  add     rax, 2
0x18000cf2a  dec     rdx
0x18000cf2d  sub     rsi, 1
0x18000cf31  jnz     short loc_18000CF11
0x18000cf33  lea     rcx, [rax-2]
0x18000cf37  test    rsi, rsi
0x18000cf3a  cmovnz  rcx, rax
0x18000cf3e  mov     [rcx], r8w
0x18000cf42  mov     qword ptr [rbp+var_30+8], r14
0x18000cf46  mov     r9d, dword ptr [rbp+arg_0]
0x18000cf4a  mov     r10d, [rbp+arg_18]
0x18000cf4e  mov     r11d, [rbp+var_50]
0x18000cf52  jmp     short loc_18000CF5D
0x18000cf54  mov     rdi, qword ptr [rbp+var_30]
0x18000cf58  mov     ebx, 80070216h
0x18000cf5d  test    ebx, ebx
0x18000cf5f  js      short loc_18000CFDE
0x18000cf61  mov     esi, [rbp+var_4C]
0x18000cf64  mov     r14d, [rbp+var_48]
0x18000cf68  mov     ebx, r8d
0x18000cf6b  mov     rdx, [r13+8]
0x18000cf6f  cmp     rdx, [r13+18h]
0x18000cf73  jnz     short loc_18000CF95
0x18000cf75  inc     rdx
0x18000cf78  mov     rcx, r13
0x18000cf7b  call    ?_EnsureCapacity@?$CTSimpleArray@UWordbreakerReplayData@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@UWordbreakerReplayData@@@@V?$CSimpleArrayStandardCompareHelper@UWordbreakerReplayData@@@@V?$CSimpleArrayStandardMergeHelper@UWordbreakerReplayData@@@@@@QEAAJ_K0@Z; CTSimpleArray<WordbreakerReplayData,4294967294,CTPolicyCoTaskMem<WordbreakerReplayData>,CSimpleArrayStandardCompareHelper<WordbreakerReplayData>,CSimpleArrayStandardMergeHelper<WordbreakerReplayData>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x18000cf80  mov     ebx, eax
0x18000cf82  xor     r8d, r8d
0x18000cf85  test    eax, eax
0x18000cf87  js      short loc_18000CFDE
0x18000cf89  mov     r9d, dword ptr [rbp+arg_0]
0x18000cf8d  mov     r10d, [rbp+arg_18]
0x18000cf91  mov     r11d, [rbp+var_50]
0x18000cf95  inc     qword ptr [r13+8]
0x18000cf99  mov     rax, [r13+8]
0x18000cf9d  lea     rcx, [rax+rax*2]
0x18000cfa1  shl     rcx, 4
0x18000cfa5  mov     rdx, [r13+0]
0x18000cfa9  add     rdx, 0FFFFFFFFFFFFFFD0h
0x18000cfad  add     rdx, rcx
0x18000cfb0  jz      short loc_18000CFDE
0x18000cfb2  mov     [rdx], r9d
0x18000cfb5  mov     rax, qword ptr [rbp+var_30+8]
0x18000cfb9  mov     [rdx+10h], rax
0x18000cfbd  mov     rax, [rbp+var_20]
0x18000cfc1  mov     [rdx+18h], rax
0x18000cfc5  mov     rax, rdi
0x18000cfc8  mov     rdi, r8
0x18000cfcb  mov     [rdx+8], rax
0x18000cfcf  mov     [rdx+20h], r10d
0x18000cfd3  mov     [rdx+24h], r11d
0x18000cfd7  mov     [rdx+28h], esi
0x18000cfda  mov     [rdx+2Ch], r14d
0x18000cfde  test    rdi, rdi
0x18000cfe1  jz      short loc_18000CFEF
0x18000cfe3  mov     rcx, rdi; pv
0x18000cfe6  call    cs:__imp_CoTaskMemFree
0x18000cfec  xor     r8d, r8d
0x18000cfef  inc     r12
0x18000cff2  test    ebx, ebx
0x18000cff4  mov     rax, [rbp+arg_8]
0x18000cff8  jns     loc_18000CE14
0x18000cffe  mov     eax, ebx
0x18000d000  mov     rbx, [rsp+70h+arg_10]
0x18000d008  add     rsp, 70h
0x18000d00c  pop     r15
0x18000d00e  pop     r14
0x18000d010  pop     r13
0x18000d012  pop     r12
0x18000d014  pop     rdi
0x18000d015  pop     rsi
0x18000d016  pop     rbp
0x18000d017  retn
0x18000d018  mov     rax, r14
0x18000d01b  jmp     loc_18000CEAA
0x18000d020  mov     ebx, 8007000Eh
0x18000d025  mov     rdi, qword ptr [rbp+var_30]
0x18000d029  jmp     short loc_18000CFDE
0x18000d02b  mov     r8, [rdx+rcx*8+8]
0x18000d030  xor     ebx, ebx
0x18000d032  test    r8, r8
0x18000d035  jz      short loc_18000D049
0x18000d037  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000d03b  jmp     loc_180087936
0x18000d040  mov     [rax], r8w
0x18000d044  jmp     loc_18000CF42
0x18000d049  lea     rcx, [rbp+var_30]
0x18000d04d  call    ??1?$NativeString@V?$CoTaskMemPolicy@_W@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<wchar_t>>::~NativeString<Windows::Internal::CoTaskMemPolicy<wchar_t>>(void)
0x18000d052  mov     r14d, [rbp+var_C]
0x18000d056  mov     esi, [rbp+var_10]
0x18000d059  mov     r11d, [rbp+var_14]
0x18000d05d  mov     [rbp+var_50], r11d
0x18000d061  mov     r10d, [rbp+var_18]
0x18000d065  mov     [rbp+arg_18], r10d
0x18000d069  mov     rdi, qword ptr [rbp+var_30]
0x18000d06d  mov     r9d, [rbp+var_38]
0x18000d071  mov     dword ptr [rbp+arg_0], r9d
0x18000d075  xor     r8d, r8d
0x18000d078  jmp     loc_18000CF68
0x180087936  inc     rax
0x180087939  cmp     [r8+rax*2], bx
0x18008793e  jnz     short loc_180087936
0x180087940  mov     r15, r8
0x180087943  xor     r8d, r8d
0x180087946  jmp     loc_18000CE8B
```
