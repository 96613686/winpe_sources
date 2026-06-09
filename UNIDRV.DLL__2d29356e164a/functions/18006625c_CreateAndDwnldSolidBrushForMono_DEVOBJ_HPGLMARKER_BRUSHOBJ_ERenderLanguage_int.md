# CreateAndDwnldSolidBrushForMono(_DEVOBJ *,_HPGLMARKER *,_BRUSHOBJ *,ERenderLanguage,int)

- ea: `0x18006625c`
- end: `0x180066588`
- name: `?CreateAndDwnldSolidBrushForMono@@YAHPEAU_DEVOBJ@@PEAU_HPGLMARKER@@PEAU_BRUSHOBJ@@W4ERenderLanguage@@H@Z`
- size: `812`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x1800660b4`
- `0x1800676f0`

## callees

- `0x180066000`
- `0x18006615c`
- `0x18006625c`
- `0x180067bf0`
- `0x180067d84`
- `0x180067dbc`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18006655c`
- `KERNEL32!LocalFree` at `0x18006655c`
- `KERNEL32!LocalAlloc` at `0x18006649c`
- `KERNEL32!LocalAlloc` at `0x18006649c`
- `KERNEL32!SetLastError` at `0x18006656f`
- `KERNEL32!SetLastError` at `0x18006656f`

## pseudocode

