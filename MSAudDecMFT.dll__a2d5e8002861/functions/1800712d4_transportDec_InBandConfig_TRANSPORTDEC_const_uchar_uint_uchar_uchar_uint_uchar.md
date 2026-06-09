# transportDec_InBandConfig(TRANSPORTDEC * const,uchar *,uint,uchar,uchar *,uint,uchar *)

- ea: `0x1800712d4`
- end: `0x1800716cd`
- name: `?transportDec_InBandConfig@@YA?AW4TRANSPORTDEC_ERROR@@QEAUTRANSPORTDEC@@PEAEIE1I1@Z`
- size: `1017`
- prototype: `__int64 __fastcall(__int64, const void *, unsigned int, __int64, _BYTE *, __int64, _BYTE *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180047994`

## callees

- `0x18000e9b0`
- `0x18001115c`
- `0x180011da8`
- `0x1800712d4`
- `0x180096060`
- `0x18009606c`
- `0x1800960c0`

## pseudocode

```c
__int64 __fastcall transportDec_InBandConfig(
        __int64 a1,
        const void *a2,
        unsigned int a3,
        __int64 a4,
        _BYTE *a5,
        __int64 a6,
        _BYTE *a7)
{
  _BYTE *v7; // rdi
  char v8; // r14
  const void *v9; // r13
  size_t v10; // r12
  char v12; // al
  unsigned int v14; // esi
  void (__fastcall *v15)(_QWORD, __int64, _QWORD); // rax
  int v16; // ecx
  _BYTE *v17; // r14
  unsigned int (__fastcall *v18)(_QWORD, __int64, _QWORD); // rax
  char v19; // cl
  int v20; // r14d
  __int64 v21; // r8
  __int64 v22; // rcx
  unsigned int (__fastcall *v23)(__int64, __int64, _QWORD); // rax
  int v24; // [rsp+20h] [rbp-50h]
  int v25; // [rsp+28h] [rbp-48h]
  __int64 v26; // [rsp+40h] [rbp-30h] BYREF
  int v27; // [rsp+48h] [rbp-28h]
  __int64 v28; // [rsp+4Ch] [rbp-24h]
  int v29; // [rsp+54h] [rbp-1Ch]
  const void *v30; // [rsp+58h] [rbp-18h]
  int v31; // [rsp+60h] [rbp-10h]
  int v32; // [rsp+64h] [rbp-Ch]
  __int64 v33; // [rsp+68h] [rbp-8h]
  int v35; // [rsp+C0h] [rbp+50h]
  char v36; // [rsp+C8h] [rbp+58h]

  v7 = (_BYTE *)(a1 + 3827);
  v8 = *(_BYTE *)(a1 + 3825);
  v9 = a2;
  v10 = a3;
  v30 = a2;
  v33 = 0;
  v35 = 0;
  *a7 = 0;
  v27 = 8 * a3;
  v28 = 0;
  v29 = 0;
  v31 = 512;
  v32 = 4096;
  v26 = 0;
  if ( v8 )
  {
    v14 = 0;
    goto LABEL_29;
  }
  if ( *v7 == 5 || *(_DWORD *)(a1 + 1512) != 42 )
  {
    v14 = 0;
LABEL_25:
    if ( *v7 == 5 )
      goto LABEL_38;
    *(_BYTE *)(a1 + 3824) = 0;
    *(_BYTE *)(a1 + 3826) = 0;
    *v7 = 0;
    if ( *(_DWORD *)(a1 + 1512) != 42 )
      goto LABEL_53;
    *(_BYTE *)(a1 + 3825) = 3;
    goto LABEL_31;
  }
  if ( ((unsigned int)*(unsigned __int16 *)(a1 + 1040) + 7) >> 3 == a3 )
  {
    if ( !memcmp_0(a2, (const void *)(a1 + 527), a3) )
    {
      if ( !*(_BYTE *)(a1 + 230) )
      {
        *a5 = 0;
        return 0;
      }
      *(_BYTE *)(a1 + 230) = 0;
      v12 = 0;
      *(_WORD *)(a1 + 3824) = 768;
      v8 = 3;
      *(_BYTE *)(a1 + 3826) = 0;
      *v7 = 0;
    }
    else
    {
      *a7 = 1;
      v12 = 1;
    }
    if ( !v12 )
      goto LABEL_16;
  }
  else
  {
    *a7 = 1;
  }
  if ( *(_DWORD *)a1 == 6 || *(_DWORD *)a1 == 7 || *(_DWORD *)a1 == 10 )
  {
    (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(a1 + 40))(*(_QWORD *)(a1 + 48), a1 + 312, 0);
    *(_WORD *)(a1 + 230) = 256;
    v14 = 1025;
    goto LABEL_19;
  }
LABEL_16:
  v14 = 0;
  if ( !v8 )
    goto LABEL_25;
LABEL_29:
  if ( v8 != 2 && v8 != 3 )
    goto LABEL_38;
LABEL_31:
  v16 = *(_DWORD *)(a1 + 1512);
  v17 = (_BYTE *)(a1 + 3824);
  if ( *(char *)(a1 + 3824) >= (v16 == 42) )
  {
    *v17 = 0;
    *(_BYTE *)(a1 + 3825) = 0;
    *(_BYTE *)(a1 + 3830) = 0;
    if ( v16 == 42 )
    {
      *(_BYTE *)(a1 + 3826) = 0;
      *v7 = 3;
    }
  }
  v18 = *(unsigned int (__fastcall **)(_QWORD, __int64, _QWORD))(a1 + 56);
  if ( v18 && v18(*(_QWORD *)(a1 + 64), a1 + 3824, 0) )
    v14 = 1025;
  if ( (unsigned __int8)(*(_BYTE *)(a1 + 3825) - 2) > 1u )
  {
LABEL_38:
    if ( *(_DWORD *)(a1 + 1512) == 42 )
    {
      v35 = 1;
      if ( !v14 )
      {
        v19 = 1;
        v36 = 1;
        v20 = 0;
        *a5 = 0;
        while ( 1 )
        {
          if ( v20 > 0 )
          {
            CDKsyncCache_0(&v26);
            CDKpushBack(&v26, (unsigned int)(8 * v10 - v27));
            v19 = 2;
            v36 = 2;
          }
          LOBYTE(v25) = *a5;
          LOBYTE(v24) = v19;
          v14 = AudioSpecificConfig_Parse(a1 + 2068, &v26, 0, a1 + 8, v24, v25, *(_DWORD *)(a1 + 1512));
          if ( v14 )
            break;
          memcpy_0((void *)(a1 + 312), (const void *)(a1 + 2068), 0x6DCu);
          LOBYTE(v21) = *(_BYTE *)(a1 + 1546);
          if ( (*(unsigned int (__fastcall **)(_QWORD, __int64, __int64, __int64))(a1 + 8))(
                 *(_QWORD *)(a1 + 16),
                 a1 + 312,
                 v21,
                 a1 + 1547)
            || !v20
            && (*(_BYTE *)(a1 + 1547) || *(_BYTE *)(a1 + 1548) || *(_BYTE *)(a1 + 1549))
            && (v22 = *(_QWORD *)(a1 + 48),
                v23 = *(unsigned int (__fastcall **)(__int64, __int64, _QWORD))(a1 + 40),
                *a5 = 1,
                v23(v22, a1 + 312, 0)) )
          {
            v14 = 1025;
            goto LABEL_19;
          }
          if ( ++v20 >= 2 )
          {
            v9 = a2;
            goto LABEL_56;
          }
          v19 = v36;
        }
      }
      goto LABEL_19;
    }
LABEL_53:
    if ( !v14 )
    {
LABEL_56:
      if ( *(_DWORD *)(a1 + 1512) == 42 )
      {
        *(_WORD *)(a1 + 1040) = 8 * v10;
        memcpy_0((void *)(a1 + 527), v9, v10);
        *(_WORD *)(a1 + 3824) = 0;
        *(_BYTE *)(a1 + 3826) = 0;
        *v7 = 0;
      }
      if ( v35 )
        *(_DWORD *)(a1 + 3872) |= 0x20u;
      return v14;
    }
LABEL_19:
    *(_DWORD *)(a1 + 3844) = 0;
    *(_BYTE *)(a1 + 3824) = 0;
    *(_WORD *)(a1 + 3825) = 0;
    *v7 = 0;
    *(_WORD *)(a1 + 3828) = 0;
    *(_BYTE *)(a1 + 3830) = 0;
    v15 = *(void (__fastcall **)(_QWORD, __int64, _QWORD))(a1 + 56);
    if ( v15 )
      v15(*(_QWORD *)(a1 + 64), a1 + 3824, 0);
    return v14;
  }
  ++*v17;
  return v14;
}

```

