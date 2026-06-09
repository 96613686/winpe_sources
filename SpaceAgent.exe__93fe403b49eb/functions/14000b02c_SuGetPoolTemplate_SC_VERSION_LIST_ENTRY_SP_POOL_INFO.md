# SuGetPoolTemplate(_SC_VERSION,_LIST_ENTRY *,_SP_POOL_INFO * *)

- ea: `0x14000b02c`
- end: `0x14000b34e`
- name: `?SuGetPoolTemplate@@YAHW4_SC_VERSION@@PEAU_LIST_ENTRY@@PEAPEAU_SP_POOL_INFO@@@Z`
- size: `802`
- prototype: `__int64 __fastcall(__int64, __int64 *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140014e74`

## callees

- `0x14000a440`
- `0x14000b02c`
- `0x14000b7ec`
- `0x14000d29c`

## import_xrefs

- `KERNEL32!LocalFree` at `0x14000b327`
- `KERNEL32!LocalFree` at `0x14000b335`
- `KERNEL32!LocalFree` at `0x14000b327`
- `KERNEL32!LocalFree` at `0x14000b335`
- `KERNEL32!SetLastError` at `0x14000b064`
- `KERNEL32!SetLastError` at `0x14000b178`
- `KERNEL32!SetLastError` at `0x14000b064`
- `KERNEL32!SetLastError` at `0x14000b178`
- `KERNEL32!LocalAlloc` at `0x14000b12c`
- `KERNEL32!LocalAlloc` at `0x14000b12c`
- `RPCRT4!UuidCreate` at `0x14000b16c`
- `RPCRT4!UuidCreate` at `0x14000b16c`

## pseudocode

```c
__int64 __fastcall SuGetPoolTemplate(__int64 a1, __int64 *a2, _QWORD *a3)
{
  DWORD v4; // ecx
  unsigned int v5; // esi
  int v6; // r13d
  char v7; // r12
  unsigned int v8; // ecx
  __int64 v9; // r9
  __int64 *v10; // rax
  __int64 v11; // rcx
  int v12; // edx
  char v13; // r15
  unsigned int v14; // ebp
  unsigned int v15; // r14d
  unsigned int v16; // eax
  SIZE_T v17; // rsi
  char *v18; // rax
  char *v19; // rbx
  RPC_STATUS v20; // eax
  unsigned int Pool; // eax
  char *v22; // rcx
  _OWORD *v23; // r8
  __int64 v24; // rdx
  __int64 v25; // xmm0_8
  char *v26; // rdx
  __int64 i; // rax
  __int128 v29; // [rsp+30h] [rbp-68h] BYREF
  int v30; // [rsp+40h] [rbp-58h]
  int v31; // [rsp+A0h] [rbp+8h]
  unsigned int v32; // [rsp+A8h] [rbp+10h]
  HLOCAL hMem; // [rsp+B8h] [rbp+20h] BYREF

  v30 = 0;
  v29 = 0;
  hMem = 0;
  if ( (__int64 *)*a2 == a2 )
  {
    v4 = 87;
LABEL_3:
    SetLastError(v4);
    return 0;
  }
  v6 = 0;
  v7 = 1;
  v8 = 2
     * (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SpacesPoolVersion2700>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SpacesPoolVersion2700>::GetImpl'::`2'::impl)
     + 29;
  v10 = (__int64 *)*a2;
  v32 = v8;
  while ( v10 != a2 )
  {
    v10 = (__int64 *)*v10;
    ++v6;
  }
  v5 = SiSelectMetadataDrives(v8, (__int64)&v29, 0, v9, a2);
  if ( v5 )
  {
    v11 = *a2;
    v12 = 0;
    v13 = 0;
    v31 = 0;
    v14 = 512;
    v15 = 4096;
    if ( (__int64 *)*a2 != a2 )
    {
      do
      {
        if ( (*(_BYTE *)(v11 + 20) & 4) != 0 )
          ++v12;
        v13 |= *(_BYTE *)(v11 + 2833);
        if ( v14 <= *(_DWORD *)(v11 + 2712) )
          v14 = *(_DWORD *)(v11 + 2712);
        v16 = *(_DWORD *)(v11 + 2716);
        v11 = *(_QWORD *)v11;
        if ( v15 <= v16 )
          v15 = v16;
      }
      while ( (__int64 *)v11 != a2 );
      v31 = v12;
    }
    v17 = (unsigned int)(16 * (v6 + v12 + 177));
    v18 = (char *)LocalAlloc(0x40u, v17);
    v19 = v18;
    if ( !v18 )
    {
      v4 = 1450;
      goto LABEL_3;
    }
    *(_DWORD *)v18 = 2832;
    *((_DWORD *)v18 + 1) = v17;
    v18[2584] = 0;
    v18[2586] = v13;
    *((_DWORD *)v18 + 647) = v32;
    v20 = UuidCreate((UUID *)(v18 + 8));
    if ( v20 )
    {
      SetLastError(v20);
      v5 = 0;
LABEL_33:
      LocalFree(v19);
      return v5;
    }
    Pool = SiGetPool(&GUID_NULL, 0, (struct _SU_POOL_OBJECT **)&hMem);
    v22 = (char *)hMem;
    v5 = Pool;
    if ( Pool )
    {
      v19[2668] = *((_BYTE *)hMem + 2724);
      v19[2669] = v22[2725];
      if ( !v13 )
        v7 = v22[2726];
      v19[2670] = v7;
      v23 = v19 + 2832;
      v19[2671] = v22[2727];
      v19[2672] = v22[2728];
      *((_DWORD *)v19 + 669) = *((_DWORD *)v22 + 683);
      *((_QWORD *)v19 + 335) = *((_QWORD *)v22 + 342);
      v24 = (unsigned int)(16 * (v6 + 177));
      *((_OWORD *)v19 + 168) = *(_OWORD *)(v22 + 2744);
      *((_OWORD *)v19 + 169) = *(_OWORD *)(v22 + 2760);
      *((_DWORD *)v19 + 680) = *((_DWORD *)v22 + 694);
      *((_OWORD *)v19 + 175) = *(_OWORD *)(v22 + 2856);
      *((_QWORD *)v19 + 352) = *((_QWORD *)v22 + 359);
      *((_DWORD *)v19 + 662) = *((_DWORD *)v22 + 676);
      *((_DWORD *)v19 + 665) = v14;
      *((_DWORD *)v19 + 666) = v15;
      *(_OWORD *)(v19 + 2724) = *(_OWORD *)(v22 + 2780);
      *(_OWORD *)(v19 + 2740) = *(_OWORD *)(v22 + 2796);
      *(_OWORD *)(v19 + 2756) = *(_OWORD *)(v22 + 2812);
      *(_OWORD *)(v19 + 2772) = *(_OWORD *)(v22 + 2828);
      v25 = *(_QWORD *)(v22 + 2844);
      *((_DWORD *)v19 + 661) = v24;
      v26 = &v19[v24];
      *(_QWORD *)(v19 + 2788) = v25;
      *((_DWORD *)v19 + 658) = v6;
      *((_DWORD *)v19 + 659) = 2832;
      *((_DWORD *)v19 + 660) = v31;
      for ( i = *a2; (__int64 *)i != a2; i = *(_QWORD *)i )
      {
        *v23++ = *(_OWORD *)(i + 56);
        if ( (*(_BYTE *)(i + 20) & 4) != 0 )
        {
          *(_OWORD *)v26 = *(_OWORD *)(i + 56);
          v26 += 16;
        }
      }
      *a3 = v19;
      v19 = 0;
    }
    if ( v22 )
      LocalFree(v22);
    if ( v19 )
      goto LABEL_33;
  }
  return v5;
}

