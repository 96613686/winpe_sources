# CreateAndDwnldSolidBrushForMono(_DEVOBJ *,_HPGLMARKER *,_BRUSHOBJ *,ERenderLanguage,int)

- ea: `0x180067a10`
- end: `0x180067d4f`
- name: `?CreateAndDwnldSolidBrushForMono@@YAHPEAU_DEVOBJ@@PEAU_HPGLMARKER@@PEAU_BRUSHOBJ@@W4ERenderLanguage@@H@Z`
- size: `831`
- prototype: `__int64 __fastcall(__int64, _DWORD *, unsigned int *, unsigned int, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180067860`
- `0x180068f10`

## callees

- `0x1800677a4`
- `0x18006790c`
- `0x180067a10`
- `0x180069438`
- `0x1800695d8`
- `0x180069610`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180067d16`
- `KERNEL32!LocalFree` at `0x180067d16`
- `KERNEL32!LocalAlloc` at `0x180067c50`
- `KERNEL32!LocalAlloc` at `0x180067c50`
- `KERNEL32!SetLastError` at `0x180067d2f`
- `KERNEL32!SetLastError` at `0x180067d2f`

## pseudocode

```c
__int64 __fastcall CreateAndDwnldSolidBrushForMono(__int64 a1, _DWORD *a2, unsigned int *a3, int a4, int a5)
{
  __int64 v8; // r13
  unsigned int v9; // ecx
  __int64 v10; // r11
  unsigned int v11; // edx
  int v12; // edi
  int v13; // esi
  unsigned __int64 v14; // rbx
  _DWORD *v15; // r8
  int v16; // r10d
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
  __int64 v32; // rdx
  unsigned int v33; // ebx
  int v35; // [rsp+30h] [rbp-48h] BYREF
  int v36; // [rsp+34h] [rbp-44h]
  int v37; // [rsp+38h] [rbp-40h]
  unsigned int v38; // [rsp+3Ch] [rbp-3Ch]
  unsigned int v39; // [rsp+40h] [rbp-38h]
  __int128 v40; // [rsp+48h] [rbp-30h] BYREF
  __m128i v41; // [rsp+58h] [rbp-20h]
  int v42; // [rsp+68h] [rbp-10h]

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
          v38 = v9;
          v11 = v9;
          v35 = -1;
          if ( v9 == -1 )
            v11 = 0;
          v12 = -1;
          v13 = v11;
          v36 = *(_DWORD *)(v8 + 4464);
          v14 = -2147418113;
          v39 = v11;
          v15 = *(_DWORD **)(v10 + 16);
          if ( v9 == -1 )
            v13 = 0;
          v16 = 3;
          if ( v9 != -1 )
            v16 = 1;
          v17 = *(_DWORD *)(v10 + 8) == 0;
          v37 = (unsigned __int8)(63
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
                if ( v36 )
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
                else if ( v15[3] == v37 )
                {
                  v14 = 0;
                  v35 = i;
                  v15[5] = 0;
                  v12 = i;
                }
              }
              else if ( !v15[4] )
              {
                v14 = 0;
                v35 = i;
                v12 = i;
              }
            }
            if ( !v14 )
              goto LABEL_25;
            v15 += 9;
          }
          if ( i == v19 )
          {
            v21 = BrushCache::AddBrushEntry((BrushCache *)v10, &v35, v16, v13, 0, 0);
            v12 = v35;
            if ( !v21 )
            {
              v14 = 1;
              goto LABEL_32;
            }
          }