## disassembly

```asm
0x1800712d4  mov     [rsp-38h+arg_0], rbx
0x1800712d9  mov     [rsp-38h+arg_18], r9b
0x1800712de  mov     [rsp-38h+arg_8], rdx
0x1800712e3  push    rbp
0x1800712e4  push    rsi
0x1800712e5  push    rdi
0x1800712e6  push    r12
0x1800712e8  push    r13
0x1800712ea  push    r14
0x1800712ec  push    r15
0x1800712ee  mov     rbp, rsp
0x1800712f1  sub     rsp, 70h
0x1800712f5  mov     rsi, [rbp+arg_30]
0x1800712f9  lea     rdi, [rcx+0EF3h]
0x180071300  mov     r14b, [rcx+0EF1h]
0x180071307  mov     r13, rdx
0x18007130a  mov     r12d, r8d
0x18007130d  mov     rbx, rcx
0x180071310  xor     r8d, r8d
0x180071313  mov     [rbp+var_18], rdx
0x180071317  mov     [rbp+var_8], r8
0x18007131b  mov     r15d, 401h
0x180071321  mov     [rbp+arg_10], r8d
0x180071325  mov     [rsi], r8b
0x180071328  lea     eax, ds:0[r12*8]
0x180071330  mov     [rbp+var_28], eax
0x180071333  mov     [rbp+var_24], r8
0x180071337  mov     [rbp+var_1C], r8d
0x18007133b  mov     [rbp+var_10], 200h
0x180071342  mov     [rbp+var_C], 1000h
0x180071349  mov     [rbp+var_30], r8
0x18007134d  test    r14b, r14b
0x180071350  jnz     loc_1800714B8
0x180071356  cmp     byte ptr [rdi], 5
0x180071359  jz      loc_180071485
0x18007135f  cmp     dword ptr [rcx+5E8h], 2Ah ; '*'
0x180071366  jnz     loc_180071485
0x18007136c  movzx   eax, word ptr [rcx+410h]
0x180071373  add     eax, 7
0x180071376  shr     eax, 3
0x180071379  cmp     eax, r12d
0x18007137c  jnz     short loc_1800713DB
0x18007137e  lea     rdx, [rcx+20Fh]; Buf2
0x180071385  mov     r8d, r12d; Size
0x180071388  mov     rcx, r13; Buf1
0x18007138b  call    memcmp_0
0x180071390  xor     r8d, r8d
0x180071393  test    eax, eax
0x180071395  jnz     short loc_1800713D0
0x180071397  cmp     [rbx+0E6h], r8b
0x18007139e  jz      short loc_1800713C2
0x1800713a0  mov     [rbx+0E6h], r8b
0x1800713a7  mov     al, r8b
0x1800713aa  mov     word ptr [rbx+0EF0h], 300h
0x1800713b3  mov     r14b, 3
0x1800713b6  mov     [rbx+0EF2h], r8b
0x1800713bd  mov     [rdi], r8b
0x1800713c0  jmp     short loc_1800713D5
0x1800713c2  mov     rax, [rbp+arg_20]
0x1800713c6  mov     [rax], r8b
0x1800713c9  xor     eax, eax
0x1800713cb  jmp     loc_1800716B4
0x1800713d0  mov     byte ptr [rsi], 1
0x1800713d3  mov     al, 1
0x1800713d5  test    al, al
0x1800713d7  jnz     short loc_1800713DE
0x1800713d9  jmp     short loc_1800713EF
0x1800713db  mov     byte ptr [rsi], 1
0x1800713de  mov     ecx, [rbx]
0x1800713e0  sub     ecx, 6
0x1800713e3  jz      short loc_180071400
0x1800713e5  sub     ecx, 1
0x1800713e8  jz      short loc_180071400
0x1800713ea  cmp     ecx, 3
0x1800713ed  jz      short loc_180071400
0x1800713ef  mov     esi, r8d
0x1800713f2  test    r14b, r14b
0x1800713f5  jnz     loc_1800714BB
0x1800713fb  jmp     loc_180071488
0x180071400  mov     rcx, [rbx+30h]
0x180071404  lea     rdx, [rbx+138h]
0x18007140b  mov     rax, [rbx+28h]
0x18007140f  call    cs:__guard_dispatch_icall_fptr
0x180071415  xor     r8d, r8d
0x180071418  mov     word ptr [rbx+0E6h], 100h
0x180071421  mov     esi, r15d
0x180071424  mov     [rbx+0F04h], r8d
0x18007142b  lea     rdx, [rbx+0EF0h]
0x180071432  mov     [rdx], r8b
0x180071435  mov     word ptr [rbx+0EF1h], 0
0x18007143e  mov     [rdi], r8b
0x180071441  mov     word ptr [rbx+0EF4h], 0
0x18007144a  mov     [rbx+0EF6h], r8b
0x180071451  mov     rax, [rbx+38h]
0x180071455  test    rax, rax
0x180071458  jz      short loc_180071467
0x18007145a  mov     rcx, [rbx+40h]
0x18007145e  call    cs:__guard_dispatch_icall_fptr
0x180071464  xor     r8d, r8d
0x180071467  test    esi, esi
0x180071469  jnz     loc_1800716B2
0x18007146f  cmp     [rbp+arg_10], r8d
0x180071473  jz      loc_1800716B2
0x180071479  or      dword ptr [rbx+0F20h], 20h
0x180071480  jmp     loc_1800716B2
0x180071485  mov     esi, r8d
0x180071488  cmp     byte ptr [rdi], 5
0x18007148b  jz      loc_18007152E
0x180071491  mov     [rbx+0EF0h], r8b
0x180071498  mov     [rbx+0EF2h], r8b
0x18007149f  mov     [rdi], r8b
0x1800714a2  cmp     dword ptr [rbx+5E8h], 2Ah ; '*'
0x1800714a9  jnz     loc_180071659
0x1800714af  mov     byte ptr [rbx+0EF1h], 3
0x1800714b6  jmp     short loc_1800714C7
0x1800714b8  mov     esi, r8d
0x1800714bb  cmp     r14b, 2
0x1800714bf  jz      short loc_1800714C7
0x1800714c1  cmp     r14b, 3
0x1800714c5  jnz     short loc_18007152E
0x1800714c7  mov     ecx, [rbx+5E8h]
0x1800714cd  lea     r14, [rbx+0EF0h]
0x1800714d4  cmp     ecx, 2Ah ; '*'
0x1800714d7  setz    al
0x1800714da  cmp     [r14], al
0x1800714dd  jl      short loc_1800714FF
0x1800714df  mov     [r14], r8b
0x1800714e2  mov     [rbx+0EF1h], r8b
0x1800714e9  mov     [rbx+0EF6h], r8b
0x1800714f0  cmp     ecx, 2Ah ; '*'
0x1800714f3  jnz     short loc_1800714FF
0x1800714f5  mov     [rbx+0EF2h], r8b
0x1800714fc  mov     byte ptr [rdi], 3
0x1800714ff  mov     rax, [rbx+38h]
0x180071503  test    rax, rax
0x180071506  jz      short loc_18007151E
0x180071508  mov     rcx, [rbx+40h]
0x18007150c  mov     rdx, r14
0x18007150f  call    cs:__guard_dispatch_icall_fptr
0x180071515  xor     r8d, r8d
0x180071518  test    eax, eax
0x18007151a  cmovnz  esi, r15d
0x18007151e  mov     al, [rbx+0EF1h]
0x180071524  sub     al, 2
0x180071526  cmp     al, 1
0x180071528  jbe     loc_1800716AF
0x18007152e  cmp     dword ptr [rbx+5E8h], 2Ah ; '*'
0x180071535  jnz     loc_180071659
0x18007153b  mov     [rbp+arg_10], 1
0x180071542  test    esi, esi
0x180071544  jnz     loc_180071424
0x18007154a  mov     r15, [rbp+arg_20]
0x18007154e  mov     cl, 1
0x180071550  mov     [rbp+arg_18], cl
0x180071553  mov     r14d, r8d
0x180071556  mov     [r15], r8b
0x180071559  lea     r13, [rbx+814h]
0x180071560  lea     rsi, [rbx+8]
0x180071564  test    r14d, r14d
0x180071567  jle     short loc_18007158B
0x180071569  lea     rcx, [rbp+var_30]
0x18007156d  call    CDKsyncCache_0
0x180071572  lea     edx, ds:0[r12*8]
0x18007157a  sub     edx, [rbp+var_28]
0x18007157d  lea     rcx, [rbp+var_30]
0x180071581  call    CDKpushBack
0x180071586  mov     cl, 2
0x180071588  mov     [rbp+arg_18], cl
0x18007158b  mov     eax, [rbx+5E8h]
0x180071591  lea     rdx, [rbp+var_30]
0x180071595  mov     [rsp+70h+var_40], eax
0x180071599  mov     r9, rsi
0x18007159c  mov     al, [r15]
0x18007159f  xor     r8d, r8d
0x1800715a2  mov     [rsp+70h+var_48], al
0x1800715a6  mov     [rsp+70h+var_50], cl
0x1800715aa  mov     rcx, r13
0x1800715ad  call    ?AudioSpecificConfig_Parse@@YA?AW4TRANSPORTDEC_ERROR@@PEAUCSAudioSpecificConfig@@PEAUCDK_BITSTREAM@@HPEAUCSTpCallBacks@@EEW4AUDIO_OBJECT_TYPE@@@Z; AudioSpecificConfig_Parse(CSAudioSpecificConfig *,CDK_BITSTREAM *,int,CSTpCallBacks *,uchar,uchar,AUDIO_OBJECT_TYPE)
0x1800715b2  xor     r8d, r8d
0x1800715b5  mov     esi, eax
0x1800715b7  test    eax, eax
0x1800715b9  jnz     loc_180071424
0x1800715bf  lea     rcx, [rbx+138h]; void *
0x1800715c6  mov     rdx, r13; Src
0x1800715c9  mov     r8d, 6DCh; Size
0x1800715cf  call    memcpy_0
0x1800715d4  mov     r8b, [rbx+60Ah]
0x1800715db  lea     r13, [rbx+60Bh]
0x1800715e2  mov     rcx, [rbx+10h]
0x1800715e6  lea     rdx, [rbx+138h]
0x1800715ed  mov     rax, [rbx+8]
0x1800715f1  mov     r9, r13
0x1800715f4  call    cs:__guard_dispatch_icall_fptr
0x1800715fa  xor     r8d, r8d
0x1800715fd  test    eax, eax
0x1800715ff  jnz     short loc_18007164F
0x180071601  test    r14d, r14d
0x180071604  jnz     short loc_18007163E
0x180071606  cmp     [r13+0], r8b
0x18007160a  jnz     short loc_18007161E
0x18007160c  cmp     [rbx+60Ch], r8b
0x180071613  jnz     short loc_18007161E
0x180071615  cmp     [rbx+60Dh], r8b
0x18007161c  jz      short loc_18007163E
0x18007161e  mov     rcx, [rbx+30h]
0x180071622  lea     rdx, [rbx+138h]
0x180071629  mov     rax, [rbx+28h]
0x18007162d  mov     byte ptr [r15], 1
0x180071631  call    cs:__guard_dispatch_icall_fptr
0x180071637  xor     r8d, r8d
0x18007163a  test    eax, eax
0x18007163c  jnz     short loc_18007164F
0x18007163e  inc     r14d
0x180071641  cmp     r14d, 2
0x180071645  jge     short loc_180071663
0x180071647  mov     cl, [rbp+arg_18]
0x18007164a  jmp     loc_180071559
0x18007164f  mov     esi, 401h
0x180071654  jmp     loc_180071424
0x180071659  test    esi, esi
0x18007165b  jnz     loc_180071424
0x180071661  jmp     short loc_180071667
0x180071663  mov     r13, [rbp+arg_8]
0x180071667  cmp     dword ptr [rbx+5E8h], 2Ah ; '*'
0x18007166e  jnz     loc_18007146F
0x180071674  movzx   eax, r12w
0x180071678  lea     rcx, [rbx+20Fh]; void *
0x18007167f  shl     ax, 3
0x180071683  mov     r8, r12; Size
0x180071686  mov     rdx, r13; Src
0x180071689  mov     [rbx+410h], ax
0x180071690  call    memcpy_0
0x180071695  xor     r8d, r8d
0x180071698  mov     [rbx+0EF0h], r8w
0x1800716a0  mov     [rbx+0EF2h], r8b
0x1800716a7  mov     [rdi], r8b
0x1800716aa  jmp     loc_18007146F
0x1800716af  inc     byte ptr [r14]
0x1800716b2  mov     eax, esi
0x1800716b4  mov     rbx, [rsp+70h+arg_0]
0x1800716bc  add     rsp, 70h
0x1800716c0  pop     r15
0x1800716c2  pop     r14
0x1800716c4  pop     r13
0x1800716c6  pop     r12
0x1800716c8  pop     rdi
0x1800716c9  pop     rsi
0x1800716ca  pop     rbp
0x1800716cb  retn
```
