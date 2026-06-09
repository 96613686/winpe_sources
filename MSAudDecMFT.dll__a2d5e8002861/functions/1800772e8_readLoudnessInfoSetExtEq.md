# _readLoudnessInfoSetExtEq

- ea: `0x1800772e8`
- end: `0x180077569`
- name: `_readLoudnessInfoSetExtEq`
- size: `641`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180077570`

## callees

- `0x1800110c0`
- `0x18004d320`
- `0x18004dd14`
- `0x180077174`
- `0x1800772e8`
- `0x180096060`

## pseudocode

```c
__int64 __fastcall readLoudnessInfoSetExtEq(_DWORD *a1, unsigned __int8 *a2, __int64 a3)
{
  int v3; // esi
  unsigned __int8 v6; // al
  unsigned __int8 v7; // bl
  unsigned __int8 v8; // di
  __int64 v9; // r8
  unsigned __int8 v10; // al
  bool v11; // zf
  int v12; // r15d
  int v13; // esi
  char v14; // al
  int v15; // edi
  __int64 result; // rax
  int v17; // eax
  __int64 v18; // rbx
  __int128 v19; // xmm1
  int v20; // eax
  __int64 v21; // rcx
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  __int128 v26; // xmm0
  int v27; // esi
  char v28; // al
  int v29; // ebx
  int v30; // eax
  __int64 v31; // rdi
  __int128 v32; // xmm1
  int v33; // eax
  __int64 v34; // rcx
  __int128 v35; // xmm0
  __int128 v36; // xmm1
  __int128 v37; // xmm0
  __int128 v38; // xmm1
  __int128 v39; // xmm0
  __int128 Buf1; // [rsp+20h] [rbp-59h] BYREF
  __int128 v41; // [rsp+30h] [rbp-49h]
  __int128 v42; // [rsp+40h] [rbp-39h]
  __int128 v43; // [rsp+50h] [rbp-29h]
  __int128 v44; // [rsp+60h] [rbp-19h]
  __int128 v45; // [rsp+70h] [rbp-9h]
  __int128 v46; // [rsp+80h] [rbp+7h]
  int v47; // [rsp+90h] [rbp+17h]

  v3 = a2[2832];
  v6 = CDKreadBits(a1, 6, a3);
  v7 = a2[1];
  v8 = v6;
  a2[1] = v6;
  v10 = CDKreadBits(a1, 6, v9);
  v11 = a2[4] == v10;
  a2[4] = v10;
  v12 = v3 | (v7 != v8 || !v11);
  v13 = *a2;
  v14 = 12;
  if ( (unsigned __int8)(a2[1] + *a2) < 0xCu )
    v14 = a2[1] + *a2;
  v15 = 0;
  a2[2] = v14;
  while ( v15 < a2[1] )
  {
    memset_0(&Buf1, 0, 0x74u);
    result = readLoudnessInfo(a1, 1, &Buf1);
    if ( (_DWORD)result )
      return result;
    v17 = v13 + v15;
    if ( v13 + v15 < 12 )
    {
      v18 = v17;
      if ( !v12 )
        v12 = memcmp_0(&Buf1, &a2[116 * v17 + 8], 0x74u) != 0;
      v19 = v41;
      v20 = v47;
      v21 = 116 * v18;
      *(_OWORD *)&a2[v21 + 8] = Buf1;
      v22 = v42;
      *(_OWORD *)&a2[v21 + 24] = v19;
      v23 = v43;
      *(_OWORD *)&a2[v21 + 40] = v22;
      v24 = v44;
      *(_OWORD *)&a2[v21 + 56] = v23;
      v25 = v45;
      *(_OWORD *)&a2[v21 + 72] = v24;
      v26 = v46;
      *(_OWORD *)&a2[v21 + 88] = v25;
      *(_OWORD *)&a2[v21 + 104] = v26;
      *(_DWORD *)&a2[v21 + 120] = v20;
    }
    ++v15;
  }
  v27 = a2[3];
  v28 = 12;
  if ( (unsigned __int8)(a2[4] + a2[3]) < 0xCu )
    v28 = a2[4] + a2[3];
  v29 = 0;
  a2[5] = v28;
  while ( v29 < a2[4] )
  {
    memset_0(&Buf1, 0, 0x74u);
    result = readLoudnessInfo(a1, 1, &Buf1);
    if ( (_DWORD)result )
      return result;
    v30 = v27 + v29;
    if ( v27 + v29 < 12 )
    {
      v31 = v30;
      if ( !v12 )
        v12 = memcmp_0(&Buf1, &a2[116 * v30 + 1400], 0x74u) != 0;
      v32 = v41;
      v33 = v47;
      v34 = 116 * v31;
      *(_OWORD *)&a2[v34 + 1400] = Buf1;
      v35 = v42;
      *(_OWORD *)&a2[v34 + 1416] = v32;
      v36 = v43;
      *(_OWORD *)&a2[v34 + 1432] = v35;
      v37 = v44;
      *(_OWORD *)&a2[v34 + 1448] = v36;
      v38 = v45;
      *(_OWORD *)&a2[v34 + 1464] = v37;
      v39 = v46;
      *(_OWORD *)&a2[v34 + 1480] = v38;
      *(_OWORD *)&a2[v34 + 1496] = v39;
      *(_DWORD *)&a2[v34 + 1512] = v33;
    }
    ++v29;
  }
  a2[2832] = v12;
  return 0;
}