LABEL_33:
          if ( v38 != -1 && v14 <= 1 )
          {
            v22 = *(_QWORD *)(v8 + 4408);
            v23 = *(_QWORD *)(v22 + 16);
            if ( v23 )
            {
              v24 = *(_DWORD *)(v22 + 4);
              if ( v24 )
              {
                v25 = (unsigned int)(v12 - 1);
                if ( !*(_DWORD *)(v22 + 8) )
                  v24 = *(_DWORD *)v22;
                if ( (unsigned int)v25 < v24 )
                {
                  v26 = *(_OWORD *)(v23 + 36 * v25);
                  v27 = *(__m128i *)(v23 + 36 * v25 + 16);
                  v42 = *(_DWORD *)(v23 + 36 * v25 + 32);
                  v40 = v26;
                  v41 = v27;
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
                    if ( !BSetupBRUSHINFOForSolidBrush((struct _DEVOBJ *)a1, v32, v12, v39, v31) )
                    {
                      v33 = 0;
LABEL_57:
                      LocalFree(v29);
                      return v33;
                    }
                    v30 = 1;
                    *((_DWORD *)v29 + 2) = 1;
LABEL_47:
                    v33 = BDwnldAndOrActivatePattern(a1, a2, (__int64)v29, &v40, a4);
                    if ( v33 )
                    {
                      if ( v30 )
                      {
                        BrushCache::BSetDownloadType(*(_QWORD *)(v8 + 4408), v12, a4);
                        BrushCache::BSetDownloadedFlag(*(BrushCache **)(v8 + 4408), v12);
                        a2[10] = a4;
                        a2[9] = a4 != 0 ? 11 : 22;
                      }
                      else if ( a4 == 1 && v41.m128i_i32[3] == 1 )
                      {
                        a2[10] = 1;
                        a2[9] = 11;
                      }
                      else
                      {
                        *(_QWORD *)(a2 + 9) = 22;
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
0x180067a10  mov     [rsp-40h+arg_0], rcx
0x180067a15  push    rbp
0x180067a16  push    rbx
0x180067a17  push    rsi
0x180067a18  push    rdi
0x180067a19  push    r12
0x180067a1b  push    r13
0x180067a1d  push    r14
0x180067a1f  push    r15
0x180067a21  mov     rbp, rsp
0x180067a24  sub     rsp, 78h
0x180067a28  mov     r15d, r9d
0x180067a2b  mov     r14, rdx
0x180067a2e  mov     r12, rcx
0x180067a31  test    rcx, rcx
0x180067a34  jz      loc_180067D2A
0x180067a3a  test    rdx, rdx
0x180067a3d  jz      loc_180067D2A
0x180067a43  test    r8, r8
0x180067a46  jz      loc_180067D2A
0x180067a4c  mov     r13, [rcx+8]
0x180067a50  test    r13, r13
0x180067a53  jz      loc_180067D2A
0x180067a59  mov     ecx, [r8]
0x180067a5c  xor     eax, eax
0x180067a5e  mov     r11, [r13+1138h]
0x180067a65  or      r8d, 0FFFFFFFFh
0x180067a69  cmp     ecx, r8d
0x180067a6c  mov     [rbp+var_3C], ecx
0x180067a6f  mov     edx, ecx
0x180067a71  mov     [rbp+var_48], r8d
0x180067a75  cmovz   edx, eax
0x180067a78  mov     edi, r8d
0x180067a7b  mov     eax, [r13+1170h]
0x180067a82  mov     esi, edx
0x180067a84  mov     [rbp+var_44], eax
0x180067a87  mov     rbx, 0FFFFFFFF8000FFFFh
0x180067a8e  xor     eax, eax
0x180067a90  mov     [rbp+var_38], edx
0x180067a93  cmp     ecx, r8d
0x180067a96  mov     r8, [r11+10h]
0x180067a9a  cmovz   esi, eax
0x180067a9d  mov     eax, 1
0x180067aa2  lea     r10d, [rax+2]
0x180067aa6  cmovnz  r10d, eax
0x180067aaa  mov     eax, esi
0x180067aac  shr     eax, 8
0x180067aaf  movzx   eax, al
0x180067ab2  imul    edx, eax, 3Bh ; ';'
0x180067ab5  movzx   eax, si
0x180067ab8  movzx   ecx, al
0x180067abb  imul    eax, ecx, 1Eh
0x180067abe  add     edx, eax
0x180067ac0  mov     eax, esi
0x180067ac2  shr     eax, 10h
0x180067ac5  movzx   eax, al
0x180067ac8  imul    ecx, eax, 0Bh
0x180067acb  mov     eax, 51EB851Fh
0x180067ad0  add     edx, ecx
0x180067ad2  mul     edx
0x180067ad4  mov     eax, 3Fh ; '?'
0x180067ad9  shr     edx, 5
0x180067adc  shr     dl, 2
0x180067adf  sub     al, dl
0x180067ae1  cmp     dword ptr [r11+8], 0
0x180067ae6  movzx   eax, al
0x180067ae9  mov     [rbp+var_40], eax
0x180067aec  lea     rax, [r11+4]
0x180067af0  jnz     short loc_180067AF5
0x180067af2  mov     rax, r11
0x180067af5  mov     r9d, [rax]
0x180067af8  xor     edx, edx
0x180067afa  cmp     edx, r9d
0x180067afd  jnb     loc_180067B83
0x180067b03  cmp     [r8], r10d
0x180067b06  jnz     short loc_180067B34
0x180067b08  cmp     dword ptr [r8+18h], 0
0x180067b0d  jz      short loc_180067B34
0x180067b0f  mov     ecx, r10d
0x180067b12  test    r10d, r10d
0x180067b15  jz      short loc_180067B74
0x180067b17  sub     ecx, 1
0x180067b1a  jz      short loc_180067B41
0x180067b1c  sub     ecx, 1
0x180067b1f  jz      short loc_180067B41
0x180067b21  cmp     ecx, 1
0x180067b24  jnz     short loc_180067B34
0x180067b26  cmp     dword ptr [r8+10h], 0
0x180067b2b  jnz     short loc_180067B34
0x180067b2d  xor     ebx, ebx
0x180067b2f  mov     [rbp+var_48], edx
0x180067b32  mov     edi, edx
0x180067b34  test    rbx, rbx
0x180067b37  jz      short loc_180067B55
0x180067b39  inc     edx
0x180067b3b  add     r8, 24h ; '$'
0x180067b3f  jmp     short loc_180067AFA
0x180067b41  cmp     [rbp+var_44], 0
0x180067b45  jz      short loc_180067B5E
0x180067b47  cmp     [r8+8], esi
0x180067b4b  jnz     short loc_180067B34
0x180067b4d  xor     ebx, ebx
0x180067b4f  mov     edi, edx
0x180067b51  mov     [r8+14h], ebx
0x180067b55  mov     eax, [rbp+arg_20]
0x180067b58  mov     [r8+20h], eax
0x180067b5c  jmp     short loc_180067BBF
0x180067b5e  mov     eax, [rbp+var_40]
0x180067b61  cmp     [r8+0Ch], eax
0x180067b65  jnz     short loc_180067B34
0x180067b67  xor     ebx, ebx
0x180067b69  mov     [rbp+var_48], edx
0x180067b6c  mov     [r8+14h], ebx
0x180067b70  mov     edi, edx
0x180067b72  jmp     short loc_180067B34
0x180067b74  or      edi, 0FFFFFFFFh
0x180067b77  mov     rbx, 0FFFFFFFF8000FFFFh
0x180067b7e  mov     [rbp+var_48], edi
0x180067b81  jmp     short loc_180067B39
0x180067b83  jnz     short loc_180067BB4
0x180067b85  mov     [rsp+78h+var_50], 0
0x180067b8d  lea     rdx, [rbp+var_48]
0x180067b91  mov     r9d, esi
0x180067b94  mov     dword ptr [rsp+78h+var_58], 0
0x180067b9c  mov     r8d, r10d
0x180067b9f  mov     rcx, r11
0x180067ba2  call    ?AddBrushEntry@BrushCache@@AEAA_JPEAKW4BRUSHTYPE@@KKK@Z; BrushCache::AddBrushEntry(ulong *,BRUSHTYPE,ulong,ulong,ulong)
0x180067ba7  mov     edi, [rbp+var_48]
0x180067baa  test    rax, rax
0x180067bad  jnz     short loc_180067BB4
0x180067baf  lea     ebx, [rax+1]
0x180067bb2  jmp     short loc_180067BBF
0x180067bb4  test    rbx, rbx
0x180067bb7  jz      short loc_180067BBF
0x180067bb9  cmp     rbx, 1
0x180067bbd  jnz     short loc_180067BC1
0x180067bbf  inc     edi
0x180067bc1  cmp     [rbp+var_3C], 0FFFFFFFFh
0x180067bc5  jz      loc_180067D24
0x180067bcb  cmp     rbx, 1
0x180067bcf  ja      loc_180067D24
0x180067bd5  mov     rax, [r13+1138h]
0x180067bdc  mov     rcx, [rax+10h]
0x180067be0  test    rcx, rcx
0x180067be3  jz      loc_180067D24
0x180067be9  mov     edx, [rax+4]
0x180067bec  test    edx, edx
0x180067bee  jz      loc_180067D24
0x180067bf4  cmp     dword ptr [rax+8], 0
0x180067bf8  lea     r8d, [rdi-1]
0x180067bfc  jnz     short loc_180067C00
0x180067bfe  mov     edx, [rax]
0x180067c00  cmp     r8d, edx
0x180067c03  jnb     loc_180067D24
0x180067c09  lea     rax, [r8+r8*8]
0x180067c0d  movups  xmm0, xmmword ptr [rcx+rax*4]
0x180067c11  movups  xmm1, xmmword ptr [rcx+rax*4+10h]
0x180067c16  mov     eax, [rcx+rax*4+20h]
0x180067c1a  mov     [rbp+var_10], eax
0x180067c1d  movups  [rbp+var_30], xmm0
0x180067c21  movups  [rbp+var_20], xmm1
0x180067c25  test    rbx, rbx
0x180067c28  jnz     short loc_180067C48
0x180067c2a  psrldq  xmm1, 8
0x180067c2f  movq    rax, xmm1
0x180067c34  shr     rax, 20h
0x180067c38  test    eax, eax
0x180067c3a  jz      short loc_180067C41
0x180067c3c  cmp     eax, r15d
0x180067c3f  jnz     short loc_180067C48
0x180067c41  xor     esi, esi
0x180067c43  xor     r12d, r12d
0x180067c46  jmp     short loc_180067C8E
0x180067c48  mov     edx, 90h; uBytes
0x180067c4d  lea     ecx, [rdx-50h]; uFlags
0x180067c50  call    cs:__imp_LocalAlloc
0x180067c57  nop     dword ptr [rax+rax+00h]
0x180067c5c  mov     rsi, rax
0x180067c5f  test    rax, rax
0x180067c62  jz      loc_180067D24
0x180067c68  mov     r9d, [rbp+var_38]; unsigned int
0x180067c6c  mov     r8d, edi; unsigned int
0x180067c6f  mov     rcx, r12; struct _DEVOBJ *
0x180067c72  mov     [rsp+78h+var_58], rax; struct _BRUSHINFO *
0x180067c77  call    ?BSetupBRUSHINFOForSolidBrush@@YAHPEAU_DEVOBJ@@JKKPEAU_BRUSHINFO@@J@Z; BSetupBRUSHINFOForSolidBrush(_DEVOBJ *,long,ulong,ulong,_BRUSHINFO *,long)
0x180067c7c  test    eax, eax
0x180067c7e  jz      loc_180067D11
0x180067c84  mov     r12d, 1
0x180067c8a  mov     [rsi+8], r12d
0x180067c8e  mov     rcx, [rbp+arg_0]
0x180067c92  lea     r9, [rbp+var_30]
0x180067c96  mov     r8, rsi
0x180067c99  mov     dword ptr [rsp+78h+var_58], r15d
0x180067c9e  mov     rdx, r14
0x180067ca1  call    ?BDwnldAndOrActivatePattern@@YAHPEAU_DEVOBJ@@PEAU_HPGLMARKER@@PEAU_BRUSHINFO@@PEAU_HPGL2BRUSH@@W4ERenderLanguage@@@Z; BDwnldAndOrActivatePattern(_DEVOBJ *,_HPGLMARKER *,_BRUSHINFO *,_HPGL2BRUSH *,ERenderLanguage)
0x180067ca6  mov     ebx, eax
0x180067ca8  test    eax, eax
0x180067caa  jz      short loc_180067D0A
0x180067cac  test    r12d, r12d
0x180067caf  jz      short loc_180067CE5
0x180067cb1  mov     rcx, [r13+1138h]
0x180067cb8  mov     r8d, r15d
0x180067cbb  mov     edx, edi
0x180067cbd  call    ?BSetDownloadType@BrushCache@@QEAAHKW4ERenderLanguage@@@Z; BrushCache::BSetDownloadType(ulong,ERenderLanguage)
0x180067cc2  mov     rcx, [r13+1138h]; this
0x180067cc9  mov     edx, edi; unsigned int
0x180067ccb  call    ?BSetDownloadedFlag@BrushCache@@QEAAHKH@Z; BrushCache::BSetDownloadedFlag(ulong,int)
0x180067cd0  mov     [r14+28h], r15d
0x180067cd4  neg     r15d
0x180067cd7  sbb     eax, eax
0x180067cd9  and     eax, 0FFFFFFF5h
0x180067cdc  add     eax, 16h
0x180067cdf  mov     [r14+24h], eax
0x180067ce3  jmp     short loc_180067D0A
0x180067ce5  mov     eax, 1
0x180067cea  cmp     r15d, eax
0x180067ced  jnz     short loc_180067D02
0x180067cef  cmp     dword ptr [rbp+var_20+0Ch], eax
0x180067cf2  jnz     short loc_180067D02
0x180067cf4  mov     [r14+28h], eax
0x180067cf8  mov     dword ptr [r14+24h], 0Bh
0x180067d00  jmp     short loc_180067D0A
0x180067d02  mov     qword ptr [r14+24h], 16h
0x180067d0a  test    rsi, rsi
0x180067d0d  jz      short loc_180067D26
0x180067d0f  jmp     short loc_180067D13
0x180067d11  xor     ebx, ebx
0x180067d13  mov     rcx, rsi; hMem
0x180067d16  call    cs:__imp_LocalFree
0x180067d1d  nop     dword ptr [rax+rax+00h]
0x180067d22  jmp     short loc_180067D26
0x180067d24  xor     ebx, ebx
0x180067d26  mov     eax, ebx
0x180067d28  jmp     short loc_180067D3D
0x180067d2a  mov     ecx, 0Dh; dwErrCode
0x180067d2f  call    cs:__imp_SetLastError
0x180067d36  nop     dword ptr [rax+rax+00h]
0x180067d3b  xor     eax, eax
0x180067d3d  add     rsp, 78h
0x180067d41  pop     r15
0x180067d43  pop     r14
0x180067d45  pop     r13
0x180067d47  pop     r12
0x180067d49  pop     rdi
0x180067d4a  pop     rsi
0x180067d4b  pop     rbx
0x180067d4c  pop     rbp
0x180067d4d  retn
```