```c
__int64 __fastcall CreateAndDwnldSolidBrushForMono(__int64 a1, __int64 a2, unsigned int *a3, unsigned int a4, int a5)
{
  __int64 v8; // r13
  unsigned int v9; // ecx
  __int64 v10; // r11
  unsigned int v11; // edx
  unsigned int v12; // edi
  unsigned int v13; // esi
  unsigned __int64 v14; // rbx
  _DWORD *v15; // r8
  unsigned int v16; // r10d
  bool v17; // zf
  unsigned int *v18; // rax
  unsigned int v19; // r9d
  unsigned int i; // edx
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rcx
  unsigned int v24; // edx
  __int64 v25; // r8
  __int128 v26; // xmm0
  __m128i v27; // xmm1
  unsigned __int64 v28; // xmm1_8
  struct _BRUSHINFO *v29; // rsi
  int v30; // r12d
  struct _BRUSHINFO *v31; // rax
  int v32; // edx
  unsigned int v33; // ebx
  int v34; // r8d
  int v36; // [rsp+28h] [rbp-50h]
  int v37; // [rsp+30h] [rbp-48h] BYREF
  int v38; // [rsp+34h] [rbp-44h]
  int v39; // [rsp+38h] [rbp-40h]
  unsigned int v40; // [rsp+3Ch] [rbp-3Ch]
  unsigned int v41; // [rsp+40h] [rbp-38h]
  __int128 v42; // [rsp+48h] [rbp-30h] BYREF
  __m128i v43; // [rsp+58h] [rbp-20h]
  int v44; // [rsp+68h] [rbp-10h]

  if ( a1 )
  {
    if ( a2 )
    {
      if ( a3 )
      {
        v8 = *(_QWORD *)(a1 + 8);
        if ( v8 )
        {
          v9 = *a3;
          v10 = *(_QWORD *)(v8 + 4408);
          v40 = v9;
          v11 = v9;
          v37 = -1;
          if ( v9 == -1 )
            v11 = 0;
          v12 = -1;
          v13 = v11;
          v38 = *(_DWORD *)(v8 + 4464);
          v14 = -2147418113;
          v41 = v11;
          v15 = *(_DWORD **)(v10 + 16);
          if ( v9 == -1 )
            v13 = 0;
          v16 = 3;
          if ( v9 != -1 )
            v16 = 1;
          v17 = *(_DWORD *)(v10 + 8) == 0;
          v39 = (unsigned __int8)(63
                                - ((unsigned __int8)((11 * BYTE2(v13)
                                                    + 30 * (unsigned __int8)v13
                                                    + 59 * (unsigned int)BYTE1(v13))
                                                   / 0x64) >> 2));
          v18 = (unsigned int *)(v10 + 4);
          if ( v17 )
            v18 = (unsigned int *)v10;
          v19 = *v18;
          for ( i = 0; i < v19; ++i )
          {
            if ( *v15 == v16 && v15[6] )
            {
              if ( v16 == 1 )
              {
                if ( v38 )
                {
                  if ( v15[2] == v13 )
                  {
                    v14 = 0;
                    v12 = i;
                    v15[5] = 0;
LABEL_25:
                    v15[8] = a5;
LABEL_32:
                    ++v12;
                    goto LABEL_33;
                  }
                }
                else if ( v15[3] == v39 )
                {
                  v14 = 0;
                  v37 = i;
                  v15[5] = 0;
                  v12 = i;
                }
              }
              else if ( !v15[4] )
              {
                v14 = 0;
                v37 = i;
                v12 = i;
              }
            }
            if ( !v14 )
              goto LABEL_25;
            v15 += 9;
          }
          if ( i == v19 )
          {
            v36 = 0;
            v21 = BrushCache::AddBrushEntry(v10, &v37, v16, v13, 0);
            v12 = v37;
            if ( !v21 )
            {
              v14 = 1;
              goto LABEL_32;
            }
          }
LABEL_33:
          if ( v40 != -1 && v14 <= 1 )
          {
            v22 = *(_QWORD *)(v8 + 4408);
            v23 = *(_QWORD *)(v22 + 16);
            if ( v23 )
            {
              v24 = *(_DWORD *)(v22 + 4);
              if ( v24 )
              {
                v25 = v12 - 1;
                if ( !*(_DWORD *)(v22 + 8) )
                  v24 = *(_DWORD *)v22;
                if ( (unsigned int)v25 < v24 )
                {
                  v26 = *(_OWORD *)(v23 + 36 * v25);
                  v27 = *(__m128i *)(v23 + 36 * v25 + 16);
                  v44 = *(_DWORD *)(v23 + 36 * v25 + 32);
                  v42 = v26;
                  v43 = v27;
                  if ( !v14 )
                  {
                    v28 = _mm_srli_si128(v27, 8).m128i_u64[0];
                    if ( !HIDWORD(v28) || HIDWORD(v28) == a4 )
                    {
                      v29 = 0;
                      v30 = 0;
                      goto LABEL_47;
                    }
                  }
                  v31 = (struct _BRUSHINFO *)LocalAlloc(0x40u, 0x90u);
                  v29 = v31;
                  if ( v31 )
                  {
                    if ( !(unsigned int)BSetupBRUSHINFOForSolidBrush((struct _DEVOBJ *)a1, v32, v12, v41, v31, v36) )
                    {
                      v33 = 0;
LABEL_57:
                      LocalFree(v29);
                      return v33;
                    }
                    v30 = 1;
                    *((_DWORD *)v29 + 2) = 1;
LABEL_47:
                    v33 = BDwnldAndOrActivatePattern(a1, a2, v29, &v42, a4);
                    if ( v33 )
                    {
                      if ( v30 )
                      {
                        BrushCache::BSetDownloadType(*(_QWORD *)(v8 + 4408), v12, a4);
                        BrushCache::BSetDownloadedFlag(*(BrushCache **)(v8 + 4408), v12, v34);
                        *(_DWORD *)(a2 + 40) = a4;
                        *(_DWORD *)(a2 + 36) = a4 != 0 ? 11 : 22;
                      }
                      else if ( a4 == 1 && v43.m128i_i32[3] == 1 )
                      {
                        *(_DWORD *)(a2 + 40) = 1;
                        *(_DWORD *)(a2 + 36) = 11;
                      }
                      else
                      {
                        *(_QWORD *)(a2 + 36) = 22;
                      }
                    }
                    if ( !v29 )
                      return v33;
                    goto LABEL_57;
                  }
                }
              }
            }
          }
          return 0;
        }
      }
    }
  }
  SetLastError(0xDu);
  return 0;
}

```

## disassembly

