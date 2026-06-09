# ZtComputeConfigChange

- ea: `0x18000fb40`
- end: `0x18000fddf`
- name: `ZtComputeConfigChange`
- size: `671`
- prototype: `__int64 __fastcall(__int128 *, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800046ec`

## callees

- `0x18000fb40`
- `0x180015008`
- `0x180015478`
- `0x1800163e0`

## pseudocode

```c
__int64 __fastcall ZtComputeConfigChange(__int128 *a1, __int64 a2, __int64 *a3)
{
  unsigned int v6; // ebx
  __int64 v7; // r14
  __int128 v8; // xmm6
  __int64 v9; // r8
  int v10; // r9d
  int v11; // r10d
  __int64 v12; // rcx
  int v13; // r11d
  int v14; // r12d
  int v15; // r13d
  __int64 v16; // rdx
  __int64 v17; // rax
  int v18; // esi
  bool v19; // zf
  int v20; // eax
  __int64 v22; // [rsp+28h] [rbp-110h]
  __int64 v23; // [rsp+30h] [rbp-108h]
  int v24; // [rsp+B8h] [rbp-80h]
  int v25; // [rsp+BCh] [rbp-7Ch]
  int v26; // [rsp+C0h] [rbp-78h]
  int v27; // [rsp+C4h] [rbp-74h]
  int v28; // [rsp+C8h] [rbp-70h]
  unsigned int v29; // [rsp+CCh] [rbp-6Ch]
  __int128 v30; // [rsp+E0h] [rbp-58h]
  __int128 v31; // [rsp+F0h] [rbp-48h]
  __int64 v32; // [rsp+100h] [rbp-38h]
  int v33; // [rsp+168h] [rbp+30h]
  int v34; // [rsp+170h] [rbp+38h]

  if ( (BYTE1(xmmword_18001F260) & 8) != 0 )
    WPP_SF_qqq(1035, 0x15u, (ULONGLONG)WPP_7eb1482970b13f51d23b3992b8531bf6_Traceguids, a2, a1, a3);
  v6 = 0;
  if ( a3 )
    *a3 = 0;
  if ( a2 && a1 && a3 )
  {
    v7 = 0;
    v8 = *a1;
    v29 = *((_DWORD *)a1 + 4);
    v9 = v29;
    LODWORD(v30) = v29;
    v10 = *((_DWORD *)a1 + 5);
    v28 = v10;
    DWORD1(v30) = v10;
    v11 = *((_DWORD *)a1 + 6);
    v27 = v11;
    DWORD2(v30) = v11;
    v12 = *((unsigned int *)a1 + 7);
    v26 = *((_DWORD *)a1 + 7);
    HIDWORD(v30) = v26;
    v13 = *((_DWORD *)a1 + 8);
    v25 = v13;
    LODWORD(v31) = v13;
    v14 = *((_DWORD *)a1 + 9);
    v24 = v14;
    DWORD1(v31) = v14;
    v15 = *((_DWORD *)a1 + 10);
    v34 = v15;
    DWORD2(v31) = v15;
    v33 = *((_DWORD *)a1 + 11);
    HIDWORD(v31) = v33;
    v16 = *((unsigned int *)a1 + 12);
    v32 = *((_QWORD *)a1 + 6);
    v17 = *(_QWORD *)(a2 + 8);
    if ( (v17 & 1) != 0 && *(_DWORD *)(a2 + 16) != v29 )
    {
      v9 = *(unsigned int *)(a2 + 16);
      v7 = 1;
      LODWORD(v30) = *(_DWORD *)(a2 + 16);
    }
    if ( (v17 & 2) != 0 && *(_DWORD *)(a2 + 20) != v10 )
    {
      v10 = *(_DWORD *)(a2 + 20);
      v7 |= 2uLL;
      DWORD1(v30) = v10;
    }
    if ( (v17 & 4) != 0 && *(_DWORD *)(a2 + 24) != v11 )
    {
      v11 = *(_DWORD *)(a2 + 24);
      v7 |= 4uLL;
      DWORD2(v30) = v11;
    }
    if ( (v17 & 8) != 0 && *(_DWORD *)(a2 + 28) != (_DWORD)v12 )
    {
      v12 = *(unsigned int *)(a2 + 28);
      v7 |= 8uLL;
      HIDWORD(v30) = *(_DWORD *)(a2 + 28);
    }
    if ( (v17 & 0x80u) != 0LL && *(_DWORD *)(a2 + 32) != v13 )
    {
      v13 = *(_DWORD *)(a2 + 32);
      v7 |= 0x80uLL;
      LODWORD(v31) = v13;
    }
    if ( (v17 & 0x100) != 0 && *(_DWORD *)(a2 + 36) != v14 )
    {
      v14 = *(_DWORD *)(a2 + 36);
      v7 |= 0x100uLL;
      DWORD1(v31) = v14;
    }
    if ( (v17 & 0x10) != 0 && *(_DWORD *)(a2 + 40) != v15 )
    {
      v15 = *(_DWORD *)(a2 + 40);
      v7 |= 0x10uLL;
      DWORD2(v31) = v15;
    }
    if ( (v17 & 0x20) == 0 || *(_DWORD *)(a2 + 44) == v33 )
    {
      v18 = *((_DWORD *)a1 + 11);
    }
    else
    {
      v18 = *(_DWORD *)(a2 + 44);
      v7 |= 0x20uLL;
      HIDWORD(v31) = v18;
    }
    v19 = (v17 & 0x40) == 0;
    v20 = v16;
    if ( !v19 && *(_DWORD *)(a2 + 48) != (_DWORD)v16 )
    {
      v16 = *(unsigned int *)(a2 + 48);
      v7 |= 0x40uLL;
      LODWORD(v32) = *(_DWORD *)(a2 + 48);
    }
    if ( (BYTE1(xmmword_18001F260) & 8) != 0 )
    {
      LODWORD(v23) = v28;
      LODWORD(v22) = v9;
      WPP_SF_ddlllllllllldddddd(
        v12,
        v16,
        v9,
        v29,
        v22,
        v23,
        v10,
        v27,
        v11,
        v26,
        v12,
        v25,
        v13,
        v24,
        v14,
        v34,
        v15,
        v33,
        v18,
        v20,
        v16);
    }
    *(_OWORD *)a2 = v8;
    *(_OWORD *)(a2 + 16) = v30;
    *(_OWORD *)(a2 + 32) = v31;
    *(_QWORD *)(a2 + 48) = v32;
    *a3 = v7;
  }
  else
  {
    v6 = 87;
  }
  if ( (BYTE1(xmmword_18001F260) & 8) != 0 )
    WPP_SF_d(1035, 0x17u, (ULONGLONG)WPP_7eb1482970b13f51d23b3992b8531bf6_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x18000fb40  mov     rax, rsp
0x18000fb43  mov     [rax+8], rbx
0x18000fb47  push    rbp
0x18000fb48  push    rsi
0x18000fb49  push    rdi
0x18000fb4a  push    r12
0x18000fb4c  push    r13
0x18000fb4e  push    r14
0x18000fb50  push    r15
0x18000fb52  lea     rbp, [rax-18h]
0x18000fb56  sub     rsp, 110h
0x18000fb5d  movaps  xmmword ptr [rax-48h], xmm6
0x18000fb61  mov     r15, r8
0x18000fb64  mov     rdi, rdx
0x18000fb67  mov     rsi, rcx
0x18000fb6a  test    byte ptr cs:xmmword_18001F260+1, 8
0x18000fb71  jz      short loc_18000FB96
0x18000fb73  mov     [rsp+140h+var_118], r8
0x18000fb78  mov     edx, 15h
0x18000fb7d  lea     r8, WPP_7eb1482970b13f51d23b3992b8531bf6_Traceguids
0x18000fb84  mov     [rsp+140h+var_120], rsi
0x18000fb89  mov     ecx, 40Bh
0x18000fb8e  mov     r9, rdi
0x18000fb91  call    WPP_SF_qqq
0x18000fb96  xor     ebx, ebx
0x18000fb98  test    r15, r15
0x18000fb9b  jz      short loc_18000FBA0
0x18000fb9d  mov     [r15], rbx
0x18000fba0  test    rdi, rdi
0x18000fba3  jnz     short loc_18000FBAF
0x18000fba5  mov     ebx, 57h ; 'W'
0x18000fbaa  jmp     loc_18000FD9B
0x18000fbaf  test    rsi, rsi
0x18000fbb2  jz      short loc_18000FBA5
0x18000fbb4  test    r15, r15
0x18000fbb7  jz      short loc_18000FBA5
0x18000fbb9  mov     eax, [rsi+10h]
0x18000fbbc  mov     r14, rbx
0x18000fbbf  movups  xmm6, xmmword ptr [rsi]
0x18000fbc2  mov     [rbp+10h+var_7C], eax
0x18000fbc5  mov     r8d, eax
0x18000fbc8  mov     dword ptr [rbp+10h+var_68], eax
0x18000fbcb  mov     eax, [rsi+14h]
0x18000fbce  mov     r9d, eax
0x18000fbd1  mov     [rbp+10h+var_80], eax
0x18000fbd4  mov     dword ptr [rbp+10h+var_68+4], eax
0x18000fbd7  mov     eax, [rsi+18h]
0x18000fbda  mov     r10d, eax
0x18000fbdd  mov     [rbp+10h+var_84], eax
0x18000fbe0  mov     dword ptr [rbp+10h+var_68+8], eax
0x18000fbe3  mov     eax, [rsi+1Ch]
0x18000fbe6  mov     ecx, eax
0x18000fbe8  mov     [rbp+10h+var_88], eax
0x18000fbeb  mov     dword ptr [rbp+10h+var_68+0Ch], eax
0x18000fbee  mov     eax, [rsi+20h]
0x18000fbf1  mov     r11d, eax
0x18000fbf4  mov     [rbp+10h+var_8C], eax
0x18000fbf7  mov     dword ptr [rbp+10h+var_58], eax
0x18000fbfa  mov     eax, [rsi+24h]
0x18000fbfd  mov     r12d, eax
0x18000fc00  mov     [rbp+10h+var_90], eax
0x18000fc03  mov     dword ptr [rbp+10h+var_58+4], eax
0x18000fc06  mov     eax, [rsi+28h]
0x18000fc09  mov     r13d, eax
0x18000fc0c  mov     [rbp+10h+arg_18], eax
0x18000fc0f  mov     dword ptr [rbp+10h+var_58+8], eax
0x18000fc12  mov     eax, [rsi+2Ch]
0x18000fc15  mov     [rbp+10h+arg_10], eax
0x18000fc18  mov     dword ptr [rbp+10h+var_58+0Ch], eax
0x18000fc1b  mov     eax, [rsi+30h]
0x18000fc1e  mov     edx, eax
0x18000fc20  mov     dword ptr [rbp+10h+var_48], eax
0x18000fc23  mov     eax, [rsi+34h]
0x18000fc26  mov     dword ptr [rbp+10h+var_48+4], eax
0x18000fc29  mov     rax, [rdi+8]
0x18000fc2d  test    al, 1
0x18000fc2f  jz      short loc_18000FC45
0x18000fc31  cmp     [rdi+10h], r8d
0x18000fc35  jz      short loc_18000FC45
0x18000fc37  mov     r8d, [rdi+10h]
0x18000fc3b  mov     r14d, 1
0x18000fc41  mov     dword ptr [rbp+10h+var_68], r8d
0x18000fc45  test    al, 2
0x18000fc47  jz      short loc_18000FC5B
0x18000fc49  cmp     [rdi+14h], r9d
0x18000fc4d  jz      short loc_18000FC5B
0x18000fc4f  mov     r9d, [rdi+14h]
0x18000fc53  or      r14, 2
0x18000fc57  mov     dword ptr [rbp+10h+var_68+4], r9d
0x18000fc5b  test    al, 4
0x18000fc5d  jz      short loc_18000FC71
0x18000fc5f  cmp     [rdi+18h], r10d
0x18000fc63  jz      short loc_18000FC71
0x18000fc65  mov     r10d, [rdi+18h]
0x18000fc69  or      r14, 4
0x18000fc6d  mov     dword ptr [rbp+10h+var_68+8], r10d
0x18000fc71  test    al, 8
0x18000fc73  jz      short loc_18000FC84
0x18000fc75  cmp     [rdi+1Ch], ecx
0x18000fc78  jz      short loc_18000FC84
0x18000fc7a  mov     ecx, [rdi+1Ch]
0x18000fc7d  or      r14, 8
0x18000fc81  mov     dword ptr [rbp+10h+var_68+0Ch], ecx
0x18000fc84  test    al, al
0x18000fc86  jns     short loc_18000FC9B
0x18000fc88  cmp     [rdi+20h], r11d
0x18000fc8c  jz      short loc_18000FC9B
0x18000fc8e  mov     r11d, [rdi+20h]
0x18000fc92  bts     r14, 7
0x18000fc97  mov     dword ptr [rbp+10h+var_58], r11d
0x18000fc9b  bt      rax, 8
0x18000fca0  jnb     short loc_18000FCB5
0x18000fca2  cmp     [rdi+24h], r12d
0x18000fca6  jz      short loc_18000FCB5
0x18000fca8  mov     r12d, [rdi+24h]
0x18000fcac  bts     r14, 8
0x18000fcb1  mov     dword ptr [rbp+10h+var_58+4], r12d
0x18000fcb5  test    al, 10h
0x18000fcb7  jz      short loc_18000FCCB
0x18000fcb9  cmp     [rdi+28h], r13d
0x18000fcbd  jz      short loc_18000FCCB
0x18000fcbf  mov     r13d, [rdi+28h]
0x18000fcc3  or      r14, 10h
0x18000fcc7  mov     dword ptr [rbp+10h+var_58+8], r13d
0x18000fccb  test    al, 20h
0x18000fccd  jz      short loc_18000FCE3
0x18000fccf  mov     esi, [rbp+10h+arg_10]
0x18000fcd2  cmp     [rdi+2Ch], esi
0x18000fcd5  jz      short loc_18000FCE3
0x18000fcd7  mov     esi, [rdi+2Ch]
0x18000fcda  or      r14, 20h
0x18000fcde  mov     dword ptr [rbp+10h+var_58+0Ch], esi
0x18000fce1  jmp     short loc_18000FCE6
0x18000fce3  mov     esi, dword ptr [rbp+10h+var_58+0Ch]
0x18000fce6  test    al, 40h
0x18000fce8  mov     eax, edx
0x18000fcea  jz      short loc_18000FCFB
0x18000fcec  cmp     [rdi+30h], edx
0x18000fcef  jz      short loc_18000FCFB
0x18000fcf1  mov     edx, [rdi+30h]
0x18000fcf4  or      r14, 40h
0x18000fcf8  mov     dword ptr [rbp+10h+var_48], edx
0x18000fcfb  test    byte ptr cs:xmmword_18001F260+1, 8
0x18000fd02  jz      short loc_18000FD7B
0x18000fd04  mov     [rsp+140h+var_A0], edx
0x18000fd0b  mov     [rsp+140h+var_A8], eax
0x18000fd12  mov     eax, [rbp+10h+arg_10]
0x18000fd15  mov     [rsp+140h+var_B0], esi
0x18000fd1c  mov     [rsp+140h+var_B8], eax
0x18000fd23  mov     eax, [rbp+10h+arg_18]
0x18000fd26  mov     [rsp+140h+var_C0], r13d
0x18000fd2e  mov     [rsp+140h+var_C8], eax
0x18000fd32  mov     eax, [rbp+10h+var_90]
0x18000fd35  mov     [rsp+140h+var_D0], r12d
0x18000fd3a  mov     [rsp+140h+var_D8], eax
0x18000fd3e  mov     eax, [rbp+10h+var_8C]
0x18000fd41  mov     [rsp+140h+var_E0], r11d
0x18000fd46  mov     [rsp+140h+var_E8], eax
0x18000fd4a  mov     eax, [rbp+10h+var_88]
0x18000fd4d  mov     [rsp+140h+var_F0], ecx
0x18000fd51  mov     [rsp+140h+var_F8], eax
0x18000fd55  mov     eax, [rbp+10h+var_84]
0x18000fd58  mov     [rsp+140h+var_100], r10d
0x18000fd5d  mov     [rsp+140h+var_108], eax
0x18000fd61  mov     eax, [rbp+10h+var_80]
0x18000fd64  mov     [rsp+140h+var_110], r9d
0x18000fd69  mov     r9d, [rbp+10h+var_7C]
0x18000fd6d  mov     dword ptr [rsp+140h+var_118], eax
0x18000fd71  mov     dword ptr [rsp+140h+var_120], r8d
0x18000fd76  call    WPP_SF_ddlllllllllldddddd
0x18000fd7b  movups  xmm0, [rbp+10h+var_68]
0x18000fd7f  movups  xmm1, [rbp+10h+var_58]
0x18000fd83  movups  xmmword ptr [rdi], xmm6
0x18000fd86  movups  xmmword ptr [rdi+10h], xmm0
0x18000fd8a  movsd   xmm0, [rbp+10h+var_48]
0x18000fd8f  movups  xmmword ptr [rdi+20h], xmm1
0x18000fd93  movsd   qword ptr [rdi+30h], xmm0
0x18000fd98  mov     [r15], r14
0x18000fd9b  test    byte ptr cs:xmmword_18001F260+1, 8
0x18000fda2  jz      short loc_18000FDBD
0x18000fda4  mov     edx, 17h
0x18000fda9  lea     r8, WPP_7eb1482970b13f51d23b3992b8531bf6_Traceguids
0x18000fdb0  mov     ecx, 40Bh
0x18000fdb5  mov     r9d, ebx
0x18000fdb8  call    WPP_SF_d
0x18000fdbd  lea     r11, [rsp+140h+var_30]
0x18000fdc5  mov     eax, ebx
0x18000fdc7  mov     rbx, [r11+40h]
0x18000fdcb  movaps  xmm6, xmmword ptr [r11-10h]
0x18000fdd0  mov     rsp, r11
0x18000fdd3  pop     r15
0x18000fdd5  pop     r14
0x18000fdd7  pop     r13
0x18000fdd9  pop     r12
0x18000fddb  pop     rdi
0x18000fddc  pop     rsi
0x18000fddd  pop     rbp
0x18000fdde  retn
```