```

## disassembly

```asm
0x1800772e8  mov     [rsp-8+arg_10], rbx
0x1800772ed  mov     [rsp-8+arg_18], rsi
0x1800772f2  push    rbp
0x1800772f3  push    rdi
0x1800772f4  push    r12
0x1800772f6  push    r14
0x1800772f8  push    r15
0x1800772fa  lea     rbp, [rsp-37h]
0x1800772ff  sub     rsp, 0B0h
0x180077306  mov     rax, cs:__security_cookie
0x18007730d  xor     rax, rsp
0x180077310  mov     [rbp+57h+var_30], rax
0x180077314  movzx   esi, byte ptr [rdx+0B10h]
0x18007731b  mov     r14, rdx
0x18007731e  mov     r15d, 6
0x180077324  mov     r12, rcx
0x180077327  mov     edx, r15d
0x18007732a  call    CDKreadBits
0x18007732f  mov     bl, [r14+1]
0x180077333  mov     edi, eax
0x180077335  mov     edx, r15d
0x180077338  mov     [r14+1], dil
0x18007733c  mov     rcx, r12
0x18007733f  call    CDKreadBits
0x180077344  mov     cl, [r14+4]
0x180077348  xor     r15d, r15d
0x18007734b  cmp     cl, al
0x18007734d  mov     [r14+4], al
0x180077351  setnz   r15b
0x180077355  xor     eax, eax
0x180077357  cmp     bl, dil
0x18007735a  setnz   al
0x18007735d  or      r15d, eax
0x180077360  or      r15d, esi
0x180077363  movzx   esi, byte ptr [r14]
0x180077367  mov     al, sil
0x18007736a  add     al, [r14+1]
0x18007736e  movzx   ecx, al
0x180077371  mov     eax, 0Ch
0x180077376  cmp     ecx, eax
0x180077378  cmovb   eax, ecx
0x18007737b  xor     edi, edi
0x18007737d  mov     [r14+2], al
0x180077381  movzx   eax, byte ptr [r14+1]
0x180077386  cmp     edi, eax
0x180077388  jge     loc_18007743D
0x18007738e  xor     edx, edx; Val
0x180077390  lea     rcx, [rbp+57h+Buf1]; void *
0x180077394  lea     r8d, [rdx+74h]; Size
0x180077398  call    memset_0
0x18007739d  lea     r8, [rbp+57h+Buf1]
0x1800773a1  mov     edx, 1
0x1800773a6  mov     rcx, r12
0x1800773a9  call    _readLoudnessInfo
0x1800773ae  test    eax, eax
0x1800773b0  jnz     loc_180077540
0x1800773b6  lea     eax, [rsi+rdi]
0x1800773b9  cmp     eax, 0Ch
0x1800773bc  jge     short loc_180077436
0x1800773be  movsxd  rbx, eax
0x1800773c1  test    r15d, r15d
0x1800773c4  jnz     short loc_1800773E4
0x1800773c6  imul    rdx, rbx, 74h ; 't'
0x1800773ca  lea     r8d, [r15+74h]; Size
0x1800773ce  add     rdx, 8
0x1800773d2  lea     rcx, [rbp+57h+Buf1]; Buf1
0x1800773d6  add     rdx, r14; Buf2
0x1800773d9  call    memcmp_0
0x1800773de  test    eax, eax
0x1800773e0  setnz   r15b
0x1800773e4  movaps  xmm0, [rbp+57h+Buf1]
0x1800773e8  movaps  xmm1, [rbp+57h+var_A0]
0x1800773ec  mov     eax, [rbp+57h+var_40]
0x1800773ef  imul    rcx, rbx, 74h ; 't'
0x1800773f3  movups  xmmword ptr [rcx+r14+8], xmm0
0x1800773f9  movaps  xmm0, [rbp+57h+var_90]
0x1800773fd  movups  xmmword ptr [rcx+r14+18h], xmm1
0x180077403  movaps  xmm1, [rbp+57h+var_80]
0x180077407  movups  xmmword ptr [rcx+r14+28h], xmm0
0x18007740d  movaps  xmm0, [rbp+57h+var_70]
0x180077411  movups  xmmword ptr [rcx+r14+38h], xmm1
0x180077417  movaps  xmm1, [rbp+57h+var_60]
0x18007741b  movups  xmmword ptr [rcx+r14+48h], xmm0
0x180077421  movaps  xmm0, [rbp+57h+var_50]
0x180077425  movups  xmmword ptr [rcx+r14+58h], xmm1
0x18007742b  movups  xmmword ptr [rcx+r14+68h], xmm0
0x180077431  mov     [rcx+r14+78h], eax
0x180077436  inc     edi
0x180077438  jmp     loc_180077381
0x18007743d  movzx   esi, byte ptr [r14+3]
0x180077442  mov     al, sil
0x180077445  add     al, [r14+4]
0x180077449  movzx   ecx, al
0x18007744c  mov     eax, 0Ch
0x180077451  cmp     ecx, eax
0x180077453  cmovb   eax, ecx
0x180077456  xor     ebx, ebx
0x180077458  mov     [r14+5], al
0x18007745c  movzx   eax, byte ptr [r14+4]
0x180077461  cmp     ebx, eax
0x180077463  jge     loc_180077537
0x180077469  xor     edx, edx; Val
0x18007746b  lea     rcx, [rbp+57h+Buf1]; void *
0x18007746f  lea     r8d, [rdx+74h]; Size
0x180077473  call    memset_0
0x180077478  lea     r8, [rbp+57h+Buf1]
0x18007747c  mov     edx, 1
0x180077481  mov     rcx, r12
0x180077484  call    _readLoudnessInfo
0x180077489  test    eax, eax
0x18007748b  jnz     loc_180077540
0x180077491  lea     eax, [rsi+rbx]
0x180077494  cmp     eax, 0Ch
0x180077497  jge     loc_180077530
0x18007749d  movsxd  rdi, eax
0x1800774a0  test    r15d, r15d
0x1800774a3  jnz     short loc_1800774C6
0x1800774a5  imul    rdx, rdi, 74h ; 't'
0x1800774a9  lea     r8d, [r15+74h]; Size
0x1800774ad  add     rdx, 578h
0x1800774b4  lea     rcx, [rbp+57h+Buf1]; Buf1
0x1800774b8  add     rdx, r14; Buf2
0x1800774bb  call    memcmp_0
0x1800774c0  test    eax, eax
0x1800774c2  setnz   r15b
0x1800774c6  movaps  xmm0, [rbp+57h+Buf1]
0x1800774ca  movaps  xmm1, [rbp+57h+var_A0]
0x1800774ce  mov     eax, [rbp+57h+var_40]
0x1800774d1  imul    rcx, rdi, 74h ; 't'
0x1800774d5  movups  xmmword ptr [rcx+r14+578h], xmm0
0x1800774de  movaps  xmm0, [rbp+57h+var_90]
0x1800774e2  movups  xmmword ptr [rcx+r14+588h], xmm1
0x1800774eb  movaps  xmm1, [rbp+57h+var_80]
0x1800774ef  movups  xmmword ptr [rcx+r14+598h], xmm0
0x1800774f8  movaps  xmm0, [rbp+57h+var_70]
0x1800774fc  movups  xmmword ptr [rcx+r14+5A8h], xmm1
0x180077505  movaps  xmm1, [rbp+57h+var_60]
0x180077509  movups  xmmword ptr [rcx+r14+5B8h], xmm0
0x180077512  movaps  xmm0, [rbp+57h+var_50]
0x180077516  movups  xmmword ptr [rcx+r14+5C8h], xmm1
0x18007751f  movups  xmmword ptr [rcx+r14+5D8h], xmm0
0x180077528  mov     [rcx+r14+5E8h], eax
0x180077530  inc     ebx
0x180077532  jmp     loc_18007745C
0x180077537  mov     [r14+0B10h], r15b
0x18007753e  xor     eax, eax
0x180077540  mov     rcx, [rbp+57h+var_30]
0x180077544  xor     rcx, rsp; StackCookie
0x180077547  call    __security_check_cookie
0x18007754c  lea     r11, [rsp+0D0h+var_20]
0x180077554  mov     rbx, [r11+40h]
0x180077558  mov     rsi, [r11+48h]
0x18007755c  mov     rsp, r11
0x18007755f  pop     r15
0x180077561  pop     r14
0x180077563  pop     r12
0x180077565  pop     rdi
0x180077566  pop     rbp
0x180077567  retn
```