```asm
0x18006625c  mov     [rsp-40h+arg_0], rcx
0x180066261  push    rbp
0x180066262  push    rbx
0x180066263  push    rsi
0x180066264  push    rdi
0x180066265  push    r12
0x180066267  push    r13
0x180066269  push    r14
0x18006626b  push    r15
0x18006626d  mov     rbp, rsp
0x180066270  sub     rsp, 78h
0x180066274  mov     r15d, r9d
0x180066277  mov     r14, rdx
0x18006627a  mov     r12, rcx
0x18006627d  test    rcx, rcx
0x180066280  jz      loc_18006656A
0x180066286  test    rdx, rdx
0x180066289  jz      loc_18006656A
0x18006628f  test    r8, r8
0x180066292  jz      loc_18006656A
0x180066298  mov     r13, [rcx+8]
0x18006629c  test    r13, r13
0x18006629f  jz      loc_18006656A
0x1800662a5  mov     ecx, [r8]
0x1800662a8  xor     eax, eax
0x1800662aa  mov     r11, [r13+1138h]
0x1800662b1  or      r8d, 0FFFFFFFFh
0x1800662b5  cmp     ecx, r8d
0x1800662b8  mov     [rbp+var_3C], ecx
0x1800662bb  mov     edx, ecx
0x1800662bd  mov     [rbp+var_48], r8d
0x1800662c1  cmovz   edx, eax
0x1800662c4  mov     edi, r8d
0x1800662c7  mov     eax, [r13+1170h]
0x1800662ce  mov     esi, edx
0x1800662d0  mov     [rbp+var_44], eax
0x1800662d3  mov     rbx, 0FFFFFFFF8000FFFFh
0x1800662da  xor     eax, eax
0x1800662dc  mov     [rbp+var_38], edx
0x1800662df  cmp     ecx, r8d
0x1800662e2  mov     r8, [r11+10h]
0x1800662e6  cmovz   esi, eax
0x1800662e9  mov     eax, 1
0x1800662ee  lea     r10d, [rax+2]
0x1800662f2  cmovnz  r10d, eax
0x1800662f6  mov     eax, esi
0x1800662f8  shr     eax, 8
0x1800662fb  movzx   eax, al
0x1800662fe  imul    edx, eax, 3Bh ; ';'
0x180066301  movzx   eax, si
0x180066304  movzx   ecx, al
0x180066307  imul    eax, ecx, 1Eh
0x18006630a  add     edx, eax
0x18006630c  mov     eax, esi
0x18006630e  shr     eax, 10h
0x180066311  movzx   eax, al
0x180066314  imul    ecx, eax, 0Bh
0x180066317  mov     eax, 51EB851Fh
0x18006631c  add     edx, ecx
0x18006631e  mul     edx
0x180066320  mov     eax, 3Fh ; '?'
0x180066325  shr     edx, 5
0x180066328  shr     dl, 2
0x18006632b  sub     al, dl
0x18006632d  cmp     dword ptr [r11+8], 0
0x180066332  movzx   eax, al
0x180066335  mov     [rbp+var_40], eax
0x180066338  lea     rax, [r11+4]
0x18006633c  jnz     short loc_180066341
0x18006633e  mov     rax, r11
0x180066341  mov     r9d, [rax]
0x180066344  xor     edx, edx
0x180066346  cmp     edx, r9d
0x180066349  jnb     loc_1800663CF
0x18006634f  cmp     [r8], r10d
0x180066352  jnz     short loc_180066380
0x180066354  cmp     dword ptr [r8+18h], 0
0x180066359  jz      short loc_180066380
0x18006635b  mov     ecx, r10d
0x18006635e  test    r10d, r10d
0x180066361  jz      short loc_1800663C0
0x180066363  sub     ecx, 1
0x180066366  jz      short loc_18006638D
0x180066368  sub     ecx, 1
0x18006636b  jz      short loc_18006638D
0x18006636d  cmp     ecx, 1
0x180066370  jnz     short loc_180066380
0x180066372  cmp     dword ptr [r8+10h], 0
0x180066377  jnz     short loc_180066380
0x180066379  xor     ebx, ebx
0x18006637b  mov     [rbp+var_48], edx
0x18006637e  mov     edi, edx
0x180066380  test    rbx, rbx
0x180066383  jz      short loc_1800663A1
0x180066385  inc     edx
0x180066387  add     r8, 24h ; '$'
0x18006638b  jmp     short loc_180066346
0x18006638d  cmp     [rbp+var_44], 0
0x180066391  jz      short loc_1800663AA
0x180066393  cmp     [r8+8], esi
0x180066397  jnz     short loc_180066380
0x180066399  xor     ebx, ebx
0x18006639b  mov     edi, edx
0x18006639d  mov     [r8+14h], ebx
0x1800663a1  mov     eax, [rbp+arg_20]
0x1800663a4  mov     [r8+20h], eax
0x1800663a8  jmp     short loc_18006640B
0x1800663aa  mov     eax, [rbp+var_40]
0x1800663ad  cmp     [r8+0Ch], eax
0x1800663b1  jnz     short loc_180066380
0x1800663b3  xor     ebx, ebx
0x1800663b5  mov     [rbp+var_48], edx
0x1800663b8  mov     [r8+14h], ebx
0x1800663bc  mov     edi, edx
0x1800663be  jmp     short loc_180066380
0x1800663c0  or      edi, 0FFFFFFFFh
0x1800663c3  mov     rbx, 0FFFFFFFF8000FFFFh
0x1800663ca  mov     [rbp+var_48], edi
0x1800663cd  jmp     short loc_180066385
0x1800663cf  jnz     short loc_180066400
0x1800663d1  mov     [rsp+78h+var_50], 0
0x1800663d9  lea     rdx, [rbp+var_48]
0x1800663dd  mov     r9d, esi
0x1800663e0  mov     dword ptr [rsp+78h+var_58], 0
0x1800663e8  mov     r8d, r10d
0x1800663eb  mov     rcx, r11
0x1800663ee  call    ?AddBrushEntry@BrushCache@@AEAA_JPEAKW4BRUSHTYPE@@KKK@Z; BrushCache::AddBrushEntry(ulong *,BRUSHTYPE,ulong,ulong,ulong)
0x1800663f3  mov     edi, [rbp+var_48]
0x1800663f6  test    rax, rax
0x1800663f9  jnz     short loc_180066400
0x1800663fb  lea     ebx, [rax+1]
0x1800663fe  jmp     short loc_18006640B
0x180066400  test    rbx, rbx
0x180066403  jz      short loc_18006640B
0x180066405  cmp     rbx, 1
0x180066409  jnz     short loc_18006640D
0x18006640b  inc     edi
0x18006640d  cmp     [rbp+var_3C], 0FFFFFFFFh
0x180066411  jz      loc_180066564
0x180066417  cmp     rbx, 1
0x18006641b  ja      loc_180066564
0x180066421  mov     rax, [r13+1138h]
0x180066428  mov     rcx, [rax+10h]
0x18006642c  test    rcx, rcx
0x18006642f  jz      loc_180066564
0x180066435  mov     edx, [rax+4]
0x180066438  test    edx, edx
0x18006643a  jz      loc_180066564
0x180066440  cmp     dword ptr [rax+8], 0
0x180066444  lea     r8d, [rdi-1]
0x180066448  jnz     short loc_18006644C
0x18006644a  mov     edx, [rax]
0x18006644c  cmp     r8d, edx
0x18006644f  jnb     loc_180066564
0x180066455  lea     rax, [r8+r8*8]
0x180066459  movups  xmm0, xmmword ptr [rcx+rax*4]
0x18006645d  movups  xmm1, xmmword ptr [rcx+rax*4+10h]
0x180066462  mov     eax, [rcx+rax*4+20h]
0x180066466  mov     [rbp+var_10], eax
0x180066469  movups  [rbp+var_30], xmm0
0x18006646d  movups  [rbp+var_20], xmm1
0x180066471  test    rbx, rbx
0x180066474  jnz     short loc_180066494
0x180066476  psrldq  xmm1, 8
0x18006647b  movq    rax, xmm1
0x180066480  shr     rax, 20h
0x180066484  test    eax, eax
0x180066486  jz      short loc_18006648D
0x180066488  cmp     eax, r15d
0x18006648b  jnz     short loc_180066494
0x18006648d  xor     esi, esi
0x18006648f  xor     r12d, r12d
0x180066492  jmp     short loc_1800664D4
0x180066494  mov     edx, 90h; uBytes
0x180066499  lea     ecx, [rdx-50h]; uFlags
0x18006649c  call    cs:__imp_LocalAlloc
0x1800664a2  mov     rsi, rax
0x1800664a5  test    rax, rax
0x1800664a8  jz      loc_180066564
0x1800664ae  mov     r9d, [rbp+var_38]; unsigned int
0x1800664b2  mov     r8d, edi; unsigned int
0x1800664b5  mov     rcx, r12; struct _DEVOBJ *
0x1800664b8  mov     [rsp+78h+var_58], rax; struct _BRUSHINFO *
0x1800664bd  call    ?BSetupBRUSHINFOForSolidBrush@@YAHPEAU_DEVOBJ@@JKKPEAU_BRUSHINFO@@J@Z; BSetupBRUSHINFOForSolidBrush(_DEVOBJ *,long,ulong,ulong,_BRUSHINFO *,long)
0x1800664c2  test    eax, eax
0x1800664c4  jz      loc_180066557
0x1800664ca  mov     r12d, 1
0x1800664d0  mov     [rsi+8], r12d
0x1800664d4  mov     rcx, [rbp+arg_0]
0x1800664d8  lea     r9, [rbp+var_30]
0x1800664dc  mov     r8, rsi
0x1800664df  mov     dword ptr [rsp+78h+var_58], r15d
0x1800664e4  mov     rdx, r14
0x1800664e7  call    ?BDwnldAndOrActivatePattern@@YAHPEAU_DEVOBJ@@PEAU_HPGLMARKER@@PEAU_BRUSHINFO@@PEAU_HPGL2BRUSH@@W4ERenderLanguage@@@Z; BDwnldAndOrActivatePattern(_DEVOBJ *,_HPGLMARKER *,_BRUSHINFO *,_HPGL2BRUSH *,ERenderLanguage)
0x1800664ec  mov     ebx, eax
0x1800664ee  test    eax, eax
0x1800664f0  jz      short loc_180066550
0x1800664f2  test    r12d, r12d
0x1800664f5  jz      short loc_18006652B
0x1800664f7  mov     rcx, [r13+1138h]
0x1800664fe  mov     r8d, r15d
0x180066501  mov     edx, edi
0x180066503  call    ?BSetDownloadType@BrushCache@@QEAAHKW4ERenderLanguage@@@Z; BrushCache::BSetDownloadType(ulong,ERenderLanguage)
0x180066508  mov     rcx, [r13+1138h]; this
0x18006650f  mov     edx, edi; unsigned int
0x180066511  call    ?BSetDownloadedFlag@BrushCache@@QEAAHKH@Z; BrushCache::BSetDownloadedFlag(ulong,int)
0x180066516  mov     [r14+28h], r15d
0x18006651a  neg     r15d
0x18006651d  sbb     eax, eax
0x18006651f  and     eax, 0FFFFFFF5h
0x180066522  add     eax, 16h
0x180066525  mov     [r14+24h], eax
0x180066529  jmp     short loc_180066550
0x18006652b  mov     eax, 1
0x180066530  cmp     r15d, eax
0x180066533  jnz     short loc_180066548
0x180066535  cmp     dword ptr [rbp+var_20+0Ch], eax
0x180066538  jnz     short loc_180066548
0x18006653a  mov     [r14+28h], eax
0x18006653e  mov     dword ptr [r14+24h], 0Bh
0x180066546  jmp     short loc_180066550
0x180066548  mov     qword ptr [r14+24h], 16h
0x180066550  test    rsi, rsi
0x180066553  jz      short loc_180066566
0x180066555  jmp     short loc_180066559
0x180066557  xor     ebx, ebx
0x180066559  mov     rcx, rsi; hMem
0x18006655c  call    cs:__imp_LocalFree
0x180066562  jmp     short loc_180066566
0x180066564  xor     ebx, ebx
0x180066566  mov     eax, ebx
0x180066568  jmp     short loc_180066577
0x18006656a  mov     ecx, 0Dh; dwErrCode
0x18006656f  call    cs:__imp_SetLastError
0x180066575  xor     eax, eax
0x180066577  add     rsp, 78h
0x18006657b  pop     r15
0x18006657d  pop     r14
0x18006657f  pop     r13
0x180066581  pop     r12
0x180066583  pop     rdi
0x180066584  pop     rsi
0x180066585  pop     rbx
0x180066586  pop     rbp
0x180066587  retn
```