```

## disassembly

```asm
0x14000b02c  mov     r11, rsp
0x14000b02f  mov     [r11+18h], r8
0x14000b033  mov     [rsp+arg_0], ecx
0x14000b037  push    rbx
0x14000b038  push    rbp
0x14000b039  push    rsi
0x14000b03a  push    rdi
0x14000b03b  push    r12
0x14000b03d  push    r13
0x14000b03f  push    r14
0x14000b041  push    r15
0x14000b043  sub     rsp, 58h
0x14000b047  xor     eax, eax
0x14000b049  xorps   xmm0, xmm0
0x14000b04c  mov     rdi, rdx
0x14000b04f  mov     [rsp+98h+var_58], eax
0x14000b053  movups  [rsp+98h+var_68], xmm0
0x14000b058  mov     [r11+20h], rax
0x14000b05c  cmp     [rdx], rdx
0x14000b05f  jnz     short loc_14000B071
0x14000b061  lea     ecx, [rax+57h]; dwErrCode
0x14000b064  call    cs:__imp_SetLastError
0x14000b06a  xor     esi, esi
0x14000b06c  jmp     loc_14000B33B
0x14000b071  xor     r13d, r13d
0x14000b074  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SpacesPoolVersion2700@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SpacesPoolVersion2700@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SpacesPoolVersion2700> `wil::Feature<__WilFeatureTraits_Feature_SpacesPoolVersion2700>::GetImpl(void)'::`2'::impl
0x14000b07b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SpacesPoolVersion2700@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SpacesPoolVersion2700>::__private_IsEnabled(void)
0x14000b080  movzx   eax, al
0x14000b083  lea     r12d, [r13+1]
0x14000b087  lea     ecx, ds:1Dh[rax*2]
0x14000b08e  mov     rax, [rdi]
0x14000b091  mov     [rsp+98h+arg_8], ecx
0x14000b098  jmp     short loc_14000B0A0
0x14000b09a  mov     rax, [rax]
0x14000b09d  add     r13d, r12d
0x14000b0a0  cmp     rax, rdi
0x14000b0a3  jnz     short loc_14000B09A
0x14000b0a5  xor     r8d, r8d
0x14000b0a8  mov     [rsp+98h+var_78], rdi
0x14000b0ad  lea     rdx, [rsp+98h+var_68]
0x14000b0b2  call    ?SiSelectMetadataDrives@@YAHW4_SC_VERSION@@PEAU_SP_IDS@@PEAU_SP_FD_IDS@@1PEAU_LIST_ENTRY@@@Z; SiSelectMetadataDrives(_SC_VERSION,_SP_IDS *,_SP_FD_IDS *,_SP_IDS *,_LIST_ENTRY *)
0x14000b0b7  mov     esi, eax
0x14000b0b9  test    eax, eax
0x14000b0bb  jz      loc_14000B33B
0x14000b0c1  mov     rcx, [rdi]
0x14000b0c4  xor     edx, edx
0x14000b0c6  xor     r15b, r15b
0x14000b0c9  mov     [rsp+98h+arg_0], edx
0x14000b0d0  mov     ebp, 200h
0x14000b0d5  mov     r14d, 1000h
0x14000b0db  cmp     rcx, rdi
0x14000b0de  jz      short loc_14000B117
0x14000b0e0  test    byte ptr [rcx+14h], 4
0x14000b0e4  jz      short loc_14000B0E9
0x14000b0e6  add     edx, r12d
0x14000b0e9  or      r15b, [rcx+0B11h]
0x14000b0f0  mov     eax, [rcx+0A98h]
0x14000b0f6  cmp     ebp, eax
0x14000b0f8  cmovbe  ebp, eax
0x14000b0fb  mov     eax, [rcx+0A9Ch]
0x14000b101  mov     rcx, [rcx]
0x14000b104  cmp     r14d, eax
0x14000b107  cmovbe  r14d, eax
0x14000b10b  cmp     rcx, rdi
0x14000b10e  jnz     short loc_14000B0E0
0x14000b110  mov     [rsp+98h+arg_0], edx
0x14000b117  lea     eax, [rdx+0B1h]
0x14000b11d  mov     ecx, 40h ; '@'; uFlags
0x14000b122  add     eax, r13d
0x14000b125  shl     eax, 4
0x14000b128  mov     edx, eax; uBytes
0x14000b12a  mov     esi, eax
0x14000b12c  call    cs:__imp_LocalAlloc
0x14000b132  mov     rbx, rax
0x14000b135  test    rax, rax
0x14000b138  jnz     short loc_14000B144
0x14000b13a  mov     ecx, 5AAh
0x14000b13f  jmp     loc_14000B064
0x14000b144  mov     dword ptr [rax], 0B10h
0x14000b14a  lea     rcx, [rbx+8]; Uuid
0x14000b14e  mov     [rax+4], esi
0x14000b151  mov     byte ptr [rax+0A18h], 0
0x14000b158  mov     [rax+0A1Ah], r15b
0x14000b15f  mov     eax, [rsp+98h+arg_8]
0x14000b166  mov     [rbx+0A1Ch], eax
0x14000b16c  call    cs:__imp_UuidCreate
0x14000b172  test    eax, eax
0x14000b174  jz      short loc_14000B185
0x14000b176  mov     ecx, eax; dwErrCode
0x14000b178  call    cs:__imp_SetLastError
0x14000b17e  xor     esi, esi
0x14000b180  jmp     loc_14000B332
0x14000b185  lea     r8, [rsp+98h+hMem]; struct _SU_POOL_OBJECT **
0x14000b18d  xor     edx, edx; unsigned int
0x14000b18f  lea     rcx, GUID_NULL; struct _GUID *
0x14000b196  call    ?SiGetPool@@YAHPEAU_GUID@@KPEAPEAU_SU_POOL_OBJECT@@@Z; SiGetPool(_GUID *,ulong,_SU_POOL_OBJECT * *)
0x14000b19b  mov     rcx, [rsp+98h+hMem]; hMem
0x14000b1a3  mov     esi, eax
0x14000b1a5  test    eax, eax
0x14000b1a7  jz      loc_14000B322
0x14000b1ad  mov     al, [rcx+0AA4h]
0x14000b1b3  mov     [rbx+0A6Ch], al
0x14000b1b9  mov     al, [rcx+0AA5h]
0x14000b1bf  mov     [rbx+0A6Dh], al
0x14000b1c5  test    r15b, r15b
0x14000b1c8  jnz     short loc_14000B1D1
0x14000b1ca  mov     r12b, [rcx+0AA6h]
0x14000b1d1  mov     [rbx+0A6Eh], r12b
0x14000b1d8  lea     edx, [r13+0B1h]
0x14000b1df  mov     al, [rcx+0AA7h]
0x14000b1e5  lea     r8, [rbx+0B10h]
0x14000b1ec  mov     [rbx+0A6Fh], al
0x14000b1f2  mov     al, [rcx+0AA8h]
0x14000b1f8  mov     [rbx+0A70h], al
0x14000b1fe  mov     eax, [rcx+0AACh]
0x14000b204  mov     [rbx+0A74h], eax
0x14000b20a  mov     rax, [rcx+0AB0h]
0x14000b211  mov     [rbx+0A78h], rax
0x14000b218  movups  xmm0, xmmword ptr [rcx+0AB8h]
0x14000b21f  shl     edx, 4
0x14000b222  movups  xmmword ptr [rbx+0A80h], xmm0
0x14000b229  movups  xmm1, xmmword ptr [rcx+0AC8h]
0x14000b230  movups  xmmword ptr [rbx+0A90h], xmm1
0x14000b237  mov     eax, [rcx+0AD8h]
0x14000b23d  mov     [rbx+0AA0h], eax
0x14000b243  movups  xmm0, xmmword ptr [rcx+0B28h]
0x14000b24a  movups  xmmword ptr [rbx+0AF0h], xmm0
0x14000b251  movsd   xmm1, qword ptr [rcx+0B38h]
0x14000b259  movsd   qword ptr [rbx+0B00h], xmm1
0x14000b261  mov     eax, [rcx+0A90h]
0x14000b267  mov     [rbx+0A58h], eax
0x14000b26d  mov     eax, [rsp+98h+arg_0]
0x14000b274  mov     [rbx+0A64h], ebp
0x14000b27a  mov     [rbx+0A68h], r14d
0x14000b281  movups  xmm0, xmmword ptr [rcx+0ADCh]
0x14000b288  movups  xmmword ptr [rbx+0AA4h], xmm0
0x14000b28f  movups  xmm1, xmmword ptr [rcx+0AECh]
0x14000b296  movups  xmmword ptr [rbx+0AB4h], xmm1
0x14000b29d  movups  xmm0, xmmword ptr [rcx+0AFCh]
0x14000b2a4  movups  xmmword ptr [rbx+0AC4h], xmm0
0x14000b2ab  movups  xmm1, xmmword ptr [rcx+0B0Ch]
0x14000b2b2  movups  xmmword ptr [rbx+0AD4h], xmm1
0x14000b2b9  movsd   xmm0, qword ptr [rcx+0B1Ch]
0x14000b2c1  mov     [rbx+0A54h], edx
0x14000b2c7  add     rdx, rbx
0x14000b2ca  movsd   qword ptr [rbx+0AE4h], xmm0
0x14000b2d2  mov     [rbx+0A48h], r13d
0x14000b2d9  mov     dword ptr [rbx+0A4Ch], 0B10h
0x14000b2e3  mov     [rbx+0A50h], eax
0x14000b2e9  mov     rax, [rdi]
0x14000b2ec  jmp     short loc_14000B310
0x14000b2ee  movups  xmm0, xmmword ptr [rax+38h]
0x14000b2f2  movdqu  xmmword ptr [r8], xmm0
0x14000b2f7  test    byte ptr [rax+14h], 4
0x14000b2fb  lea     r8, [r8+10h]
0x14000b2ff  jz      short loc_14000B30D
0x14000b301  movups  xmm0, xmmword ptr [rax+38h]
0x14000b305  movdqu  xmmword ptr [rdx], xmm0
0x14000b309  add     rdx, 10h
0x14000b30d  mov     rax, [rax]
0x14000b310  cmp     rax, rdi
0x14000b313  jnz     short loc_14000B2EE
0x14000b315  mov     rax, [rsp+98h+arg_10]
0x14000b31d  mov     [rax], rbx
0x14000b320  xor     ebx, ebx
0x14000b322  test    rcx, rcx
0x14000b325  jz      short loc_14000B32D
0x14000b327  call    cs:__imp_LocalFree
0x14000b32d  test    rbx, rbx
0x14000b330  jz      short loc_14000B33B
0x14000b332  mov     rcx, rbx; hMem
0x14000b335  call    cs:__imp_LocalFree
0x14000b33b  mov     eax, esi
0x14000b33d  add     rsp, 58h
0x14000b341  pop     r15
0x14000b343  pop     r14
0x14000b345  pop     r13
0x14000b347  pop     r12
0x14000b349  pop     rdi
0x14000b34a  pop     rsi
0x14000b34b  pop     rbp
0x14000b34c  pop     rbx
0x14000b34d  retn
```
